# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008784`
- end: `0x180008847`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800074d8`
- `0x180008b60`

## callees

- `0x180008784`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800087e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800087e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008821`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008821`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008813`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008813`

## pseudocode

```c
__int64 __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    result = (__int64)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = (volatile signed __int32 *)result;
    if ( result )
    {
      *(_DWORD *)result = 0;
      if ( *this )
      {
        if ( _InterlockedExchangeAdd(*this, 0xFFFFFFFF) == 1 )
        {
          v10 = *this;
          v11 = GetProcessHeap();
          HeapFree(v11, 0, (LPVOID)v10);
        }
        this[1] = 0;
      }
      *this = v9;
      result = 1;
      this[1] = a2;
      _InterlockedAdd(v9, 1u);
    }
  }
  else
  {
    v4 = *this;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
      {
        v5 = *this;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, (LPVOID)v5);
      }
      *this = 0;
      this[1] = 0;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180008784  push    rbx
0x180008786  push    rbp
0x180008787  push    rsi
0x180008788  push    rdi
0x180008789  sub     rsp, 28h
0x18000878d  mov     rbp, rdx
0x180008790  mov     rdi, rcx
0x180008793  test    rdx, rdx
0x180008796  jnz     short loc_1800087D9
0x180008798  mov     rcx, [rcx]
0x18000879b  test    rcx, rcx
0x18000879e  jz      short loc_1800087D2
0x1800087a0  or      eax, 0FFFFFFFFh
0x1800087a3  lock xadd [rcx], eax
0x1800087a7  cmp     eax, 1
0x1800087aa  jnz     short loc_1800087C3
0x1800087ac  mov     rbx, [rdi]
0x1800087af  call    cs:__imp_GetProcessHeap
0x1800087b5  mov     r8, rbx; lpMem
0x1800087b8  xor     edx, edx; dwFlags
0x1800087ba  mov     rcx, rax; hHeap
0x1800087bd  call    cs:__imp_HeapFree
0x1800087c3  mov     qword ptr [rdi], 0
0x1800087ca  mov     qword ptr [rdi+8], 0
0x1800087d2  mov     eax, 1
0x1800087d7  jmp     short loc_18000883E
0x1800087d9  call    cs:__imp_GetProcessHeap
0x1800087df  lea     r8, [rbp+4]; dwBytes
0x1800087e3  xor     edx, edx; dwFlags
0x1800087e5  mov     rcx, rax; hHeap
0x1800087e8  call    cs:__imp_HeapAlloc
0x1800087ee  mov     rsi, rax
0x1800087f1  test    rax, rax
0x1800087f4  jz      short loc_18000883E
0x1800087f6  mov     dword ptr [rax], 0
0x1800087fc  mov     rcx, [rdi]
0x1800087ff  test    rcx, rcx
0x180008802  jz      short loc_18000882F
0x180008804  or      eax, 0FFFFFFFFh
0x180008807  lock xadd [rcx], eax
0x18000880b  cmp     eax, 1
0x18000880e  jnz     short loc_180008827
0x180008810  mov     rbx, [rdi]
0x180008813  call    cs:__imp_GetProcessHeap
0x180008819  mov     r8, rbx; lpMem
0x18000881c  xor     edx, edx; dwFlags
0x18000881e  mov     rcx, rax; hHeap
0x180008821  call    cs:__imp_HeapFree
0x180008827  mov     qword ptr [rdi+8], 0
0x18000882f  mov     [rdi], rsi
0x180008832  mov     eax, 1
0x180008837  mov     [rdi+8], rbp
0x18000883b  lock add [rsi], eax
0x18000883e  add     rsp, 28h
0x180008842  pop     rdi
0x180008843  pop     rsi
0x180008844  pop     rbp
0x180008845  pop     rbx
0x180008846  retn
```
