# Registrar::RegisterComClass(Registrar::ClassInfo const &,Registrar::ServerKind,ushort const *,ushort const *)

- ea: `0x180040628`
- end: `0x180040901`
- name: `?RegisterComClass@Registrar@@CAJAEBUClassInfo@1@W4ServerKind@1@PEBG2@Z`
- size: `729`
- prototype: `static int __high(const struct Registrar::ClassInfo *, enum Registrar::ServerKind, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180040908`

## callees

- `0x180006194`
- `0x1800404ec`
- `0x18004050c`
- `0x1800405dc`
- `0x180040628`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040682`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800408cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800408cb`

## string_xrefs

- `0x180040697`: `Software\Classes\CLSID\%s`
- `0x180040739`: `ThreadingModel`
- `0x1800407da`: `CLSID`
- `0x18004087e`: `CLSID`

## pseudocode

```c
__int64 __fastcall Registrar::RegisterComClass(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const IID *v5; // rcx
  HRESULT NamedValue; // edi
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // r8
  __int64 v11; // r9
  const unsigned __int16 *v12; // r8
  __int64 v13; // r9
  HKEY v15; // [rsp+20h] [rbp-E0h] BYREF
  HKEY v16; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v19[72]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v20[72]; // [rsp+D0h] [rbp-30h] BYREF

  lpsz = 0;
  v5 = *(const IID **)(a1 + 8);
  v16 = 0;
  if ( !v5 )
  {
    NamedValue = -2147418113;
    goto LABEL_25;
  }
  NamedValue = StringFromCLSID(v5, &lpsz);
  if ( NamedValue < 0 )
    goto LABEL_25;
  NamedValue = StringCchPrintfW(v20, 0x42u, L"Software\\Classes\\CLSID\\%s", lpsz);
  if ( NamedValue < 0 )
    goto LABEL_25;
  NamedValue = CreateKey(HKEY_LOCAL_MACHINE, v20, *(const unsigned __int16 **)(a1 + 16), &v16);
  if ( NamedValue < 0 )
    goto LABEL_25;
  if ( a4 )
  {
    NamedValue = CreateNamedValue(v16, L"AppID", a4);
    if ( NamedValue < 0 )
      goto LABEL_25;
  }
  v15 = 0;
  NamedValue = CreateKey(v16, L"InprocServer32", a3, &v15);
  if ( NamedValue < 0 )
    goto LABEL_24;
  v9 = *(const unsigned __int16 **)(a1 + 40);
  if ( v9 )
  {
    NamedValue = CreateNamedValue(v15, L"ThreadingModel", v9);
    if ( NamedValue < 0 )
      goto LABEL_24;
  }
  AutoCloseHKEY::~AutoCloseHKEY((AutoCloseHKEY *)&v15);
  v10 = *(const unsigned __int16 **)(a1 + 24);
  if ( v10 )
  {
    NamedValue = CreateKey(v16, L"ProgID", v10, 0);
    if ( NamedValue < 0 )
      goto LABEL_25;
    v11 = *(_QWORD *)(a1 + 24);
    v15 = 0;
    NamedValue = StringCchPrintfW(v19, 0x45u, L"Software\\Classes\\%s", v11);
    if ( NamedValue >= 0 )
    {
      NamedValue = CreateKey(HKEY_LOCAL_MACHINE, v19, *(const unsigned __int16 **)(a1 + 16), &v15);
      if ( NamedValue >= 0 )
      {
        NamedValue = CreateKey(v15, L"CLSID", lpsz, 0);
        if ( NamedValue >= 0 )
        {
          AutoCloseHKEY::~AutoCloseHKEY((AutoCloseHKEY *)&v15);
          goto LABEL_17;
        }
      }
    }
LABEL_24:
    AutoCloseHKEY::~AutoCloseHKEY((AutoCloseHKEY *)&v15);
    goto LABEL_25;
  }
LABEL_17:
  v12 = *(const unsigned __int16 **)(a1 + 32);
  if ( v12 )
  {
    NamedValue = CreateKey(v16, L"VersionIndependentProgID", v12, 0);
    if ( NamedValue >= 0 )
    {
      v13 = *(_QWORD *)(a1 + 32);
      v15 = 0;
      v17 = 0;
      NamedValue = StringCchPrintfW(v19, 0x45u, L"Software\\Classes\\%s", v13);
      if ( NamedValue >= 0 )
      {
        NamedValue = CreateKey(HKEY_LOCAL_MACHINE, v19, *(const unsigned __int16 **)(a1 + 16), &v15);
        if ( NamedValue >= 0 )
        {
          NamedValue = CreateKey(v15, L"CLSID", lpsz, 0);
          if ( NamedValue >= 0 )
            NamedValue = CreateKey(v15, L"CurVer", *(const unsigned __int16 **)(a1 + 24), 0);
        }
      }
      AutoCloseHKEY::~AutoCloseHKEY((AutoCloseHKEY *)&v17);
      goto LABEL_24;
    }
  }
LABEL_25:
  CoTaskMemFree(lpsz);
  AutoCloseHKEY::~AutoCloseHKEY((AutoCloseHKEY *)&v16);
  return (unsigned int)NamedValue;
}

```

