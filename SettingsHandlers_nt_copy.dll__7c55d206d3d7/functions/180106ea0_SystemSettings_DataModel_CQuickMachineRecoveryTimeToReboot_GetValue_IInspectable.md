# SystemSettings::DataModel::CQuickMachineRecoveryTimeToReboot::GetValue(IInspectable * *)

- ea: `0x180106ea0`
- end: `0x1801070b6`
- name: `?GetValue@CQuickMachineRecoveryTimeToReboot@DataModel@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `534`
- prototype: `int(SystemSettings::DataModel::CQuickMachineRecoveryTimeToReboot *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18001a64c`
- `0x1800201c4`
- `0x18004d1ac`
- `0x18004d218`
- `0x180106ea0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106fb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180107062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106f06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106fb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180107062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180106f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180107025`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180106f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180107025`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CQuickMachineRecoveryTimeToReboot::GetValue(
        SystemSettings::DataModel::CQuickMachineRecoveryTimeToReboot *this,
        struct IInspectable **a2,
        struct IInspectable **a3)
{
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rbx
  HSTRING *v8; // r8
  int ResourceStringById; // eax
  unsigned int v10; // edi
  HSTRING v11; // rbx
  __int64 v12; // rdx
  unsigned int v13; // edi
  const unsigned __int16 *StringRawBuffer; // rax
  HSTRING *v16; // r8
  const unsigned __int16 *v17; // rax
  int ResourceStringValue; // eax
  unsigned int v19; // ebx
  HSTRING string[2]; // [rsp+20h] [rbp-248h] BYREF
  unsigned __int16 v21[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v5 = *(_QWORD *)(*((_QWORD *)this + 11) + 24LL);
  if ( *(_BYTE *)(v5 + 235) )
  {
    v6 = 0;
    while ( 1 )
    {
      v7 = 2LL * v6;
      if ( *(_DWORD *)(v5 + 244) == *((_DWORD *)&off_1802BFDB0 + 4 * v6 + 2) )
        break;
      if ( (unsigned int)++v6 >= 6 )
      {
        WindowsDeleteString(0);
        string[0] = 0;
        ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                               (SystemSettings::DataModel *)L"SystemSettings_Misc_QuickMachineRecovery_TimeToReboot_CustomValue",
                               string,
                               v8);
        v10 = ResourceStringById;
        v11 = string[0];
        if ( ResourceStringById < 0 )
        {
          v12 = 1105;
          goto LABEL_17;
        }
        v13 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 244LL);
        StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
        ResourceStringById = StringCchPrintfW(v21, 0x104u, StringRawBuffer, v13);
        v10 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v12 = 1108;
          goto LABEL_17;
        }
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v21, a2);
        v10 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v12 = 1110;
          goto LABEL_17;
        }
LABEL_11:
        WindowsDeleteString(v11);
        return 0;
      }
    }
    WindowsDeleteString(0);
    string[0] = 0;
    ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                           (SystemSettings::DataModel *)(&off_1802BFDB0)[v7],
                           string,
                           v16);
    v10 = ResourceStringById;
    v11 = string[0];
    if ( ResourceStringById >= 0 )
    {
      v17 = WindowsGetStringRawBuffer(string[0], 0);
      ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v17, a2);
      v10 = ResourceStringById;
      if ( ResourceStringById >= 0 )
        goto LABEL_11;
      v12 = 1094;
    }
    else
    {
      v12 = 1093;
    }
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
      (const char *)(unsigned int)ResourceStringById,
      (int)string[0]);
    WindowsDeleteString(v11);
    return v10;
  }
  else
  {
    ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue(
                            (SystemSettings::DataModel *)L"SystemSettings_Misc_QuickMachineRecovery_TimeToReboot_0",
                            a2,
                            a3);
    v19 = ResourceStringValue;
    if ( ResourceStringValue >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45C,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\quickmachinerecovery.cpp",
        (const char *)(unsigned int)ResourceStringValue,
        (int)string[0]);
      return v19;
    }
  }
}

