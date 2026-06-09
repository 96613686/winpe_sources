# CAdapter::ControlResetRecovery(void)

- ea: `0x1400a1694`
- end: `0x1400a185c`
- name: `?ControlResetRecovery@CAdapter@@QEAAHXZ`
- size: `456`
- prototype: `__int64 __fastcall(CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140077e34`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x14007a86c`
- `0x1400a1694`
- `0x1400a3da8`
- `0x1400a42c8`
- `0x1400a4374`
- `0x1400a7c70`
- `0x1400da4f0`

## import_xrefs

- `NDIS!NdisCloseConfiguration` at `0x1400a1825`
- `NDIS!NdisCloseConfiguration` at `0x1400a1825`

## pseudocode

```c
__int64 __fastcall CAdapter::ControlResetRecovery(CAdapter *this)
{
  int v2; // edx
  unsigned int v3; // edi
  unsigned int v4; // ebx
  unsigned __int64 reset_recovery_period; // rax
  unsigned int v6; // r8d
  unsigned int v8; // [rsp+30h] [rbp-50h] BYREF
  void *m_MiniportAdapterHandle; // [rsp+38h] [rbp-48h] BYREF
  NDIS_HANDLE ConfigurationHandle; // [rsp+40h] [rbp-40h]
  unsigned __int8 v11[16]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v12; // [rsp+58h] [rbp-28h]
  __int64 v13; // [rsp+68h] [rbp-18h]

  m_MiniportAdapterHandle = this->m_MiniportAdapterHandle;
  ConfigurationHandle = 0;
  v13 = 0;
  *(_OWORD *)v11 = 0;
  v8 = 40;
  v12 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      12,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  v3 = CRegistryHelper::ReadAdapterRegistryBinaries(
         (CRegistryHelper *)&m_MiniportAdapterHandle,
         L"ResetRecoveryHistory",
         &v8,
         v11);
  if ( v3 || !v8 || (v8 & 7) != 0 )
  {
    v3 = 0;
  }
  else
  {
    v4 = v8 >> 3;
    if ( (unsigned int)Feature_WifiIhvPLDRStormProtectUpdate__private_IsEnabledDeviceUsageNoInline() )
      this->m_lResetTriggerCount = v4;
    if ( v4 >= 5 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          1,
          13,
          (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
      if ( (unsigned int)Feature_WifiIhvPLDRStormProtectUpdate__private_IsEnabledDeviceUsageNoInline() )
      {
        reset_recovery_period = get_reset_recovery_period();
        CAdapter::TraceLoggingResetRecoveryStorm(this, (const unsigned __int64 *)v11, v6, reset_recovery_period);
      }
      CRegistryHelper::WriteAdapterRegistryBinaries(
        (CRegistryHelper *)&m_MiniportAdapterHandle,
        L"ResetRecoveryHistory",
        1u,
        (wchar_t *)v11);
      v3 = -1073676276;
    }
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      1,
      14,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v3);
  }
  if ( ConfigurationHandle )
    NdisCloseConfiguration(ConfigurationHandle);
  return v3;
}

