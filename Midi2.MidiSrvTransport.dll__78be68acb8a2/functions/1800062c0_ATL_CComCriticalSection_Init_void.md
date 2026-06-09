# ATL::CComCriticalSection::Init(void)

- ea: `0x1800062c0`
- end: `0x1800062e0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001e80`
- `0x180001f20`
- `0x180001f60`
- `0x180001fa0`
- `0x1800051e4`
- `0x1800052f4`
- `0x180005430`

## callees

- `0x1800062c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800062c4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800062c4`

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
0x1800062c0  sub     rsp, 38h
0x1800062c4  call    cs:__imp_InitializeCriticalSection
0x1800062ca  xor     eax, eax
0x1800062cc  mov     [rsp+38h+var_18], eax
0x1800062d0  jmp     short loc_1800062DB
0x1800062d2  mov     eax, 8007000Eh
0x1800062d7  mov     [rsp+38h+var_18], eax
0x1800062db  add     rsp, 38h
0x1800062df  retn
```
