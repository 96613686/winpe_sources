# winrt::hresult_error::to_abi(void)

- ea: `0x18000f474`
- end: `0x18000f4ec`
- name: `?to_abi@hresult_error@winrt@@QEBA?AUhresult@2@XZ`
- size: `120`
- prototype: `_DWORD *__fastcall(__int64, _DWORD *)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010858`
- `0x180010ad5`
- `0x180010e07`
- `0x180010e6d`
- `0x180010f66`
- `0x18001105f`

## callees

- `0x180002ee5`
- `0x18000f474`
- `0x18000f544`
- `0x180012010`

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
0x18000f474  mov     r11, rsp
0x18000f477  mov     [r11+10h], rbx
0x18000f47b  mov     [r11+18h], rsi
0x18000f47f  push    rdi
0x18000f480  sub     rsp, 20h
0x18000f484  mov     rsi, rcx
0x18000f487  mov     rdi, rdx
0x18000f48a  mov     rcx, [rcx+10h]
0x18000f48e  test    rcx, rcx
0x18000f491  jz      short loc_18000F4D4
0x18000f493  mov     rax, [rcx]
0x18000f496  lea     r8, [r11+8]
0x18000f49a  lea     rdx, ??$guid_v@UIErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IErrorInfo>
0x18000f4a1  mov     qword ptr [r11+8], 0
0x18000f4a9  mov     rax, [rax]
0x18000f4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4b1  mov     rbx, [rsp+28h+perrinfo]
0x18000f4b6  xor     ecx, ecx; dwReserved
0x18000f4b8  mov     rdx, rbx; perrinfo
0x18000f4bb  mov     [rsp+28h+perrinfo], rbx
0x18000f4c0  call    SetErrorInfo_0
0x18000f4c5  test    rbx, rbx
0x18000f4c8  jz      short loc_18000F4D4
0x18000f4ca  lea     rcx, [rsp+28h+perrinfo]
0x18000f4cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000f4d4  mov     eax, [rsi+0Ch]
0x18000f4d7  mov     rbx, [rsp+28h+arg_8]
0x18000f4dc  mov     rsi, [rsp+28h+arg_10]
0x18000f4e1  mov     [rdi], eax
0x18000f4e3  mov     rax, rdi
0x18000f4e6  add     rsp, 20h
0x18000f4ea  pop     rdi
0x18000f4eb  retn
```
