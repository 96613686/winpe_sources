# SystemSettings::DataModel::CSettingBase::get_Description(HSTRING__ * *)

- ea: `0x1800117d0`
- end: `0x1800119e2`
- name: `?get_Description@CSettingBase@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `530`
- prototype: `int(SystemSettings::DataModel::CSettingBase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x1800028d0`
- `0x18000a13c`
- `0x18000a160`
- `0x18000a8fc`
- `0x18000f1f8`
- `0x18000fb0c`
- `0x1800117d0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001186e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800118ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001199f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800119ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001186e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800118ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001199f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800119ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800118bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001192e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800118bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001192e`

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
          (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
          (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
          (const char *)0x80070003LL,
          (int)"Missing description: %ls",
          v16);
      }
      else if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x2F4,
          (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
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
                           (unsigned int)"OneCoreUap\\Internal\\Shell\\inc\\SettingHandlersBaseCore.h",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x1800117d0  mov     [rsp+arg_10], rbx
0x1800117d5  mov     [rsp+arg_18], rsi
0x1800117da  push    rdi
0x1800117db  sub     rsp, 260h
0x1800117e2  mov     rax, cs:__security_cookie
0x1800117e9  xor     rax, rsp
0x1800117ec  mov     [rsp+268h+var_18], rax
0x1800117f4  mov     rsi, rdx
0x1800117f7  mov     rdi, rcx
0x1800117fa  mov     qword ptr [rdx], 0
0x180011801  mov     rax, [rcx+60h]
0x180011805  test    rax, rax
0x180011808  jz      short loc_180011815
0x18001180a  cmp     qword ptr [rax+20h], 0
0x18001180f  jnz     loc_1800119B4
0x180011815  mov     [rsp+268h+string], 0
0x18001181e  mov     rax, [rcx]
0x180011821  mov     rbx, [rax+30h]
0x180011825  xor     ecx, ecx; string
0x180011827  call    cs:__imp_WindowsDeleteString
0x18001182d  mov     [rsp+268h+string], 0
0x180011836  lea     rdx, [rsp+268h+string]
0x18001183b  mov     rcx, rdi
0x18001183e  mov     rax, rbx
0x180011841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011846  mov     ebx, eax
0x180011848  test    eax, eax
0x18001184a  jns     short loc_18001187B
0x18001184c  mov     rcx, [rsp+268h]; this
0x180011854  mov     r9d, eax; char *
0x180011857  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18001185e  mov     edx, 2D7h; void *
0x180011863  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011868  nop
0x180011869  mov     rcx, [rsp+268h+string]; string
0x18001186e  call    cs:__imp_WindowsDeleteString
0x180011874  mov     eax, ebx
0x180011876  jmp     loc_1800119BC
0x18001187b  mov     rcx, [rsp+268h+string]; string
0x180011880  test    rcx, rcx
0x180011883  jnz     short loc_1800118B9
0x180011885  mov     rcx, [rsp+268h]; this
0x18001188d  mov     ebx, 80070057h
0x180011892  mov     r9d, ebx; char *
0x180011895  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18001189c  mov     edx, 2DCh; void *
0x1800118a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118a6  nop
0x1800118a7  mov     rcx, [rsp+268h+string]; string
0x1800118ac  call    cs:__imp_WindowsDeleteString
0x1800118b2  mov     eax, ebx
0x1800118b4  jmp     loc_1800119BC
0x1800118b9  xor     edx, edx; length
0x1800118bb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800118c1  mov     r9, rax
0x1800118c4  lea     r8, aLsdescription; "%lsDescription"
0x1800118cb  mov     edx, 104h; unsigned __int64
0x1800118d0  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800118d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800118da  mov     ebx, eax
0x1800118dc  test    eax, eax
0x1800118de  jns     short loc_18001190F
0x1800118e0  mov     rcx, [rsp+268h]; this
0x1800118e8  mov     r9d, eax; char *
0x1800118eb  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x1800118f2  mov     edx, 2E1h; void *
0x1800118f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118fc  nop
0x1800118fd  mov     rcx, [rsp+268h+string]; string
0x180011902  call    cs:__imp_WindowsDeleteString
0x180011908  mov     eax, ebx
0x18001190a  jmp     loc_1800119BC
0x18001190f  mov     rdx, rsi; HSTRING *
0x180011912  lea     rcx, [rsp+268h+var_228]; this
0x180011917  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18001191c  mov     ebx, eax
0x18001191e  mov     edi, 80070003h
0x180011923  cmp     eax, edi
0x180011925  jnz     short loc_180011963
0x180011927  xor     edx, edx; length
0x180011929  mov     rcx, [rsp+268h+string]; string
0x18001192e  call    cs:__imp_WindowsGetStringRawBuffer
0x180011934  mov     rcx, [rsp+268h]; this
0x18001193c  mov     [rsp+268h+var_240], rax; char *
0x180011941  lea     rax, aMissingDescrip; "Missing description: %ls"
0x180011948  mov     qword ptr [rsp+268h+var_248], rax; int
0x18001194d  mov     r9d, edi; char *
0x180011950  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x180011957  mov     edx, 2EEh; void *
0x18001195c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180011961  jmp     short loc_1800119A9
0x180011963  test    ebx, ebx
0x180011965  jns     short loc_1800119A9
0x180011967  mov     rcx, [rsp+268h]; this
0x18001196f  lea     rax, [rsp+268h+var_228]
0x180011974  mov     [rsp+268h+var_240], rax; char *
0x180011979  lea     rax, aLs; "%ls"
0x180011980  mov     qword ptr [rsp+268h+var_248], rax; int
0x180011985  mov     r9d, ebx; char *
0x180011988  lea     r8, aOnecoreuapInte; "OneCoreUap\\Internal\\Shell\\inc\\Setti"...
0x18001198f  mov     edx, 2F4h; void *
0x180011994  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180011999  nop
0x18001199a  mov     rcx, [rsp+268h+string]; string
0x18001199f  call    cs:__imp_WindowsDeleteString
0x1800119a5  mov     eax, ebx
0x1800119a7  jmp     short loc_1800119BC
0x1800119a9  mov     rcx, [rsp+268h+string]; string
0x1800119ae  call    cs:__imp_WindowsDeleteString
0x1800119b4  xor     eax, eax
0x1800119b6  jmp     short loc_1800119BC
0x1800119b8  mov     eax, dword ptr [rsp+268h+string]
0x1800119bc  mov     rcx, [rsp+268h+var_18]
0x1800119c4  xor     rcx, rsp; StackCookie
0x1800119c7  call    __security_check_cookie
0x1800119cc  lea     r11, [rsp+268h+var_8]
0x1800119d4  mov     rbx, [r11+20h]
0x1800119d8  mov     rsi, [r11+28h]
0x1800119dc  mov     rsp, r11
0x1800119df  pop     rdi
0x1800119e0  retn
```
