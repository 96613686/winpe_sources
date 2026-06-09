# ClientPicker::_SyncUIActive(void)

- ea: `0x18000fdc4`
- end: `0x18000fef1`
- name: `?_SyncUIActive@ClientPicker@@AEAAXXZ`
- size: `301`
- prototype: `void __fastcall(UINT_PTR uIDEvent)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ccb0`
- `0x18000e3d4`

## callees

- `0x1800089f0`
- `0x18000aec8`
- `0x18000af14`
- `0x18000f534`
- `0x18000fcb8`
- `0x18000fdc4`

## import_xrefs

- `USER32!SetTimer` at `0x18000fe6a`
- `USER32!SetTimer` at `0x18000fe6a`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000fdf6`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000fdf6`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18000fe79`
- `DUI70!?GetSelection@Combobox@DirectUI@@QEAAHXZ` at `0x18000fe79`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000fecb`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000feda`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000fecb`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000feda`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18000fddb`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x18000fddb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000fe0d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000fe0d`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18000fe02`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18000fe02`

## pseudocode

```c
void __fastcall ClientPicker::_SyncUIActive(UINT_PTR uIDEvent)
{
  ARPFrame *Ancestor; // rbp
  DirectUI::Value *Value; // rdi
  bool Bool; // bl
  char v5; // al
  HWND HostWindow; // rax
  unsigned int Selection; // eax
  _DWORD *v8; // r8
  int v9; // edx
  _QWORD *v10; // r8
  const unsigned __int16 *FilteredName; // rax

  Ancestor = (ARPFrame *)FindAncestorElement<ARPFrame>();
  v5 = 0;
  if ( DirectUI::Element::GetSelected((DirectUI::Element *)uIDEvent) )
  {
    Value = DirectUI::Element::GetValue(
              (DirectUI::Element *)uIDEvent,
              (const struct DirectUI::PropertyInfo *)&off_180077328,
              2,
              0);
    Bool = DirectUI::Value::GetBool(Value);
    DirectUI::Value::Release(Value);
    if ( Bool )
      v5 = 1;
  }
  if ( *(_BYTE *)(uIDEvent + 210) != v5 )
  {
    *(_BYTE *)(uIDEvent + 210) = v5;
    if ( v5 )
    {
      HostWindow = ARPFrame::GetHostWindow(Ancestor);
      *(_QWORD *)(uIDEvent + 216) = HostWindow;
      if ( HostWindow )
        SetTimer(HostWindow, uIDEvent, *((_BYTE *)Ancestor + 372) != 0 ? 0x15E : 0, ClientPicker::s_DelayShowCombo);
    }
    else
    {
      Selection = DirectUI::Combobox::GetSelection(*(DirectUI::Combobox **)(uIDEvent + 240));
      v8 = *(_DWORD **)(uIDEvent + 224);
      v9 = *v8;
      if ( Selection < (*v8 & 0xFFFFFFFu) )
      {
        v10 = v8 + 2;
        if ( (v9 & 0x10000000) != 0 )
          v10 = (_QWORD *)*v10;
        FilteredName = (const unsigned __int16 *)CLIENTINFO::GetFilteredName(
                                                   v10[Selection],
                                                   *(unsigned int *)(uIDEvent + 204));
        _SetStaticTextAndAccName(*(struct DirectUI::Element **)(uIDEvent + 232), FilteredName);
      }
      DirectUI::Element::SetVisible(*(DirectUI::Element **)(uIDEvent + 240), 0);
      DirectUI::Element::SetVisible(*(DirectUI::Element **)(uIDEvent + 232), 1);
      ClientPicker::_CancelDelayShowCombo(uIDEvent);
    }
  }
}

