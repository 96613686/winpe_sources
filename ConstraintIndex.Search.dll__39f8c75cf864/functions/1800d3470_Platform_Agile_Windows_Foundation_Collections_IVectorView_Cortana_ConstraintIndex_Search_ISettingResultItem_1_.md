# Platform::Agile<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *,1>::Get(void)

- ea: `0x1800d3470`
- end: `0x1800d35af`
- name: `?Get@?$Agile@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@$00@Platform@@QEBAPE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@XZ`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800d5f40`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x180087e90`
- `0x1800d3470`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800d34ad`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800d34ad`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800d34e7`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800d34e7`

## pseudocode

```c
__int64 __fastcall Platform::Agile<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *,1>::Get(
        Platform::Details **a1)
{
  HRESULT ContextToken; // eax
  Platform::Details *v3; // rcx
  int v4; // eax
  unsigned int (__fastcall *v5)(struct IUnknownVtbl *, GUID *, __int64 *); // rbx
  __int64 v6; // rbx
  struct IUnknown v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  ULONG_PTR pToken; // [rsp+30h] [rbp-18h] BYREF

  if ( *((_DWORD *)a1 + 6) == 1 || !*a1 )
  {
    v3 = *a1;
  }
  else
  {
    pToken = 0;
    ContextToken = CoGetContextToken(&pToken);
    if ( ContextToken < 0 )
      __abi_WinRTraiseException(ContextToken);
    v3 = *a1;
    if ( (Platform::Details *)pToken != a1[2] )
    {
      v8.lpVtbl = 0;
      v4 = ((int (__stdcall *)(Platform::Details *__hidden, struct IUnknown *, const struct _GUID *, struct IUnknown *))Platform::Details::GetProxyImpl)(
             v3,
             (struct IUnknown *)&_uuidof__AU__IVectorView_PE_AAUISettingResultItem_Search_ConstraintIndex_Cortana___Collections_Foundation_Windows__,
             (const struct _GUID *)a1[1],
             &v8);
      if ( v4 < 0 )
        __abi_WinRTraiseException(v4);
      if ( *((_DWORD *)a1 + 6) == 2 )
      {
        v9 = 0;
        v5 = *(unsigned int (__fastcall **)(struct IUnknownVtbl *, GUID *, __int64 *))v8.lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
        if ( !v5(v8.lpVtbl, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90, &v9) )
        {
          *((_DWORD *)a1 + 6) = 1;
          a1[2] = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 1);
          v6 = __abi_winrt_ptr_ctor(*a1);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
LABEL_11:
          __abi_winrt_ptr_dtor(v8.lpVtbl);
          return v6;
        }
        *((_DWORD *)a1 + 6) = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      }
      v6 = __abi_winrt_ptr_ctor(v8.lpVtbl);
      goto LABEL_11;
    }
  }
  return __abi_winrt_ptr_ctor(v3);
}

```

## disassembly

```asm
0x1800d3470  push    rbp
0x1800d3472  push    rbx
0x1800d3473  push    rsi
0x1800d3474  push    rdi
0x1800d3475  mov     rbp, rsp
0x1800d3478  sub     rsp, 48h
0x1800d347c  mov     rax, cs:__security_cookie
0x1800d3483  xor     rax, rsp
0x1800d3486  mov     [rbp+var_10], rax
0x1800d348a  mov     rdi, rcx
0x1800d348d  cmp     dword ptr [rcx+18h], 1
0x1800d3491  jz      loc_1800D3592
0x1800d3497  cmp     qword ptr [rcx], 0
0x1800d349b  jz      loc_1800D3592
0x1800d34a1  mov     [rbp+pToken], 0
0x1800d34a9  lea     rcx, [rbp+pToken]; pToken
0x1800d34ad  call    cs:__imp_CoGetContextToken
0x1800d34b3  test    eax, eax
0x1800d34b5  jns     short loc_1800D34BF
0x1800d34b7  mov     ecx, eax; int
0x1800d34b9  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800d34bf  mov     rcx, [rdi]
0x1800d34c2  mov     rax, [rdi+10h]
0x1800d34c6  cmp     [rbp+pToken], rax
0x1800d34ca  jz      loc_1800D3595
0x1800d34d0  mov     [rbp+var_28], 0
0x1800d34d8  lea     r9, [rbp+var_28]
0x1800d34dc  mov     r8, [rdi+8]
0x1800d34e0  lea     rdx, __uuidof_?AU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@
0x1800d34e7  call    cs:__imp_?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z; Platform::Details::GetProxyImpl(IUnknown *,_GUID const &,IUnknown *,IUnknown * *)
0x1800d34ed  test    eax, eax
0x1800d34ef  jns     short loc_1800D34F9
0x1800d34f1  mov     ecx, eax; int
0x1800d34f3  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800d34f9  cmp     dword ptr [rdi+18h], 2
0x1800d34fd  jnz     loc_1800D3584
0x1800d3503  mov     [rbp+var_20], 0
0x1800d350b  mov     rax, [rbp+var_28]
0x1800d350f  mov     rcx, [rax]
0x1800d3512  mov     rbx, [rcx]
0x1800d3515  lea     rcx, [rbp+var_20]
0x1800d3519  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d351e  lea     r8, [rbp+var_20]
0x1800d3522  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x1800d3529  mov     rcx, [rbp+var_28]
0x1800d352d  mov     rax, rbx
0x1800d3530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3535  test    eax, eax
0x1800d3537  jnz     short loc_1800D3574
0x1800d3539  mov     dword ptr [rdi+18h], 1
0x1800d3540  mov     qword ptr [rdi+10h], 0
0x1800d3548  lea     rcx, [rdi+8]
0x1800d354c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d3551  mov     rcx, [rdi]
0x1800d3554  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d3559  mov     rbx, rax
0x1800d355c  lea     rcx, [rbp+var_20]
0x1800d3560  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d3565  nop
0x1800d3566  mov     rcx, [rbp+var_28]
0x1800d356a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800d356f  mov     rax, rbx
0x1800d3572  jmp     short loc_1800D359A
0x1800d3574  mov     dword ptr [rdi+18h], 0
0x1800d357b  lea     rcx, [rbp+var_20]
0x1800d357f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d3584  mov     rcx, [rbp+var_28]
0x1800d3588  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d358d  mov     rbx, rax
0x1800d3590  jmp     short loc_1800D3566
0x1800d3592  mov     rcx, [rcx]
0x1800d3595  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d359a  mov     rcx, [rbp+var_10]
0x1800d359e  xor     rcx, rsp; StackCookie
0x1800d35a1  call    __security_check_cookie
0x1800d35a6  add     rsp, 48h
0x1800d35aa  pop     rdi
0x1800d35ab  pop     rsi
0x1800d35ac  pop     rbx
0x1800d35ad  pop     rbp
0x1800d35ae  retn
```
