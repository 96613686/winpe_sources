# DmGetAadUserToken_Internal2(ushort const *,ushort const *,ushort const *,uchar,uchar,uchar,ushort const *,ushort * *,ushort * *,int *)

- ea: `0x1800759c0`
- end: `0x180076de2`
- name: `?DmGetAadUserToken_Internal2@@YAJPEBG00EEE0PEAPEAG1PEAH@Z`
- size: `5154`
- prototype: `__int64 __usercall@<rax>(PCWSTR sourceString@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int8@<r9b>, unsigned __int8, char, PCWSTR, unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180076de8`

## callees

- `0x1800012d0`
- `0x180007270`
- `0x180053ef0`
- `0x180054c38`
- `0x1800592a4`
- `0x18005c118`
- `0x18005c180`
- `0x18005c258`
- `0x18005c370`
- `0x18005c46c`
- `0x18005c56c`
- `0x18005c684`
- `0x18005d690`
- `0x180063ab8`
- `0x180064a44`
- `0x18006dbb0`
- `0x18006ed58`
- `0x18006fc00`
- `0x1800728c8`
- `0x180072920`
- `0x180072978`
- `0x1800729d0`
- `0x180072f7c`
- `0x180072fc4`
- `0x180073004`
- `0x18007389c`
- `0x180073a34`
- `0x180074994`
- `0x180074a34`
- `0x180074cd8`
- `0x180074d0c`
- `0x1800759c0`
- `0x1800783b0`
- `0x1800785cc`
- `0x180078934`
- `0x180079ce4`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800767ed`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18007681e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800767ed`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18007681e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075b04`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075b3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075ba5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075be8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007609d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180076156`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075b04`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075b3f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075ba5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180075be8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007609d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180076156`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180076855`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180076855`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180075c33`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180075c33`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180075fb0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180075fb0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007686e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007686e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800764f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007662f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800766b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007670c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076cf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800764f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007662f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800766b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007670c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076765`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076cf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007668c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800767de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007680f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007668c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800767de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007680f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076caa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075adf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075b62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075b8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800760c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180076179`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075adf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075b62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075b8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180075bcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800760c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180076179`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180075de7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180075de7`

## string_xrefs

