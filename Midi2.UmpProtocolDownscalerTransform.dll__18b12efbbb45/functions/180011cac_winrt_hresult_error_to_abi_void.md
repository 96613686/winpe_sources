# winrt::hresult_error::to_abi(void)

- ea: `0x180011cac`
- end: `0x180011d24`
- name: `?to_abi@hresult_error@winrt@@QEBA?AUhresult@2@XZ`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001272b`
- `0x180012791`
- `0x180012895`
- `0x180012999`

## callees

- `0x180003b79`
- `0x180011cac`
- `0x180011e0c`
- `0x180013010`

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
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&perrinfo);
  }
  *a2 = *(_DWORD *)(a1 + 12);
  return a2;
}

```

## disassembly

```asm
0x180011cac  mov     r11, rsp
0x180011caf  mov     [r11+10h], rbx
0x180011cb3  mov     [r11+18h], rsi
0x180011cb7  push    rdi
0x180011cb8  sub     rsp, 20h
0x180011cbc  mov     rsi, rcx
0x180011cbf  mov     rdi, rdx
0x180011cc2  mov     rcx, [rcx+10h]
0x180011cc6  test    rcx, rcx
0x180011cc9  jz      short loc_180011D0C
0x180011ccb  mov     rax, [rcx]
0x180011cce  lea     r8, [r11+8]
0x180011cd2  lea     rdx, ??$guid_v@UIErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IErrorInfo>
0x180011cd9  mov     qword ptr [r11+8], 0
0x180011ce1  mov     rax, [rax]
0x180011ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ce9  mov     rbx, [rsp+28h+perrinfo]
0x180011cee  xor     ecx, ecx; dwReserved
0x180011cf0  mov     rdx, rbx; perrinfo
0x180011cf3  mov     [rsp+28h+perrinfo], rbx
0x180011cf8  call    SetErrorInfo_0
0x180011cfd  test    rbx, rbx
0x180011d00  jz      short loc_180011D0C
0x180011d02  lea     rcx, [rsp+28h+perrinfo]
0x180011d07  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011d0c  mov     eax, [rsi+0Ch]
0x180011d0f  mov     rbx, [rsp+28h+arg_8]
0x180011d14  mov     rsi, [rsp+28h+arg_10]
0x180011d19  mov     [rdi], eax
0x180011d1b  mov     rax, rdi
0x180011d1e  add     rsp, 20h
0x180011d22  pop     rdi
0x180011d23  retn
```
