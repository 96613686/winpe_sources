# Windows::Internal::HostingContainerRootElement::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)

- ea: `0x18009c280`
- end: `0x18009c40a`
- name: `?_SelfLayoutUpdateDesiredSize@HostingContainerRootElement@Internal@Windows@@EEAA?AUtagSIZE@@HHPEAVSurface@DirectUI@@@Z`
- size: `394`
- prototype: `struct tagSIZE __fastcall(Windows::Internal::HostingContainerRootElement *__hidden this, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18005ae80`
- `0x18009c280`

## import_xrefs

- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c2d3`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c324`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c37f`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c2d3`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c324`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c37f`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18009c366`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18009c366`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c2f2`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c3a1`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c3db`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c2f2`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c3a1`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c3db`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c2bb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c30b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c35a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c2bb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c30b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c35a`
- `DUI70!StrToID` at `0x18009c2af`
- `DUI70!StrToID` at `0x18009c2ff`
- `DUI70!StrToID` at `0x18009c34e`
- `DUI70!StrToID` at `0x18009c2af`
- `DUI70!StrToID` at `0x18009c2ff`
- `DUI70!StrToID` at `0x18009c34e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct tagSIZE __fastcall Windows::Internal::HostingContainerRootElement::_SelfLayoutUpdateDesiredSize(
        Windows::Internal::HostingContainerRootElement *this,
        _DWORD *a2,
        int a3,
        struct DirectUI::Surface *a4)
{
  unsigned int v4; // esi
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rbx
  const struct tagRECT *Margin; // rdi
  unsigned __int16 v10; // ax
  const struct tagRECT *v11; // rax
  LONG bottom; // ecx
  int v13; // esi
  unsigned int v14; // r15d
  unsigned __int16 v15; // ax
  DirectUI::Element *v16; // rsi
  LONG top; // ebx
  LONG v18; // edi
  int v19; // r15d
  unsigned __int64 v20; // r9
  struct DirectUI::Value *v22; // [rsp+30h] [rbp-48h] BYREF
  struct DirectUI::Value *v23; // [rsp+38h] [rbp-40h] BYREF
  struct DirectUI::Value *v24; // [rsp+40h] [rbp-38h] BYREF
  char v25; // [rsp+48h] [rbp-30h] BYREF
  int v26; // [rsp+4Ch] [rbp-2Ch]
  const struct tagRECT *v27; // [rsp+50h] [rbp-28h]
  _BYTE v28[4]; // [rsp+58h] [rbp-20h] BYREF
  int v29; // [rsp+5Ch] [rbp-1Ch]
  DirectUI::Element *v30; // [rsp+60h] [rbp-18h]

