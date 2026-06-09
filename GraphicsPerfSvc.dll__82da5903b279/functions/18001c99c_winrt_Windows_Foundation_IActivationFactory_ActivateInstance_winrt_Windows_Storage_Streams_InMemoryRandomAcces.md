# winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream>(void)

- ea: `0x18001c99c`
- end: `0x18001ca4f`
- name: `??$ActivateInstance@UInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUInMemoryRandomAccessStream@Streams@Storage@23@XZ`
- size: `179`
- prototype: `struct IUnknown *__fastcall(__int64 *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001c900`
- `0x18001ec04`

## callees

- `0x18001c99c`
- `0x180021880`
- `0x180022258`
- `0x180022a18`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct IUnknown *__fastcall winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream>(
        __int64 *a1,
        struct IUnknown *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, void **); // rbx
  void **v5; // rax
  unsigned int v6; // eax
  void (__fastcall ***v7)(_QWORD, __int64 *, _QWORD *); // rcx
  int v9; // [rsp+28h] [rbp-18h] BYREF
  __int128 v10; // [rsp+30h] [rbp-10h]
  void (__fastcall ***v11)(_QWORD, __int64 *, struct IUnknown **); // [rsp+60h] [rbp+20h] BYREF
  struct IUnknown *v12; // [rsp+68h] [rbp+28h] BYREF

  v12 = a2;
  v11 = 0;
  v9 = 0;
  v10 = 0;
  v3 = *a1;
  v4 = *(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)*a1 + 48LL);
  v5 = winrt::put_abi((winrt *)&v11, a2);
  v6 = v4(v3, v5);
  winrt::check_hresult(&v12, v6, &v9);
  v7 = (void (__fastcall ***)(_QWORD, __int64 *, _QWORD *))v11;
  if ( v11 )
  {
    v12 = 0;
    (**v11)(v11, winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>, &v12);
    a2->lpVtbl = (struct IUnknownVtbl *)v12;
    v7 = (void (__fastcall ***)(_QWORD, __int64 *, _QWORD *))v11;
  }
  else
  {
    a2->lpVtbl = 0;
  }
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  return a2;
}

```

## disassembly

```asm
0x18001c99c  mov     [rsp-18h+arg_10], rbx
0x18001c9a1  mov     [rsp-18h+arg_8], rdx
0x18001c9a6  push    rbp
0x18001c9a7  push    rsi
0x18001c9a8  push    rdi
0x18001c9a9  mov     rbp, rsp
0x18001c9ac  sub     rsp, 40h
0x18001c9b0  mov     rsi, rdx
0x18001c9b3  mov     [rbp+arg_0], 0
0x18001c9bb  mov     [rbp+var_18], 0
0x18001c9c2  xorps   xmm0, xmm0
0x18001c9c5  movdqu  [rbp+var_10], xmm0
0x18001c9ca  mov     rdi, [rcx]
0x18001c9cd  mov     rax, [rdi]
0x18001c9d0  mov     rbx, [rax+30h]
0x18001c9d4  lea     rcx, [rbp+arg_0]; this
0x18001c9d8  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18001c9dd  mov     rdx, rax
0x18001c9e0  mov     rcx, rdi
0x18001c9e3  mov     rax, rbx
0x18001c9e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9eb  lea     r8, [rbp+var_18]
0x18001c9ef  mov     edx, eax
0x18001c9f1  lea     rcx, [rbp+arg_8]
0x18001c9f5  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001c9fa  mov     rcx, [rbp+arg_0]
0x18001c9fe  test    rcx, rcx
0x18001ca01  jnz     short loc_18001CA08
0x18001ca03  mov     [rsi], rcx
0x18001ca06  jmp     short loc_18001CA31
0x18001ca08  mov     [rbp+arg_8], 0
0x18001ca10  mov     rax, [rcx]
0x18001ca13  lea     r8, [rbp+arg_8]
0x18001ca17  lea     rdx, ??$guid_v@UIRandomAccessStream@Streams@Storage@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Storage::Streams::IRandomAccessStream>
0x18001ca1e  mov     rax, [rax]
0x18001ca21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca26  mov     rax, [rbp+arg_8]
0x18001ca2a  mov     [rsi], rax
0x18001ca2d  mov     rcx, [rbp+arg_0]
0x18001ca31  test    rcx, rcx
0x18001ca34  jz      short loc_18001CA3F
0x18001ca36  lea     rcx, [rbp+arg_0]
0x18001ca3a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001ca3f  mov     rax, rsi
0x18001ca42  mov     rbx, [rsp+40h+arg_10]
0x18001ca47  add     rsp, 40h
0x18001ca4b  pop     rdi
0x18001ca4c  pop     rsi
0x18001ca4d  pop     rbp
0x18001ca4e  retn
```
