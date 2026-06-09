# WaasMedic::SettingsProvider::GetSettingUInt(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::Setting<uint> &)

- ea: `0x180023a50`
- end: `0x180023c29`
- name: `?GetSettingUInt@SettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z`
- size: `473`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18000f954`
- `0x1800222c0`
- `0x18002339c`
- `0x180023a50`
- `0x180023c30`
- `0x180023f40`
- `0x180024a10`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023ba5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023bb4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023ba5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023bb4`

## pseudocode

```c
__int64 __fastcall WaasMedic::SettingsProvider::GetSettingUInt(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4)
{
  unsigned int SettingUInt; // ebx
  int v8; // eax
  int v9; // eax
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
    v9 = WaasMedic::OneSettingsProvider::GetSettingUInt((WaasMedic::OneSettingsProvider *)&v13);
    v10 = v9;
    if ( v9 >= 0 )
    {
      SettingUInt = 0;
    }
    else
    {
      SettingUInt = -2147024894;
      if ( v9 != -2147024894 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\settingsprovider.cpp",
          (const char *)(unsigned int)v9,
          v12);
        SettingUInt = v10;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
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
      SettingUInt = WaasMedic::DefaultSettingsProvider::GetSettingUInt(&v13, a2, a3, a4);
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
  LogLevelW(5u, L"Setting: %s_%s; value: %d; source: %d", a2, a3, v12, *(_DWORD *)(a4 + 4), v13);
  return SettingUInt;
}

```

## disassembly

