# ATL::CComCriticalSection::Init(void)

- ea: `0x180002960`
- end: `0x180002980`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001e88`
- `0x180001f04`
- `0x180001f70`
- `0x180001ff8`
- `0x1800026f0`
- `0x180002800`
- `0x180002830`

## callees

- `0x180002960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002964`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002964`

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
0x180002960  sub     rsp, 38h
0x180002964  call    cs:__imp_InitializeCriticalSection
0x18000296a  xor     eax, eax
0x18000296c  mov     [rsp+38h+var_18], eax
0x180002970  jmp     short loc_18000297B
0x180002972  mov     eax, 8007000Eh
0x180002977  mov     [rsp+38h+var_18], eax
0x18000297b  add     rsp, 38h
0x18000297f  retn
```
