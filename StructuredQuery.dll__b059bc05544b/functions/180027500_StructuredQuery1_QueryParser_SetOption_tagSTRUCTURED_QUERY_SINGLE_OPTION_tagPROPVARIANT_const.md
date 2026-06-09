# StructuredQuery1::QueryParser::SetOption(tagSTRUCTURED_QUERY_SINGLE_OPTION,tagPROPVARIANT const *)

- ea: `0x180027500`
- end: `0x180027774`
- name: `?SetOption@QueryParser@StructuredQuery1@@UEAAJW4tagSTRUCTURED_QUERY_SINGLE_OPTION@@PEBUtagPROPVARIANT@@@Z`
- size: `628`
- prototype: `int(StructuredQuery1::QueryParser *__hidden this, enum tagSTRUCTURED_QUERY_SINGLE_OPTION, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001b2b4`
- `0x180026ae4`
- `0x180027500`
- `0x18002777c`
- `0x1800277a0`
- `0x180027d08`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002752e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002752e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800275cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800275cc`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180027689`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180027766`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180027689`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x180027766`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800276e3`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800276e3`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18002775b`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18002775b`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002767e`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18002767e`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x1800276d2`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x1800276d2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800275c1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800275c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002759c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002759c`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::SetOption(
        StructuredQuery1::QueryParser *this,
        int a2,
        const struct tagPROPVARIANT *a3)
{
  RTL_SRWLOCK *v6; // r14
  HRESULT Schema; // edi
  struct _TIME_ZONE_INFORMATION **v8; // r8
  int v9; // ebx
  unsigned int UserDefaultLCID; // eax
  LONG v11; // eax
  HRESULT v12; // eax
  int v14; // ebx
  unsigned __int16 uiVal; // ax
  int UserDefaultLangID; // ebx
  int v17; // ebx
  enum tagSTRUCTURED_QUERY_SYNTAX lVal; // edx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  unsigned int ulVal; // ecx
  __int64 v24; // rax
  __int64 (__fastcall ***QuadPart)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v26; // ecx
  __int64 v27; // rax
  BYTE *pData; // rcx
  struct _TIME_ZONE_INFORMATION **v29; // r8
  __int64 v30; // rdx
  __int64 v31; // [rsp+70h] [rbp+18h] BYREF

  if ( !a3 )
    return (unsigned int)-2147024809;
  v6 = (RTL_SRWLOCK *)((char *)this + 152);
  Schema = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  if ( a2 > 5 )
  {
    v14 = a2 - 6;
    if ( !v14 )
    {
      if ( a3->vt == 19 )
      {
        uiVal = a3->uiVal;
        if ( uiVal == 1024 )
        {
          uiVal = GetUserDefaultLangID();
        }
        else if ( uiVal == 2048 )
        {
          uiVal = GetSystemDefaultLangID();
        }
        UserDefaultLangID = uiVal;
        if ( !IsValidOrFallbackLocale(uiVal) )
          UserDefaultLangID = GetUserDefaultLangID();
        *((_DWORD *)this + 12) = UserDefaultLangID;
        goto LABEL_18;
      }
      goto LABEL_41;
    }
    v17 = v14 - 1;
    if ( v17 )
    {
      v21 = v17 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( v22 )
        {
          if ( v22 == 1 && a3->vt == 19 )
          {
            ulVal = a3->ulVal;
            if ( ulVal <= 1 )
            {
              v24 = *((_QWORD *)this + 12);
              *((_DWORD *)this + 20) = ulVal;
              if ( v24 )
                *(_DWORD *)(v24 + 164) = ulVal;
              goto LABEL_18;
            }
          }
        }
        else if ( a3->vt == 19 )
        {
          v26 = a3->ulVal;
          if ( v26 <= 1 )
          {
            v27 = *((_QWORD *)this + 13);
            *((_DWORD *)this + 19) = v26;
            if ( v27 )
              *(_DWORD *)(v27 + 64) = v26;
            goto LABEL_18;
          }
        }
        goto LABEL_41;
      }
      if ( a3->vt == 1 )
      {
        pData = 0;
      }
      else
      {
        if ( a3->vt != 65 || a3->lVal != 172 )
          goto LABEL_41;
        pData = a3->bstrblobVal.pData;
      }
      Schema = StructuredQuery1::CopyTimeZoneInfo(
                 (StructuredQuery1 *)pData,
                 (const struct _TIME_ZONE_INFORMATION *)((char *)this + 136),
                 v8);
      if ( Schema < 0 )
        goto LABEL_18;
      v30 = *((_QWORD *)this + 13);
      if ( !v30 )
        goto LABEL_18;
      v12 = StructuredQuery1::CopyTimeZoneInfo(
              *((StructuredQuery1 **)this + 17),
              (const struct _TIME_ZONE_INFORMATION *)(v30 + 56),
              v29);
      goto LABEL_17;
    }
    if ( a3->vt == 19 )
    {
      lVal = a3->lVal;
      if ( (unsigned int)lVal <= SQS_NATURAL_QUERY_SYNTAX )
        goto LABEL_32;
    }
LABEL_41:
    Schema = -2147024809;
    goto LABEL_18;
  }
  if ( a2 == 5 )
  {
    if ( !a3->vt )
    {
      *((_DWORD *)this + 22) = 2;
      goto LABEL_18;
    }
    if ( a3->vt == 3 )
    {
      *((_DWORD *)this + 22) = a3->lVal;
      goto LABEL_18;
    }
    goto LABEL_41;
  }
  if ( !a2 )
  {
    Schema = PropVariantClear((PROPVARIANT *)this + 3);
    if ( Schema < 0 )
      goto LABEL_18;
    Schema = StructuredQuery1::QueryParser::LoadSchema((StructuredQuery1::QueryParser *)((char *)this - 8), a3);
    if ( Schema < 0 )
      goto LABEL_18;
    v12 = PropVariantCopy((PROPVARIANT *)this + 3, (const PROPVARIANT *)a3);
    goto LABEL_17;
  }
  v9 = a2 - 1;
  if ( !v9 )
  {
    if ( !a3->vt )
    {
      *((_DWORD *)this + 13) = (unsigned __int16)GetKeyboardLayout(0);
      goto LABEL_18;
    }
    if ( a3->vt == 19 )
    {
      UserDefaultLCID = a3->ulVal;
      if ( UserDefaultLCID == 1024 )
      {
        UserDefaultLCID = GetUserDefaultLCID();
      }
      else if ( UserDefaultLCID == 2048 )
      {
        UserDefaultLCID = GetSystemDefaultLCID();
      }
      if ( IsValidOrFallbackLocale(UserDefaultLCID) )
        v11 = a3->lVal;
      else
        v11 = 127;
      *((_DWORD *)this + 13) = v11;
      goto LABEL_18;
    }
    goto LABEL_41;
  }
  v19 = v9 - 1;
  if ( !v19 )
  {
    if ( !a3->vt )
    {
      IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>((_QWORD *)this + 7);
      goto LABEL_18;
    }
    if ( a3->vt == 13 )
    {
      QuadPart = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))a3->hVal.QuadPart;
      v31 = 0;
      Schema = (**QuadPart)(QuadPart, &GUID_d53552c8_77e3_101a_b552_08002b33b0e6, &v31);
      if ( Schema >= 0 )
      {
        IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>((_QWORD *)this + 7);
        *((_QWORD *)this + 7) = v31;
      }
      goto LABEL_18;
    }
    goto LABEL_41;
  }
  v20 = v19 - 1;
  if ( !v20 )
  {
    if ( !a3->vt )
    {
      lVal = SQS_ADVANCED_QUERY_SYNTAX;
LABEL_32:
      v12 = StructuredQuery1::QueryParser::SetSyntax((StructuredQuery1::QueryParser *)((char *)this - 8), lVal);
LABEL_17:
      Schema = v12;
      goto LABEL_18;
    }
    if ( a3->vt == 11 )
    {
      lVal = (a3->iVal != 0) + 1;
      goto LABEL_32;
    }
    goto LABEL_41;
  }
  if ( v20 != 1 )
    goto LABEL_41;
  if ( !a3->vt )
  {
    *((_BYTE *)this + 84) = 1;
    goto LABEL_18;
  }
  if ( a3->vt != 11 )
    goto LABEL_41;
  *((_BYTE *)this + 84) = a3->iVal != 0;
LABEL_18:
  ReleaseSRWLockExclusive(v6);
  return (unsigned int)Schema;
}

```

