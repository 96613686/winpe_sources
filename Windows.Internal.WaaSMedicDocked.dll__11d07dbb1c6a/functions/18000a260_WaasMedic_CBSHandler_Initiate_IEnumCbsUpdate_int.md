# WaasMedic::CBSHandler::Initiate(IEnumCbsUpdate *,int *)

- ea: `0x18000a260`
- end: `0x18000a26a`
- name: `?Initiate@CBSHandler@WaasMedic@@UEAAJPEAUIEnumCbsUpdate@@PEAH@Z`
- size: `10`
- prototype: `__int64 __fastcall(WaasMedic::CBSHandler *__hidden this, struct IEnumCbsUpdate *, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## pseudocode

```c
__int64 __fastcall WaasMedic::CBSHandler::Initiate(WaasMedic::CBSHandler *this, struct IEnumCbsUpdate *a2, int *a3)
{
  *a3 = 1;
  return 0;
}

```

## disassembly

```asm
0x18000a260  mov     dword ptr [r8], 1
0x18000a267  xor     eax, eax
0x18000a269  retn
```
