# Platform::Agile<Cortana::ConstraintIndex::Search::ISettingResultItem *,1>::Get(void)

- ea: `0x1800d35b8`
- end: `0x1800d36f7`
- name: `?Get@?$Agile@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@$00@Platform@@QEBAPE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@XZ`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800d1c14`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x180087e90`
- `0x1800d35b8`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800d35f5`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800d35f5`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800d362f`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800d362f`

## pseudocode

```c
__int64 __fastcall Platform::Agile<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *,1>::Get(
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
             (struct IUnknown *)&_uuidof__AUISettingResultItem_Search_ConstraintIndex_Cortana__,
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
0x1800d35b8  push    rbp
0x1800d35ba  push    rbx
0x1800d35bb  push    rsi
0x1800d35bc  push    rdi
0x1800d35bd  mov     rbp, rsp
0x1800d35c0  sub     rsp, 48h
0x1800d35c4  mov     rax, cs:__security_cookie
0x1800d35cb  xor     rax, rsp
0x1800d35ce  mov     [rbp+var_10], rax
0x1800d35d2  mov     rdi, rcx
0x1800d35d5  cmp     dword ptr [rcx+18h], 1
0x1800d35d9  jz      loc_1800D36DA
0x1800d35df  cmp     qword ptr [rcx], 0
0x1800d35e3  jz      loc_1800D36DA
0x1800d35e9  mov     [rbp+pToken], 0
0x1800d35f1  lea     rcx, [rbp+pToken]; pToken
0x1800d35f5  call    cs:__imp_CoGetContextToken
0x1800d35fb  test    eax, eax
0x1800d35fd  jns     short loc_1800D3607
0x1800d35ff  mov     ecx, eax; int
0x1800d3601  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800d3607  mov     rcx, [rdi]
0x1800d360a  mov     rax, [rdi+10h]
0x1800d360e  cmp     [rbp+pToken], rax
0x1800d3612  jz      loc_1800D36DD
0x1800d3618  mov     [rbp+var_28], 0
0x1800d3620  lea     r9, [rbp+var_28]
0x1800d3624  mov     r8, [rdi+8]
0x1800d3628  lea     rdx, __uuidof_?AUISettingResultItem@Search@ConstraintIndex@Cortana@@
0x1800d362f  call    cs:__imp_?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z; Platform::Details::GetProxyImpl(IUnknown *,_GUID const &,IUnknown *,IUnknown * *)
0x1800d3635  test    eax, eax
0x1800d3637  jns     short loc_1800D3641
0x1800d3639  mov     ecx, eax; int
0x1800d363b  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800d3641  cmp     dword ptr [rdi+18h], 2
0x1800d3645  jnz     loc_1800D36CC
0x1800d364b  mov     [rbp+var_20], 0
0x1800d3653  mov     rax, [rbp+var_28]
0x1800d3657  mov     rcx, [rax]
0x1800d365a  mov     rbx, [rcx]
0x1800d365d  lea     rcx, [rbp+var_20]
0x1800d3661  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d3666  lea     r8, [rbp+var_20]
0x1800d366a  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x1800d3671  mov     rcx, [rbp+var_28]
0x1800d3675  mov     rax, rbx
0x1800d3678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d367d  test    eax, eax
0x1800d367f  jnz     short loc_1800D36BC
0x1800d3681  mov     dword ptr [rdi+18h], 1
0x1800d3688  mov     qword ptr [rdi+10h], 0
0x1800d3690  lea     rcx, [rdi+8]
0x1800d3694  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d3699  mov     rcx, [rdi]
0x1800d369c  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d36a1  mov     rbx, rax
0x1800d36a4  lea     rcx, [rbp+var_20]
0x1800d36a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d36ad  nop
0x1800d36ae  mov     rcx, [rbp+var_28]
0x1800d36b2  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800d36b7  mov     rax, rbx
0x1800d36ba  jmp     short loc_1800D36E2
0x1800d36bc  mov     dword ptr [rdi+18h], 0
0x1800d36c3  lea     rcx, [rbp+var_20]
0x1800d36c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d36cc  mov     rcx, [rbp+var_28]
0x1800d36d0  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d36d5  mov     rbx, rax
0x1800d36d8  jmp     short loc_1800D36AE
0x1800d36da  mov     rcx, [rcx]
0x1800d36dd  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800d36e2  mov     rcx, [rbp+var_10]
0x1800d36e6  xor     rcx, rsp; StackCookie
0x1800d36e9  call    __security_check_cookie
0x1800d36ee  add     rsp, 48h
0x1800d36f2  pop     rdi
0x1800d36f3  pop     rsi
0x1800d36f4  pop     rbx
0x1800d36f5  pop     rbp
0x1800d36f6  retn
```
