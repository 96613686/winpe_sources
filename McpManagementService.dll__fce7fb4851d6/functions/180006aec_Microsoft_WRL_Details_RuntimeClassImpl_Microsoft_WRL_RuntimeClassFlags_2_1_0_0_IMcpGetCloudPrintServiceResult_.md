# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>(void)

- ea: `0x180006aec`
- end: `0x180006af7`
- name: `??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMcpGetCloudPrintServiceResult@@UIFastRundown@@@Details@WRL@Microsoft@@IEAA@XZ`
- size: `11`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005714`
- `0x1800216b0`
- `0x1800217bc`
- `0x1800221bc`
- `0x180022b58`
- `0x1800238cc`
- `0x1800249a8`
- `0x180025540`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMcpGetCloudPrintServiceResult,IFastRundown>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 20) = 1;
  return a1;
}

```

## disassembly

```asm
0x180006aec  mov     dword ptr [rcx+14h], 1
0x180006af3  mov     rax, rcx
0x180006af6  retn
```
