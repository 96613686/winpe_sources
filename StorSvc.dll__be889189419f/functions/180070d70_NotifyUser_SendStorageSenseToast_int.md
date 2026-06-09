# NotifyUser::SendStorageSenseToast(int)

- ea: `0x180070d70`
- end: `0x1800710a7`
- name: `?SendStorageSenseToast@NotifyUser@@QEAAEH@Z`
- size: `823`
- prototype: `unsigned __int8 __fastcall(NotifyUser *__hidden this, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006fd7c`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180014a00`
- `0x180017500`
- `0x180019bc4`
- `0x180019d4c`
- `0x180019dd4`
- `0x18001c130`
- `0x18001c208`
- `0x18001c5ec`
- `0x18001dcf4`
- `0x18002ebb4`
- `0x18003584c`
- `0x18004b7c0`
- `0x180057218`
- `0x180065344`
- `0x1800702f4`
- `0x180070bc4`
- `0x180070d70`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071037`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070e99`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180070e99`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180070e84`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180070e84`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180070f2c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180071002`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180070f2c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180071002`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180070e49`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180070e49`

## string_xrefs

- `0x180070f11`: `RegisterSystemToastComponentFailed`
- `0x18007103f`: `UserImpersonationFailed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall NotifyUser::SendStorageSenseToast(struct Windows::System::IUser **this, unsigned int a2)
{
  NotifyUser *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // ebx
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rax
  DWORD LastError; // ebx
  __int64 v13; // rax
  HANDLE Token; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  char v17; // [rsp+49h] [rbp-B7h]
  unsigned __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __m256i v19; // [rsp+60h] [rbp-A0h]
  __int128 v20; // [rsp+80h] [rbp-80h]
  __int128 v21; // [rsp+90h] [rbp-70h]
  __int128 v22; // [rsp+A0h] [rbp-60h]
  __m256i v23; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v24; // [rsp+D0h] [rbp-30h]
  __int128 v25; // [rsp+E0h] [rbp-20h]
  __int128 v26; // [rsp+F0h] [rbp-10h]
  _BYTE v27[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v28[32]; // [rsp+120h] [rbp+20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+140h] [rbp+40h] BYREF
  __int64 v30; // [rsp+158h] [rbp+58h]

  v18 = 0;
  hExistingToken = 0;
  Token = 0;
  std::wstring::wstring(v28);
  memset_0(&v23, 0, 0x50u);
  v16 = 0;
  v30 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  if ( (int)Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
              v30,
              (__int64)&v16) < 0
    || (*(int (__fastcall **)(__int64, struct Windows::System::IUser *, unsigned __int64 *))(*(_QWORD *)v16 + 136LL))(
         v16,
         *this,
         &v18) < 0
    || (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hExistingToken,
          0),
        (int)UMgrQueryUserToken(v18, &hExistingToken) < 0)
    || (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &Token,
          0),
        !DuplicateTokenEx(hExistingToken, 4u, 0, SecurityImpersonation, TokenImpersonation, &Token))
    || !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v13 = std::string::string(v27, "UserImpersonationFailed");
    StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(v13, LastError);
    goto LABEL_15;
  }
  v17 = 1;
  if ( a2 == -1 )
  {
    std::wstring::operator=(v28, qword_1800C9AB0);
  }
  else
  {
    v5 = std::to_wstring(v27, a2);
    v6 = std::operator+<unsigned short>(&hstringHeader, qword_1800C9AD0, v5);
    std::wstring::operator=(v28, v6);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    std::wstring::_Tidy_deallocate(v27);
  }
  v7 = NotifyUser::RegisterSystemToastComponent(v4, v18);
  if ( v7 < 0 )
  {
    v8 = std::string::string(v27, "RegisterSystemToastComponentFailed");
    StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(v8, (unsigned int)v7);
    RevertToSelf();
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
    std::wstring::_Tidy_deallocate(v28);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
    return 0;
  }
  v19.m256i_i64[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800C9A70);
  v19.m256i_i32[2] = 3005;
  *(__int64 *)((char *)&v19.m256i_i64[1] + 4) = 3006;
  v19.m256i_i32[5] = 0;
  v19.m256i_i64[3] = 0;
  v20 = 0u;
  *(_QWORD *)&v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800C9A30);
  *((_QWORD *)&v21 + 1) = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800C9A50);
  *(_QWORD *)&v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  *((_QWORD *)&v22 + 1) = L"Foreground";
  v23 = v19;
  v24 = v20;
  v25 = v21;
  v26 = v22;
  v9 = LaunchToast(*this, (const struct TOAST_DATA *)&v23);
  if ( v9 < 0 )
  {
    v10 = std::string::string(v27, "LaunchToastFailed");
    StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(v10, (unsigned int)v9);
  }
  RevertToSelf();
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  std::wstring::_Tidy_deallocate(v28);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
  return v9 >= 0;
}

```

