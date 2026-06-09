# ATL::CComCriticalSection::Init(void)

- ea: `0x14000bd38`
- end: `0x14000bd58`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001de0`
- `0x140001e10`

## callees

- `0x14000bd38`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000bd3c`
- `KERNEL32!InitializeCriticalSection` at `0x14000bd3c`

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
0x14000bd38  sub     rsp, 38h
0x14000bd3c  call    cs:__imp_InitializeCriticalSection
0x14000bd42  xor     eax, eax
0x14000bd44  mov     [rsp+38h+var_18], eax
0x14000bd48  jmp     short loc_14000BD53
0x14000bd4a  mov     eax, 8007000Eh
0x14000bd4f  mov     [rsp+38h+var_18], eax
0x14000bd53  add     rsp, 38h
0x14000bd57  retn
0x140015c86  push    rbp
0x140015c88  sub     rsp, 20h
0x140015c8c  mov     rbp, rdx
0x140015c8f  mov     rax, [rcx]
0x140015c92  xor     ecx, ecx
0x140015c94  cmp     dword ptr [rax], 0C0000017h
0x140015c9a  setz    cl
0x140015c9d  mov     eax, ecx
0x140015c9f  add     rsp, 20h
0x140015ca3  pop     rbp
0x140015ca4  retn
```
