# ATL::CComCriticalSection::Init(void)

- ea: `0x1800084d8`
- end: `0x1800084f8`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002520`
- `0x180002650`
- `0x180002690`
- `0x1800026d0`
- `0x1800073e4`
- `0x180007504`
- `0x180007650`

## callees

- `0x1800084d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800084dc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800084dc`

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
0x1800084d8  sub     rsp, 38h
0x1800084dc  call    cs:__imp_InitializeCriticalSection
0x1800084e2  xor     eax, eax
0x1800084e4  mov     [rsp+38h+var_18], eax
0x1800084e8  jmp     short loc_1800084F3
0x1800084ea  mov     eax, 8007000Eh
0x1800084ef  mov     [rsp+38h+var_18], eax
0x1800084f3  add     rsp, 38h
0x1800084f7  retn
```
