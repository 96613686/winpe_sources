# ScoMp_AddScoCxn(_SCO_INTERFACE *,_SCO_CONNECTION *,long (*)(void *,_BTH_SCO_MP_INDICATION_CODE,_BTH_SCO_MP_INDICATION_PARAMETERS *),void *)

- ea: `0x140141910`
- end: `0x140141b64`
- name: `?ScoMp_AddScoCxn@@YAJPEAU_SCO_INTERFACE@@PEAU_SCO_CONNECTION@@P6AJPEAXW4_BTH_SCO_MP_INDICATION_CODE@@PEAU_BTH_SCO_MP_INDICATION_PARAMETERS@@@Z2@Z`
- size: `596`
- prototype: `__int64 __fastcall(struct _SCO_INTERFACE *, struct _SCO_CONNECTION *, int (*)(void *, enum _BTH_SCO_MP_INDICATION_CODE, struct _BTH_SCO_MP_INDICATION_PARAMETERS *), void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140134580`

## callees

- `0x140005ce8`
- `0x14000764c`
- `0x140139c94`
- `0x14013e32c`
- `0x140141910`
- `0x140161a44`
- `0x140161d7c`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140141a9f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140141a9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140141a46`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140141a46`
- `ntoskrnl!KeWaitForSingleObject` at `0x140141a69`
- `ntoskrnl!KeWaitForSingleObject` at `0x140141a69`
- `ntoskrnl!KeSetEvent` at `0x140141a93`
- `ntoskrnl!KeSetEvent` at `0x140141a93`

## string_xrefs

- `0x1401419cb`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\scominiport.cpp`
- `0x140141aaf`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\scominiport.cpp`

## pseudocode

