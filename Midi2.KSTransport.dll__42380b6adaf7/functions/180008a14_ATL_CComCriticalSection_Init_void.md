# ATL::CComCriticalSection::Init(void)

- ea: `0x180008a14`
- end: `0x180008a34`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002780`
- `0x180002820`
- `0x180002860`
- `0x1800028a0`
- `0x180007864`
- `0x180007974`
- `0x180007ab0`

## callees

- `0x180008a14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008a18`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180008a18`

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
0x180008a14  sub     rsp, 38h
0x180008a18  call    cs:__imp_InitializeCriticalSection
0x180008a1e  xor     eax, eax
0x180008a20  mov     [rsp+38h+var_18], eax
0x180008a24  jmp     short loc_180008A2F
0x180008a26  mov     eax, 8007000Eh
0x180008a2b  mov     [rsp+38h+var_18], eax
0x180008a2f  add     rsp, 38h
0x180008a33  retn
```
