# HamCreateActivityForProcess

- ea: `0x1800098f0`
- end: `0x180009a90`
- name: `HamCreateActivityForProcess`
- size: `416`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800098f0`
- `0x180009d40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a3f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009a58`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009a58`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009a39`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009a39`
- `ntdll!RtlFreeHeap` at `0x1800099f7`
- `ntdll!RtlFreeHeap` at `0x1800099f7`
- `ntdll!RtlAllocateHeap` at `0x18000992b`
- `ntdll!RtlAllocateHeap` at `0x18000992b`
- `RPCRT4!NdrClientCall3` at `0x1800099b2`
- `RPCRT4!NdrClientCall3` at `0x1800099b2`
- `RPCRT4!RpcExceptionFilter` at `0x18001b23e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b23e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800099c8`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800099c8`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCreateActivityForProcess` at `0x180009a1b`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCreateActivityForProcess` at `0x180009a1b`

## pseudocode

```c
__int64 __fastcall HamCreateActivityForProcess(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  _QWORD *Heap; // rax
  _QWORD *v10; // rdi
  int v11; // eax
  __int64 v12; // rcx
  int Pointer; // ebx
  __int64 v15; // rbx
  __int64 v16; // [rsp+A0h] [rbp+8h] BYREF

  v16 = -1;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x40u);
  v10 = Heap;
  if ( Heap )
  {
    *Heap = 0;
    Heap[1] = 0;
    Heap[2] = 0;
    Heap[3] = 0;
    Heap[4] = 0;
    Heap[5] = a1 + 3;
    Heap[7] = a2;
    Heap[6] = -1;
    v11 = 0;
  }
  else
  {
    v10 = 0;
    v11 = -1073741801;
  }
  if ( v11 < 0 )
  {
    Pointer = v11;
  }
  else
  {
    v12 = a1[1];
    if ( v12 )
      Pointer = HampInProcCreateActivityForProcess(v12, a3, a4, &v16);
    else
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 4u, 0, *a1, a3, a4, &v16).Pointer;
    if ( Pointer >= 0 )
    {
      v10[6] = v16;
      v15 = v10[5];
      RtlAcquireSRWLockExclusive(v15 + 8);
      *(_DWORD *)(v15 + 16) = GetCurrentThreadId();
      HampIpcChannelAddCallbackUnsafe(v10);
      *(_DWORD *)(v15 + 16) = 0;
      RtlReleaseSRWLockExclusive(v15 + 8);
      v10 = 0;
      *a5 = v16;
      Pointer = 0;
    }
  }
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800098f0  push    rbx
0x1800098f2  push    rsi
0x1800098f3  push    rdi
0x1800098f4  push    r12
0x1800098f6  push    r14
0x1800098f8  push    r15
0x1800098fa  sub     rsp, 68h
0x1800098fe  mov     r15, r9
0x180009901  mov     r12, r8
0x180009904  mov     rsi, rdx
0x180009907  mov     rbx, rcx
0x18000990a  mov     [rsp+98h+arg_0], 0FFFFFFFFFFFFFFFFh
0x180009916  mov     rcx, gs:60h
0x18000991f  xor     edx, edx; Flags
0x180009921  mov     r8d, 40h ; '@'; Size
0x180009927  mov     rcx, [rcx+30h]; HeapHandle
0x18000992b  call    cs:__imp_RtlAllocateHeap
0x180009931  mov     rdi, rax
0x180009934  xor     r14d, r14d
0x180009937  test    rax, rax
0x18000993a  jz      loc_180009A83
0x180009940  mov     [rax], r14
0x180009943  mov     [rax+8], r14
0x180009947  mov     [rax+10h], r14
0x18000994b  mov     [rax+18h], r14
0x18000994f  mov     [rax+20h], r14
0x180009953  lea     rax, [rbx+18h]
0x180009957  mov     [rdi+28h], rax
0x18000995b  mov     [rdi+38h], rsi
0x18000995f  mov     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x180009967  mov     eax, r14d
0x18000996a  mov     [rsp+98h+var_50], rdi
0x18000996f  test    eax, eax
0x180009971  js      loc_180009A7C
0x180009977  mov     rcx, [rbx+8]
0x18000997b  test    rcx, rcx
0x18000997e  jnz     loc_180009A0D
0x180009984  mov     [rsp+98h+var_48], r14
0x180009989  lea     rax, [rsp+98h+arg_0]
0x180009991  mov     [rsp+98h+var_68], rax
0x180009996  mov     [rsp+98h+var_70], r15
0x18000999b  mov     [rsp+98h+var_78], r12
0x1800099a0  mov     r9, [rbx]
0x1800099a3  xor     r8d, r8d; pReturnValue
0x1800099a6  mov     edx, 4; nProcNum
0x1800099ab  lea     rcx, pProxyInfo; pProxyInfo
0x1800099b2  call    cs:__imp_NdrClientCall3
0x1800099b8  mov     rbx, rax
0x1800099bb  mov     [rsp+98h+var_48], rax
0x1800099c0  mov     [rsp+98h+var_58], eax
0x1800099c4  jmp     short loc_1800099DC
0x1800099c6  mov     ecx, eax; Status
0x1800099c8  call    cs:__imp_I_RpcMapWin32Status
0x1800099ce  mov     ebx, eax
0x1800099d0  mov     [rsp+98h+var_58], eax
0x1800099d4  xor     r14d, r14d
0x1800099d7  mov     rdi, [rsp+98h+var_50]
0x1800099dc  test    ebx, ebx
0x1800099de  jns     short loc_180009A25
0x1800099e0  test    rdi, rdi
0x1800099e3  jz      short loc_1800099FD
0x1800099e5  mov     rcx, gs:60h
0x1800099ee  mov     r8, rdi; P
0x1800099f1  xor     edx, edx; Flags
0x1800099f3  mov     rcx, [rcx+30h]; HeapHandle
0x1800099f7  call    cs:__imp_RtlFreeHeap
0x1800099fd  mov     eax, ebx
0x1800099ff  add     rsp, 68h
0x180009a03  pop     r15
0x180009a05  pop     r14
0x180009a07  pop     r12
0x180009a09  pop     rdi
0x180009a0a  pop     rsi
0x180009a0b  pop     rbx
0x180009a0c  retn
0x180009a0d  lea     r9, [rsp+98h+arg_0]
0x180009a15  mov     r8, r15
0x180009a18  mov     rdx, r12
0x180009a1b  call    cs:__imp_HampInProcCreateActivityForProcess
0x180009a21  mov     ebx, eax
0x180009a23  jmp     short loc_1800099DC
0x180009a25  mov     rax, [rsp+98h+arg_0]
0x180009a2d  mov     [rdi+30h], rax
0x180009a31  mov     rbx, [rdi+28h]
0x180009a35  lea     rcx, [rbx+8]
0x180009a39  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009a3f  call    cs:__imp_GetCurrentThreadId
0x180009a45  mov     [rbx+10h], eax
0x180009a48  mov     rcx, rdi
0x180009a4b  call    HampIpcChannelAddCallbackUnsafe
0x180009a50  mov     [rbx+10h], r14d
0x180009a54  lea     rcx, [rbx+8]
0x180009a58  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009a5e  mov     rdi, r14
0x180009a61  mov     rcx, [rsp+98h+arg_20]
0x180009a69  mov     rax, [rsp+98h+arg_0]
0x180009a71  mov     [rcx], rax
0x180009a74  mov     ebx, r14d
0x180009a77  jmp     loc_1800099E0
0x180009a7c  mov     ebx, eax
0x180009a7e  jmp     loc_1800099E0
0x180009a83  mov     rdi, r14
0x180009a86  mov     eax, 0C0000017h
0x180009a8b  jmp     loc_18000996A
0x18001b230  push    rbp
0x18001b232  sub     rsp, 40h
0x18001b236  mov     rbp, rdx
0x18001b239  mov     rcx, [rcx]
0x18001b23c  mov     ecx, [rcx]; ExceptionCode
0x18001b23e  call    cs:__imp_RpcExceptionFilter
0x18001b244  nop
0x18001b245  add     rsp, 40h
0x18001b249  pop     rbp
0x18001b24a  retn
```
