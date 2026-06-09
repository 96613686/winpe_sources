# CodeIntegrity::Management::detail::SbcpTokenView::ParseSbcpToken(void)

- ea: `0x180016b24`
- end: `0x180016b7a`
- name: `?ParseSbcpToken@SbcpTokenView@detail@Management@CodeIntegrity@@AEAAXXZ`
- size: `86`
- prototype: `void __fastcall(CodeIntegrity::Management::detail::SbcpTokenView *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009970`
- `0x180016780`
- `0x1800184d8`

## callees

- `0x180016828`
- `0x180016b24`
- `0x180029338`

## pseudocode

```c
void __fastcall CodeIntegrity::Management::detail::SbcpTokenView::ParseSbcpToken(
        CodeIntegrity::Management::detail::SbcpTokenView *this)
{
  char *v2; // rax
  void *v3; // rcx
  int v4; // ebx
  _QWORD v5[2]; // [rsp+20h] [rbp-28h] BYREF
  char v6; // [rsp+30h] [rbp-18h]

  v5[1] = 0;
  v2 = (char *)this + 16;
  v3 = (void *)*((_QWORD *)this + 14);
  v5[0] = v2;
  v6 = 1;
  v4 = SbpParsePolicy(v3, (unsigned int)(*((_DWORD *)this + 30) - (_DWORD)v3));
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECUREBOOT_POLICY *,void (*)(_SECUREBOOT_POLICY *),&void SbFreePolicy(_SECUREBOOT_POLICY *),wistd::integral_constant<unsigned __int64,0>,_SECUREBOOT_POLICY *,_SECUREBOOT_POLICY *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECUREBOOT_POLICY *,void (*)(_SECUREBOOT_POLICY *),&void SbFreePolicy(_SECUREBOOT_POLICY *),wistd::integral_constant<unsigned __int64,0>,_SECUREBOOT_POLICY *,_SECUREBOOT_POLICY *,0,std::nullptr_t>>>>(v5);
  if ( v4 < 0 )
    *((_WORD *)this + 4) |= 4u;
}

```

## disassembly

```asm
0x180016b24  mov     r11, rsp
0x180016b27  mov     [r11+8], rbx
0x180016b2b  push    rdi
0x180016b2c  sub     rsp, 40h
0x180016b30  mov     rdi, rcx
0x180016b33  mov     qword ptr [r11-20h], 0
0x180016b3b  lea     rax, [rcx+10h]
0x180016b3f  mov     rcx, [rcx+70h]; Src
0x180016b43  mov     [r11-28h], rax
0x180016b47  lea     r8, [r11-20h]
0x180016b4b  mov     [rsp+48h+var_18], 1
0x180016b50  mov     edx, [rdi+78h]
0x180016b53  sub     edx, ecx; Size
0x180016b55  call    SbpParsePolicy
0x180016b5a  lea     rcx, [rsp+48h+var_28]
0x180016b5f  mov     ebx, eax
0x180016b61  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SECUREBOOT_POLICY@@P6AXPEAU1@@Z$1?SbFreePolicy@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECUREBOOT_POLICY *,void (*)(_SECUREBOOT_POLICY *),&SbFreePolicy(_SECUREBOOT_POLICY *),wistd::integral_constant<unsigned __int64,0>,_SECUREBOOT_POLICY *,_SECUREBOOT_POLICY *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SECUREBOOT_POLICY *,void (*)(_SECUREBOOT_POLICY *),&SbFreePolicy(_SECUREBOOT_POLICY *),wistd::integral_constant<unsigned __int64,0>,_SECUREBOOT_POLICY *,_SECUREBOOT_POLICY *,0,std::nullptr_t>>>>(void)
0x180016b66  test    ebx, ebx
0x180016b68  jns     short loc_180016B6F
0x180016b6a  or      word ptr [rdi+8], 4
0x180016b6f  mov     rbx, [rsp+48h+arg_0]
0x180016b74  add     rsp, 40h
0x180016b78  pop     rdi
0x180016b79  retn
```
