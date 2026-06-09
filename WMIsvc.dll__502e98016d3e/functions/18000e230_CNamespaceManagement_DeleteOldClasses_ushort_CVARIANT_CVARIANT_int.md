# CNamespaceManagement::DeleteOldClasses(ushort *,CVARIANT &,CVARIANT &,int)

- ea: `0x18000e230`
- end: `0x18000e6d6`
- name: `?DeleteOldClasses@CNamespaceManagement@@QEAAHPEAGAEAVCVARIANT@@1H@Z`
- size: `1190`
- prototype: `__int64 __usercall@<rax>(CNamespaceManagement *__hidden this@<rcx>, unsigned __int16 *@<rdx>, struct CVARIANT *@<r8>, struct CVARIANT *@<r9>, int)`
- caller_count: `4`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000226c`
- `0x180002478`
- `0x180002a5c`
- `0x180017fd8`

## callees

- `0x1800021f0`
- `0x1800031e0`
- `0x180003b08`
- `0x180003e10`
- `0x1800079f0`
- `0x18000d904`
- `0x18000dc88`
- `0x18000e230`
- `0x180017648`
- `0x1800183b8`
- `0x1800187d4`
- `0x180018850`
- `0x1800193b4`
- `0x18001947c`
- `0x180020010`

## import_xrefs

- `wbemcomn!DebugTrace` at `0x18000e27f`
- `wbemcomn!DebugTrace` at `0x18000e299`
- `wbemcomn!DebugTrace` at `0x18000e27f`
- `wbemcomn!DebugTrace` at `0x18000e299`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e356`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e356`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e3b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e3b8`
- `OLEAUT32!__imp_VariantInit` at `0x18000e3e3`
- `OLEAUT32!__imp_VariantInit` at `0x18000e454`
- `OLEAUT32!__imp_VariantInit` at `0x18000e3e3`
- `OLEAUT32!__imp_VariantInit` at `0x18000e454`
- `OLEAUT32!__imp_VariantClear` at `0x18000e627`
- `OLEAUT32!__imp_VariantClear` at `0x18000e632`
- `OLEAUT32!__imp_VariantClear` at `0x18000e65e`
- `OLEAUT32!__imp_VariantClear` at `0x18000e69c`
- `OLEAUT32!__imp_VariantClear` at `0x18000e627`
- `OLEAUT32!__imp_VariantClear` at `0x18000e632`
- `OLEAUT32!__imp_VariantClear` at `0x18000e65e`
- `OLEAUT32!__imp_VariantClear` at `0x18000e69c`

## string_xrefs

