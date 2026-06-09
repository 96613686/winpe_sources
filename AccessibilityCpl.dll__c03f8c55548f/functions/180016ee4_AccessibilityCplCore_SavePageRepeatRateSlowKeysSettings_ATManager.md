# AccessibilityCplCore::SavePageRepeatRateSlowKeysSettings(ATManager *)

- ea: `0x180016ee4`
- end: `0x18001710d`
- name: `?SavePageRepeatRateSlowKeysSettings@AccessibilityCplCore@@AEAAJPEAVATManager@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct ATManager *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800134a0`
- `0x1800143a0`

## callees

- `0x180004f78`
- `0x1800055c0`
- `0x180007644`
- `0x180014828`
- `0x180016ee4`
- `0x180018260`
- `0x180020d64`
- `0x180020edc`
- `0x1800241b0`
- `0x18002d220`

## import_xrefs

- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016f7a`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x180016f7a`
- `DUI70!StrToID` at `0x180016f60`
- `DUI70!StrToID` at `0x180016f99`
- `DUI70!StrToID` at `0x180016fb9`
- `DUI70!StrToID` at `0x180017013`
- `DUI70!StrToID` at `0x180016f60`
- `DUI70!StrToID` at `0x180016f99`
- `DUI70!StrToID` at `0x180016fb9`
- `DUI70!StrToID` at `0x180017013`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016f6c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016fa5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016fc5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001701f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016f6c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016fa5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016fc5`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001701f`

## string_xrefs

- `0x180017071`: `Control Panel\Accessibility\Keyboard Response`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SavePageRepeatRateSlowKeysSettings(
        AccessibilityCplCore *this,
        struct ATManager *a2)
{
  unsigned int v4; // edi
  const wchar_t **v5; // rbx
  DirectUI::Element *v6; // rdi
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v9; // rdi
  unsigned __int16 v10; // ax
  struct DirectUI::Element *v11; // rax
  DirectUI::Element *v12; // rdi
  struct DirectUI::Combobox *v13; // r14
  unsigned __int16 v14; // ax
  struct DirectUI::Element *v15; // rax
  AccessibilityCplCore *v16; // rcx
  struct DirectUI::Combobox *v17; // rdi
  AccessibilityCplCore *v18; // rcx
  DirectUI::Element *v19; // rdi
  unsigned __int16 v20; // ax
  struct DirectUI::Combobox *v21; // rax
  AccessibilityCplCore *v22; // rcx
  unsigned int v23; // edx
  HKEY v25[3]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v26[6]; // [rsp+48h] [rbp-28h] BYREF

  v4 = 0;
  v5 = (const wchar_t **)Accommodation::Open(L"filterkeys");
  if ( v5 )
  {
    memset(v26, 0, sizeof(v26));
    Accommodation::GetData(v5, v26);
    if ( !*((_DWORD *)this + 50) )
      Accommodation::GetData(v5, (_DWORD *)this + 51);
    v6 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v7 = StrToID(L"nokeyboardrepeat");
    Descendent = DirectUI::Element::FindDescendent(v6, v7);
    if ( Descendent && DirectUI::Element::GetSelected(Descendent) )
    {
      *(_QWORD *)&v26[3] = 0;
    }
    else
    {
      v9 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v10 = StrToID(L"repeat");
      v11 = DirectUI::Element::FindDescendent(v9, v10);
      v12 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v13 = v11;
      v14 = StrToID(L"delay");
      v15 = DirectUI::Element::FindDescendent(v12, v14);
      v17 = v15;
      if ( v13 || v15 )
      {
        v26[4] = AccessibilityCplCore::GetValuefromCombo(v16, v13, &qword_180033880, 6);
        v26[3] = AccessibilityCplCore::GetValuefromCombo(v18, v17, &qword_1800338A0, 6);
      }
    }
    v19 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v20 = StrToID(L"wait");
    v21 = DirectUI::Element::FindDescendent(v19, v20);
    if ( v21 )
      v26[2] = AccessibilityCplCore::GetValuefromCombo(v22, v21, &qword_180033830, 10);
    v26[5] = 0;
    memset(v25, 0, sizeof(v25));
    v4 = (unsigned int)StartList::Start(a2, v5, v26, 0, 0);
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)v25,
                          HKEY_CURRENT_USER,
                          L"Control Panel\\Accessibility\\Keyboard Response",
                          0x2001Fu) )
    {
      ATL::CRegKey::SetDWORDValue(v25, L"Last Valid Delay", v26[3]);
      ATL::CRegKey::SetDWORDValue(v25, L"Last Valid Repeat", v26[4]);
      ATL::CRegKey::SetDWORDValue(v25, L"Last Valid Wait", v26[2]);
    }
    ATL::CRegKey::Close((ATL::CRegKey *)v25);
    Accommodation::`scalar deleting destructor'((Accommodation *)v5, v23);
  }
  return v4;
}

```

