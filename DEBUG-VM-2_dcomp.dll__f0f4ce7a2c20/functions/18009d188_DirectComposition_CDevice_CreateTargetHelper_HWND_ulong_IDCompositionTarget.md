# DirectComposition::CDevice::CreateTargetHelper(HWND__ *,ulong,IDCompositionTarget * *)

- ea: `0x18009d188`
- end: `0x18009d2c4`
- name: `?CreateTargetHelper@CDevice@DirectComposition@@AEAAJPEAUHWND__@@KPEAPEAUIDCompositionTarget@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(DirectComposition::CDevice *__hidden this, HWND, unsigned int, struct IDCompositionTarget **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009d170`
- `0x18010f220`

## callees

- `0x18001cf2c`
- `0x1800348d0`
- `0x1800827d0`
- `0x18009d188`
- `0x18009d2cc`
- `0x18009d300`
- `0x18009d9d0`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009d2bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009d2bc`
- `ntdll!RtlGetLastNtStatus` at `0x18009d29b`
- `ntdll!RtlGetLastNtStatus` at `0x18009d29b`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateDCompositionHwndTarget` at `0x18009d1ec`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!CreateDCompositionHwndTarget` at `0x18009d1ec`

## pseudocode

```c
__int64 __fastcall DirectComposition::CDevice::CreateTargetHelper(
        DirectComposition::CDevice *this,
        HWND a2,
        unsigned int a3,
        struct IDCompositionTarget **a4)
{
  DirectComposition::CHwndTarget *v8; // rax
  __int64 v9; // rbx
  int v10; // edi
  volatile signed __int32 *v11; // rcx
  NTSTATUS LastNtStatus; // eax
  HANDLE hObject; // [rsp+30h] [rbp-28h] BYREF
  void *v15; // [rsp+38h] [rbp-20h] BYREF
  volatile signed __int32 *v16; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v17; // [rsp+A8h] [rbp+50h] BYREF

