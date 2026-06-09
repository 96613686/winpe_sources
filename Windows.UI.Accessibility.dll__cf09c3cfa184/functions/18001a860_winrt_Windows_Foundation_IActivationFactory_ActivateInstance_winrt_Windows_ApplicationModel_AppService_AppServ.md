# winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::ApplicationModel::AppService::AppServiceConnection>(void)

- ea: `0x18001a860`
- end: `0x18001a913`
- name: `??$ActivateInstance@UAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUAppServiceConnection@AppService@ApplicationModel@23@XZ`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a600`
- `0x180023898`

## callees

- `0x1800072d8`
- `0x18001a860`
- `0x180024334`
- `0x18002474c`
- `0x180035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct IUnknown *__fastcall winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::ApplicationModel::AppService::AppServiceConnection>(
        __int64 *a1,
        struct IUnknown *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, void **); // rbx
  void **v5; // rax
  unsigned int v6; // eax
  void (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rcx
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
  v7 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v11;
  if ( v11 )
  {
    v12 = 0;
    (**v11)(v11, winrt::impl::guid_v<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>, &v12);
    a2->lpVtbl = (struct IUnknownVtbl *)v12;
    v7 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v11;
  }
  else
  {
    a2->lpVtbl = 0;
  }
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v11);
  return a2;
}

```

## disassembly

```asm
0x18001a860  mov     [rsp-18h+arg_10], rbx
0x18001a865  mov     [rsp-18h+arg_8], rdx
0x18001a86a  push    rbp
0x18001a86b  push    rsi
0x18001a86c  push    rdi
0x18001a86d  mov     rbp, rsp
0x18001a870  sub     rsp, 40h
0x18001a874  mov     rsi, rdx
0x18001a877  mov     [rbp+arg_0], 0
0x18001a87f  mov     [rbp+var_18], 0
0x18001a886  xorps   xmm0, xmm0
0x18001a889  movdqu  [rbp+var_10], xmm0
0x18001a88e  mov     rdi, [rcx]
0x18001a891  mov     rax, [rdi]
0x18001a894  mov     rbx, [rax+30h]
0x18001a898  lea     rcx, [rbp+arg_0]; this
0x18001a89c  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18001a8a1  mov     rdx, rax
0x18001a8a4  mov     rcx, rdi
0x18001a8a7  mov     rax, rbx
0x18001a8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8af  lea     r8, [rbp+var_18]
0x18001a8b3  mov     edx, eax
0x18001a8b5  lea     rcx, [rbp+arg_8]
0x18001a8b9  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001a8be  mov     rcx, [rbp+arg_0]
0x18001a8c2  test    rcx, rcx
0x18001a8c5  jnz     short loc_18001A8CC
0x18001a8c7  mov     [rsi], rcx
0x18001a8ca  jmp     short loc_18001A8F5
0x18001a8cc  mov     [rbp+arg_8], 0
0x18001a8d4  mov     rax, [rcx]
0x18001a8d7  lea     r8, [rbp+arg_8]
0x18001a8db  lea     rdx, ??$guid_v@UIAppServiceConnection@AppService@ApplicationModel@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::ApplicationModel::AppService::IAppServiceConnection>
0x18001a8e2  mov     rax, [rax]
0x18001a8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8ea  mov     rax, [rbp+arg_8]
0x18001a8ee  mov     [rsi], rax
0x18001a8f1  mov     rcx, [rbp+arg_0]
0x18001a8f5  test    rcx, rcx
0x18001a8f8  jz      short loc_18001A903
0x18001a8fa  lea     rcx, [rbp+arg_0]
0x18001a8fe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001a903  mov     rax, rsi
0x18001a906  mov     rbx, [rsp+40h+arg_10]
0x18001a90b  add     rsp, 40h
0x18001a90f  pop     rdi
0x18001a910  pop     rsi
0x18001a911  pop     rbp
0x18001a912  retn
```