## disassembly

```asm
0x180027500  push    rbx
0x180027502  push    rbp
0x180027503  push    rsi
0x180027504  push    rdi
0x180027505  push    r14
0x180027507  push    r15
0x180027509  sub     rsp, 28h
0x18002750d  xor     r15d, r15d
0x180027510  mov     rsi, r8
0x180027513  mov     ebx, edx
0x180027515  mov     rbp, rcx
0x180027518  test    r8, r8
0x18002751b  jz      loc_180027627
0x180027521  lea     r14, [rcx+98h]
0x180027528  mov     edi, r15d
0x18002752b  mov     rcx, r14; SRWLock
0x18002752e  call    cs:__imp_AcquireSRWLockExclusive
0x180027534  cmp     ebx, 5
0x180027537  jg      loc_1800275E1
0x18002753d  jz      loc_1800276F8
0x180027543  test    ebx, ebx
0x180027545  jz      short loc_180027598
0x180027547  sub     ebx, 1
0x18002754a  jnz     loc_180027653
0x180027550  cmp     [rsi], r15w
0x180027554  jz      loc_1800276D0
0x18002755a  cmp     word ptr [rsi], 13h
0x18002755e  jnz     loc_180027694
0x180027564  mov     eax, [rsi+8]
0x180027567  mov     ecx, 400h
0x18002756c  cmp     eax, ecx
0x18002756e  jz      loc_18002767E
0x180027574  mov     ecx, 800h
0x180027579  cmp     eax, ecx
0x18002757b  jz      loc_1800276E3
0x180027581  mov     ecx, eax; unsigned int
0x180027583  call    ?IsValidOrFallbackLocale@@YA_NK@Z; IsValidOrFallbackLocale(ulong)
0x180027588  test    al, al
0x18002758a  jz      loc_1800276EE
0x180027590  mov     eax, [rsi+8]
0x180027593  mov     [rbp+34h], eax
0x180027596  jmp     short loc_1800275C9
0x180027598  lea     rcx, [rbp+18h]; pvar
0x18002759c  call    cs:__imp_PropVariantClear
0x1800275a2  mov     edi, eax
0x1800275a4  test    eax, eax
0x1800275a6  js      short loc_1800275C9
0x1800275a8  lea     rcx, [rbp-8]; this
0x1800275ac  mov     rdx, rsi; struct tagPROPVARIANT *
0x1800275af  call    ?LoadSchema@QueryParser@StructuredQuery1@@QEAAJPEBUtagPROPVARIANT@@@Z; StructuredQuery1::QueryParser::LoadSchema(tagPROPVARIANT const *)
0x1800275b4  mov     edi, eax
0x1800275b6  test    eax, eax
0x1800275b8  js      short loc_1800275C9
0x1800275ba  mov     rdx, rsi; pvarSrc
0x1800275bd  lea     rcx, [rbp+18h]; pvarDest
0x1800275c1  call    cs:__imp_PropVariantCopy
0x1800275c7  mov     edi, eax
0x1800275c9  mov     rcx, r14; SRWLock
0x1800275cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800275d2  mov     eax, edi
0x1800275d4  add     rsp, 28h
0x1800275d8  pop     r15
0x1800275da  pop     r14
0x1800275dc  pop     rdi
0x1800275dd  pop     rsi
0x1800275de  pop     rbp
0x1800275df  pop     rbx
0x1800275e0  retn
0x1800275e1  sub     ebx, 6
0x1800275e4  jnz     short loc_18002762E
0x1800275e6  cmp     word ptr [rsi], 13h
0x1800275ea  jnz     loc_180027694
0x1800275f0  movzx   eax, word ptr [rsi+8]
0x1800275f4  mov     ecx, 400h
0x1800275f9  cmp     ax, cx
0x1800275fc  jz      loc_180027689
0x180027602  mov     ecx, 800h
0x180027607  cmp     ax, cx
0x18002760a  jz      loc_18002775B
0x180027610  movzx   ebx, ax
0x180027613  mov     ecx, ebx; unsigned int
0x180027615  call    ?IsValidOrFallbackLocale@@YA_NK@Z; IsValidOrFallbackLocale(ulong)
0x18002761a  test    al, al
0x18002761c  jz      loc_180027766
0x180027622  mov     [rbp+30h], ebx
0x180027625  jmp     short loc_1800275C9
0x180027627  mov     edi, 80070057h
0x18002762c  jmp     short loc_1800275D2
0x18002762e  sub     ebx, 1
0x180027631  jnz     loc_18002770E
0x180027637  cmp     word ptr [rsi], 13h
0x18002763b  jnz     short loc_180027694
0x18002763d  mov     edx, [rsi+8]; enum tagSTRUCTURED_QUERY_SYNTAX
0x180027640  cmp     edx, 2
0x180027643  ja      short loc_180027694
0x180027645  lea     rcx, [rbp-8]; this
0x180027649  call    ?SetSyntax@QueryParser@StructuredQuery1@@AEAAJW4tagSTRUCTURED_QUERY_SYNTAX@@@Z; StructuredQuery1::QueryParser::SetSyntax(tagSTRUCTURED_QUERY_SYNTAX)
0x18002764e  jmp     loc_1800275C7
0x180027653  sub     ebx, 1
0x180027656  jz      short loc_1800276B8
0x180027658  sub     ebx, 1
0x18002765b  jz      short loc_1800276A7
0x18002765d  cmp     ebx, 1
0x180027660  jnz     short loc_180027694
0x180027662  cmp     [rsi], r15w
0x180027666  jz      short loc_18002769E
0x180027668  cmp     word ptr [rsi], 0Bh
0x18002766c  jnz     short loc_180027694
0x18002766e  cmp     [rsi+8], r15w
0x180027673  setnz   al
0x180027676  mov     [rbp+54h], al
0x180027679  jmp     loc_1800275C9
0x18002767e  call    cs:__imp_GetUserDefaultLCID
0x180027684  jmp     loc_180027581
0x180027689  call    cs:__imp_GetUserDefaultLangID
0x18002768f  jmp     loc_180027610
0x180027694  mov     edi, 80070057h
0x180027699  jmp     loc_1800275C9
0x18002769e  mov     byte ptr [rbp+54h], 1
0x1800276a2  jmp     loc_1800275C9
0x1800276a7  cmp     [rsi], r15w
0x1800276ab  jnz     loc_1800892EA
0x1800276b1  mov     edx, 1
0x1800276b6  jmp     short loc_180027645
0x1800276b8  cmp     [rsi], r15w
0x1800276bc  jnz     loc_180089306
0x1800276c2  lea     rcx, [rbp+38h]
0x1800276c6  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x1800276cb  jmp     loc_1800275C9
0x1800276d0  xor     ecx, ecx; idThread
0x1800276d2  call    cs:__imp_GetKeyboardLayout
0x1800276d8  movzx   ecx, ax
0x1800276db  mov     [rbp+34h], ecx
0x1800276de  jmp     loc_1800275C9
0x1800276e3  call    cs:__imp_GetSystemDefaultLCID
0x1800276e9  jmp     loc_180027581
0x1800276ee  mov     eax, 7Fh
0x1800276f3  jmp     loc_180027593
0x1800276f8  cmp     [rsi], r15w
0x1800276fc  jnz     loc_180089351
0x180027702  mov     dword ptr [rbp+58h], 2
0x180027709  jmp     loc_1800275C9
0x18002770e  sub     ebx, 1
0x180027711  jz      loc_180089398
0x180027717  sub     ebx, 1
0x18002771a  jz      loc_180089366
0x180027720  cmp     ebx, 1
0x180027723  jnz     loc_180027694
0x180027729  cmp     word ptr [rsi], 13h
0x18002772d  jnz     loc_180027694
0x180027733  mov     ecx, [rsi+8]
0x180027736  mov     eax, ebx
0x180027738  cmp     ecx, eax
0x18002773a  ja      loc_180027694
0x180027740  mov     rax, [rbp+60h]
0x180027744  mov     [rbp+50h], ecx
0x180027747  test    rax, rax
0x18002774a  jz      loc_1800275C9
0x180027750  mov     [rax+0A4h], ecx
0x180027756  jmp     loc_1800275C9
0x18002775b  call    cs:__imp_GetSystemDefaultLangID
0x180027761  jmp     loc_180027610
0x180027766  call    cs:__imp_GetUserDefaultLangID
0x18002776c  movzx   ebx, ax
0x18002776f  jmp     loc_180027622
0x1800892ea  cmp     word ptr [rsi], 0Bh
0x1800892ee  jnz     loc_180027694
0x1800892f4  movzx   eax, word ptr [rsi+8]
0x1800892f8  neg     ax
0x1800892fb  sbb     edx, edx
0x1800892fd  neg     edx
0x1800892ff  inc     edx
0x180089301  jmp     loc_180027645
0x180089306  cmp     word ptr [rsi], 0Dh
0x18008930a  jnz     loc_180027694
0x180089310  mov     rcx, [rsi+8]
0x180089314  lea     r8, [rsp+58h+arg_10]
0x180089319  mov     [rsp+58h+arg_10], r15
0x18008931e  lea     rdx, _GUID_d53552c8_77e3_101a_b552_08002b33b0e6
0x180089325  mov     rax, [rcx]
0x180089328  mov     rax, [rax]
0x18008932b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089330  mov     edi, eax
0x180089332  test    eax, eax
0x180089334  js      loc_1800275C9
0x18008933a  lea     rcx, [rbp+38h]
0x18008933e  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x180089343  mov     rax, [rsp+58h+arg_10]
0x180089348  mov     [rbp+38h], rax
0x18008934c  jmp     loc_1800275C9
0x180089351  cmp     word ptr [rsi], 3
0x180089355  jnz     loc_180027694
0x18008935b  mov     eax, [rsi+8]
0x18008935e  mov     [rbp+58h], eax
0x180089361  jmp     loc_1800275C9
0x180089366  cmp     word ptr [rsi], 13h
0x18008936a  jnz     loc_180027694
0x180089370  mov     ecx, [rsi+8]
0x180089373  mov     eax, 1
0x180089378  cmp     ecx, eax
0x18008937a  ja      loc_180027694
0x180089380  mov     rax, [rbp+68h]
0x180089384  mov     [rbp+4Ch], ecx
0x180089387  test    rax, rax
0x18008938a  jz      loc_1800275C9
0x180089390  mov     [rax+40h], ecx
0x180089393  jmp     loc_1800275C9
0x180089398  mov     eax, 1
0x18008939d  cmp     [rsi], ax
0x1800893a0  jnz     short loc_1800893A7
0x1800893a2  mov     rcx, r15
0x1800893a5  jmp     short loc_1800893C2
0x1800893a7  cmp     word ptr [rsi], 41h ; 'A'
0x1800893ab  jnz     loc_180027694
0x1800893b1  cmp     dword ptr [rsi+8], 0ACh
0x1800893b8  jnz     loc_180027694
0x1800893be  mov     rcx, [rsi+10h]; this
0x1800893c2  lea     rbx, [rbp+88h]
0x1800893c9  mov     rdx, rbx; struct _TIME_ZONE_INFORMATION *
0x1800893cc  call    ?CopyTimeZoneInfo@StructuredQuery1@@YAJPEBU_TIME_ZONE_INFORMATION@@PEAPEAU2@@Z; StructuredQuery1::CopyTimeZoneInfo(_TIME_ZONE_INFORMATION const *,_TIME_ZONE_INFORMATION * *)
0x1800893d1  mov     edi, eax
0x1800893d3  test    eax, eax
0x1800893d5  js      loc_1800275C9
0x1800893db  mov     rdx, [rbp+68h]
0x1800893df  test    rdx, rdx
0x1800893e2  jz      loc_1800275C9
0x1800893e8  mov     rcx, [rbx]; this
0x1800893eb  add     rdx, 38h ; '8'; struct _TIME_ZONE_INFORMATION *
0x1800893ef  call    ?CopyTimeZoneInfo@StructuredQuery1@@YAJPEBU_TIME_ZONE_INFORMATION@@PEAPEAU2@@Z; StructuredQuery1::CopyTimeZoneInfo(_TIME_ZONE_INFORMATION const *,_TIME_ZONE_INFORMATION * *)
0x1800893f4  nop
0x1800893f5  jmp     loc_1800275C7
```
