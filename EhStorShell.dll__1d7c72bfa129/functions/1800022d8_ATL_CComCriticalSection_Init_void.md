# ATL::CComCriticalSection::Init(void)

- ea: `0x1800022d8`
- end: `0x1800022f8`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001e20`
- `0x180001f40`
- `0x180002130`
- `0x1800021c0`

## callees

- `0x1800022d8`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800022dc`
- `KERNEL32!InitializeCriticalSection` at `0x1800022dc`

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
0x1800022d8  sub     rsp, 38h
0x1800022dc  call    cs:__imp_InitializeCriticalSection
0x1800022e2  xor     eax, eax
0x1800022e4  mov     [rsp+38h+var_18], eax
0x1800022e8  jmp     short loc_1800022F3
0x1800022ea  mov     eax, 8007000Eh
0x1800022ef  mov     [rsp+38h+var_18], eax
0x1800022f3  add     rsp, 38h
0x1800022f7  retn
```
