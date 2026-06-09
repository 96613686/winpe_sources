# ATL::CComCriticalSection::Init(void)

- ea: `0x180005b68`
- end: `0x180005b88`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001900`
- `0x1800019a0`
- `0x1800019e0`
- `0x180001a20`
- `0x180004a94`
- `0x180004ba4`
- `0x180004ce0`

## callees

- `0x180005b68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005b6c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005b6c`

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
0x180005b68  sub     rsp, 38h
0x180005b6c  call    cs:__imp_InitializeCriticalSection
0x180005b72  xor     eax, eax
0x180005b74  mov     [rsp+38h+var_18], eax
0x180005b78  jmp     short loc_180005B83
0x180005b7a  mov     eax, 8007000Eh
0x180005b7f  mov     [rsp+38h+var_18], eax
0x180005b83  add     rsp, 38h
0x180005b87  retn
```
