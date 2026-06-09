# WaasMedic::SettingsProvider::GetSettingBool(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::SettingSource,WaasMedic::Setting<bool> &)

- ea: `0x180023444`
- end: `0x180023601`
- name: `?GetSettingBool@SettingsProvider@WaasMedic@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4SettingSource@2@AEAU?$Setting@_N@2@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x180023610`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18000f954`
- `0x180021da0`
- `0x18002339c`
- `0x180023444`
- `0x180023c30`
- `0x180023df0`
- `0x180024460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800235b3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800235cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800235b3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800235cd`

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
0x180023444  mov     [rsp-8+arg_0], rbx
0x180023449  push    rbp
0x18002344a  push    rsi
0x18002344b  push    rdi
0x18002344c  push    r14
0x18002344e  push    r15
0x180023450  lea     rbp, [rsp-2Fh]
0x180023455  sub     rsp, 0A0h
0x18002345c  mov     rax, cs:__security_cookie
0x180023463  xor     rax, rsp
0x180023466  mov     [rbp+4Fh+var_30], rax
0x18002346a  mov     r15, r8
0x18002346d  mov     r14, rdx
0x180023470  mov     rdi, [rbp+4Fh+arg_20]
0x180023474  lea     rax, ??_7MockSettingsProvider@WaasMedic@@6B@; const WaasMedic::MockSettingsProvider::`vftable'
0x18002347b  mov     [rbp+4Fh+var_A0], rax
0x18002347f  xorps   xmm0, xmm0
0x180023482  movups  [rbp+4Fh+var_98], xmm0
0x180023486  xorps   xmm1, xmm1
0x180023489  movdqu  [rbp+4Fh+var_88], xmm1
0x18002348e  mov     r8d, 11h
0x180023494  lea     rdx, aSystemMedicTes; "System\\Medic\\Test"
0x18002349b  lea     rcx, [rbp+4Fh+var_98]
0x18002349f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800234a4  nop
0x1800234a5  mov     r9, rdi
0x1800234a8  mov     r8, r15
0x1800234ab  mov     rdx, r14
0x1800234ae  lea     rcx, [rbp+4Fh+var_A0]
0x1800234b2  call    ?GetSettingBool@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@_N@2@@Z; WaasMedic::MockSettingsProvider::GetSettingBool(std::wstring const &,std::wstring const &,WaasMedic::Setting<bool> &)
0x1800234b7  mov     ebx, eax
0x1800234b9  test    eax, eax
0x1800234bb  jns     short loc_1800234D8
0x1800234bd  mov     rcx, [rbp+57h]; this
0x1800234c1  mov     r9d, eax; char *
0x1800234c4  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x1800234cb  mov     edx, 0DCh; void *
0x1800234d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800234d5  nop
0x1800234d6  jmp     short loc_1800234DA
0x1800234d8  xor     ebx, ebx
0x1800234da  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800234de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800234e3  cmp     dword ptr [rdi+4], 5
0x1800234e7  jz      loc_1800235DC
0x1800234ed  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800234f1  call    ??0OneSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::OneSettingsProvider::OneSettingsProvider(void)
0x1800234f6  nop
0x1800234f7  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800234fb  call    ?Init@OneSettingsProvider@WaasMedic@@QEAAJXZ; WaasMedic::OneSettingsProvider::Init(void)
0x180023500  mov     ebx, eax
0x180023502  test    eax, eax
0x180023504  jns     short loc_180023521
0x180023506  mov     rcx, [rbp+57h]; this
0x18002350a  mov     r9d, eax; char *
0x18002350d  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180023514  mov     edx, 0EBh; void *
0x180023519  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002351e  nop
0x18002351f  jmp     short loc_180023561
0x180023521  mov     r9, rdi
0x180023524  mov     r8, r15
0x180023527  mov     rdx, r14
0x18002352a  lea     rcx, [rbp+4Fh+var_A0]; this
0x18002352e  call    ?GetSettingBool@OneSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@_N@2@@Z; WaasMedic::OneSettingsProvider::GetSettingBool(std::wstring const &,std::wstring const &,WaasMedic::Setting<bool> &)
0x180023533  mov     esi, eax
0x180023535  test    eax, eax
0x180023537  jns     short loc_18002355F
0x180023539  mov     ebx, 80070002h
0x18002353e  cmp     eax, ebx
0x180023540  jz      short loc_18002351F
0x180023542  mov     rcx, [rbp+57h]; this
0x180023546  mov     r9d, eax; char *
0x180023549  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180023550  mov     edx, 0ECh; void *
0x180023555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002355a  nop
0x18002355b  mov     ebx, esi
0x18002355d  jmp     short loc_180023561
0x18002355f  xor     ebx, ebx
0x180023561  lea     rcx, [rbp+4Fh+var_78]; void *
0x180023565  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002356a  lea     rcx, [rbp+4Fh+var_98]; void *
0x18002356e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023573  cmp     dword ptr [rdi+4], 4
0x180023577  jz      short loc_1800235DC
0x180023579  cmp     qword ptr [r14+10h], 0
0x18002357e  jz      short loc_1800235C2
0x180023580  lea     rcx, [rbp+4Fh+var_A0]; this
0x180023584  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x180023589  nop
0x18002358a  mov     r9, rdi
0x18002358d  mov     r8, r15
0x180023590  mov     rdx, r14
0x180023593  lea     rcx, [rbp+4Fh+var_A0]
0x180023597  call    ?GetSettingBool@DefaultSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@_N@2@@Z; WaasMedic::DefaultSettingsProvider::GetSettingBool(std::wstring const &,std::wstring const &,WaasMedic::Setting<bool> &)
0x18002359c  mov     ebx, eax
0x18002359e  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x1800235a5  lea     rcx, [rbp+4Fh+CriticalSection]; lpCriticalSection
0x1800235a9  mov     [rbp+4Fh+var_70], rax
0x1800235ad  cmp     dword ptr [rdi+4], 3
0x1800235b1  jz      short loc_1800235CD
0x1800235b3  call    cs:__imp_DeleteCriticalSection
0x1800235b9  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800235bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800235c2  mov     al, [rdi+8]
0x1800235c5  neg     al
0x1800235c7  sbb     eax, eax
0x1800235c9  and     eax, ebx
0x1800235cb  jmp     short loc_1800235DE
0x1800235cd  call    cs:__imp_DeleteCriticalSection
0x1800235d3  lea     rcx, [rbp+4Fh+var_98]; void *
0x1800235d7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800235dc  mov     eax, ebx
0x1800235de  mov     rcx, [rbp+4Fh+var_30]
0x1800235e2  xor     rcx, rsp; StackCookie
0x1800235e5  call    __security_check_cookie
0x1800235ea  mov     rbx, [rsp+0C0h+arg_0]
0x1800235f2  add     rsp, 0A0h
0x1800235f9  pop     r15
0x1800235fb  pop     r14
0x1800235fd  pop     rdi
0x1800235fe  pop     rsi
0x1800235ff  pop     rbp
0x180023600  retn
```
