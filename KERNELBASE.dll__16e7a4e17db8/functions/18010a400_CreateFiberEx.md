# CreateFiberEx

- ea: `0x18010a400`
- end: `0x18010a639`
- name: `CreateFiberEx`
- size: `569`
- prototype: `LPVOID __stdcall(SIZE_T dwStackCommitSize, SIZE_T dwStackReserveSize, DWORD dwFlags, LPFIBER_START_ROUTINE lpStartAddress, LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18010a3d0`

## callees

- `0x1800134a0`
- `0x1800f343c`
- `0x1800fb2c8`
- `0x18010a400`
- `0x18012d119`
- `0x18017f478`
- `0x18017f4b0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18010a443`
- `ntdll!RtlSetLastWin32Error` at `0x18010a443`
- `ntdll!RtlFreeHeap` at `0x18010a502`
- `ntdll!RtlFreeHeap` at `0x18010a55c`
- `ntdll!RtlFreeHeap` at `0x18010a502`
- `ntdll!RtlFreeHeap` at `0x18010a55c`
- `ntdll!RtlAllocateActivationContextStack` at `0x18010a466`
- `ntdll!RtlAllocateActivationContextStack` at `0x18010a466`
- `ntdll!RtlFreeActivationContextStack` at `0x18010a4a6`
- `ntdll!RtlFreeActivationContextStack` at `0x18010a4ea`
- `ntdll!RtlFreeActivationContextStack` at `0x18010a544`
- `ntdll!RtlFreeActivationContextStack` at `0x18010a4a6`
- `ntdll!RtlFreeActivationContextStack` at `0x18010a4ea`
- `ntdll!RtlFreeActivationContextStack` at `0x18010a544`
- `ntdll!RtlCreateUserStack` at `0x18010a4d5`
- `ntdll!RtlCreateUserStack` at `0x18010a4d5`
- `ntdll!RtlCreateUserFiberShadowStack` at `0x18010a52f`
- `ntdll!RtlCreateUserFiberShadowStack` at `0x18010a52f`
- `ntdll!RtlFreeUserStack` at `0x18010a566`
- `ntdll!RtlFreeUserStack` at `0x18010a566`
- `ntdll!RtlAllocateHeap` at `0x18010a494`
- `ntdll!RtlAllocateHeap` at `0x18010a494`

## pseudocode

```c
LPVOID __stdcall CreateFiberEx(
        SIZE_T dwStackCommitSize,
        SIZE_T dwStackReserveSize,
        DWORD dwFlags,
        LPFIBER_START_ROUTINE lpStartAddress,
        LPVOID lpParameter)
{
  int v5; // r12d
  char v6; // si
  ULONG v9; // ecx
  __int64 NtdllRtlUserFiberStartAddress; // r14
  NTSTATUS v12; // eax
  SIZE_T FiberAllocSize; // rax
  unsigned __int64 Heap; // rdi
  int v15; // eax
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r8
  PACTIVATION_CONTEXT_STACK Stack; // [rsp+30h] [rbp-40h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h] BYREF
  __int128 v22; // [rsp+40h] [rbp-30h] BYREF
  __int128 v23; // [rsp+50h] [rbp-20h]
  __int64 v24; // [rsp+60h] [rbp-10h]

  v24 = 0;
  v5 = (int)lpStartAddress;
  v21 = 0;
  v6 = dwFlags;
  Stack = 0;
  v22 = 0;
  v23 = 0;
  if ( (dwFlags & 0xFFFFFFFE) != 0 )
  {
    v9 = 87;
LABEL_3:
    RtlSetLastWin32Error(v9);
    return 0;
  }
  NtdllRtlUserFiberStartAddress = BasepGetNtdllRtlUserFiberStartAddress();
  if ( !NtdllRtlUserFiberStartAddress )
  {
    v9 = 50;
    goto LABEL_3;
  }
  v12 = RtlAllocateActivationContextStack(&Stack);
  if ( v12 < 0 )
  {
    BaseSetLastNTError((unsigned int)v12);
    return 0;
  }
  FiberAllocSize = BasepGetFiberAllocSize();
  Heap = (unsigned __int64)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, FiberAllocSize);
  if ( !Heap )
  {
    RtlFreeActivationContextStack(Stack);
    v9 = 8;
    goto LABEL_3;
  }
  v15 = RtlCreateUserStack(
          dwStackCommitSize,
          dwStackReserveSize,
          0,
          (unsigned int)dword_1803A2D68,
          (unsigned int)dword_1803A2D78,
          &v22);
  if ( v15 < 0 )
  {
    BaseSetLastNTError((unsigned int)v15);
    RtlFreeActivationContextStack(Stack);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)Heap);
    return 0;
  }
  v21 = 0;
  __asm { rdsspq  rax }
  if ( _RAX )
  {
    v17 = RtlCreateUserFiberShadowStack(&v22, (unsigned int)dword_1803A2D68, &v21);
    if ( v17 < 0 )
    {
      BaseSetLastNTError((unsigned int)v17);
      RtlFreeActivationContextStack(Stack);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)Heap);
      RtlFreeUserStack(v24);
      return 0;
    }
  }
  memset_0((void *)(Heap + 48), 0, 0x4D0u);
  *(_QWORD *)Heap = lpParameter;
  v18 = v23;
  *(_QWORD *)(Heap + 16) = v23;
  v19 = BasepFiberCookie ^ Heap ^ v18;
  *(_QWORD *)(Heap + 24) = *((_QWORD *)&v23 + 1);
  *(_QWORD *)(Heap + 32) = v24;
  *(_WORD *)(Heap + 1340) = 0;
  *(_QWORD *)(Heap + 8) = -1;
  *(_QWORD *)(Heap + 1312) = 0;
  *(_QWORD *)(Heap + 1328) = 0;
  *(_DWORD *)(Heap + 1336) = 0;
  *(_QWORD *)(Heap + 1320) = Stack;
  *(_QWORD *)(Heap + 1344) = v19;
  *(_QWORD *)(Heap + 1352) = v21;
  *(_DWORD *)(Heap + 96) = (v6 & 1) != 0 ? 0x100008 : 0;
  BaseInitializeFiberContext(Heap + 48, (_DWORD)lpParameter, v5, v23, NtdllRtlUserFiberStartAddress);
  BasepInitializeFiberContextEx(Heap);
  return (LPVOID)Heap;
}

```

