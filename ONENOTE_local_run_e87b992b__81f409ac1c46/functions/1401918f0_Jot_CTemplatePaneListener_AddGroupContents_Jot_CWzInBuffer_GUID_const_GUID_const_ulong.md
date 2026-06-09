# Jot::CTemplatePaneListener::AddGroupContents(Jot::CWzInBuffer &,_GUID const &,_GUID const &,ulong)

- ea: `0x1401918f0`
- end: `0x140191a92`
- name: `?AddGroupContents@CTemplatePaneListener@Jot@@AEAAPEAVElement@NetUI@@AEAVCWzInBuffer@2@AEBU_GUID@@1K@Z`
- size: `418`
- prototype: `struct NetUI::Element *(Jot::CTemplatePaneListener *__hidden this, struct Jot::CWzInBuffer *, const struct _GUID *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400858b8`

## callees

- `0x14000b818`
- `0x1400218f4`
- `0x14002a850`
- `0x1400478e4`
- `0x140048a58`
- `0x1401918f0`
- `0x14019319c`

## import_xrefs

- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1401919d0`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140191a6b`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1401919d0`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140191a6b`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140191a3e`
- `onmain!?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z` at `0x140191a3e`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1401919f6`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1401919f6`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x140191949`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x140191970`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x140191949`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x140191970`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1401919a4`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1401919b6`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1401919a4`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1401919b6`
- `mso40uiWin32Client!__imp_?Create@Hyperlink@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x14019198a`
- `mso40uiWin32Client!__imp_?Create@Hyperlink@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x14019198a`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x14019192f`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x140191959`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x14019192f`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x140191959`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct NetUI::Element *__fastcall Jot::CTemplatePaneListener::AddGroupContents(
        Jot::CTemplatePaneListener *this,
        struct Jot::CWzInBuffer *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        unsigned int a5)
{
  unsigned __int64 v8; // rdx
  unsigned int v9; // r8d
  struct _GUID *v11; // r15
  const wchar_t *v12; // r14
  struct NetUI::Element *v13; // rdi
  NetUI::Element *v14; // rbx
  NetUI::Element *v15; // rbx
  NetUI::Element *v16; // [rsp+20h] [rbp-30h] BYREF
  NetUI::Element *v17; // [rsp+28h] [rbp-28h] BYREF
  struct NetUI::Element *v18[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+48h] [rbp-8h]

  v19 = 0;
  v20 = 0;
  v17 = 0;
  NetUI::Element::Create(0, &v17);
  NetUI::Element::SetExpandToFillHoriz(v17, 1);
  NetUI::Element::SetLayout(v17, 6);
  v16 = 0;
  NetUI::Element::Create(0, &v16);
  NetUI::Element::SetExpandToFillHoriz(v16, 1);
  NetUI::Element::SetLayout(v16, 6);
  NetUI::Element::SetAlignChildren(v16, 3);
  v18[0] = 0;
  NetUI::Hyperlink::Create(v18);
  Jot::CTemplatePaneListener::SetTextWz(v18[0], a2);
  if ( (int)NetUI::Node::Add(v16, (struct Node *)v18[0]) >= 0 && (int)NetUI::Node::Add(v17, (struct Node *)v16) >= 0 )
  {
    v11 = (struct _GUID *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x1A0, v8, v9);
    v18[1] = (struct NetUI::Element *)v11;
    if ( v11 )
    {
      v12 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(a2);
      v13 = v18[0];
      v14 = v17;
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v11[3].Data4);
      *(_QWORD *)&v11->Data1 = v14;
      *(_QWORD *)v11->Data4 = v13;
      v11[1] = *a3;
      v11[2] = *a4;
      v11[3].Data1 = a5;
      Jot::CWzInBuffer::CopyWz((Jot::CWzInBuffer *)v11[3].Data4, v12);
    }
    else
    {
      v11 = 0;
    }
    *Ofc::CListImpl::NewTail((Jot::CTemplatePaneListener *)((char *)this + 80)) = v11;
    v15 = v17;
    if ( (v20 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v19);
    return v15;
  }
  else
  {
    if ( (v20 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v19);
    return 0;
  }
}

```

## disassembly