```c
__int64 __fastcall ScoMp_AddScoCxn(
        struct _SCO_INTERFACE *a1,
        struct _SCO_CONNECTION *a2,
        int (*a3)(void *, enum _BTH_SCO_MP_INDICATION_CODE, struct _BTH_SCO_MP_INDICATION_PARAMETERS *),
        void *a4)
{
  int v4; // ebx
  int (*v6)(void *, enum _BTH_SCO_MP_INDICATION_CODE, struct _BTH_SCO_MP_INDICATION_PARAMETERS *); // r12
  struct _SCO_CONNECTION *v7; // r14
  char v9; // si
  __int16 DeviceType; // ax
  int v11; // r8d
  unsigned __int16 ConnectionHandle; // ax
  unsigned int v13; // eax
  DEVICE_EXTENSION *DevExt; // rbx
  unsigned int v15; // eax
  __int16 v16; // ax
  __int64 *v17; // rdx
  __int128 v19; // [rsp+60h] [rbp-19h] BYREF
  __int128 v20; // [rsp+70h] [rbp-9h]
  __int128 v21; // [rsp+80h] [rbp+7h]

  v4 = 0;
  v19 = 0;
  v6 = a3;
  v7 = a2;
  v20 = 0;
  v21 = 0;
  v9 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
  {
    LOBYTE(a3) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_qi(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      14,
      (__int64)WPP_d1b5d2f28dbf3eff616e3ff89a0fbf9e_Traceguids,
      (char)a1,
      v7);
  }
  if ( ScoInt_IsInBandSupported(a1) )
  {
    ConnectionHandle = v7->ConnectionHandle;
    v19 = 0;
    WORD2(v19) = ConnectionHandle;
    *((_QWORD *)&v19 + 1) = *(_QWORD *)&v7->LineTxBandwidth;
    LOBYTE(ConnectionHandle) = (v7->ChannelFlags & 0x20) != 0;
    LODWORD(v19) = 48;
    *(_QWORD *)&v20 = 0;
    *((_QWORD *)&v21 + 1) = (unsigned __int8)ConnectionHandle;
    *((_QWORD *)&v20 + 1) = v6;
    *(_QWORD *)&v21 = a4;
    v13 = RefObj_AddRefEx(
            &v7->RefObj,
            ScoMp_AddScoCxn,
            192,
            "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\scominiport.cpp");
    ScoRefTrace(SCO_REF_ADD, v7, ScoMp_AddScoCxn, v13);
    DevExt = a1->DevExt;
    KeEnterCriticalRegion();
    KeWaitForSingleObject(&a1->MiniportMutex, Executive, 0, 0, 0);
    v4 = DevExt->MpDispatch->ScoAdd(&DevExt->BtDevice, (_BTH_SCO_ADD_CHANNEL_ARG *)&v19);
    KeSetEvent(&a1->MiniportMutex, 0, 0);
    KeLeaveCriticalRegion();
    if ( v4 < 0 )
    {
      v15 = RefObj_ReleaseEx(
              &v7->RefObj,
              ScoMp_AddScoCxn,
              206,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\scominiport.cpp");
      ScoRefTrace(SCO_REF_RELEASE, v7, ScoMp_AddScoCxn, v15);
      LOBYTE(v7) = 0;
    }
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v9 = 0;
  v16 = WPP_GLOBAL_Control->DeviceType;
  if ( v9 || v16 )
  {
    v17 = WPP_d1b5d2f28dbf3eff616e3ff89a0fbf9e_Traceguids;
    LOBYTE(v17) = v9;
    LOBYTE(v11) = v16 != 0;
    WPP_RECORDER_AND_TRACE_SF_qiD(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v17,
      v11,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      15,
      (__int64)WPP_d1b5d2f28dbf3eff616e3ff89a0fbf9e_Traceguids,
      (char)a1,
      (char)v7,
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140141910  push    rbp
0x140141912  push    rbx
0x140141913  push    rsi
0x140141914  push    rdi
0x140141915  push    r12
0x140141917  push    r13
0x140141919  push    r14
0x14014191b  push    r15
0x14014191d  lea     rbp, [rsp-1Fh]
0x140141922  sub     rsp, 98h
0x140141929  xorps   xmm0, xmm0
0x14014192c  xor     r13d, r13d
0x14014192f  mov     ebx, r13d
0x140141932  mov     rdi, r9
0x140141935  movups  [rbp+57h+var_70], xmm0
0x140141939  mov     r12, r8
0x14014193c  mov     r14, rdx
0x14014193f  movups  [rbp+57h+var_60], xmm0
0x140141943  mov     r15, rcx
0x140141946  movups  [rbp+57h+var_50], xmm0
0x14014194a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140141951  lea     esi, [r13+1]
0x140141955  mov     eax, [rcx+2Ch]
0x140141958  test    al, 8
0x14014195a  jz      short loc_140141965
0x14014195c  cmp     byte ptr [rcx+29h], 5
0x140141960  mov     dl, sil
0x140141963  jnb     short loc_140141968
0x140141965  mov     dl, r13b
0x140141968  movzx   eax, word ptr [rcx+48h]
0x14014196c  lea     r9, WPP_d1b5d2f28dbf3eff616e3ff89a0fbf9e_Traceguids
0x140141973  test    ax, ax
0x140141976  setnz   r8b
0x14014197a  test    dl, dl
0x14014197c  jnz     short loc_140141983
0x14014197e  test    ax, ax
0x140141981  jz      short loc_1401419B3
0x140141983  mov     [rsp+0D0h+var_88], r14
0x140141988  mov     [rsp+0D0h+var_90], r15
0x14014198d  mov     [rsp+0D0h+var_98], r9
0x140141992  mov     r9, [rcx+40h]
0x140141996  mov     rcx, [rcx+18h]
0x14014199a  mov     [rsp+0D0h+var_A0], 0Eh
0x1401419a1  mov     [rsp+0D0h+var_A8], 4
0x1401419a9  mov     byte ptr [rsp+0D0h+Timeout], 5
0x1401419ae  call    WPP_RECORDER_AND_TRACE_SF_qi
0x1401419b3  mov     rcx, r15; struct _SCO_INTERFACE *
0x1401419b6  call    ?ScoInt_IsInBandSupported@@YAEPEAU_SCO_INTERFACE@@@Z; ScoInt_IsInBandSupported(_SCO_INTERFACE *)
0x1401419bb  test    al, al
0x1401419bd  jz      loc_140141AE3
0x1401419c3  movzx   eax, word ptr [r14+1D8h]
0x1401419cb  lea     r9, aOnecoreDrivers_35; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1401419d2  xorps   xmm0, xmm0
0x1401419d5  lea     rdx, ?ScoMp_AddScoCxn@@YAJPEAU_SCO_INTERFACE@@PEAU_SCO_CONNECTION@@P6AJPEAXW4_BTH_SCO_MP_INDICATION_CODE@@PEAU_BTH_SCO_MP_INDICATION_PARAMETERS@@@Z2@Z; ScoMp_AddScoCxn(_SCO_INTERFACE *,_SCO_CONNECTION *,long (*)(void *,_BTH_SCO_MP_INDICATION_CODE,_BTH_SCO_MP_INDICATION_PARAMETERS *),void *)
0x1401419dc  movups  [rbp+57h+var_70], xmm0
0x1401419e0  mov     word ptr [rbp+57h+var_70+4], ax
0x1401419e4  lea     rcx, [r14+8]
0x1401419e8  mov     eax, [r14+1E8h]
0x1401419ef  mov     r8d, 0C0h
0x1401419f5  mov     dword ptr [rbp+57h+var_70+8], eax
0x1401419f8  mov     eax, [r14+1ECh]
0x1401419ff  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x140141a02  mov     al, [r14+230h]
0x140141a09  movups  [rbp+57h+var_50], xmm0
0x140141a0d  shr     al, 5
0x140141a10  and     al, sil
0x140141a13  mov     dword ptr [rbp+57h+var_70], 30h ; '0'
0x140141a1a  movups  [rbp+57h+var_60], xmm0
0x140141a1e  mov     byte ptr [rbp+57h+var_50+8], al
0x140141a21  mov     qword ptr [rbp+57h+var_60+8], r12
0x140141a25  mov     qword ptr [rbp+57h+var_50], rdi
0x140141a29  call    RefObj_AddRefEx
0x140141a2e  mov     r9d, eax; unsigned int
0x140141a31  lea     r8, ?ScoMp_AddScoCxn@@YAJPEAU_SCO_INTERFACE@@PEAU_SCO_CONNECTION@@P6AJPEAXW4_BTH_SCO_MP_INDICATION_CODE@@PEAU_BTH_SCO_MP_INDICATION_PARAMETERS@@@Z2@Z; void *
0x140141a38  mov     rdx, r14; struct _SCO_CONNECTION *
0x140141a3b  xor     ecx, ecx; enum _SCO_REF_TRACE_TYPE
0x140141a3d  call    ?ScoRefTrace@@YAXW4_SCO_REF_TRACE_TYPE@@PEAU_SCO_CONNECTION@@PEAXK@Z; ScoRefTrace(_SCO_REF_TRACE_TYPE,_SCO_CONNECTION *,void *,ulong)
0x140141a42  mov     rbx, [r15+20h]
0x140141a46  call    cs:__imp_KeEnterCriticalRegion
0x140141a4d  nop     dword ptr [rax+rax+00h]
0x140141a52  lea     rdi, [r15+88h]
0x140141a59  mov     [rsp+0D0h+Timeout], r13; Timeout
0x140141a5e  mov     rcx, rdi; Object
0x140141a61  xor     r9d, r9d; Alertable
0x140141a64  xor     r8d, r8d; WaitMode
0x140141a67  xor     edx, edx; WaitReason
0x140141a69  call    cs:__imp_KeWaitForSingleObject
0x140141a70  nop     dword ptr [rax+rax+00h]
0x140141a75  mov     rax, [rbx+58h]
0x140141a79  lea     rdx, [rbp+57h+var_70]
0x140141a7d  mov     rcx, rbx
0x140141a80  mov     rax, [rax+10h]
0x140141a84  call    _guard_dispatch_icall
0x140141a89  xor     r8d, r8d; Wait
0x140141a8c  xor     edx, edx; Increment
0x140141a8e  mov     rcx, rdi; Event
0x140141a91  mov     ebx, eax
0x140141a93  call    cs:__imp_KeSetEvent
0x140141a9a  nop     dword ptr [rax+rax+00h]
0x140141a9f  call    cs:__imp_KeLeaveCriticalRegion
0x140141aa6  nop     dword ptr [rax+rax+00h]
0x140141aab  test    ebx, ebx
0x140141aad  jns     short loc_140141AE3
0x140141aaf  lea     r9, aOnecoreDrivers_35; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140141ab6  mov     r8d, 0CEh
0x140141abc  lea     rdx, ?ScoMp_AddScoCxn@@YAJPEAU_SCO_INTERFACE@@PEAU_SCO_CONNECTION@@P6AJPEAXW4_BTH_SCO_MP_INDICATION_CODE@@PEAU_BTH_SCO_MP_INDICATION_PARAMETERS@@@Z2@Z; ScoMp_AddScoCxn(_SCO_INTERFACE *,_SCO_CONNECTION *,long (*)(void *,_BTH_SCO_MP_INDICATION_CODE,_BTH_SCO_MP_INDICATION_PARAMETERS *),void *)
0x140141ac3  lea     rcx, [r14+8]
0x140141ac7  call    RefObj_ReleaseEx
0x140141acc  mov     r9d, eax; unsigned int
0x140141acf  lea     r8, ?ScoMp_AddScoCxn@@YAJPEAU_SCO_INTERFACE@@PEAU_SCO_CONNECTION@@P6AJPEAXW4_BTH_SCO_MP_INDICATION_CODE@@PEAU_BTH_SCO_MP_INDICATION_PARAMETERS@@@Z2@Z; void *
0x140141ad6  mov     rdx, r14; struct _SCO_CONNECTION *
0x140141ad9  mov     ecx, esi; enum _SCO_REF_TRACE_TYPE
0x140141adb  call    ?ScoRefTrace@@YAXW4_SCO_REF_TRACE_TYPE@@PEAU_SCO_CONNECTION@@PEAXK@Z; ScoRefTrace(_SCO_REF_TRACE_TYPE,_SCO_CONNECTION *,void *,ulong)
0x140141ae0  mov     r14, r13
0x140141ae3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140141aea  mov     eax, [rcx+2Ch]
0x140141aed  test    al, 8
0x140141aef  jz      short loc_140141AF7
0x140141af1  cmp     byte ptr [rcx+29h], 5
0x140141af5  jnb     short loc_140141AFA
0x140141af7  mov     sil, r13b
0x140141afa  movzx   eax, word ptr [rcx+48h]
0x140141afe  test    ax, ax
0x140141b01  setnz   r8b
0x140141b05  test    sil, sil
0x140141b08  jnz     short loc_140141B0F
0x140141b0a  test    ax, ax
0x140141b0d  jz      short loc_140141B4D
0x140141b0f  mov     r9, [rcx+40h]
0x140141b13  lea     rdx, WPP_d1b5d2f28dbf3eff616e3ff89a0fbf9e_Traceguids
0x140141b1a  mov     rcx, [rcx+18h]
0x140141b1e  mov     [rsp+0D0h+var_80], ebx
0x140141b22  mov     [rsp+0D0h+var_88], r14
0x140141b27  mov     [rsp+0D0h+var_90], r15
0x140141b2c  mov     [rsp+0D0h+var_98], rdx
0x140141b31  mov     dl, sil
0x140141b34  mov     [rsp+0D0h+var_A0], 0Fh
0x140141b3b  mov     [rsp+0D0h+var_A8], 4
0x140141b43  mov     byte ptr [rsp+0D0h+Timeout], 5
0x140141b48  call    WPP_RECORDER_AND_TRACE_SF_qiD
0x140141b4d  mov     eax, ebx
0x140141b4f  add     rsp, 98h
0x140141b56  pop     r15
0x140141b58  pop     r14
0x140141b5a  pop     r13
0x140141b5c  pop     r12
0x140141b5e  pop     rdi
0x140141b5f  pop     rsi
0x140141b60  pop     rbx
0x140141b61  pop     rbp
0x140141b62  retn
```
