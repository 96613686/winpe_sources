# WaasMedic::SettingsProvider::GetSettingUInt(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::Setting<uint> &)

- ea: `0x180021e10`
- end: `0x180021fe9`
- name: `?GetSettingUInt@SettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z`
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
- `0x180021e10`
- `0x180021ff0`
- `0x180022e80`
- `0x1800233d0`
- `0x180024080`
- `0x18002543c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021f65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021f74`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021f65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021f74`

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
0x180021e10  mov     [rsp-8+arg_0], rbx
0x180021e15  push    rbp
0x180021e16  push    rsi
0x180021e17  push    rdi
0x180021e18  push    r14
0x180021e1a  push    r15
0x180021e1c  lea     rbp, [rsp-37h]
0x180021e21  sub     rsp, 0B0h
0x180021e28  mov     rax, cs:__security_cookie
0x180021e2f  xor     rax, rsp
0x180021e32  mov     [rbp+57h+var_30], rax
0x180021e36  mov     rsi, r9
0x180021e39  mov     r14, r8
0x180021e3c  mov     rdi, rdx
0x180021e3f  lea     rax, ??_7MockSettingsProvider@WaasMedic@@6B@; const WaasMedic::MockSettingsProvider::`vftable'
0x180021e46  mov     [rbp+57h+var_A0], rax
0x180021e4a  xorps   xmm0, xmm0
0x180021e4d  movups  [rbp+57h+var_98], xmm0
0x180021e51  xorps   xmm1, xmm1
0x180021e54  movdqu  [rbp+57h+var_88], xmm1
0x180021e59  mov     r8d, 11h
0x180021e5f  lea     rdx, aSystemMedicTes; "System\\Medic\\Test"
0x180021e66  lea     rcx, [rbp+57h+var_98]
0x180021e6a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021e6f  nop
0x180021e70  mov     r9, rsi
0x180021e73  mov     r8, r14
0x180021e76  mov     rdx, rdi
0x180021e79  lea     rcx, [rbp+57h+var_A0]
0x180021e7d  call    ?GetSettingUInt@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z; WaasMedic::MockSettingsProvider::GetSettingUInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<uint> &)
0x180021e82  mov     ebx, eax
0x180021e84  lea     rcx, [rbp+57h+var_98]; void *
0x180021e88  cmp     dword ptr [rsi+4], 5
0x180021e8c  jnz     short loc_180021E98
0x180021e8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021e93  jmp     loc_180021F8C
0x180021e98  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021e9d  lea     rcx, [rbp+57h+var_A0]; this
0x180021ea1  call    ??0OneSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::OneSettingsProvider::OneSettingsProvider(void)
0x180021ea6  nop
0x180021ea7  lea     rcx, [rbp+57h+var_A0]; this
0x180021eab  call    ?Init@OneSettingsProvider@WaasMedic@@QEAAJXZ; WaasMedic::OneSettingsProvider::Init(void)
0x180021eb0  mov     ebx, eax
0x180021eb2  test    eax, eax
0x180021eb4  jns     short loc_180021ED1
0x180021eb6  mov     rcx, [rbp+5Fh]; this
0x180021eba  mov     r9d, eax; char *
0x180021ebd  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180021ec4  mov     edx, 69h ; 'i'; void *
0x180021ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021ece  nop
0x180021ecf  jmp     short loc_180021F13
0x180021ed1  mov     r9, rsi
0x180021ed4  mov     r8, r14
0x180021ed7  mov     rdx, rdi
0x180021eda  lea     rcx, [rbp+57h+var_A0]; this
0x180021ede  call    ?GetSettingUInt@OneSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z; WaasMedic::OneSettingsProvider::GetSettingUInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<uint> &)
0x180021ee3  mov     r15d, eax
0x180021ee6  test    eax, eax
0x180021ee8  jns     short loc_180021F11
0x180021eea  mov     ebx, 80070002h
0x180021eef  cmp     eax, ebx
0x180021ef1  jz      short loc_180021ECF
0x180021ef3  mov     rcx, [rbp+5Fh]; this
0x180021ef7  mov     r9d, eax; char *
0x180021efa  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180021f01  mov     edx, 6Ah ; 'j'; void *
0x180021f06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021f0b  nop
0x180021f0c  mov     ebx, r15d
0x180021f0f  jmp     short loc_180021F13
0x180021f11  xor     ebx, ebx
0x180021f13  lea     rcx, [rbp+57h+var_78]; void *
0x180021f17  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f1c  lea     rcx, [rbp+57h+var_98]; void *
0x180021f20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f25  cmp     dword ptr [rsi+4], 4
0x180021f29  jz      short loc_180021F8C
0x180021f2b  cmp     qword ptr [rdi+10h], 0
0x180021f30  jz      short loc_180021F83
0x180021f32  lea     rcx, [rbp+57h+var_A0]; this
0x180021f36  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x180021f3b  nop
0x180021f3c  mov     r9, rsi
0x180021f3f  mov     r8, r14
0x180021f42  mov     rdx, rdi
0x180021f45  lea     rcx, [rbp+57h+var_A0]
0x180021f49  call    ?GetSettingUInt@DefaultSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z; WaasMedic::DefaultSettingsProvider::GetSettingUInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<uint> &)
0x180021f4e  mov     ebx, eax
0x180021f50  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x180021f57  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x180021f5b  mov     [rbp+57h+var_70], rax
0x180021f5f  cmp     dword ptr [rsi+4], 3
0x180021f63  jnz     short loc_180021F74
0x180021f65  call    cs:__imp_DeleteCriticalSection
0x180021f6b  lea     rcx, [rbp+57h+var_98]
0x180021f6f  jmp     loc_180021E8E
0x180021f74  call    cs:__imp_DeleteCriticalSection
0x180021f7a  lea     rcx, [rbp+57h+var_98]; void *
0x180021f7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f83  mov     al, [rsi+8]
0x180021f86  neg     al
0x180021f88  sbb     ecx, ecx
0x180021f8a  and     ebx, ecx
0x180021f8c  mov     eax, [rsi+4]
0x180021f8f  mov     ecx, [rsi]
0x180021f91  cmp     qword ptr [r14+18h], 7
0x180021f96  jbe     short loc_180021F9B
0x180021f98  mov     r14, [r14]
0x180021f9b  cmp     qword ptr [rdi+18h], 7
0x180021fa0  jbe     short loc_180021FA5
0x180021fa2  mov     rdi, [rdi]
0x180021fa5  mov     [rsp+0D0h+var_A8], eax
0x180021fa9  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x180021fad  mov     r9, r14
0x180021fb0  mov     r8, rdi
0x180021fb3  lea     rdx, aSettingSSValue; "Setting: %s_%s; value: %d; source: %d"
0x180021fba  mov     ecx, 5; unsigned __int8
0x180021fbf  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180021fc4  mov     eax, ebx
0x180021fc6  mov     rcx, [rbp+57h+var_30]
0x180021fca  xor     rcx, rsp; StackCookie
0x180021fcd  call    __security_check_cookie
0x180021fd2  mov     rbx, [rsp+0D0h+arg_0]
0x180021fda  add     rsp, 0B0h
0x180021fe1  pop     r15
0x180021fe3  pop     r14
0x180021fe5  pop     rdi
0x180021fe6  pop     rsi
0x180021fe7  pop     rbp
0x180021fe8  retn
```
