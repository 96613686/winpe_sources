# ATL::CComObject<CPolicyComponent>::`vector deleting destructor'(uint)

- ea: `0x18000cbd0`
- end: `0x18000cc38`
- name: `??_E?$CComObject@VCPolicyComponent@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000cbd0`
- `0x180015c0c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cc11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cc11`

## pseudocode

```c
char *__fastcall ATL::CComObject<CPolicyComponent>::`vector deleting destructor'(char *hMem, char a2)
{
  *((_DWORD *)hMem + 2) = -1073741823;
  *(_QWORD *)hMem = &ATL::CComObject<CPolicyComponent>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( hMem[56] )
  {
    hMem[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(hMem + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(hMem);
  return hMem;
}

```

## disassembly

```asm
0x18000cbd0  mov     [rsp+arg_0], rbx
0x18000cbd5  push    rdi
0x18000cbd6  sub     rsp, 20h
0x18000cbda  mov     dword ptr [rcx+8], 0C0000001h
0x18000cbe1  lea     rax, ??_7?$CComObject@VCPolicyComponent@@@ATL@@6B@; const ATL::CComObject<CPolicyComponent>::`vftable'
0x18000cbe8  mov     [rcx], rax
0x18000cbeb  mov     rbx, rcx
0x18000cbee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cbf5  mov     edi, edx
0x18000cbf7  mov     rax, [rcx]
0x18000cbfa  mov     rax, [rax+10h]
0x18000cbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc03  cmp     byte ptr [rbx+38h], 0
0x18000cc07  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000cc0b  jz      short loc_18000CC17
0x18000cc0d  mov     byte ptr [rcx+28h], 0
0x18000cc11  call    cs:__imp_DeleteCriticalSection
0x18000cc17  test    dil, 1
0x18000cc1b  jz      short loc_18000CC2A
0x18000cc1d  mov     edx, 48h ; 'H'
0x18000cc22  mov     rcx, rbx; hMem
0x18000cc25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cc2a  mov     rax, rbx
0x18000cc2d  mov     rbx, [rsp+28h+arg_0]
0x18000cc32  add     rsp, 20h
0x18000cc36  pop     rdi
0x18000cc37  retn
```
