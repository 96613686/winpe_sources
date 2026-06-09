# HamCreateActivityEx

- ea: `0x180009ad0`
- end: `0x180009d2d`
- name: `HamCreateActivityEx`
- size: `605`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009aa0`

## callees

- `0x180004550`
- `0x180009ad0`
- `0x180009d40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c43`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009c5c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180009c5c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009c3d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180009c3d`
- `ntdll!RtlLengthSid` at `0x180009b8c`
- `ntdll!RtlLengthSid` at `0x180009cb5`
- `ntdll!RtlLengthSid` at `0x180009b8c`
- `ntdll!RtlLengthSid` at `0x180009cb5`
- `ntdll!RtlAllocateHeap` at `0x180009b16`
- `ntdll!RtlAllocateHeap` at `0x180009b16`
- `RPCRT4!NdrClientCall3` at `0x180009bf8`
- `RPCRT4!NdrClientCall3` at `0x180009bf8`
- `RPCRT4!RpcExceptionFilter` at `0x18001b26e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b26e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009c11`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009c11`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCreateActivity` at `0x180009d06`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcCreateActivity` at `0x180009d06`

## pseudocode

```c
__int64 __fastcall HamCreateActivityEx(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 *a6)
{
  _QWORD *Heap; // rax
  _QWORD *v10; // rdi
  int Pointer; // ebx
  __int64 v12; // rbx
  int v13; // esi
  int v14; // r14d
  void *v15; // r15
  __int64 v16; // rbx
  ULONG v18; // eax
  ULONG v19; // [rsp+30h] [rbp-98h]
  __int64 v20; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v21; // [rsp+E0h] [rbp+18h]
  __int64 v22; // [rsp+E8h] [rbp+20h]

  v22 = a4;
  v21 = a3;
  v20 = -1;
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
    Pointer = 0;
  }
  else
  {
    v10 = 0;
    Pointer = -1073741801;
  }
  if ( Pointer >= 0 )
  {
    v12 = *(_QWORD *)(a3 + 544);
    v13 = *(_DWORD *)(a3 + 536);
    v14 = *(_DWORD *)(a3 + 532);
    if ( a1[1] )
    {
      v18 = RtlLengthSid((PSID)(a3 + 464));
      Pointer = HampInProcCreateActivity(a1[1], v21, a3 + 464, v18, v14, v13, v12, v22, a5, &v20);
    }
    else
    {
      v15 = (void *)(a3 + 464);
      v19 = RtlLengthSid(v15);
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                3u,
                                0,
                                *a1,
                                v21,
                                v15,
                                v19,
                                v14,
                                v13,
                                v12,
                                v22,
                                a5,
                                &v20).Pointer;
    }
    if ( Pointer >= 0 )
    {
      v10[6] = v20;
      v16 = v10[5];
      RtlAcquireSRWLockExclusive(v16 + 8);
      *(_DWORD *)(v16 + 16) = GetCurrentThreadId();
      HampIpcChannelAddCallbackUnsafe(v10);
      *(_DWORD *)(v16 + 16) = 0;
      RtlReleaseSRWLockExclusive(v16 + 8);
      v10 = 0;
      *a6 = v20;
      Pointer = 0;
    }
  }
  if ( v10 )
    HamFreeBuffer(v10);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180009ad0  mov     [rsp+arg_18], r9