```

## disassembly

```asm
0x180106ea0  mov     [rsp+arg_10], rbx
0x180106ea5  push    rbp
0x180106ea6  push    rsi
0x180106ea7  push    rdi
0x180106ea8  sub     rsp, 250h
0x180106eaf  mov     rax, cs:__security_cookie
0x180106eb6  xor     rax, rsp
0x180106eb9  mov     [rsp+268h+var_28], rax
0x180106ec1  mov     rsi, rdx
0x180106ec4  mov     rbp, rcx
0x180106ec7  mov     rax, [rcx+58h]
0x180106ecb  mov     rdx, [rax+18h]
0x180106ecf  cmp     byte ptr [rdx+0EBh], 0
0x180106ed6  jz      loc_18010707A
0x180106edc  xor     eax, eax
0x180106ede  mov     r8d, [rdx+0F4h]
0x180106ee5  lea     rdi, off_1802BFDB0; "SystemSettings_Misc_QuickMachineRecover"...
0x180106eec  movsxd  rbx, eax
0x180106eef  add     rbx, rbx
0x180106ef2  cmp     r8d, [rdi+rbx*8+8]
0x180106ef7  jz      loc_180106FE9
0x180106efd  inc     eax
0x180106eff  cmp     eax, 6
0x180106f02  jb      short loc_180106EEC
0x180106f04  xor     ecx, ecx; string
0x180106f06  call    cs:__imp_WindowsDeleteString
0x180106f0d  nop     dword ptr [rax+rax+00h]
0x180106f12  mov     [rsp+268h+string], 0; int
0x180106f1b  lea     rdx, [rsp+268h+string]; HSTRING *
0x180106f20  lea     rcx, aSystemsettings_1426; "SystemSettings_Misc_QuickMachineRecover"...
0x180106f27  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180106f2c  mov     edi, eax
0x180106f2e  mov     rbx, [rsp+268h+string]
0x180106f33  test    eax, eax
0x180106f35  jns     short loc_180106F3E
0x180106f37  mov     edx, 451h
0x180106f3c  jmp     short loc_180106F97
0x180106f3e  mov     rax, [rbp+58h]
0x180106f42  mov     rcx, [rax+18h]
0x180106f46  mov     edi, [rcx+0F4h]
0x180106f4c  xor     edx, edx; length
0x180106f4e  mov     rcx, rbx; string
0x180106f51  call    cs:__imp_WindowsGetStringRawBuffer
0x180106f58  nop     dword ptr [rax+rax+00h]
0x180106f5d  mov     r9d, edi
0x180106f60  mov     r8, rax; unsigned __int16 *
0x180106f63  mov     edx, 104h; unsigned __int64
0x180106f68  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180106f6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180106f72  mov     edi, eax
0x180106f74  test    eax, eax
0x180106f76  jns     short loc_180106F7F
0x180106f78  mov     edx, 454h
0x180106f7d  jmp     short loc_180106F97
0x180106f7f  mov     rdx, rsi; struct IInspectable **
0x180106f82  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180106f87  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180106f8c  mov     edi, eax
0x180106f8e  test    eax, eax
0x180106f90  jns     short loc_180106FB4
0x180106f92  mov     edx, 456h; void *
0x180106f97  mov     r9d, eax; char *
0x180106f9a  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180106fa1  mov     rcx, [rsp+268h]; this
0x180106fa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106fae  nop
0x180106faf  jmp     loc_18010705F
0x180106fb4  mov     rcx, rbx; string
0x180106fb7  call    cs:__imp_WindowsDeleteString
0x180106fbe  nop     dword ptr [rax+rax+00h]
0x180106fc3  xor     eax, eax
0x180106fc5  mov     rcx, [rsp+268h+var_28]
0x180106fcd  xor     rcx, rsp; StackCookie
0x180106fd0  call    __security_check_cookie
0x180106fd5  mov     rbx, [rsp+268h+arg_10]
0x180106fdd  add     rsp, 250h
0x180106fe4  pop     rdi
0x180106fe5  pop     rsi
0x180106fe6  pop     rbp
0x180106fe7  retn
0x180106fe9  xor     ecx, ecx; string
0x180106feb  call    cs:__imp_WindowsDeleteString
0x180106ff2  nop     dword ptr [rax+rax+00h]
0x180106ff7  mov     [rsp+268h+string], 0; int
0x180107000  lea     rdx, [rsp+268h+string]; HSTRING *
0x180107005  mov     rcx, [rdi+rbx*8]; this
0x180107009  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18010700e  mov     edi, eax
0x180107010  mov     rbx, [rsp+268h+string]
0x180107015  test    eax, eax
0x180107017  jns     short loc_180107020
0x180107019  mov     edx, 445h
0x18010701e  jmp     short loc_180107047
0x180107020  xor     edx, edx; length
0x180107022  mov     rcx, rbx; string
0x180107025  call    cs:__imp_WindowsGetStringRawBuffer
0x18010702c  nop     dword ptr [rax+rax+00h]
0x180107031  mov     rdx, rsi; struct IInspectable **
0x180107034  mov     rcx, rax; unsigned __int16 *
0x180107037  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18010703c  mov     edi, eax
0x18010703e  test    eax, eax
0x180107040  jns     short loc_180107075
0x180107042  mov     edx, 446h; void *
0x180107047  mov     r9d, eax; char *
0x18010704a  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180107051  mov     rcx, [rsp+268h]; this
0x180107059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010705e  nop
0x18010705f  mov     rcx, rbx; string
0x180107062  call    cs:__imp_WindowsDeleteString
0x180107069  nop     dword ptr [rax+rax+00h]
0x18010706e  mov     eax, edi
0x180107070  jmp     loc_180106FC5
0x180107075  jmp     loc_180106FB4
0x18010707a  mov     rdx, rsi; struct IInspectable **
0x18010707d  lea     rcx, aSystemsettings_1247; "SystemSettings_Misc_QuickMachineRecover"...
0x180107084  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x180107089  mov     ebx, eax
0x18010708b  test    eax, eax
0x18010708d  jns     loc_180106FC3
0x180107093  mov     rcx, [rsp+268h]; this
0x18010709b  mov     r9d, eax; char *
0x18010709e  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x1801070a5  mov     edx, 45Ch; void *
0x1801070aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801070af  mov     eax, ebx
0x1801070b1  jmp     loc_180106FC5
```
