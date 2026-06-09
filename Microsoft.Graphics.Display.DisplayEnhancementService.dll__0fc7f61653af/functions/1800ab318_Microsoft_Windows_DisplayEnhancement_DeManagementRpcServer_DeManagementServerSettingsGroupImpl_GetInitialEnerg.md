# Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl::GetInitialEnergySaverBrightnessMultiplierGuidValue(void)

- ea: `0x1800ab318`
- end: `0x1800ab503`
- name: `?GetInitialEnergySaverBrightnessMultiplierGuidValue@DeManagementServerSettingsGroupImpl@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@AEAAMXZ`
- size: `491`
- prototype: `float __fastcall(Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800bd520`

## callees

- `0x18000fa0c`
- `0x180037fbc`
- `0x18006ce0c`
- `0x1800ab318`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800ab369`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x1800ab369`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab435`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab435`
- `POWRPROF!PowerReadDCValue` at `0x1800ab3e0`
- `POWRPROF!PowerReadDCValue` at `0x1800ab3e0`

## string_xrefs

- `0x1800ab37e`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`
- `0x1800ab3f5`: `onecoreuap\drivers\mobilepc\displayenhancement\service\demanagement\server\lib\demanagementserversettingsgroup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
float __fastcall Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl::GetInitialEnergySaverBrightnessMultiplierGuidValue(
        Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroupImpl *this)
{
  char v1; // si
  float v2; // xmm7_4
  char v3; // di
  DWORD ActiveScheme; // eax
  DWORD v5; // eax
  int v6; // edx
  int v7; // r8d
  const char *v8; // r9
  float v9; // xmm6_4
  GUID *v10; // rcx
  float v11; // xmm6_4
  unsigned int Type; // [rsp+20h] [rbp-98h]
  unsigned int Typea; // [rsp+20h] [rbp-98h]
  int v15; // [rsp+40h] [rbp-78h]
  double v16; // [rsp+48h] [rbp-70h]
  GUID *SchemeGuid; // [rsp+60h] [rbp-58h] BYREF
  GUID **p_SchemeGuid; // [rsp+68h] [rbp-50h] BYREF
  GUID *v19; // [rsp+70h] [rbp-48h] BYREF
  char v20; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  char v22; // [rsp+C0h] [rbp+8h]
  int Buffer; // [rsp+C8h] [rbp+10h] BYREF
  float v24; // [rsp+D0h] [rbp+18h]
  DWORD BufferSize; // [rsp+D8h] [rbp+20h] BYREF

  v22 = (char)this;
  v1 = (char)this;
  v2 = FLOAT_1_0;
  v24 = 1.0;
  SchemeGuid = 0;
  p_SchemeGuid = &SchemeGuid;
  v19 = 0;
  v3 = 1;
  v20 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &v19);
  try
  {
    if ( ActiveScheme )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3E3,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagemen"
                      "tserversettingsgroup.cpp",
        (const char *)ActiveScheme,
        Type);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_SchemeGuid);
    Buffer = 0;
    BufferSize = 4;
    v5 = PowerReadDCValue(
           0,
           SchemeGuid,
           &GUID_ENERGY_SAVER_SUBGROUP,
           &GUID_ENERGY_SAVER_BRIGHTNESS,
           0,
           (PUCHAR)&Buffer,
           &BufferSize);
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x3ED,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagemen"
                      "tserversettingsgroup.cpp",
        (const char *)v5,
        Typea);
    v9 = (float)Buffer / 100.0;
    v24 = v9;
    v10 = SchemeGuid;
    SchemeGuid = 0;
    if ( v10 )
      LocalFree(v10);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3F1,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\demanagement\\server\\lib\\demanagements"
                    "erversettingsgroup.cpp",
      v8);
    v3 = 1;
    v1 = v22;
    v9 = v24;
    v2 = FLOAT_1_0;
  }
  v11 = fminf(fmaxf(v9, 0.001), v2);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
    || (LOBYTE(v6) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(v6) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 24) )
    v3 = 0;
  if ( (_BYTE)v6 || v3 )
  {
    v16 = v11;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_sgq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      v7,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      Typea,
      5,
      47,
      &WPP_657806f372a330d9e5ead528bff1261b_Traceguids,
      v15,
      SLOBYTE(v16),
      v1);
  }
  return v11;
}

