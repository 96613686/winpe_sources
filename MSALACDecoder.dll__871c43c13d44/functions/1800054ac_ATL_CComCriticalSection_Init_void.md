# ATL::CComCriticalSection::Init(void)

- ea: `0x1800054ac`
- end: `0x1800054cc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001060`
- `0x1800010a0`
- `0x1800010d0`
- `0x1800051b0`
- `0x180006bcc`
- `0x180006ef4`

## callees

- `0x1800054ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800054b0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800054b0`

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
0x1800054ac  sub     rsp, 38h
0x1800054b0  call    cs:__imp_InitializeCriticalSection
0x1800054b6  xor     eax, eax
0x1800054b8  mov     [rsp+38h+var_18], eax
0x1800054bc  jmp     short loc_1800054C7
0x1800054be  mov     eax, 8007000Eh
0x1800054c3  mov     [rsp+38h+var_18], eax
0x1800054c7  add     rsp, 38h
0x1800054cb  retn
```
