# HubPage::OnNavTaskLinkClicked(int)

- ea: `0x18001d2e0`
- end: `0x18001d4ab`
- name: `?OnNavTaskLinkClicked@HubPage@@UEAAXH@Z`
- size: `459`
- prototype: `void __fastcall(HubPage *__hidden this, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000466c`
- `0x180005fec`
- `0x18001cb78`
- `0x18001d2e0`
- `0x180029c04`
- `0x180029fd8`
- `0x18002a940`
- `0x18002e010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001d3dd`
- `OLEAUT32!__imp_VariantClear` at `0x18001d3dd`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001d39e`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001d39e`
- `USER32!KillTimer` at `0x18001d37e`
- `USER32!KillTimer` at `0x18001d37e`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001d326`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18001d326`
- `DUI70!StrToID` at `0x18001d30a`
- `DUI70!StrToID` at `0x18001d30a`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d316`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d316`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18001d3cf`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18001d3cf`

## string_xrefs

- `0x18001d3b6`: `AccessibilityAdminObject`
- `0x18001d41d`: `AccessibilityAdminObject`

## pseudocode

```c
void __fastcall HubPage::OnNavTaskLinkClicked(HubPage *this, int a2)
{
  DirectUI::Element *v2; // rbx
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  const struct _GUID *v6; // rdx
  const struct _GUID *v7; // r8
  HWND v8; // rcx
  int v9; // eax
  IUnknown *v10; // rcx
  unsigned int v11; // edx
  __int128 v12; // [rsp+20h] [rbp-30h] BYREF
  __int64 v13; // [rsp+30h] [rbp-20h]
  VARIANT var; // [rsp+38h] [rbp-18h] BYREF
  void *ppvOut; // [rsp+80h] [rbp+30h] BYREF
  void *v16; // [rsp+88h] [rbp+38h] BYREF

  if ( a2 == 1 )
  {
    v2 = (DirectUI::Element *)*((_QWORD *)this + 32);
    v4 = StrToID(L"selfvoice");
    Descendent = DirectUI::Element::FindDescendent(v2, v4);
    if ( Descendent && DirectUI::Element::GetSelected(Descendent) )
      DuiVoice::Speak((HubPage *)((char *)this + 264), &Data);
    v8 = (HWND)*((_QWORD *)this + 1);
    v16 = 0;
    v9 = CoCreateInstanceAsAdmin(v8, v6, v7, &v16);
    if ( v9 >= 0 && v16 )
    {
      DuiVoice::Off((HubPage *)((char *)this + 264));
      KillTimer(*((HWND *)this + 41), 0x123u);
      v10 = (IUnknown *)*((_QWORD *)this + 2);
      ppvOut = 0;
      if ( IUnknown_QueryService(
             v10,
             &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
             &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
             &ppvOut) >= 0 )
      {
        memset(&var, 0, sizeof(var));
        if ( PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"AccessibilityAdminObject", &var, 0xDu) < 0 )
        {
          v13 = 0;
          v12 = 0;
          LOWORD(v12) = 13;
          if ( (**(int (__fastcall ***)(void *, GUID *, char *))v16)(
                 v16,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 (char *)&v12 + 8) >= 0 )
            (*(void (__fastcall **)(void *, const WCHAR *, __int128 *))(*(_QWORD *)ppvOut + 32LL))(
              ppvOut,
              L"AccessibilityAdminObject",
              &v12);
        }
        else
        {
          VariantClear(&var);
        }
      }
      CNavigateButton::Navigate(&Data, L"pageAdminSettings", *((struct IUnknown **)this + 2), 0);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvOut);
    }
    else
    {
      if ( (unsigned __int16)v9 != 1223 )
      {
        v11 = 6002;
        if ( (unsigned __int16)v9 != 86 )
          v11 = 6003;
        AccessibilityCplCore::ErrorMessage(this, v11, v9);
      }
      CNavigateButton::Navigate(&Data, &Data, *((struct IUnknown **)this + 2), 0);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  }
}

```

## disassembly

