# Microsoft::Bluetooth::Foundation::ComServiceModule::IncrementObjectCount(void)

- ea: `0x18000c850`
- end: `0x18000c867`
- name: `?IncrementObjectCount@ComServiceModule@Foundation@Bluetooth@Microsoft@@UEAAKXZ`
- size: `23`
- prototype: `unsigned int __fastcall(Microsoft::Bluetooth::Foundation::ComServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027b9c`

## callees

- `0x18000c850`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x18000c859`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x18000c860`

## pseudocode

```c
ULONG __fastcall Microsoft::Bluetooth::Foundation::ComServiceModule::IncrementObjectCount(
        Microsoft::Bluetooth::Foundation::ComServiceModule *this)
{
  if ( *((_BYTE *)this + 20) )
    return CoAddRefSharedService(*((unsigned int *)this + 4));
  else
    return CoAddRefServerProcess();
}

```

## disassembly

```asm
0x18000c850  cmp     byte ptr [rcx+14h], 0
0x18000c854  jz      short loc_18000C860
0x18000c856  mov     ecx, [rcx+10h]
0x18000c859  jmp     cs:__imp_CoAddRefSharedService
0x18000c860  jmp     cs:__imp_CoAddRefServerProcess
```
