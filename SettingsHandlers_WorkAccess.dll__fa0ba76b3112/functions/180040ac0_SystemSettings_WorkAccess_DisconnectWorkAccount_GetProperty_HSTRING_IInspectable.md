# SystemSettings::WorkAccess::DisconnectWorkAccount::GetProperty(HSTRING__ *,IInspectable * *)

- ea: `0x180040ac0`
- end: `0x180040bfb`
- name: `?GetProperty@DisconnectWorkAccount@WorkAccess@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `315`
- prototype: `int(SystemSettings::WorkAccess::DisconnectWorkAccount *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x1800119c0`
- `0x180015000`
- `0x180016e84`
- `0x180040ac0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040bbf`

## string_xrefs

- `0x180040af9`: `SystemSettings_WorkAccess_DisconnectConfirmation`
- `0x180040b7f`: `SystemSettings_WorkAccess_DisconnectButton`
- `0x180040b38`: `shellcommon\shell\settingshandlers\workaccess\lib\disconnectworkaccount.cpp`
- `0x180040bd4`: `shellcommon\shell\settingshandlers\workaccess\lib\disconnectworkaccount.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::DisconnectWorkAccount::GetProperty(
        SystemSettings::WorkAccess::DisconnectWorkAccount *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v5; // r8
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005E188, (const unsigned __int16 *)a3) )
  {
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18005E148, v5) )
    {
      v7 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\disconnectworkaccount.cpp",
        (const char *)0x80070057LL,
        v10);
      return v7;
    }
    string = 0;
    v6 = Microsoft::WRL::Wrappers::HString::Set(
           (Microsoft::WRL::Wrappers::HString *)&string,
           L"SystemSettings_WorkAccess_DisconnectButton",
           0x2Au);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 109;
      goto LABEL_6;
    }
    v6 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 110;
      goto LABEL_6;
    }
    goto LABEL_12;
  }
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HString::Set(
         (Microsoft::WRL::Wrappers::HString *)&string,
         L"SystemSettings_WorkAccess_DisconnectConfirmation",
         0x30u);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 104;
      goto LABEL_6;
    }
LABEL_12:
    WindowsDeleteString(string);
    return 0;
  }
  v8 = 103;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\disconnectworkaccount.cpp",
    (const char *)(unsigned int)v6,
    v10);
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x180040ac0  mov     [rsp+arg_0], rbx
0x180040ac5  push    rdi; int
0x180040ac6  sub     rsp, 20h
0x180040aca  mov     rbx, rdx
0x180040acd  mov     qword ptr [r8], 0
0x180040ad4  mov     rcx, rbx; this
0x180040ad7  lea     rdx, stru_18005E188; HSTRING
0x180040ade  mov     rdi, r8
0x180040ae1  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180040ae6  test    al, al
0x180040ae8  jz      short loc_180040B5D
0x180040aea  mov     r8d, 30h ; '0'; unsigned int
0x180040af0  mov     [rsp+28h+string], 0
0x180040af9  lea     rdx, aSystemsettings_7; "SystemSettings_WorkAccess_DisconnectCon"...
0x180040b00  lea     rcx, [rsp+28h+string]; this
0x180040b05  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180040b0a  mov     ebx, eax
0x180040b0c  test    eax, eax
0x180040b0e  jns     short loc_180040B17
0x180040b10  mov     edx, 67h ; 'g'
0x180040b15  jmp     short loc_180040B33
0x180040b17  mov     rcx, [rsp+28h+string]; HSTRING
0x180040b1c  mov     rdx, rdi; struct IInspectable **
0x180040b1f  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180040b24  mov     ebx, eax
0x180040b26  test    eax, eax
0x180040b28  jns     loc_180040BBA
0x180040b2e  mov     edx, 68h ; 'h'; void *
0x180040b33  mov     rcx, [rsp+28h]; this
0x180040b38  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\w"...
0x180040b3f  mov     r9d, eax; char *
0x180040b42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040b47  mov     rcx, [rsp+28h+string]; string
0x180040b4c  call    cs:__imp_WindowsDeleteString
0x180040b53  nop     dword ptr [rax+rax+00h]
0x180040b58  jmp     loc_180040BED
0x180040b5d  lea     rdx, stru_18005E148; HSTRING
0x180040b64  mov     rcx, rbx; this
0x180040b67  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180040b6c  test    al, al
0x180040b6e  jz      short loc_180040BCF
0x180040b70  mov     r8d, 2Ah ; '*'; unsigned int
0x180040b76  mov     [rsp+28h+string], 0
0x180040b7f  lea     rdx, aSystemsettings_47; "SystemSettings_WorkAccess_DisconnectBut"...
0x180040b86  lea     rcx, [rsp+28h+string]; this
0x180040b8b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180040b90  mov     ebx, eax
0x180040b92  test    eax, eax
0x180040b94  jns     short loc_180040B9D
0x180040b96  mov     edx, 6Dh ; 'm'
0x180040b9b  jmp     short loc_180040B33
0x180040b9d  mov     rcx, [rsp+28h+string]; HSTRING
0x180040ba2  mov     rdx, rdi; struct IInspectable **
0x180040ba5  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180040baa  mov     ebx, eax
0x180040bac  test    eax, eax
0x180040bae  jns     short loc_180040BBA
0x180040bb0  mov     edx, 6Eh ; 'n'
0x180040bb5  jmp     loc_180040B33
0x180040bba  mov     rcx, [rsp+28h+string]; string
0x180040bbf  call    cs:__imp_WindowsDeleteString
0x180040bc6  nop     dword ptr [rax+rax+00h]
0x180040bcb  xor     eax, eax
0x180040bcd  jmp     short loc_180040BEF
0x180040bcf  mov     rcx, [rsp+28h]; this
0x180040bd4  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\w"...
0x180040bdb  mov     ebx, 80070057h
0x180040be0  mov     edx, 72h ; 'r'; void *
0x180040be5  mov     r9d, ebx; char *
0x180040be8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040bed  mov     eax, ebx
0x180040bef  mov     rbx, [rsp+28h+arg_0]
0x180040bf4  add     rsp, 20h
0x180040bf8  pop     rdi
0x180040bf9  retn
```
