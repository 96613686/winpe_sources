# Windows::Internal::FlyoutElement::Create(HWND__ *,bool,int,uint,DirectUI::Element *,bool,ulong *,DirectUI::Element * *)

- ea: `0x18002a4dc`
- end: `0x18002a658`
- name: `?Create@FlyoutElement@Internal@Windows@@SAJPEAUHWND__@@_NHIPEAVElement@DirectUI@@1PEAKPEAPEAV56@@Z`
- size: `380`
- prototype: `__int64 __fastcall(HWND, bool, int, unsigned int, struct DirectUI::Element *, bool, unsigned int *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180044ff4`

## callees

- `0x18002a4dc`
- `0x18003c694`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a501`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a501`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a515`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a515`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a59c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a59c`
- `DUI70!??0TouchHWNDElement@DirectUI@@QEAA@XZ` at `0x18002a52a`
- `DUI70!??0TouchHWNDElement@DirectUI@@QEAA@XZ` at `0x18002a52a`
- `DUI70!?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x18002a56c`
- `DUI70!?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z` at `0x18002a56c`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18002a5c6`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18002a5c6`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18002a604`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18002a604`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002a623`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002a623`
- `DUI70!StrToID` at `0x18002a617`
- `DUI70!StrToID` at `0x18002a617`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18002a645`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18002a645`

## pseudocode

```c
__int64 __fastcall Windows::Internal::FlyoutElement::Create(
        HWND a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        struct DirectUI::Element *a5,
        bool a6,
        unsigned int *a7,
        struct DirectUI::Element **a8)
{
  struct DirectUI::Element **v8; // r14
  int Element; // ebx
  HANDLE ProcessHeap; // rax
  DirectUI::TouchHWNDElement *v13; // rax
  DirectUI::TouchHWNDElement *v14; // rdi
  DirectUI::DUIXmlParser **Value; // rax
  DirectUI::DUIXmlParser *v16; // rsi
  unsigned __int16 v17; // ax
  struct DirectUI::Element *Descendent; // rax

