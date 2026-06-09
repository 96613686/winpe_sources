# SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval::GetValue(IInspectable * *)

- ea: `0x180106c80`
- end: `0x180106e96`
- name: `?GetValue@CQuickMachineRecoveryRetryInterval@DataModel@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `534`
- prototype: `int(SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval *__hidden this, struct IInspectable **)`
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
- `0x180106c80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106ce6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106dcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106ce6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106dcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180106e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180106d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180106e05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180106d31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180106e05`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval::GetValue(
        SystemSettings::DataModel::CQuickMachineRecoveryRetryInterval *this,
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
      if ( *(_DWORD *)(v5 + 240) == *((_DWORD *)&off_1802BFE10 + 4 * v6 + 2) )
        break;
      if ( (unsigned int)++v6 >= 7 )
      {
        WindowsDeleteString(0);
        string[0] = 0;
        ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                               (SystemSettings::DataModel *)L"SystemSettings_Misc_QuickMachineRecovery_RetryInterval_CustomValue",
                               string,
                               v8);
        v10 = ResourceStringById;
        v11 = string[0];
        if ( ResourceStringById < 0 )
        {
          v12 = 496;
          goto LABEL_17;
        }
        v13 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 240LL);
        StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
        ResourceStringById = StringCchPrintfW(v21, 0x104u, StringRawBuffer, v13);
        v10 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v12 = 499;
          goto LABEL_17;
        }
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v21, a2);
        v10 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v12 = 501;
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
                           (SystemSettings::DataModel *)(&off_1802BFE10)[v7],
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
      v12 = 487;
    }
    else
    {
      v12 = 486;
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
                            (SystemSettings::DataModel *)L"SystemSettings_Misc_QuickMachineRecovery_RetryInterval_0",
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
        (void *)0x1FB,
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
0x180106c80  mov     [rsp+arg_10], rbx
0x180106c85  push    rbp
0x180106c86  push    rsi
0x180106c87  push    rdi
0x180106c88  sub     rsp, 250h
0x180106c8f  mov     rax, cs:__security_cookie
0x180106c96  xor     rax, rsp
0x180106c99  mov     [rsp+268h+var_28], rax
0x180106ca1  mov     rsi, rdx
0x180106ca4  mov     rbp, rcx
0x180106ca7  mov     rax, [rcx+58h]
0x180106cab  mov     rdx, [rax+18h]
0x180106caf  cmp     byte ptr [rdx+0EBh], 0
0x180106cb6  jz      loc_180106E5A
0x180106cbc  xor     eax, eax
0x180106cbe  mov     r8d, [rdx+0F0h]
0x180106cc5  lea     rdi, off_1802BFE10; "SystemSettings_Misc_QuickMachineRecover"...
0x180106ccc  movsxd  rbx, eax
0x180106ccf  add     rbx, rbx
0x180106cd2  cmp     r8d, [rdi+rbx*8+8]
0x180106cd7  jz      loc_180106DC9
0x180106cdd  inc     eax
0x180106cdf  cmp     eax, 7
0x180106ce2  jb      short loc_180106CCC
0x180106ce4  xor     ecx, ecx; string
0x180106ce6  call    cs:__imp_WindowsDeleteString
0x180106ced  nop     dword ptr [rax+rax+00h]
0x180106cf2  mov     [rsp+268h+string], 0; int
0x180106cfb  lea     rdx, [rsp+268h+string]; HSTRING *
0x180106d00  lea     rcx, aSystemsettings_1414; "SystemSettings_Misc_QuickMachineRecover"...
0x180106d07  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180106d0c  mov     edi, eax
0x180106d0e  mov     rbx, [rsp+268h+string]
0x180106d13  test    eax, eax
0x180106d15  jns     short loc_180106D1E
0x180106d17  mov     edx, 1F0h
0x180106d1c  jmp     short loc_180106D77
0x180106d1e  mov     rax, [rbp+58h]
0x180106d22  mov     rcx, [rax+18h]
0x180106d26  mov     edi, [rcx+0F0h]
0x180106d2c  xor     edx, edx; length
0x180106d2e  mov     rcx, rbx; string
0x180106d31  call    cs:__imp_WindowsGetStringRawBuffer
0x180106d38  nop     dword ptr [rax+rax+00h]
0x180106d3d  mov     r9d, edi
0x180106d40  mov     r8, rax; unsigned __int16 *
0x180106d43  mov     edx, 104h; unsigned __int64
0x180106d48  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180106d4d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180106d52  mov     edi, eax
0x180106d54  test    eax, eax
0x180106d56  jns     short loc_180106D5F
0x180106d58  mov     edx, 1F3h
0x180106d5d  jmp     short loc_180106D77
0x180106d5f  mov     rdx, rsi; struct IInspectable **
0x180106d62  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180106d67  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180106d6c  mov     edi, eax
0x180106d6e  test    eax, eax
0x180106d70  jns     short loc_180106D94
0x180106d72  mov     edx, 1F5h; void *
0x180106d77  mov     r9d, eax; char *
0x180106d7a  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180106d81  mov     rcx, [rsp+268h]; this
0x180106d89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106d8e  nop
0x180106d8f  jmp     loc_180106E3F
0x180106d94  mov     rcx, rbx; string
0x180106d97  call    cs:__imp_WindowsDeleteString
0x180106d9e  nop     dword ptr [rax+rax+00h]
0x180106da3  xor     eax, eax
0x180106da5  mov     rcx, [rsp+268h+var_28]
0x180106dad  xor     rcx, rsp; StackCookie
0x180106db0  call    __security_check_cookie
0x180106db5  mov     rbx, [rsp+268h+arg_10]
0x180106dbd  add     rsp, 250h
0x180106dc4  pop     rdi
0x180106dc5  pop     rsi
0x180106dc6  pop     rbp
0x180106dc7  retn
0x180106dc9  xor     ecx, ecx; string
0x180106dcb  call    cs:__imp_WindowsDeleteString
0x180106dd2  nop     dword ptr [rax+rax+00h]
0x180106dd7  mov     [rsp+268h+string], 0; int
0x180106de0  lea     rdx, [rsp+268h+string]; HSTRING *
0x180106de5  mov     rcx, [rdi+rbx*8]; this
0x180106de9  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180106dee  mov     edi, eax
0x180106df0  mov     rbx, [rsp+268h+string]
0x180106df5  test    eax, eax
0x180106df7  jns     short loc_180106E00
0x180106df9  mov     edx, 1E6h
0x180106dfe  jmp     short loc_180106E27
0x180106e00  xor     edx, edx; length
0x180106e02  mov     rcx, rbx; string
0x180106e05  call    cs:__imp_WindowsGetStringRawBuffer
0x180106e0c  nop     dword ptr [rax+rax+00h]
0x180106e11  mov     rdx, rsi; struct IInspectable **
0x180106e14  mov     rcx, rax; unsigned __int16 *
0x180106e17  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180106e1c  mov     edi, eax
0x180106e1e  test    eax, eax
0x180106e20  jns     short loc_180106E55
0x180106e22  mov     edx, 1E7h; void *
0x180106e27  mov     r9d, eax; char *
0x180106e2a  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180106e31  mov     rcx, [rsp+268h]; this
0x180106e39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106e3e  nop
0x180106e3f  mov     rcx, rbx; string
0x180106e42  call    cs:__imp_WindowsDeleteString
0x180106e49  nop     dword ptr [rax+rax+00h]
0x180106e4e  mov     eax, edi
0x180106e50  jmp     loc_180106DA5
0x180106e55  jmp     loc_180106D94
0x180106e5a  mov     rdx, rsi; struct IInspectable **
0x180106e5d  lea     rcx, aSystemsettings_908; "SystemSettings_Misc_QuickMachineRecover"...
0x180106e64  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x180106e69  mov     ebx, eax
0x180106e6b  test    eax, eax
0x180106e6d  jns     loc_180106DA3
0x180106e73  mov     rcx, [rsp+268h]; this
0x180106e7b  mov     r9d, eax; char *
0x180106e7e  lea     r8, aShellSystemset_65; "shell\\systemsettingsthreshold\\handler"...
0x180106e85  mov     edx, 1FBh; void *
0x180106e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180106e8f  mov     eax, ebx
0x180106e91  jmp     loc_180106DA5
```
