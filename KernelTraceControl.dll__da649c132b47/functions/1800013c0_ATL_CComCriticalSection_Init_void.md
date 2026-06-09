# ATL::CComCriticalSection::Init(void)

- ea: `0x1800013c0`
- end: `0x1800013e0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001000`
- `0x1800010c0`
- `0x180001270`
- `0x180001310`

## callees

- `0x1800013c0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800013c4`
- `KERNEL32!InitializeCriticalSection` at `0x1800013c4`

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
0x1800013c0  sub     rsp, 38h
0x1800013c4  call    cs:__imp_InitializeCriticalSection
0x1800013ca  xor     eax, eax
0x1800013cc  mov     [rsp+38h+var_18], eax
0x1800013d0  jmp     short loc_1800013DB
0x1800013d2  mov     eax, 8007000Eh
0x1800013d7  mov     [rsp+38h+var_18], eax
0x1800013db  add     rsp, 38h
0x1800013df  retn
0x180027a30  push    rbp
0x180027a32  sub     rsp, 20h
0x180027a36  mov     rbp, rdx
0x180027a39  mov     rax, [rcx]
0x180027a3c  xor     ecx, ecx
0x180027a3e  cmp     dword ptr [rax], 0C0000017h
0x180027a44  setz    cl
0x180027a47  mov     eax, ecx
0x180027a49  add     rsp, 20h
0x180027a4d  pop     rbp
0x180027a4e  retn
```
