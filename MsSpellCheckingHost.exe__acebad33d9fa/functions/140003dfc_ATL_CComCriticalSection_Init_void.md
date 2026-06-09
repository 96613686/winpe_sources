# ATL::CComCriticalSection::Init(void)

- ea: `0x140003dfc`
- end: `0x140003e1c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001070`
- `0x140001430`
- `0x140001470`
- `0x1400014b0`
- `0x140005f04`
- `0x140009b40`
- `0x140010440`

## callees

- `0x140003dfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140003e00`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140003e00`

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
0x140003dfc  sub     rsp, 38h
0x140003e00  call    cs:__imp_InitializeCriticalSection
0x140003e06  xor     eax, eax
0x140003e08  mov     [rsp+38h+var_18], eax
0x140003e0c  jmp     short loc_140003E17
0x140003e0e  mov     eax, 8007000Eh
0x140003e13  mov     [rsp+38h+var_18], eax
0x140003e17  add     rsp, 38h
0x140003e1b  retn
```
