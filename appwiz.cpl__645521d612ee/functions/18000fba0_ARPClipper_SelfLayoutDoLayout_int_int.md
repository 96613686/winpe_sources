# ARPClipper::_SelfLayoutDoLayout(int,int)

- ea: `0x18000fba0`
- end: `0x18000fbf2`
- name: `?_SelfLayoutDoLayout@ARPClipper@@UEAAXHH@Z`
- size: `82`
- prototype: `void __fastcall(ARPClipper *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000b13c`
- `0x18000fba0`

## import_xrefs

- `DUI70!?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z` at `0x18000fbd4`
- `DUI70!?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z` at `0x18000fbd4`
- `DUI70!?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z` at `0x18000fbe3`
- `DUI70!?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z` at `0x18000fbe3`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18000fbc0`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18000fbc0`

## pseudocode

```c
void __fastcall ARPClipper::_SelfLayoutDoLayout(ARPClipper *this, int a2, int a3)
{
  DirectUI::Element *NthChild; // rax
  DirectUI::Element *v6; // rdi
  const struct tagSIZE *DesiredSize; // rbx

  NthChild = GetNthChild(this, 0);
  v6 = NthChild;
  if ( NthChild )
  {
    DesiredSize = DirectUI::Element::GetDesiredSize(NthChild);
    DirectUI::Element::_UpdateLayoutPosition(v6, 0, a3 - DesiredSize->cy);
    DirectUI::Element::_UpdateLayoutSize(v6, a2, DesiredSize->cy);
  }
}

```

## disassembly

```asm
0x18000fba0  push    rbx
0x18000fba2  push    rbp
0x18000fba3  push    rsi
0x18000fba4  push    rdi
0x18000fba5  sub     rsp, 28h
0x18000fba9  mov     ebp, edx
0x18000fbab  mov     esi, r8d
0x18000fbae  xor     edx, edx; unsigned int
0x18000fbb0  call    ?GetNthChild@@YAPEAVElement@DirectUI@@PEAV12@I@Z; GetNthChild(DirectUI::Element *,uint)
0x18000fbb5  mov     rdi, rax
0x18000fbb8  test    rax, rax
0x18000fbbb  jz      short loc_18000FBE9
0x18000fbbd  mov     rcx, rax
0x18000fbc0  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x18000fbc6  xor     edx, edx
0x18000fbc8  mov     rcx, rdi
0x18000fbcb  mov     rbx, rax
0x18000fbce  sub     esi, [rax+4]
0x18000fbd1  mov     r8d, esi
0x18000fbd4  call    cs:__imp_?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z; DirectUI::Element::_UpdateLayoutPosition(int,int)
0x18000fbda  mov     r8d, [rbx+4]
0x18000fbde  mov     edx, ebp
0x18000fbe0  mov     rcx, rdi
0x18000fbe3  call    cs:__imp_?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z; DirectUI::Element::_UpdateLayoutSize(int,int)
0x18000fbe9  add     rsp, 28h
0x18000fbed  pop     rdi
0x18000fbee  pop     rsi
0x18000fbef  pop     rbp
0x18000fbf0  pop     rbx
0x18000fbf1  retn
```
