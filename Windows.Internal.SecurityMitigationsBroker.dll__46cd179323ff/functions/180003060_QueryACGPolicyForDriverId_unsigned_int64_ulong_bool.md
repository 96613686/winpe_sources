# QueryACGPolicyForDriverId(unsigned __int64,ulong,bool *)

- ea: `0x180003060`
- end: `0x180003272`
- name: `?QueryACGPolicyForDriverId@@YAJ_KKPEA_N@Z`
- size: `530`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002288`

## callees

- `0x1800025f4`
- `0x1800026f4`
- `0x180003060`
- `0x18000342c`
- `0x18000448c`
- `0x180004724`
- `0x180006980`

## pseudocode

```c
__int64 __fastcall QueryACGPolicyForDriverId(unsigned __int64 a1, unsigned int a2, bool *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // r8
  int DisplayDriverCapabilities; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // ebx
  bool v15; // al
  char v16; // cl
  int v17; // ecx
  int v18; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v21[16]; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 *v22; // [rsp+58h] [rbp-28h]
  __int64 v23; // [rsp+60h] [rbp-20h]
  int *v24; // [rsp+68h] [rbp-18h]
  __int64 v25; // [rsp+70h] [rbp-10h]

  *a3 = 1;
  v18 = 0;
  if ( (int)GetBOOL((__int64 *)SettingStore::IEVALUE_CodeIntegrity_DisableACGDowngradeForUMDCompat[0], &v18) < 0 || v18 )
  {
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
    {
      LODWORD(v19) = a2;
      v22 = &v20;
      v20 = a1;
      v24 = (int *)&v19;
      v23 = 8;
      v25 = 4;
      McGenEventWrite_EventWriteTransfer(v6, ProcessRemoteDowngradeDisabled, v7, 3, v21);
    }
    v17 = 4;
    goto LABEL_18;
  }
  v18 = 0;
  if ( (int)GetBOOL((__int64 *)SettingStore::IEVALUE_Browser_UseSWRender[0], &v18) < 0 || v18 )
  {
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
    {
      LODWORD(v19) = a2;
      v22 = &v20;
      v20 = a1;
      v24 = (int *)&v19;
      v23 = 8;
      v25 = 4;
      McGenEventWrite_EventWriteTransfer(v8, SoftwareRenderingPolicySet, v9, 3, v21);
    }
    v17 = 6;
LABEL_18:
    SecurityBrokerTelemetry::LogACGDxDriverTelemetry(v17);
    v16 = 1;
LABEL_19:
    CacheACGStatusForTroubleshooting(v16);
    return 0;
  }
  v18 = 0;
  DisplayDriverCapabilities = GetDisplayDriverCapabilities(a1, a2, (enum _ACGLockDownState *)&v18);
  v13 = DisplayDriverCapabilities;
  if ( DisplayDriverCapabilities >= 0 )
  {
    v15 = v18 != 2;
    *a3 = v18 != 2;
    if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
    {
      LODWORD(v19) = v15;
      v20 = a1;
      v22 = &v20;
      v24 = (int *)&v19;
      v23 = 8;
      v25 = 4;
      McGenEventWrite_EventWriteTransfer(v11, DriverACGState, v12, 3, v21);
    }
    SecurityBrokerTelemetry::LogACGDxDriverTelemetry(v18);
    v16 = *a3;
    goto LABEL_19;
  }
  if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 2) != 0 )
  {
    v18 = DisplayDriverCapabilities;
    v19 = a1;
    v22 = &v19;
    v23 = 8;
    v24 = &v18;
    v25 = 4;
    McGenEventWrite_EventWriteTransfer(v11, GetDisplayDriverCapabilitiesFailed, v12, 3, v21);
  }
  return v13;
}