- `0x18000e473`: `__RELPATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CNamespaceManagement::DeleteOldClasses(
        const OLECHAR **this,
        unsigned __int16 *a2,
        struct CVARIANT *a3,
        struct CVARIANT *a4,
        int a5)
{
  const WCHAR *v7; // r14
  int v9; // r15d
  unsigned int v10; // edi
  unsigned __int16 *v11; // rsi
  unsigned int v12; // r12d
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // rdx
  OLECHAR *v15; // rdi
  int v16; // ebx
  const unsigned __int16 *v17; // rdx
  BOOL v18; // r14d
  OLECHAR *bstrVal; // rdx
  __int64 v20; // rdi
  OLECHAR *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r15
  __int64 (__fastcall *v24)(__int64, __int64, _QWORD, __int64, __int64 *, _QWORD); // r14
  __int64 v25; // rdi
  int v26; // ebx
  unsigned __int16 *v27; // r9
  unsigned __int16 *v28; // r8
  __int64 v30; // [rsp+28h] [rbp-89h]
  __int64 v31; // [rsp+30h] [rbp-81h]
  __int64 v32; // [rsp+40h] [rbp-71h] BYREF
  __int64 v33; // [rsp+48h] [rbp-69h] BYREF
  unsigned int v34; // [rsp+50h] [rbp-61h]
  __int64 v35; // [rsp+58h] [rbp-59h] BYREF
  int v36; // [rsp+60h] [rbp-51h] BYREF
  __int64 v37; // [rsp+68h] [rbp-49h] BYREF
  __int64 v38; // [rsp+70h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-39h] BYREF
  OLECHAR *psz; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int16 *v41; // [rsp+98h] [rbp-19h] BYREF
  VARIANTARG v42; // [rsp+A0h] [rbp-11h] BYREF

  v7 = a2;
  CAutoWChar::CAutoWChar((CAutoWChar *)&v41, 520);
  v9 = 0;
  v10 = 0;
  v35 = 0;
  DebugTrace(10, "Deleting Old Classes for Driver\n");
  TranslateAndLog(v7, 1);
  DebugTrace(10, "***************************************\n");
  v11 = v41;
  if ( !v41 )
    goto LABEL_55;
  if ( a5 )
  {
    v12 = *((_DWORD *)a3 + 2);
    v13 = *((_DWORD *)a4 + 2);
  }
  else
  {
    v13 = 0;
    v12 = 0;
  }
  v34 = v13;
  if ( (int)ConvertStringToCTypeString(v41, 520, v7) < 0
    || (int)CNamespaceManagement::InitQuery(
              (CNamespaceManagement *)this,
              L"select * from WDMClassesOfDriver where Driver = ") < 0
    || (int)CNamespaceManagement::UpdateQuery((CNamespaceManagement *)this, v14, v7) < 0
    || (int)CNamespaceManagement::UpdateQuery((CNamespaceManagement *)this, L" and (HighDateTime != ", v13) < 0
    || (int)CNamespaceManagement::UpdateQuery((CNamespaceManagement *)this, L" or LowDateTime != ", v12) < 0
    || (int)CNamespaceManagement::AddToQuery((CNamespaceManagement *)this, L")") < 0 )
  {
    goto LABEL_55;
  }
  v15 = SysAllocString(this[1]);
  if ( v15 )
  {
    v33 = 0;
    CBSTR::SetStr((CBSTR *)&v33, (OLECHAR *)L"WQL");
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, OLECHAR *, __int64, _QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this[8] + 3) + 16LL)
                                                                                            + 160LL))(
            *(_QWORD *)(*((_QWORD *)this[8] + 3) + 16LL),
            v33,
            v15,
            48,
            *(_QWORD *)(*((_QWORD *)this[8] + 3) + 24LL),
            &v35);
    SysFreeString(v15);
    CBSTR::Clear((CBSTR *)&v33);
  }
  else
  {
    v16 = -2147024882;
  }
  if ( v16 )
    goto LABEL_52;
  v32 = 0;
  v36 = 0;
  VariantInit(&pvarg);
  while ( 1 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v35 + 32LL))(
            v35,
            2000,
            1,
            &v32,
            &v36);
    if ( v16 )
      break;
    v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v32 + 32LL))(
            v32,
            L"ClassName",
            0,
            &pvarg,
            0,
            0);
    if ( v16 )
    {
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      v32 = 0;
      break;
    }
    VariantInit(&v42);
    v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v32 + 32LL))(
            v32,
            L"__RELPATH",
            0,
            &v42,
            0,
            0);
    if ( v16 )
    {
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      v32 = 0;
      VariantClear(&v42);
      break;
    }
    if ( a5 )
    {
      v18 = 1;
      v37 = 0;
      bstrVal = 0;
      if ( pvarg.vt == 8 )
        bstrVal = pvarg.bstrVal;
      v38 = 0;
      CBSTR::SetStr((CBSTR *)&v38, bstrVal);
      v20 = v38;
      if ( v38 )
      {
        CAutoWChar::CAutoWChar((CAutoWChar *)&psz, 1040);
        v21 = psz;
        if ( psz )
        {
          LODWORD(v31) = v12;
          LODWORD(v30) = v34;
          if ( (int)StringCchPrintfW(
                      psz,
                      0x410u,
                      L"WDMClassesOfDriver.ClassName=\"%s\",Driver=\"%s\",HighDateTime=%lu,LowDateTime=%lu",
                      v20,
                      v11,
                      v30,
                      v31) >= 0 )
          {
            v22 = *((_QWORD *)this[8] + 3);
            v23 = *(_QWORD *)(v22 + 16);
            v24 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64 *, _QWORD))(*(_QWORD *)v23 + 48LL);
            v25 = *(_QWORD *)(v22 + 24);
            v33 = 0;
            CBSTR::SetStr((CBSTR *)&v33, v21);
            v26 = v24(v23, v33, 0, v25, &v37, 0);
            CBSTR::Clear((CBSTR *)&v33);
            v18 = v26 != 0;
            if ( v37 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            v37 = 0;
            v9 = 1;
          }
        }
        CAutoWChar::~CAutoWChar((CAutoWChar *)&psz);
      }
      CBSTR::Clear((CBSTR *)&v38);
      if ( !v9 )
      {
        v9 = 0;
        goto LABEL_40;
      }
      v9 = 0;
    }
    else
    {
      v17 = 0;
      if ( pvarg.vt == 8 )
        v17 = pvarg.bstrVal;
      v18 = CNamespaceManagement::IsClassAsociatedWithDifferentDriver((CNamespaceManagement *)this, v17, v7) == 0;
    }
    v27 = 0;
    if ( v42.vt == 8 )
      v27 = v42.bstrVal;
    v28 = 0;
    if ( pvarg.vt == 8 )
      v28 = pvarg.bstrVal;
    CNamespaceManagement::DeleteUnusedClassAndDriverInfo((CNamespaceManagement *)this, v18, v28, v27);
LABEL_40:
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
    VariantClear(&pvarg);
    VariantClear(&v42);
    v7 = a2;
  }
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v35 = 0;
  VariantClear(&pvarg);
LABEL_52:
  if ( v16 == 262149 || (v10 = 0, v16 == 1) )
    v10 = 1;
LABEL_55:
  CAutoWChar::~CAutoWChar((CAutoWChar *)&v41);
  return v10;
}

```

