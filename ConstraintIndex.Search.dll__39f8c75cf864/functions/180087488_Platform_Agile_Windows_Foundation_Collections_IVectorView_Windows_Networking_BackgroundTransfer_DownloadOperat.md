# Platform::Agile<Windows::Foundation::Collections::IVectorView<Windows::Networking::BackgroundTransfer::DownloadOperation *> *,1>::Get(void)

- ea: `0x180087488`
- end: `0x1800875c7`
- name: `?Get@?$Agile@PE$AAU?$IVectorView@PE$AAVDownloadOperation@BackgroundTransfer@Networking@Windows@@@Collections@Foundation@Windows@@$00@Platform@@QEBAPE$AAU?$IVectorView@PE$AAVDownloadOperation@BackgroundTransfer@Networking@Windows@@@Collections@Foundation@Windows@@XZ`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008afe4`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x180087488`
- `0x180087e90`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800874c5`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x1800874c5`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800874ff`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800874ff`

## pseudocode

```c
__int64 __fastcall Platform::Agile<Windows::Foundation::Collections::IVectorView<Windows::Networking::BackgroundTransfer::DownloadOperation __gc *> __gc *,1>::Get(
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
             (struct IUnknown *)_uuidof__AU__IVectorView_PE_AAVDownloadOperation_BackgroundTransfer_Networking_Windows___Collections_Foundation_Windows__,
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
0x180087488  push    rbp
0x18008748a  push    rbx
0x18008748b  push    rsi
0x18008748c  push    rdi
0x18008748d  mov     rbp, rsp
0x180087490  sub     rsp, 48h
0x180087494  mov     rax, cs:__security_cookie
0x18008749b  xor     rax, rsp
0x18008749e  mov     [rbp+var_10], rax
0x1800874a2  mov     rdi, rcx
0x1800874a5  cmp     dword ptr [rcx+18h], 1
0x1800874a9  jz      loc_1800875AA
0x1800874af  cmp     qword ptr [rcx], 0
0x1800874b3  jz      loc_1800875AA
0x1800874b9  mov     [rbp+pToken], 0
0x1800874c1  lea     rcx, [rbp+pToken]; pToken
0x1800874c5  call    cs:__imp_CoGetContextToken
0x1800874cb  test    eax, eax
0x1800874cd  jns     short loc_1800874D7
0x1800874cf  mov     ecx, eax; int
0x1800874d1  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800874d7  mov     rcx, [rdi]
0x1800874da  mov     rax, [rdi+10h]
0x1800874de  cmp     [rbp+pToken], rax
0x1800874e2  jz      loc_1800875AD
0x1800874e8  mov     [rbp+var_28], 0
0x1800874f0  lea     r9, [rbp+var_28]
0x1800874f4  mov     r8, [rdi+8]
0x1800874f8  lea     rdx, __uuidof_?AU?$IVectorView@PE$AAVDownloadOperation@BackgroundTransfer@Networking@Windows@@@Collections@Foundation@Windows@@
0x1800874ff  call    cs:__imp_?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z; Platform::Details::GetProxyImpl(IUnknown *,_GUID const &,IUnknown *,IUnknown * *)
0x180087505  test    eax, eax
0x180087507  jns     short loc_180087511
0x180087509  mov     ecx, eax; int
0x18008750b  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x180087511  cmp     dword ptr [rdi+18h], 2
0x180087515  jnz     loc_18008759C
0x18008751b  mov     [rbp+var_20], 0
0x180087523  mov     rax, [rbp+var_28]
0x180087527  mov     rcx, [rax]
0x18008752a  mov     rbx, [rcx]
0x18008752d  lea     rcx, [rbp+var_20]
0x180087531  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180087536  lea     r8, [rbp+var_20]
0x18008753a  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x180087541  mov     rcx, [rbp+var_28]
0x180087545  mov     rax, rbx
0x180087548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008754d  test    eax, eax
0x18008754f  jnz     short loc_18008758C
0x180087551  mov     dword ptr [rdi+18h], 1
0x180087558  mov     qword ptr [rdi+10h], 0
0x180087560  lea     rcx, [rdi+8]
0x180087564  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180087569  mov     rcx, [rdi]
0x18008756c  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180087571  mov     rbx, rax
0x180087574  lea     rcx, [rbp+var_20]
0x180087578  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008757d  nop
0x18008757e  mov     rcx, [rbp+var_28]
0x180087582  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180087587  mov     rax, rbx
0x18008758a  jmp     short loc_1800875B2
0x18008758c  mov     dword ptr [rdi+18h], 0
0x180087593  lea     rcx, [rbp+var_20]
0x180087597  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008759c  mov     rcx, [rbp+var_28]
0x1800875a0  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800875a5  mov     rbx, rax
0x1800875a8  jmp     short loc_18008757E
0x1800875aa  mov     rcx, [rcx]
0x1800875ad  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800875b2  mov     rcx, [rbp+var_10]
0x1800875b6  xor     rcx, rsp; StackCookie
0x1800875b9  call    __security_check_cookie
0x1800875be  add     rsp, 48h
0x1800875c2  pop     rdi
0x1800875c3  pop     rsi
0x1800875c4  pop     rbx
0x1800875c5  pop     rbp
0x1800875c6  retn
```