```

## disassembly

```asm
0x1400a1694  mov     [rsp-28h+arg_8], rbx
0x1400a1699  mov     [rsp-28h+arg_10], rsi
0x1400a169e  push    rbp
0x1400a169f  push    rdi
0x1400a16a0  push    r13
0x1400a16a2  push    r14
0x1400a16a4  push    r15
0x1400a16a6  mov     rbp, rsp
0x1400a16a9  sub     rsp, 80h
0x1400a16b0  mov     rax, cs:__security_cookie
0x1400a16b7  xor     rax, rsp
0x1400a16ba  mov     [rbp+var_10], rax
0x1400a16be  mov     rax, [rcx+58h]
0x1400a16c2  xor     r14d, r14d
0x1400a16c5  xorps   xmm0, xmm0
0x1400a16c8  mov     [rbp+var_48], rax
0x1400a16cc  xor     eax, eax
0x1400a16ce  mov     [rbp+ConfigurationHandle], r14
0x1400a16d2  mov     [rbp+var_18], rax
0x1400a16d6  mov     rsi, rcx
0x1400a16d9  movups  xmmword ptr [rbp+var_38], xmm0
0x1400a16dd  mov     [rbp+var_50], 28h ; '('
0x1400a16e4  movups  [rbp+var_28], xmm0
0x1400a16e8  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a16ef  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400a16f6  lea     r13, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a16fd  jz      short loc_1400A172D
0x1400a16ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1706  cmp     byte ptr [rcx+29h], 5
0x1400a170a  jnb     short loc_1400A1713
0x1400a170c  cmp     [rcx+48h], r14w
0x1400a1711  jz      short loc_1400A172D
0x1400a1713  mov     rcx, [rcx+40h]
0x1400a1717  mov     r9d, 0Ch
0x1400a171d  mov     dl, 5
0x1400a171f  mov     [rsp+80h+var_60], r13
0x1400a1724  lea     r8d, [r9-0Bh]
0x1400a1728  call    WPP_RECORDER_SF_
0x1400a172d  lea     r9, [rbp+var_38]; unsigned __int8 *
0x1400a1731  lea     r8, [rbp+var_50]; unsigned int *
0x1400a1735  lea     rdx, aResetrecoveryh; "ResetRecoveryHistory"
0x1400a173c  lea     rcx, [rbp+var_48]; this
0x1400a1740  call    ?ReadAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGPEAKPEAE@Z; CRegistryHelper::ReadAdapterRegistryBinaries(ushort const *,ulong *,uchar *)
0x1400a1745  mov     edi, eax
0x1400a1747  test    eax, eax
0x1400a1749  jnz     loc_1400A17DE
0x1400a174f  mov     ebx, [rbp+var_50]
0x1400a1752  test    ebx, ebx
0x1400a1754  jz      loc_1400A17DE
0x1400a175a  test    bl, 7
0x1400a175d  jnz     short loc_1400A17DE
0x1400a175f  shr     ebx, 3
0x1400a1762  call    Feature_WifiIhvPLDRStormProtectUpdate__private_IsEnabledDeviceUsageNoInline
0x1400a1767  test    eax, eax
0x1400a1769  jz      short loc_1400A1771
0x1400a176b  mov     [rsi+15C4h], ebx
0x1400a1771  cmp     ebx, 5
0x1400a1774  jb      short loc_1400A17E1
0x1400a1776  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400a177d  jz      short loc_1400A17A0
0x1400a177f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a1786  mov     r9d, 0Dh
0x1400a178c  mov     dl, 2
0x1400a178e  mov     [rsp+80h+var_60], r13
0x1400a1793  mov     rcx, [rcx+40h]
0x1400a1797  lea     r8d, [r9-0Ch]
0x1400a179b  call    WPP_RECORDER_SF_
0x1400a17a0  call    Feature_WifiIhvPLDRStormProtectUpdate__private_IsEnabledDeviceUsageNoInline
0x1400a17a5  test    eax, eax
0x1400a17a7  jz      short loc_1400A17BD
0x1400a17a9  call    ?get_reset_recovery_period@@YA_KXZ; get_reset_recovery_period(void)
0x1400a17ae  mov     r9, rax; unsigned __int64
0x1400a17b1  lea     rdx, [rbp+var_38]; unsigned __int64 *
0x1400a17b5  mov     rcx, rsi; this
0x1400a17b8  call    ?TraceLoggingResetRecoveryStorm@CAdapter@@QEAAXPEB_KI_K@Z; CAdapter::TraceLoggingResetRecoveryStorm(unsigned __int64 const *,uint,unsigned __int64)
0x1400a17bd  lea     r9, [rbp+var_38]; unsigned __int8 *
0x1400a17c1  mov     r8d, 1; unsigned int
0x1400a17c7  lea     rdx, aResetrecoveryh; "ResetRecoveryHistory"
0x1400a17ce  lea     rcx, [rbp+var_48]; this
0x1400a17d2  call    ?WriteAdapterRegistryBinaries@CRegistryHelper@@QEAAHPEBGKPEAE@Z; CRegistryHelper::WriteAdapterRegistryBinaries(ushort const *,ulong,uchar *)
0x1400a17d7  mov     edi, 0C001000Ch
0x1400a17dc  jmp     short loc_1400A17E1
0x1400a17de  mov     edi, r14d
0x1400a17e1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x1400a17e8  jz      short loc_1400A181C
0x1400a17ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a17f1  cmp     byte ptr [rcx+29h], 5
0x1400a17f5  jnb     short loc_1400A17FE
0x1400a17f7  cmp     [rcx+48h], r14w
0x1400a17fc  jz      short loc_1400A181C
0x1400a17fe  mov     rcx, [rcx+40h]
0x1400a1802  mov     r9d, 0Eh
0x1400a1808  mov     [rsp+80h+var_58], edi
0x1400a180c  mov     dl, 5
0x1400a180e  mov     [rsp+80h+var_60], r13
0x1400a1813  lea     r8d, [r9-0Dh]
0x1400a1817  call    WPP_RECORDER_SF_D
0x1400a181c  mov     rcx, [rbp+ConfigurationHandle]; ConfigurationHandle
0x1400a1820  test    rcx, rcx
0x1400a1823  jz      short loc_1400A1831
0x1400a1825  call    cs:__imp_NdisCloseConfiguration
0x1400a182c  nop     dword ptr [rax+rax+00h]
0x1400a1831  mov     eax, edi
0x1400a1833  mov     rcx, [rbp+var_10]
0x1400a1837  xor     rcx, rsp; StackCookie
0x1400a183a  call    __security_check_cookie
0x1400a183f  lea     r11, [rsp+80h+var_s0]
0x1400a1847  mov     rbx, [r11+38h]
0x1400a184b  mov     rsi, [r11+40h]
0x1400a184f  mov     rsp, r11
0x1400a1852  pop     r15
0x1400a1854  pop     r14
0x1400a1856  pop     r13
0x1400a1858  pop     rdi
0x1400a1859  pop     rbp
0x1400a185a  retn
```
