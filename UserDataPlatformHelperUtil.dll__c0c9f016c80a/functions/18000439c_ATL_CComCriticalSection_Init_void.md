# ATL::CComCriticalSection::Init(void)

- ea: `0x18000439c`
- end: `0x1800043bc`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010f0`
- `0x180004180`
- `0x180006790`

## callees

- `0x18000439c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800043a0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800043a0`

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
0x18000439c  sub     rsp, 38h
0x1800043a0  call    cs:__imp_InitializeCriticalSection
0x1800043a6  xor     eax, eax
0x1800043a8  mov     [rsp+38h+var_18], eax
0x1800043ac  jmp     short loc_1800043B7
0x1800043ae  mov     eax, 8007000Eh
0x1800043b3  mov     [rsp+38h+var_18], eax
0x1800043b7  add     rsp, 38h
0x1800043bb  retn
0x18000a56a  push    rbp
0x18000a56c  sub     rsp, 20h
0x18000a570  mov     rbp, rdx
0x18000a573  mov     rax, [rcx]
0x18000a576  xor     ecx, ecx
0x18000a578  cmp     dword ptr [rax], 0C0000017h
0x18000a57e  setz    cl
0x18000a581  mov     eax, ecx
0x18000a583  add     rsp, 20h
0x18000a587  pop     rbp
0x18000a588  retn
```
