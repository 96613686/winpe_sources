# Jot::CNoteTagListener::AddGroup(Jot::CNoteTagLabel *,Ofc::TOwnerPtr<Jot::CLabelElement> &)

- ea: `0x140153c30`
- end: `0x140153e3f`
- name: `?AddGroup@CNoteTagListener@Jot@@AEAAPEAVGroupBox@NetUI@@PEAVCNoteTagLabel@2@AEAV?$TOwnerPtr@VCLabelElement@Jot@@@Ofc@@@Z`
- size: `527`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x140158d00`
- `0x14015ac6c`

## callees

- `0x1400187d4`
- `0x1400194e0`
- `0x1400478e4`
- `0x140057580`
- `0x140065cc4`
- `0x1400b058c`
- `0x1400baa48`
- `0x1400baa7c`
- `0x140153a60`
- `0x140153c30`
- `0x140153e40`

## import_xrefs

- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140153d76`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140153d76`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140153e11`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140153e11`
- `mso40uiWin32Client!__imp_?Create@GroupContent@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140153cfe`
- `mso40uiWin32Client!__imp_?Create@GroupContent@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140153cfe`
- `mso40uiWin32Client!__imp_?Create@GroupHeader@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140153c93`
- `mso40uiWin32Client!__imp_?Create@GroupHeader@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140153c93`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140153cda`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140153dc6`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140153dea`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140153cda`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140153dc6`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140153dea`
- `mso40uiWin32Client!__imp_?Create@GroupBox@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140153c6f`
- `mso40uiWin32Client!__imp_?Create@GroupBox@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x140153c6f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153c80`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153ca4`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153ceb`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153d0f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153ddb`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153dfb`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153c80`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153ca4`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153ceb`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153d0f`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153ddb`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x140153dfb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
NetUI::Node *__fastcall Jot::CNoteTagListener::AddGroup(
        struct Jot::CNoteTagListener *a1,
        Jot::CNoteTagSet *a2,
        Jot::CLabelElement **a3)
{
  int v6; // eax
  int v7; // eax
  bool v8; // dl
  const wchar_t *v9; // r14
  const wchar_t *v10; // rdx
  int v11; // eax
  int v12; // eax
  int v13; // r13d
  unsigned __int64 v14; // rdx
  unsigned int v15; // r8d
  struct NetUI::Element *v16; // rax
  unsigned int v17; // edx
  struct NetUI::Element *v18; // rsi
  NetUI::Node *v19; // rbx
  Jot::CLabelElement *v20; // rcx
  int i; // edi
  Jot::CLabelElement *v22; // rbx
  struct Jot::INoteTagSearchResult *Item; // rax
  struct Node *v24; // rax
  int v25; // eax
  int v26; // eax
  const wchar_t *v27; // rax
  struct NetUI::Element *v28[2]; // [rsp+20h] [rbp-10h] BYREF
  NetUI::Node *v30; // [rsp+78h] [rbp+48h] BYREF
  NetUI::SimpleButton *v31; // [rsp+88h] [rbp+58h] BYREF

  if ( !*((_QWORD *)a2 + 18) )
    return 0;
  v30 = 0;
  v6 = NetUI::GroupBox::Create(&v30);
  if ( v6 < 0 )
  {
    CrashWithRecoveryHrTag(v6, 0x1E48C054u);
    __debugbreak();
  }
  v31 = 0;
  v7 = NetUI::GroupHeader::Create(&v31);
  if ( v7 < 0 )
  {
    CrashWithRecoveryHrTag(v7, 0x1E48C053u);
    __debugbreak();
  }
  NetUI::SimpleButton::SetIsAcceleratorIgnored(v31, v8);
  v9 = (const wchar_t *)((char *)a2 + 128);
  v10 = (const wchar_t *)((char *)a2 + 128);
  if ( *((_QWORD *)a2 + 19) > 7u )
    v10 = *(const wchar_t **)v9;
  NetUI::Element::SetTextString(v31, v10);
  v11 = NetUI::Node::Add(v30, (struct Node *)v31);
  if ( v11 < 0 )
  {
    CrashWithRecoveryHrTag(v11, 0x1E48C052u);
    __debugbreak();
  }
  v28[0] = 0;
  v12 = NetUI::GroupContent::Create(v28);
  if ( v12 < 0 )
  {
    CrashWithRecoveryHrTag(v12, 0x1E48C051u);
    __debugbreak();
  }
  v13 = (*(__int64 (__fastcall **)(Jot::CNoteTagSet *))(*(_QWORD *)a2 + 320LL))(a2);
  v16 = (struct NetUI::Element *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x80, v14, v15);
  v18 = v16;
  v28[1] = v16;
  if ( v16 )
  {
    if ( *((_QWORD *)a2 + 19) > 7u )
      v9 = *(const wchar_t **)v9;
    v19 = v30;
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>((char *)v16 + 16);
    *((_QWORD *)v18 + 13) = 0;
    *((_QWORD *)v18 + 14) = 0;
    *((_QWORD *)v18 + 15) = 0;
    *(_QWORD *)v18 = v19;
    *((_DWORD *)v18 + 2) = 0;
    Jot::CWzInBuffer::CopyWz((struct NetUI::Element *)((char *)v18 + 16), v9);
  }
  else
  {
    v18 = 0;
  }
  v20 = *a3;
  if ( *a3 != v18 )
  {
    if ( v20 )
      Jot::CLabelElement::`scalar deleting destructor'(v20, v17);
    *a3 = v18;
  }
  for ( i = 0; i < v13; ++i )
  {
    v22 = *a3;
    Item = Jot::CNoteTagSet::GetItem(a2, i);
    v24 = (struct Node *)Jot::CLabelElement::AddGroupContents(v22, Item, a1, -1);
    v25 = NetUI::Node::Add(v28[0], v24);
    if ( v25 < 0 )
    {
      CrashWithRecoveryHrTag(v25, 0x1E48C050u);
      __debugbreak();
    }
  }
  v26 = NetUI::Node::Add(v30, (struct Node *)v28[0]);
  if ( v26 < 0 )
  {
    CrashWithRecoveryHrTag(v26, 0x1E48C04Fu);
    __debugbreak();
  }
  Jot::CLabelElement::UpdateVisiblity(*a3);
  v27 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *((char *)*a3 + 16);
  NetUI::Node::SetID(v30, v27);
  return v30;
}

```

## disassembly

```asm
0x140153c30  mov     [rsp-38h+arg_10], rbx
0x140153c35  mov     [rsp-38h+arg_0], rcx
0x140153c3a  push    rbp
0x140153c3b  push    rsi
0x140153c3c  push    rdi
0x140153c3d  push    r12
0x140153c3f  push    r13
0x140153c41  push    r14
0x140153c43  push    r15
0x140153c45  mov     rbp, rsp
0x140153c48  sub     rsp, 30h
0x140153c4c  mov     r15, r8
0x140153c4f  mov     r12, rdx
0x140153c52  cmp     qword ptr [rdx+90h], 0
0x140153c5a  jnz     short loc_140153C63
0x140153c5c  xor     eax, eax
0x140153c5e  jmp     loc_140153E27
0x140153c63  mov     [rbp+arg_8], 0
0x140153c6b  lea     rcx, [rbp+arg_8]
0x140153c6f  call    cs:__imp_?Create@GroupBox@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::GroupBox::Create(NetUI::Element * *)
0x140153c75  test    eax, eax
0x140153c77  jns     short loc_140153C87
0x140153c79  mov     edx, 1E48C054h
0x140153c7e  mov     ecx, eax
0x140153c80  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x140153c86  int     3; Trap to Debugger
0x140153c87  mov     [rbp+arg_18], 0
0x140153c8f  lea     rcx, [rbp+arg_18]
0x140153c93  call    cs:__imp_?Create@GroupHeader@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::GroupHeader::Create(NetUI::Element * *)
0x140153c99  test    eax, eax
0x140153c9b  jns     short loc_140153CAB
0x140153c9d  mov     edx, 1E48C053h
0x140153ca2  mov     ecx, eax
0x140153ca4  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x140153caa  int     3; Trap to Debugger
0x140153cab  mov     rcx, [rbp+arg_18]; this
0x140153caf  call    ?SetIsAcceleratorIgnored@SimpleButton@NetUI@@QEAAJ_N@Z; NetUI::SimpleButton::SetIsAcceleratorIgnored(bool)
0x140153cb4  lea     r14, [r12+80h]
0x140153cbc  mov     rdx, r14
0x140153cbf  cmp     qword ptr [r14+18h], 7
0x140153cc4  jbe     short loc_140153CC9
0x140153cc6  mov     rdx, [r14]; wchar_t *
0x140153cc9  mov     rcx, [rbp+arg_18]; this
0x140153ccd  call    ?SetTextString@Element@NetUI@@QEAAJPEB_W@Z; NetUI::Element::SetTextString(wchar_t const *)
0x140153cd2  mov     rdx, [rbp+arg_18]
0x140153cd6  mov     rcx, [rbp+arg_8]
0x140153cda  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x140153ce0  test    eax, eax
0x140153ce2  jns     short loc_140153CF2
0x140153ce4  mov     edx, 1E48C052h
0x140153ce9  mov     ecx, eax
0x140153ceb  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x140153cf1  int     3; Trap to Debugger
0x140153cf2  mov     [rbp+var_10], 0
0x140153cfa  lea     rcx, [rbp+var_10]
0x140153cfe  call    cs:__imp_?Create@GroupContent@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::GroupContent::Create(NetUI::Element * *)
0x140153d04  test    eax, eax
0x140153d06  jns     short loc_140153D16
0x140153d08  mov     edx, 1E48C051h
0x140153d0d  mov     ecx, eax
0x140153d0f  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x140153d15  int     3; Trap to Debugger
0x140153d16  mov     rax, [r12]
0x140153d1a  mov     rcx, r12
0x140153d1d  mov     rax, [rax+140h]
0x140153d24  call    cs:__guard_dispatch_icall_fptr
0x140153d2a  mov     r13d, eax
0x140153d2d  mov     ecx, 80h; this
0x140153d32  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x140153d37  mov     rsi, rax
0x140153d3a  mov     [rbp+var_8], rax
0x140153d3e  test    rax, rax
0x140153d41  jz      short loc_140153D7E
0x140153d43  cmp     qword ptr [r14+18h], 7
0x140153d48  jbe     short loc_140153D4D
0x140153d4a  mov     r14, [r14]
0x140153d4d  mov     rbx, [rbp+arg_8]
0x140153d51  lea     rcx, [rax+10h]
0x140153d55  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CHeapBuffer@_W@2@@MsoCF@@$0A@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CHeapBuffer<wchar_t>>,0>(void)
0x140153d5a  nop
0x140153d5b  xor     eax, eax
0x140153d5d  mov     [rsi+68h], rax
0x140153d61  mov     [rsi+70h], rax
0x140153d65  mov     [rsi+78h], rax
0x140153d69  mov     [rsi], rbx
0x140153d6c  mov     [rsi+8], eax
0x140153d6f  mov     rdx, r14
0x140153d72  lea     rcx, [rsi+10h]
0x140153d76  call    cs:__imp_?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x140153d7c  jmp     short loc_140153D80
0x140153d7e  xor     esi, esi
0x140153d80  mov     rcx, [r15]; this
0x140153d83  cmp     rcx, rsi
0x140153d86  jz      short loc_140153D95
0x140153d88  test    rcx, rcx
0x140153d8b  jz      short loc_140153D92
0x140153d8d  call    ??_GCLabelElement@Jot@@QEAAPEAXI@Z; Jot::CLabelElement::`scalar deleting destructor'(uint)
0x140153d92  mov     [r15], rsi
0x140153d95  xor     edi, edi
0x140153d97  mov     rsi, [rbp+arg_0]
0x140153d9b  cmp     edi, r13d
0x140153d9e  jge     short loc_140153DE2
0x140153da0  mov     rbx, [r15]
0x140153da3  mov     edx, edi; int
0x140153da5  mov     rcx, r12; this
0x140153da8  call    ?GetItem@CNoteTagSet@Jot@@QEBAPEAUINoteTagSearchResult@2@H@Z; Jot::CNoteTagSet::GetItem(int)
0x140153dad  or      r9d, 0FFFFFFFFh; int
0x140153db1  mov     r8, rsi; struct Jot::CNoteTagListener *
0x140153db4  mov     rdx, rax; struct Jot::INoteTagSearchResult *
0x140153db7  mov     rcx, rbx; this
0x140153dba  call    ?AddGroupContents@CLabelElement@Jot@@QEAAPEAVElement@NetUI@@PEAUINoteTagSearchResult@2@PEAVCNoteTagListener@2@H@Z; Jot::CLabelElement::AddGroupContents(Jot::INoteTagSearchResult *,Jot::CNoteTagListener *,int)
0x140153dbf  mov     rdx, rax
0x140153dc2  mov     rcx, [rbp+var_10]
0x140153dc6  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x140153dcc  test    eax, eax
0x140153dce  js      short loc_140153DD4
0x140153dd0  inc     edi
0x140153dd2  jmp     short loc_140153D9B
0x140153dd4  mov     edx, 1E48C050h
0x140153dd9  mov     ecx, eax
0x140153ddb  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x140153de1  int     3; Trap to Debugger
0x140153de2  mov     rdx, [rbp+var_10]
0x140153de6  mov     rcx, [rbp+arg_8]
0x140153dea  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x140153df0  test    eax, eax
0x140153df2  jns     short loc_140153E02
0x140153df4  mov     edx, 1E48C04Fh
0x140153df9  mov     ecx, eax
0x140153dfb  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x140153e01  int     3; Trap to Debugger
0x140153e02  mov     rcx, [r15]; this
0x140153e05  call    ?UpdateVisiblity@CLabelElement@Jot@@QEAAXXZ; Jot::CLabelElement::UpdateVisiblity(void)
0x140153e0a  mov     rcx, [r15]
0x140153e0d  add     rcx, 10h
0x140153e11  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x140153e17  mov     rdx, rax; wchar_t *
0x140153e1a  mov     rcx, [rbp+arg_8]; this
0x140153e1e  call    ?SetID@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetID(wchar_t const *)
0x140153e23  mov     rax, [rbp+arg_8]
0x140153e27  mov     rbx, [rsp+30h+arg_10]
0x140153e2f  add     rsp, 30h
0x140153e33  pop     r15
0x140153e35  pop     r14
0x140153e37  pop     r13
0x140153e39  pop     r12
0x140153e3b  pop     rdi
0x140153e3c  pop     rsi
0x140153e3d  pop     rbp
0x140153e3e  retn
```