- `0x180075b83`: `client_TokenType`
- `0x180075ff0`: `https://login.windows-ppe.net/common`
- `0x18007678b`: `TokenExpiresOn`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
__int64 __fastcall DmGetAadUserToken_Internal2(
        PCWSTR sourceString,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        char a6,
        PCWSTR a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9,
        int *a10)
{
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // rcx
  const unsigned __int16 *v13; // rdx
  int ActivationFactory; // esi
  _QWORD *v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, HSTRING *); // rbx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v19)(_QWORD, GUID *, HSTRING *); // rdi
  HSTRING v20; // rdi
  __int64 (__fastcall *v21)(HSTRING, HSTRING, struct _FILETIME *); // rbx
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, HSTRING, HSTRING, _DWORD); // rbx
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, __int64, __int64, _BYTE *); // rdi
  __int64 v28; // rbx
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, _QWORD, __int64, _BYTE *); // rdi
  __int64 v31; // rbx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, _QWORD, HSTRING, _BYTE *); // rsi
  unsigned __int64 v34; // rcx
  const WCHAR *v35; // rbx
  HSTRING v36; // rbx
  const unsigned __int16 (*v37)[9]; // rdx
  _QWORD *v38; // rax
  __int64 (__fastcall ***v39)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v40)(_QWORD, GUID *, HSTRING *); // rdi
  HSTRING v41; // rbx
  _QWORD *v42; // rax
  unsigned int v43; // r12d
  char v44; // r13
  unsigned __int8 v45; // r14
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v47)(_QWORD, GUID *, HSTRING *); // rdi
  HSTRING v48; // r14
  __int64 (__fastcall *v49)(HSTRING, HWND, __int64, __int64, GUID *); // rsi
  __int64 v50; // rbx
  __int64 v51; // rdi
  HWND WindowsHandle; // rax
  HSTRING v53; // rsi
  __int64 (__fastcall *v54)(HSTRING, HWND, __int64, GUID *, UINT32 *); // rdi
  __int64 v55; // rbx
  HWND v56; // rax
  __int64 (__fastcall ***v57)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall **v58)(_QWORD, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v59)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v60)(_QWORD, __int64, UINT32 *); // rbx
  __int64 v61; // rbx
  __int64 v62; // rdi
  int (__fastcall *v63)(__int64, HSTRING *); // rbx
  HSTRING v64; // rdi
  void (__fastcall *v65)(HSTRING, HSTRING *); // rbx
  __int64 v66; // rdi
  __int64 (__fastcall *v67)(__int64, __int64 *); // rbx
  __int64 v68; // rdi
  __int64 (__fastcall *v69)(__int64, _QWORD, __int64 *); // rbx
  int v70; // ebx
  __int64 v71; // rdi
  __int64 (__fastcall *v72)(__int64, _QWORD, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rax
  char IsEnabled; // al
  __int64 v75; // rdi
  __int64 (__fastcall *v76)(__int64, __int64, HSTRING *); // rbx
  int v77; // eax
  const wchar_t *v78; // rax
  __int64 v79; // rax
  __int64 v80; // rbx
  DWORD v81; // eax
  const wchar_t *v82; // rax
  COmaDmLogger *Logger; // rax
  unsigned __int64 v84; // rcx
  int v85; // ebx
  __int64 v86; // rax
  HSTRING_HEADER *v87; // rcx
  bool v88; // di
  int v89; // ebx
  COmaDmLogger *v90; // rax
  HSTRING v91; // rcx
  COmaDmLogger *v92; // rax
  __int64 v93; // rcx
  __int64 v94; // rbx
  unsigned __int16 **v95; // rbx
  const wchar_t *v96; // rax
  wil *v97; // rcx
  unsigned __int8 v98; // bl
  unsigned __int16 **v99; // rdi
  unsigned __int16 *v100; // r14
  COmaDmLogger *v101; // rax
  int v102; // r8d
  int v103; // r9d
  __int64 v104; // rcx
  __int64 v105; // rcx
  UINT32 *pvData; // [rsp+28h] [rbp-280h]
  _BYTE v109[7]; // [rsp+41h] [rbp-267h] BYREF
  HSTRING v110; // [rsp+48h] [rbp-260h] BYREF
  char v111; // [rsp+50h] [rbp-258h]
  UINT32 v112[2]; // [rsp+58h] [rbp-250h] BYREF
  unsigned __int8 v113; // [rsp+60h] [rbp-248h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-240h] BYREF
  UINT32 v115; // [rsp+70h] [rbp-238h] BYREF
  unsigned int v116; // [rsp+74h] [rbp-234h] BYREF
  UINT32 length; // [rsp+78h] [rbp-230h] BYREF
  HSTRING v118; // [rsp+80h] [rbp-228h] BYREF
  unsigned int v119; // [rsp+88h] [rbp-220h] BYREF
  __int64 v120; // [rsp+90h] [rbp-218h] BYREF
  __int64 v121; // [rsp+98h] [rbp-210h] BYREF
  __int64 (__fastcall ***v122)(_QWORD, GUID *, HSTRING *); // [rsp+A0h] [rbp-208h] BYREF
  DWORD pcbData; // [rsp+A8h] [rbp-200h] BYREF
  __int64 v124; // [rsp+B0h] [rbp-1F8h] BYREF
  __int64 v125; // [rsp+B8h] [rbp-1F0h] BYREF
  __int64 v126; // [rsp+C0h] [rbp-1E8h] BYREF
  FILETIME FileTime2; // [rsp+C8h] [rbp-1E0h] BYREF
  __int64 v128; // [rsp+D0h] [rbp-1D8h] BYREF
  HSTRING v129; // [rsp+D8h] [rbp-1D0h] BYREF
  LPVOID ppv; // [rsp+E0h] [rbp-1C8h] BYREF
  PCWSTR sourceStringa; // [rsp+E8h] [rbp-1C0h] BYREF
  __int64 v132; // [rsp+F0h] [rbp-1B8h] BYREF
  __int64 v133; // [rsp+F8h] [rbp-1B0h] BYREF
  __int64 v134; // [rsp+100h] [rbp-1A8h] BYREF
  __int64 v135; // [rsp+108h] [rbp-1A0h] BYREF
  unsigned __int16 **v136; // [rsp+110h] [rbp-198h]
  HSTRING v137; // [rsp+118h] [rbp-190h] BYREF
  PCWSTR v138; // [rsp+120h] [rbp-188h] BYREF
  unsigned __int16 **v139; // [rsp+128h] [rbp-180h]
  unsigned __int16 *v140; // [rsp+130h] [rbp-178h]
  unsigned __int16 *v141; // [rsp+138h] [rbp-170h] BYREF
  __int64 v142; // [rsp+140h] [rbp-168h] BYREF
  int *v143; // [rsp+148h] [rbp-160h]
  _BYTE v144[8]; // [rsp+150h] [rbp-158h] BYREF
  _BYTE v145[8]; // [rsp+158h] [rbp-150h] BYREF
  __int64 v146; // [rsp+160h] [rbp-148h]
  HSTRING v147; // [rsp+168h] [rbp-140h] BYREF
  HSTRING_HEADER v148; // [rsp+170h] [rbp-138h] BYREF
  HSTRING_HEADER v149; // [rsp+188h] [rbp-120h] BYREF
  __int64 v150; // [rsp+1A0h] [rbp-108h]
  HSTRING_HEADER v151; // [rsp+1A8h] [rbp-100h] BYREF
  __int64 v152; // [rsp+1C0h] [rbp-E8h]
  HSTRING string; // [rsp+1C8h] [rbp-E0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1D0h] [rbp-D8h] BYREF
  HSTRING v155; // [rsp+1E8h] [rbp-C0h] BYREF
  HSTRING v156; // [rsp+208h] [rbp-A0h] BYREF
  HSTRING_HEADER v157; // [rsp+210h] [rbp-98h] BYREF
  HSTRING v158; // [rsp+228h] [rbp-80h] BYREF
  HSTRING_HEADER v159; // [rsp+230h] [rbp-78h] BYREF
  HSTRING v160; // [rsp+248h] [rbp-60h] BYREF
  HSTRING_HEADER v161; // [rsp+250h] [rbp-58h] BYREF

  v140 = a3;
  sourceStringa = a2;
  v141 = a3;
  v113 = a4;
  v139 = a8;
  v136 = a9;
  v138 = (PCWSTR)a9;
  v143 = a10;
  v122 = 0;
  v135 = 0;
  v121 = 0;
  v133 = 0;
  v120 = 0;
  v146 = 0;
  v126 = 0;
  v132 = 0;
  v134 = 0;
  v125 = 0;
  ppv = 0;
  v142 = 0;
  v111 = 0;
  v116 = 0;
  v119 = 0;
  v129 = 0;
  Windows::Internal::StringReference::StringReference(&v155, (const unsigned __int16 (*)[26])a2);
  if ( WindowsCreateStringReference(&pszSrc, 0, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  length = 0;
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( sourceString[v12] );
  if ( (int)ULongLongToULong(v12, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(sourceString, length, &v157, &v156);
  if ( WindowsCreateStringReference(L"client_TokenType", 0x10u, &v161, &v160) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( WindowsCreateStringReference(L"DeviceAuth", 0xAu, &v159, &v158) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v137 = 0;
  v115 = 0;
  v109[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  ActivationFactory = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, 5, &v142);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
      v111 = 1;
    }
  }
  try
  {
    if ( ActivationFactory >= 0 )
    {
      v15 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                        (HSTRING *)&v151,
                        (const unsigned __int16 (*)[70])v13);
      ActivationFactory = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
                            *v15,
                            &v122);
      if ( ActivationFactory >= 0 )
      {
        SystemTimeAsFileTime = 0;
        if ( a5 )
        {
          v110 = 0;
          v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
          v19 = **v122;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
          ActivationFactory = v19(v18, &GUID_54e633fe_96e0_41e8_9832_1298897c2aaf, &v110);
          if ( ActivationFactory >= 0 )
          {
            v20 = v110;
            v21 = *(__int64 (__fastcall **)(HSTRING, HSTRING, struct _FILETIME *))(*(_QWORD *)v110 + 64LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SystemTimeAsFileTime);
            ActivationFactory = v21(v20, v155, &SystemTimeAsFileTime);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
        }
        else
        {
          v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
          v17 = (*v122)[11];
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SystemTimeAsFileTime);
          ActivationFactory = v17(v16, (GUID *)v155, (HSTRING *)&SystemTimeAsFileTime);
        }
        if ( ActivationFactory >= 0 )
          ActivationFactory = ((__int64 (__fastcall *)(_QWORD, _QWORD))BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>)(
                                SystemTimeAsFileTime,
                                &v133);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SystemTimeAsFileTime);
        if ( ActivationFactory >= 0 )
        {
          if ( !v133 )
            ActivationFactory = -2102788082;
          if ( ActivationFactory >= 0 )
          {
            v23 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                               (HSTRING *)&v151,
                               (const unsigned __int16 (*)[57])v22);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
            ActivationFactory = RoGetActivationFactory(v23, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v135);
            if ( ActivationFactory >= 0 )
            {
              v24 = v135;
              v25 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, HSTRING, _DWORD))(*(_QWORD *)v135 + 56LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
              pvData = (UINT32 *)&v121;
              ActivationFactory = v25(v24, v133, string, v156, 0);
              if ( ActivationFactory >= 0 )
              {
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v121 + 80LL))(
                                      v121,
                                      &v120);
                if ( ActivationFactory >= 0 )
                {
                  if ( !a5
                    || (ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v120 + 80LL))(
                                              v120,
                                              v160,
                                              v158,
                                              v109),
                        ActivationFactory >= 0) )
                  {
                    ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v120 + 80LL))(
                                          v120,
                                          v155,
                                          string,
                                          v109);
                    if ( ActivationFactory >= 0 )
                    {
                      if ( v140 )
                      {
                        v26 = v120;
                        v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v120 + 80LL);
                        v28 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v151, &v141) + 24);
                        v150 = 0;
                        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                          &v149,
                          L"CloudAssignedMdmId",
                          0x13u,
                          0x12u);
                        ActivationFactory = v27(v26, v150, v28, v109);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    length = 0;
    pcbData = 4;
    if ( ActivationFactory >= 0 )
    {
      if ( !RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\CDJ",
              L"PPE",
              0x10u,
              0,
              &length,
              &pcbData)
        && length )
      {
        v29 = v120;
        v30 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v120 + 80LL);
        v150 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &v149,
          L"https://login.windows-ppe.net/common",
          0x25u,
          0x24u);
        v31 = v150;
        *(_QWORD *)&v148.Reserved.Reserved2[16] = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)&v147, L"authority", 0xAu, 9u);
        ActivationFactory = v30(v29, *(_QWORD *)&v148.Reserved.Reserved2[16], v31, v109);
      }
      if ( ActivationFactory >= 0 )
      {
        v32 = v120;
        v33 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _BYTE *))(*(_QWORD *)v120 + 80LL);
        v112[0] = 0;
        v34 = -1;
        v35 = sourceStringa;
        do
          ++v34;
        while ( sourceStringa[v34] );
        if ( (int)ULongLongToULong(v34, v112) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        WindowsCreateStringReference(v35, v112[0], &v148, &v147);
        v36 = v147;
        v38 = (_QWORD *)Windows::Internal::StringReference::StringReference((HSTRING *)&v151, v37);
        ActivationFactory = v33(v32, *v38, v36, v109);
        if ( ActivationFactory >= 0 && a7 )
        {
          v110 = 0;
          v39 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
          v40 = (*v122)[10];
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
          v112[0] = 0;
          do
            ++v11;
          while ( a7[v11] );
          if ( (int)ULongLongToULong(v11, v112) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          WindowsCreateStringReference(a7, v112[0], &v148, &v147);
          if ( ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64, HSTRING, HSTRING *))v40)(
                 v39,
                 v133,
                 v147,
                 &v110) >= 0 )
          {
            v41 = v110;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
            BlockOnCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccount *>,Windows::Security::Credentials::IWebAccount *>(
              v41,
              &v125);
          }
          ActivationFactory = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
        }
      }
    }
    v124 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl'::`2'::impl) )
    {
      v110 = 0;
      v42 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::ensure_data(&v110);
      tip2::details::shared_data<0,0,0>::start(*v42 + 8LL, &v149);
      wil::com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>::operator=(
        &v124,
        &v110);
      wil::com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>(&v110);
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::operator->(
                              &v124,
                              &sourceStringa)
               + 272LL) = a5 != 0;
      tip2::test_data_control<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>(&sourceStringa);
    }
    v43 = 0;
    v44 = a6;
    v45 = a4;
    while ( 1 )
    {
      if ( ActivationFactory >= 0 )
      {
        *(_QWORD *)v112 = 0;
        if ( a4 )
        {
          v110 = 0;
          v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
          v47 = **v122;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
          ActivationFactory = v47(v46, &GUID_f4b8e804_811e_4436_b69c_44cb67b72084, &v110);
          if ( ActivationFactory >= 0 )
          {
            if ( v125 )
            {
              v48 = v110;
              v49 = *(__int64 (__fastcall **)(HSTRING, HWND, __int64, __int64, GUID *))(*(_QWORD *)v110 + 56LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112);
              v50 = v125;
              v51 = v121;
              WindowsHandle = _GetWindowsHandle();
              pvData = v112;
              ActivationFactory = v49(v48, WindowsHandle, v51, v50, &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9);
            }
            else
            {
              v53 = v110;
              v54 = *(__int64 (__fastcall **)(HSTRING, HWND, __int64, GUID *, UINT32 *))(*(_QWORD *)v110 + 48LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112);
              v55 = v121;
              v56 = _GetWindowsHandle();
              ActivationFactory = v54(v53, v56, v55, &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9, v112);
            }
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
        }
        else
        {
          v57 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v122;
          v58 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v122;
          if ( v125 )
          {
            v59 = v58[7];
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112);
            ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64, __int64, UINT32 *))v59)(
                                  v57,
                                  v121,
                                  v125,
                                  v112);
          }
          else
          {
            v60 = (__int64 (__fastcall *)(_QWORD, __int64, UINT32 *))v58[6];
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112);
            ActivationFactory = v60(v57, v121, v112);
          }
        }
        if ( ActivationFactory >= 0 )
        {
          v61 = *(_QWORD *)v112;
          ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(*(_QWORD *)v112);
          if ( ActivationFactory >= 0 )
            ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 64LL))(v61, &v126);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v112);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v126 + 56LL))(v126, &v116);
          if ( ActivationFactory >= 0 )
          {
            if ( !v116 )
              goto LABEL_82;
            if ( v116 == 3 && v143 )
              *v143 = 1;
            v110 = 0;
            ActivationFactory = -2147467259;
            v62 = v126;
            v63 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v126 + 64LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
            if ( v63(v62, &v110) >= 0 && v110 )
            {
              if ( (*(int (__fastcall **)(HSTRING, unsigned int *))(*(_QWORD *)v110 + 48LL))(v110, &v119) >= 0 )
              {
                ActivationFactory = v119;
                if ( (int)v119 > 0 )
                  ActivationFactory = (unsigned __int16)v119 | 0x80070000;
              }
              v64 = v110;
              v65 = *(void (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v110 + 56LL);
              WindowsDeleteString(v129);
              v129 = 0;
              v65(v64, &v129);
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v110);
            if ( ActivationFactory >= 0 )
            {
LABEL_82:
              v66 = v126;
              v67 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v126 + 48LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
              ActivationFactory = v67(v66, &v132);
              if ( ActivationFactory >= 0 )
              {
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v132 + 56LL))(v132, &v115);
                if ( ActivationFactory >= 0 )
                {
                  if ( v115 )
                  {
                    v68 = v132;
                    v69 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v132 + 48LL);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
                    ActivationFactory = v69(v68, 0, &v134);
                  }
                  else
                  {
                    ActivationFactory = -2147418113;
                  }
                }
              }
            }
          }
        }
        v45 = a4;
      }
      ++v43;
      v128 = 0;
      FileTime2 = 0;
      SystemTimeAsFileTime = 0;
      if ( ActivationFactory < 0 )
        goto LABEL_115;
      v70 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v134 + 72LL))(v134, &v128);
      if ( v70 < 0 )
      {
        if ( v136 )
          goto LABEL_95;
      }
      else if ( v136 )
      {
        v110 = 0;
        v71 = v128;
        v72 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v128 + 48LL);
        WindowsDeleteString(0);
        v110 = 0;
        *(_QWORD *)&v148.Reserved.Reserved2[16] = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          (HSTRING_HEADER *)&v147,
          L"mdm_enrollment_url",
          0x13u,
          0x12u);
        v70 = v72(v71, *(_QWORD *)&v148.Reserved.Reserved2[16], &v110);
        if ( v70 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(v110, 0);
          v70 = CopyString(StringRawBuffer, 0xFFFFFFFF, v136);
        }
        WindowsDeleteString(v110);
