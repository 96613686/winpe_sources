# AuthHostWebInstance::OnDomContentLoaded(IHTMLWindow2 *,IUri *,WebPlatformNavigationDataFlags)

- ea: `0x14000a4b0`
- end: `0x14000a7ad`
- name: `?OnDomContentLoaded@AuthHostWebInstance@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@W4WebPlatformNavigationDataFlags@@@Z`
- size: `765`
- prototype: `__int64 __fastcall(__int64, struct IHTMLWindow2 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002c70`
- `0x1400066dc`
- `0x140006a24`
- `0x140009214`
- `0x1400096a8`
- `0x14000a4b0`
- `0x14000b308`
- `0x14000b6f0`
- `0x14000bb4c`
- `0x14000c0c0`
- `0x14000c2dc`
- `0x14000ce5c`
- `0x140011aa4`
- `0x140012f60`
- `0x140014010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-2!KillTimer` at `0x14000a63a`
- `ext-ms-win-ntuser-window-l1-1-2!KillTimer` at `0x14000a682`
- `ext-ms-win-ntuser-window-l1-1-2!KillTimer` at `0x14000a63a`
- `ext-ms-win-ntuser-window-l1-1-2!KillTimer` at `0x14000a682`
- `ext-ms-win-ntuser-window-l1-1-2!SetTimer` at `0x14000a6ad`
- `ext-ms-win-ntuser-window-l1-1-2!SetTimer` at `0x14000a6ad`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::OnDomContentLoaded(__int64 a1, struct IHTMLWindow2 *a2)
{
  PVOID *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // r8
  const unsigned __int16 *v10; // rdx
  UINT_PTR v11; // rdx
  AuthHostWebInstance *v12; // rcx
  UINT_PTR v13; // rdx
  UINT AuthHostRegDWORDValue; // eax
  _QWORD v16[4]; // [rsp+30h] [rbp-48h] BYREF

  if ( !(unsigned __int8)IsValidWindow(a2) )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      v5 = 34;
LABEL_6:
      WPP_SF_(v4[7], v5, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
      return 0;
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
  }
  TraceWindow(a2);
  if ( *(_DWORD *)(a1 - 8 + 504) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 36, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
    }
    v6 = *(_QWORD *)(a1 + 96);
    *(_DWORD *)(a1 + 496) = 0;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 96LL))(v6, 4);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 96) + 96LL))(*(_QWORD *)(a1 + 96), 0);
  }
  UpdateWebDialogMetaTagContent(a2, (struct _WEB_DIALOG_META_TAG_CONTENT *)(a1 + 168));
  v8 = HasWebDialogHeaderMetaTag((struct _WEB_DIALOG_META_TAG_CONTENT *)(a1 + 168));
  if ( v8 )
  {
    v10 = &szColor;
    if ( *(_QWORD *)(a1 + 176) )
      v10 = *(const unsigned __int16 **)(a1 + 176);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v16, v10);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 96) + 112LL))(
      *(_QWORD *)(a1 + 96),
      v16[0],
      *(unsigned int *)(a1 + 184));
    v11 = *(_QWORD *)(a1 + 488);
    if ( v11 )
    {
      KillTimer(0, v11);
      *(_QWORD *)(a1 + 488) = 0;
    }
    AuthHostWebInstance::UpdateBrokerLogo((HSTRING *)(a1 - 8));
    *(_DWORD *)(a1 + 480) = 0;
    goto LABEL_33;
  }
  if ( *(_DWORD *)(a1 + 124) == 1 )
  {
    v12 = (AuthHostWebInstance *)(a1 - 8);
LABEL_32:
    AuthHostWebInstance::SetBrokerToFallback(v12);
    goto LABEL_33;
  }
  if ( !*(_DWORD *)(a1 + 480) )
  {
    v13 = *(_QWORD *)(a1 + 488);
    if ( v13 )
    {
      KillTimer(0, v13);
      *(_QWORD *)(a1 + 488) = 0;
    }
    AuthHostRegDWORDValue = GetAuthHostRegDWORDValue(L"FallbackMilliseconds");
    if ( AuthHostRegDWORDValue )
      *(_QWORD *)(a1 + 488) = SetTimer(0, 0, AuthHostRegDWORDValue, 0);
    if ( !*(_QWORD *)(a1 + 488) )
    {
      v12 = (AuthHostWebInstance *)(a1 - 8);
      goto LABEL_32;
    }
  }
