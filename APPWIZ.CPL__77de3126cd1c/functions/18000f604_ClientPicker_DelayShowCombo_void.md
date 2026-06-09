# ClientPicker::_DelayShowCombo(void)

- ea: `0x18000f604`
- end: `0x18000f72f`
- name: `?_DelayShowCombo@ClientPicker@@AEAAXXZ`
- size: `299`
- prototype: `void __fastcall(ClientPicker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800100b0`

## callees

- `0x18000aec8`
- `0x18000f604`
- `0x180059010`

## import_xrefs

- `USER32!SendMessageW` at `0x18000f6b4`
- `USER32!SendMessageW` at `0x18000f6b4`
- `DUI70!?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000f667`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18000f675`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18000f675`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18000f6f4`
- `DUI70!?AddString@Combobox@DirectUI@@QEAAHPEBG@Z` at `0x18000f6f4`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x18000f719`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x18000f719`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18000f661`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x18000f661`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f632`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f645`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f632`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000f645`
- `DUI70!?GetWidth@Element@DirectUI@@QEAAHXZ` at `0x18000f655`
- `DUI70!?GetWidth@Element@DirectUI@@QEAAHXZ` at `0x18000f655`

## pseudocode

```c
void __fastcall ClientPicker::_DelayShowCombo(ClientPicker *this)
{
  unsigned int v2; // ebx
  DirectUI::Element *v3; // rbx
  int Width; // eax
  __int64 v5; // rbx
  __int64 v6; // rcx
  HWND v7; // rax
  _DWORD *v8; // rcx
  int v9; // edx
  DirectUI::Combobox *v10; // rsi
  _QWORD *v11; // rax
  const unsigned __int16 *FilteredName; // rax

  v2 = **((_DWORD **)this + 28) & 0xFFFFFFF;
  DirectUI::Element::SetVisible(*((DirectUI::Element **)this + 30), v2 > 1);
  DirectUI::Element::SetVisible(*((DirectUI::Element **)this + 29), v2 <= 1);
  v3 = (DirectUI::Element *)*((_QWORD *)this + 30);
  Width = DirectUI::Element::GetWidth(v3);
  DirectUI::Element::SetWidth(v3, Width - 1);
  DirectUI::Element::RemoveLocalValue(
    *((DirectUI::Element **)this + 30),
    (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::WidthProp);
  v5 = 0;
  if ( !*((_BYTE *)this + 208) )
  {
    v6 = *((_QWORD *)this + 30);
    *((_BYTE *)this + 208) = 1;
    v7 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 360LL))(v6);
    SendMessageW(v7, 0x14Bu, 0, 0);
    v8 = (_DWORD *)*((_QWORD *)this + 28);
    v9 = *v8;
    if ( (*v8 & 0xFFFFFFF) != 0 )
    {
      do
      {
        v10 = (DirectUI::Combobox *)*((_QWORD *)this + 30);
        v11 = v8 + 2;
        if ( (v9 & 0x10000000) != 0 )
          v11 = (_QWORD *)*v11;
        FilteredName = (const unsigned __int16 *)CLIENTINFO::GetFilteredName(v11[v5], *((unsigned int *)this + 51));
        DirectUI::Combobox::AddString(v10, FilteredName);
        v8 = (_DWORD *)*((_QWORD *)this + 28);
        v5 = (unsigned int)(v5 + 1);
        v9 = *v8;
      }
      while ( (unsigned int)v5 < (*v8 & 0xFFFFFFFu) );
    }
    DirectUI::Combobox::SetSelection(*((DirectUI::Combobox **)this + 30), 0);
  }
}

```

## disassembly

```asm
0x18000f604  mov     [rsp+arg_0], rbx
0x18000f609  mov     [rsp+arg_8], rsi
0x18000f60e  push    rdi
0x18000f60f  sub     rsp, 20h
0x18000f613  mov     rax, [rcx+0E0h]
0x18000f61a  mov     rdi, rcx
0x18000f61d  mov     rcx, [rcx+0F0h]
0x18000f624  mov     ebx, [rax]
0x18000f626  and     ebx, 0FFFFFFFh
0x18000f62c  cmp     ebx, 1
0x18000f62f  setnbe  dl
0x18000f632  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000f638  mov     rcx, [rdi+0E8h]
0x18000f63f  cmp     ebx, 1
0x18000f642  setbe   dl
0x18000f645  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18000f64b  mov     rbx, [rdi+0F0h]
0x18000f652  mov     rcx, rbx
0x18000f655  call    cs:__imp_?GetWidth@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetWidth(void)
0x18000f65b  mov     rcx, rbx
0x18000f65e  lea     edx, [rax-1]
0x18000f661  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x18000f667  mov     rdx, cs:__imp_?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::WidthProp(void)
0x18000f66e  mov     rcx, [rdi+0F0h]
0x18000f675  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18000f67b  xor     ebx, ebx
0x18000f67d  cmp     [rdi+0D0h], bl
0x18000f683  jnz     loc_18000F71F
0x18000f689  mov     rcx, [rdi+0F0h]
0x18000f690  mov     byte ptr [rdi+0D0h], 1
0x18000f697  mov     rax, [rcx]
0x18000f69a  mov     rax, [rax+168h]
0x18000f6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6a6  mov     rcx, rax; hWnd
0x18000f6a9  xor     r9d, r9d; lParam
0x18000f6ac  xor     r8d, r8d; wParam
0x18000f6af  mov     edx, 14Bh; Msg
0x18000f6b4  call    cs:__imp_SendMessageW
0x18000f6ba  mov     rcx, [rdi+0E0h]
0x18000f6c1  mov     edx, [rcx]
0x18000f6c3  test    edx, 0FFFFFFFh
0x18000f6c9  jbe     short loc_18000F710
0x18000f6cb  mov     rsi, [rdi+0F0h]
0x18000f6d2  lea     rax, [rcx+8]
0x18000f6d6  bt      edx, 1Ch
0x18000f6da  jnb     short loc_18000F6DF
0x18000f6dc  mov     rax, [rax]
0x18000f6df  mov     edx, [rdi+0CCh]
0x18000f6e5  mov     rcx, [rax+rbx*8]
0x18000f6e9  call    ?GetFilteredName@CLIENTINFO@@QEAAPEBGW4CLIENTFILTER@@@Z; CLIENTINFO::GetFilteredName(CLIENTFILTER)
0x18000f6ee  mov     rdx, rax
0x18000f6f1  mov     rcx, rsi
0x18000f6f4  call    cs:__imp_?AddString@Combobox@DirectUI@@QEAAHPEBG@Z; DirectUI::Combobox::AddString(ushort const *)
0x18000f6fa  mov     rcx, [rdi+0E0h]
0x18000f701  inc     ebx
0x18000f703  mov     edx, [rcx]
0x18000f705  mov     eax, edx
0x18000f707  and     eax, 0FFFFFFFh
0x18000f70c  cmp     ebx, eax
0x18000f70e  jb      short loc_18000F6CB
0x18000f710  mov     rcx, [rdi+0F0h]
0x18000f717  xor     edx, edx
0x18000f719  call    cs:__imp_?SetSelection@Combobox@DirectUI@@QEAAJH@Z; DirectUI::Combobox::SetSelection(int)
0x18000f71f  mov     rbx, [rsp+28h+arg_0]
0x18000f724  mov     rsi, [rsp+28h+arg_8]
0x18000f729  add     rsp, 20h
0x18000f72d  pop     rdi
0x18000f72e  retn
```
