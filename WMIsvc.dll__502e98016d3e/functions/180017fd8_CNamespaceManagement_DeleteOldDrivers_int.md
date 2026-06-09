# CNamespaceManagement::DeleteOldDrivers(int)

- ea: `0x180017fd8`
- end: `0x1800183b0`
- name: `?DeleteOldDrivers@CNamespaceManagement@@QEAAHH@Z`
- size: `984`
- prototype: `__int64 __fastcall(CNamespaceManagement *__hidden this, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180017e3c`

## callees

- `0x180003e10`
- `0x18000b670`
- `0x18000ce8c`
- `0x18000d904`
- `0x18000dc88`
- `0x18000e230`
- `0x180017434`
- `0x180017dc8`
- `0x180017fd8`
- `0x180018ed8`
- `0x180020010`

## import_xrefs

- `wbemcomn!DebugTrace` at `0x180018163`
- `wbemcomn!DebugTrace` at `0x180018172`
- `wbemcomn!DebugTrace` at `0x180018262`
- `wbemcomn!DebugTrace` at `0x180018163`
- `wbemcomn!DebugTrace` at `0x180018172`
- `wbemcomn!DebugTrace` at `0x180018262`
- `wbemcomn!ErrorTrace` at `0x180018234`
- `wbemcomn!ErrorTrace` at `0x18001825a`
- `wbemcomn!ErrorTrace` at `0x1800182ad`
- `wbemcomn!ErrorTrace` at `0x18001836c`
- `wbemcomn!ErrorTrace` at `0x18001837b`
- `wbemcomn!ErrorTrace` at `0x180018234`
- `wbemcomn!ErrorTrace` at `0x18001825a`
- `wbemcomn!ErrorTrace` at `0x1800182ad`
- `wbemcomn!ErrorTrace` at `0x18001836c`
- `wbemcomn!ErrorTrace` at `0x18001837b`
- `OLEAUT32!__imp_SysAllocString` at `0x180018002`
- `OLEAUT32!__imp_SysAllocString` at `0x180018002`
- `OLEAUT32!__imp_SysFreeString` at `0x180018066`
- `OLEAUT32!__imp_SysFreeString` at `0x180018066`
- `OLEAUT32!__imp_VariantInit` at `0x1800180a3`
- `OLEAUT32!__imp_VariantInit` at `0x18001810b`
- `OLEAUT32!__imp_VariantInit` at `0x180018116`
- `OLEAUT32!__imp_VariantInit` at `0x180018121`
- `OLEAUT32!__imp_VariantInit` at `0x1800181a6`
- `OLEAUT32!__imp_VariantInit` at `0x1800180a3`
- `OLEAUT32!__imp_VariantInit` at `0x18001810b`
- `OLEAUT32!__imp_VariantInit` at `0x180018116`
- `OLEAUT32!__imp_VariantInit` at `0x180018121`
- `OLEAUT32!__imp_VariantInit` at `0x1800181a6`
- `OLEAUT32!__imp_VariantClear` at `0x1800182b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800182c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800182ce`
- `OLEAUT32!__imp_VariantClear` at `0x1800182d9`
- `OLEAUT32!__imp_VariantClear` at `0x18001831a`
- `OLEAUT32!__imp_VariantClear` at `0x180018325`
- `OLEAUT32!__imp_VariantClear` at `0x180018330`
- `OLEAUT32!__imp_VariantClear` at `0x180018353`
- `OLEAUT32!__imp_VariantClear` at `0x1800182b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800182c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800182ce`
- `OLEAUT32!__imp_VariantClear` at `0x1800182d9`
- `OLEAUT32!__imp_VariantClear` at `0x18001831a`
- `OLEAUT32!__imp_VariantClear` at `0x180018325`
- `OLEAUT32!__imp_VariantClear` at `0x180018330`
- `OLEAUT32!__imp_VariantClear` at `0x180018353`

## string_xrefs

