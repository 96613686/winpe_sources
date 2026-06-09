# ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::`scalar deleting destructor'(uint)

- ea: `0x140010230`
- end: `0x140010297`
- name: `??_G?$CComObject@VCHostProviderFactory@Spelling@Globalization@Windows@@@ATL@@UEAAPEAXI@Z`
- size: `103`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140010230`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140010283`
- `msvcrt!??3@YAXPEAX@Z` at `0x140010283`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::`vftable';
  a1[2] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)a1 + 4);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140010230  mov     [rsp+arg_0], rbx
0x140010235  push    rdi
0x140010236  sub     rsp, 20h
0x14001023a  mov     edi, edx
0x14001023c  mov     rbx, rcx
0x14001023f  lea     rax, ??_7?$CComObject@VCHostProviderFactory@Spelling@Globalization@Windows@@@ATL@@6B@; const ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::`vftable'
0x140010246  mov     [rcx], rax
0x140010249  mov     dword ptr [rcx+8], 0C0000001h
0x140010250  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140010257  mov     rax, [rcx]
0x14001025a  mov     rax, [rax+10h]
0x14001025e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010263  nop
0x140010264  mov     rcx, [rbx+20h]
0x140010268  test    rcx, rcx
0x14001026b  jz      short loc_14001027A
0x14001026d  mov     rax, [rcx]
0x140010270  mov     rax, [rax+10h]
0x140010274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010279  nop
0x14001027a  test    dil, 1
0x14001027e  jz      short loc_140010289
0x140010280  mov     rcx, rbx
0x140010283  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140010289  mov     rax, rbx
0x14001028c  mov     rbx, [rsp+28h+arg_0]
0x140010291  add     rsp, 20h
0x140010295  pop     rdi
0x140010296  retn
```
