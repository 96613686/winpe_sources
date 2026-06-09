# WaasMedic::SettingsProvider::GetSettingString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::Setting<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &)

- ea: `0x180021c20`
- end: `0x180021e02`
- name: `?GetSettingString@SettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x1800216a4`
- `0x18002171c`
- `0x180021c20`
- `0x180021ff0`
- `0x180022d20`
- `0x1800234e0`
- `0x180023e50`
- `0x18002543c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021d75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021d84`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021d75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021d84`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::SettingsProvider::GetSettingString(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 *a4)
{
  unsigned int SettingString; // ebx
  int v8; // eax
  int v9; // eax
  unsigned int v10; // r15d
  int v11; // eax
  int v13; // [rsp+20h] [rbp-59h]
  void **v14; // [rsp+30h] [rbp-49h] BYREF
  _OWORD v15[2]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v16[8]; // [rsp+58h] [rbp-21h] BYREF
  void **v17; // [rsp+60h] [rbp-19h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v14 = &WaasMedic::MockSettingsProvider::`vftable';
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,unsigned short const *>(v15, L"System\\Medic\\Test", 17);
  SettingString = WaasMedic::MockSettingsProvider::GetSettingString(&v14, a2, a3, a4);
  if ( *((_DWORD *)a4 + 8) == 5 )
    goto LABEL_2;
  std::wstring::~wstring(v15);
  WaasMedic::OneSettingsProvider::OneSettingsProvider((WaasMedic::OneSettingsProvider *)&v14);
  v8 = WaasMedic::OneSettingsProvider::Init((WaasMedic::OneSettingsProvider *)&v14);
  SettingString = v8;
  if ( v8 >= 0 )
  {
    v9 = WaasMedic::OneSettingsProvider::GetSettingString((WaasMedic::OneSettingsProvider *)&v14);
    v10 = v9;
    if ( v9 >= 0 )
    {
      SettingString = 0;
    }
    else
    {
      SettingString = -2147024894;
      if ( v9 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\settingsprovider.cpp",
          (const char *)(unsigned int)v9,
          v13);
        SettingString = v10;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\settingsprovider.cpp",
      (const char *)(unsigned int)v8,
      v13);
  }
  std::wstring::~wstring(v16);
  std::wstring::~wstring(v15);
  if ( *((_DWORD *)a4 + 8) != 4 )
  {
    if ( a2[2] )
    {
      WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider((WaasMedic::DefaultSettingsProvider *)&v14);
      SettingString = WaasMedic::DefaultSettingsProvider::GetSettingString(&v14, a2, a3, a4);
      v17 = &WaasMedic::CLock::`vftable';
      if ( *((_DWORD *)a4 + 8) == 3 )
      {
        DeleteCriticalSection(&CriticalSection);
LABEL_2:
        std::wstring::~wstring(v15);
        goto LABEL_16;
      }
      DeleteCriticalSection(&CriticalSection);
      std::wstring::~wstring(v15);
    }
    SettingString &= -(*((_BYTE *)a4 + 36) != 0);
  }
LABEL_16:
  v11 = *((_DWORD *)a4 + 8);
  if ( (unsigned __int64)a4[3] > 7 )
    a4 = (__int64 *)*a4;
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  LogLevelW(5u, L"Setting: %s_%s; value: '%s'; source: %d", a2, a3, a4, v11, v14);
  return SettingString;
}

```

## disassembly

```asm
0x180021c20  mov     [rsp-8+arg_0], rbx
0x180021c25  push    rbp
0x180021c26  push    rsi
0x180021c27  push    rdi
0x180021c28  push    r14
0x180021c2a  push    r15
0x180021c2c  lea     rbp, [rsp-37h]
0x180021c31  sub     rsp, 0B0h
0x180021c38  mov     rax, cs:__security_cookie
0x180021c3f  xor     rax, rsp
0x180021c42  mov     [rbp+57h+var_30], rax
0x180021c46  mov     rdi, r9
0x180021c49  mov     r14, r8
0x180021c4c  mov     rsi, rdx
0x180021c4f  lea     rax, ??_7MockSettingsProvider@WaasMedic@@6B@; const WaasMedic::MockSettingsProvider::`vftable'
0x180021c56  mov     [rbp+57h+var_A0], rax
0x180021c5a  xorps   xmm0, xmm0
0x180021c5d  movups  [rbp+57h+var_98], xmm0
0x180021c61  xorps   xmm1, xmm1
0x180021c64  movdqu  [rbp+57h+var_88], xmm1
0x180021c69  mov     r8d, 11h
0x180021c6f  lea     rdx, aSystemMedicTes; "System\\Medic\\Test"
0x180021c76  lea     rcx, [rbp+57h+var_98]
0x180021c7a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021c7f  nop
0x180021c80  mov     r9, rdi
0x180021c83  mov     r8, r14
0x180021c86  mov     rdx, rsi
0x180021c89  lea     rcx, [rbp+57h+var_A0]
0x180021c8d  call    ?GetSettingString@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z; WaasMedic::MockSettingsProvider::GetSettingString(std::wstring const &,std::wstring const &,WaasMedic::Setting<std::wstring> &)
0x180021c92  mov     ebx, eax
0x180021c94  lea     rcx, [rbp+57h+var_98]; void *
0x180021c98  cmp     dword ptr [rdi+20h], 5
0x180021c9c  jnz     short loc_180021CA8
0x180021c9e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021ca3  jmp     loc_180021D9C
0x180021ca8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021cad  lea     rcx, [rbp+57h+var_A0]; this
0x180021cb1  call    ??0OneSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::OneSettingsProvider::OneSettingsProvider(void)
0x180021cb6  nop
0x180021cb7  lea     rcx, [rbp+57h+var_A0]; this
0x180021cbb  call    ?Init@OneSettingsProvider@WaasMedic@@QEAAJXZ; WaasMedic::OneSettingsProvider::Init(void)
0x180021cc0  mov     ebx, eax
0x180021cc2  test    eax, eax
0x180021cc4  jns     short loc_180021CE1
0x180021cc6  mov     rcx, [rbp+5Fh]; this
0x180021cca  mov     r9d, eax; char *
0x180021ccd  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180021cd4  mov     edx, 0A8h; void *
0x180021cd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021cde  nop
0x180021cdf  jmp     short loc_180021D23
0x180021ce1  mov     r9, rdi
0x180021ce4  mov     r8, r14
0x180021ce7  mov     rdx, rsi
0x180021cea  lea     rcx, [rbp+57h+var_A0]; this
0x180021cee  call    ?GetSettingString@OneSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z; WaasMedic::OneSettingsProvider::GetSettingString(std::wstring const &,std::wstring const &,WaasMedic::Setting<std::wstring> &)
0x180021cf3  mov     r15d, eax
0x180021cf6  test    eax, eax
0x180021cf8  jns     short loc_180021D21
0x180021cfa  mov     ebx, 80070002h
0x180021cff  cmp     eax, ebx
0x180021d01  jz      short loc_180021CDF
0x180021d03  mov     rcx, [rbp+5Fh]; this
0x180021d07  mov     r9d, eax; char *
0x180021d0a  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180021d11  mov     edx, 0A9h; void *
0x180021d16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021d1b  nop
0x180021d1c  mov     ebx, r15d
0x180021d1f  jmp     short loc_180021D23
0x180021d21  xor     ebx, ebx
0x180021d23  lea     rcx, [rbp+57h+var_78]; void *
0x180021d27  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021d2c  lea     rcx, [rbp+57h+var_98]; void *
0x180021d30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021d35  cmp     dword ptr [rdi+20h], 4
0x180021d39  jz      short loc_180021D9C
0x180021d3b  cmp     qword ptr [rsi+10h], 0
0x180021d40  jz      short loc_180021D93
0x180021d42  lea     rcx, [rbp+57h+var_A0]; this
0x180021d46  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x180021d4b  nop
0x180021d4c  mov     r9, rdi
0x180021d4f  mov     r8, r14
0x180021d52  mov     rdx, rsi
0x180021d55  lea     rcx, [rbp+57h+var_A0]
0x180021d59  call    ?GetSettingString@DefaultSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z; WaasMedic::DefaultSettingsProvider::GetSettingString(std::wstring const &,std::wstring const &,WaasMedic::Setting<std::wstring> &)
0x180021d5e  mov     ebx, eax
0x180021d60  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x180021d67  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180021d6b  mov     [rbp+57h+var_70], rax
0x180021d6f  cmp     dword ptr [rdi+20h], 3
0x180021d73  jnz     short loc_180021D84
0x180021d75  call    cs:__imp_DeleteCriticalSection
0x180021d7b  lea     rcx, [rbp+57h+var_98]
0x180021d7f  jmp     loc_180021C9E
0x180021d84  call    cs:__imp_DeleteCriticalSection
0x180021d8a  lea     rcx, [rbp+57h+var_98]; void *
0x180021d8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021d93  mov     al, [rdi+24h]
0x180021d96  neg     al
0x180021d98  sbb     ecx, ecx
0x180021d9a  and     ebx, ecx
0x180021d9c  mov     eax, [rdi+20h]
0x180021d9f  cmp     qword ptr [rdi+18h], 7
0x180021da4  jbe     short loc_180021DA9
0x180021da6  mov     rdi, [rdi]
0x180021da9  cmp     qword ptr [r14+18h], 7
0x180021dae  jbe     short loc_180021DB3
0x180021db0  mov     r14, [r14]
0x180021db3  cmp     qword ptr [rsi+18h], 7
0x180021db8  jbe     short loc_180021DBD
0x180021dba  mov     rsi, [rsi]
0x180021dbd  mov     [rsp+0D0h+var_A8], eax
0x180021dc1  mov     [rsp+0D0h+var_B0], rdi
0x180021dc6  mov     r9, r14
0x180021dc9  mov     r8, rsi
0x180021dcc  lea     rdx, aSettingSSValue_0; "Setting: %s_%s; value: '%s'; source: %d"
0x180021dd3  mov     ecx, 5; unsigned __int8
0x180021dd8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180021ddd  mov     eax, ebx
0x180021ddf  mov     rcx, [rbp+57h+var_30]
0x180021de3  xor     rcx, rsp; StackCookie
0x180021de6  call    __security_check_cookie
0x180021deb  mov     rbx, [rsp+0D0h+arg_0]
0x180021df3  add     rsp, 0B0h
0x180021dfa  pop     r15
0x180021dfc  pop     r14
0x180021dfe  pop     rdi
0x180021dff  pop     rsi
0x180021e00  pop     rbp
0x180021e01  retn
```
