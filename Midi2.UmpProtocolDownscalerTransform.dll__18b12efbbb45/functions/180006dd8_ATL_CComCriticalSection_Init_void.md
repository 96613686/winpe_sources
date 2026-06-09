# ATL::CComCriticalSection::Init(void)

- ea: `0x180006dd8`
- end: `0x180006df8`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001970`
- `0x180001a10`
- `0x180001a50`
- `0x180001a90`
- `0x180005d04`
- `0x180005e14`
- `0x180005f50`

## callees

- `0x180006dd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006ddc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006ddc`

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
0x180006dd8  sub     rsp, 38h
0x180006ddc  call    cs:__imp_InitializeCriticalSection
0x180006de2  xor     eax, eax
0x180006de4  mov     [rsp+38h+var_18], eax
0x180006de8  jmp     short loc_180006DF3
0x180006dea  mov     eax, 8007000Eh
0x180006def  mov     [rsp+38h+var_18], eax
0x180006df3  add     rsp, 38h
0x180006df7  retn
```
