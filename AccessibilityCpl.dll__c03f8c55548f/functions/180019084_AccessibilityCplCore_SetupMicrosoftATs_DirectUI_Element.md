# AccessibilityCplCore::SetupMicrosoftATs(DirectUI::Element *)

- ea: `0x180019084`
- end: `0x18001918e`
- name: `?SetupMicrosoftATs@AccessibilityCplCore@@AEAAJPEAVElement@DirectUI@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180018688`

## callees

- `0x180004f78`
- `0x180005534`
- `0x1800063c0`
- `0x180015780`
- `0x180019084`
- `0x180020dfc`
- `0x180020edc`
- `0x180023090`
- `0x18002d1ee`
- `0x18002d1fa`
- `0x18002d220`

## import_xrefs

- `KERNEL32!GetAtomNameW` at `0x1800190e0`
- `KERNEL32!GetAtomNameW` at `0x1800190e0`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800190ae`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800190ae`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800190cc`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x1800190cc`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001915b`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001915b`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SetupMicrosoftATs(AccessibilityCplCore *this, struct DirectUI::Element *a2)
{
  DirectUI::Element *Parent; // rbx
  ATOM ID; // ax
  struct Accommodation *v6; // rax
  Accommodation *v7; // rdi
  bool v8; // dl
  StartList *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rbx
  ATL::CStringData *v12; // r11
  WCHAR Buffer[128]; // [rsp+20h] [rbp-128h] BYREF

  Parent = DirectUI::Element::GetParent(a2);
  memset_0(Buffer, 0, sizeof(Buffer));
  ID = DirectUI::Element::GetID(Parent);
  if ( GetAtomNameW(ID, Buffer, 128) )
  {
    v6 = Accommodation::Open(Buffer);
    v7 = v6;
    if ( v6 )
    {
      if ( !wcscmp_0(*((const wchar_t **)v6 + 5), L"SystemSetting") )
      {
        v8 = (unsigned int)Accommodation::IsRunning(v7) != 0;
      }
      else
      {
        v9 = (StartList *)*((_QWORD *)this + 11);
        StartList::LoadSettings(v9);
        v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)v7 - 24LL);
        v11 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
                v9,
                v10 + 24);
        ATL::CStringData::Release(v12);
        if ( !v11 )
        {
LABEL_8:
          Accommodation::`scalar deleting destructor'(v7);
          return 0;
        }
        v8 = 1;
      }
      DirectUI::Element::SetSelected(a2, v8);
      goto LABEL_8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019084  mov     [rsp+arg_10], rbx
0x180019089  push    rbp
0x18001908a  push    rsi
0x18001908b  push    rdi
0x18001908c  sub     rsp, 130h
0x180019093  mov     rax, cs:__security_cookie
0x18001909a  xor     rax, rsp
0x18001909d  mov     [rsp+148h+var_28], rax
0x1800190a5  mov     rbp, rcx
0x1800190a8  mov     rsi, rdx
0x1800190ab  mov     rcx, rdx
0x1800190ae  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x1800190b4  xor     edx, edx; Val
0x1800190b6  lea     rcx, [rsp+148h+Buffer]; void *
0x1800190bb  mov     r8d, 100h; Size
0x1800190c1  mov     rbx, rax
0x1800190c4  call    memset_0
0x1800190c9  mov     rcx, rbx
0x1800190cc  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x1800190d2  mov     r8d, 80h; nSize
0x1800190d8  lea     rdx, [rsp+148h+Buffer]; lpBuffer
0x1800190dd  movzx   ecx, ax; nAtom
0x1800190e0  call    cs:__imp_GetAtomNameW
0x1800190e6  test    eax, eax
0x1800190e8  jz      short loc_180019169
0x1800190ea  lea     rcx, [rsp+148h+Buffer]; unsigned __int16 *
0x1800190ef  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x1800190f4  mov     rdi, rax
0x1800190f7  test    rax, rax
0x1800190fa  jz      short loc_180019169
0x1800190fc  mov     rcx, [rax+28h]; String1
0x180019100  lea     rdx, aSystemsetting; "SystemSetting"
0x180019107  call    wcscmp_0
0x18001910c  test    eax, eax
0x18001910e  jnz     short loc_18001911F
0x180019110  mov     rcx, rdi; this
0x180019113  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x180019118  test    eax, eax
0x18001911a  setnz   dl
0x18001911d  jmp     short loc_180019158
0x18001911f  mov     rbx, [rbp+58h]
0x180019123  mov     rcx, rbx; this
0x180019126  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x18001912b  mov     rcx, [rdi]
0x18001912e  sub     rcx, 18h
0x180019132  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180019137  mov     rcx, rbx
0x18001913a  mov     r11, rax
0x18001913d  lea     rdx, [rax+18h]
0x180019141  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x180019146  mov     rcx, r11; this
0x180019149  mov     rbx, rax
0x18001914c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019151  test    rbx, rbx
0x180019154  jz      short loc_180019161
0x180019156  mov     dl, 1
0x180019158  mov     rcx, rsi
0x18001915b  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180019161  mov     rcx, rdi; this
0x180019164  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180019169  xor     eax, eax
0x18001916b  mov     rcx, [rsp+148h+var_28]
0x180019173  xor     rcx, rsp; StackCookie
0x180019176  call    __security_check_cookie
0x18001917b  mov     rbx, [rsp+148h+arg_10]
0x180019183  add     rsp, 130h
0x18001918a  pop     rdi
0x18001918b  pop     rsi
0x18001918c  pop     rbp
0x18001918d  retn
```
