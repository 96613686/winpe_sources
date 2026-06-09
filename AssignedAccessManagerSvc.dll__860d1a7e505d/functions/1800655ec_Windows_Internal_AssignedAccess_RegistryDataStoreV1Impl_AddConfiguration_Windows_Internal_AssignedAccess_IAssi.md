# Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::AddConfiguration(Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *)

- ea: `0x1800655ec`
- end: `0x180065a23`
- name: `?AddConfiguration@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXPEAUIAssignedAccessConfiguration@234@@Z`
- size: `1079`
- prototype: `void __fastcall(Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *__hidden this, struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066590`

## callees

- `0x180006640`
- `0x18000cfe4`
- `0x180010590`
- `0x180020050`
- `0x18002be50`
- `0x1800575cc`
- `0x18006440c`
- `0x180064d08`
- `0x180064d90`
- `0x180064ebc`
- `0x1800651d0`
- `0x1800655ec`
- `0x1800665dc`
- `0x180066928`
- `0x180066a5c`
- `0x180066d38`
- `0x180066f90`
- `0x180066fc4`
- `0x180096010`

## string_xrefs

- `0x1800659a5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180065641`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065679`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065920`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065935`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065951`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065966`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x18006597b`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`
- `0x180065990`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1impl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::AddConfiguration(
        Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *this,
        struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *a2)
{
  __int64 v3; // rax
  int v4; // eax
  int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  unsigned int v9; // esi
  int i; // eax
  struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *v11; // rdi
  __int64 (__fastcall *v12)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD, struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo **); // rbx
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  char v18; // al
  Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *v19; // rcx
  _QWORD *v20; // rax
  int v21; // eax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // [rsp+20h] [rbp-E0h]
  char v27[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *v28; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+44h] [rbp-BCh] BYREF
  Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *v31; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *v32; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *v33; // [rsp+58h] [rbp-A8h]
  unsigned int v34; // [rsp+60h] [rbp-A0h]
  struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *v35; // [rsp+68h] [rbp-98h] BYREF
  __int128 v36; // [rsp+70h] [rbp-90h] BYREF
  IID v37; // [rsp+80h] [rbp-80h] BYREF
  Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *v38; // [rsp+90h] [rbp-70h]
  _BYTE v39[24]; // [rsp+A0h] [rbp-60h] BYREF
  char v40[8]; // [rsp+B8h] [rbp-48h] BYREF
  int v41; // [rsp+C0h] [rbp-40h]
  char v42[8]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v43[24]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v44[24]; // [rsp+E8h] [rbp-18h] BYREF
  char v45[16]; // [rsp+100h] [rbp+0h] BYREF
  IID v46; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v3 = *(_QWORD *)a2;
  v32 = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessConfiguration *, struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **))(v3 + 80))(
         a2,
         &v32);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
      (const char *)(unsigned int)v4,
      v26);
  v30 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, int *))(*(_QWORD *)v32 + 56LL))(
         v32,
         &v30);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
      (const char *)(unsigned int)v5,
      v26);
  if ( v30 )
  {
    Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(*((_QWORD *)this + 1), v44, v6, (char *)this + 48);
    Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(*((_QWORD *)this + 1), v39, v7, (char *)this + 80);
    Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(*((_QWORD *)this + 1), v43, v8, (char *)this + 112);
    v36 = 0;
    std::_Tree_std::_Tmap_traits__GUID_wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy___Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::AddConfiguration_::_2_::GUIDLessComparer_std::allocator_std::pair__GUID_const__wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy______0___::_Alloc_sentinel_and_proxy(&v36);
    v9 = 0;
    v28 = v32;
    v33 = v32;
    v34 = 0;
    v35 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Management::MdmAlert *>,wil::err_exception_policy>::end(
      &v28,
      v40);
    for ( i = v34; i != v41; i = ++v34 )
    {
      v11 = v33;
      v12 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD, struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo **))(*(_QWORD *)v33 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
      v13 = v12(v11, v34, &v35);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v13,
          v26);
      v28 = 0;
      v14 = *(_QWORD *)v35;
      v28 = 0;
      v15 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, struct Windows::Internal::AssignedAccess::IAssignedAccessProfile **))(v14 + 64))(
              v35,
              &v28);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE2,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
          (const char *)(unsigned int)v15,
          v26);
      v46 = 0;
      v16 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, IID *))(*(_QWORD *)v28 + 56LL))(
              v28,
              &v46);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE4,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
          (const char *)(unsigned int)v16,
          v26);
      std::_Tree_std::_Tmap_traits__GUID_wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy___Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::AddConfiguration_::_2_::GUIDLessComparer_std::allocator_std::pair__GUID_const__wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy______0___::_Find_lower_bound__GUID_(
        &v36,
        &v37,
        &v46);
      v18 = std::_Tree_std::_Tmap_traits__GUID_wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy___Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::AddConfiguration_::_2_::GUIDLessComparer_std::allocator_std::pair__GUID_const__wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy______0___::_Lower_bound_duplicate__GUID_(
              v17,
              v38,
              &v46);
      v19 = (Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *)v36;
      if ( v18 )
        v19 = v38;
      if ( v19 == (Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *)v36 )
      {
        Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeProfile(
          v19,
          (struct Windows::Internal::AssignedAccess::RegistryKeyBroker *)v44,
          v28);
        v20 = (_QWORD *)std::map__GUID_wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy___Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::AddConfiguration_::_2_::GUIDLessComparer_std::allocator_std::pair__GUID_const__wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy_______::_Try_emplace__GUID_const___(
                          &v36,
                          v45,
                          &v46);
        wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::operator=(
          *v20 + 48LL,
          v28);
      }
      LODWORD(v31) = 0;
      v21 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl **))(*(_QWORD *)v35 + 88LL))(
              v35,
              &v31);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
          (const char *)(unsigned int)v21,
          v26);
      v22 = (unsigned int)v31;
      if ( !(_DWORD)v31 || (v22 = (unsigned int)((_DWORD)v31 - 1), (_DWORD)v31 == 1) )
      {
        Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeUserInfo(
          (Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *)v22,
          (struct Windows::Internal::AssignedAccess::RegistryKeyBroker *)v39,
          v35);
      }
      else
      {
        v23 = (unsigned int)((_DWORD)v31 - 100);
        if ( (_DWORD)v31 == 100
          || (v23 = (unsigned int)((_DWORD)v31 - 101), (_DWORD)v31 == 101)
          || (v23 = (unsigned int)((_DWORD)v31 - 102), (_DWORD)v31 == 102)
          || (v23 = (unsigned int)((_DWORD)v31 - 200), (_DWORD)v31 == 200) )
        {
          Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGroupInfo(
            (Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl *)v23,
            (struct Windows::Internal::AssignedAccess::RegistryKeyBroker *)v43,
            v9++,
            v35);
        }
        else
        {
          if ( (_DWORD)v31 != 300 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x109,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
              (const char *)0x8000FFFFLL,
              v26);
          v29 = 0;
          v24 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, int *))(*(_QWORD *)v35 + 72LL))(
                  v35,
                  &v29);
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x100,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
              (const char *)(unsigned int)v24,
              v26);
          v27[0] = 0;
          v25 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, char *))(*(_QWORD *)v28 + 216LL))(
                  v28,
                  v27);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x103,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1impl.cpp",
              (const char *)(unsigned int)v25,
              v26);
          v37 = v46;
          Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGlobalProfile(
            (__int64)retaddr,
            (__int64)v39,
            v29,
            &v37,
            v27[0] != 0);
        }
      }
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v28);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v42);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    std::_Tree_std::_Tmap_traits__GUID_wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy___Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::AddConfiguration_::_2_::GUIDLessComparer_std::allocator_std::pair__GUID_const__wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy______0___::__Tree_std::_Tmap_traits__GUID_wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy___Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::AddConfiguration_::_2_::GUIDLessComparer_std::allocator_std::pair__GUID_const__wil::com_ptr_t_Windows::Internal::AssignedAccess::IAssignedAccessProfile_wil::err_exception_policy______0___(&v36);
    Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v43);
    Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v39);
    Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v44);
  }
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v32);
}

```

