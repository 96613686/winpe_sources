# BthSyncWithPolicyManager

- ea: `0x180030dd4`
- end: `0x180031036`
- name: `BthSyncWithPolicyManager`
- size: `610`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800100c0`
- `0x18001c534`

## callees

- `0x180002470`
- `0x18000247c`
- `0x180002488`
- `0x1800024ac`
- `0x180030a44`
- `0x180030b50`
- `0x180030c50`
- `0x180030dd4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180030ef3`
- `ntdll!RtlInitUnicodeString` at `0x180030ef3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030fa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030fa2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031019`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031019`
- `policymanager!PolicyManager_GetPolicyString` at `0x180030ead`
- `policymanager!PolicyManager_GetPolicyString` at `0x180030f19`
- `policymanager!PolicyManager_GetPolicyString` at `0x180030f63`
- `policymanager!PolicyManager_GetPolicyString` at `0x180030ead`
- `policymanager!PolicyManager_GetPolicyString` at `0x180030f19`
- `policymanager!PolicyManager_GetPolicyString` at `0x180030f63`
- `policymanager!PolicyManager_FreeStringValue` at `0x180030f01`
- `policymanager!PolicyManager_FreeStringValue` at `0x180030f4b`
- `policymanager!PolicyManager_FreeStringValue` at `0x180030f95`
- `policymanager!PolicyManager_FreeStringValue` at `0x180030f01`
- `policymanager!PolicyManager_FreeStringValue` at `0x180030f4b`
- `policymanager!PolicyManager_FreeStringValue` at `0x180030f95`

## string_xrefs

- `0x180030f55`: `ServicesAllowedList`

## pseudocode

```c
__int64 BthSyncWithPolicyManager()
{
  wchar_t *v0; // rdi
  __int64 v1; // rbx
  WCHAR *v2; // rsi
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int128 v6; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  __int128 v8; // [rsp+40h] [rbp-30h] BYREF
  struct _GUID *v9[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v10; // [rsp+60h] [rbp-10h]
  unsigned int v11; // [rsp+90h] [rbp+20h] BYREF
  wchar_t *Source; // [rsp+98h] [rbp+28h] BYREF

  Source = 0;
  memset_0(&v6, 0, 0x50u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 1u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 2u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 4u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 8u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 0x10u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 0x20u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 0x200u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 0x400u);
  BthReadPolicyManagerPolicyValue((__int64)&v6, 0x800u);
  if ( (int)PolicyManager_GetPolicyString(L"Bluetooth", L"LocalDeviceName", &Source) >= 0 )
  {
    v0 = Source;
    v1 = -1;
    do
      ++v1;
    while ( Source[v1] );
    v2 = (WCHAR *)o_malloc_0(2 * v1 + 2);
    if ( !wcscpy_s(v2, v1 + 1, v0) )
    {
      RtlInitUnicodeString((PUNICODE_STRING)&DestinationString.Buffer, v2);
      DWORD1(v10) |= 0x40u;
    }
    PolicyManager_FreeStringValue(Source);
  }
  if ( (int)PolicyManager_GetPolicyString(L"Bluetooth", L"DevicesAllowedList", &Source) >= 0 )
  {
    v11 = 0;
    if ( (int)TokenListToBthAddrArray(Source, v3, (void **)&v8 + 1, &v11) >= 0 )
    {
      DWORD1(v10) |= 0x80u;
      DWORD2(v10) = v11;
    }
    PolicyManager_FreeStringValue(Source);
  }
  if ( (int)PolicyManager_GetPolicyString(L"Bluetooth", L"ServicesAllowedList", &Source) >= 0 )
  {
    v11 = 0;
    if ( (int)TokenListToGuidArray(Source, v4, v9, &v11) >= 0 )
    {
      DWORD1(v10) |= 0x100u;
      HIDWORD(v10) = v11;
    }
    PolicyManager_FreeStringValue(Source);
  }
  EnterCriticalSection(&g_PolicyLock);
  if ( *(_QWORD *)&ymmword_180044A20.m256_f32[4] )
    free(*(void **)&ymmword_180044A20.m256_f32[4]);
  if ( *(_QWORD *)&ymmword_180044A20.m256_f32[6] )
    free(*(void **)&ymmword_180044A20.m256_f32[6]);
  if ( Src )
    free(Src);
  g_Policies = v6;
  *(_OWORD *)&ymmword_180044A20.m256_f32[4] = v8;
  *(struct _UNICODE_STRING *)ymmword_180044A20.m256_f32 = DestinationString;
  xmmword_180044A50 = v10;
  *(_OWORD *)&Src = *(_OWORD *)v9;
  LeaveCriticalSection(&g_PolicyLock);
  return 0;
}

```

