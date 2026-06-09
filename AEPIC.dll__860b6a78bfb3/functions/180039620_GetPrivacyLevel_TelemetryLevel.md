# GetPrivacyLevel(TelemetryLevel *)

- ea: `0x180039620`
- end: `0x18003984c`
- name: `?GetPrivacyLevel@@YAJPEAW4TelemetryLevel@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(enum TelemetryLevel *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18001e510`
- `0x180021530`
- `0x1800252b0`
- `0x1800295dc`
- `0x180039620`
- `0x180039854`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003982b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003982b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003967f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003967f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800396a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800396a4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039767`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039767`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetPrivacyLevel(enum TelemetryLevel *a1, unsigned __int16 a2, unsigned __int16 a3)
{
  HMODULE Library; // rax
  HMODULE v6; // rsi
  FARPROC ProcAddress; // rax
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rbx
  int ActivationFactory; // eax
  const char *v13; // r9
  __int64 v14; // r8
  __int64 v15; // [rsp+20h] [rbp-58h]
  int v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  int v18; // [rsp+40h] [rbp-38h] BYREF
  int v19; // [rsp+44h] [rbp-34h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  __int64 v21; // [rsp+60h] [rbp-18h]

  if ( !a1 )
    return 2147942487LL;
  if ( !IsWindowsVersionOrGreaterEx((unsigned __int16)a1, a2, a3, 0x295Au) )
    return 2147500033LL;
  v18 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings", 0, 0x800u);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelEvaluateActiveSettingAuthority");
    if ( ProcAddress )
    {
      v8 = ((__int64 (__fastcall *)(int *, _QWORD))ProcAddress)(&v18, 0);
      v9 = v8;
      if ( v8 >= 0 )
      {
        *(_DWORD *)a1 = v18;
LABEL_28:
        FreeLibrary(v6);
        return v9;
      }
      AslLogCallPrintf(1, "GetPrivacyLevel", 89, "GetMaximumAllowedTelemetryLevel failed [%#x]", v8);
    }
  }
  v16 = -2147221008;
  v10 = Common::AutoWinRTInitialize::Initialize(&v16);
  v9 = v10;
  if ( v10 < 0 )
  {
    AslLogCallPrintf(1, "GetPrivacyLevel", 106, "Windows::Foundation::Initialize failed [%#x]", v10);
    goto LABEL_27;
  }
  v19 = 0;
  v17 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Profile.PlatformDiagnosticsAndUsageDataSettings",
    0x3Fu,
    0x3Eu);
  v11 = v21;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
  ActivationFactory = RoGetActivationFactory(v11, &GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a, &v17);
  v9 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 48LL))(v17, &v19);
    v9 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      if ( v19 )
      {
        switch ( v19 )
        {
          case 1:
            *(_DWORD *)a1 = 1;
            break;
          case 2:
            *(_DWORD *)a1 = 2;
            break;
          case 3:
            *(_DWORD *)a1 = 3;
            break;
          default:
            AslLogCallPrintf(1, "GetPrivacyLevel", 144, "Unexpected RtCollectionLevel [%d]", v19);
            v9 = -2147467259;
            break;
        }
      }
      else
      {
        *(_DWORD *)a1 = 0;
      }
      goto LABEL_26;
    }
    v13 = "IPlatformDiagnosticsAndUsageDataSettingsStatics::get_CollectionLevel failed [%#x]";
    v14 = 124;
  }
  else
  {
    v13 = "GetActivationFactory [%#x]";
    v14 = 117;
  }
  LODWORD(v15) = ActivationFactory;
  AslLogCallPrintf(1, "GetPrivacyLevel", v14, v13, v15);
LABEL_26:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
LABEL_27:
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v16);
  if ( v6 )
    goto LABEL_28;
  return v9;
}

