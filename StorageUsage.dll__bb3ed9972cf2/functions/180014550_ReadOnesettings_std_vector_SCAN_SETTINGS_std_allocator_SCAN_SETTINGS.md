# ReadOnesettings(std::vector<SCAN_SETTINGS,std::allocator<SCAN_SETTINGS>> &)

- ea: `0x180014550`
- end: `0x18001498c`
- name: `?ReadOnesettings@@YAJAEAV?$vector@USCAN_SETTINGS@@V?$allocator@USCAN_SETTINGS@@@std@@@std@@@Z`
- size: `1084`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012340`

## callees

- `0x1800050f0`
- `0x18000ebbc`
- `0x18000fab4`
- `0x18000fd08`
- `0x180010330`
- `0x180011438`
- `0x18001151c`
- `0x18001442c`
- `0x180014550`
- `0x180014994`
- `0x180014adc`
- `0x1800152d4`
- `0x180015e28`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800147db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800148e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800147db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800148e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800145e5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800145e5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180014920`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001495c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180014920`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001495c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180014584`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180014584`

## pseudocode

```c
__int64 __fastcall ReadOnesettings(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int ActivationFactory; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, double *); // rbx
  int v13; // eax
  int v14; // r15d
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, __int64 **); // rbx
  int v17; // eax
  int i; // r14d
  __int64 v19; // rax
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, __int64, HSTRING *); // rbx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  unsigned int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v30; // rcx
  HSTRING string; // [rsp+20h] [rbp-79h] BYREF
  __int64 v32; // [rsp+28h] [rbp-71h] BYREF
  __int64 v33; // [rsp+30h] [rbp-69h] BYREF
  __int64 *v34; // [rsp+38h] [rbp-61h] BYREF
  __int64 v35; // [rsp+40h] [rbp-59h] BYREF
  char v36; // [rsp+49h] [rbp-50h]
  double v37; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v38[8]; // [rsp+58h] [rbp-41h] BYREF
  int v39; // [rsp+60h] [rbp-39h] BYREF
  __int16 v40; // [rsp+64h] [rbp-35h]
  __int64 v41; // [rsp+68h] [rbp-31h]
  _BYTE v42[16]; // [rsp+78h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-11h] BYREF
  __int64 v44; // [rsp+A0h] [rbp+7h]
  HSTRING_HEADER v45; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v46; // [rsp+C0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = RoInitialize(1);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)(unsigned int)v2,
      (int)string);
    return v3;
  }
  v36 = 1;
  v35 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
    0x3Au,
    0x39u);
  ActivationFactory = RoGetActivationFactory(v44, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &v35);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)string);
