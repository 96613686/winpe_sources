# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetActionDescription(IInspectable * *)

- ea: `0x18004a620`
- end: `0x18004a7c3`
- name: `?GetActionDescription@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAPEAUIInspectable@@@Z`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x1800028d0`
- `0x18000a13c`
- `0x18000a8fc`
- `0x18000f1f8`
- `0x1800177e0`
- `0x18004a620`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a71b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a78f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a6aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a71b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a78f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a6be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a6be`

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
          (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
        (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
      (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
      (const char *)(unsigned int)v5,
      (int)string);
    WindowsDeleteString(string);
    return v6;
  }
}

```

## disassembly

```asm
0x18004a620  mov     [rsp+arg_10], rbx
0x18004a625  mov     [rsp+arg_18], rsi
0x18004a62a  push    rdi
0x18004a62b  sub     rsp, 250h
0x18004a632  mov     rax, cs:__security_cookie
0x18004a639  xor     rax, rsp
0x18004a63c  mov     [rsp+258h+var_18], rax
0x18004a644  mov     rsi, rdx
0x18004a647  mov     rdi, rcx
0x18004a64a  mov     qword ptr [rdx], 0
0x18004a651  mov     [rsp+258h+string], 0
0x18004a65a  mov     rax, [rcx]
0x18004a65d  mov     rbx, [rax+30h]
0x18004a661  xor     ecx, ecx; string
0x18004a663  call    cs:__imp_WindowsDeleteString
0x18004a669  mov     [rsp+258h+string], 0; int
0x18004a672  lea     rdx, [rsp+258h+string]
0x18004a677  mov     rcx, rdi
0x18004a67a  mov     rax, rbx
0x18004a67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a682  mov     ebx, eax
0x18004a684  test    eax, eax
0x18004a686  jns     short loc_18004A6B7
0x18004a688  mov     rcx, [rsp+258h]; this
0x18004a690  mov     r9d, eax; char *
0x18004a693  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18004a69a  mov     edx, 821h; void *
0x18004a69f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a6a4  nop
0x18004a6a5  mov     rcx, [rsp+258h+string]; string
0x18004a6aa  call    cs:__imp_WindowsDeleteString
0x18004a6b0  mov     eax, ebx
0x18004a6b2  jmp     loc_18004A79D
0x18004a6b7  xor     edx, edx; length
0x18004a6b9  mov     rcx, [rsp+258h+string]; string
0x18004a6be  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a6c4  mov     r9, rax
0x18004a6c7  lea     r8, aWsActiondescri; "%ws_ActionDescription"
0x18004a6ce  mov     edx, 104h; unsigned __int64
0x18004a6d3  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18004a6d8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a6dd  mov     ebx, eax
0x18004a6df  test    eax, eax
0x18004a6e1  jns     short loc_18004A712
0x18004a6e3  mov     rcx, [rsp+258h]; this
0x18004a6eb  mov     r9d, eax; char *
0x18004a6ee  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18004a6f5  mov     edx, 827h; void *
0x18004a6fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a6ff  nop
0x18004a700  mov     rcx, [rsp+258h+string]; string
0x18004a705  call    cs:__imp_WindowsDeleteString
0x18004a70b  mov     eax, ebx
0x18004a70d  jmp     loc_18004A79D
0x18004a712  mov     qword ptr [rsi], 0
0x18004a719  xor     ecx, ecx; string
0x18004a71b  call    cs:__imp_WindowsDeleteString
0x18004a721  mov     [rsp+258h+var_230], 0
0x18004a72a  lea     rdx, [rsp+258h+var_230]; HSTRING *
0x18004a72f  lea     rcx, [rsp+258h+var_228]; this
0x18004a734  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18004a739  mov     edi, eax
0x18004a73b  mov     rbx, [rsp+258h+var_230]
0x18004a740  test    eax, eax
0x18004a742  js      short loc_18004A751
0x18004a744  mov     rdx, rsi; struct IInspectable **
0x18004a747  mov     rcx, rbx; HSTRING
0x18004a74a  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18004a74f  mov     edi, eax
0x18004a751  mov     rcx, rbx; string
0x18004a754  call    cs:__imp_WindowsDeleteString
0x18004a75a  test    edi, edi
0x18004a75c  jns     short loc_18004A78A
0x18004a75e  mov     rcx, [rsp+258h]; this
0x18004a766  mov     r9d, edi; char *
0x18004a769  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18004a770  mov     edx, 828h; void *
0x18004a775  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a77a  nop
0x18004a77b  mov     rcx, [rsp+258h+string]; string
0x18004a780  call    cs:__imp_WindowsDeleteString
0x18004a786  mov     eax, edi
0x18004a788  jmp     short loc_18004A79D
0x18004a78a  mov     rcx, [rsp+258h+string]; string
0x18004a78f  call    cs:__imp_WindowsDeleteString
0x18004a795  xor     eax, eax
0x18004a797  jmp     short loc_18004A79D
0x18004a799  mov     eax, dword ptr [rsp+258h+string]
0x18004a79d  mov     rcx, [rsp+258h+var_18]
0x18004a7a5  xor     rcx, rsp; StackCookie
0x18004a7a8  call    __security_check_cookie
0x18004a7ad  lea     r11, [rsp+258h+var_8]
0x18004a7b5  mov     rbx, [r11+20h]
0x18004a7b9  mov     rsi, [r11+28h]
0x18004a7bd  mov     rsp, r11
0x18004a7c0  pop     rdi
0x18004a7c1  retn
```
