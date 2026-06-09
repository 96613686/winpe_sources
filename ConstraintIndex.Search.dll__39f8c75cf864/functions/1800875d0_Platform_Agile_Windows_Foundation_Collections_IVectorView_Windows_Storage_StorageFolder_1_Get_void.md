# Platform::Agile<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFolder *> *,1>::Get(void)

- ea: `0x1800875d0`
- end: `0x18008770f`
- name: `?Get@?$Agile@PE$AAU?$IVectorView@PE$AAVStorageFolder@Storage@Windows@@@Collections@Foundation@Windows@@$00@Platform@@QEBAPE$AAU?$IVectorView@PE$AAVStorageFolder@Storage@Windows@@@Collections@Foundation@Windows@@XZ`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008b0ec`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x1800875d0`
- `0x180087e90`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x18008760d`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x18008760d`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x180087647`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x180087647`

## pseudocode

```c
__int64 __fastcall Platform::Agile<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFolder __gc *> __gc *,1>::Get(
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
             (struct IUnknown *)_uuidof__AU__IVectorView_PE_AAVStorageFolder_Storage_Windows___Collections_Foundation_Windows__,
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
0x1800875d0  push    rbp
0x1800875d2  push    rbx
0x1800875d3  push    rsi
0x1800875d4  push    rdi
0x1800875d5  mov     rbp, rsp
0x1800875d8  sub     rsp, 48h
0x1800875dc  mov     rax, cs:__security_cookie
0x1800875e3  xor     rax, rsp
0x1800875e6  mov     [rbp+var_10], rax
0x1800875ea  mov     rdi, rcx
0x1800875ed  cmp     dword ptr [rcx+18h], 1
0x1800875f1  jz      loc_1800876F2
0x1800875f7  cmp     qword ptr [rcx], 0
0x1800875fb  jz      loc_1800876F2
0x180087601  mov     [rbp+pToken], 0
0x180087609  lea     rcx, [rbp+pToken]; pToken
0x18008760d  call    cs:__imp_CoGetContextToken
0x180087613  test    eax, eax
0x180087615  jns     short loc_18008761F
0x180087617  mov     ecx, eax; int
0x180087619  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18008761f  mov     rcx, [rdi]
0x180087622  mov     rax, [rdi+10h]
0x180087626  cmp     [rbp+pToken], rax
0x18008762a  jz      loc_1800876F5
0x180087630  mov     [rbp+var_28], 0
0x180087638  lea     r9, [rbp+var_28]
0x18008763c  mov     r8, [rdi+8]
0x180087640  lea     rdx, __uuidof_?AU?$IVectorView@PE$AAVStorageFolder@Storage@Windows@@@Collections@Foundation@Windows@@
0x180087647  call    cs:__imp_?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z; Platform::Details::GetProxyImpl(IUnknown *,_GUID const &,IUnknown *,IUnknown * *)
0x18008764d  test    eax, eax
0x18008764f  jns     short loc_180087659
0x180087651  mov     ecx, eax; int
0x180087653  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180087659  cmp     dword ptr [rdi+18h], 2
0x18008765d  jnz     loc_1800876E4
0x180087663  mov     [rbp+var_20], 0
0x18008766b  mov     rax, [rbp+var_28]
0x18008766f  mov     rcx, [rax]
0x180087672  mov     rbx, [rcx]
0x180087675  lea     rcx, [rbp+var_20]
0x180087679  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008767e  lea     r8, [rbp+var_20]
0x180087682  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x180087689  mov     rcx, [rbp+var_28]
0x18008768d  mov     rax, rbx
0x180087690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087695  test    eax, eax
0x180087697  jnz     short loc_1800876D4
0x180087699  mov     dword ptr [rdi+18h], 1
0x1800876a0  mov     qword ptr [rdi+10h], 0
0x1800876a8  lea     rcx, [rdi+8]
0x1800876ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800876b1  mov     rcx, [rdi]
0x1800876b4  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800876b9  mov     rbx, rax
0x1800876bc  lea     rcx, [rbp+var_20]
0x1800876c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800876c5  nop
0x1800876c6  mov     rcx, [rbp+var_28]
0x1800876ca  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800876cf  mov     rax, rbx
0x1800876d2  jmp     short loc_1800876FA
0x1800876d4  mov     dword ptr [rdi+18h], 0
0x1800876db  lea     rcx, [rbp+var_20]
0x1800876df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800876e4  mov     rcx, [rbp+var_28]
0x1800876e8  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800876ed  mov     rbx, rax
0x1800876f0  jmp     short loc_1800876C6
0x1800876f2  mov     rcx, [rcx]
0x1800876f5  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800876fa  mov     rcx, [rbp+var_10]
0x1800876fe  xor     rcx, rsp; StackCookie
0x180087701  call    __security_check_cookie
0x180087706  add     rsp, 48h
0x18008770a  pop     rdi
0x18008770b  pop     rsi
0x18008770c  pop     rbx
0x18008770d  pop     rbp
0x18008770e  retn
```
