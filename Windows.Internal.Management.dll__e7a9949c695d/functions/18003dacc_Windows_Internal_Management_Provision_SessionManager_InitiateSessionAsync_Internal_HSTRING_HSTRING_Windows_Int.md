# Windows::Internal::Management::Provision::SessionManager::InitiateSessionAsync_Internal(HSTRING__ *,HSTRING__ *,Windows::Internal::Management::Provision::DeviceManagementInitiationInformation,uint,Windows::Internal::Management::Provision::DeviceManagementAlertInformation const *,bool,Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::SessionResult *> * *)

- ea: `0x18003dacc`
- end: `0x18003e219`
- name: `?InitiateSessionAsync_Internal@SessionManager@Provision@Management@Internal@Windows@@AEAAJPEAUHSTRING__@@0UDeviceManagementInitiationInformation@2345@IPEBUDeviceManagementAlertInformation@2345@_NPEAPEAU?$IAsyncOperation@PEAVSessionResult@Provision@Management@Internal@Windows@@@Foundation@5@@Z`
- size: `1869`
- prototype: ``
- caller_count: `6`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d730`
- `0x18003d760`
- `0x18003d7b0`
- `0x18003d870`
- `0x18003d960`
- `0x18003da00`

## callees

- `0x1800011d4`
- `0x1800052a4`
- `0x18000992c`
- `0x18000a2a4`
- `0x18001e3c8`
- `0x18003b838`
- `0x18003b8c8`
- `0x18003ba64`
- `0x18003bb2c`
- `0x18003bb44`
- `0x18003bbd4`
- `0x18003bf64`
- `0x18003c250`
- `0x18003c270`
- `0x18003d6dc`
- `0x18003dacc`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!CopyString` at `0x18003dd75`
- `DMCmnUtils!CopyString` at `0x18003dda5`
- `DMCmnUtils!CopyString` at `0x18003ddd5`
- `DMCmnUtils!CopyString` at `0x18003de05`
- `DMCmnUtils!CopyString` at `0x18003de35`
- `DMCmnUtils!CopyString` at `0x18003dd75`
- `DMCmnUtils!CopyString` at `0x18003dda5`
- `DMCmnUtils!CopyString` at `0x18003ddd5`
- `DMCmnUtils!CopyString` at `0x18003de05`
- `DMCmnUtils!CopyString` at `0x18003de35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003dd62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003dd92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ddc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ddf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003de22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003dd62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003dd92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ddc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ddf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003de22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003db67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18003db67`

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
  _QWORD *v9; // rax
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
  v9 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
         &v56,
         (__int64)&v45);
  wil::ScopeExit__lambda_1712defea65a5aaf7dcfd3577ccc8d93___(v53, v9);
  v46 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  v10 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Provision::SessionResult,Windows::Internal::Management::Provision::SessionResult,>(&v46);
  LODWORD(v45) = v10;
  if ( v10 < 0 )
    goto LABEL_114;
  CreateRefCountedObj<Windows::Internal::String,>(&v49);
  v11 = v49;
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v49 + 1), &v58);
  if ( WindowsIsStringEmpty(v11[1]) )
    goto LABEL_80;
  CreateRefCountedObj<Windows::Internal::String,>(&v50);
  v12 = v50;
  Windows::Internal::String::Initialize((Windows::Internal::String *)(v50 + 8), &v57);
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
0x18003dacc  mov     rax, rsp
0x18003dacf  mov     [rax+20h], r9
0x18003dad3  mov     [rax+18h], r8
0x18003dad7  mov     [rax+10h], rdx
0x18003dadb  mov     [rax+8], rcx
0x18003dadf  push    rbp
0x18003dae0  push    rbx
0x18003dae1  push    rsi
0x18003dae2  push    rdi
0x18003dae3  push    r12
0x18003dae5  push    r13
0x18003dae7  push    r14
0x18003dae9  push    r15
0x18003daeb  lea     rbp, [rax-47h]
0x18003daef  sub     rsp, 0F8h
0x18003daf6  mov     rbx, r9
0x18003daf9  mov     dword ptr [rsp+130h+var_D8], 0
0x18003db01  lea     rdx, [rsp+130h+var_D8]
0x18003db06  lea     rcx, [rbp+3Fh+arg_0]
0x18003db0a  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003db0f  mov     rdx, rax
0x18003db12  lea     rcx, [rbp+3Fh+var_88]
0x18003db16  call    wil__ScopeExit__lambda_1712defea65a5aaf7dcfd3577ccc8d93___
0x18003db1b  nop
0x18003db1c  mov     [rsp+130h+var_D0], 0
0x18003db25  lea     rcx, [rsp+130h+var_D0]
0x18003db2a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003db2f  lea     rcx, [rsp+130h+var_D0]
0x18003db34  call    ??$MakeAndInitialize@VSessionResult@Provision@Management@Internal@Windows@@V12345@$$V@Details@WRL@Microsoft@@YAJPEAPEAVSessionResult@Provision@Management@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::Management::Provision::SessionResult,Windows::Internal::Management::Provision::SessionResult,>(Windows::Internal::Management::Provision::SessionResult * *)
0x18003db39  mov     r15d, eax
0x18003db3c  mov     dword ptr [rsp+130h+var_D8], eax
0x18003db40  test    eax, eax
0x18003db42  js      loc_18003E1EE
0x18003db48  lea     rcx, [rbp+3Fh+var_A8]
0x18003db4c  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x18003db51  nop
0x18003db52  mov     rsi, [rbp+3Fh+var_A8]
0x18003db56  lea     rdx, [rbp+3Fh+arg_10]; HSTRING *
0x18003db5a  lea     rcx, [rsi+8]; this
0x18003db5e  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18003db63  mov     rcx, [rsi+8]; string
0x18003db67  call    cs:__imp_WindowsIsStringEmpty
0x18003db6d  test    eax, eax
0x18003db6f  jz      short loc_18003DB76
0x18003db71  jmp     loc_18003DF72
0x18003db76  lea     rcx, [rbp+3Fh+var_A0]
0x18003db7a  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x18003db7f  nop
0x18003db80  mov     rdi, [rbp+3Fh+var_A0]
0x18003db84  lea     rcx, [rdi+8]; this
0x18003db88  lea     rdx, [rbp+3Fh+arg_8]; HSTRING *
0x18003db8c  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18003db91  mov     ecx, [rbp+3Fh+arg_1C]
0x18003db94  cmp     ecx, 7
0x18003db97  jg      short loc_18003DC01
0x18003db99  jz      short loc_18003DBF8
0x18003db9b  sub     ecx, 1
0x18003db9e  jz      short loc_18003DBEF
0x18003dba0  sub     ecx, 1
0x18003dba3  jz      short loc_18003DBE6
0x18003dba5  sub     ecx, 1
0x18003dba8  jz      short loc_18003DBDD
0x18003dbaa  sub     ecx, 1
0x18003dbad  jz      short loc_18003DBD1
0x18003dbaf  sub     ecx, 1
0x18003dbb2  jz      short loc_18003DBC5
0x18003dbb4  cmp     ecx, 1
0x18003dbb7  jnz     short loc_18003DC1A
0x18003dbb9  mov     dword ptr [rbp+3Fh+arg_0], 23h ; '#'
0x18003dbc0  jmp     loc_18003DC5F
0x18003dbc5  mov     dword ptr [rbp+3Fh+arg_0], 22h ; '"'
0x18003dbcc  jmp     loc_18003DC5F
0x18003dbd1  mov     dword ptr [rbp+3Fh+arg_0], 21h ; '!'
0x18003dbd8  jmp     loc_18003DC5F
0x18003dbdd  mov     dword ptr [rbp+3Fh+arg_0], 20h ; ' '
0x18003dbe4  jmp     short loc_18003DC5F
0x18003dbe6  mov     dword ptr [rbp+3Fh+arg_0], 1Fh
0x18003dbed  jmp     short loc_18003DC5F
0x18003dbef  mov     dword ptr [rbp+3Fh+arg_0], 1
0x18003dbf6  jmp     short loc_18003DC5F
0x18003dbf8  mov     dword ptr [rbp+3Fh+arg_0], 24h ; '$'
0x18003dbff  jmp     short loc_18003DC5F
0x18003dc01  sub     ecx, 8
0x18003dc04  jz      short loc_18003DC58
0x18003dc06  sub     ecx, 1
0x18003dc09  jz      short loc_18003DC4F
0x18003dc0b  sub     ecx, 1
0x18003dc0e  jz      short loc_18003DC46
0x18003dc10  sub     ecx, 1
0x18003dc13  jz      short loc_18003DC3D
0x18003dc15  cmp     ecx, 1
0x18003dc18  jz      short loc_18003DC34
0x18003dc1a  test    rdi, rdi
0x18003dc1d  jz      short loc_18003DC2F
0x18003dc1f  mov     rax, [rdi]
0x18003dc22  mov     rcx, rdi
0x18003dc25  mov     rax, [rax+10h]
0x18003dc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc2e  nop
0x18003dc2f  jmp     loc_18003DF72
0x18003dc34  mov     dword ptr [rbp+3Fh+arg_0], 2Ch ; ','
0x18003dc3b  jmp     short loc_18003DC5F
0x18003dc3d  mov     dword ptr [rbp+3Fh+arg_0], 2Bh ; '+'
0x18003dc44  jmp     short loc_18003DC5F
0x18003dc46  mov     dword ptr [rbp+3Fh+arg_0], 2Ah ; '*'
0x18003dc4d  jmp     short loc_18003DC5F
0x18003dc4f  mov     dword ptr [rbp+3Fh+arg_0], 28h ; '('
0x18003dc56  jmp     short loc_18003DC5F
0x18003dc58  mov     dword ptr [rbp+3Fh+arg_0], 25h ; '%'
0x18003dc5f  test    ebx, ebx
0x18003dc61  jz      short loc_18003DC89
0x18003dc63  cmp     ebx, 1
0x18003dc66  jz      short loc_18003DC82
0x18003dc68  test    rdi, rdi
0x18003dc6b  jz      short loc_18003DC7D
0x18003dc6d  mov     rax, [rdi]
0x18003dc70  mov     rcx, rdi
0x18003dc73  mov     rax, [rax+10h]
0x18003dc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc7c  nop
0x18003dc7d  jmp     loc_18003DF72
0x18003dc82  mov     eax, 4
0x18003dc87  jmp     short loc_18003DC8E
0x18003dc89  mov     eax, 2
0x18003dc8e  mov     [rsp+130h+var_C8], eax
0x18003dc92  mov     [rsp+130h+var_E0], 0
0x18003dc9b  lea     r8, [rbp+3Fh+arg_20]
0x18003dc9f  lea     rdx, [rsp+130h+var_E0]
0x18003dca4  lea     rcx, [rbp+3Fh+var_98]
0x18003dca8  call    ??0_lambda_06f40ebce54247e3f11ddce21d34cd52_@@QEAA@PEAV?$SimpleVectorView@PEAUIPackage@Provisioning@Management@Windows@@V?$Vector@PEAUIPackage@Provisioning@Management@Windows@@U?$DefaultEqualityPredicate@PEAUIPackage@Provisioning@Management@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPackage@Provisioning@Management@Windows@@@6784@U?$VectorOptions@PEAUIPackage@Provisioning@Management@Windows@@$00$00$0A@@6784@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIPackage@Provisioning@Management@Windows@@@6784@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAPEAI@Z; _lambda_06f40ebce54247e3f11ddce21d34cd52_::_lambda_06f40ebce54247e3f11ddce21d34cd52_(Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Management::Provisioning::IPackage *,Windows::Foundation::Collections::Internal::Vector<Windows::Management::Provisioning::IPackage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Management::Provisioning::IPackage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Management::Provisioning::IPackage *>,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Management::Provisioning::IPackage *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Management::Provisioning::IPackage *>,XWinRT::IntVersionTag,1> *,uint * &)
0x18003dcad  mov     rdx, rax
0x18003dcb0  lea     rcx, [rsp+70h]
0x18003dcb5  call    wil__ScopeExit__lambda_69febd7a99d3cb245321704ad0be5e6f___
0x18003dcba  nop
0x18003dcbb  mov     eax, [rbp+3Fh+arg_20]
0x18003dcbe  test    eax, eax
0x18003dcc0  jz      short loc_18003DD33
0x18003dcc2  mov     ecx, eax
0x18003dcc4  mov     eax, 40h ; '@'
0x18003dcc9  mul     rcx
0x18003dccc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003dcd3  cmovb   rax, rcx
0x18003dcd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003dcde  mov     rcx, rax; unsigned __int64
0x18003dce1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003dce6  mov     [rsp+130h+var_E0], rax
0x18003dceb  test    rax, rax
0x18003dcee  jnz     short loc_18003DD30
0x18003dcf0  lea     rcx, [rsp+70h]
0x18003dcf5  call    wil__details__ScopeExitFn__lambda_330d32309249a3947adb96a95f558109______ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___
0x18003dcfa  nop
0x18003dcfb  test    rdi, rdi
0x18003dcfe  jz      short loc_18003DD10
0x18003dd00  mov     rax, [rdi]
0x18003dd03  mov     rcx, rdi
0x18003dd06  mov     rax, [rax+10h]
0x18003dd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd0f  nop
0x18003dd10  test    rsi, rsi
0x18003dd13  jz      short loc_18003DD25
0x18003dd15  mov     rax, [rsi]
0x18003dd18  mov     rcx, rsi
0x18003dd1b  mov     rax, [rax+10h]
0x18003dd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd24  nop
0x18003dd25  mov     r15d, 8007000Eh
0x18003dd2b  jmp     loc_18003E1EE
0x18003dd30  mov     eax, [rbp+3Fh+arg_20]
0x18003dd33  mov     r12, [rbp+3Fh+arg_28]
0x18003dd37  xor     r13d, r13d
0x18003dd3a  cmp     r13d, eax
0x18003dd3d  jnb     loc_18003E131
0x18003dd43  mov     r14d, r13d
0x18003dd46  shl     r14, 6
0x18003dd4a  mov     rax, [rsp+130h+var_E0]
0x18003dd4f  mov     dword ptr [r14+rax], 40h ; '@'
0x18003dd57  mov     rbx, [rsp+130h+var_E0]
0x18003dd5c  xor     edx, edx; length
0x18003dd5e  mov     rcx, [r12+r14]; string
0x18003dd62  call    cs:__imp_WindowsGetStringRawBuffer
0x18003dd68  lea     r8, [rbx+8]
0x18003dd6c  add     r8, r14
0x18003dd6f  or      edx, 0FFFFFFFFh
0x18003dd72  mov     rcx, rax
0x18003dd75  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003dd7b  mov     r15d, eax
0x18003dd7e  test    eax, eax
0x18003dd80  js      loc_18003E0DE
0x18003dd86  mov     rbx, [rsp+130h+var_E0]
0x18003dd8b  xor     edx, edx; length
0x18003dd8d  mov     rcx, [r12+r14+8]; string
0x18003dd92  call    cs:__imp_WindowsGetStringRawBuffer
0x18003dd98  lea     r8, [rbx+10h]
0x18003dd9c  add     r8, r14
0x18003dd9f  or      edx, 0FFFFFFFFh
0x18003dda2  mov     rcx, rax
0x18003dda5  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003ddab  mov     r15d, eax
0x18003ddae  test    eax, eax
0x18003ddb0  js      loc_18003E08B
0x18003ddb6  mov     rbx, [rsp+130h+var_E0]
0x18003ddbb  xor     edx, edx; length
0x18003ddbd  mov     rcx, [r12+r14+10h]; string
0x18003ddc2  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ddc8  lea     r8, [rbx+38h]
0x18003ddcc  add     r8, r14
0x18003ddcf  or      edx, 0FFFFFFFFh
0x18003ddd2  mov     rcx, rax
0x18003ddd5  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003dddb  mov     r15d, eax
0x18003ddde  test    eax, eax
0x18003dde0  js      loc_18003E038
0x18003dde6  mov     rbx, [rsp+130h+var_E0]
0x18003ddeb  xor     edx, edx; length
0x18003dded  mov     rcx, [r12+r14+28h]; string
0x18003ddf2  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ddf8  lea     r8, [rbx+18h]
0x18003ddfc  add     r8, r14
0x18003ddff  or      edx, 0FFFFFFFFh
0x18003de02  mov     rcx, rax
0x18003de05  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003de0b  mov     r15d, eax
0x18003de0e  test    eax, eax
0x18003de10  js      loc_18003DFE5
0x18003de16  mov     rbx, [rsp+130h+var_E0]
0x18003de1b  xor     edx, edx; length
0x18003de1d  mov     rcx, [r12+r14+18h]; string
0x18003de22  call    cs:__imp_WindowsGetStringRawBuffer
0x18003de28  lea     r8, [rbx+28h]
0x18003de2c  add     r8, r14
0x18003de2f  or      edx, 0FFFFFFFFh
0x18003de32  mov     rcx, rax
0x18003de35  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18003de3b  mov     r15d, eax
0x18003de3e  test    eax, eax
0x18003de40  js      loc_18003DF92
0x18003de46  mov     ecx, [r12+r14+20h]
0x18003de4b  mov     rax, [rsp+130h+var_E0]
0x18003de50  mov     [r14+rax+30h], ecx
0x18003de55  mov     ecx, [r12+r14+38h]
0x18003de5a  test    ecx, ecx
0x18003de5c  jz      short loc_18003DEA1
0x18003de5e  sub     ecx, 1
0x18003de61  jz      short loc_18003DE91
0x18003de63  sub     ecx, 1
0x18003de66  jz      short loc_18003DE81
0x18003de68  cmp     ecx, 1
0x18003de6b  jnz     loc_18003DF0E
0x18003de71  mov     rax, [rsp+130h+var_E0]
0x18003de76  mov     dword ptr [r14+rax+24h], 5
0x18003de7f  jmp     short loc_18003DEAF
0x18003de81  mov     rax, [rsp+130h+var_E0]
0x18003de86  mov     dword ptr [r14+rax+24h], 4
0x18003de8f  jmp     short loc_18003DEAF
0x18003de91  mov     rax, [rsp+130h+var_E0]
0x18003de96  mov     dword ptr [r14+rax+24h], 2
0x18003de9f  jmp     short loc_18003DEAF
0x18003dea1  mov     rax, [rsp+130h+var_E0]
0x18003dea6  mov     dword ptr [r14+rax+24h], 1
0x18003deaf  mov     ecx, [r12+r14+34h]
0x18003deb4  test    ecx, ecx
0x18003deb6  jz      short loc_18003DECD
0x18003deb8  cmp     ecx, 1
0x18003debb  jnz     short loc_18003DF30
0x18003debd  mov     rax, [rsp+130h+var_E0]
0x18003dec2  mov     dword ptr [r14+rax+4], 4CAh
0x18003decb  jmp     short loc_18003DEDB
0x18003decd  mov     rax, [rsp+130h+var_E0]
0x18003ded2  mov     dword ptr [r14+rax+4], 4C8h
0x18003dedb  mov     ecx, [r12+r14+30h]
0x18003dee0  test    ecx, ecx
0x18003dee2  jz      short loc_18003DEF5
0x18003dee4  cmp     ecx, 1
0x18003dee7  jnz     short loc_18003DF52
0x18003dee9  mov     rax, [rsp+130h+var_E0]
0x18003deee  mov     [r14+rax+20h], ecx
0x18003def3  jmp     short loc_18003DF03
0x18003def5  mov     rax, [rsp+130h+var_E0]
0x18003defa  mov     dword ptr [r14+rax+20h], 0
0x18003df03  inc     r13d
0x18003df06  mov     eax, [rbp+3Fh+arg_20]
0x18003df09  jmp     loc_18003DD3A
0x18003df0e  lea     rcx, [rsp+70h]
0x18003df13  call    wil__details__ScopeExitFn__lambda_330d32309249a3947adb96a95f558109______ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___
0x18003df18  nop
0x18003df19  test    rdi, rdi
0x18003df1c  jz      short loc_18003DF2E
0x18003df1e  mov     rax, [rdi]
0x18003df21  mov     rcx, rdi
0x18003df24  mov     rax, [rax+10h]
0x18003df28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df2d  nop
0x18003df2e  jmp     short loc_18003DF72
0x18003df30  lea     rcx, [rsp+70h]
0x18003df35  call    wil__details__ScopeExitFn__lambda_330d32309249a3947adb96a95f558109______ScopeExitFn__lambda_330d32309249a3947adb96a95f558109___
0x18003df3a  nop
0x18003df3b  test    rdi, rdi
0x18003df3e  jz      short loc_18003DF50
0x18003df40  mov     rax, [rdi]
0x18003df43  mov     rcx, rdi
  ... truncated ...
```
