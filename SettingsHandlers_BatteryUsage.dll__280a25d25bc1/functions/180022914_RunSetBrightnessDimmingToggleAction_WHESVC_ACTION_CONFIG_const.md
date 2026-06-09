# RunSetBrightnessDimmingToggleAction(_WHESVC_ACTION_CONFIG * const)

- ea: `0x180022914`
- end: `0x180022b17`
- name: `?RunSetBrightnessDimmingToggleAction@@YAJQEAU_WHESVC_ACTION_CONFIG@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(struct _WHESVC_ACTION_CONFIG *const, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180008100`

## callees

- `0x18000a13c`
- `0x1800228bc`
- `0x180022914`
- `0x180055864`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022aff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022aff`
- `POWRPROF!PowerGetActiveScheme` at `0x180022993`
- `POWRPROF!PowerGetActiveScheme` at `0x180022993`
- `POWRPROF!PowerWriteDCValueIndex` at `0x180022a69`
- `POWRPROF!PowerWriteDCValueIndex` at `0x180022a69`
- `POWRPROF!PowerReadACDefaultIndex` at `0x180022a1f`
- `POWRPROF!PowerReadACDefaultIndex` at `0x180022a1f`
- `POWRPROF!PowerReadDCDefaultIndex` at `0x1800229e3`
- `POWRPROF!PowerReadDCDefaultIndex` at `0x1800229e3`
- `POWRPROF!PowerSetActiveScheme` at `0x180022ac8`
- `POWRPROF!PowerSetActiveScheme` at `0x180022ac8`
- `POWRPROF!PowerWriteACValueIndex` at `0x180022aa3`
- `POWRPROF!PowerWriteACValueIndex` at `0x180022aa3`

## pseudocode

```c
__int64 __fastcall RunSetBrightnessDimmingToggleAction(struct _WHESVC_ACTION_CONFIG *const a1, __int64 a2)
{
  signed int ActiveScheme; // ebx
  __int64 v3; // rdx
  GUID *v4; // rcx
  signed int v5; // eax
  signed int v6; // eax
  DWORD v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  signed int active; // eax
  int DcDefaultIndex; // [rsp+20h] [rbp-40h]
  GUID **p_SchemePersonalityGuid; // [rsp+30h] [rbp-30h] BYREF
  GUID *ActivePolicyGuid; // [rsp+38h] [rbp-28h] BYREF
  char v15; // [rsp+40h] [rbp-20h]
  __int128 v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD DcValueIndex; // [rsp+88h] [rbp+28h] BYREF
  DWORD AcDefaultIndex; // [rsp+90h] [rbp+30h] BYREF
  GUID *SchemePersonalityGuid; // [rsp+98h] [rbp+38h] BYREF

  SchemePersonalityGuid = 0;
  DcValueIndex = 0;
  AcDefaultIndex = 0;
  v16 = 0;
  v17 = 0;
  ActiveScheme = WhesvcConfigLookupValue(a1, a2, &v16);
  if ( ActiveScheme < 0 )
  {
    v3 = 17;
    goto LABEL_3;
  }
  if ( (_DWORD)v16 != 1 )
  {
    ActiveScheme = -2147024809;
    v3 = 22;
    goto LABEL_3;
  }
  p_SchemePersonalityGuid = &SchemePersonalityGuid;
  ActivePolicyGuid = 0;
  v15 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_SchemePersonalityGuid);
  v4 = SchemePersonalityGuid;
  if ( ActiveScheme )
  {
    if ( ActiveScheme > 0 )
      ActiveScheme = (unsigned __int16)ActiveScheme | 0x80070000;
  }
  else if ( SchemePersonalityGuid )
  {
    if ( DWORD2(v16) )
    {
      v5 = PowerReadDCDefaultIndex(
             0,
             SchemePersonalityGuid,
             &GUID_ENERGY_SAVER_SUBGROUP,
             &GUID_ENERGY_SAVER_BRIGHTNESS,
             &DcValueIndex);
      ActiveScheme = v5;
      if ( v5 > 0 )
        ActiveScheme = (unsigned __int16)v5 | 0x80070000;
      if ( ActiveScheme < 0 )
      {
        v3 = 44;
        goto LABEL_3;
      }
      v6 = PowerReadACDefaultIndex(
             0,
             SchemePersonalityGuid,
             &GUID_ENERGY_SAVER_SUBGROUP,
             &GUID_ENERGY_SAVER_BRIGHTNESS,
             &AcDefaultIndex);
      ActiveScheme = v6;
      if ( v6 > 0 )
        ActiveScheme = (unsigned __int16)v6 | 0x80070000;
      if ( ActiveScheme < 0 )
      {
        v3 = 52;
        goto LABEL_3;
      }
      v4 = SchemePersonalityGuid;
      v7 = DcValueIndex;
    }
    else
    {
      v7 = 100;
      DcValueIndex = 100;
      AcDefaultIndex = 100;
    }
    v8 = PowerWriteDCValueIndex(0, v4, &GUID_ENERGY_SAVER_SUBGROUP, &GUID_ENERGY_SAVER_BRIGHTNESS, v7);
    ActiveScheme = v8;
    if ( v8 > 0 )
      ActiveScheme = (unsigned __int16)v8 | 0x80070000;
    if ( ActiveScheme >= 0 )
    {
      v9 = PowerWriteACValueIndex(
             0,
             SchemePersonalityGuid,
             &GUID_ENERGY_SAVER_SUBGROUP,
             &GUID_ENERGY_SAVER_BRIGHTNESS,
             AcDefaultIndex);
      ActiveScheme = v9;
      if ( v9 > 0 )
        ActiveScheme = (unsigned __int16)v9 | 0x80070000;
      if ( ActiveScheme >= 0 )
      {
        active = PowerSetActiveScheme(0, SchemePersonalityGuid);
        ActiveScheme = active;
        if ( active > 0 )
          ActiveScheme = (unsigned __int16)active | 0x80070000;
        if ( ActiveScheme >= 0 )
          goto LABEL_4;
        v3 = 79;
      }
      else
      {
        v3 = 75;
      }
    }
    else
    {
      v3 = 68;
    }
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\whesvcactions.cpp",
      (const char *)(unsigned int)ActiveScheme,
      DcDefaultIndex);
