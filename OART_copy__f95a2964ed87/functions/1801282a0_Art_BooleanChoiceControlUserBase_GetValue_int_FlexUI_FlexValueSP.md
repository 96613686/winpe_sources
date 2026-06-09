# Art::BooleanChoiceControlUserBase::GetValue(int,FlexUI::FlexValueSP &)

- ea: `0x1801282a0`
- end: `0x1801283f1`
- name: `?GetValue@BooleanChoiceControlUserBase@Art@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z`
- size: `337`
- prototype: `bool __fastcall(Art::BooleanChoiceControlUserBase *__hidden this, int, struct FlexUI::FlexValueSP *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1809d2600`

## callees

- `0x1801282a0`
- `0x180128400`
- `0x180278e70`
- `0x180279050`

## import_xrefs

- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x180128301`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x180128301`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18012836e`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1801283b3`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1801283e5`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x18012836e`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1801283b3`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1801283e5`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x18012833a`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x18012833a`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180128360`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x1801283a5`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x1801283d7`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180128360`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x1801283a5`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x1801283d7`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180128347`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18012838c`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1801283be`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180128347`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18012838c`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1801283be`
- `Mso20Win32Client!__imp_?MsoGetApp@@YAHXZ` at `0x1801282ca`
- `Mso20Win32Client!__imp_?MsoGetApp@@YAHXZ` at `0x1801282ca`

## pseudocode

```c
bool __fastcall Art::BooleanChoiceControlUserBase::GetValue(
        Art::BooleanChoiceControlUserBase *this,
        int a2,
        struct FlexUI::FlexValueSP *a3)
{
  int Tcid; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned __int8 v10; // al
  __int64 HinstIntl; // rax
  __int64 v12; // rax
  wchar_t v13[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( a2 == 124 )
  {
    v10 = (*(__int64 (__fastcall **)(Art::BooleanChoiceControlUserBase *))(*(_QWORD *)this + 176LL))(this);
    return FlexUI::FlexValue::CreateInt32(v10, a3);
  }
  else
  {
    if ( MsoGetApp() != 3 )
      return Art::ControlUserBase::GetValue(this, a2, a3);
    Tcid = OfficeSpace::DataSourceBase::GetTcid(this);
    if ( Tcid == 2792 )
    {
      if ( a2 != 56 )
        return Art::ControlUserBase::GetValue(this, a2, a3);
      HinstIntl = MsoGetHinstIntl(v9, v8);
      MsoFLoadWz(HinstIntl, 4093707112LL, v13, 260);
      return FlexUI::FlexValue::CreateString(v13, a3);
    }
    else
    {
      if ( Tcid == 123 )
      {
        if ( a2 != 56 )
          return Art::ControlUserBase::GetValue(this, a2, a3);
      }
      else if ( Tcid != 13900 || a2 != 6 )
      {
        return Art::ControlUserBase::GetValue(this, a2, a3);
      }
      v12 = MsoGetHinstIntl(v9, v8);
      MsoFLoadWz(v12, 4093707111LL, v13, 260);
      return FlexUI::FlexValue::CreateString(v13, a3);
    }
  }
}

```

## disassembly

```asm
0x1801282a0  push    rbx
0x1801282a2  push    rsi
0x1801282a3  push    rdi
0x1801282a4  sub     rsp, 250h
0x1801282ab  mov     rax, cs:__security_cookie
0x1801282b2  xor     rax, rsp
0x1801282b5  mov     [rsp+268h+var_28], rax
0x1801282bd  mov     rsi, r8
0x1801282c0  mov     ebx, edx
0x1801282c2  mov     rdi, rcx
0x1801282c5  cmp     edx, 7Ch ; '|'
0x1801282c8  jz      short loc_180128324
0x1801282ca  call    cs:__imp_?MsoGetApp@@YAHXZ; MsoGetApp(void)
0x1801282d0  cmp     eax, 3
0x1801282d3  jz      short loc_1801282FE
0x1801282d5  mov     r8, rsi; struct FlexUI::FlexValueSP *
0x1801282d8  mov     edx, ebx; int
0x1801282da  mov     rcx, rdi; this
0x1801282dd  call    ?GetValue@ControlUserBase@Art@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z; Art::ControlUserBase::GetValue(int,FlexUI::FlexValueSP &)
0x1801282e2  nop
0x1801282e3  mov     rcx, [rsp+268h+var_28]
0x1801282eb  xor     rcx, rsp; StackCookie
0x1801282ee  call    __security_check_cookie
0x1801282f3  add     rsp, 250h
0x1801282fa  pop     rdi
0x1801282fb  pop     rsi
0x1801282fc  pop     rbx
0x1801282fd  retn
0x1801282fe  mov     rcx, rdi
0x180128301  call    cs:__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ; OfficeSpace::DataSourceBase::GetTcid(void)
0x180128307  cmp     eax, 0AE8h
0x18012830c  jz      short loc_180128342
0x18012830e  cmp     eax, 7Bh ; '{'
0x180128311  jz      short loc_180128383
0x180128313  cmp     eax, 364Ch
0x180128318  jnz     short loc_1801282D5
0x18012831a  cmp     ebx, 6
0x18012831d  jnz     short loc_1801282D5
0x18012831f  jmp     loc_1801283BE
0x180128324  mov     rax, [rcx]
0x180128327  mov     rax, [rax+0B0h]
0x18012832e  call    cs:__guard_dispatch_icall_fptr
0x180128334  movzx   ecx, al
0x180128337  mov     rdx, rsi
0x18012833a  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x180128340  jmp     short loc_1801282E3
0x180128342  cmp     ebx, 38h ; '8'
0x180128345  jnz     short loc_1801282D5
0x180128347  call    cs:__imp_MsoGetHinstIntl
0x18012834d  mov     rcx, rax
0x180128350  mov     r9d, 104h
0x180128356  lea     r8, [rsp+268h+var_238]
0x18012835b  mov     edx, 0F4010368h
0x180128360  call    cs:__imp_MsoFLoadWz
0x180128366  mov     rdx, rsi
0x180128369  lea     rcx, [rsp+268h+var_238]
0x18012836e  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x180128374  jmp     loc_1801282E3
0x180128379  movzx   eax, [rsp+268h+var_248]
0x18012837e  jmp     loc_1801282E3
0x180128383  cmp     ebx, 38h ; '8'
0x180128386  jnz     loc_1801282D5
0x18012838c  call    cs:__imp_MsoGetHinstIntl
0x180128392  mov     rcx, rax
0x180128395  mov     r9d, 104h
0x18012839b  lea     r8, [rsp+268h+var_238]
0x1801283a0  mov     edx, 0F4010367h
0x1801283a5  call    cs:__imp_MsoFLoadWz
0x1801283ab  mov     rdx, rsi
0x1801283ae  lea     rcx, [rsp+268h+var_238]
0x1801283b3  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1801283b9  jmp     loc_1801282E3
0x1801283be  call    cs:__imp_MsoGetHinstIntl
0x1801283c4  mov     rcx, rax
0x1801283c7  mov     r9d, 104h
0x1801283cd  lea     r8, [rsp+268h+var_238]
0x1801283d2  mov     edx, 0F4010367h
0x1801283d7  call    cs:__imp_MsoFLoadWz
0x1801283dd  mov     rdx, rsi
0x1801283e0  lea     rcx, [rsp+268h+var_238]
0x1801283e5  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1801283eb  jmp     loc_1801282E3
```
