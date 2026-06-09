# ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)

- ea: `0x140007900`
- end: `0x14000791e`
- name: `?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140004e94`
- `0x1400069fc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000790c`
- `KERNEL32!EnterCriticalSection` at `0x14000790c`

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
0x140007900  push    rbx
0x140007902  sub     rsp, 20h
0x140007906  mov     rbx, rcx
0x140007909  mov     rcx, [rcx]; lpCriticalSection
0x14000790c  call    cs:__imp_EnterCriticalSection
0x140007912  xor     eax, eax
0x140007914  mov     byte ptr [rbx+8], 1
0x140007918  add     rsp, 20h
0x14000791c  pop     rbx
0x14000791d  retn
```
