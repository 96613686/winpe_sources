# Platform::Agile<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFolder *> *,1>::SetObject(Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFolder *> *)

- ea: `0x180088cd0`
- end: `0x180088d9a`
- name: `?SetObject@?$Agile@PE$AAU?$IVectorView@PE$AAVStorageFolder@Storage@Windows@@@Collections@Foundation@Windows@@$00@Platform@@AEAAXPE$AAU?$IVectorView@PE$AAVStorageFolder@Storage@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `202`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180080cd8`
- `0x180081390`
- `0x180082eb8`
- `0x1800d23fc`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x180082fac`
- `0x180087e90`
- `0x18008892c`
- `0x180088cd0`
- `0x180092508`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x180088d4f`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x180088d4f`
- `wincorlib!?GetObjectContext@Details@Platform@@YAPEAUIUnknown@@XZ` at `0x180088d39`
- `wincorlib!?GetObjectContext@Details@Platform@@YAPEAUIUnknown@@XZ` at `0x180088d39`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Platform::Agile<Windows::Foundation::Collections::IVectorView<Windows::Storage::StorageFolder __gc *> __gc *,1>::SetObject(
        __int64 a1,
        unsigned int (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  unsigned int (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rbx
  Platform::Details *v5; // rcx
  struct IUnknown *ObjectContext; // rax
  HRESULT ContextToken; // eax
  __int64 v9; // [rsp+20h] [rbp-18h] BYREF

  Platform::Agile<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *,1>::Release();
  if ( a2 )
  {
    v9 = 0;
    v4 = **a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    if ( v4(a2, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90, &v9) )
    {
      *(_DWORD *)(a1 + 24) = 0;
      ObjectContext = Platform::Details::GetObjectContext(v5);
      Microsoft::WRL::ComPtr<IUnknown>::operator=(a1 + 8, ObjectContext);
      ContextToken = CoGetContextToken((ULONG_PTR *)(a1 + 16));
      if ( ContextToken < 0 )
        __abi_WinRTraiseException(ContextToken);
    }
    else
    {
      *(_DWORD *)(a1 + 24) = 1;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  }
  return __abi_winrt_ptr_assign(a1, a2);
}

```

## disassembly

```asm
0x180088cd0  mov     [rsp+arg_10], rbx
0x180088cd5  mov     [rsp+arg_18], rsi
0x180088cda  push    rdi
0x180088cdb  sub     rsp, 30h
0x180088cdf  mov     rax, cs:__security_cookie
0x180088ce6  xor     rax, rsp
0x180088ce9  mov     [rsp+38h+var_10], rax
0x180088cee  mov     rsi, rdx
0x180088cf1  mov     rdi, rcx
0x180088cf4  call    ?Release@?$Agile@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@$00@Platform@@QEAAXXZ; Platform::Agile<Cortana::ConstraintIndex::Search::ISettingResultItem *,1>::Release(void)
0x180088cf9  test    rsi, rsi
0x180088cfc  jz      short loc_180088D72
0x180088cfe  mov     [rsp+38h+var_18], 0
0x180088d07  mov     rax, [rsi]
0x180088d0a  mov     rbx, [rax]
0x180088d0d  lea     rcx, [rsp+38h+var_18]
0x180088d12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180088d17  lea     r8, [rsp+38h+var_18]
0x180088d1c  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x180088d23  mov     rcx, rsi
0x180088d26  mov     rax, rbx
0x180088d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d2e  test    eax, eax
0x180088d30  jz      short loc_180088D61
0x180088d32  mov     dword ptr [rdi+18h], 0
0x180088d39  call    cs:__imp_?GetObjectContext@Details@Platform@@YAPEAUIUnknown@@XZ; Platform::Details::GetObjectContext(void)
0x180088d3f  mov     rdx, rax
0x180088d42  lea     rcx, [rdi+8]
0x180088d46  call    ??4?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUnknown@@@Z; Microsoft::WRL::ComPtr<IUnknown>::operator=(IUnknown *)
0x180088d4b  lea     rcx, [rdi+10h]; pToken
0x180088d4f  call    cs:__imp_CoGetContextToken
0x180088d55  test    eax, eax
0x180088d57  jns     short loc_180088D68
0x180088d59  mov     ecx, eax; int
0x180088d5b  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180088d61  mov     dword ptr [rdi+18h], 1
0x180088d68  lea     rcx, [rsp+38h+var_18]
0x180088d6d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180088d72  mov     rdx, rsi
0x180088d75  mov     rcx, rdi
0x180088d78  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x180088d7d  mov     rcx, [rsp+38h+var_10]
0x180088d82  xor     rcx, rsp; StackCookie
0x180088d85  call    __security_check_cookie
0x180088d8a  mov     rbx, [rsp+38h+arg_10]
0x180088d8f  mov     rsi, [rsp+38h+arg_18]
0x180088d94  add     rsp, 30h
0x180088d98  pop     rdi
0x180088d99  retn
```
