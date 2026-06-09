# UiaManagerEndpointStateNotifier::Advise(IUiaManagerEndpointStateNotifierSink *,IUiaManagerLifetimeNotifier *,IUiaManagerEndpointStateNotifierSinkRegistrationToken * *)

- ea: `0x180007e10`
- end: `0x18000802c`
- name: `?Advise@UiaManagerEndpointStateNotifier@@UEAAJPEAUIUiaManagerEndpointStateNotifierSink@@PEAUIUiaManagerLifetimeNotifier@@PEAPEAUIUiaManagerEndpointStateNotifierSinkRegistrationToken@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(UiaManagerEndpointStateNotifier *__hidden this, struct IUiaManagerEndpointStateNotifierSink *, struct IUiaManagerLifetimeNotifier *, struct IUiaManagerEndpointStateNotifierSinkRegistrationToken **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800054f8`
- `0x180007e10`
- `0x180008034`
- `0x1800081ac`
- `0x180008318`
- `0x180008370`
- `0x180018868`
- `0x180031540`
- `0x180091010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180007ee2`
- `msvcp_win!_Mtx_unlock` at `0x180007ee2`

## string_xrefs

- `0x180007e3d`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerendpointstatenotifier.cpp`
- `0x180007f5c`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerendpointstatenotifier.cpp`
- `0x180007fac`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerendpointstatenotifier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall UiaManagerEndpointStateNotifier::Advise(
        UiaManagerEndpointStateNotifier *this,
        struct IUiaManagerEndpointStateNotifierSink *a2,
        struct IUiaManagerLifetimeNotifier *a3,
        struct IUiaManagerEndpointStateNotifierSinkRegistrationToken **a4)
{
  __int64 **v7; // rcx
  __int64 *i; // rax
  int v9; // esi
  int v10; // eax
  int v11; // eax
  const char *v12; // r9
  __int64 v13; // rcx
  struct IUiaManagerEndpointStateNotifierSink *v14; // rcx
  __int64 result; // rax
  int v16[2]; // [rsp+20h] [rbp-48h] BYREF
  struct IUiaManagerEndpointStateNotifierSink *v17; // [rsp+28h] [rbp-40h] BYREF
  struct IUiaManagerLifetimeNotifier *v18; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v19[6]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char *v21; // [rsp+78h] [rbp+10h] BYREF
  char *v22; // [rsp+88h] [rbp+20h] BYREF

  try
  {
    *a4 = 0;
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifier.cpp",
        (const char *)0x80070057LL,
        v16[0]);
    v17 = a2;
    (*(void (__fastcall **)(struct IUiaManagerEndpointStateNotifierSink *))(*(_QWORD *)a2 + 8LL))(a2);
    v18 = a3;
    if ( a3 )
      (*(void (__fastcall **)(struct IUiaManagerLifetimeNotifier *))(*(_QWORD *)a3 + 8LL))(a3);
    LODWORD(v21) = _InterlockedIncrement((volatile signed __int32 *)this + 10);
    v22 = (char *)this + 48;
    std::_Mutex_base::lock((UiaManagerEndpointStateNotifier *)((char *)this + 48));
    v7 = (__int64 **)*((_QWORD *)this + 17);
    for ( i = *v7; i != (__int64 *)v7; i = (__int64 *)*i )
    {
      if ( (struct IUiaManagerEndpointStateNotifierSink *)i[3] == v17 )
      {
        v9 = *((_DWORD *)i + 4);
        goto LABEL_12;
      }
    }
    std::_Hash<std::_Umap_traits<unsigned long,Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink>>>,0>>::emplace<unsigned long const &,Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink> const &>(
      (char *)this + 128,
      v19,
      &v21,
      &v17);
    v9 = (int)v21;
LABEL_12:
    _Mtx_unlock((UiaManagerEndpointStateNotifier *)((char *)this + 48));
    LODWORD(v22) = v9;
    ThreadSafeMap<unsigned long,Microsoft::WRL::ComPtr<IUiaManagerLifetimeNotifier>>::Emplace<unsigned long const &,Microsoft::WRL::ComPtr<IUiaManagerLifetimeNotifier> &>(
      (char *)this + 192,
      &v21,
      &v18);
    *(_QWORD *)v16 = 0;
    v21 = (char *)this - 32;
    v21 = *(char **)wil::com_query<IUiaManagerEndpointStateNotifierSinkRegistration,UiaManagerEndpointStateNotifier *>(
                      v19,
                      &v21);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
    v10 = Microsoft::WRL::Details::MakeAndInitialize<UiaManagerEndPointNotificationSinkRegistrationToken,UiaManagerEndPointNotificationSinkRegistrationToken,IUiaManagerEndpointStateNotifierSinkRegistration *,unsigned long &>(
            v16,
            &v21,
            &v22);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifier.cpp",
        (const char *)(unsigned int)v10,
        v16[0]);
    if ( v19[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
    v11 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IUiaManagerEndpointStateNotifierSinkRegistrationToken **))v16)(
            *(_QWORD *)v16,
            &GUID_fcbc010e_a314_43e9_b40a_49690a0c8b78,
            a4);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifier.cpp",
        (const char *)(unsigned int)v11,
        v16[0]);
    v13 = *(_QWORD *)v16;
    if ( *(_QWORD *)v16 )
    {
      *(_QWORD *)v16 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    if ( v18 )
      (*(void (__fastcall **)(struct IUiaManagerLifetimeNotifier *))(*(_QWORD *)v18 + 16LL))(v18);
    v14 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(struct IUiaManagerEndpointStateNotifierSink *))(*(_QWORD *)v14 + 16LL))(v14);
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v21) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x5F,
                     (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerendpointstatenotifier.cpp",
                     v12);
    return (unsigned int)v21;
  }
  return result;
}