LABEL_95:
        if ( !v139 )
          ActivationFactory = v70;
      }
      v118 = 0;
      if ( v70 >= 0 )
      {
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl'::`2'::impl);
        v75 = v128;
        v76 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v128 + 48LL);
        if ( IsEnabled )
        {
          WindowsDeleteString(v118);
          v118 = 0;
          v152 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v151, L"exp", 4u, 3u);
          v77 = v76(v75, v152, &v118);
        }
        else
        {
          WindowsDeleteString(v118);
          v118 = 0;
          *(_QWORD *)&v148.Reserved.Reserved2[16] = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            (HSTRING_HEADER *)&v147,
            L"TokenExpiresOn",
            0xFu,
            0xEu);
          v77 = v76(v75, *(_QWORD *)&v148.Reserved.Reserved2[16], &v118);
        }
        if ( v77 >= 0 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl'::`2'::impl) )
          {
            v78 = WindowsGetStringRawBuffer(v118, 0);
            v79 = _wtoi64(v78);
            v80 = v79 + 0x2B6109498LL;
            v81 = 10000000 * (v79 - 1240427368);
          }
          else
          {
            v82 = WindowsGetStringRawBuffer(v118, 0);
            v80 = _wtoi64(v82);
            v81 = 10000000 * v80;
          }
          FileTime2.dwHighDateTime = (unsigned __int64)(10000000 * v80) >> 32;
          FileTime2.dwLowDateTime = v81;
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) == 1 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl'::`2'::impl) )
            {
              Logger = COmaDmLogger::GetLogger();
              COmaDmLogger::LogDmGetAadTokenExpired(Logger, v45, a5, &FileTime2, &SystemTimeAsFileTime, (char)pvData);
              sourceStringa = (PCWSTR)SystemTimeAsFileTime;
              v84 = *(_QWORD *)&SystemTimeAsFileTime - 10000000 * v80;
              v85 = -1;
              if ( !(v84 / 0x98968000000000LL) )
                v85 = v84 / 0x989680;
              v86 = tip2::tip_test<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::operator->(
                      &v124,
                      v144);
              ++*(_DWORD *)(*(_QWORD *)v86 + 276LL);
              tip2::test_data_control<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>(v144);
              if ( v43 == 1 )
              {
                *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::operator->(
                                         &v124,
                                         v145)
                          + 280LL) = v85;
                v87 = (HSTRING_HEADER *)v145;
              }
              else
              {
                *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::operator->(
                                         &v124,
                                         &v149)
                          + 284LL) = v85;
                v87 = &v149;
              }
              tip2::test_data_control<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>>(v87);
            }
            ActivationFactory = -2102788087;
          }
        }
      }
      WindowsDeleteString(v118);
      v118 = 0;