```asm
0x18001d2e0  cmp     edx, 1
0x18001d2e3  jnz     locret_18001D4AA
0x18001d2e9  mov     [rsp-18h+arg_0], rbx
0x18001d2ee  push    rbp
0x18001d2ef  push    rdi
0x18001d2f0  push    r14
0x18001d2f2  mov     rbp, rsp
0x18001d2f5  sub     rsp, 50h
0x18001d2f9  mov     rbx, [rcx+100h]
0x18001d300  mov     rdi, rcx
0x18001d303  lea     rcx, aSelfvoice; "selfvoice"
0x18001d30a  call    cs:__imp_StrToID
0x18001d310  movzx   edx, ax
0x18001d313  mov     rcx, rbx
0x18001d316  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001d31c  xor     ebx, ebx
0x18001d31e  test    rax, rax
0x18001d321  jz      short loc_18001D343
0x18001d323  mov     rcx, rax
0x18001d326  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18001d32c  test    al, al
0x18001d32e  jz      short loc_18001D343
0x18001d330  lea     rcx, [rdi+108h]; this
0x18001d337  lea     rdx, Data; unsigned __int16 *
0x18001d33e  call    ?Speak@DuiVoice@@QEAAJPEBG@Z; DuiVoice::Speak(ushort const *)
0x18001d343  mov     rcx, [rdi+8]; HWND
0x18001d347  lea     r9, [rbp+arg_18]; void **
0x18001d34b  mov     [rbp+arg_18], rbx
0x18001d34f  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18001d354  test    eax, eax
0x18001d356  js      loc_18001D455
0x18001d35c  cmp     [rbp+arg_18], rbx
0x18001d360  jz      loc_18001D455
0x18001d366  lea     rcx, [rdi+108h]; this
0x18001d36d  call    ?Off@DuiVoice@@QEAAXXZ; DuiVoice::Off(void)
0x18001d372  mov     rcx, [rdi+148h]; hWnd
0x18001d379  mov     edx, 123h; uIDEvent
0x18001d37e  call    cs:__imp_KillTimer
0x18001d384  mov     rcx, [rdi+10h]; punk
0x18001d388  lea     r9, [rbp+ppvOut]; ppvOut
0x18001d38c  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18001d393  mov     [rbp+ppvOut], rbx
0x18001d397  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18001d39e  call    cs:__imp_IUnknown_QueryService
0x18001d3a4  test    eax, eax
0x18001d3a6  js      loc_18001D430
0x18001d3ac  mov     rcx, [rbp+ppvOut]; propBag
0x18001d3b0  lea     r8, [rbp+var]; var
0x18001d3b4  xor     eax, eax
0x18001d3b6  lea     rdx, propName; "AccessibilityAdminObject"
0x18001d3bd  xorps   xmm0, xmm0
0x18001d3c0  mov     qword ptr [rbp+var+10h], rax
0x18001d3c4  movups  xmmword ptr [rbp+var], xmm0
0x18001d3c8  lea     r14d, [rax+0Dh]
0x18001d3cc  mov     r9d, r14d; type
0x18001d3cf  call    cs:__imp_PSPropertyBag_ReadType
0x18001d3d5  test    eax, eax
0x18001d3d7  js      short loc_18001D3E5
0x18001d3d9  lea     rcx, [rbp+var]; pvarg
0x18001d3dd  call    cs:__imp_VariantClear
0x18001d3e3  jmp     short loc_18001D430
0x18001d3e5  mov     rcx, [rbp+arg_18]
0x18001d3e9  lea     r8, [rbp+var_28]
0x18001d3ed  xor     eax, eax
0x18001d3ef  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001d3f6  mov     [rbp+var_20], rax
0x18001d3fa  xorps   xmm0, xmm0
0x18001d3fd  movups  xmmword ptr [rbp-30h], xmm0
0x18001d401  mov     [rbp+var_30], r14w
0x18001d406  mov     rax, [rcx]
0x18001d409  mov     rax, [rax]
0x18001d40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d411  test    eax, eax
0x18001d413  js      short loc_18001D430
0x18001d415  mov     rcx, [rbp+ppvOut]
0x18001d419  lea     r8, [rbp+var_30]
0x18001d41d  lea     rdx, propName; "AccessibilityAdminObject"
0x18001d424  mov     rax, [rcx]
0x18001d427  mov     rax, [rax+20h]
0x18001d42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d430  mov     r8, [rdi+10h]; struct IUnknown *
0x18001d434  lea     rdx, aPageadminsetti; "pageAdminSettings"
0x18001d43b  xor     r9d, r9d; bool
0x18001d43e  lea     rcx, Data; unsigned __int16 *
0x18001d445  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x18001d44a  lea     rcx, [rbp+ppvOut]
0x18001d44e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d453  jmp     short loc_18001D494
0x18001d455  movzx   ecx, ax
0x18001d458  cmp     ecx, 4C7h
0x18001d45e  jz      short loc_18001D47A
0x18001d460  cmp     ecx, 56h ; 'V'
0x18001d463  mov     r8d, eax; int
0x18001d466  mov     rcx, rdi; this
0x18001d469  mov     edx, 1772h
0x18001d46e  jz      short loc_18001D475
0x18001d470  mov     edx, 1773h; unsigned int
0x18001d475  call    ?ErrorMessage@AccessibilityCplCore@@AEAAXIJ@Z; AccessibilityCplCore::ErrorMessage(uint,long)
0x18001d47a  mov     r8, [rdi+10h]; struct IUnknown *
0x18001d47e  lea     rdx, Data; unsigned __int16 *
0x18001d485  xor     r9d, r9d; bool
0x18001d488  lea     rcx, Data; unsigned __int16 *
0x18001d48f  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x18001d494  lea     rcx, [rbp+arg_18]
0x18001d498  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d49d  mov     rbx, [rsp+50h+arg_0]
0x18001d4a2  add     rsp, 50h
0x18001d4a6  pop     r14
0x18001d4a8  pop     rdi
0x18001d4a9  pop     rbp
0x18001d4aa  retn
```
