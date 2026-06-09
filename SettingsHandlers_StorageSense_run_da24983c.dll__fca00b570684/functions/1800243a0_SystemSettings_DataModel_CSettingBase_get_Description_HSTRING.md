# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x1800243a0`
- end: `0x1800245b2`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `530`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x18000f07c`
- `0x180012374`
- `0x18001dfe8`
- `0x18001f784`
- `0x1800243a0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800243f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002443e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002447c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002456f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002457e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800243f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002443e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002447c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002456f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002457e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002448b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800244fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002448b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800244fe`

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
0x1800243a0  mov     [rsp+arg_10], rbx
0x1800243a5  mov     [rsp+arg_18], rsi
0x1800243aa  push    rdi
0x1800243ab  sub     rsp, 260h
0x1800243b2  mov     rax, cs:__security_cookie
0x1800243b9  xor     rax, rsp
0x1800243bc  mov     [rsp+268h+var_18], rax
0x1800243c4  mov     rsi, rdx
0x1800243c7  mov     rdi, rcx
0x1800243ca  mov     qword ptr [rdx], 0
0x1800243d1  mov     rax, [rcx+60h]
0x1800243d5  test    rax, rax
0x1800243d8  jz      short loc_1800243E5
0x1800243da  cmp     qword ptr [rax+20h], 0
0x1800243df  jnz     loc_180024584
0x1800243e5  mov     [rsp+268h+string], 0
0x1800243ee  mov     rax, [rcx]
0x1800243f1  mov     rbx, [rax+30h]
0x1800243f5  xor     ecx, ecx; string
0x1800243f7  call    cs:__imp_WindowsDeleteString
0x1800243fd  mov     [rsp+268h+string], 0
0x180024406  lea     rdx, [rsp+268h+string]
0x18002440b  mov     rcx, rdi
0x18002440e  mov     rax, rbx
0x180024411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024416  mov     ebx, eax
0x180024418  test    eax, eax
0x18002441a  jns     short loc_18002444B
0x18002441c  mov     rcx, [rsp+268h]; this
0x180024424  mov     r9d, eax; char *
0x180024427  lea     r8, aOnecoreuapInte_10; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002442e  mov     edx, 2D7h; void *
0x180024433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024438  nop
0x180024439  mov     rcx, [rsp+268h+string]; string
0x18002443e  call    cs:__imp_WindowsDeleteString
0x180024444  mov     eax, ebx
0x180024446  jmp     loc_18002458C
0x18002444b  mov     rcx, [rsp+268h+string]; string
0x180024450  test    rcx, rcx
0x180024453  jnz     short loc_180024489
0x180024455  mov     rcx, [rsp+268h]; this
0x18002445d  mov     ebx, 80070057h
0x180024462  mov     r9d, ebx; char *
0x180024465  lea     r8, aOnecoreuapInte_10; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002446c  mov     edx, 2DCh; void *
0x180024471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024476  nop
0x180024477  mov     rcx, [rsp+268h+string]; string
0x18002447c  call    cs:__imp_WindowsDeleteString
0x180024482  mov     eax, ebx
0x180024484  jmp     loc_18002458C
0x180024489  xor     edx, edx; length
0x18002448b  call    cs:__imp_WindowsGetStringRawBuffer
0x180024491  mov     r9, rax
0x180024494  lea     r8, aLsdescription; "%lsDescription"
0x18002449b  mov     edx, 104h; unsigned __int64
0x1800244a0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800244a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800244aa  mov     ebx, eax
0x1800244ac  test    eax, eax
0x1800244ae  jns     short loc_1800244DF
0x1800244b0  mov     rcx, [rsp+268h]; this
0x1800244b8  mov     r9d, eax; char *
0x1800244bb  lea     r8, aOnecoreuapInte_10; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x1800244c2  mov     edx, 2E1h; void *
0x1800244c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800244cc  nop
0x1800244cd  mov     rcx, [rsp+268h+string]; string
0x1800244d2  call    cs:__imp_WindowsDeleteString
0x1800244d8  mov     eax, ebx
0x1800244da  jmp     loc_18002458C
0x1800244df  mov     rdx, rsi; HSTRING *
0x1800244e2  lea     rcx, [rsp+268h+var_228]; this
0x1800244e7  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1800244ec  mov     ebx, eax
0x1800244ee  mov     edi, 80070003h
0x1800244f3  cmp     eax, edi
0x1800244f5  jnz     short loc_180024533
0x1800244f7  xor     edx, edx; length
0x1800244f9  mov     rcx, [rsp+268h+string]; string
0x1800244fe  call    cs:__imp_WindowsGetStringRawBuffer
0x180024504  mov     rcx, [rsp+268h]; this
0x18002450c  mov     [rsp+268h+var_240], rax; char *
0x180024511  lea     rax, aMissingDescrip; "Missing description: %ls"
0x180024518  mov     qword ptr [rsp+268h+var_248], rax; int
0x18002451d  mov     r9d, edi; char *
0x180024520  lea     r8, aOnecoreuapInte_10; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x180024527  mov     edx, 2EEh; void *
0x18002452c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024531  jmp     short loc_180024579
0x180024533  test    ebx, ebx
0x180024535  jns     short loc_180024579
0x180024537  mov     rcx, [rsp+268h]; this
0x18002453f  lea     rax, [rsp+268h+var_228]
0x180024544  mov     [rsp+268h+var_240], rax; char *
0x180024549  lea     rax, aLs; "%ls"
0x180024550  mov     qword ptr [rsp+268h+var_248], rax; int
0x180024555  mov     r9d, ebx; char *
0x180024558  lea     r8, aOnecoreuapInte_10; "OnecoreUAP\\internal\\Shell\\inc\\Setti"...
0x18002455f  mov     edx, 2F4h; void *
0x180024564  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024569  nop
0x18002456a  mov     rcx, [rsp+268h+string]; string
0x18002456f  call    cs:__imp_WindowsDeleteString
0x180024575  mov     eax, ebx
0x180024577  jmp     short loc_18002458C
0x180024579  mov     rcx, [rsp+268h+string]; string
0x18002457e  call    cs:__imp_WindowsDeleteString
0x180024584  xor     eax, eax
0x180024586  jmp     short loc_18002458C
0x180024588  mov     eax, dword ptr [rsp+268h+string]
0x18002458c  mov     rcx, [rsp+268h+var_18]
0x180024594  xor     rcx, rsp; StackCookie
0x180024597  call    __security_check_cookie
0x18002459c  lea     r11, [rsp+268h+var_8]
0x1800245a4  mov     rbx, [r11+20h]
0x1800245a8  mov     rsi, [r11+28h]
0x1800245ac  mov     rsp, r11
0x1800245af  pop     rdi
0x1800245b0  retn
```
