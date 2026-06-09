# FwEnumLegacyLocalPolicyRules(_tag_FW_PROFILE_TYPE,_tag_FW_BLOB_RULE * *,ulong *,ulong,ulong)

- ea: `0x18002b1cc`
- end: `0x18002b3c8`
- name: `?FwEnumLegacyLocalPolicyRules@@YAJW4_tag_FW_PROFILE_TYPE@@PEAPEAU_tag_FW_BLOB_RULE@@PEAKKK@Z`
- size: `508`
- prototype: `__int64 __fastcall(int, void **, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002bc34`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x180008360`
- `0x18001ba5c`
- `0x18001f650`
- `0x18002b1cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b391`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b391`
- `fwbase!FwRegOpenKey` at `0x18002b2fb`
- `fwbase!FwRegOpenKey` at `0x18002b2fb`

## string_xrefs

- `0x18002b22a`: `DomainProfile\GloballyOpenPorts`
- `0x18002b2b1`: `StandardProfile\GloballyOpenPorts`

## pseudocode

```c
__int64 __fastcall FwEnumLegacyLocalPolicyRules(int a1, void **a2, _DWORD *a3)
{
  int RulesAndSettings; // ebx
  HKEY hKey[3]; // [rsp+50h] [rbp-51h] BYREF
  int v9; // [rsp+68h] [rbp-39h] BYREF
  const wchar_t *v10; // [rsp+70h] [rbp-31h] BYREF
  int v11; // [rsp+78h] [rbp-29h]
  int v12; // [rsp+7Ch] [rbp-25h]
  const wchar_t *v13; // [rsp+80h] [rbp-21h]
  int v14; // [rsp+88h] [rbp-19h]
  int v15; // [rsp+8Ch] [rbp-15h]
  const wchar_t *v16; // [rsp+90h] [rbp-11h]
  int v17; // [rsp+98h] [rbp-9h]
  int v18; // [rsp+9Ch] [rbp-5h]
  const wchar_t *v19; // [rsp+A0h] [rbp-1h]
  int v20; // [rsp+A8h] [rbp+7h]
  int v21; // [rsp+ACh] [rbp+Bh]
  const wchar_t *v22; // [rsp+B0h] [rbp+Fh]
  int v23; // [rsp+B8h] [rbp+17h]
  int v24; // [rsp+BCh] [rbp+1Bh]

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  *a2 = 0;
  v10 = L"DomainProfile\\GloballyOpenPorts";
  v13 = L"DomainProfile\\AuthorizedApplications";
  v16 = L"DomainProfile";
  v19 = L"DomainProfile";
  v22 = L"DomainProfile";
  v23 = 5;
  hKey[1] = (HKEY)5;
  hKey[2] = (HKEY)&v10;
  v9 = 0;
  hKey[0] = 0;
  v11 = 1;
  v12 = a1;
  v14 = 2;
  v15 = a1;
  v17 = 3;
  v18 = a1;
  v20 = 4;
  v21 = a1;
  v24 = a1;
  *a3 = 0;
  if ( a1 == 2 )
  {
    v10 = L"StandardProfile\\GloballyOpenPorts";
    v13 = L"StandardProfile\\AuthorizedApplications";
    v22 = L"StandardProfile";
    v19 = L"StandardProfile";
    v16 = L"StandardProfile";
  }
  else if ( a1 != 1 )
  {
    return 2147942487LL;
  }
  RulesAndSettings = FwRegOpenKey(-2147483646, off_18004DAC0[0], 9, hKey, &v9);
  if ( RulesAndSettings >= 0 )
  {
    if ( v9 )
      RulesAndSettings = FwReadRulesAndSettings(hKey[0], 1, 2);
    else
      RulesAndSettings = -2147024894;
  }
  else if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      101,
      WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
      (unsigned int)RulesAndSettings);
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( RulesAndSettings < 0 )
  {
    FwFreeRules(*a2);
    *a2 = 0;
  }
  return (unsigned int)RulesAndSettings;
}

```

