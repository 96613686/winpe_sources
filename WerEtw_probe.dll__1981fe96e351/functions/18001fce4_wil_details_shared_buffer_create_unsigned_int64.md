# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18001fce4`
- end: `0x18001fda7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e9f0`
- `0x180020100`

## callees

- `0x18001fce4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fd48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001fd48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fd81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fd73`

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
0x18001fce4  push    rbx
0x18001fce6  push    rbp
0x18001fce7  push    rsi
0x18001fce8  push    rdi
0x18001fce9  sub     rsp, 28h
0x18001fced  mov     rbp, rdx
0x18001fcf0  mov     rdi, rcx
0x18001fcf3  test    rdx, rdx
0x18001fcf6  jnz     short loc_18001FD39
0x18001fcf8  mov     rcx, [rcx]
0x18001fcfb  test    rcx, rcx
0x18001fcfe  jz      short loc_18001FD32
0x18001fd00  or      eax, 0FFFFFFFFh
0x18001fd03  lock xadd [rcx], eax
0x18001fd07  cmp     eax, 1
0x18001fd0a  jnz     short loc_18001FD23
0x18001fd0c  mov     rbx, [rdi]
0x18001fd0f  call    cs:__imp_GetProcessHeap
0x18001fd15  mov     r8, rbx; lpMem
0x18001fd18  xor     edx, edx; dwFlags
0x18001fd1a  mov     rcx, rax; hHeap
0x18001fd1d  call    cs:__imp_HeapFree
0x18001fd23  mov     qword ptr [rdi], 0
0x18001fd2a  mov     qword ptr [rdi+8], 0
0x18001fd32  mov     eax, 1
0x18001fd37  jmp     short loc_18001FD9E
0x18001fd39  call    cs:__imp_GetProcessHeap
0x18001fd3f  lea     r8, [rbp+4]; dwBytes
0x18001fd43  xor     edx, edx; dwFlags
0x18001fd45  mov     rcx, rax; hHeap
0x18001fd48  call    cs:__imp_HeapAlloc
0x18001fd4e  mov     rsi, rax
0x18001fd51  test    rax, rax
0x18001fd54  jz      short loc_18001FD9E
0x18001fd56  mov     dword ptr [rax], 0
0x18001fd5c  mov     rcx, [rdi]
0x18001fd5f  test    rcx, rcx
0x18001fd62  jz      short loc_18001FD8F
0x18001fd64  or      eax, 0FFFFFFFFh
0x18001fd67  lock xadd [rcx], eax
0x18001fd6b  cmp     eax, 1
0x18001fd6e  jnz     short loc_18001FD87
0x18001fd70  mov     rbx, [rdi]
0x18001fd73  call    cs:__imp_GetProcessHeap
0x18001fd79  mov     r8, rbx; lpMem
0x18001fd7c  xor     edx, edx; dwFlags
0x18001fd7e  mov     rcx, rax; hHeap
0x18001fd81  call    cs:__imp_HeapFree
0x18001fd87  mov     qword ptr [rdi+8], 0
0x18001fd8f  mov     [rdi], rsi
0x18001fd92  mov     eax, 1
0x18001fd97  mov     [rdi+8], rbp
0x18001fd9b  lock add [rsi], eax
0x18001fd9e  add     rsp, 28h
0x18001fda2  pop     rdi
0x18001fda3  pop     rsi
0x18001fda4  pop     rbp
0x18001fda5  pop     rbx
0x18001fda6  retn
```
