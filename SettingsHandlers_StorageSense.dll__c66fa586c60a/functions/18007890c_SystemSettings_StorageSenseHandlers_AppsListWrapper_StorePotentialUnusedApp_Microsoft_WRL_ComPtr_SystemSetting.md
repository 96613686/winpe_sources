# SystemSettings::StorageSenseHandlers::AppsListWrapper::StorePotentialUnusedApp(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>,bool)

- ea: `0x18007890c`
- end: `0x180078dcf`
- name: `?StorePotentialUnusedApp@AppsListWrapper@StorageSenseHandlers@SystemSettings@@AEAAJV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@_N@Z`
- size: `1219`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::AppsListWrapper *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800726d8`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x180012374`
- `0x18001f468`
- `0x180023578`
- `0x180023928`
- `0x1800402fc`
- `0x180040c70`
- `0x18006a180`
- `0x18006af04`
- `0x18006af90`
- `0x18006b150`
- `0x18006b430`
- `0x180074560`
- `0x180076998`
- `0x180076a64`
- `0x180076ac8`
- `0x180076b1c`
- `0x18007890c`
- `0x18007a934`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078ae8`
- `msvcp_win!_Mtx_unlock` at `0x180078c2a`
- `msvcp_win!_Mtx_unlock` at `0x180078d71`
- `msvcp_win!_Mtx_unlock` at `0x180078c2a`
- `msvcp_win!_Mtx_unlock` at `0x180078d71`

## string_xrefs

- `0x18007896b`: `CleanupRecommendations`
- `0x180078a07`: `CleanupRecommendations`
- `0x180078a7e`: `CleanupRecommendations`
- `0x180078c46`: `CleanupRecommendations`
- `0x180078cab`: `CleanupRecommendations`
- `0x18007898b`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180078a22`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180078a99`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180078c61`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180078cc6`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::StorageSenseHandlers::AppsListWrapper::StorePotentialUnusedApp(
        void **this,
        __int64 a2,
        char a3)
{
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v5; // rsi
  int LastUsedTimestamp; // edi
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v7; // rcx
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v8; // rcx
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v9; // rcx
  __int64 v10; // rcx
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v11; // rcx
  _QWORD *v12; // r15
  __int64 v13; // rax
  _QWORD *v14; // rdi
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v15; // rcx
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v16; // rcx
  __int64 AppId; // rax
  __int64 v19; // rcx
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v20; // rcx
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v21; // rcx
  unsigned __int8 v22[8]; // [rsp+30h] [rbp-88h] BYREF
  SystemSettings::StorageSenseHandlers::UnusedApplicationItem *v23; // [rsp+38h] [rbp-80h] BYREF
  HSTRING StringRawBuffer; // [rsp+40h] [rbp-78h] BYREF
  _Mtx_t v25; // [rsp+48h] [rbp-70h] BYREF
  __int64 v26; // [rsp+50h] [rbp-68h] BYREF
  unsigned __int8 *v27; // [rsp+58h] [rbp-60h]
  __int64 v28; // [rsp+60h] [rbp-58h]
  _BYTE v29[32]; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  char v31; // [rsp+D0h] [rbp+18h] BYREF

  v31 = a3;
  v28 = a2;
  StringRawBuffer = (HSTRING)&v31;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::UnusedApplicationItem,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData> &,bool *>(
    &v23,
    a2,
    &StringRawBuffer);
  v5 = v23;
  if ( !v23 )
  {
    LastUsedTimestamp = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x535,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)0x8007000ELL,
      (int)"%hs",
      "CleanupRecommendations");
    v7 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *))(*(_QWORD *)v7 + 16LL))(v7);
    }
LABEL_35:
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a2);
    return (unsigned int)LastUsedTimestamp;
  }
  StringRawBuffer = 0;
  v22[0] = 1;
  SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetIsUninstallableAndToolTipMessage(
    v23,
    (bool *)v22,
    &StringRawBuffer);
  if ( !v22[0] )
    goto LABEL_16;
  LastUsedTimestamp = SystemSettings::StorageSenseHandlers::UnusedApplicationItem::LoadLastUsedTimestamp(v5, this + 145);
  if ( LastUsedTimestamp < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x53F,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)(unsigned int)LastUsedTimestamp,
      (int)"%hs",
      "CleanupRecommendations");
    v8 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_35;
  }
  if ( *((_QWORD *)v5 + 46) == -1 )
  {
    LastUsedTimestamp = SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetPackageSize(
                          v5,
                          1,
                          (unsigned __int64 *)v5 + 46);
    if ( LastUsedTimestamp < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x540,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
        (const char *)(unsigned int)LastUsedTimestamp,
        (int)"%hs",
        "CleanupRecommendations");
      v9 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      goto LABEL_35;
    }
  }
  v22[0] = SystemSettings::StorageSenseHandlers::AppsListWrapper::IsValidUnusedAppRecommendation(
             (SystemSettings::StorageSenseHandlers::AppsListWrapper *)this,
             v5);
  StringRawBuffer = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)v5 + 52), 0);
  CleanupRecommendationsLogger::ExecutionInfo<bool &,unsigned short const *>(v10, v22, &StringRawBuffer);
  if ( !v22[0] )
  {
LABEL_16:
    v11 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    LastUsedTimestamp = 0;
    goto LABEL_35;
  }
  v25 = (_Mtx_t)(this + 183);
  v26 = (__int64)(this + 183);
  std::_Mutex_base::lock((std::_Mutex_base *)(this + 183));
  try
  {
    v27 = (unsigned __int8 *)this + 1361;
    StringRawBuffer = (HSTRING)v5;
    if ( *((_BYTE *)this + 1361) )
    {
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&StringRawBuffer);
      v14 = this + 167;
      std::vector<Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::push_back(
        this + 167,
        &StringRawBuffer);
      if ( StringRawBuffer )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)StringRawBuffer + 16LL))(StringRawBuffer);
      v13 = (__int64)this[168] - *v14;
      v12 = this + 164;
    }
    else
    {
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&StringRawBuffer);
      v12 = this + 164;
      std::vector<Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::push_back(
        this + 164,
        &StringRawBuffer);
      if ( StringRawBuffer )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)StringRawBuffer + 16LL))(StringRawBuffer);
      v13 = (__int64)this[165] - *v12;
      v14 = this + 167;
    }
    v26 = v13 >> 3;
    StringRawBuffer = (HSTRING)((__int64)(v14[1] - *v14) >> 3);
    v25 = (_Mtx_t)((__int64)(v12[1] - *v12) >> 3);
    CleanupRecommendationsLogger::ExecutionInfo<unsigned __int64,unsigned __int64>(
      (wchar_t *)L"Potential unused apps: primary buffer: %d; secondary buffer: %d",
      &v25,
      &StringRawBuffer);
    _Mtx_unlock((_Mtx_t)(this + 183));
  }
  catch ( ... )
  {
    LODWORD(StringRawBuffer) = wil::details::in1diag3::Return_CaughtExceptionMsg(
                                 retaddr,
                                 (void *)0x55F,
                                 (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
                                 "%hs",
                                 "CleanupRecommendations");
    _Mtx_unlock(v25);
    v21 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v28);
    return (unsigned int)StringRawBuffer;
  }
  LastUsedTimestamp = SystemSettings::StorageSenseHandlers::UnusedApplicationItem::LoadAppId(v5);
  if ( LastUsedTimestamp < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x568,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)(unsigned int)LastUsedTimestamp,
      (int)"%hs",
      "CleanupRecommendations");
    v15 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_35;
  }
  LastUsedTimestamp = SystemSettings::StorageSenseHandlers::UnusedApplicationItem::LoadDescription(v5);
  if ( LastUsedTimestamp < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x569,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)(unsigned int)LastUsedTimestamp,
      (int)"%hs",
      "CleanupRecommendations");
    v16 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_35;
  }
  AppId = SystemSettings::StorageSenseHandlers::UnusedApplicationItem::GetAppId(v5, v29);
  v25 = (_Mtx_t)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(AppId);
  CleanupRecommendationsLogger::ExecutionInfo<unsigned __int64 &,unsigned short const *,bool &>(v19, &v26, &v25, v27);
  std::wstring::_Tidy_deallocate(v29);
  v20 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::UnusedApplicationItem *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a2);
  return 0;
}

```

