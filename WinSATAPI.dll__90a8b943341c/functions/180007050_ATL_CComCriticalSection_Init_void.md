# ATL::CComCriticalSection::Init(void)

- ea: `0x180007050`
- end: `0x180007077`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001060`
- `0x1800010a0`
- `0x180006aa0`
- `0x180006bd0`
- `0x180006f30`
- `0x18000ebdc`

## callees

- `0x180007050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007054`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007054`

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
0x180007050  sub     rsp, 38h
0x180007054  call    cs:__imp_InitializeCriticalSection
0x18000705b  nop     dword ptr [rax+rax+00h]
0x180007060  xor     eax, eax
0x180007062  mov     [rsp+38h+var_18], eax
0x180007066  jmp     short loc_180007071
0x180007068  mov     eax, 8007000Eh
0x18000706d  mov     [rsp+38h+var_18], eax
0x180007071  add     rsp, 38h
0x180007075  retn
```
