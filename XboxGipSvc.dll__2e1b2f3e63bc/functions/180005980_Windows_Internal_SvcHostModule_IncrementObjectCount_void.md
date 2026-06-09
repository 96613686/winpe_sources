# Windows::Internal::SvcHostModule::IncrementObjectCount(void)

- ea: `0x180005980`
- end: `0x18000598a`
- name: `?IncrementObjectCount@SvcHostModule@Internal@Windows@@UEAAKXZ`
- size: `10`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005990`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x180005983`

## pseudocode

```c
__int64 __fastcall Windows::Internal::SvcHostModule::IncrementObjectCount(Windows::Internal::SvcHostModule *this)
{
  return CoAddRefSharedService(*((unsigned int *)this + 14));
}

```

## disassembly

```asm
0x180005980  mov     ecx, [rcx+38h]
0x180005983  jmp     cs:__imp_CoAddRefSharedService
```