```

## disassembly

```asm
0x180039620  push    rbp
0x180039622  push    rbx
0x180039623  push    rsi
0x180039624  push    rdi
0x180039625  push    r12
0x180039627  push    r15
0x180039629  mov     rbp, rsp
0x18003962c  sub     rsp, 78h
0x180039630  mov     rax, cs:__security_cookie
0x180039637  xor     rax, rsp
0x18003963a  mov     [rbp+var_10], rax
0x18003963e  mov     rdi, rcx
0x180039641  test    rcx, rcx
0x180039644  jnz     short loc_180039650
0x180039646  mov     eax, 80070057h
0x18003964b  jmp     loc_180039833
0x180039650  mov     r9d, 295Ah; unsigned __int16
0x180039656  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18003965b  test    al, al
0x18003965d  jnz     short loc_180039669
0x18003965f  mov     eax, 80004001h
0x180039664  jmp     loc_180039833
0x180039669  mov     [rbp+var_38], 0
0x180039670  xor     edx, edx; hFile
0x180039672  mov     r8d, 800h; dwFlags
0x180039678  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x18003967f  call    cs:__imp_LoadLibraryExW
0x180039685  mov     rsi, rax
0x180039688  lea     r12, aGetprivacyleve_0; "GetPrivacyLevel"
0x18003968f  mov     r15d, 1
0x180039695  test    rax, rax
0x180039698  jz      short loc_1800396DA
0x18003969a  lea     rdx, aTelevaluateact; "TelEvaluateActiveSettingAuthority"
0x1800396a1  mov     rcx, rax; hModule
0x1800396a4  call    cs:__imp_GetProcAddress
0x1800396aa  test    rax, rax
0x1800396ad  jz      short loc_1800396DA
0x1800396af  xor     edx, edx
0x1800396b1  lea     rcx, [rbp+var_38]
0x1800396b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800396ba  mov     ebx, eax
0x1800396bc  test    eax, eax
0x1800396be  jns     short loc_180039711
0x1800396c0  mov     [rsp+78h+var_58], eax
0x1800396c4  lea     r9, aGetmaximumallo; "GetMaximumAllowedTelemetryLevel failed "...
0x1800396cb  lea     r8d, [r15+58h]
0x1800396cf  mov     rdx, r12
0x1800396d2  mov     ecx, r15d
0x1800396d5  call    AslLogCallPrintf
0x1800396da  mov     [rbp+var_48], 800401F0h
0x1800396e1  lea     rcx, [rbp+var_48]
0x1800396e5  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x1800396ea  mov     ebx, eax
0x1800396ec  test    eax, eax
0x1800396ee  jns     short loc_18003971B
0x1800396f0  mov     [rsp+78h+var_58], eax
0x1800396f4  lea     r9, aWindowsFoundat_0; "Windows::Foundation::Initialize failed "...
0x1800396fb  mov     r8d, 6Ah ; 'j'
0x180039701  mov     rdx, r12
0x180039704  mov     ecx, r15d
0x180039707  call    AslLogCallPrintf
0x18003970c  jmp     loc_18003981A
0x180039711  mov     eax, [rbp+var_38]
0x180039714  mov     [rdi], eax
0x180039716  jmp     loc_180039828
0x18003971b  mov     [rbp+var_34], 0
0x180039722  mov     [rbp+var_40], 0
0x18003972a  mov     [rbp+var_18], 0
0x180039732  mov     r9d, 3Eh ; '>'; unsigned int
0x180039738  lea     r8d, [r9+1]; unsigned int
0x18003973c  lea     rdx, ?RuntimeClass_Windows_System_Profile_PlatformDiagnosticsAndUsageDataSettings@@3QBGB; "Windows.System.Profile.PlatformDiagnost"...
0x180039743  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180039747  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003974c  mov     rbx, [rbp+var_18]
0x180039750  lea     rcx, [rbp+var_40]
0x180039754  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039759  lea     r8, [rbp+var_40]
0x18003975d  lea     rdx, _GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a
0x180039764  mov     rcx, rbx
0x180039767  call    cs:__imp_RoGetActivationFactory
0x18003976d  mov     ebx, eax
0x18003976f  test    eax, eax
0x180039771  jns     short loc_180039791
0x180039773  lea     r9, aGetactivationf; "GetActivationFactory [%#x]"
0x18003977a  mov     r8d, 75h ; 'u'
0x180039780  mov     [rsp+78h+var_58], eax
0x180039784  mov     rdx, r12
0x180039787  mov     ecx, r15d
0x18003978a  call    AslLogCallPrintf
0x18003978f  jmp     short loc_180039810
0x180039791  mov     rcx, [rbp+var_40]
0x180039795  mov     rax, [rcx]
0x180039798  lea     rdx, [rbp+var_34]
0x18003979c  mov     rax, [rax+30h]
0x1800397a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397a5  mov     ebx, eax
0x1800397a7  test    eax, eax
0x1800397a9  jns     short loc_1800397BA
0x1800397ab  lea     r9, aIplatformdiagn; "IPlatformDiagnosticsAndUsageDataSetting"...
0x1800397b2  mov     r8d, 7Ch ; '|'
0x1800397b8  jmp     short loc_180039780
0x1800397ba  mov     edx, [rbp+var_34]
0x1800397bd  mov     ecx, edx
0x1800397bf  test    edx, edx
0x1800397c1  jz      short loc_18003980A
0x1800397c3  sub     ecx, 1
0x1800397c6  jz      short loc_180039805
0x1800397c8  sub     ecx, 1
0x1800397cb  jz      short loc_1800397FD
0x1800397cd  cmp     ecx, 1
0x1800397d0  jz      short loc_1800397F5
0x1800397d2  mov     [rsp+78h+var_58], edx
0x1800397d6  lea     r9, aUnexpectedRtco; "Unexpected RtCollectionLevel [%d]"
0x1800397dd  mov     r8d, 90h
0x1800397e3  mov     rdx, r12
0x1800397e6  mov     ecx, r15d
0x1800397e9  call    AslLogCallPrintf
0x1800397ee  mov     ebx, 80004005h
0x1800397f3  jmp     short loc_180039810
0x1800397f5  mov     dword ptr [rdi], 3
0x1800397fb  jmp     short loc_180039810
0x1800397fd  mov     dword ptr [rdi], 2
0x180039803  jmp     short loc_180039810
0x180039805  mov     [rdi], r15d
0x180039808  jmp     short loc_180039810
0x18003980a  mov     dword ptr [rdi], 0
0x180039810  lea     rcx, [rbp+var_40]
0x180039814  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039819  nop
0x18003981a  lea     rcx, [rbp+var_48]; this
0x18003981e  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x180039823  test    rsi, rsi
0x180039826  jz      short loc_180039831
0x180039828  mov     rcx, rsi; hLibModule
0x18003982b  call    cs:__imp_FreeLibrary
0x180039831  mov     eax, ebx
0x180039833  mov     rcx, [rbp+var_10]
0x180039837  xor     rcx, rsp; StackCookie
0x18003983a  call    __security_check_cookie
0x18003983f  add     rsp, 78h
0x180039843  pop     r15
0x180039845  pop     r12
0x180039847  pop     rdi
0x180039848  pop     rsi
0x180039849  pop     rbx
0x18003984a  pop     rbp
0x18003984b  retn
```
