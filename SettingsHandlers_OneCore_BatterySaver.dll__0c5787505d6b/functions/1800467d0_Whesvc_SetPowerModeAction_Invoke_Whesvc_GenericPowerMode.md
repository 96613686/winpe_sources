# Whesvc::SetPowerModeAction::Invoke(Whesvc::GenericPowerMode)

- ea: `0x1800467d0`
- end: `0x18004690b`
- name: `?Invoke@SetPowerModeAction@Whesvc@@QEAAJW4GenericPowerMode@2@@Z`
- size: `315`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800452dc`

## callees

- `0x180009190`
- `0x18000a0e1`
- `0x18000eacc`
- `0x18001f94c`
- `0x1800467d0`

## import_xrefs

- `POWRPROF!PowerGetUserConfiguredDCPowerMode` at `0x18004684c`
- `POWRPROF!PowerGetUserConfiguredDCPowerMode` at `0x18004684c`
- `POWRPROF!PowerSetUserConfiguredDCPowerMode` at `0x1800468ee`
- `POWRPROF!PowerSetUserConfiguredDCPowerMode` at `0x1800468ee`
- `POWRPROF!PowerSetUserConfiguredACPowerMode` at `0x1800468d0`
- `POWRPROF!PowerSetUserConfiguredACPowerMode` at `0x1800468d0`
- `POWRPROF!PowerGetUserConfiguredACPowerMode` at `0x180046810`
- `POWRPROF!PowerGetUserConfiguredACPowerMode` at `0x180046810`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Whesvc::SetPowerModeAction::Invoke(__int64 a1, int a2)
{
  int OverlayType; // esi
  int UserConfiguredACPowerMode; // eax
  signed int v5; // edi
  __int64 v6; // rdx
  int UserConfiguredDCPowerMode; // eax
  int v9; // esi
  int v10; // ebx
  GUID v11; // xmm0
  GUID Buf2; // [rsp+20h] [rbp-48h] BYREF
  __int128 Buf1; // [rsp+30h] [rbp-38h] BYREF
  __int128 v14; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  OverlayType = SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverPowerOverlaySingleton::GetOverlayType(&SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverPowerOverlaySingleton);
  Buf1 = 0;
  v14 = 0;
  Buf2 = 0;
  UserConfiguredACPowerMode = PowerGetUserConfiguredACPowerMode(&Buf1);
  v5 = UserConfiguredACPowerMode;
  if ( UserConfiguredACPowerMode > 0 )
    v5 = (unsigned __int16)UserConfiguredACPowerMode | 0x80070000;
  if ( v5 < 0 )
  {
    v6 = 36;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\setpowermodeaction.cpp",
      (const char *)(unsigned int)v5,
      Buf2.Data1);
    return (unsigned int)v5;
  }
  UserConfiguredDCPowerMode = PowerGetUserConfiguredDCPowerMode(&v14);
  v5 = UserConfiguredDCPowerMode;
  if ( UserConfiguredDCPowerMode > 0 )
    v5 = (unsigned __int16)UserConfiguredDCPowerMode | 0x80070000;
  if ( v5 < 0 )
  {
    v6 = 39;
    goto LABEL_5;
  }
  v9 = OverlayType - 1;
  if ( !v9 )
  {
    if ( a2 )
    {
      v10 = a2 - 1;
      if ( !v10 )
      {
        v11 = GUID_POWER_MODE_PERFORMANCE;
        goto LABEL_21;
      }
      goto LABEL_14;
    }
LABEL_20:
    v11 = GUID_POWER_MODE_NONE;
    goto LABEL_21;
  }
  if ( v9 != 1 )
    goto LABEL_22;
  if ( !a2 )
  {
    v11 = GUID_POWER_MODE_BEST_EFFICIENCY;
    goto LABEL_21;
  }
  v10 = a2 - 1;
  if ( !v10 )
    goto LABEL_20;
LABEL_14:
  if ( v10 == 1 )
  {
    v11 = GUID_POWER_MODE_BEST_PERFORMANCE;
LABEL_21:
    Buf2 = v11;
  }
LABEL_22:
  if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
    PowerSetUserConfiguredACPowerMode(&Buf2);
  if ( memcmp_0(&v14, &Buf2, 0x10u) )
    PowerSetUserConfiguredDCPowerMode(&Buf2);
  return 0;
}

```

## disassembly