```asm
0x1401918f0  mov     rax, rsp
0x1401918f3  mov     [rax+8], rbx
0x1401918f7  mov     [rax+10h], rsi
0x1401918fb  mov     [rax+20h], rdi
0x1401918ff  mov     [rax+18h], r8
0x140191903  push    rbp
0x140191904  push    r12
0x140191906  push    r13
0x140191908  push    r14
0x14019190a  push    r15
0x14019190c  mov     rbp, rsp
0x14019190f  sub     rsp, 50h
0x140191913  mov     r12, r9
0x140191916  mov     rbx, rdx
0x140191919  mov     r13, rcx
0x14019191c  xor     esi, esi
0x14019191e  mov     [rbp+var_10], rsi
0x140191922  mov     [rbp+var_8], esi
0x140191925  mov     [rbp+var_28], rsi
0x140191929  lea     rdx, [rbp+var_28]
0x14019192d  xor     ecx, ecx
0x14019192f  call    cs:__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z; NetUI::Element::Create(uint,NetUI::Element * *)
0x140191935  mov     dl, 1; bool
0x140191937  mov     rcx, [rbp+var_28]; this
0x14019193b  call    ?SetExpandToFillHoriz@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillHoriz(bool)
0x140191940  lea     edi, [rsi+6]
0x140191943  mov     edx, edi
0x140191945  mov     rcx, [rbp+var_28]
0x140191949  call    cs:__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z; NetUI::Element::SetLayout(NetUI::DALLayoutType)
0x14019194f  mov     [rbp+var_30], rsi
0x140191953  lea     rdx, [rbp+var_30]
0x140191957  xor     ecx, ecx
0x140191959  call    cs:__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z; NetUI::Element::Create(uint,NetUI::Element * *)
0x14019195f  mov     dl, 1; bool
0x140191961  mov     rcx, [rbp+var_30]; this
0x140191965  call    ?SetExpandToFillHoriz@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillHoriz(bool)
0x14019196a  mov     edx, edi
0x14019196c  mov     rcx, [rbp+var_30]
0x140191970  call    cs:__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z; NetUI::Element::SetLayout(NetUI::DALLayoutType)
0x140191976  lea     edx, [rsi+3]; int
0x140191979  mov     rcx, [rbp+var_30]; this
0x14019197d  call    ?SetAlignChildren@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetAlignChildren(int)
0x140191982  mov     [rbp+var_20], rsi
0x140191986  lea     rcx, [rbp+var_20]
0x14019198a  call    cs:__imp_?Create@Hyperlink@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Hyperlink::Create(NetUI::Element * *)
0x140191990  mov     rdx, rbx; struct Jot::CWzInBuffer *
0x140191993  mov     rcx, [rbp+var_20]; struct NetUI::Element *
0x140191997  call    ?SetTextWz@CTemplatePaneListener@Jot@@CAXPEAVElement@NetUI@@AEAVCWzInBuffer@2@@Z; Jot::CTemplatePaneListener::SetTextWz(NetUI::Element *,Jot::CWzInBuffer &)
0x14019199c  mov     rdx, [rbp+var_20]
0x1401919a0  mov     rcx, [rbp+var_30]
0x1401919a4  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1401919aa  test    eax, eax
0x1401919ac  js      short loc_1401919C0
0x1401919ae  mov     rdx, [rbp+var_30]
0x1401919b2  mov     rcx, [rbp+var_28]
0x1401919b6  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1401919bc  test    eax, eax
0x1401919be  jns     short loc_1401919DD
0x1401919c0  mov     edx, [rbp+var_8]
0x1401919c3  mov     eax, edx
0x1401919c5  shr     eax, 19h
0x1401919c8  test    al, 1
0x1401919ca  jz      short loc_1401919D6
0x1401919cc  lea     rcx, [rbp+var_10]
0x1401919d0  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x1401919d6  xor     eax, eax
0x1401919d8  jmp     loc_140191A74
0x1401919dd  mov     ecx, 1A0h; this
0x1401919e2  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1401919e7  mov     r15, rax
0x1401919ea  mov     [rbp+var_18], rax
0x1401919ee  test    rax, rax
0x1401919f1  jz      short loc_140191A47
0x1401919f3  mov     rcx, rbx
0x1401919f6  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1401919fc  mov     r14, rax
0x1401919ff  mov     rdi, [rbp+var_20]
0x140191a03  mov     rbx, [rbp+var_28]
0x140191a07  lea     rcx, [r15+38h]
0x140191a0b  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x140191a10  nop
0x140191a11  mov     [r15], rbx
0x140191a14  mov     [r15+8], rdi
0x140191a18  mov     rax, [rbp+arg_10]
0x140191a1c  movups  xmm0, xmmword ptr [rax]
0x140191a1f  movdqu  xmmword ptr [r15+10h], xmm0
0x140191a25  movups  xmm1, xmmword ptr [r12]
0x140191a2a  movdqu  xmmword ptr [r15+20h], xmm1
0x140191a30  mov     edx, [rbp+arg_20]
0x140191a33  mov     [r15+30h], edx
0x140191a37  mov     rdx, r14
0x140191a3a  lea     rcx, [r15+38h]
0x140191a3e  call    cs:__imp_?CopyWz@CWzInBuffer@Jot@@QEAAXPEB_W@Z; Jot::CWzInBuffer::CopyWz(wchar_t const *)
0x140191a44  nop
0x140191a45  jmp     short loc_140191A4A
0x140191a47  mov     r15, rsi
0x140191a4a  lea     rcx, [r13+50h]; this
0x140191a4e  call    ?NewTail@CListImpl@Ofc@@IEAAPEAPEAXXZ; Ofc::CListImpl::NewTail(void)
0x140191a53  mov     [rax], r15
0x140191a56  mov     rbx, [rbp+var_28]
0x140191a5a  mov     edx, [rbp+var_8]
0x140191a5d  mov     ecx, edx
0x140191a5f  shr     ecx, 19h
0x140191a62  test    cl, 1
0x140191a65  jz      short loc_140191A71
0x140191a67  lea     rcx, [rbp+var_10]
0x140191a6b  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x140191a71  mov     rax, rbx
0x140191a74  lea     r11, [rsp+50h+var_s0]
0x140191a79  mov     rbx, [r11+30h]
0x140191a7d  mov     rsi, [r11+38h]
0x140191a81  mov     rdi, [r11+48h]
0x140191a85  mov     rsp, r11
0x140191a88  pop     r15
0x140191a8a  pop     r14
0x140191a8c  pop     r13
0x140191a8e  pop     r12
0x140191a90  pop     rbp
0x140191a91  retn
```