```

## disassembly

```asm
0x18000fdc4  push    rbx
0x18000fdc6  push    rbp
0x18000fdc7  push    rsi
0x18000fdc8  push    rdi
0x18000fdc9  sub     rsp, 28h
0x18000fdcd  mov     rsi, rcx
0x18000fdd0  call    ??$FindAncestorElement@VARPFrame@@@@YAPEAVARPFrame@@PEAVElement@DirectUI@@@Z; FindAncestorElement<ARPFrame>(DirectUI::Element *)
0x18000fdd5  mov     rcx, rsi
0x18000fdd8  mov     rbp, rax
0x18000fddb  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x18000fde1  test    al, al
0x18000fde3  jz      short loc_18000FE1B
0x18000fde5  xor     r9d, r9d
0x18000fde8  lea     rdx, off_180077328; "parentexpanded"
0x18000fdef  mov     rcx, rsi
0x18000fdf2  lea     r8d, [r9+2]
0x18000fdf6  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000fdfc  mov     rcx, rax
0x18000fdff  mov     rdi, rax
0x18000fe02  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x18000fe08  mov     rcx, rdi
0x18000fe0b  mov     bl, al
0x18000fe0d  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000fe13  test    bl, bl
0x18000fe15  jz      short loc_18000FE1B
0x18000fe17  mov     al, 1
0x18000fe19  jmp     short loc_18000FE1D
0x18000fe1b  xor     al, al
0x18000fe1d  cmp     [rsi+0D2h], al
0x18000fe23  jz      loc_18000FEE8
0x18000fe29  mov     [rsi+0D2h], al
0x18000fe2f  test    al, al
0x18000fe31  jz      short loc_18000FE72
0x18000fe33  mov     rcx, rbp; this
0x18000fe36  call    ?GetHostWindow@ARPFrame@@QEAAPEAUHWND__@@XZ; ARPFrame::GetHostWindow(void)
0x18000fe3b  mov     [rsi+0D8h], rax
0x18000fe42  test    rax, rax
0x18000fe45  jz      loc_18000FEE8
0x18000fe4b  mov     cl, [rbp+174h]
0x18000fe51  lea     r9, ?s_DelayShowCombo@ClientPicker@@CAXPEAUHWND__@@I_KK@Z; lpTimerFunc
0x18000fe58  neg     cl
0x18000fe5a  mov     rdx, rsi; nIDEvent
0x18000fe5d  mov     rcx, rax; hWnd
0x18000fe60  sbb     r8d, r8d
0x18000fe63  and     r8d, 15Eh; uElapse
0x18000fe6a  call    cs:__imp_SetTimer
0x18000fe70  jmp     short loc_18000FEE8
0x18000fe72  mov     rcx, [rsi+0F0h]
0x18000fe79  call    cs:__imp_?GetSelection@Combobox@DirectUI@@QEAAHXZ; DirectUI::Combobox::GetSelection(void)
0x18000fe7f  mov     r8, [rsi+0E0h]
0x18000fe86  mov     edx, [r8]
0x18000fe89  mov     ecx, edx
0x18000fe8b  and     ecx, 0FFFFFFFh
0x18000fe91  cmp     eax, ecx
0x18000fe93  jnb     short loc_18000FEC2
0x18000fe95  add     r8, 8
0x18000fe99  bt      edx, 1Ch
0x18000fe9d  jnb     short loc_18000FEA2
0x18000fe9f  mov     r8, [r8]
0x18000fea2  mov     edx, [rsi+0CCh]
0x18000fea8  mov     ecx, eax
0x18000feaa  mov     rcx, [r8+rcx*8]
0x18000feae  call    ?GetFilteredName@CLIENTINFO@@QEAAPEBGW4CLIENTFILTER@@@Z; CLIENTINFO::GetFilteredName(CLIENTFILTER)
0x18000feb3  mov     rcx, [rsi+0E8h]; struct DirectUI::Element *
0x18000feba  mov     rdx, rax; unsigned __int16 *
0x18000febd  call    ?_SetStaticTextAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; _SetStaticTextAndAccName(DirectUI::Element *,ushort const *)
0x18000fec2  mov     rcx, [rsi+0F0h]
0x18000fec9  xor     edx, edx
0x18000fecb  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000fed1  mov     rcx, [rsi+0E8h]
0x18000fed8  mov     dl, 1
0x18000feda  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000fee0  mov     rcx, rsi; uIDEvent
0x18000fee3  call    ?_CancelDelayShowCombo@ClientPicker@@AEAAXXZ; ClientPicker::_CancelDelayShowCombo(void)
0x18000fee8  add     rsp, 28h
0x18000feec  pop     rdi
0x18000feed  pop     rsi
0x18000feee  pop     rbp
0x18000feef  pop     rbx
0x18000fef0  retn
```
