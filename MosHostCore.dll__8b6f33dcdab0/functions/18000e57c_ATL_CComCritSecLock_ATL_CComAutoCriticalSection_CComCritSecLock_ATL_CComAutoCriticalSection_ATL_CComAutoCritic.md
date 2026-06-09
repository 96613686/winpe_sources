# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)

- ea: `0x18000e57c`
- end: `0x18000e5a2`
- name: `??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z`
- size: `38`
- prototype: `__int64 __fastcall(__int64, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000ea5c`
- `0x18000ec18`
- `0x18000ec6c`
- `0x18000ed40`
- `0x180010780`
- `0x18001b690`
- `0x18001cc50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e58f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e58f`

## pseudocode

```c
__int64 __fastcall ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2)
{
  __int64 result; // rax

  *(_QWORD *)a1 = a2;
  *(_BYTE *)(a1 + 8) = 0;
  EnterCriticalSection(a2);
  result = a1;
  *(_BYTE *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x18000e57c  push    rbx
0x18000e57e  sub     rsp, 20h
0x18000e582  mov     rbx, rcx
0x18000e585  mov     [rcx], rdx
0x18000e588  mov     byte ptr [rcx+8], 0
0x18000e58c  mov     rcx, rdx; lpCriticalSection
0x18000e58f  call    cs:__imp_EnterCriticalSection
0x18000e595  mov     rax, rbx
0x18000e598  mov     byte ptr [rbx+8], 1
0x18000e59c  add     rsp, 20h
0x18000e5a0  pop     rbx
0x18000e5a1  retn
```
