# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>(void)

- ea: `0x1400071f4`
- end: `0x1400071ff`
- name: `??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UICreateObject@@@Details@WRL@Microsoft@@IEAA@XZ`
- size: `11`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000622c`
- `0x140006680`
- `0x1400071d0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ICreateObject>(
        __int64 a1)
{
  *(_DWORD *)(a1 + 12) = 1;
  return a1;
}

```

## disassembly

```asm
0x1400071f4  mov     dword ptr [rcx+0Ch], 1
0x1400071fb  mov     rax, rcx
0x1400071fe  retn
```