- `0x1800181c5`: `__RELPATH`
- `0x180018227`: `We have been requested to delete this instance:\n`
- `0x18001835e`: `Cannot delete driver. ExecQuery return value: 0x%08lx\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CNamespaceManagement::DeleteOldDrivers(const OLECHAR **this, int a2)
{
  OLECHAR *v3; // rdi
  unsigned int v4; // r14d
  int v5; // ebx
  int v6; // ebx
  unsigned __int16 *bstrVal; // rdx
  int v8; // eax
  OLECHAR *v9; // rdx
  const WCHAR *v10; // rcx
  const WCHAR *v11; // rcx
  CWMIBinMof *v12; // rcx
  const unsigned __int16 *v13; // rdx
  __int64 v15; // [rsp+40h] [rbp-69h] BYREF
  VARIANTARG v16; // [rsp+48h] [rbp-61h] BYREF
  VARIANTARG v17; // [rsp+60h] [rbp-49h] BYREF
  VARIANTARG v18; // [rsp+78h] [rbp-31h] BYREF
  VARIANTARG v19; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v20[24]; // [rsp+A8h] [rbp-1h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp+17h] BYREF
  struct IWbemClassObject *v22; // [rsp+110h] [rbp+67h] BYREF
  int v23; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v24; // [rsp+120h] [rbp+77h] BYREF

  v23 = a2;
  v15 = 0;
  v3 = SysAllocString(this[1]);
  if ( v3 )
  {
    v4 = 1;
    v22 = 0;
    CBSTR::SetStr((CBSTR *)&v22, (OLECHAR *)L"WQL");
    v5 = (*(__int64 (__fastcall **)(_QWORD, struct IWbemClassObject *, OLECHAR *, __int64, _QWORD, __int64 *))(**(_QWORD **)(*((_QWORD *)this[8] + 3) + 16LL) + 160LL))(
           *(_QWORD *)(*((_QWORD *)this[8] + 3) + 16LL),
           v22,
           v3,
           48,
           *(_QWORD *)(*((_QWORD *)this[8] + 3) + 24LL),
           &v15);
    SysFreeString(v3);
    CBSTR::Clear((CBSTR *)&v22);
  }
  else
  {
    v5 = -2147024882;
    v4 = 0;
  }
  CFilterIgnoreSet::CFilterIgnoreSet((CFilterIgnoreSet *)v20);
  CFilterIgnoreSet::MoveValueFrom((CFilterIgnoreSet *)v20, (struct CFilterIgnoreSet *)(this + 2));
  if ( v5 )
  {
    ErrorTrace(10, "Cannot delete driver. ExecQuery return value: 0x%08lx\n", v5);
    ErrorTrace(10, "Current query: \n");
    TranslateAndLog(this[1], 0);
  }
  else
  {
    VariantInit(&pvarg);
    v6 = 0;
    while ( !v6 )
    {
      v22 = 0;
      v23 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, struct IWbemClassObject **, int *))(*(_QWORD *)v15 + 32LL))(
             v15,
             2000,
             1,
             &v22,
             &v23);
      if ( !v6 && !CFilterIgnoreSet::IsIgnored((CFilterIgnoreSet *)v20, v22) )
      {
        VariantInit(&v19);
        VariantInit(&v18);
        VariantInit(&v17);
        v6 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v22->lpVtbl->Get)(
               v22,
               L"Name",
               0,
               &v17,
               0,
               0);
        if ( v6 )
        {
          if ( v22 )
            ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
          v22 = 0;
          VariantClear(&v17);
          VariantClear(&v18);
          VariantClear(&v19);
          break;
        }
        DebugTrace(10, "Deleting Old Drivers\n");
        DebugTrace(10, "***************************************\n");
        bstrVal = 0;
        if ( v17.vt == 8 )
          bstrVal = v17.bstrVal;
        if ( (unsigned int)CNamespaceManagement::DeleteOldClasses(
                             (CNamespaceManagement *)this,
                             bstrVal,
                             (struct CVARIANT *)&v19,
                             (struct CVARIANT *)&v18,
                             0) )
        {
          VariantInit(&v16);
          v8 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v22->lpVtbl->Get)(
                 v22,
                 L"__RELPATH",
                 0,
                 &v16,
                 0,
                 0);
          v6 = v8;
          if ( v8 )
          {
            ErrorTrace(10, "Get returned value: 0x%08lx\n", v8);
          }
          else
          {
            v9 = 0;
            if ( v16.vt == 8 )
              v9 = v16.bstrVal;
            v24 = 0;
            CBSTR::SetStr((CBSTR *)&v24, v9);
            v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this[8] + 3)
                                                                                                  + 16LL)
                                                                                    + 128LL))(
                   *(_QWORD *)(*((_QWORD *)this[8] + 3) + 16LL),
                   v24,
                   0,
                   *(_QWORD *)(*((_QWORD *)this[8] + 3) + 24LL),
                   0);
            if ( v6 >= 0 )
            {
              DebugTrace(10, "We have been requested to delete this instance:\n");
              v11 = 0;
              if ( v16.vt == 8 )
                v11 = v16.bstrVal;
              TranslateAndLog(v11, 1);
              if ( !v6 )
              {
                v13 = 0;
                if ( v17.vt == 8 )
                  v13 = v17.bstrVal;
                CWMIBinMof::DeleteMofFromRegistry(v12, v13);
              }
            }
            else
            {
              ErrorTrace(10, "We have been requested to delete this instance:\n");
              v10 = 0;
              if ( v16.vt == 8 )
                v10 = v16.bstrVal;
              TranslateAndLog(v10, 0);
              ErrorTrace(10, "It failed with 0x%08lx\n", v6);
            }
            CBSTR::Clear((CBSTR *)&v24);
          }
          VariantClear(&v16);
        }
        VariantClear(&v17);
        VariantClear(&v18);
        VariantClear(&v19);
      }
      if ( v22 )
        ((void (__fastcall *)(struct IWbemClassObject *))v22->lpVtbl->Release)(v22);
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
    VariantClear(&pvarg);
  }
  CFilterIgnoreSet::~CFilterIgnoreSet((CFilterIgnoreSet *)v20);
  return v4;
}

```

