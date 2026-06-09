# StructuredQuery1::LeafCondition::GetComparisonInfo(wchar_t * *,tagCONDITION_OPERATION *,tagPROPVARIANT *)

- ea: `0x1800114c0`
- end: `0x1800115cb`
- name: `?GetComparisonInfo@LeafCondition@StructuredQuery1@@UEAAJPEAPEA_WPEAW4tagCONDITION_OPERATION@@PEAUtagPROPVARIANT@@@Z`
- size: `267`
- prototype: `int(StructuredQuery1::LeafCondition *__hidden this, wchar_t **, enum tagCONDITION_OPERATION *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180010904`
- `0x1800114c0`
- `0x180015a40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180011554`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180011554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011570`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011570`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::LeafCondition::GetComparisonInfo(
        StructuredQuery1::LeafCondition *this,
        wchar_t **a2,
        enum tagCONDITION_OPERATION *a3,
        PROPVARIANT *a4)
{
  enum tagCONDITION_OPERATION v4; // r12d
  void *v5; // rdi
  HRESULT v6; // ebx
  PROPERTYKEY *v12; // rcx
  HRESULT ConditionPropertyNameFromKey; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  struct _tagpropertykey v16; // [rsp+50h] [rbp+8h] BYREF

  v4 = *((_DWORD *)this + 17);
  v5 = 0;
  v6 = 0;
  *(_QWORD *)&v16.fmtid.Data1 = 0;
  if ( a2 )
  {
    v12 = (PROPERTYKEY *)((char *)this + 48);
    if ( v12->pid == 6 )
    {
      v14 = *(_QWORD *)&v12->fmtid.Data1 - *(_QWORD *)&PKEY_FullText.fmtid.Data1;
      if ( *(_QWORD *)&v12->fmtid.Data1 == *(_QWORD *)&PKEY_FullText.fmtid.Data1 )
        v14 = *(_QWORD *)v12->fmtid.Data4 - *(_QWORD *)PKEY_FullText.fmtid.Data4;
      if ( !v14 )
        goto LABEL_20;
    }
    if ( v12->pid != 5 )
      goto LABEL_11;
    v15 = *(_QWORD *)&v12->fmtid.Data1 - PKEY_ForceFullText;
    if ( *(_QWORD *)&v12->fmtid.Data1 == PKEY_ForceFullText )
      v15 = *(_QWORD *)v12->fmtid.Data4 + 0x5C081FED8E732952LL;
    if ( v15 )
LABEL_11:
      ConditionPropertyNameFromKey = StructuredQuery1::GetConditionPropertyNameFromKey(v12, &v16, (wchar_t **)a3);
    else
LABEL_20:
      ConditionPropertyNameFromKey = _AllocString<CTCoAllocPolicy>(
                                       (__int64)v12,
                                       (__int64)a2,
                                       (const size_t *)L"*",
                                       &v16);
    v5 = *(void **)&v16.fmtid.Data1;
    v6 = ConditionPropertyNameFromKey;
  }
  if ( !a4 )
  {
LABEL_3:
    if ( v6 >= 0 )
      goto LABEL_4;
    goto LABEL_16;
  }
  if ( v6 >= 0 )
  {
    v6 = PropVariantCopy(a4, (const PROPVARIANT *)this + 9);
    goto LABEL_3;
  }
  *(_OWORD *)a4 = 0;
  a4[2] = 0;
LABEL_16:
  v4 = COP_IMPLICIT;
  CoTaskMemFree(v5);
  v5 = 0;
LABEL_4:
  if ( a3 )
    *a3 = v4;
  if ( a2 )
    *a2 = (wchar_t *)v5;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800114c0  mov     qword ptr [rsp+arg_0.fmtid.Data4], rbx
0x1800114c5  mov     qword ptr [rsp+arg_0.pid], rbp
0x1800114ca  push    rsi
0x1800114cb  push    rdi
0x1800114cc  push    r12
0x1800114ce  push    r14
0x1800114d0  push    r15
0x1800114d2  sub     rsp, 20h
0x1800114d6  mov     r12d, [rcx+44h]
0x1800114da  xor     edi, edi
0x1800114dc  xor     ebx, ebx
0x1800114de  mov     qword ptr [rsp+48h+arg_0.fmtid.Data1], rdi
0x1800114e3  mov     rsi, r9
0x1800114e6  mov     r15, r8
0x1800114e9  mov     r14, rdx
0x1800114ec  mov     rbp, rcx
0x1800114ef  test    rdx, rdx
0x1800114f2  jnz     short loc_180011526
0x1800114f4  test    rsi, rsi
0x1800114f7  jnz     short loc_180011549
0x1800114f9  test    ebx, ebx
0x1800114fb  js      short loc_18001156A
0x1800114fd  test    r15, r15
0x180011500  jz      short loc_180011505
0x180011502  mov     [r15], r12d
0x180011505  test    r14, r14
0x180011508  jz      short loc_18001150D
0x18001150a  mov     [r14], rdi
0x18001150d  mov     rbp, qword ptr [rsp+48h+arg_0.pid]
0x180011512  mov     eax, ebx
0x180011514  mov     rbx, qword ptr [rsp+48h+arg_0.fmtid.Data4]
0x180011519  add     rsp, 20h
0x18001151d  pop     r15
0x18001151f  pop     r14
0x180011521  pop     r12
0x180011523  pop     rdi
0x180011524  pop     rsi
0x180011525  retn
0x180011526  add     rcx, 30h ; '0'; propkey
0x18001152a  cmp     dword ptr [rcx+10h], 6
0x18001152e  jz      short loc_18001157A
0x180011530  cmp     dword ptr [rcx+10h], 5
0x180011534  jz      short loc_1800115A9
0x180011536  lea     rdx, [rsp+48h+arg_0]; struct _tagpropertykey *
0x18001153b  call    ?GetConditionPropertyNameFromKey@StructuredQuery1@@YAJAEBU_tagpropertykey@@PEAPEA_W@Z; StructuredQuery1::GetConditionPropertyNameFromKey(_tagpropertykey const &,wchar_t * *)
0x180011540  mov     rdi, qword ptr [rsp+48h+arg_0.fmtid.Data1]
0x180011545  mov     ebx, eax
0x180011547  jmp     short loc_1800114F4
0x180011549  test    ebx, ebx
0x18001154b  js      short loc_18001155E
0x18001154d  lea     rdx, [rbp+48h]; pvarSrc
0x180011551  mov     rcx, rsi; pvarDest
0x180011554  call    cs:__imp_PropVariantCopy
0x18001155a  mov     ebx, eax
0x18001155c  jmp     short loc_1800114F9
0x18001155e  xorps   xmm0, xmm0
0x180011561  xor     eax, eax
0x180011563  movups  xmmword ptr [rsi], xmm0
0x180011566  mov     [rsi+10h], rax
0x18001156a  mov     rcx, rdi; pv
0x18001156d  xor     r12d, r12d
0x180011570  call    cs:__imp_CoTaskMemFree
0x180011576  xor     edi, edi
0x180011578  jmp     short loc_1800114FD
0x18001157a  mov     rax, [rcx]
0x18001157d  sub     rax, qword ptr cs:PKEY_FullText.fmtid.Data1
0x180011584  jnz     short loc_180011591
0x180011586  mov     rax, [rcx+8]
0x18001158a  sub     rax, qword ptr cs:PKEY_FullText.fmtid.Data4
0x180011591  test    rax, rax
0x180011594  jnz     short loc_180011530
0x180011596  lea     r9, [rsp+48h+arg_0]
0x18001159b  lea     r8, StringValue; "*"
0x1800115a2  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x1800115a7  jmp     short loc_180011540
0x1800115a9  mov     rax, [rcx]
0x1800115ac  sub     rax, cs:PKEY_ForceFullText
0x1800115b3  jnz     short loc_1800115C0
0x1800115b5  mov     rax, [rcx+8]
0x1800115b9  sub     rax, cs:qword_18009B8E0
0x1800115c0  test    rax, rax
0x1800115c3  jnz     loc_180011536
0x1800115c9  jmp     short loc_180011596
```
