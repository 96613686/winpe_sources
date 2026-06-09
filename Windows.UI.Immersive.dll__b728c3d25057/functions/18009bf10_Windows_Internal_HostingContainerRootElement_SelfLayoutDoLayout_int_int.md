# Windows::Internal::HostingContainerRootElement::_SelfLayoutDoLayout(int,int)

- ea: `0x18009bf10`
- end: `0x18009c140`
- name: `?_SelfLayoutDoLayout@HostingContainerRootElement@Internal@Windows@@EEAAXHH@Z`
- size: `560`
- prototype: `void __fastcall(Windows::Internal::HostingContainerRootElement *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18005ae80`
- `0x18009bf10`

## import_xrefs

- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009bf56`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c008`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c0b7`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009bf56`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c008`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x18009c0b7`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18009bf64`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18009c014`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18009c03c`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18009bf64`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18009c014`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18009c03c`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18009c060`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18009c060`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009bf3d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009bf85`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009bfed`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c030`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009bf3d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009bf85`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009bfed`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c030`
- `DUI70!StrToID` at `0x18009bf31`
- `DUI70!StrToID` at `0x18009bf79`
- `DUI70!StrToID` at `0x18009bfe1`
- `DUI70!StrToID` at `0x18009c024`
- `DUI70!StrToID` at `0x18009bf31`
- `DUI70!StrToID` at `0x18009bf79`
- `DUI70!StrToID` at `0x18009bfe1`
- `DUI70!StrToID` at `0x18009c024`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009bfaf`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009bfd4`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009c09a`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009c113`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009bfaf`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009bfd4`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009c09a`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009c113`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Internal::HostingContainerRootElement::_SelfLayoutDoLayout(
        Windows::Internal::HostingContainerRootElement *this,
        int a2,
        int a3)
{
  unsigned __int16 v6; // ax
  DirectUI::Element *Descendent; // rdi
  unsigned __int16 v8; // ax
  struct DirectUI::Element *v9; // rax
  unsigned __int16 v10; // ax
  struct DirectUI::Element *v11; // rbx
  const struct tagRECT *v12; // r15
  __int64 v13; // rbx
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // r13
  int v16; // r12d
  int v17; // edi
  const struct tagRECT *v18; // rax
  LONG bottom; // ecx
  int v20; // edi
  LONG top; // eax
  __int64 v22; // [rsp+40h] [rbp-78h]
  struct DirectUI::Value *v23; // [rsp+48h] [rbp-70h] BYREF
  struct DirectUI::Value *v24; // [rsp+50h] [rbp-68h] BYREF
  const struct tagRECT *Margin; // [rsp+58h] [rbp-60h]
  struct DirectUI::Element *v26; // [rsp+60h] [rbp-58h]
  struct DirectUI::Value *v27; // [rsp+D8h] [rbp+20h] BYREF

  v6 = StrToID(L"TitleBar");
  Descendent = DirectUI::Element::FindDescendent(this, v6);
  v24 = 0;
  Margin = DirectUI::Element::GetMargin(Descendent, &v24);
  v22 = (__int64)*DirectUI::Element::GetDesiredSize(Descendent);
  v8 = StrToID(L"OldTitleBarBackground");
  v9 = DirectUI::Element::FindDescendent(this, v8);
  DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v9, 0, 0, v22, HIDWORD(v22));
  DirectUI::Layout::UpdateLayoutRect(this, a2, a3, Descendent, 0, 0, v22, HIDWORD(v22));
  v10 = StrToID(L"ContentAreaContainer");
  v11 = DirectUI::Element::FindDescendent(this, v10);
  v26 = v11;
  v23 = 0;
  v12 = DirectUI::Element::GetMargin(v11, &v23);
  v13 = (__int64)*DirectUI::Element::GetDesiredSize(v11);
  v14 = StrToID(L"ButtonBar");
  v15 = DirectUI::Element::FindDescendent(this, v14);
  v27 = (struct DirectUI::Value *)*DirectUI::Element::GetDesiredSize(v15);
  v16 = (a2 - (int)v13) / 2;
  if ( DirectUI::Element::GetVisible(v15) )
  {
    v17 = 0;
    if ( a3 - HIDWORD(v27) >= 0 )
      v17 = a3 - HIDWORD(v27);
    DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v15, v16, v17, v13, HIDWORD(v27));
    v27 = 0;
    v18 = DirectUI::Element::GetMargin(v15, &v27);
    bottom = v12->bottom;
    if ( bottom <= v18->top )
      bottom = v18->top;
    v20 = v17 - bottom;
    CValuePtr::Release((CValuePtr *)&v27);
  }
  else
  {
    v20 = a3;
  }
  top = Margin->bottom;
  if ( top <= v12->top )
    top = v12->top;
  DirectUI::Layout::UpdateLayoutRect(this, a2, a3, v26, v16, top + HIDWORD(v22), v13, v20 - (top + HIDWORD(v22)));
  CValuePtr::Release((CValuePtr *)&v23);
  CValuePtr::Release((CValuePtr *)&v24);
}

