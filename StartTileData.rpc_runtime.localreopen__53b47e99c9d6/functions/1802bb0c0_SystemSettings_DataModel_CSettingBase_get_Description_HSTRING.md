# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x1802bb0c0`
- end: `0x1802bb2d2`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `530`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x18001aca4`
- `0x180057570`
- `0x180161028`
- `0x180170b2c`
- `0x180201e50`
- `0x1802b1340`
- `0x1802bb0c0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb19c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb28f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb19c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb1f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb28f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802bb29e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802bb1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802bb21e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802bb1ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802bb21e`

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
0x1802bb0c0  mov     [rsp+arg_10], rbx
0x1802bb0c5  mov     [rsp+arg_18], rsi
0x1802bb0ca  push    rdi
0x1802bb0cb  sub     rsp, 260h
0x1802bb0d2  mov     rax, cs:__security_cookie
0x1802bb0d9  xor     rax, rsp
0x1802bb0dc  mov     [rsp+268h+var_18], rax
0x1802bb0e4  mov     rsi, rdx
0x1802bb0e7  mov     rdi, rcx
0x1802bb0ea  mov     qword ptr [rdx], 0
0x1802bb0f1  mov     rax, [rcx+60h]
0x1802bb0f5  test    rax, rax
0x1802bb0f8  jz      short loc_1802BB105
0x1802bb0fa  cmp     qword ptr [rax+20h], 0
0x1802bb0ff  jnz     loc_1802BB2A4
0x1802bb105  mov     [rsp+268h+string], 0
0x1802bb10e  mov     rax, [rcx]
0x1802bb111  mov     rbx, [rax+30h]
0x1802bb115  xor     ecx, ecx; string
0x1802bb117  call    cs:__imp_WindowsDeleteString
0x1802bb11d  mov     [rsp+268h+string], 0
0x1802bb126  lea     rdx, [rsp+268h+string]
0x1802bb12b  mov     rcx, rdi
0x1802bb12e  mov     rax, rbx
0x1802bb131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802bb136  mov     ebx, eax
0x1802bb138  test    eax, eax
0x1802bb13a  jns     short loc_1802BB16B
0x1802bb13c  mov     rcx, [rsp+268h]; this
0x1802bb144  mov     r9d, eax; char *
0x1802bb147  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1802bb14e  mov     edx, 2D7h; void *
0x1802bb153  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802bb158  nop
0x1802bb159  mov     rcx, [rsp+268h+string]; string
0x1802bb15e  call    cs:__imp_WindowsDeleteString
0x1802bb164  mov     eax, ebx
0x1802bb166  jmp     loc_1802BB2AC
0x1802bb16b  mov     rcx, [rsp+268h+string]; string
0x1802bb170  test    rcx, rcx
0x1802bb173  jnz     short loc_1802BB1A9
0x1802bb175  mov     rcx, [rsp+268h]; this
0x1802bb17d  mov     ebx, 80070057h
0x1802bb182  mov     r9d, ebx; char *
0x1802bb185  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1802bb18c  mov     edx, 2DCh; void *
0x1802bb191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802bb196  nop
0x1802bb197  mov     rcx, [rsp+268h+string]; string
0x1802bb19c  call    cs:__imp_WindowsDeleteString
0x1802bb1a2  mov     eax, ebx
0x1802bb1a4  jmp     loc_1802BB2AC
0x1802bb1a9  xor     edx, edx; length
0x1802bb1ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1802bb1b1  mov     r9, rax
0x1802bb1b4  lea     r8, aLsdescription; "%lsDescription"
0x1802bb1bb  mov     edx, 104h; unsigned __int64
0x1802bb1c0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1802bb1c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802bb1ca  mov     ebx, eax
0x1802bb1cc  test    eax, eax
0x1802bb1ce  jns     short loc_1802BB1FF
0x1802bb1d0  mov     rcx, [rsp+268h]; this
0x1802bb1d8  mov     r9d, eax; char *
0x1802bb1db  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1802bb1e2  mov     edx, 2E1h; void *
0x1802bb1e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802bb1ec  nop
0x1802bb1ed  mov     rcx, [rsp+268h+string]; string
0x1802bb1f2  call    cs:__imp_WindowsDeleteString
0x1802bb1f8  mov     eax, ebx
0x1802bb1fa  jmp     loc_1802BB2AC
0x1802bb1ff  mov     rdx, rsi; HSTRING *
0x1802bb202  lea     rcx, [rsp+268h+var_228]; this
0x1802bb207  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1802bb20c  mov     ebx, eax
0x1802bb20e  mov     edi, 80070003h
0x1802bb213  cmp     eax, edi
0x1802bb215  jnz     short loc_1802BB253
0x1802bb217  xor     edx, edx; length
0x1802bb219  mov     rcx, [rsp+268h+string]; string
0x1802bb21e  call    cs:__imp_WindowsGetStringRawBuffer
0x1802bb224  mov     rcx, [rsp+268h]; this
0x1802bb22c  mov     [rsp+268h+var_240], rax; char *
0x1802bb231  lea     rax, aMissingDescrip; "Missing description: %ls"
0x1802bb238  mov     qword ptr [rsp+268h+var_248], rax; int
0x1802bb23d  mov     r9d, edi; char *
0x1802bb240  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1802bb247  mov     edx, 2EEh; void *
0x1802bb24c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1802bb251  jmp     short loc_1802BB299
0x1802bb253  test    ebx, ebx
0x1802bb255  jns     short loc_1802BB299
0x1802bb257  mov     rcx, [rsp+268h]; this
0x1802bb25f  lea     rax, [rsp+268h+var_228]
0x1802bb264  mov     [rsp+268h+var_240], rax; char *
0x1802bb269  lea     rax, aLs; "%ls"
0x1802bb270  mov     qword ptr [rsp+268h+var_248], rax; int
0x1802bb275  mov     r9d, ebx; char *
0x1802bb278  lea     r8, aOnecoreuapInte_6; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x1802bb27f  mov     edx, 2F4h; void *
0x1802bb284  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1802bb289  nop
0x1802bb28a  mov     rcx, [rsp+268h+string]; string
0x1802bb28f  call    cs:__imp_WindowsDeleteString
0x1802bb295  mov     eax, ebx
0x1802bb297  jmp     short loc_1802BB2AC
0x1802bb299  mov     rcx, [rsp+268h+string]; string
0x1802bb29e  call    cs:__imp_WindowsDeleteString
0x1802bb2a4  xor     eax, eax
0x1802bb2a6  jmp     short loc_1802BB2AC
0x1802bb2a8  mov     eax, dword ptr [rsp+268h+string]
0x1802bb2ac  mov     rcx, [rsp+268h+var_18]
0x1802bb2b4  xor     rcx, rsp; StackCookie
0x1802bb2b7  call    __security_check_cookie
0x1802bb2bc  lea     r11, [rsp+268h+var_8]
0x1802bb2c4  mov     rbx, [r11+20h]
0x1802bb2c8  mov     rsi, [r11+28h]
0x1802bb2cc  mov     rsp, r11
0x1802bb2cf  pop     rdi
0x1802bb2d0  retn
```
