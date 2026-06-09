# NcbPolicyAddUserLockscreenAppsUnderLock

- ea: `0x180007314`
- end: `0x18000736d`
- name: `NcbPolicyAddUserLockscreenAppsUnderLock`
- size: `89`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007870`

## callees

- `0x180007314`
- `0x180009990`
- `0x18000a0a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007347`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007347`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000732b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000732b`

## string_xrefs

- `0x18000735f`: `NcbPolicy: NcbPolicyAddUserLockscreenAppsUnderLock couldn't convert user SID to string`

## pseudocode

```c
unsigned int __fastcall NcbPolicyAddUserLockscreenAppsUnderLock(PSID Sid)
{
  unsigned int result; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  LPWSTR StringSid; // [rsp+38h] [rbp+10h] BYREF

  StringSid = 0;
  result = ConvertSidToStringSidW(Sid, &StringSid);
  if ( result )
  {
    NcbPolicyEnumerateUserLockscreenApps((unsigned __int8 *)Sid, (__int64)StringSid);
    return (unsigned int)LocalFree(StringSid);
  }
  else if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    return McTemplateU0zq_EventWriteTransfer(
             v4,
             v3,
             L"NcbPolicy: NcbPolicyAddUserLockscreenAppsUnderLock couldn't convert user SID to string",
             0);
  }
  return result;
}

```

## disassembly

```asm
0x180007314  push    rbx
0x180007316  sub     rsp, 20h
0x18000731a  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18000731f  mov     [rsp+28h+StringSid], 0
0x180007328  mov     rbx, rcx
0x18000732b  call    cs:__imp_ConvertSidToStringSidW
0x180007331  test    eax, eax
0x180007333  jz      short loc_180007353
0x180007335  mov     rdx, [rsp+28h+StringSid]
0x18000733a  mov     rcx, rbx; Sid
0x18000733d  call    NcbPolicyEnumerateUserLockscreenApps
0x180007342  mov     rcx, [rsp+28h+StringSid]; hMem
0x180007347  call    cs:__imp_LocalFree
0x18000734d  add     rsp, 20h
0x180007351  pop     rbx
0x180007352  retn
0x180007353  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000735a  jz      short loc_18000734D
0x18000735c  xor     r9d, r9d
0x18000735f  lea     r8, aNcbpolicyNcbpo_12; "NcbPolicy: NcbPolicyAddUserLockscreenAp"...
0x180007366  call    McTemplateU0zq_EventWriteTransfer
0x18000736b  jmp     short loc_18000734D
```
