# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800086a4`
- end: `0x180008767`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007418`
- `0x180008860`

## callees

- `0x1800086a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008733`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008733`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008741`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008741`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008708`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008708`

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
0x1800086a4  push    rbx
0x1800086a6  push    rbp
0x1800086a7  push    rsi
0x1800086a8  push    rdi
0x1800086a9  sub     rsp, 28h
0x1800086ad  mov     rbp, rdx
0x1800086b0  mov     rdi, rcx
0x1800086b3  test    rdx, rdx
0x1800086b6  jnz     short loc_1800086F9
0x1800086b8  mov     rcx, [rcx]
0x1800086bb  test    rcx, rcx
0x1800086be  jz      short loc_1800086F2
0x1800086c0  or      eax, 0FFFFFFFFh
0x1800086c3  lock xadd [rcx], eax
0x1800086c7  cmp     eax, 1
0x1800086ca  jnz     short loc_1800086E3
0x1800086cc  mov     rbx, [rdi]
0x1800086cf  call    cs:__imp_GetProcessHeap
0x1800086d5  mov     r8, rbx; lpMem
0x1800086d8  xor     edx, edx; dwFlags
0x1800086da  mov     rcx, rax; hHeap
0x1800086dd  call    cs:__imp_HeapFree
0x1800086e3  mov     qword ptr [rdi], 0
0x1800086ea  mov     qword ptr [rdi+8], 0
0x1800086f2  mov     eax, 1
0x1800086f7  jmp     short loc_18000875E
0x1800086f9  call    cs:__imp_GetProcessHeap
0x1800086ff  lea     r8, [rbp+4]; dwBytes
0x180008703  xor     edx, edx; dwFlags
0x180008705  mov     rcx, rax; hHeap
0x180008708  call    cs:__imp_HeapAlloc
0x18000870e  mov     rsi, rax
0x180008711  test    rax, rax
0x180008714  jz      short loc_18000875E
0x180008716  mov     dword ptr [rax], 0
0x18000871c  mov     rcx, [rdi]
0x18000871f  test    rcx, rcx
0x180008722  jz      short loc_18000874F
0x180008724  or      eax, 0FFFFFFFFh
0x180008727  lock xadd [rcx], eax
0x18000872b  cmp     eax, 1
0x18000872e  jnz     short loc_180008747
0x180008730  mov     rbx, [rdi]
0x180008733  call    cs:__imp_GetProcessHeap
0x180008739  mov     r8, rbx; lpMem
0x18000873c  xor     edx, edx; dwFlags
0x18000873e  mov     rcx, rax; hHeap
0x180008741  call    cs:__imp_HeapFree
0x180008747  mov     qword ptr [rdi+8], 0
0x18000874f  mov     [rdi], rsi
0x180008752  mov     eax, 1
0x180008757  mov     [rdi+8], rbp
0x18000875b  lock add [rsi], eax
0x18000875e  add     rsp, 28h
0x180008762  pop     rdi
0x180008763  pop     rsi
0x180008764  pop     rbp
0x180008765  pop     rbx
0x180008766  retn
```
