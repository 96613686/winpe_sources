# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x1800212f0`
- end: `0x180021532`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `578`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x1800087ec`
- `0x180008f60`
- `0x18000b2fc`
- `0x180017418`
- `0x18001a348`
- `0x1800212f0`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800213d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002143a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800214e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800214f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021394`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800213d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002143a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800214e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800214f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800213ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002146c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800213ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002146c`

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
0x1800212f0  mov     [rsp+arg_10], rbx
0x1800212f5  mov     [rsp+arg_18], rsi
0x1800212fa  push    rdi
0x1800212fb  sub     rsp, 260h
0x180021302  mov     rax, cs:__security_cookie
0x180021309  xor     rax, rsp
0x18002130c  mov     [rsp+268h+var_18], rax
0x180021314  mov     rsi, rdx
0x180021317  mov     rdi, rcx
0x18002131a  mov     qword ptr [rdx], 0
0x180021321  mov     rax, [rcx+60h]
0x180021325  test    rax, rax
0x180021328  jz      short loc_180021335
0x18002132a  cmp     qword ptr [rax+20h], 0
0x18002132f  jnz     loc_180021504
0x180021335  mov     [rsp+268h+string], 0
0x18002133e  mov     rax, [rcx]
0x180021341  mov     rbx, [rax+30h]
0x180021345  xor     ecx, ecx; string
0x180021347  call    cs:__imp_WindowsDeleteString
0x18002134e  nop     dword ptr [rax+rax+00h]
0x180021353  mov     [rsp+268h+string], 0
0x18002135c  lea     rdx, [rsp+268h+string]
0x180021361  mov     rcx, rdi
0x180021364  mov     rax, rbx
0x180021367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002136c  mov     ebx, eax
0x18002136e  test    eax, eax
0x180021370  jns     short loc_1800213A7
0x180021372  mov     rcx, [rsp+268h]; this
0x18002137a  mov     r9d, eax; char *
0x18002137d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180021384  mov     edx, 2D7h; void *
0x180021389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002138e  nop
0x18002138f  mov     rcx, [rsp+268h+string]; string
0x180021394  call    cs:__imp_WindowsDeleteString
0x18002139b  nop     dword ptr [rax+rax+00h]
0x1800213a0  mov     eax, ebx
0x1800213a2  jmp     loc_18002150C
0x1800213a7  mov     rcx, [rsp+268h+string]; string
0x1800213ac  test    rcx, rcx
0x1800213af  jnz     short loc_1800213EB
0x1800213b1  mov     rcx, [rsp+268h]; this
0x1800213b9  mov     ebx, 80070057h
0x1800213be  mov     r9d, ebx; char *
0x1800213c1  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800213c8  mov     edx, 2DCh; void *
0x1800213cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800213d2  nop
0x1800213d3  mov     rcx, [rsp+268h+string]; string
0x1800213d8  call    cs:__imp_WindowsDeleteString
0x1800213df  nop     dword ptr [rax+rax+00h]
0x1800213e4  mov     eax, ebx
0x1800213e6  jmp     loc_18002150C
0x1800213eb  xor     edx, edx; length
0x1800213ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800213f4  nop     dword ptr [rax+rax+00h]
0x1800213f9  mov     r9, rax
0x1800213fc  lea     r8, aLsdescription; "%lsDescription"
0x180021403  mov     edx, 104h; unsigned __int64
0x180021408  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18002140d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021412  mov     ebx, eax
0x180021414  test    eax, eax
0x180021416  jns     short loc_18002144D
0x180021418  mov     rcx, [rsp+268h]; this
0x180021420  mov     r9d, eax; char *
0x180021423  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18002142a  mov     edx, 2E1h; void *
0x18002142f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021434  nop
0x180021435  mov     rcx, [rsp+268h+string]; string
0x18002143a  call    cs:__imp_WindowsDeleteString
0x180021441  nop     dword ptr [rax+rax+00h]
0x180021446  mov     eax, ebx
0x180021448  jmp     loc_18002150C
0x18002144d  mov     rdx, rsi; HSTRING *
0x180021450  lea     rcx, [rsp+268h+var_228]; this
0x180021455  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18002145a  mov     ebx, eax
0x18002145c  mov     edi, 80070003h
0x180021461  cmp     eax, edi
0x180021463  jnz     short loc_1800214A7
0x180021465  xor     edx, edx; length
0x180021467  mov     rcx, [rsp+268h+string]; string
0x18002146c  call    cs:__imp_WindowsGetStringRawBuffer
0x180021473  nop     dword ptr [rax+rax+00h]
0x180021478  mov     rcx, [rsp+268h]; this
0x180021480  mov     [rsp+268h+var_240], rax; char *
0x180021485  lea     rax, aMissingDescrip; "Missing description: %ls"
0x18002148c  mov     qword ptr [rsp+268h+var_248], rax; int
0x180021491  mov     r9d, edi; char *
0x180021494  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18002149b  mov     edx, 2EEh; void *
0x1800214a0  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800214a5  jmp     short loc_1800214F3
0x1800214a7  test    ebx, ebx
0x1800214a9  jns     short loc_1800214F3
0x1800214ab  mov     rcx, [rsp+268h]; this
0x1800214b3  lea     rax, [rsp+268h+var_228]
0x1800214b8  mov     [rsp+268h+var_240], rax; char *
0x1800214bd  lea     rax, aLs; "%ls"
0x1800214c4  mov     qword ptr [rsp+268h+var_248], rax; int
0x1800214c9  mov     r9d, ebx; char *
0x1800214cc  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800214d3  mov     edx, 2F4h; void *
0x1800214d8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800214dd  nop
0x1800214de  mov     rcx, [rsp+268h+string]; string
0x1800214e3  call    cs:__imp_WindowsDeleteString
0x1800214ea  nop     dword ptr [rax+rax+00h]
0x1800214ef  mov     eax, ebx
0x1800214f1  jmp     short loc_18002150C
0x1800214f3  mov     rcx, [rsp+268h+string]; string
0x1800214f8  call    cs:__imp_WindowsDeleteString
0x1800214ff  nop     dword ptr [rax+rax+00h]
0x180021504  xor     eax, eax
0x180021506  jmp     short loc_18002150C
0x180021508  mov     eax, dword ptr [rsp+268h+string]
0x18002150c  mov     rcx, [rsp+268h+var_18]
0x180021514  xor     rcx, rsp; StackCookie
0x180021517  call    __security_check_cookie
0x18002151c  lea     r11, [rsp+268h+var_8]
0x180021524  mov     rbx, [r11+20h]
0x180021528  mov     rsi, [r11+28h]
0x18002152c  mov     rsp, r11
0x18002152f  pop     rdi
0x180021530  retn
```
