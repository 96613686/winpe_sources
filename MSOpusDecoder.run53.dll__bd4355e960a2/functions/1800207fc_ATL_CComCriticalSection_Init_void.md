# ATL::CComCriticalSection::Init(void)

- ea: `0x1800207fc`
- end: `0x18002081c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001300`
- `0x180001350`
- `0x180001390`
- `0x1800013c0`
- `0x180020500`
- `0x180021f9c`
- `0x1800222c4`

## callees

- `0x1800207fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020800`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180020800`

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
0x1800207fc  sub     rsp, 38h
0x180020800  call    cs:__imp_InitializeCriticalSection
0x180020806  xor     eax, eax
0x180020808  mov     [rsp+38h+var_18], eax
0x18002080c  jmp     short loc_180020817
0x18002080e  mov     eax, 8007000Eh
0x180020813  mov     [rsp+38h+var_18], eax
0x180020817  add     rsp, 38h
0x18002081b  retn
```
