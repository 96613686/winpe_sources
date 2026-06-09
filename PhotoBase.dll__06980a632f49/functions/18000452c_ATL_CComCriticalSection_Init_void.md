# ATL::CComCriticalSection::Init(void)

- ea: `0x18000452c`
- end: `0x18000454c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002a24`

## callees

- `0x18000452c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004530`
- `KERNEL32!InitializeCriticalSection` at `0x180004530`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x18000452c  sub     rsp, 38h
0x180004530  call    cs:__imp_InitializeCriticalSection
0x180004536  xor     eax, eax
0x180004538  mov     [rsp+38h+var_18], eax
0x18000453c  jmp     short loc_180004547
0x18000453e  mov     eax, 8007000Eh
0x180004543  mov     [rsp+38h+var_18], eax
0x180004547  add     rsp, 38h
0x18000454b  retn
```