## disassembly

```asm
0x18007890c  mov     r11, rsp
0x18007890f  mov     [r11+20h], rsi
0x180078913  mov     [r11+18h], r8b
0x180078917  push    rdi
0x180078918  push    r12
0x18007891a  push    r13
0x18007891c  push    r14
0x18007891e  push    r15
0x180078920  sub     rsp, 90h
0x180078927  mov     rax, cs:__security_cookie
0x18007892e  xor     rax, rsp
0x180078931  mov     [rsp+0B8h+var_30], rax
0x180078939  mov     r13, rdx
0x18007893c  mov     r14, rcx
0x18007893f  mov     [r11-58h], rdx
0x180078943  lea     rax, [r11+18h]
0x180078947  mov     [r11-78h], rax
0x18007894b  lea     r8, [r11-78h]
0x18007894f  lea     rcx, [r11-80h]
0x180078953  call    ??$Make@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@AEAV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@PEA_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@12@AEAV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAPEA_N@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::UnusedApplicationItem,Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData> &,bool *>(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData> &,bool * &&)
0x180078958  nop
0x180078959  mov     rsi, [rsp+0B8h+var_80]
0x18007895e  test    rsi, rsi
0x180078961  jnz     short loc_1800789BE
0x180078963  mov     rcx, [rsp+0B8h]; this
0x18007896b  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180078972  mov     [rsp+0B8h+var_90], rax; char *
0x180078977  lea     rax, aHs; "%hs"
0x18007897e  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180078983  mov     edi, 8007000Eh
0x180078988  mov     r9d, edi; char *
0x18007898b  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180078992  mov     edx, 535h; void *
0x180078997  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007899c  nop
0x18007899d  mov     rcx, [rsp+0B8h+var_80]
0x1800789a2  test    rcx, rcx
0x1800789a5  jz      short loc_1800789B9
0x1800789a7  mov     [rsp+0B8h+var_80], rsi
0x1800789ac  mov     rax, [rcx]
0x1800789af  mov     rax, [rax+10h]
0x1800789b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789b8  nop
0x1800789b9  jmp     loc_180078CF8
0x1800789be  mov     [rsp+0B8h+var_78], 0
0x1800789c7  mov     [rsp+0B8h+var_88], 1
0x1800789cc  lea     r8, [rsp+0B8h+var_78]; HSTRING *
0x1800789d1  lea     rdx, [rsp+0B8h+var_88]; bool *
0x1800789d6  mov     rcx, rsi; this
0x1800789d9  call    ?GetIsUninstallableAndToolTipMessage@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@AEAAJPEA_NPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetIsUninstallableAndToolTipMessage(bool *,HSTRING__ * *)
0x1800789de  cmp     [rsp+0B8h+var_88], 0
0x1800789e3  jnz     short loc_1800789EA
0x1800789e5  jmp     loc_180078B09
0x1800789ea  lea     rdx, [r14+488h]; void **
0x1800789f1  mov     rcx, rsi; this
0x1800789f4  call    ?LoadLastUsedTimestamp@UnusedApplicationItem@StorageSenseHandlers@SystemSettings@@QEAAJAEBQEAX@Z; SystemSettings::StorageSenseHandlers::UnusedApplicationItem::LoadLastUsedTimestamp(void * const &)
0x1800789f9  mov     edi, eax
0x1800789fb  test    eax, eax
0x1800789fd  jns     short loc_180078A59
0x1800789ff  mov     rcx, [rsp+0B8h]; this
0x180078a07  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180078a0e  mov     [rsp+0B8h+var_90], rax; char *
0x180078a13  lea     rax, aHs; "%hs"
0x180078a1a  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180078a1f  mov     r9d, edi; char *
0x180078a22  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180078a29  mov     edx, 53Fh; void *
0x180078a2e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180078a33  nop
0x180078a34  mov     rcx, [rsp+0B8h+var_80]
0x180078a39  test    rcx, rcx
0x180078a3c  jz      short loc_180078A54
0x180078a3e  mov     [rsp+0B8h+var_80], 0
0x180078a47  mov     rax, [rcx]
0x180078a4a  mov     rax, [rax+10h]
0x180078a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a53  nop
0x180078a54  jmp     loc_180078CF8
0x180078a59  lea     r8, [rsi+170h]; unsigned __int64 *
0x180078a60  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180078a64  jnz     short loc_180078AD0
0x180078a66  mov     dl, 1; bool
0x180078a68  mov     rcx, rsi; this
0x180078a6b  call    ?GetPackageSize@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAJ_NPEA_K@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetPackageSize(bool,unsigned __int64 *)
0x180078a70  mov     edi, eax
0x180078a72  test    eax, eax
0x180078a74  jns     short loc_180078AD0
0x180078a76  mov     rcx, [rsp+0B8h]; this
0x180078a7e  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180078a85  mov     [rsp+0B8h+var_90], rax; char *
0x180078a8a  lea     rax, aHs; "%hs"
0x180078a91  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180078a96  mov     r9d, edi; char *
0x180078a99  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180078aa0  mov     edx, 540h; void *
0x180078aa5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180078aaa  nop
0x180078aab  mov     rcx, [rsp+0B8h+var_80]
0x180078ab0  test    rcx, rcx
0x180078ab3  jz      short loc_180078ACB
0x180078ab5  mov     [rsp+0B8h+var_80], 0
0x180078abe  mov     rax, [rcx]
0x180078ac1  mov     rax, [rax+10h]
0x180078ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078aca  nop
0x180078acb  jmp     loc_180078CF8
0x180078ad0  mov     rdx, rsi; struct SystemSettings::StorageSenseHandlers::UnusedApplicationItem *
0x180078ad3  mov     rcx, r14; this
0x180078ad6  call    ?IsValidUnusedAppRecommendation@AppsListWrapper@StorageSenseHandlers@SystemSettings@@AEBA_NPEBVUnusedApplicationItem@23@@Z; SystemSettings::StorageSenseHandlers::AppsListWrapper::IsValidUnusedAppRecommendation(SystemSettings::StorageSenseHandlers::UnusedApplicationItem const *)
0x180078adb  mov     [rsp+0B8h+var_88], al
0x180078adf  xor     edx, edx; length
0x180078ae1  mov     rcx, [rsi+1A0h]; string
0x180078ae8  call    cs:__imp_WindowsGetStringRawBuffer
0x180078aee  mov     [rsp+0B8h+var_78], rax
0x180078af3  lea     r8, [rsp+0B8h+var_78]
0x180078af8  lea     rdx, [rsp+0B8h+var_88]
0x180078afd  call    ??$ExecutionInfo@AEA_NPEBG@CleanupRecommendationsLogger@@SAXPEBGAEA_N$$QEAPEBG@Z; CleanupRecommendationsLogger::ExecutionInfo<bool &,ushort const *>(ushort const *,bool &,ushort const * &&)
0x180078b02  cmp     [rsp+0B8h+var_88], 0
0x180078b07  jnz     short loc_180078B30
0x180078b09  mov     rcx, [rsp+0B8h+var_80]
0x180078b0e  test    rcx, rcx
0x180078b11  jz      short loc_180078B29
0x180078b13  mov     [rsp+0B8h+var_80], 0
0x180078b1c  mov     rax, [rcx]
0x180078b1f  mov     rax, [rax+10h]
0x180078b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b28  nop
0x180078b29  xor     edi, edi
0x180078b2b  jmp     loc_180078CF8
0x180078b30  lea     r12, [r14+5B8h]
0x180078b37  mov     [rsp+0B8h+var_70], r12
0x180078b3c  mov     [rsp+0B8h+var_68], r12
0x180078b41  mov     rcx, r12; this
0x180078b44  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180078b49  nop
0x180078b4a  lea     rax, [r14+551h]
0x180078b51  mov     [rsp+0B8h+var_60], rax
0x180078b56  mov     [rsp+0B8h+var_78], rsi
0x180078b5b  lea     rcx, [rsp+0B8h+var_78]
0x180078b60  cmp     byte ptr [rax], 0
0x180078b63  jnz     short loc_180078BA7
0x180078b65  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180078b6a  nop
0x180078b6b  lea     r15, [r14+520h]
0x180078b72  lea     rdx, [rsp+0B8h+var_78]
0x180078b77  mov     rcx, r15
0x180078b7a  call    ?push_back@?$vector@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAV?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@Z; std::vector<Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::push_back(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem> &&)
0x180078b7f  nop
0x180078b80  mov     rcx, [rsp+0B8h+var_78]
0x180078b85  test    rcx, rcx
0x180078b88  jz      short loc_180078B97
0x180078b8a  mov     rax, [rcx]
0x180078b8d  mov     rax, [rax+10h]
0x180078b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b96  nop
0x180078b97  mov     rax, [r15+8]
0x180078b9b  sub     rax, [r15]
0x180078b9e  lea     rdi, [r14+538h]
0x180078ba5  jmp     short loc_180078BE7
0x180078ba7  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180078bac  nop
0x180078bad  lea     rdi, [r14+538h]
0x180078bb4  lea     rdx, [rsp+0B8h+var_78]
0x180078bb9  mov     rcx, rdi
0x180078bbc  call    ?push_back@?$vector@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAV?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@Z; std::vector<Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::push_back(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem> &&)
0x180078bc1  nop
0x180078bc2  mov     rcx, [rsp+0B8h+var_78]
0x180078bc7  test    rcx, rcx
0x180078bca  jz      short loc_180078BD9
0x180078bcc  mov     rax, [rcx]
0x180078bcf  mov     rax, [rax+10h]
0x180078bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078bd8  nop
0x180078bd9  mov     rax, [rdi+8]
0x180078bdd  sub     rax, [rdi]
0x180078be0  lea     r15, [r14+520h]
0x180078be7  sar     rax, 3
0x180078beb  mov     [rsp+0B8h+var_68], rax
0x180078bf0  mov     rax, [rdi+8]
0x180078bf4  sub     rax, [rdi]
0x180078bf7  sar     rax, 3
0x180078bfb  mov     [rsp+0B8h+var_78], rax
0x180078c00  mov     rax, [r15+8]
0x180078c04  sub     rax, [r15]
0x180078c07  sar     rax, 3
0x180078c0b  mov     [rsp+0B8h+var_70], rax
0x180078c10  lea     r8, [rsp+0B8h+var_78]
0x180078c15  lea     rdx, [rsp+0B8h+var_70]
0x180078c1a  lea     rcx, aPotentialUnuse_0; "Potential unused apps: primary buffer: "...
0x180078c21  call    ??$ExecutionInfo@_K_K@CleanupRecommendationsLogger@@SAXPEBG$$QEA_K1@Z; CleanupRecommendationsLogger::ExecutionInfo<unsigned __int64,unsigned __int64>(ushort const *,unsigned __int64 &&,unsigned __int64 &&)
0x180078c26  nop
0x180078c27  mov     rcx, r12; _Mtx_t
0x180078c2a  call    cs:__imp__Mtx_unlock
0x180078c30  mov     rcx, rsi; this
0x180078c33  call    ?LoadAppId@UnusedApplicationItem@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::UnusedApplicationItem::LoadAppId(void)
0x180078c38  mov     edi, eax
0x180078c3a  test    eax, eax
0x180078c3c  jns     short loc_180078C95
0x180078c3e  mov     rcx, [rsp+0B8h]; this
0x180078c46  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180078c4d  mov     [rsp+0B8h+var_90], rax; char *
0x180078c52  lea     rax, aHs; "%hs"
0x180078c59  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180078c5e  mov     r9d, edi; char *
0x180078c61  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180078c68  mov     edx, 568h; void *
0x180078c6d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180078c72  nop
0x180078c73  mov     rcx, [rsp+0B8h+var_80]
0x180078c78  test    rcx, rcx
0x180078c7b  jz      short loc_180078C93
0x180078c7d  mov     [rsp+0B8h+var_80], 0
0x180078c86  mov     rax, [rcx]
0x180078c89  mov     rax, [rax+10h]
0x180078c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c92  nop
0x180078c93  jmp     short loc_180078CF8
0x180078c95  mov     rcx, rsi; this
0x180078c98  call    ?LoadDescription@UnusedApplicationItem@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::UnusedApplicationItem::LoadDescription(void)
0x180078c9d  mov     edi, eax
0x180078c9f  test    eax, eax
0x180078ca1  jns     short loc_180078D07
0x180078ca3  mov     rcx, [rsp+0B8h]; this
0x180078cab  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180078cb2  mov     [rsp+0B8h+var_90], rax; char *
0x180078cb7  lea     rax, aHs; "%hs"
0x180078cbe  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180078cc3  mov     r9d, edi; char *
0x180078cc6  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x180078ccd  mov     edx, 569h; void *
0x180078cd2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180078cd7  nop
0x180078cd8  mov     rcx, [rsp+0B8h+var_80]
0x180078cdd  test    rcx, rcx
0x180078ce0  jz      short loc_180078CF8
0x180078ce2  mov     [rsp+0B8h+var_80], 0
0x180078ceb  mov     rax, [rcx]
0x180078cee  mov     rax, [rax+10h]
0x180078cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078cf7  nop
0x180078cf8  mov     rcx, r13
0x180078cfb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180078d00  mov     eax, edi
0x180078d02  jmp     loc_180078DA6
0x180078d07  lea     rdx, [rsp+0B8h+var_50]
0x180078d0c  mov     rcx, rsi
0x180078d0f  call    ?GetAppId@UnusedApplicationItem@StorageSenseHandlers@SystemSettings@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SystemSettings::StorageSenseHandlers::UnusedApplicationItem::GetAppId(void)
0x180078d14  mov     rcx, rax
0x180078d17  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180078d1c  mov     [rsp+0B8h+var_70], rax
0x180078d21  mov     r9, [rsp+0B8h+var_60]
0x180078d26  lea     r8, [rsp+0B8h+var_70]
0x180078d2b  lea     rdx, [rsp+0B8h+var_68]
0x180078d30  call    ??$ExecutionInfo@AEA_KPEBGAEA_N@CleanupRecommendationsLogger@@SAXPEBGAEA_K$$QEAPEBGAEA_N@Z; CleanupRecommendationsLogger::ExecutionInfo<unsigned __int64 &,ushort const *,bool &>(ushort const *,unsigned __int64 &,ushort const * &&,bool &)
0x180078d35  lea     rcx, [rsp+0B8h+var_50]
0x180078d3a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180078d3f  nop
0x180078d40  mov     rcx, [rsp+0B8h+var_80]
0x180078d45  test    rcx, rcx
0x180078d48  jz      short loc_180078D60
0x180078d4a  mov     [rsp+0B8h+var_80], 0
0x180078d53  mov     rax, [rcx]
0x180078d56  mov     rax, [rax+10h]
0x180078d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d5f  nop
0x180078d60  mov     rcx, r13
0x180078d63  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180078d68  xor     eax, eax
0x180078d6a  jmp     short loc_180078DA6
0x180078d6c  mov     rcx, [rsp+0B8h+var_70]; _Mtx_t
0x180078d71  call    cs:__imp__Mtx_unlock
0x180078d77  nop
0x180078d78  mov     rcx, [rsp+0B8h+var_80]
0x180078d7d  test    rcx, rcx
0x180078d80  jz      short loc_180078D98
0x180078d82  mov     [rsp+0B8h+var_80], 0
0x180078d8b  mov     rax, [rcx]
0x180078d8e  mov     rax, [rax+10h]
0x180078d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d97  nop
0x180078d98  mov     rcx, [rsp+0B8h+var_58]
0x180078d9d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180078da2  mov     eax, dword ptr [rsp+0B8h+var_78]
0x180078da6  mov     rcx, [rsp+0B8h+var_30]
0x180078dae  xor     rcx, rsp; StackCookie
0x180078db1  call    __security_check_cookie
0x180078db6  mov     rsi, [rsp+0B8h+arg_18]
0x180078dbe  add     rsp, 90h
0x180078dc5  pop     r15
0x180078dc7  pop     r14
0x180078dc9  pop     r13
0x180078dcb  pop     r12
0x180078dcd  pop     rdi
0x180078dce  retn
```
