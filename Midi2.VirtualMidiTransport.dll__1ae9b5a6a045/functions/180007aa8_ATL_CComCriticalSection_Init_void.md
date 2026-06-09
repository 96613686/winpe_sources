# ATL::CComCriticalSection::Init(void)

- ea: `0x180007aa8`
- end: `0x180007ac8`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001db0`
- `0x180001ee0`
- `0x180001f20`
- `0x180001f60`
- `0x1800069d4`
- `0x180006ae4`
- `0x180006c20`

## callees

- `0x180007aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007aac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007aac`

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
0x180007aa8  sub     rsp, 38h
0x180007aac  call    cs:__imp_InitializeCriticalSection
0x180007ab2  xor     eax, eax
0x180007ab4  mov     [rsp+38h+var_18], eax
0x180007ab8  jmp     short loc_180007AC3
0x180007aba  mov     eax, 8007000Eh
0x180007abf  mov     [rsp+38h+var_18], eax
0x180007ac3  add     rsp, 38h
0x180007ac7  retn
```
