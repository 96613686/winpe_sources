# CSearchPaneBroker::_EnsureSearchControlBroker(_GUID const &,void * *)

- ea: `0x180038a18`
- end: `0x180038c16`
- name: `?_EnsureSearchControlBroker@CSearchPaneBroker@@AEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `510`
- prototype: `__int64 __fastcall(CSearchPaneBroker *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180036ad0`
- `0x180037ac0`
- `0x1800381f0`
- `0x1800387dc`

## callees

- `0x180007b3c`
- `0x1800120dc`
- `0x180038a18`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038a76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038a76`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSearchPaneBroker::_EnsureSearchControlBroker(
        CSearchPaneBroker *this,
        const struct _GUID *a2,
        void **a3)
{
  _QWORD *v6; // rsi
  HRESULT v7; // edi
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, GUID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v14; // rbx
  __int64 v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h] BYREF
  __int64 v18; // [rsp+40h] [rbp-10h]
  __int64 v19; // [rsp+48h] [rbp-8h]
  __int64 v20; // [rsp+90h] [rbp+40h] BYREF
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp+50h] BYREF
  LPVOID ppv; // [rsp+A8h] [rbp+58h] BYREF

  *a3 = 0;
  v6 = (_QWORD *)((char *)this + 96);
  if ( *((_QWORD *)this + 12) )
    return (unsigned int)(**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v6)(*v6, a2, a3);
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
  v7 = CoCreateInstance(&CLSID_SearchSuggestionsService, 0, 1u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &ppv);
  if ( v7 >= 0 )
  {
    v21 = 0;
    v8 = ppv;
    v9 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)ppv + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v21);
    v7 = v9(
           v8,
           &IID_ISearchControlBrokerLocal,
           &GUID_cfac4e7e_0aec_4b8f_a1e3_70bec876d886,
           (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v21);
    if ( v7 >= 0 )
    {
      v17 = 0;
      v18 = 0;
      v19 = 0;
      v10 = *((_QWORD *)this + 15);
      v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 32LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v17);
      v18 = -1;
      v19 = -1;
      v7 = v11(v10, &v17);
      if ( v7 >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v21)[3])(v21, v17);
        if ( v7 >= 0 )
        {
          v20 = 0;
          v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v21;
          v13 = **v21;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v20);
          v7 = v13(v12, &GUID_1382fca2_6ff7_4775_b1af_87d3b3507e95, &v20);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v20 + 24LL))(
                   v20,
                   ((unsigned __int64)this + 32) & -(__int64)(this != 0));
            if ( v7 >= 0 )
            {
              v14 = v20;
              if ( *v6 != v20 )
              {
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
                v16 = *v6;
                *v6 = v14;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
              }
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v20);
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v17);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v21);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
  if ( v7 >= 0 )
    return (unsigned int)(**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v6)(*v6, a2, a3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180038a18  push    rbp
0x180038a1a  push    rbx
0x180038a1b  push    rsi
0x180038a1c  push    rdi
0x180038a1d  push    r12
0x180038a1f  push    r14
0x180038a21  push    r15
0x180038a23  mov     rbp, rsp
0x180038a26  sub     rsp, 50h
0x180038a2a  mov     r15, r8
0x180038a2d  mov     r12, rdx
0x180038a30  mov     r14, rcx
0x180038a33  mov     qword ptr [r8], 0
0x180038a3a  lea     rsi, [rcx+60h]
0x180038a3e  cmp     qword ptr [rsi], 0
0x180038a42  jnz     loc_180038BEF
0x180038a48  mov     [rbp+arg_18], 0
0x180038a50  lea     rcx, [rbp+arg_18]
0x180038a54  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038a59  lea     rax, [rbp+arg_18]
0x180038a5d  mov     [rsp+50h+ppv], rax; ppv
0x180038a62  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180038a69  xor     edx, edx; pUnkOuter
0x180038a6b  lea     r8d, [rdx+1]; dwClsContext
0x180038a6f  lea     rcx, CLSID_SearchSuggestionsService; rclsid
0x180038a76  call    cs:__imp_CoCreateInstance
0x180038a7c  mov     edi, eax
0x180038a7e  test    eax, eax
0x180038a80  js      loc_180038BE2
0x180038a86  mov     [rbp+arg_10], 0
0x180038a8e  mov     rdi, [rbp+arg_18]
0x180038a92  mov     rax, [rdi]
0x180038a95  mov     rbx, [rax+18h]
0x180038a99  lea     rcx, [rbp+arg_10]
0x180038a9d  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038aa2  lea     r9, [rbp+arg_10]
0x180038aa6  lea     r8, _GUID_cfac4e7e_0aec_4b8f_a1e3_70bec876d886
0x180038aad  lea     rdx, IID_ISearchControlBrokerLocal
0x180038ab4  mov     rcx, rdi
0x180038ab7  mov     rax, rbx
0x180038aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038abf  mov     edi, eax
0x180038ac1  test    eax, eax
0x180038ac3  js      loc_180038BD8
0x180038ac9  mov     [rbp+var_18], 0
0x180038ad1  mov     [rbp+var_10], 0
0x180038ad9  mov     [rbp+var_8], 0
0x180038ae1  mov     rdi, [r14+78h]
0x180038ae5  mov     rax, [rdi]
0x180038ae8  mov     rbx, [rax+20h]
0x180038aec  lea     rcx, [rbp+var_18]
0x180038af0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180038af5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180038af9  mov     [rbp+var_10], rax
0x180038afd  mov     [rbp+var_8], rax
0x180038b01  lea     rdx, [rbp+var_18]
0x180038b05  mov     rcx, rdi
0x180038b08  mov     rax, rbx
0x180038b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b10  mov     edi, eax
0x180038b12  test    eax, eax
0x180038b14  js      loc_180038BCE
0x180038b1a  mov     rcx, [rbp+arg_10]
0x180038b1e  mov     rax, [rcx]
0x180038b21  mov     rdx, [rbp+var_18]
0x180038b25  mov     rax, [rax+18h]
0x180038b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b2e  mov     edi, eax
0x180038b30  test    eax, eax
0x180038b32  js      loc_180038BCE
0x180038b38  mov     [rbp+arg_0], 0
0x180038b40  mov     rbx, [rbp+arg_10]
0x180038b44  mov     rax, [rbx]
0x180038b47  mov     rdi, [rax]
0x180038b4a  lea     rcx, [rbp+arg_0]
0x180038b4e  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038b53  lea     r8, [rbp+arg_0]
0x180038b57  lea     rdx, _GUID_1382fca2_6ff7_4775_b1af_87d3b3507e95
0x180038b5e  mov     rcx, rbx
0x180038b61  mov     rax, rdi
0x180038b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b69  mov     edi, eax
0x180038b6b  test    eax, eax
0x180038b6d  js      short loc_180038BC4
0x180038b6f  mov     rcx, [rbp+arg_0]
0x180038b73  mov     r8, [rcx]
0x180038b76  lea     rax, [r14+20h]
0x180038b7a  neg     r14
0x180038b7d  sbb     rdx, rdx
0x180038b80  and     rdx, rax
0x180038b83  mov     rax, [r8+18h]
0x180038b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b8c  mov     edi, eax
0x180038b8e  test    eax, eax
0x180038b90  js      short loc_180038BC4
0x180038b92  mov     rbx, [rbp+arg_0]
0x180038b96  cmp     [rsi], rbx
0x180038b99  jz      short loc_180038BC4
0x180038b9b  test    rbx, rbx
0x180038b9e  jz      short loc_180038BB0
0x180038ba0  mov     rax, [rbx]
0x180038ba3  mov     rcx, rbx
0x180038ba6  mov     rax, [rax+8]
0x180038baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038baf  nop
0x180038bb0  mov     rax, [rsi]
0x180038bb3  mov     [rbp+var_20], rax
0x180038bb7  mov     [rsi], rbx
0x180038bba  lea     rcx, [rbp+var_20]
0x180038bbe  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038bc3  nop
0x180038bc4  lea     rcx, [rbp+arg_0]
0x180038bc8  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038bcd  nop
0x180038bce  lea     rcx, [rbp+var_18]
0x180038bd2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180038bd7  nop
0x180038bd8  lea     rcx, [rbp+arg_10]
0x180038bdc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038be1  nop
0x180038be2  lea     rcx, [rbp+arg_18]
0x180038be6  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180038beb  test    edi, edi
0x180038bed  js      short loc_180038C05
0x180038bef  mov     rcx, [rsi]
0x180038bf2  mov     rax, [rcx]
0x180038bf5  mov     r8, r15
0x180038bf8  mov     rdx, r12
0x180038bfb  mov     rax, [rax]
0x180038bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c03  mov     edi, eax
0x180038c05  mov     eax, edi
0x180038c07  add     rsp, 50h
0x180038c0b  pop     r15
0x180038c0d  pop     r14
0x180038c0f  pop     r12
0x180038c11  pop     rdi
0x180038c12  pop     rsi
0x180038c13  pop     rbx
0x180038c14  pop     rbp
0x180038c15  retn
```
