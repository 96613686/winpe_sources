# OneCore::Base::Telemetry::DeviceTicket::GetTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18009f5fc`
- end: `0x1800a1077`
- name: `?GetTicket@DeviceTicket@Telemetry@Base@OneCore@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `6779`
- prototype: `__int64 __fastcall(PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009cf6c`

## callees

- `0x180008570`
- `0x180010ffc`
- `0x180012bdc`
- `0x1800726b4`
- `0x18008fadc`
- `0x1800948e8`
- `0x18009b6d4`
- `0x18009f5fc`
- `0x1800a42d8`
- `0x1800a4d48`
- `0x1802174e4`
- `0x1802174f0`
- `0x18021f010`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x18009f9e6`
- `KERNEL32!CreateEventExW` at `0x18009f9e6`
- `KERNEL32!CloseHandle` at `0x18009fa14`
- `KERNEL32!CloseHandle` at `0x18009fab1`
- `KERNEL32!CloseHandle` at `0x18009fb9c`
- `KERNEL32!CloseHandle` at `0x18009fc9d`
- `KERNEL32!CloseHandle` at `0x18009fd8d`
- `KERNEL32!CloseHandle` at `0x18009ff3a`
- `KERNEL32!CloseHandle` at `0x1800a0058`
- `KERNEL32!CloseHandle` at `0x1800a0192`
- `KERNEL32!CloseHandle` at `0x1800a02fc`
- `KERNEL32!CloseHandle` at `0x1800a047e`
- `KERNEL32!CloseHandle` at `0x1800a0613`
- `KERNEL32!CloseHandle` at `0x1800a0798`
- `KERNEL32!CloseHandle` at `0x1800a0901`
- `KERNEL32!CloseHandle` at `0x1800a0a9c`
- `KERNEL32!CloseHandle` at `0x1800a0cc3`
- `KERNEL32!CloseHandle` at `0x1800a0dc7`
- `KERNEL32!CloseHandle` at `0x1800a0edb`
- `KERNEL32!CloseHandle` at `0x18009fa14`
- `KERNEL32!CloseHandle` at `0x18009fab1`
- `KERNEL32!CloseHandle` at `0x18009fb9c`
- `KERNEL32!CloseHandle` at `0x18009fc9d`
- `KERNEL32!CloseHandle` at `0x18009fd8d`
- `KERNEL32!CloseHandle` at `0x18009ff3a`
- `KERNEL32!CloseHandle` at `0x1800a0058`
- `KERNEL32!CloseHandle` at `0x1800a0192`
- `KERNEL32!CloseHandle` at `0x1800a02fc`
- `KERNEL32!CloseHandle` at `0x1800a047e`
- `KERNEL32!CloseHandle` at `0x1800a0613`
- `KERNEL32!CloseHandle` at `0x1800a0798`
- `KERNEL32!CloseHandle` at `0x1800a0901`
- `KERNEL32!CloseHandle` at `0x1800a0a9c`
- `KERNEL32!CloseHandle` at `0x1800a0cc3`
- `KERNEL32!CloseHandle` at `0x1800a0dc7`
- `KERNEL32!CloseHandle` at `0x1800a0edb`
- `KERNEL32!GetLastError` at `0x18009f9f8`
- `KERNEL32!GetLastError` at `0x18009fa08`
- `KERNEL32!GetLastError` at `0x18009f9f8`
- `KERNEL32!GetLastError` at `0x18009fa08`
- `KERNEL32!SetLastError` at `0x18009fa2d`
- `KERNEL32!SetLastError` at `0x18009fa2d`
- `OLE32!CoWaitForMultipleHandles` at `0x18009fe77`
- `OLE32!CoWaitForMultipleHandles` at `0x18009fe77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f786`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009f786`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f7b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f7ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f85d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f86e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f99e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f9af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009faff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fb10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fbea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fbfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fcfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fdec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ff88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ff99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a00a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a00b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a01e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a01f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a034a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a035b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a04cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a04dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a07e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a07f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a094f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a09d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0aea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0afb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0b8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0c00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0d11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0d22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0e15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0e26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0f29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0f3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f7b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f7ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f85d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f86e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f99e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f9af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009faff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fb10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fbea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fbfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fceb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fcfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fdec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ff88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ff99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a00a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a00b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a01e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a01f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a034a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a035b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a04cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a04dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a07e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a07f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a094f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0960`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a09d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0aea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0afb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0b8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0c00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0d11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0d22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0e15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0e26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0f29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a0f3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a0b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009f652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009f8bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009f652`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009f8bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009f674`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009f674`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18009f8e1`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18009f8e1`

## string_xrefs

- `0x1800a0fd2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18009f8b5`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x18009f64b`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=156
__int64 __fastcall OneCore::Base::Telemetry::DeviceTicket::GetTicket(PCNZWCH sourceString, char *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  const char *v8; // r9
  unsigned int v9; // edi
  _WORD *v10; // rcx
  __int64 result; // rax
  const WCHAR *v12; // rcx
  HRESULT v13; // eax
  unsigned int v14; // edi
  PCNZWCH v15; // rcx
  HRESULT v16; // eax
  unsigned int v17; // edi
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // edi
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  int v24; // edi
  void *v25; // rdx
  HANDLE Event; // rdi
  unsigned int v27; // r8d
  const char *v28; // r9
  HANDLE v29; // r14
  DWORD LastError; // r15d
  BOOL v31; // eax
  unsigned int v32; // r8d
  const char *v33; // r9
  wil::details::in1diag3 *v34; // rcx
  __int64 *v35; // rax
  __int64 v36; // rdi
  HSTRING v37; // rcx
  unsigned int v38; // r8d
  int v39; // eax
  unsigned int v40; // esi
  unsigned int v41; // r8d
  __int64 v42; // rax
  int v43; // eax
  unsigned int v44; // esi
  unsigned int v45; // r8d
  int v46; // eax
  unsigned int v47; // esi
  unsigned int v48; // r8d
  int v49; // eax
  int v50; // eax
  unsigned int v51; // esi
  int v52; // eax
  void *v53; // rdx
  unsigned int v54; // r8d
  unsigned int v55; // r8d
  unsigned int v56; // esi
  int v57; // eax
  void *v58; // rdx
  unsigned int v59; // r8d
  unsigned int v60; // r8d
  int v61; // eax
  unsigned int v62; // esi
  int v63; // eax
  void *v64; // rdx
  unsigned int v65; // r8d
  unsigned int v66; // r8d
  __int64 v67; // rax
  int v68; // eax
  unsigned int v69; // esi
  int v70; // eax
  void *v71; // rdx
  unsigned int v72; // r8d
  unsigned int v73; // r8d
  __int64 *v74; // rcx
  __int64 v75; // rax
  int v76; // eax
  unsigned int v77; // esi
  int v78; // eax
  void *v79; // rdx
  unsigned int v80; // r8d
  unsigned int v81; // r8d
  __int64 v82; // rax
  int v83; // eax
  unsigned int v84; // esi
  int v85; // eax
  void *v86; // rdx
  unsigned int v87; // r8d
  unsigned int v88; // r8d
  int v89; // eax
  unsigned int v90; // esi
  int v91; // eax
  void *v92; // rdx
  unsigned int v93; // r8d
  unsigned int v94; // r8d
  DWORD v95; // esi
  int v96; // eax
  void *v97; // rdx
  unsigned int v98; // r8d
  unsigned int v99; // r8d
  __int64 v100; // rax
  int v101; // eax
  unsigned int v102; // esi
  int v103; // eax
  void *v104; // rdx
  unsigned int v105; // r8d
  unsigned int v106; // r8d
  PCWSTR StringRawBuffer; // rax
  __int64 v108; // r8
  unsigned __int64 v109; // rdx
  char *v110; // rsi
  __int64 v111; // rbx
  int v112; // eax
  void *v113; // rdx
  unsigned int v114; // r8d
  unsigned int v115; // r8d
  int v116; // eax
  void *v117; // rdx
  unsigned int v118; // r8d
  unsigned int v119; // r8d
  int v120; // eax
  void *v121; // rdx
  unsigned int v122; // r8d
  unsigned int v123; // r8d
  int lpdwindex; // [rsp+20h] [rbp-E8h]
  int lpdwindexa; // [rsp+20h] [rbp-E8h]
  int lpdwindexb; // [rsp+20h] [rbp-E8h]
  int lpdwindexc; // [rsp+20h] [rbp-E8h]
  int lpdwindexd; // [rsp+20h] [rbp-E8h]
  int lpdwindexe; // [rsp+20h] [rbp-E8h]
  int lpdwindexf; // [rsp+20h] [rbp-E8h]
  int lpdwindexg; // [rsp+20h] [rbp-E8h]
  int lpdwindexh; // [rsp+20h] [rbp-E8h]
  int lpdwindexi; // [rsp+20h] [rbp-E8h]
  int lpdwindexj; // [rsp+20h] [rbp-E8h]
  int lpdwindexk; // [rsp+20h] [rbp-E8h]
  int lpdwindexl; // [rsp+20h] [rbp-E8h]
  __int64 v137; // [rsp+30h] [rbp-D8h] BYREF
  _QWORD *v138; // [rsp+38h] [rbp-D0h] BYREF
  HSTRING v139; // [rsp+40h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v141; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING v142; // [rsp+58h] [rbp-B0h] BYREF
  __int64 *v143; // [rsp+60h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-A0h] BYREF
  DWORD dwindex; // [rsp+70h] [rbp-98h] BYREF
  HSTRING v146; // [rsp+78h] [rbp-90h] BYREF
  __int64 *v147; // [rsp+80h] [rbp-88h] BYREF
  __int64 *v148; // [rsp+88h] [rbp-80h] BYREF
  __int128 v149; // [rsp+90h] [rbp-78h] BYREF
  int v150; // [rsp+A0h] [rbp-68h] BYREF
  int v151; // [rsp+A4h] [rbp-64h] BYREF
  __int64 v152; // [rsp+A8h] [rbp-60h]
  __int64 v153; // [rsp+B0h] [rbp-58h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-50h] BYREF
  HSTRING v155; // [rsp+D0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v152 = -2;
  v138 = 0;
  v155 = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
         0x45u,
         &hstringHeader,
         &v155);
  try
  {
    if ( v4 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    }
    else
    {
      ActivationFactory = RoGetActivationFactory(v155, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v138);
      v9 = ActivationFactory;
      if ( ActivationFactory == -2147221164 )
      {
        if ( *((_QWORD *)a2 + 3) <= 7u )
          v10 = a2;
        else
          v10 = *(_WORD **)a2;
        *((_QWORD *)a2 + 2) = 0;
        *v10 = 0;
        if ( v138 )
          (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
        return 0;
      }
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
          (const char *)(unsigned int)ActivationFactory,
          lpdwindex);
        if ( v138 )
          (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
        return v9;
      }
      string = 0;
      if ( *((_QWORD *)sourceString + 3) <= 7u )
        v12 = sourceString;
      else
        v12 = *(const WCHAR **)sourceString;
      v13 = WindowsCreateString(v12, *((_DWORD *)sourceString + 4), &string);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
          (const char *)(unsigned int)v13,
          lpdwindex);
        if ( string )
          WindowsDeleteString(string);
        if ( v138 )
          (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
        return v14;
      }
      v142 = 0;
      v15 = sourceString + 16;
      if ( *((_QWORD *)sourceString + 7) > 7u )
        v15 = *(PCNZWCH *)v15;
      v16 = WindowsCreateString(v15, *((_DWORD *)sourceString + 12), &v142);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
          (const char *)(unsigned int)v16,
          lpdwindex);
        if ( v142 )
          WindowsDeleteString(v142);
        if ( string )
          WindowsDeleteString(string);
        if ( v138 )
          (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
        return v17;
      }
      v141 = 0;
      v18 = *v138;
      v141 = 0;
      v19 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING, __int64 *))(v18 + 48))(v138, string, v142, &v141);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB0,
          (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
          (const char *)(unsigned int)v19,
          lpdwindex);
        if ( v141 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
        if ( v142 )
          WindowsDeleteString(v142);
        if ( string )
          WindowsDeleteString(string);
        if ( v138 )
          (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
        return v20;
      }
      v139 = 0;
      v155 = 0;
      v21 = WindowsCreateStringReference(
              L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
              0x41u,
              &hstringHeader,
              &v155);
      if ( v21 >= 0 )
      {
        v139 = 0;
        v146 = 0;
        v24 = RoActivateInstance(v155, &v146);
        if ( v24 >= 0 )
        {
          if ( !memcmp_0(&GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
          {
            v139 = v146;
          }
          else
          {
            v24 = (**(__int64 (__fastcall ***)(HSTRING, GUID *, HSTRING *))v146)(
                    v146,
                    &GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb,
                    &v139);
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v146 + 16LL))(v146);
          }
        }
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB5,
            (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
            (const char *)(unsigned int)v24,
            lpdwindex);
          if ( v139 )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
          if ( v141 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
          if ( v142 )
            WindowsDeleteString(v142);
          if ( string )
            WindowsDeleteString(string);
          if ( v138 )
            (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
          return (unsigned int)v24;
        }
        hObject = 0;
        Event = CreateEventExW(0, 0, 0, 0x1F0003u);
        if ( !Event )
          wil::details::in1diag3::Throw_GetLastError(retaddr, v25, v27, v28);
        GetLastError();
        v29 = hObject;
        if ( !hObject )
        {
LABEL_64:
          hObject = Event;
          *(_QWORD *)&v149 = Event;
          v35 = (__int64 *)Microsoft::WRL::Details::Make<OneCore::Base::Telemetry::AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>,void *>(
                             &v146,
                             &v149);
          v36 = *v35;
          *v35 = 0;
          v153 = v36;
          v37 = v146;
          if ( v146 )
          {
            v146 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v37 + 16LL))(v37);
          }
          if ( !v36 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)0x8007000ELL,
              lpdwindex);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v138 + 16LL))(v138, *v138);
            return 2147942414LL;
          }
          v149 = *((_OWORD *)sourceString + 4);
          v39 = (*(__int64 (__fastcall **)(HSTRING, __int128 *))(*(_QWORD *)v139 + 72LL))(v139, &v149);
          v40 = v39;
          if ( v39 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBD,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)(unsigned int)v39,
              lpdwindex);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v41, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
            return v40;
          }
          v143 = 0;
          v42 = *(_QWORD *)v139;
          v143 = 0;
          v43 = (*(__int64 (__fastcall **)(HSTRING, __int64, __int64 **))(v42 + 56))(v139, v141, &v143);
          v44 = v43;
          if ( v43 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC2,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)(unsigned int)v43,
              lpdwindex);
            if ( v143 )
              (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v45, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
            return v44;
          }
          v46 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v143 + 48))(v143, v36);
          v47 = v46;
          if ( v46 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC3,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)(unsigned int)v46,
              lpdwindex);
            if ( v143 )
              (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v48, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
            return v47;
          }
          v137 = 0;
          v49 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*v143)(
                  v143,
                  &GUID_00000036_0000_0000_c000_000000000046,
                  &v137);
          if ( v49 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v49,
              lpdwindex);
          hstringHeader.Reserved.Reserved1 = &v137;
          hstringHeader.Reserved.Reserved2[8] = 1;
          dwindex = 0;
          while ( CoWaitForMultipleHandles(0x18u, 0x64u, 1u, &hObject, &dwindex) == -2147417835 )
            ;
          v150 = 0;
          v50 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v137 + 64LL))(v137, &v150);
          v51 = v50;
          if ( v50 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xDA,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)(unsigned int)v50,
              lpdwindexa);
            v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
            if ( v52 < 0 )
              wil::details::in1diag3::_Log_Hr(retaddr, v53, v54, (const char *)(unsigned int)v52, lpdwindexb);
            if ( v137 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
            if ( v143 )
              (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v55, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
            return v51;
          }
          v56 = v150;
          if ( v150 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xDB,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)(unsigned int)v150,
              lpdwindexa);
            v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
            if ( v57 < 0 )
              wil::details::in1diag3::_Log_Hr(retaddr, v58, v59, (const char *)(unsigned int)v57, lpdwindexc);
            if ( v137 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
            if ( v143 )
              (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v60, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v138 + 16LL))(v138, *v138);
            return v56;
          }
          v151 = 0;
          v61 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v137 + 56LL))(v137, &v151);
          v62 = v61;
          if ( v61 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xDF,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)(unsigned int)v61,
              lpdwindexa);
            v63 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
            if ( v63 < 0 )
              wil::details::in1diag3::_Log_Hr(retaddr, v64, v65, (const char *)(unsigned int)v63, lpdwindexd);
            if ( v137 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
            if ( v143 )
              (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v66, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
            return v62;
          }
          if ( v151 == 1 )
          {
            v147 = 0;
            v67 = *v143;
            v147 = 0;
            v68 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v67 + 64))(v143, &v147);
            v69 = v68;
            if ( v68 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE4,
                (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
                (const char *)(unsigned int)v68,
                lpdwindexa);
              if ( v147 )
                (*(void (__fastcall **)(__int64 *))(*v147 + 16))(v147);
              v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
              if ( v70 < 0 )
                wil::details::in1diag3::_Log_Hr(retaddr, v71, v72, (const char *)(unsigned int)v70, lpdwindexe);
              if ( v137 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
              if ( v143 )
                (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( hObject && !CloseHandle(hObject) )
                wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v73, v8);
              if ( v139 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
              if ( v141 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
              if ( v142 )
                WindowsDeleteString(v142);
              if ( string )
                WindowsDeleteString(string);
              if ( v138 )
                (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
              return v69;
            }
            v74 = v147;
            if ( !v147 )
              goto LABEL_386;
            *(_QWORD *)&v149 = 0;
            v75 = *v147;
            *(_QWORD *)&v149 = 0;
            v76 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v75 + 48))(v147, &v149);
            v77 = v76;
            if ( v76 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xEB,
                (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
                (const char *)(unsigned int)v76,
                lpdwindexa);
              if ( (_QWORD)v149 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v149 + 16LL))(v149);
              if ( v147 )
                (*(void (__fastcall **)(__int64 *))(*v147 + 16))(v147);
              v78 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
              if ( v78 < 0 )
                wil::details::in1diag3::_Log_Hr(retaddr, v79, v80, (const char *)(unsigned int)v78, lpdwindexf);
              if ( v137 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
              if ( v143 )
                (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( hObject && !CloseHandle(hObject) )
                wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v81, v8);
              if ( v139 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
              if ( v141 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
              if ( v142 )
                WindowsDeleteString(v142);
              if ( string )
                WindowsDeleteString(string);
              if ( v138 )
                (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
              return v77;
            }
            v148 = 0;
            v82 = *(_QWORD *)v149;
            v148 = 0;
            v83 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v82 + 48))(v149, 0, &v148);
            v84 = v83;
            if ( v83 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xEE,
                (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
                (const char *)(unsigned int)v83,
                lpdwindexa);
              if ( v148 )
                (*(void (__fastcall **)(__int64 *))(*v148 + 16))(v148);
              if ( (_QWORD)v149 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v149 + 16LL))(v149);
              if ( v147 )
                (*(void (__fastcall **)(__int64 *))(*v147 + 16))(v147);
              v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
              if ( v85 < 0 )
                wil::details::in1diag3::_Log_Hr(retaddr, v86, v87, (const char *)(unsigned int)v85, lpdwindexg);
              if ( v137 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
              if ( v143 )
                (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( hObject && !CloseHandle(hObject) )
                wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v88, v8);
              if ( v139 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
              if ( v141 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
              if ( v142 )
                WindowsDeleteString(v142);
              if ( string )
                WindowsDeleteString(string);
              if ( v138 )
                (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
              return v84;
            }
            dwindex = 0;
            v89 = (*(__int64 (__fastcall **)(__int64 *, DWORD *))(*v148 + 64))(v148, &dwindex);
            v90 = v89;
            if ( v89 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF1,
                (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
                (const char *)(unsigned int)v89,
                lpdwindexa);
              if ( v148 )
                (*(void (__fastcall **)(__int64 *))(*v148 + 16))(v148);
              if ( (_QWORD)v149 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v149 + 16LL))(v149);
              if ( v147 )
                (*(void (__fastcall **)(__int64 *))(*v147 + 16))(v147);
              v91 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
              if ( v91 < 0 )
                wil::details::in1diag3::_Log_Hr(retaddr, v92, v93, (const char *)(unsigned int)v91, lpdwindexh);
              if ( v137 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
              if ( v143 )
                (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( hObject && !CloseHandle(hObject) )
                wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v94, v8);
              if ( v139 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
              if ( v141 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
              if ( v142 )
                WindowsDeleteString(v142);
              if ( string )
                WindowsDeleteString(string);
              if ( v138 )
                (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
              return v90;
            }
            v95 = dwindex;
            if ( (dwindex & 0x80000000) != 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF2,
                (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
                (const char *)dwindex,
                lpdwindexa);
              if ( v148 )
                (*(void (__fastcall **)(__int64 *))(*v148 + 16))(v148);
              if ( (_QWORD)v149 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v149 + 16LL))(v149);
              if ( v147 )
                (*(void (__fastcall **)(__int64 *))(*v147 + 16))(v147);
              v96 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
              if ( v96 < 0 )
                wil::details::in1diag3::_Log_Hr(retaddr, v97, v98, (const char *)(unsigned int)v96, lpdwindexi);
              if ( v137 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
              if ( v143 )
                (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( hObject && !CloseHandle(hObject) )
                wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v99, v8);
              if ( v139 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
              if ( v141 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
              if ( v142 )
                WindowsDeleteString(v142);
              if ( string )
                WindowsDeleteString(string);
              if ( v138 )
                (*(void (__fastcall **)(_QWORD *, _QWORD))(*v138 + 16LL))(v138, *v138);
              return v95;
            }
            v146 = 0;
            v100 = *v148;
            v146 = 0;
            v101 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v100 + 48))(v148, &v146);
            v102 = v101;
            if ( v101 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF5,
                (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
                (const char *)(unsigned int)v101,
                lpdwindexa);
              if ( v146 )
                WindowsDeleteString(v146);
              if ( v148 )
                (*(void (__fastcall **)(__int64 *))(*v148 + 16))(v148);
              if ( (_QWORD)v149 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v149 + 16LL))(v149);
              if ( v147 )
                (*(void (__fastcall **)(__int64 *))(*v147 + 16))(v147);
              v103 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
              if ( v103 < 0 )
                wil::details::in1diag3::_Log_Hr(retaddr, v104, v105, (const char *)(unsigned int)v103, lpdwindexj);
              if ( v137 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
              if ( v143 )
                (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( hObject && !CloseHandle(hObject) )
                wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v106, v8);
              if ( v139 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
              if ( v141 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
              if ( v142 )
                WindowsDeleteString(v142);
              if ( string )
                WindowsDeleteString(string);
              if ( v138 )
                (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
              return v102;
            }
            if ( v146 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(v146, 0);
              v109 = -1;
              do
                ++v109;
              while ( StringRawBuffer[v109] );
              if ( v109 > *((_QWORD *)a2 + 3) )
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  a2,
                  v109,
                  v108,
                  StringRawBuffer);
              }
              else
              {
                if ( *((_QWORD *)a2 + 3) <= 7u )
                  v110 = a2;
                else
                  v110 = *(char **)a2;
                *((_QWORD *)a2 + 2) = v109;
                v111 = 2 * v109;
                memmove_0(v110, StringRawBuffer, 2 * v109);
                *(_WORD *)&v110[v111] = 0;
              }
              if ( v146 )
                WindowsDeleteString(v146);
              if ( v148 )
                (*(void (__fastcall **)(__int64 *))(*v148 + 16))(v148);
              if ( (_QWORD)v149 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v149 + 16LL))(v149);
              v74 = v147;
LABEL_386:
              if ( v74 )
                (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
              v116 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
              if ( v116 < 0 )
                wil::details::in1diag3::_Log_Hr(retaddr, v117, v118, (const char *)(unsigned int)v116, lpdwindexa);
              if ( v137 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
              if ( v143 )
                (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              if ( hObject && !CloseHandle(hObject) )
                wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v119, v8);
              if ( v139 )
                (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
              if ( v141 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
              if ( v142 )
                WindowsDeleteString(v142);
              if ( string )
                WindowsDeleteString(string);
              if ( v138 )
                (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
              return 0;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xFC,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)0x87C51026LL,
              lpdwindexa);
            if ( v146 )
              WindowsDeleteString(v146);
            if ( v148 )
              (*(void (__fastcall **)(__int64 *))(*v148 + 16))(v148);
            if ( (_QWORD)v149 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v149 + 16LL))(v149);
            if ( v147 )
              (*(void (__fastcall **)(__int64 *))(*v147 + 16))(v147);
            v112 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
            if ( v112 < 0 )
              wil::details::in1diag3::_Log_Hr(retaddr, v113, v114, (const char *)(unsigned int)v112, lpdwindexk);
            if ( v137 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
            if ( v143 )
              (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v115, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v138 + 16LL))(v138, *v138);
            return 2277838886LL;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x102,
              (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
              (const char *)0x87C51026LL,
              lpdwindexa);
            v120 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 80LL))(v137);
            if ( v120 < 0 )
              wil::details::in1diag3::_Log_Hr(retaddr, v121, v122, (const char *)(unsigned int)v120, lpdwindexl);
            if ( v137 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 16LL))(v137);
            if ( v143 )
              (*(void (__fastcall **)(__int64 *))(*v143 + 16))(v143);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            if ( hObject && !CloseHandle(hObject) )
              wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v123, v8);
            if ( v139 )
              (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v139 + 16LL))(v139);
            if ( v141 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
            if ( v142 )
              WindowsDeleteString(v142);
            if ( string )
              WindowsDeleteString(string);
            if ( v138 )
              (*(void (__fastcall **)(_QWORD *))(*v138 + 16LL))(v138);
            return 2277838886LL;
          }
        }
        LastError = GetLastError();
        v31 = CloseHandle(v29);
        v34 = retaddr;
        if ( v31 )
        {
          SetLastError(LastError);
          goto LABEL_64;
        }
LABEL_428:
        wil::details::in1diag3::_FailFast_GetLastError(v34, (void *)0xA0B, v32, v33);
      }
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
    goto LABEL_428;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x107,
                           (unsigned int)"onecore\\internal\\base\\inc\\telemetry\\DeviceTicketImp.h",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18009f5fc  mov     r11, rsp
0x18009f5ff  push    rsi
0x18009f600  push    rdi
0x18009f601  push    r12
0x18009f603  push    r14
0x18009f605  push    r15
0x18009f607  sub     rsp, 0E0h
0x18009f60e  mov     qword ptr [r11-60h], 0FFFFFFFFFFFFFFFEh
0x18009f616  mov     [r11+18h], rbx
0x18009f61a  mov     rax, cs:__security_cookie
0x18009f621  xor     rax, rsp
0x18009f624  mov     [rsp+108h+var_30], rax
0x18009f62c  mov     rbx, rdx
0x18009f62f  mov     rsi, rcx
0x18009f632  xor     r12d, r12d
0x18009f635  mov     [rsp+108h+var_D0], r12
0x18009f63a  mov     [r11-38h], r12
0x18009f63e  lea     r9, [r11-38h]; string
0x18009f642  lea     r8, [r11-50h]; hstringHeader
0x18009f646  lea     edx, [r12+45h]; length
0x18009f64b  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18009f652  call    cs:__imp_WindowsCreateStringReference
0x18009f658  test    eax, eax
0x18009f65a  js      loc_1800A0F88
0x18009f660  lea     r8, [rsp+108h+var_D0]
0x18009f665  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x18009f66c  mov     rcx, [rsp+108h+var_38]
0x18009f674  call    cs:__imp_RoGetActivationFactory
0x18009f67a  mov     edi, eax
0x18009f67c  cmp     eax, 80040154h
0x18009f681  jnz     short loc_18009F6B8
0x18009f683  cmp     qword ptr [rbx+18h], 7
0x18009f688  jbe     short loc_18009F68F
0x18009f68a  mov     rcx, [rbx]
0x18009f68d  jmp     short loc_18009F692
0x18009f68f  mov     rcx, rbx
0x18009f692  mov     [rbx+10h], r12
0x18009f696  mov     [rcx], r12w
0x18009f69a  mov     rcx, [rsp+108h+var_D0]
0x18009f69f  test    rcx, rcx
0x18009f6a2  jz      short loc_18009F6B1
0x18009f6a4  mov     rax, [rcx]
0x18009f6a7  mov     rax, [rax+10h]
0x18009f6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6b0  nop
0x18009f6b1  xor     eax, eax
0x18009f6b3  jmp     loc_1800A0F60
0x18009f6b8  test    edi, edi
0x18009f6ba  jns     short loc_18009F6F7
0x18009f6bc  mov     rcx, [rsp+108h]; this
0x18009f6c4  mov     r9d, edi; char *
0x18009f6c7  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\telemetry"...
0x18009f6ce  mov     edx, 0A6h; void *
0x18009f6d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f6d8  nop
0x18009f6d9  mov     rcx, [rsp+108h+var_D0]
0x18009f6de  test    rcx, rcx
0x18009f6e1  jz      short loc_18009F6F0
0x18009f6e3  mov     rax, [rcx]
0x18009f6e6  mov     rax, [rax+10h]
0x18009f6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6ef  nop
0x18009f6f0  mov     eax, edi
0x18009f6f2  jmp     loc_1800A0F60
0x18009f6f7  mov     [rsp+108h+string], r12
0x18009f6fc  cmp     qword ptr [rsi+18h], 7
0x18009f701  jbe     short loc_18009F708
0x18009f703  mov     rcx, [rsi]
0x18009f706  jmp     short loc_18009F70B
0x18009f708  mov     rcx, rsi; sourceString
0x18009f70b  lea     r8, [rsp+108h+string]; string
0x18009f710  mov     edx, [rsi+10h]; length
0x18009f713  call    cs:__imp_WindowsCreateString
0x18009f719  mov     edi, eax
0x18009f71b  test    eax, eax
0x18009f71d  jns     short loc_18009F76B
0x18009f71f  mov     rcx, [rsp+108h]; this
0x18009f727  mov     r9d, eax; char *
0x18009f72a  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\telemetry"...
0x18009f731  mov     edx, 0AAh; void *
0x18009f736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f73b  nop
0x18009f73c  mov     rcx, [rsp+108h+string]; string
0x18009f741  test    rcx, rcx
0x18009f744  jz      short loc_18009F74D
0x18009f746  call    cs:__imp_WindowsDeleteString
0x18009f74c  nop
0x18009f74d  mov     rcx, [rsp+108h+var_D0]
0x18009f752  test    rcx, rcx
0x18009f755  jz      short loc_18009F764
0x18009f757  mov     rax, [rcx]
0x18009f75a  mov     rax, [rax+10h]
0x18009f75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f763  nop
0x18009f764  mov     eax, edi
0x18009f766  jmp     loc_1800A0F60
0x18009f76b  mov     [rsp+108h+var_B0], r12
0x18009f770  lea     rcx, [rsi+20h]
0x18009f774  cmp     qword ptr [rcx+18h], 7
0x18009f779  jbe     short loc_18009F77E
0x18009f77b  mov     rcx, [rcx]; sourceString
0x18009f77e  lea     r8, [rsp+108h+var_B0]; string
0x18009f783  mov     edx, [rsi+30h]; length
0x18009f786  call    cs:__imp_WindowsCreateString
0x18009f78c  mov     edi, eax
0x18009f78e  test    eax, eax
0x18009f790  jns     short loc_18009F7EF
0x18009f792  mov     rcx, [rsp+108h]; this
0x18009f79a  mov     r9d, eax; char *
0x18009f79d  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\telemetry"...
0x18009f7a4  mov     edx, 0ADh; void *
0x18009f7a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f7ae  nop
0x18009f7af  mov     rcx, [rsp+108h+var_B0]; string
0x18009f7b4  test    rcx, rcx
0x18009f7b7  jz      short loc_18009F7C0
0x18009f7b9  call    cs:__imp_WindowsDeleteString
0x18009f7bf  nop
0x18009f7c0  mov     rcx, [rsp+108h+string]; string
0x18009f7c5  test    rcx, rcx
0x18009f7c8  jz      short loc_18009F7D1
0x18009f7ca  call    cs:__imp_WindowsDeleteString
0x18009f7d0  nop
0x18009f7d1  mov     rcx, [rsp+108h+var_D0]
0x18009f7d6  test    rcx, rcx
0x18009f7d9  jz      short loc_18009F7E8
0x18009f7db  mov     rax, [rcx]
0x18009f7de  mov     rax, [rax+10h]
0x18009f7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f7e7  nop
0x18009f7e8  mov     eax, edi
0x18009f7ea  jmp     loc_1800A0F60
0x18009f7ef  mov     [rsp+108h+var_B8], r12
0x18009f7f4  mov     rcx, [rsp+108h+var_D0]
0x18009f7f9  mov     rax, [rcx]
0x18009f7fc  mov     [rsp+108h+var_B8], r12
0x18009f801  lea     r9, [rsp+108h+var_B8]
0x18009f806  mov     r8, [rsp+108h+var_B0]
0x18009f80b  mov     rdx, [rsp+108h+string]
0x18009f810  mov     rax, [rax+30h]
0x18009f814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f819  mov     edi, eax
0x18009f81b  test    eax, eax
0x18009f81d  jns     short loc_18009F893
0x18009f81f  mov     rcx, [rsp+108h]; this
0x18009f827  mov     r9d, eax; char *
0x18009f82a  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\telemetry"...
0x18009f831  mov     edx, 0B0h; void *
0x18009f836  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f83b  nop
0x18009f83c  mov     rcx, [rsp+108h+var_B8]
0x18009f841  test    rcx, rcx
0x18009f844  jz      short loc_18009F853
0x18009f846  mov     rax, [rcx]
0x18009f849  mov     rax, [rax+10h]
0x18009f84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f852  nop
0x18009f853  mov     rcx, [rsp+108h+var_B0]; string
0x18009f858  test    rcx, rcx
0x18009f85b  jz      short loc_18009F864
0x18009f85d  call    cs:__imp_WindowsDeleteString
0x18009f863  nop
0x18009f864  mov     rcx, [rsp+108h+string]; string
0x18009f869  test    rcx, rcx
0x18009f86c  jz      short loc_18009F875
0x18009f86e  call    cs:__imp_WindowsDeleteString
0x18009f874  nop
0x18009f875  mov     rcx, [rsp+108h+var_D0]
0x18009f87a  test    rcx, rcx
0x18009f87d  jz      short loc_18009F88C
0x18009f87f  mov     rax, [rcx]
0x18009f882  mov     rax, [rax+10h]
0x18009f886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f88b  nop
0x18009f88c  mov     eax, edi
0x18009f88e  jmp     loc_1800A0F60
0x18009f893  mov     [rsp+108h+var_C8], r12
0x18009f898  mov     [rsp+108h+var_38], r12
0x18009f8a0  lea     r9, [rsp+108h+var_38]; string
0x18009f8a8  lea     r8, [rsp+108h+hstringHeader]; hstringHeader
0x18009f8b0  mov     edx, 41h ; 'A'; length
0x18009f8b5  lea     rcx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x18009f8bc  call    cs:__imp_WindowsCreateStringReference
0x18009f8c2  test    eax, eax
0x18009f8c4  js      loc_1800A0F90
0x18009f8ca  mov     [rsp+108h+var_C8], r12
0x18009f8cf  mov     [rsp+108h+var_90], r12
0x18009f8d4  lea     rdx, [rsp+108h+var_90]
0x18009f8d9  mov     rcx, [rsp+108h+var_38]
0x18009f8e1  call    cs:__imp_RoActivateInstance
0x18009f8e7  mov     edi, eax
0x18009f8e9  test    eax, eax
0x18009f8eb  js      short loc_18009F941
0x18009f8ed  mov     r8d, 10h; Size
0x18009f8f3  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18009f8fa  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x18009f901  call    memcmp_0
0x18009f906  mov     rcx, [rsp+108h+var_90]
0x18009f90b  test    eax, eax
0x18009f90d  jnz     short loc_18009F916
0x18009f90f  mov     [rsp+108h+var_C8], rcx
0x18009f914  jmp     short loc_18009F941
0x18009f916  mov     rax, [rcx]
0x18009f919  lea     r8, [rsp+108h+var_C8]
0x18009f91e  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x18009f925  mov     rax, [rax]
0x18009f928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f92d  mov     edi, eax
0x18009f92f  mov     rcx, [rsp+108h+var_90]
0x18009f934  mov     rax, [rcx]
0x18009f937  mov     rax, [rax+10h]
0x18009f93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f940  nop
0x18009f941  test    edi, edi
0x18009f943  jns     loc_18009F9D4
0x18009f949  mov     rcx, [rsp+108h]; this
0x18009f951  mov     r9d, edi; char *
0x18009f954  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\telemetry"...
0x18009f95b  mov     edx, 0B5h; void *
0x18009f960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f965  nop
0x18009f966  mov     rcx, [rsp+108h+var_C8]
0x18009f96b  test    rcx, rcx
0x18009f96e  jz      short loc_18009F97D
0x18009f970  mov     rax, [rcx]
0x18009f973  mov     rax, [rax+10h]
0x18009f977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f97c  nop
0x18009f97d  mov     rcx, [rsp+108h+var_B8]
0x18009f982  test    rcx, rcx
0x18009f985  jz      short loc_18009F994
0x18009f987  mov     rax, [rcx]
0x18009f98a  mov     rax, [rax+10h]
0x18009f98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f993  nop
0x18009f994  mov     rcx, [rsp+108h+var_B0]; string
0x18009f999  test    rcx, rcx
0x18009f99c  jz      short loc_18009F9A5
0x18009f99e  call    cs:__imp_WindowsDeleteString
0x18009f9a4  nop
0x18009f9a5  mov     rcx, [rsp+108h+string]; string
0x18009f9aa  test    rcx, rcx
0x18009f9ad  jz      short loc_18009F9B6
0x18009f9af  call    cs:__imp_WindowsDeleteString
0x18009f9b5  nop
0x18009f9b6  mov     rcx, [rsp+108h+var_D0]
0x18009f9bb  test    rcx, rcx
0x18009f9be  jz      short loc_18009F9CD
0x18009f9c0  mov     rax, [rcx]
0x18009f9c3  mov     rax, [rax+10h]
0x18009f9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f9cc  nop
0x18009f9cd  mov     eax, edi
0x18009f9cf  jmp     loc_1800A0F60
0x18009f9d4  mov     [rsp+108h+hObject], r12
0x18009f9d9  mov     r9d, 1F0003h; dwDesiredAccess
0x18009f9df  xor     r8d, r8d; dwFlags
0x18009f9e2  xor     edx, edx; lpName
0x18009f9e4  xor     ecx, ecx; lpEventAttributes
0x18009f9e6  call    cs:__imp_CreateEventExW
0x18009f9ec  mov     rdi, rax
0x18009f9ef  test    rax, rax
0x18009f9f2  jz      loc_1800A1068
0x18009f9f8  call    cs:__imp_GetLastError
0x18009f9fe  mov     r14, [rsp+108h+hObject]
0x18009fa03  test    r14, r14
0x18009fa06  jz      short loc_18009FA33
0x18009fa08  call    cs:__imp_GetLastError
0x18009fa0e  mov     r15d, eax
0x18009fa11  mov     rcx, r14; hObject
0x18009fa14  call    cs:__imp_CloseHandle
0x18009fa1a  mov     rcx, [rsp+108h]
0x18009fa22  test    eax, eax
0x18009fa24  jz      loc_1800A0F98
0x18009fa2a  mov     ecx, r15d; dwErrCode
0x18009fa2d  call    cs:__imp_SetLastError
0x18009fa33  mov     [rsp+108h+hObject], rdi
0x18009fa38  mov     qword ptr [rsp+108h+var_78], rdi
0x18009fa40  lea     rdx, [rsp+108h+var_78]
0x18009fa48  lea     rcx, [rsp+108h+var_90]
0x18009fa4d  call    ??$Make@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@Telemetry@Base@OneCore@@PEAX@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@Telemetry@Base@OneCore@@@12@$$QEAPEAX@Z; Microsoft::WRL::Details::Make<OneCore::Base::Telemetry::AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>,void *>(void * &&)
0x18009fa52  mov     rdi, [rax]
0x18009fa55  mov     [rax], r12
0x18009fa58  mov     [rsp+108h+var_58], rdi
0x18009fa60  mov     rcx, [rsp+108h+var_90]
0x18009fa65  test    rcx, rcx
0x18009fa68  jz      short loc_18009FA7C
0x18009fa6a  mov     [rsp+108h+var_90], r12
0x18009fa6f  mov     rax, [rcx]
0x18009fa72  mov     rax, [rax+10h]
0x18009fa76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fa7b  nop
0x18009fa7c  test    rdi, rdi
0x18009fa7f  jnz     loc_18009FB35
0x18009fa85  mov     rcx, [rsp+108h]; this
0x18009fa8d  mov     ebx, 8007000Eh
0x18009fa92  mov     r9d, ebx; char *
0x18009fa95  lea     r8, aOnecoreInterna; "onecore\\internal\\base\\inc\\telemetry"...
0x18009fa9c  mov     edx, 0BAh; void *
0x18009faa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
