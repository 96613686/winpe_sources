# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x180017e60`
- end: `0x1800180a2`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `578`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x180009eac`
- `0x18000c518`
- `0x1800136e8`
- `0x180015170`
- `0x180017e60`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017fdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017f5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017fdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017eb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017f04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017f48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018068`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017eb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017f04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017f48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018068`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSettingBase::get_Description(
        SystemSettings::DataModel::CSettingBase *this,
        HSTRING *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rax
  __int64 (__fastcall *v7)(SystemSettings::DataModel::CSettingBase *, HSTRING *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  PCWSTR StringRawBuffer; // rax
  int v12; // eax
  HSTRING *v13; // r8
  unsigned int v14; // ebx
  int ResourceStringById; // ebx
  const char *v16; // rax
  int v17; // [rsp+20h] [rbp-248h]
  HSTRING string[2]; // [rsp+30h] [rbp-238h] BYREF
  char v19[2]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  try
  {
    *a2 = 0;
    v6 = *((_QWORD *)this + 12);
    if ( !v6 || !*(_QWORD *)(v6 + 32) )
    {
      string[0] = 0;
      v7 = *(__int64 (__fastcall **)(SystemSettings::DataModel::CSettingBase *, HSTRING *))(*(_QWORD *)this + 48LL);
      WindowsDeleteString(0);
      string[0] = 0;
      v8 = v7(this, string);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D7,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v8,
          v17);
        WindowsDeleteString(string[0]);
        return v9;
      }
      if ( !string[0] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2DC,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)0x80070057LL,
          v17);
        WindowsDeleteString(string[0]);
        return 2147942487LL;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      v12 = StringCchPrintfW((unsigned __int16 *)v19, 0x104u, L"%lsDescription", StringRawBuffer);
      v14 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2E1,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)v12,
          v17);
        WindowsDeleteString(string[0]);
        return v14;
      }
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById((SystemSettings::DataModel *)v19, a2, v13);
      if ( ResourceStringById == -2147024893 )
      {
        v16 = (const char *)WindowsGetStringRawBuffer(string[0], 0);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x2EE,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)0x80070003LL,
          (int)"Missing description: %ls",
          v16);
      }
      else if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x2F4,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)(unsigned int)ResourceStringById,
          (int)"%ls",
          v19);
        WindowsDeleteString(string[0]);
        return (unsigned int)ResourceStringById;
      }
      WindowsDeleteString(string[0]);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2FA,
                           (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingHandlersBaseCore.h",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180017e60  mov     [rsp+arg_10], rbx
0x180017e65  mov     [rsp+arg_18], rsi
0x180017e6a  push    rdi
0x180017e6b  sub     rsp, 260h
0x180017e72  mov     rax, cs:__security_cookie
0x180017e79  xor     rax, rsp
0x180017e7c  mov     [rsp+268h+var_18], rax
0x180017e84  mov     rsi, rdx
0x180017e87  mov     rdi, rcx
0x180017e8a  mov     qword ptr [rdx], 0
0x180017e91  mov     rax, [rcx+60h]
0x180017e95  test    rax, rax
0x180017e98  jz      short loc_180017EA5
0x180017e9a  cmp     qword ptr [rax+20h], 0
0x180017e9f  jnz     loc_180018074
0x180017ea5  mov     [rsp+268h+string], 0
0x180017eae  mov     rax, [rcx]
0x180017eb1  mov     rbx, [rax+30h]
0x180017eb5  xor     ecx, ecx; string
0x180017eb7  call    cs:__imp_WindowsDeleteString
0x180017ebe  nop     dword ptr [rax+rax+00h]
0x180017ec3  mov     [rsp+268h+string], 0
0x180017ecc  lea     rdx, [rsp+268h+string]
0x180017ed1  mov     rcx, rdi
0x180017ed4  mov     rax, rbx
0x180017ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017edc  mov     ebx, eax
0x180017ede  test    eax, eax
0x180017ee0  jns     short loc_180017F17
0x180017ee2  mov     rcx, [rsp+268h]; this
0x180017eea  mov     r9d, eax; char *
0x180017eed  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180017ef4  mov     edx, 2D7h; void *
0x180017ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017efe  nop
0x180017eff  mov     rcx, [rsp+268h+string]; string
0x180017f04  call    cs:__imp_WindowsDeleteString
0x180017f0b  nop     dword ptr [rax+rax+00h]
0x180017f10  mov     eax, ebx
0x180017f12  jmp     loc_18001807C
0x180017f17  mov     rcx, [rsp+268h+string]; string
0x180017f1c  test    rcx, rcx
0x180017f1f  jnz     short loc_180017F5B
0x180017f21  mov     rcx, [rsp+268h]; this
0x180017f29  mov     ebx, 80070057h
0x180017f2e  mov     r9d, ebx; char *
0x180017f31  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180017f38  mov     edx, 2DCh; void *
0x180017f3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f42  nop
0x180017f43  mov     rcx, [rsp+268h+string]; string
0x180017f48  call    cs:__imp_WindowsDeleteString
0x180017f4f  nop     dword ptr [rax+rax+00h]
0x180017f54  mov     eax, ebx
0x180017f56  jmp     loc_18001807C
0x180017f5b  xor     edx, edx; length
0x180017f5d  call    cs:__imp_WindowsGetStringRawBuffer
0x180017f64  nop     dword ptr [rax+rax+00h]
0x180017f69  mov     r9, rax
0x180017f6c  lea     r8, aLsdescription; "%lsDescription"
0x180017f73  mov     edx, 104h; unsigned __int64
0x180017f78  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180017f7d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017f82  mov     ebx, eax
0x180017f84  test    eax, eax
0x180017f86  jns     short loc_180017FBD
0x180017f88  mov     rcx, [rsp+268h]; this
0x180017f90  mov     r9d, eax; char *
0x180017f93  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180017f9a  mov     edx, 2E1h; void *
0x180017f9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fa4  nop
0x180017fa5  mov     rcx, [rsp+268h+string]; string
0x180017faa  call    cs:__imp_WindowsDeleteString
0x180017fb1  nop     dword ptr [rax+rax+00h]
0x180017fb6  mov     eax, ebx
0x180017fb8  jmp     loc_18001807C
0x180017fbd  mov     rdx, rsi; HSTRING *
0x180017fc0  lea     rcx, [rsp+268h+var_228]; this
0x180017fc5  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180017fca  mov     ebx, eax
0x180017fcc  mov     edi, 80070003h
0x180017fd1  cmp     eax, edi
0x180017fd3  jnz     short loc_180018017
0x180017fd5  xor     edx, edx; length
0x180017fd7  mov     rcx, [rsp+268h+string]; string
0x180017fdc  call    cs:__imp_WindowsGetStringRawBuffer
0x180017fe3  nop     dword ptr [rax+rax+00h]
0x180017fe8  mov     rcx, [rsp+268h]; this
0x180017ff0  mov     [rsp+268h+var_240], rax; char *
0x180017ff5  lea     rax, aMissingDescrip; "Missing description: %ls"
0x180017ffc  mov     qword ptr [rsp+268h+var_248], rax; int
0x180018001  mov     r9d, edi; char *
0x180018004  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001800b  mov     edx, 2EEh; void *
0x180018010  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180018015  jmp     short loc_180018063
0x180018017  test    ebx, ebx
0x180018019  jns     short loc_180018063
0x18001801b  mov     rcx, [rsp+268h]; this
0x180018023  lea     rax, [rsp+268h+var_228]
0x180018028  mov     [rsp+268h+var_240], rax; char *
0x18001802d  lea     rax, aLs; "%ls"
0x180018034  mov     qword ptr [rsp+268h+var_248], rax; int
0x180018039  mov     r9d, ebx; char *
0x18001803c  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180018043  mov     edx, 2F4h; void *
0x180018048  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001804d  nop
0x18001804e  mov     rcx, [rsp+268h+string]; string
0x180018053  call    cs:__imp_WindowsDeleteString
0x18001805a  nop     dword ptr [rax+rax+00h]
0x18001805f  mov     eax, ebx
0x180018061  jmp     short loc_18001807C
0x180018063  mov     rcx, [rsp+268h+string]; string
0x180018068  call    cs:__imp_WindowsDeleteString
0x18001806f  nop     dword ptr [rax+rax+00h]
0x180018074  xor     eax, eax
0x180018076  jmp     short loc_18001807C
0x180018078  mov     eax, dword ptr [rsp+268h+string]
0x18001807c  mov     rcx, [rsp+268h+var_18]
0x180018084  xor     rcx, rsp; StackCookie
0x180018087  call    __security_check_cookie
0x18001808c  lea     r11, [rsp+268h+var_8]
0x180018094  mov     rbx, [r11+20h]
0x180018098  mov     rsi, [r11+28h]
0x18001809c  mov     rsp, r11
0x18001809f  pop     rdi
0x1800180a0  retn
```