LABEL_115:
      v88 = 0;
      if ( (ActivationFactory == -2102788087 || a6) && v126 && v43 < 2 )
      {
        v110 = 0;
        v89 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v126 + 72LL))(v126, &v110);
        if ( v89 >= 0 )
          v89 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v110);
        if ( a6 )
        {
          ActivationFactory = v89;
        }
        else
        {
          if ( v89 >= 0 )
            ActivationFactory = 0;
          v90 = COmaDmLogger::GetLogger();
          COmaDmLogger::LogDmGetAadUserTokenRetryOnExpiration(v90, v45, a5, v89, &FileTime2, &SystemTimeAsFileTime);
          v88 = v89 >= 0;
        }
        v91 = v110;
        if ( v110 )
        {
          v110 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v91 + 16LL))(v91);
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl'::`2'::impl)
        && ActivationFactory == -2102788087
        && v43 >= 2 )
      {
        v92 = COmaDmLogger::GetLogger();
        COmaDmLogger::LogDmGetAadUserTokenReturnExpiredToken(
          v92,
          v45,
          a5,
          &FileTime2,
          &SystemTimeAsFileTime,
          (char)pvData);
        ActivationFactory = 0;
      }
      v93 = v128;
      if ( v128 )
      {
        v128 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v93 + 16LL))(v93);
      }
      if ( !v88 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_OmadmClient_AadTokenExpiration>::GetImpl'::`2'::impl)
          && v124 )
        {
          v94 = v124 + 8;
          wil::EnterCriticalSection(&v149, v124 + 200);
          *(_DWORD *)(v94 + 64) |= 0x300u;
          if ( *(_QWORD *)(v94 + 240) )
            tip2::details::shared_data<0,0,0>::complete_helper(v94, 2);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v149);
        }
        v95 = v139;
        if ( v139 )
        {
          if ( ActivationFactory >= 0 )
          {
            ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v134 + 48LL))(v134, &v137);
            if ( ActivationFactory >= 0 )
            {
              v115 = 0;
              v96 = WindowsGetStringRawBuffer(v137, &v115);
              if ( v96 && v115 )
                ActivationFactory = CopyString(v96, 0xFFFFFFFF, v95);
              else
                ActivationFactory = -2147418113;
            }
          }
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OmadmClientAadTokenExpirationTipTest,_tip_OmadmClientAadTokenExpirationTipTest>,wil::err_returncode_policy>(&v124);
        v98 = a4;
        v99 = v136;
        v100 = v140;
        goto LABEL_166;
      }
    }
  }
  catch ( ... )
  {
    pcbData = wil::ResultFromCaughtException(v97);
    v44 = a6;
    ActivationFactory = pcbData;
    v100 = v141;
    v98 = v113;
    v99 = (unsigned __int16 **)v138;
  }
