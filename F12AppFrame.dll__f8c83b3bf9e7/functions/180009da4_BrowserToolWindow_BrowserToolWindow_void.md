# BrowserToolWindow::~BrowserToolWindow(void)

- ea: `0x180009da4`
- end: `0x180009e88`
- name: `??1BrowserToolWindow@@UEAA@XZ`
- size: `228`
- prototype: `void __fastcall(BrowserToolWindow *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a120`
- `0x18000a340`

## callees

- `0x180009da4`
- `0x18000bb44`
- `0x18002d4c4`
- `0x180035010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009e7b`
- `KERNEL32!DeleteCriticalSection` at `0x180009e7b`

## pseudocode

```c
void __fastcall BrowserToolWindow::~BrowserToolWindow(BrowserToolWindow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  AtlThunkData_t *v8; // rcx

  *(_QWORD *)this = &BrowserToolWindow::`vftable'{for `ATL::CWindowImpl<BrowserToolWindow,ATL::CAxWindow2T<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>'};
  *((_QWORD *)this + 9) = &BrowserToolWindow::`vftable'{for `IWPCEvents'};
  BrowserToolWindow::Cleanup(this);
  v2 = *((_QWORD *)this + 22);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 21);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 20);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 19);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 18);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 17);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = (AtlThunkData_t *)*((_QWORD *)this + 5);
  if ( v8 )
    AtlThunk_FreeData(v8);
  if ( *((_BYTE *)this + 128) )
  {
    *((_BYTE *)this + 128) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  }
}

```

## disassembly

```asm
0x180009da4  push    rbx
0x180009da6  sub     rsp, 20h
0x180009daa  mov     rbx, rcx
0x180009dad  lea     rax, ??_7BrowserToolWindow@@6B?$CWindowImpl@UBrowserToolWindow@@V?$CAxWindow2T@VCWindow@ATL@@@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@; const BrowserToolWindow::`vftable'{for `ATL::CWindowImpl<BrowserToolWindow,ATL::CAxWindow2T<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>'}
0x180009db4  mov     [rcx], rax
0x180009db7  lea     rax, ??_7BrowserToolWindow@@6BIWPCEvents@@@; const BrowserToolWindow::`vftable'{for `IWPCEvents'}
0x180009dbe  mov     [rcx+48h], rax
0x180009dc2  call    ?Cleanup@BrowserToolWindow@@QEAAXXZ; BrowserToolWindow::Cleanup(void)
0x180009dc7  nop
0x180009dc8  mov     rcx, [rbx+0B0h]
0x180009dcf  test    rcx, rcx
0x180009dd2  jz      short loc_180009DE1
0x180009dd4  mov     rax, [rcx]
0x180009dd7  mov     rax, [rax+10h]
0x180009ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009de0  nop
0x180009de1  mov     rcx, [rbx+0A8h]
0x180009de8  test    rcx, rcx
0x180009deb  jz      short loc_180009DFA
0x180009ded  mov     rax, [rcx]
0x180009df0  mov     rax, [rax+10h]
0x180009df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df9  nop
0x180009dfa  mov     rcx, [rbx+0A0h]
0x180009e01  test    rcx, rcx
0x180009e04  jz      short loc_180009E13
0x180009e06  mov     rax, [rcx]
0x180009e09  mov     rax, [rax+10h]
0x180009e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e12  nop
0x180009e13  mov     rcx, [rbx+98h]
0x180009e1a  test    rcx, rcx
0x180009e1d  jz      short loc_180009E2C
0x180009e1f  mov     rax, [rcx]
0x180009e22  mov     rax, [rax+10h]
0x180009e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e2b  nop
0x180009e2c  mov     rcx, [rbx+90h]
0x180009e33  test    rcx, rcx
0x180009e36  jz      short loc_180009E45
0x180009e38  mov     rax, [rcx]
0x180009e3b  mov     rax, [rax+10h]
0x180009e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e44  nop
0x180009e45  mov     rcx, [rbx+88h]
0x180009e4c  test    rcx, rcx
0x180009e4f  jz      short loc_180009E5E
0x180009e51  mov     rax, [rcx]
0x180009e54  mov     rax, [rax+10h]
0x180009e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e5d  nop
0x180009e5e  mov     rcx, [rbx+28h]; Thunk
0x180009e62  test    rcx, rcx
0x180009e65  jz      short loc_180009E6D
0x180009e67  call    AtlThunk_FreeData
0x180009e6c  nop
0x180009e6d  lea     rcx, [rbx+58h]; lpCriticalSection
0x180009e71  cmp     byte ptr [rcx+28h], 0
0x180009e75  jz      short loc_180009E82
0x180009e77  mov     byte ptr [rcx+28h], 0
0x180009e7b  call    cs:__imp_DeleteCriticalSection
0x180009e81  nop
0x180009e82  add     rsp, 20h
0x180009e86  pop     rbx
0x180009e87  retn
```
