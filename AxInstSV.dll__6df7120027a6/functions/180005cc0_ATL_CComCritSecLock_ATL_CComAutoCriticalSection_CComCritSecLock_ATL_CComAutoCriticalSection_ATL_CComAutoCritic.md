# ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)

- ea: `0x180005cc0`
- end: `0x180005ce6`
- name: `??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z`
- size: `38`
- prototype: `__int64 __fastcall(__int64, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006a20`
- `0x180006c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005cd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005cd3`

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
0x180005cc0  push    rbx
0x180005cc2  sub     rsp, 20h
0x180005cc6  mov     rbx, rcx
0x180005cc9  mov     [rcx], rdx
0x180005ccc  mov     byte ptr [rcx+8], 0
0x180005cd0  mov     rcx, rdx; lpCriticalSection
0x180005cd3  call    cs:__imp_EnterCriticalSection
0x180005cd9  mov     rax, rbx
0x180005cdc  mov     byte ptr [rbx+8], 1
0x180005ce0  add     rsp, 20h
0x180005ce4  pop     rbx
0x180005ce5  retn
```
