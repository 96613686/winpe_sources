# AuthHostWebInstance::QueryCustomPolicy(IUri *,_GUID const &,uchar * *,ulong *,uchar *,ulong)

- ea: `0x140011180`
- end: `0x140011213`
- name: `?QueryCustomPolicy@AuthHostWebInstance@@UEAAJPEAUIUri@@AEBU_GUID@@PEAPEAEPEAKPEAEK@Z`
- size: `147`
- prototype: `int(AuthHostWebInstance *__hidden this, struct IUri *, const struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140005770`

## callees

- `0x140011180`
- `0x14001121c`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400111fb`
- `OLEAUT32!__imp_SysFreeString` at `0x1400111fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::QueryCustomPolicy(
        AuthHostWebInstance *this,
        struct IUri *a2,
        const struct _GUID *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        IID *rclsid,
        unsigned int a7)
{
  const unsigned __int16 *v9; // rbx
  unsigned int CustomPolicyInternal; // ebx
  BSTR bstrString; // [rsp+50h] [rbp+8h] BYREF

  bstrString = 0;
  v9 = 0;
  if ( a2 && ((int (__fastcall *)(struct IUri *, BSTR *))a2->lpVtbl->GetAbsoluteUri)(a2, &bstrString) >= 0 )
    v9 = bstrString;
  CustomPolicyInternal = AuthHostWebInstance::QueryCustomPolicyInternal(this, v9, a3, a4, a5, rclsid, a7);
  SysFreeString(bstrString);
  return CustomPolicyInternal;
}

```

## disassembly

```asm
0x140011180  mov     r11, rsp
0x140011183  mov     [r11+10h], rbx
0x140011187  mov     [r11+18h], rsi
0x14001118b  mov     [r11+8], rcx
0x14001118f  push    rdi
0x140011190  sub     rsp, 40h
0x140011194  mov     rdi, r9
0x140011197  mov     rsi, r8
0x14001119a  mov     r10, rdx
0x14001119d  mov     qword ptr [r11+8], 0
0x1400111a5  xor     ebx, ebx
0x1400111a7  test    rdx, rdx
0x1400111aa  jz      short loc_1400111C7
0x1400111ac  mov     rax, [rdx]
0x1400111af  lea     rdx, [r11+8]
0x1400111b3  mov     rcx, r10
0x1400111b6  mov     rax, [rax+38h]
0x1400111ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400111bf  test    eax, eax
0x1400111c1  cmovns  rbx, [rsp+48h+bstrString]
0x1400111c7  mov     eax, [rsp+48h+arg_30]
0x1400111ce  mov     [rsp+48h+var_18], eax; unsigned int
0x1400111d2  mov     rax, [rsp+48h+arg_28]
0x1400111d7  mov     [rsp+48h+rclsid], rax; rclsid
0x1400111dc  mov     rax, [rsp+48h+arg_20]
0x1400111e1  mov     [rsp+48h+var_28], rax; unsigned int *
0x1400111e6  mov     r9, rdi; unsigned __int8 **
0x1400111e9  mov     r8, rsi; struct _GUID *
0x1400111ec  mov     rdx, rbx; unsigned __int16 *
0x1400111ef  call    ?QueryCustomPolicyInternal@AuthHostWebInstance@@AEAAJPEBGAEBU_GUID@@PEAPEAEPEAKPEAEK@Z; AuthHostWebInstance::QueryCustomPolicyInternal(ushort const *,_GUID const &,uchar * *,ulong *,uchar *,ulong)
0x1400111f4  mov     ebx, eax
0x1400111f6  mov     rcx, [rsp+48h+bstrString]; bstrString
0x1400111fb  call    cs:__imp_SysFreeString
0x140011201  mov     eax, ebx
0x140011203  mov     rbx, [rsp+48h+arg_8]
0x140011208  mov     rsi, [rsp+48h+arg_10]
0x14001120d  add     rsp, 40h
0x140011211  pop     rdi
0x140011212  retn
```
