# ATL::CComContainedObject<CBrowserCap>::GetControllingUnknown(void)

- ea: `0x180003ed0`
- end: `0x180003ed5`
- name: `?GetControllingUnknown@?$CComContainedObject@VCBrowserCap@@@ATL@@UEAAPEAUIUnknown@@XZ`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CBrowserCap>::GetControllingUnknown(__int64 a1)
{
  return *(_QWORD *)(a1 + 16);
}

```

## disassembly

```asm
0x180003ed0  mov     rax, [rcx+10h]
0x180003ed4  retn
```
