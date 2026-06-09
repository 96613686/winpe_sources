# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x180013100`
- end: `0x180013267`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x1800030e0`
- `0x18000a2bc`
- `0x18000ac78`
- `0x180013100`
- `0x180014710`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001319e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001319e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001318a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800131e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001318a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800131e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013233`

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
0x180013100  mov     [rsp+arg_10], rbx
0x180013105  mov     [rsp+arg_18], rsi
0x18001310a  push    rdi
0x18001310b  sub     rsp, 250h
0x180013112  mov     rax, cs:__security_cookie
0x180013119  xor     rax, rsp
0x18001311c  mov     [rsp+258h+var_18], rax
0x180013124  mov     rdi, rdx
0x180013127  mov     rsi, rcx
0x18001312a  mov     qword ptr [rdx], 0
0x180013131  mov     [rsp+258h+string], 0
0x18001313a  mov     rax, [rcx]
0x18001313d  mov     rbx, [rax+30h]
0x180013141  xor     ecx, ecx; string
0x180013143  call    cs:__imp_WindowsDeleteString
0x180013149  mov     [rsp+258h+string], 0; int
0x180013152  lea     rdx, [rsp+258h+string]
0x180013157  mov     rcx, rsi
0x18001315a  mov     rax, rbx
0x18001315d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013162  mov     ebx, eax
0x180013164  test    eax, eax
0x180013166  jns     short loc_180013197
0x180013168  mov     rcx, [rsp+258h]; this
0x180013170  mov     r9d, eax; char *
0x180013173  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001317a  mov     edx, 821h; void *
0x18001317f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013184  nop
0x180013185  mov     rcx, [rsp+258h+string]; string
0x18001318a  call    cs:__imp_WindowsDeleteString
0x180013190  mov     eax, ebx
0x180013192  jmp     loc_180013241
0x180013197  xor     edx, edx; length
0x180013199  mov     rcx, [rsp+258h+string]; string
0x18001319e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800131a4  mov     r9, rax
0x1800131a7  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x1800131ae  mov     edx, 104h; unsigned __int64
0x1800131b3  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800131b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800131bd  mov     ebx, eax
0x1800131bf  test    eax, eax
0x1800131c1  jns     short loc_1800131EF
0x1800131c3  mov     rcx, [rsp+258h]; this
0x1800131cb  mov     r9d, eax; char *
0x1800131ce  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800131d5  mov     edx, 827h; void *
0x1800131da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131df  nop
0x1800131e0  mov     rcx, [rsp+258h+string]; string
0x1800131e5  call    cs:__imp_WindowsDeleteString
0x1800131eb  mov     eax, ebx
0x1800131ed  jmp     short loc_180013241
0x1800131ef  mov     rdx, rdi; struct IInspectable **
0x1800131f2  lea     rcx, [rsp+258h+var_228]; this
0x1800131f7  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x1800131fc  mov     ebx, eax
0x1800131fe  test    eax, eax
0x180013200  jns     short loc_18001322E
0x180013202  mov     rcx, [rsp+258h]; this
0x18001320a  mov     r9d, eax; char *
0x18001320d  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180013214  mov     edx, 828h; void *
0x180013219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001321e  nop
0x18001321f  mov     rcx, [rsp+258h+string]; string
0x180013224  call    cs:__imp_WindowsDeleteString
0x18001322a  mov     eax, ebx
0x18001322c  jmp     short loc_180013241
0x18001322e  mov     rcx, [rsp+258h+string]; string
0x180013233  call    cs:__imp_WindowsDeleteString
0x180013239  xor     eax, eax
0x18001323b  jmp     short loc_180013241
0x18001323d  mov     eax, dword ptr [rsp+258h+string]
0x180013241  mov     rcx, [rsp+258h+var_18]
0x180013249  xor     rcx, rsp; StackCookie
0x18001324c  call    __security_check_cookie
0x180013251  lea     r11, [rsp+258h+var_8]
0x180013259  mov     rbx, [r11+20h]
0x18001325d  mov     rsi, [r11+28h]
0x180013261  mov     rsp, r11
0x180013264  pop     rdi
0x180013265  retn
```
