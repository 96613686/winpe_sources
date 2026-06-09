# winrt::hresult_error::to_abi(void)

- ea: `0x180006d6c`
- end: `0x180006de4`
- name: `?to_abi@hresult_error@winrt@@QEBA?AUhresult@2@XZ`
- size: `120`
- prototype: `_DWORD *__fastcall(__int64, _DWORD *)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d5f0`
- `0x18000e257`
- `0x18000e4d4`
- `0x18000e8c1`
- `0x18000e927`
- `0x18000ea20`
- `0x18000eb19`

## callees

- `0x180002e05`
- `0x180006d6c`
- `0x180006dec`
- `0x18000f010`

## pseudocode

```c
_DWORD *__fastcall winrt::hresult_error::to_abi(__int64 a1, _DWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, IErrorInfo **); // rcx
  void (__fastcall **v5)(_QWORD, __int64 *, IErrorInfo **); // rax
  IErrorInfo *v6; // rbx
  IErrorInfo *perrinfo; // [rsp+30h] [rbp+8h] BYREF

  v4 = *(void (__fastcall ****)(_QWORD, __int64 *, IErrorInfo **))(a1 + 16);
  if ( v4 )
  {
    v5 = *v4;
    perrinfo = 0;
    (*v5)(v4, winrt::impl::guid_v<winrt::impl::IErrorInfo>, &perrinfo);
    v6 = perrinfo;
    SetErrorInfo_0(0, perrinfo);
    if ( v6 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&perrinfo);
  }
  *a2 = *(_DWORD *)(a1 + 12);
  return a2;
}

```

## disassembly

```asm
0x180006d6c  mov     r11, rsp
0x180006d6f  mov     [r11+10h], rbx
0x180006d73  mov     [r11+18h], rsi
0x180006d77  push    rdi
0x180006d78  sub     rsp, 20h
0x180006d7c  mov     rsi, rcx
0x180006d7f  mov     rdi, rdx
0x180006d82  mov     rcx, [rcx+10h]
0x180006d86  test    rcx, rcx
0x180006d89  jz      short loc_180006DCC
0x180006d8b  mov     rax, [rcx]
0x180006d8e  lea     r8, [r11+8]
0x180006d92  lea     rdx, ??$guid_v@UIErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IErrorInfo>
0x180006d99  mov     qword ptr [r11+8], 0
0x180006da1  mov     rax, [rax]
0x180006da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da9  mov     rbx, [rsp+28h+perrinfo]
0x180006dae  xor     ecx, ecx; dwReserved
0x180006db0  mov     rdx, rbx; perrinfo
0x180006db3  mov     [rsp+28h+perrinfo], rbx
0x180006db8  call    SetErrorInfo_0
0x180006dbd  test    rbx, rbx
0x180006dc0  jz      short loc_180006DCC
0x180006dc2  lea     rcx, [rsp+28h+perrinfo]
0x180006dc7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180006dcc  mov     eax, [rsi+0Ch]
0x180006dcf  mov     rbx, [rsp+28h+arg_8]
0x180006dd4  mov     rsi, [rsp+28h+arg_10]
0x180006dd9  mov     [rdi], eax
0x180006ddb  mov     rax, rdi
0x180006dde  add     rsp, 20h
0x180006de2  pop     rdi
0x180006de3  retn
```
