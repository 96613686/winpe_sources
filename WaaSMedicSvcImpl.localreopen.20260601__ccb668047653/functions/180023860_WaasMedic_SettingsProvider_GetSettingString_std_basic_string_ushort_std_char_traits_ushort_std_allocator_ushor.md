# WaasMedic::SettingsProvider::GetSettingString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::Setting<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &)

- ea: `0x180023860`
- end: `0x180023a42`
- name: `?GetSettingString@SettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z`
- size: `482`
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
- `0x180022160`
- `0x18002339c`
- `0x180023860`
- `0x180023c30`
- `0x180024080`
- `0x1800247c0`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800239b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800239c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800239b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800239c4`

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
0x180023860  mov     [rsp-8+arg_0], rbx
0x180023865  push    rbp
0x180023866  push    rsi
0x180023867  push    rdi
0x180023868  push    r14
0x18002386a  push    r15
0x18002386c  lea     rbp, [rsp-37h]
0x180023871  sub     rsp, 0B0h
0x180023878  mov     rax, cs:__security_cookie
0x18002387f  xor     rax, rsp
0x180023882  mov     [rbp+57h+var_30], rax
0x180023886  mov     rdi, r9
0x180023889  mov     r14, r8
0x18002388c  mov     rsi, rdx
0x18002388f  lea     rax, ??_7MockSettingsProvider@WaasMedic@@6B@; const WaasMedic::MockSettingsProvider::`vftable'
0x180023896  mov     [rbp+57h+var_A0], rax
0x18002389a  xorps   xmm0, xmm0
0x18002389d  movups  [rbp+57h+var_98], xmm0
0x1800238a1  xorps   xmm1, xmm1
0x1800238a4  movdqu  [rbp+57h+var_88], xmm1
0x1800238a9  mov     r8d, 11h
0x1800238af  lea     rdx, aSystemMedicTes; "System\\Medic\\Test"
0x1800238b6  lea     rcx, [rbp+57h+var_98]
0x1800238ba  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800238bf  nop
0x1800238c0  mov     r9, rdi
0x1800238c3  mov     r8, r14
0x1800238c6  mov     rdx, rsi
0x1800238c9  lea     rcx, [rbp+57h+var_A0]
0x1800238cd  call    ?GetSettingString@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z; WaasMedic::MockSettingsProvider::GetSettingString(std::wstring const &,std::wstring const &,WaasMedic::Setting<std::wstring> &)
0x1800238d2  mov     ebx, eax
0x1800238d4  lea     rcx, [rbp+57h+var_98]; void *
0x1800238d8  cmp     dword ptr [rdi+20h], 5
0x1800238dc  jnz     short loc_1800238E8
0x1800238de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800238e3  jmp     loc_1800239DC
0x1800238e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800238ed  lea     rcx, [rbp+57h+var_A0]; this
0x1800238f1  call    ??0OneSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::OneSettingsProvider::OneSettingsProvider(void)
0x1800238f6  nop
0x1800238f7  lea     rcx, [rbp+57h+var_A0]; this
0x1800238fb  call    ?Init@OneSettingsProvider@WaasMedic@@QEAAJXZ; WaasMedic::OneSettingsProvider::Init(void)
0x180023900  mov     ebx, eax
0x180023902  test    eax, eax
0x180023904  jns     short loc_180023921
0x180023906  mov     rcx, [rbp+5Fh]; this
0x18002390a  mov     r9d, eax; char *
0x18002390d  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180023914  mov     edx, 0A8h; void *
0x180023919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002391e  nop
0x18002391f  jmp     short loc_180023963
0x180023921  mov     r9, rdi
0x180023924  mov     r8, r14
0x180023927  mov     rdx, rsi
0x18002392a  lea     rcx, [rbp+57h+var_A0]; this
0x18002392e  call    ?GetSettingString@OneSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z; WaasMedic::OneSettingsProvider::GetSettingString(std::wstring const &,std::wstring const &,WaasMedic::Setting<std::wstring> &)
0x180023933  mov     r15d, eax
0x180023936  test    eax, eax
0x180023938  jns     short loc_180023961
0x18002393a  mov     ebx, 80070002h
0x18002393f  cmp     eax, ebx
0x180023941  jz      short loc_18002391F
0x180023943  mov     rcx, [rbp+5Fh]; this
0x180023947  mov     r9d, eax; char *
0x18002394a  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180023951  mov     edx, 0A9h; void *
0x180023956  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002395b  nop
0x18002395c  mov     ebx, r15d
0x18002395f  jmp     short loc_180023963
0x180023961  xor     ebx, ebx
0x180023963  lea     rcx, [rbp+57h+var_78]; void *
0x180023967  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002396c  lea     rcx, [rbp+57h+var_98]; void *
0x180023970  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023975  cmp     dword ptr [rdi+20h], 4
0x180023979  jz      short loc_1800239DC
0x18002397b  cmp     qword ptr [rsi+10h], 0
0x180023980  jz      short loc_1800239D3
0x180023982  lea     rcx, [rbp+57h+var_A0]; this
0x180023986  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x18002398b  nop
0x18002398c  mov     r9, rdi
0x18002398f  mov     r8, r14
0x180023992  mov     rdx, rsi
0x180023995  lea     rcx, [rbp+57h+var_A0]
0x180023999  call    ?GetSettingString@DefaultSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z; WaasMedic::DefaultSettingsProvider::GetSettingString(std::wstring const &,std::wstring const &,WaasMedic::Setting<std::wstring> &)
0x18002399e  mov     ebx, eax
0x1800239a0  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x1800239a7  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x1800239ab  mov     [rbp+57h+var_70], rax
0x1800239af  cmp     dword ptr [rdi+20h], 3
0x1800239b3  jnz     short loc_1800239C4
0x1800239b5  call    cs:__imp_DeleteCriticalSection
0x1800239bb  lea     rcx, [rbp+57h+var_98]
0x1800239bf  jmp     loc_1800238DE
0x1800239c4  call    cs:__imp_DeleteCriticalSection
0x1800239ca  lea     rcx, [rbp+57h+var_98]; void *
0x1800239ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800239d3  mov     al, [rdi+24h]
0x1800239d6  neg     al
0x1800239d8  sbb     ecx, ecx
0x1800239da  and     ebx, ecx
0x1800239dc  mov     eax, [rdi+20h]
0x1800239df  cmp     qword ptr [rdi+18h], 7
0x1800239e4  jbe     short loc_1800239E9
0x1800239e6  mov     rdi, [rdi]
0x1800239e9  cmp     qword ptr [r14+18h], 7
0x1800239ee  jbe     short loc_1800239F3
0x1800239f0  mov     r14, [r14]
0x1800239f3  cmp     qword ptr [rsi+18h], 7
0x1800239f8  jbe     short loc_1800239FD
0x1800239fa  mov     rsi, [rsi]
0x1800239fd  mov     [rsp+0D0h+var_A8], eax
0x180023a01  mov     [rsp+0D0h+var_B0], rdi
0x180023a06  mov     r9, r14
0x180023a09  mov     r8, rsi
0x180023a0c  lea     rdx, aSettingSSValue_0; "Setting: %s_%s; value: '%s'; source: %d"
0x180023a13  mov     ecx, 5; unsigned __int8
0x180023a18  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180023a1d  mov     eax, ebx
0x180023a1f  mov     rcx, [rbp+57h+var_30]
0x180023a23  xor     rcx, rsp; StackCookie
0x180023a26  call    __security_check_cookie
0x180023a2b  mov     rbx, [rsp+0D0h+arg_0]
0x180023a33  add     rsp, 0B0h
0x180023a3a  pop     r15
0x180023a3c  pop     r14
0x180023a3e  pop     rdi
0x180023a3f  pop     rsi
0x180023a40  pop     rbp
0x180023a41  retn
```
