# Jot::CJotApp::XMainAppUser::RaiseReadTextAloudEvent(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Jot::UIANotificationKind)

- ea: `0x1400b0070`
- end: `0x1400b046b`
- name: `?RaiseReadTextAloudEvent@XMainAppUser@CJotApp@Jot@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UIANotificationKind@3@@Z`
- size: `1019`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140057580`
- `0x1400b0070`
- `0x1400b046c`

## import_xrefs

- `onmain!?DisableCanvasAccessibility@Jot@@YAAEBVFeatureGate@Optimized@AB@Mso@@XZ` at `0x1400b0434`
- `onmain!?DisableCanvasAccessibility@Jot@@YAAEBVFeatureGate@Optimized@AB@Mso@@XZ` at `0x1400b0434`
- `OLEACC!ObjectFromLresult` at `0x1400b01a4`
- `OLEACC!ObjectFromLresult` at `0x1400b0294`
- `OLEACC!ObjectFromLresult` at `0x1400b0422`
- `OLEACC!ObjectFromLresult` at `0x1400b01a4`
- `OLEACC!ObjectFromLresult` at `0x1400b0294`
- `OLEACC!ObjectFromLresult` at `0x1400b0422`
- `OLEAUT32!__imp_SysFreeString` at `0x1400b0132`
- `OLEAUT32!__imp_SysFreeString` at `0x1400b0132`
- `UIAutomationCore!UiaProviderFromIAccessible` at `0x1400b01c0`
- `UIAutomationCore!UiaProviderFromIAccessible` at `0x1400b02c9`
- `UIAutomationCore!UiaProviderFromIAccessible` at `0x1400b01c0`
- `UIAutomationCore!UiaProviderFromIAccessible` at `0x1400b02c9`
- `UIAutomationCore!UiaClientsAreListening` at `0x1400b0098`
- `UIAutomationCore!UiaClientsAreListening` at `0x1400b0098`
- `USER32!IsWindow` at `0x1400b02eb`
- `USER32!IsWindow` at `0x1400b02eb`
- `USER32!SendMessageW` at `0x1400b0161`
- `USER32!SendMessageW` at `0x1400b0180`
- `USER32!SendMessageW` at `0x1400b0406`
- `USER32!SendMessageW` at `0x1400b0161`
- `USER32!SendMessageW` at `0x1400b0180`
- `USER32!SendMessageW` at `0x1400b0406`
- `USER32!GetFocus` at `0x1400b00a2`
- `USER32!GetFocus` at `0x1400b00a2`
- `USER32!IsWindowVisible` at `0x1400b00be`
- `USER32!IsWindowVisible` at `0x1400b00be`
- `mso40uiWin32Client!__imp_?SimpleRaiseUiaNotificationWithCheckImport@WinUia@NetUI@@YAJAEAUIRawElementProviderSimple@@W4NotificationKind@@W4NotificationProcessing@@PEA_W3@Z` at `0x1400b0278`
- `mso40uiWin32Client!__imp_?SimpleRaiseUiaNotificationWithCheckImport@WinUia@NetUI@@YAJAEAUIRawElementProviderSimple@@W4NotificationKind@@W4NotificationProcessing@@PEA_W3@Z` at `0x1400b0278`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1400b0446`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1400b0446`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Jot::CJotApp::XMainAppUser::RaiseReadTextAloudEvent(__int64 a1, const wchar_t *a2, int a3)
{
  HWND Focus; // rbx
  HWND *v7; // rsi
  int v8; // eax
  OLECHAR *v9; // rbx
  HRESULT v10; // r14d
  LRESULT v11; // rax
  LRESULT v12; // rax
  Jot *v13; // rcx
  BSTR v14; // rcx
  BSTR v15; // rbx
  __int64 v16; // rdx
  int v17; // edi
  __int64 v18; // rdx
  int v19; // edi
  Jot::CJotApp *v20; // rsi
  __int64 v21; // r12
  __int64 v22; // rax
  LRESULT v23; // rax
  Mso::AB::Optimized::FeatureGate *v24; // rax
  wchar_t *v25; // [rsp+28h] [rbp-18h]
  void *ppvObject; // [rsp+30h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+48h] BYREF

  if ( !UiaClientsAreListening() )
    return;
  Focus = GetFocus();
  v7 = (HWND *)(a1 + 232);
  if ( !Focus )
  {
    if ( !*v7 )
      return;
    if ( !IsWindow(*v7) )
      return;
    Focus = *v7;
    if ( !*v7 )
      return;
  }
  if ( !IsWindowVisible(Focus) )
    return;
  if ( !*(_QWORD *)(a1 + 240) || *v7 != Focus )
  {
    bstrString = 0;
    v10 = -2147467259;
    v11 = SendMessageW(Focus, 0x3Du, 0x4334u, -16);
    if ( v11 )
    {
      v10 = ObjectFromLresult(v11, &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c, 0, (void **)&bstrString);
      if ( v10 >= 0 )
        goto LABEL_20;
    }
    v12 = SendMessageW(Focus, 0x3Du, 0x4334u, -4);
    if ( v12 )
    {
      ppvObject = 0;
      if ( ObjectFromLresult(v12, &GUID_618736e0_3c3d_11cf_810c_00aa00389b71, 0, &ppvObject) < 0
        || (v10 = UiaProviderFromIAccessible((IAccessible *)ppvObject, 0, 0, (IRawElementProviderSimple **)&bstrString),
            v10 < 0) )
      {
        v10 = UiaProviderFromIAccessible((IAccessible *)ppvObject, 0, 1u, (IRawElementProviderSimple **)&bstrString);
      }
      v13 = (Jot *)ppvObject;
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    }
    if ( v10 >= 0 )
      goto LABEL_20;
    v20 = Jot::CJotApp::s_pSingletonJotApp;
    if ( Jot::CJotApp::s_pSingletonJotApp )
      v20 = (Jot::CJotApp *)*((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 58);
    if ( v20 )
      v20 = (Jot::CJotApp *)*((_QWORD *)v20 + 14);
    if ( v20 )
      v21 = (*(__int64 (__fastcall **)(Jot::CJotApp *, _QWORD))(*(_QWORD *)v20 + 152LL))(v20, 0);
    else
      v21 = 0;
    if ( v21 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 400LL))(v21) )
        goto LABEL_57;
      Focus = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 24LL))(v21);
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 400LL))(v21);
      v23 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v22 + 128LL))(
              v22,
              61,
              17204,
              -16);
    }
    else
    {
      if ( !v20 || !(*(__int64 (__fastcall **)(Jot::CJotApp *))(*(_QWORD *)v20 + 400LL))(v20) )
        goto LABEL_57;
      Focus = *(HWND *)((*(__int64 (__fastcall **)(Jot::CJotApp *))(*(_QWORD *)v20 + 400LL))(v20) + 8);
      v23 = SendMessageW(Focus, 0x3Du, 0x4334u, -16);
    }
    if ( v23 )
      v10 = ObjectFromLresult(v23, &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c, 0, (void **)&bstrString);
LABEL_57:
    if ( v10 < 0 )
    {
      v24 = Jot::DisableCanvasAccessibility(v13);
      if ( *(char *)v24 < 0 )
        Mso::AB::Optimized::FeatureGate::Evaluate(v24);
      goto LABEL_24;
    }
LABEL_20:
    *(_QWORD *)(a1 + 232) = Focus;
    v14 = bstrString;
    v15 = bstrString;
    if ( bstrString )
    {
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 8LL))(bstrString);
      v14 = bstrString;
    }
    v16 = *(_QWORD *)(a1 + 240);
    *(_QWORD *)(a1 + 240) = v15;
    if ( !v16 )
      goto LABEL_25;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
LABEL_24:
    v14 = bstrString;
LABEL_25:
    if ( v14 )
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)v14 + 16LL))(v14);
  }
  if ( *(_QWORD *)(a1 + 240) )
  {
    bstrString = 0;
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const wchar_t **)a2;
    v8 = Mso::BStrHolder::HrCopyWz((Mso::BStrHolder *)&bstrString, a2);
    v9 = bstrString;
    if ( v8 >= 0 )
    {
      if ( a3 )
      {
        v17 = a3 - 1;
        if ( v17 )
        {
          v19 = v17 - 1;
          if ( v19 )
          {
            if ( v19 == 1 )
              v18 = 3;
            else
              v18 = 4;
          }
          else
          {
            v18 = 2;
          }
        }
        else
        {
          v18 = 1;
        }
      }
      else
      {
        v18 = 0;
      }
      NetUI::WinUia::SimpleRaiseUiaNotificationWithCheckImport(
        *(NetUI::WinUia **)(a1 + 240),
        (struct IRawElementProviderSimple *)v18,
        NotificationKind_ItemRemoved,
        (enum NotificationProcessing)bstrString,
        bstrString,
        v25);
    }
    if ( v9 )
      SysFreeString(v9);
  }
}

```

