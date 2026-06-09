# ATL::CComCriticalSection::Init(void)

- ea: `0x180005d08`
- end: `0x180005d28`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001a90`
- `0x180001b30`
- `0x180001b70`
- `0x180001bb0`
- `0x180004c34`
- `0x180004d44`
- `0x180004e80`

## callees

- `0x180005d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005d0c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005d0c`

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
0x180005d08  sub     rsp, 38h
0x180005d0c  call    cs:__imp_InitializeCriticalSection
0x180005d12  xor     eax, eax
0x180005d14  mov     [rsp+38h+var_18], eax
0x180005d18  jmp     short loc_180005D23
0x180005d1a  mov     eax, 8007000Eh
0x180005d1f  mov     [rsp+38h+var_18], eax
0x180005d23  add     rsp, 38h
0x180005d27  retn
```
