# CWfHelperClass::GetAttributeInfo(ulong *,tagHelperAttributeInfo * *)

- ea: `0x180003d20`
- end: `0x180003ea8`
- name: `?GetAttributeInfo@CWfHelperClass@@UEAAJPEAKPEAPEAUtagHelperAttributeInfo@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(CWfHelperClass *__hidden this, unsigned int *, struct tagHelperAttributeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003d20`
- `0x180005ce0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003dc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003e8f`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::GetAttributeInfo(
        CWfHelperClass *this,
        unsigned int *a2,
        struct tagHelperAttributeInfo **a3)
{
  unsigned int v5; // ebx
  const struct tagHelperAttributeInfo near *const *v6; // rsi
  const struct tagHelperAttributeInfo near *const *v7; // rax
  __int64 result; // rax
  SIZE_T v9; // rdi
  struct tagHelperAttributeInfo *v10; // rax
  struct tagHelperAttributeInfo *v11; // r14
  struct tagHelperAttributeInfo *i; // rbp
  unsigned int v13; // edi
  int v14; // r15d
  unsigned int j; // ebx
  LPWSTR pwszName; // rcx

  if ( !a2 || !a3 )
    return 2147942487LL;
  v5 = 0;
  v6 = &CWfHelperClass::m_attrInfos;
  v7 = &CWfHelperClass::m_attrInfos;
  if ( CWfHelperClass::m_attrInfos )
  {
    do
    {
      ++v5;
      v7 += 2;
    }
    while ( *v7 );
  }
  *a2 = 0;
  *a3 = 0;
  if ( !v5 )
    return 0;
  if ( v5 > 0x104 )
    return 2147942487LL;
  v9 = 16LL * v5;
  v10 = (struct tagHelperAttributeInfo *)CoTaskMemAlloc(v9);
  v11 = v10;
  if ( !v10 )
    return 2147942414LL;
  for ( i = v10; v9; --v9 )
  {
    LOBYTE(v10->pwszName) = 0;
    v10 = (struct tagHelperAttributeInfo *)((char *)v10 + 1);
  }
  v13 = 0;
  while ( 1 )
  {
    v14 = StringCchCopyWithAlloc(&i->pwszName, 0xFFFFu, *(const unsigned __int16 **)v6);
    if ( v14 < 0 )
      break;
    ++v13;
    i->type = *((_DWORD *)v6 + 2);
    v6 += 2;
    ++i;
    if ( v13 >= v5 )
    {
      *a2 = v5;
      result = 0;
      *a3 = v11;
      return result;
    }
  }
  if ( v13 )
  {
    for ( j = 0; j < v13; ++j )
    {
      pwszName = v11[j].pwszName;
      if ( pwszName )
        CoTaskMemFree(pwszName);
    }
  }
  CoTaskMemFree(v11);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180003d20  push    r12
0x180003d22  push    r13
0x180003d24  sub     rsp, 38h
0x180003d28  mov     r12, r8
0x180003d2b  mov     r13, rdx
0x180003d2e  test    rdx, rdx
0x180003d31  jz      loc_180003E9A
0x180003d37  test    r8, r8
0x180003d3a  jz      loc_180003E9A
0x180003d40  mov     [rsp+48h+arg_0], rbx
0x180003d45  xor     ebx, ebx
0x180003d47  cmp     cs:?m_attrInfos@CWfHelperClass@@0QBUtagHelperAttributeInfo@@B, rbx; tagHelperAttributeInfo const near * const CWfHelperClass::m_attrInfos
0x180003d4e  mov     [rsp+48h+arg_10], rsi
0x180003d53  lea     rsi, ?m_attrInfos@CWfHelperClass@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CWfHelperClass::m_attrInfos
0x180003d5a  mov     rax, rsi
0x180003d5d  jz      short loc_180003D6C
0x180003d5f  nop
0x180003d60  inc     ebx
0x180003d62  lea     rax, [rax+10h]
0x180003d66  cmp     qword ptr [rax], 0
0x180003d6a  jnz     short loc_180003D60
0x180003d6c  mov     dword ptr [rdx], 0
0x180003d72  mov     qword ptr [r8], 0
0x180003d79  test    ebx, ebx
0x180003d7b  jnz     short loc_180003D92
0x180003d7d  mov     rbx, [rsp+48h+arg_0]
0x180003d82  xor     eax, eax
0x180003d84  mov     rsi, [rsp+48h+arg_10]
0x180003d89  add     rsp, 38h
0x180003d8d  pop     r13
0x180003d8f  pop     r12
0x180003d91  retn
0x180003d92  cmp     ebx, 104h
0x180003d98  jbe     short loc_180003DB2
0x180003d9a  mov     rbx, [rsp+48h+arg_0]
0x180003d9f  mov     eax, 80070057h
0x180003da4  mov     rsi, [rsp+48h+arg_10]
0x180003da9  add     rsp, 38h
0x180003dad  pop     r13
0x180003daf  pop     r12
0x180003db1  retn
0x180003db2  mov     [rsp+48h+var_18], rdi
0x180003db7  mov     edi, ebx
0x180003db9  shl     rdi, 4
0x180003dbd  mov     rcx, rdi; cb
0x180003dc0  mov     [rsp+48h+var_20], r14
0x180003dc5  call    cs:__imp_CoTaskMemAlloc
0x180003dcb  mov     r14, rax
0x180003dce  test    rax, rax
0x180003dd1  jnz     short loc_180003DDA
0x180003dd3  mov     eax, 8007000Eh
0x180003dd8  jmp     short loc_180003E4F
0x180003dda  mov     [rsp+48h+arg_8], rbp
0x180003ddf  mov     rbp, r14
0x180003de2  test    rdi, rdi
0x180003de5  jz      short loc_180003DFD
0x180003de7  nop     word ptr [rax+rax+00000000h]
0x180003df0  mov     byte ptr [rax], 0
0x180003df3  lea     rax, [rax+1]
0x180003df7  sub     rdi, 1
0x180003dfb  jnz     short loc_180003DF0
0x180003dfd  xor     edi, edi
0x180003dff  mov     [rsp+48h+var_28], r15
0x180003e04  test    ebx, ebx
0x180003e06  jz      short loc_180003E3B
0x180003e08  nop     dword ptr [rax+rax+00000000h]
0x180003e10  mov     r8, [rsi]; unsigned __int16 *
0x180003e13  mov     edx, 0FFFFh; unsigned __int64
0x180003e18  mov     rcx, rbp; unsigned __int16 **
0x180003e1b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180003e20  mov     r15d, eax
0x180003e23  test    eax, eax
0x180003e25  js      short loc_180003E6C
0x180003e27  mov     eax, [rsi+8]
0x180003e2a  inc     edi
0x180003e2c  mov     [rbp+8], eax
0x180003e2f  add     rsi, 10h
0x180003e33  add     rbp, 10h
0x180003e37  cmp     edi, ebx
0x180003e39  jb      short loc_180003E10
0x180003e3b  mov     [r13+0], ebx
0x180003e3f  xor     eax, eax
0x180003e41  mov     [r12], r14
0x180003e45  mov     r15, [rsp+48h+var_28]
0x180003e4a  mov     rbp, [rsp+48h+arg_8]
0x180003e4f  mov     rdi, [rsp+48h+var_18]
0x180003e54  mov     r14, [rsp+48h+var_20]
0x180003e59  mov     rbx, [rsp+48h+arg_0]
0x180003e5e  mov     rsi, [rsp+48h+arg_10]
0x180003e63  add     rsp, 38h
0x180003e67  pop     r13
0x180003e69  pop     r12
0x180003e6b  retn
0x180003e6c  test    edi, edi
0x180003e6e  jz      short loc_180003E8C
0x180003e70  xor     ebx, ebx
0x180003e72  mov     eax, ebx
0x180003e74  add     rax, rax
0x180003e77  mov     rcx, [r14+rax*8]; pv
0x180003e7b  test    rcx, rcx
0x180003e7e  jz      short loc_180003E86
0x180003e80  call    cs:__imp_CoTaskMemFree
0x180003e86  inc     ebx
0x180003e88  cmp     ebx, edi
0x180003e8a  jb      short loc_180003E72
0x180003e8c  mov     rcx, r14; pv
0x180003e8f  call    cs:__imp_CoTaskMemFree
0x180003e95  mov     eax, r15d
0x180003e98  jmp     short loc_180003E45
0x180003e9a  mov     eax, 80070057h
0x180003e9f  add     rsp, 38h
0x180003ea3  pop     r13
0x180003ea5  pop     r12
0x180003ea7  retn
```
