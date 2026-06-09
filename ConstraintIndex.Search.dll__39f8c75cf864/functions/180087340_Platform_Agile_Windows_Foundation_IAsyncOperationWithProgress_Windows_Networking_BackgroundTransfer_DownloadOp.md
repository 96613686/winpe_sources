# Platform::Agile<Windows::Foundation::IAsyncOperationWithProgress<Windows::Networking::BackgroundTransfer::DownloadOperation *,Windows::Networking::BackgroundTransfer::DownloadOperation *> *,1>::Get(void)

- ea: `0x180087340`
- end: `0x18008747f`
- name: `?Get@?$Agile@PE$AAU?$IAsyncOperationWithProgress@PE$AAVDownloadOperation@BackgroundTransfer@Networking@Windows@@PE$AAV1234@@Foundation@Windows@@$00@Platform@@QEBAPE$AAU?$IAsyncOperationWithProgress@PE$AAVDownloadOperation@BackgroundTransfer@Networking@Windows@@PE$AAV1234@@Foundation@Windows@@XZ`
- size: `319`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800868d0`
- `0x180086a50`
- `0x180087bd0`
- `0x1800927c0`
- `0x180092910`
- `0x180092a50`
- `0x180093cc0`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x180087340`
- `0x180087e90`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x18008737d`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x18008737d`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800873b7`
- `wincorlib!?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z` at `0x1800873b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Platform::Agile<Windows::Foundation::IAsyncOperationWithProgress<Windows::Networking::BackgroundTransfer::DownloadOperation __gc *,Windows::Networking::BackgroundTransfer::DownloadOperation __gc *> __gc *,1>::Get(
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
             (struct IUnknown *)_uuidof__AU__IAsyncOperationWithProgress_PE_AAVDownloadOperation_BackgroundTransfer_Networking_Windows__PE_AAV1234__Foundation_Windows__,
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
0x180087340  push    rbp
0x180087342  push    rbx
0x180087343  push    rsi
0x180087344  push    rdi
0x180087345  mov     rbp, rsp
0x180087348  sub     rsp, 48h
0x18008734c  mov     rax, cs:__security_cookie
0x180087353  xor     rax, rsp
0x180087356  mov     [rbp+var_10], rax
0x18008735a  mov     rdi, rcx
0x18008735d  cmp     dword ptr [rcx+18h], 1
0x180087361  jz      loc_180087462
0x180087367  cmp     qword ptr [rcx], 0
0x18008736b  jz      loc_180087462
0x180087371  mov     [rbp+pToken], 0
0x180087379  lea     rcx, [rbp+pToken]; pToken
0x18008737d  call    cs:__imp_CoGetContextToken
0x180087383  test    eax, eax
0x180087385  jns     short loc_18008738F
0x180087387  mov     ecx, eax; int
0x180087389  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18008738f  mov     rcx, [rdi]
0x180087392  mov     rax, [rdi+10h]
0x180087396  cmp     [rbp+pToken], rax
0x18008739a  jz      loc_180087465
0x1800873a0  mov     [rbp+var_28], 0
0x1800873a8  lea     r9, [rbp+var_28]
0x1800873ac  mov     r8, [rdi+8]
0x1800873b0  lea     rdx, __uuidof_?AU?$IAsyncOperationWithProgress@PE$AAVDownloadOperation@BackgroundTransfer@Networking@Windows@@PE$AAV1234@@Foundation@Windows@@
0x1800873b7  call    cs:__imp_?GetProxyImpl@Details@Platform@@YAJPEAUIUnknown@@AEBU_GUID@@0PEAPEAU3@@Z; Platform::Details::GetProxyImpl(IUnknown *,_GUID const &,IUnknown *,IUnknown * *)
0x1800873bd  test    eax, eax
0x1800873bf  jns     short loc_1800873C9
0x1800873c1  mov     ecx, eax; int
0x1800873c3  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800873c9  cmp     dword ptr [rdi+18h], 2
0x1800873cd  jnz     loc_180087454
0x1800873d3  mov     [rbp+var_20], 0
0x1800873db  mov     rax, [rbp+var_28]
0x1800873df  mov     rcx, [rax]
0x1800873e2  mov     rbx, [rcx]
0x1800873e5  lea     rcx, [rbp+var_20]
0x1800873e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800873ee  lea     r8, [rbp+var_20]
0x1800873f2  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90
0x1800873f9  mov     rcx, [rbp+var_28]
0x1800873fd  mov     rax, rbx
0x180087400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087405  test    eax, eax
0x180087407  jnz     short loc_180087444
0x180087409  mov     dword ptr [rdi+18h], 1
0x180087410  mov     qword ptr [rdi+10h], 0
0x180087418  lea     rcx, [rdi+8]
0x18008741c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180087421  mov     rcx, [rdi]
0x180087424  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x180087429  mov     rbx, rax
0x18008742c  lea     rcx, [rbp+var_20]
0x180087430  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180087435  nop
0x180087436  mov     rcx, [rbp+var_28]
0x18008743a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18008743f  mov     rax, rbx
0x180087442  jmp     short loc_18008746A
0x180087444  mov     dword ptr [rdi+18h], 0
0x18008744b  lea     rcx, [rbp+var_20]
0x18008744f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180087454  mov     rcx, [rbp+var_28]
0x180087458  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18008745d  mov     rbx, rax
0x180087460  jmp     short loc_180087436
0x180087462  mov     rcx, [rcx]
0x180087465  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18008746a  mov     rcx, [rbp+var_10]
0x18008746e  xor     rcx, rsp; StackCookie
0x180087471  call    __security_check_cookie
0x180087476  add     rsp, 48h
0x18008747a  pop     rdi
0x18008747b  pop     rsi
0x18008747c  pop     rbx
0x18008747d  pop     rbp
0x18008747e  retn
```