```

## disassembly

```asm
0x1800ab318  mov     r11, rsp
0x1800ab31b  mov     [r11+8], rcx
0x1800ab31f  push    rbx
0x1800ab320  push    rsi
0x1800ab321  push    rdi
0x1800ab322  sub     rsp, 0A0h
0x1800ab329  movaps  xmmword ptr [r11-28h], xmm6
0x1800ab32e  movaps  xmmword ptr [r11-38h], xmm7
0x1800ab333  mov     rsi, rcx
0x1800ab336  movss   xmm7, cs:__real@3f800000
0x1800ab33e  mov     [rsp+0B8h+arg_10], 3F800000h
0x1800ab349  xor     ebx, ebx
0x1800ab34b  mov     [r11-58h], rbx
0x1800ab34f  lea     rax, [r11-58h]
0x1800ab353  mov     [r11-50h], rax
0x1800ab357  mov     [r11-48h], rbx
0x1800ab35b  mov     dil, 1
0x1800ab35e  mov     [rsp+0B8h+var_40], dil
0x1800ab363  lea     rdx, [r11-48h]; ActivePolicyGuid
0x1800ab367  xor     ecx, ecx; UserRootPowerKey
0x1800ab369  call    cs:__imp_PowerGetActiveScheme
0x1800ab36f  mov     rcx, [rsp+0B8h]; this
0x1800ab377  test    eax, eax
0x1800ab379  jz      short loc_1800AB390
0x1800ab37b  mov     r9d, eax; char *
0x1800ab37e  lea     r8, aOnecoreuapDriv_8; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800ab385  mov     edx, 3E3h; void *
0x1800ab38a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ab390  lea     rcx, [rsp+0B8h+var_50]
0x1800ab395  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800ab39a  mov     [rsp+0B8h+arg_8], ebx
0x1800ab3a1  mov     [rsp+0B8h+arg_18], 4
0x1800ab3ac  lea     rax, [rsp+0B8h+arg_18]
0x1800ab3b4  mov     [rsp+0B8h+BufferSize], rax; BufferSize
0x1800ab3b9  lea     rax, [rsp+0B8h+arg_8]
0x1800ab3c1  mov     [rsp+0B8h+Buffer], rax; Buffer
0x1800ab3c6  mov     [rsp+0B8h+Type], rbx; unsigned int
0x1800ab3cb  lea     r9, GUID_ENERGY_SAVER_BRIGHTNESS; PowerSettingGuid
0x1800ab3d2  lea     r8, GUID_ENERGY_SAVER_SUBGROUP; SubGroupOfPowerSettingsGuid
0x1800ab3d9  mov     rdx, [rsp+0B8h+SchemeGuid]; SchemeGuid
0x1800ab3de  xor     ecx, ecx; RootPowerKey
0x1800ab3e0  call    cs:__imp_PowerReadDCValue
0x1800ab3e6  mov     rcx, [rsp+0B8h]; this
0x1800ab3ee  test    eax, eax
0x1800ab3f0  jz      short loc_1800AB406
0x1800ab3f2  mov     r9d, eax; char *
0x1800ab3f5  lea     r8, aOnecoreuapDriv_8; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800ab3fc  mov     edx, 3EDh; void *
0x1800ab401  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800ab406  mov     eax, [rsp+0B8h+arg_8]
0x1800ab40d  xorps   xmm6, xmm6
0x1800ab410  cvtsi2ss xmm6, rax
0x1800ab415  divss   xmm6, cs:__real@42c80000
0x1800ab41d  movss   [rsp+0B8h+arg_10], xmm6
0x1800ab426  mov     rcx, [rsp+0B8h+SchemeGuid]; hMem
0x1800ab42b  mov     [rsp+0B8h+SchemeGuid], rbx
0x1800ab430  test    rcx, rcx
0x1800ab433  jz      short loc_1800AB43C
0x1800ab435  call    cs:__imp_LocalFree
0x1800ab43b  nop
0x1800ab43c  jmp     short loc_1800AB45C
0x1800ab43e  xor     ebx, ebx
0x1800ab440  mov     dil, 1
0x1800ab443  mov     rsi, [rsp+0B8h+arg_0]
0x1800ab44b  movss   xmm6, [rsp+0B8h+arg_10]
0x1800ab454  movss   xmm7, cs:__real@3f800000
0x1800ab45c  maxss   xmm6, cs:__real@3a83126f
0x1800ab464  minss   xmm6, xmm7
0x1800ab468  lea     rax, WPP_GLOBAL_Control
0x1800ab46f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab476  cmp     rcx, rax
0x1800ab479  jz      short loc_1800AB48A
0x1800ab47b  test    byte ptr [rcx+1Ch], 10h
0x1800ab47f  jz      short loc_1800AB48A
0x1800ab481  cmp     byte ptr [rcx+19h], 5
0x1800ab485  mov     dl, dil
0x1800ab488  jnb     short loc_1800AB48C
0x1800ab48a  mov     dl, bl; int
0x1800ab48c  lea     rax, WPP_RECORDER_INITIALIZED
0x1800ab493  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800ab49a  jz      short loc_1800AB4A2
0x1800ab49c  cmp     [rcx+30h], bx
0x1800ab4a0  jnz     short loc_1800AB4A5
0x1800ab4a2  mov     dil, bl
0x1800ab4a5  test    dl, dl
0x1800ab4a7  jnz     short loc_1800AB4AE
0x1800ab4a9  test    dil, dil
0x1800ab4ac  jz      short loc_1800AB4E7
0x1800ab4ae  cvtps2pd xmm1, xmm6
0x1800ab4b1  mov     qword ptr [rsp+0B8h+var_68], rsi; char
0x1800ab4b6  movsd   qword ptr [rsp+0B8h+var_70], xmm1; char
0x1800ab4bc  lea     rax, WPP_657806f372a330d9e5ead528bff1261b_Traceguids
0x1800ab4c3  mov     [rsp+0B8h+MessageGuid], rax; MessageGuid
0x1800ab4c8  mov     word ptr [rsp+0B8h+BufferSize], 2Fh ; '/'; __int16
0x1800ab4cf  mov     dword ptr [rsp+0B8h+Buffer], 5; int
0x1800ab4d7  mov     r9, [rcx+28h]; int
0x1800ab4db  mov     r8b, dil; int
0x1800ab4de  mov     rcx, [rcx+10h]; int
0x1800ab4e2  call    WPP_RECORDER_AND_TRACE_SF_sgq
0x1800ab4e7  movaps  xmm0, xmm6
0x1800ab4ea  lea     r11, [rsp+0B8h+var_18]
0x1800ab4f2  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ab4f7  movaps  xmm7, xmmword ptr [r11-20h]
0x1800ab4fc  mov     rsp, r11
0x1800ab4ff  pop     rdi
0x1800ab500  pop     rsi
0x1800ab501  pop     rbx
0x1800ab502  retn
```
