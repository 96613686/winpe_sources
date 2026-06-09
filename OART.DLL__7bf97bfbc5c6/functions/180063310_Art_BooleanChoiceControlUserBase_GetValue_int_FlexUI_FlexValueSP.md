# Art::BooleanChoiceControlUserBase::GetValue(int,FlexUI::FlexValueSP &)

- ea: `0x180063310`
- end: `0x180063461`
- name: `?GetValue@BooleanChoiceControlUserBase@Art@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z`
- size: `337`
- prototype: `bool __fastcall(Art::BooleanChoiceControlUserBase *__hidden this, int, struct FlexUI::FlexValueSP *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1809c9c60`

## callees

- `0x18005f7f0`
- `0x180063310`
- `0x180070fe0`
- `0x180071720`

## import_xrefs

- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x180063371`
- `Mso98Win32Client!__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ` at `0x180063371`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1800633de`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180063423`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180063455`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x1800633de`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180063423`
- `mso40uiWin32Client!__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z` at `0x180063455`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1800633aa`
- `mso40uiWin32Client!__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z` at `0x1800633aa`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x1800633d0`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180063415`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180063447`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x1800633d0`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180063415`
- `Mso30Win32Client!__imp_MsoFLoadWz` at `0x180063447`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1800633b7`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1800633fc`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18006342e`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1800633b7`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1800633fc`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18006342e`
- `Mso20Win32Client!__imp_?MsoGetApp@@YAHXZ` at `0x18006333a`
- `Mso20Win32Client!__imp_?MsoGetApp@@YAHXZ` at `0x18006333a`

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
      MsoFLoadWz(HinstIntl, 4093707111LL, v13, 260);
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
      MsoFLoadWz(v12, 4093707110LL, v13, 260);
      return FlexUI::FlexValue::CreateString(v13, a3);
    }
  }
}

```

## disassembly

```asm
0x180063310  push    rbx
0x180063312  push    rsi
0x180063313  push    rdi
0x180063314  sub     rsp, 250h
0x18006331b  mov     rax, cs:__security_cookie
0x180063322  xor     rax, rsp
0x180063325  mov     [rsp+268h+var_28], rax
0x18006332d  mov     rsi, r8
0x180063330  mov     ebx, edx
0x180063332  mov     rdi, rcx
0x180063335  cmp     edx, 7Ch ; '|'
0x180063338  jz      short loc_180063394
0x18006333a  call    cs:__imp_?MsoGetApp@@YAHXZ; MsoGetApp(void)
0x180063340  cmp     eax, 3
0x180063343  jz      short loc_18006336E
0x180063345  mov     r8, rsi; struct FlexUI::FlexValueSP *
0x180063348  mov     edx, ebx; int
0x18006334a  mov     rcx, rdi; this
0x18006334d  call    ?GetValue@ControlUserBase@Art@@UEAA_NHAEAVFlexValueSP@FlexUI@@@Z; Art::ControlUserBase::GetValue(int,FlexUI::FlexValueSP &)
0x180063352  nop
0x180063353  mov     rcx, [rsp+268h+var_28]
0x18006335b  xor     rcx, rsp; StackCookie
0x18006335e  call    __security_check_cookie
0x180063363  add     rsp, 250h
0x18006336a  pop     rdi
0x18006336b  pop     rsi
0x18006336c  pop     rbx
0x18006336d  retn
0x18006336e  mov     rcx, rdi
0x180063371  call    cs:__imp_?GetTcid@DataSourceBase@OfficeSpace@@IEBAHXZ; OfficeSpace::DataSourceBase::GetTcid(void)
0x180063377  cmp     eax, 0AE8h
0x18006337c  jz      short loc_1800633B2
0x18006337e  cmp     eax, 7Bh ; '{'
0x180063381  jz      short loc_1800633F3
0x180063383  cmp     eax, 364Ch
0x180063388  jnz     short loc_180063345
0x18006338a  cmp     ebx, 6
0x18006338d  jnz     short loc_180063345
0x18006338f  jmp     loc_18006342E
0x180063394  mov     rax, [rcx]
0x180063397  mov     rax, [rax+0B0h]
0x18006339e  call    cs:__guard_dispatch_icall_fptr
0x1800633a4  movzx   ecx, al
0x1800633a7  mov     rdx, rsi
0x1800633aa  call    cs:__imp_?CreateInt32@FlexValue@FlexUI@@SA_NHAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateInt32(int,FlexUI::FlexValueSP &)
0x1800633b0  jmp     short loc_180063353
0x1800633b2  cmp     ebx, 38h ; '8'
0x1800633b5  jnz     short loc_180063345
0x1800633b7  call    cs:__imp_MsoGetHinstIntl
0x1800633bd  mov     rcx, rax
0x1800633c0  mov     r9d, 104h
0x1800633c6  lea     r8, [rsp+268h+var_238]
0x1800633cb  mov     edx, 0F4010367h
0x1800633d0  call    cs:__imp_MsoFLoadWz
0x1800633d6  mov     rdx, rsi
0x1800633d9  lea     rcx, [rsp+268h+var_238]
0x1800633de  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x1800633e4  jmp     loc_180063353
0x1800633e9  movzx   eax, [rsp+268h+var_248]
0x1800633ee  jmp     loc_180063353
0x1800633f3  cmp     ebx, 38h ; '8'
0x1800633f6  jnz     loc_180063345
0x1800633fc  call    cs:__imp_MsoGetHinstIntl
0x180063402  mov     rcx, rax
0x180063405  mov     r9d, 104h
0x18006340b  lea     r8, [rsp+268h+var_238]
0x180063410  mov     edx, 0F4010366h
0x180063415  call    cs:__imp_MsoFLoadWz
0x18006341b  mov     rdx, rsi
0x18006341e  lea     rcx, [rsp+268h+var_238]
0x180063423  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x180063429  jmp     loc_180063353
0x18006342e  call    cs:__imp_MsoGetHinstIntl
0x180063434  mov     rcx, rax
0x180063437  mov     r9d, 104h
0x18006343d  lea     r8, [rsp+268h+var_238]
0x180063442  mov     edx, 0F4010366h
0x180063447  call    cs:__imp_MsoFLoadWz
0x18006344d  mov     rdx, rsi
0x180063450  lea     rcx, [rsp+268h+var_238]
0x180063455  call    cs:__imp_?CreateString@FlexValue@FlexUI@@SA_NPEB_WAEAVFlexValueSP@2@@Z; FlexUI::FlexValue::CreateString(wchar_t const *,FlexUI::FlexValueSP &)
0x18006345b  jmp     loc_180063353
```
