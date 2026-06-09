# CComInit::~CComInit(void)

- ea: `0x180002fa0`
- end: `0x180002fc0`
- name: `??1CComInit@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(CComInit *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ae9c`

## callees

- `0x180002fa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002fae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180002fae`

## pseudocode

```c
void __fastcall CComInit::~CComInit(CComInit *this)
{
  if ( *(_DWORD *)this )
  {
    CoUninitialize();
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180002fa0  push    rbx
0x180002fa2  sub     rsp, 20h
0x180002fa6  cmp     dword ptr [rcx], 0
0x180002fa9  mov     rbx, rcx
0x180002fac  jz      short loc_180002FBA
0x180002fae  call    cs:__imp_CoUninitialize
0x180002fb4  mov     dword ptr [rbx], 0
0x180002fba  add     rsp, 20h
0x180002fbe  pop     rbx
0x180002fbf  retn
```
