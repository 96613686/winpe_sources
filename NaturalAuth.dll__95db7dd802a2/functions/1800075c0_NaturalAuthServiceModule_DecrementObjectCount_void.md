# NaturalAuthServiceModule::DecrementObjectCount(void)

- ea: `0x1800075c0`
- end: `0x1800075ca`
- name: `?DecrementObjectCount@NaturalAuthServiceModule@@UEAAKXZ`
- size: `10`
- prototype: `unsigned int __fastcall(NaturalAuthServiceModule *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x1800075c3`

## pseudocode

```c
__int64 __fastcall NaturalAuthServiceModule::DecrementObjectCount(NaturalAuthServiceModule *this)
{
  return CoReleaseSharedService(*((unsigned int *)this + 4));
}

```

## disassembly

```asm
0x1800075c0  mov     ecx, [rcx+10h]
0x1800075c3  jmp     cs:__imp_CoReleaseSharedService
```