  v8 = a8;
  Element = -2147024882;
  *a8 = 0;
  ProcessHeap = GetProcessHeap();
  v13 = (DirectUI::TouchHWNDElement *)HeapAlloc(ProcessHeap, 8u, 0x1B0u);
  v14 = v13;
  if ( v13 )
  {
    DirectUI::TouchHWNDElement::TouchHWNDElement(v13);
    *(_QWORD *)v14 = &Windows::Internal::FlyoutElement::`vftable';
    *((_BYTE *)v14 + 424) = a6;
    Element = DirectUI::TouchHWNDElement::Initialize(v14, a1, 1, 0x18u, 0, a7);
    if ( Element < 0 )
      goto LABEL_10;
    Element = -2147024882;
    a8 = 0;
    if ( dwTlsIndex == -1 )
      goto LABEL_10;
    Value = (DirectUI::DUIXmlParser **)TlsGetValue(dwTlsIndex);
    if ( !Value )
      goto LABEL_10;
    v16 = *Value;
    if ( *Value
      && (Element = DirectUI::DUIXmlParser::SetXMLFromResource(*Value, a3, &_ImageBase, &_ImageBase), Element >= 0)
      && (a8 = 0,
          Element = DirectUI::DUIXmlParser::CreateElement(v16, L"main", v14, 0, 0, (struct DirectUI::Element **)&a8),
          Element >= 0)
      && (v17 = StrToID(L"ButtonBar"),
          Descendent = DirectUI::Element::FindDescendent(v14, v17),
          Element = Windows::Internal::ButtonBarLayout::CreateAndAttachButtonBarLayout(Descendent),
          Element >= 0) )
    {
      *v8 = v14;
    }
    else
    {
LABEL_10:
      DirectUI::Element::Destroy(v14, 0);
    }
  }
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x18002a4dc  push    rbx
0x18002a4de  push    rbp
0x18002a4df  push    rsi
0x18002a4e0  push    rdi
0x18002a4e1  push    r14
0x18002a4e3  sub     rsp, 30h
0x18002a4e7  mov     r14, [rsp+58h+arg_38]
0x18002a4ef  mov     ebp, r8d
0x18002a4f2  mov     rsi, rcx
0x18002a4f5  mov     ebx, 8007000Eh
0x18002a4fa  mov     qword ptr [r14], 0
0x18002a501  call    cs:__imp_GetProcessHeap
0x18002a507  mov     edx, 8; dwFlags
0x18002a50c  mov     r8d, 1B0h; dwBytes
0x18002a512  mov     rcx, rax; hHeap
0x18002a515  call    cs:__imp_HeapAlloc
0x18002a51b  mov     rdi, rax
0x18002a51e  test    rax, rax
0x18002a521  jz      loc_18002A64B
0x18002a527  mov     rcx, rax
0x18002a52a  call    cs:__imp_??0TouchHWNDElement@DirectUI@@QEAA@XZ; DirectUI::TouchHWNDElement::TouchHWNDElement(void)
0x18002a530  lea     rax, ??_7FlyoutElement@Internal@Windows@@6B@; const Windows::Internal::FlyoutElement::`vftable'
0x18002a537  mov     r9d, 18h
0x18002a53d  mov     [rdi], rax
0x18002a540  mov     r8b, 1
0x18002a543  mov     al, [rsp+58h+arg_28]
0x18002a54a  mov     rdx, rsi
0x18002a54d  mov     [rdi+1A8h], al
0x18002a553  mov     rcx, rdi
0x18002a556  mov     rax, [rsp+58h+arg_30]
0x18002a55e  mov     [rsp+58h+var_30], rax
0x18002a563  mov     [rsp+58h+var_38], 0
0x18002a56c  call    cs:__imp_?Initialize@TouchHWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z; DirectUI::TouchHWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)
0x18002a572  mov     ebx, eax
0x18002a574  test    eax, eax
0x18002a576  js      loc_18002A640
0x18002a57c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18002a582  mov     ebx, 8007000Eh
0x18002a587  mov     [rsp+58h+arg_38], 0
0x18002a593  cmp     ecx, 0FFFFFFFFh
0x18002a596  jz      loc_18002A63C
0x18002a59c  call    cs:__imp_TlsGetValue
0x18002a5a2  test    rax, rax
0x18002a5a5  jz      loc_18002A63C
0x18002a5ab  mov     rsi, [rax]
0x18002a5ae  test    rsi, rsi
0x18002a5b1  jz      loc_18002A63C
0x18002a5b7  lea     r8, __ImageBase
0x18002a5be  mov     edx, ebp
0x18002a5c0  mov     r9, r8
0x18002a5c3  mov     rcx, rsi
0x18002a5c6  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18002a5cc  mov     ebx, eax
0x18002a5ce  test    eax, eax
0x18002a5d0  js      short loc_18002A63C
0x18002a5d2  lea     rax, [rsp+58h+arg_38]
0x18002a5da  mov     [rsp+58h+arg_38], 0
0x18002a5e6  mov     [rsp+58h+var_30], rax
0x18002a5eb  lea     rdx, aMain; "main"
0x18002a5f2  xor     r9d, r9d
0x18002a5f5  mov     [rsp+58h+var_38], 0
0x18002a5fe  mov     r8, rdi
0x18002a601  mov     rcx, rsi
0x18002a604  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18002a60a  mov     ebx, eax
0x18002a60c  test    eax, eax
0x18002a60e  js      short loc_18002A63C
0x18002a610  lea     rcx, aButtonbar; "ButtonBar"
0x18002a617  call    cs:__imp_StrToID
0x18002a61d  movzx   edx, ax
0x18002a620  mov     rcx, rdi
0x18002a623  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002a629  mov     rcx, rax; struct DirectUI::Element *
0x18002a62c  call    ?CreateAndAttachButtonBarLayout@ButtonBarLayout@Internal@Windows@@SAJPEAVElement@DirectUI@@@Z; Windows::Internal::ButtonBarLayout::CreateAndAttachButtonBarLayout(DirectUI::Element *)
0x18002a631  mov     ebx, eax
0x18002a633  test    eax, eax
0x18002a635  js      short loc_18002A640
0x18002a637  mov     [r14], rdi
0x18002a63a  jmp     short loc_18002A64B
0x18002a63c  test    ebx, ebx
0x18002a63e  jns     short loc_18002A64B
0x18002a640  xor     edx, edx
0x18002a642  mov     rcx, rdi
0x18002a645  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18002a64b  mov     eax, ebx
0x18002a64d  add     rsp, 30h
0x18002a651  pop     r14
0x18002a653  pop     rdi
0x18002a654  pop     rsi
0x18002a655  pop     rbp
0x18002a656  pop     rbx
0x18002a657  retn
```
