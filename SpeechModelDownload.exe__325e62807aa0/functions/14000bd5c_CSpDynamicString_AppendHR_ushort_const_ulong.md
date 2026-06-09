# CSpDynamicString::AppendHR(ushort const *,ulong)

- ea: `0x14000bd5c`
- end: `0x14000be93`
- name: `?AppendHR@CSpDynamicString@@QEAAJPEBGK@Z`
- size: `311`
- prototype: `__int64 __fastcall(const void **this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000f920`

## callees

- `0x14000bd5c`
- `0x1400131e4`
- `0x14001bb9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bdef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000bdef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000bdcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000be5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000bdcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000be5c`

## pseudocode

```c
__int64 __fastcall CSpDynamicString::AppendHR(const void **this, const unsigned __int16 *a2, unsigned int a3)
{
  _WORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // r15
  unsigned __int64 v9; // rdx
  __int64 v10; // rbp
  SIZE_T v11; // rcx
  char *v12; // rax
  char *v13; // rbx
  int v14; // esi
  size_t v15; // rdi
  _WORD *v16; // rax
  const void *v18; // [rsp+78h] [rbp+10h] BYREF

  if ( a2 && a3 )
  {
    v5 = *this;
    LODWORD(v6) = 0;
    if ( v5 )
    {
      v6 = -1;
      do
        ++v6;
      while ( v5[v6] );
    }
    v7 = (unsigned int)v6;
    v8 = a3;
    v9 = (unsigned int)v6 + (unsigned __int64)a3;
    if ( v9 <= (unsigned int)v6 )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v18 = 0;
      if ( (unsigned int)v9 >= 0x4FFFFFFF
        || (v10 = (unsigned int)v9, v11 = 2LL * (unsigned int)(v9 + 1), v11 <= (unsigned int)v9) )
      {
        SetLastError(0x216u);
        v14 = -2147024362;
      }
      else
      {
        v12 = (char *)CoTaskMemAlloc(v11);
        v18 = v12;
        v13 = v12;
        if ( v12 )
        {
          v14 = 0;
          *(_WORD *)&v12[2 * v10] = 0;
        }
        else
        {
          SetLastError(0xEu);
          v14 = -2147024882;
        }
        if ( v14 >= 0 )
        {
          v15 = 2 * v7;
          memcpy_0(v13, *this, v15);
          memcpy_0(&v13[v15], a2, 2 * v8);
          v18 = *this;
          *this = v13;
        }
      }
      CSpDynamicString::_free((LPVOID *)&v18);
    }
  }
  else
  {
    v14 = 0;
    if ( !*this )
    {
      v16 = CoTaskMemAlloc(2u);
      *this = v16;
      if ( v16 )
      {
        *v16 = 0;
      }
      else
      {
        SetLastError(0xEu);
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14000bd5c  push    rbx
0x14000bd5e  push    rbp
0x14000bd5f  push    rsi
0x14000bd60  push    rdi
0x14000bd61  push    r12
0x14000bd63  push    r13
0x14000bd65  push    r14
0x14000bd67  push    r15
0x14000bd69  sub     rsp, 28h
0x14000bd6d  xor     r13d, r13d
0x14000bd70  mov     r12, rdx
0x14000bd73  mov     r14, rcx
0x14000bd76  test    rdx, rdx
0x14000bd79  jz      loc_14000BE4F
0x14000bd7f  test    r8d, r8d
0x14000bd82  jz      loc_14000BE4F
0x14000bd88  mov     rcx, [rcx]
0x14000bd8b  mov     eax, r13d
0x14000bd8e  test    rcx, rcx
0x14000bd91  jz      short loc_14000BDA1
0x14000bd93  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bd97  inc     rax
0x14000bd9a  cmp     [rcx+rax*2], r13w
0x14000bd9f  jnz     short loc_14000BD97
0x14000bda1  mov     edi, eax
0x14000bda3  mov     r15d, r8d
0x14000bda6  lea     rdx, [rdi+r15]
0x14000bdaa  cmp     rdx, rdi
0x14000bdad  jbe     loc_14000BE48
0x14000bdb3  mov     [rsp+68h+arg_8], r13
0x14000bdb8  cmp     edx, 4FFFFFFFh
0x14000bdbe  jnb     short loc_14000BE2C
0x14000bdc0  lea     ecx, [rdx+1]
0x14000bdc3  mov     ebp, edx
0x14000bdc5  add     rcx, rcx; cb
0x14000bdc8  cmp     rcx, rbp
0x14000bdcb  jbe     short loc_14000BE2C
0x14000bdcd  call    cs:__imp_CoTaskMemAlloc
0x14000bdd3  mov     [rsp+68h+arg_8], rax
0x14000bdd8  mov     rbx, rax
0x14000bddb  test    rax, rax
0x14000bdde  jz      short loc_14000BDEA
0x14000bde0  mov     esi, r13d
0x14000bde3  mov     [rax+rbp*2], r13w
0x14000bde8  jmp     short loc_14000BDFA
0x14000bdea  mov     ecx, 0Eh; dwErrCode
0x14000bdef  call    cs:__imp_SetLastError
0x14000bdf5  mov     esi, 8007000Eh
0x14000bdfa  test    esi, esi
0x14000bdfc  js      short loc_14000BE3C
0x14000bdfe  mov     rdx, [r14]; Src
0x14000be01  add     rdi, rdi
0x14000be04  mov     r8, rdi; Size
0x14000be07  mov     rcx, rbx; void *
0x14000be0a  call    memcpy_0
0x14000be0f  lea     r8, [r15+r15]; Size
0x14000be13  mov     rdx, r12; Src
0x14000be16  lea     rcx, [rdi+rbx]; void *
0x14000be1a  call    memcpy_0
0x14000be1f  mov     rax, [r14]
0x14000be22  mov     [rsp+68h+arg_8], rax
0x14000be27  mov     [r14], rbx
0x14000be2a  jmp     short loc_14000BE3C
0x14000be2c  mov     ecx, 216h; dwErrCode
0x14000be31  call    cs:__imp_SetLastError
0x14000be37  mov     esi, 80070216h
0x14000be3c  lea     rcx, [rsp+68h+arg_8]; this
0x14000be41  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x14000be46  jmp     short loc_14000BE80
0x14000be48  mov     esi, 80070216h
0x14000be4d  jmp     short loc_14000BE80
0x14000be4f  mov     esi, r13d
0x14000be52  cmp     [rcx], r13
0x14000be55  jnz     short loc_14000BE80
0x14000be57  mov     ecx, 2; cb
0x14000be5c  call    cs:__imp_CoTaskMemAlloc
0x14000be62  mov     [r14], rax
0x14000be65  test    rax, rax
0x14000be68  jz      short loc_14000BE70
0x14000be6a  mov     [rax], r13w
0x14000be6e  jmp     short loc_14000BE80
0x14000be70  mov     ecx, 0Eh; dwErrCode
0x14000be75  call    cs:__imp_SetLastError
0x14000be7b  mov     esi, 8007000Eh
0x14000be80  mov     eax, esi
0x14000be82  add     rsp, 28h
0x14000be86  pop     r15
0x14000be88  pop     r14
0x14000be8a  pop     r13
0x14000be8c  pop     r12
0x14000be8e  pop     rdi
0x14000be8f  pop     rsi
0x14000be90  pop     rbp
0x14000be91  pop     rbx
0x14000be92  retn
```