## disassembly

```asm
0x1400b0070  mov     [rsp-28h+arg_0], rbx
0x1400b0075  mov     [rsp-28h+arg_8], rsi
0x1400b007a  mov     [rsp-28h+arg_10], rdi
0x1400b007f  push    rbp
0x1400b0080  push    r12
0x1400b0082  push    r13
0x1400b0084  push    r14
0x1400b0086  push    r15
0x1400b0088  mov     rbp, rsp
0x1400b008b  sub     rsp, 40h
0x1400b008f  mov     edi, r8d
0x1400b0092  mov     r13, rdx
0x1400b0095  mov     r15, rcx
0x1400b0098  call    cs:__imp_UiaClientsAreListening
0x1400b009e  test    eax, eax
0x1400b00a0  jz      short loc_1400B00E1
0x1400b00a2  call    cs:__imp_GetFocus
0x1400b00a8  mov     rbx, rax
0x1400b00ab  lea     rsi, [r15+0E8h]
0x1400b00b2  test    rax, rax
0x1400b00b5  jz      loc_1400B02DF
0x1400b00bb  mov     rcx, rbx; hWnd
0x1400b00be  call    cs:__imp_IsWindowVisible
0x1400b00c4  test    eax, eax
0x1400b00c6  jz      short loc_1400B00E1
0x1400b00c8  cmp     qword ptr [r15+0F0h], 0
0x1400b00d0  jz      short loc_1400B013A
0x1400b00d2  cmp     [rsi], rbx
0x1400b00d5  jnz     short loc_1400B013A
0x1400b00d7  cmp     qword ptr [r15+0F0h], 0
0x1400b00df  jnz     short loc_1400B00FF
0x1400b00e1  lea     r11, [rsp+40h+var_s0]
0x1400b00e6  mov     rbx, [r11+30h]
0x1400b00ea  mov     rsi, [r11+38h]
0x1400b00ee  mov     rdi, [r11+40h]
0x1400b00f2  mov     rsp, r11
0x1400b00f5  pop     r15
0x1400b00f7  pop     r14
0x1400b00f9  pop     r13
0x1400b00fb  pop     r12
0x1400b00fd  pop     rbp
0x1400b00fe  retn
0x1400b00ff  mov     [rbp+bstrString], 0
0x1400b0107  cmp     qword ptr [r13+18h], 7
0x1400b010c  ja      loc_1400B024E
0x1400b0112  mov     rdx, r13; wchar_t *
0x1400b0115  lea     rcx, [rbp+bstrString]; this
0x1400b0119  call    ?HrCopyWz@BStrHolder@Mso@@QEAAJPEB_W@Z; Mso::BStrHolder::HrCopyWz(wchar_t const *)
0x1400b011e  mov     rbx, [rbp+bstrString]
0x1400b0122  test    eax, eax
0x1400b0124  jns     loc_1400B0257
0x1400b012a  test    rbx, rbx
0x1400b012d  jz      short loc_1400B00E1
0x1400b012f  mov     rcx, rbx; bstrString
0x1400b0132  call    cs:__imp_SysFreeString
0x1400b0138  jmp     short loc_1400B00E1
0x1400b013a  mov     [rbp+bstrString], 0
0x1400b0142  mov     esi, 4334h
0x1400b0147  mov     r14d, 80004005h
0x1400b014d  mov     r9, 0FFFFFFFFFFFFFFF0h; lParam
0x1400b0154  mov     r8d, esi; wParam
0x1400b0157  lea     r12d, [r9+4Dh]
0x1400b015b  mov     edx, r12d; Msg
0x1400b015e  mov     rcx, rbx; hWnd
0x1400b0161  call    cs:__imp_SendMessageW
0x1400b0167  test    rax, rax
0x1400b016a  jnz     loc_1400B0283
0x1400b0170  mov     r9, 0FFFFFFFFFFFFFFFCh; lParam
0x1400b0177  mov     r8, rsi; wParam
0x1400b017a  mov     edx, r12d; Msg
0x1400b017d  mov     rcx, rbx; hWnd
0x1400b0180  call    cs:__imp_SendMessageW
0x1400b0186  test    rax, rax
0x1400b0189  jz      short loc_1400B01DF
0x1400b018b  mov     [rbp+ppvObject], 0
0x1400b0193  lea     r9, [rbp+ppvObject]; ppvObject
0x1400b0197  xor     r8d, r8d; wParam
0x1400b019a  lea     rdx, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71; riid
0x1400b01a1  mov     rcx, rax; lResult
0x1400b01a4  call    cs:__imp_ObjectFromLresult
0x1400b01aa  test    eax, eax
0x1400b01ac  jns     loc_1400B02BC
0x1400b01b2  lea     r9, [rbp+bstrString]; ppProvider
0x1400b01b6  xor     edx, edx; idChild
0x1400b01b8  lea     r8d, [rdx+1]; dwFlags
0x1400b01bc  mov     rcx, [rbp+ppvObject]; pAccessible
0x1400b01c0  call    cs:__imp_UiaProviderFromIAccessible
0x1400b01c6  mov     r14d, eax
0x1400b01c9  mov     rcx, [rbp+ppvObject]
0x1400b01cd  test    rcx, rcx
0x1400b01d0  jz      short loc_1400B01DF
0x1400b01d2  mov     rax, [rcx]
0x1400b01d5  mov     rax, [rax+10h]
0x1400b01d9  call    cs:__guard_dispatch_icall_fptr
0x1400b01df  test    r14d, r14d
0x1400b01e2  js      loc_1400B030B
0x1400b01e8  mov     [r15+0E8h], rbx
0x1400b01ef  mov     rcx, [rbp+bstrString]
0x1400b01f3  mov     rbx, rcx
0x1400b01f6  test    rcx, rcx
0x1400b01f9  jz      short loc_1400B020C
0x1400b01fb  mov     rax, [rcx]
0x1400b01fe  mov     rax, [rax+8]
0x1400b0202  call    cs:__guard_dispatch_icall_fptr
0x1400b0208  mov     rcx, [rbp+bstrString]
0x1400b020c  mov     rdx, [r15+0F0h]
0x1400b0213  mov     [r15+0F0h], rbx
0x1400b021a  test    rdx, rdx
0x1400b021d  jz      short loc_1400B0233
0x1400b021f  mov     rax, [rdx]
0x1400b0222  mov     rcx, rdx
0x1400b0225  mov     rax, [rax+10h]
0x1400b0229  call    cs:__guard_dispatch_icall_fptr
0x1400b022f  mov     rcx, [rbp+bstrString]
0x1400b0233  test    rcx, rcx
0x1400b0236  jz      loc_1400B00D7
0x1400b023c  mov     rax, [rcx]
0x1400b023f  mov     rax, [rax+10h]
0x1400b0243  call    cs:__guard_dispatch_icall_fptr
0x1400b0249  jmp     loc_1400B00D7
0x1400b024e  mov     r13, [r13+0]
0x1400b0252  jmp     loc_1400B0112
0x1400b0257  test    edi, edi
0x1400b0259  jz      short loc_1400B02B8
0x1400b025b  sub     edi, 1
0x1400b025e  jnz     short loc_1400B02AA
0x1400b0260  lea     edx, [rdi+1]
0x1400b0263  mov     [rsp+40h+var_20], rbx
0x1400b0268  mov     r9, rbx
0x1400b026b  mov     r8d, 1
0x1400b0271  mov     rcx, [r15+0F0h]
0x1400b0278  call    cs:__imp_?SimpleRaiseUiaNotificationWithCheckImport@WinUia@NetUI@@YAJAEAUIRawElementProviderSimple@@W4NotificationKind@@W4NotificationProcessing@@PEA_W3@Z; NetUI::WinUia::SimpleRaiseUiaNotificationWithCheckImport(IRawElementProviderSimple &,NotificationKind,NotificationProcessing,wchar_t *,wchar_t *)
0x1400b027e  jmp     loc_1400B012A
0x1400b0283  lea     r9, [rbp+bstrString]; ppvObject
0x1400b0287  xor     r8d, r8d; wParam
0x1400b028a  lea     rdx, _GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c; riid
0x1400b0291  mov     rcx, rax; lResult
0x1400b0294  call    cs:__imp_ObjectFromLresult
0x1400b029a  mov     r14d, eax
0x1400b029d  test    eax, eax
0x1400b029f  jns     loc_1400B01E8
0x1400b02a5  jmp     loc_1400B0170
0x1400b02aa  sub     edi, 1
0x1400b02ad  jnz     loc_1400B0451
0x1400b02b3  lea     edx, [rdi+2]
0x1400b02b6  jmp     short loc_1400B0263
0x1400b02b8  xor     edx, edx
0x1400b02ba  jmp     short loc_1400B0263
0x1400b02bc  lea     r9, [rbp+bstrString]; ppProvider
0x1400b02c0  xor     r8d, r8d; dwFlags
0x1400b02c3  xor     edx, edx; idChild
0x1400b02c5  mov     rcx, [rbp+ppvObject]; pAccessible
0x1400b02c9  call    cs:__imp_UiaProviderFromIAccessible
0x1400b02cf  mov     r14d, eax
0x1400b02d2  test    eax, eax
0x1400b02d4  jns     loc_1400B01C9
0x1400b02da  jmp     loc_1400B01B2
0x1400b02df  mov     rcx, [rsi]; hWnd
0x1400b02e2  test    rcx, rcx
0x1400b02e5  jz      loc_1400B00E1
0x1400b02eb  call    cs:__imp_IsWindow
0x1400b02f1  cmp     eax, 1
0x1400b02f4  jnz     loc_1400B00E1
0x1400b02fa  mov     rbx, [rsi]
0x1400b02fd  test    rbx, rbx
0x1400b0300  jz      loc_1400B00E1
0x1400b0306  jmp     loc_1400B00BB
0x1400b030b  mov     rsi, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1400b0312  test    rsi, rsi
0x1400b0315  jz      short loc_1400B031E
0x1400b0317  mov     rsi, [rsi+1D0h]
0x1400b031e  test    rsi, rsi
0x1400b0321  jz      short loc_1400B0327
0x1400b0323  mov     rsi, [rsi+70h]
0x1400b0327  test    rsi, rsi
0x1400b032a  jz      short loc_1400B0346
0x1400b032c  mov     rax, [rsi]
0x1400b032f  xor     edx, edx
0x1400b0331  mov     rcx, rsi
0x1400b0334  mov     rax, [rax+98h]
0x1400b033b  call    cs:__guard_dispatch_icall_fptr
0x1400b0341  mov     r12, rax
0x1400b0344  jmp     short loc_1400B0349
0x1400b0346  xor     r12d, r12d
0x1400b0349  test    r12, r12
0x1400b034c  jz      short loc_1400B03BD
0x1400b034e  mov     rax, [r12]
0x1400b0352  mov     rcx, r12
0x1400b0355  mov     rax, [rax+190h]
0x1400b035c  call    cs:__guard_dispatch_icall_fptr
0x1400b0362  test    rax, rax
0x1400b0365  jz      loc_1400B042B
0x1400b036b  mov     rax, [r12]
0x1400b036f  mov     rcx, r12
0x1400b0372  mov     rax, [rax+18h]
0x1400b0376  call    cs:__guard_dispatch_icall_fptr
0x1400b037c  mov     rbx, rax
0x1400b037f  mov     rax, [r12]
0x1400b0383  mov     rcx, r12
0x1400b0386  mov     rax, [rax+190h]
0x1400b038d  call    cs:__guard_dispatch_icall_fptr
0x1400b0393  mov     r10, rax
0x1400b0396  mov     rcx, [rax]
0x1400b0399  mov     rax, [rcx+80h]
0x1400b03a0  mov     edx, 3Dh ; '='
0x1400b03a5  mov     r9, 0FFFFFFFFFFFFFFF0h
0x1400b03ac  mov     r8d, 4334h
0x1400b03b2  mov     rcx, r10
0x1400b03b5  call    cs:__guard_dispatch_icall_fptr
0x1400b03bb  jmp     short loc_1400B040C
0x1400b03bd  test    rsi, rsi
0x1400b03c0  jz      short loc_1400B042B
0x1400b03c2  mov     rax, [rsi]
0x1400b03c5  mov     rcx, rsi
0x1400b03c8  mov     rax, [rax+190h]
0x1400b03cf  call    cs:__guard_dispatch_icall_fptr
0x1400b03d5  test    rax, rax
0x1400b03d8  jz      short loc_1400B042B
0x1400b03da  mov     rax, [rsi]
0x1400b03dd  mov     rcx, rsi
0x1400b03e0  mov     rax, [rax+190h]
0x1400b03e7  call    cs:__guard_dispatch_icall_fptr
0x1400b03ed  mov     rbx, [rax+8]
0x1400b03f1  mov     edx, 3Dh ; '='; Msg
0x1400b03f6  mov     r9, 0FFFFFFFFFFFFFFF0h; lParam
0x1400b03fd  mov     r8d, 4334h; wParam
0x1400b0403  mov     rcx, rbx; hWnd
0x1400b0406  call    cs:__imp_SendMessageW
0x1400b040c  test    rax, rax
0x1400b040f  jz      short loc_1400B042B
0x1400b0411  lea     r9, [rbp+bstrString]; ppvObject
0x1400b0415  xor     r8d, r8d; wParam
0x1400b0418  lea     rdx, _GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c; riid
0x1400b041f  mov     rcx, rax; lResult
0x1400b0422  call    cs:__imp_ObjectFromLresult
0x1400b0428  mov     r14d, eax
0x1400b042b  test    r14d, r14d
0x1400b042e  jns     loc_1400B01E8
0x1400b0434  call    cs:__imp_?DisableCanvasAccessibility@Jot@@YAAEBVFeatureGate@Optimized@AB@Mso@@XZ; Jot::DisableCanvasAccessibility(void)
0x1400b043a  cmp     byte ptr [rax], 0
0x1400b043d  jge     loc_1400B022F
0x1400b0443  mov     rcx, rax
0x1400b0446  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x1400b044c  jmp     loc_1400B022F
0x1400b0451  cmp     edi, 1
0x1400b0454  jz      short loc_1400B0460
0x1400b0456  mov     edx, 4
0x1400b045b  jmp     loc_1400B0263
0x1400b0460  mov     edx, 3
0x1400b0465  jmp     loc_1400B0263
```
