# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x18001249c`
- end: `0x1800124ba`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180012420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124a8`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(__int64 a1)
{
  __int64 result; // rax

  EnterCriticalSection(*(LPCRITICAL_SECTION *)a1);
  result = 0;
  *(_BYTE *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x18001249c  push    rbx
0x18001249e  sub     rsp, 20h
0x1800124a2  mov     rbx, rcx
0x1800124a5  mov     rcx, [rcx]; lpCriticalSection
0x1800124a8  call    cs:__imp_EnterCriticalSection
0x1800124ae  xor     eax, eax
0x1800124b0  mov     byte ptr [rbx+8], 1
0x1800124b4  add     rsp, 20h
0x1800124b8  pop     rbx
0x1800124b9  retn
```
