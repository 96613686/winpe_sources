# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x18001df50`
- end: `0x18001e0f3`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x180009190`
- `0x18000eacc`
- `0x18000f208`
- `0x18001d140`
- `0x18001df50`
- `0x1800202b0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dfee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001dfee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001df93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dfda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e035`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e04b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e0b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e0bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001df93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001dfda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e035`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e04b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e0b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e0bf`

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
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
        (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
      (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
      (const char *)(unsigned int)v5,
      (int)string);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x18001df50  mov     [rsp+arg_10], rbx
0x18001df55  mov     [rsp+arg_18], rsi
0x18001df5a  push    rdi
0x18001df5b  sub     rsp, 250h
0x18001df62  mov     rax, cs:__security_cookie
0x18001df69  xor     rax, rsp
0x18001df6c  mov     [rsp+258h+var_18], rax
0x18001df74  mov     rsi, rdx
0x18001df77  mov     rdi, rcx
0x18001df7a  mov     qword ptr [rdx], 0
0x18001df81  mov     [rsp+258h+string], 0
0x18001df8a  mov     rax, [rcx]
0x18001df8d  mov     rbx, [rax+30h]
0x18001df91  xor     ecx, ecx; string
0x18001df93  call    cs:__imp_WindowsDeleteString
0x18001df99  mov     [rsp+258h+string], 0; int
0x18001dfa2  lea     rdx, [rsp+258h+string]
0x18001dfa7  mov     rcx, rdi
0x18001dfaa  mov     rax, rbx
0x18001dfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfb2  mov     ebx, eax
0x18001dfb4  test    eax, eax
0x18001dfb6  jns     short loc_18001DFE7
0x18001dfb8  mov     rcx, [rsp+258h]; this
0x18001dfc0  mov     r9d, eax; char *
0x18001dfc3  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18001dfca  mov     edx, 821h; void *
0x18001dfcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dfd4  nop
0x18001dfd5  mov     rcx, [rsp+258h+string]; string
0x18001dfda  call    cs:__imp_WindowsDeleteString
0x18001dfe0  mov     eax, ebx
0x18001dfe2  jmp     loc_18001E0CD
0x18001dfe7  xor     edx, edx; length
0x18001dfe9  mov     rcx, [rsp+258h+string]; string
0x18001dfee  call    cs:__imp_WindowsGetStringRawBuffer
0x18001dff4  mov     r9, rax
0x18001dff7  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x18001dffe  mov     edx, 104h; unsigned __int64
0x18001e003  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18001e008  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e00d  mov     ebx, eax
0x18001e00f  test    eax, eax
0x18001e011  jns     short loc_18001E042
0x18001e013  mov     rcx, [rsp+258h]; this
0x18001e01b  mov     r9d, eax; char *
0x18001e01e  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18001e025  mov     edx, 827h; void *
0x18001e02a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e02f  nop
0x18001e030  mov     rcx, [rsp+258h+string]; string
0x18001e035  call    cs:__imp_WindowsDeleteString
0x18001e03b  mov     eax, ebx
0x18001e03d  jmp     loc_18001E0CD
0x18001e042  mov     qword ptr [rsi], 0
0x18001e049  xor     ecx, ecx; string
0x18001e04b  call    cs:__imp_WindowsDeleteString
0x18001e051  mov     [rsp+258h+var_230], 0
0x18001e05a  lea     rdx, [rsp+258h+var_230]; HSTRING *
0x18001e05f  lea     rcx, [rsp+258h+var_228]; this
0x18001e064  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18001e069  mov     edi, eax
0x18001e06b  mov     rbx, [rsp+258h+var_230]
0x18001e070  test    eax, eax
0x18001e072  js      short loc_18001E081
0x18001e074  mov     rdx, rsi; struct IInspectable **
0x18001e077  mov     rcx, rbx; HSTRING
0x18001e07a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18001e07f  mov     edi, eax
0x18001e081  mov     rcx, rbx; string
0x18001e084  call    cs:__imp_WindowsDeleteString
0x18001e08a  test    edi, edi
0x18001e08c  jns     short loc_18001E0BA
0x18001e08e  mov     rcx, [rsp+258h]; this
0x18001e096  mov     r9d, edi; char *
0x18001e099  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18001e0a0  mov     edx, 828h; void *
0x18001e0a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e0aa  nop
0x18001e0ab  mov     rcx, [rsp+258h+string]; string
0x18001e0b0  call    cs:__imp_WindowsDeleteString
0x18001e0b6  mov     eax, edi
0x18001e0b8  jmp     short loc_18001E0CD
0x18001e0ba  mov     rcx, [rsp+258h+string]; string
0x18001e0bf  call    cs:__imp_WindowsDeleteString
0x18001e0c5  xor     eax, eax
0x18001e0c7  jmp     short loc_18001E0CD
0x18001e0c9  mov     eax, dword ptr [rsp+258h+string]
0x18001e0cd  mov     rcx, [rsp+258h+var_18]
0x18001e0d5  xor     rcx, rsp; StackCookie
0x18001e0d8  call    __security_check_cookie
0x18001e0dd  lea     r11, [rsp+258h+var_8]
0x18001e0e5  mov     rbx, [r11+20h]
0x18001e0e9  mov     rsi, [r11+28h]
0x18001e0ed  mov     rsp, r11
0x18001e0f0  pop     rdi
0x18001e0f1  retn
```
