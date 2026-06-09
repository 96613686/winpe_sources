# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005a88`
- end: `0x180005b4b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b24`
- `0x180005e70`

## callees

- `0x180005a88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005aec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005aec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ab3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005add`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ab3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005add`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005ac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b25`

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
0x180005a88  push    rbx
0x180005a8a  push    rbp
0x180005a8b  push    rsi
0x180005a8c  push    rdi
0x180005a8d  sub     rsp, 28h
0x180005a91  mov     rbp, rdx
0x180005a94  mov     rdi, rcx
0x180005a97  test    rdx, rdx
0x180005a9a  jnz     short loc_180005ADD
0x180005a9c  mov     rcx, [rcx]
0x180005a9f  test    rcx, rcx
0x180005aa2  jz      short loc_180005AD6
0x180005aa4  or      eax, 0FFFFFFFFh
0x180005aa7  lock xadd [rcx], eax
0x180005aab  cmp     eax, 1
0x180005aae  jnz     short loc_180005AC7
0x180005ab0  mov     rbx, [rdi]
0x180005ab3  call    cs:__imp_GetProcessHeap
0x180005ab9  mov     r8, rbx; lpMem
0x180005abc  xor     edx, edx; dwFlags
0x180005abe  mov     rcx, rax; hHeap
0x180005ac1  call    cs:__imp_HeapFree
0x180005ac7  mov     qword ptr [rdi], 0
0x180005ace  mov     qword ptr [rdi+8], 0
0x180005ad6  mov     eax, 1
0x180005adb  jmp     short loc_180005B42
0x180005add  call    cs:__imp_GetProcessHeap
0x180005ae3  lea     r8, [rbp+4]; dwBytes
0x180005ae7  xor     edx, edx; dwFlags
0x180005ae9  mov     rcx, rax; hHeap
0x180005aec  call    cs:__imp_HeapAlloc
0x180005af2  mov     rsi, rax
0x180005af5  test    rax, rax
0x180005af8  jz      short loc_180005B42
0x180005afa  mov     dword ptr [rax], 0
0x180005b00  mov     rcx, [rdi]
0x180005b03  test    rcx, rcx
0x180005b06  jz      short loc_180005B33
0x180005b08  or      eax, 0FFFFFFFFh
0x180005b0b  lock xadd [rcx], eax
0x180005b0f  cmp     eax, 1
0x180005b12  jnz     short loc_180005B2B
0x180005b14  mov     rbx, [rdi]
0x180005b17  call    cs:__imp_GetProcessHeap
0x180005b1d  mov     r8, rbx; lpMem
0x180005b20  xor     edx, edx; dwFlags
0x180005b22  mov     rcx, rax; hHeap
0x180005b25  call    cs:__imp_HeapFree
0x180005b2b  mov     qword ptr [rdi+8], 0
0x180005b33  mov     [rdi], rsi
0x180005b36  mov     eax, 1
0x180005b3b  mov     [rdi+8], rbp
0x180005b3f  lock add [rsi], eax
0x180005b42  add     rsp, 28h
0x180005b46  pop     rdi
0x180005b47  pop     rsi
0x180005b48  pop     rbp
0x180005b49  pop     rbx
0x180005b4a  retn
```
