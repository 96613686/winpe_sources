# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180009c44`
- end: `0x180009d07`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800087c8`
- `0x180009e00`

## callees

- `0x180009c44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009ca8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009ca8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009ce1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cd3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009cd3`

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
0x180009c44  push    rbx
0x180009c46  push    rbp
0x180009c47  push    rsi
0x180009c48  push    rdi
0x180009c49  sub     rsp, 28h
0x180009c4d  mov     rbp, rdx
0x180009c50  mov     rdi, rcx
0x180009c53  test    rdx, rdx
0x180009c56  jnz     short loc_180009C99
0x180009c58  mov     rcx, [rcx]
0x180009c5b  test    rcx, rcx
0x180009c5e  jz      short loc_180009C92
0x180009c60  or      eax, 0FFFFFFFFh
0x180009c63  lock xadd [rcx], eax
0x180009c67  cmp     eax, 1
0x180009c6a  jnz     short loc_180009C83
0x180009c6c  mov     rbx, [rdi]
0x180009c6f  call    cs:__imp_GetProcessHeap
0x180009c75  mov     r8, rbx; lpMem
0x180009c78  xor     edx, edx; dwFlags
0x180009c7a  mov     rcx, rax; hHeap
0x180009c7d  call    cs:__imp_HeapFree
0x180009c83  mov     qword ptr [rdi], 0
0x180009c8a  mov     qword ptr [rdi+8], 0
0x180009c92  mov     eax, 1
0x180009c97  jmp     short loc_180009CFE
0x180009c99  call    cs:__imp_GetProcessHeap
0x180009c9f  lea     r8, [rbp+4]; dwBytes
0x180009ca3  xor     edx, edx; dwFlags
0x180009ca5  mov     rcx, rax; hHeap
0x180009ca8  call    cs:__imp_HeapAlloc
0x180009cae  mov     rsi, rax
0x180009cb1  test    rax, rax
0x180009cb4  jz      short loc_180009CFE
0x180009cb6  mov     dword ptr [rax], 0
0x180009cbc  mov     rcx, [rdi]
0x180009cbf  test    rcx, rcx
0x180009cc2  jz      short loc_180009CEF
0x180009cc4  or      eax, 0FFFFFFFFh
0x180009cc7  lock xadd [rcx], eax
0x180009ccb  cmp     eax, 1
0x180009cce  jnz     short loc_180009CE7
0x180009cd0  mov     rbx, [rdi]
0x180009cd3  call    cs:__imp_GetProcessHeap
0x180009cd9  mov     r8, rbx; lpMem
0x180009cdc  xor     edx, edx; dwFlags
0x180009cde  mov     rcx, rax; hHeap
0x180009ce1  call    cs:__imp_HeapFree
0x180009ce7  mov     qword ptr [rdi+8], 0
0x180009cef  mov     [rdi], rsi
0x180009cf2  mov     eax, 1
0x180009cf7  mov     [rdi+8], rbp
0x180009cfb  lock add [rsi], eax
0x180009cfe  add     rsp, 28h
0x180009d02  pop     rdi
0x180009d03  pop     rsi
0x180009d04  pop     rbp
0x180009d05  pop     rbx
0x180009d06  retn
```
