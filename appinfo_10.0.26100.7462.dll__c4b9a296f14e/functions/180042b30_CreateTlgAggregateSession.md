# CreateTlgAggregateSession

- ea: `0x180042b30`
- end: `0x180042c06`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180043718`

## callees

- `0x180042b30`
- `0x180042c0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180042b84`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180042b84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042b64`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180042b64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042b4a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042b4a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180042bac`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180042bac`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_18005DB48 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    DestroyAggregateSession(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180042b30  mov     [rsp+arg_0], rbx
0x180042b35  mov     [rsp+arg_18], rsi
0x180042b3a  push    rdi
0x180042b3b  sub     rsp, 30h
0x180042b3f  mov     sil, cl
0x180042b42  xor     dil, dil
0x180042b45  mov     [rsp+38h+arg_8], dil
0x180042b4a  call    cs:__imp_GetProcessHeap
0x180042b51  nop     dword ptr [rax+rax+00h]
0x180042b56  mov     rcx, rax; hHeap
0x180042b59  mov     edx, 8; dwFlags
0x180042b5e  mov     r8d, 168h; dwBytes
0x180042b64  call    cs:__imp_HeapAlloc
0x180042b6b  nop     dword ptr [rax+rax+00h]
0x180042b70  mov     rbx, rax
0x180042b73  mov     [rsp+38h+arg_10], rax
0x180042b78  test    rax, rax
0x180042b7b  jz      short loc_180042BE3
0x180042b7d  lea     rcx, [rax+108h]; SRWLock
0x180042b84  call    cs:__imp_InitializeSRWLock
0x180042b8b  nop     dword ptr [rax+rax+00h]
0x180042b90  test    sil, sil
0x180042b93  jz      short loc_180042BE0
0x180042b95  mov     ecx, cs:dword_18005DB48
0x180042b9b  test    ecx, ecx
0x180042b9d  jnz     short loc_180042BE3
0x180042b9f  xor     r8d, r8d; pcbe
0x180042ba2  mov     rdx, rbx; pv
0x180042ba5  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180042bac  call    cs:__imp_CreateThreadpoolTimer
0x180042bb3  nop     dword ptr [rax+rax+00h]
0x180042bb8  mov     [rbx+158h], rax
0x180042bbf  jmp     short loc_180042BD6
0x180042bc1  mov     eax, 1
0x180042bc6  xchg    eax, cs:dword_18005DB48
0x180042bcc  mov     dil, [rsp+38h+arg_8]
0x180042bd1  mov     rbx, [rsp+38h+arg_10]
0x180042bd6  cmp     qword ptr [rbx+158h], 0
0x180042bde  jz      short loc_180042BE3
0x180042be0  mov     dil, 1
0x180042be3  test    dil, dil
0x180042be6  jnz     short loc_180042BF2
0x180042be8  mov     rcx, rbx; lpMem
0x180042beb  call    DestroyAggregateSession
0x180042bf0  xor     ebx, ebx
0x180042bf2  mov     rax, rbx
0x180042bf5  mov     rbx, [rsp+38h+arg_0]
0x180042bfa  mov     rsi, [rsp+38h+arg_18]
0x180042bff  add     rsp, 30h
0x180042c03  pop     rdi
0x180042c04  retn
0x180044e96  push    rbp
0x180044e98  sub     rsp, 20h
0x180044e9c  mov     rbp, rdx
0x180044e9f  mov     [rbp+28h], rcx
0x180044ea3  mov     rax, [rcx]
0x180044ea6  mov     ecx, [rax]
0x180044ea8  mov     [rbp+20h], ecx
0x180044eab  xor     eax, eax
0x180044ead  cmp     ecx, 0C000000Dh
0x180044eb3  setz    al
0x180044eb6  add     rsp, 20h
0x180044eba  pop     rbp
0x180044ebb  retn
```
