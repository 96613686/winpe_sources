# DMCSP_DevDetail_GetVoLTEServiceSetting

- ea: `0x180008da0`
- end: `0x180008da9`
- name: `DMCSP_DevDetail_GetVoLTEServiceSetting`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall DMCSP_DevDetail_GetVoLTEServiceSetting(_DWORD *a1)
{
  *a1 = 0;
  return 0;
}

```

## disassembly

```asm
0x180008da0  mov     dword ptr [rcx], 0
0x180008da6  xor     eax, eax
0x180008da8  retn
```
