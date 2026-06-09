# COCMFrame::Setup(DirectUI::DUIXmlParser *)

- ea: `0x180033718`
- end: `0x1800338d4`
- name: `?Setup@COCMFrame@@QEAA_NPEAVDUIXmlParser@DirectUI@@@Z`
- size: `444`
- prototype: `bool __fastcall(COCMFrame *__hidden this, struct DirectUI::DUIXmlParser *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003f9ec`

## callees

- `0x18000b2dc`
- `0x180031484`
- `0x180031d28`
- `0x1800334ec`
- `0x180033718`
- `0x180059010`

## import_xrefs

- `USER32!SendMessageW` at `0x18003384c`
- `USER32!SendMessageW` at `0x18003384c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800337f7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800337f7`
- `DUI70!StrToID` at `0x180033738`
- `DUI70!StrToID` at `0x1800337eb`
- `DUI70!StrToID` at `0x180033738`
- `DUI70!StrToID` at `0x1800337eb`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800338bc`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800338bc`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18003388f`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18003388f`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800338a2`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800338a2`
- `DUI70!?SetStyle@CCTreeView@DirectUI@@QEAAKK@Z` at `0x18003381f`
- `DUI70!?SetStyle@CCTreeView@DirectUI@@QEAAKK@Z` at `0x18003381f`
- `DUI70!?GetStyle@CCTreeView@DirectUI@@QEAAKXZ` at `0x18003380f`
- `DUI70!?GetStyle@CCTreeView@DirectUI@@QEAAKXZ` at `0x18003380f`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x1800338b0`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x1800338b0`

## pseudocode

```c
char __fastcall COCMFrame::Setup(COCMFrame *this, struct DirectUI::DUIXmlParser *a2)
{
  COCMFrame *v3; // rcx
  COCMFrame *v4; // rcx
  COCMFrame *v5; // rcx
  COCMFrame *v6; // rcx
  CWindowFeaturesData **v7; // rsi
  unsigned __int64 v8; // rdx
  CWindowFeaturesData *v9; // rax
  CWindowFeaturesData *v10; // rbx
  unsigned __int16 v11; // ax
  DirectUI::CCTreeView *Descendent; // rax
  DirectUI::CCTreeView *v13; // rbx
  unsigned int Style; // eax
  HWND v15; // rax
  CWindowFeaturesData *v16; // rbx
  HWND v17; // rax
  DirectUI::Element **v18; // rbx

  *((_QWORD *)this + 33) = a2;
  COCMFrame::s_idClose = StrToID(L"close");
  *((_QWORD *)this + 35) = COCMFrame::FindDescendentByName(v3, this, L"ok");
  *((_QWORD *)this + 36) = COCMFrame::FindDescendentByName(v4, this, L"cancel");
  *((_QWORD *)this + 37) = COCMFrame::FindDescendentByName(v5, this, L"help");
  *((_QWORD *)this + 40) = COCMFrame::FindDescendentByName(v6, this, L"waittext");
  v7 = (CWindowFeaturesData **)((char *)this + 336);
  v9 = (CWindowFeaturesData *)DirectUI::HAllocAndZero((DirectUI *)0x28, v8);
  v10 = v9;
  if ( v9 )
  {
    *(_DWORD *)v9 = 1;
    *((_QWORD *)v9 + 3) = 0;
    *((_QWORD *)v9 + 4) = 0;
  }
  else
  {
    v10 = 0;
  }
  CTSmartObj<CWindowFeaturesData *,CTSmartPtr_PolicyComplete<CTContainer_PolicyRelease<CWindowFeaturesData>>>::Release((char *)this + 336);
  *v7 = v10;
  if ( v10 )
  {
    v11 = StrToID(L"treeview");
    Descendent = DirectUI::Element::FindDescendent(this, v11);
    *((_QWORD *)this + 41) = Descendent;
    v13 = Descendent;
    if ( Descendent )
    {
      Style = DirectUI::CCTreeView::GetStyle(Descendent);
      DirectUI::CCTreeView::SetStyle(v13, Style | 0x815);
      v15 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 41) + 360LL))(*((_QWORD *)this + 41));
      SendMessageW(v15, 0x112Cu, 0x80u, 128);
      v16 = *v7;
      v17 = (HWND)(*(__int64 (__fastcall **)(COCMFrame *))(*(_QWORD *)this + 360LL))(this);
      CWindowFeaturesData::BeginEnumeration(v16, v17);
    }
  }
  v18 = (DirectUI::Element **)((char *)this + 304);
  *((_QWORD *)this + 39) = 0;
  DirectUI::Element::Create(0, this, 0, (struct DirectUI::Element **)this + 38);
  if ( *((_QWORD *)this + 38) )
  {
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 38), -2);
    DirectUI::Element::SetBackgroundColor(*v18, 0x4000FFFFu);
    DirectUI::Element::Add(this, *v18);
  }
  return 1;
}

```

## disassembly

