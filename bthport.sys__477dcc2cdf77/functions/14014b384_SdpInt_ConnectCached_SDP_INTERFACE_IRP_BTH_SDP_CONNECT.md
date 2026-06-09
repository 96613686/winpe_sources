# SdpInt_ConnectCached(_SDP_INTERFACE *,_IRP *,_BTH_SDP_CONNECT *)

- ea: `0x14014b384`
- end: `0x14014b59c`
- name: `?SdpInt_ConnectCached@@YAJPEAU_SDP_INTERFACE@@PEAU_IRP@@PEAU_BTH_SDP_CONNECT@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(struct _SDP_INTERFACE *, struct _IRP *, struct _BTH_SDP_CONNECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1401ef6d0`

## callees

- `0x140005c04`
- `0x140148c48`
- `0x14014b384`
- `0x140161d7c`
- `0x1401eab14`
- `0x1401f06f0`
- `0x1401f270c`
- `0x14020934c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14014b439`
- `ntoskrnl!ZwClose` at `0x14014b56d`
- `ntoskrnl!ZwClose` at `0x14014b439`
- `ntoskrnl!ZwClose` at `0x14014b56d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014b3d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014b3f0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014b3d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014b3f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014b49a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014b49a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014b4d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014b4d1`

## string_xrefs

- `0x14014b3c9`: `DynamicCachedServices`
- `0x14014b3e9`: `CachedServices`

## pseudocode