  v4 = (unsigned int)a4;
  *a2 = a3;
  a2[1] = (_DWORD)a4;
  v7 = StrToID(L"TitleBar");
  Descendent = DirectUI::Element::FindDescendent(this, v7);
  v24 = 0;
  Margin = DirectUI::Element::GetMargin(Descendent, &v24);
  DirectUI::Element::_UpdateDesiredSize(Descendent, (unsigned int)&v25, a3, (struct DirectUI::Surface *)v4);
  v10 = StrToID(L"ContentAreaContainer");
  v30 = DirectUI::Element::FindDescendent(this, v10);
  v23 = 0;
  v11 = DirectUI::Element::GetMargin(v30, &v23);
  v27 = v11;
  bottom = Margin->bottom;
  if ( bottom <= v11->top )
    bottom = v11->top;
  v13 = v4 - bottom - v26;
  v14 = 0;
  if ( v13 >= 0 )
    v14 = v13;
  v15 = StrToID(L"ButtonBar");
  v16 = DirectUI::Element::FindDescendent(this, v15);
  if ( DirectUI::Element::GetVisible(v16) )
  {
    v22 = 0;
    top = DirectUI::Element::GetMargin(v16, &v22)->top;
    v18 = v27->bottom;
    DirectUI::Element::_UpdateDesiredSize(v16, (unsigned int)v28, a3, (struct DirectUI::Surface *)v14);
    if ( v18 <= top )
      v18 = top;
    v19 = v14 - v18 - v29;
    CValuePtr::Release((CValuePtr *)&v22);
    v20 = 0;
    if ( v19 >= 0 )
      v20 = (unsigned int)v19;
  }
  else
  {
    v20 = v14;
  }
  DirectUI::Element::_UpdateDesiredSize(v30, (unsigned int)v28, a3, (struct DirectUI::Surface *)v20);
  CValuePtr::Release((CValuePtr *)&v23);
  CValuePtr::Release((CValuePtr *)&v24);
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x18009c280  mov     [rsp-40h+arg_8], rdx
0x18009c285  push    rbp
0x18009c286  push    rbx
0x18009c287  push    rsi
0x18009c288  push    rdi
0x18009c289  push    r12
0x18009c28b  push    r13
0x18009c28d  push    r14
0x18009c28f  push    r15
0x18009c291  mov     rbp, rsp
0x18009c294  sub     rsp, 78h
0x18009c298  mov     esi, r9d
0x18009c29b  mov     r12d, r8d
0x18009c29e  mov     r14, rcx
0x18009c2a1  mov     [rdx], r8d
0x18009c2a4  mov     [rdx+4], r9d
0x18009c2a8  lea     rcx, aTitlebar; "TitleBar"
0x18009c2af  call    cs:__imp_StrToID
0x18009c2b5  movzx   edx, ax
0x18009c2b8  mov     rcx, r14
0x18009c2bb  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009c2c1  mov     rbx, rax
0x18009c2c4  mov     [rbp+var_38], 0
0x18009c2cc  lea     rdx, [rbp+var_38]
0x18009c2d0  mov     rcx, rax
0x18009c2d3  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009c2d9  mov     rdi, rax
0x18009c2dc  mov     r13, [rbp+arg_20]
0x18009c2e0  mov     [rsp+78h+var_58], r13
0x18009c2e5  mov     r9d, esi
0x18009c2e8  mov     r8d, r12d
0x18009c2eb  lea     rdx, [rbp+var_30]
0x18009c2ef  mov     rcx, rbx
0x18009c2f2  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18009c2f8  lea     rcx, aContentareacon; "ContentAreaContainer"
0x18009c2ff  call    cs:__imp_StrToID
0x18009c305  movzx   edx, ax
0x18009c308  mov     rcx, r14
0x18009c30b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009c311  mov     [rbp+var_18], rax
0x18009c315  mov     [rbp+var_40], 0
0x18009c31d  lea     rdx, [rbp+var_40]
0x18009c321  mov     rcx, rax
0x18009c324  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009c32a  mov     [rbp+var_28], rax
0x18009c32e  mov     ecx, [rdi+0Ch]
0x18009c331  cmp     ecx, [rax+4]
0x18009c334  cmovle  ecx, [rax+4]
0x18009c338  sub     esi, ecx
0x18009c33a  sub     esi, [rbp+var_2C]
0x18009c33d  mov     r15d, 0
0x18009c343  cmovns  r15d, esi
0x18009c347  lea     rcx, aButtonbar; "ButtonBar"
0x18009c34e  call    cs:__imp_StrToID
0x18009c354  movzx   edx, ax
0x18009c357  mov     rcx, r14
0x18009c35a  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009c360  mov     rsi, rax
0x18009c363  mov     rcx, rax
0x18009c366  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x18009c36c  test    al, al
0x18009c36e  jz      short loc_18009C3C8
0x18009c370  mov     [rbp+var_48], 0
0x18009c378  lea     rdx, [rbp+var_48]
0x18009c37c  mov     rcx, rsi
0x18009c37f  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009c385  mov     ebx, [rax+4]
0x18009c388  mov     rdi, [rbp+var_28]
0x18009c38c  mov     edi, [rdi+0Ch]
0x18009c38f  mov     [rsp+78h+var_58], r13
0x18009c394  mov     r9d, r15d
0x18009c397  mov     r8d, r12d
0x18009c39a  lea     rdx, [rbp+var_20]
0x18009c39e  mov     rcx, rsi
0x18009c3a1  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18009c3a7  cmp     edi, ebx
0x18009c3a9  cmovle  edi, ebx
0x18009c3ac  sub     r15d, edi
0x18009c3af  sub     r15d, [rbp+var_1C]
0x18009c3b3  lea     rcx, [rbp+var_48]; this
0x18009c3b7  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18009c3bc  xor     r9d, r9d
0x18009c3bf  test    r15d, r15d
0x18009c3c2  cmovns  r9d, r15d
0x18009c3c6  jmp     short loc_18009C3CB
0x18009c3c8  mov     r9d, r15d
0x18009c3cb  mov     [rsp+78h+var_58], r13
0x18009c3d0  mov     r8d, r12d
0x18009c3d3  lea     rdx, [rbp+var_20]
0x18009c3d7  mov     rcx, [rbp+var_18]
0x18009c3db  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18009c3e1  nop
0x18009c3e2  lea     rcx, [rbp+var_40]; this
0x18009c3e6  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18009c3eb  nop
0x18009c3ec  lea     rcx, [rbp+var_38]; this
0x18009c3f0  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18009c3f5  mov     rax, [rbp+arg_8]
0x18009c3f9  add     rsp, 78h
0x18009c3fd  pop     r15
0x18009c3ff  pop     r14
0x18009c401  pop     r13
0x18009c403  pop     r12
0x18009c405  pop     rdi
0x18009c406  pop     rsi
0x18009c407  pop     rbx
0x18009c408  pop     rbp
0x18009c409  retn
```
