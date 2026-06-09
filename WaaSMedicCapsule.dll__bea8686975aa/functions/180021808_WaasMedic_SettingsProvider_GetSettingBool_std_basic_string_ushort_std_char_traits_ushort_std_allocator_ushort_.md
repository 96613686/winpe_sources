# WaasMedic::SettingsProvider::GetSettingBool(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::SettingSource,WaasMedic::Setting<bool> &)

- ea: `0x180021808`
- end: `0x1800219c5`
- name: `?GetSettingBool@SettingsProvider@WaasMedic@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4SettingSource@2@AEAU?$Setting@_N@2@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1800219d0`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x1800216a4`
- `0x18002171c`
- `0x180021808`
- `0x180021ff0`
- `0x180022960`
- `0x1800232b0`
- `0x180023b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021977`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021991`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021977`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021991`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::SettingsProvider::GetSettingBool(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int SettingBool; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // eax
  unsigned int v11; // esi
  void **v13; // [rsp+20h] [rbp-51h] BYREF
  _OWORD v14[2]; // [rsp+28h] [rbp-49h] BYREF
  _BYTE v15[8]; // [rsp+48h] [rbp-29h] BYREF
  void **v16; // [rsp+50h] [rbp-21h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+60h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v13 = &WaasMedic::MockSettingsProvider::`vftable';
  memset(v14, 0, sizeof(v14));
  std::wstring::_Construct<1,unsigned short const *>(v14, L"System\\Medic\\Test", 17);
  SettingBool = WaasMedic::MockSettingsProvider::GetSettingBool(&v13, a2, a3, a5);
  v8 = SettingBool;
  if ( SettingBool >= 0 )
    v8 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\settingsprovider.cpp",
      (const char *)(unsigned int)SettingBool,
      (int)v13);
  std::wstring::~wstring(v14);
  if ( *(_DWORD *)(a5 + 4) != 5 )
  {
    WaasMedic::OneSettingsProvider::OneSettingsProvider((WaasMedic::OneSettingsProvider *)&v13);
    v9 = WaasMedic::OneSettingsProvider::Init((WaasMedic::OneSettingsProvider *)&v13);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v10 = WaasMedic::OneSettingsProvider::GetSettingBool((WaasMedic::OneSettingsProvider *)&v13);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v8 = 0;
      }
      else
      {
        v8 = -2147024894;
        if ( v10 != -2147024894 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEC,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\settingsprovider.cpp",
            (const char *)(unsigned int)v10,
            (int)v13);
          v8 = v11;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\settingsprovider.cpp",
        (const char *)(unsigned int)v9,
        (int)v13);
    }
    std::wstring::~wstring(v15);
    std::wstring::~wstring(v14);
    if ( *(_DWORD *)(a5 + 4) != 4 )
    {
      if ( !*(_QWORD *)(a2 + 16) )
        return *(_BYTE *)(a5 + 8) != 0 ? v8 : 0;
      WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider((WaasMedic::DefaultSettingsProvider *)&v13);
      v8 = WaasMedic::DefaultSettingsProvider::GetSettingBool(&v13, a2, a3, a5);
      v16 = &WaasMedic::CLock::`vftable';
      if ( *(_DWORD *)(a5 + 4) != 3 )
      {
        DeleteCriticalSection(&CriticalSection);
        std::wstring::~wstring(v14);
        return *(_BYTE *)(a5 + 8) != 0 ? v8 : 0;
      }
      DeleteCriticalSection(&CriticalSection);
      std::wstring::~wstring(v14);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180021808  mov     [rsp-8+arg_0], rbx
0x18002180d  push    rbp
0x18002180e  push    rsi
0x18002180f  push    rdi
0x180021810  push    r14
0x180021812  push    r15
0x180021814  lea     rbp, [rsp-2Fh]
0x180021819  sub     rsp, 0A0h
0x180021820  mov     rax, cs:__security_cookie
0x180021827  xor     rax, rsp
0x18002182a  mov     [rbp+4Fh+var_30], rax
0x18002182e  mov     r15, r8
0x180021831  mov     r14, rdx
0x180021834  mov     rdi, [rbp+4Fh+arg_20]
0x180021838  lea     rax, ??_7MockSettingsProvider@WaasMedic@@6B@; const WaasMedic::MockSettingsProvider::`vftable'
0x18002183f  mov     [rbp+4Fh+var_A0], rax
0x180021843  xorps   xmm0, xmm0
0x180021846  movups  [rbp+4Fh+var_98], xmm0
0x18002184a  xorps   xmm1, xmm1
0x18002184d  movdqu  [rbp+4Fh+var_88], xmm1
0x180021852  mov     r8d, 11h
0x180021858  lea     rdx, aSystemMedicTes; "System\\Medic\\Test"
0x18002185f  lea     rcx, [rbp+4Fh+var_98]
0x180021863  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021868  nop
0x180021869  mov     r9, rdi
0x18002186c  mov     r8, r15
0x18002186f  mov     rdx, r14
0x180021872  lea     rcx, [rbp+4Fh+var_A0]
0x180021876  call    ?GetSettingBool@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@_N@2@@Z; WaasMedic::MockSettingsProvider::GetSettingBool(std::wstring const &,std::wstring const &,WaasMedic::Setting<bool> &)
0x18002187b  mov     ebx, eax
0x18002187d  test    eax, eax
0x18002187f  jns     short loc_18002189C
0x180021881  mov     rcx, [rbp+57h]; this
0x180021885  mov     r9d, eax; char *
0x180021888  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x18002188f  mov     edx, 0DCh; void *
0x180021894  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021899  nop
0x18002189a  jmp     short loc_18002189E
0x18002189c  xor     ebx, ebx
0x18002189e  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800218a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800218a7  cmp     dword ptr [rdi+4], 5
0x1800218ab  jz      loc_1800219A0
0x1800218b1  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800218b5  call    ??0OneSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::OneSettingsProvider::OneSettingsProvider(void)
0x1800218ba  nop
0x1800218bb  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800218bf  call    ?Init@OneSettingsProvider@WaasMedic@@QEAAJXZ; WaasMedic::OneSettingsProvider::Init(void)
0x1800218c4  mov     ebx, eax
0x1800218c6  test    eax, eax
0x1800218c8  jns     short loc_1800218E5
0x1800218ca  mov     rcx, [rbp+57h]; this
0x1800218ce  mov     r9d, eax; char *
0x1800218d1  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x1800218d8  mov     edx, 0EBh; void *
0x1800218dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800218e2  nop
0x1800218e3  jmp     short loc_180021925
0x1800218e5  mov     r9, rdi
0x1800218e8  mov     r8, r15
0x1800218eb  mov     rdx, r14
0x1800218ee  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800218f2  call    ?GetSettingBool@OneSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@_N@2@@Z; WaasMedic::OneSettingsProvider::GetSettingBool(std::wstring const &,std::wstring const &,WaasMedic::Setting<bool> &)
0x1800218f7  mov     esi, eax
0x1800218f9  test    eax, eax
0x1800218fb  jns     short loc_180021923
0x1800218fd  mov     ebx, 80070002h
0x180021902  cmp     eax, ebx
0x180021904  jz      short loc_1800218E3
0x180021906  mov     rcx, [rbp+57h]; this
0x18002190a  mov     r9d, eax; char *
0x18002190d  lea     r8, aOnecoreEnduser_24; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180021914  mov     edx, 0ECh; void *
0x180021919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002191e  nop
0x18002191f  mov     ebx, esi
0x180021921  jmp     short loc_180021925
0x180021923  xor     ebx, ebx
0x180021925  lea     rcx, [rbp+4Fh+var_78]; void *
0x180021929  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002192e  lea     rcx, [rbp+4Fh+var_98]; void *
0x180021932  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021937  cmp     dword ptr [rdi+4], 4
0x18002193b  jz      short loc_1800219A0
0x18002193d  cmp     qword ptr [r14+10h], 0
0x180021942  jz      short loc_180021986
0x180021944  lea     rcx, [rbp+4Fh+var_A0]; this
0x180021948  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x18002194d  nop
0x18002194e  mov     r9, rdi
0x180021951  mov     r8, r15
0x180021954  mov     rdx, r14
0x180021957  lea     rcx, [rbp+4Fh+var_A0]
0x18002195b  call    ?GetSettingBool@DefaultSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@_N@2@@Z; WaasMedic::DefaultSettingsProvider::GetSettingBool(std::wstring const &,std::wstring const &,WaasMedic::Setting<bool> &)
0x180021960  mov     ebx, eax
0x180021962  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x180021969  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x18002196d  mov     [rbp+4Fh+var_70], rax
0x180021971  cmp     dword ptr [rdi+4], 3
0x180021975  jz      short loc_180021991
0x180021977  call    cs:__imp_DeleteCriticalSection
0x18002197d  lea     rcx, [rbp+4Fh+var_98]; void *
0x180021981  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021986  mov     al, [rdi+8]
0x180021989  neg     al
0x18002198b  sbb     eax, eax
0x18002198d  and     eax, ebx
0x18002198f  jmp     short loc_1800219A2
0x180021991  call    cs:__imp_DeleteCriticalSection
0x180021997  lea     rcx, [rbp+4Fh+var_98]; void *
0x18002199b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800219a0  mov     eax, ebx
0x1800219a2  mov     rcx, [rbp+4Fh+var_30]
0x1800219a6  xor     rcx, rsp; StackCookie
0x1800219a9  call    __security_check_cookie
0x1800219ae  mov     rbx, [rsp+0C0h+arg_0]
0x1800219b6  add     rsp, 0A0h
0x1800219bd  pop     r15
0x1800219bf  pop     r14
0x1800219c1  pop     rdi
0x1800219c2  pop     rsi
0x1800219c3  pop     rbp
0x1800219c4  retn
```
