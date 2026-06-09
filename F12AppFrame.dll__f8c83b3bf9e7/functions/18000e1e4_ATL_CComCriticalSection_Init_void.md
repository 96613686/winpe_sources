# ATL::CComCriticalSection::Init(void)

- ea: `0x18000e1e4`
- end: `0x18000e204`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800011d0`
- `0x180001200`
- `0x180001240`
- `0x180001280`
- `0x1800012e0`
- `0x180001340`
- `0x18000c64c`
- `0x18000c9e4`
- `0x180013eb8`
- `0x180013fc0`
- `0x180021680`
- `0x180031a20`

## callees

- `0x18000e1e4`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000e1e8`
- `KERNEL32!InitializeCriticalSection` at `0x18000e1e8`

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
0x18000e1e4  sub     rsp, 38h
0x18000e1e8  call    cs:__imp_InitializeCriticalSection
0x18000e1ee  xor     eax, eax
0x18000e1f0  mov     [rsp+38h+var_18], eax
0x18000e1f4  jmp     short loc_18000E1FF
0x18000e1f6  mov     eax, 8007000Eh
0x18000e1fb  mov     [rsp+38h+var_18], eax
0x18000e1ff  add     rsp, 38h
0x18000e203  retn
```