LABEL_34:
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v35);
    RoUninitialize(v30);
    return v3;
  }
  v32 = 0;
  v5 = v35;
  v6 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v35 + 48LL);
  v32 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"STORAGEGROVELER", 0x10u, 0xFu);
  v7 = v6(v5, v44, &v32);
  v3 = v7;
  if ( v7 < 0 )
  {
    v8 = (unsigned int)v7;
    v9 = 312;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)v8,
      (int)string);
    goto LABEL_33;
  }
  v39 = -1;
  v40 = 256;
  v41 = 168;
  v33 = v32;
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
  v10 = ReadDefaultSharedScanSettings(&v33, &v39);
  v3 = v10;
  if ( v10 < 0 )
  {
    TracelogOnesettingsError(0xFFFFFFFFLL, 0, (unsigned int)v10);
LABEL_33:
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v32);
    goto LABEL_34;
  }
  v37 = 0.0;
  v11 = v32;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, double *))(*(_QWORD *)v32 + 80LL);
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ScanListLength", 0xFu, 0xEu);
  v13 = v12(v11, v44, &v37);
  v3 = v13;
  if ( v13 < 0 )
  {
    v8 = (unsigned int)v13;
    v9 = 323;
    goto LABEL_32;
  }
  v14 = (int)v37;
  if ( (unsigned int)((int)v37 - 1) > 0x12 )
  {
    v3 = -2147024872;
    v8 = 2147942424LL;
    v9 = 325;
    goto LABEL_32;
  }
  v34 = 0;
  v15 = v32;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)v32 + 64LL);
  v34 = 0;
  v44 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ScanList", 9u, 8u);
  v17 = v16(v15, v44, &v34);
  v3 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelertelemetry.cpp",
      (const char *)(unsigned int)v17,
      (int)string);
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v34);
    goto LABEL_33;
  }
  for ( i = 0; i < v14; ++i )
  {
    v33 = 0;
    v19 = *v34;
    v33 = 0;
    if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64 *))(v19 + 48))(v34, (unsigned int)i, &v33) >= 0 )
    {
      string = 0;
      v20 = v33;
      v21 = *(int (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v33 + 80LL);
      WindowsDeleteString(0);
      string = 0;
      v46 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v45, L"ScanName", 9u, 8u);
      if ( v21(v20, v46, &string) >= 0 )
      {
        LODWORD(hstringHeader.Reserved.Reserved1) = -1;
        *(_WORD *)&hstringHeader.Reserved.Reserved2[4] = 256;
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 168;
        LODWORD(hstringHeader.Reserved.Reserved1) = FindScanId(string);
        if ( LODWORD(hstringHeader.Reserved.Reserved1) != -1 )
        {
          v22 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
                  v42,
                  &v33);
          v23 = ReadSharedScanSettings(v22, &v39, &hstringHeader);
          if ( v23 >= 0 )
          {
            v24 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
                    v38,
                    &v33);
            v25 = ReadPrivateScanSettings(v24, &hstringHeader);
            v26 = v25 + 0x80000000;
            if ( (int)v26 >= 0 && v25 != -2147467263 )
              TracelogOnesettingsError(LODWORD(hstringHeader.Reserved.Reserved1), 2, v25);
            v27 = *(_QWORD *)(a1 + 8);
            if ( v27 == *(_QWORD *)(a1 + 16) )
            {
              std::vector<SCAN_SETTINGS>::_Emplace_reallocate<SCAN_SETTINGS const &>(a1, v27, &hstringHeader);
            }
            else
            {
              std::_Default_allocator_traits<std::allocator<SCAN_SETTINGS>>::construct<SCAN_SETTINGS,SCAN_SETTINGS const &>(
                v26,
                v27,
                &hstringHeader);
              *(_QWORD *)(a1 + 8) += 24LL;
            }
          }
          else
          {
            TracelogOnesettingsError(LODWORD(hstringHeader.Reserved.Reserved1), 1, (unsigned int)v23);
          }
        }
      }
      WindowsDeleteString(string);
      string = 0;
    }
    wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v33);
  }
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v34);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v32);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(&v35);
  RoUninitialize(v28);
  return 0;
}

