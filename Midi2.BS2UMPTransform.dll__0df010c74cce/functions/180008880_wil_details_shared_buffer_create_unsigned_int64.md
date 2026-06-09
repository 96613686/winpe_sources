# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008880`
- end: `0x180008943`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007960`
- `0x180008950`

## callees

- `0x180008880`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000890f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000890f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800088e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800088e4`

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
0x180008880  push    rbx
0x180008882  push    rbp
0x180008883  push    rsi
0x180008884  push    rdi
0x180008885  sub     rsp, 28h
0x180008889  mov     rbp, rdx
0x18000888c  mov     rdi, rcx
0x18000888f  test    rdx, rdx
0x180008892  jnz     short loc_1800088D5
0x180008894  mov     rcx, [rcx]
0x180008897  test    rcx, rcx
0x18000889a  jz      short loc_1800088CE
0x18000889c  or      eax, 0FFFFFFFFh
0x18000889f  lock xadd [rcx], eax
0x1800088a3  cmp     eax, 1
0x1800088a6  jnz     short loc_1800088BF
0x1800088a8  mov     rbx, [rdi]
0x1800088ab  call    cs:__imp_GetProcessHeap
0x1800088b1  mov     r8, rbx; lpMem
0x1800088b4  xor     edx, edx; dwFlags
0x1800088b6  mov     rcx, rax; hHeap
0x1800088b9  call    cs:__imp_HeapFree
0x1800088bf  mov     qword ptr [rdi], 0
0x1800088c6  mov     qword ptr [rdi+8], 0
0x1800088ce  mov     eax, 1
0x1800088d3  jmp     short loc_18000893A
0x1800088d5  call    cs:__imp_GetProcessHeap
0x1800088db  lea     r8, [rbp+4]; dwBytes
0x1800088df  xor     edx, edx; dwFlags
0x1800088e1  mov     rcx, rax; hHeap
0x1800088e4  call    cs:__imp_HeapAlloc
0x1800088ea  mov     rsi, rax
0x1800088ed  test    rax, rax
0x1800088f0  jz      short loc_18000893A
0x1800088f2  mov     dword ptr [rax], 0
0x1800088f8  mov     rcx, [rdi]
0x1800088fb  test    rcx, rcx
0x1800088fe  jz      short loc_18000892B
0x180008900  or      eax, 0FFFFFFFFh
0x180008903  lock xadd [rcx], eax
0x180008907  cmp     eax, 1
0x18000890a  jnz     short loc_180008923
0x18000890c  mov     rbx, [rdi]
0x18000890f  call    cs:__imp_GetProcessHeap
0x180008915  mov     r8, rbx; lpMem
0x180008918  xor     edx, edx; dwFlags
0x18000891a  mov     rcx, rax; hHeap
0x18000891d  call    cs:__imp_HeapFree
0x180008923  mov     qword ptr [rdi+8], 0
0x18000892b  mov     [rdi], rsi
0x18000892e  mov     eax, 1
0x180008933  mov     [rdi+8], rbp
0x180008937  lock add [rsi], eax
0x18000893a  add     rsp, 28h
0x18000893e  pop     rdi
0x18000893f  pop     rsi
0x180008940  pop     rbp
0x180008941  pop     rbx
0x180008942  retn
```
