# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x180033390`
- end: `0x18003351b`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x18001a64c`
- `0x180033390`
- `0x18004d218`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800333d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800334cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800334e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800333d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800334cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800334e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003343a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003343a`

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
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
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
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
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
                           (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180033390  mov     [rsp+arg_10], rbx
0x180033395  mov     [rsp+arg_18], rsi
0x18003339a  push    rdi
0x18003339b  sub     rsp, 250h
0x1800333a2  mov     rax, cs:__security_cookie
0x1800333a9  xor     rax, rsp
0x1800333ac  mov     [rsp+258h+var_18], rax
0x1800333b4  mov     rdi, rdx
0x1800333b7  mov     rsi, rcx
0x1800333ba  mov     qword ptr [rdx], 0
0x1800333c1  mov     [rsp+258h+string], 0
0x1800333ca  mov     rax, [rcx]
0x1800333cd  mov     rbx, [rax+30h]
0x1800333d1  xor     ecx, ecx; string
0x1800333d3  call    cs:__imp_WindowsDeleteString
0x1800333da  nop     dword ptr [rax+rax+00h]
0x1800333df  mov     [rsp+258h+string], 0; int
0x1800333e8  lea     rdx, [rsp+258h+string]
0x1800333ed  mov     rcx, rsi
0x1800333f0  mov     rax, rbx
0x1800333f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333f8  mov     ebx, eax
0x1800333fa  test    eax, eax
0x1800333fc  jns     short loc_180033433
0x1800333fe  mov     rcx, [rsp+258h]; this
0x180033406  mov     r9d, eax; char *
0x180033409  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180033410  mov     edx, 821h; void *
0x180033415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003341a  nop
0x18003341b  mov     rcx, [rsp+258h+string]; string
0x180033420  call    cs:__imp_WindowsDeleteString
0x180033427  nop     dword ptr [rax+rax+00h]
0x18003342c  mov     eax, ebx
0x18003342e  jmp     loc_1800334F5
0x180033433  xor     edx, edx; length
0x180033435  mov     rcx, [rsp+258h+string]; string
0x18003343a  call    cs:__imp_WindowsGetStringRawBuffer
0x180033441  nop     dword ptr [rax+rax+00h]
0x180033446  mov     r9, rax
0x180033449  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x180033450  mov     edx, 104h; unsigned __int64
0x180033455  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18003345a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003345f  mov     ebx, eax
0x180033461  test    eax, eax
0x180033463  jns     short loc_180033497
0x180033465  mov     rcx, [rsp+258h]; this
0x18003346d  mov     r9d, eax; char *
0x180033470  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180033477  mov     edx, 827h; void *
0x18003347c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033481  nop
0x180033482  mov     rcx, [rsp+258h+string]; string
0x180033487  call    cs:__imp_WindowsDeleteString
0x18003348e  nop     dword ptr [rax+rax+00h]
0x180033493  mov     eax, ebx
0x180033495  jmp     short loc_1800334F5
0x180033497  mov     rdx, rdi; struct IInspectable **
0x18003349a  lea     rcx, [rsp+258h+var_228]; this
0x18003349f  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x1800334a4  mov     ebx, eax
0x1800334a6  test    eax, eax
0x1800334a8  jns     short loc_1800334DC
0x1800334aa  mov     rcx, [rsp+258h]; this
0x1800334b2  mov     r9d, eax; char *
0x1800334b5  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800334bc  mov     edx, 828h; void *
0x1800334c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800334c6  nop
0x1800334c7  mov     rcx, [rsp+258h+string]; string
0x1800334cc  call    cs:__imp_WindowsDeleteString
0x1800334d3  nop     dword ptr [rax+rax+00h]
0x1800334d8  mov     eax, ebx
0x1800334da  jmp     short loc_1800334F5
0x1800334dc  mov     rcx, [rsp+258h+string]; string
0x1800334e1  call    cs:__imp_WindowsDeleteString
0x1800334e8  nop     dword ptr [rax+rax+00h]
0x1800334ed  xor     eax, eax
0x1800334ef  jmp     short loc_1800334F5
0x1800334f1  mov     eax, dword ptr [rsp+258h+string]
0x1800334f5  mov     rcx, [rsp+258h+var_18]
0x1800334fd  xor     rcx, rsp; StackCookie
0x180033500  call    __security_check_cookie
0x180033505  lea     r11, [rsp+258h+var_8]
0x18003350d  mov     rbx, [r11+20h]
0x180033511  mov     rsi, [r11+28h]
0x180033515  mov     rsp, r11
0x180033518  pop     rdi
0x180033519  retn
```