## disassembly

```asm
0x180070d70  mov     [rsp-8+arg_10], rbx
0x180070d75  mov     [rsp-8+arg_18], rdi
0x180070d7a  push    rbp
0x180070d7b  lea     rbp, [rsp-70h]
0x180070d80  sub     rsp, 170h
0x180070d87  mov     rax, cs:__security_cookie
0x180070d8e  xor     rax, rsp
0x180070d91  mov     [rbp+70h+var_10], rax
0x180070d95  mov     ebx, edx
0x180070d97  mov     rdi, rcx
0x180070d9a  mov     [rsp+170h+var_120], 0
0x180070da3  mov     [rsp+170h+hExistingToken], 0
0x180070dac  mov     [rsp+170h+Token], 0
0x180070db5  lea     rcx, [rbp+70h+var_50]
0x180070db9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180070dbe  nop
0x180070dbf  xor     edx, edx; Val
0x180070dc1  lea     r8d, [rdx+50h]; Size
0x180070dc5  lea     rcx, [rbp+70h+var_C0]; void *
0x180070dc9  call    memset_0
0x180070dce  mov     [rsp+170h+var_130], 0
0x180070dd7  mov     [rbp+70h+var_18], 0
0x180070ddf  mov     r9d, 23h ; '#'; unsigned int
0x180070de5  lea     r8d, [r9+1]; unsigned int
0x180070de9  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180070df0  lea     rcx, [rbp+70h+hstringHeader]; hstringHeader
0x180070df4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180070df9  lea     rdx, [rsp+170h+var_130]
0x180070dfe  mov     rcx, [rbp+70h+var_18]
0x180070e02  call    ??$GetActivationFactory@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UISignInStateManager@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>)
0x180070e07  test    eax, eax
0x180070e09  js      loc_180071037
0x180070e0f  mov     rcx, [rsp+170h+var_130]
0x180070e14  mov     rax, [rcx]
0x180070e17  lea     r8, [rsp+170h+var_120]
0x180070e1c  mov     rdx, [rdi]
0x180070e1f  mov     rax, [rax+88h]
0x180070e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070e2b  test    eax, eax
0x180070e2d  js      loc_180071037
0x180070e33  xor     edx, edx
0x180070e35  lea     rcx, [rsp+170h+hExistingToken]
0x180070e3a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180070e3f  lea     rdx, [rsp+170h+hExistingToken]
0x180070e44  mov     rcx, [rsp+170h+var_120]
0x180070e49  call    cs:__imp_UMgrQueryUserToken
0x180070e4f  test    eax, eax
0x180070e51  js      loc_180071037
0x180070e57  xor     edx, edx
0x180070e59  lea     rcx, [rsp+170h+Token]
0x180070e5e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180070e63  lea     rax, [rsp+170h+Token]
0x180070e68  mov     [rsp+170h+phNewToken], rax; phNewToken
0x180070e6d  mov     r9d, 2; ImpersonationLevel
0x180070e73  mov     [rsp+170h+TokenType], r9d; TokenType
0x180070e78  xor     r8d, r8d; lpTokenAttributes
0x180070e7b  lea     edx, [r9+2]; dwDesiredAccess
0x180070e7f  mov     rcx, [rsp+170h+hExistingToken]; hExistingToken
0x180070e84  call    cs:__imp_DuplicateTokenEx
0x180070e8a  test    eax, eax
0x180070e8c  jz      loc_180071037
0x180070e92  mov     rdx, [rsp+170h+Token]; Token
0x180070e97  xor     ecx, ecx; Thread
0x180070e99  call    cs:__imp_SetThreadToken
0x180070e9f  test    eax, eax
0x180070ea1  jz      loc_180071037
0x180070ea7  mov     [rsp+170h+var_127], 1
0x180070eac  cmp     ebx, 0FFFFFFFFh
0x180070eaf  jnz     short loc_180070EC3
0x180070eb1  lea     rdx, qword_1800C9AB0
0x180070eb8  lea     rcx, [rbp+70h+var_50]
0x180070ebc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180070ec1  jmp     short loc_180070F01
0x180070ec3  mov     edx, ebx
0x180070ec5  lea     rcx, [rbp+70h+var_70]
0x180070ec9  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x180070ece  nop
0x180070ecf  mov     r8, rax
0x180070ed2  lea     rdx, qword_1800C9AD0
0x180070ed9  lea     rcx, [rbp+70h+hstringHeader]
0x180070edd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x180070ee2  mov     rdx, rax
0x180070ee5  lea     rcx, [rbp+70h+var_50]
0x180070ee9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180070eee  lea     rcx, [rbp+70h+hstringHeader]
0x180070ef2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070ef7  nop
0x180070ef8  lea     rcx, [rbp+70h+var_70]
0x180070efc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070f01  mov     rdx, [rsp+170h+var_120]; unsigned __int64
0x180070f06  call    ?RegisterSystemToastComponent@NotifyUser@@AEAAJ_K@Z; NotifyUser::RegisterSystemToastComponent(unsigned __int64)
0x180070f0b  mov     ebx, eax
0x180070f0d  test    eax, eax
0x180070f0f  jns     short loc_180070F38
0x180070f11  lea     rdx, aRegistersystem; "RegisterSystemToastComponentFailed"
0x180070f18  lea     rcx, [rbp+70h+var_70]
0x180070f1c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180070f21  mov     edx, ebx
0x180070f23  mov     rcx, rax
0x180070f26  call    ?TraceLoggingWriteStatusErrorCode@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(std::string,ulong)
0x180070f2b  nop
0x180070f2c  call    cs:__imp_RevertToSelf
0x180070f32  nop
0x180070f33  jmp     loc_18007105A
0x180070f38  lea     rcx, qword_1800C9A70
0x180070f3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070f44  mov     qword ptr [rsp+170h+var_110], rax
0x180070f49  mov     dword ptr [rsp+170h+var_110+8], 0BBDh
0x180070f51  mov     qword ptr [rsp+170h+var_110+0Ch], 0BBEh
0x180070f5a  xor     eax, eax
0x180070f5c  mov     [rsp+170h+var_FC], eax
0x180070f60  mov     [rsp+170h+var_F8], rax
0x180070f65  mov     qword ptr [rbp+70h+var_F0], rax
0x180070f69  mov     qword ptr [rbp+70h+var_F0+8], rax
0x180070f6d  lea     rcx, qword_1800C9A30
0x180070f74  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070f79  mov     qword ptr [rbp+70h+var_E0], rax
0x180070f7d  lea     rcx, qword_1800C9A50
0x180070f84  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070f89  mov     qword ptr [rbp+70h+var_E0+8], rax
0x180070f8d  lea     rcx, [rbp+70h+var_50]
0x180070f91  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070f96  mov     qword ptr [rbp+70h+var_D0], rax
0x180070f9a  lea     rax, aForeground; "Foreground"
0x180070fa1  mov     qword ptr [rbp+70h+var_D0+8], rax
0x180070fa5  movups  xmm0, [rsp+170h+var_110]
0x180070faa  movaps  [rbp+70h+var_C0], xmm0
0x180070fae  movups  xmm1, xmmword ptr [rsp+70h]
0x180070fb3  movaps  [rbp+70h+var_B0], xmm1
0x180070fb7  movups  xmm0, [rbp+70h+var_F0]
0x180070fbb  movaps  [rbp+70h+var_A0], xmm0
0x180070fbf  movups  xmm1, [rbp+70h+var_E0]
0x180070fc3  movaps  [rbp+70h+var_90], xmm1
0x180070fc7  movups  xmm0, [rbp+70h+var_D0]
0x180070fcb  movaps  [rbp+70h+var_80], xmm0
0x180070fcf  lea     rdx, [rbp+70h+var_C0]; struct TOAST_DATA *
0x180070fd3  mov     rcx, [rdi]; struct Windows::System::IUser *
0x180070fd6  call    ?LaunchToast@@YAJPEAUIUser@System@Windows@@PEBUTOAST_DATA@@@Z; LaunchToast(Windows::System::IUser *,TOAST_DATA const *)
0x180070fdb  mov     ebx, eax
0x180070fdd  test    eax, eax
0x180070fdf  jns     short loc_180070FFC
0x180070fe1  lea     rdx, aLaunchtoastfai; "LaunchToastFailed"
0x180070fe8  lea     rcx, [rbp+70h+var_70]
0x180070fec  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180070ff1  mov     edx, ebx
0x180070ff3  mov     rcx, rax
0x180070ff6  call    ?TraceLoggingWriteStatusErrorCode@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(std::string,ulong)
0x180070ffb  nop
0x180070ffc  shr     ebx, 1Fh
0x180070fff  xor     bl, 1
0x180071002  call    cs:__imp_RevertToSelf
0x180071008  nop
0x180071009  lea     rcx, [rsp+170h+var_130]
0x18007100e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180071013  nop
0x180071014  lea     rcx, [rbp+70h+var_50]
0x180071018  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007101d  nop
0x18007101e  lea     rcx, [rsp+170h+Token]
0x180071023  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180071028  nop
0x180071029  lea     rcx, [rsp+170h+hExistingToken]
0x18007102e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180071033  mov     al, bl
0x180071035  jmp     short loc_180071086
0x180071037  call    cs:__imp_GetLastError
0x18007103d  mov     ebx, eax
0x18007103f  lea     rdx, aUserimpersonat; "UserImpersonationFailed"
0x180071046  lea     rcx, [rbp+70h+var_70]
0x18007104a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007104f  mov     edx, ebx
0x180071051  mov     rcx, rax
0x180071054  call    ?TraceLoggingWriteStatusErrorCode@StorageHealthMonitorTelemetry@@SAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; StorageHealthMonitorTelemetry::TraceLoggingWriteStatusErrorCode(std::string,ulong)
0x180071059  nop
0x18007105a  lea     rcx, [rsp+170h+var_130]
0x18007105f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180071064  nop
0x180071065  lea     rcx, [rbp+70h+var_50]
0x180071069  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007106e  nop
0x18007106f  lea     rcx, [rsp+170h+Token]
0x180071074  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180071079  nop
0x18007107a  lea     rcx, [rsp+170h+hExistingToken]
0x18007107f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180071084  xor     al, al
0x180071086  mov     rcx, [rbp+70h+var_10]
0x18007108a  xor     rcx, rsp; StackCookie
0x18007108d  call    __security_check_cookie
0x180071092  lea     r11, [rsp+170h+var_s0]
0x18007109a  mov     rbx, [r11+20h]
0x18007109e  mov     rdi, [r11+28h]
0x1800710a2  mov     rsp, r11
0x1800710a5  pop     rbp
0x1800710a6  retn
```
