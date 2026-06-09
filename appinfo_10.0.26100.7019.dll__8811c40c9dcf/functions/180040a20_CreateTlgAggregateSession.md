# CreateTlgAggregateSession

- ea: `0x180040a20`
- end: `0x180040af6`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180041608`

## callees

- `0x180040a20`
- `0x180040afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180040a74`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180040a74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040a3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040a3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040a54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040a54`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180040a9c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180040a9c`

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
    if ( !a1 || !dword_18005BC08 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180040a20  mov     [rsp+arg_0], rbx
0x180040a25  mov     [rsp+arg_18], rsi
0x180040a2a  push    rdi
0x180040a2b  sub     rsp, 30h
0x180040a2f  mov     sil, cl
0x180040a32  xor     dil, dil
0x180040a35  mov     [rsp+38h+arg_8], dil
0x180040a3a  call    cs:__imp_GetProcessHeap
0x180040a41  nop     dword ptr [rax+rax+00h]
0x180040a46  mov     rcx, rax; hHeap
0x180040a49  mov     edx, 8; dwFlags
0x180040a4e  mov     r8d, 168h; dwBytes
0x180040a54  call    cs:__imp_HeapAlloc
0x180040a5b  nop     dword ptr [rax+rax+00h]
0x180040a60  mov     rbx, rax
0x180040a63  mov     [rsp+38h+arg_10], rax
0x180040a68  test    rax, rax
0x180040a6b  jz      short loc_180040AD3
0x180040a6d  lea     rcx, [rax+108h]; SRWLock
0x180040a74  call    cs:__imp_InitializeSRWLock
0x180040a7b  nop     dword ptr [rax+rax+00h]
0x180040a80  test    sil, sil
0x180040a83  jz      short loc_180040AD0
0x180040a85  mov     ecx, cs:dword_18005BC08
0x180040a8b  test    ecx, ecx
0x180040a8d  jnz     short loc_180040AD3
0x180040a8f  xor     r8d, r8d; pcbe
0x180040a92  mov     rdx, rbx; pv
0x180040a95  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180040a9c  call    cs:__imp_CreateThreadpoolTimer
0x180040aa3  nop     dword ptr [rax+rax+00h]
0x180040aa8  mov     [rbx+158h], rax
0x180040aaf  jmp     short loc_180040AC6
0x180040ab1  mov     eax, 1
0x180040ab6  xchg    eax, cs:dword_18005BC08
0x180040abc  mov     dil, [rsp+38h+arg_8]
0x180040ac1  mov     rbx, [rsp+38h+arg_10]
0x180040ac6  cmp     qword ptr [rbx+158h], 0
0x180040ace  jz      short loc_180040AD3
0x180040ad0  mov     dil, 1
0x180040ad3  test    dil, dil
0x180040ad6  jnz     short loc_180040AE2
0x180040ad8  mov     rcx, rbx; lpMem
0x180040adb  call    DestroyAggregateSession
0x180040ae0  xor     ebx, ebx
0x180040ae2  mov     rax, rbx
0x180040ae5  mov     rbx, [rsp+38h+arg_0]
0x180040aea  mov     rsi, [rsp+38h+arg_18]
0x180040aef  add     rsp, 30h
0x180040af3  pop     rdi
0x180040af4  retn
0x180042dc6  push    rbp
0x180042dc8  sub     rsp, 20h
0x180042dcc  mov     rbp, rdx
0x180042dcf  mov     [rbp+28h], rcx
0x180042dd3  mov     rax, [rcx]
0x180042dd6  mov     ecx, [rax]
0x180042dd8  mov     [rbp+20h], ecx
0x180042ddb  xor     eax, eax
0x180042ddd  cmp     ecx, 0C000000Dh
0x180042de3  setz    al
0x180042de6  add     rsp, 20h
0x180042dea  pop     rbp
0x180042deb  retn
```