```asm
0x180033718  mov     [rsp+arg_0], rbx
0x18003371d  mov     [rsp+arg_8], rsi
0x180033722  push    rdi
0x180033723  sub     rsp, 20h
0x180033727  mov     rdi, rcx
0x18003372a  mov     [rcx+108h], rdx
0x180033731  lea     rcx, aClose; "close"
0x180033738  call    cs:__imp_StrToID
0x18003373e  lea     r8, aOk; "ok"
0x180033745  mov     rdx, rdi; struct DirectUI::Element *
0x180033748  mov     cs:?s_idClose@COCMFrame@@2GA, ax; ushort COCMFrame::s_idClose
0x18003374f  call    ?FindDescendentByName@COCMFrame@@QEAAPEAVElement@DirectUI@@PEAV23@PEBG@Z; COCMFrame::FindDescendentByName(DirectUI::Element *,ushort const *)
0x180033754  lea     r8, aCancel; "cancel"
0x18003375b  mov     [rdi+118h], rax
0x180033762  mov     rdx, rdi; struct DirectUI::Element *
0x180033765  call    ?FindDescendentByName@COCMFrame@@QEAAPEAVElement@DirectUI@@PEAV23@PEBG@Z; COCMFrame::FindDescendentByName(DirectUI::Element *,ushort const *)
0x18003376a  lea     r8, aHelp; "help"
0x180033771  mov     [rdi+120h], rax
0x180033778  mov     rdx, rdi; struct DirectUI::Element *
0x18003377b  call    ?FindDescendentByName@COCMFrame@@QEAAPEAVElement@DirectUI@@PEAV23@PEBG@Z; COCMFrame::FindDescendentByName(DirectUI::Element *,ushort const *)
0x180033780  lea     r8, aWaittext; "waittext"
0x180033787  mov     [rdi+128h], rax
0x18003378e  mov     rdx, rdi; struct DirectUI::Element *
0x180033791  call    ?FindDescendentByName@COCMFrame@@QEAAPEAVElement@DirectUI@@PEAV23@PEBG@Z; COCMFrame::FindDescendentByName(DirectUI::Element *,ushort const *)
0x180033796  mov     ecx, 28h ; '('; this
0x18003379b  mov     [rdi+140h], rax
0x1800337a2  lea     rsi, [rdi+150h]
0x1800337a9  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800337ae  mov     rbx, rax
0x1800337b1  test    rax, rax
0x1800337b4  jz      short loc_1800337CE
0x1800337b6  mov     dword ptr [rax], 1
0x1800337bc  mov     qword ptr [rax+18h], 0
0x1800337c4  mov     qword ptr [rax+20h], 0
0x1800337cc  jmp     short loc_1800337D0
0x1800337ce  xor     ebx, ebx
0x1800337d0  mov     rcx, rsi
0x1800337d3  call    ?Release@?$CTSmartObj@PEAVCWindowFeaturesData@@V?$CTSmartPtr_PolicyComplete@V?$CTContainer_PolicyRelease@VCWindowFeaturesData@@@@@@@@QEAAXXZ; CTSmartObj<CWindowFeaturesData *,CTSmartPtr_PolicyComplete<CTContainer_PolicyRelease<CWindowFeaturesData>>>::Release(void)
0x1800337d8  mov     [rsi], rbx
0x1800337db  test    rbx, rbx
0x1800337de  jz      loc_180033872
0x1800337e4  lea     rcx, aTreeview; "treeview"
0x1800337eb  call    cs:__imp_StrToID
0x1800337f1  movzx   edx, ax
0x1800337f4  mov     rcx, rdi
0x1800337f7  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800337fd  mov     [rdi+148h], rax
0x180033804  mov     rbx, rax
0x180033807  test    rax, rax
0x18003380a  jz      short loc_180033872
0x18003380c  mov     rcx, rax
0x18003380f  call    cs:__imp_?GetStyle@CCTreeView@DirectUI@@QEAAKXZ; DirectUI::CCTreeView::GetStyle(void)
0x180033815  or      eax, 815h
0x18003381a  mov     rcx, rbx
0x18003381d  mov     edx, eax
0x18003381f  call    cs:__imp_?SetStyle@CCTreeView@DirectUI@@QEAAKK@Z; DirectUI::CCTreeView::SetStyle(ulong)
0x180033825  mov     rcx, [rdi+148h]
0x18003382c  mov     rax, [rcx]
0x18003382f  mov     rax, [rax+168h]
0x180033836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003383b  mov     r8d, 80h; wParam
0x180033841  mov     rcx, rax; hWnd
0x180033844  mov     r9d, r8d; lParam
0x180033847  mov     edx, 112Ch; Msg
0x18003384c  call    cs:__imp_SendMessageW
0x180033852  mov     rax, [rdi]
0x180033855  mov     rcx, rdi
0x180033858  mov     rbx, [rsi]
0x18003385b  mov     rax, [rax+168h]
0x180033862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033867  mov     rdx, rax; HWND
0x18003386a  mov     rcx, rbx; this
0x18003386d  call    ?BeginEnumeration@CWindowFeaturesData@@QEAAJPEAUHWND__@@@Z; CWindowFeaturesData::BeginEnumeration(HWND__ *)
0x180033872  lea     rbx, [rdi+130h]
0x180033879  mov     qword ptr [rdi+138h], 0
0x180033884  mov     r9, rbx
0x180033887  xor     r8d, r8d
0x18003388a  mov     rdx, rdi
0x18003388d  xor     ecx, ecx
0x18003388f  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180033895  mov     rcx, [rbx]
0x180033898  test    rcx, rcx
0x18003389b  jz      short loc_1800338C2
0x18003389d  mov     edx, 0FFFFFFFEh
0x1800338a2  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800338a8  mov     rcx, [rbx]
0x1800338ab  mov     edx, 4000FFFFh
0x1800338b0  call    cs:__imp_?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetBackgroundColor(ulong)
0x1800338b6  mov     rdx, [rbx]
0x1800338b9  mov     rcx, rdi
0x1800338bc  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x1800338c2  mov     rbx, [rsp+28h+arg_0]
0x1800338c7  mov     al, 1
0x1800338c9  mov     rsi, [rsp+28h+arg_8]
0x1800338ce  add     rsp, 20h
0x1800338d2  pop     rdi
0x1800338d3  retn
```
