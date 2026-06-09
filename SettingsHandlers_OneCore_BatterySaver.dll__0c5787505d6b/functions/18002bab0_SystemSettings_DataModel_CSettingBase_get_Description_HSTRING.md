# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x18002bab0`
- end: `0x18002bcc2`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `530`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180009190`
- `0x18000eacc`
- `0x18000f208`
- `0x1800135cc`
- `0x1800202b0`
- `0x180024248`
- `0x18002bab0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bb9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bc0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bb9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bc0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bb8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc8e`

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
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)0x80070003LL,
          (int)"Missing description: %ls",
          v16);
      }
      else if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x2F4,
          (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
                           (unsigned int)"OnecoreUAP\\internal\\Shell\\inc\\SettingHandlersBaseCore.h",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x18002bab0  mov     [rsp+arg_10], rbx
0x18002bab5  mov     [rsp+arg_18], rsi
0x18002baba  push    rdi
0x18002babb  sub     rsp, 260h
0x18002bac2  mov     rax, cs:__security_cookie
0x18002bac9  xor     rax, rsp
0x18002bacc  mov     [rsp+268h+var_18], rax
0x18002bad4  mov     rsi, rdx
0x18002bad7  mov     rdi, rcx
0x18002bada  mov     qword ptr [rdx], 0
0x18002bae1  mov     rax, [rcx+60h]
0x18002bae5  test    rax, rax
0x18002bae8  jz      short loc_18002BAF5
0x18002baea  cmp     qword ptr [rax+20h], 0
0x18002baef  jnz     loc_18002BC94
0x18002baf5  mov     [rsp+268h+string], 0
0x18002bafe  mov     rax, [rcx]
0x18002bb01  mov     rbx, [rax+30h]
0x18002bb05  xor     ecx, ecx; string
0x18002bb07  call    cs:__imp_WindowsDeleteString
0x18002bb0d  mov     [rsp+268h+string], 0
0x18002bb16  lea     rdx, [rsp+268h+string]
0x18002bb1b  mov     rcx, rdi
0x18002bb1e  mov     rax, rbx
0x18002bb21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb26  mov     ebx, eax
0x18002bb28  test    eax, eax
0x18002bb2a  jns     short loc_18002BB5B
0x18002bb2c  mov     rcx, [rsp+268h]; this
0x18002bb34  mov     r9d, eax; char *
0x18002bb37  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002bb3e  mov     edx, 2D7h; void *
0x18002bb43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bb48  nop
0x18002bb49  mov     rcx, [rsp+268h+string]; string
0x18002bb4e  call    cs:__imp_WindowsDeleteString
0x18002bb54  mov     eax, ebx
0x18002bb56  jmp     loc_18002BC9C
0x18002bb5b  mov     rcx, [rsp+268h+string]; string
0x18002bb60  test    rcx, rcx
0x18002bb63  jnz     short loc_18002BB99
0x18002bb65  mov     rcx, [rsp+268h]; this
0x18002bb6d  mov     ebx, 80070057h
0x18002bb72  mov     r9d, ebx; char *
0x18002bb75  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002bb7c  mov     edx, 2DCh; void *
0x18002bb81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bb86  nop
0x18002bb87  mov     rcx, [rsp+268h+string]; string
0x18002bb8c  call    cs:__imp_WindowsDeleteString
0x18002bb92  mov     eax, ebx
0x18002bb94  jmp     loc_18002BC9C
0x18002bb99  xor     edx, edx; length
0x18002bb9b  call    cs:__imp_WindowsGetStringRawBuffer
0x18002bba1  mov     r9, rax
0x18002bba4  lea     r8, aLsdescription; "%lsDescription"
0x18002bbab  mov     edx, 104h; unsigned __int64
0x18002bbb0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18002bbb5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bbba  mov     ebx, eax
0x18002bbbc  test    eax, eax
0x18002bbbe  jns     short loc_18002BBEF
0x18002bbc0  mov     rcx, [rsp+268h]; this
0x18002bbc8  mov     r9d, eax; char *
0x18002bbcb  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002bbd2  mov     edx, 2E1h; void *
0x18002bbd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bbdc  nop
0x18002bbdd  mov     rcx, [rsp+268h+string]; string
0x18002bbe2  call    cs:__imp_WindowsDeleteString
0x18002bbe8  mov     eax, ebx
0x18002bbea  jmp     loc_18002BC9C
0x18002bbef  mov     rdx, rsi; HSTRING *
0x18002bbf2  lea     rcx, [rsp+268h+var_228]; this
0x18002bbf7  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18002bbfc  mov     ebx, eax
0x18002bbfe  mov     edi, 80070003h
0x18002bc03  cmp     eax, edi
0x18002bc05  jnz     short loc_18002BC43
0x18002bc07  xor     edx, edx; length
0x18002bc09  mov     rcx, [rsp+268h+string]; string
0x18002bc0e  call    cs:__imp_WindowsGetStringRawBuffer
0x18002bc14  mov     rcx, [rsp+268h]; this
0x18002bc1c  mov     [rsp+268h+var_240], rax; char *
0x18002bc21  lea     rax, aMissingDescrip; "Missing description: %ls"
0x18002bc28  mov     qword ptr [rsp+268h+var_248], rax; int
0x18002bc2d  mov     r9d, edi; char *
0x18002bc30  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002bc37  mov     edx, 2EEh; void *
0x18002bc3c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002bc41  jmp     short loc_18002BC89
0x18002bc43  test    ebx, ebx
0x18002bc45  jns     short loc_18002BC89
0x18002bc47  mov     rcx, [rsp+268h]; this
0x18002bc4f  lea     rax, [rsp+268h+var_228]
0x18002bc54  mov     [rsp+268h+var_240], rax; char *
0x18002bc59  lea     rax, aLs; "%ls"
0x18002bc60  mov     qword ptr [rsp+268h+var_248], rax; int
0x18002bc65  mov     r9d, ebx; char *
0x18002bc68  lea     r8, aOnecoreuapInte_4; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002bc6f  mov     edx, 2F4h; void *
0x18002bc74  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002bc79  nop
0x18002bc7a  mov     rcx, [rsp+268h+string]; string
0x18002bc7f  call    cs:__imp_WindowsDeleteString
0x18002bc85  mov     eax, ebx
0x18002bc87  jmp     short loc_18002BC9C
0x18002bc89  mov     rcx, [rsp+268h+string]; string
0x18002bc8e  call    cs:__imp_WindowsDeleteString
0x18002bc94  xor     eax, eax
0x18002bc96  jmp     short loc_18002BC9C
0x18002bc98  mov     eax, dword ptr [rsp+268h+string]
0x18002bc9c  mov     rcx, [rsp+268h+var_18]
0x18002bca4  xor     rcx, rsp; StackCookie
0x18002bca7  call    __security_check_cookie
0x18002bcac  lea     r11, [rsp+268h+var_8]
0x18002bcb4  mov     rbx, [r11+20h]
0x18002bcb8  mov     rsi, [r11+28h]
0x18002bcbc  mov     rsp, r11
0x18002bcbf  pop     rdi
0x18002bcc0  retn
```
