# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x180015510`
- end: `0x180015677`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180002350`
- `0x180008c24`
- `0x180009718`
- `0x180015510`
- `0x18001879c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800155ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800155ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001559a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800155f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001559a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800155f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015643`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(
        __int64 a1,
        const unsigned __int16 *a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 result; // rax
  PCWSTR StringRawBuffer; // rax
  int v11; // eax
  struct IInspectable **v12; // r8
  unsigned int v13; // ebx
  int ResourceStringValue; // eax
  unsigned int v15; // ebx
  HSTRING string[2]; // [rsp+20h] [rbp-238h] BYREF
  unsigned __int16 v17[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *(_QWORD *)a2 = 0;
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
      v11 = StringCchPrintfW(v17, 0x104u, L"%ws_ActionDescription", StringRawBuffer);
      v13 = v11;
      if ( v11 >= 0 )
      {
        ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue(
                                (SystemSettings::DataModel *)v17,
                                a2,
                                v12);
        v15 = ResourceStringValue;
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
          result = v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x827,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v11,
          (int)string[0]);
        WindowsDeleteString(string[0]);
        result = v13;
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x82C, v7, v8);
  }
  return result;
}

```

## disassembly

```asm
0x180015510  mov     [rsp+arg_10], rbx
0x180015515  mov     [rsp+arg_18], rsi
0x18001551a  push    rdi
0x18001551b  sub     rsp, 250h
0x180015522  mov     rax, cs:__security_cookie
0x180015529  xor     rax, rsp
0x18001552c  mov     [rsp+258h+var_18], rax
0x180015534  mov     rdi, rdx
0x180015537  mov     rsi, rcx
0x18001553a  mov     qword ptr [rdx], 0
0x180015541  mov     [rsp+258h+string], 0
0x18001554a  mov     rax, [rcx]
0x18001554d  mov     rbx, [rax+30h]
0x180015551  xor     ecx, ecx; string
0x180015553  call    cs:__imp_WindowsDeleteString
0x180015559  mov     [rsp+258h+string], 0; int
0x180015562  lea     rdx, [rsp+258h+string]
0x180015567  mov     rcx, rsi
0x18001556a  mov     rax, rbx
0x18001556d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015572  mov     ebx, eax
0x180015574  test    eax, eax
0x180015576  jns     short loc_1800155A7
0x180015578  mov     rcx, [rsp+258h]; this
0x180015580  mov     r9d, eax; char *
0x180015583  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001558a  mov     edx, 821h; void *
0x18001558f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015594  nop
0x180015595  mov     rcx, [rsp+258h+string]; string
0x18001559a  call    cs:__imp_WindowsDeleteString
0x1800155a0  mov     eax, ebx
0x1800155a2  jmp     loc_180015651
0x1800155a7  xor     edx, edx; length
0x1800155a9  mov     rcx, [rsp+258h+string]; string
0x1800155ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800155b4  mov     r9, rax
0x1800155b7  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x1800155be  mov     edx, 104h; unsigned __int64
0x1800155c3  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x1800155c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800155cd  mov     ebx, eax
0x1800155cf  test    eax, eax
0x1800155d1  jns     short loc_1800155FF
0x1800155d3  mov     rcx, [rsp+258h]; this
0x1800155db  mov     r9d, eax; char *
0x1800155de  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800155e5  mov     edx, 827h; void *
0x1800155ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155ef  nop
0x1800155f0  mov     rcx, [rsp+258h+string]; string
0x1800155f5  call    cs:__imp_WindowsDeleteString
0x1800155fb  mov     eax, ebx
0x1800155fd  jmp     short loc_180015651
0x1800155ff  mov     rdx, rdi; unsigned __int16 *
0x180015602  lea     rcx, [rsp+258h+var_228]; this
0x180015607  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x18001560c  mov     ebx, eax
0x18001560e  test    eax, eax
0x180015610  jns     short loc_18001563E
0x180015612  mov     rcx, [rsp+258h]; this
0x18001561a  mov     r9d, eax; char *
0x18001561d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180015624  mov     edx, 828h; void *
0x180015629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001562e  nop
0x18001562f  mov     rcx, [rsp+258h+string]; string
0x180015634  call    cs:__imp_WindowsDeleteString
0x18001563a  mov     eax, ebx
0x18001563c  jmp     short loc_180015651
0x18001563e  mov     rcx, [rsp+258h+string]; string
0x180015643  call    cs:__imp_WindowsDeleteString
0x180015649  xor     eax, eax
0x18001564b  jmp     short loc_180015651
0x18001564d  mov     eax, dword ptr [rsp+258h+string]
0x180015651  mov     rcx, [rsp+258h+var_18]
0x180015659  xor     rcx, rsp; StackCookie
0x18001565c  call    __security_check_cookie
0x180015661  lea     r11, [rsp+258h+var_8]
0x180015669  mov     rbx, [r11+20h]
0x18001566d  mov     rsi, [r11+28h]
0x180015671  mov     rsp, r11
0x180015674  pop     rdi
0x180015675  retn
```