## disassembly

```asm
0x18010a400  push    rbp
0x18010a402  push    rbx
0x18010a403  push    rsi
0x18010a404  push    rdi
0x18010a405  push    r12
0x18010a407  push    r14
0x18010a409  push    r15
0x18010a40b  mov     rbp, rsp
0x18010a40e  sub     rsp, 70h
0x18010a412  xor     eax, eax
0x18010a414  xorps   xmm0, xmm0
0x18010a417  mov     [rbp+var_10], rax
0x18010a41b  mov     r12, r9
0x18010a41e  mov     [rbp+var_38], rax
0x18010a422  mov     esi, r8d
0x18010a425  mov     [rbp+Stack], rax
0x18010a429  mov     rbx, rdx
0x18010a42c  mov     r15, rcx
0x18010a42f  movups  [rbp+var_30], xmm0
0x18010a433  movups  [rbp+var_20], xmm0
0x18010a437  test    r8d, 0FFFFFFFEh
0x18010a43e  jz      short loc_18010A450
0x18010a440  lea     ecx, [rax+57h]; LastError
0x18010a443  call    cs:__imp_RtlSetLastWin32Error
0x18010a449  xor     eax, eax
0x18010a44b  jmp     loc_18010A62A
0x18010a450  call    BasepGetNtdllRtlUserFiberStartAddress
0x18010a455  mov     r14, rax
0x18010a458  test    rax, rax
0x18010a45b  jnz     short loc_18010A462
0x18010a45d  lea     ecx, [rax+32h]
0x18010a460  jmp     short loc_18010A443
0x18010a462  lea     rcx, [rbp+Stack]; Stack
0x18010a466  call    cs:__imp_RtlAllocateActivationContextStack
0x18010a46c  test    eax, eax
0x18010a46e  jns     short loc_18010A479
0x18010a470  mov     ecx, eax
0x18010a472  call    BaseSetLastNTError
0x18010a477  jmp     short loc_18010A449
0x18010a479  call    BasepGetFiberAllocSize
0x18010a47e  mov     rcx, gs:60h
0x18010a487  mov     r8, rax; Size
0x18010a48a  mov     edx, cs:KernelBaseGlobalData; Flags
0x18010a490  mov     rcx, [rcx+30h]; HeapHandle
0x18010a494  call    cs:__imp_RtlAllocateHeap
0x18010a49a  mov     rdi, rax
0x18010a49d  test    rax, rax
0x18010a4a0  jnz     short loc_18010A4B1
0x18010a4a2  mov     rcx, [rbp+Stack]; Stack
0x18010a4a6  call    cs:__imp_RtlFreeActivationContextStack
0x18010a4ac  lea     ecx, [rdi+8]
0x18010a4af  jmp     short loc_18010A443
0x18010a4b1  mov     eax, cs:dword_1803A2D78
0x18010a4b7  lea     rcx, [rbp+var_30]
0x18010a4bb  mov     r9d, cs:dword_1803A2D68
0x18010a4c2  xor     r8d, r8d
0x18010a4c5  mov     [rsp+70h+var_48], rcx
0x18010a4ca  mov     rdx, rbx
0x18010a4cd  mov     rcx, r15
0x18010a4d0  mov     [rsp+70h+var_50], rax
0x18010a4d5  call    cs:__imp_RtlCreateUserStack
0x18010a4db  test    eax, eax
0x18010a4dd  jns     short loc_18010A50D
0x18010a4df  mov     ecx, eax
0x18010a4e1  call    BaseSetLastNTError
0x18010a4e6  mov     rcx, [rbp+Stack]; Stack
0x18010a4ea  call    cs:__imp_RtlFreeActivationContextStack
0x18010a4f0  mov     rcx, gs:60h
0x18010a4f9  mov     r8, rdi; P
0x18010a4fc  xor     edx, edx; Flags
0x18010a4fe  mov     rcx, [rcx+30h]; HeapHandle
0x18010a502  call    cs:__imp_RtlFreeHeap
0x18010a508  jmp     loc_18010A449
0x18010a50d  xor     eax, eax
0x18010a50f  mov     [rbp+var_38], 0
0x18010a517  rdsspq  rax
0x18010a51c  test    rax, rax
0x18010a51f  jz      short loc_18010A571
0x18010a521  mov     edx, cs:dword_1803A2D68
0x18010a527  lea     r8, [rbp+var_38]
0x18010a52b  lea     rcx, [rbp+var_30]
0x18010a52f  call    cs:__imp_RtlCreateUserFiberShadowStack
0x18010a535  test    eax, eax
0x18010a537  jns     short loc_18010A571
0x18010a539  mov     ecx, eax
0x18010a53b  call    BaseSetLastNTError
0x18010a540  mov     rcx, [rbp+Stack]; Stack
0x18010a544  call    cs:__imp_RtlFreeActivationContextStack
0x18010a54a  mov     rcx, gs:60h
0x18010a553  mov     r8, rdi; P
0x18010a556  xor     edx, edx; Flags
0x18010a558  mov     rcx, [rcx+30h]; HeapHandle
0x18010a55c  call    cs:__imp_RtlFreeHeap
0x18010a562  mov     rcx, [rbp+var_10]
0x18010a566  call    cs:__imp_RtlFreeUserStack
0x18010a56c  jmp     loc_18010A449
0x18010a571  xor     edx, edx; Val
0x18010a573  lea     rcx, [rdi+30h]; void *
0x18010a577  mov     r8d, 4D0h; Size
0x18010a57d  call    memset_0
0x18010a582  mov     rdx, [rbp+lpParameter]
0x18010a586  lea     rcx, [rdi+30h]
0x18010a58a  mov     [rdi], rdx
0x18010a58d  and     sil, 1
0x18010a591  mov     r8, qword ptr [rbp+var_20]
0x18010a595  mov     [rdi+10h], r8
0x18010a599  xor     r8, rdi
0x18010a59c  mov     rax, qword ptr [rbp+var_20+8]
0x18010a5a0  xor     r8, cs:BasepFiberCookie
0x18010a5a7  mov     [rdi+18h], rax
0x18010a5ab  mov     rax, [rbp+var_10]
0x18010a5af  mov     [rdi+20h], rax
0x18010a5b3  xor     eax, eax
0x18010a5b5  mov     [rdi+53Ch], ax
0x18010a5bc  neg     sil
0x18010a5bf  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18010a5c7  mov     qword ptr [rdi+520h], 0
0x18010a5d2  mov     qword ptr [rdi+530h], 0
0x18010a5dd  mov     dword ptr [rdi+538h], 0
0x18010a5e7  mov     rax, [rbp+Stack]
0x18010a5eb  mov     [rdi+528h], rax
0x18010a5f2  mov     [rdi+540h], r8
0x18010a5f9  mov     r8, r12
0x18010a5fc  mov     rax, [rbp+var_38]
0x18010a600  mov     [rdi+548h], rax
0x18010a607  sbb     eax, eax
0x18010a609  and     eax, 100008h
0x18010a60e  mov     [rsp+70h+var_50], r14
0x18010a613  mov     [rdi+60h], eax
0x18010a616  mov     r9, qword ptr [rbp+var_20]
0x18010a61a  call    BaseInitializeFiberContext
0x18010a61f  mov     rcx, rdi
0x18010a622  call    BasepInitializeFiberContextEx
0x18010a627  mov     rax, rdi
0x18010a62a  add     rsp, 70h
0x18010a62e  pop     r15
0x18010a630  pop     r14
0x18010a632  pop     r12
0x18010a634  pop     rdi
0x18010a635  pop     rsi
0x18010a636  pop     rbx
0x18010a637  pop     rbp
0x18010a638  retn
```
