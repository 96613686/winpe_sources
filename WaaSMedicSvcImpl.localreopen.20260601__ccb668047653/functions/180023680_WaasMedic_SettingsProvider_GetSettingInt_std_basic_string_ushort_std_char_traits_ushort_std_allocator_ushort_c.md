# WaasMedic::SettingsProvider::GetSettingInt(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::Setting<int> &)

- ea: `0x180023680`
- end: `0x180023859`
- name: `?GetSettingInt@SettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@H@2@@Z`
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
- `0x180021f60`
- `0x18002339c`
- `0x180023680`
- `0x180023c30`
- `0x180023f40`
- `0x180024610`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800237d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800237e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800237d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800237e4`

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
0x180023680  mov     [rsp-8+arg_0], rbx
0x180023685  push    rbp
0x180023686  push    rsi
0x180023687  push    rdi
0x180023688  push    r14
0x18002368a  push    r15
0x18002368c  lea     rbp, [rsp-37h]
0x180023691  sub     rsp, 0B0h
0x180023698  mov     rax, cs:__security_cookie
0x18002369f  xor     rax, rsp
0x1800236a2  mov     [rbp+57h+var_30], rax
0x1800236a6  mov     rsi, r9
0x1800236a9  mov     r14, r8
0x1800236ac  mov     rdi, rdx
0x1800236af  lea     rax, ??_7MockSettingsProvider@WaasMedic@@6B@; const WaasMedic::MockSettingsProvider::`vftable'
0x1800236b6  mov     [rbp+57h+var_A0], rax
0x1800236ba  xorps   xmm0, xmm0
0x1800236bd  movups  [rbp+57h+var_98], xmm0
0x1800236c1  xorps   xmm1, xmm1
0x1800236c4  movdqu  [rbp+57h+var_88], xmm1
0x1800236c9  mov     r8d, 11h
0x1800236cf  lea     rdx, aSystemMedicTes; "System\\Medic\\Test"
0x1800236d6  lea     rcx, [rbp+57h+var_98]
0x1800236da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800236df  nop
0x1800236e0  mov     r9, rsi
0x1800236e3  mov     r8, r14
0x1800236e6  mov     rdx, rdi
0x1800236e9  lea     rcx, [rbp+57h+var_A0]
0x1800236ed  call    ?GetSettingUInt@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@I@2@@Z; WaasMedic::MockSettingsProvider::GetSettingUInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<uint> &)
0x1800236f2  mov     ebx, eax
0x1800236f4  lea     rcx, [rbp+57h+var_98]; void *
0x1800236f8  cmp     dword ptr [rsi+4], 5
0x1800236fc  jnz     short loc_180023708
0x1800236fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023703  jmp     loc_1800237FC
0x180023708  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002370d  lea     rcx, [rbp+57h+var_A0]; this
0x180023711  call    ??0OneSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::OneSettingsProvider::OneSettingsProvider(void)
0x180023716  nop
0x180023717  lea     rcx, [rbp+57h+var_A0]; this
0x18002371b  call    ?Init@OneSettingsProvider@WaasMedic@@QEAAJXZ; WaasMedic::OneSettingsProvider::Init(void)
0x180023720  mov     ebx, eax
0x180023722  test    eax, eax
0x180023724  jns     short loc_180023741
0x180023726  mov     rcx, [rbp+5Fh]; this
0x18002372a  mov     r9d, eax; char *
0x18002372d  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180023734  mov     edx, 2Ah ; '*'; void *
0x180023739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002373e  nop
0x18002373f  jmp     short loc_180023783
0x180023741  mov     r9, rsi
0x180023744  mov     r8, r14
0x180023747  mov     rdx, rdi
0x18002374a  lea     rcx, [rbp+57h+var_A0]; this
0x18002374e  call    ?GetSettingInt@OneSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@H@2@@Z; WaasMedic::OneSettingsProvider::GetSettingInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<int> &)
0x180023753  mov     r15d, eax
0x180023756  test    eax, eax
0x180023758  jns     short loc_180023781
0x18002375a  mov     ebx, 80070002h
0x18002375f  cmp     eax, ebx
0x180023761  jz      short loc_18002373F
0x180023763  mov     rcx, [rbp+5Fh]; this
0x180023767  mov     r9d, eax; char *
0x18002376a  lea     r8, aOnecoreEnduser_14; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180023771  mov     edx, 2Bh ; '+'; void *
0x180023776  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002377b  nop
0x18002377c  mov     ebx, r15d
0x18002377f  jmp     short loc_180023783
0x180023781  xor     ebx, ebx
0x180023783  lea     rcx, [rbp+57h+var_78]; void *
0x180023787  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002378c  lea     rcx, [rbp+57h+var_98]; void *
0x180023790  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023795  cmp     dword ptr [rsi+4], 4
0x180023799  jz      short loc_1800237FC
0x18002379b  cmp     qword ptr [rdi+10h], 0
0x1800237a0  jz      short loc_1800237F3
0x1800237a2  lea     rcx, [rbp+57h+var_A0]; this
0x1800237a6  call    ??0DefaultSettingsProvider@WaasMedic@@QEAA@XZ; WaasMedic::DefaultSettingsProvider::DefaultSettingsProvider(void)
0x1800237ab  nop
0x1800237ac  mov     r9, rsi
0x1800237af  mov     r8, r14
0x1800237b2  mov     rdx, rdi
0x1800237b5  lea     rcx, [rbp+57h+var_A0]
0x1800237b9  call    ?GetSettingInt@DefaultSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@H@2@@Z; WaasMedic::DefaultSettingsProvider::GetSettingInt(std::wstring const &,std::wstring const &,WaasMedic::Setting<int> &)
0x1800237be  mov     ebx, eax
0x1800237c0  lea     rax, ??_7CLock@WaasMedic@@6B@; const WaasMedic::CLock::`vftable'
0x1800237c7  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x1800237cb  mov     [rbp+57h+var_70], rax
0x1800237cf  cmp     dword ptr [rsi+4], 3
0x1800237d3  jnz     short loc_1800237E4
0x1800237d5  call    cs:__imp_DeleteCriticalSection
0x1800237db  lea     rcx, [rbp+57h+var_98]
0x1800237df  jmp     loc_1800236FE
0x1800237e4  call    cs:__imp_DeleteCriticalSection
0x1800237ea  lea     rcx, [rbp+57h+var_98]; void *
0x1800237ee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800237f3  mov     al, [rsi+8]
0x1800237f6  neg     al
0x1800237f8  sbb     ecx, ecx
0x1800237fa  and     ebx, ecx
0x1800237fc  mov     eax, [rsi+4]
0x1800237ff  mov     ecx, [rsi]
0x180023801  cmp     qword ptr [r14+18h], 7
0x180023806  jbe     short loc_18002380B
0x180023808  mov     r14, [r14]
0x18002380b  cmp     qword ptr [rdi+18h], 7
0x180023810  jbe     short loc_180023815
0x180023812  mov     rdi, [rdi]
0x180023815  mov     [rsp+0D0h+var_A8], eax
0x180023819  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x18002381d  mov     r9, r14
0x180023820  mov     r8, rdi
0x180023823  lea     rdx, aSettingSSValue_1; "Setting: %s_%s; value: %d; source: %d;"
0x18002382a  mov     ecx, 5; unsigned __int8
0x18002382f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180023834  mov     eax, ebx
0x180023836  mov     rcx, [rbp+57h+var_30]
0x18002383a  xor     rcx, rsp; StackCookie
0x18002383d  call    __security_check_cookie
0x180023842  mov     rbx, [rsp+0D0h+arg_0]
0x18002384a  add     rsp, 0B0h
0x180023851  pop     r15
0x180023853  pop     r14
0x180023855  pop     rdi
0x180023856  pop     rsi
0x180023857  pop     rbp
0x180023858  retn
```