```

## disassembly

```asm
0x180003060  push    rbp
0x180003062  push    rbx
0x180003063  push    rsi
0x180003064  push    rdi
0x180003065  push    r14
0x180003067  mov     rbp, rsp
0x18000306a  sub     rsp, 80h
0x180003071  mov     rax, cs:__security_cookie
0x180003078  xor     rax, rsp
0x18000307b  mov     [rbp+var_8], rax
0x18000307f  mov     ebx, edx
0x180003081  mov     byte ptr [r8], 1
0x180003085  mov     rdi, rcx
0x180003088  lea     rdx, [rbp+var_50]
0x18000308c  mov     rcx, cs:?IEVALUE_CodeIntegrity_DisableACGDowngradeForUMDCompat@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_CodeIntegrity_DisableACGDowngradeForUMDCompat
0x180003093  xor     r14d, r14d
0x180003096  mov     [rbp+var_50], r14d
0x18000309a  mov     rsi, r8
0x18000309d  call    GetBOOL
0x1800030a2  test    eax, eax
0x1800030a4  js      loc_1800031FA
0x1800030aa  cmp     [rbp+var_50], r14d
0x1800030ae  jnz     loc_1800031FA
0x1800030b4  mov     rcx, cs:?IEVALUE_Browser_UseSWRender@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Browser_UseSWRender
0x1800030bb  lea     rdx, [rbp+var_50]
0x1800030bf  mov     [rbp+var_50], r14d
0x1800030c3  call    GetBOOL
0x1800030c8  test    eax, eax
0x1800030ca  js      loc_1800031A8
0x1800030d0  cmp     [rbp+var_50], r14d
0x1800030d4  jnz     loc_1800031A8
0x1800030da  lea     r8, [rbp+var_50]; enum _ACGLockDownState *
0x1800030de  mov     [rbp+var_50], r14d
0x1800030e2  mov     edx, ebx; unsigned int
0x1800030e4  mov     rcx, rdi; unsigned __int64
0x1800030e7  call    ?GetDisplayDriverCapabilities@@YAJ_KKPEAW4_ACGLockDownState@@@Z; GetDisplayDriverCapabilities(unsigned __int64,ulong,_ACGLockDownState *)
0x1800030ec  mov     ebx, eax
0x1800030ee  test    eax, eax
0x1800030f0  jns     short loc_180003142
0x1800030f2  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 2
0x1800030f9  jz      short loc_18000313B
0x1800030fb  mov     [rbp+var_50], eax
0x1800030fe  lea     r9d, [r14+3]
0x180003102  lea     rax, [rbp+var_48]
0x180003106  mov     [rbp+var_48], rdi
0x18000310a  mov     [rbp+var_28], rax
0x18000310e  lea     rdx, GetDisplayDriverCapabilitiesFailed
0x180003115  lea     rax, [rbp+var_50]
0x180003119  mov     [rbp+var_20], 8
0x180003121  mov     [rbp+var_18], rax
0x180003125  lea     rax, [rbp+var_38]
0x180003129  mov     [rsp+80h+var_60], rax
0x18000312e  mov     [rbp+var_10], 4
0x180003136  call    McGenEventWrite_EventWriteTransfer
0x18000313b  mov     eax, ebx
0x18000313d  jmp     loc_180003258
0x180003142  cmp     [rbp+var_50], 2
0x180003146  setnz   al
0x180003149  mov     [rsi], al
0x18000314b  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 4
0x180003152  jz      short loc_180003199
0x180003154  movzx   eax, al
0x180003157  lea     rdx, DriverACGState
0x18000315e  mov     dword ptr [rbp+var_48], eax
0x180003161  mov     r9d, 3
0x180003167  lea     rax, [rbp+var_40]
0x18000316b  mov     [rbp+var_40], rdi
0x18000316f  mov     [rbp+var_28], rax
0x180003173  lea     rax, [rbp+var_48]
0x180003177  mov     [rbp+var_18], rax
0x18000317b  lea     rax, [rbp+var_38]
0x18000317f  mov     [rsp+80h+var_60], rax
0x180003184  mov     [rbp+var_20], 8
0x18000318c  mov     [rbp+var_10], 4
0x180003194  call    McGenEventWrite_EventWriteTransfer
0x180003199  mov     ecx, [rbp+var_50]; int
0x18000319c  call    ?LogACGDxDriverTelemetry@SecurityBrokerTelemetry@@SAXH@Z; SecurityBrokerTelemetry::LogACGDxDriverTelemetry(int)
0x1800031a1  mov     cl, [rsi]
0x1800031a3  jmp     loc_180003251
0x1800031a8  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 4
0x1800031af  jz      short loc_1800031F3
0x1800031b1  lea     rax, [rbp+var_40]
0x1800031b5  mov     dword ptr [rbp+var_48], ebx
0x1800031b8  mov     [rbp+var_28], rax
0x1800031bc  lea     rdx, SoftwareRenderingPolicySet
0x1800031c3  lea     rax, [rbp+var_48]
0x1800031c7  mov     [rbp+var_40], rdi
0x1800031cb  mov     [rbp+var_18], rax
0x1800031cf  mov     r9d, 3
0x1800031d5  lea     rax, [rbp+var_38]
0x1800031d9  mov     [rbp+var_20], 8
0x1800031e1  mov     [rsp+80h+var_60], rax
0x1800031e6  mov     [rbp+var_10], 4
0x1800031ee  call    McGenEventWrite_EventWriteTransfer
0x1800031f3  mov     ecx, 6
0x1800031f8  jmp     short loc_18000324A
0x1800031fa  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 4
0x180003201  jz      short loc_180003245
0x180003203  lea     rax, [rbp+var_40]
0x180003207  mov     dword ptr [rbp+var_48], ebx
0x18000320a  mov     [rbp+var_28], rax
0x18000320e  lea     rdx, ProcessRemoteDowngradeDisabled
0x180003215  lea     rax, [rbp+var_48]
0x180003219  mov     [rbp+var_40], rdi
0x18000321d  mov     [rbp+var_18], rax
0x180003221  mov     r9d, 3
0x180003227  lea     rax, [rbp+var_38]
0x18000322b  mov     [rbp+var_20], 8
0x180003233  mov     [rsp+80h+var_60], rax
0x180003238  mov     [rbp+var_10], 4
0x180003240  call    McGenEventWrite_EventWriteTransfer
0x180003245  mov     ecx, 4; int
0x18000324a  call    ?LogACGDxDriverTelemetry@SecurityBrokerTelemetry@@SAXH@Z; SecurityBrokerTelemetry::LogACGDxDriverTelemetry(int)
0x18000324f  mov     cl, 1; bool
0x180003251  call    ?CacheACGStatusForTroubleshooting@@YAX_N@Z; CacheACGStatusForTroubleshooting(bool)
0x180003256  xor     eax, eax
0x180003258  mov     rcx, [rbp+var_8]
0x18000325c  xor     rcx, rsp; StackCookie
0x18000325f  call    __security_check_cookie
0x180003264  add     rsp, 80h
0x18000326b  pop     r14
0x18000326d  pop     rdi
0x18000326e  pop     rsi
0x18000326f  pop     rbx
0x180003270  pop     rbp
0x180003271  retn
```
