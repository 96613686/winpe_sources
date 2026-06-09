# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180003190`
- end: `0x1800031e5`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAPEAXI@Z`
- size: `85`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003190`
- `0x180007a90`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800031be`
- `KERNEL32!DeleteCriticalSection` at `0x1800031be`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rcx

  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
  v3 = (struct _RTL_CRITICAL_SECTION *)(Block + 4);
  if ( LOBYTE(v3[1].DebugInfo) )
  {
    LOBYTE(v3[1].DebugInfo) = 0;
    DeleteCriticalSection(v3);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003190  mov     [rsp+arg_0], rbx
0x180003195  push    rdi
0x180003196  sub     rsp, 20h
0x18000319a  mov     dword ptr [rcx+8], 0C0000001h
0x1800031a1  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800031a8  mov     [rcx], rax
0x1800031ab  mov     rbx, rcx
0x1800031ae  add     rcx, 10h; lpCriticalSection
0x1800031b2  mov     edi, edx
0x1800031b4  cmp     byte ptr [rcx+28h], 0
0x1800031b8  jz      short loc_1800031C4
0x1800031ba  mov     byte ptr [rcx+28h], 0
0x1800031be  call    cs:__imp_DeleteCriticalSection
0x1800031c4  test    dil, 1
0x1800031c8  jz      short loc_1800031D7
0x1800031ca  mov     edx, 48h ; 'H'
0x1800031cf  mov     rcx, rbx; Block
0x1800031d2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800031d7  mov     rax, rbx
0x1800031da  mov     rbx, [rsp+28h+arg_0]
0x1800031df  add     rsp, 20h
0x1800031e3  pop     rdi
0x1800031e4  retn
```