```asm
0x180023a50  mov     [rsp-8+arg_0], rbx
0x180023a55  push    rbp
0x180023a56  push    rsi
0x180023a57  push    rdi
0x180023a58  push    r14
0x180023a5a  push    r15
0x180023a5c  lea     rbp, [rsp-37h]
0x180023a61  sub     rsp, 0B0h
0x180023a68  mov     rax, cs:__security_cookie
0x180023a6f  xor     rax, rsp
0x180023a72  mov     [rbp+57h+var_30], rax
0x180023a76  mov     rsi, r9
0x180023a79  mov     r14, r8
0x180023a7c  mov     rdi, rdx
0x180023a7f  lea     rax, ??_7MockSettingsProvider@WaasMedic@@6B@; const WaasMedic::MockSettingsProvider::`vftable'
0x180023a86  mov     [rbp+57h+var_A0], rax
0x180023a8a  xorps   xmm0, xmm0
0x180023a8d  movups  [rbp+57h+var_98], xmm0
0x180023a91  xorps   xmm1, xmm1
0x180023a94  movdqu  [rbp+57h+var_88], xmm1
0x180023a99  mov     r8d, 11h
0x180023a9f  lea     rdx, aSystemMedicTes; "System\\Medic\\Test"
0x180023aa6  lea     rcx, [rbp+57h+var_98]
0x180023aaa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023aaf  nop
0x180023ab0  mov     r9, rsi
0x180023ab3  mov     r8, r14
0x180023ab6  mov     rdx, rdi
0x180023ab9  lea     rcx, [rbp+57h+var_A0]
0x180023abd  call    ?GetSettingUInt@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z; WaasMedic::MockSettingsProvider::GetSettingUInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<uint> &)
0x180023ac2  mov     ebx, eax
0x180023ac4  lea     rcx, [rbp+57h+var_98]; void *
0x180023ac8  cmp     dword ptr [rsi+4], 5
0x180023acc  jnz     short loc_180023AD8
0x180023ace  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023ad3  jmp     loc_180023BCC
0x180023ad8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023add  lea     rcx, [rbp+57h+var_A0]; this
0x180023ae1  call    ??0OneSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::OneSettingsProvider::OneSettingsProvider(void)
0x180023ae6  nop
0x180023ae7  lea     rcx, [rbp+57h+var_A0]; this
0x180023aeb  call    ?Init@OneSettingsProvider@WaasMedic@@QEAAJXZ; WaasMedic::OneSettingsProvider::Init(void)
0x180023af0  mov     ebx, eax
0x180023af2  test    eax, eax
0x180023af4  jns     short loc_180023B11
0x180023af6  mov     rcx, [rbp+5Fh]; this
0x180023afa  mov     r9d, eax; char *
0x180023afd  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180023b04  mov     edx, 69h ; 'i'; void *
0x180023b09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b0e  nop
0x180023b0f  jmp     short loc_180023B53
0x180023b11  mov     r9, rsi
0x180023b14  mov     r8, r14
0x180023b17  mov     rdx, rdi
0x180023b1a  lea     rcx, [rbp+57h+var_A0]; this
0x180023b1e  call    ?GetSettingUInt@OneSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z; WaasMedic::OneSettingsProvider::GetSettingUInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<uint> &)
0x180023b23  mov     r15d, eax
0x180023b26  test    eax, eax
0x180023b28  jns     short loc_180023B51
0x180023b2a  mov     ebx, 80070002h
0x180023b2f  cmp     eax, ebx
0x180023b31  jz      short loc_180023B0F
0x180023b33  mov     rcx, [rbp+5Fh]; this
0x180023b37  mov     r9d, eax; char *
0x180023b3a  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180023b41  mov     edx, 6Ah ; 'j'; void *
0x180023b46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b4b  nop
0x180023b4c  mov     ebx, r15d
0x180023b4f  jmp     short loc_180023B53
0x180023b51  xor     ebx, ebx
0x180023b53  lea     rcx, [rbp+57h+var_78]; void *
0x180023b57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b5c  lea     rcx, [rbp+57h+var_98]; void *
0x180023b60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b65  cmp     dword ptr [rsi+4], 4
0x180023b69  jz      short loc_180023BCC
0x180023b6b  cmp     qword ptr [rdi+10h], 0
0x180023b70  jz      short loc_180023BC3
0x180023b72  lea     rcx, [rbp+57h+var_A0]; this
0x180023b76  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x180023b7b  nop
0x180023b7c  mov     r9, rsi
0x180023b7f  mov     r8, r14
0x180023b82  mov     rdx, rdi
0x180023b85  lea     rcx, [rbp+57h+var_A0]
0x180023b89  call    ?GetSettingUInt@DefaultSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z; WaasMedic::DefaultSettingsProvider::GetSettingUInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<uint> &)
0x180023b8e  mov     ebx, eax
0x180023b90  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x180023b97  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180023b9b  mov     [rbp+57h+var_70], rax
0x180023b9f  cmp     dword ptr [rsi+4], 3
0x180023ba3  jnz     short loc_180023BB4
0x180023ba5  call    cs:__imp_DeleteCriticalSection
0x180023bab  lea     rcx, [rbp+57h+var_98]
0x180023baf  jmp     loc_180023ACE
0x180023bb4  call    cs:__imp_DeleteCriticalSection
0x180023bba  lea     rcx, [rbp+57h+var_98]; void *
0x180023bbe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023bc3  mov     al, [rsi+8]
0x180023bc6  neg     al
0x180023bc8  sbb     ecx, ecx
0x180023bca  and     ebx, ecx
0x180023bcc  mov     eax, [rsi+4]
0x180023bcf  mov     ecx, [rsi]
0x180023bd1  cmp     qword ptr [r14+18h], 7
0x180023bd6  jbe     short loc_180023BDB
0x180023bd8  mov     r14, [r14]
0x180023bdb  cmp     qword ptr [rdi+18h], 7
0x180023be0  jbe     short loc_180023BE5
0x180023be2  mov     rdi, [rdi]
0x180023be5  mov     [rsp+0D0h+var_A8], eax
0x180023be9  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x180023bed  mov     r9, r14
0x180023bf0  mov     r8, rdi
0x180023bf3  lea     rdx, aSettingSSValue; "Setting: %s_%s; value: %d; source: %d"
0x180023bfa  mov     ecx, 5; unsigned __int8
0x180023bff  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180023c04  mov     eax, ebx
0x180023c06  mov     rcx, [rbp+57h+var_30]
0x180023c0a  xor     rcx, rsp; StackCookie
0x180023c0d  call    __security_check_cookie
0x180023c12  mov     rbx, [rsp+0D0h+arg_0]
0x180023c1a  add     rsp, 0B0h
0x180023c21  pop     r15
0x180023c23  pop     r14
0x180023c25  pop     rdi
0x180023c26  pop     rsi
0x180023c27  pop     rbp
0x180023c28  retn
```