```

## disassembly

```asm
0x180014550  mov     [rsp-8+arg_8], rbx
0x180014555  mov     [rsp-8+arg_10], rsi
0x18001455a  push    rbp
0x18001455b  push    rdi
0x18001455c  push    r12
0x18001455e  push    r14
0x180014560  push    r15
0x180014562  lea     rbp, [rsp-37h]
0x180014567  sub     rsp, 0D0h
0x18001456e  mov     rax, cs:__security_cookie
0x180014575  xor     rax, rsp
0x180014578  mov     [rbp+57h+var_28], rax
0x18001457c  mov     rsi, rcx
0x18001457f  mov     ecx, 1
0x180014584  call    cs:__imp_RoInitialize
0x18001458a  mov     ebx, eax
0x18001458c  xor     r12d, r12d
0x18001458f  test    eax, eax
0x180014591  jns     short loc_1800145B0
0x180014593  mov     rcx, [rbp+5Fh]; this
0x180014597  mov     r9d, eax; char *
0x18001459a  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800145a1  mov     edx, 129h; void *
0x1800145a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145ab  jmp     loc_180014962
0x1800145b0  mov     [rbp+57h+var_A7], 1
0x1800145b4  mov     [rbp+57h+var_B0], r12
0x1800145b8  mov     [rbp+57h+var_50], r12
0x1800145bc  mov     r9d, 39h ; '9'; unsigned int
0x1800145c2  lea     r8d, [r9+1]; unsigned int
0x1800145c6  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x1800145cd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800145d1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800145d6  lea     r8, [rbp+57h+var_B0]
0x1800145da  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x1800145e1  mov     rcx, [rbp+57h+var_50]
0x1800145e5  call    cs:__imp_RoGetActivationFactory
0x1800145eb  mov     ebx, eax
0x1800145ed  test    eax, eax
0x1800145ef  jns     short loc_18001460E
0x1800145f1  mov     rcx, [rbp+5Fh]; this
0x1800145f5  mov     r9d, eax; char *
0x1800145f8  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800145ff  mov     edx, 135h; void *
0x180014604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014609  jmp     loc_180014952
0x18001460e  mov     [rbp+57h+var_C8], r12
0x180014612  mov     rdi, [rbp+57h+var_B0]
0x180014616  mov     rax, [rdi]
0x180014619  mov     rbx, [rax+30h]
0x18001461d  mov     [rbp+57h+var_C8], r12
0x180014621  mov     [rbp+57h+var_50], r12
0x180014625  mov     r14d, 0Fh
0x18001462b  mov     r9d, r14d; unsigned int
0x18001462e  lea     r8d, [r14+1]; unsigned int
0x180014632  lea     rdx, aStoragegrovele; "STORAGEGROVELER"
0x180014639  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001463d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014642  nop
0x180014643  lea     r8, [rbp+57h+var_C8]
0x180014647  mov     rdx, [rbp+57h+var_50]
0x18001464b  mov     rcx, rdi
0x18001464e  mov     rax, rbx
0x180014651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014656  mov     ebx, eax
0x180014658  test    eax, eax
0x18001465a  jns     short loc_180014669
0x18001465c  mov     r9d, eax
0x18001465f  mov     edx, 138h
0x180014664  jmp     loc_180014937
0x180014669  or      edi, 0FFFFFFFFh
0x18001466c  mov     [rbp+57h+var_90], edi
0x18001466f  mov     [rbp+57h+var_8C], 100h
0x180014675  mov     [rbp+57h+var_88], 0A8h
0x18001467d  mov     rcx, [rbp+57h+var_C8]
0x180014681  mov     [rbp+57h+var_C0], rcx
0x180014685  test    rcx, rcx
0x180014688  jz      short loc_180014697
0x18001468a  mov     rax, [rcx]
0x18001468d  mov     rax, [rax+8]
0x180014691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014696  nop
0x180014697  lea     rdx, [rbp+57h+var_90]
0x18001469b  lea     rcx, [rbp+57h+var_C0]
0x18001469f  call    ?ReadDefaultSharedScanSettings@@YAJV?$com_ptr_t@UIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUSCAN_SETTINGS@@@Z; ReadDefaultSharedScanSettings(wil::com_ptr_t<Windows::Internal::Flighting::OneSettings::IOneSettingsPayload,wil::err_exception_policy>,SCAN_SETTINGS &)
0x1800146a4  mov     ebx, eax
0x1800146a6  test    eax, eax
0x1800146a8  jns     short loc_1800146BB
0x1800146aa  mov     r8d, eax
0x1800146ad  xor     edx, edx
0x1800146af  mov     ecx, edi
0x1800146b1  call    ?TracelogOnesettingsError@@YAXW4SCAN_ID@@W4ONESETTINGS_SETTING_TYPE@@J@Z; TracelogOnesettingsError(SCAN_ID,ONESETTINGS_SETTING_TYPE,long)
0x1800146b6  jmp     loc_180014948
0x1800146bb  xorps   xmm0, xmm0
0x1800146be  movsd   [rbp+57h+var_A0], xmm0
0x1800146c3  mov     rdi, [rbp+57h+var_C8]
0x1800146c7  mov     rax, [rdi]
0x1800146ca  mov     rbx, [rax+50h]
0x1800146ce  mov     [rbp+57h+var_50], r12
0x1800146d2  mov     r9d, 0Eh; unsigned int
0x1800146d8  mov     r8d, r14d; unsigned int
0x1800146db  lea     rdx, aScanlistlength; "ScanListLength"
0x1800146e2  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800146e6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800146eb  nop
0x1800146ec  lea     r8, [rbp+57h+var_A0]
0x1800146f0  mov     rdx, [rbp+57h+var_50]
0x1800146f4  mov     rcx, rdi
0x1800146f7  mov     rax, rbx
0x1800146fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146ff  mov     ebx, eax
0x180014701  test    eax, eax
0x180014703  jns     short loc_180014712
0x180014705  mov     r9d, eax
0x180014708  mov     edx, 143h
0x18001470d  jmp     loc_180014937
0x180014712  cvttsd2si r15d, [rbp+57h+var_A0]
0x180014718  lea     eax, [r15-1]
0x18001471c  cmp     eax, 12h
0x18001471f  ja      loc_18001492A
0x180014725  mov     [rbp+57h+var_B8], r12
0x180014729  mov     rdi, [rbp+57h+var_C8]
0x18001472d  mov     rax, [rdi]
0x180014730  mov     rbx, [rax+40h]
0x180014734  mov     [rbp+57h+var_B8], r12
0x180014738  mov     [rbp+57h+var_50], r12
0x18001473c  mov     r9d, 8; unsigned int
0x180014742  lea     r8d, [r9+1]; unsigned int
0x180014746  lea     rdx, aScanlist; "ScanList"
0x18001474d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180014751  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014756  nop
0x180014757  lea     r8, [rbp+57h+var_B8]
0x18001475b  mov     rdx, [rbp+57h+var_50]
0x18001475f  mov     rcx, rdi
0x180014762  mov     rax, rbx
0x180014765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001476a  mov     ebx, eax
0x18001476c  test    eax, eax
0x18001476e  jns     short loc_180014797
0x180014770  mov     rcx, [rbp+5Fh]; this
0x180014774  mov     r9d, eax; char *
0x180014777  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001477e  mov     edx, 148h; void *
0x180014783  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014788  nop
0x180014789  lea     rcx, [rbp+57h+var_B8]
0x18001478d  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180014792  jmp     loc_180014948
0x180014797  mov     r14d, r12d
0x18001479a  test    r15d, r15d
0x18001479d  jle     loc_180014902
0x1800147a3  mov     [rbp+57h+var_C0], r12
0x1800147a7  mov     rcx, [rbp+57h+var_B8]
0x1800147ab  mov     rax, [rcx]
0x1800147ae  mov     [rbp+57h+var_C0], r12
0x1800147b2  lea     r8, [rbp+57h+var_C0]
0x1800147b6  mov     edx, r14d
0x1800147b9  mov     rax, [rax+30h]
0x1800147bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147c2  test    eax, eax
0x1800147c4  js      loc_1800148ED
0x1800147ca  mov     [rbp+57h+string], r12
0x1800147ce  mov     rdi, [rbp+57h+var_C0]
0x1800147d2  mov     rax, [rdi]
0x1800147d5  mov     rbx, [rax+50h]
0x1800147d9  xor     ecx, ecx; string
0x1800147db  call    cs:__imp_WindowsDeleteString
0x1800147e1  mov     [rbp+57h+string], r12
0x1800147e5  mov     [rbp+57h+var_30], r12
0x1800147e9  mov     r9d, 8; unsigned int
0x1800147ef  lea     r8d, [r9+1]; unsigned int
0x1800147f3  lea     rdx, aScanname; "ScanName"
0x1800147fa  lea     rcx, [rbp+57h+var_48]; hstringHeader
0x1800147fe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014803  nop
0x180014804  lea     r8, [rbp+57h+string]
0x180014808  mov     rdx, [rbp+57h+var_30]
0x18001480c  mov     rcx, rdi
0x18001480f  mov     rax, rbx
0x180014812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014817  nop
0x180014818  shr     eax, 1Fh
0x18001481b  test    al, al
0x18001481d  jnz     loc_1800148DF
0x180014823  mov     dword ptr [rbp+57h+hstringHeader.Reserved], 0FFFFFFFFh
0x18001482a  mov     word ptr [rbp+57h+hstringHeader.Reserved+4], 100h
0x180014830  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], 0A8h
0x180014838  mov     rcx, [rbp+57h+string]
0x18001483c  call    ?FindScanId@@YA?AW4SCAN_ID@@PEAUHSTRING__@@@Z; FindScanId(HSTRING__ *)
0x180014841  mov     dword ptr [rbp+57h+hstringHeader.Reserved], eax
0x180014844  cmp     eax, 0FFFFFFFFh
0x180014847  jz      loc_1800148DF
0x18001484d  lea     rdx, [rbp+57h+var_C0]
0x180014851  lea     rcx, [rbp+57h+var_78]
0x180014855  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x18001485a  lea     r8, [rbp+57h+hstringHeader]
0x18001485e  lea     rdx, [rbp+57h+var_90]
0x180014862  mov     rcx, rax
0x180014865  call    ?ReadSharedScanSettings@@YAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUSCAN_SETTINGS@@1@Z; ReadSharedScanSettings(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,SCAN_SETTINGS &,SCAN_SETTINGS &)
0x18001486a  test    eax, eax
0x18001486c  jns     short loc_180014880
0x18001486e  mov     r8d, eax
0x180014871  mov     edx, 1
0x180014876  mov     ecx, dword ptr [rbp+57h+hstringHeader.Reserved]
0x180014879  call    ?TracelogOnesettingsError@@YAXW4SCAN_ID@@W4ONESETTINGS_SETTING_TYPE@@J@Z; TracelogOnesettingsError(SCAN_ID,ONESETTINGS_SETTING_TYPE,long)
0x18001487e  jmp     short loc_1800148DF
0x180014880  lea     rdx, [rbp+57h+var_C0]
0x180014884  lea     rcx, [rbp+57h+var_98]
0x180014888  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x18001488d  lea     rdx, [rbp+57h+hstringHeader]
0x180014891  mov     rcx, rax
0x180014894  call    ?ReadPrivateScanSettings@@YAJV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUSCAN_SETTINGS@@@Z; ReadPrivateScanSettings(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,SCAN_SETTINGS &)
0x180014899  mov     ebx, 80000000h
0x18001489e  lea     ecx, [rax+rbx]
0x1800148a1  test    ebx, ecx
0x1800148a3  jnz     short loc_1800148BC
0x1800148a5  cmp     eax, 80004001h
0x1800148aa  jz      short loc_1800148BC
0x1800148ac  mov     r8d, eax
0x1800148af  mov     edx, 2
0x1800148b4  mov     ecx, dword ptr [rbp+57h+hstringHeader.Reserved]
0x1800148b7  call    ?TracelogOnesettingsError@@YAXW4SCAN_ID@@W4ONESETTINGS_SETTING_TYPE@@J@Z; TracelogOnesettingsError(SCAN_ID,ONESETTINGS_SETTING_TYPE,long)
0x1800148bc  mov     rdx, [rsi+8]
0x1800148c0  lea     r8, [rbp+57h+hstringHeader]
0x1800148c4  cmp     rdx, [rsi+10h]
0x1800148c8  jz      short loc_1800148D6
0x1800148ca  call    ??$construct@USCAN_SETTINGS@@AEBU1@@?$_Default_allocator_traits@V?$allocator@USCAN_SETTINGS@@@std@@@std@@SAXAEAV?$allocator@USCAN_SETTINGS@@@1@QEAUSCAN_SETTINGS@@AEBU3@@Z; std::_Default_allocator_traits<std::allocator<SCAN_SETTINGS>>::construct<SCAN_SETTINGS,SCAN_SETTINGS const &>(std::allocator<SCAN_SETTINGS> &,SCAN_SETTINGS * const,SCAN_SETTINGS const &)
0x1800148cf  add     qword ptr [rsi+8], 18h
0x1800148d4  jmp     short loc_1800148DF
0x1800148d6  mov     rcx, rsi
0x1800148d9  call    ??$_Emplace_reallocate@AEBUSCAN_SETTINGS@@@?$vector@USCAN_SETTINGS@@V?$allocator@USCAN_SETTINGS@@@std@@@std@@AEAAPEAUSCAN_SETTINGS@@QEAU2@AEBU2@@Z; std::vector<SCAN_SETTINGS>::_Emplace_reallocate<SCAN_SETTINGS const &>(SCAN_SETTINGS * const,SCAN_SETTINGS const &)
0x1800148de  nop
0x1800148df  mov     rcx, [rbp+57h+string]; string
0x1800148e3  call    cs:__imp_WindowsDeleteString
0x1800148e9  mov     [rbp+57h+string], r12
0x1800148ed  lea     rcx, [rbp+57h+var_C0]
0x1800148f1  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x1800148f6  inc     r14d
0x1800148f9  cmp     r14d, r15d
0x1800148fc  jl      loc_1800147A3
0x180014902  lea     rcx, [rbp+57h+var_B8]
0x180014906  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18001490b  nop
0x18001490c  lea     rcx, [rbp+57h+var_C8]
0x180014910  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180014915  nop
0x180014916  lea     rcx, [rbp+57h+var_B0]
0x18001491a  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18001491f  nop
0x180014920  call    cs:__imp_RoUninitialize
0x180014926  xor     eax, eax
0x180014928  jmp     short loc_180014964
0x18001492a  mov     ebx, 80070018h
0x18001492f  mov     r9d, ebx; char *
0x180014932  mov     edx, 145h; void *
0x180014937  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001493e  mov     rcx, [rbp+5Fh]; this
0x180014942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014947  nop
0x180014948  lea     rcx, [rbp+57h+var_C8]
0x18001494c  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x180014951  nop
0x180014952  lea     rcx, [rbp+57h+var_B0]
0x180014956  call    ??1?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(void)
0x18001495b  nop
0x18001495c  call    cs:__imp_RoUninitialize
0x180014962  mov     eax, ebx
0x180014964  mov     rcx, [rbp+57h+var_28]
0x180014968  xor     rcx, rsp; StackCookie
0x18001496b  call    __security_check_cookie
0x180014970  lea     r11, [rsp+0F0h+var_20]
0x180014978  mov     rbx, [r11+38h]
0x18001497c  mov     rsi, [r11+40h]
0x180014980  mov     rsp, r11
0x180014983  pop     r15
0x180014985  pop     r14
0x180014987  pop     r12
0x180014989  pop     rdi
0x18001498a  pop     rbp
0x18001498b  retn
```
