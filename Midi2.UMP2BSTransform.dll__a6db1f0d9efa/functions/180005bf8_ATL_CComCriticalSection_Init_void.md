# ATL::CComCriticalSection::Init(void)

- ea: `0x180005bf8`
- end: `0x180005c18`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001900`
- `0x180001a30`
- `0x180001a70`
- `0x180001ab0`
- `0x180004b24`
- `0x180004c34`
- `0x180004d70`

## callees

- `0x180005bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005bfc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180005bfc`

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
0x180005bf8  sub     rsp, 38h
0x180005bfc  call    cs:__imp_InitializeCriticalSection
0x180005c02  xor     eax, eax
0x180005c04  mov     [rsp+38h+var_18], eax
0x180005c08  jmp     short loc_180005C13
0x180005c0a  mov     eax, 8007000Eh
0x180005c0f  mov     [rsp+38h+var_18], eax
0x180005c13  add     rsp, 38h
0x180005c17  retn
```