LABEL_166:
  if ( ppv && v111 )
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, v142);
  if ( ActivationFactory < 0 )
  {
    v101 = COmaDmLogger::GetLogger();
    if ( v44 )
    {
      COmaDmLogger::LogDmInvalidateAadUserTokenFailure(v101, v98, a5, ActivationFactory);
    }
    else if ( v99 )
    {
      COmaDmLogger::LogDmGetAadDeviceMdmResourceUrlFailure(v101, v100, ActivationFactory, v116, v119);
    }
    else
    {
      COmaDmLogger::LogDmGetAadUserTokenFailure(v101, v98, a5, ActivationFactory, v116, v119);
      if ( (unsigned int)dword_180102138 > 5 )
      {
        v138 = WindowsGetStringRawBuffer(v129, 0);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (unsigned int)&dword_180102138,
          (unsigned int)&word_1800EA986,
          v102,
          v103,
          (__int64)&v138);
      }
    }
  }
  Windows::Internal::String::~String((Windows::Internal::String *)&v137);
  WindowsDeleteString(v129);
  v129 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v125);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v132);
  v104 = v126;
  if ( v126 )
  {
    v126 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  }
  v105 = v120;
  if ( v120 )
  {
    v120 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v135);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v122);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800759c0  mov     r11, rsp
