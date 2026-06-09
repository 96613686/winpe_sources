# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x18002bbf0`
- end: `0x18002bd57`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x18000f07c`
- `0x18001e050`
- `0x18002bbf0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bcd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bcd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bc8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bc8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(
        __int64 a1,
        struct IInspectable **a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  PCWSTR StringRawBuffer; // rax
  int v10; // eax
  struct IInspectable **v11; // r8
  unsigned int v12; // ebx
  int ResourceStringValue; // eax
  unsigned int v14; // ebx
  HSTRING string[2]; // [rsp+20h] [rbp-238h] BYREF
  unsigned __int16 v16[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *a2 = 0;
  string[0] = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 48LL);
  WindowsDeleteString(0);
  try
  {
    string[0] = 0;
    v5 = v4(a1, string);
    v6 = v5;
    if ( v5 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      v10 = StringCchPrintfW(v16, 0x104u, L"%ws_ActionDescription", StringRawBuffer);
      v12 = v10;
      if ( v10 >= 0 )
      {
        ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue(
                                (SystemSettings::DataModel *)v16,
                                a2,
                                v11);
        v14 = ResourceStringValue;
        if ( ResourceStringValue >= 0 )
        {
          WindowsDeleteString(string[0]);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x828,
            (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
            (const char *)(unsigned int)ResourceStringValue,
            (int)string[0]);
          WindowsDeleteString(string[0]);
          result = v14;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x827,
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v10,
          (int)string[0]);
        WindowsDeleteString(string[0]);
        result = v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x821,
        (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
        (const char *)(unsigned int)v5,
        (int)string[0]);
      WindowsDeleteString(string[0]);
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x82C,
                           (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18002bbf0  mov     [rsp+arg_10], rbx
0x18002bbf5  mov     [rsp+arg_18], rsi
0x18002bbfa  push    rdi
0x18002bbfb  sub     rsp, 250h
0x18002bc02  mov     rax, cs:__security_cookie
0x18002bc09  xor     rax, rsp
0x18002bc0c  mov     [rsp+258h+var_18], rax
0x18002bc14  mov     rdi, rdx
0x18002bc17  mov     rsi, rcx
0x18002bc1a  mov     qword ptr [rdx], 0
0x18002bc21  mov     [rsp+258h+string], 0
0x18002bc2a  mov     rax, [rcx]
0x18002bc2d  mov     rbx, [rax+30h]
0x18002bc31  xor     ecx, ecx; string
0x18002bc33  call    cs:__imp_WindowsDeleteString
0x18002bc39  mov     [rsp+258h+string], 0; int
0x18002bc42  lea     rdx, [rsp+258h+string]
0x18002bc47  mov     rcx, rsi
0x18002bc4a  mov     rax, rbx
0x18002bc4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc52  mov     ebx, eax
0x18002bc54  test    eax, eax
0x18002bc56  jns     short loc_18002BC87
0x18002bc58  mov     rcx, [rsp+258h]; this
0x18002bc60  mov     r9d, eax; char *
0x18002bc63  lea     r8, aOnecoreuapInte_10; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002bc6a  mov     edx, 821h; void *
0x18002bc6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bc74  nop
0x18002bc75  mov     rcx, [rsp+258h+string]; string
0x18002bc7a  call    cs:__imp_WindowsDeleteString
0x18002bc80  mov     eax, ebx
0x18002bc82  jmp     loc_18002BD31
0x18002bc87  xor     edx, edx; length
0x18002bc89  mov     rcx, [rsp+258h+string]; string
0x18002bc8e  call    cs:__imp_WindowsGetStringRawBuffer
0x18002bc94  mov     r9, rax
0x18002bc97  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x18002bc9e  mov     edx, 104h; unsigned __int64
0x18002bca3  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18002bca8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bcad  mov     ebx, eax
0x18002bcaf  test    eax, eax
0x18002bcb1  jns     short loc_18002BCDF
0x18002bcb3  mov     rcx, [rsp+258h]; this
0x18002bcbb  mov     r9d, eax; char *
0x18002bcbe  lea     r8, aOnecoreuapInte_10; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002bcc5  mov     edx, 827h; void *
0x18002bcca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bccf  nop
0x18002bcd0  mov     rcx, [rsp+258h+string]; string
0x18002bcd5  call    cs:__imp_WindowsDeleteString
0x18002bcdb  mov     eax, ebx
0x18002bcdd  jmp     short loc_18002BD31
0x18002bcdf  mov     rdx, rdi; struct IInspectable **
0x18002bce2  lea     rcx, [rsp+258h+var_228]; this
0x18002bce7  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x18002bcec  mov     ebx, eax
0x18002bcee  test    eax, eax
0x18002bcf0  jns     short loc_18002BD1E
0x18002bcf2  mov     rcx, [rsp+258h]; this
0x18002bcfa  mov     r9d, eax; char *
0x18002bcfd  lea     r8, aOnecoreuapInte_10; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002bd04  mov     edx, 828h; void *
0x18002bd09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd0e  nop
0x18002bd0f  mov     rcx, [rsp+258h+string]; string
0x18002bd14  call    cs:__imp_WindowsDeleteString
0x18002bd1a  mov     eax, ebx
0x18002bd1c  jmp     short loc_18002BD31
0x18002bd1e  mov     rcx, [rsp+258h+string]; string
0x18002bd23  call    cs:__imp_WindowsDeleteString
0x18002bd29  xor     eax, eax
0x18002bd2b  jmp     short loc_18002BD31
0x18002bd2d  mov     eax, dword ptr [rsp+258h+string]
0x18002bd31  mov     rcx, [rsp+258h+var_18]
0x18002bd39  xor     rcx, rsp; StackCookie
0x18002bd3c  call    __security_check_cookie
0x18002bd41  lea     r11, [rsp+258h+var_8]
0x18002bd49  mov     rbx, [r11+20h]
0x18002bd4d  mov     rsi, [r11+28h]
0x18002bd51  mov     rsp, r11
0x18002bd54  pop     rdi
0x18002bd55  retn
```
