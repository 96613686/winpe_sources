# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x180014dd0`
- end: `0x180014fa3`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `467`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x1800087ec`
- `0x180008f60`
- `0x180013710`
- `0x180014dd0`
- `0x180017418`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ec7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014f22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014f54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ec7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014f22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014f54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014e7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014e7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(
        __int64 a1,
        struct IInspectable **a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  PCWSTR StringRawBuffer; // rax
  int v9; // eax
  unsigned int v10; // ebx
  HSTRING *v11; // r8
  int ResourceStringById; // edi
  HSTRING v13; // rbx
  HSTRING string; // [rsp+20h] [rbp-238h] BYREF
  HSTRING v15; // [rsp+28h] [rbp-230h] BYREF
  unsigned __int16 v16[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *a2 = 0;
  string = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a1, &string);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v9 = StringCchPrintfW(v16, 0x104u, L"%ws_ActionDescription", StringRawBuffer);
    v10 = v9;
    if ( v9 >= 0 )
    {
      *a2 = 0;
      WindowsDeleteString(0);
      v15 = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById((SystemSettings::DataModel *)v16, &v15, v11);
      v13 = v15;
      if ( ResourceStringById >= 0 )
        ResourceStringById = SystemSettings::DataModel::PropValueHelper::CreateString(v15, a2);
      WindowsDeleteString(v13);
      if ( ResourceStringById >= 0 )
      {
        WindowsDeleteString(string);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x828,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)ResourceStringById,
          (int)string);
        WindowsDeleteString(string);
        return (unsigned int)ResourceStringById;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x827,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
        (const char *)(unsigned int)v9,
        (int)string);
      WindowsDeleteString(string);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x821,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
      (const char *)(unsigned int)v5,
      (int)string);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x180014dd0  mov     [rsp+arg_10], rbx
0x180014dd5  mov     [rsp+arg_18], rsi
0x180014dda  push    rdi
0x180014ddb  sub     rsp, 250h
0x180014de2  mov     rax, cs:__security_cookie
0x180014de9  xor     rax, rsp
0x180014dec  mov     [rsp+258h+var_18], rax
0x180014df4  mov     rsi, rdx
0x180014df7  mov     rdi, rcx
0x180014dfa  mov     qword ptr [rdx], 0
0x180014e01  mov     [rsp+258h+string], 0
0x180014e0a  mov     rax, [rcx]
0x180014e0d  mov     rbx, [rax+30h]
0x180014e11  xor     ecx, ecx; string
0x180014e13  call    cs:__imp_WindowsDeleteString
0x180014e1a  nop     dword ptr [rax+rax+00h]
0x180014e1f  mov     [rsp+258h+string], 0; int
0x180014e28  lea     rdx, [rsp+258h+string]
0x180014e2d  mov     rcx, rdi
0x180014e30  mov     rax, rbx
0x180014e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e38  mov     ebx, eax
0x180014e3a  test    eax, eax
0x180014e3c  jns     short loc_180014E73
0x180014e3e  mov     rcx, [rsp+258h]; this
0x180014e46  mov     r9d, eax; char *
0x180014e49  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180014e50  mov     edx, 821h; void *
0x180014e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e5a  nop
0x180014e5b  mov     rcx, [rsp+258h+string]; string
0x180014e60  call    cs:__imp_WindowsDeleteString
0x180014e67  nop     dword ptr [rax+rax+00h]
0x180014e6c  mov     eax, ebx
0x180014e6e  jmp     loc_180014F7D
0x180014e73  xor     edx, edx; length
0x180014e75  mov     rcx, [rsp+258h+string]; string
0x180014e7a  call    cs:__imp_WindowsGetStringRawBuffer
0x180014e81  nop     dword ptr [rax+rax+00h]
0x180014e86  mov     r9, rax
0x180014e89  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x180014e90  mov     edx, 104h; unsigned __int64
0x180014e95  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x180014e9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014e9f  mov     ebx, eax
0x180014ea1  test    eax, eax
0x180014ea3  jns     short loc_180014EDA
0x180014ea5  mov     rcx, [rsp+258h]; this
0x180014ead  mov     r9d, eax; char *
0x180014eb0  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180014eb7  mov     edx, 827h; void *
0x180014ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014ec1  nop
0x180014ec2  mov     rcx, [rsp+258h+string]; string
0x180014ec7  call    cs:__imp_WindowsDeleteString
0x180014ece  nop     dword ptr [rax+rax+00h]
0x180014ed3  mov     eax, ebx
0x180014ed5  jmp     loc_180014F7D
0x180014eda  mov     qword ptr [rsi], 0
0x180014ee1  xor     ecx, ecx; string
0x180014ee3  call    cs:__imp_WindowsDeleteString
0x180014eea  nop     dword ptr [rax+rax+00h]
0x180014eef  mov     [rsp+258h+var_230], 0
0x180014ef8  lea     rdx, [rsp+258h+var_230]; HSTRING *
0x180014efd  lea     rcx, [rsp+258h+var_228]; this
0x180014f02  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180014f07  mov     edi, eax
0x180014f09  mov     rbx, [rsp+258h+var_230]
0x180014f0e  test    eax, eax
0x180014f10  js      short loc_180014F1F
0x180014f12  mov     rdx, rsi; struct IInspectable **
0x180014f15  mov     rcx, rbx; HSTRING
0x180014f18  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x180014f1d  mov     edi, eax
0x180014f1f  mov     rcx, rbx; string
0x180014f22  call    cs:__imp_WindowsDeleteString
0x180014f29  nop     dword ptr [rax+rax+00h]
0x180014f2e  test    edi, edi
0x180014f30  jns     short loc_180014F64
0x180014f32  mov     rcx, [rsp+258h]; this
0x180014f3a  mov     r9d, edi; char *
0x180014f3d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180014f44  mov     edx, 828h; void *
0x180014f49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f4e  nop
0x180014f4f  mov     rcx, [rsp+258h+string]; string
0x180014f54  call    cs:__imp_WindowsDeleteString
0x180014f5b  nop     dword ptr [rax+rax+00h]
0x180014f60  mov     eax, edi
0x180014f62  jmp     short loc_180014F7D
0x180014f64  mov     rcx, [rsp+258h+string]; string
0x180014f69  call    cs:__imp_WindowsDeleteString
0x180014f70  nop     dword ptr [rax+rax+00h]
0x180014f75  xor     eax, eax
0x180014f77  jmp     short loc_180014F7D
0x180014f79  mov     eax, dword ptr [rsp+258h+string]
0x180014f7d  mov     rcx, [rsp+258h+var_18]
0x180014f85  xor     rcx, rsp; StackCookie
0x180014f88  call    __security_check_cookie
0x180014f8d  lea     r11, [rsp+258h+var_8]
0x180014f95  mov     rbx, [r11+20h]
0x180014f99  mov     rsi, [r11+28h]
0x180014f9d  mov     rsp, r11
0x180014fa0  pop     rdi
0x180014fa1  retn
```
