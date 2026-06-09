# WaasMedic::CBSHandler::ResolveSource(ushort const *,ICbsIdentity *,ushort const *,ushort * *,int *)

- ea: `0x18000a460`
- end: `0x18000a47a`
- name: `?ResolveSource@CBSHandler@WaasMedic@@UEAAJPEBGPEAUICbsIdentity@@0PEAPEAGPEAH@Z`
- size: `26`
- prototype: `__int64 __fastcall(WaasMedic::CBSHandler *__hidden this, const unsigned __int16 *, struct ICbsIdentity *, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, installer_update`

## pseudocode

```c
__int64 __fastcall WaasMedic::CBSHandler::ResolveSource(
        WaasMedic::CBSHandler *this,
        const unsigned __int16 *a2,
        struct ICbsIdentity *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5,
        int *a6)
{
  *a5 = 0;
  *a6 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000a460  mov     rax, [rsp+arg_20]
0x18000a465  mov     qword ptr [rax], 0
0x18000a46c  mov     rax, [rsp+arg_28]
0x18000a471  mov     dword ptr [rax], 1
0x18000a477  xor     eax, eax
0x18000a479  retn
```