## disassembly

```asm
0x180030dd4  mov     [rsp-18h+arg_10], rbx
0x180030dd9  mov     [rsp-18h+arg_18], rsi
0x180030dde  push    rbp
0x180030ddf  push    rdi
0x180030de0  push    r14
0x180030de2  mov     rbp, rsp
0x180030de5  sub     rsp, 70h
0x180030de9  xor     r14d, r14d
0x180030dec  lea     rcx, [rbp+var_50]; void *
0x180030df0  xor     edx, edx; Val
0x180030df2  mov     [rbp+Source], r14
0x180030df6  lea     r8d, [r14+50h]; Size
0x180030dfa  call    memset_0
0x180030dff  lea     r8, [rbp+var_50]
0x180030e03  lea     edx, [r14+1]
0x180030e07  lea     rcx, [rbp+var_50]
0x180030e0b  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e10  lea     r8, [rbp+var_50+4]
0x180030e14  lea     edx, [r14+2]
0x180030e18  lea     rcx, [rbp+var_50]
0x180030e1c  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e21  lea     r8, [rbp+var_50+8]
0x180030e25  lea     edx, [r14+4]
0x180030e29  lea     rcx, [rbp+var_50]
0x180030e2d  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e32  lea     r8, [rbp+var_50+0Ch]
0x180030e36  lea     edx, [r14+8]
0x180030e3a  lea     rcx, [rbp+var_50]
0x180030e3e  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e43  lea     r8, [rbp+DestinationString]
0x180030e47  lea     edx, [r14+10h]
0x180030e4b  lea     rcx, [rbp+var_50]
0x180030e4f  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e54  lea     r8, [rbp+DestinationString+4]
0x180030e58  lea     edx, [r14+20h]
0x180030e5c  lea     rcx, [rbp+var_50]
0x180030e60  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e65  lea     r8, [rbp+var_20+8]
0x180030e69  mov     edx, 200h
0x180030e6e  lea     rcx, [rbp+var_50]
0x180030e72  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e77  lea     r8, [rbp+var_20+0Ch]
0x180030e7b  mov     edx, 400h
0x180030e80  lea     rcx, [rbp+var_50]
0x180030e84  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e89  lea     r8, [rbp+var_10]
0x180030e8d  mov     edx, 800h
0x180030e92  lea     rcx, [rbp+var_50]
0x180030e96  call    ?BthReadPolicyManagerPolicyValue@@YAXPEAUPolicies@@W4BthPolicy@@PEAH@Z; BthReadPolicyManagerPolicyValue(Policies *,BthPolicy,int *)
0x180030e9b  lea     r8, [rbp+Source]
0x180030e9f  lea     rdx, aLocaldevicenam; "LocalDeviceName"
0x180030ea6  lea     rcx, aBluetooth; "Bluetooth"
0x180030ead  call    cs:__imp_PolicyManager_GetPolicyString
0x180030eb3  test    eax, eax
0x180030eb5  js      short loc_180030F07
0x180030eb7  mov     rdi, [rbp+Source]
0x180030ebb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030ebf  inc     rbx
0x180030ec2  cmp     [rdi+rbx*2], r14w
0x180030ec7  jnz     short loc_180030EBF
0x180030ec9  lea     rcx, ds:2[rbx*2]; Size
0x180030ed1  call    _o_malloc_0
0x180030ed6  lea     rdx, [rbx+1]; SizeInWords
0x180030eda  mov     r8, rdi; Source
0x180030edd  mov     rcx, rax; Destination
0x180030ee0  mov     rsi, rax
0x180030ee3  call    wcscpy_s
0x180030ee8  test    eax, eax
0x180030eea  jnz     short loc_180030EFD
0x180030eec  mov     rdx, rsi; SourceString
0x180030eef  lea     rcx, [rbp+DestinationString.Buffer]; DestinationString
0x180030ef3  call    cs:__imp_RtlInitUnicodeString
0x180030ef9  or      dword ptr [rbp+var_10+4], 40h
0x180030efd  mov     rcx, [rbp+Source]
0x180030f01  call    cs:__imp_PolicyManager_FreeStringValue
0x180030f07  lea     r8, [rbp+Source]
0x180030f0b  lea     rdx, aDevicesallowed; "DevicesAllowedList"
0x180030f12  lea     rcx, aBluetooth; "Bluetooth"
0x180030f19  call    cs:__imp_PolicyManager_GetPolicyString
0x180030f1f  test    eax, eax
0x180030f21  js      short loc_180030F51
0x180030f23  mov     rcx, [rbp+Source]; unsigned __int16 *
0x180030f27  lea     r9, [rbp+arg_0]; unsigned int *
0x180030f2b  lea     r8, [rbp+var_28]; unsigned __int64 **
0x180030f2f  mov     [rbp+arg_0], r14d
0x180030f33  call    ?TokenListToBthAddrArray@@YAJPEAGGPEAPEA_KPEAI@Z; TokenListToBthAddrArray(ushort *,ushort,unsigned __int64 * *,uint *)
0x180030f38  test    eax, eax
0x180030f3a  js      short loc_180030F47
0x180030f3c  mov     eax, [rbp+arg_0]
0x180030f3f  bts     dword ptr [rbp+var_10+4], 7
0x180030f44  mov     dword ptr [rbp+var_10+8], eax
0x180030f47  mov     rcx, [rbp+Source]
0x180030f4b  call    cs:__imp_PolicyManager_FreeStringValue
0x180030f51  lea     r8, [rbp+Source]
0x180030f55  lea     rdx, aServicesallowe; "ServicesAllowedList"
0x180030f5c  lea     rcx, aBluetooth; "Bluetooth"
0x180030f63  call    cs:__imp_PolicyManager_GetPolicyString
0x180030f69  test    eax, eax
0x180030f6b  js      short loc_180030F9B
0x180030f6d  mov     rcx, [rbp+Source]; unsigned __int16 *
0x180030f71  lea     r9, [rbp+arg_0]; unsigned int *
0x180030f75  lea     r8, [rbp+var_20]; struct _GUID **
0x180030f79  mov     [rbp+arg_0], r14d
0x180030f7d  call    ?TokenListToGuidArray@@YAJPEAGGPEAPEAU_GUID@@PEAI@Z; TokenListToGuidArray(ushort *,ushort,_GUID * *,uint *)
0x180030f82  test    eax, eax
0x180030f84  js      short loc_180030F91
0x180030f86  mov     eax, [rbp+arg_0]
0x180030f89  bts     dword ptr [rbp+var_10+4], 8
0x180030f8e  mov     dword ptr [rbp+var_10+0Ch], eax
0x180030f91  mov     rcx, [rbp+Source]
0x180030f95  call    cs:__imp_PolicyManager_FreeStringValue
0x180030f9b  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030fa2  call    cs:__imp_EnterCriticalSection
0x180030fa8  mov     rcx, qword ptr cs:ymmword_180044A20+10h; Block
0x180030faf  test    rcx, rcx
0x180030fb2  jz      short loc_180030FB9
0x180030fb4  call    free
0x180030fb9  mov     rcx, qword ptr cs:ymmword_180044A20+18h; Block
0x180030fc0  test    rcx, rcx
0x180030fc3  jz      short loc_180030FCA
0x180030fc5  call    free
0x180030fca  mov     rcx, qword ptr cs:Src; Block
0x180030fd1  test    rcx, rcx
0x180030fd4  jz      short loc_180030FDB
0x180030fd6  call    free
0x180030fdb  movaps  xmm0, [rbp+var_50]
0x180030fdf  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030fe6  movaps  xmm1, xmmword ptr [rbp+DestinationString.Length]
0x180030fea  movaps  cs:?g_Policies@@3UPolicies@@A, xmm0; Policies g_Policies
0x180030ff1  movaps  xmm0, xmmword ptr [rbp-30h]
0x180030ff5  movaps  xmmword ptr cs:ymmword_180044A20+10h, xmm0
0x180030ffc  movaps  xmm0, [rbp+var_10]
0x180031000  movaps  xmmword ptr cs:ymmword_180044A20, xmm1
0x180031007  movaps  xmm1, xmmword ptr [rbp+var_20]
0x18003100b  movaps  cs:xmmword_180044A50, xmm0
0x180031012  movaps  cs:Src, xmm1
0x180031019  call    cs:__imp_LeaveCriticalSection
0x18003101f  lea     r11, [rsp+70h+var_s0]
0x180031024  xor     eax, eax
0x180031026  mov     rbx, [r11+30h]
0x18003102a  mov     rsi, [r11+38h]
0x18003102e  mov     rsp, r11
0x180031031  pop     r14
0x180031033  pop     rdi
0x180031034  pop     rbp
0x180031035  retn
```