## disassembly

```asm
0x18002b1cc  push    rbp
0x18002b1ce  push    rbx
0x18002b1cf  push    rsi
0x18002b1d0  push    rdi
0x18002b1d1  push    r14
0x18002b1d3  lea     rbp, [rsp-2Fh]
0x18002b1d8  sub     rsp, 0D0h
0x18002b1df  mov     rax, cs:__security_cookie
0x18002b1e6  xor     rax, rsp
0x18002b1e9  mov     [rbp+4Fh+var_30], rax
0x18002b1ed  mov     r14, r8
0x18002b1f0  mov     rsi, rdx
0x18002b1f3  mov     edi, ecx
0x18002b1f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1fc  lea     rax, WPP_GLOBAL_Control
0x18002b203  cmp     rcx, rax
0x18002b206  jz      short loc_18002B223
0x18002b208  test    byte ptr [rcx+1Ch], 8
0x18002b20c  jz      short loc_18002B223
0x18002b20e  mov     rcx, [rcx+10h]
0x18002b212  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002b219  mov     edx, 64h ; 'd'
0x18002b21e  call    WPP_SF_
0x18002b223  mov     qword ptr [rsi], 0
0x18002b22a  lea     rax, aDomainprofileG; "DomainProfile\\GloballyOpenPorts"
0x18002b231  mov     [rbp+4Fh+var_80], rax
0x18002b235  lea     rax, aDomainprofileA; "DomainProfile\\AuthorizedApplications"
0x18002b23c  mov     [rbp+4Fh+var_70], rax
0x18002b240  lea     rax, aDomainprofile; "DomainProfile"
0x18002b247  mov     [rbp+4Fh+var_60], rax
0x18002b24b  mov     [rbp+4Fh+var_50], rax
0x18002b24f  mov     [rbp+4Fh+var_40], rax
0x18002b253  mov     eax, 5
0x18002b258  mov     [rbp+4Fh+var_38], eax
0x18002b25b  mov     [rbp+4Fh+var_98], rax
0x18002b25f  lea     rax, [rbp+4Fh+var_80]
0x18002b263  mov     [rbp+4Fh+var_90], rax
0x18002b267  mov     [rbp+4Fh+var_88], 0
0x18002b26e  mov     [rbp+4Fh+hKey], 0
0x18002b276  mov     [rbp+4Fh+var_78], 1
0x18002b27d  mov     [rbp+4Fh+var_74], edi
0x18002b280  mov     [rbp+4Fh+var_68], 2
0x18002b287  mov     [rbp+4Fh+var_64], edi
0x18002b28a  mov     [rbp+4Fh+var_58], 3
0x18002b291  mov     [rbp+4Fh+var_54], edi
0x18002b294  mov     [rbp+4Fh+var_48], 4
0x18002b29b  mov     [rbp+4Fh+var_44], edi
0x18002b29e  mov     [rbp+4Fh+var_34], edi
0x18002b2a1  mov     dword ptr [r14], 0
0x18002b2a8  cmp     edi, 2
0x18002b2ab  jnz     loc_18002B33A
0x18002b2b1  lea     rax, aStandardprofil_0; "StandardProfile\\GloballyOpenPorts"
0x18002b2b8  mov     [rbp+4Fh+var_80], rax
0x18002b2bc  lea     rax, aStandardprofil; "StandardProfile\\AuthorizedApplications"
0x18002b2c3  mov     [rbp+4Fh+var_70], rax
0x18002b2c7  lea     rax, aStandardprofil_1; "StandardProfile"
0x18002b2ce  mov     [rbp+4Fh+var_40], rax
0x18002b2d2  mov     [rbp+4Fh+var_50], rax
0x18002b2d6  mov     [rbp+4Fh+var_60], rax
0x18002b2da  mov     rdx, cs:off_18004DAC0; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18002b2e1  lea     rax, [rbp+4Fh+var_88]
0x18002b2e5  lea     r9, [rbp+4Fh+hKey]
0x18002b2e9  mov     [rsp+0F0h+var_D0], rax
0x18002b2ee  mov     r8d, 9
0x18002b2f4  mov     rcx, 0FFFFFFFF80000002h
0x18002b2fb  call    cs:__imp_FwRegOpenKey
0x18002b301  mov     ebx, eax
0x18002b303  test    eax, eax
0x18002b305  jns     short loc_18002B346
0x18002b307  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b30e  lea     rax, WPP_GLOBAL_Control
0x18002b315  cmp     rcx, rax
0x18002b318  jz      short loc_18002B388
0x18002b31a  test    byte ptr [rcx+1Ch], 1
0x18002b31e  jz      short loc_18002B388
0x18002b320  mov     rcx, [rcx+10h]
0x18002b324  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002b32b  mov     edx, 65h ; 'e'
0x18002b330  mov     r9d, ebx
0x18002b333  call    WPP_SF_d
0x18002b338  jmp     short loc_18002B388
0x18002b33a  cmp     edi, 1
0x18002b33d  jz      short loc_18002B2DA
0x18002b33f  mov     eax, 80070057h
0x18002b344  jmp     short loc_18002B3AE
0x18002b346  cmp     [rbp+4Fh+var_88], 0
0x18002b34a  jnz     short loc_18002B353
0x18002b34c  mov     ebx, 80070002h
0x18002b351  jmp     short loc_18002B388
0x18002b353  mov     rcx, [rbp+4Fh+hKey]
0x18002b357  lea     rax, [rbp+4Fh+var_98]
0x18002b35b  mov     [rsp+0F0h+var_B0], edi
0x18002b35f  xor     r9d, r9d
0x18002b362  mov     [rsp+0F0h+var_B8], 30000h
0x18002b36a  mov     [rsp+0F0h+var_C0], r14
0x18002b36f  mov     [rsp+0F0h+var_C8], rsi
0x18002b374  lea     edx, [r9+1]
0x18002b378  mov     [rsp+0F0h+var_D0], rax
0x18002b37d  lea     r8d, [r9+2]
0x18002b381  call    ?FwReadRulesAndSettings@@YAJPEAUHKEY__@@HW4_tag_FW_STORE_TYPE@@W4FW_RULE_TYPE@@PEAU_tag_WF_POLICY_STORE_HIVE_LIST@@PEAPEAU_tag_FW_BLOB_RULE@@PEAKKK@Z; FwReadRulesAndSettings(HKEY__ *,int,_tag_FW_STORE_TYPE,FW_RULE_TYPE,_tag_WF_POLICY_STORE_HIVE_LIST *,_tag_FW_BLOB_RULE * *,ulong *,ulong,ulong)
0x18002b386  mov     ebx, eax
0x18002b388  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18002b38c  test    rcx, rcx
0x18002b38f  jz      short loc_18002B397
0x18002b391  call    cs:__imp_RegCloseKey
0x18002b397  test    ebx, ebx
0x18002b399  jns     short loc_18002B3AC
0x18002b39b  mov     rcx, [rsi]; void *
0x18002b39e  xor     edx, edx
0x18002b3a0  call    FwFreeRules
0x18002b3a5  mov     qword ptr [rsi], 0
0x18002b3ac  mov     eax, ebx
0x18002b3ae  mov     rcx, [rbp+4Fh+var_30]
0x18002b3b2  xor     rcx, rsp; StackCookie
0x18002b3b5  call    __security_check_cookie
0x18002b3ba  add     rsp, 0D0h
0x18002b3c1  pop     r14
0x18002b3c3  pop     rdi
0x18002b3c4  pop     rsi
0x18002b3c5  pop     rbx
0x18002b3c6  pop     rbp
0x18002b3c7  retn
```
