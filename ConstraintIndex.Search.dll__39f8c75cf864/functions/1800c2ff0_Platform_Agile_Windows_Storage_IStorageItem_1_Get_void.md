# Platform::Agile<Windows::Storage::IStorageItem *,1>::Get(void)

- ea: `0x1800c2ff0`
- end: `0x1800c312f`
- name: `?Get@?$Agile@PE$AAUIStorageItem@Storage@Windows@@$00@Platform@@QEBAPE$AAUIStorageItem@Storage@Windows@@XZ`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800c6684`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x180087e90`
- `0x1800c2ff0`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800c302d`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800c302d`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800c3067`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800c3067`

## pseudocode

```c
__int64 __fastcall Platform::Agile<Windows::Storage::IStorageItem __gc *,1>::Get(Platform::Details **a1)
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
             (struct IUnknown *)_uuidof__AUIStorageItem_Storage_Windows__,
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
0x1800c2ff0  push    rbp
0x1800c2ff2  push    rbx
0x1800c2ff3  push    rsi
0x1800c2ff4  push    rdi
0x1800c2ff5  mov     rbp, rsp
0x1800c2ff8  sub     rsp, 48h
0x1800c2ffc  mov     rax, cs:__security_cookie
0x1800c3003  xor     rax, rsp
0x1800c3006  mov     [rbp+var_10], rax
0x1800c300a  mov     rdi, rcx
0x1800c300d  cmp     dword ptr [rcx+18h], 1
0x1800c3011  jz      loc_1800C3112
0x1800c3017  cmp     qword ptr [rcx], 0
0x1800c301b  jz      loc_1800C3112
0x1800c3021  mov     [rbp+pToken], 0
0x1800c3029  lea     rcx, [rbp+pToken]; pToken
0x1800c302d  call    cs:__imp_CoGetContextToken
0x1800c3033  test    eax, eax
0x1800c3035  jns     short loc_1800C303F
0x1800c3037  mov     ecx, eax; int
0x1800c3039  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800c303f  mov     rcx, [rdi]
0x1800c3042  mov     rax, [rdi+10h]
0x1800c3046  cmp     [rbp+pToken], rax
0x1800c304a  jz      loc_1800C3115
0x1800c3050  mov     [rbp+var_28], 0
0x1800c3058  lea     r9, [rbp+var_28]
0x1800c305c  mov     r8, [rdi+8]
0x1800c3060  lea     rdx, __uuidof_?AUIStorageItem@Storage@Windows@@
0x1800c3067  call    cs:__imp_?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z; Platform::Details::GetProxyImpl(IUnknown *,_GUID const &,IUnknown *,IUnknown * *)
0x1800c306d  test    eax, eax
0x1800c306f  jns     short loc_1800C3079
0x1800c3071  mov     ecx, eax; int
0x1800c3073  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800c3079  cmp     dword ptr [rdi+18h], 2
0x1800c307d  jnz     loc_1800C3104
0x1800c3083  mov     [rbp+var_20], 0
0x1800c308b  mov     rax, [rbp+var_28]
0x1800c308f  mov     rcx, [rax]
0x1800c3092  mov     rbx, [rcx]
0x1800c3095  lea     rcx, [rbp+var_20]
0x1800c3099  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c309e  lea     r8, [rbp+var_20]
0x1800c30a2  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x1800c30a9  mov     rcx, [rbp+var_28]
0x1800c30ad  mov     rax, rbx
0x1800c30b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c30b5  test    eax, eax
0x1800c30b7  jnz     short loc_1800C30F4
0x1800c30b9  mov     dword ptr [rdi+18h], 1
0x1800c30c0  mov     qword ptr [rdi+10h], 0
0x1800c30c8  lea     rcx, [rdi+8]
0x1800c30cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c30d1  mov     rcx, [rdi]
0x1800c30d4  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c30d9  mov     rbx, rax
0x1800c30dc  lea     rcx, [rbp+var_20]
0x1800c30e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c30e5  nop
0x1800c30e6  mov     rcx, [rbp+var_28]
0x1800c30ea  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800c30ef  mov     rax, rbx
0x1800c30f2  jmp     short loc_1800C311A
0x1800c30f4  mov     dword ptr [rdi+18h], 0
0x1800c30fb  lea     rcx, [rbp+var_20]
0x1800c30ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c3104  mov     rcx, [rbp+var_28]
0x1800c3108  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c310d  mov     rbx, rax
0x1800c3110  jmp     short loc_1800C30E6
0x1800c3112  mov     rcx, [rcx]
0x1800c3115  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800c311a  mov     rcx, [rbp+var_10]
0x1800c311e  xor     rcx, rsp; StackCookie
0x1800c3121  call    __security_check_cookie
0x1800c3126  add     rsp, 48h
0x1800c312a  pop     rdi
0x1800c312b  pop     rsi
0x1800c312c  pop     rbx
0x1800c312d  pop     rbp
0x1800c312e  retn
```