## disassembly

```asm
0x180016ee4  mov     [rsp-28h+arg_10], rbx
0x180016ee9  push    rbp
0x180016eea  push    rsi
0x180016eeb  push    rdi
0x180016eec  push    r14
0x180016eee  push    r15
0x180016ef0  mov     rbp, rsp
0x180016ef3  sub     rsp, 70h
0x180016ef7  mov     rax, cs:__security_cookie
0x180016efe  xor     rax, rsp
0x180016f01  mov     [rbp+var_10], rax
0x180016f05  mov     rsi, rcx
0x180016f08  mov     r15, rdx
0x180016f0b  lea     rcx, aFilterkeys; "filterkeys"
0x180016f12  xor     edi, edi
0x180016f14  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180016f19  mov     rbx, rax
0x180016f1c  test    rax, rax
0x180016f1f  jz      loc_1800170EB
0x180016f25  xorps   xmm0, xmm0
0x180016f28  lea     rdx, [rbp+var_28]; void *
0x180016f2c  xor     eax, eax
0x180016f2e  mov     rcx, rbx; this
0x180016f31  movups  xmmword ptr [rbp+var_28], xmm0
0x180016f35  mov     qword ptr [rbp+var_18], rax
0x180016f39  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180016f3e  cmp     [rsi+0C8h], edi
0x180016f44  jnz     short loc_180016F55
0x180016f46  lea     rdx, [rsi+0CCh]; void *
0x180016f4d  mov     rcx, rbx; this
0x180016f50  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180016f55  mov     rdi, [rsi+60h]
0x180016f59  lea     rcx, aNokeyboardrepe; "nokeyboardrepeat"
0x180016f60  call    cs:__imp_StrToID
0x180016f66  movzx   edx, ax
0x180016f69  mov     rcx, rdi
0x180016f6c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016f72  test    rax, rax
0x180016f75  jz      short loc_180016F8E
0x180016f77  mov     rcx, rax
0x180016f7a  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x180016f80  test    al, al
0x180016f82  jz      short loc_180016F8E
0x180016f84  mov     qword ptr [rbp+var_28+0Ch], 0
0x180016f8c  jmp     short loc_180017008
0x180016f8e  mov     rdi, [rsi+60h]
0x180016f92  lea     rcx, aRepeat; "repeat"
0x180016f99  call    cs:__imp_StrToID
0x180016f9f  movzx   edx, ax
0x180016fa2  mov     rcx, rdi
0x180016fa5  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016fab  mov     rdi, [rsi+60h]
0x180016faf  lea     rcx, aDelay; "delay"
0x180016fb6  mov     r14, rax
0x180016fb9  call    cs:__imp_StrToID
0x180016fbf  movzx   edx, ax
0x180016fc2  mov     rcx, rdi
0x180016fc5  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016fcb  mov     rdi, rax
0x180016fce  test    r14, r14
0x180016fd1  jnz     short loc_180016FD8
0x180016fd3  test    rax, rax
0x180016fd6  jz      short loc_180017008
0x180016fd8  mov     r9d, 6; int
0x180016fde  lea     r8, qword_180033880; unsigned int *
0x180016fe5  mov     rdx, r14; struct DirectUI::Combobox *
0x180016fe8  call    ?GetValuefromCombo@AccessibilityCplCore@@AEAAIPEAVCombobox@DirectUI@@PEBIH@Z; AccessibilityCplCore::GetValuefromCombo(DirectUI::Combobox *,uint const *,int)
0x180016fed  mov     r9d, 6; int
0x180016ff3  mov     [rbp+var_18], eax
0x180016ff6  lea     r8, qword_1800338A0; unsigned int *
0x180016ffd  mov     rdx, rdi; struct DirectUI::Combobox *
0x180017000  call    ?GetValuefromCombo@AccessibilityCplCore@@AEAAIPEAVCombobox@DirectUI@@PEBIH@Z; AccessibilityCplCore::GetValuefromCombo(DirectUI::Combobox *,uint const *,int)
0x180017005  mov     [rbp+var_28+0Ch], eax
0x180017008  mov     rdi, [rsi+60h]
0x18001700c  lea     rcx, aWait_0; "wait"
0x180017013  call    cs:__imp_StrToID
0x180017019  movzx   edx, ax
0x18001701c  mov     rcx, rdi
0x18001701f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180017025  test    rax, rax
0x180017028  jz      short loc_180017042
0x18001702a  mov     r9d, 0Ah; int
0x180017030  lea     r8, qword_180033830; unsigned int *
0x180017037  mov     rdx, rax; struct DirectUI::Combobox *
0x18001703a  call    ?GetValuefromCombo@AccessibilityCplCore@@AEAAIPEAVCombobox@DirectUI@@PEBIH@Z; AccessibilityCplCore::GetValuefromCombo(DirectUI::Combobox *,uint const *,int)
0x18001703f  mov     [rbp+var_28+8], eax
0x180017042  xor     r9d, r9d; int
0x180017045  mov     [rbp+var_18+4], 0
0x18001704c  lea     r8, [rbp+var_28]; void *
0x180017050  mov     [rsp+70h+var_50], 0; int
0x180017058  mov     rdx, rbx; struct Accommodation *
0x18001705b  mov     rcx, r15; this
0x18001705e  call    ?Start@StartList@@QEAAJPEAVAccommodation@@PEAXHH@Z; StartList::Start(Accommodation *,void *,int,int)
0x180017063  mov     r9d, 2001Fh; unsigned int
0x180017069  mov     [rbp+var_40], 0
0x180017071  lea     r8, aControlPanelAc; "Control Panel\\Accessibility\\Keyboard "...
0x180017078  mov     [rbp+var_38], 0
0x180017080  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180017087  mov     [rbp+var_30], 0
0x18001708f  lea     rcx, [rbp+var_40]; this
0x180017093  mov     edi, eax
0x180017095  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001709a  test    eax, eax
0x18001709c  jnz     short loc_1800170DA
0x18001709e  mov     r8d, [rbp+var_28+0Ch]; unsigned int
0x1800170a2  lea     rdx, aLastValidDelay; "Last Valid Delay"
0x1800170a9  lea     rcx, [rbp+var_40]; this
0x1800170ad  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800170b2  mov     r8d, [rbp+var_18]; unsigned int
0x1800170b6  lea     rdx, aLastValidRepea; "Last Valid Repeat"
0x1800170bd  lea     rcx, [rbp+var_40]; this
0x1800170c1  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800170c6  mov     r8d, [rbp+var_28+8]; unsigned int
0x1800170ca  lea     rdx, aLastValidWait; "Last Valid Wait"
0x1800170d1  lea     rcx, [rbp+var_40]; this
0x1800170d5  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800170da  lea     rcx, [rbp+var_40]; this
0x1800170de  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800170e3  mov     rcx, rbx; this
0x1800170e6  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x1800170eb  mov     eax, edi
0x1800170ed  mov     rcx, [rbp+var_10]
0x1800170f1  xor     rcx, rsp; StackCookie
0x1800170f4  call    __security_check_cookie
0x1800170f9  mov     rbx, [rsp+70h+arg_10]
0x180017101  add     rsp, 70h
0x180017105  pop     r15
0x180017107  pop     r14
0x180017109  pop     rdi
0x18001710a  pop     rsi
0x18001710b  pop     rbp
0x18001710c  retn
```
