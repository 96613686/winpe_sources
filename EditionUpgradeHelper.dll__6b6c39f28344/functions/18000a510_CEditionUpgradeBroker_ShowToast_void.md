# CEditionUpgradeBroker::ShowToast(void)

- ea: `0x18000a510`
- end: `0x18000ad2c`
- name: `?ShowToast@CEditionUpgradeBroker@@UEAAJXZ`
- size: `2076`
- prototype: `__int64 __fastcall(CEditionUpgradeBroker *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018e0`
- `0x180008c60`
- `0x180009978`
- `0x18000a020`
- `0x18000a240`
- `0x18000a510`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a5c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a5c1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000a590`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000a590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000aa5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000aa5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a674`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a72c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a8b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a924`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a96f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a674`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a72c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a822`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a8b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a924`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a96f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000aa31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ab5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000aa31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ab5b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a624`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a624`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeBroker::ShowToast(CEditionUpgradeBroker *this)
{
  PCWSTR v1; // rsi
  PCWSTR v2; // r14
  HRESULT ActivationFactory; // eax
  unsigned int v4; // edi
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  __int64 (__fastcall ***v8)(__int64, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v9)(__int64, GUID *, __int64 *); // rdi
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int v13; // eax
  unsigned int v14; // r8d
  __int64 (__fastcall ***v15)(__int64, GUID *, __int64 *); // rdi
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rdx
  __int64 (__fastcall **v18)(__int64, GUID *, __int64 *); // r15
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  __int64 (__fastcall ***v25)(__int64, GUID *, __int64 *); // rdi
  __int64 (__fastcall **v26)(__int64, GUID *, __int64 *); // r15
  HRESULT v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  __int64 (__fastcall ***v30)(__int64, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v31)(__int64, GUID *, __int64 *); // rdi
  HRESULT v32; // eax
  int v33; // edx
  unsigned int v34; // r8d
  __int64 (__fastcall ***v35)(__int64, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v36)(__int64, GUID *, __int64 *); // rdi
  HRESULT v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  __int64 (__fastcall ***v40)(__int64, GUID *, __int64 *); // rbx
  __int64 (__fastcall **v41)(__int64, GUID *, __int64 *); // rdi
  HRESULT v42; // eax
  int v43; // edx
  unsigned int v44; // r8d
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 (__fastcall *v50)(__int64 *, const wchar_t *, const wchar_t *, _QWORD, int, PCWSTR, const wchar_t *, const wchar_t *, PCWSTR *, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *); // rax
  HANDLE ProcessHeap; // rax
  HANDLE v52; // rax
  __int64 (__fastcall ***v54)(__int64, GUID *, __int64 *); // [rsp+90h] [rbp-80h] BYREF
  __int64 v55; // [rsp+98h] [rbp-78h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-70h] BYREF
  HSTRING v57; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v58; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-58h] BYREF
  UINT32 length; // [rsp+C0h] [rbp-50h] BYREF
  __int64 v61; // [rsp+C8h] [rbp-48h] BYREF
  __int64 (__fastcall ***v62)(__int64, GUID *, __int64 *); // [rsp+D0h] [rbp-40h] BYREF
  __int64 *v63; // [rsp+D8h] [rbp-38h] BYREF
  __int64 v64; // [rsp+E0h] [rbp-30h] BYREF
  __int64 v65; // [rsp+E8h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+F0h] [rbp-20h] BYREF
  __int64 v67; // [rsp+F8h] [rbp-18h] BYREF
  PCWSTR v68; // [rsp+100h] [rbp-10h] BYREF
  int v69; // [rsp+108h] [rbp-8h]
  int v70; // [rsp+110h] [rbp+0h] BYREF
  PCWSTR sourceString; // [rsp+118h] [rbp+8h] BYREF
  __int64 v72; // [rsp+120h] [rbp+10h] BYREF
  _QWORD v73[2]; // [rsp+128h] [rbp+18h]
  HSTRING_HEADER hstringHeader; // [rsp+138h] [rbp+28h] BYREF
  HSTRING string; // [rsp+150h] [rbp+40h] BYREF

  v72 = 0;
  v54 = 0;
  v1 = 0;
  v56 = 0;
  v2 = 0;
  v59 = 0;
  v55 = 0;
  v58 = 0;
  v67 = 0;
  v62 = 0;
  ppv = 0;
  v65 = 0;
  v64 = 0;
  v63 = 0;
  v61 = 0;
  *(_QWORD *)((char *)v73 + 4) = 0;
  v70 = 0;
  length = 0;
  v57 = 0;
  sourceString = 0;
  v68 = 0;
  ActivationFactory = CoInitializeEx(0, 0);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = CoCreateInstance(
                        &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                        0,
                        4u,
                        &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                        &ppv);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(*(_QWORD *)ppv + 24LL))(ppv, &v63);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.UI.Notifications.ToastNotificationManager",
         0x31u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v72);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v72 + 64LL))(
                        v72,
                        5,
                        (__int64 *)&v54);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  v8 = v54;
  v9 = *v54;
  string = 0;
  v10 = WindowsCreateStringReference(L"text", 4u, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    __debugbreak();
  }
  ActivationFactory = v9[16]((__int64)v8, (GUID *)string, &v56);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v56 + 56LL))(v56, 0, &v55);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  v13 = STRAPI_LoadFromResource(0x70u, (unsigned __int16 **)&sourceString);
  v4 = v13;
  if ( v13 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
    v1 = sourceString;
    goto LABEL_48;
  }
  v15 = v54;
  v16 = -1;
  v1 = sourceString;
  v17 = -1;
  v18 = *v54;
  string = 0;
  do
    ++v17;
  while ( sourceString[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v17, v14);
    __debugbreak();
  }
  if ( (int)v17 + 1 < (unsigned int)v17 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v17, v14);
    __debugbreak();
  }
  v19 = WindowsCreateStringReference(sourceString, v17, &hstringHeader, &string);
  if ( v19 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    __debugbreak();
  }
  ActivationFactory = v18[11]((__int64)v15, (GUID *)string, &v59);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v59)(
                        v59,
                        &GUID_1c741d59_2122_47d5_a856_83f3d4214875,
                        &v58);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 176LL))(v55, v58, &v61);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v56 + 56LL))(v56, 1, &v55);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  v22 = STRAPI_LoadFromResource(0x71u, (unsigned __int16 **)&v68);
  v4 = v22;
  if ( v22 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v22);
    v2 = v68;
    goto LABEL_48;
  }
  v25 = v54;
  v2 = v68;
  v26 = *v54;
  string = 0;
  do
    ++v16;
  while ( v68[v16] );
  if ( v16 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, v24);
    __debugbreak();
  }
  if ( (int)v16 + 1 < (unsigned int)v16 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, v24);
    __debugbreak();
  }
  v27 = WindowsCreateStringReference(v68, v16, &hstringHeader, &string);
  if ( v27 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
    __debugbreak();
  }
  ActivationFactory = v26[11]((__int64)v25, (GUID *)string, &v59);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v59)(
                        v59,
                        &GUID_1c741d59_2122_47d5_a856_83f3d4214875,
                        &v58);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 176LL))(v55, v58, &v61);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  v30 = v54;
  v31 = *v54;
  string = 0;
  v32 = WindowsCreateStringReference(L"toast", 5u, &hstringHeader, &string);
  if ( v32 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v32, v33, v34);
    __debugbreak();
  }
  ActivationFactory = v31[16]((__int64)v30, (GUID *)string, &v56);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v56 + 56LL))(v56, 0, &v55);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  v35 = v54;
  v36 = *v54;
  string = 0;
  v37 = WindowsCreateStringReference(L"launch", 6u, &hstringHeader, &string);
  if ( v37 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
    __debugbreak();
  }
  ActivationFactory = v36[14]((__int64)v35, (GUID *)string, (__int64 *)&v62);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  v40 = v62;
  v41 = *v62;
  string = 0;
  v42 = WindowsCreateStringReference(L"page=SettingsPageActivate", 0x19u, &hstringHeader, &string);
  if ( v42 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v42, v43, v44);
    JUMPOUT(0x18000AD2BLL);
  }
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), HSTRING))v41[9])(
                        v40,
                        string);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v55 + 128LL))(v55, &v65);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (**v62)((__int64)v62, &GUID_1c741d59_2122_47d5_a856_83f3d4214875, &v67);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v65 + 72LL))(v65, v67, &v61);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
    goto LABEL_46;
  ActivationFactory = (**v54)((__int64)v54, &GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c, &v64);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0
    || (v45 = v64,
        v46 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v64 + 48LL),
        WindowsDeleteString(v57),
        v57 = 0,
        ActivationFactory = v46(v45, &v57),
        v4 = ActivationFactory,
        ActivationFactory < 0) )
  {
LABEL_46:
    v48 = (unsigned int)ActivationFactory;
    goto LABEL_47;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v57, &length);
  if ( length )
  {
    v69 = v73[1];
    v49 = *v63;
    LODWORD(v73[0]) = 0;
    v50 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *, _QWORD, int, PCWSTR, const wchar_t *, const wchar_t *, PCWSTR *, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *))(v49 + 64);
    v68 = (PCWSTR)v73[0];
    ActivationFactory = v50(
                          v63,
                          L"windows.immersivecontrolpanel_cw5n1h2txyewy",
                          L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
                          0,
                          1,
                          StringRawBuffer,
                          L"ClipTroubleshootTag",
                          L"ClipTroubleshootGroup",
                          &v68,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          &v70);
    v4 = ActivationFactory;
    if ( ActivationFactory >= 0 )
      goto LABEL_48;
    goto LABEL_46;
  }
  v4 = -2147418113;
  v48 = 2147549183LL;
