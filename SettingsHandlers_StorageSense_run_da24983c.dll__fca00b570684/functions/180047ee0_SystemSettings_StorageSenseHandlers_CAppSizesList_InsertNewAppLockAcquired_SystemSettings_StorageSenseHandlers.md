# SystemSettings::StorageSenseHandlers::CAppSizesList::_InsertNewAppLockAcquired(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *)

- ea: `0x180047ee0`
- end: `0x18004815f`
- name: `?_InsertNewAppLockAcquired@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAAJPEAVCPackageSizeSetting@23@@Z`
- size: `639`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppSizesList *__hidden this, struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004303c`
- `0x180048168`
- `0x180049c8c`

## callees

- `0x18000e6cc`
- `0x180014940`
- `0x18001f230`
- `0x18001f53c`
- `0x180026994`
- `0x180038830`
- `0x180039580`
- `0x180040dc4`
- `0x1800440c0`
- `0x180044d90`
- `0x180046280`
- `0x180047ee0`
- `0x18004947c`
- `0x180049d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047f06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800480de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048145`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppSizesList::_InsertNewAppLockAcquired(
        SystemSettings::StorageSenseHandlers::CAppSizesList *this,
        SystemSettings::StorageSenseHandlers::CAppTileData **a2)
{
  char *v4; // rbx
  SystemSettings::StorageSenseHandlers::CAppSizesList *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  const char *v8; // r9
  __int64 result; // rax
  __int64 v10; // rbx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-58h]
  __int128 v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h]
  _QWORD v16[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HSTRING string; // [rsp+80h] [rbp+8h] BYREF
  SystemSettings::StorageSenseHandlers::CAppTileData **v19; // [rsp+88h] [rbp+10h] BYREF
  char *v20; // [rsp+90h] [rbp+18h] BYREF
  HSTRING v21; // [rsp+98h] [rbp+20h] BYREF

  v19 = a2;
  string = 0;
  v4 = (char *)this + 1072;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1072));
  v20 = v4;
  v21 = (HSTRING)*((_QWORD *)this + 131);
  Microsoft::WRL::Wrappers::HString::Set(&string, &v21);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v20);
  try
  {
    if ( SystemSettings::StorageSenseHandlers::CAppSizesList::_UpdateAppVisibility(
           v5,
           a2,
           string,
           *((_DWORD *)this + 259)) )
    {
      ++*((_DWORD *)this + 200);
      SystemSettings::StorageSenseHandlers::CAppSizesList::NotifyTotalAppsUpdated(this);
    }
    SystemSettings::StorageSenseHandlers::SortModes(v16);
    v6 = *((int *)this + 256);
    v7 = v16[0];
    if ( (int)v6 < (int)((__int64)(v16[1] - v16[0]) >> 4) )
    {
      if ( *(__int64 (__fastcall **)(const void *, const void *))(v16[0] + 16 * v6 + 8) == compareSizeDescending
        || *(__int64 (__fastcall **)(const void *, const void *))(v16[0] + 16 * v6 + 8) == compareSizeAscending )
      {
        SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetPackageSizeCallback((SystemSettings::StorageSenseHandlers::CPackageSizeSetting *)a2);
        v7 = v16[0];
      }
      v10 = *(_QWORD *)(v7 + 16LL * *((int *)this + 256) + 8);
      wil::to_vector<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>>(
        &v14,
        *((_QWORD *)this + 26));
      std::lower_bound_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Microsoft::WRL::ComPtr_SystemSettings::DataModel::ISettingItem________SystemSettings::StorageSenseHandlers::CPackageSizeSetting____lambda_a03b5597f87b3364fe5a7b4197c6713e___(
        (unsigned int)&v21,
        v14,
        DWORD2(v14),
        (unsigned int)&v19,
        v10);
      v11 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
              *((_QWORD *)this + 26),
              (__int64)((__int64)v21 - v14) >> 3,
              a2,
              0);
      v12 = v11;
      if ( v11 >= 0 )
      {
        if ( (_QWORD)v14 )
        {
          std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(
            v14,
            *((_QWORD *)&v14 + 1));
          std::_Deallocate<16>(v14, (v15 - v14) & 0xFFFFFFFFFFFFFFF8uLL);
          v14 = 0;
          v15 = 0;
        }
        std::vector<SystemSettings::StorageSenseHandlers::AppSortModes>::_Tidy(v16);
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v20);
        WindowsDeleteString(string);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE8,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
          (const char *)(unsigned int)v11,
          v13);
        if ( (_QWORD)v14 )
        {
          std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(
            v14,
            *((_QWORD *)&v14 + 1));
          std::_Deallocate<16>(v14, (v15 - v14) & 0xFFFFFFFFFFFFFFF8uLL);
          v14 = 0;
          v15 = 0;
        }
        std::vector<SystemSettings::StorageSenseHandlers::AppSortModes>::_Tidy(v16);
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v20);
        WindowsDeleteString(string);
        result = v12;
      }
    }
    else
    {
      std::vector<SystemSettings::StorageSenseHandlers::AppSortModes>::_Tidy(v16);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v20);
      WindowsDeleteString(string);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    LODWORD(v19) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xFEB,
                     (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
                     v8);
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x180047ee0  mov     rax, rsp
0x180047ee3  mov     [rax+10h], rdx
0x180047ee7  push    rbx
0x180047ee8  push    rsi
0x180047ee9  push    rdi
0x180047eea  sub     rsp, 60h
0x180047eee  mov     rsi, rdx
0x180047ef1  mov     rdi, rcx
0x180047ef4  mov     qword ptr [rax+8], 0
0x180047efc  lea     rbx, [rcx+430h]
0x180047f03  mov     rcx, rbx; lpCriticalSection
0x180047f06  call    cs:__imp_EnterCriticalSection
0x180047f0c  mov     [rsp+78h+arg_10], rbx
0x180047f14  mov     rax, [rdi+418h]
0x180047f1b  mov     [rsp+78h+arg_18], rax
0x180047f23  lea     rdx, [rsp+78h+arg_18]; HSTRING *
0x180047f2b  lea     rcx, [rsp+78h+string]; newString
0x180047f33  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180047f38  lea     rcx, [rsp+78h+arg_10]; this
0x180047f40  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180047f45  mov     r9d, [rdi+40Ch]; int
0x180047f4c  mov     r8, [rsp+78h+string]; HSTRING
0x180047f54  mov     rdx, rsi; struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *
0x180047f57  call    ?_UpdateAppVisibility@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAA_NPEAVCPackageSizeSetting@23@PEAUHSTRING__@@H@Z; SystemSettings::StorageSenseHandlers::CAppSizesList::_UpdateAppVisibility(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *,HSTRING__ *,int)
0x180047f5c  test    al, al
0x180047f5e  jz      short loc_180047F6E
0x180047f60  inc     dword ptr [rdi+320h]
0x180047f66  mov     rcx, rdi; this
0x180047f69  call    ?NotifyTotalAppsUpdated@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAAXXZ; SystemSettings::StorageSenseHandlers::CAppSizesList::NotifyTotalAppsUpdated(void)
0x180047f6e  lea     rcx, [rsp+78h+var_30]
0x180047f73  call    SystemSettings__StorageSenseHandlers__SortModes
0x180047f78  nop
0x180047f79  movsxd  rdx, dword ptr [rdi+400h]
0x180047f80  mov     rax, [rsp+78h+var_28]
0x180047f85  mov     rcx, [rsp+78h+var_30]
0x180047f8a  sub     rax, rcx
0x180047f8d  sar     rax, 4
0x180047f91  cmp     edx, eax
0x180047f93  jl      short loc_180047FC6
0x180047f95  lea     rcx, [rsp+78h+var_30]
0x180047f9a  call    ?_Tidy@?$vector@UAppSortModes@StorageSenseHandlers@SystemSettings@@V?$allocator@UAppSortModes@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::AppSortModes>::_Tidy(void)
0x180047f9f  nop
0x180047fa0  lea     rcx, [rsp+78h+arg_10]; this
0x180047fa8  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180047fad  nop
0x180047fae  mov     rcx, [rsp+78h+string]; string
0x180047fb6  call    cs:__imp_WindowsDeleteString
0x180047fbc  mov     eax, 80070057h
0x180047fc1  jmp     loc_180048156
0x180047fc6  mov     rax, rdx
0x180047fc9  add     rax, rax
0x180047fcc  lea     rdx, ?compareSizeDescending@@YAHPEBX0@Z; compareSizeDescending(void const *,void const *)
0x180047fd3  cmp     [rcx+rax*8+8], rdx
0x180047fd8  jz      short loc_180047FE8
0x180047fda  lea     rdx, ?compareSizeAscending@@YAHPEBX0@Z; compareSizeAscending(void const *,void const *)
0x180047fe1  cmp     [rcx+rax*8+8], rdx
0x180047fe6  jnz     short loc_180047FF5
0x180047fe8  mov     rcx, rsi; this
0x180047feb  call    ?GetPackageSizeCallback@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAXXZ; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetPackageSizeCallback(void)
0x180047ff0  mov     rcx, [rsp+78h+var_30]
0x180047ff5  movsxd  rax, dword ptr [rdi+400h]
0x180047ffc  add     rax, rax
0x180047fff  mov     rbx, [rcx+rax*8+8]
0x180048004  mov     rdx, [rdi+0D0h]
0x18004800b  lea     rcx, [rsp+78h+var_48]
0x180048010  call    ??$to_vector@U?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@@wil@@YA?A_PPEAU?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@@Z
0x180048015  nop
0x180048016  mov     qword ptr [rsp+78h+var_58], rbx; int
0x18004801b  lea     r9, [rsp+78h+arg_8]
0x180048023  mov     r8, qword ptr [rsp+78h+var_48+8]
0x180048028  mov     rdx, qword ptr [rsp+78h+var_48]
0x18004802d  lea     rcx, [rsp+78h+arg_18]
0x180048035  call    std__lower_bound_std___Vector_iterator_std___Vector_val_std___Simple_types_Microsoft__WRL__ComPtr_SystemSettings__DataModel__ISettingItem________SystemSettings__StorageSenseHandlers__CPackageSizeSetting____lambda_a03b5597f87b3364fe5a7b4197c6713e___
0x18004803a  mov     rdx, [rsp+78h+arg_18]
0x180048042  sub     rdx, qword ptr [rsp+78h+var_48]
0x180048047  sar     rdx, 3
0x18004804b  xor     r9d, r9d
0x18004804e  mov     r8, rsi
0x180048051  mov     rcx, [rdi+0D0h]
0x180048058  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x18004805d  mov     ebx, eax
0x18004805f  test    eax, eax
0x180048061  jns     loc_1800480E8
0x180048067  mov     rcx, [rsp+78h]; this
0x18004806c  mov     r9d, eax; char *
0x18004806f  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x180048076  mov     edx, 0FE8h; void *
0x18004807b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048080  nop
0x180048081  mov     rcx, qword ptr [rsp+78h+var_48]
0x180048086  test    rcx, rcx
0x180048089  jz      short loc_1800480BD
0x18004808b  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x180048090  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> *,Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> * const,std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>> &)
0x180048095  mov     rcx, qword ptr [rsp+78h+var_48]
0x18004809a  mov     rdx, [rsp+78h+var_38]
0x18004809f  sub     rdx, rcx
0x1800480a2  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800480a6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800480ab  xorps   xmm0, xmm0
0x1800480ae  movdqu  [rsp+78h+var_48], xmm0
0x1800480b4  mov     [rsp+78h+var_38], 0
0x1800480bd  lea     rcx, [rsp+78h+var_30]
0x1800480c2  call    ?_Tidy@?$vector@UAppSortModes@StorageSenseHandlers@SystemSettings@@V?$allocator@UAppSortModes@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::AppSortModes>::_Tidy(void)
0x1800480c7  nop
0x1800480c8  lea     rcx, [rsp+78h+arg_10]; this
0x1800480d0  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800480d5  nop
0x1800480d6  mov     rcx, [rsp+78h+string]; string
0x1800480de  call    cs:__imp_WindowsDeleteString
0x1800480e4  mov     eax, ebx
0x1800480e6  jmp     short loc_180048156
0x1800480e8  mov     rcx, qword ptr [rsp+78h+var_48]
0x1800480ed  test    rcx, rcx
0x1800480f0  jz      short loc_180048124
0x1800480f2  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1800480f7  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>>(Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> *,Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem> * const,std::allocator<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>> &)
0x1800480fc  mov     rcx, qword ptr [rsp+78h+var_48]
0x180048101  mov     rdx, [rsp+78h+var_38]
0x180048106  sub     rdx, rcx
0x180048109  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004810d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180048112  xorps   xmm0, xmm0
0x180048115  movdqu  [rsp+78h+var_48], xmm0
0x18004811b  mov     [rsp+78h+var_38], 0
0x180048124  lea     rcx, [rsp+78h+var_30]
0x180048129  call    ?_Tidy@?$vector@UAppSortModes@StorageSenseHandlers@SystemSettings@@V?$allocator@UAppSortModes@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::AppSortModes>::_Tidy(void)
0x18004812e  nop
0x18004812f  lea     rcx, [rsp+78h+arg_10]; this
0x180048137  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18004813c  nop
0x18004813d  mov     rcx, [rsp+78h+string]; string
0x180048145  call    cs:__imp_WindowsDeleteString
0x18004814b  xor     eax, eax
0x18004814d  jmp     short loc_180048156
0x18004814f  mov     eax, dword ptr [rsp+78h+arg_8]
0x180048156  add     rsp, 60h
0x18004815a  pop     rdi
0x18004815b  pop     rsi
0x18004815c  pop     rbx
0x18004815d  retn
```
