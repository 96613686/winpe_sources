# winrt::hresult_error::to_abi(void)

- ea: `0x180009ef0`
- end: `0x180009f68`
- name: `?to_abi@hresult_error@winrt@@QEBA?AUhresult@2@XZ`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bb08`
- `0x18000bb6e`
- `0x18000bc67`
- `0x18000bd60`

## callees

- `0x1800020f1`
- `0x180009ef0`
- `0x18000a014`
- `0x18000d010`

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
0x180009ef0  mov     r11, rsp
0x180009ef3  mov     [r11+10h], rbx
0x180009ef7  mov     [r11+18h], rsi
0x180009efb  push    rdi
0x180009efc  sub     rsp, 20h
0x180009f00  mov     rsi, rcx
0x180009f03  mov     rdi, rdx
0x180009f06  mov     rcx, [rcx+10h]
0x180009f0a  test    rcx, rcx
0x180009f0d  jz      short loc_180009F50
0x180009f0f  mov     rax, [rcx]
0x180009f12  lea     r8, [r11+8]
0x180009f16  lea     rdx, ??$guid_v@UIErrorInfo@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IErrorInfo>
0x180009f1d  mov     qword ptr [r11+8], 0
0x180009f25  mov     rax, [rax]
0x180009f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f2d  mov     rbx, [rsp+28h+perrinfo]
0x180009f32  xor     ecx, ecx; dwReserved
0x180009f34  mov     rdx, rbx; perrinfo
0x180009f37  mov     [rsp+28h+perrinfo], rbx
0x180009f3c  call    SetErrorInfo_0
0x180009f41  test    rbx, rbx
0x180009f44  jz      short loc_180009F50
0x180009f46  lea     rcx, [rsp+28h+perrinfo]
0x180009f4b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180009f50  mov     eax, [rsi+0Ch]
0x180009f53  mov     rbx, [rsp+28h+arg_8]
0x180009f58  mov     rsi, [rsp+28h+arg_10]
0x180009f5d  mov     [rdi], eax
0x180009f5f  mov     rax, rdi
0x180009f62  add     rsp, 20h
0x180009f66  pop     rdi
0x180009f67  retn
```