LABEL_47:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v48);
LABEL_48:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v2 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v1 )
  {
    v52 = GetProcessHeap();
    HeapFree(v52, 0, (LPVOID)(v1 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  WindowsDeleteString(v57);
  v57 = 0;
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64 *))(*v63 + 16))(v63);
    v63 = 0;
  }
  if ( v64 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v62 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v62)[2])(v62);
    v62 = 0;
  }
  if ( v67 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    v67 = 0;
  }
  if ( v58 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
  }
  if ( v55 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
  if ( v59 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  if ( v54 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v54)[2])(v54);
    v54 = 0;
  }
  if ( v72 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  return v4;
}

```

## disassembly

```asm
0x18000a510  push    rbp
0x18000a512  push    rbx
0x18000a513  push    rsi
0x18000a514  push    rdi
0x18000a515  push    r12
0x18000a517  push    r13
0x18000a519  push    r14
0x18000a51b  push    r15
0x18000a51d  lea     rbp, [rsp-58h]
0x18000a522  sub     rsp, 168h
0x18000a529  mov     rax, cs:__security_cookie
0x18000a530  xor     rax, rsp
0x18000a533  mov     [rbp+90h+var_48], rax
0x18000a537  xor     r12d, r12d
0x18000a53a  xor     edx, edx; dwCoInit
0x18000a53c  xor     ecx, ecx; pvReserved
0x18000a53e  mov     [rbp+90h+var_80], r12
0x18000a542  mov     [rbp+90h+var_110], r12
0x18000a546  mov     esi, r12d
0x18000a549  mov     [rbp+90h+var_100], r12
0x18000a54d  mov     r14d, r12d
0x18000a550  mov     [rbp+90h+var_E8], r12
0x18000a554  mov     [rbp+90h+var_108], r12
0x18000a558  mov     [rbp+90h+var_F0], r12
0x18000a55c  mov     [rbp+90h+var_A8], r12
0x18000a560  mov     [rbp+90h+var_D0], r12
0x18000a564  mov     [rbp+90h+var_B0], r12
0x18000a568  mov     [rbp+90h+var_B8], r12
0x18000a56c  mov     [rbp+90h+var_C0], r12
0x18000a570  mov     [rbp+90h+var_C8], r12
0x18000a574  mov     [rbp+90h+var_D8], r12
0x18000a578  mov     qword ptr [rbp+90h+var_78+4], r12
0x18000a57c  mov     [rbp+90h+var_90], r12d
0x18000a580  mov     [rbp+90h+length], r12d
0x18000a584  mov     [rbp+90h+var_F8], r12
0x18000a588  mov     [rbp+90h+sourceString], r12
0x18000a58c  mov     [rbp+90h+var_A0], r12
0x18000a590  call    cs:__imp_CoInitializeEx
0x18000a596  mov     edi, eax
0x18000a598  test    eax, eax
0x18000a59a  js      loc_18000AB07
0x18000a5a0  lea     rax, [rbp+90h+var_B0]
0x18000a5a4  xor     edx, edx; pUnkOuter
0x18000a5a6  lea     r15d, [r12+4]
0x18000a5ab  mov     [rsp+1A0h+ppv], rax; ppv
0x18000a5b0  mov     r8d, r15d; dwClsContext
0x18000a5b3  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18000a5ba  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18000a5c1  call    cs:__imp_CoCreateInstance
0x18000a5c7  mov     edi, eax
0x18000a5c9  test    eax, eax
0x18000a5cb  js      loc_18000AB07
0x18000a5d1  mov     rcx, [rbp+90h+var_B0]
0x18000a5d5  lea     rdx, [rbp+90h+var_C8]
0x18000a5d9  mov     rax, [rcx]
0x18000a5dc  mov     rax, [rax+18h]
0x18000a5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5e5  mov     edi, eax
0x18000a5e7  test    eax, eax
0x18000a5e9  js      loc_18000AB07
0x18000a5ef  lea     r9, [rbp+90h+string]; string
0x18000a5f3  mov     [rbp+90h+string], r12
0x18000a5f7  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000a5fb  lea     edx, [r12+31h]; length
0x18000a600  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x18000a607  call    cs:__imp_WindowsCreateStringReference
0x18000a60d  test    eax, eax
0x18000a60f  js      loc_18000ACDE
0x18000a615  mov     rcx, [rbp+90h+string]
0x18000a619  lea     r8, [rbp+90h+var_80]
0x18000a61d  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x18000a624  call    cs:__imp_RoGetActivationFactory
0x18000a62a  mov     edi, eax
0x18000a62c  test    eax, eax
0x18000a62e  js      loc_18000AB07
0x18000a634  mov     rcx, [rbp+90h+var_80]
0x18000a638  lea     r8, [rbp+90h+var_110]
0x18000a63c  lea     edx, [r12+5]
0x18000a641  mov     rax, [rcx]
0x18000a644  mov     rax, [rax+40h]
0x18000a648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a64d  mov     edi, eax
0x18000a64f  test    eax, eax
0x18000a651  js      loc_18000AB07
0x18000a657  mov     rbx, [rbp+90h+var_110]
0x18000a65b  lea     r9, [rbp+90h+string]; string
0x18000a65f  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000a663  mov     edx, r15d; length
0x18000a666  lea     rcx, sourceString; "text"
0x18000a66d  mov     rdi, [rbx]
0x18000a670  mov     [rbp+90h+string], r12
0x18000a674  call    cs:__imp_WindowsCreateStringReference
0x18000a67a  test    eax, eax
0x18000a67c  js      loc_18000ACE6
0x18000a682  mov     rdx, [rbp+90h+string]
0x18000a686  lea     r8, [rbp+90h+var_100]
0x18000a68a  mov     rax, [rdi+80h]
0x18000a691  mov     rcx, rbx
0x18000a694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a699  mov     edi, eax
0x18000a69b  test    eax, eax
0x18000a69d  js      loc_18000AB07
0x18000a6a3  mov     rcx, [rbp+90h+var_100]
0x18000a6a7  lea     r8, [rbp+90h+var_108]
0x18000a6ab  xor     edx, edx
0x18000a6ad  mov     rax, [rcx]
0x18000a6b0  mov     rax, [rax+38h]
0x18000a6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b9  mov     edi, eax
0x18000a6bb  test    eax, eax
0x18000a6bd  js      loc_18000AB07
0x18000a6c3  lea     rdx, [rbp+90h+sourceString]; unsigned __int16 **
0x18000a6c7  lea     ecx, [r12+70h]; unsigned int
0x18000a6cc  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x18000a6d1  mov     edi, eax
0x18000a6d3  test    eax, eax
0x18000a6d5  jns     short loc_18000A6E7
0x18000a6d7  mov     ecx, eax
0x18000a6d9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a6de  mov     rsi, [rbp+90h+sourceString]
0x18000a6e2  jmp     loc_18000AB0E
0x18000a6e7  mov     rdi, [rbp+90h+var_110]
0x18000a6eb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a6ef  mov     rsi, [rbp+90h+sourceString]
0x18000a6f3  mov     rdx, rbx
0x18000a6f6  mov     r15, [rdi]
0x18000a6f9  mov     [rbp+90h+string], r12
0x18000a6fd  inc     rdx; int
0x18000a700  cmp     [rsi+rdx*2], r12w
0x18000a705  jnz     short loc_18000A6FD
0x18000a707  mov     r13d, 0FFFFFFFFh
0x18000a70d  cmp     rdx, r13
0x18000a710  ja      loc_18000ACD3
0x18000a716  lea     eax, [rdx+1]
0x18000a719  cmp     eax, edx
0x18000a71b  jb      loc_18000ACEE
0x18000a721  lea     r9, [rbp+90h+string]; string
0x18000a725  mov     rcx, rsi; sourceString
0x18000a728  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000a72c  call    cs:__imp_WindowsCreateStringReference
0x18000a732  test    eax, eax
0x18000a734  js      loc_18000ACF9
0x18000a73a  mov     rdx, [rbp+90h+string]
0x18000a73e  lea     r8, [rbp+90h+var_E8]
0x18000a742  mov     rax, [r15+58h]
0x18000a746  mov     rcx, rdi
0x18000a749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a74e  mov     edi, eax
0x18000a750  test    eax, eax
0x18000a752  js      loc_18000AB07
0x18000a758  mov     rcx, [rbp+90h+var_E8]
0x18000a75c  lea     r8, [rbp+90h+var_F0]
0x18000a760  lea     rdx, _GUID_1c741d59_2122_47d5_a856_83f3d4214875
0x18000a767  mov     rax, [rcx]
0x18000a76a  mov     rax, [rax]
0x18000a76d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a772  mov     edi, eax
0x18000a774  test    eax, eax
0x18000a776  js      loc_18000AB07
0x18000a77c  mov     rcx, [rbp+90h+var_108]
0x18000a780  lea     r8, [rbp+90h+var_D8]
0x18000a784  mov     rdx, [rbp+90h+var_F0]
0x18000a788  mov     rax, [rcx]
0x18000a78b  mov     rax, [rax+0B0h]
0x18000a792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a797  mov     edi, eax
0x18000a799  test    eax, eax
0x18000a79b  js      loc_18000AB07
0x18000a7a1  mov     rcx, [rbp+90h+var_100]
0x18000a7a5  lea     r8, [rbp+90h+var_108]
0x18000a7a9  mov     edx, 1
0x18000a7ae  mov     rax, [rcx]
0x18000a7b1  mov     rax, [rax+38h]
0x18000a7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7ba  mov     edi, eax
0x18000a7bc  test    eax, eax
0x18000a7be  js      loc_18000AB07
0x18000a7c4  lea     rdx, [rbp+90h+var_A0]; unsigned __int16 **
0x18000a7c8  mov     ecx, 71h ; 'q'; unsigned int
0x18000a7cd  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x18000a7d2  mov     edi, eax
0x18000a7d4  test    eax, eax
0x18000a7d6  jns     short loc_18000A7E8
0x18000a7d8  mov     ecx, eax
0x18000a7da  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a7df  mov     r14, [rbp+90h+var_A0]
0x18000a7e3  jmp     loc_18000AB0E
0x18000a7e8  mov     rdi, [rbp+90h+var_110]
0x18000a7ec  mov     r14, [rbp+90h+var_A0]
0x18000a7f0  mov     r15, [rdi]
0x18000a7f3  mov     [rbp+90h+string], r12
0x18000a7f7  inc     rbx
0x18000a7fa  cmp     [r14+rbx*2], r12w
0x18000a7ff  jnz     short loc_18000A7F7
0x18000a801  cmp     rbx, r13
0x18000a804  ja      loc_18000ACC8
0x18000a80a  lea     eax, [rbx+1]
0x18000a80d  cmp     eax, ebx
0x18000a80f  jb      loc_18000AD01
0x18000a815  lea     r9, [rbp+90h+string]; string
0x18000a819  mov     edx, ebx; length
0x18000a81b  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000a81f  mov     rcx, r14; sourceString
0x18000a822  call    cs:__imp_WindowsCreateStringReference
0x18000a828  test    eax, eax
0x18000a82a  js      loc_18000AD0C
0x18000a830  mov     rdx, [rbp+90h+string]
0x18000a834  lea     r8, [rbp+90h+var_E8]
0x18000a838  mov     rax, [r15+58h]
0x18000a83c  mov     rcx, rdi
0x18000a83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a844  mov     edi, eax
0x18000a846  test    eax, eax
0x18000a848  js      loc_18000AB07
0x18000a84e  mov     rcx, [rbp+90h+var_E8]
0x18000a852  lea     r8, [rbp+90h+var_F0]
0x18000a856  lea     rdx, _GUID_1c741d59_2122_47d5_a856_83f3d4214875
0x18000a85d  mov     rax, [rcx]
0x18000a860  mov     rax, [rax]
0x18000a863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a868  mov     edi, eax
0x18000a86a  test    eax, eax
0x18000a86c  js      loc_18000AB07
0x18000a872  mov     rcx, [rbp+90h+var_108]
0x18000a876  lea     r8, [rbp+90h+var_D8]
0x18000a87a  mov     rdx, [rbp+90h+var_F0]
0x18000a87e  mov     rax, [rcx]
0x18000a881  mov     rax, [rax+0B0h]
0x18000a888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a88d  mov     edi, eax
0x18000a88f  test    eax, eax
0x18000a891  js      loc_18000AB07
0x18000a897  mov     rbx, [rbp+90h+var_110]
0x18000a89b  lea     r9, [rbp+90h+string]; string
0x18000a89f  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000a8a3  mov     edx, 5; length
0x18000a8a8  lea     rcx, aToast; "toast"
0x18000a8af  mov     rdi, [rbx]
0x18000a8b2  mov     [rbp+90h+string], r12
0x18000a8b6  call    cs:__imp_WindowsCreateStringReference
0x18000a8bc  test    eax, eax
0x18000a8be  js      loc_18000AD14
0x18000a8c4  mov     rdx, [rbp+90h+string]
0x18000a8c8  lea     r8, [rbp+90h+var_100]
0x18000a8cc  mov     rax, [rdi+80h]
0x18000a8d3  mov     rcx, rbx
0x18000a8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8db  mov     edi, eax
0x18000a8dd  test    eax, eax
0x18000a8df  js      loc_18000AB07
0x18000a8e5  mov     rcx, [rbp+90h+var_100]
0x18000a8e9  lea     r8, [rbp+90h+var_108]
0x18000a8ed  xor     edx, edx
0x18000a8ef  mov     rax, [rcx]
0x18000a8f2  mov     rax, [rax+38h]
0x18000a8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8fb  mov     edi, eax
0x18000a8fd  test    eax, eax
0x18000a8ff  js      loc_18000AB07
0x18000a905  mov     rbx, [rbp+90h+var_110]
0x18000a909  lea     r9, [rbp+90h+string]; string
0x18000a90d  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000a911  mov     edx, 6; length
0x18000a916  lea     rcx, aLaunch; "launch"
0x18000a91d  mov     rdi, [rbx]
0x18000a920  mov     [rbp+90h+string], r12
0x18000a924  call    cs:__imp_WindowsCreateStringReference
0x18000a92a  test    eax, eax
0x18000a92c  js      loc_18000AD1C
0x18000a932  mov     rdx, [rbp+90h+string]
0x18000a936  lea     r8, [rbp+90h+var_D0]
0x18000a93a  mov     rax, [rdi+70h]
0x18000a93e  mov     rcx, rbx
0x18000a941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a946  mov     edi, eax
0x18000a948  test    eax, eax
0x18000a94a  js      loc_18000AB07
0x18000a950  mov     rbx, [rbp+90h+var_D0]
0x18000a954  lea     r9, [rbp+90h+string]; string
0x18000a958  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000a95c  mov     edx, 19h; length
0x18000a961  lea     rcx, aPageSettingspa; "page=SettingsPageActivate"
0x18000a968  mov     rdi, [rbx]
0x18000a96b  mov     [rbp+90h+string], r12
0x18000a96f  call    cs:__imp_WindowsCreateStringReference
0x18000a975  test    eax, eax
0x18000a977  js      loc_18000AD24
0x18000a97d  mov     rdx, [rbp+90h+string]
0x18000a981  mov     rcx, rbx
0x18000a984  mov     rax, [rdi+48h]
0x18000a988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a98d  mov     edi, eax
0x18000a98f  test    eax, eax
0x18000a991  js      loc_18000AB07
0x18000a997  mov     rcx, [rbp+90h+var_108]
0x18000a99b  lea     rdx, [rbp+90h+var_B8]
0x18000a99f  mov     rax, [rcx]
0x18000a9a2  mov     rax, [rax+80h]
0x18000a9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ae  mov     edi, eax
  ... truncated ...
```
