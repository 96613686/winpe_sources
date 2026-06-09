# Platform::Agile<Windows::Foundation::IAsyncAction *,1>::Get(void)

- ea: `0x180087718`
- end: `0x180087857`
- name: `?Get@?$Agile@PE$AAUIAsyncAction@Foundation@Windows@@$00@Platform@@QEBAPE$AAUIAsyncAction@Foundation@Windows@@XZ`
- size: `319`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180086940`
- `0x180086ac0`
- `0x180087b80`
- `0x180092850`
- `0x180092990`
- `0x180092ad0`
- `0x180093c20`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x180087718`
- `0x180087e90`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x180087755`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x180087755`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x18008778f`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x18008778f`

## pseudocode

```c
__int64 __fastcall Platform::Agile<Windows::Foundation::IAsyncAction __gc *,1>::Get(Platform::Details **a1)
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
             (struct IUnknown *)&_uuidof__AUIAsyncAction_Foundation_Windows__,
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
0x180087718  push    rbp
0x18008771a  push    rbx
0x18008771b  push    rsi
0x18008771c  push    rdi
0x18008771d  mov     rbp, rsp
0x180087720  sub     rsp, 48h
0x180087724  mov     rax, cs:__security_cookie
0x18008772b  xor     rax, rsp
0x18008772e  mov     [rbp+var_10], rax
0x180087732  mov     rdi, rcx
0x180087735  cmp     dword ptr [rcx+18h], 1
0x180087739  jz      loc_18008783A
0x18008773f  cmp     qword ptr [rcx], 0
0x180087743  jz      loc_18008783A
0x180087749  mov     [rbp+pToken], 0
0x180087751  lea     rcx, [rbp+pToken]; pToken
0x180087755  call    cs:__imp_CoGetContextToken
0x18008775b  test    eax, eax
0x18008775d  jns     short loc_180087767
0x18008775f  mov     ecx, eax; int
0x180087761  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180087767  mov     rcx, [rdi]
0x18008776a  mov     rax, [rdi+10h]
0x18008776e  cmp     [rbp+pToken], rax
0x180087772  jz      loc_18008783D
0x180087778  mov     [rbp+var_28], 0
0x180087780  lea     r9, [rbp+var_28]
0x180087784  mov     r8, [rdi+8]
0x180087788  lea     rdx, __uuidof_?AUIAsyncAction@Foundation@Windows@@
0x18008778f  call    cs:__imp_?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z; Platform::Details::GetProxyImpl(IUnknown *,_GUID const &,IUnknown *,IUnknown * *)
0x180087795  test    eax, eax
0x180087797  jns     short loc_1800877A1
0x180087799  mov     ecx, eax; int
0x18008779b  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800877a1  cmp     dword ptr [rdi+18h], 2
0x1800877a5  jnz     loc_18008782C
0x1800877ab  mov     [rbp+var_20], 0
0x1800877b3  mov     rax, [rbp+var_28]
0x1800877b7  mov     rcx, [rax]
0x1800877ba  mov     rbx, [rcx]
0x1800877bd  lea     rcx, [rbp+var_20]
0x1800877c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800877c6  lea     r8, [rbp+var_20]
0x1800877ca  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x1800877d1  mov     rcx, [rbp+var_28]
0x1800877d5  mov     rax, rbx
0x1800877d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800877dd  test    eax, eax
0x1800877df  jnz     short loc_18008781C
0x1800877e1  mov     dword ptr [rdi+18h], 1
0x1800877e8  mov     qword ptr [rdi+10h], 0
0x1800877f0  lea     rcx, [rdi+8]
0x1800877f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800877f9  mov     rcx, [rdi]
0x1800877fc  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180087801  mov     rbx, rax
0x180087804  lea     rcx, [rbp+var_20]
0x180087808  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008780d  nop
0x18008780e  mov     rcx, [rbp+var_28]
0x180087812  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180087817  mov     rax, rbx
0x18008781a  jmp     short loc_180087842
0x18008781c  mov     dword ptr [rdi+18h], 0
0x180087823  lea     rcx, [rbp+var_20]
0x180087827  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008782c  mov     rcx, [rbp+var_28]
0x180087830  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180087835  mov     rbx, rax
0x180087838  jmp     short loc_18008780E
0x18008783a  mov     rcx, [rcx]
0x18008783d  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180087842  mov     rcx, [rbp+var_10]
0x180087846  xor     rcx, rsp; StackCookie
0x180087849  call    __security_check_cookie
0x18008784e  add     rsp, 48h
0x180087852  pop     rdi
0x180087853  pop     rsi
0x180087854  pop     rbx
0x180087855  pop     rbp
0x180087856  retn
```
