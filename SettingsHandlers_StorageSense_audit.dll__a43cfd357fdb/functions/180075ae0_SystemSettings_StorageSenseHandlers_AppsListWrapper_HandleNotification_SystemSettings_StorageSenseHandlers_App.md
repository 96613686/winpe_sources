# SystemSettings::StorageSenseHandlers::AppsListWrapper::HandleNotification(SystemSettings::StorageSenseHandlers::AppEnumNotification *)

- ea: `0x180075ae0`
- end: `0x180075d95`
- name: `?HandleNotification@AppsListWrapper@StorageSenseHandlers@SystemSettings@@MEAAXPEAUAppEnumNotification@23@@Z`
- size: `693`
- prototype: `void __fastcall(SystemSettings::StorageSenseHandlers::AppsListWrapper *__hidden this, struct SystemSettings::StorageSenseHandlers::AppEnumNotification *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c964`
- `0x18001f468`
- `0x18001f784`
- `0x18003b0a0`
- `0x18006a180`
- `0x18006ae84`
- `0x18006c374`
- `0x18006ee38`
- `0x1800724d4`
- `0x180075ae0`
- `0x18007a57c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180075cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075ca6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180075ca6`
- `msvcp_win!_Mtx_unlock` at `0x180075c48`
- `msvcp_win!_Mtx_unlock` at `0x180075d5b`
- `msvcp_win!_Mtx_unlock` at `0x180075c48`
- `msvcp_win!_Mtx_unlock` at `0x180075d5b`

## string_xrefs

- `0x180075b03`: `CleanupRecommendations`
- `0x180075b81`: `CleanupRecommendations`
- `0x180075bd2`: `CleanupRecommendations`
- `0x180075b21`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180075b9f`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180075bf0`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall SystemSettings::StorageSenseHandlers::AppsListWrapper::HandleNotification(
        SystemSettings::StorageSenseHandlers::AppsListWrapper *this,
        struct SystemSettings::StorageSenseHandlers::AppEnumNotification *a2)
{
  unsigned int v4; // r12d
  char *v5; // rsi
  __int64 v6; // rbx
  char v7; // r13
  struct _Mtx_internal_imp_t *v8; // r14
  void (__fastcall *v9)(__int64, HSTRING *); // rdi
  _QWORD v10[2]; // [rsp+30h] [rbp-78h] BYREF
  struct _Mtx_internal_imp_t *v11; // [rsp+40h] [rbp-68h]
  char *v12; // [rsp+48h] [rbp-60h]
  char *v13; // [rsp+50h] [rbp-58h] BYREF
  __int64 v14; // [rsp+58h] [rbp-50h] BYREF
  char v15; // [rsp+60h] [rbp-48h]
  unsigned int v16; // [rsp+64h] [rbp-44h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  __int64 v18; // [rsp+B8h] [rbp+10h] BYREF
  HSTRING string; // [rsp+C0h] [rbp+18h] BYREF
  char *v20; // [rsp+C8h] [rbp+20h] BYREF

  if ( !a2 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x4E2,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)0x80004003LL,
      (int)"%hs",
      "CleanupRecommendations");
    return;
  }
  v4 = *((_DWORD *)a2 + 1);
  v5 = (char *)this - 232;
  v20 = (char *)this - 232;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v20);
  v6 = *((_QWORD *)a2 + 1);
  v18 = v6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v18);
  if ( !*((_QWORD *)a2 + 1) )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x4EE,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)0x8007000ELL,
      (int)"%hs",
      "CleanupRecommendations");
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v18);
    goto LABEL_17;
  }
  if ( v4 > 2 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x4F6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)0x80070057LL,
      (int)"%hs",
      "CleanupRecommendations");
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v18);
    goto LABEL_17;
  }
  v7 = *((_BYTE *)a2 + 16);
  v8 = (SystemSettings::StorageSenseHandlers::AppsListWrapper *)((char *)this + 1392);
  v11 = (SystemSettings::StorageSenseHandlers::AppsListWrapper *)((char *)this + 1392);
  v12 = (char *)this + 1392;
  std::_Mutex_base::lock((SystemSettings::StorageSenseHandlers::AppsListWrapper *)((char *)this + 1392));
  if ( v4 )
  {
LABEL_11:
    v13 = v5;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v13);
    v14 = v6;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v14);
    try
    {
      v15 = v7;
      v16 = v4;
      std::thread::_Start__lambda_ab28329ee579c64e4d84bcb5dcc5862d____(v10, &v13);
      if ( v4 )
        std::thread::detach((std::thread *)v10);
      else
        std::vector<std::thread>::_Emplace_one_at_back<std::thread>((char *)this + 1480, v10);
      std::thread::~thread((std::thread *)v10);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtExceptionMsg(
        retaddr,
        (void *)0x52F,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
        "%hs",
        "CleanupRecommendations");
      v5 = v20;
      v8 = v11;
    }
    lambda_ab28329ee579c64e4d84bcb5dcc5862d_::__lambda_ab28329ee579c64e4d84bcb5dcc5862d_(&v13);
    _Mtx_unlock(v8);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v18);
    goto LABEL_17;
  }
  if ( !*((_BYTE *)this + 1473) )
  {
    string = 0;
    v9 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v9(v6, &string);
    v10[0] = WindowsGetStringRawBuffer(string, 0);
    CleanupRecommendationsLogger::ExecutionInfo<unsigned short const * &>((wchar_t *)L"Received notification to add app: %s");
    *((_BYTE *)this + 1472) = 1;
    WindowsDeleteString(string);
    goto LABEL_11;
  }
  _Mtx_unlock((SystemSettings::StorageSenseHandlers::AppsListWrapper *)((char *)this + 1392));
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v18);
LABEL_17:
  if ( v5 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 16LL))(v5);
}

