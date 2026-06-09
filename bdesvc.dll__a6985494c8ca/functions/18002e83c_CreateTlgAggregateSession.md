# CreateTlgAggregateSession

- ea: `0x18002e83c`
- end: `0x18002e912`
- name: `CreateTlgAggregateSession`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e724`

## callees

- `0x18002e83c`
- `0x18007a348`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002e890`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002e890`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e870`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e870`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e856`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e856`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002e8b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002e8b8`

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
    if ( !a1 || !dword_18009B898 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18002e83c  mov     [rsp+arg_0], rbx
0x18002e841  mov     [rsp+arg_18], rsi
0x18002e846  push    rdi
0x18002e847  sub     rsp, 20h
0x18002e84b  mov     sil, cl
0x18002e84e  xor     dil, dil
0x18002e851  mov     [rsp+28h+arg_8], dil
0x18002e856  call    cs:__imp_GetProcessHeap
0x18002e85d  nop     dword ptr [rax+rax+00h]
0x18002e862  mov     rcx, rax; hHeap
0x18002e865  mov     edx, 8; dwFlags
0x18002e86a  mov     r8d, 168h; dwBytes
0x18002e870  call    cs:__imp_HeapAlloc
0x18002e877  nop     dword ptr [rax+rax+00h]
0x18002e87c  mov     rbx, rax
0x18002e87f  mov     [rsp+28h+arg_10], rax
0x18002e884  test    rax, rax
0x18002e887  jz      short loc_18002E8EF
0x18002e889  lea     rcx, [rax+108h]; SRWLock
0x18002e890  call    cs:__imp_InitializeSRWLock
0x18002e897  nop     dword ptr [rax+rax+00h]
0x18002e89c  test    sil, sil
0x18002e89f  jz      short loc_18002E8EC
0x18002e8a1  mov     ecx, cs:dword_18009B898
0x18002e8a7  test    ecx, ecx
0x18002e8a9  jnz     short loc_18002E8EF
0x18002e8ab  xor     r8d, r8d; pcbe
0x18002e8ae  mov     rdx, rbx; pv
0x18002e8b1  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18002e8b8  call    cs:__imp_CreateThreadpoolTimer
0x18002e8bf  nop     dword ptr [rax+rax+00h]
0x18002e8c4  mov     [rbx+158h], rax
0x18002e8cb  jmp     short loc_18002E8E2
0x18002e8cd  mov     eax, 1
0x18002e8d2  xchg    eax, cs:dword_18009B898
0x18002e8d8  mov     dil, [rsp+28h+arg_8]
0x18002e8dd  mov     rbx, [rsp+28h+arg_10]
0x18002e8e2  cmp     qword ptr [rbx+158h], 0
0x18002e8ea  jz      short loc_18002E8EF
0x18002e8ec  mov     dil, 1
0x18002e8ef  test    dil, dil
0x18002e8f2  jnz     short loc_18002E8FE
0x18002e8f4  mov     rcx, rbx; lpMem
0x18002e8f7  call    DestroyAggregateSession
0x18002e8fc  xor     ebx, ebx
0x18002e8fe  mov     rax, rbx
0x18002e901  mov     rbx, [rsp+28h+arg_0]
0x18002e906  mov     rsi, [rsp+28h+arg_18]
0x18002e90b  add     rsp, 20h
0x18002e90f  pop     rdi
0x18002e910  retn
0x18007c17f  push    rbp
0x18007c181  sub     rsp, 20h
0x18007c185  mov     rbp, rdx
0x18007c188  mov     rax, [rcx]
0x18007c18b  xor     ecx, ecx
0x18007c18d  cmp     dword ptr [rax], 0C000000Dh
0x18007c193  setz    cl
0x18007c196  mov     eax, ecx
0x18007c198  add     rsp, 20h
0x18007c19c  pop     rbp
0x18007c19d  retn
```
