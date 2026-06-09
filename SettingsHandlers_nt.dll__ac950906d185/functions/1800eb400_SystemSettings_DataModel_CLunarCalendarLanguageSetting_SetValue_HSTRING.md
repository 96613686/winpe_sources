# SystemSettings::DataModel::CLunarCalendarLanguageSetting::SetValue(HSTRING__ *)

- ea: `0x1800eb400`
- end: `0x1800eb596`
- name: `?SetValue@CLunarCalendarLanguageSetting@DataModel@SystemSettings@@MEAAJPEAUHSTRING__@@@Z`
- size: `406`
- prototype: `int(SystemSettings::DataModel::CLunarCalendarLanguageSetting *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x180043d18`
- `0x180057424`
- `0x18005fd48`
- `0x1800e6fb4`
- `0x1800eb400`
- `0x1800ebda8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800eb4c6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800eb4c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb56f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb56f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb582`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eb42d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eb4a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eb42d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eb4a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::CLunarCalendarLanguageSetting::SetValue(
        const unsigned __int16 **this,
        HSTRING a2)
{
  const WCHAR *StringRawBuffer; // r14
  unsigned __int64 i; // rdi
  SystemSettings::DataModel::CLunarCalendarLanguageSetting *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  HSTRING v8; // rbx
  const WCHAR *v9; // rax
  int v10; // r9d
  const char *v11; // r9
  BOOL bIgnoreCase; // [rsp+20h] [rbp-88h]
  HSTRING string; // [rsp+48h] [rbp-60h] BYREF
  char v15; // [rsp+50h] [rbp-58h] BYREF
  std::_Ref_count_base *v16; // [rsp+58h] [rbp-50h]
  _BYTE v17[32]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  for ( i = 1; ; ++i )
  {
    if ( i >= 4 )
      return 0;
    WindowsDeleteString(0);
    string = 0;
    v6 = SystemSettings::DataModel::CLunarCalendarLanguageSetting::_ConvertLunarCalendarLanguageTypeStringToResourceStringId(
           v5,
           this[i + 27],
           &string);
    v7 = v6;
    if ( v6 < 0 )
      break;
    v8 = string;
    v9 = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(v9, -1, StringRawBuffer, -1, 1) == 2 )
    {
      try
      {
        *((_DWORD *)this + 76) = i;
        std::string::string(v17, &MultiByteStr);
        wil::cloud_store::save_async_internal<Windows::Data::LunarCalendar>(
          (_DWORD)this + 264,
          (unsigned int)&v15,
          (_DWORD)this + 304,
          v10,
          bIgnoreCase);
        std::string::_Tidy_deallocate(v17);
        if ( v16 )
          std::_Ref_count_base::_Decref(v16);
        WindowsDeleteString(v8);
      }
      catch ( ... )
      {
        v7 = wil::details::in1diag3::Return_CaughtException(
               retaddr,
               (void *)0x208,
               (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\datetime\\datetime.cpp",
               v11);
        goto LABEL_11;
      }
      return 0;
    }
    WindowsDeleteString(v8);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x200,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\datetime\\datetime.cpp",
    (const char *)(unsigned int)v6,
    bIgnoreCase);
LABEL_11:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x1800eb400  mov     [rsp+arg_10], rbx
0x1800eb405  push    rsi
0x1800eb406  push    rdi
0x1800eb407  push    r14
0x1800eb409  sub     rsp, 90h
0x1800eb410  mov     rax, cs:__security_cookie
0x1800eb417  xor     rax, rsp
0x1800eb41a  mov     [rsp+0A8h+var_28], rax
0x1800eb422  mov     rax, rdx
0x1800eb425  mov     rsi, rcx
0x1800eb428  xor     edx, edx; length
0x1800eb42a  mov     rcx, rax; string
0x1800eb42d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800eb434  nop     dword ptr [rax+rax+00h]
0x1800eb439  mov     r14, rax
0x1800eb43c  mov     edi, 1
0x1800eb441  cmp     rdi, 4
0x1800eb445  jnb     loc_1800EB53F
0x1800eb44b  xor     ecx, ecx; string
0x1800eb44d  call    cs:__imp_WindowsDeleteString
0x1800eb454  nop     dword ptr [rax+rax+00h]
0x1800eb459  mov     [rsp+0A8h+string], 0
0x1800eb462  lea     r8, [rsp+0A8h+string]; HSTRING *
0x1800eb467  mov     rdx, [rsi+rdi*8+0D8h]; unsigned __int16 *
0x1800eb46f  call    ?_ConvertLunarCalendarLanguageTypeStringToResourceStringId@CLunarCalendarLanguageSetting@DataModel@SystemSettings@@AEAAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::CLunarCalendarLanguageSetting::_ConvertLunarCalendarLanguageTypeStringToResourceStringId(ushort const *,HSTRING__ * *)
0x1800eb474  mov     ebx, eax
0x1800eb476  test    eax, eax
0x1800eb478  jns     short loc_1800EB49B
0x1800eb47a  mov     rcx, [rsp+0A8h]; this
0x1800eb482  mov     r9d, eax; char *
0x1800eb485  lea     r8, aShellSystemset_78; "shell\\systemsettingsthreshold\\handler"...
0x1800eb48c  mov     edx, 200h; void *
0x1800eb491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb496  jmp     loc_1800EB56A
0x1800eb49b  xor     edx, edx; length
0x1800eb49d  mov     rbx, [rsp+0A8h+string]
0x1800eb4a2  mov     rcx, rbx; string
0x1800eb4a5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800eb4ac  nop     dword ptr [rax+rax+00h]
0x1800eb4b1  mov     [rsp+0A8h+bIgnoreCase], 1; bIgnoreCase
0x1800eb4b9  or      r9d, 0FFFFFFFFh; cchCount2
0x1800eb4bd  mov     r8, r14; lpString2
0x1800eb4c0  or      edx, r9d; cchCount1
0x1800eb4c3  mov     rcx, rax; lpString1
0x1800eb4c6  call    cs:__imp_CompareStringOrdinal
0x1800eb4cd  nop     dword ptr [rax+rax+00h]
0x1800eb4d2  cmp     eax, 2
0x1800eb4d5  jnz     loc_1800EB57F
0x1800eb4db  lea     r14, [rsi+130h]
0x1800eb4e2  mov     [r14], edi
0x1800eb4e5  lea     rdx, MultiByteStr
0x1800eb4ec  lea     rcx, [rsp+0A8h+var_48]
0x1800eb4f1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800eb4f6  nop
0x1800eb4f7  lea     rax, [rsp+0A8h+var_48]
0x1800eb4fc  mov     [rsp+0A8h+var_78], rax
0x1800eb501  mov     r8, r14
0x1800eb504  lea     rdx, [rsp+0A8h+var_58]
0x1800eb509  lea     rcx, [rsi+108h]
0x1800eb510  call    ??$save_async_internal@ULunarCalendar@Data@Windows@@@cloud_store@wil@@AEAA?AV?$task@Vcloud_store_save_result@wil@@@Concurrency@@AEBV?$cloud_store_data@ULunarCalendar@Data@Windows@@@1@PEBU?$ItemReference@ULunarCalendar@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_save_options@1@_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; wil::cloud_store::save_async_internal<Windows::Data::LunarCalendar>(wil::cloud_store_data<Windows::Data::LunarCalendar> const &,Windows::Data::Platform::ItemReference<Windows::Data::LunarCalendar> const *,wil::cloud_store_save_options,unsigned __int64,std::string const &)
0x1800eb515  nop
0x1800eb516  lea     rcx, [rsp+0A8h+var_48]
0x1800eb51b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800eb520  mov     rcx, [rsp+0A8h+var_50]; this
0x1800eb525  test    rcx, rcx
0x1800eb528  jz      short loc_1800EB530
0x1800eb52a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800eb52f  nop
0x1800eb530  mov     rcx, rbx; string
0x1800eb533  call    cs:__imp_WindowsDeleteString
0x1800eb53a  nop     dword ptr [rax+rax+00h]
0x1800eb53f  xor     eax, eax
0x1800eb541  mov     rcx, [rsp+0A8h+var_28]
0x1800eb549  xor     rcx, rsp; StackCookie
0x1800eb54c  call    __security_check_cookie
0x1800eb551  mov     rbx, [rsp+0A8h+arg_10]
0x1800eb559  add     rsp, 90h
0x1800eb560  pop     r14
0x1800eb562  pop     rdi
0x1800eb563  pop     rsi
0x1800eb564  retn
0x1800eb566  mov     ebx, [rsp+0A8h+var_68]
0x1800eb56a  mov     rcx, [rsp+0A8h+string]; string
0x1800eb56f  call    cs:__imp_WindowsDeleteString
0x1800eb576  nop     dword ptr [rax+rax+00h]
0x1800eb57b  mov     eax, ebx
0x1800eb57d  jmp     short loc_1800EB541
0x1800eb57f  mov     rcx, rbx; string
0x1800eb582  call    cs:__imp_WindowsDeleteString
0x1800eb589  nop     dword ptr [rax+rax+00h]
0x1800eb58e  inc     rdi
0x1800eb591  jmp     loc_1800EB441
```