```asm
0x1800467d0  push    rbp
0x1800467d2  push    rbx
0x1800467d3  push    rsi
0x1800467d4  push    rdi
0x1800467d5  mov     rbp, rsp
0x1800467d8  sub     rsp, 68h
0x1800467dc  mov     rax, cs:__security_cookie
0x1800467e3  xor     rax, rsp
0x1800467e6  mov     [rbp+var_18], rax
0x1800467ea  lea     rcx, ?g_CBatterySaverPowerOverlaySingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCBatterySaverPowerOverlaySingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverPowerOverlaySingleton SystemSettings::BatterySaverOneCoreDataModel::g_CBatterySaverPowerOverlaySingleton
0x1800467f1  mov     ebx, edx
0x1800467f3  call    ?GetOverlayType@CBatterySaverPowerOverlaySingleton@BatterySaverOneCoreDataModel@SystemSettings@@QEAA?AW4PowerOverlayType@23@XZ; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverPowerOverlaySingleton::GetOverlayType(void)
0x1800467f8  xorps   xmm0, xmm0
0x1800467fb  lea     rcx, [rbp+Buf1]
0x1800467ff  xorps   xmm1, xmm1
0x180046802  mov     esi, eax
0x180046804  movups  [rbp+Buf1], xmm0
0x180046808  movups  [rbp+var_28], xmm1
0x18004680c  movups  [rbp+Buf2], xmm0
0x180046810  call    cs:__imp_PowerGetUserConfiguredACPowerMode
0x180046816  mov     edi, eax
0x180046818  test    eax, eax
0x18004681a  jle     short loc_180046825
0x18004681c  movzx   edi, ax
0x18004681f  or      edi, 80070000h
0x180046825  test    edi, edi
0x180046827  jns     short loc_180046848
0x180046829  mov     edx, 24h ; '$'; void *
0x18004682e  mov     rcx, [rbp+20h]; this
0x180046832  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\coresettinghandlers"...
0x180046839  mov     r9d, edi; char *
0x18004683c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046841  mov     eax, edi
0x180046843  jmp     loc_1800468F6
0x180046848  lea     rcx, [rbp+var_28]
0x18004684c  call    cs:__imp_PowerGetUserConfiguredDCPowerMode
0x180046852  mov     edi, eax
0x180046854  test    eax, eax
0x180046856  jle     short loc_180046861
0x180046858  movzx   edi, ax
0x18004685b  or      edi, 80070000h
0x180046861  test    edi, edi
0x180046863  jns     short loc_18004686C
0x180046865  mov     edx, 27h ; '''
0x18004686a  jmp     short loc_18004682E
0x18004686c  sub     esi, 1
0x18004686f  jz      short loc_180046895
0x180046871  cmp     esi, 1
0x180046874  jnz     short loc_1800468B3
0x180046876  test    ebx, ebx
0x180046878  jz      short loc_18004688C
0x18004687a  sub     ebx, esi
0x18004687c  jz      short loc_1800468A7
0x18004687e  cmp     ebx, 1
0x180046881  jnz     short loc_1800468B3
0x180046883  movups  xmm0, xmmword ptr cs:GUID_POWER_MODE_BEST_PERFORMANCE.Data1
0x18004688a  jmp     short loc_1800468AE
0x18004688c  movups  xmm0, xmmword ptr cs:GUID_POWER_MODE_BEST_EFFICIENCY.Data1
0x180046893  jmp     short loc_1800468AE
0x180046895  test    ebx, ebx
0x180046897  jz      short loc_1800468A7
0x180046899  sub     ebx, 1
0x18004689c  jnz     short loc_18004687E
0x18004689e  movups  xmm0, xmmword ptr cs:GUID_POWER_MODE_PERFORMANCE.Data1
0x1800468a5  jmp     short loc_1800468AE
0x1800468a7  movups  xmm0, xmmword ptr cs:GUID_POWER_MODE_NONE.Data1
0x1800468ae  movdqu  [rbp+Buf2], xmm0
0x1800468b3  mov     ebx, 10h
0x1800468b8  lea     rdx, [rbp+Buf2]; Buf2
0x1800468bc  mov     r8d, ebx; Size
0x1800468bf  lea     rcx, [rbp+Buf1]; Buf1
0x1800468c3  call    memcmp_0
0x1800468c8  test    eax, eax
0x1800468ca  jz      short loc_1800468D6
0x1800468cc  lea     rcx, [rbp+Buf2]
0x1800468d0  call    cs:__imp_PowerSetUserConfiguredACPowerMode
0x1800468d6  mov     r8, rbx; Size
0x1800468d9  lea     rdx, [rbp+Buf2]; Buf2
0x1800468dd  lea     rcx, [rbp+var_28]; Buf1
0x1800468e1  call    memcmp_0
0x1800468e6  test    eax, eax
0x1800468e8  jz      short loc_1800468F4
0x1800468ea  lea     rcx, [rbp+Buf2]
0x1800468ee  call    cs:__imp_PowerSetUserConfiguredDCPowerMode
0x1800468f4  xor     eax, eax
0x1800468f6  mov     rcx, [rbp+var_18]
0x1800468fa  xor     rcx, rsp; StackCookie
0x1800468fd  call    __security_check_cookie
0x180046902  add     rsp, 68h
0x180046906  pop     rdi
0x180046907  pop     rsi
0x180046908  pop     rbx
0x180046909  pop     rbp
0x18004690a  retn
```
