# ATL::CComCriticalSection::Init(void)

- ea: `0x1800057a0`
- end: `0x1800057c0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800030b0`

## callees

- `0x1800057a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800057a4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800057a4`

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
0x1800057a0  sub     rsp, 38h
0x1800057a4  call    cs:__imp_InitializeCriticalSection
0x1800057aa  xor     eax, eax
0x1800057ac  mov     [rsp+38h+var_18], eax
0x1800057b0  jmp     short loc_1800057BB
0x1800057b2  mov     eax, 8007000Eh
0x1800057b7  mov     [rsp+38h+var_18], eax
0x1800057bb  add     rsp, 38h
0x1800057bf  retn
0x180013c56  push    rbp
0x180013c58  sub     rsp, 20h
0x180013c5c  mov     rbp, rdx
0x180013c5f  mov     rax, [rcx]
0x180013c62  xor     ecx, ecx
0x180013c64  cmp     dword ptr [rax], 0C0000017h
0x180013c6a  setz    cl
0x180013c6d  mov     eax, ecx
0x180013c6f  add     rsp, 20h
0x180013c73  pop     rbp
0x180013c74  retn
```