```

## disassembly

```asm
0x180075ae0  push    rbx
0x180075ae2  push    rsi
0x180075ae3  push    rdi
0x180075ae4  push    r12
0x180075ae6  push    r13
0x180075ae8  push    r14
0x180075aea  push    r15
0x180075aec  sub     rsp, 70h
0x180075af0  mov     rdi, rdx
0x180075af3  mov     r15, rcx
0x180075af6  test    rdx, rdx
0x180075af9  jnz     short loc_180075B37
0x180075afb  mov     rcx, [rsp+0A8h]; this
0x180075b03  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180075b0a  mov     [rsp+0A8h+var_80], rax; char *
0x180075b0f  lea     rax, aHs; "%hs"
0x180075b16  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180075b1b  mov     r9d, 80004003h; char *
0x180075b21  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180075b28  mov     edx, 4E2h; void *
0x180075b2d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180075b32  jmp     loc_180075D85
0x180075b37  mov     r12d, [rdx+4]
0x180075b3b  lea     rsi, [rcx-0E8h]
0x180075b42  mov     [rsp+0A8h+arg_18], rsi
0x180075b4a  lea     rcx, [rsp+0A8h+arg_18]
0x180075b52  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180075b57  nop
0x180075b58  mov     rbx, [rdi+8]
0x180075b5c  mov     [rsp+0A8h+arg_8], rbx
0x180075b64  lea     rcx, [rsp+0A8h+arg_8]
0x180075b6c  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180075b71  nop
0x180075b72  cmp     qword ptr [rdi+8], 0
0x180075b77  jnz     short loc_180075BC4
0x180075b79  mov     rcx, [rsp+0A8h]; this
0x180075b81  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180075b88  mov     [rsp+0A8h+var_80], rax; char *
0x180075b8d  lea     rax, aHs; "%hs"
0x180075b94  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180075b99  mov     r9d, 8007000Eh; char *
0x180075b9f  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180075ba6  mov     edx, 4EEh; void *
0x180075bab  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180075bb0  nop
0x180075bb1  lea     rcx, [rsp+0A8h+arg_8]
0x180075bb9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180075bbe  nop
0x180075bbf  jmp     loc_180075D70
0x180075bc4  cmp     r12d, 2
0x180075bc8  jbe     short loc_180075C15
0x180075bca  mov     rcx, [rsp+0A8h]; this
0x180075bd2  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180075bd9  mov     [rsp+0A8h+var_80], rax; char *
0x180075bde  lea     rax, aHs; "%hs"
0x180075be5  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180075bea  mov     r9d, 80070057h; char *
0x180075bf0  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180075bf7  mov     edx, 4F6h; void *
0x180075bfc  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180075c01  nop
0x180075c02  lea     rcx, [rsp+0A8h+arg_8]
0x180075c0a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180075c0f  nop
0x180075c10  jmp     loc_180075D70
0x180075c15  mov     r13b, [rdi+10h]
0x180075c19  lea     r14, [r15+570h]
0x180075c20  mov     [rsp+0A8h+var_68], r14
0x180075c25  mov     [rsp+0A8h+var_60], r14
0x180075c2a  mov     rcx, r14; this
0x180075c2d  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180075c32  nop
0x180075c33  test    r12d, r12d
0x180075c36  jnz     loc_180075CD8
0x180075c3c  cmp     [r15+5C1h], r12b
0x180075c43  jz      short loc_180075C62
0x180075c45  mov     rcx, r14; _Mtx_t
0x180075c48  call    cs:__imp__Mtx_unlock
0x180075c4e  nop
0x180075c4f  lea     rcx, [rsp+0A8h+arg_8]
0x180075c57  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180075c5c  nop
0x180075c5d  jmp     loc_180075D70
0x180075c62  mov     [rsp+0A8h+string], 0
0x180075c6e  mov     rax, [rbx]
0x180075c71  mov     rdi, [rax+38h]
0x180075c75  xor     ecx, ecx; string
0x180075c77  call    cs:__imp_WindowsDeleteString
0x180075c7d  mov     [rsp+0A8h+string], 0
0x180075c89  lea     rdx, [rsp+0A8h+string]
0x180075c91  mov     rcx, rbx
0x180075c94  mov     rax, rdi
0x180075c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c9c  xor     edx, edx; length
0x180075c9e  mov     rcx, [rsp+0A8h+string]; string
0x180075ca6  call    cs:__imp_WindowsGetStringRawBuffer
0x180075cac  mov     [rsp+0A8h+var_78], rax
0x180075cb1  lea     rdx, [rsp+0A8h+var_78]
0x180075cb6  lea     rcx, aReceivedNotifi; "Received notification to add app: %s"
0x180075cbd  call    ??$ExecutionInfo@AEAPEBG@CleanupRecommendationsLogger@@SAXPEBGAEAPEBG@Z; CleanupRecommendationsLogger::ExecutionInfo<ushort const * &>(ushort const *,ushort const * &)
0x180075cc2  mov     byte ptr [r15+5C0h], 1
0x180075cca  mov     rcx, [rsp+0A8h+string]; string
0x180075cd2  call    cs:__imp_WindowsDeleteString
0x180075cd8  mov     [rsp+0A8h+var_58], rsi
0x180075cdd  lea     rcx, [rsp+0A8h+var_58]
0x180075ce2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180075ce7  mov     [rsp+0A8h+var_50], rbx
0x180075cec  lea     rcx, [rsp+0A8h+var_50]
0x180075cf1  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180075cf6  mov     [rsp+0A8h+var_48], r13b
0x180075cfb  mov     [rsp+0A8h+var_44], r12d
0x180075d00  lea     rdx, [rsp+0A8h+var_58]
0x180075d05  lea     rcx, [rsp+0A8h+var_78]
0x180075d0a  call    std__thread___Start__lambda_ab28329ee579c64e4d84bcb5dcc5862d____
0x180075d0f  test    r12d, r12d
0x180075d12  jnz     short loc_180075D28
0x180075d14  lea     rdx, [rsp+0A8h+var_78]
0x180075d19  lea     rcx, [r15+5C8h]
0x180075d20  call    ??$_Emplace_one_at_back@Vthread@std@@@?$vector@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@AEAAAEAVthread@1@$$QEAV21@@Z; std::vector<std::thread>::_Emplace_one_at_back<std::thread>(std::thread &&)
0x180075d25  nop
0x180075d26  jmp     short loc_180075D33
0x180075d28  lea     rcx, [rsp+0A8h+var_78]; this
0x180075d2d  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x180075d32  nop
0x180075d33  lea     rcx, [rsp+0A8h+var_78]; this
0x180075d38  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180075d3d  nop
0x180075d3e  jmp     short loc_180075D4D
0x180075d40  mov     rsi, [rsp+0A8h+arg_18]
0x180075d48  mov     r14, [rsp+0A8h+var_68]
0x180075d4d  lea     rcx, [rsp+0A8h+var_58]
0x180075d52  call    _lambda_ab28329ee579c64e4d84bcb5dcc5862d_____lambda_ab28329ee579c64e4d84bcb5dcc5862d_
0x180075d57  nop
0x180075d58  mov     rcx, r14; _Mtx_t
0x180075d5b  call    cs:__imp__Mtx_unlock
0x180075d61  nop
0x180075d62  lea     rcx, [rsp+0A8h+arg_8]
0x180075d6a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180075d6f  nop
0x180075d70  test    rsi, rsi
0x180075d73  jz      short loc_180075D85
0x180075d75  mov     rax, [rsi]
0x180075d78  mov     rcx, rsi
0x180075d7b  mov     rax, [rax+10h]
0x180075d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d84  nop
0x180075d85  add     rsp, 70h
0x180075d89  pop     r15
0x180075d8b  pop     r14
0x180075d8d  pop     r13
0x180075d8f  pop     r12
0x180075d91  pop     rdi
0x180075d92  pop     rsi
0x180075d93  pop     rbx
0x180075d94  retn
```
