# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180015bd4`
- end: `0x180015c97`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001485c`
- `0x180015d90`

## callees

- `0x180015bd4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180015c0d`
- `KERNEL32!HeapFree` at `0x180015c71`
- `KERNEL32!HeapFree` at `0x180015c0d`
- `KERNEL32!HeapFree` at `0x180015c71`
- `KERNEL32!HeapAlloc` at `0x180015c38`
- `KERNEL32!HeapAlloc` at `0x180015c38`
- `KERNEL32!GetProcessHeap` at `0x180015bff`
- `KERNEL32!GetProcessHeap` at `0x180015c29`
- `KERNEL32!GetProcessHeap` at `0x180015c63`
- `KERNEL32!GetProcessHeap` at `0x180015bff`
- `KERNEL32!GetProcessHeap` at `0x180015c29`
- `KERNEL32!GetProcessHeap` at `0x180015c63`

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
0x180015bd4  push    rbx
0x180015bd6  push    rbp
0x180015bd7  push    rsi
0x180015bd8  push    rdi
0x180015bd9  sub     rsp, 28h
0x180015bdd  mov     rbp, rdx
0x180015be0  mov     rdi, rcx
0x180015be3  test    rdx, rdx
0x180015be6  jnz     short loc_180015C29
0x180015be8  mov     rcx, [rcx]
0x180015beb  test    rcx, rcx
0x180015bee  jz      short loc_180015C22
0x180015bf0  or      eax, 0FFFFFFFFh
0x180015bf3  lock xadd [rcx], eax
0x180015bf7  cmp     eax, 1
0x180015bfa  jnz     short loc_180015C13
0x180015bfc  mov     rbx, [rdi]
0x180015bff  call    cs:__imp_GetProcessHeap
0x180015c05  mov     r8, rbx; lpMem
0x180015c08  xor     edx, edx; dwFlags
0x180015c0a  mov     rcx, rax; hHeap
0x180015c0d  call    cs:__imp_HeapFree
0x180015c13  mov     qword ptr [rdi], 0
0x180015c1a  mov     qword ptr [rdi+8], 0
0x180015c22  mov     eax, 1
0x180015c27  jmp     short loc_180015C8E
0x180015c29  call    cs:__imp_GetProcessHeap
0x180015c2f  lea     r8, [rbp+4]; dwBytes
0x180015c33  xor     edx, edx; dwFlags
0x180015c35  mov     rcx, rax; hHeap
0x180015c38  call    cs:__imp_HeapAlloc
0x180015c3e  mov     rsi, rax
0x180015c41  test    rax, rax
0x180015c44  jz      short loc_180015C8E
0x180015c46  mov     dword ptr [rax], 0
0x180015c4c  mov     rcx, [rdi]
0x180015c4f  test    rcx, rcx
0x180015c52  jz      short loc_180015C7F
0x180015c54  or      eax, 0FFFFFFFFh
0x180015c57  lock xadd [rcx], eax
0x180015c5b  cmp     eax, 1
0x180015c5e  jnz     short loc_180015C77
0x180015c60  mov     rbx, [rdi]
0x180015c63  call    cs:__imp_GetProcessHeap
0x180015c69  mov     r8, rbx; lpMem
0x180015c6c  xor     edx, edx; dwFlags
0x180015c6e  mov     rcx, rax; hHeap
0x180015c71  call    cs:__imp_HeapFree
0x180015c77  mov     qword ptr [rdi+8], 0
0x180015c7f  mov     [rdi], rsi
0x180015c82  mov     eax, 1
0x180015c87  mov     [rdi+8], rbp
0x180015c8b  lock add [rsi], eax
0x180015c8e  add     rsp, 28h
0x180015c92  pop     rdi
0x180015c93  pop     rsi
0x180015c94  pop     rbp
0x180015c95  pop     rbx
0x180015c96  retn
```
