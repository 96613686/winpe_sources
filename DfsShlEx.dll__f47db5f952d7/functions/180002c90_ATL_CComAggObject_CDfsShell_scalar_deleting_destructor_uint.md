# ATL::CComAggObject<CDfsShell>::`scalar deleting destructor'(uint)

- ea: `0x180002c90`
- end: `0x180002ce8`
- name: `??_G?$CComAggObject@VCDfsShell@@@ATL@@UEAAPEAXI@Z`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002b10`
- `0x180002c90`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002cd4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002cd4`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CDfsShell>::`scalar deleting destructor'(_DWORD *a1, char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CDfsShell>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CDfsShell::~CDfsShell((CDfsShell *)(a1 + 4));
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002c90  mov     [rsp+arg_0], rbx
0x180002c95  push    rdi
0x180002c96  sub     rsp, 20h
0x180002c9a  mov     dword ptr [rcx+8], 0C0000001h
0x180002ca1  lea     rax, ??_7?$CComAggObject@VCDfsShell@@@ATL@@6B@; const ATL::CComAggObject<CDfsShell>::`vftable'
0x180002ca8  mov     [rcx], rax
0x180002cab  mov     rdi, rcx
0x180002cae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002cb5  mov     ebx, edx
0x180002cb7  mov     rax, [rcx]
0x180002cba  mov     rax, [rax+10h]
0x180002cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc3  lea     rcx, [rdi+10h]; this
0x180002cc7  call    ??1CDfsShell@@QEAA@XZ; CDfsShell::~CDfsShell(void)
0x180002ccc  test    bl, 1
0x180002ccf  jz      short loc_180002CDA
0x180002cd1  mov     rcx, rdi
0x180002cd4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002cda  mov     rbx, [rsp+28h+arg_0]
0x180002cdf  mov     rax, rdi
0x180002ce2  add     rsp, 20h
0x180002ce6  pop     rdi
0x180002ce7  retn
```
