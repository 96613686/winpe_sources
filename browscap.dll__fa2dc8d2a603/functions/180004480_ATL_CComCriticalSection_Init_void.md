# ATL::CComCriticalSection::Init(void)

- ea: `0x180004480`
- end: `0x1800044a0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001130`
- `0x180001170`
- `0x1800011a0`
- `0x1800011e0`
- `0x1800039c4`
- `0x180003b20`
- `0x180003c50`
- `0x18000672c`
- `0x180006b14`
- `0x180007358`
- `0x180009e8c`

## callees

- `0x180004480`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004484`
- `KERNEL32!InitializeCriticalSection` at `0x180004484`

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
0x180004480  sub     rsp, 38h
0x180004484  call    cs:__imp_InitializeCriticalSection
0x18000448a  xor     eax, eax
0x18000448c  mov     [rsp+38h+var_18], eax
0x180004490  jmp     short loc_18000449B
0x180004492  mov     eax, 8007000Eh
0x180004497  mov     [rsp+38h+var_18], eax
0x18000449b  add     rsp, 38h
0x18000449f  retn
```
