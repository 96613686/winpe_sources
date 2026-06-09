# SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_GetCurrentPowerOverlay(void)

- ea: `0x18003e6bc`
- end: `0x18003e7f2`
- name: `?_GetCurrentPowerOverlay@CPowerMode@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJXZ`
- size: `310`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e630`

## callees

- `0x180009190`
- `0x18000a0e1`
- `0x180012c58`
- `0x18003e6bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e6ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e6ea`
- `POWRPROF!PowerGetUserConfiguredDCPowerMode` at `0x18003e709`
- `POWRPROF!PowerGetUserConfiguredDCPowerMode` at `0x18003e709`
- `POWRPROF!PowerGetUserConfiguredACPowerMode` at `0x18003e701`
- `POWRPROF!PowerGetUserConfiguredACPowerMode` at `0x18003e701`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CPowerMode::_GetCurrentPowerOverlay(
        SystemSettings::BatterySaverOneCoreDataModel::CPowerMode *this)
{
  bool v2; // zf
  int UserConfiguredACPowerMode; // eax
  unsigned int v4; // ebx
  int v5; // eax
  GUID *v6; // rdx
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+20h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+28h] [rbp-20h] BYREF

  Buf1 = 0;
  EnterCriticalSection(&SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection);
  v2 = *((_BYTE *)this + 380) == 1;
  v8 = &SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection;
  if ( v2 )
    UserConfiguredACPowerMode = PowerGetUserConfiguredACPowerMode(&Buf1);
  else
    UserConfiguredACPowerMode = PowerGetUserConfiguredDCPowerMode(&Buf1);
  v4 = UserConfiguredACPowerMode;
  if ( UserConfiguredACPowerMode > 0 )
    v4 = (unsigned __int16)UserConfiguredACPowerMode | 0x80070000;
  if ( *((_DWORD *)this + 90) == 1 )
  {
    if ( !memcmp_0(&Buf1, &GUID_POWER_MODE_NONE, 0x10u) )
      goto LABEL_9;
    v6 = &GUID_POWER_MODE_PERFORMANCE;
  }
  else
  {
    if ( *((_DWORD *)this + 90) != 2 )
      goto LABEL_15;
    if ( !memcmp_0(&Buf1, &GUID_POWER_MODE_BEST_EFFICIENCY, 0x10u) )
    {
LABEL_9:
      v5 = 100;
LABEL_19:
      *((_DWORD *)this + 89) = v5;
      goto LABEL_15;
    }
    v6 = &GUID_POWER_MODE_NONE;
  }
  if ( !memcmp_0(&Buf1, v6, 0x10u) )
  {
    v5 = 200;
    goto LABEL_19;
  }
  if ( !memcmp_0(&Buf1, &GUID_POWER_MODE_BEST_PERFORMANCE, 0x10u) )
  {
    v5 = 300;
    goto LABEL_19;
  }
  v4 = 1;
LABEL_15:
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v8);
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v8);
  return v4;
}

```

## disassembly

```asm
0x18003e6bc  push    rbp
0x18003e6be  push    rbx
0x18003e6bf  push    rsi
0x18003e6c0  push    rdi
0x18003e6c1  mov     rbp, rsp
0x18003e6c4  sub     rsp, 48h
0x18003e6c8  mov     rax, cs:__security_cookie
0x18003e6cf  xor     rax, rsp
0x18003e6d2  mov     [rbp+var_10], rax
0x18003e6d6  mov     rsi, rcx
0x18003e6d9  lea     rbx, ?_SliderPositionCritSection@BatterySaverOneCoreDataModel@SystemSettings@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SystemSettings::BatterySaverOneCoreDataModel::_SliderPositionCritSection
0x18003e6e0  xorps   xmm0, xmm0
0x18003e6e3  mov     rcx, rbx; lpCriticalSection
0x18003e6e6  movups  [rbp+Buf1], xmm0
0x18003e6ea  call    cs:__imp_EnterCriticalSection
0x18003e6f0  cmp     byte ptr [rsi+17Ch], 1
0x18003e6f7  lea     rcx, [rbp+Buf1]
0x18003e6fb  mov     [rbp+var_28], rbx
0x18003e6ff  jnz     short loc_18003E709
0x18003e701  call    cs:__imp_PowerGetUserConfiguredACPowerMode
0x18003e707  jmp     short loc_18003E70F
0x18003e709  call    cs:__imp_PowerGetUserConfiguredDCPowerMode
0x18003e70f  mov     ebx, eax
0x18003e711  test    eax, eax
0x18003e713  jle     short loc_18003E71E
0x18003e715  movzx   ebx, ax
0x18003e718  or      ebx, 80070000h
0x18003e71e  mov     ecx, [rsi+168h]
0x18003e724  sub     ecx, 1
0x18003e727  jz      loc_18003E7B9
0x18003e72d  cmp     ecx, 1
0x18003e730  jnz     short loc_18003E790
0x18003e732  lea     edi, [rcx+0Fh]
0x18003e735  mov     r8d, edi; Size
0x18003e738  lea     rdx, GUID_POWER_MODE_BEST_EFFICIENCY; Buf2
0x18003e73f  lea     rcx, [rbp+Buf1]; Buf1
0x18003e743  call    memcmp_0
0x18003e748  test    eax, eax
0x18003e74a  jnz     short loc_18003E756
0x18003e74c  mov     eax, 64h ; 'd'
0x18003e751  jmp     loc_18003E7EA
0x18003e756  lea     rdx, GUID_POWER_MODE_NONE; Buf2
0x18003e75d  mov     r8, rdi; Size
0x18003e760  lea     rcx, [rbp+Buf1]; Buf1
0x18003e764  call    memcmp_0
0x18003e769  test    eax, eax
0x18003e76b  jnz     short loc_18003E774
0x18003e76d  mov     eax, 0C8h
0x18003e772  jmp     short loc_18003E7EA
0x18003e774  mov     r8, rdi; Size
0x18003e777  lea     rdx, GUID_POWER_MODE_BEST_PERFORMANCE; Buf2
0x18003e77e  lea     rcx, [rbp+Buf1]; Buf1
0x18003e782  call    memcmp_0
0x18003e787  test    eax, eax
0x18003e789  jz      short loc_18003E7E5
0x18003e78b  mov     ebx, 1
0x18003e790  lea     rcx, [rbp+var_28]; this
0x18003e794  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e799  lea     rcx, [rbp+var_28]; this
0x18003e79d  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18003e7a2  mov     eax, ebx
0x18003e7a4  mov     rcx, [rbp+var_10]
0x18003e7a8  xor     rcx, rsp; StackCookie
0x18003e7ab  call    __security_check_cookie
0x18003e7b0  add     rsp, 48h
0x18003e7b4  pop     rdi
0x18003e7b5  pop     rsi
0x18003e7b6  pop     rbx
0x18003e7b7  pop     rbp
0x18003e7b8  retn
0x18003e7b9  mov     edi, 10h
0x18003e7be  lea     rdx, GUID_POWER_MODE_NONE; Buf2
0x18003e7c5  mov     r8d, edi; Size
0x18003e7c8  lea     rcx, [rbp+Buf1]; Buf1
0x18003e7cc  call    memcmp_0
0x18003e7d1  test    eax, eax
0x18003e7d3  jz      loc_18003E74C
0x18003e7d9  lea     rdx, GUID_POWER_MODE_PERFORMANCE
0x18003e7e0  jmp     loc_18003E75D
0x18003e7e5  mov     eax, 12Ch
0x18003e7ea  mov     [rsi+164h], eax
0x18003e7f0  jmp     short loc_18003E790
```
