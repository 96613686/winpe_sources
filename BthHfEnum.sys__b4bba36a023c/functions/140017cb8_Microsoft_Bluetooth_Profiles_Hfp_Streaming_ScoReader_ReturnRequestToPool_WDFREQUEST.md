# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::ReturnRequestToPool(WDFREQUEST__ *)

- ea: `0x140017cb8`
- end: `0x140017cdf`
- name: `?ReturnRequestToPool@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@SAXPEAUWDFREQUEST__@@@Z`
- size: `39`
- prototype: `void __fastcall(struct WDFREQUEST__ *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002db70`
- `0x14002f2f4`

## callees

- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::ReturnRequestToPool(struct WDFREQUEST__ *a1)
{
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *))(WdfFunctions_01015 + 1664))(WdfDriverGlobals, a1);
}

```

## disassembly

```asm
0x140017cb8  sub     rsp, 28h
0x140017cbc  mov     rax, cs:WdfFunctions_01015
0x140017cc3  mov     rdx, rcx
0x140017cc6  mov     rcx, cs:WdfDriverGlobals
0x140017ccd  mov     rax, [rax+680h]
0x140017cd4  call    _guard_dispatch_icall
0x140017cd9  add     rsp, 28h
0x140017cdd  retn
```
