# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x18001a730`
- end: `0x18001a942`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `530`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x1800030e0`
- `0x18000a2bc`
- `0x18000a2e0`
- `0x18000ac78`
- `0x1800146a8`
- `0x180016a1c`
- `0x18001a730`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a81b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a81b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a80c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a862`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a8ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a7ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a80c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a862`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a8ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001a90e`

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
0x18001a730  mov     [rsp+arg_10], rbx
0x18001a735  mov     [rsp+arg_18], rsi
0x18001a73a  push    rdi
0x18001a73b  sub     rsp, 260h
0x18001a742  mov     rax, cs:__security_cookie
0x18001a749  xor     rax, rsp
0x18001a74c  mov     [rsp+268h+var_18], rax
0x18001a754  mov     rsi, rdx
0x18001a757  mov     rdi, rcx
0x18001a75a  mov     qword ptr [rdx], 0
0x18001a761  mov     rax, [rcx+60h]
0x18001a765  test    rax, rax
0x18001a768  jz      short loc_18001A775
0x18001a76a  cmp     qword ptr [rax+20h], 0
0x18001a76f  jnz     loc_18001A914
0x18001a775  mov     [rsp+268h+string], 0
0x18001a77e  mov     rax, [rcx]
0x18001a781  mov     rbx, [rax+30h]
0x18001a785  xor     ecx, ecx; string
0x18001a787  call    cs:__imp_WindowsDeleteString
0x18001a78d  mov     [rsp+268h+string], 0
0x18001a796  lea     rdx, [rsp+268h+string]
0x18001a79b  mov     rcx, rdi
0x18001a79e  mov     rax, rbx
0x18001a7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7a6  mov     ebx, eax
0x18001a7a8  test    eax, eax
0x18001a7aa  jns     short loc_18001A7DB
0x18001a7ac  mov     rcx, [rsp+268h]; this
0x18001a7b4  mov     r9d, eax; char *
0x18001a7b7  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001a7be  mov     edx, 2D7h; void *
0x18001a7c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a7c8  nop
0x18001a7c9  mov     rcx, [rsp+268h+string]; string
0x18001a7ce  call    cs:__imp_WindowsDeleteString
0x18001a7d4  mov     eax, ebx
0x18001a7d6  jmp     loc_18001A91C
0x18001a7db  mov     rcx, [rsp+268h+string]; string
0x18001a7e0  test    rcx, rcx
0x18001a7e3  jnz     short loc_18001A819
0x18001a7e5  mov     rcx, [rsp+268h]; this
0x18001a7ed  mov     ebx, 80070057h
0x18001a7f2  mov     r9d, ebx; char *
0x18001a7f5  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001a7fc  mov     edx, 2DCh; void *
0x18001a801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a806  nop
0x18001a807  mov     rcx, [rsp+268h+string]; string
0x18001a80c  call    cs:__imp_WindowsDeleteString
0x18001a812  mov     eax, ebx
0x18001a814  jmp     loc_18001A91C
0x18001a819  xor     edx, edx; length
0x18001a81b  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a821  mov     r9, rax
0x18001a824  lea     r8, aLsdescription; "%lsDescription"
0x18001a82b  mov     edx, 104h; unsigned __int64
0x18001a830  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18001a835  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a83a  mov     ebx, eax
0x18001a83c  test    eax, eax
0x18001a83e  jns     short loc_18001A86F
0x18001a840  mov     rcx, [rsp+268h]; this
0x18001a848  mov     r9d, eax; char *
0x18001a84b  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001a852  mov     edx, 2E1h; void *
0x18001a857  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a85c  nop
0x18001a85d  mov     rcx, [rsp+268h+string]; string
0x18001a862  call    cs:__imp_WindowsDeleteString
0x18001a868  mov     eax, ebx
0x18001a86a  jmp     loc_18001A91C
0x18001a86f  mov     rdx, rsi; HSTRING *
0x18001a872  lea     rcx, [rsp+268h+var_228]; this
0x18001a877  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18001a87c  mov     ebx, eax
0x18001a87e  mov     edi, 80070003h
0x18001a883  cmp     eax, edi
0x18001a885  jnz     short loc_18001A8C3
0x18001a887  xor     edx, edx; length
0x18001a889  mov     rcx, [rsp+268h+string]; string
0x18001a88e  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a894  mov     rcx, [rsp+268h]; this
0x18001a89c  mov     [rsp+268h+var_240], rax; char *
0x18001a8a1  lea     rax, aMissingDescrip; "Missing description: %ls"
0x18001a8a8  mov     qword ptr [rsp+268h+var_248], rax; int
0x18001a8ad  mov     r9d, edi; char *
0x18001a8b0  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001a8b7  mov     edx, 2EEh; void *
0x18001a8bc  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a8c1  jmp     short loc_18001A909
0x18001a8c3  test    ebx, ebx
0x18001a8c5  jns     short loc_18001A909
0x18001a8c7  mov     rcx, [rsp+268h]; this
0x18001a8cf  lea     rax, [rsp+268h+var_228]
0x18001a8d4  mov     [rsp+268h+var_240], rax; char *
0x18001a8d9  lea     rax, aLs; "%ls"
0x18001a8e0  mov     qword ptr [rsp+268h+var_248], rax; int
0x18001a8e5  mov     r9d, ebx; char *
0x18001a8e8  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18001a8ef  mov     edx, 2F4h; void *
0x18001a8f4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001a8f9  nop
0x18001a8fa  mov     rcx, [rsp+268h+string]; string
0x18001a8ff  call    cs:__imp_WindowsDeleteString
0x18001a905  mov     eax, ebx
0x18001a907  jmp     short loc_18001A91C
0x18001a909  mov     rcx, [rsp+268h+string]; string
0x18001a90e  call    cs:__imp_WindowsDeleteString
0x18001a914  xor     eax, eax
0x18001a916  jmp     short loc_18001A91C
0x18001a918  mov     eax, dword ptr [rsp+268h+string]
0x18001a91c  mov     rcx, [rsp+268h+var_18]
0x18001a924  xor     rcx, rsp; StackCookie
0x18001a927  call    __security_check_cookie
0x18001a92c  lea     r11, [rsp+268h+var_8]
0x18001a934  mov     rbx, [r11+20h]
0x18001a938  mov     rsi, [r11+28h]
0x18001a93c  mov     rsp, r11
0x18001a93f  pop     rdi
0x18001a940  retn
```
