# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x1800151f0`
- end: `0x180015271`
- name: `??_E?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `129`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x1800151f0`
- `0x180037010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
  a1[6] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)a1 + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)a1 + 1);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800151f0  mov     [rsp+arg_0], rbx
0x1800151f5  push    rdi
0x1800151f6  sub     rsp, 20h
0x1800151fa  mov     edi, edx
0x1800151fc  mov     rbx, rcx
0x1800151ff  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x180015206  mov     [rcx], rax
0x180015209  mov     dword ptr [rcx+18h], 0C0000001h
0x180015210  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015217  mov     rax, [rcx]
0x18001521a  mov     rax, [rax+10h]
0x18001521e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015223  nop
0x180015224  mov     rcx, [rbx+10h]
0x180015228  test    rcx, rcx
0x18001522b  jz      short loc_18001523A
0x18001522d  mov     rax, [rcx]
0x180015230  mov     rax, [rax+10h]
0x180015234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015239  nop
0x18001523a  mov     rcx, [rbx+8]
0x18001523e  test    rcx, rcx
0x180015241  jz      short loc_180015250
0x180015243  mov     rax, [rcx]
0x180015246  mov     rax, [rax+10h]
0x18001524a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001524f  nop
0x180015250  test    dil, 1
0x180015254  jz      short loc_180015263
0x180015256  mov     edx, 28h ; '('; unsigned __int64
0x18001525b  mov     rcx, rbx; void *
0x18001525e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015263  mov     rax, rbx
0x180015266  mov     rbx, [rsp+28h+arg_0]
0x18001526b  add     rsp, 20h
0x18001526f  pop     rdi
0x180015270  retn
```
