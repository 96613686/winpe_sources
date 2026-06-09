# CSearchBox::SetFlags(SSCSTATEFLAGS)

- ea: `0x1800dcbf0`
- end: `0x1800dcd1c`
- name: `?SetFlags@CSearchBox@@UEAAJW4SSCSTATEFLAGS@@@Z`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800cb760`
- `0x1800dcbf0`

## import_xrefs

- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x1800dcc56`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x1800dcc96`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x1800dccd6`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x1800dcc56`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x1800dcc96`
- `DUI70!?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z` at `0x1800dccd6`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800dcc77`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800dccb7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800dccfb`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800dcc77`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800dccb7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1800dccfb`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800dcc22`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x1800dcc22`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dcc80`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dccc0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dcd04`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dcc80`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dccc0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dcd04`

## pseudocode

```c
__int64 __fastcall CSearchBox::SetFlags(__int64 a1, int a2)
{
  CSearchBox *v2; // r14
  int v3; // esi
  DirectUI::Element *v5; // rcx
  DirectUI::Element *v6; // rdi
  struct DirectUI::Value *Bool; // rax
  DirectUI::Value *v9; // rbp
  DirectUI::Element *v10; // rbp
  struct DirectUI::Value *v11; // rax
  DirectUI::Value *v12; // rdi
  DirectUI::Element *v13; // rdi
  struct DirectUI::Value *v14; // rax
  DirectUI::Value *v15; // rbx

  v2 = (CSearchBox *)(a1 - 48);
  v3 = *(_DWORD *)(a1 - 48 + 192) ^ a2;
  *(_DWORD *)(a1 + 144) = a2;
  v5 = *(DirectUI::Element **)(a1 + 48);
  if ( v5 )
    DirectUI::Element::SetEnabled(v5, (a2 & 0x40) == 0);
  v6 = *(DirectUI::Element **)(a1 + 56);
  if ( v6 )
  {
    Bool = DirectUI::Value::CreateBool((*(_DWORD *)(a1 + 144) & 0x80) == 0);
    v9 = Bool;
    if ( Bool )
    {
      DirectUI::Element::SetValue(v6, (const struct DirectUI::PropertyInfo *)&off_18021BB90, 1, Bool);
      DirectUI::Value::Release(v9);
    }
    v10 = *(DirectUI::Element **)(a1 + 56);
    v11 = DirectUI::Value::CreateBool(*(_DWORD *)(a1 + 144) & 0x100);
    v12 = v11;
    if ( v11 )
    {
      DirectUI::Element::SetValue(v10, (const struct DirectUI::PropertyInfo *)&off_18021BB60, 1, v11);
      DirectUI::Value::Release(v12);
    }
    v13 = *(DirectUI::Element **)(a1 + 56);
    v14 = DirectUI::Value::CreateBool((*(_DWORD *)(a1 + 144) & 4) != 0);
    v15 = v14;
    if ( v14 )
    {
      DirectUI::Element::SetValue(v13, (const struct DirectUI::PropertyInfo *)&off_18021BBC0, 1, v14);
      DirectUI::Value::Release(v15);
    }
  }
  if ( (v3 & 0x40) != 0 )
    CSearchBox::_Invalidate(v2);
  return 0;
}

```

## disassembly

```asm
0x1800dcbf0  push    rbx
0x1800dcbf2  push    rbp
0x1800dcbf3  push    rsi
0x1800dcbf4  push    rdi
0x1800dcbf5  push    r14
0x1800dcbf7  sub     rsp, 20h
0x1800dcbfb  lea     r14, [rcx-30h]
0x1800dcbff  mov     esi, edx
0x1800dcc01  xor     esi, [r14+0C0h]
0x1800dcc08  mov     rbx, rcx
0x1800dcc0b  mov     [rcx+90h], edx
0x1800dcc11  mov     rcx, [rcx+30h]
0x1800dcc15  test    rcx, rcx
0x1800dcc18  jz      short loc_1800DCC28
0x1800dcc1a  shr     edx, 6
0x1800dcc1d  not     dl
0x1800dcc1f  and     dl, 1
0x1800dcc22  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x1800dcc28  mov     rdi, [rbx+38h]
0x1800dcc2c  test    rdi, rdi
0x1800dcc2f  jnz     short loc_1800DCC48
0x1800dcc31  test    sil, 40h
0x1800dcc35  jnz     loc_1800DCD0F
0x1800dcc3b  xor     eax, eax
0x1800dcc3d  add     rsp, 20h
0x1800dcc41  pop     r14
0x1800dcc43  pop     rdi
0x1800dcc44  pop     rsi
0x1800dcc45  pop     rbp
0x1800dcc46  pop     rbx
0x1800dcc47  retn
0x1800dcc48  mov     ecx, [rbx+90h]
0x1800dcc4e  shr     ecx, 7
0x1800dcc51  not     cl
0x1800dcc53  and     cl, 1
0x1800dcc56  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x1800dcc5c  mov     rbp, rax
0x1800dcc5f  test    rax, rax
0x1800dcc62  jz      short loc_1800DCC86
0x1800dcc64  mov     r9, rax
0x1800dcc67  lea     rdx, off_18021BB90; "SuggestionsEnabled"
0x1800dcc6e  mov     r8d, 1
0x1800dcc74  mov     rcx, rdi
0x1800dcc77  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x1800dcc7d  mov     rcx, rbp
0x1800dcc80  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800dcc86  mov     ecx, [rbx+90h]
0x1800dcc8c  mov     rbp, [rbx+38h]
0x1800dcc90  shr     ecx, 8
0x1800dcc93  and     cl, 1
0x1800dcc96  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x1800dcc9c  mov     rdi, rax
0x1800dcc9f  test    rax, rax
0x1800dcca2  jz      short loc_1800DCCC6
0x1800dcca4  mov     r9, rax
0x1800dcca7  lea     rdx, off_18021BB60; "ParsingEnabledEnabled"
0x1800dccae  mov     r8d, 1
0x1800dccb4  mov     rcx, rbp
0x1800dccb7  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x1800dccbd  mov     rcx, rdi
0x1800dccc0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800dccc6  mov     ecx, [rbx+90h]
0x1800dcccc  mov     rdi, [rbx+38h]
0x1800dccd0  shr     ecx, 2
0x1800dccd3  and     cl, 1
0x1800dccd6  call    cs:__imp_?CreateBool@Value@DirectUI@@SAPEAV12@_N@Z; DirectUI::Value::CreateBool(bool)
0x1800dccdc  mov     rbx, rax
0x1800dccdf  test    rax, rax
0x1800dcce2  jz      loc_1800DCC31
0x1800dcce8  mov     r9, rax
0x1800dcceb  lea     rdx, off_18021BBC0; "PromptWithCaretEnabled"
0x1800dccf2  mov     r8d, 1
0x1800dccf8  mov     rcx, rdi
0x1800dccfb  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x1800dcd01  mov     rcx, rbx
0x1800dcd04  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800dcd0a  jmp     loc_1800DCC31
0x1800dcd0f  mov     rcx, r14; this
0x1800dcd12  call    ?_Invalidate@CSearchBox@@AEAAXXZ; CSearchBox::_Invalidate(void)
0x1800dcd17  jmp     loc_1800DCC3B
```
