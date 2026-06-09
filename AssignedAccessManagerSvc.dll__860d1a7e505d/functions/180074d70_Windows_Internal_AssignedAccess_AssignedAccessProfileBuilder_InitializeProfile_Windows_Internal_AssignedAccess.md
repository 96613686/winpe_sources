# Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder::InitializeProfile(Windows::Internal::AssignedAccess::IAssignedAccessProfile *)

- ea: `0x180074d70`
- end: `0x1800750c4`
- name: `?InitializeProfile@AssignedAccessProfileBuilder@AssignedAccess@Internal@Windows@@AEBAXPEAUIAssignedAccessProfile@234@@Z`
- size: `852`
- prototype: `void __fastcall(Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder *__hidden this, struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074b2c`

## callees

- `0x180006640`
- `0x18000cfe4`
- `0x1800116bc`
- `0x18002001c`
- `0x180020050`
- `0x1800746b4`
- `0x180074714`
- `0x180074c98`
- `0x180074d70`
- `0x180096010`

## string_xrefs

- `0x180074dc0`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180074e11`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180074e43`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180074e75`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180074ebb`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180074f0a`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180074f49`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180074f9d`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180074ff5`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x18007502d`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180075062`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`
- `0x180075091`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\assignedaccessprofilebuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder::InitializeProfile(
        Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder *this,
        struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *a2)
{
  int v4; // eax
  __int64 (__fastcall *v5)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD); // rbx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 (__fastcall *v12)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD); // rbx
  _QWORD *v13; // rax
  int v14; // eax
  __int64 (__fastcall *v15)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD); // rbx
  _QWORD *v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 (__fastcall *v19)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD); // rbx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  __int64 (__fastcall *v23)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD); // rbx
  __int64 v24; // rax
  int v25; // eax
  char v26; // bl
  char v27; // r14
  int v28; // eax
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  __int128 v32; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v33[32]; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v32 = *((_OWORD *)this + 4);
  v4 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, __int128 *))(*(_QWORD *)a2 + 64LL))(
         a2,
         &v32);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v4,
      v32);
  v5 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD))(*(_QWORD *)a2 + 144LL);
  *(_QWORD *)&v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 88);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v33, &v32);
  v7 = v5(a2, *(_QWORD *)(v6 + 24));
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v7,
      v32);
  LOBYTE(v8) = *((_BYTE *)this + 81);
  v9 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, __int64))(*(_QWORD *)a2 + 160LL))(
         a2,
         v8);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v9,
      v32);
  LOBYTE(v10) = *((_BYTE *)this + 82);
  v11 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, __int64))(*(_QWORD *)a2 + 176LL))(
          a2,
          v10);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v11,
      v32);
  v12 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD))(*(_QWORD *)a2 + 128LL);
  v13 = (_QWORD *)Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder::GetVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>(
                    &v32,
                    *((_QWORD *)this + 23));
  v14 = v12(a2, *v13);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v14,
      v32);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v32);
  v15 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD))(*(_QWORD *)a2 + 192LL);
  v16 = (_QWORD *)Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder::GetVectorView<enum Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>(
                    &v32,
                    *((_QWORD *)this + 24));
  v17 = v15(a2, *v16);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v17,
      v32);
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v32);
  v18 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD))(*(_QWORD *)a2 + 208LL))(
          a2,
          *((_QWORD *)this + 25));
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v18,
      v32);
  v19 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD))(*(_QWORD *)a2 + 256LL);
  *(_QWORD *)&v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 152);
  v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v33, &v32);
  v21 = v19(a2, *(_QWORD *)(v20 + 24));
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v21,
      v32);
  if ( *((_QWORD *)this + 17) )
  {
    v23 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, _QWORD))(*(_QWORD *)a2 + 240LL);
    *(_QWORD *)&v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 120);
    v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v33, &v32);
    v25 = v23(a2, *(_QWORD *)(v24 + 24));
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
        (const char *)(unsigned int)v25,
        v32);
  }
  v26 = 0;
  v27 = 0;
  if ( *((_BYTE *)this + 80) )
  {
    v28 = Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder::ExtractProfileFirstAppType(a2) - 1;
    if ( v28 )
    {
      if ( v28 != 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
          (const char *)0x80070057LL,
          v32);
      v27 = 1;
    }
    else
    {
      v26 = 1;
    }
  }
  LOBYTE(v22) = v26;
  v29 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, __int64))(*(_QWORD *)a2 + 80LL))(
          a2,
          v22);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v29,
      v32);
  LOBYTE(v30) = v27;
  v31 = (*(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessProfile *, __int64))(*(_QWORD *)a2 + 96LL))(
          a2,
          v30);
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\assignedaccessprofilebuilder.cpp",
      (const char *)(unsigned int)v31,
      v32);
}

```

## disassembly

