# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x18000c528`
- end: `0x18000c568`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `64`
- prototype: `_DWORD *__fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007a10`
- `0x18000c4c0`

## callees

- `0x18000c528`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c559`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c559`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c550`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c550`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(_DWORD *a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx

  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 4);
  if ( LOBYTE(v2[1].DebugInfo) )
  {
    LOBYTE(v2[1].DebugInfo) = 0;
    DeleteCriticalSection(v2);
  }
  operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000c528  push    rbx
0x18000c52a  sub     rsp, 20h
0x18000c52e  mov     dword ptr [rcx+8], 0C0000001h
0x18000c535  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000c53c  mov     [rcx], rax
0x18000c53f  mov     rbx, rcx
0x18000c542  add     rcx, 10h; lpCriticalSection
0x18000c546  cmp     byte ptr [rcx+28h], 0
0x18000c54a  jz      short loc_18000C556
0x18000c54c  mov     byte ptr [rcx+28h], 0
0x18000c550  call    cs:__imp_DeleteCriticalSection
0x18000c556  mov     rcx, rbx
0x18000c559  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c55f  mov     rax, rbx
0x18000c562  add     rsp, 20h
0x18000c566  pop     rbx
0x18000c567  retn
```
