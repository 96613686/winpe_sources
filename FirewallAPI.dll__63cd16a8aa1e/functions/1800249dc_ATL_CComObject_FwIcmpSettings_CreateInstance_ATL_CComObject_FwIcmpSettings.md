# ATL::CComObject<FwIcmpSettings>::CreateInstance(ATL::CComObject<FwIcmpSettings> * *)

- ea: `0x1800249dc`
- end: `0x180024aa9`
- name: `?CreateInstance@?$CComObject@VFwIcmpSettings@@@ATL@@SAJPEAPEAV12@@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002d04`

## callees

- `0x1800249dc`
- `0x180027d40`
- `0x1800284c4`
- `0x18005e010`

## import_xrefs

- `FWPolicyIOMgr!CopyIcmpSettings` at `0x180024a35`
- `FWPolicyIOMgr!CopyIcmpSettings` at `0x180024a35`
- `FWPolicyIOMgr!CopyIcmpV4Rules` at `0x180024a42`
- `FWPolicyIOMgr!CopyIcmpV4Rules` at `0x180024a42`
- `FWPolicyIOMgr!CopyIcmpV6Rules` at `0x180024a4f`
- `FWPolicyIOMgr!CopyIcmpV6Rules` at `0x180024a4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<FwIcmpSettings>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // rdi
  _QWORD *v3; // r14
  unsigned int v4; // esi
  _QWORD *v6; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v4 = -2147024882;
    v3 = operator new(0x3B8u);
    memset_0(v3, 0, 0x3B8u);
    CopyIcmpSettings((struct FW_ICMP_SETTING_ *)((char *)v3 + 28));
    CopyIcmpV4Rules((struct FW_ICMP_RULE_ *)(v3 + 59));
    CopyIcmpV6Rules((struct FW_ICMP_RULE_ *)(v3 + 95));
    _InterlockedIncrement((_DWORD *)&qword_180098028 + 1);
    *v3 = &ATL::CComObject<FwIcmpSettings>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v6 = v3;
  }
  catch ( ... )
  {
    v1 = a1;
    v4 = -2147024882;
    v3 = v6;
  }
  if ( v3 )
    v4 = 0;
  *v1 = v3;
  return v4;
}

```

## disassembly

```asm
0x1800249dc  mov     [rsp+arg_18], rbx
0x1800249e1  mov     [rsp+arg_0], rcx
0x1800249e6  push    rsi
0x1800249e7  push    rdi
0x1800249e8  push    r14
0x1800249ea  sub     rsp, 20h
0x1800249ee  mov     rdi, rcx
0x1800249f1  xor     ebx, ebx
0x1800249f3  test    rcx, rcx
0x1800249f6  jnz     short loc_180024A02
0x1800249f8  mov     eax, 80004003h
0x1800249fd  jmp     loc_180024A9B
0x180024a02  mov     [rcx], rbx
0x180024a05  mov     esi, 8007000Eh
0x180024a0a  mov     [rsp+38h+arg_8], esi
0x180024a0e  mov     [rsp+38h+arg_10], rbx
0x180024a13  mov     ecx, 3B8h; Size
0x180024a18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024a1d  mov     r14, rax
0x180024a20  xor     edx, edx; Val
0x180024a22  mov     r8d, 3B8h; Size
0x180024a28  mov     rcx, rax; void *
0x180024a2b  call    memset_0
0x180024a30  nop
0x180024a31  lea     rcx, [r14+1Ch]
0x180024a35  call    cs:__imp_?CopyIcmpSettings@@YAXPEAUFW_ICMP_SETTING_@@@Z; CopyIcmpSettings(FW_ICMP_SETTING_ *)
0x180024a3b  lea     rcx, [r14+1D8h]
0x180024a42  call    cs:__imp_?CopyIcmpV4Rules@@YAXPEAUFW_ICMP_RULE_@@@Z; CopyIcmpV4Rules(FW_ICMP_RULE_ *)
0x180024a48  lea     rcx, [r14+2F8h]
0x180024a4f  call    cs:__imp_?CopyIcmpV6Rules@@YAXPEAUFW_ICMP_RULE_@@@Z; CopyIcmpV6Rules(FW_ICMP_RULE_ *)
0x180024a55  lock inc dword ptr cs:qword_180098028+4
0x180024a5c  lea     rax, ??_7?$CComObject@VFwIcmpSettings@@@ATL@@6B@; const ATL::CComObject<FwIcmpSettings>::`vftable'
0x180024a63  mov     [r14], rax
0x180024a66  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180024a6d  mov     rax, [rcx]
0x180024a70  mov     rax, [rax+8]
0x180024a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a79  mov     [rsp+38h+arg_10], r14
0x180024a7e  jmp     short loc_180024A90
0x180024a80  xor     ebx, ebx
0x180024a82  mov     rdi, [rsp+38h+arg_0]
0x180024a87  mov     esi, [rsp+38h+arg_8]
0x180024a8b  mov     r14, [rsp+38h+arg_10]
0x180024a90  test    r14, r14
0x180024a93  cmovnz  esi, ebx
0x180024a96  mov     [rdi], r14
0x180024a99  mov     eax, esi
0x180024a9b  mov     rbx, [rsp+38h+arg_18]
0x180024aa0  add     rsp, 20h
0x180024aa4  pop     r14
0x180024aa6  pop     rdi
0x180024aa7  pop     rsi
0x180024aa8  retn
```
