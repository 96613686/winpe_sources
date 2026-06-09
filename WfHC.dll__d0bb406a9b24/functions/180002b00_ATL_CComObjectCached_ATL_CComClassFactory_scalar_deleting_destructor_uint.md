# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180002b00`
- end: `0x180002b40`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `64`
- prototype: `_DWORD *__fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800039f0`

## callees

- `0x180002b00`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002b31`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002b31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002b28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002b28`

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
0x180002b00  push    rbx
0x180002b02  sub     rsp, 20h
0x180002b06  mov     dword ptr [rcx+8], 0C0000001h
0x180002b0d  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180002b14  mov     [rcx], rax
0x180002b17  mov     rbx, rcx
0x180002b1a  add     rcx, 10h; lpCriticalSection
0x180002b1e  cmp     byte ptr [rcx+28h], 0
0x180002b22  jz      short loc_180002B2E
0x180002b24  mov     byte ptr [rcx+28h], 0
0x180002b28  call    cs:__imp_DeleteCriticalSection
0x180002b2e  mov     rcx, rbx
0x180002b31  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002b37  mov     rax, rbx
0x180002b3a  add     rsp, 20h
0x180002b3e  pop     rbx
0x180002b3f  retn
```
