# ATL::CComCriticalSection::Init(void)

- ea: `0x180004d6c`
- end: `0x180004d8c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001db0`
- `0x180001e00`
- `0x180001e40`
- `0x180001e70`
- `0x180004898`
- `0x180004a50`
- `0x18000637c`
- `0x18000669c`

## callees

- `0x180004d6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004d70`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180004d70`

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
0x180004d6c  sub     rsp, 38h
0x180004d70  call    cs:__imp_InitializeCriticalSection
0x180004d76  xor     eax, eax
0x180004d78  mov     [rsp+38h+var_18], eax
0x180004d7c  jmp     short loc_180004D87
0x180004d7e  mov     eax, 8007000Eh
0x180004d83  mov     [rsp+38h+var_18], eax
0x180004d87  add     rsp, 38h
0x180004d8b  retn
```