0x180009ad5  mov     [rsp+arg_10], r8
0x180009ada  push    rbx
0x180009adb  push    rsi
0x180009adc  push    rdi
0x180009add  push    r12
0x180009adf  push    r13
0x180009ae1  push    r14
0x180009ae3  push    r15
0x180009ae5  sub     rsp, 90h
0x180009aec  mov     r15, r8
0x180009aef  mov     rbx, rdx
0x180009af2  mov     r13, rcx
0x180009af5  mov     [rsp+0C8h+arg_0], 0FFFFFFFFFFFFFFFFh
0x180009b01  mov     rcx, gs:60h
0x180009b0a  xor     edx, edx; Flags
0x180009b0c  mov     r8d, 40h ; '@'; Size
0x180009b12  mov     rcx, [rcx+30h]; HeapHandle
0x180009b16  call    cs:__imp_RtlAllocateHeap
0x180009b1c  mov     rdi, rax
0x180009b1f  xor     r12d, r12d
0x180009b22  test    rax, rax
0x180009b25  jz      loc_180009D13
0x180009b2b  mov     [rax], r12
0x180009b2e  mov     [rax+8], r12
0x180009b32  mov     [rax+10h], r12
0x180009b36  mov     [rax+18h], r12
0x180009b3a  mov     [rax+20h], r12
0x180009b3e  lea     rax, [r13+18h]
0x180009b42  mov     [rdi+28h], rax
0x180009b46  mov     [rdi+38h], rbx
0x180009b4a  mov     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x180009b52  mov     ebx, r12d
0x180009b55  mov     [rsp+0C8h+var_50], rdi
0x180009b5a  test    ebx, ebx
0x180009b5c  js      loc_180009C7B
0x180009b62  cmp     qword ptr [r13+8], 0
0x180009b67  jnz     loc_180009C99
0x180009b6d  mov     rbx, [r15+220h]
0x180009b74  mov     esi, [r15+218h]
0x180009b7b  mov     r14d, [r15+214h]
0x180009b82  add     r15, 1D0h
0x180009b89  mov     rcx, r15; Sid
0x180009b8c  call    cs:__imp_RtlLengthSid
0x180009b92  mov     [rsp+0C8h+var_48], r12
0x180009b9a  lea     rcx, [rsp+0C8h+arg_0]
0x180009ba2  mov     [rsp+0C8h+var_68], rcx
0x180009ba7  mov     rcx, [rsp+0C8h+arg_20]
0x180009baf  mov     [rsp+0C8h+var_70], rcx
0x180009bb4  mov     rcx, [rsp+0C8h+arg_18]
0x180009bbc  mov     [rsp+0C8h+var_78], rcx
0x180009bc1  mov     [rsp+0C8h+var_80], rbx
0x180009bc6  mov     dword ptr [rsp+0C8h+var_88], esi
0x180009bca  mov     dword ptr [rsp+0C8h+var_90], r14d
0x180009bcf  mov     dword ptr [rsp+0C8h+var_98], eax
0x180009bd3  mov     [rsp+0C8h+var_A0], r15
0x180009bd8  mov     rax, [rsp+0C8h+arg_10]
0x180009be0  mov     [rsp+0C8h+var_A8], rax
0x180009be5  mov     r9, [r13+0]
0x180009be9  xor     r8d, r8d; pReturnValue
0x180009bec  mov     edx, 3; nProcNum
0x180009bf1  lea     rcx, pProxyInfo; pProxyInfo
0x180009bf8  call    cs:__imp_NdrClientCall3
0x180009bfe  mov     rbx, rax
0x180009c01  mov     [rsp+0C8h+var_48], rax
0x180009c09  mov     [rsp+0C8h+var_58], eax
0x180009c0d  jmp     short loc_180009C25
0x180009c0f  mov     ecx, eax; Status
0x180009c11  call    cs:__imp_I_RpcMapWin32Status
0x180009c17  mov     ebx, eax
0x180009c19  mov     [rsp+0C8h+var_58], eax
0x180009c1d  xor     r12d, r12d
0x180009c20  mov     rdi, [rsp+0C8h+var_50]
0x180009c25  test    ebx, ebx
0x180009c27  js      short loc_180009C7B
0x180009c29  mov     rax, [rsp+0C8h+arg_0]
0x180009c31  mov     [rdi+30h], rax
0x180009c35  mov     rbx, [rdi+28h]
0x180009c39  lea     rcx, [rbx+8]
0x180009c3d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009c43  call    cs:__imp_GetCurrentThreadId
0x180009c49  mov     [rbx+10h], eax
0x180009c4c  mov     rcx, rdi
0x180009c4f  call    HampIpcChannelAddCallbackUnsafe
0x180009c54  mov     [rbx+10h], r12d
0x180009c58  lea     rcx, [rbx+8]
0x180009c5c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009c62  mov     rdi, r12
0x180009c65  mov     rcx, [rsp+0C8h+arg_28]
0x180009c6d  mov     rax, [rsp+0C8h+arg_0]
0x180009c75  mov     [rcx], rax
0x180009c78  mov     ebx, r12d
0x180009c7b  test    rdi, rdi
0x180009c7e  jnz     loc_180009D20
0x180009c84  mov     eax, ebx
0x180009c86  add     rsp, 90h
0x180009c8d  pop     r15
0x180009c8f  pop     r14
0x180009c91  pop     r13
0x180009c93  pop     r12
0x180009c95  pop     rdi
0x180009c96  pop     rsi
0x180009c97  pop     rbx
0x180009c98  retn
0x180009c99  mov     rbx, [r15+220h]
0x180009ca0  mov     esi, [r15+218h]
0x180009ca7  mov     r14d, [r15+214h]
0x180009cae  lea     rcx, [r15+1D0h]; Sid
0x180009cb5  call    cs:__imp_RtlLengthSid
0x180009cbb  lea     rcx, [rsp+0C8h+arg_0]
0x180009cc3  mov     [rsp+0C8h+var_80], rcx
0x180009cc8  mov     rcx, [rsp+0C8h+arg_20]
0x180009cd0  mov     [rsp+0C8h+var_88], rcx
0x180009cd5  mov     rcx, [rsp+0C8h+arg_18]
0x180009cdd  mov     [rsp+0C8h+var_90], rcx
0x180009ce2  mov     [rsp+0C8h+var_98], rbx
0x180009ce7  mov     dword ptr [rsp+0C8h+var_A0], esi
0x180009ceb  mov     dword ptr [rsp+0C8h+var_A8], r14d
0x180009cf0  mov     r9d, eax
0x180009cf3  lea     r8, [r15+1D0h]
0x180009cfa  mov     rdx, [rsp+0C8h+arg_10]
0x180009d02  mov     rcx, [r13+8]
0x180009d06  call    cs:__imp_HampInProcCreateActivity
0x180009d0c  mov     ebx, eax
0x180009d0e  jmp     loc_180009C25
0x180009d13  mov     rdi, r12
0x180009d16  mov     ebx, 0C0000017h
0x180009d1b  jmp     loc_180009B55
0x180009d20  mov     rcx, rdi
0x180009d23  call    HamFreeBuffer
0x180009d28  jmp     loc_180009C84
0x18001b260  push    rbp
0x18001b262  sub     rsp, 70h
0x18001b266  mov     rbp, rdx
0x18001b269  mov     rcx, [rcx]
0x18001b26c  mov     ecx, [rcx]; ExceptionCode
0x18001b26e  call    cs:__imp_RpcExceptionFilter
0x18001b274  nop
0x18001b275  add     rsp, 70h
0x18001b279  pop     rbp
0x18001b27a  retn
```
