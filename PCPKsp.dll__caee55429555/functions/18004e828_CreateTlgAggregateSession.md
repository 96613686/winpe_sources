# CreateTlgAggregateSession

- ea: `0x18004e828`
- end: `0x18004e902`
- name: `CreateTlgAggregateSession`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004e618`

## callees

- `0x18004e828`
- `0x18004eaa4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e842`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e842`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e85c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004e85c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004e8a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004e8a4`
- `KERNEL32!InitializeSRWLock` at `0x18004e87c`
- `KERNEL32!InitializeSRWLock` at `0x18004e87c`

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
    if ( !a1 || !dword_180109BF8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x18004e828  mov     [rsp+arg_0], rbx
0x18004e82d  mov     [rsp+arg_18], rsi
0x18004e832  push    rdi
0x18004e833  sub     rsp, 20h
0x18004e837  mov     sil, cl
0x18004e83a  xor     dil, dil
0x18004e83d  mov     [rsp+28h+arg_8], dil
0x18004e842  call    cs:__imp_GetProcessHeap
0x18004e849  nop     dword ptr [rax+rax+00h]
0x18004e84e  mov     rcx, rax; hHeap
0x18004e851  mov     edx, 8; dwFlags
0x18004e856  mov     r8d, 168h; dwBytes
0x18004e85c  call    cs:__imp_HeapAlloc
0x18004e863  nop     dword ptr [rax+rax+00h]
0x18004e868  mov     rbx, rax
0x18004e86b  mov     [rsp+28h+arg_10], rax
0x18004e870  test    rax, rax
0x18004e873  jz      short loc_18004E8D8
0x18004e875  lea     rcx, [rax+108h]; SRWLock
0x18004e87c  call    cs:__imp_InitializeSRWLock
0x18004e883  nop     dword ptr [rax+rax+00h]
0x18004e888  test    sil, sil
0x18004e88b  jz      short loc_18004E8F1
0x18004e88d  mov     ecx, cs:dword_180109BF8
0x18004e893  test    ecx, ecx
0x18004e895  jnz     short loc_18004E8D8
0x18004e897  xor     r8d, r8d; pcbe
0x18004e89a  mov     rdx, rbx; pv
0x18004e89d  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x18004e8a4  call    cs:__imp_CreateThreadpoolTimer
0x18004e8ab  nop     dword ptr [rax+rax+00h]
0x18004e8b0  mov     [rbx+158h], rax
0x18004e8b7  jmp     short loc_18004E8CE
0x18004e8b9  mov     eax, 1
0x18004e8be  xchg    eax, cs:dword_180109BF8
0x18004e8c4  mov     dil, [rsp+28h+arg_8]
0x18004e8c9  mov     rbx, [rsp+28h+arg_10]
0x18004e8ce  cmp     qword ptr [rbx+158h], 0
0x18004e8d6  jnz     short loc_18004E8F1
0x18004e8d8  test    dil, dil
0x18004e8db  jz      short loc_18004E8F6
0x18004e8dd  mov     rax, rbx
0x18004e8e0  mov     rbx, [rsp+28h+arg_0]
0x18004e8e5  mov     rsi, [rsp+28h+arg_18]
0x18004e8ea  add     rsp, 20h
0x18004e8ee  pop     rdi
0x18004e8ef  retn
0x18004e8f1  mov     dil, 1
0x18004e8f4  jmp     short loc_18004E8D8
0x18004e8f6  mov     rcx, rbx; lpMem
0x18004e8f9  call    DestroyAggregateSession
0x18004e8fe  xor     ebx, ebx
0x18004e900  jmp     short loc_18004E8DD
0x1800c5c5c  push    rbp
0x1800c5c5e  sub     rsp, 20h
0x1800c5c62  mov     rbp, rdx
0x1800c5c65  mov     rax, [rcx]
0x1800c5c68  xor     ecx, ecx
0x1800c5c6a  cmp     dword ptr [rax], 0C000000Dh
0x1800c5c70  setz    cl
0x1800c5c73  mov     eax, ecx
0x1800c5c75  add     rsp, 20h
0x1800c5c79  pop     rbp
0x1800c5c7a  retn
```
