# NaturalAuthServiceModule::IncrementObjectCount(void)

- ea: `0x180008420`
- end: `0x18000842a`
- name: `?IncrementObjectCount@NaturalAuthServiceModule@@UEAAKXZ`
- size: `10`
- prototype: `unsigned int __fastcall(NaturalAuthServiceModule *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x180008423`

## pseudocode

```c
__int64 __fastcall NaturalAuthServiceModule::IncrementObjectCount(NaturalAuthServiceModule *this)
{
  return CoAddRefSharedService(*((unsigned int *)this + 4));
}

```

## disassembly

```asm
0x180008420  mov     ecx, [rcx+10h]
0x180008423  jmp     cs:__imp_CoAddRefSharedService
```
