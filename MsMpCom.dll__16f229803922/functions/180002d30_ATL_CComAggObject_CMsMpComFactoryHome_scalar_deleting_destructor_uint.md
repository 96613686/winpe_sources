# ATL::CComAggObject<CMsMpComFactoryHome>::`scalar deleting destructor'(uint)

- ea: `0x180002d30`
- end: `0x180002dac`
- name: `??_G?$CComAggObject@VCMsMpComFactoryHome@@@ATL@@UEAAPEAXI@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180002d30`
- `0x18000a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002d98`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d98`
- `KERNEL32!DeleteCriticalSection` at `0x180002d89`
- `KERNEL32!DeleteCriticalSection` at `0x180002d89`
- `mpclient!MpConfigUninitialize` at `0x180002d6a`
- `mpclient!MpConfigUninitialize` at `0x180002d6a`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMsMpComFactoryHome>::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *a1,
        char a2)
{
  a1->LockCount = -1073741823;
  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMsMpComFactoryHome>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( a1[2].OwningThread )
    MpConfigUninitialize();
  a1->LockSemaphore = &MP_CComObjectRootEx::`vftable';
  if ( LOBYTE(a1[2].DebugInfo) )
  {
    LOBYTE(a1[2].DebugInfo) = 0;
    DeleteCriticalSection(a1 + 1);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002d30  mov     [rsp+arg_0], rbx
0x180002d35  push    rdi
0x180002d36  sub     rsp, 20h
0x180002d3a  mov     dword ptr [rcx+8], 0C0000001h
0x180002d41  lea     rax, ??_7?$CComAggObject@VCMsMpComFactoryHome@@@ATL@@6B@; const ATL::CComAggObject<CMsMpComFactoryHome>::`vftable'
0x180002d48  mov     [rcx], rax
0x180002d4b  mov     rbx, rcx
0x180002d4e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d55  mov     edi, edx
0x180002d57  mov     rax, [rcx]
0x180002d5a  mov     rax, [rax+10h]
0x180002d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d63  cmp     qword ptr [rbx+60h], 0
0x180002d68  jz      short loc_180002D70
0x180002d6a  call    cs:__imp_MpConfigUninitialize
0x180002d70  lea     rax, ??_7MP_CComObjectRootEx@@6B@; const MP_CComObjectRootEx::`vftable'
0x180002d77  lea     rcx, [rbx+28h]; lpCriticalSection
0x180002d7b  mov     [rbx+18h], rax
0x180002d7f  cmp     byte ptr [rcx+28h], 0
0x180002d83  jz      short loc_180002D8F
0x180002d85  mov     byte ptr [rcx+28h], 0
0x180002d89  call    cs:__imp_DeleteCriticalSection
0x180002d8f  test    dil, 1
0x180002d93  jz      short loc_180002D9E
0x180002d95  mov     rcx, rbx
0x180002d98  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002d9e  mov     rax, rbx
0x180002da1  mov     rbx, [rsp+28h+arg_0]
0x180002da6  add     rsp, 20h
0x180002daa  pop     rdi
0x180002dab  retn
```
