# ATL::CComCriticalSection::Init(void)

- ea: `0x140005dec`
- end: `0x140005e0c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001920`
- `0x140005c30`
- `0x1400069e8`

## callees

- `0x140005dec`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x140005df0`
- `KERNEL32!InitializeCriticalSection` at `0x140005df0`

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
0x140005dec  sub     rsp, 38h
0x140005df0  call    cs:__imp_InitializeCriticalSection
0x140005df6  xor     eax, eax
0x140005df8  mov     [rsp+38h+var_18], eax
0x140005dfc  jmp     short loc_140005E07
0x140005dfe  mov     eax, 8007000Eh
0x140005e03  mov     [rsp+38h+var_18], eax
0x140005e07  add     rsp, 38h
0x140005e0b  retn
0x14000781e  push    rbp
0x140007820  sub     rsp, 20h
0x140007824  mov     rbp, rdx
0x140007827  mov     rax, [rcx]
0x14000782a  xor     ecx, ecx
0x14000782c  cmp     dword ptr [rax], 0C0000017h
0x140007832  setz    cl
0x140007835  mov     eax, ecx
0x140007837  add     rsp, 20h
0x14000783b  pop     rbp
0x14000783c  retn
```
