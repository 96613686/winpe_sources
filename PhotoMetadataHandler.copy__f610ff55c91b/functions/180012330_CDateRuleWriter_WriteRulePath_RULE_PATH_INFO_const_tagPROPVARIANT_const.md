# CDateRuleWriter::WriteRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)

- ea: `0x180012330`
- end: `0x180012435`
- name: `?WriteRulePath@CDateRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(CDateRuleWriter *__hidden this, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180012330`
- `0x1800129d8`
- `0x1800130bc`
- `0x18001329c`
- `0x180013470`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001238d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012398`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001238d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012398`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDateRuleWriter::WriteRulePath(
        CDateRuleWriter *this,
        const struct RULE_PATH_INFO *a2,
        const struct tagPROPVARIANT *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rdx
  PROPVARIANT pvar; // [rsp+30h] [rbp-38h] BYREF
  PROPVARIANT v10; // [rsp+48h] [rbp-20h] BYREF

  memset(&v10, 0, sizeof(v10));
  memset(&pvar, 0, sizeof(pvar));
  if ( *((_DWORD *)a2 + 3) == 9 )
  {
    v5 = ConvertIPTCDateTimeOnWrite(a3, &v10, &pvar);
  }
  else
  {
    if ( *((_DWORD *)a2 + 3) != 4 )
    {
      v5 = CRuleWriter::WriteRulePath(this, a2, a3);
      goto LABEL_4;
    }
    v5 = ConvertDateToExifStringsOnWrite(a3, &v10, &pvar);
  }
  v6 = v5;
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(CDateRuleWriter *, _QWORD, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
           this,
           *((_QWORD *)a2 + 3),
           *((unsigned int *)a2 + 2),
           0,
           &v10);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_7;
      goto LABEL_6;
    }
    v8 = *((_QWORD *)a2 + 4);
    if ( !v8 )
      goto LABEL_7;
    v5 = (*(__int64 (__fastcall **)(CDateRuleWriter *, __int64, _QWORD, _QWORD, PROPVARIANT *))(*(_QWORD *)this + 64LL))(
           this,
           v8,
           *((unsigned int *)a2 + 2),
           0,
           &pvar);
LABEL_4:
    v6 = v5;
    if ( v5 >= 0 )
      goto LABEL_7;
  }
  if ( g_doStackCaptures )
LABEL_6:
    DoStackCapture(v5);
LABEL_7:
  PropVariantClear(&pvar);
  PropVariantClear(&v10);
  return v6;
}

```

## disassembly

```asm
0x180012330  push    rbp
0x180012332  push    rbx
0x180012333  push    rsi
0x180012334  push    rdi
0x180012335  mov     rbp, rsp
0x180012338  sub     rsp, 68h
0x18001233c  mov     rax, r8
0x18001233f  mov     rdi, rdx
0x180012342  mov     rsi, rcx
0x180012345  xorps   xmm0, xmm0
0x180012348  xor     ecx, ecx
0x18001234a  movups  xmmword ptr [rbp+var_20], xmm0
0x18001234e  mov     qword ptr [rbp+var_20+10h], rcx
0x180012352  movups  xmmword ptr [rbp+pvar], xmm0
0x180012356  mov     qword ptr [rbp+pvar+10h], rcx
0x18001235a  cmp     dword ptr [rdx+0Ch], 9
0x18001235e  jz      loc_180012422
0x180012364  cmp     dword ptr [rdx+0Ch], 4
0x180012368  jz      short loc_1800123A9
0x18001236a  mov     rcx, rsi; this
0x18001236d  call    ?WriteRulePath@CRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z; CRuleWriter::WriteRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)
0x180012372  test    eax, eax
0x180012374  mov     ebx, eax
0x180012376  jns     short loc_180012389
0x180012378  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001237f  jz      short loc_180012389
0x180012381  mov     ecx, eax; int
0x180012383  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012388  nop
0x180012389  lea     rcx, [rbp+pvar]; pvar
0x18001238d  call    cs:__imp_PropVariantClear
0x180012393  nop
0x180012394  lea     rcx, [rbp+var_20]; pvar
0x180012398  call    cs:__imp_PropVariantClear
0x18001239e  mov     eax, ebx
0x1800123a0  add     rsp, 68h
0x1800123a4  pop     rdi
0x1800123a5  pop     rsi
0x1800123a6  pop     rbx
0x1800123a7  pop     rbp
0x1800123a8  retn
0x1800123a9  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x1800123ad  lea     rdx, [rbp+var_20]; struct tagPROPVARIANT *
0x1800123b1  mov     rcx, rax; struct tagPROPVARIANT *
0x1800123b4  call    ?ConvertDateToExifStringsOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z; ConvertDateToExifStringsOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)
0x1800123b9  test    eax, eax
0x1800123bb  mov     ebx, eax
0x1800123bd  js      short loc_180012378
0x1800123bf  mov     rax, [rsi]
0x1800123c2  lea     rcx, [rbp+var_20]
0x1800123c6  mov     [rsp+68h+var_48], rcx
0x1800123cb  xor     r9d, r9d
0x1800123ce  mov     r8d, [rdi+8]
0x1800123d2  mov     rdx, [rdi+18h]
0x1800123d6  mov     rcx, rsi
0x1800123d9  mov     rax, [rax+40h]
0x1800123dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123e2  mov     ebx, eax
0x1800123e4  test    eax, eax
0x1800123e6  jns     short loc_1800123F5
0x1800123e8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800123ef  jnz     short loc_180012381
0x1800123f1  test    eax, eax
0x1800123f3  js      short loc_180012389
0x1800123f5  mov     rdx, [rdi+20h]
0x1800123f9  test    rdx, rdx
0x1800123fc  jz      short loc_180012389
0x1800123fe  mov     rax, [rsi]
0x180012401  lea     rcx, [rbp+pvar]
0x180012405  mov     [rsp+68h+var_48], rcx
0x18001240a  xor     r9d, r9d
0x18001240d  mov     r8d, [rdi+8]
0x180012411  mov     rcx, rsi
0x180012414  mov     rax, [rax+40h]
0x180012418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001241d  jmp     loc_180012372
0x180012422  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180012426  lea     rdx, [rbp+var_20]; struct tagPROPVARIANT *
0x18001242a  mov     rcx, rax; struct tagPROPVARIANT *
0x18001242d  call    ?ConvertIPTCDateTimeOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z; ConvertIPTCDateTimeOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180012432  jmp     short loc_1800123B9
```
