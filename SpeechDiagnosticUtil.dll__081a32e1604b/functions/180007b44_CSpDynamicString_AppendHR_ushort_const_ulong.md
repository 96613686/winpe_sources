# CSpDynamicString::AppendHR(ushort const *,ulong)

- ea: `0x180007b44`
- end: `0x180007c31`
- name: `?AppendHR@CSpDynamicString@@QEAAJPEBGK@Z`
- size: `237`
- prototype: `int(CSpDynamicString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800087b0`

## callees

- `0x180007b44`
- `0x18000d630`
- `0x18000d6b4`
- `0x180010564`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007c10`
- `KERNEL32!SetLastError` at `0x180007c10`
- `ole32!CoTaskMemAlloc` at `0x180007bf2`
- `ole32!CoTaskMemAlloc` at `0x180007bf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSpDynamicString::AppendHR(const void **this, const unsigned __int16 *a2, unsigned int a3)
{
  __int64 v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // r15
  __int64 v8; // rdi
  unsigned __int64 v9; // rdx
  int v10; // esi
  size_t v11; // rdi
  char *v12; // rbx
  void *v13; // rcx
  _WORD *v14; // rax
  void *v16; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 && a3 )
  {
    LODWORD(v5) = 0;
    v6 = *this;
    if ( v6 )
    {
      v5 = -1;
      do
        ++v5;
      while ( v6[v5] );
    }
    v7 = a3;
    v8 = (unsigned int)v5;
    v9 = (unsigned int)v5 + (unsigned __int64)a3;
    if ( v9 <= (unsigned int)v5 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v16 = 0;
      v10 = CSpDynamicString::_allocate((CSpDynamicString *)&v16, v9);
      if ( v10 >= 0 )
      {
        v11 = 2 * v8;
        v12 = (char *)v16;
        memcpy_0(v16, *this, v11);
        memcpy_0(&v12[v11], a2, 2 * v7);
        v13 = (void *)*this;
        *this = v12;
        v16 = v13;
      }
      CSpDynamicString::_free(&v16);
    }
  }
  else
  {
    v10 = 0;
    if ( !*this )
    {
      v14 = CoTaskMemAlloc(2u);
      *this = v14;
      if ( v14 )
      {
        *v14 = 0;
      }
      else
      {
        SetLastError(0xEu);
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180007b44  push    rbx
0x180007b46  push    rbp
0x180007b47  push    rsi
0x180007b48  push    rdi
0x180007b49  push    r14
0x180007b4b  push    r15
0x180007b4d  sub     rsp, 28h
0x180007b51  mov     rbp, rdx
0x180007b54  mov     r14, rcx
0x180007b57  xor     ebx, ebx
0x180007b59  test    rdx, rdx
0x180007b5c  jz      loc_180007BE6
0x180007b62  test    r8d, r8d
0x180007b65  jz      short loc_180007BE6
0x180007b67  mov     eax, ebx
0x180007b69  mov     rcx, [rcx]
0x180007b6c  test    rcx, rcx
0x180007b6f  jz      short loc_180007B7E
0x180007b71  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007b75  inc     rax
0x180007b78  cmp     [rcx+rax*2], bx
0x180007b7c  jnz     short loc_180007B75
0x180007b7e  mov     r15d, r8d
0x180007b81  mov     edi, eax
0x180007b83  lea     rdx, [rdi+r15]; unsigned int
0x180007b87  cmp     rdx, rdi
0x180007b8a  jbe     short loc_180007BDF
0x180007b8c  mov     [rsp+58h+arg_8], rbx
0x180007b91  lea     rcx, [rsp+58h+arg_8]; this
0x180007b96  call    ?_allocate@CSpDynamicString@@AEAAJK@Z; CSpDynamicString::_allocate(ulong)
0x180007b9b  mov     esi, eax
0x180007b9d  test    eax, eax
0x180007b9f  js      short loc_180007BD2
0x180007ba1  add     rdi, rdi
0x180007ba4  mov     r8, rdi; Size
0x180007ba7  mov     rdx, [r14]; Src
0x180007baa  mov     rbx, [rsp+58h+arg_8]
0x180007baf  mov     rcx, rbx; void *
0x180007bb2  call    memcpy_0
0x180007bb7  lea     r8, [r15+r15]; Size
0x180007bbb  lea     rcx, [rdi+rbx]; void *
0x180007bbf  mov     rdx, rbp; Src
0x180007bc2  call    memcpy_0
0x180007bc7  mov     rcx, [r14]
0x180007bca  mov     [r14], rbx
0x180007bcd  mov     [rsp+58h+arg_8], rcx
0x180007bd2  lea     rcx, [rsp+58h+arg_8]; this
0x180007bd7  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x180007bdc  nop
0x180007bdd  jmp     short loc_180007C21
0x180007bdf  mov     esi, 80070216h
0x180007be4  jmp     short loc_180007C21
0x180007be6  mov     esi, ebx
0x180007be8  cmp     [rcx], rbx
0x180007beb  jnz     short loc_180007C21
0x180007bed  mov     ecx, 2; cb
0x180007bf2  call    cs:__imp_CoTaskMemAlloc
0x180007bf9  nop     dword ptr [rax+rax+00h]
0x180007bfe  mov     [r14], rax
0x180007c01  test    rax, rax
0x180007c04  jz      short loc_180007C0B
0x180007c06  mov     [rax], bx
0x180007c09  jmp     short loc_180007C21
0x180007c0b  mov     ecx, 0Eh; dwErrCode
0x180007c10  call    cs:__imp_SetLastError
0x180007c17  nop     dword ptr [rax+rax+00h]
0x180007c1c  mov     esi, 8007000Eh
0x180007c21  mov     eax, esi
0x180007c23  add     rsp, 28h
0x180007c27  pop     r15
0x180007c29  pop     r14
0x180007c2b  pop     rdi
0x180007c2c  pop     rsi
0x180007c2d  pop     rbp
0x180007c2e  pop     rbx
0x180007c2f  retn
```
