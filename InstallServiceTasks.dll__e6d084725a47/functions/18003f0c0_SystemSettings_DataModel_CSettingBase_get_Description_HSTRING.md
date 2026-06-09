# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x18003f0c0`
- end: `0x18003f2d2`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `530`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180003450`
- `0x18000912c`
- `0x1800098c8`
- `0x18000f5dc`
- `0x18000fc84`
- `0x18003cca8`
- `0x18003f0c0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f19c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f28f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f19c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f28f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f21e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f21e`

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
0x18003f0c0  mov     [rsp+arg_10], rbx
0x18003f0c5  mov     [rsp+arg_18], rsi
0x18003f0ca  push    rdi
0x18003f0cb  sub     rsp, 260h
0x18003f0d2  mov     rax, cs:__security_cookie
0x18003f0d9  xor     rax, rsp
0x18003f0dc  mov     [rsp+268h+var_18], rax
0x18003f0e4  mov     rsi, rdx
0x18003f0e7  mov     rdi, rcx
0x18003f0ea  mov     qword ptr [rdx], 0
0x18003f0f1  mov     rax, [rcx+60h]
0x18003f0f5  test    rax, rax
0x18003f0f8  jz      short loc_18003F105
0x18003f0fa  cmp     qword ptr [rax+20h], 0
0x18003f0ff  jnz     loc_18003F2A4
0x18003f105  mov     [rsp+268h+string], 0
0x18003f10e  mov     rax, [rcx]
0x18003f111  mov     rbx, [rax+30h]
0x18003f115  xor     ecx, ecx; string
0x18003f117  call    cs:__imp_WindowsDeleteString
0x18003f11d  mov     [rsp+268h+string], 0
0x18003f126  lea     rdx, [rsp+268h+string]
0x18003f12b  mov     rcx, rdi
0x18003f12e  mov     rax, rbx
0x18003f131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f136  mov     ebx, eax
0x18003f138  test    eax, eax
0x18003f13a  jns     short loc_18003F16B
0x18003f13c  mov     rcx, [rsp+268h]; this
0x18003f144  mov     r9d, eax; char *
0x18003f147  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18003f14e  mov     edx, 2D7h; void *
0x18003f153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f158  nop
0x18003f159  mov     rcx, [rsp+268h+string]; string
0x18003f15e  call    cs:__imp_WindowsDeleteString
0x18003f164  mov     eax, ebx
0x18003f166  jmp     loc_18003F2AC
0x18003f16b  mov     rcx, [rsp+268h+string]; string
0x18003f170  test    rcx, rcx
0x18003f173  jnz     short loc_18003F1A9
0x18003f175  mov     rcx, [rsp+268h]; this
0x18003f17d  mov     ebx, 80070057h
0x18003f182  mov     r9d, ebx; char *
0x18003f185  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18003f18c  mov     edx, 2DCh; void *
0x18003f191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f196  nop
0x18003f197  mov     rcx, [rsp+268h+string]; string
0x18003f19c  call    cs:__imp_WindowsDeleteString
0x18003f1a2  mov     eax, ebx
0x18003f1a4  jmp     loc_18003F2AC
0x18003f1a9  xor     edx, edx; length
0x18003f1ab  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f1b1  mov     r9, rax
0x18003f1b4  lea     r8, aLsdescription; "%lsDescription"
0x18003f1bb  mov     edx, 104h; unsigned __int64
0x18003f1c0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18003f1c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f1ca  mov     ebx, eax
0x18003f1cc  test    eax, eax
0x18003f1ce  jns     short loc_18003F1FF
0x18003f1d0  mov     rcx, [rsp+268h]; this
0x18003f1d8  mov     r9d, eax; char *
0x18003f1db  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18003f1e2  mov     edx, 2E1h; void *
0x18003f1e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f1ec  nop
0x18003f1ed  mov     rcx, [rsp+268h+string]; string
0x18003f1f2  call    cs:__imp_WindowsDeleteString
0x18003f1f8  mov     eax, ebx
0x18003f1fa  jmp     loc_18003F2AC
0x18003f1ff  mov     rdx, rsi; HSTRING *
0x18003f202  lea     rcx, [rsp+268h+var_228]; this
0x18003f207  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18003f20c  mov     ebx, eax
0x18003f20e  mov     edi, 80070003h
0x18003f213  cmp     eax, edi
0x18003f215  jnz     short loc_18003F253
0x18003f217  xor     edx, edx; length
0x18003f219  mov     rcx, [rsp+268h+string]; string
0x18003f21e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f224  mov     rcx, [rsp+268h]; this
0x18003f22c  mov     [rsp+268h+var_240], rax; char *
0x18003f231  lea     rax, aMissingDescrip; "Missing description: %ls"
0x18003f238  mov     qword ptr [rsp+268h+var_248], rax; int
0x18003f23d  mov     r9d, edi; char *
0x18003f240  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18003f247  mov     edx, 2EEh; void *
0x18003f24c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f251  jmp     short loc_18003F299
0x18003f253  test    ebx, ebx
0x18003f255  jns     short loc_18003F299
0x18003f257  mov     rcx, [rsp+268h]; this
0x18003f25f  lea     rax, [rsp+268h+var_228]
0x18003f264  mov     [rsp+268h+var_240], rax; char *
0x18003f269  lea     rax, aLs; "%ls"
0x18003f270  mov     qword ptr [rsp+268h+var_248], rax; int
0x18003f275  mov     r9d, ebx; char *
0x18003f278  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x18003f27f  mov     edx, 2F4h; void *
0x18003f284  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003f289  nop
0x18003f28a  mov     rcx, [rsp+268h+string]; string
0x18003f28f  call    cs:__imp_WindowsDeleteString
0x18003f295  mov     eax, ebx
0x18003f297  jmp     short loc_18003F2AC
0x18003f299  mov     rcx, [rsp+268h+string]; string
0x18003f29e  call    cs:__imp_WindowsDeleteString
0x18003f2a4  xor     eax, eax
0x18003f2a6  jmp     short loc_18003F2AC
0x18003f2a8  mov     eax, dword ptr [rsp+268h+string]
0x18003f2ac  mov     rcx, [rsp+268h+var_18]
0x18003f2b4  xor     rcx, rsp; StackCookie
0x18003f2b7  call    __security_check_cookie
0x18003f2bc  lea     r11, [rsp+268h+var_8]
0x18003f2c4  mov     rbx, [r11+20h]
0x18003f2c8  mov     rsi, [r11+28h]
0x18003f2cc  mov     rsp, r11
0x18003f2cf  pop     rdi
0x18003f2d0  retn
```
