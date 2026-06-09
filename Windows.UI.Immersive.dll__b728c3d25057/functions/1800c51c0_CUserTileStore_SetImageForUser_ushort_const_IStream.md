# CUserTileStore::SetImageForUser(ushort const *,IStream *)

- ea: `0x1800c51c0`
- end: `0x1800c541d`
- name: `?SetImageForUser@CUserTileStore@@UEAAJPEBGPEAUIStream@@@Z`
- size: `605`
- prototype: `int(CUserTileStore *__hidden this, const unsigned __int16 *, struct IStream *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000bb20`
- `0x18000bd60`
- `0x1800140e0`
- `0x18003217c`
- `0x180034768`
- `0x180034db4`
- `0x180039e34`
- `0x180050ba0`
- `0x18007fd38`
- `0x1800c51c0`
- `0x1800d36a4`
- `0x1800d4c58`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x1800c5274`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x1800c5274`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800c521b`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800c521b`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x1800c5393`
- `SHELL32!__imp_SHSetUserPicturePath` at `0x1800c5393`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c52c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800c52c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CUserTileStore::SetImageForUser(
        CUserTileStore *this,
        const unsigned __int16 *a2,
        struct IStream *a3)
{
  int v6; // eax
  unsigned int LastError; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, const unsigned __int16 *, struct IStream *, _QWORD); // rbx
  unsigned int ScaleFactorForDevice; // eax
  const char *v12; // r9
  int v13; // eax
  HRESULT TilePath; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int *v17; // [rsp+20h] [rbp-50h]
  PSID Sid; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR v19; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  int v21[2]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
  {
    v17 = v21;
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      UserTile_Store_Commit_Start,
      a3,
      1);
  }
  if ( (unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) )
    return 2147943660LL;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v6 = CoCreateInstanceAsSystem(&CLSID_UserTileBroker, &GUID_d6d737ff_9e13_4a65_be89_a1e013cc6b76, &v20);
  LastError = v6;
  if ( v6 < 0 )
  {
    v8 = 1498;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
      (const char *)(unsigned int)v6,
      (int)v17);
    goto LABEL_24;
  }
  v9 = v20;
  v10 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IStream *, _QWORD))(*(_QWORD *)v20 + 32LL);
  ScaleFactorForDevice = GetScaleFactorForDevice(1);
  v6 = v10(v9, a2, a3, ScaleFactorForDevice);
  LastError = v6;
  if ( v6 < 0 )
  {
    v8 = 1499;
    goto LABEL_9;
  }
  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    *(_QWORD *)v21 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v21,
      0);
    v13 = SHTranslateSIDToName(Sid, (wchar_t **)v21);
    LastError = v13;
    if ( v13 >= 0 )
    {
      v19 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v19,
        0);
      TilePath = _GetTilePath(1u, a2, 0, &v19);
      LastError = TilePath;
      if ( TilePath >= 0 )
      {
        TilePath = SHSetUserPicturePath(*(_QWORD *)v21, 0, v19);
        LastError = TilePath;
        if ( TilePath >= 0 )
        {
          if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(
              Microsoft_Windows_Shell_Core_Provider_Context,
              UserTile_Store_Commit_Stop,
              v16,
              1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v19);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v21);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
          LastError = 0;
          goto LABEL_24;
        }
        v15 = 1508;
      }
      else
      {
        v15 = 1507;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)TilePath,
        (int)v17);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v19);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E1,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
        (const char *)(unsigned int)v13,
        (int)v17);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v21);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5DF,
                  (unsigned int)"shell\\windowsuiimmersive\\userinfo\\userinfo.cpp",
                  v12);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return LastError;
}

```

## disassembly

