# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x180022720`
- end: `0x180022932`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `530`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180022710`

## callees

- `0x180002350`
- `0x180008c24`
- `0x180009718`
- `0x18000b784`
- `0x18001868c`
- `0x18001c060`
- `0x180022720`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002280b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002287e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002280b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002287e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022777`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800228ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800228fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022777`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800227fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022852`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800228ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800228fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CSettingBase::get_Description(
        SystemSettings::DataModel::CSettingBase *this,
        HSTRING *a2,
        unsigned int a3,
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x2FA, a3, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180022720  mov     [rsp+arg_10], rbx
0x180022725  mov     [rsp+arg_18], rsi
0x18002272a  push    rdi
0x18002272b  sub     rsp, 260h
0x180022732  mov     rax, cs:__security_cookie
0x180022739  xor     rax, rsp
0x18002273c  mov     [rsp+268h+var_18], rax
0x180022744  mov     rsi, rdx
0x180022747  mov     rdi, rcx
0x18002274a  mov     qword ptr [rdx], 0
0x180022751  mov     rax, [rcx+60h]
0x180022755  test    rax, rax
0x180022758  jz      short loc_180022765
0x18002275a  cmp     qword ptr [rax+20h], 0
0x18002275f  jnz     loc_180022904
0x180022765  mov     [rsp+268h+string], 0
0x18002276e  mov     rax, [rcx]
0x180022771  mov     rbx, [rax+30h]
0x180022775  xor     ecx, ecx; string
0x180022777  call    cs:__imp_WindowsDeleteString
0x18002277d  mov     [rsp+268h+string], 0
0x180022786  lea     rdx, [rsp+268h+string]
0x18002278b  mov     rcx, rdi
0x18002278e  mov     rax, rbx
0x180022791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022796  mov     ebx, eax
0x180022798  test    eax, eax
0x18002279a  jns     short loc_1800227CB
0x18002279c  mov     rcx, [rsp+268h]; this
0x1800227a4  mov     r9d, eax; char *
0x1800227a7  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800227ae  mov     edx, 2D7h; void *
0x1800227b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227b8  nop
0x1800227b9  mov     rcx, [rsp+268h+string]; string
0x1800227be  call    cs:__imp_WindowsDeleteString
0x1800227c4  mov     eax, ebx
0x1800227c6  jmp     loc_18002290C
0x1800227cb  mov     rcx, [rsp+268h+string]; string
0x1800227d0  test    rcx, rcx
0x1800227d3  jnz     short loc_180022809
0x1800227d5  mov     rcx, [rsp+268h]; this
0x1800227dd  mov     ebx, 80070057h
0x1800227e2  mov     r9d, ebx; char *
0x1800227e5  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800227ec  mov     edx, 2DCh; void *
0x1800227f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800227f6  nop
0x1800227f7  mov     rcx, [rsp+268h+string]; string
0x1800227fc  call    cs:__imp_WindowsDeleteString
0x180022802  mov     eax, ebx
0x180022804  jmp     loc_18002290C
0x180022809  xor     edx, edx; length
0x18002280b  call    cs:__imp_WindowsGetStringRawBuffer
0x180022811  mov     r9, rax
0x180022814  lea     r8, aLsdescription; "%lsDescription"
0x18002281b  mov     edx, 104h; unsigned __int64
0x180022820  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180022825  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002282a  mov     ebx, eax
0x18002282c  test    eax, eax
0x18002282e  jns     short loc_18002285F
0x180022830  mov     rcx, [rsp+268h]; this
0x180022838  mov     r9d, eax; char *
0x18002283b  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180022842  mov     edx, 2E1h; void *
0x180022847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002284c  nop
0x18002284d  mov     rcx, [rsp+268h+string]; string
0x180022852  call    cs:__imp_WindowsDeleteString
0x180022858  mov     eax, ebx
0x18002285a  jmp     loc_18002290C
0x18002285f  mov     rdx, rsi; HSTRING *
0x180022862  lea     rcx, [rsp+268h+var_228]; this
0x180022867  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18002286c  mov     ebx, eax
0x18002286e  mov     edi, 80070003h
0x180022873  cmp     eax, edi
0x180022875  jnz     short loc_1800228B3
0x180022877  xor     edx, edx; length
0x180022879  mov     rcx, [rsp+268h+string]; string
0x18002287e  call    cs:__imp_WindowsGetStringRawBuffer
0x180022884  mov     rcx, [rsp+268h]; this
0x18002288c  mov     [rsp+268h+var_240], rax; char *
0x180022891  lea     rax, aMissingDescrip; "Missing description: %ls"
0x180022898  mov     qword ptr [rsp+268h+var_248], rax; int
0x18002289d  mov     r9d, edi; char *
0x1800228a0  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800228a7  mov     edx, 2EEh; void *
0x1800228ac  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800228b1  jmp     short loc_1800228F9
0x1800228b3  test    ebx, ebx
0x1800228b5  jns     short loc_1800228F9
0x1800228b7  mov     rcx, [rsp+268h]; this
0x1800228bf  lea     rax, [rsp+268h+var_228]
0x1800228c4  mov     [rsp+268h+var_240], rax; char *
0x1800228c9  lea     rax, aLs; "%ls"
0x1800228d0  mov     qword ptr [rsp+268h+var_248], rax; int
0x1800228d5  mov     r9d, ebx; char *
0x1800228d8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1800228df  mov     edx, 2F4h; void *
0x1800228e4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800228e9  nop
0x1800228ea  mov     rcx, [rsp+268h+string]; string
0x1800228ef  call    cs:__imp_WindowsDeleteString
0x1800228f5  mov     eax, ebx
0x1800228f7  jmp     short loc_18002290C
0x1800228f9  mov     rcx, [rsp+268h+string]; string
0x1800228fe  call    cs:__imp_WindowsDeleteString
0x180022904  xor     eax, eax
0x180022906  jmp     short loc_18002290C
0x180022908  mov     eax, dword ptr [rsp+268h+string]
0x18002290c  mov     rcx, [rsp+268h+var_18]
0x180022914  xor     rcx, rsp; StackCookie
0x180022917  call    __security_check_cookie
0x18002291c  lea     r11, [rsp+268h+var_8]
0x180022924  mov     rbx, [r11+20h]
0x180022928  mov     rsi, [r11+28h]
0x18002292c  mov     rsp, r11
0x18002292f  pop     rdi
0x180022930  retn
```
