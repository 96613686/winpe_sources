# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x180023a00`
- end: `0x180023c42`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180046070`
- `0x1800c2350`
- `0x180133960`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x180019a48`
- `0x18001a64c`
- `0x180021470`
- `0x180023a00`
- `0x18004d1ac`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023b4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023b4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023c08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023b7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023afd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023b7c`

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
0x180023a00  mov     [rsp+arg_10], rbx
0x180023a05  mov     [rsp+arg_18], rsi
0x180023a0a  push    rdi
0x180023a0b  sub     rsp, 260h
0x180023a12  mov     rax, cs:__security_cookie
0x180023a19  xor     rax, rsp
0x180023a1c  mov     [rsp+268h+var_18], rax
0x180023a24  mov     rsi, rdx
0x180023a27  mov     rdi, rcx
0x180023a2a  mov     qword ptr [rdx], 0
0x180023a31  mov     rax, [rcx+60h]
0x180023a35  test    rax, rax
0x180023a38  jz      short loc_180023A45
0x180023a3a  cmp     qword ptr [rax+20h], 0
0x180023a3f  jnz     loc_180023C14
0x180023a45  mov     [rsp+268h+string], 0
0x180023a4e  mov     rax, [rcx]
0x180023a51  mov     rbx, [rax+30h]
0x180023a55  xor     ecx, ecx; string
0x180023a57  call    cs:__imp_WindowsDeleteString
0x180023a5e  nop     dword ptr [rax+rax+00h]
0x180023a63  mov     [rsp+268h+string], 0
0x180023a6c  lea     rdx, [rsp+268h+string]
0x180023a71  mov     rcx, rdi
0x180023a74  mov     rax, rbx
0x180023a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a7c  mov     ebx, eax
0x180023a7e  test    eax, eax
0x180023a80  jns     short loc_180023AB7
0x180023a82  mov     rcx, [rsp+268h]; this
0x180023a8a  mov     r9d, eax; char *
0x180023a8d  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180023a94  mov     edx, 2D7h; void *
0x180023a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023a9e  nop
0x180023a9f  mov     rcx, [rsp+268h+string]; string
0x180023aa4  call    cs:__imp_WindowsDeleteString
0x180023aab  nop     dword ptr [rax+rax+00h]
0x180023ab0  mov     eax, ebx
0x180023ab2  jmp     loc_180023C1C
0x180023ab7  mov     rcx, [rsp+268h+string]; string
0x180023abc  test    rcx, rcx
0x180023abf  jnz     short loc_180023AFB
0x180023ac1  mov     rcx, [rsp+268h]; this
0x180023ac9  mov     ebx, 80070057h
0x180023ace  mov     r9d, ebx; char *
0x180023ad1  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180023ad8  mov     edx, 2DCh; void *
0x180023add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ae2  nop
0x180023ae3  mov     rcx, [rsp+268h+string]; string
0x180023ae8  call    cs:__imp_WindowsDeleteString
0x180023aef  nop     dword ptr [rax+rax+00h]
0x180023af4  mov     eax, ebx
0x180023af6  jmp     loc_180023C1C
0x180023afb  xor     edx, edx; length
0x180023afd  call    cs:__imp_WindowsGetStringRawBuffer
0x180023b04  nop     dword ptr [rax+rax+00h]
0x180023b09  mov     r9, rax
0x180023b0c  lea     r8, aLsdescription; "%lsDescription"
0x180023b13  mov     edx, 104h; unsigned __int64
0x180023b18  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180023b1d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023b22  mov     ebx, eax
0x180023b24  test    eax, eax
0x180023b26  jns     short loc_180023B5D
0x180023b28  mov     rcx, [rsp+268h]; this
0x180023b30  mov     r9d, eax; char *
0x180023b33  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180023b3a  mov     edx, 2E1h; void *
0x180023b3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b44  nop
0x180023b45  mov     rcx, [rsp+268h+string]; string
0x180023b4a  call    cs:__imp_WindowsDeleteString
0x180023b51  nop     dword ptr [rax+rax+00h]
0x180023b56  mov     eax, ebx
0x180023b58  jmp     loc_180023C1C
0x180023b5d  mov     rdx, rsi; HSTRING *
0x180023b60  lea     rcx, [rsp+268h+var_228]; this
0x180023b65  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180023b6a  mov     ebx, eax
0x180023b6c  mov     edi, 80070003h
0x180023b71  cmp     eax, edi
0x180023b73  jnz     short loc_180023BB7
0x180023b75  xor     edx, edx; length
0x180023b77  mov     rcx, [rsp+268h+string]; string
0x180023b7c  call    cs:__imp_WindowsGetStringRawBuffer
0x180023b83  nop     dword ptr [rax+rax+00h]
0x180023b88  mov     rcx, [rsp+268h]; this
0x180023b90  mov     [rsp+268h+var_240], rax; char *
0x180023b95  lea     rax, aMissingDescrip; "Missing description: %ls"
0x180023b9c  mov     qword ptr [rsp+268h+var_248], rax; int
0x180023ba1  mov     r9d, edi; char *
0x180023ba4  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180023bab  mov     edx, 2EEh; void *
0x180023bb0  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023bb5  jmp     short loc_180023C03
0x180023bb7  test    ebx, ebx
0x180023bb9  jns     short loc_180023C03
0x180023bbb  mov     rcx, [rsp+268h]; this
0x180023bc3  lea     rax, [rsp+268h+var_228]
0x180023bc8  mov     [rsp+268h+var_240], rax; char *
0x180023bcd  lea     rax, aLs; "%ls"
0x180023bd4  mov     qword ptr [rsp+268h+var_248], rax; int
0x180023bd9  mov     r9d, ebx; char *
0x180023bdc  lea     r8, aOnecoreuapInte_11; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180023be3  mov     edx, 2F4h; void *
0x180023be8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023bed  nop
0x180023bee  mov     rcx, [rsp+268h+string]; string
0x180023bf3  call    cs:__imp_WindowsDeleteString
0x180023bfa  nop     dword ptr [rax+rax+00h]
0x180023bff  mov     eax, ebx
0x180023c01  jmp     short loc_180023C1C
0x180023c03  mov     rcx, [rsp+268h+string]; string
0x180023c08  call    cs:__imp_WindowsDeleteString
0x180023c0f  nop     dword ptr [rax+rax+00h]
0x180023c14  xor     eax, eax
0x180023c16  jmp     short loc_180023C1C
0x180023c18  mov     eax, dword ptr [rsp+268h+string]
0x180023c1c  mov     rcx, [rsp+268h+var_18]
0x180023c24  xor     rcx, rsp; StackCookie
0x180023c27  call    __security_check_cookie
0x180023c2c  lea     r11, [rsp+268h+var_8]
0x180023c34  mov     rbx, [r11+20h]
0x180023c38  mov     rsi, [r11+28h]
0x180023c3c  mov     rsp, r11
0x180023c3f  pop     rdi
0x180023c40  retn
```