```c
__int64 __fastcall SdpInt_ConnectCached(struct _SDP_INTERFACE *a1, struct _IRP *a2, struct _BTH_SDP_CONNECT *a3)
{
  bool v3; // zf
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  struct _SECURITY_DATABASE *v8; // rcx
  NTSTATUS v9; // ebx
  void *FileObject; // r8
  struct _SDP_CACHED_CONNECTION *v11; // rax
  _LIST_ENTRY *v12; // r14
  int v13; // edx
  int v14; // ebx
  int v15; // r8d
  unsigned __int64 *p_L2capConnectionListLock; // r15
  KIRQL v17; // al
  _LIST_ENTRY *Blink; // rcx
  _LIST_ENTRY *p_CachedConnectionsList; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+38h] BYREF
  HANDLE v23; // [rsp+A0h] [rbp+40h] BYREF
  HANDLE_SDP v24; // [rsp+A8h] [rbp+48h] BYREF

  v3 = (a3->fSdpConnect & 4) == 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DestinationString = 0;
  Handle = 0;
  v23 = 0;
  if ( v3 )
  {
    RtlInitUnicodeString(&DestinationString, L"CachedServices");
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, L"DynamicCachedServices");
    SdpInt_MigrateCache(a1, &a3->bthAddress);
  }
  if ( (int)SecDB_OpenDeviceKey(v8, &a3->bthAddress, &Handle) < 0 )
    return 3221225629LL;
  v9 = BthOpenKeyEx(Handle, &DestinationString, &v23, a2->RequestorMode == 0 ? 0x200 : 0);
  ZwClose(Handle);
  if ( v9 < 0 )
    return 3221225629LL;
  FileObject = CurrentStackLocation->FileObject;
  if ( !FileObject )
    FileObject = CurrentStackLocation->DeviceObject;
  v11 = SdpCached_Create(a1, v23, FileObject);
  v12 = (_LIST_ENTRY *)v11;
  if ( v11 )
  {
    v24 = 0;
    v14 = HandleManager<void,256>::CreateHandle(&a1->sdpConnectionHandleMgr, v11, &v24);
    if ( v14 < 0 )
    {
      LOBYTE(v13) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v15) = 1;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        v15,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        8,
        21,
        (__int64)WPP_1c8b0d14a8043465701df8be11446151_Traceguids,
        (char)v12,
        v14,
        *(_QWORD *)&DestinationString.Length,
        DestinationString.Buffer);
      RefObj_ReleaseEx(v12, v12, 805, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\sdpinterface.cpp");
    }
    else
    {
      p_L2capConnectionListLock = &a1->L2capConnectionListLock;
      v17 = KeAcquireSpinLockRaiseToDpc(&a1->L2capConnectionListLock);
      Blink = a1->CachedConnectionsList.Blink;
      p_CachedConnectionsList = &a1->CachedConnectionsList;
      if ( Blink->Flink != p_CachedConnectionsList )
        __fastfail(3u);
      v12[2].Blink = Blink;
      v12[2].Flink = p_CachedConnectionsList;
      Blink->Flink = v12 + 2;
      p_CachedConnectionsList->Blink = v12 + 2;
      KeReleaseSpinLock(p_L2capConnectionListLock, v17);
      a3->bthAddress = 0;
      a3->fSdpConnect = 0;
      a3->requestTimeout = 0;
      a3->hConnection = v24;
    }
  }
  else
  {
    ZwClose(v23);
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14014b384  mov     [rsp-28h+arg_0], rbx
0x14014b389  push    rbp
0x14014b38a  push    rsi
0x14014b38b  push    rdi
0x14014b38c  push    r14
0x14014b38e  push    r15
0x14014b390  mov     rbp, rsp
0x14014b393  sub     rsp, 60h
0x14014b397  test    byte ptr [r8+8], 4
0x14014b39c  xorps   xmm0, xmm0
0x14014b39f  mov     r14, [rdx+0B8h]
0x14014b3a6  mov     rsi, rcx
0x14014b3a9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14014b3ad  mov     rdi, r8
0x14014b3b0  mov     [rbp+Handle], 0
0x14014b3b8  mov     rbx, rdx
0x14014b3bb  mov     [rbp+arg_10], 0
0x14014b3c3  lea     rcx, [rbp+DestinationString]; DestinationString
0x14014b3c7  jz      short loc_14014B3E9
0x14014b3c9  lea     rdx, aDynamiccacheds; "DynamicCachedServices"
0x14014b3d0  call    cs:__imp_RtlInitUnicodeString
0x14014b3d7  nop     dword ptr [rax+rax+00h]
0x14014b3dc  mov     rdx, rdi; unsigned __int64 *
0x14014b3df  mov     rcx, rsi; struct _SDP_INTERFACE *
0x14014b3e2  call    ?SdpInt_MigrateCache@@YAJPEAU_SDP_INTERFACE@@PEB_K@Z; SdpInt_MigrateCache(_SDP_INTERFACE *,unsigned __int64 const *)
0x14014b3e7  jmp     short loc_14014B3FC
0x14014b3e9  lea     rdx, aCachedservices; "CachedServices"
0x14014b3f0  call    cs:__imp_RtlInitUnicodeString
0x14014b3f7  nop     dword ptr [rax+rax+00h]
0x14014b3fc  lea     r8, [rbp+Handle]; void **
0x14014b400  mov     rdx, rdi; unsigned __int64 *
0x14014b403  call    ?SecDB_OpenDeviceKey@@YAJPEAU_SECURITY_DATABASE@@PEB_KPEAPEAX@Z; SecDB_OpenDeviceKey(_SECURITY_DATABASE *,unsigned __int64 const *,void * *)
0x14014b408  test    eax, eax
0x14014b40a  js      loc_14014B582
0x14014b410  mov     al, [rbx+40h]
0x14014b413  lea     r8, [rbp+arg_10]
0x14014b417  mov     rcx, [rbp+Handle]
0x14014b41b  lea     rdx, [rbp+DestinationString]
0x14014b41f  neg     al
0x14014b421  sbb     r9d, r9d
0x14014b424  not     r9d
0x14014b427  and     r9d, 200h
0x14014b42e  call    BthOpenKeyEx
0x14014b433  mov     rcx, [rbp+Handle]; Handle
0x14014b437  mov     ebx, eax
0x14014b439  call    cs:__imp_ZwClose
0x14014b440  nop     dword ptr [rax+rax+00h]
0x14014b445  test    ebx, ebx
0x14014b447  js      loc_14014B582
0x14014b44d  mov     r8, [r14+30h]
0x14014b451  test    r8, r8
0x14014b454  jnz     short loc_14014B45A
0x14014b456  mov     r8, [r14+28h]; void *
0x14014b45a  mov     rdx, [rbp+arg_10]; void *
0x14014b45e  mov     rcx, rsi; struct _SDP_INTERFACE *
0x14014b461  call    ?SdpCached_Create@@YAPEAU_SDP_CACHED_CONNECTION@@PEAU_SDP_INTERFACE@@PEAX1@Z; SdpCached_Create(_SDP_INTERFACE *,void *,void *)
0x14014b466  mov     r14, rax
0x14014b469  test    rax, rax
0x14014b46c  jz      loc_14014B569
0x14014b472  lea     rcx, [rsi+0A8h]
0x14014b479  mov     [rbp+arg_18], 0
0x14014b481  lea     r8, [rbp+arg_18]
0x14014b485  mov     rdx, rax
0x14014b488  call    ?CreateHandle@?$HandleManager@X$0BAA@@@QEAAJPEAXPEA_K1@Z; HandleManager<void,256>::CreateHandle(void *,unsigned __int64 *,unsigned __int64 *)
0x14014b48d  mov     ebx, eax
0x14014b48f  test    eax, eax
0x14014b491  js      short loc_14014B4FC
0x14014b493  lea     r15, [rsi+8]
0x14014b497  mov     rcx, r15; SpinLock
0x14014b49a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14014b4a1  nop     dword ptr [rax+rax+00h]
0x14014b4a6  mov     rcx, [rsi+38h]
0x14014b4aa  add     rsi, 30h ; '0'
0x14014b4ae  mov     dl, al; NewIrql
0x14014b4b0  cmp     [rcx], rsi
0x14014b4b3  jz      short loc_14014B4BC
0x14014b4b5  mov     ecx, 3
0x14014b4ba  int     29h; Win8: RtlFailFast(ecx)
0x14014b4bc  lea     rax, [r14+20h]
0x14014b4c0  mov     [rax+8], rcx
0x14014b4c4  mov     [rax], rsi
0x14014b4c7  mov     [rcx], rax
0x14014b4ca  mov     rcx, r15; SpinLock
0x14014b4cd  mov     [rsi+8], rax
0x14014b4d1  call    cs:__imp_KeReleaseSpinLock
0x14014b4d8  nop     dword ptr [rax+rax+00h]
0x14014b4dd  mov     qword ptr [rdi], 0
0x14014b4e4  mov     dword ptr [rdi+8], 0
0x14014b4eb  mov     byte ptr [rdi+14h], 0
0x14014b4ef  mov     rax, [rbp+arg_18]
0x14014b4f3  mov     [rdi+0Ch], rax
0x14014b4f7  jmp     loc_14014B57E
0x14014b4fc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014b503  mov     eax, [rcx+2Ch]
0x14014b506  test    al, al
0x14014b508  jns     short loc_14014B514
0x14014b50a  cmp     byte ptr [rcx+29h], 2
0x14014b50e  jb      short loc_14014B514
0x14014b510  mov     dl, 1
0x14014b512  jmp     short loc_14014B516
0x14014b514  xor     dl, dl
0x14014b516  mov     r9, [rcx+40h]
0x14014b51a  lea     rax, WPP_1c8b0d14a8043465701df8be11446151_Traceguids
0x14014b521  mov     rcx, [rcx+18h]
0x14014b525  mov     r8b, 1
0x14014b528  mov     [rsp+60h+var_18], ebx
0x14014b52c  mov     [rsp+60h+var_20], r14
0x14014b531  mov     [rsp+60h+var_28], rax
0x14014b536  mov     [rsp+60h+var_30], 15h
0x14014b53d  mov     [rsp+60h+var_38], 8
0x14014b545  mov     [rsp+60h+var_40], 2
0x14014b54a  call    WPP_RECORDER_AND_TRACE_SF_qL
0x14014b54f  lea     r9, aOnecoreDrivers_28; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14014b556  mov     r8d, 325h
0x14014b55c  mov     rdx, r14
0x14014b55f  mov     rcx, r14
0x14014b562  call    RefObj_ReleaseEx
0x14014b567  jmp     short loc_14014B57E
0x14014b569  mov     rcx, [rbp+arg_10]; Handle
0x14014b56d  call    cs:__imp_ZwClose
0x14014b574  nop     dword ptr [rax+rax+00h]
0x14014b579  mov     ebx, 0C000009Ah
0x14014b57e  mov     eax, ebx
0x14014b580  jmp     short loc_14014B587
0x14014b582  mov     eax, 0C000009Dh
0x14014b587  mov     rbx, [rsp+60h+arg_0]
0x14014b58f  add     rsp, 60h
0x14014b593  pop     r15
0x14014b595  pop     r14
0x14014b597  pop     rdi
0x14014b598  pop     rsi
0x14014b599  pop     rbp
0x14014b59a  retn
```
