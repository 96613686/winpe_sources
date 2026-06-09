# Windows::Internal::Management::Provision::SessionManager::InitiateSessionAsync_Internal(HSTRING__ *,HSTRING__ *,Windows::Internal::Management::Provision::DeviceManagementInitiationInformation,uint,Windows::Internal::Management::Provision::DeviceManagementAlertInformation const *,bool,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> * *)

- ea: `0x18003d42c`
- end: `0x18003dbbc`
- name: `?InitiateSessionAsync_Internal@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEAUHSTRING__@@0UDeviceManagementInitiationInformation@2345@IPEBUDeviceManagementAlertInformation@2345@_NPEAPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@5@@Z`
- size: `1936`
- prototype: ``
- caller_count: `6`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d080`
- `0x18003d0c0`
- `0x18003d110`
- `0x18003d1d0`
- `0x18003d2c0`
- `0x18003d360`

## callees

- `0x1800011d4`
- `0x180005404`
- `0x180009be4`
- `0x18000a5c4`
- `0x18001c8d0`
- `0x18003afc8`
- `0x18003b060`
- `0x18003b200`
- `0x18003b2cc`
- `0x18003b2e4`
- `0x18003b374`
- `0x18003b714`
- `0x18003ba1c`
- `0x18003ba3c`
- `0x18003d034`
- `0x18003d42c`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x18003d6e1`
- `DMCmnUtils!CopyString` at `0x18003d71d`
- `DMCmnUtils!CopyString` at `0x18003d759`
- `DMCmnUtils!CopyString` at `0x18003d795`
- `DMCmnUtils!CopyString` at `0x18003d7d1`
- `DMCmnUtils!CopyString` at `0x18003d6e1`
- `DMCmnUtils!CopyString` at `0x18003d71d`
- `DMCmnUtils!CopyString` at `0x18003d759`
- `DMCmnUtils!CopyString` at `0x18003d795`
- `DMCmnUtils!CopyString` at `0x18003d7d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d6c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d77c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d7b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d6c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d77c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d7b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003d4c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003d4c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::Management::Provision::SessionManager::InitiateSessionAsync_Internal(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        char a7,
        __int64 a8)
{
  int v8; // ebx
  __int64 v9; // rax
  int v10; // r15d
  HSTRING *v11; // rsi
  __int64 v12; // rdi
  int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned __int64 v16; // rax
  __int64 v17; // r12
  unsigned int i; // r13d
  unsigned __int64 v19; // r14
  char *v20; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v22; // eax
  char *v23; // rbx
  const unsigned __int16 *v24; // rax
  int v25; // eax
  char *v26; // rbx
  const unsigned __int16 *v27; // rax
  int v28; // eax
  char *v29; // rbx
  const unsigned __int16 *v30; // rax
  int v31; // eax
  char *v32; // rbx
  const unsigned __int16 *v33; // rax
  int v34; // eax
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  int v39; // ecx
  __int64 v40; // rax
  __int64 v41; // r8
  int v43; // [rsp+28h] [rbp-D1h]
  char *v44; // [rsp+58h] [rbp-A1h] BYREF
  __int64 v45; // [rsp+60h] [rbp-99h] BYREF
  __int64 v46; // [rsp+68h] [rbp-91h] BYREF
  int v47; // [rsp+70h] [rbp-89h] BYREF
  _BYTE v48[24]; // [rsp+78h] [rbp-81h] BYREF
  HSTRING *v49; // [rsp+90h] [rbp-69h] BYREF
  __int64 v50; // [rsp+98h] [rbp-61h] BYREF
  int v51; // [rsp+A0h] [rbp-59h] BYREF
  __int64 v52; // [rsp+A4h] [rbp-55h]
  _BYTE v53[16]; // [rsp+B0h] [rbp-49h] BYREF
  _BYTE v54[120]; // [rsp+C0h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+47h]
  __int64 v56; // [rsp+148h] [rbp+4Fh] BYREF
  HSTRING v57; // [rsp+150h] [rbp+57h] BYREF
  HSTRING v58; // [rsp+158h] [rbp+5Fh] BYREF
  __int64 v59; // [rsp+160h] [rbp+67h]

  v59 = a4;
  v58 = a3;
  v57 = a2;
  v56 = a1;
  v8 = a4;
  LODWORD(v45) = 0;
  v9 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v56, &v45);
  wil::ScopeExit__lambda_1712defea65a5aaf7dcfd3577ccc8d93___(v53, v9);
  v46 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v10 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Provision::SessionResult,Windows::Internal::Management::Provision::SessionResult,>(&v46);
  LODWORD(v45) = v10;
  if ( v10 < 0 )
    goto LABEL_114;
  CreateRefCountedObj<Windows::Internal::String,>(&v49);
  v11 = v49;
  Windows::Internal::String::Initialize(v49 + 1, &v58);
  if ( WindowsIsStringEmpty(v11[1]) )
    goto LABEL_80;
  CreateRefCountedObj<Windows::Internal::String,>(&v50);
  v12 = v50;
  Windows::Internal::String::Initialize((HSTRING *)(v50 + 8), &v57);
  if ( SHIDWORD(v59) > 7 )
  {
    switch ( HIDWORD(v59) )
    {
      case 8:
        LODWORD(v56) = 37;
        break;
      case 9:
        LODWORD(v56) = 40;
        break;
      case 0xA:
        LODWORD(v56) = 42;
        break;
      case 0xB:
        LODWORD(v56) = 43;
        break;
      case 0xC:
        LODWORD(v56) = 44;
        break;
      default:
        goto LABEL_23;
    }
  }
  else
  {
    switch ( HIDWORD(v59) )
    {
      case 7:
        LODWORD(v56) = 36;
        break;
      case 1:
        LODWORD(v56) = 1;
        break;
      case 2:
        LODWORD(v56) = 31;
        break;
      case 3:
        LODWORD(v56) = 32;
        break;
      case 4:
        LODWORD(v56) = 33;
        break;
      case 5:
        LODWORD(v56) = 34;
        break;
      case 6:
        LODWORD(v56) = 35;
        break;
      default:
LABEL_23:
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        goto LABEL_80;
    }
  }
  if ( v8 )
  {
    if ( v8 != 1 )
    {
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_80:
      if ( v11 )
        (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
      v10 = -2147024809;
      goto LABEL_114;
    }
    v13 = 4;
  }
  else
  {
    v13 = 2;
  }
  v47 = v13;
  v44 = 0;
  v14 = _lambda_06f40ebce54247e3f11ddce21d34cd52_::_lambda_06f40ebce54247e3f11ddce21d34cd52_(&v51, &v44, &a5);
  wil::ScopeExit__lambda_69febd7a99d3cb245321704ad0be5e6f___(v48, v14);
  v15 = a5;
  if ( a5 )
  {
    v16 = (unsigned __int64)a5 << 6;
    if ( !is_mul_ok(a5, 0x40u) )
      v16 = -1;
    v44 = (char *)operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v44 )
    {
      wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v11 )
        (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
      v10 = -2147024882;
      goto LABEL_114;
    }
    v15 = a5;
  }
  v17 = a6;
  for ( i = 0; i < v15; ++i )
  {
    v19 = (unsigned __int64)i << 6;
    *(_DWORD *)&v44[v19] = 64;
    v20 = v44;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v17 + v19), 0);
    v22 = CopyString(StringRawBuffer, 0xFFFFFFFF, (unsigned __int16 **)&v20[v19 + 8]);
    v10 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
        (const char *)(unsigned int)v22,
        v43);
      wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v11 )
        (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
      goto LABEL_114;
    }
    v23 = v44;
    v24 = WindowsGetStringRawBuffer(*(HSTRING *)(v17 + v19 + 8), 0);
    v25 = CopyString(v24, 0xFFFFFFFF, (unsigned __int16 **)&v23[v19 + 16]);
    v10 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11A,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
        (const char *)(unsigned int)v25,
        v43);
      wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v11 )
        (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
      goto LABEL_114;
    }
    v26 = v44;
    v27 = WindowsGetStringRawBuffer(*(HSTRING *)(v17 + v19 + 16), 0);
    v28 = CopyString(v27, 0xFFFFFFFF, (unsigned __int16 **)&v26[v19 + 56]);
    v10 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
        (const char *)(unsigned int)v28,
        v43);
      wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v11 )
        (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
      goto LABEL_114;
    }
    v29 = v44;
    v30 = WindowsGetStringRawBuffer(*(HSTRING *)(v17 + v19 + 40), 0);
    v31 = CopyString(v30, 0xFFFFFFFF, (unsigned __int16 **)&v29[v19 + 24]);
    v10 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
        (const char *)(unsigned int)v31,
        v43);
      wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v11 )
        (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
      goto LABEL_114;
    }
    v32 = v44;
    v33 = WindowsGetStringRawBuffer(*(HSTRING *)(v17 + v19 + 24), 0);
    v34 = CopyString(v33, 0xFFFFFFFF, (unsigned __int16 **)&v32[v19 + 40]);
    v10 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\sessionmanager.cpp",
        (const char *)(unsigned int)v34,
        v43);
      wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v11 )
        (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
      goto LABEL_114;
    }
    *(_DWORD *)&v44[v19 + 48] = *(_DWORD *)(v17 + v19 + 32);
    v35 = *(_DWORD *)(v17 + v19 + 56);
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          if ( v37 != 1 )
          {
            wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
            if ( v12 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            goto LABEL_80;
          }
          *(_DWORD *)&v44[v19 + 36] = 5;
        }
        else
        {
          *(_DWORD *)&v44[v19 + 36] = 4;
        }
      }
      else
      {
        *(_DWORD *)&v44[v19 + 36] = 2;
      }
    }
    else
    {
      *(_DWORD *)&v44[v19 + 36] = 1;
    }
    v38 = *(_DWORD *)(v17 + v19 + 52);
    if ( v38 )
    {
      if ( v38 != 1 )
      {
        wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        goto LABEL_80;
      }
      *(_DWORD *)&v44[v19 + 4] = 1226;
    }
    else
    {
      *(_DWORD *)&v44[v19 + 4] = 1224;
    }
    v39 = *(_DWORD *)(v17 + v19 + 48);
    if ( v39 )
    {
      if ( v39 != 1 )
      {
        wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        goto LABEL_80;
      }
      *(_DWORD *)&v44[v19 + 32] = 1;
    }
    else
    {
      *(_DWORD *)&v44[v19 + 32] = 0;
    }
    v15 = a5;
  }
  v40 = lambda_155511d5d231700d07931fe42a92de9d_::_lambda_155511d5d231700d07931fe42a92de9d_(
          (unsigned int)v54,
          (unsigned int)&v50,
          (unsigned int)&v49,
          (unsigned int)&v47,
          (__int64)&v56,
          (__int64)&a5,
          (__int64)&v44,
          (__int64)&a7,
          (__int64)&v46);
  v51 = 3;
  v52 = 128;
  LODWORD(v45) = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Management::Provision::ISessionResult__Windows::Internal::Management::Provision::SessionResult___Windows::Internal::ComTaskPoolHandler__lambda_155511d5d231700d07931fe42a92de9d___(
                   &v51,
                   a8,
                   v41,
                   v40);
  lambda_155511d5d231700d07931fe42a92de9d_::__lambda_155511d5d231700d07931fe42a92de9d_(v54);
  v10 = v45;
  if ( (int)v45 >= 0 )
    v44 = 0;
  wil::details::ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___::_ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___(v48);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v11 )
    (*((void (__fastcall **)(HSTRING *))*v11 + 2))(v11);
LABEL_114:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  wil::details::ScopeExitFn__lambda_7bba135abbd1306f9dbf396dbc07f029___::_ScopeExitFn__lambda_7bba135abbd1306f9dbf396dbc07f029___(v53);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003d42c  mov     rax, rsp
0x18003d42f  mov     [rax+20h], r9
0x18003d433  mov     [rax+18h], r8
0x18003d437  mov     [rax+10h], rdx
0x18003d43b  mov     [rax+8], rcx
0x18003d43f  push    rbp
0x18003d440  push    rbx
0x18003d441  push    rsi
0x18003d442  push    rdi
0x18003d443  push    r12
0x18003d445  push    r13
0x18003d447  push    r14
0x18003d449  push    r15
0x18003d44b  lea     rbp, [rax-47h]
0x18003d44f  sub     rsp, 0F8h
0x18003d456  mov     rbx, r9
0x18003d459  mov     dword ptr [rsp+130h+var_D8], 0
0x18003d461  lea     rdx, [rsp+130h+var_D8]
0x18003d466  lea     rcx, [rbp+3Fh+arg_0]
0x18003d46a  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003d46f  mov     rdx, rax
0x18003d472  lea     rcx, [rbp+3Fh+var_88]
0x18003d476  call    wil__ScopeExit__lambda_1712defea65a5aaf7dcfd3577ccc8d93___
0x18003d47b  nop
0x18003d47c  mov     [rsp+130h+var_D0], 0
0x18003d485  lea     rcx, [rsp+130h+var_D0]
0x18003d48a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003d48f  lea     rcx, [rsp+130h+var_D0]
0x18003d494  call    ??$MakeAndInitialize@VSessionResult@Provision@Management@Internal@Windows@@V12345@$$V@Details@WRL@Microsoft@@YAJPEAPEAVSessionResult@Provision@Management@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Provision::SessionResult,Windows::Internal::Management::Provision::SessionResult,>(Windows::Internal::Management::Provision::SessionResult * *)
0x18003d499  mov     r15d, eax
0x18003d49c  mov     dword ptr [rsp+130h+var_D8], eax
0x18003d4a0  test    eax, eax
0x18003d4a2  js      loc_18003DB90
0x18003d4a8  lea     rcx, [rbp+3Fh+var_A8]
0x18003d4ac  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x18003d4b1  nop
0x18003d4b2  mov     rsi, [rbp+3Fh+var_A8]
0x18003d4b6  lea     rdx, [rbp+3Fh+arg_10]; HSTRING *
0x18003d4ba  lea     rcx, [rsi+8]; this
0x18003d4be  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18003d4c3  mov     rcx, [rsi+8]; string
0x18003d4c7  call    cs:__imp_WindowsIsStringEmpty
0x18003d4ce  nop     dword ptr [rax+rax+00h]
0x18003d4d3  test    eax, eax
0x18003d4d5  jz      short loc_18003D4DC
0x18003d4d7  jmp     loc_18003D914
0x18003d4dc  lea     rcx, [rbp+3Fh+var_A0]
0x18003d4e0  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x18003d4e5  nop
0x18003d4e6  mov     rdi, [rbp+3Fh+var_A0]
0x18003d4ea  lea     rcx, [rdi+8]; this
0x18003d4ee  lea     rdx, [rbp+3Fh+arg_8]; HSTRING *
0x18003d4f2  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18003d4f7  mov     ecx, [rbp+3Fh+arg_1C]
0x18003d4fa  cmp     ecx, 7
0x18003d4fd  jg      short loc_18003D567
0x18003d4ff  jz      short loc_18003D55E
0x18003d501  sub     ecx, 1
0x18003d504  jz      short loc_18003D555
0x18003d506  sub     ecx, 1
0x18003d509  jz      short loc_18003D54C
0x18003d50b  sub     ecx, 1
0x18003d50e  jz      short loc_18003D543
0x18003d510  sub     ecx, 1
0x18003d513  jz      short loc_18003D537
0x18003d515  sub     ecx, 1
0x18003d518  jz      short loc_18003D52B
0x18003d51a  cmp     ecx, 1
0x18003d51d  jnz     short loc_18003D580
0x18003d51f  mov     dword ptr [rbp+3Fh+arg_0], 23h ; '#'
0x18003d526  jmp     loc_18003D5C5
0x18003d52b  mov     dword ptr [rbp+3Fh+arg_0], 22h ; '"'
0x18003d532  jmp     loc_18003D5C5
0x18003d537  mov     dword ptr [rbp+3Fh+arg_0], 21h ; '!'
0x18003d53e  jmp     loc_18003D5C5
0x18003d543  mov     dword ptr [rbp+3Fh+arg_0], 20h ; ' '
0x18003d54a  jmp     short loc_18003D5C5
0x18003d54c  mov     dword ptr [rbp+3Fh+arg_0], 1Fh
0x18003d553  jmp     short loc_18003D5C5
0x18003d555  mov     dword ptr [rbp+3Fh+arg_0], 1
0x18003d55c  jmp     short loc_18003D5C5
0x18003d55e  mov     dword ptr [rbp+3Fh+arg_0], 24h ; '$'
0x18003d565  jmp     short loc_18003D5C5
0x18003d567  sub     ecx, 8
0x18003d56a  jz      short loc_18003D5BE
0x18003d56c  sub     ecx, 1
0x18003d56f  jz      short loc_18003D5B5
0x18003d571  sub     ecx, 1
0x18003d574  jz      short loc_18003D5AC
0x18003d576  sub     ecx, 1
0x18003d579  jz      short loc_18003D5A3
0x18003d57b  cmp     ecx, 1
0x18003d57e  jz      short loc_18003D59A
0x18003d580  test    rdi, rdi
0x18003d583  jz      short loc_18003D595
0x18003d585  mov     rax, [rdi]
0x18003d588  mov     rcx, rdi
0x18003d58b  mov     rax, [rax+10h]
0x18003d58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d594  nop
0x18003d595  jmp     loc_18003D914
0x18003d59a  mov     dword ptr [rbp+3Fh+arg_0], 2Ch ; ','
0x18003d5a1  jmp     short loc_18003D5C5
0x18003d5a3  mov     dword ptr [rbp+3Fh+arg_0], 2Bh ; '+'
0x18003d5aa  jmp     short loc_18003D5C5
0x18003d5ac  mov     dword ptr [rbp+3Fh+arg_0], 2Ah ; '*'
0x18003d5b3  jmp     short loc_18003D5C5
0x18003d5b5  mov     dword ptr [rbp+3Fh+arg_0], 28h ; '('
0x18003d5bc  jmp     short loc_18003D5C5
0x18003d5be  mov     dword ptr [rbp+3Fh+arg_0], 25h ; '%'
0x18003d5c5  test    ebx, ebx
0x18003d5c7  jz      short loc_18003D5EF
0x18003d5c9  cmp     ebx, 1
0x18003d5cc  jz      short loc_18003D5E8
0x18003d5ce  test    rdi, rdi
0x18003d5d1  jz      short loc_18003D5E3
0x18003d5d3  mov     rax, [rdi]
0x18003d5d6  mov     rcx, rdi
0x18003d5d9  mov     rax, [rax+10h]
0x18003d5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5e2  nop
0x18003d5e3  jmp     loc_18003D914
0x18003d5e8  mov     eax, 4
0x18003d5ed  jmp     short loc_18003D5F4
0x18003d5ef  mov     eax, 2
0x18003d5f4  mov     [rsp+130h+var_C8], eax
0x18003d5f8  mov     [rsp+130h+var_E0], 0
0x18003d601  lea     r8, [rbp+3Fh+arg_20]
0x18003d605  lea     rdx, [rsp+130h+var_E0]
0x18003d60a  lea     rcx, [rbp+3Fh+var_98]
0x18003d60e  call    ??0_lambda_06f40ebce54247e3f11ddce21d34cd52_@@QEAA@PEAV?$SimpleVectorView@PEAUIPackage@Provisioning@Management@Windows@@V?$Vector@PEAUIPackage@Provisioning@Management@Windows@@U?$DefaultEqualityPredicate@PEAUIPackage@Provisioning@Management@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPackage@Provisioning@Management@Windows@@@6784@U?$VectorOptions@PEAUIPackage@Provisioning@Management@Windows@@$00$00$0A@@6784@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPackage@Provisioning@Management@Windows@@@6784@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAPEAI@Z; _lambda_06f40ebce54247e3f11ddce21d34cd52_::_lambda_06f40ebce54247e3f11ddce21d34cd52_(Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Management::Provisioning::IPackage *,Windows::Foundation::Collections::Internal::Vector<Windows::Management::Provisioning::IPackage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Management::Provisioning::IPackage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Management::Provisioning::IPackage *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Management::Provisioning::IPackage *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Management::Provisioning::IPackage *>,XWinRT::IntVersionTag,1> *,uint * &)
0x18003d613  mov     rdx, rax
0x18003d616  lea     rcx, [rsp+70h]
0x18003d61b  call    wil__ScopeExit__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x18003d620  nop
0x18003d621  mov     eax, [rbp+3Fh+arg_20]
0x18003d624  test    eax, eax
0x18003d626  jz      short loc_18003D699
0x18003d628  mov     ecx, eax
0x18003d62a  mov     eax, 40h ; '@'
0x18003d62f  mul     rcx
0x18003d632  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003d639  cmovb   rax, rcx
0x18003d63d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d644  mov     rcx, rax; unsigned __int64
0x18003d647  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003d64c  mov     [rsp+130h+var_E0], rax
0x18003d651  test    rax, rax
0x18003d654  jnz     short loc_18003D696
0x18003d656  lea     rcx, [rsp+70h]
0x18003d65b  call    wil__details__ScopeExitFn__lambda_330d32309249a3947adb96a95f558109______ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___
0x18003d660  nop
0x18003d661  test    rdi, rdi
0x18003d664  jz      short loc_18003D676
0x18003d666  mov     rax, [rdi]
0x18003d669  mov     rcx, rdi
0x18003d66c  mov     rax, [rax+10h]
0x18003d670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d675  nop
0x18003d676  test    rsi, rsi
0x18003d679  jz      short loc_18003D68B
0x18003d67b  mov     rax, [rsi]
0x18003d67e  mov     rcx, rsi
0x18003d681  mov     rax, [rax+10h]
0x18003d685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d68a  nop
0x18003d68b  mov     r15d, 8007000Eh
0x18003d691  jmp     loc_18003DB90
0x18003d696  mov     eax, [rbp+3Fh+arg_20]
0x18003d699  mov     r12, [rbp+3Fh+arg_28]
0x18003d69d  xor     r13d, r13d
0x18003d6a0  cmp     r13d, eax
0x18003d6a3  jnb     loc_18003DAD3
0x18003d6a9  mov     r14d, r13d
0x18003d6ac  shl     r14, 6
0x18003d6b0  mov     rax, [rsp+130h+var_E0]
0x18003d6b5  mov     dword ptr [r14+rax], 40h ; '@'
0x18003d6bd  mov     rbx, [rsp+130h+var_E0]
0x18003d6c2  xor     edx, edx; length
0x18003d6c4  mov     rcx, [r12+r14]; string
0x18003d6c8  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d6cf  nop     dword ptr [rax+rax+00h]
0x18003d6d4  lea     r8, [rbx+8]
0x18003d6d8  add     r8, r14
0x18003d6db  or      edx, 0FFFFFFFFh
0x18003d6de  mov     rcx, rax
0x18003d6e1  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003d6e8  nop     dword ptr [rax+rax+00h]
0x18003d6ed  mov     r15d, eax
0x18003d6f0  test    eax, eax
0x18003d6f2  js      loc_18003DA80
0x18003d6f8  mov     rbx, [rsp+130h+var_E0]
0x18003d6fd  xor     edx, edx; length
0x18003d6ff  mov     rcx, [r12+r14+8]; string
0x18003d704  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d70b  nop     dword ptr [rax+rax+00h]
0x18003d710  lea     r8, [rbx+10h]
0x18003d714  add     r8, r14
0x18003d717  or      edx, 0FFFFFFFFh
0x18003d71a  mov     rcx, rax
0x18003d71d  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003d724  nop     dword ptr [rax+rax+00h]
0x18003d729  mov     r15d, eax
0x18003d72c  test    eax, eax
0x18003d72e  js      loc_18003DA2D
0x18003d734  mov     rbx, [rsp+130h+var_E0]
0x18003d739  xor     edx, edx; length
0x18003d73b  mov     rcx, [r12+r14+10h]; string
0x18003d740  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d747  nop     dword ptr [rax+rax+00h]
0x18003d74c  lea     r8, [rbx+38h]
0x18003d750  add     r8, r14
0x18003d753  or      edx, 0FFFFFFFFh
0x18003d756  mov     rcx, rax
0x18003d759  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003d760  nop     dword ptr [rax+rax+00h]
0x18003d765  mov     r15d, eax
0x18003d768  test    eax, eax
0x18003d76a  js      loc_18003D9DA
0x18003d770  mov     rbx, [rsp+130h+var_E0]
0x18003d775  xor     edx, edx; length
0x18003d777  mov     rcx, [r12+r14+28h]; string
0x18003d77c  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d783  nop     dword ptr [rax+rax+00h]
0x18003d788  lea     r8, [rbx+18h]
0x18003d78c  add     r8, r14
0x18003d78f  or      edx, 0FFFFFFFFh
0x18003d792  mov     rcx, rax
0x18003d795  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003d79c  nop     dword ptr [rax+rax+00h]
0x18003d7a1  mov     r15d, eax
0x18003d7a4  test    eax, eax
0x18003d7a6  js      loc_18003D987
0x18003d7ac  mov     rbx, [rsp+130h+var_E0]
0x18003d7b1  xor     edx, edx; length
0x18003d7b3  mov     rcx, [r12+r14+18h]; string
0x18003d7b8  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d7bf  nop     dword ptr [rax+rax+00h]
0x18003d7c4  lea     r8, [rbx+28h]
0x18003d7c8  add     r8, r14
0x18003d7cb  or      edx, 0FFFFFFFFh
0x18003d7ce  mov     rcx, rax
0x18003d7d1  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003d7d8  nop     dword ptr [rax+rax+00h]
0x18003d7dd  mov     r15d, eax
0x18003d7e0  test    eax, eax
0x18003d7e2  js      loc_18003D934
0x18003d7e8  mov     ecx, [r12+r14+20h]
0x18003d7ed  mov     rax, [rsp+130h+var_E0]
0x18003d7f2  mov     [r14+rax+30h], ecx
0x18003d7f7  mov     ecx, [r12+r14+38h]
0x18003d7fc  test    ecx, ecx
0x18003d7fe  jz      short loc_18003D843
0x18003d800  sub     ecx, 1
0x18003d803  jz      short loc_18003D833
0x18003d805  sub     ecx, 1
0x18003d808  jz      short loc_18003D823
0x18003d80a  cmp     ecx, 1
0x18003d80d  jnz     loc_18003D8B0
0x18003d813  mov     rax, [rsp+130h+var_E0]
0x18003d818  mov     dword ptr [r14+rax+24h], 5
0x18003d821  jmp     short loc_18003D851
0x18003d823  mov     rax, [rsp+130h+var_E0]
0x18003d828  mov     dword ptr [r14+rax+24h], 4
0x18003d831  jmp     short loc_18003D851
0x18003d833  mov     rax, [rsp+130h+var_E0]
0x18003d838  mov     dword ptr [r14+rax+24h], 2
0x18003d841  jmp     short loc_18003D851
0x18003d843  mov     rax, [rsp+130h+var_E0]
0x18003d848  mov     dword ptr [r14+rax+24h], 1
0x18003d851  mov     ecx, [r12+r14+34h]
0x18003d856  test    ecx, ecx
0x18003d858  jz      short loc_18003D86F
0x18003d85a  cmp     ecx, 1
0x18003d85d  jnz     short loc_18003D8D2
0x18003d85f  mov     rax, [rsp+130h+var_E0]
0x18003d864  mov     dword ptr [r14+rax+4], 4CAh
0x18003d86d  jmp     short loc_18003D87D
0x18003d86f  mov     rax, [rsp+130h+var_E0]
0x18003d874  mov     dword ptr [r14+rax+4], 4C8h
0x18003d87d  mov     ecx, [r12+r14+30h]
0x18003d882  test    ecx, ecx
0x18003d884  jz      short loc_18003D897
0x18003d886  cmp     ecx, 1
0x18003d889  jnz     short loc_18003D8F4
0x18003d88b  mov     rax, [rsp+130h+var_E0]
0x18003d890  mov     [r14+rax+20h], ecx
0x18003d895  jmp     short loc_18003D8A5
0x18003d897  mov     rax, [rsp+130h+var_E0]
0x18003d89c  mov     dword ptr [r14+rax+20h], 0
0x18003d8a5  inc     r13d
0x18003d8a8  mov     eax, [rbp+3Fh+arg_20]
0x18003d8ab  jmp     loc_18003D6A0
0x18003d8b0  lea     rcx, [rsp+70h]
0x18003d8b5  call    wil__details__ScopeExitFn__lambda_330d32309249a3947adb96a95f558109______ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___
0x18003d8ba  nop
0x18003d8bb  test    rdi, rdi
0x18003d8be  jz      short loc_18003D8D0
0x18003d8c0  mov     rax, [rdi]
0x18003d8c3  mov     rcx, rdi
  ... truncated ...
```