## disassembly

```asm
0x18000e230  mov     [rsp-8+arg_8], rdx
0x18000e235  push    rbp
0x18000e236  push    rbx
0x18000e237  push    rsi
0x18000e238  push    rdi
0x18000e239  push    r12
0x18000e23b  push    r13
0x18000e23d  push    r14
0x18000e23f  push    r15
0x18000e241  lea     rbp, [rsp-17h]
0x18000e246  sub     rsp, 0C8h
0x18000e24d  mov     rbx, r9
0x18000e250  mov     r12, r8
0x18000e253  mov     r14, rdx
0x18000e256  mov     r13, rcx
0x18000e259  mov     edx, 208h; int
0x18000e25e  lea     rcx, [rbp+4Fh+var_68]; this
0x18000e262  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x18000e267  nop
0x18000e268  xor     r15d, r15d
0x18000e26b  mov     edi, r15d
0x18000e26e  mov     [rbp+4Fh+var_A8], r15
0x18000e272  lea     rdx, aDeletingOldCla; "Deleting Old Classes for Driver\n"
0x18000e279  lea     esi, [r15+0Ah]
0x18000e27d  mov     ecx, esi
0x18000e27f  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000e285  lea     edx, [rsi-9]; int
0x18000e288  mov     rcx, r14; lpWideCharStr
0x18000e28b  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x18000e290  lea     rdx, asc_180023540; "***************************************"...
0x18000e297  mov     ecx, esi
0x18000e299  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x18000e29f  mov     rsi, [rbp+4Fh+var_68]
0x18000e2a3  test    rsi, rsi
0x18000e2a6  jz      loc_18000E6B7
0x18000e2ac  cmp     [rbp+4Fh+arg_20], r15d
0x18000e2b0  jz      short loc_18000E2BC
0x18000e2b2  mov     r12d, [r12+8]
0x18000e2b7  mov     ebx, [rbx+8]
0x18000e2ba  jmp     short loc_18000E2C2
0x18000e2bc  mov     ebx, r15d
0x18000e2bf  mov     r12d, r15d
0x18000e2c2  mov     [rbp+4Fh+var_B0], ebx
0x18000e2c5  mov     r8, r14; unsigned __int16 *
0x18000e2c8  mov     edx, 208h; int
0x18000e2cd  mov     rcx, rsi; unsigned __int16 *
0x18000e2d0  call    ?ConvertStringToCTypeString@@YAJPEAGHPEBG@Z; ConvertStringToCTypeString(ushort *,int,ushort const *)
0x18000e2d5  test    eax, eax
0x18000e2d7  js      loc_18000E6B7
0x18000e2dd  lea     rdx, aSelectFromWdmc; "select * from WDMClassesOfDriver where "...
0x18000e2e4  mov     rcx, r13; this
0x18000e2e7  call    ?InitQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::InitQuery(ushort const *)
0x18000e2ec  test    eax, eax
0x18000e2ee  js      loc_18000E6B7
0x18000e2f4  mov     r8, r14; unsigned __int16 *
0x18000e2f7  mov     rcx, r13; this
0x18000e2fa  call    ?UpdateQuery@CNamespaceManagement@@QEAAJPEBG0@Z; CNamespaceManagement::UpdateQuery(ushort const *,ushort const *)
0x18000e2ff  test    eax, eax
0x18000e301  js      loc_18000E6B7
0x18000e307  mov     r8d, ebx; unsigned int
0x18000e30a  lea     rdx, aAndHighdatetim; " and (HighDateTime != "
0x18000e311  mov     rcx, r13; this
0x18000e314  call    ?UpdateQuery@CNamespaceManagement@@QEAAJPEBGK@Z; CNamespaceManagement::UpdateQuery(ushort const *,ulong)
0x18000e319  test    eax, eax
0x18000e31b  js      loc_18000E6B7
0x18000e321  mov     r8d, r12d; unsigned int
0x18000e324  lea     rdx, aOrLowdatetime; " or LowDateTime != "
0x18000e32b  mov     rcx, r13; this
0x18000e32e  call    ?UpdateQuery@CNamespaceManagement@@QEAAJPEBGK@Z; CNamespaceManagement::UpdateQuery(ushort const *,ulong)
0x18000e333  test    eax, eax
0x18000e335  js      loc_18000E6B7
0x18000e33b  lea     rdx, pszSrc; ")"
0x18000e342  mov     rcx, r13; this
0x18000e345  call    ?AddToQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::AddToQuery(ushort const *)
0x18000e34a  test    eax, eax
0x18000e34c  js      loc_18000E6B7
0x18000e352  mov     rcx, [r13+8]; psz
0x18000e356  call    cs:__imp_SysAllocString
0x18000e35c  mov     rdi, rax
0x18000e35f  test    rax, rax
0x18000e362  jz      short loc_18000E3CA
0x18000e364  mov     [rbp+4Fh+var_B8], r15
0x18000e368  lea     rdx, aWql; "WQL"
0x18000e36f  lea     rcx, [rbp+4Fh+var_B8]; this
0x18000e373  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x18000e378  nop
0x18000e379  mov     rcx, [r13+40h]
0x18000e37d  mov     r8, [rcx+18h]
0x18000e381  mov     rcx, [r8+10h]
0x18000e385  mov     rdx, [rcx]
0x18000e388  mov     rax, [rdx+0A0h]
0x18000e38f  lea     rdx, [rbp+4Fh+var_A8]
0x18000e393  mov     [rsp+100h+var_D8], rdx
0x18000e398  mov     rdx, [r8+18h]
0x18000e39c  mov     [rsp+100h+var_E0], rdx
0x18000e3a1  mov     r9d, 30h ; '0'
0x18000e3a7  mov     r8, rdi
0x18000e3aa  mov     rdx, [rbp+4Fh+var_B8]
0x18000e3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3b3  mov     ebx, eax
0x18000e3b5  mov     rcx, rdi; bstrString
0x18000e3b8  call    cs:__imp_SysFreeString
0x18000e3be  nop
0x18000e3bf  lea     rcx, [rbp+4Fh+var_B8]; this
0x18000e3c3  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x18000e3c8  jmp     short loc_18000E3CF
0x18000e3ca  mov     ebx, 8007000Eh
0x18000e3cf  test    ebx, ebx
0x18000e3d1  jnz     loc_18000E6A2
0x18000e3d7  mov     [rbp+4Fh+var_C0], r15
0x18000e3db  mov     [rbp+4Fh+var_A0], r15d
0x18000e3df  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000e3e3  call    cs:__imp_VariantInit
0x18000e3e9  nop
0x18000e3ea  mov     rcx, [rbp+4Fh+var_A8]
0x18000e3ee  mov     rax, [rcx]
0x18000e3f1  lea     rdx, [rbp+4Fh+var_A0]
0x18000e3f5  mov     [rsp+100h+var_E0], rdx
0x18000e3fa  lea     r9, [rbp+4Fh+var_C0]
0x18000e3fe  mov     edi, 1
0x18000e403  mov     r8d, edi
0x18000e406  mov     edx, 7D0h
0x18000e40b  mov     rax, [rax+20h]
0x18000e40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e414  mov     ebx, eax
0x18000e416  test    eax, eax
0x18000e418  jnz     loc_18000E67F
0x18000e41e  mov     rcx, [rbp+4Fh+var_C0]
0x18000e422  mov     rax, [rcx]
0x18000e425  mov     [rsp+100h+var_D8], r15
0x18000e42a  mov     [rsp+100h+var_E0], r15
0x18000e42f  lea     r9, [rbp+4Fh+pvarg]
0x18000e433  xor     r8d, r8d
0x18000e436  lea     rdx, aClassname; "ClassName"
0x18000e43d  mov     rax, [rax+20h]
0x18000e441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e446  mov     ebx, eax
0x18000e448  test    eax, eax
0x18000e44a  jnz     loc_18000E666
0x18000e450  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x18000e454  call    cs:__imp_VariantInit
0x18000e45a  nop
0x18000e45b  mov     rcx, [rbp+4Fh+var_C0]
0x18000e45f  mov     rax, [rcx]
0x18000e462  mov     [rsp+100h+var_D8], r15
0x18000e467  mov     [rsp+100h+var_E0], r15
0x18000e46c  lea     r9, [rbp+4Fh+var_60]
0x18000e470  xor     r8d, r8d
0x18000e473  lea     rdx, aRelpath; "__RELPATH"
0x18000e47a  mov     rax, [rax+20h]
0x18000e47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e483  mov     ebx, eax
0x18000e485  test    eax, eax
0x18000e487  jnz     loc_18000E641
0x18000e48d  cmp     [rbp+4Fh+arg_20], r15d
0x18000e491  jnz     short loc_18000E4B9
0x18000e493  mov     rdx, r15
0x18000e496  cmp     word ptr [rbp+4Fh+pvarg], 8
0x18000e49b  cmovz   rdx, qword ptr [rbp+4Fh+pvarg+8]; unsigned __int16 *
0x18000e4a0  mov     r8, r14; unsigned __int16 *
0x18000e4a3  mov     rcx, r13; this
0x18000e4a6  call    ?IsClassAsociatedWithDifferentDriver@CNamespaceManagement@@AEAAHPEBG0@Z; CNamespaceManagement::IsClassAsociatedWithDifferentDriver(ushort const *,ushort const *)
0x18000e4ab  mov     r14d, r15d
0x18000e4ae  test    eax, eax
0x18000e4b0  setz    r14b
0x18000e4b4  jmp     loc_18000E5E0
0x18000e4b9  mov     r14d, edi
0x18000e4bc  mov     [rbp+4Fh+var_98], 0
0x18000e4c4  xor     edx, edx
0x18000e4c6  cmp     word ptr [rbp+4Fh+pvarg], 8
0x18000e4cb  cmovz   rdx, qword ptr [rbp+4Fh+pvarg+8]; psz
0x18000e4d0  mov     [rbp+4Fh+var_90], 0
0x18000e4d8  lea     rcx, [rbp+4Fh+var_90]; this
0x18000e4dc  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x18000e4e1  nop
0x18000e4e2  mov     rdi, [rbp+4Fh+var_90]
0x18000e4e6  test    rdi, rdi
0x18000e4e9  jz      loc_18000E5CF
0x18000e4ef  mov     edx, 410h; int
0x18000e4f4  lea     rcx, [rbp+4Fh+psz]; this
0x18000e4f8  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x18000e4fd  nop
0x18000e4fe  mov     rbx, [rbp+4Fh+psz]
0x18000e502  test    rbx, rbx
0x18000e505  jz      loc_18000E5C5
0x18000e50b  mov     [rsp+100h+var_D0], r12d
0x18000e510  mov     eax, [rbp+4Fh+var_B0]
0x18000e513  mov     dword ptr [rsp+100h+var_D8], eax
0x18000e517  mov     [rsp+100h+var_E0], rsi
0x18000e51c  mov     r9, rdi
0x18000e51f  lea     r8, aWdmclassesofdr; "WDMClassesOfDriver.ClassName=\"%s\",Dri"...
0x18000e526  mov     edx, 410h; unsigned __int64
0x18000e52b  mov     rcx, rbx; unsigned __int16 *
0x18000e52e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e533  test    eax, eax
0x18000e535  js      loc_18000E5C5
0x18000e53b  mov     rax, [r13+40h]
0x18000e53f  mov     rcx, [rax+18h]
0x18000e543  mov     r15, [rcx+10h]
0x18000e547  mov     rax, [r15]
0x18000e54a  mov     r14, [rax+30h]
0x18000e54e  mov     rdi, [rcx+18h]
0x18000e552  mov     [rbp+4Fh+var_B8], 0
0x18000e55a  mov     rdx, rbx; psz
0x18000e55d  lea     rcx, [rbp+4Fh+var_B8]; this
0x18000e561  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x18000e566  nop
0x18000e567  mov     [rsp+100h+var_D8], 0
0x18000e570  lea     rax, [rbp+4Fh+var_98]
0x18000e574  mov     [rsp+100h+var_E0], rax
0x18000e579  mov     r9, rdi
0x18000e57c  xor     r8d, r8d
0x18000e57f  mov     rdx, [rbp+4Fh+var_B8]
0x18000e583  mov     rcx, r15
0x18000e586  mov     rax, r14
0x18000e589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e58e  mov     ebx, eax
0x18000e590  lea     rcx, [rbp+4Fh+var_B8]; this
0x18000e594  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x18000e599  xor     r14d, r14d
0x18000e59c  test    ebx, ebx
0x18000e59e  setnz   r14b
0x18000e5a2  mov     rcx, [rbp+4Fh+var_98]
0x18000e5a6  test    rcx, rcx
0x18000e5a9  jz      short loc_18000E5B7
0x18000e5ab  mov     rax, [rcx]
0x18000e5ae  mov     rax, [rax+10h]
0x18000e5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5b7  mov     [rbp+4Fh+var_98], 0
0x18000e5bf  mov     r15d, 1
0x18000e5c5  lea     rcx, [rbp+4Fh+psz]; this
0x18000e5c9  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x18000e5ce  nop
0x18000e5cf  lea     rcx, [rbp+4Fh+var_90]; this
0x18000e5d3  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x18000e5d8  test    r15d, r15d
0x18000e5db  jz      short loc_18000E607
0x18000e5dd  xor     r15d, r15d
0x18000e5e0  mov     r9, r15
0x18000e5e3  cmp     word ptr [rbp+4Fh+var_60], 8
0x18000e5e8  cmovz   r9, qword ptr [rbp+4Fh+var_60+8]; unsigned __int16 *
0x18000e5ed  mov     r8, r15
0x18000e5f0  cmp     word ptr [rbp+4Fh+pvarg], 8
0x18000e5f5  cmovz   r8, qword ptr [rbp+4Fh+pvarg+8]; unsigned __int16 *
0x18000e5fa  mov     edx, r14d; int
0x18000e5fd  mov     rcx, r13; this
0x18000e600  call    ?DeleteUnusedClassAndDriverInfo@CNamespaceManagement@@QEAAJHPEAG0@Z; CNamespaceManagement::DeleteUnusedClassAndDriverInfo(int,ushort *,ushort *)
0x18000e605  jmp     short loc_18000E60A
0x18000e607  xor     r15d, r15d
0x18000e60a  mov     rcx, [rbp+4Fh+var_C0]
0x18000e60e  test    rcx, rcx
0x18000e611  jz      short loc_18000E61F
0x18000e613  mov     rax, [rcx]
0x18000e616  mov     rax, [rax+10h]
0x18000e61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61f  mov     [rbp+4Fh+var_C0], r15
0x18000e623  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000e627  call    cs:__imp_VariantClear
0x18000e62d  nop
0x18000e62e  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x18000e632  call    cs:__imp_VariantClear
0x18000e638  mov     r14, [rbp+4Fh+arg_8]
0x18000e63c  jmp     loc_18000E3EA
0x18000e641  mov     rcx, [rbp+4Fh+var_C0]
0x18000e645  test    rcx, rcx
0x18000e648  jz      short loc_18000E656
0x18000e64a  mov     rax, [rcx]
0x18000e64d  mov     rax, [rax+10h]
0x18000e651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e656  mov     [rbp+4Fh+var_C0], r15
0x18000e65a  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x18000e65e  call    cs:__imp_VariantClear
0x18000e664  jmp     short loc_18000E67F
0x18000e666  mov     rcx, [rbp+4Fh+var_C0]
0x18000e66a  test    rcx, rcx
0x18000e66d  jz      short loc_18000E67B
0x18000e66f  mov     rax, [rcx]
0x18000e672  mov     rax, [rax+10h]
0x18000e676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e67b  mov     [rbp+4Fh+var_C0], r15
0x18000e67f  mov     rcx, [rbp+4Fh+var_A8]
0x18000e683  test    rcx, rcx
0x18000e686  jz      short loc_18000E694
0x18000e688  mov     rax, [rcx]
0x18000e68b  mov     rax, [rax+10h]
0x18000e68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e694  mov     [rbp+4Fh+var_A8], r15
0x18000e698  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18000e69c  call    cs:__imp_VariantClear
0x18000e6a2  cmp     ebx, 40005h
0x18000e6a8  jz      short loc_18000E6B2
0x18000e6aa  mov     edi, r15d
0x18000e6ad  cmp     ebx, 1
0x18000e6b0  jnz     short loc_18000E6B7
0x18000e6b2  mov     edi, 1
0x18000e6b7  lea     rcx, [rbp+4Fh+var_68]; this
0x18000e6bb  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x18000e6c0  mov     eax, edi
0x18000e6c2  add     rsp, 0C8h
0x18000e6c9  pop     r15
  ... truncated ...
```