```

## disassembly

```asm
0x180007e10  mov     [rsp+arg_0], rbx
0x180007e15  push    rsi
0x180007e16  push    rdi
0x180007e17  push    r14
0x180007e19  sub     rsp, 50h
0x180007e1d  mov     r14, r9
0x180007e20  mov     rbx, r8
0x180007e23  mov     rdi, rcx
0x180007e26  mov     qword ptr [r9], 0
0x180007e2d  mov     rcx, [rsp+68h]; this
0x180007e32  test    rdx, rdx
0x180007e35  jnz     short loc_180007E4E
0x180007e37  mov     r9d, 80070057h; char *
0x180007e3d  lea     r8, aOnecoreWindows_27; "onecore\\windows\\accessibletech\\uiama"...
0x180007e44  mov     edx, 49h ; 'I'; void *
0x180007e49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007e4e  mov     [rsp+68h+var_40], rdx
0x180007e53  mov     rax, [rdx]
0x180007e56  mov     rcx, rdx
0x180007e59  mov     rax, [rax+8]
0x180007e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e62  nop
0x180007e63  mov     [rsp+68h+var_38], rbx
0x180007e68  test    rbx, rbx
0x180007e6b  jz      short loc_180007E7D
0x180007e6d  mov     rax, [rbx]
0x180007e70  mov     rcx, rbx
0x180007e73  mov     rax, [rax+8]
0x180007e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e7c  nop
0x180007e7d  mov     eax, 1
0x180007e82  lock xadd [rdi+28h], eax
0x180007e87  inc     eax
0x180007e89  mov     dword ptr [rsp+68h+arg_8], eax
0x180007e8d  lea     rbx, [rdi+30h]
0x180007e91  mov     [rsp+68h+arg_18], rbx
0x180007e99  mov     rcx, rbx; this
0x180007e9c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180007ea1  nop
0x180007ea2  mov     rcx, [rbx+58h]
0x180007ea6  mov     rax, [rcx]
0x180007ea9  mov     rdx, [rsp+68h+var_40]
0x180007eae  cmp     rax, rcx
0x180007eb1  jz      short loc_180007EC3
0x180007eb3  cmp     [rax+18h], rdx
0x180007eb7  jz      short loc_180007EBE
0x180007eb9  mov     rax, [rax]
0x180007ebc  jmp     short loc_180007EAE
0x180007ebe  mov     esi, [rax+10h]
0x180007ec1  jmp     short loc_180007EDF
0x180007ec3  lea     r9, [rsp+68h+var_40]
0x180007ec8  lea     r8, [rsp+68h+arg_8]
0x180007ecd  lea     rdx, [rsp+68h+var_30]
0x180007ed2  lea     rcx, [rbx+50h]
0x180007ed6  call    ??$emplace@AEBKAEBV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@@?$_Hash@V?$_Umap_traits@KV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@AEBKAEBV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@@Z; std::_Hash<std::_Umap_traits<ulong,Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink>>>,0>>::emplace<ulong const &,Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink> const &>(ulong const &,Microsoft::WRL::ComPtr<IUiaManagerEndpointStateNotifierSink> const &)
0x180007edb  mov     esi, dword ptr [rsp+68h+arg_8]
0x180007edf  mov     rcx, rbx; _Mtx_t
0x180007ee2  call    cs:__imp__Mtx_unlock
0x180007ee8  mov     dword ptr [rsp+68h+arg_18], esi
0x180007eef  lea     rcx, [rdi+0C0h]
0x180007ef6  lea     r8, [rsp+68h+var_38]
0x180007efb  lea     rdx, [rsp+68h+arg_8]
0x180007f00  call    ??$Emplace@AEBKAEAV?$ComPtr@UIUiaManagerLifetimeNotifier@@@WRL@Microsoft@@@?$ThreadSafeMap@KV?$ComPtr@UIUiaManagerLifetimeNotifier@@@WRL@Microsoft@@@@QEAAXAEBKAEAV?$ComPtr@UIUiaManagerLifetimeNotifier@@@WRL@Microsoft@@@Z; ThreadSafeMap<ulong,Microsoft::WRL::ComPtr<IUiaManagerLifetimeNotifier>>::Emplace<ulong const &,Microsoft::WRL::ComPtr<IUiaManagerLifetimeNotifier> &>(ulong const &,Microsoft::WRL::ComPtr<IUiaManagerLifetimeNotifier> &)
0x180007f05  mov     qword ptr [rsp+68h+var_48], 0; int
0x180007f0e  lea     rax, [rdi-20h]
0x180007f12  mov     [rsp+68h+arg_8], rax
0x180007f17  lea     rdx, [rsp+68h+arg_8]
0x180007f1c  lea     rcx, [rsp+68h+var_30]
0x180007f21  call    ??$com_query@UIUiaManagerEndpointStateNotifierSinkRegistration@@PEAVUiaManagerEndpointStateNotifier@@@wil@@YA?AV?$com_ptr_t@UIUiaManagerEndpointStateNotifierSinkRegistration@@Uerr_exception_policy@wil@@@0@$$QEAPEAVUiaManagerEndpointStateNotifier@@@Z; wil::com_query<IUiaManagerEndpointStateNotifierSinkRegistration,UiaManagerEndpointStateNotifier *>(UiaManagerEndpointStateNotifier * &&)
0x180007f26  nop
0x180007f27  mov     rax, [rax]
0x180007f2a  mov     [rsp+68h+arg_8], rax
0x180007f2f  lea     rcx, [rsp+68h+var_48]
0x180007f34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007f39  lea     r8, [rsp+68h+arg_18]
0x180007f41  lea     rdx, [rsp+68h+arg_8]
0x180007f46  lea     rcx, [rsp+68h+var_48]
0x180007f4b  call    ??$MakeAndInitialize@VUiaManagerEndPointNotificationSinkRegistrationToken@@V1@PEAUIUiaManagerEndpointStateNotifierSinkRegistration@@AEAK@Details@WRL@Microsoft@@YAJPEAPEAVUiaManagerEndPointNotificationSinkRegistrationToken@@$$QEAPEAUIUiaManagerEndpointStateNotifierSinkRegistration@@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<UiaManagerEndPointNotificationSinkRegistrationToken,UiaManagerEndPointNotificationSinkRegistrationToken,IUiaManagerEndpointStateNotifierSinkRegistration *,ulong &>(UiaManagerEndPointNotificationSinkRegistrationToken * *,IUiaManagerEndpointStateNotifierSinkRegistration * &&,ulong &)
0x180007f50  mov     rcx, [rsp+68h]; this
0x180007f55  test    eax, eax
0x180007f57  jns     short loc_180007F6E
0x180007f59  mov     r9d, eax; char *
0x180007f5c  lea     r8, aOnecoreWindows_27; "onecore\\windows\\accessibletech\\uiama"...
0x180007f63  mov     edx, 59h ; 'Y'; void *
0x180007f68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007f6e  mov     rcx, [rsp+68h+var_30]
0x180007f73  test    rcx, rcx
0x180007f76  jz      short loc_180007F85
0x180007f78  mov     rax, [rcx]
0x180007f7b  mov     rax, [rax+10h]
0x180007f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f84  nop
0x180007f85  mov     rcx, qword ptr [rsp+68h+var_48]
0x180007f8a  mov     rax, [rcx]
0x180007f8d  mov     r8, r14
0x180007f90  lea     rdx, _GUID_fcbc010e_a314_43e9_b40a_49690a0c8b78
0x180007f97  mov     rax, [rax]
0x180007f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f9f  nop
0x180007fa0  mov     rcx, [rsp+68h]; this
0x180007fa5  test    eax, eax
0x180007fa7  jns     short loc_180007FBE
0x180007fa9  mov     r9d, eax; char *
0x180007fac  lea     r8, aOnecoreWindows_27; "onecore\\windows\\accessibletech\\uiama"...
0x180007fb3  mov     edx, 5Bh ; '['; void *
0x180007fb8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007fbe  mov     rcx, qword ptr [rsp+68h+var_48]
0x180007fc3  test    rcx, rcx
0x180007fc6  jz      short loc_180007FDE
0x180007fc8  mov     qword ptr [rsp+68h+var_48], 0
0x180007fd1  mov     rax, [rcx]
0x180007fd4  mov     rax, [rax+10h]
0x180007fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fdd  nop
0x180007fde  mov     rcx, [rsp+68h+var_38]
0x180007fe3  test    rcx, rcx
0x180007fe6  jz      short loc_180007FF5
0x180007fe8  mov     rax, [rcx]
0x180007feb  mov     rax, [rax+10h]
0x180007fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ff4  nop
0x180007ff5  mov     rcx, [rsp+68h+var_40]
0x180007ffa  test    rcx, rcx
0x180007ffd  jz      short loc_180008015
0x180007fff  mov     [rsp+68h+var_40], 0
0x180008008  mov     rax, [rcx]
0x18000800b  mov     rax, [rax+10h]
0x18000800f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008014  nop
0x180008015  xor     eax, eax
0x180008017  jmp     short loc_18000801D
0x180008019  mov     eax, dword ptr [rsp+68h+arg_8]
0x18000801d  mov     rbx, [rsp+68h+arg_0]
0x180008022  add     rsp, 50h
0x180008026  pop     r14
0x180008028  pop     rdi
0x180008029  pop     rsi
0x18000802a  retn
```
