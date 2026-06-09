# Windows::Internal::HostingContainerTitleBarElement::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)

- ea: `0x18009c410`
- end: `0x18009c4f2`
- name: `?_SelfLayoutUpdateDesiredSize@HostingContainerTitleBarElement@Internal@Windows@@EEAA?AUtagSIZE@@HHPEAVSurface@DirectUI@@@Z`
- size: `226`
- prototype: `struct tagSIZE __fastcall(Windows::Internal::HostingContainerTitleBarElement *__hidden this, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18009c410`

## import_xrefs

- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x18009c431`
- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x18009c442`
- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x18009c431`
- `DUI70!?GetHeight@Element@DirectUI@@QEAAHXZ` at `0x18009c442`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18009c46d`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18009c46d`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c4a4`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c4d6`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c4a4`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18009c4d6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c45f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c486`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c4bd`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c45f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c486`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18009c4bd`
- `DUI70!StrToID` at `0x18009c453`
- `DUI70!StrToID` at `0x18009c47a`
- `DUI70!StrToID` at `0x18009c4b1`
- `DUI70!StrToID` at `0x18009c453`
- `DUI70!StrToID` at `0x18009c47a`
- `DUI70!StrToID` at `0x18009c4b1`

## pseudocode

```c
struct tagSIZE __fastcall Windows::Internal::HostingContainerTitleBarElement::_SelfLayoutUpdateDesiredSize(
        Windows::Internal::HostingContainerTitleBarElement *this,
        _DWORD *a2,
        int a3,
        struct DirectUI::Surface *a4)
{
  unsigned int v4; // esi
  unsigned int Height; // eax
  unsigned __int16 v9; // ax
  DirectUI::Element *Descendent; // rax
  unsigned __int16 v11; // ax
  DirectUI::Element *v12; // rax
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rax
  char v16; // [rsp+58h] [rbp+10h] BYREF

  v4 = (unsigned int)a4;
  *a2 = a3;
  if ( (int)a4 >= DirectUI::Element::GetHeight(this) )
    Height = DirectUI::Element::GetHeight(this);
  else
    Height = v4;
  a2[1] = Height;
  v9 = StrToID(L"Title");
  Descendent = DirectUI::Element::FindDescendent(this, v9);
  DirectUI::Element::SetLayoutPos(Descendent, 4);
  v11 = StrToID(L"CenteredTitle");
  v12 = DirectUI::Element::FindDescendent(this, v11);
  DirectUI::Element::_UpdateDesiredSize(v12, (unsigned int)&v16, a3, (struct DirectUI::Surface *)v4);
  v13 = StrToID(L"Progress");
  v14 = DirectUI::Element::FindDescendent(this, v13);
  DirectUI::Element::_UpdateDesiredSize(v14, (unsigned int)&v16, a3, (struct DirectUI::Surface *)v4);
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x18009c410  mov     [rsp+arg_0], rbx
0x18009c415  mov     [rsp+arg_10], rbp
0x18009c41a  push    rsi
0x18009c41b  push    rdi
0x18009c41c  push    r14
0x18009c41e  sub     rsp, 30h
0x18009c422  mov     esi, r9d
0x18009c425  mov     [rdx], r8d
0x18009c428  mov     ebp, r8d
0x18009c42b  mov     r14, rdx
0x18009c42e  mov     rdi, rcx
0x18009c431  call    cs:__imp_?GetHeight@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetHeight(void)
0x18009c437  cmp     esi, eax
0x18009c439  jge     short loc_18009C43F
0x18009c43b  mov     eax, esi
0x18009c43d  jmp     short loc_18009C448
0x18009c43f  mov     rcx, rdi
0x18009c442  call    cs:__imp_?GetHeight@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetHeight(void)
0x18009c448  lea     rcx, aTitle_0; "Title"
0x18009c44f  mov     [r14+4], eax
0x18009c453  call    cs:__imp_StrToID
0x18009c459  movzx   edx, ax
0x18009c45c  mov     rcx, rdi
0x18009c45f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009c465  mov     rcx, rax
0x18009c468  mov     edx, 4
0x18009c46d  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18009c473  lea     rcx, aCenteredtitle; "CenteredTitle"
0x18009c47a  call    cs:__imp_StrToID
0x18009c480  movzx   edx, ax
0x18009c483  mov     rcx, rdi
0x18009c486  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009c48c  mov     rbx, [rsp+48h+arg_20]
0x18009c491  lea     rdx, [rsp+48h+arg_8]
0x18009c496  mov     rcx, rax
0x18009c499  mov     [rsp+48h+var_28], rbx
0x18009c49e  mov     r9d, esi
0x18009c4a1  mov     r8d, ebp
0x18009c4a4  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18009c4aa  lea     rcx, aProgress; "Progress"
0x18009c4b1  call    cs:__imp_StrToID
0x18009c4b7  movzx   edx, ax
0x18009c4ba  mov     rcx, rdi
0x18009c4bd  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18009c4c3  mov     r9d, esi
0x18009c4c6  mov     [rsp+48h+var_28], rbx
0x18009c4cb  mov     rcx, rax
0x18009c4ce  lea     rdx, [rsp+48h+arg_8]
0x18009c4d3  mov     r8d, ebp
0x18009c4d6  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x18009c4dc  mov     rbx, [rsp+48h+arg_0]
0x18009c4e1  mov     rax, r14
0x18009c4e4  mov     rbp, [rsp+48h+arg_10]
0x18009c4e9  add     rsp, 30h
0x18009c4ed  pop     r14
0x18009c4ef  pop     rdi
0x18009c4f0  pop     rsi
0x18009c4f1  retn
```
