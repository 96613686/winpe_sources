# FwRemoteAdminSettings::CreateDefaultRemoteAdminRules(void)

- ea: `0x180043bac`
- end: `0x180043c5a`
- name: `?CreateDefaultRemoteAdminRules@FwRemoteAdminSettings@@AEAAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180043fc8`

## callees

- `0x180043bac`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180043c30`
- `fwbase!FwReportReturnError` at `0x180043c45`
- `fwbase!FwReportReturnError` at `0x180043c30`
- `fwbase!FwReportReturnError` at `0x180043c45`
- `FWPolicyIOMgr!GetRemoteAdminSettings` at `0x180043bbc`
- `FWPolicyIOMgr!GetRemoteAdminSettings` at `0x180043bbc`
- `FWPolicyIOMgr!CreateDefaultRemoteAdminRule` at `0x180043c0e`
- `FWPolicyIOMgr!CreateDefaultRemoteAdminRule` at `0x180043c0e`

## string_xrefs

- `0x180043c29`: `FwRemoteAdminSettings::CreateDefaultRemoteAdminRules`
- `0x180043c3e`: `FwRemoteAdminSettings::CreateDefaultRemoteAdminRules`

## pseudocode

```c
__int64 __fastcall FwRemoteAdminSettings::CreateDefaultRemoteAdminRules(FwRemoteAdminSettings *this)
{
  unsigned int v2; // ebx
  struct FW_REMOTE_ADMIN_SETTING_ *RemoteAdminSettings; // r14
  __int64 i; // rdi
  char *v5; // rsi
  int DefaultRemoteAdminRule; // eax

  v2 = 0;
  RemoteAdminSettings = GetRemoteAdminSettings();
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    v5 = (char *)this + 8 * i + 80;
    if ( !*(_QWORD *)v5 )
    {
      DefaultRemoteAdminRule = CreateDefaultRemoteAdminRule(
                                 *((unsigned int *)RemoteAdminSettings + 12 * i),
                                 *((unsigned int *)RemoteAdminSettings + 12 * i + 1),
                                 *((_QWORD *)RemoteAdminSettings + 6 * i + 1),
                                 *((_QWORD *)RemoteAdminSettings + 6 * i + 2),
                                 (char *)RemoteAdminSettings + 48 * i + 24,
                                 (char *)this + 8 * i + 80,
                                 0x7FFFFFFF);
      v2 = DefaultRemoteAdminRule;
      if ( DefaultRemoteAdminRule < 0 )
      {
        FwReportReturnError(
          "FwRemoteAdminSettings::CreateDefaultRemoteAdminRules",
          (unsigned int)DefaultRemoteAdminRule);
        return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::CreateDefaultRemoteAdminRules", v2);
      }
      *(_DWORD *)(*(_QWORD *)v5 + 40LL) = *((_DWORD *)this + 16);
    }
  }
  if ( (v2 & 0x80000000) == 0 )
    return v2;
  return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::CreateDefaultRemoteAdminRules", v2);
}

```

## disassembly

```asm
0x180043bac  push    rbx
0x180043bae  push    rbp
0x180043baf  push    rsi
0x180043bb0  push    rdi
0x180043bb1  push    r14
0x180043bb3  sub     rsp, 40h
0x180043bb7  mov     rbp, rcx
0x180043bba  xor     ebx, ebx
0x180043bbc  call    cs:__imp_?GetRemoteAdminSettings@@YAPEAUFW_REMOTE_ADMIN_SETTING_@@XZ; GetRemoteAdminSettings(void)
0x180043bc2  mov     r14, rax
0x180043bc5  xor     edi, edi
0x180043bc7  cmp     edi, 3
0x180043bca  jnb     short loc_180043C38
0x180043bcc  lea     rsi, [rbp+50h]
0x180043bd0  lea     rsi, [rsi+rdi*8]
0x180043bd4  cmp     qword ptr [rsi], 0
0x180043bd8  jnz     short loc_180043C23
0x180043bda  mov     [rsp+68h+var_38], 7FFFFFFFh
0x180043be2  lea     rcx, [rdi+rdi*2]
0x180043be6  shl     rcx, 4
0x180043bea  lea     rax, [r14+18h]
0x180043bee  add     rax, rcx
0x180043bf1  mov     [rsp+68h+var_40], rsi
0x180043bf6  mov     [rsp+68h+var_48], rax
0x180043bfb  mov     r9, [rcx+r14+10h]
0x180043c00  mov     r8, [rcx+r14+8]
0x180043c05  mov     edx, [rcx+r14+4]
0x180043c0a  mov     ecx, [rcx+r14]
0x180043c0e  call    cs:__imp_?CreateDefaultRemoteAdminRule@@YAJIIPEBG0PEAU_tag_FW_PORTS@@PEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultRemoteAdminRule(uint,uint,ushort const *,ushort const *,_tag_FW_PORTS *,_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180043c14  mov     ebx, eax
0x180043c16  test    eax, eax
0x180043c18  js      short loc_180043C27
0x180043c1a  mov     rdx, [rsi]
0x180043c1d  mov     ecx, [rbp+40h]
0x180043c20  mov     [rdx+28h], ecx
0x180043c23  inc     edi
0x180043c25  jmp     short loc_180043BC7
0x180043c27  mov     edx, eax
0x180043c29  lea     rcx, aFwremoteadmins_4; "FwRemoteAdminSettings::CreateDefaultRem"...
0x180043c30  call    cs:__imp_FwReportReturnError
0x180043c36  jmp     short loc_180043C3C
0x180043c38  test    ebx, ebx
0x180043c3a  jns     short loc_180043C4D
0x180043c3c  mov     edx, ebx
0x180043c3e  lea     rcx, aFwremoteadmins_4; "FwRemoteAdminSettings::CreateDefaultRem"...
0x180043c45  call    cs:__imp_FwReportReturnError
0x180043c4b  mov     ebx, eax
0x180043c4d  mov     eax, ebx
0x180043c4f  add     rsp, 40h
0x180043c53  pop     r14
0x180043c55  pop     rdi
0x180043c56  pop     rsi
0x180043c57  pop     rbp
0x180043c58  pop     rbx
0x180043c59  retn
```