LABEL_4:
    v4 = SchemePersonalityGuid;
  }
  SchemePersonalityGuid = 0;
  if ( v4 )
    LocalFree(v4);
  return (unsigned int)ActiveScheme;
}

```

## disassembly

```asm
0x180022914  mov     [rsp-18h+arg_0], rbx
0x180022919  push    rbp
0x18002291a  push    rsi
0x18002291b  push    rdi
0x18002291c  mov     rbp, rsp
0x18002291f  sub     rsp, 60h
0x180022923  xor     esi, esi
0x180022925  mov     [rbp+SchemePersonalityGuid], rsi
0x180022929  mov     [rbp+DcValueIndex], esi
0x18002292c  mov     [rbp+AcDefaultIndex], esi
0x18002292f  xorps   xmm0, xmm0
0x180022932  xor     eax, eax
0x180022934  movups  [rbp+var_18], xmm0
0x180022938  mov     [rbp+var_8], rax
0x18002293c  lea     r8, [rbp+var_18]
0x180022940  call    WhesvcConfigLookupValue
0x180022945  mov     ebx, eax
0x180022947  test    eax, eax
0x180022949  jns     short loc_18002296B
0x18002294b  lea     edx, [rsi+11h]; void *
0x18002294e  mov     rcx, [rbp+18h]; this
0x180022952  mov     r9d, ebx; char *
0x180022955  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\coresettinghandlers"...
0x18002295c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022961  nop
0x180022962  mov     rcx, [rbp+SchemePersonalityGuid]
0x180022966  jmp     loc_180022AF6
0x18002296b  cmp     dword ptr [rbp+var_18], 1
0x18002296f  jz      short loc_18002297D
0x180022971  mov     ebx, 80070057h
0x180022976  mov     edx, 16h
0x18002297b  jmp     short loc_18002294E
0x18002297d  lea     rax, [rbp+SchemePersonalityGuid]
0x180022981  mov     [rbp+var_30], rax
0x180022985  mov     [rbp+ActivePolicyGuid], rsi
0x180022989  mov     [rbp+var_20], 1
0x18002298d  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x180022991  xor     ecx, ecx; UserRootPowerKey
0x180022993  call    cs:__imp_PowerGetActiveScheme
0x180022999  mov     ebx, eax
0x18002299b  lea     rcx, [rbp+var_30]
0x18002299f  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800229a4  mov     rcx, [rbp+SchemePersonalityGuid]; hMem
0x1800229a8  test    ebx, ebx
0x1800229aa  jnz     loc_180022AEB
0x1800229b0  test    rcx, rcx
0x1800229b3  jz      loc_180022AF6
0x1800229b9  mov     edi, 80070000h
0x1800229be  cmp     dword ptr [rbp+var_18+8], esi
0x1800229c1  jz      loc_180022A47
0x1800229c7  lea     rax, [rbp+DcValueIndex]
0x1800229cb  mov     qword ptr [rsp+60h+DcDefaultIndex], rax; DcDefaultIndex
0x1800229d0  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x1800229d7  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800229de  mov     rdx, rcx; SchemePersonalityGuid
0x1800229e1  xor     ecx, ecx; RootPowerKey
0x1800229e3  call    cs:__imp_PowerReadDCDefaultIndex
0x1800229e9  mov     ebx, eax
0x1800229eb  test    eax, eax
0x1800229ed  jle     short loc_1800229F4
0x1800229ef  movzx   ebx, ax
0x1800229f2  or      ebx, edi
0x1800229f4  test    ebx, ebx
0x1800229f6  jns     short loc_180022A02
0x1800229f8  mov     edx, 2Ch ; ','
0x1800229fd  jmp     loc_18002294E
0x180022a02  lea     rax, [rbp+AcDefaultIndex]
0x180022a06  mov     qword ptr [rsp+60h+DcDefaultIndex], rax; AcDefaultIndex
0x180022a0b  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x180022a12  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180022a19  mov     rdx, [rbp+SchemePersonalityGuid]; SchemePersonalityGuid
0x180022a1d  xor     ecx, ecx; RootPowerKey
0x180022a1f  call    cs:__imp_PowerReadACDefaultIndex
0x180022a25  mov     ebx, eax
0x180022a27  test    eax, eax
0x180022a29  jle     short loc_180022A30
0x180022a2b  movzx   ebx, ax
0x180022a2e  or      ebx, edi
0x180022a30  test    ebx, ebx
0x180022a32  jns     short loc_180022A3E
0x180022a34  mov     edx, 34h ; '4'
0x180022a39  jmp     loc_18002294E
0x180022a3e  mov     rcx, [rbp+SchemePersonalityGuid]
0x180022a42  mov     eax, [rbp+DcValueIndex]
0x180022a45  jmp     short loc_180022A52
0x180022a47  mov     eax, 64h ; 'd'
0x180022a4c  mov     [rbp+DcValueIndex], eax
0x180022a4f  mov     [rbp+AcDefaultIndex], eax
0x180022a52  mov     [rsp+60h+DcDefaultIndex], eax; DcValueIndex
0x180022a56  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x180022a5d  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180022a64  mov     rdx, rcx; SchemeGuid
0x180022a67  xor     ecx, ecx; RootPowerKey
0x180022a69  call    cs:__imp_PowerWriteDCValueIndex
0x180022a6f  mov     ebx, eax
0x180022a71  test    eax, eax
0x180022a73  jle     short loc_180022A7A
0x180022a75  movzx   ebx, ax
0x180022a78  or      ebx, edi
0x180022a7a  test    ebx, ebx
0x180022a7c  jns     short loc_180022A88
0x180022a7e  mov     edx, 44h ; 'D'
0x180022a83  jmp     loc_18002294E
0x180022a88  mov     eax, [rbp+AcDefaultIndex]
0x180022a8b  mov     [rsp+60h+DcDefaultIndex], eax; AcValueIndex
0x180022a8f  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x180022a96  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x180022a9d  mov     rdx, [rbp+SchemePersonalityGuid]; SchemeGuid
0x180022aa1  xor     ecx, ecx; RootPowerKey
0x180022aa3  call    cs:__imp_PowerWriteACValueIndex
0x180022aa9  mov     ebx, eax
0x180022aab  test    eax, eax
0x180022aad  jle     short loc_180022AB4
0x180022aaf  movzx   ebx, ax
0x180022ab2  or      ebx, edi
0x180022ab4  test    ebx, ebx
0x180022ab6  jns     short loc_180022AC2
0x180022ab8  mov     edx, 4Bh ; 'K'
0x180022abd  jmp     loc_18002294E
0x180022ac2  mov     rdx, [rbp+SchemePersonalityGuid]; SchemeGuid
0x180022ac6  xor     ecx, ecx; UserRootPowerKey
0x180022ac8  call    cs:__imp_PowerSetActiveScheme
0x180022ace  mov     ebx, eax
0x180022ad0  test    eax, eax
0x180022ad2  jle     short loc_180022AD9
0x180022ad4  movzx   ebx, ax
0x180022ad7  or      ebx, edi
0x180022ad9  test    ebx, ebx
0x180022adb  jns     loc_180022962
0x180022ae1  mov     edx, 4Fh ; 'O'
0x180022ae6  jmp     loc_18002294E
0x180022aeb  jle     short loc_180022AF6
0x180022aed  movzx   ebx, bx
0x180022af0  or      ebx, 80070000h
0x180022af6  mov     [rbp+SchemePersonalityGuid], rsi
0x180022afa  test    rcx, rcx
0x180022afd  jz      short loc_180022B05
0x180022aff  call    cs:__imp_LocalFree
0x180022b05  mov     eax, ebx
0x180022b07  mov     rbx, [rsp+60h+arg_0]
0x180022b0f  add     rsp, 60h
0x180022b13  pop     rdi
0x180022b14  pop     rsi
0x180022b15  pop     rbp
0x180022b16  retn
```