## disassembly

```asm
0x180040628  mov     [rsp-8+arg_8], rsi
0x18004062d  push    rbp
0x18004062e  push    rdi
0x18004062f  push    r13
0x180040631  push    r14
0x180040633  push    r15
0x180040635  lea     rbp, [rsp-70h]
0x18004063a  sub     rsp, 170h
0x180040641  mov     rax, cs:__security_cookie
0x180040648  xor     rax, rsp
0x18004064b  mov     [rbp+90h+var_30], rax
0x18004064f  mov     rsi, rcx
0x180040652  mov     [rsp+190h+lpsz], 0
0x18004065b  mov     rcx, [rcx+8]; rclsid
0x18004065f  mov     r14, r9
0x180040662  mov     [rsp+190h+var_168], 0
0x18004066b  mov     r15, r8
0x18004066e  test    rcx, rcx
0x180040671  jnz     short loc_18004067D
0x180040673  mov     edi, 8000FFFFh
0x180040678  jmp     loc_1800408C6
0x18004067d  lea     rdx, [rsp+190h+lpsz]; lplpsz
0x180040682  call    cs:__imp_StringFromCLSID
0x180040688  mov     edi, eax
0x18004068a  test    eax, eax
0x18004068c  js      loc_1800408C6
0x180040692  mov     r9, [rsp+190h+lpsz]
0x180040697  lea     r8, aSoftwareClasse_0; "Software\\Classes\\CLSID\\%s"
0x18004069e  mov     edx, 42h ; 'B'; unsigned __int64
0x1800406a3  lea     rcx, [rbp+90h+var_C0]; unsigned __int16 *
0x1800406a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800406ac  mov     edi, eax
0x1800406ae  test    eax, eax
0x1800406b0  js      loc_1800408C6
0x1800406b6  mov     r8, [rsi+10h]; unsigned __int16 *
0x1800406ba  lea     r9, [rsp+190h+var_168]; HKEY *
0x1800406bf  mov     r13, 0FFFFFFFF80000002h
0x1800406c6  lea     rdx, [rbp+90h+var_C0]; unsigned __int16 *
0x1800406ca  mov     rcx, r13; HKEY
0x1800406cd  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x1800406d2  mov     edi, eax
0x1800406d4  test    eax, eax
0x1800406d6  js      loc_1800408C6
0x1800406dc  test    r14, r14
0x1800406df  jz      short loc_1800406FF
0x1800406e1  mov     rcx, [rsp+190h+var_168]; HKEY
0x1800406e6  lea     rdx, aAppid; "AppID"
0x1800406ed  mov     r8, r14; unsigned __int16 *
0x1800406f0  call    ?CreateNamedValue@@YAJPEAUHKEY__@@PEBG1@Z; CreateNamedValue(HKEY__ *,ushort const *,ushort const *)
0x1800406f5  mov     edi, eax
0x1800406f7  test    eax, eax
0x1800406f9  js      loc_1800408C6
0x1800406ff  mov     rcx, [rsp+190h+var_168]; HKEY
0x180040704  lea     r9, [rsp+190h+var_170]; HKEY *
0x180040709  mov     r8, r15; unsigned __int16 *
0x18004070c  mov     [rsp+190h+var_170], 0
0x180040715  lea     rdx, aInprocserver32; "InprocServer32"
0x18004071c  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x180040721  mov     edi, eax
0x180040723  test    eax, eax
0x180040725  js      loc_1800408BC
0x18004072b  mov     r8, [rsi+28h]; unsigned __int16 *
0x18004072f  test    r8, r8
0x180040732  jz      short loc_18004074F
0x180040734  mov     rcx, [rsp+190h+var_170]; HKEY
0x180040739  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180040740  call    ?CreateNamedValue@@YAJPEAUHKEY__@@PEBG1@Z; CreateNamedValue(HKEY__ *,ushort const *,ushort const *)
0x180040745  mov     edi, eax
0x180040747  test    eax, eax
0x180040749  js      loc_1800408BC
0x18004074f  lea     rcx, [rsp+190h+var_170]; this
0x180040754  call    ??1AutoCloseHKEY@@QEAA@XZ; AutoCloseHKEY::~AutoCloseHKEY(void)
0x180040759  mov     r8, [rsi+18h]; unsigned __int16 *
0x18004075d  mov     r14d, 45h ; 'E'
0x180040763  test    r8, r8
0x180040766  jz      loc_180040802
0x18004076c  mov     rcx, [rsp+190h+var_168]; HKEY
0x180040771  lea     rdx, aProgid; "ProgID"
0x180040778  xor     r9d, r9d; HKEY *
0x18004077b  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x180040780  mov     edi, eax
0x180040782  test    eax, eax
0x180040784  js      loc_1800408C6
0x18004078a  mov     r9, [rsi+18h]
0x18004078e  lea     r8, aSoftwareClasse_1; "Software\\Classes\\%s"
0x180040795  mov     edx, r14d; unsigned __int64
0x180040798  mov     [rsp+190h+var_170], 0
0x1800407a1  lea     rcx, [rsp+190h+var_150]; unsigned __int16 *
0x1800407a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800407ab  mov     edi, eax
0x1800407ad  test    eax, eax
0x1800407af  js      loc_1800408BC
0x1800407b5  mov     r8, [rsi+10h]; unsigned __int16 *
0x1800407b9  lea     r9, [rsp+190h+var_170]; HKEY *
0x1800407be  lea     rdx, [rsp+190h+var_150]; unsigned __int16 *
0x1800407c3  mov     rcx, r13; HKEY
0x1800407c6  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x1800407cb  mov     edi, eax
0x1800407cd  test    eax, eax
0x1800407cf  js      loc_1800408BC
0x1800407d5  mov     r8, [rsp+190h+lpsz]; unsigned __int16 *
0x1800407da  lea     rdx, aClsid; "CLSID"
0x1800407e1  mov     rcx, [rsp+190h+var_170]; HKEY
0x1800407e6  xor     r9d, r9d; HKEY *
0x1800407e9  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x1800407ee  lea     rcx, [rsp+190h+var_170]; this
0x1800407f3  mov     edi, eax
0x1800407f5  test    eax, eax
0x1800407f7  js      loc_1800408C1
0x1800407fd  call    ??1AutoCloseHKEY@@QEAA@XZ; AutoCloseHKEY::~AutoCloseHKEY(void)
0x180040802  mov     r8, [rsi+20h]; unsigned __int16 *
0x180040806  test    r8, r8
0x180040809  jz      loc_1800408C6
0x18004080f  mov     rcx, [rsp+190h+var_168]; HKEY
0x180040814  lea     rdx, aVersionindepen; "VersionIndependentProgID"
0x18004081b  xor     r9d, r9d; HKEY *
0x18004081e  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x180040823  mov     edi, eax
0x180040825  test    eax, eax
0x180040827  js      loc_1800408C6
0x18004082d  mov     r9, [rsi+20h]
0x180040831  lea     r8, aSoftwareClasse_1; "Software\\Classes\\%s"
0x180040838  mov     rdx, r14; unsigned __int64
0x18004083b  mov     [rsp+190h+var_170], 0
0x180040844  lea     rcx, [rsp+190h+var_150]; unsigned __int16 *
0x180040849  mov     [rsp+190h+var_160], 0
0x180040852  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040857  mov     edi, eax
0x180040859  test    eax, eax
0x18004085b  js      short loc_1800408B2
0x18004085d  mov     r8, [rsi+10h]; unsigned __int16 *
0x180040861  lea     r9, [rsp+190h+var_170]; HKEY *
0x180040866  lea     rdx, [rsp+190h+var_150]; unsigned __int16 *
0x18004086b  mov     rcx, r13; HKEY
0x18004086e  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x180040873  mov     edi, eax
0x180040875  test    eax, eax
0x180040877  js      short loc_1800408B2
0x180040879  mov     r8, [rsp+190h+lpsz]; unsigned __int16 *
0x18004087e  lea     rdx, aClsid; "CLSID"
0x180040885  mov     rcx, [rsp+190h+var_170]; HKEY
0x18004088a  xor     r9d, r9d; HKEY *
0x18004088d  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x180040892  mov     edi, eax
0x180040894  test    eax, eax
0x180040896  js      short loc_1800408B2
0x180040898  mov     r8, [rsi+18h]; unsigned __int16 *
0x18004089c  lea     rdx, aCurver; "CurVer"
0x1800408a3  mov     rcx, [rsp+190h+var_170]; HKEY
0x1800408a8  xor     r9d, r9d; HKEY *
0x1800408ab  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x1800408b0  mov     edi, eax
0x1800408b2  lea     rcx, [rsp+190h+var_160]; this
0x1800408b7  call    ??1AutoCloseHKEY@@QEAA@XZ; AutoCloseHKEY::~AutoCloseHKEY(void)
0x1800408bc  lea     rcx, [rsp+190h+var_170]; this
0x1800408c1  call    ??1AutoCloseHKEY@@QEAA@XZ; AutoCloseHKEY::~AutoCloseHKEY(void)
0x1800408c6  mov     rcx, [rsp+190h+lpsz]; pv
0x1800408cb  call    cs:__imp_CoTaskMemFree
0x1800408d1  lea     rcx, [rsp+190h+var_168]; this
0x1800408d6  call    ??1AutoCloseHKEY@@QEAA@XZ; AutoCloseHKEY::~AutoCloseHKEY(void)
0x1800408db  mov     eax, edi
0x1800408dd  mov     rcx, [rbp+90h+var_30]
0x1800408e1  xor     rcx, rsp; StackCookie
0x1800408e4  call    __security_check_cookie
0x1800408e9  mov     rsi, [rsp+190h+arg_8]
0x1800408f1  add     rsp, 170h
0x1800408f8  pop     r15
0x1800408fa  pop     r14
0x1800408fc  pop     r13
0x1800408fe  pop     rdi
0x1800408ff  pop     rbp
0x180040900  retn
```