  if ( !a4 )
    return (unsigned int)-2147024809;
  *a4 = 0;
  v8 = (DirectComposition::CHwndTarget *)DefaultHeap::Alloc(0x28u);
  if ( !v8 || (v9 = DirectComposition::CHwndTarget::CHwndTarget(v8)) == 0 )
    return (unsigned int)-2147024882;
  hObject = 0;
  if ( (unsigned int)CreateDCompositionHwndTarget(a2, a3, &hObject) )
  {
    *(_QWORD *)(v9 + 16) = a2;
    *(_DWORD *)(v9 + 24) = a3;
  }
  else
  {
    LastNtStatus = RtlGetLastNtStatus();
    v10 = DirectComposition::CDevice::HRESULTFromNTSTATUS(LastNtStatus);
    if ( v10 < 0 )
      goto LABEL_14;
  }
  v15 = 0;
  v17 = 0;
  v10 = DirectComposition::CDevice::OpenSharedProxy(this, hObject, 0x9Eu, 0, &v15, &v17);
  if ( v10 >= 0 )
  {
    v16 = 0;
    CreateVisualTargetProxy(v15, v17, &v16);
    v11 = v16;
    *(_QWORD *)(v9 + 32) = v16;
    _InterlockedIncrement(v11 + 2);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
    *a4 = (struct IDCompositionTarget *)v9;
    goto LABEL_8;
  }
LABEL_14:
  DirectComposition::CHwndTarget::Release((DirectComposition::CHwndTarget *)v9);
LABEL_8:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18009d188  push    rbp
0x18009d18a  push    rbx
0x18009d18b  push    rsi
0x18009d18c  push    rdi
0x18009d18d  push    r14
0x18009d18f  push    r15
0x18009d191  mov     rbp, rsp
0x18009d194  sub     rsp, 58h
0x18009d198  mov     rsi, r9
0x18009d19b  mov     edi, r8d
0x18009d19e  mov     r14, rdx
0x18009d1a1  mov     r15, rcx
0x18009d1a4  test    r9, r9
0x18009d1a7  jz      loc_18009D28D
0x18009d1ad  mov     ecx, 28h ; '('; unsigned __int64
0x18009d1b2  mov     qword ptr [r9], 0
0x18009d1b9  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x18009d1be  test    rax, rax
0x18009d1c1  jz      loc_18009D294
0x18009d1c7  mov     rcx, rax; this
0x18009d1ca  call    ??0CHwndTarget@DirectComposition@@QEAA@XZ; DirectComposition::CHwndTarget::CHwndTarget(void)
0x18009d1cf  mov     rbx, rax
0x18009d1d2  test    rax, rax
0x18009d1d5  jz      loc_18009D294
0x18009d1db  lea     r8, [rbp+hObject]
0x18009d1df  mov     [rbp+hObject], 0
0x18009d1e7  mov     edx, edi
0x18009d1e9  mov     rcx, r14
0x18009d1ec  call    cs:__imp_CreateDCompositionHwndTarget
0x18009d1f2  test    eax, eax
0x18009d1f4  jz      loc_18009D29B
0x18009d1fa  mov     [rbx+10h], r14
0x18009d1fe  mov     [rbx+18h], edi
0x18009d201  mov     rdx, [rbp+hObject]; void *
0x18009d205  lea     rax, [rbp+arg_18]
0x18009d209  mov     [rsp+58h+var_30], rax; unsigned int *
0x18009d20e  xor     r9d, r9d; bool
0x18009d211  lea     rax, [rbp+var_20]
0x18009d215  mov     [rbp+var_20], 0
0x18009d21d  mov     r8d, 9Eh; unsigned int
0x18009d223  mov     [rsp+58h+var_38], rax; void **
0x18009d228  mov     rcx, r15; this
0x18009d22b  mov     [rbp+arg_18], 0
0x18009d232  call    ?OpenSharedProxy@CDevice@DirectComposition@@AEAAJPEAXI_NPEAPEAXPEAI@Z; DirectComposition::CDevice::OpenSharedProxy(void *,uint,bool,void * *,uint *)
0x18009d237  mov     edi, eax
0x18009d239  test    eax, eax
0x18009d23b  js      short loc_18009D2B2
0x18009d23d  mov     edx, [rbp+arg_18]
0x18009d240  lea     r8, [rbp+var_18]
0x18009d244  mov     rcx, [rbp+var_20]
0x18009d248  mov     [rbp+var_18], 0
0x18009d250  call    CreateVisualTargetProxy
0x18009d255  mov     rcx, [rbp+var_18]
0x18009d259  mov     [rbx+20h], rcx
0x18009d25d  lock inc dword ptr [rcx+8]
0x18009d261  mov     rax, [rcx]
0x18009d264  mov     rax, [rax+10h]
0x18009d268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d26d  mov     [rsi], rbx
0x18009d270  mov     rcx, [rbp+hObject]; hObject
0x18009d274  lea     rax, [rcx-1]
0x18009d278  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009d27c  jbe     short loc_18009D2BC
0x18009d27e  mov     eax, edi
0x18009d280  add     rsp, 58h
0x18009d284  pop     r15
0x18009d286  pop     r14
0x18009d288  pop     rdi
0x18009d289  pop     rsi
0x18009d28a  pop     rbx
0x18009d28b  pop     rbp
0x18009d28c  retn
0x18009d28d  mov     edi, 80070057h
0x18009d292  jmp     short loc_18009D27E
0x18009d294  mov     edi, 8007000Eh
0x18009d299  jmp     short loc_18009D27E
0x18009d29b  call    cs:__imp_RtlGetLastNtStatus
0x18009d2a1  mov     ecx, eax; int
0x18009d2a3  call    ?HRESULTFromNTSTATUS@CDevice@DirectComposition@@SAJJ@Z; DirectComposition::CDevice::HRESULTFromNTSTATUS(long)
0x18009d2a8  mov     edi, eax
0x18009d2aa  test    eax, eax
0x18009d2ac  jns     loc_18009D201
0x18009d2b2  mov     rcx, rbx; this
0x18009d2b5  call    ?Release@CHwndTarget@DirectComposition@@UEAAKXZ; DirectComposition::CHwndTarget::Release(void)
0x18009d2ba  jmp     short loc_18009D270
0x18009d2bc  call    cs:__imp_CloseHandle
0x18009d2c2  jmp     short loc_18009D27E
```
