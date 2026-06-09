# SystemSettings::StorageSenseHandlers::AppsListWrapper::RemoveApp(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>)

- ea: `0x18007782c`
- end: `0x180077a56`
- name: `?RemoveApp@AppsListWrapper@StorageSenseHandlers@SystemSettings@@AEAAJV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@Z`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800726d8`

## callees

- `0x180006e50`
- `0x1800077ec`
- `0x18000c964`
- `0x180012374`
- `0x180023578`
- `0x180023928`
- `0x18005c450`
- `0x18005fa88`
- `0x1800623b4`
- `0x18006a180`
- `0x18006ae84`
- `0x18006fd5c`
- `0x180074560`
- `0x180074b70`
- `0x18007782c`
- `0x18007a648`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077876`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a16`
- `msvcp_win!_Mtx_unlock` at `0x180077910`
- `msvcp_win!_Mtx_unlock` at `0x180077a0a`
- `msvcp_win!_Mtx_unlock` at `0x180077910`
- `msvcp_win!_Mtx_unlock` at `0x180077a0a`

## string_xrefs

- `0x18007789d`: `CleanupRecommendations`
- `0x1800778b8`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommenderengine.cpp`
- `0x180077997`: `Uninstalled app: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::AppsListWrapper::RemoveApp(_QWORD *a1, HSTRING a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // ebx
  HSTRING v7; // rbx
  std::_Ref_count_base **v8; // rbx
  HSTRING v9; // r12
  __int64 AppId; // rax
  struct SystemSettings::StorageSenseHandlers::RecommendationSingleton *Instance; // rax
  std::_Ref_count_base **v13; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string[5]; // [rsp+38h] [rbp-21h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  string[1] = a2;
  string[0] = 0;
  v4 = *(_QWORD *)a2;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)a2 + 56LL);
  WindowsDeleteString(0);
  string[0] = 0;
  v6 = v5(v4, string);
  if ( v6 >= 0 )
  {
    v7 = string[0];
    string[2] = (HSTRING)(a1 + 148);
    std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 148));
    std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Microsoft::WRL::ComPtr_SystemSettings::StorageSenseHandlers::UnusedApplicationItem_________lambda_c995b92b967c00b64edb1a3433f2612f___(
      &v13,
      a1[158],
      a1[159],
      v7);
    v8 = v13;
    if ( v13 == (std::_Ref_count_base **)a1[159] )
    {
      _Mtx_unlock((_Mtx_t)(a1 + 148));
      v6 = -2147024893;
    }
    else
    {
      v9 = (HSTRING)operator new(0x20u);
      v13 = (std::_Ref_count_base **)v9;
      *(_OWORD *)v9 = 0;
      *((_DWORD *)v9 + 2) = 1;
      *((_DWORD *)v9 + 3) = 1;
      *(_QWORD *)v9 = &std::_Ref_count_obj2<SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalSuccessNotification>::`vftable';
      *((_QWORD *)v9 + 2) = &SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalSuccessNotification::`vftable';
      *((_QWORD *)v9 + 3) = 0;
      string[3] = v9 + 4;
      string[4] = v9;
      Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>::operator=(v9 + 6, v8);
      AppId = SystemSettings::StorageSenseHandlers::UnusedApplicationItem::GetAppId(*v8, v15);
      v13 = (std::_Ref_count_base **)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(AppId);
      CleanupRecommendationsLogger::ExecutionInfo<unsigned short const * &>((wchar_t *)L"Uninstalled app: %s", &v13);
      std::wstring::_Tidy_deallocate(v15);
      std::vector<Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::erase(
        a1 + 158,
        &v13,
        v8);
      Instance = SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance();
      *(_OWORD *)v15 = 0;
      _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
      v15[0] = (std::_Ref_count_base *)(v9 + 4);
      v15[1] = (std::_Ref_count_base *)v9;
      v13 = v15;
      SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(
        Instance,
        &v13);
      if ( v15[1] )
        std::_Ref_count_base::_Decref(v15[1]);
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v9);
      _Mtx_unlock((_Mtx_t)(a1 + 148));
      v6 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x63E,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommenderengine.cpp",
      (const char *)(unsigned int)v6,
      (int)"%hs",
      "CleanupRecommendations");
  }
  WindowsDeleteString(string[0]);
  string[0] = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007782c  mov     [rsp-8+arg_10], rbx
0x180077831  mov     [rsp-8+arg_18], rsi
0x180077836  push    rbp
0x180077837  push    rdi
0x180077838  push    r12
0x18007783a  push    r14
0x18007783c  push    r15
0x18007783e  lea     rbp, [rsp-37h]
0x180077843  sub     rsp, 90h
0x18007784a  mov     rax, cs:__security_cookie
0x180077851  xor     rax, rsp
0x180077854  mov     [rbp+57h+var_30], rax
0x180077858  mov     r14, rdx
0x18007785b  mov     r15, rcx
0x18007785e  mov     [rbp+57h+var_70], rdx
0x180077862  mov     [rbp+57h+string], 0
0x18007786a  mov     rdi, [rdx]
0x18007786d  mov     rax, [rdi]
0x180077870  mov     rbx, [rax+38h]
0x180077874  xor     ecx, ecx; string
0x180077876  call    cs:__imp_WindowsDeleteString
0x18007787c  mov     [rbp+57h+string], 0
0x180077884  lea     rdx, [rbp+57h+string]
0x180077888  mov     rcx, rdi
0x18007788b  mov     rax, rbx
0x18007788e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077893  mov     ebx, eax
0x180077895  test    eax, eax
0x180077897  jns     short loc_1800778CE
0x180077899  mov     rcx, [rbp+5Fh]; this
0x18007789d  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x1800778a4  mov     [rsp+0B0h+var_88], rax; char *
0x1800778a9  lea     rax, aHs; "%hs"
0x1800778b0  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x1800778b5  mov     r9d, ebx; char *
0x1800778b8  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\coresettinghandlers"...
0x1800778bf  mov     edx, 63Eh; void *
0x1800778c4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800778c9  jmp     loc_180077A12
0x1800778ce  mov     rbx, [rbp+57h+string]
0x1800778d2  lea     rsi, [r15+4A0h]
0x1800778d9  mov     [rbp+57h+var_68], rsi
0x1800778dd  mov     rcx, rsi; this
0x1800778e0  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800778e5  nop
0x1800778e6  mov     r9, rbx
0x1800778e9  mov     r8, [r15+4F8h]
0x1800778f0  mov     rdx, [r15+4F0h]
0x1800778f7  lea     rcx, [rbp+57h+var_80]
0x1800778fb  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_Microsoft__WRL__ComPtr_SystemSettings__StorageSenseHandlers__UnusedApplicationItem_________lambda_c995b92b967c00b64edb1a3433f2612f___
0x180077900  mov     rbx, [rbp+57h+var_80]
0x180077904  cmp     rbx, [r15+4F8h]
0x18007790b  jnz     short loc_180077920
0x18007790d  mov     rcx, rsi; _Mtx_t
0x180077910  call    cs:__imp__Mtx_unlock
0x180077916  mov     ebx, 80070003h
0x18007791b  jmp     loc_180077A12
0x180077920  mov     ecx, 20h ; ' '; Size
0x180077925  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007792a  mov     r12, rax
0x18007792d  mov     [rbp+57h+var_80], rax
0x180077931  xorps   xmm0, xmm0
0x180077934  movups  xmmword ptr [rax], xmm0
0x180077937  mov     dword ptr [rax+8], 1
0x18007793e  mov     dword ptr [rax+0Ch], 1
0x180077945  lea     rax, ??_7?$_Ref_count_obj2@UUnusedApplicationsRemovalSuccessNotification@StorageSenseHandlers@SystemSettings@@@std@@6B@; const std::_Ref_count_obj2<SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalSuccessNotification>::`vftable'
0x18007794c  mov     [r12], rax
0x180077950  lea     rdi, [r12+10h]
0x180077955  lea     rax, ??_7UnusedApplicationsRemovalSuccessNotification@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::UnusedApplicationsRemovalSuccessNotification::`vftable'
0x18007795c  mov     [rdi], rax
0x18007795f  mov     qword ptr [rdi+8], 0
0x180077967  mov     [rbp+57h+var_60], rdi
0x18007796b  mov     [rbp+57h+var_58], r12
0x18007796f  lea     rcx, [rdi+8]
0x180077973  mov     rdx, rbx
0x180077976  call    ??4?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>::operator=(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem> const &)
0x18007797b  lea     rdx, [rbp+57h+var_50]
0x18007797f  mov     rcx, [rbx]
0x180077982  call    ?GetAppId@UnusedApplicationItem@StorageSenseHandlers@SystemSettings@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SystemSettings::StorageSenseHandlers::UnusedApplicationItem::GetAppId(void)
0x180077987  mov     rcx, rax
0x18007798a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007798f  mov     [rbp+57h+var_80], rax
0x180077993  lea     rdx, [rbp+57h+var_80]
0x180077997  lea     rcx, aUninstalledApp; "Uninstalled app: %s"
0x18007799e  call    ??$ExecutionInfo@AEAPEBG@CleanupRecommendationsLogger@@SAXPEBGAEAPEBG@Z; CleanupRecommendationsLogger::ExecutionInfo<ushort const * &>(ushort const *,ushort const * &)
0x1800779a3  lea     rcx, [rbp+57h+var_50]
0x1800779a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800779ac  mov     r8, rbx
0x1800779af  lea     rdx, [rbp+57h+var_80]
0x1800779b3  lea     rcx, [r15+4F0h]
0x1800779ba  call    ?erase@?$vector@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VUnusedApplicationItem@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@std@@@2@@Z; std::vector<Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::UnusedApplicationItem>>>>)
0x1800779bf  call    ?GetInstance@RecommendationSingleton@StorageSenseHandlers@SystemSettings@@SAPEAV123@XZ; SystemSettings::StorageSenseHandlers::RecommendationSingleton::GetInstance(void)
0x1800779c4  xorps   xmm0, xmm0
0x1800779c7  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x1800779cc  lock inc dword ptr [r12+8]
0x1800779d2  mov     [rbp+57h+var_50], rdi
0x1800779d6  mov     [rbp+57h+var_50+8], r12
0x1800779da  lea     rcx, [rbp+57h+var_50]
0x1800779de  mov     [rbp+57h+var_80], rcx
0x1800779e2  lea     rdx, [rbp+57h+var_80]
0x1800779e6  mov     rcx, rax
0x1800779e9  call    ??$_Notify@V_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@?$CSingletonHelper@AEBV?$shared_ptr@UCleanupListHandlerEvent@StorageSenseHandlers@SystemSettings@@@std@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_@@@Z; SystemSettings::DataModel::CSingletonHelper<std::shared_ptr<SystemSettings::StorageSenseHandlers::CleanupListHandlerEvent> const &>::_Notify<_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_>(_lambda_7dbba1c7e7ffb19530f3f904d18f1b18_ const &)
0x1800779ee  nop
0x1800779ef  mov     rcx, [rbp+57h+var_50+8]; this
0x1800779f3  test    rcx, rcx
0x1800779f6  jz      short loc_1800779FE
0x1800779f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800779fd  nop
0x1800779fe  mov     rcx, r12; this
0x180077a01  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180077a06  nop
0x180077a07  mov     rcx, rsi; _Mtx_t
0x180077a0a  call    cs:__imp__Mtx_unlock
0x180077a10  xor     ebx, ebx
0x180077a12  mov     rcx, [rbp+57h+string]; string
0x180077a16  call    cs:__imp_WindowsDeleteString
0x180077a1c  mov     [rbp+57h+string], 0
0x180077a24  mov     rcx, r14
0x180077a27  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180077a2c  mov     eax, ebx
0x180077a2e  mov     rcx, [rbp+57h+var_30]
0x180077a32  xor     rcx, rsp; StackCookie
0x180077a35  call    __security_check_cookie
0x180077a3a  lea     r11, [rsp+0B0h+var_20]
0x180077a42  mov     rbx, [r11+40h]
0x180077a46  mov     rsi, [r11+48h]
0x180077a4a  mov     rsp, r11
0x180077a4d  pop     r15
0x180077a4f  pop     r14
0x180077a51  pop     r12
0x180077a53  pop     rdi
0x180077a54  pop     rbp
0x180077a55  retn
```
