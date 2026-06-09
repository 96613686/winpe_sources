# HubPage::InitNavPane(void)

- ea: `0x18001cde4`
- end: `0x18001cf33`
- name: `?InitNavPane@HubPage@@AEAAJXZ`
- size: `335`
- prototype: `__int64 __fastcall(HubPage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001cf40`

## callees

- `0x18000314c`
- `0x18001cde4`
- `0x18002cd28`
- `0x18002d1ee`
- `0x18002d220`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001cec2`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001cec2`
- `SHELL32!SHGetStockIconInfo` at `0x18001ce88`
- `SHELL32!SHGetStockIconInfo` at `0x18001ce88`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x18001cedd`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x18001cedd`

## string_xrefs

- `0x18001ced3`: `ControlPanelNavLinks`

## pseudocode

```c
__int64 __fastcall HubPage::InitNavPane(IUnknown **this, unsigned __int64 a2)
{
  IUnknown *v3; // rax
  IUnknown *v4; // rbx
  HRESULT v5; // edi
  _QWORD *v6; // rax
  void *ppvOut; // [rsp+30h] [rbp-248h] BYREF
  SHSTOCKICONINFO psii; // [rsp+40h] [rbp-238h] BYREF

  v3 = (IUnknown *)DirectUI::HAllocAndZero((DirectUI *)0x18, a2);
  v4 = v3;
  if ( v3 )
  {
    v3[1].lpVtbl = 0;
    v3->lpVtbl = (struct IUnknownVtbl *)&CControlPanelNavLinks::`vftable';
    LODWORD(v3[2].lpVtbl) = 1;
    ppvOut = 0;
    v5 = CControlPanelNavLinks::AddLinkNotify(v3);
    if ( v5 >= 0 )
    {
      memset_0(&psii.cbSize + 1, 0, 0x21Cu);
      psii.cbSize = 544;
      v5 = SHGetStockIconInfo(SIID_SHIELD, 0x101u, &psii);
      if ( v5 >= 0 )
      {
        v6 = ppvOut;
        ppvOut = 0;
        v6[3] = psii.hIcon;
        v5 = IUnknown_QueryService(
               this[2],
               (const GUID *const)&SID_PerLayoutPropertyBag,
               &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
               &ppvOut);
        if ( v5 >= 0 )
        {
          v5 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppvOut, L"ControlPanelNavLinks", v4);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
        }
      }
    }
    ((void (__fastcall *)(IUnknown *))v4->lpVtbl->Release)(v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001cde4  mov     [rsp+arg_8], rbx
0x18001cde9  mov     [rsp+arg_10], rsi
0x18001cdee  push    rdi
0x18001cdef  sub     rsp, 270h
0x18001cdf6  mov     rax, cs:__security_cookie
0x18001cdfd  xor     rax, rsp
0x18001ce00  mov     [rsp+278h+var_18], rax
0x18001ce08  mov     rsi, rcx
0x18001ce0b  mov     ecx, 18h; this
0x18001ce10  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18001ce15  mov     rbx, rax
0x18001ce18  test    rax, rax
0x18001ce1b  jz      loc_18001CF07
0x18001ce21  lea     rax, ??_7CControlPanelNavLinks@@6B@; const CControlPanelNavLinks::`vftable'
0x18001ce28  mov     qword ptr [rbx+8], 0
0x18001ce30  mov     [rbx], rax
0x18001ce33  mov     rcx, rbx
0x18001ce36  lea     rax, [rsp+278h+ppvOut]
0x18001ce3b  mov     dword ptr [rbx+10h], 1
0x18001ce42  mov     [rsp+278h+var_250], rax
0x18001ce47  mov     [rsp+278h+ppvOut], 0
0x18001ce50  call    ?AddLinkNotify@CControlPanelNavLinks@@QEAAJW4CPNAV_LIST@@PEAUHINSTANCE__@@IHPEAPEAVCControlPanelNavLink@@@Z; CControlPanelNavLinks::AddLinkNotify(CPNAV_LIST,HINSTANCE__ *,uint,int,CControlPanelNavLink * *)
0x18001ce55  mov     edi, eax
0x18001ce57  test    eax, eax
0x18001ce59  js      loc_18001CEF6
0x18001ce5f  xor     edx, edx; Val
0x18001ce61  lea     rcx, [rsp+278h+psii+4]; void *
0x18001ce66  mov     r8d, 21Ch; Size
0x18001ce6c  call    memset_0
0x18001ce71  lea     r8, [rsp+278h+psii]; psii
0x18001ce76  mov     [rsp+278h+psii.cbSize], 220h
0x18001ce7e  mov     edx, 101h; uFlags
0x18001ce83  mov     ecx, 4Dh ; 'M'; siid
0x18001ce88  call    cs:__imp_SHGetStockIconInfo
0x18001ce8e  mov     edi, eax
0x18001ce90  test    eax, eax
0x18001ce92  js      short loc_18001CEF6
0x18001ce94  mov     rax, [rsp+278h+ppvOut]
0x18001ce99  lea     r9, [rsp+278h+ppvOut]; ppvOut
0x18001ce9e  mov     rdx, [rsp+278h+psii.hIcon]
0x18001cea3  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18001ceaa  mov     [rsp+278h+ppvOut], 0
0x18001ceb3  mov     [rax+18h], rdx
0x18001ceb7  lea     rdx, SID_PerLayoutPropertyBag; guidService
0x18001cebe  mov     rcx, [rsi+10h]; punk
0x18001cec2  call    cs:__imp_IUnknown_QueryService
0x18001cec8  mov     edi, eax
0x18001ceca  test    eax, eax
0x18001cecc  js      short loc_18001CEF6
0x18001cece  mov     rcx, [rsp+278h+ppvOut]; propBag
0x18001ced3  lea     rdx, aControlpanelna; "ControlPanelNavLinks"
0x18001ceda  mov     r8, rbx; punk
0x18001cedd  call    cs:__imp_PSPropertyBag_WriteUnknown
0x18001cee3  mov     rcx, [rsp+278h+ppvOut]
0x18001cee8  mov     edi, eax
0x18001ceea  mov     rax, [rcx]
0x18001ceed  mov     rax, [rax+10h]
0x18001cef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cef6  mov     rax, [rbx]
0x18001cef9  mov     rcx, rbx
0x18001cefc  mov     rax, [rax+10h]
0x18001cf00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf05  jmp     short loc_18001CF0C
0x18001cf07  mov     edi, 8007000Eh
0x18001cf0c  mov     eax, edi
0x18001cf0e  mov     rcx, [rsp+278h+var_18]
0x18001cf16  xor     rcx, rsp; StackCookie
0x18001cf19  call    __security_check_cookie
0x18001cf1e  lea     r11, [rsp+278h+var_8]
0x18001cf26  mov     rbx, [r11+18h]
0x18001cf2a  mov     rsi, [r11+20h]
0x18001cf2e  mov     rsp, r11
0x18001cf31  pop     rdi
0x18001cf32  retn
```