LABEL_33:
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_ddq(*((_QWORD *)WPP_GLOBAL_Control + 7), v7, v9, v8, *(_DWORD *)(a1 + 480), *(_QWORD *)(a1 + 488));
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(a1 + 208) || *(_DWORD *)(a1 + 212))
    && v4 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v4 + 68) & 4) != 0
    && *((_BYTE *)v4 + 65) >= 5u )
  {
    WPP_SF_Dd(v4[7], 38, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(a1 + 120) & 0x20000) == 0 )
  {
    AuthHostWebInstance::ParseHtmlDoc((AuthHostWebInstance *)(a1 - 8), a2);
    return 0;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 4) != 0 && *((_BYTE *)v4 + 65) >= 5u )
  {
    v5 = 39;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x14000a4b0  mov     [rsp+arg_10], rbx
0x14000a4b5  mov     [rsp+arg_18], rbp
0x14000a4ba  push    rdi
0x14000a4bb  push    r12
0x14000a4bd  push    r15
0x14000a4bf  sub     rsp, 60h
0x14000a4c3  mov     rax, cs:__security_cookie
0x14000a4ca  xor     rax, rsp
0x14000a4cd  mov     [rsp+78h+var_28], rax
0x14000a4d2  mov     rdi, rcx
0x14000a4d5  mov     r12, rdx
0x14000a4d8  mov     rcx, rdx
0x14000a4db  call    _IsValidWindow
0x14000a4e0  test    al, al
0x14000a4e2  jnz     short loc_14000A529
0x14000a4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a4eb  lea     rbp, WPP_GLOBAL_Control
0x14000a4f2  cmp     rcx, rbp
0x14000a4f5  jz      loc_14000A788
0x14000a4fb  test    byte ptr [rcx+44h], 4
0x14000a4ff  jz      loc_14000A788
0x14000a505  cmp     byte ptr [rcx+41h], 5
0x14000a509  jb      loc_14000A788
0x14000a50f  mov     edx, 22h ; '"'
0x14000a514  mov     rcx, [rcx+38h]
0x14000a518  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a51f  call    WPP_SF_
0x14000a524  jmp     loc_14000A788
0x14000a529  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a530  lea     rbp, WPP_GLOBAL_Control
0x14000a537  cmp     rcx, rbp
0x14000a53a  jz      short loc_14000A55D
0x14000a53c  test    byte ptr [rcx+44h], 4
0x14000a540  jz      short loc_14000A55D
0x14000a542  cmp     byte ptr [rcx+41h], 5
0x14000a546  jb      short loc_14000A55D
0x14000a548  mov     rcx, [rcx+38h]
0x14000a54c  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a553  mov     edx, 23h ; '#'
0x14000a558  call    WPP_SF_
0x14000a55d  mov     rcx, r12
0x14000a560  call    _TraceWindow
0x14000a565  lea     r15, [rdi-8]
0x14000a569  cmp     dword ptr [r15+1F8h], 0
0x14000a571  jz      short loc_14000A5D1
0x14000a573  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a57a  cmp     rcx, rbp
0x14000a57d  jz      short loc_14000A5A0
0x14000a57f  test    byte ptr [rcx+44h], 4
0x14000a583  jz      short loc_14000A5A0
0x14000a585  cmp     byte ptr [rcx+41h], 5
0x14000a589  jb      short loc_14000A5A0
0x14000a58b  mov     rcx, [rcx+38h]
0x14000a58f  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a596  mov     edx, 24h ; '$'
0x14000a59b  call    WPP_SF_
0x14000a5a0  mov     rcx, [rdi+60h]
0x14000a5a4  mov     edx, 4
0x14000a5a9  mov     dword ptr [rdi+1F0h], 0
0x14000a5b3  mov     rax, [rcx]
0x14000a5b6  mov     rax, [rax+60h]
0x14000a5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5bf  mov     rcx, [rdi+60h]
0x14000a5c3  xor     edx, edx
0x14000a5c5  mov     rax, [rcx]
0x14000a5c8  mov     rax, [rax+60h]
0x14000a5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5d1  lea     rbx, [rdi+0A8h]
0x14000a5d8  mov     rcx, r12; struct IHTMLWindow2 *
0x14000a5db  mov     rdx, rbx; struct _WEB_DIALOG_META_TAG_CONTENT *
0x14000a5de  call    ?UpdateWebDialogMetaTagContent@@YAXPEAUIHTMLWindow2@@PEAU_WEB_DIALOG_META_TAG_CONTENT@@@Z; UpdateWebDialogMetaTagContent(IHTMLWindow2 *,_WEB_DIALOG_META_TAG_CONTENT *)
0x14000a5e3  mov     rcx, rbx; struct _WEB_DIALOG_META_TAG_CONTENT *
0x14000a5e6  call    ?HasWebDialogHeaderMetaTag@@YAHPEAU_WEB_DIALOG_META_TAG_CONTENT@@@Z; HasWebDialogHeaderMetaTag(_WEB_DIALOG_META_TAG_CONTENT *)
0x14000a5eb  mov     ebx, eax
0x14000a5ed  test    eax, eax
0x14000a5ef  jz      short loc_14000A65F
0x14000a5f1  mov     rcx, [rdi+0B0h]
0x14000a5f8  lea     rdx, szColor
0x14000a5ff  test    rcx, rcx
0x14000a602  cmovnz  rdx, rcx; unsigned __int16 *
0x14000a606  lea     rcx, [rsp+78h+var_48]; this
0x14000a60b  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x14000a610  mov     rcx, [rdi+60h]
0x14000a614  mov     r8d, [rdi+0B8h]
0x14000a61b  mov     rdx, [rsp+78h+var_48]
0x14000a620  mov     rax, [rcx]
0x14000a623  mov     rax, [rax+70h]
0x14000a627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a62c  mov     rdx, [rdi+1E8h]; uIDEvent
0x14000a633  test    rdx, rdx
0x14000a636  jz      short loc_14000A64B
0x14000a638  xor     ecx, ecx; hWnd
0x14000a63a  call    cs:__imp_KillTimer
0x14000a640  mov     qword ptr [rdi+1E8h], 0
0x14000a64b  mov     rcx, r15; this
0x14000a64e  call    ?UpdateBrokerLogo@AuthHostWebInstance@@AEAAXXZ; AuthHostWebInstance::UpdateBrokerLogo(void)
0x14000a653  mov     dword ptr [rdi+1E0h], 0
0x14000a65d  jmp     short loc_14000A6CC
0x14000a65f  cmp     dword ptr [rdi+7Ch], 1
0x14000a663  jnz     short loc_14000A66B
0x14000a665  lea     rcx, [rdi-8]
0x14000a669  jmp     short loc_14000A6C7
0x14000a66b  cmp     dword ptr [rdi+1E0h], 0
0x14000a672  jnz     short loc_14000A6CC
0x14000a674  mov     rdx, [rdi+1E8h]; uIDEvent
0x14000a67b  test    rdx, rdx
0x14000a67e  jz      short loc_14000A693
0x14000a680  xor     ecx, ecx; hWnd
0x14000a682  call    cs:__imp_KillTimer
0x14000a688  mov     qword ptr [rdi+1E8h], 0
0x14000a693  lea     rcx, ValueName; "FallbackMilliseconds"
0x14000a69a  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x14000a69f  test    eax, eax
0x14000a6a1  jz      short loc_14000A6BA
0x14000a6a3  xor     r9d, r9d; lpTimerFunc
0x14000a6a6  mov     r8d, eax; uElapse
0x14000a6a9  xor     edx, edx; nIDEvent
0x14000a6ab  xor     ecx, ecx; hWnd
0x14000a6ad  call    cs:__imp_SetTimer
0x14000a6b3  mov     [rdi+1E8h], rax
0x14000a6ba  cmp     qword ptr [rdi+1E8h], 0
0x14000a6c2  jnz     short loc_14000A6CC
0x14000a6c4  mov     rcx, r15; this
0x14000a6c7  call    ?SetBrokerToFallback@AuthHostWebInstance@@AEAAXXZ; AuthHostWebInstance::SetBrokerToFallback(void)
0x14000a6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a6d3  cmp     rcx, rbp
0x14000a6d6  jz      short loc_14000A70D
0x14000a6d8  test    byte ptr [rcx+44h], 4
0x14000a6dc  jz      short loc_14000A70D
0x14000a6de  cmp     byte ptr [rcx+41h], 5
0x14000a6e2  jb      short loc_14000A70D
0x14000a6e4  mov     rax, [rdi+1E8h]
0x14000a6eb  mov     r9d, ebx
0x14000a6ee  mov     rcx, [rcx+38h]
0x14000a6f2  mov     [rsp+78h+var_50], rax
0x14000a6f7  mov     eax, [rdi+1E0h]
0x14000a6fd  mov     [rsp+78h+var_58], eax
0x14000a701  call    WPP_SF_ddq
0x14000a706  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a70d  mov     r9d, [rdi+0D0h]
0x14000a714  test    r9d, r9d
0x14000a717  jnz     short loc_14000A722
0x14000a719  cmp     [rdi+0D4h], r9d
0x14000a720  jz      short loc_14000A759
0x14000a722  cmp     rcx, rbp
0x14000a725  jz      short loc_14000A759
0x14000a727  test    byte ptr [rcx+44h], 4
0x14000a72b  jz      short loc_14000A759
0x14000a72d  cmp     byte ptr [rcx+41h], 5
0x14000a731  jb      short loc_14000A759
0x14000a733  mov     eax, [rdi+0D4h]
0x14000a739  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a740  mov     rcx, [rcx+38h]
0x14000a744  mov     edx, 26h ; '&'
0x14000a749  mov     [rsp+78h+var_58], eax
0x14000a74d  call    WPP_SF_Dd
0x14000a752  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a759  test    dword ptr [rdi+78h], 20000h
0x14000a760  jz      short loc_14000A77D
0x14000a762  cmp     rcx, rbp
0x14000a765  jz      short loc_14000A788
0x14000a767  test    byte ptr [rcx+44h], 4
0x14000a76b  jz      short loc_14000A788
0x14000a76d  cmp     byte ptr [rcx+41h], 5
0x14000a771  jb      short loc_14000A788
0x14000a773  mov     edx, 27h ; '''
0x14000a778  jmp     loc_14000A514
0x14000a77d  mov     rdx, r12; struct IHTMLWindow2 *
0x14000a780  mov     rcx, r15; this
0x14000a783  call    ?ParseHtmlDoc@AuthHostWebInstance@@AEAAJPEAUIHTMLWindow2@@@Z; AuthHostWebInstance::ParseHtmlDoc(IHTMLWindow2 *)
0x14000a788  xor     eax, eax
0x14000a78a  mov     rcx, [rsp+78h+var_28]
0x14000a78f  xor     rcx, rsp; StackCookie
0x14000a792  call    __security_check_cookie
0x14000a797  lea     r11, [rsp+78h+var_18]
0x14000a79c  mov     rbx, [r11+30h]
0x14000a7a0  mov     rbp, [r11+38h]
0x14000a7a4  mov     rsp, r11
0x14000a7a7  pop     r15
0x14000a7a9  pop     r12
0x14000a7ab  pop     rdi
0x14000a7ac  retn
```
