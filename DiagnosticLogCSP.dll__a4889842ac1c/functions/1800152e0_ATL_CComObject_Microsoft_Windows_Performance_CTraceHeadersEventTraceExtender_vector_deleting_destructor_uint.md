# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x1800152e0`
- end: `0x180015361`
- name: `??_E?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `129`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x1800152e0`
- `0x180037010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
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
0x1800152e0  mov     [rsp+arg_0], rbx
0x1800152e5  push    rdi
0x1800152e6  sub     rsp, 20h
0x1800152ea  mov     edi, edx
0x1800152ec  mov     rbx, rcx
0x1800152ef  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x1800152f6  mov     [rcx], rax
0x1800152f9  mov     dword ptr [rcx+18h], 0C0000001h
0x180015300  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015307  mov     rax, [rcx]
0x18001530a  mov     rax, [rax+10h]
0x18001530e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015313  nop
0x180015314  mov     rcx, [rbx+10h]
0x180015318  test    rcx, rcx
0x18001531b  jz      short loc_18001532A
0x18001531d  mov     rax, [rcx]
0x180015320  mov     rax, [rax+10h]
0x180015324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015329  nop
0x18001532a  mov     rcx, [rbx+8]
0x18001532e  test    rcx, rcx
0x180015331  jz      short loc_180015340
0x180015333  mov     rax, [rcx]
0x180015336  mov     rax, [rax+10h]
0x18001533a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001533f  nop
0x180015340  test    dil, 1
0x180015344  jz      short loc_180015353
0x180015346  mov     edx, 20h ; ' '; unsigned __int64
0x18001534b  mov     rcx, rbx; void *
0x18001534e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015353  mov     rax, rbx
0x180015356  mov     rbx, [rsp+28h+arg_0]
0x18001535b  add     rsp, 20h
0x18001535f  pop     rdi
0x180015360  retn
```