```asm
0x1800c51c0  mov     [rsp-18h+arg_0], rbx
0x1800c51c5  mov     [rsp-18h+arg_18], rsi
0x1800c51ca  push    rbp
0x1800c51cb  push    rdi
0x1800c51cc  push    r14
0x1800c51ce  mov     rbp, rsp
0x1800c51d1  sub     rsp, 70h
0x1800c51d5  mov     rax, cs:__security_cookie
0x1800c51dc  xor     rax, rsp
0x1800c51df  mov     [rbp+var_8], rax
0x1800c51e3  mov     r14, r8
0x1800c51e6  mov     rsi, rdx
0x1800c51e9  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800c51f0  jz      short loc_1800C5214
0x1800c51f2  lea     rax, [rbp+var_28]
0x1800c51f6  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800c51fb  mov     r9d, 1
0x1800c5201  lea     rdx, UserTile_Store_Commit_Start
0x1800c5208  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1800c520f  call    McGenEventWrite_EventWriteTransfer
0x1800c5214  lea     rcx, POLID_UseDefaultTile
0x1800c521b  call    cs:__imp_SHWindowsPolicy
0x1800c5221  test    eax, eax
0x1800c5223  jz      short loc_1800C522F
0x1800c5225  mov     eax, 800704ECh
0x1800c522a  jmp     loc_1800C53FC
0x1800c522f  mov     [rbp+var_30], 0
0x1800c5237  lea     rcx, [rbp+var_30]
0x1800c523b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c5240  lea     r8, [rbp+var_30]
0x1800c5244  lea     rdx, _GUID_d6d737ff_9e13_4a65_be89_a1e013cc6b76
0x1800c524b  lea     rcx, CLSID_UserTileBroker
0x1800c5252  call    CoCreateInstanceAsSystem
0x1800c5257  mov     ebx, eax
0x1800c5259  test    eax, eax
0x1800c525b  jns     short loc_1800C5264
0x1800c525d  mov     edx, 5DAh
0x1800c5262  jmp     short loc_1800C5299
0x1800c5264  mov     rdi, [rbp+var_30]
0x1800c5268  mov     rax, [rdi]
0x1800c526b  mov     rbx, [rax+20h]
0x1800c526f  mov     ecx, 1
0x1800c5274  call    cs:__imp_GetScaleFactorForDevice
0x1800c527a  mov     r9d, eax
0x1800c527d  mov     r8, r14
0x1800c5280  mov     rdx, rsi
0x1800c5283  mov     rcx, rdi
0x1800c5286  mov     rax, rbx
0x1800c5289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c528e  mov     ebx, eax
0x1800c5290  test    eax, eax
0x1800c5292  jns     short loc_1800C52B1
0x1800c5294  mov     edx, 5DBh; void *
0x1800c5299  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800c52a0  mov     r9d, eax; char *
0x1800c52a3  mov     rcx, [rbp+18h]; this
0x1800c52a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c52ac  jmp     loc_1800C53F1
0x1800c52b1  mov     [rbp+Sid], 0
0x1800c52b9  lea     rdx, [rbp+Sid]; Sid
0x1800c52bd  mov     rcx, rsi; StringSid
0x1800c52c0  call    cs:__imp_ConvertStringSidToSidW
0x1800c52c6  test    eax, eax
0x1800c52c8  jnz     short loc_1800C52EF
0x1800c52ca  mov     rcx, [rbp+18h]; this
0x1800c52ce  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800c52d5  mov     edx, 5DFh; void *
0x1800c52da  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c52df  mov     ebx, eax
0x1800c52e1  lea     rcx, [rbp+Sid]
0x1800c52e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c52ea  jmp     loc_1800C53F1
0x1800c52ef  mov     qword ptr [rbp+var_28], 0
0x1800c52f7  xor     edx, edx
0x1800c52f9  lea     rcx, [rbp+var_28]
0x1800c52fd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c5302  lea     rdx, [rbp+var_28]
0x1800c5306  mov     rcx, [rbp+Sid]
0x1800c530a  call    SHTranslateSIDToName
0x1800c530f  mov     ebx, eax
0x1800c5311  test    eax, eax
0x1800c5313  jns     short loc_1800C5339
0x1800c5315  mov     rcx, [rbp+18h]; this
0x1800c5319  mov     r9d, eax; char *
0x1800c531c  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800c5323  mov     edx, 5E1h; void *
0x1800c5328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c532d  nop
0x1800c532e  lea     rcx, [rbp+var_28]
0x1800c5332  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c5337  jmp     short loc_1800C52E1
0x1800c5339  mov     [rbp+var_38], 0
0x1800c5341  xor     edx, edx
0x1800c5343  lea     rcx, [rbp+var_38]
0x1800c5347  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c534c  lea     r9, [rbp+var_38]
0x1800c5350  xor     r8d, r8d
0x1800c5353  mov     rdx, rsi
0x1800c5356  lea     ecx, [r8+1]
0x1800c535a  call    ?_GetTilePath@@YAJW4USER_TILE_TYPE@@PEBG_NPEAPEAG@Z; _GetTilePath(USER_TILE_TYPE,ushort const *,bool,ushort * *)
0x1800c535f  mov     ebx, eax
0x1800c5361  test    eax, eax
0x1800c5363  jns     short loc_1800C5389
0x1800c5365  mov     edx, 5E3h; void *
0x1800c536a  lea     r8, aShellWindowsui_8; "shell\\windowsuiimmersive\\userinfo\\us"...
0x1800c5371  mov     r9d, eax; char *
0x1800c5374  mov     rcx, [rbp+18h]; this
0x1800c5378  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c537d  nop
0x1800c537e  lea     rcx, [rbp+var_38]
0x1800c5382  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c5387  jmp     short loc_1800C532E
0x1800c5389  mov     r8, [rbp+var_38]
0x1800c538d  xor     edx, edx
0x1800c538f  mov     rcx, qword ptr [rbp+var_28]
0x1800c5393  call    cs:__imp_SHSetUserPicturePath
0x1800c5399  mov     ebx, eax
0x1800c539b  test    eax, eax
0x1800c539d  jns     short loc_1800C53A6
0x1800c539f  mov     edx, 5E4h
0x1800c53a4  jmp     short loc_1800C536A
0x1800c53a6  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x1800c53ad  jz      short loc_1800C53D2
0x1800c53af  lea     rax, [rbp+var_18]
0x1800c53b3  mov     qword ptr [rsp+70h+var_50], rax
0x1800c53b8  mov     r9d, 1
0x1800c53be  lea     rdx, UserTile_Store_Commit_Stop
0x1800c53c5  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1800c53cc  call    McGenEventWrite_EventWriteTransfer
0x1800c53d1  nop
0x1800c53d2  lea     rcx, [rbp+var_38]
0x1800c53d6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c53db  nop
0x1800c53dc  lea     rcx, [rbp+var_28]
0x1800c53e0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800c53e5  nop
0x1800c53e6  lea     rcx, [rbp+Sid]
0x1800c53ea  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800c53ef  xor     ebx, ebx
0x1800c53f1  lea     rcx, [rbp+var_30]
0x1800c53f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c53fa  mov     eax, ebx
0x1800c53fc  mov     rcx, [rbp+var_8]
0x1800c5400  xor     rcx, rsp; StackCookie
0x1800c5403  call    __security_check_cookie
0x1800c5408  lea     r11, [rsp+70h+var_s0]
0x1800c540d  mov     rbx, [r11+20h]
0x1800c5411  mov     rsi, [r11+38h]
0x1800c5415  mov     rsp, r11
0x1800c5418  pop     r14
0x1800c541a  pop     rdi
0x1800c541b  pop     rbp
0x1800c541c  retn
```
