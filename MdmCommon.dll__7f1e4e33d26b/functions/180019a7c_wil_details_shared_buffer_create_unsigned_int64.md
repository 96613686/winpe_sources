# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180019a7c`
- end: `0x180019b3f`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019080`
- `0x180019b50`

## callees

- `0x180019a7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019ae0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019ae0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019aa7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b0b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019aa7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019b0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ab5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b19`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ab5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b19`

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
0x180019a7c  push    rbx
0x180019a7e  push    rbp
0x180019a7f  push    rsi
0x180019a80  push    rdi
0x180019a81  sub     rsp, 28h
0x180019a85  mov     rbp, rdx
0x180019a88  mov     rdi, rcx
0x180019a8b  test    rdx, rdx
0x180019a8e  jnz     short loc_180019AD1
0x180019a90  mov     rcx, [rcx]
0x180019a93  test    rcx, rcx
0x180019a96  jz      short loc_180019ACA
0x180019a98  or      eax, 0FFFFFFFFh
0x180019a9b  lock xadd [rcx], eax
0x180019a9f  cmp     eax, 1
0x180019aa2  jnz     short loc_180019ABB
0x180019aa4  mov     rbx, [rdi]
0x180019aa7  call    cs:__imp_GetProcessHeap
0x180019aad  mov     r8, rbx; lpMem
0x180019ab0  xor     edx, edx; dwFlags
0x180019ab2  mov     rcx, rax; hHeap
0x180019ab5  call    cs:__imp_HeapFree
0x180019abb  mov     qword ptr [rdi], 0
0x180019ac2  mov     qword ptr [rdi+8], 0
0x180019aca  mov     eax, 1
0x180019acf  jmp     short loc_180019B36
0x180019ad1  call    cs:__imp_GetProcessHeap
0x180019ad7  lea     r8, [rbp+4]; dwBytes
0x180019adb  xor     edx, edx; dwFlags
0x180019add  mov     rcx, rax; hHeap
0x180019ae0  call    cs:__imp_HeapAlloc
0x180019ae6  mov     rsi, rax
0x180019ae9  test    rax, rax
0x180019aec  jz      short loc_180019B36
0x180019aee  mov     dword ptr [rax], 0
0x180019af4  mov     rcx, [rdi]
0x180019af7  test    rcx, rcx
0x180019afa  jz      short loc_180019B27
0x180019afc  or      eax, 0FFFFFFFFh
0x180019aff  lock xadd [rcx], eax
0x180019b03  cmp     eax, 1
0x180019b06  jnz     short loc_180019B1F
0x180019b08  mov     rbx, [rdi]
0x180019b0b  call    cs:__imp_GetProcessHeap
0x180019b11  mov     r8, rbx; lpMem
0x180019b14  xor     edx, edx; dwFlags
0x180019b16  mov     rcx, rax; hHeap
0x180019b19  call    cs:__imp_HeapFree
0x180019b1f  mov     qword ptr [rdi+8], 0
0x180019b27  mov     [rdi], rsi
0x180019b2a  mov     eax, 1
0x180019b2f  mov     [rdi+8], rbp
0x180019b33  lock add [rsi], eax
0x180019b36  add     rsp, 28h
0x180019b3a  pop     rdi
0x180019b3b  pop     rsi
0x180019b3c  pop     rbp
0x180019b3d  pop     rbx
0x180019b3e  retn
```
