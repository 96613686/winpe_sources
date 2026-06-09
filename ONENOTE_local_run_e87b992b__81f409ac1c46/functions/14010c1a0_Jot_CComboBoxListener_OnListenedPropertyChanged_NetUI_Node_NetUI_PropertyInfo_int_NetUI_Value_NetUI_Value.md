# Jot::CComboBoxListener::OnListenedPropertyChanged(NetUI::Node *,NetUI::PropertyInfo *,int,NetUI::Value *,NetUI::Value *)

- ea: `0x14010c1a0`
- end: `0x14010c471`
- name: `?OnListenedPropertyChanged@CComboBoxListener@Jot@@UEAAXPEAVNode@NetUI@@PEAUPropertyInfo@4@HPEAVValue@4@2@Z`
- size: `721`
- prototype: `void __fastcall(Jot::CComboBoxListener *__hidden this, struct Node *, struct NetUI::PropertyInfo *, int, struct NetUI::Value *, struct NetUI::Value *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140038754`
- `0x140049304`
- `0x140057580`
- `0x140064e70`
- `0x140066540`
- `0x1400d4af0`
- `0x1400e4566`
- `0x14010a7fc`
- `0x14010b054`
- `0x14010c1a0`

## import_xrefs

- `onmain!?AreEqual_ComplexType@CPropertyData@MsoCF@@SA_NPEBX0W4PropertyType@2@@Z` at `0x14010c3e8`
- `onmain!?AreEqual_ComplexType@CPropertyData@MsoCF@@SA_NPEBX0W4PropertyType@2@@Z` at `0x14010c3e8`
- `onmain!?priCommandShowedAnAlert@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14010c233`
- `onmain!?priCommandShowedAnAlert@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14010c277`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x14010c327`
- `onmain!?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z` at `0x14010c327`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14010c405`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14010c405`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x14010c342`
- `onmain!?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z` at `0x14010c342`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010c372`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010c428`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010c443`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010c372`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010c428`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14010c443`
- `USER32!SetFocus` at `0x14010c2a2`
- `USER32!SetFocus` at `0x14010c2a2`
- `USER32!GetFocus` at `0x14010c244`
- `USER32!GetFocus` at `0x14010c244`
- `mso40uiWin32Client!__imp_?GetValue@Node@NetUI@@QEBAPEAVValue@2@PEBUPropertyInfo@2@HE@Z` at `0x14010c31b`
- `mso40uiWin32Client!__imp_?GetValue@Node@NetUI@@QEBAPEAVValue@2@PEBUPropertyInfo@2@HE@Z` at `0x14010c31b`
- `mso40uiWin32Client!__imp_?TextPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14010c2ad`
- `mso40uiWin32Client!__imp_?TextPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14010c308`
- `mso40uiWin32Client!__imp_?TextPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14010c2ad`
- `mso40uiWin32Client!__imp_?TextPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14010c308`
- `mso40uiWin32Client!__imp_?GetExpandoString@Node@NetUI@@QEBAPEB_WPEBD@Z` at `0x14010c211`
- `mso40uiWin32Client!__imp_?GetExpandoString@Node@NetUI@@QEBAPEB_WPEBD@Z` at `0x14010c211`
- `mso40uiWin32Client!__imp_?KeyFocusedPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14010c1c8`
- `mso40uiWin32Client!__imp_?KeyFocusedPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x14010c1c8`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14010c44c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x14010c44c`

## pseudocode

```c
void __fastcall Jot::CComboBoxListener::OnListenedPropertyChanged(
        Jot::CComboBoxListener *this,
        struct Node *a2,
        struct NetUI::PropertyInfo *a3,
        int a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  HWND Focus; // rbx
  const char *v10; // r8
  Jot *v11; // rcx
  unsigned int PropertyHandle; // r14d
  NetUI::Node *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  const struct NetUI::PropertyInfo *v16; // rax
  struct NetUI::Value *Value; // rbx
  unsigned int v18; // edx
  const struct MsoCF::PropertyInfo *v19; // r13
  const wchar_t *String; // r14
  int v21; // r15d
  unsigned int v22; // r14d
  char v23; // al
  void *Buf2; // [rsp+20h] [rbp-20h] BYREF
  int v25; // [rsp+28h] [rbp-18h]
  __int64 Buf1; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-8h]
  char v28; // [rsp+80h] [rbp+40h] BYREF

  if ( (struct NetUI::PropertyInfo *)NetUI::Element::KeyFocusedPropInfo(this, a2) == a3
    && (*((_WORD *)a3 + 4) & 3) == a4 )
  {
    if ( (*(_BYTE *)(NetUI::nui_control_cast<NetUI::Combobox>(*((NetUI::Node **)this + 2)) + 194) & 4) == 0 )
    {
      Jot::CNetUIDialog::FireForceUpdateEvent(*((struct Node **)this + 2));
      if ( !NetUI::Node::GetExpandoString(*((NetUI::Node **)this + 2), "fDontSendEventOnFocusChangeProperty")
        && !*((_BYTE *)this + 40) )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 72LL))(
          *((_QWORD *)this + 3),
          Jot::PropertySpace_JotMain::priCommandShowedAnAlert);
        Focus = GetFocus();
        sub_14010B054(*((Jot **)this + 2), (struct Node *)&stru_1401F93C0, *((struct MsoCF::IPropertySet **)this + 3));
        v28 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 3) + 48LL))(
               *((_QWORD *)this + 3),
               Jot::PropertySpace_JotMain::priCommandShowedAnAlert,
               &v28) )
        {
          if ( v28 )
          {
            if ( Focus )
              SetFocus(Focus);
          }
        }
      }
    }
  }
  else if ( (struct NetUI::PropertyInfo *)NetUI::Element::TextPropInfo(v8, v7) == a3 && (*((_WORD *)a3 + 4) & 3) == a4 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      v11 = (Jot *)*((_QWORD *)this + 2);
      if ( v11 )
      {
        PropertyHandle = Jot::GetPropertyHandle(v11, (struct Node *)&stru_1401F7F30, v10);
        if ( PropertyHandle )
        {
          v13 = (NetUI::Node *)NetUI::nui_control_cast<NetUI::Element>(*((NetUI::Node **)this + 2));
          v16 = (const struct NetUI::PropertyInfo *)NetUI::Element::TextPropInfo(v15, v14);
          Value = NetUI::Node::GetValue(v13, v16, 1, 0);
          v19 = MsoCF::LookupProperty((MsoCF *)PropertyHandle, v18);
          Buf1 = 0;
          v27 = 0;
          MsoCF::IPropertySet::GetProperty(
            *((MsoCF::IPropertySet **)this + 3),
            v19,
            (struct MsoCF::CPropertyValue *)&Buf1);
          Buf2 = 0;
          v25 = 0;
          if ( *((_WORD *)Value + 2) == 7 )
          {
            String = NetUI::Value::GetString(Value);
            MsoCF::ProduceAtomFromString<MsoCF::String<MsoCF::WzTraits>>(&Buf2, String);
          }
          else
          {
            Buf2 = &g_zeroAtom;
            _InterlockedIncrement((volatile signed __int32 *)&g_zeroAtom);
          }
          v21 = 117899322;
          v25 = 117899322;
          v22 = v27;
          if ( v27 != 117899322
            || (memcmp_0(&Buf1, &Buf2, 8u)
              ? (v23 = MsoCF::CPropertyData::AreEqual_ComplexType(&Buf1, &Buf2, v22), v22 = v27, v21 = v25)
              : (v23 = 1),
                !v23) )
          {
            MsoCF::IPropertySet::SetProperty(
              *((MsoCF::IPropertySet **)this + 3),
              v19,
              (const struct MsoCF::CPropertyValue *)&Buf2);
            *((_BYTE *)this + 40) = 0;
            v22 = v27;
            v21 = v25;
          }
          if ( (v21 & 0x2000000) != 0 )
          {
            MsoCF::CPropertyData::FreeAndZero_ComplexType(&Buf2);
            v22 = v27;
          }
          if ( (v22 & 0x2000000) != 0 )
            MsoCF::CPropertyData::FreeAndZero_ComplexType(&Buf1);
          NetUI::BaseValue::Release(Value);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14010c1a0  mov     [rsp-28h+arg_0], rbx
0x14010c1a5  mov     [rsp-28h+arg_8], rsi
0x14010c1aa  mov     [rsp-28h+arg_18], rdi
0x14010c1af  push    rbp
0x14010c1b0  push    r12
0x14010c1b2  push    r13
0x14010c1b4  push    r14
0x14010c1b6  push    r15
0x14010c1b8  mov     rbp, rsp
0x14010c1bb  sub     rsp, 40h
0x14010c1bf  mov     r14d, r9d
0x14010c1c2  mov     rdi, r8
0x14010c1c5  mov     rsi, rcx
0x14010c1c8  call    cs:__imp_?KeyFocusedPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::KeyFocusedPropInfo(void)
0x14010c1ce  cmp     rax, rdi
0x14010c1d1  jnz     loc_14010C2AD
0x14010c1d7  movzx   eax, word ptr [rdi+8]
0x14010c1db  and     eax, 3
0x14010c1de  cmp     eax, r14d
0x14010c1e1  jnz     loc_14010C2AD
0x14010c1e7  mov     rcx, [rsi+10h]; this
0x14010c1eb  call    ??$nui_control_cast@VCombobox@NetUI@@@NetUI@@YAPEBVCombobox@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Combobox>(NetUI::Node const *)
0x14010c1f0  test    byte ptr [rax+0C2h], 4
0x14010c1f7  jnz     loc_14010C453
0x14010c1fd  mov     rcx, [rsi+10h]; struct Node *
0x14010c201  call    ?FireForceUpdateEvent@CNetUIDialog@Jot@@SAXPEAVNode@NetUI@@@Z; Jot::CNetUIDialog::FireForceUpdateEvent(NetUI::Node *)
0x14010c206  lea     rdx, aFdontsendevent; "fDontSendEventOnFocusChangeProperty"
0x14010c20d  mov     rcx, [rsi+10h]
0x14010c211  call    cs:__imp_?GetExpandoString@Node@NetUI@@QEBAPEB_WPEBD@Z; NetUI::Node::GetExpandoString(char const *)
0x14010c217  xor     edi, edi
0x14010c219  test    rax, rax
0x14010c21c  jnz     loc_14010C453
0x14010c222  cmp     [rsi+28h], dil
0x14010c226  jnz     loc_14010C453
0x14010c22c  mov     rcx, [rsi+18h]
0x14010c230  mov     rax, [rcx]
0x14010c233  mov     rdx, cs:__imp_?priCommandShowedAnAlert@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priCommandShowedAnAlert
0x14010c23a  mov     rax, [rax+48h]
0x14010c23e  call    cs:__guard_dispatch_icall_fptr
0x14010c244  call    cs:__imp_GetFocus
0x14010c24a  mov     rbx, rax
0x14010c24d  mov     r9b, 1
0x14010c250  mov     r8, [rsi+18h]; struct MsoCF::IPropertySet *
0x14010c254  lea     rdx, stru_1401F93C0; struct Node *
0x14010c25b  mov     rcx, [rsi+10h]; this
0x14010c25f  call    sub_14010B054
0x14010c264  mov     [rbp+arg_10], dil
0x14010c268  mov     rcx, [rsi+18h]
0x14010c26c  mov     r8, [rcx]
0x14010c26f  mov     rax, [r8+30h]
0x14010c273  lea     r8, [rbp+arg_10]
0x14010c277  mov     rdx, cs:__imp_?priCommandShowedAnAlert@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priCommandShowedAnAlert
0x14010c27e  call    cs:__guard_dispatch_icall_fptr
0x14010c284  test    al, al
0x14010c286  jz      loc_14010C453
0x14010c28c  cmp     [rbp+arg_10], dil
0x14010c290  jz      loc_14010C453
0x14010c296  test    rbx, rbx
0x14010c299  jz      loc_14010C453
0x14010c29f  mov     rcx, rbx; hWnd
0x14010c2a2  call    cs:__imp_SetFocus
0x14010c2a8  jmp     loc_14010C453
0x14010c2ad  call    cs:__imp_?TextPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::TextPropInfo(void)
0x14010c2b3  cmp     rax, rdi
0x14010c2b6  jnz     loc_14010C453
0x14010c2bc  movzx   eax, word ptr [rdi+8]
0x14010c2c0  and     eax, 3
0x14010c2c3  cmp     eax, r14d
0x14010c2c6  jnz     loc_14010C453
0x14010c2cc  xor     edi, edi
0x14010c2ce  cmp     [rsi+18h], rdi
0x14010c2d2  jz      loc_14010C453
0x14010c2d8  mov     rcx, [rsi+10h]; this
0x14010c2dc  test    rcx, rcx
0x14010c2df  jz      loc_14010C453
0x14010c2e5  lea     rdx, stru_1401F7F30; struct Node *
0x14010c2ec  call    ?GetPropertyHandle@Jot@@YAIPEAVNode@NetUI@@PEBD@Z; Jot::GetPropertyHandle(NetUI::Node *,char const *)
0x14010c2f1  mov     r14d, eax
0x14010c2f4  test    eax, eax
0x14010c2f6  jz      loc_14010C453
0x14010c2fc  mov     rcx, [rsi+10h]; this
0x14010c300  call    ??$nui_control_cast@VElement@NetUI@@@NetUI@@YAPEBVElement@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Element>(NetUI::Node const *)
0x14010c305  mov     rbx, rax
0x14010c308  call    cs:__imp_?TextPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::TextPropInfo(void)
0x14010c30e  mov     rdx, rax
0x14010c311  xor     r9d, r9d
0x14010c314  lea     r8d, [rdi+1]
0x14010c318  mov     rcx, rbx
0x14010c31b  call    cs:__imp_?GetValue@Node@NetUI@@QEBAPEAVValue@2@PEBUPropertyInfo@2@HE@Z; NetUI::Node::GetValue(NetUI::PropertyInfo const *,int,uchar)
0x14010c321  mov     rbx, rax
0x14010c324  mov     ecx, r14d
0x14010c327  call    cs:__imp_?LookupProperty@MsoCF@@YAAEBUPropertyInfo@1@I@Z; MsoCF::LookupProperty(uint)
0x14010c32d  mov     r13, rax
0x14010c330  mov     [rbp+Buf1], rdi
0x14010c334  mov     [rbp+var_8], edi
0x14010c337  lea     r8, [rbp+Buf1]
0x14010c33b  mov     rdx, rax
0x14010c33e  mov     rcx, [rsi+18h]
0x14010c342  call    cs:__imp_?GetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@PEAVCPropertyValue@2@@Z; MsoCF::IPropertySet::GetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue *)
0x14010c348  mov     [rbp+Buf2], rdi
0x14010c34c  mov     [rbp+var_18], edi
0x14010c34f  cmp     word ptr [rbx+4], 7
0x14010c354  jnz     short loc_14010C386
0x14010c356  mov     rcx, rbx; this
0x14010c359  call    ?GetString@Value@NetUI@@QEBAPEB_WXZ; NetUI::Value::GetString(void)
0x14010c35e  mov     r14, rax
0x14010c361  mov     edx, [rbp+var_18]
0x14010c364  mov     ecx, edx
0x14010c366  shr     ecx, 19h
0x14010c369  test    cl, 1
0x14010c36c  jz      short loc_14010C378
0x14010c36e  lea     rcx, [rbp+Buf2]
0x14010c372  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14010c378  mov     rdx, r14
0x14010c37b  lea     rcx, [rbp+Buf2]
0x14010c37f  call    ??$ProduceAtomFromString@V?$String@UWzTraits@MsoCF@@@MsoCF@@@MsoCF@@YAXPEAPEAVIAtom@0@V?$String@UWzTraits@MsoCF@@@0@@Z; MsoCF::ProduceAtomFromString<MsoCF::String<MsoCF::WzTraits>>(MsoCF::IAtom * *,MsoCF::String<MsoCF::WzTraits>)
0x14010c384  jmp     short loc_14010C398
0x14010c386  lea     rax, ?g_zeroAtom@@3VCEmptyOrZeroAtom@@A; CEmptyOrZeroAtom g_zeroAtom
0x14010c38d  mov     [rbp+Buf2], rax
0x14010c391  lock inc cs:?g_zeroAtom@@3VCEmptyOrZeroAtom@@A; CEmptyOrZeroAtom g_zeroAtom
0x14010c398  mov     r15d, 707003Ah
0x14010c39e  mov     [rbp+var_18], r15d
0x14010c3a2  mov     r14d, [rbp+var_8]
0x14010c3a6  cmp     r14d, r15d
0x14010c3a9  jnz     short loc_14010C3FA
0x14010c3ab  mov     r12d, r14d
0x14010c3ae  mov     r8d, r12d
0x14010c3b1  shr     r8, 15h
0x14010c3b5  and     r8d, 0Fh; Size
0x14010c3b9  lea     rdx, [rbp+Buf2]; Buf2
0x14010c3bd  lea     rcx, [rbp+Buf1]; Buf1
0x14010c3c1  call    memcmp_0
0x14010c3c6  test    eax, eax
0x14010c3c8  jnz     short loc_14010C3CE
0x14010c3ca  mov     al, 1
0x14010c3cc  jmp     short loc_14010C3F6
0x14010c3ce  shr     r12d, 19h
0x14010c3d2  test    r12b, 1
0x14010c3d6  jnz     short loc_14010C3DD
0x14010c3d8  mov     al, dil
0x14010c3db  jmp     short loc_14010C3F6
0x14010c3dd  mov     r8d, r14d
0x14010c3e0  lea     rdx, [rbp+Buf2]
0x14010c3e4  lea     rcx, [rbp+Buf1]
0x14010c3e8  call    cs:__imp_?AreEqual_ComplexType@CPropertyData@MsoCF@@SA_NPEBX0W4PropertyType@2@@Z; MsoCF::CPropertyData::AreEqual_ComplexType(void const *,void const *,MsoCF::PropertyType)
0x14010c3ee  mov     r14d, [rbp+var_8]
0x14010c3f2  mov     r15d, [rbp+var_18]
0x14010c3f6  test    al, al
0x14010c3f8  jnz     short loc_14010C417
0x14010c3fa  lea     r8, [rbp+Buf2]
0x14010c3fe  mov     rdx, r13
0x14010c401  mov     rcx, [rsi+18h]
0x14010c405  call    cs:__imp_?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z; MsoCF::IPropertySet::SetProperty(MsoCF::PropertyInfo const &,MsoCF::CPropertyValue const &)
0x14010c40b  mov     [rsi+28h], dil
0x14010c40f  mov     r14d, [rbp+var_8]
0x14010c413  mov     r15d, [rbp+var_18]
0x14010c417  mov     eax, r15d
0x14010c41a  shr     eax, 19h
0x14010c41d  test    al, 1
0x14010c41f  jz      short loc_14010C432
0x14010c421  mov     edx, r15d
0x14010c424  lea     rcx, [rbp+Buf2]
0x14010c428  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14010c42e  mov     r14d, [rbp+var_8]
0x14010c432  mov     eax, r14d
0x14010c435  shr     eax, 19h
0x14010c438  test    al, 1
0x14010c43a  jz      short loc_14010C449
0x14010c43c  mov     edx, r14d
0x14010c43f  lea     rcx, [rbp+Buf1]
0x14010c443  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14010c449  mov     rcx, rbx
0x14010c44c  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x14010c452  nop
0x14010c453  lea     r11, [rsp+40h+var_s0]
0x14010c458  mov     rbx, [r11+30h]
0x14010c45c  mov     rsi, [r11+38h]
0x14010c460  mov     rdi, [r11+48h]
0x14010c464  mov     rsp, r11
0x14010c467  pop     r15
0x14010c469  pop     r14
0x14010c46b  pop     r13
0x14010c46d  pop     r12
0x14010c46f  pop     rbp
0x14010c470  retn
```
