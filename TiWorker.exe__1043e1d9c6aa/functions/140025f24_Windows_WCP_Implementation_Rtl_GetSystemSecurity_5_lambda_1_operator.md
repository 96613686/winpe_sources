# _Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()

- ea: `0x140025f24`
- end: `0x140025f74`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()`
- size: `80`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400269f0`

## callees

- `0x140025f24`
- `0x140026840`
- `0x140026ad4`

## pseudocode

```c
PVOID *__fastcall Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_lambda_1_::operator()(
        __int64 a1,
        struct _SID **a2)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  void *v5; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  *(_OWORD *)&P = 0;
  dword_140053790 = Windows::WCP::Implementation::Rtl::GetSystemSid((Windows::WCP::Implementation::Rtl *)&v5, a2);
  if ( dword_140053790 >= 0 )
    dword_140053790 = Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(v3, v2, v5, v5);
  return &P;
}

```

## disassembly

```asm
0x140025f24  mov     [rsp+arg_8], rdx
0x140025f29  sub     rsp, 48h
0x140025f2d  xorps   xmm0, xmm0
0x140025f30  mov     [rsp+48h+arg_8], 0
0x140025f39  lea     rcx, [rsp+48h+arg_8]; this
0x140025f3e  movdqu  cs:P, xmm0
0x140025f46  call    ?GetSystemSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSid(_SID * *)
0x140025f4b  mov     cs:dword_140053790, eax
0x140025f51  test    eax, eax
0x140025f53  js      short loc_140025F68
0x140025f55  mov     r8, [rsp+48h+arg_8]
0x140025f5a  mov     r9, r8
0x140025f5d  call    ?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z; Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)
0x140025f62  mov     cs:dword_140053790, eax
0x140025f68  lea     rax, P
0x140025f6f  add     rsp, 48h
0x140025f73  retn
```
