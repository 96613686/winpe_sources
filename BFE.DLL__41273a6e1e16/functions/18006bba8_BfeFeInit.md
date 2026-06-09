# BfeFeInit

- ea: `0x18006bba8`
- end: `0x18006bc91`
- name: `BfeFeInit`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800407c0`

## callees

- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x18005aa60`
- `0x18006bba8`
- `0x18006bd6c`
- `0x18007aa34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bbdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bbdd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18006bc15`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18006bc15`

## string_xrefs

- `0x18006bc34`: `CreateWellKnownSid`

## pseudocode

```c
__int64 BfeFeInit()
{
  __int64 v0; // rbx
  HLOCAL v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rax
  DWORD LastError; // eax
  __int64 v5; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  SIZE_T uBytes; // [rsp+20h] [rbp-18h] BYREF

  LODWORD(uBytes) = 68;
  v0 = FeInit(99);
  if ( v0 )
    goto LABEL_7;
  v1 = LocalAlloc(0, (unsigned int)uBytes);
  g_pNullSid = v1;
  if ( v1 )
  {
    if ( CreateWellKnownSid(WinNullSid, 0, v1, (DWORD *)&uBytes) )
    {
      if ( (Feature_Firewall_042024__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_Firewall_042024__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline();
      g_isEnabled_Feature_Firewall_042024 = IsEnabledDeviceUsageNoInline != 0;
      return v0;
    }
    LastError = GetLastError();
    v3 = WfpReportSysErrorAsWinError(v5, "CreateWellKnownSid", LastError);
  }
  else
  {
    v3 = WfpReportSysErrorAsNtStatus(v2, "LocalAlloc", 3221225495LL);
  }
  v0 = v3;
  if ( v3 )
LABEL_7:
    WfpReportError(v0, "BfeFeInit");
  return v0;
}

```

## disassembly

```asm
0x18006bba8  push    rbx
0x18006bbaa  sub     rsp, 30h
0x18006bbae  mov     rax, cs:__security_cookie
0x18006bbb5  xor     rax, rsp
0x18006bbb8  mov     [rsp+38h+var_10], rax
0x18006bbbd  mov     ecx, 63h ; 'c'
0x18006bbc2  mov     dword ptr [rsp+38h+uBytes], 44h ; 'D'
0x18006bbca  call    FeInit
0x18006bbcf  mov     rbx, rax
0x18006bbd2  test    rax, rax
0x18006bbd5  jnz     short loc_18006BC48
0x18006bbd7  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x18006bbdb  xor     ecx, ecx; uFlags
0x18006bbdd  call    cs:__imp_LocalAlloc
0x18006bbe4  nop     dword ptr [rax+rax+00h]
0x18006bbe9  mov     cs:g_pNullSid, rax
0x18006bbf0  test    rax, rax
0x18006bbf3  jnz     short loc_18006BC09
0x18006bbf5  mov     r8d, 0C0000017h
0x18006bbfb  lea     rdx, aLocalalloc; "LocalAlloc"
0x18006bc02  call    WfpReportSysErrorAsNtStatus
0x18006bc07  jmp     short loc_18006BC40
0x18006bc09  lea     r9, [rsp+38h+uBytes]; cbSid
0x18006bc0e  mov     r8, rax; pSid
0x18006bc11  xor     edx, edx; DomainSid
0x18006bc13  xor     ecx, ecx; WellKnownSidType
0x18006bc15  call    cs:__imp_CreateWellKnownSid
0x18006bc1c  nop     dword ptr [rax+rax+00h]
0x18006bc21  test    eax, eax
0x18006bc23  jnz     short loc_18006BC6E
0x18006bc25  call    cs:__imp_GetLastError
0x18006bc2c  nop     dword ptr [rax+rax+00h]
0x18006bc31  mov     r8d, eax
0x18006bc34  lea     rdx, aCreatewellknow; "CreateWellKnownSid"
0x18006bc3b  call    WfpReportSysErrorAsWinError
0x18006bc40  mov     rbx, rax
0x18006bc43  test    rax, rax
0x18006bc46  jz      short loc_18006BC57
0x18006bc48  lea     rdx, aBfefeinit; "BfeFeInit"
0x18006bc4f  mov     rcx, rbx
0x18006bc52  call    WfpReportError
0x18006bc57  mov     rax, rbx
0x18006bc5a  mov     rcx, [rsp+38h+var_10]
0x18006bc5f  xor     rcx, rsp; StackCookie
0x18006bc62  call    __security_check_cookie
0x18006bc67  add     rsp, 30h
0x18006bc6b  pop     rbx
0x18006bc6c  retn
0x18006bc6e  mov     eax, cs:Feature_Firewall_042024__private_featureState
0x18006bc74  test    al, 10h
0x18006bc76  jz      short loc_18006BC7D
0x18006bc78  and     eax, 1
0x18006bc7b  jmp     short loc_18006BC82
0x18006bc7d  call    Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline
0x18006bc82  xor     ecx, ecx
0x18006bc84  test    eax, eax
0x18006bc86  setnz   cl
0x18006bc89  mov     cs:g_isEnabled_Feature_Firewall_042024, ecx
0x18006bc8f  jmp     short loc_18006BC57
```
