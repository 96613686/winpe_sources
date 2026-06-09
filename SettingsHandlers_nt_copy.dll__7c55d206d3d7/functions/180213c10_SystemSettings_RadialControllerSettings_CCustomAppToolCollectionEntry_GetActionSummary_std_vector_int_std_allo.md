# SystemSettings::RadialControllerSettings::CCustomAppToolCollectionEntry::GetActionSummary(std::vector<int,std::allocator<int>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180213c10`
- end: `0x180213e06`
- name: `?GetActionSummary@CCustomAppToolCollectionEntry@RadialControllerSettings@SystemSettings@@CAJAEBV?$vector@HV?$allocator@H@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1802140d4`

## callees

- `0x180019a20`
- `0x18002395c`
- `0x180045a90`
- `0x18004d1ac`
- `0x1802126a4`
- `0x1802127e8`
- `0x180213c10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213d00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213d66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213de1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213d00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213d66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213de1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180213c99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180213d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180213dc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180213c99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180213d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180213dc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::RadialControllerSettings::CCustomAppToolCollectionEntry::GetActionSummary(
        __int64 a1,
        __int64 a2)
{
  SystemSettings::DataModel *v4; // rbx
  HSTRING *v5; // r8
  int ResourceStringById; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  PCWSTR StringRawBuffer; // rax
  HSTRING *v11; // r8
  int v12; // eax
  unsigned int v13; // ebx
  PCWSTR v14; // rdx
  __int64 CustomActionItem_FromBaseKeyList; // rax
  wchar_t *v16; // rbx
  HSTRING *v17; // r8
  int v18; // eax
  unsigned int v19; // ebx
  PCWSTR v20; // rdx
  int v21[10]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  try
  {
    v4 = *(SystemSettings::DataModel **)(SystemSettings::RadialControllerSettings::CustomActionUtilities::GetCustomActionItem_FromModifierKeyList()
                                       + 16);
    WindowsDeleteString(0);
    string = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(v4, &string, v5);
    v7 = ResourceStringById;
    if ( ResourceStringById >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::wstring::assign(a2, StringRawBuffer);
      WindowsDeleteString(string);
      string = 0;
      v12 = SystemSettings::DataModel::GetResourceStringById(
              (SystemSettings::DataModel *)L"SystemSettings_Devices_RadialController_Concat",
              &string,
              v11);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v14 = WindowsGetStringRawBuffer(string, 0);
        std::wstring::append(a2, v14);
        CustomActionItem_FromBaseKeyList = SystemSettings::RadialControllerSettings::CustomActionUtilities::GetCustomActionItem_FromBaseKeyList(
                                             v21,
                                             a1);
        if ( *(_DWORD *)(CustomActionItem_FromBaseKeyList + 4) == 30 )
        {
          v16 = L"SystemSettings_Devices_RadialController_HyphenDescription";
        }
        else if ( *(_DWORD *)(CustomActionItem_FromBaseKeyList + 4) == 31 )
        {
          v16 = L"SystemSettings_Devices_RadialController_PlusDescription";
        }
        else
        {
          v16 = *(wchar_t **)(CustomActionItem_FromBaseKeyList + 8);
        }
        WindowsDeleteString(string);
        string = 0;
        v18 = SystemSettings::DataModel::GetResourceStringById((SystemSettings::DataModel *)v16, &string, v17);
        v19 = v18;
        if ( v18 >= 0 )
        {
          v20 = WindowsGetStringRawBuffer(string, 0);
          std::wstring::append(a2, v20);
          WindowsDeleteString(string);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x56,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollercustomap"
                          "ptoolcollectionentry.cpp",
            (const char *)(unsigned int)v18,
            v21[0]);
          WindowsDeleteString(string);
          result = v19;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollercustomappt"
                        "oolcollectionentry.cpp",
          (const char *)(unsigned int)v12,
          v21[0]);
        WindowsDeleteString(string);
        result = v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontrollercustomapptoo"
                      "lcollectionentry.cpp",
        (const char *)(unsigned int)ResourceStringById,
        v21[0]);
      WindowsDeleteString(string);
      result = v7;
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x5B,
                        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\radialcontroller\\radialcontro"
                                      "llercustomapptoolcollectionentry.cpp",
                        v8);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x180213c10  mov     [rsp+arg_0], rbx
0x180213c15  mov     [rsp+arg_8], rsi
0x180213c1a  push    rdi
0x180213c1b  sub     rsp, 40h
0x180213c1f  mov     rsi, rdx
0x180213c22  mov     rdi, rcx
0x180213c25  mov     rdx, rcx
0x180213c28  lea     rcx, [rsp+48h+var_28]
0x180213c2d  call    ?GetCustomActionItem_FromModifierKeyList@CustomActionUtilities@RadialControllerSettings@SystemSettings@@SA?AUCustomAction_ModifierKeyType@23@AEBV?$vector@HV?$allocator@H@std@@@std@@@Z; SystemSettings::RadialControllerSettings::CustomActionUtilities::GetCustomActionItem_FromModifierKeyList(std::vector<int> const &)
0x180213c32  mov     rbx, [rax+10h]
0x180213c36  xor     ecx, ecx; string
0x180213c38  call    cs:__imp_WindowsDeleteString
0x180213c3f  nop     dword ptr [rax+rax+00h]
0x180213c44  mov     [rsp+48h+string], 0
0x180213c4d  lea     rdx, [rsp+48h+string]; HSTRING *
0x180213c52  mov     rcx, rbx; this
0x180213c55  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180213c5a  mov     ebx, eax
0x180213c5c  test    eax, eax
0x180213c5e  jns     short loc_180213C92
0x180213c60  mov     rcx, [rsp+48h]; this
0x180213c65  mov     r9d, eax; char *
0x180213c68  lea     r8, aShellSystemset_44; "shell\\systemsettingsthreshold\\handler"...
0x180213c6f  mov     edx, 4Bh ; 'K'; void *
0x180213c74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180213c79  nop
0x180213c7a  mov     rcx, [rsp+48h+string]; string
0x180213c7f  call    cs:__imp_WindowsDeleteString
0x180213c86  nop     dword ptr [rax+rax+00h]
0x180213c8b  mov     eax, ebx
0x180213c8d  jmp     loc_180213DF5
0x180213c92  xor     edx, edx; length
0x180213c94  mov     rcx, [rsp+48h+string]; string
0x180213c99  call    cs:__imp_WindowsGetStringRawBuffer
0x180213ca0  nop     dword ptr [rax+rax+00h]
0x180213ca5  mov     rdx, rax
0x180213ca8  mov     rcx, rsi
0x180213cab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180213cb0  mov     rcx, [rsp+48h+string]; string
0x180213cb5  call    cs:__imp_WindowsDeleteString
0x180213cbc  nop     dword ptr [rax+rax+00h]
0x180213cc1  mov     [rsp+48h+string], 0
0x180213cca  lea     rdx, [rsp+48h+string]; HSTRING *
0x180213ccf  lea     rcx, aSystemsettings_753; "SystemSettings_Devices_RadialController"...
0x180213cd6  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180213cdb  mov     ebx, eax
0x180213cdd  test    eax, eax
0x180213cdf  jns     short loc_180213D13
0x180213ce1  mov     rcx, [rsp+48h]; this
0x180213ce6  mov     r9d, eax; char *
0x180213ce9  lea     r8, aShellSystemset_44; "shell\\systemsettingsthreshold\\handler"...
0x180213cf0  mov     edx, 50h ; 'P'; void *
0x180213cf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180213cfa  nop
0x180213cfb  mov     rcx, [rsp+48h+string]; string
0x180213d00  call    cs:__imp_WindowsDeleteString
0x180213d07  nop     dword ptr [rax+rax+00h]
0x180213d0c  mov     eax, ebx
0x180213d0e  jmp     loc_180213DF5
0x180213d13  xor     edx, edx; length
0x180213d15  mov     rcx, [rsp+48h+string]; string
0x180213d1a  call    cs:__imp_WindowsGetStringRawBuffer
0x180213d21  nop     dword ptr [rax+rax+00h]
0x180213d26  mov     rdx, rax
0x180213d29  mov     rcx, rsi
0x180213d2c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180213d31  mov     rdx, rdi
0x180213d34  lea     rcx, [rsp+48h+var_28]
0x180213d39  call    ?GetCustomActionItem_FromBaseKeyList@CustomActionUtilities@RadialControllerSettings@SystemSettings@@SA?AUCustomAction_BaseKeyType@23@AEBV?$vector@HV?$allocator@H@std@@@std@@@Z; SystemSettings::RadialControllerSettings::CustomActionUtilities::GetCustomActionItem_FromBaseKeyList(std::vector<int> const &)
0x180213d3e  mov     edx, [rax+4]
0x180213d41  sub     edx, 1Eh
0x180213d44  jz      short loc_180213D5A
0x180213d46  cmp     edx, 1
0x180213d49  jz      short loc_180213D51
0x180213d4b  mov     rbx, [rax+8]
0x180213d4f  jmp     short loc_180213D61
0x180213d51  lea     rbx, aSystemsettings_869; "SystemSettings_Devices_RadialController"...
0x180213d58  jmp     short loc_180213D61
0x180213d5a  lea     rbx, aSystemsettings_21; "SystemSettings_Devices_RadialController"...
0x180213d61  mov     rcx, [rsp+48h+string]; string
0x180213d66  call    cs:__imp_WindowsDeleteString
0x180213d6d  nop     dword ptr [rax+rax+00h]
0x180213d72  mov     [rsp+48h+string], 0
0x180213d7b  lea     rdx, [rsp+48h+string]; HSTRING *
0x180213d80  mov     rcx, rbx; this
0x180213d83  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180213d88  mov     ebx, eax
0x180213d8a  test    eax, eax
0x180213d8c  jns     short loc_180213DBD
0x180213d8e  mov     rcx, [rsp+48h]; this
0x180213d93  mov     r9d, eax; char *
0x180213d96  lea     r8, aShellSystemset_44; "shell\\systemsettingsthreshold\\handler"...
0x180213d9d  mov     edx, 56h ; 'V'; void *
0x180213da2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180213da7  nop
0x180213da8  mov     rcx, [rsp+48h+string]; string
0x180213dad  call    cs:__imp_WindowsDeleteString
0x180213db4  nop     dword ptr [rax+rax+00h]
0x180213db9  mov     eax, ebx
0x180213dbb  jmp     short loc_180213DF5
0x180213dbd  xor     edx, edx; length
0x180213dbf  mov     rcx, [rsp+48h+string]; string
0x180213dc4  call    cs:__imp_WindowsGetStringRawBuffer
0x180213dcb  nop     dword ptr [rax+rax+00h]
0x180213dd0  mov     rdx, rax
0x180213dd3  mov     rcx, rsi
0x180213dd6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180213ddb  nop
0x180213ddc  mov     rcx, [rsp+48h+string]; string
0x180213de1  call    cs:__imp_WindowsDeleteString
0x180213de8  nop     dword ptr [rax+rax+00h]
0x180213ded  xor     eax, eax
0x180213def  jmp     short loc_180213DF5
0x180213df1  mov     eax, dword ptr [rsp+48h+string]
0x180213df5  mov     rbx, [rsp+48h+arg_0]
0x180213dfa  mov     rsi, [rsp+48h+arg_8]
0x180213dff  add     rsp, 40h
0x180213e03  pop     rdi
0x180213e04  retn
```