0x1800759c3  push    rbx
0x1800759c4  push    rsi
0x1800759c5  push    rdi
0x1800759c6  push    r12
0x1800759c8  push    r13
0x1800759ca  push    r14
0x1800759cc  push    r15
0x1800759ce  sub     rsp, 270h
0x1800759d5  mov     rax, cs:__security_cookie
0x1800759dc  xor     rax, rsp
0x1800759df  mov     [rsp+2A8h+var_40], rax
0x1800759e7  mov     al, r9b
0x1800759ea  mov     [rsp+2A8h+var_268], al
0x1800759ee  mov     [r11-178h], r8
0x1800759f5  mov     [rsp+2A8h+sourceString], rdx
0x1800759fd  mov     rbx, rcx
0x180075a00  mov     [r11-170h], r8
0x180075a07  mov     [rsp+2A8h+var_248], al
0x180075a0b  mov     r13, [rsp+2A8h+arg_30]
0x180075a13  mov     rax, [rsp+2A8h+arg_38]
0x180075a1b  mov     [rsp+2A8h+var_180], rax
0x180075a23  mov     rax, [rsp+2A8h+arg_40]
0x180075a2b  mov     [rsp+2A8h+var_198], rax
0x180075a33  mov     [rsp+2A8h+var_188], rax
0x180075a3b  mov     rax, [rsp+2A8h+arg_48]
0x180075a43  mov     [rsp+2A8h+var_160], rax
0x180075a4b  xor     r15d, r15d
0x180075a4e  mov     [r11-208h], r15
0x180075a55  mov     [r11-1A0h], r15
0x180075a5c  mov     [r11-210h], r15
0x180075a63  mov     [r11-1B0h], r15
0x180075a6a  mov     [r11-218h], r15
0x180075a71  mov     [r11-148h], r15
0x180075a78  mov     [r11-1E8h], r15
0x180075a7f  mov     [r11-1B8h], r15
0x180075a86  mov     [r11-1A8h], r15
0x180075a8d  mov     [r11-1F0h], r15
0x180075a94  mov     [r11-1C8h], r15
0x180075a9b  mov     [r11-168h], r15
0x180075aa2  mov     [rsp+2A8h+var_258], r15b
0x180075aa7  mov     [rsp+2A8h+var_234], r15d
0x180075aac  mov     [r11-220h], r15d
0x180075ab3  mov     [r11-1D0h], r15
0x180075aba  lea     rcx, [r11-0C0h]; string
0x180075ac1  call    ??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[26])
0x180075ac6  lea     r9, [rsp+2A8h+string]; string
0x180075ace  lea     r8, [rsp+2A8h+hstringHeader]; hstringHeader
0x180075ad6  xor     edx, edx; length
0x180075ad8  lea     rcx, pszSrc; sourceString
0x180075adf  call    cs:__imp_WindowsCreateStringReference
0x180075ae6  nop     dword ptr [rax+rax+00h]
0x180075aeb  lea     edi, [r15+1]
0x180075aef  mov     r14d, 0C000000Dh
0x180075af5  test    eax, eax
0x180075af7  jns     short loc_180075B10
0x180075af9  xor     r9d, r9d; lpArguments
0x180075afc  xor     r8d, r8d; nNumberOfArguments
0x180075aff  mov     edx, edi; dwExceptionFlags
0x180075b01  mov     ecx, r14d; dwExceptionCode
0x180075b04  call    cs:__imp_RaiseException
0x180075b0b  nop     dword ptr [rax+rax+00h]
0x180075b10  mov     [rsp+2A8h+length], r15d
0x180075b15  or      r12, 0FFFFFFFFFFFFFFFFh
0x180075b19  mov     rcx, r12
0x180075b1c  inc     rcx; unsigned __int64
0x180075b1f  cmp     [rbx+rcx*2], r15w
0x180075b24  jnz     short loc_180075B1C
0x180075b26  lea     rdx, [rsp+2A8h+length]; unsigned int *
0x180075b2b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180075b30  test    eax, eax
0x180075b32  jns     short loc_180075B4B
0x180075b34  xor     r9d, r9d; lpArguments
0x180075b37  xor     r8d, r8d; nNumberOfArguments
0x180075b3a  mov     edx, edi; dwExceptionFlags
0x180075b3c  mov     ecx, r14d; dwExceptionCode
0x180075b3f  call    cs:__imp_RaiseException
0x180075b46  nop     dword ptr [rax+rax+00h]
0x180075b4b  lea     r9, [rsp+2A8h+var_A0]; string
0x180075b53  lea     r8, [rsp+2A8h+var_98]; hstringHeader
0x180075b5b  mov     edx, [rsp+2A8h+length]; length
0x180075b5f  mov     rcx, rbx; sourceString
0x180075b62  call    cs:__imp_WindowsCreateStringReference
0x180075b69  nop     dword ptr [rax+rax+00h]
0x180075b6e  lea     r9, [rsp+2A8h+var_60]; string
0x180075b76  lea     r8, [rsp+2A8h+var_58]; hstringHeader
0x180075b7e  mov     edx, 10h; length
0x180075b83  lea     rcx, aClientTokentyp; "client_TokenType"
0x180075b8a  call    cs:__imp_WindowsCreateStringReference
0x180075b91  nop     dword ptr [rax+rax+00h]
0x180075b96  test    eax, eax
0x180075b98  jns     short loc_180075BB1
0x180075b9a  xor     r9d, r9d; lpArguments
0x180075b9d  xor     r8d, r8d; nNumberOfArguments
0x180075ba0  mov     edx, edi; dwExceptionFlags
0x180075ba2  mov     ecx, r14d; dwExceptionCode
0x180075ba5  call    cs:__imp_RaiseException
0x180075bac  nop     dword ptr [rax+rax+00h]
0x180075bb1  lea     r9, [rsp+2A8h+var_80]; string
0x180075bb9  lea     r8, [rsp+2A8h+var_78]; hstringHeader
0x180075bc1  mov     edx, 0Ah; length
0x180075bc6  lea     rcx, aDeviceauth; "DeviceAuth"
0x180075bcd  call    cs:__imp_WindowsCreateStringReference
0x180075bd4  nop     dword ptr [rax+rax+00h]
0x180075bd9  test    eax, eax
0x180075bdb  jns     short loc_180075BF4
0x180075bdd  xor     r9d, r9d; lpArguments
0x180075be0  xor     r8d, r8d; nNumberOfArguments
0x180075be3  mov     edx, edi; dwExceptionFlags
0x180075be5  mov     ecx, r14d; dwExceptionCode
0x180075be8  call    cs:__imp_RaiseException
0x180075bef  nop     dword ptr [rax+rax+00h]
0x180075bf4  mov     [rsp+2A8h+var_190], r15
0x180075bfc  mov     [rsp+2A8h+var_238], r15d
0x180075c01  mov     [rsp+2A8h+var_267], r15b
0x180075c06  lea     rcx, [rsp+2A8h+var_1C8]
0x180075c0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075c13  lea     rax, [rsp+2A8h+var_1C8]
0x180075c1b  mov     [rsp+2A8h+ppv], rax; ppv
0x180075c20  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180075c27  mov     r8d, edi; dwClsContext
0x180075c2a  xor     edx, edx; pUnkOuter
0x180075c2c  lea     rcx, CLSID_GlobalOptions; rclsid
0x180075c33  call    cs:__imp_CoCreateInstance
0x180075c3a  nop     dword ptr [rax+rax+00h]
0x180075c3f  mov     esi, eax
0x180075c41  test    eax, eax
0x180075c43  js      short loc_180075C8F
0x180075c45  mov     rcx, [rsp+2A8h+var_1C8]
0x180075c4d  mov     rax, [rcx]
0x180075c50  lea     r8, [rsp+2A8h+var_168]
0x180075c58  mov     edx, 5
0x180075c5d  mov     rax, [rax+20h]
0x180075c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c66  mov     esi, eax
0x180075c68  test    eax, eax
0x180075c6a  js      short loc_180075C8F
0x180075c6c  mov     rcx, [rsp+2A8h+var_1C8]
0x180075c74  mov     rax, [rcx]
0x180075c77  mov     r8, rdi
0x180075c7a  mov     edx, 5
0x180075c7f  mov     rax, [rax+18h]
0x180075c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c88  mov     esi, eax
0x180075c8a  mov     [rsp+2A8h+var_258], dil
0x180075c8f  test    esi, esi
0x180075c91  js      loc_180075F61
0x180075c97  lea     rcx, [rsp+2A8h+var_100]; string
0x180075c9f  call    ??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[70])
0x180075ca4  lea     rdx, [rsp+2A8h+var_208]
0x180075cac  mov     rcx, [rax]
0x180075caf  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x180075cb4  mov     esi, eax
0x180075cb6  test    eax, eax
0x180075cb8  js      loc_180075F61
0x180075cbe  mov     qword ptr [rsp+2A8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180075cc3  cmp     [rsp+2A8h+arg_20], r15b
0x180075ccb  jnz     short loc_180075D02
0x180075ccd  mov     rdi, [rsp+2A8h+var_208]
0x180075cd5  mov     rax, [rdi]
0x180075cd8  mov     rbx, [rax+58h]
0x180075cdc  lea     rcx, [rsp+2A8h+SystemTimeAsFileTime]
0x180075ce1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075ce6  lea     r8, [rsp+2A8h+SystemTimeAsFileTime]
0x180075ceb  mov     rdx, [rsp+2A8h+var_C0]
0x180075cf3  mov     rcx, rdi
0x180075cf6  mov     rax, rbx
0x180075cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cfe  mov     esi, eax
0x180075d00  jmp     short loc_180075D76
0x180075d02  mov     [rsp+2A8h+var_260], r15
0x180075d07  mov     rbx, [rsp+2A8h+var_208]
0x180075d0f  mov     rax, [rbx]
0x180075d12  mov     rdi, [rax]
0x180075d15  lea     rcx, [rsp+2A8h+var_260]
0x180075d1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075d1f  lea     r8, [rsp+2A8h+var_260]
0x180075d24  lea     rdx, _GUID_54e633fe_96e0_41e8_9832_1298897c2aaf
0x180075d2b  mov     rcx, rbx
0x180075d2e  mov     rax, rdi
0x180075d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d36  mov     esi, eax
0x180075d38  test    eax, eax
0x180075d3a  js      short loc_180075D6C
0x180075d3c  mov     rdi, [rsp+2A8h+var_260]
0x180075d41  mov     rax, [rdi]
0x180075d44  mov     rbx, [rax+40h]
0x180075d48  lea     rcx, [rsp+2A8h+SystemTimeAsFileTime]
0x180075d4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075d52  lea     r8, [rsp+2A8h+SystemTimeAsFileTime]
0x180075d57  mov     rdx, [rsp+2A8h+var_C0]
0x180075d5f  mov     rcx, rdi
0x180075d62  mov     rax, rbx
0x180075d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d6a  mov     esi, eax
0x180075d6c  lea     rcx, [rsp+2A8h+var_260]
0x180075d71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075d76  test    esi, esi
0x180075d78  js      short loc_180075D8E
0x180075d7a  lea     rdx, [rsp+2A8h+var_1B0]
0x180075d82  mov     rcx, qword ptr [rsp+2A8h+SystemTimeAsFileTime.dwLowDateTime]
0x180075d87  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x180075d8c  mov     esi, eax
0x180075d8e  lea     rcx, [rsp+2A8h+SystemTimeAsFileTime]
0x180075d93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075d98  test    esi, esi
0x180075d9a  js      loc_180075F61
0x180075da0  mov     eax, 82AA000Eh
0x180075da5  cmp     [rsp+2A8h+var_1B0], r15
0x180075dad  cmovz   esi, eax
0x180075db0  test    esi, esi
0x180075db2  js      loc_180075F61
0x180075db8  lea     rcx, [rsp+2A8h+var_100]; string
0x180075dc0  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x180075dc5  mov     rbx, [rax]
0x180075dc8  lea     rcx, [rsp+2A8h+var_1A0]
0x180075dd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075dd5  lea     r8, [rsp+2A8h+var_1A0]
0x180075ddd  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x180075de4  mov     rcx, rbx
0x180075de7  call    cs:__imp_RoGetActivationFactory
0x180075dee  nop     dword ptr [rax+rax+00h]
0x180075df3  mov     esi, eax
0x180075df5  test    eax, eax
0x180075df7  js      loc_180075F61
0x180075dfd  mov     rdi, [rsp+2A8h+var_1A0]
0x180075e05  mov     rax, [rdi]
0x180075e08  mov     rbx, [rax+38h]
0x180075e0c  lea     rcx, [rsp+2A8h+var_210]
0x180075e14  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180075e19  lea     rax, [rsp+2A8h+var_210]
0x180075e21  mov     [rsp+2A8h+pvData], rax
0x180075e26  mov     dword ptr [rsp+2A8h+ppv], r15d
0x180075e2b  mov     r9, [rsp+2A8h+var_A0]
0x180075e33  mov     r8, [rsp+2A8h+string]
0x180075e3b  mov     rdx, [rsp+2A8h+var_1B0]
0x180075e43  mov     rcx, rdi
0x180075e46  mov     rax, rbx
0x180075e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e4e  mov     esi, eax
0x180075e50  test    eax, eax
0x180075e52  js      loc_180075F61
0x180075e58  mov     rcx, [rsp+2A8h+var_210]
0x180075e60  mov     rax, [rcx]
0x180075e63  lea     rdx, [rsp+2A8h+var_218]
0x180075e6b  mov     rax, [rax+50h]
0x180075e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e74  mov     esi, eax
0x180075e76  test    eax, eax
0x180075e78  js      loc_180075F61
0x180075e7e  cmp     [rsp+2A8h+arg_20], r15b
0x180075e86  jz      short loc_180075EBB
0x180075e88  mov     rcx, [rsp+2A8h+var_218]
0x180075e90  mov     rax, [rcx]
0x180075e93  lea     r9, [rsp+2A8h+var_267]
0x180075e98  mov     r8, [rsp+2A8h+var_80]
0x180075ea0  mov     rdx, [rsp+2A8h+var_60]
0x180075ea8  mov     rax, [rax+50h]
0x180075eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075eb1  mov     esi, eax
0x180075eb3  test    eax, eax
0x180075eb5  js      loc_180075F61
0x180075ebb  mov     rcx, [rsp+2A8h+var_218]
0x180075ec3  mov     rax, [rcx]
0x180075ec6  lea     r9, [rsp+2A8h+var_267]
0x180075ecb  mov     r8, [rsp+2A8h+string]
0x180075ed3  mov     rdx, [rsp+2A8h+var_C0]
0x180075edb  mov     rax, [rax+50h]
0x180075edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075ee4  mov     esi, eax
0x180075ee6  test    eax, eax
0x180075ee8  js      short loc_180075F61
0x180075eea  cmp     [rsp+2A8h+var_178], r15
0x180075ef2  jz      short loc_180075F61
0x180075ef4  mov     rsi, [rsp+2A8h+var_218]
0x180075efc  mov     rax, [rsi]
0x180075eff  mov     rdi, [rax+50h]
0x180075f03  lea     rdx, [rsp+2A8h+var_170]
0x180075f0b  lea     rcx, [rsp+2A8h+var_100]
0x180075f13  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180075f18  nop
0x180075f19  mov     rbx, [rax+18h]
0x180075f1d  mov     [rsp+2A8h+var_108], r15
0x180075f25  mov     r9d, 12h; unsigned int
0x180075f2b  lea     r8d, [r9+1]; unsigned int
0x180075f2f  lea     rdx, aCloudassignedm; "CloudAssignedMdmId"
0x180075f36  lea     rcx, [rsp+2A8h+var_120]; hstringHeader
0x180075f3e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180075f43  nop
0x180075f44  lea     r9, [rsp+2A8h+var_267]
0x180075f49  mov     r8, rbx
0x180075f4c  mov     rdx, [rsp+2A8h+var_108]
0x180075f54  mov     rcx, rsi
0x180075f57  mov     rax, rdi
0x180075f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f5f  mov     esi, eax
0x180075f61  mov     [rsp+2A8h+length], r15d
0x180075f66  mov     [rsp+2A8h+var_200], 4
0x180075f71  test    esi, esi
0x180075f73  js      loc_1800761D8
  ... truncated ...
```
