# Platform::Agile<Windows::Foundation::Collections::IVectorView<WindowsUdk::System::Profile::SystemSettingEntryPoint *> *,1>::Get(void)

- ea: `0x1800a4fb0`
- end: `0x1800a50ef`
- name: `?Get@?$Agile@PE$AAU?$IVectorView@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@Collections@Foundation@Windows@@$00@Platform@@QEBAPE$AAU?$IVectorView@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@Collections@Foundation@Windows@@XZ`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800a9a88`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x180087e90`
- `0x1800a4fb0`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800a4fed`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800a4fed`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800a5027`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800a5027`

## pseudocode

```c
__int64 __fastcall Platform::Agile<Windows::Foundation::Collections::IVectorView<WindowsUdk::System::Profile::SystemSettingEntryPoint __gc *> __gc *,1>::Get(
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
             (struct IUnknown *)_uuidof__AU__IVectorView_PE_AAVSystemSettingEntryPoint_Profile_System_WindowsUdk___Collections_Foundation_Windows__,
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
0x1800a4fb0  push    rbp
0x1800a4fb2  push    rbx
0x1800a4fb3  push    rsi
0x1800a4fb4  push    rdi
0x1800a4fb5  mov     rbp, rsp
0x1800a4fb8  sub     rsp, 48h
0x1800a4fbc  mov     rax, cs:__security_cookie
0x1800a4fc3  xor     rax, rsp
0x1800a4fc6  mov     [rbp+var_10], rax
0x1800a4fca  mov     rdi, rcx
0x1800a4fcd  cmp     dword ptr [rcx+18h], 1
0x1800a4fd1  jz      loc_1800A50D2
0x1800a4fd7  cmp     qword ptr [rcx], 0
0x1800a4fdb  jz      loc_1800A50D2
0x1800a4fe1  mov     [rbp+pToken], 0
0x1800a4fe9  lea     rcx, [rbp+pToken]; pToken
0x1800a4fed  call    cs:__imp_CoGetContextToken
0x1800a4ff3  test    eax, eax
0x1800a4ff5  jns     short loc_1800A4FFF
0x1800a4ff7  mov     ecx, eax; int
0x1800a4ff9  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800a4fff  mov     rcx, [rdi]
0x1800a5002  mov     rax, [rdi+10h]
0x1800a5006  cmp     [rbp+pToken], rax
0x1800a500a  jz      loc_1800A50D5
0x1800a5010  mov     [rbp+var_28], 0
0x1800a5018  lea     r9, [rbp+var_28]
0x1800a501c  mov     r8, [rdi+8]
0x1800a5020  lea     rdx, __uuidof_?AU?$IVectorView@PE$AAVSystemSettingEntryPoint@Profile@System@WindowsUdk@@@Collections@Foundation@Windows@@
0x1800a5027  call    cs:__imp_?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z; Platform::Details::GetProxyImpl(IUnknown *,_GUID const &,IUnknown *,IUnknown * *)
0x1800a502d  test    eax, eax
0x1800a502f  jns     short loc_1800A5039
0x1800a5031  mov     ecx, eax; int
0x1800a5033  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800a5039  cmp     dword ptr [rdi+18h], 2
0x1800a503d  jnz     loc_1800A50C4
0x1800a5043  mov     [rbp+var_20], 0
0x1800a504b  mov     rax, [rbp+var_28]
0x1800a504f  mov     rcx, [rax]
0x1800a5052  mov     rbx, [rcx]
0x1800a5055  lea     rcx, [rbp+var_20]
0x1800a5059  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a505e  lea     r8, [rbp+var_20]
0x1800a5062  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x1800a5069  mov     rcx, [rbp+var_28]
0x1800a506d  mov     rax, rbx
0x1800a5070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5075  test    eax, eax
0x1800a5077  jnz     short loc_1800A50B4
0x1800a5079  mov     dword ptr [rdi+18h], 1
0x1800a5080  mov     qword ptr [rdi+10h], 0
0x1800a5088  lea     rcx, [rdi+8]
0x1800a508c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a5091  mov     rcx, [rdi]
0x1800a5094  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800a5099  mov     rbx, rax
0x1800a509c  lea     rcx, [rbp+var_20]
0x1800a50a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a50a5  nop
0x1800a50a6  mov     rcx, [rbp+var_28]
0x1800a50aa  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800a50af  mov     rax, rbx
0x1800a50b2  jmp     short loc_1800A50DA
0x1800a50b4  mov     dword ptr [rdi+18h], 0
0x1800a50bb  lea     rcx, [rbp+var_20]
0x1800a50bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a50c4  mov     rcx, [rbp+var_28]
0x1800a50c8  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800a50cd  mov     rbx, rax
0x1800a50d0  jmp     short loc_1800A50A6
0x1800a50d2  mov     rcx, [rcx]
0x1800a50d5  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800a50da  mov     rcx, [rbp+var_10]
0x1800a50de  xor     rcx, rsp; StackCookie
0x1800a50e1  call    __security_check_cookie
0x1800a50e6  add     rsp, 48h
0x1800a50ea  pop     rdi
0x1800a50eb  pop     rsi
0x1800a50ec  pop     rbx
0x1800a50ed  pop     rbp
0x1800a50ee  retn
```
