# CDateRuleWriter::WriteRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)

- ea: `0x180012be0`
- end: `0x180012cf6`
- name: `?WriteRulePath@CDateRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(CDateRuleWriter *__hidden this, const struct RULE_PATH_INFO *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180012be0`
- `0x1800132dc`
- `0x1800139f0`
- `0x180013bf8`
- `0x180013df0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c4e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c4e`

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
0x180012be0  push    rbp
0x180012be2  push    rbx
0x180012be3  push    rsi
0x180012be4  push    rdi
0x180012be5  mov     rbp, rsp
0x180012be8  sub     rsp, 68h
0x180012bec  mov     rax, r8
0x180012bef  mov     rdi, rdx
0x180012bf2  mov     rsi, rcx
0x180012bf5  xorps   xmm0, xmm0
0x180012bf8  xor     ecx, ecx
0x180012bfa  movups  xmmword ptr [rbp+var_20], xmm0
0x180012bfe  mov     qword ptr [rbp+var_20+10h], rcx
0x180012c02  movups  xmmword ptr [rbp+pvar], xmm0
0x180012c06  mov     qword ptr [rbp+pvar+10h], rcx
0x180012c0a  cmp     dword ptr [rdx+0Ch], 9
0x180012c0e  jz      loc_180012CE3
0x180012c14  cmp     dword ptr [rdx+0Ch], 4
0x180012c18  jz      short loc_180012C66
0x180012c1a  mov     rcx, rsi; this
0x180012c1d  call    ?WriteRulePath@CRuleWriter@@MEAAJPEBURULE_PATH_INFO@@PEBUtagPROPVARIANT@@@Z; CRuleWriter::WriteRulePath(RULE_PATH_INFO const *,tagPROPVARIANT const *)
0x180012c22  test    eax, eax
0x180012c24  mov     ebx, eax
0x180012c26  jns     short loc_180012C39
0x180012c28  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012c2f  jz      short loc_180012C39
0x180012c31  mov     ecx, eax; int
0x180012c33  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012c38  nop
0x180012c39  lea     rcx, [rbp+pvar]; pvar
0x180012c3d  call    cs:__imp_PropVariantClear
0x180012c44  nop     dword ptr [rax+rax+00h]
0x180012c49  nop
0x180012c4a  lea     rcx, [rbp+var_20]; pvar
0x180012c4e  call    cs:__imp_PropVariantClear
0x180012c55  nop     dword ptr [rax+rax+00h]
0x180012c5a  mov     eax, ebx
0x180012c5c  add     rsp, 68h
0x180012c60  pop     rdi
0x180012c61  pop     rsi
0x180012c62  pop     rbx
0x180012c63  pop     rbp
0x180012c64  retn
0x180012c66  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180012c6a  lea     rdx, [rbp+var_20]; struct tagPROPVARIANT *
0x180012c6e  mov     rcx, rax; struct tagPROPVARIANT *
0x180012c71  call    ?ConvertDateToExifStringsOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z; ConvertDateToExifStringsOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180012c76  test    eax, eax
0x180012c78  mov     ebx, eax
0x180012c7a  js      short loc_180012C28
0x180012c7c  mov     rax, [rsi]
0x180012c7f  lea     rcx, [rbp+var_20]
0x180012c83  mov     [rsp+68h+var_48], rcx
0x180012c88  xor     r9d, r9d
0x180012c8b  mov     r8d, [rdi+8]
0x180012c8f  mov     rdx, [rdi+18h]
0x180012c93  mov     rcx, rsi
0x180012c96  mov     rax, [rax+40h]
0x180012c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c9f  mov     ebx, eax
0x180012ca1  test    eax, eax
0x180012ca3  jns     short loc_180012CB2
0x180012ca5  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012cac  jnz     short loc_180012C31
0x180012cae  test    eax, eax
0x180012cb0  js      short loc_180012C39
0x180012cb2  mov     rdx, [rdi+20h]
0x180012cb6  test    rdx, rdx
0x180012cb9  jz      loc_180012C39
0x180012cbf  mov     rax, [rsi]
0x180012cc2  lea     rcx, [rbp+pvar]
0x180012cc6  mov     [rsp+68h+var_48], rcx
0x180012ccb  xor     r9d, r9d
0x180012cce  mov     r8d, [rdi+8]
0x180012cd2  mov     rcx, rsi
0x180012cd5  mov     rax, [rax+40h]
0x180012cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cde  jmp     loc_180012C22
0x180012ce3  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x180012ce7  lea     rdx, [rbp+var_20]; struct tagPROPVARIANT *
0x180012ceb  mov     rcx, rax; struct tagPROPVARIANT *
0x180012cee  call    ?ConvertIPTCDateTimeOnWrite@@YAJPEBUtagPROPVARIANT@@PEAU1@1@Z; ConvertIPTCDateTimeOnWrite(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180012cf3  jmp     short loc_180012C76
```
