# WaasMedic::SettingsProvider::GetSettingInt(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::Setting<int> &)

- ea: `0x180021a40`
- end: `0x180021c19`
- name: `?GetSettingInt@SettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@H@2@@Z`
- size: `473`
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
- `0x180021a40`
- `0x180021ff0`
- `0x180022b20`
- `0x1800233d0`
- `0x180023cd0`
- `0x18002543c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021b95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021ba4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021b95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021ba4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::SettingsProvider::GetSettingInt(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4)
{
  unsigned int SettingUInt; // ebx
  int v8; // eax
  int SettingInt; // eax
  unsigned int v10; // r15d
  __int64 v12; // [rsp+20h] [rbp-59h]
  void **v13; // [rsp+30h] [rbp-49h] BYREF
  _OWORD v14[2]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v15[8]; // [rsp+58h] [rbp-21h] BYREF
  void **v16; // [rsp+60h] [rbp-19h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v13 = &WaasMedic::MockSettingsProvider::`vftable';
  memset(v14, 0, sizeof(v14));
  std::wstring::_Construct<1,unsigned short const *>(v14, L"System\\Medic\\Test", 17);
  SettingUInt = WaasMedic::MockSettingsProvider::GetSettingUInt(&v13, a2, a3, a4);
  if ( *(_DWORD *)(a4 + 4) == 5 )
    goto LABEL_2;
  std::wstring::~wstring(v14);
  WaasMedic::OneSettingsProvider::OneSettingsProvider((WaasMedic::OneSettingsProvider *)&v13);
  v8 = WaasMedic::OneSettingsProvider::Init((WaasMedic::OneSettingsProvider *)&v13);
  SettingUInt = v8;
  if ( v8 >= 0 )
  {
    SettingInt = WaasMedic::OneSettingsProvider::GetSettingInt((WaasMedic::OneSettingsProvider *)&v13);
    v10 = SettingInt;
    if ( SettingInt >= 0 )
    {
      SettingUInt = 0;
    }
    else
    {
      SettingUInt = -2147024894;
      if ( SettingInt != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\settingsprovider.cpp",
          (const char *)(unsigned int)SettingInt,
          v12);
        SettingUInt = v10;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\settingsprovider.cpp",
      (const char *)(unsigned int)v8,
      v12);
  }
  std::wstring::~wstring(v15);
  std::wstring::~wstring(v14);
  if ( *(_DWORD *)(a4 + 4) != 4 )
  {
    if ( a2[2] )
    {
      WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider((WaasMedic::DefaultSettingsProvider *)&v13);
      SettingUInt = WaasMedic::DefaultSettingsProvider::GetSettingInt(&v13, a2, a3, a4);
      v16 = &WaasMedic::CLock::`vftable';
      if ( *(_DWORD *)(a4 + 4) == 3 )
      {
        DeleteCriticalSection(&CriticalSection);
LABEL_2:
        std::wstring::~wstring(v14);
        goto LABEL_16;
      }
      DeleteCriticalSection(&CriticalSection);
      std::wstring::~wstring(v14);
    }
    SettingUInt &= -(*(_BYTE *)(a4 + 8) != 0);
  }
LABEL_16:
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  LODWORD(v12) = *(_DWORD *)a4;
  LogLevelW(5u, L"Setting: %s_%s; value: %d; source: %d;", a2, a3, v12, *(_DWORD *)(a4 + 4), v13);
  return SettingUInt;
}

```

## disassembly

```asm
0x180021a40  mov     [rsp-8+arg_0], rbx
0x180021a45  push    rbp
0x180021a46  push    rsi
0x180021a47  push    rdi
0x180021a48  push    r14
0x180021a4a  push    r15
0x180021a4c  lea     rbp, [rsp-37h]
0x180021a51  sub     rsp, 0B0h
0x180021a58  mov     rax, cs:__security_cookie
0x180021a5f  xor     rax, rsp
0x180021a62  mov     [rbp+57h+var_30], rax
0x180021a66  mov     rsi, r9
0x180021a69  mov     r14, r8
0x180021a6c  mov     rdi, rdx
0x180021a6f  lea     rax, ??_7MockSettingsProvider@WaasMedic@@6B@; const WaasMedic::MockSettingsProvider::`vftable'
0x180021a76  mov     [rbp+57h+var_A0], rax
0x180021a7a  xorps   xmm0, xmm0
0x180021a7d  movups  [rbp+57h+var_98], xmm0
0x180021a81  xorps   xmm1, xmm1
0x180021a84  movdqu  [rbp+57h+var_88], xmm1
0x180021a89  mov     r8d, 11h
0x180021a8f  lea     rdx, aSystemMedicTes; "System\\Medic\\Test"
0x180021a96  lea     rcx, [rbp+57h+var_98]
0x180021a9a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021a9f  nop
0x180021aa0  mov     r9, rsi
0x180021aa3  mov     r8, r14
0x180021aa6  mov     rdx, rdi
0x180021aa9  lea     rcx, [rbp+57h+var_A0]
0x180021aad  call    ?GetSettingUInt@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z; WaasMedic::MockSettingsProvider::GetSettingUInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<uint> &)
0x180021ab2  mov     ebx, eax
0x180021ab4  lea     rcx, [rbp+57h+var_98]; void *
0x180021ab8  cmp     dword ptr [rsi+4], 5
0x180021abc  jnz     short loc_180021AC8
0x180021abe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021ac3  jmp     loc_180021BBC
0x180021ac8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021acd  lea     rcx, [rbp+57h+var_A0]; this
0x180021ad1  call    ??0OneSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::OneSettingsProvider::OneSettingsProvider(void)
0x180021ad6  nop
0x180021ad7  lea     rcx, [rbp+57h+var_A0]; this
0x180021adb  call    ?Init@OneSettingsProvider@WaasMedic@@QEAAJXZ; WaasMedic::OneSettingsProvider::Init(void)
0x180021ae0  mov     ebx, eax
0x180021ae2  test    eax, eax
0x180021ae4  jns     short loc_180021B01
0x180021ae6  mov     rcx, [rbp+5Fh]; this
0x180021aea  mov     r9d, eax; char *
0x180021aed  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180021af4  mov     edx, 2Ah ; '*'; void *
0x180021af9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021afe  nop
0x180021aff  jmp     short loc_180021B43
0x180021b01  mov     r9, rsi
0x180021b04  mov     r8, r14
0x180021b07  mov     rdx, rdi
0x180021b0a  lea     rcx, [rbp+57h+var_A0]; this
0x180021b0e  call    ?GetSettingInt@OneSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@H@2@@Z; WaasMedic::OneSettingsProvider::GetSettingInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<int> &)
0x180021b13  mov     r15d, eax
0x180021b16  test    eax, eax
0x180021b18  jns     short loc_180021B41
0x180021b1a  mov     ebx, 80070002h
0x180021b1f  cmp     eax, ebx
0x180021b21  jz      short loc_180021AFF
0x180021b23  mov     rcx, [rbp+5Fh]; this
0x180021b27  mov     r9d, eax; char *
0x180021b2a  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180021b31  mov     edx, 2Bh ; '+'; void *
0x180021b36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021b3b  nop
0x180021b3c  mov     ebx, r15d
0x180021b3f  jmp     short loc_180021B43
0x180021b41  xor     ebx, ebx
0x180021b43  lea     rcx, [rbp+57h+var_78]; void *
0x180021b47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021b4c  lea     rcx, [rbp+57h+var_98]; void *
0x180021b50  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021b55  cmp     dword ptr [rsi+4], 4
0x180021b59  jz      short loc_180021BBC
0x180021b5b  cmp     qword ptr [rdi+10h], 0
0x180021b60  jz      short loc_180021BB3
0x180021b62  lea     rcx, [rbp+57h+var_A0]; this
0x180021b66  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x180021b6b  nop
0x180021b6c  mov     r9, rsi
0x180021b6f  mov     r8, r14
0x180021b72  mov     rdx, rdi
0x180021b75  lea     rcx, [rbp+57h+var_A0]
0x180021b79  call    ?GetSettingInt@DefaultSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@H@2@@Z; WaasMedic::DefaultSettingsProvider::GetSettingInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<int> &)
0x180021b7e  mov     ebx, eax
0x180021b80  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x180021b87  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180021b8b  mov     [rbp+57h+var_70], rax
0x180021b8f  cmp     dword ptr [rsi+4], 3
0x180021b93  jnz     short loc_180021BA4
0x180021b95  call    cs:__imp_DeleteCriticalSection
0x180021b9b  lea     rcx, [rbp+57h+var_98]
0x180021b9f  jmp     loc_180021ABE
0x180021ba4  call    cs:__imp_DeleteCriticalSection
0x180021baa  lea     rcx, [rbp+57h+var_98]; void *
0x180021bae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021bb3  mov     al, [rsi+8]
0x180021bb6  neg     al
0x180021bb8  sbb     ecx, ecx
0x180021bba  and     ebx, ecx
0x180021bbc  mov     eax, [rsi+4]
0x180021bbf  mov     ecx, [rsi]
0x180021bc1  cmp     qword ptr [r14+18h], 7
0x180021bc6  jbe     short loc_180021BCB
0x180021bc8  mov     r14, [r14]
0x180021bcb  cmp     qword ptr [rdi+18h], 7
0x180021bd0  jbe     short loc_180021BD5
0x180021bd2  mov     rdi, [rdi]
0x180021bd5  mov     [rsp+0D0h+var_A8], eax
0x180021bd9  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x180021bdd  mov     r9, r14
0x180021be0  mov     r8, rdi
0x180021be3  lea     rdx, aSettingSSValue_1; "Setting: %s_%s; value: %d; source: %d;"
0x180021bea  mov     ecx, 5; unsigned __int8
0x180021bef  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180021bf4  mov     eax, ebx
0x180021bf6  mov     rcx, [rbp+57h+var_30]
0x180021bfa  xor     rcx, rsp; StackCookie
0x180021bfd  call    __security_check_cookie
0x180021c02  mov     rbx, [rsp+0D0h+arg_0]
0x180021c0a  add     rsp, 0B0h
0x180021c11  pop     r15
0x180021c13  pop     r14
0x180021c15  pop     rdi
0x180021c16  pop     rsi
0x180021c17  pop     rbp
0x180021c18  retn
```