## disassembly

```asm
0x1800655ec  mov     [rsp-8+arg_10], rbx
0x1800655f1  mov     [rsp-8+arg_18], rsi
0x1800655f6  push    rbp
0x1800655f7  push    rdi
0x1800655f8  push    r14
0x1800655fa  lea     rbp, [rsp-30h]
0x1800655ff  sub     rsp, 130h
0x180065606  mov     rax, cs:__security_cookie
0x18006560d  xor     rax, rsp
0x180065610  mov     [rbp+40h+var_20], rax
0x180065614  mov     r8, rdx
0x180065617  mov     rbx, rcx
0x18006561a  xor     r14d, r14d
0x18006561d  mov     rax, [rdx]
0x180065620  mov     [rsp+140h+var_F0], r14
0x180065625  lea     rdx, [rsp+140h+var_F0]
0x18006562a  mov     rcx, r8
0x18006562d  mov     rax, [rax+50h]
0x180065631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065636  mov     rcx, [rbp+48h]; this
0x18006563a  test    eax, eax
0x18006563c  jns     short loc_180065653
0x18006563e  mov     r9d, eax; char *
0x180065641  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065648  mov     edx, 0C9h; void *
0x18006564d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065653  mov     [rsp+140h+var_FC], r14d
0x180065658  mov     rcx, [rsp+140h+var_F0]
0x18006565d  mov     rax, [rcx]
0x180065660  lea     rdx, [rsp+140h+var_FC]
0x180065665  mov     rax, [rax+38h]
0x180065669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006566e  mov     rcx, [rbp+48h]; this
0x180065672  test    eax, eax
0x180065674  jns     short loc_18006568B
0x180065676  mov     r9d, eax; char *
0x180065679  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065680  mov     edx, 0CBh; void *
0x180065685  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006568b  cmp     [rsp+140h+var_FC], r14d
0x180065690  jz      loc_1800659F5
0x180065696  lea     r9, [rbx+30h]
0x18006569a  lea     rdx, [rbp+40h+var_58]
0x18006569e  mov     rcx, [rbx+8]
0x1800656a2  call    ?Create@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(HKEY__ *,std::wstring const &,ulong,ulong)
0x1800656a7  nop
0x1800656a8  lea     r9, [rbx+50h]
0x1800656ac  lea     rdx, [rbp+40h+var_A0]
0x1800656b0  mov     rcx, [rbx+8]
0x1800656b4  call    ?Create@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(HKEY__ *,std::wstring const &,ulong,ulong)
0x1800656b9  nop
0x1800656ba  lea     r9, [rbx+70h]
0x1800656be  lea     rdx, [rbp+40h+var_70]
0x1800656c2  mov     rcx, [rbx+8]
0x1800656c6  call    ?Create@RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA?AV1234@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK@Z; Windows::Internal::AssignedAccess::RegistryKeyBroker::Create(HKEY__ *,std::wstring const &,ulong,ulong)
0x1800656cb  nop
0x1800656cc  xorps   xmm0, xmm0
0x1800656cf  movdqu  [rsp+140h+var_D0], xmm0
0x1800656d5  lea     rcx, [rsp+140h+var_D0]
0x1800656da  call    std___Tree_std___Tmap_traits__GUID_wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy___Windows__Internal__AssignedAccess__RegistryDataStoreV1Impl__AddConfiguration____2___GUIDLessComparer_std__allocator_std__pair__GUID_const__wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy______0______Alloc_sentinel_and_proxy
0x1800656df  nop
0x1800656e0  mov     esi, r14d
0x1800656e3  mov     rax, [rsp+140h+var_F0]
0x1800656e8  mov     [rsp+140h+var_108], rax
0x1800656ed  mov     [rsp+140h+var_E8], rax
0x1800656f2  mov     [rsp+140h+var_E0], r14d
0x1800656f7  mov     [rsp+140h+var_D8], r14
0x1800656fc  lea     rdx, [rbp+40h+var_88]
0x180065700  lea     rcx, [rsp+140h+var_108]
0x180065705  call    ?end@?$vector_range@U?$IVectorView@PEAVMdmAlert@Management@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Management::MdmAlert *>,wil::err_exception_policy>::end(void)
0x18006570a  nop
0x18006570b  mov     eax, [rsp+140h+var_E0]
0x18006570f  cmp     eax, [rbp+40h+var_80]
0x180065712  jz      loc_1800659B7
0x180065718  mov     rdi, [rsp+140h+var_E8]
0x18006571d  mov     rax, [rdi]
0x180065720  mov     rbx, [rax+30h]
0x180065724  lea     rcx, [rsp+140h+var_D8]
0x180065729  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18006572e  lea     r8, [rsp+140h+var_D8]
0x180065733  mov     edx, [rsp+140h+var_E0]
0x180065737  mov     rcx, rdi
0x18006573a  mov     rax, rbx
0x18006573d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065742  mov     rcx, [rbp+48h]; this
0x180065746  test    eax, eax
0x180065748  js      loc_1800659A2
0x18006574e  mov     [rsp+140h+var_108], r14
0x180065753  mov     rcx, [rsp+140h+var_D8]
0x180065758  mov     rax, [rcx]
0x18006575b  mov     [rsp+140h+var_108], r14
0x180065760  lea     rdx, [rsp+140h+var_108]
0x180065765  mov     rax, [rax+40h]
0x180065769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006576e  mov     rcx, [rbp+48h]; this
0x180065772  test    eax, eax
0x180065774  js      loc_18006598D
0x18006577a  xorps   xmm0, xmm0
0x18006577d  movups  [rbp+40h+var_30], xmm0
0x180065781  mov     rcx, [rsp+140h+var_108]
0x180065786  mov     rax, [rcx]
0x180065789  lea     rdx, [rbp+40h+var_30]
0x18006578d  mov     rax, [rax+38h]
0x180065791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065796  mov     rcx, [rbp+48h]; this
0x18006579a  test    eax, eax
0x18006579c  js      loc_180065978
0x1800657a2  lea     r8, [rbp+40h+var_30]
0x1800657a6  lea     rdx, [rbp+40h+var_C0]
0x1800657aa  lea     rcx, [rsp+140h+var_D0]
0x1800657af  call    std___Tree_std___Tmap_traits__GUID_wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy___Windows__Internal__AssignedAccess__RegistryDataStoreV1Impl__AddConfiguration____2___GUIDLessComparer_std__allocator_std__pair__GUID_const__wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy______0______Find_lower_bound__GUID_
0x1800657b4  lea     r8, [rbp+40h+var_30]
0x1800657b8  mov     rdx, [rbp+40h+var_B0]
0x1800657bc  call    std___Tree_std___Tmap_traits__GUID_wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy___Windows__Internal__AssignedAccess__RegistryDataStoreV1Impl__AddConfiguration____2___GUIDLessComparer_std__allocator_std__pair__GUID_const__wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy______0______Lower_bound_duplicate__GUID_
0x1800657c1  mov     rcx, qword ptr [rsp+140h+var_D0]
0x1800657c6  test    al, al
0x1800657c8  cmovnz  rcx, [rbp+40h+var_B0]; this
0x1800657cd  cmp     rcx, qword ptr [rsp+140h+var_D0]
0x1800657d2  jnz     short loc_180065805
0x1800657d4  mov     r8, [rsp+140h+var_108]; struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *
0x1800657d9  lea     rdx, [rbp+40h+var_58]; struct Windows::Internal::AssignedAccess::RegistryKeyBroker *
0x1800657dd  call    ?SerializeProfile@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAVRegistryKeyBroker@234@PEAUIAssignedAccessProfile@234@@Z; Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeProfile(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessProfile *)
0x1800657e2  lea     r8, [rbp+40h+var_30]
0x1800657e6  lea     rdx, [rbp+40h+var_40]
0x1800657ea  lea     rcx, [rsp+140h+var_D0]
0x1800657ef  call    std__map__GUID_wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy___Windows__Internal__AssignedAccess__RegistryDataStoreV1Impl__AddConfiguration____2___GUIDLessComparer_std__allocator_std__pair__GUID_const__wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy__________Try_emplace__GUID_const___
0x1800657f4  mov     rcx, [rax]
0x1800657f7  add     rcx, 30h ; '0'
0x1800657fb  mov     rdx, [rsp+140h+var_108]
0x180065800  call    ??4?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::operator=(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)
0x180065805  mov     dword ptr [rsp+140h+var_F8], r14d
0x18006580a  mov     rcx, [rsp+140h+var_D8]
0x18006580f  mov     rax, [rcx]
0x180065812  lea     rdx, [rsp+140h+var_F8]
0x180065817  mov     rax, [rax+58h]
0x18006581b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065820  mov     rcx, [rbp+48h]; this
0x180065824  test    eax, eax
0x180065826  js      loc_180065963
0x18006582c  mov     ecx, dword ptr [rsp+140h+var_F8]; this
0x180065830  test    ecx, ecx
0x180065832  jz      loc_1800658F5
0x180065838  sub     ecx, 1
0x18006583b  jz      loc_1800658F5
0x180065841  sub     ecx, 63h ; 'c'; this
0x180065844  jz      loc_1800658E0
0x18006584a  sub     ecx, 1
0x18006584d  jz      loc_1800658E0
0x180065853  sub     ecx, 1
0x180065856  jz      loc_1800658E0
0x18006585c  sub     ecx, 62h ; 'b'
0x18006585f  jz      short loc_1800658E0
0x180065861  cmp     ecx, 64h ; 'd'
0x180065864  jnz     loc_180065947
0x18006586a  mov     [rsp+140h+var_100], r14d
0x18006586f  mov     rcx, [rsp+140h+var_D8]
0x180065874  mov     rax, [rcx]
0x180065877  lea     rdx, [rsp+140h+var_100]
0x18006587c  mov     rax, [rax+48h]
0x180065880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065885  mov     rcx, [rbp+48h]; this
0x180065889  test    eax, eax
0x18006588b  js      loc_180065932
0x180065891  mov     [rsp+140h+var_110], r14b
0x180065896  mov     rcx, [rsp+140h+var_108]
0x18006589b  mov     rax, [rcx]
0x18006589e  lea     rdx, [rsp+140h+var_110]
0x1800658a3  mov     rax, [rax+0D8h]
0x1800658aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800658af  mov     rcx, [rbp+48h]; this
0x1800658b3  test    eax, eax
0x1800658b5  js      short loc_18006591D
0x1800658b7  cmp     [rsp+140h+var_110], r14b
0x1800658bc  setnz   al
0x1800658bf  movaps  xmm0, [rbp+40h+var_30]
0x1800658c3  movdqa  [rbp+40h+var_C0], xmm0
0x1800658c8  mov     byte ptr [rsp+140h+var_120], al
0x1800658cc  lea     r9, [rbp+40h+var_C0]
0x1800658d0  mov     r8d, [rsp+140h+var_100]
0x1800658d5  lea     rdx, [rbp+40h+var_A0]
0x1800658d9  call    ?SerializeGlobalProfile@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAVRegistryKeyBroker@234@W4ConfigSource@234@U_GUID@@_N@Z; Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGlobalProfile(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::ConfigSource,_GUID,bool)
0x1800658de  jmp     short loc_180065904
0x1800658e0  mov     r9, [rsp+140h+var_D8]; struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *
0x1800658e5  mov     r8d, esi; unsigned int
0x1800658e8  lea     rdx, [rbp+40h+var_70]; struct Windows::Internal::AssignedAccess::RegistryKeyBroker *
0x1800658ec  call    ?SerializeGroupInfo@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAVRegistryKeyBroker@234@KPEAUIAssignedAccessUserInfo@234@@Z; Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeGroupInfo(Windows::Internal::AssignedAccess::RegistryKeyBroker &,ulong,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)
0x1800658f1  inc     esi
0x1800658f3  jmp     short loc_180065904
0x1800658f5  mov     r8, [rsp+140h+var_D8]; struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *
0x1800658fa  lea     rdx, [rbp+40h+var_A0]; struct Windows::Internal::AssignedAccess::RegistryKeyBroker *
0x1800658fe  call    ?SerializeUserInfo@RegistryDataStoreV1Impl@AssignedAccess@Internal@Windows@@AEAAXAEAVRegistryKeyBroker@234@PEAUIAssignedAccessUserInfo@234@@Z; Windows::Internal::AssignedAccess::RegistryDataStoreV1Impl::SerializeUserInfo(Windows::Internal::AssignedAccess::RegistryKeyBroker &,Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)
0x180065903  nop
0x180065904  lea     rcx, [rsp+140h+var_108]
0x180065909  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18006590e  mov     eax, [rsp+140h+var_E0]
0x180065912  inc     eax
0x180065914  mov     [rsp+140h+var_E0], eax
0x180065918  jmp     loc_18006570F
0x18006591d  mov     r9d, eax; char *
0x180065920  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065927  mov     edx, 103h; void *
0x18006592c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065932  mov     r9d, eax; char *
0x180065935  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006593c  mov     edx, 100h; void *
0x180065941  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065947  mov     rcx, [rbp+48h]; this
0x18006594b  mov     r9d, 8000FFFFh; char *
0x180065951  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065958  mov     edx, 109h; void *
0x18006595d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065963  mov     r9d, eax; char *
0x180065966  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006596d  mov     edx, 0ECh; void *
0x180065972  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065978  mov     r9d, eax; char *
0x18006597b  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065982  mov     edx, 0E4h; void *
0x180065987  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006598d  mov     r9d, eax; char *
0x180065990  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180065997  mov     edx, 0E2h; void *
0x18006599c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800659a2  mov     r9d, eax; char *
0x1800659a5  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800659ac  mov     edx, 1CBEh; void *
0x1800659b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800659b7  lea     rcx, [rbp+40h+var_78]
0x1800659bb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800659c0  nop
0x1800659c1  lea     rcx, [rsp+140h+var_D8]
0x1800659c6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800659cb  nop
0x1800659cc  lea     rcx, [rsp+140h+var_D0]
0x1800659d1  call    std___Tree_std___Tmap_traits__GUID_wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy___Windows__Internal__AssignedAccess__RegistryDataStoreV1Impl__AddConfiguration____2___GUIDLessComparer_std__allocator_std__pair__GUID_const__wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy______0_______Tree_std___Tmap_traits__GUID_wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy___Windows__Internal__AssignedAccess__RegistryDataStoreV1Impl__AddConfiguration____2___GUIDLessComparer_std__allocator_std__pair__GUID_const__wil__com_ptr_t_Windows__Internal__AssignedAccess__IAssignedAccessProfile_wil__err_exception_policy______0___
0x1800659d6  nop
0x1800659d7  lea     rcx, [rbp+40h+var_70]; this
0x1800659db  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x1800659e0  nop
0x1800659e1  lea     rcx, [rbp+40h+var_A0]; this
0x1800659e5  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x1800659ea  nop
0x1800659eb  lea     rcx, [rbp+40h+var_58]; this
0x1800659ef  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x1800659f4  nop
0x1800659f5  lea     rcx, [rsp+140h+var_F0]
0x1800659fa  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x1800659ff  mov     rcx, [rbp+40h+var_20]
0x180065a03  xor     rcx, rsp; StackCookie
0x180065a06  call    __security_check_cookie
0x180065a0b  lea     r11, [rsp+140h+var_10]
0x180065a13  mov     rbx, [r11+30h]
0x180065a17  mov     rsi, [r11+38h]
0x180065a1b  mov     rsp, r11
0x180065a1e  pop     r14
0x180065a20  pop     rdi
0x180065a21  pop     rbp
0x180065a22  retn
```
