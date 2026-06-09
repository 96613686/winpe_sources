# PropertyCollection::TryAppendPredicateWithSelectProperties(ConfigTreeBase *,ElementNode *,STRU &,bool (*)(PropertyNode *))

- ea: `0x18000c09c`
- end: `0x18000c1db`
- name: `?TryAppendPredicateWithSelectProperties@PropertyCollection@@AEAA_NPEAVConfigTreeBase@@PEAVElementNode@@AEAVSTRU@@P6A_NPEAVPropertyNode@@@Z@Z`
- size: `319`
- prototype: `bool(PropertyCollection *__hidden this, struct ConfigTreeBase *, struct ElementNode *, struct STRU *, bool (*)(struct PropertyNode *))`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000ab84`

## callees

- `0x180004728`
- `0x18000b2e8`
- `0x18000c09c`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `msvcrt!wcschr` at `0x18000c10f`
- `msvcrt!wcschr` at `0x18000c10f`

## pseudocode

```c
__int64 __fastcall PropertyCollection::TryAppendPredicateWithSelectProperties(
        PropertyCollection *this,
        struct ConfigTreeBase *a2,
        struct ElementNode *a3,
        struct STRU *a4,
        bool (*a5)(struct PropertyNode *))
{
  unsigned __int8 v6; // di
  struct PropertyNode *i; // rax
  unsigned __int16 **v9; // rbx
  unsigned __int16 *v10; // rax
  int v11; // eax
  bool v12; // zf
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  int v15; // eax
  int pExceptionObject; // [rsp+20h] [rbp-50h] BYREF
  wchar_t *Str; // [rsp+28h] [rbp-48h] BYREF
  unsigned __int16 *v19[8]; // [rsp+30h] [rbp-40h] BYREF

  v6 = 0;
  for ( i = PropertyCollection::GetFirstAttribute(this, a2, a3, 0);
        ;
        i = (struct PropertyNode *)(*((__int64 (__fastcall **)(unsigned __int16 **, struct ConfigTreeBase *, _QWORD))*v9
                                    + 5))(
                                     v9,
                                     a2,
                                     0) )
  {
    v9 = (unsigned __int16 **)i;
    if ( !i )
      break;
    if ( !a5 || ((unsigned __int8 (__fastcall *)(struct PropertyNode *))a5)(i) )
    {
      v10 = *v9;
      Str = 0;
      v11 = (*((__int64 (__fastcall **)(unsigned __int16 **, wchar_t **))v10 + 3))(v9, &Str);
      if ( v11 < 0 )
      {
        pExceptionObject = v11;
        throw (long *)&pExceptionObject;
      }
      v12 = wcschr(Str, 0x27u) == 0;
      v13 = L"\"";
      v14 = L" and ";
      if ( v12 )
        v13 = L"'";
      v19[4] = v13;
      v19[6] = v13;
      if ( !v6 )
        v14 = (unsigned __int16 *)&qword_1800181B0;
      v19[0] = v14;
      v19[1] = L"@";
      v19[2] = v9[3];
      v19[3] = L"=";
      v19[5] = Str;
      v15 = STRU::AuxAppend(a4, (const unsigned __int16 *const *const)v19, 7u);
      if ( v15 < 0 )
      {
        pExceptionObject = v15;
        throw (long *)&pExceptionObject;
      }
      v6 = 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000c09c  push    rbp
0x18000c09e  push    rbx
0x18000c09f  push    rdi
0x18000c0a0  push    r14
0x18000c0a2  push    r15
0x18000c0a4  mov     rbp, rsp
0x18000c0a7  sub     rsp, 70h
0x18000c0ab  mov     r15, r9
0x18000c0ae  xor     dil, dil
0x18000c0b1  xor     r9d, r9d; unsigned __int16 *
0x18000c0b4  mov     r14, rdx
0x18000c0b7  call    ?GetFirstAttribute@PropertyCollection@@QEAAPEAVPropertyNode@@PEAVConfigTreeBase@@PEAVElementNode@@PEBG@Z; PropertyCollection::GetFirstAttribute(ConfigTreeBase *,ElementNode *,ushort const *)
0x18000c0bc  mov     rbx, rax
0x18000c0bf  test    rax, rax
0x18000c0c2  jz      loc_18000C1CC
0x18000c0c8  cmp     [rbp+arg_20], 0
0x18000c0cd  jz      short loc_18000C0E3
0x18000c0cf  mov     rcx, rax
0x18000c0d2  mov     rax, [rbp+arg_20]
0x18000c0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0db  test    al, al
0x18000c0dd  jz      loc_18000C18A
0x18000c0e3  mov     rax, [rbx]
0x18000c0e6  lea     rdx, [rbp+Str]
0x18000c0ea  mov     rcx, rbx
0x18000c0ed  mov     [rbp+Str], 0
0x18000c0f5  mov     rax, [rax+18h]
0x18000c0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0fe  test    eax, eax
0x18000c100  js      loc_18000C1B8
0x18000c106  mov     rcx, [rbp+Str]; Str
0x18000c10a  mov     edx, 27h ; '''; Ch
0x18000c10f  call    cs:__imp_wcschr
0x18000c115  lea     rdx, asc_180018288; "'"
0x18000c11c  mov     r8d, 7; unsigned __int64
0x18000c122  test    rax, rax
0x18000c125  lea     rcx, asc_18001828C; "\""
0x18000c12c  lea     rax, aAnd; " and "
0x18000c133  cmovz   rcx, rdx
0x18000c137  lea     rdx, qword_1800181B0
0x18000c13e  mov     [rbp+var_20], rcx
0x18000c142  test    dil, dil
0x18000c145  mov     [rbp+var_10], rcx
0x18000c149  mov     rcx, r15; this
0x18000c14c  cmovz   rax, rdx
0x18000c150  lea     rdx, [rbp+var_40]; unsigned __int16 **
0x18000c154  mov     [rbp+var_40], rax
0x18000c158  lea     rax, asc_180018284; "@"
0x18000c15f  mov     [rbp+var_38], rax
0x18000c163  mov     rax, [rbx+18h]
0x18000c167  mov     [rbp+var_30], rax
0x18000c16b  lea     rax, asc_1800185EC; "="
0x18000c172  mov     [rbp+var_28], rax
0x18000c176  mov     rax, [rbp+Str]
0x18000c17a  mov     [rbp+var_18], rax
0x18000c17e  call    ?AuxAppend@STRU@@AEAAJQEBQEBG_K@Z; STRU::AuxAppend(ushort const * const * const,unsigned __int64)
0x18000c183  test    eax, eax
0x18000c185  js      short loc_18000C1A4
0x18000c187  mov     dil, 1
0x18000c18a  mov     rax, [rbx]
0x18000c18d  xor     r8d, r8d
0x18000c190  mov     rdx, r14
0x18000c193  mov     rcx, rbx
0x18000c196  mov     rax, [rax+28h]
0x18000c19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c19f  jmp     loc_18000C0BC
0x18000c1a4  lea     rdx, _TI1J; pThrowInfo
0x18000c1ab  mov     [rbp+pExceptionObject], eax
0x18000c1ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c1b2  call    _CxxThrowException_0
0x18000c1b8  lea     rdx, _TI1J; pThrowInfo
0x18000c1bf  mov     [rbp+pExceptionObject], eax
0x18000c1c2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c1c6  call    _CxxThrowException_0
0x18000c1cc  mov     al, dil
0x18000c1cf  add     rsp, 70h
0x18000c1d3  pop     r15
0x18000c1d5  pop     r14
0x18000c1d7  pop     rdi
0x18000c1d8  pop     rbx
0x18000c1d9  pop     rbp
0x18000c1da  retn
```