## disassembly

```asm
0x180017fd8  mov     [rsp-8+arg_18], rbx
0x180017fdd  mov     [rsp-8+arg_8], edx
0x180017fe1  push    rbp
0x180017fe2  push    rsi
0x180017fe3  push    rdi
0x180017fe4  push    r14
0x180017fe6  push    r15
0x180017fe8  lea     rbp, [rsp-37h]
0x180017fed  sub     rsp, 0E0h
0x180017ff4  mov     rsi, rcx
0x180017ff7  xor     r15d, r15d
0x180017ffa  mov     [rbp+57h+var_C0], r15
0x180017ffe  mov     rcx, [rcx+8]; psz
0x180018002  call    cs:__imp_SysAllocString
0x180018008  mov     rdi, rax
0x18001800b  test    rax, rax
0x18001800e  jz      short loc_180018078
0x180018010  lea     r14d, [r15+1]
0x180018014  mov     [rbp+57h+arg_0], r15
0x180018018  lea     rdx, aWql; "WQL"
0x18001801f  lea     rcx, [rbp+57h+arg_0]; this
0x180018023  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x180018028  nop
0x180018029  mov     rcx, [rsi+40h]
0x18001802d  mov     rdx, [rcx+18h]
0x180018031  mov     rcx, [rdx+10h]
0x180018035  mov     rax, [rcx]
0x180018038  lea     r8, [rbp+57h+var_C0]
0x18001803c  mov     [rsp+100h+var_D8], r8
0x180018041  mov     rdx, [rdx+18h]
0x180018045  mov     qword ptr [rsp+100h+var_E0], rdx
0x18001804a  lea     r9d, [r15+30h]
0x18001804e  mov     r8, rdi
0x180018051  mov     rdx, [rbp+57h+arg_0]
0x180018055  mov     rax, [rax+0A0h]
0x18001805c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018061  mov     ebx, eax
0x180018063  mov     rcx, rdi; bstrString
0x180018066  call    cs:__imp_SysFreeString
0x18001806c  nop
0x18001806d  lea     rcx, [rbp+57h+arg_0]; this
0x180018071  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x180018076  jmp     short loc_180018080
0x180018078  mov     ebx, 8007000Eh
0x18001807d  mov     r14d, r15d
0x180018080  lea     rcx, [rbp+57h+var_58]; this
0x180018084  call    ??0CFilterIgnoreSet@@QEAA@XZ; CFilterIgnoreSet::CFilterIgnoreSet(void)
0x180018089  nop
0x18001808a  lea     rdx, [rsi+10h]; struct CFilterIgnoreSet *
0x18001808e  lea     rcx, [rbp+57h+var_58]; this
0x180018092  call    ?MoveValueFrom@CFilterIgnoreSet@@QEAAJAEAV1@@Z; CFilterIgnoreSet::MoveValueFrom(CFilterIgnoreSet &)
0x180018097  test    ebx, ebx
0x180018099  jnz     loc_18001835B
0x18001809f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800180a3  call    cs:__imp_VariantInit
0x1800180a9  nop
0x1800180aa  mov     ebx, r15d
0x1800180ad  mov     edi, 0Ah
0x1800180b2  test    ebx, ebx
0x1800180b4  jnz     loc_180018336
0x1800180ba  mov     [rbp+57h+arg_0], r15
0x1800180be  mov     [rbp+57h+arg_8], r15d
0x1800180c2  mov     rcx, [rbp+57h+var_C0]
0x1800180c6  mov     rax, [rcx]
0x1800180c9  lea     rdx, [rbp+57h+arg_8]
0x1800180cd  mov     qword ptr [rsp+100h+var_E0], rdx
0x1800180d2  lea     r9, [rbp+57h+arg_0]
0x1800180d6  mov     edx, 7D0h
0x1800180db  lea     r8d, [rbx+1]
0x1800180df  mov     rax, [rax+20h]
0x1800180e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180e8  mov     ebx, eax
0x1800180ea  test    eax, eax
0x1800180ec  jnz     loc_1800182DF
0x1800180f2  mov     rdx, [rbp+57h+arg_0]; struct IWbemClassObject *
0x1800180f6  lea     rcx, [rbp+57h+var_58]; this
0x1800180fa  call    ?IsIgnored@CFilterIgnoreSet@@QEAA_NPEAUIWbemClassObject@@@Z; CFilterIgnoreSet::IsIgnored(IWbemClassObject *)
0x1800180ff  test    al, al
0x180018101  jnz     loc_1800182DF
0x180018107  lea     rcx, [rbp+57h+var_70]; pvarg
0x18001810b  call    cs:__imp_VariantInit
0x180018111  nop
0x180018112  lea     rcx, [rbp+57h+var_88]; pvarg
0x180018116  call    cs:__imp_VariantInit
0x18001811c  nop
0x18001811d  lea     rcx, [rbp+57h+var_A0]; pvarg
0x180018121  call    cs:__imp_VariantInit
0x180018127  nop
0x180018128  mov     rcx, [rbp+57h+arg_0]
0x18001812c  mov     rax, [rcx]
0x18001812f  mov     [rsp+100h+var_D8], r15
0x180018134  mov     qword ptr [rsp+100h+var_E0], r15
0x180018139  lea     r9, [rbp+57h+var_A0]
0x18001813d  xor     r8d, r8d
0x180018140  lea     rdx, aName; "Name"
0x180018147  mov     rax, [rax+20h]
0x18001814b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018150  mov     ebx, eax
0x180018152  test    eax, eax
0x180018154  jnz     loc_1800182FD
0x18001815a  lea     rdx, aDeletingOldDri; "Deleting Old Drivers\n"
0x180018161  mov     ecx, edi
0x180018163  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x180018169  lea     rdx, asc_180023540; "***************************************"...
0x180018170  mov     ecx, edi
0x180018172  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x180018178  mov     rdx, r15
0x18001817b  cmp     word ptr [rbp+57h+var_A0], 8
0x180018180  cmovz   rdx, qword ptr [rbp+57h+var_A0+8]; unsigned __int16 *
0x180018185  mov     [rsp+100h+var_E0], r15d; int
0x18001818a  lea     r9, [rbp+57h+var_88]; struct CVARIANT *
0x18001818e  lea     r8, [rbp+57h+var_70]; struct CVARIANT *
0x180018192  mov     rcx, rsi; this
0x180018195  call    ?DeleteOldClasses@CNamespaceManagement@@QEAAHPEAGAEAVCVARIANT@@1H@Z; CNamespaceManagement::DeleteOldClasses(ushort *,CVARIANT &,CVARIANT &,int)
0x18001819a  test    eax, eax
0x18001819c  jz      loc_1800182BF
0x1800181a2  lea     rcx, [rbp+57h+var_B8]; pvarg
0x1800181a6  call    cs:__imp_VariantInit
0x1800181ac  nop
0x1800181ad  mov     rcx, [rbp+57h+arg_0]
0x1800181b1  mov     rax, [rcx]
0x1800181b4  mov     [rsp+100h+var_D8], r15
0x1800181b9  mov     qword ptr [rsp+100h+var_E0], r15
0x1800181be  lea     r9, [rbp+57h+var_B8]
0x1800181c2  xor     r8d, r8d
0x1800181c5  lea     rdx, aRelpath; "__RELPATH"
0x1800181cc  mov     rax, [rax+20h]
0x1800181d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181d5  mov     ebx, eax
0x1800181d7  test    eax, eax
0x1800181d9  jnz     loc_1800182A1
0x1800181df  mov     rdx, r15
0x1800181e2  cmp     word ptr [rbp+57h+var_B8], 8
0x1800181e7  cmovz   rdx, qword ptr [rbp+57h+var_B8+8]; psz
0x1800181ec  mov     [rbp+57h+arg_10], r15
0x1800181f0  lea     rcx, [rbp+57h+arg_10]; this
0x1800181f4  call    ?SetStr@CBSTR@@QEAAXPEAG@Z; CBSTR::SetStr(ushort *)
0x1800181f9  nop
0x1800181fa  mov     rax, [rsi+40h]
0x1800181fe  mov     r9, [rax+18h]
0x180018202  mov     rcx, [r9+10h]
0x180018206  mov     rax, [rcx]
0x180018209  mov     qword ptr [rsp+100h+var_E0], r15
0x18001820e  mov     r9, [r9+18h]
0x180018212  xor     r8d, r8d
0x180018215  mov     rdx, [rbp+57h+arg_10]
0x180018219  mov     rax, [rax+80h]
0x180018220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018225  mov     ebx, eax
0x180018227  lea     rdx, aWeHaveBeenRequ; "We have been requested to delete this i"...
0x18001822e  mov     ecx, edi
0x180018230  test    eax, eax
0x180018232  jns     short loc_180018262
0x180018234  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18001823a  mov     rcx, r15
0x18001823d  cmp     word ptr [rbp+57h+var_B8], 8
0x180018242  cmovz   rcx, qword ptr [rbp+57h+var_B8+8]; lpWideCharStr
0x180018247  xor     edx, edx; int
0x180018249  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x18001824e  mov     r8d, ebx
0x180018251  lea     rdx, aItFailedWith0x; "It failed with 0x%08lx\n"
0x180018258  mov     ecx, edi
0x18001825a  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180018260  jmp     short loc_180018296
0x180018262  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x180018268  mov     rcx, r15
0x18001826b  cmp     word ptr [rbp+57h+var_B8], 8
0x180018270  cmovz   rcx, qword ptr [rbp+57h+var_B8+8]; lpWideCharStr
0x180018275  mov     edx, 1; int
0x18001827a  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x18001827f  test    ebx, ebx
0x180018281  jnz     short loc_180018296
0x180018283  mov     rdx, r15
0x180018286  cmp     word ptr [rbp+57h+var_A0], 8
0x18001828b  cmovz   rdx, qword ptr [rbp+57h+var_A0+8]; unsigned __int16 *
0x180018290  call    ?DeleteMofFromRegistry@CWMIBinMof@@QEAAJPEBG@Z; CWMIBinMof::DeleteMofFromRegistry(ushort const *)
0x180018295  nop
0x180018296  lea     rcx, [rbp+57h+arg_10]; this
0x18001829a  call    ?Clear@CBSTR@@QEAAXXZ; CBSTR::Clear(void)
0x18001829f  jmp     short loc_1800182B4
0x1800182a1  mov     r8d, eax
0x1800182a4  lea     rdx, aGetReturnedVal; "Get returned value: 0x%08lx\n"
0x1800182ab  mov     ecx, edi
0x1800182ad  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800182b3  nop
0x1800182b4  lea     rcx, [rbp+57h+var_B8]; pvarg
0x1800182b8  call    cs:__imp_VariantClear
0x1800182be  nop
0x1800182bf  lea     rcx, [rbp+57h+var_A0]; pvarg
0x1800182c3  call    cs:__imp_VariantClear
0x1800182c9  nop
0x1800182ca  lea     rcx, [rbp+57h+var_88]; pvarg
0x1800182ce  call    cs:__imp_VariantClear
0x1800182d4  nop
0x1800182d5  lea     rcx, [rbp+57h+var_70]; pvarg
0x1800182d9  call    cs:__imp_VariantClear
0x1800182df  mov     rcx, [rbp+57h+arg_0]
0x1800182e3  test    rcx, rcx
0x1800182e6  jz      loc_1800180B2
0x1800182ec  mov     rax, [rcx]
0x1800182ef  mov     rax, [rax+10h]
0x1800182f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182f8  jmp     loc_1800180B2
0x1800182fd  mov     rcx, [rbp+57h+arg_0]
0x180018301  test    rcx, rcx
0x180018304  jz      short loc_180018312
0x180018306  mov     rax, [rcx]
0x180018309  mov     rax, [rax+10h]
0x18001830d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018312  mov     [rbp+57h+arg_0], r15
0x180018316  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18001831a  call    cs:__imp_VariantClear
0x180018320  nop
0x180018321  lea     rcx, [rbp+57h+var_88]; pvarg
0x180018325  call    cs:__imp_VariantClear
0x18001832b  nop
0x18001832c  lea     rcx, [rbp+57h+var_70]; pvarg
0x180018330  call    cs:__imp_VariantClear
0x180018336  mov     rcx, [rbp+57h+var_C0]
0x18001833a  test    rcx, rcx
0x18001833d  jz      short loc_18001834B
0x18001833f  mov     rax, [rcx]
0x180018342  mov     rax, [rax+10h]
0x180018346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001834b  mov     [rbp+57h+var_C0], r15
0x18001834f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180018353  call    cs:__imp_VariantClear
0x180018359  jmp     short loc_18001838D
0x18001835b  mov     r8d, ebx
0x18001835e  lea     rdx, aCannotDeleteDr; "Cannot delete driver. ExecQuery return "...
0x180018365  mov     edi, 0Ah
0x18001836a  mov     ecx, edi
0x18001836c  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180018372  lea     rdx, aCurrentQuery; "Current query: \n"
0x180018379  mov     ecx, edi
0x18001837b  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x180018381  xor     edx, edx; int
0x180018383  mov     rcx, [rsi+8]; lpWideCharStr
0x180018387  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x18001838c  nop
0x18001838d  lea     rcx, [rbp+57h+var_58]; this
0x180018391  call    ??1CFilterIgnoreSet@@QEAA@XZ; CFilterIgnoreSet::~CFilterIgnoreSet(void)
0x180018396  mov     eax, r14d
0x180018399  mov     rbx, [rsp+100h+arg_18]
0x1800183a1  add     rsp, 0E0h
0x1800183a8  pop     r15
0x1800183aa  pop     r14
0x1800183ac  pop     rdi
0x1800183ad  pop     rsi
0x1800183ae  pop     rbp
0x1800183af  retn
```