```asm
0x180074d70  mov     [rsp-18h+arg_10], rbx
0x180074d75  mov     [rsp-18h+arg_18], rsi
0x180074d7a  push    rbp
0x180074d7b  push    rdi
0x180074d7c  push    r14
0x180074d7e  mov     rbp, rsp
0x180074d81  sub     rsp, 60h
0x180074d85  mov     rax, cs:__security_cookie
0x180074d8c  xor     rax, rsp
0x180074d8f  mov     [rbp+var_10], rax
0x180074d93  mov     rdi, rdx
0x180074d96  mov     rsi, rcx
0x180074d99  movups  xmm0, xmmword ptr [rcx+40h]
0x180074d9d  movdqu  [rbp+var_40], xmm0
0x180074da2  mov     rax, [rdx]
0x180074da5  lea     rdx, [rbp+var_40]
0x180074da9  mov     rcx, rdi
0x180074dac  mov     rax, [rax+40h]
0x180074db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074db5  mov     rcx, [rbp+18h]; this
0x180074db9  test    eax, eax
0x180074dbb  jns     short loc_180074DD2
0x180074dbd  mov     r9d, eax; char *
0x180074dc0  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074dc7  mov     edx, 87h; void *
0x180074dcc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074dd2  mov     rax, [rdi]
0x180074dd5  mov     rbx, [rax+90h]
0x180074ddc  lea     rcx, [rsi+58h]
0x180074de0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074de5  mov     qword ptr [rbp+var_40], rax
0x180074de9  lea     rdx, [rbp+var_40]
0x180074ded  lea     rcx, [rbp+var_30]
0x180074df1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180074df6  nop
0x180074df7  mov     rdx, [rax+18h]
0x180074dfb  mov     rcx, rdi
0x180074dfe  mov     rax, rbx
0x180074e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e06  mov     rcx, [rbp+18h]; this
0x180074e0a  test    eax, eax
0x180074e0c  jns     short loc_180074E23
0x180074e0e  mov     r9d, eax; char *
0x180074e11  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074e18  mov     edx, 88h; void *
0x180074e1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074e23  mov     rax, [rdi]
0x180074e26  mov     dl, [rsi+51h]
0x180074e29  mov     rcx, rdi
0x180074e2c  mov     rax, [rax+0A0h]
0x180074e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e38  mov     rcx, [rbp+18h]; this
0x180074e3c  test    eax, eax
0x180074e3e  jns     short loc_180074E55
0x180074e40  mov     r9d, eax; char *
0x180074e43  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074e4a  mov     edx, 89h; void *
0x180074e4f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074e55  mov     rax, [rdi]
0x180074e58  mov     dl, [rsi+52h]
0x180074e5b  mov     rcx, rdi
0x180074e5e  mov     rax, [rax+0B0h]
0x180074e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e6a  mov     rcx, [rbp+18h]; this
0x180074e6e  test    eax, eax
0x180074e70  jns     short loc_180074E87
0x180074e72  mov     r9d, eax; char *
0x180074e75  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074e7c  mov     edx, 8Ah; void *
0x180074e81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074e87  mov     rax, [rdi]
0x180074e8a  mov     rbx, [rax+80h]
0x180074e91  mov     rdx, [rsi+0B8h]
0x180074e98  lea     rcx, [rbp+var_40]
0x180074e9c  call    ??$GetVectorView@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@AssignedAccessProfileBuilder@AssignedAccess@Internal@Windows@@CA?AV?$com_ptr_t@U?$IVectorView@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@PEAV?$AgileObservableVector@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@3674@@2Collections@Foundation@3@@Z; Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder::GetVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>(Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessApplication *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessApplication *>> *)
0x180074ea1  nop
0x180074ea2  mov     rdx, [rax]
0x180074ea5  mov     rcx, rdi
0x180074ea8  mov     rax, rbx
0x180074eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074eb0  test    eax, eax
0x180074eb2  jns     short loc_180074ECD
0x180074eb4  mov     rcx, [rbp+18h]; this
0x180074eb8  mov     r9d, eax; char *
0x180074ebb  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074ec2  mov     edx, 8Bh; void *
0x180074ec7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074ecd  lea     rcx, [rbp+var_40]
0x180074ed1  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180074ed6  mov     rax, [rdi]
0x180074ed9  mov     rbx, [rax+0C0h]
0x180074ee0  mov     rdx, [rsi+0C0h]
0x180074ee7  lea     rcx, [rbp+var_40]
0x180074eeb  call    ??$GetVectorView@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@AssignedAccessProfileBuilder@AssignedAccess@Internal@Windows@@CA?AV?$com_ptr_t@U?$IVectorView@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@PEAV?$AgileObservableVector@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@U?$DefaultEqualityPredicate@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@W4AssignedAccessCommonFileDialogLocation@AssignedAccess@Internal@Windows@@@3674@@2Collections@Foundation@3@@Z; Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder::GetVectorView<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>(Windows::Foundation::Collections::Internal::AgileObservableVector<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::AssignedAccess::AssignedAccessCommonFileDialogLocation>> *)
0x180074ef0  nop
0x180074ef1  mov     rdx, [rax]
0x180074ef4  mov     rcx, rdi
0x180074ef7  mov     rax, rbx
0x180074efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074eff  test    eax, eax
0x180074f01  jns     short loc_180074F1C
0x180074f03  mov     rcx, [rbp+18h]; this
0x180074f07  mov     r9d, eax; char *
0x180074f0a  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074f11  mov     edx, 8Ch; void *
0x180074f16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074f1c  lea     rcx, [rbp+var_40]
0x180074f20  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180074f25  mov     rax, [rdi]
0x180074f28  mov     rdx, [rsi+0C8h]
0x180074f2f  mov     rcx, rdi
0x180074f32  mov     rax, [rax+0D0h]
0x180074f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f3e  mov     rcx, [rbp+18h]; this
0x180074f42  test    eax, eax
0x180074f44  jns     short loc_180074F5B
0x180074f46  mov     r9d, eax; char *
0x180074f49  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074f50  mov     edx, 8Dh; void *
0x180074f55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074f5b  mov     rax, [rdi]
0x180074f5e  mov     rbx, [rax+100h]
0x180074f65  lea     rcx, [rsi+98h]
0x180074f6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074f71  mov     qword ptr [rbp+var_40], rax
0x180074f75  lea     rdx, [rbp+var_40]
0x180074f79  lea     rcx, [rbp+var_30]
0x180074f7d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180074f82  nop
0x180074f83  mov     rdx, [rax+18h]
0x180074f87  mov     rcx, rdi
0x180074f8a  mov     rax, rbx
0x180074f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f92  mov     rcx, [rbp+18h]; this
0x180074f96  test    eax, eax
0x180074f98  jns     short loc_180074FAF
0x180074f9a  mov     r9d, eax; char *
0x180074f9d  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074fa4  mov     edx, 8Eh; void *
0x180074fa9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074faf  lea     rcx, [rsi+78h]
0x180074fb3  cmp     qword ptr [rcx+10h], 0
0x180074fb8  jz      short loc_180075007
0x180074fba  mov     rax, [rdi]
0x180074fbd  mov     rbx, [rax+0F0h]
0x180074fc4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180074fc9  mov     qword ptr [rbp+var_40], rax
0x180074fcd  lea     rdx, [rbp+var_40]
0x180074fd1  lea     rcx, [rbp+var_30]
0x180074fd5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180074fda  nop
0x180074fdb  mov     rdx, [rax+18h]
0x180074fdf  mov     rcx, rdi
0x180074fe2  mov     rax, rbx
0x180074fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074fea  mov     rcx, [rbp+18h]; this
0x180074fee  test    eax, eax
0x180074ff0  jns     short loc_180075007
0x180074ff2  mov     r9d, eax; char *
0x180074ff5  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180074ffc  mov     edx, 92h; void *
0x180075001  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075007  xor     bl, bl
0x180075009  xor     r14b, r14b
0x18007500c  cmp     [rsi+50h], bl
0x18007500f  jz      short loc_180075046
0x180075011  mov     rcx, rdi
0x180075014  call    ?ExtractProfileFirstAppType@AssignedAccessProfileBuilder@AssignedAccess@Internal@Windows@@CA?AW4AppType@234@PEAUIAssignedAccessProfile@234@@Z; Windows::Internal::AssignedAccess::AssignedAccessProfileBuilder::ExtractProfileFirstAppType(Windows::Internal::AssignedAccess::IAssignedAccessProfile *)
0x180075019  sub     eax, 1
0x18007501c  jz      short loc_180075044
0x18007501e  cmp     eax, 2
0x180075021  jz      short loc_18007503F
0x180075023  mov     rcx, [rbp+18h]; this
0x180075027  mov     r9d, 80070057h; char *
0x18007502d  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180075034  mov     edx, 0A2h; void *
0x180075039  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007503f  mov     r14b, 1
0x180075042  jmp     short loc_180075046
0x180075044  mov     bl, 1
0x180075046  mov     rax, [rdi]
0x180075049  mov     dl, bl
0x18007504b  mov     rcx, rdi
0x18007504e  mov     rax, [rax+50h]
0x180075052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075057  test    eax, eax
0x180075059  jns     short loc_180075074
0x18007505b  mov     rcx, [rbp+18h]; this
0x18007505f  mov     r9d, eax; char *
0x180075062  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180075069  mov     edx, 0A5h; void *
0x18007506e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180075074  mov     rax, [rdi]
0x180075077  mov     dl, r14b
0x18007507a  mov     rcx, rdi
0x18007507d  mov     rax, [rax+60h]
0x180075081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075086  test    eax, eax
0x180075088  jns     short loc_1800750A3
0x18007508a  mov     rcx, [rbp+18h]; this
0x18007508e  mov     r9d, eax; char *
0x180075091  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180075098  mov     edx, 0A6h; void *
0x18007509d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800750a3  mov     rcx, [rbp+var_10]
0x1800750a7  xor     rcx, rsp; StackCookie
0x1800750aa  call    __security_check_cookie
0x1800750af  lea     r11, [rsp+60h+var_s0]
0x1800750b4  mov     rbx, [r11+30h]
0x1800750b8  mov     rsi, [r11+38h]
0x1800750bc  mov     rsp, r11
0x1800750bf  pop     r14
0x1800750c1  pop     rdi
0x1800750c2  pop     rbp
0x1800750c3  retn
```