```

## disassembly

```asm
0x18009bf10  push    rbx
0x18009bf12  push    rbp
0x18009bf13  push    rsi
0x18009bf14  push    rdi
0x18009bf15  push    r12
0x18009bf17  push    r13
0x18009bf19  push    r14
0x18009bf1b  push    r15
0x18009bf1d  sub     rsp, 78h
0x18009bf21  mov     esi, r8d
0x18009bf24  mov     r14d, edx
0x18009bf27  mov     rbp, rcx
0x18009bf2a  lea     rcx, aTitlebar; "TitleBar"
0x18009bf31  call    cs:__imp_StrToID
0x18009bf37  movzx   edx, ax
0x18009bf3a  mov     rcx, rbp
0x18009bf3d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009bf43  mov     rdi, rax
0x18009bf46  xor     r12d, r12d
0x18009bf49  mov     [rsp+0B8h+var_68], r12
0x18009bf4e  lea     rdx, [rsp+0B8h+var_68]
0x18009bf53  mov     rcx, rax
0x18009bf56  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009bf5c  mov     [rsp+0B8h+var_60], rax
0x18009bf61  mov     rcx, rdi
0x18009bf64  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x18009bf6a  mov     rbx, [rax]
0x18009bf6d  mov     [rsp+0B8h+var_78], rbx
0x18009bf72  lea     rcx, aOldtitlebarbac; "OldTitleBarBackground"
0x18009bf79  call    cs:__imp_StrToID
0x18009bf7f  movzx   edx, ax
0x18009bf82  mov     rcx, rbp
0x18009bf85  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009bf8b  mov     r15d, dword ptr [rsp+0B8h+var_78+4]
0x18009bf90  mov     [rsp+0B8h+var_80], r15d
0x18009bf95  mov     [rsp+0B8h+var_88], ebx
0x18009bf99  mov     [rsp+0B8h+var_90], r12d
0x18009bf9e  mov     [rsp+0B8h+var_98], r12d
0x18009bfa3  mov     r9, rax
0x18009bfa6  mov     r8d, esi
0x18009bfa9  mov     edx, r14d
0x18009bfac  mov     rcx, rbp
0x18009bfaf  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18009bfb5  mov     [rsp+0B8h+var_80], r15d
0x18009bfba  mov     [rsp+0B8h+var_88], ebx
0x18009bfbe  mov     [rsp+0B8h+var_90], r12d
0x18009bfc3  mov     [rsp+0B8h+var_98], r12d
0x18009bfc8  mov     r9, rdi
0x18009bfcb  mov     r8d, esi
0x18009bfce  mov     edx, r14d
0x18009bfd1  mov     rcx, rbp
0x18009bfd4  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18009bfda  lea     rcx, aContentareacon; "ContentAreaContainer"
0x18009bfe1  call    cs:__imp_StrToID
0x18009bfe7  movzx   edx, ax
0x18009bfea  mov     rcx, rbp
0x18009bfed  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009bff3  mov     rbx, rax
0x18009bff6  mov     [rsp+0B8h+var_58], rax
0x18009bffb  mov     [rsp+0B8h+var_70], r12
0x18009c000  lea     rdx, [rsp+0B8h+var_70]
0x18009c005  mov     rcx, rax
0x18009c008  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009c00e  mov     r15, rax
0x18009c011  mov     rcx, rbx
0x18009c014  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x18009c01a  mov     rbx, [rax]
0x18009c01d  lea     rcx, aButtonbar; "ButtonBar"
0x18009c024  call    cs:__imp_StrToID
0x18009c02a  movzx   edx, ax
0x18009c02d  mov     rcx, rbp
0x18009c030  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009c036  mov     r13, rax
0x18009c039  mov     rcx, rax
0x18009c03c  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x18009c042  mov     rcx, [rax]
0x18009c045  mov     [rsp+0B8h+arg_18], rcx
0x18009c04d  mov     eax, r14d
0x18009c050  sub     eax, ebx
0x18009c052  cdq
0x18009c053  lea     ecx, [r12+2]
0x18009c058  idiv    ecx
0x18009c05a  mov     r12d, eax
0x18009c05d  mov     rcx, r13
0x18009c060  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x18009c066  test    al, al
0x18009c068  jz      short loc_18009C0D9
0x18009c06a  mov     ecx, esi
0x18009c06c  mov     edx, dword ptr [rsp+0B8h+arg_18+4]
0x18009c073  sub     ecx, edx
0x18009c075  mov     edi, 0
0x18009c07a  cmovns  edi, ecx
0x18009c07d  mov     [rsp+0B8h+var_80], edx
0x18009c081  mov     [rsp+0B8h+var_88], ebx
0x18009c085  mov     [rsp+0B8h+var_90], edi
0x18009c089  mov     [rsp+0B8h+var_98], r12d
0x18009c08e  mov     r9, r13
0x18009c091  mov     r8d, esi
0x18009c094  mov     edx, r14d
0x18009c097  mov     rcx, rbp
0x18009c09a  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18009c0a0  mov     [rsp+0B8h+arg_18], 0
0x18009c0ac  lea     rdx, [rsp+0B8h+arg_18]
0x18009c0b4  mov     rcx, r13
0x18009c0b7  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18009c0bd  mov     ecx, [r15+0Ch]
0x18009c0c1  cmp     ecx, [rax+4]
0x18009c0c4  cmovle  ecx, [rax+4]
0x18009c0c8  sub     edi, ecx
0x18009c0ca  lea     rcx, [rsp+0B8h+arg_18]; this
0x18009c0d2  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18009c0d7  jmp     short loc_18009C0DB
0x18009c0d9  mov     edi, esi
0x18009c0db  mov     rax, [rsp+0B8h+var_60]
0x18009c0e0  mov     eax, [rax+0Ch]
0x18009c0e3  cmp     eax, [r15+4]
0x18009c0e7  cmovle  eax, [r15+4]
0x18009c0ec  mov     ecx, dword ptr [rsp+0B8h+var_78+4]
0x18009c0f0  add     ecx, eax
0x18009c0f2  sub     edi, ecx
0x18009c0f4  mov     [rsp+0B8h+var_80], edi
0x18009c0f8  mov     [rsp+0B8h+var_88], ebx
0x18009c0fc  mov     [rsp+0B8h+var_90], ecx
0x18009c100  mov     [rsp+0B8h+var_98], r12d
0x18009c105  mov     r9, [rsp+0B8h+var_58]
0x18009c10a  mov     r8d, esi
0x18009c10d  mov     edx, r14d
0x18009c110  mov     rcx, rbp
0x18009c113  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18009c119  nop
0x18009c11a  lea     rcx, [rsp+0B8h+var_70]; this
0x18009c11f  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18009c124  nop
0x18009c125  lea     rcx, [rsp+0B8h+var_68]; this
0x18009c12a  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x18009c12f  add     rsp, 78h
0x18009c133  pop     r15
0x18009c135  pop     r14
0x18009c137  pop     r13
0x18009c139  pop     r12
0x18009c13b  pop     rdi
0x18009c13c  pop     rsi
0x18009c13d  pop     rbp
0x18009c13e  pop     rbx
0x18009c13f  retn
```
