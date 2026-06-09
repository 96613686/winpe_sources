# Windows::Networking::UX::Internal::Profile::GetPmProfile(std::unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter> &,ulong &)

- ea: `0x18007543c`
- end: `0x18007556e`
- name: `?GetPmProfile@Profile@Internal@UX@Networking@Windows@@QEAAJAEAV?$unique_ptr@U_PM_PROFILE@@Uppm_profile_deleter@Internal@UX@Networking@Windows@@@std@@AEAK@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005c610`

## callees

- `0x18000de4c`
- `0x18001d4d4`
- `0x18005ba94`
- `0x180074ab4`
- `0x18007543c`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075527`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075527`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x1800754bc`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x1800754bc`
- `wlanapi!WpParseProfileXml` at `0x1800754ec`
- `wlanapi!WpParseProfileXml` at `0x1800754ec`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::Profile::GetPmProfile(__int64 a1, __int64 *a2, DWORD *a3)
{
  void *v6; // rcx
  signed int Profile; // eax
  signed int v8; // ebx
  int v9; // eax
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  __int64 v12; // [rsp+48h] [rbp-8h] BYREF
  DWORD pdwGrantedAccess; // [rsp+70h] [rbp+20h] BYREF
  LPWSTR pstrProfileXml; // [rsp+88h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_660af29b5b58392da31645ec246aada0_Traceguids);
  v6 = *(void **)a1;
  pdwGrantedAccess = 0;
  pstrProfileXml = 0;
  Profile = WlanGetProfile(v6, (const GUID *)(a1 + 8), (LPCWSTR)(a1 + 24), 0, &pstrProfileXml, a3, &pdwGrantedAccess);
  v8 = Profile;
  if ( Profile > 0 )
    v8 = (unsigned __int16)Profile | 0x80070000;
  if ( v8 >= 0 )
  {
    v11 = 0;
    v9 = WpParseProfileXml(pstrProfileXml, &v11, 0, 0);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v12 = v11;
      std::unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter>::operator=<Windows::Networking::UX::Internal::ppm_profile_deleter,0>(
        a2,
        &v12);
      std::unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter>::~unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter>(&v12);
    }
  }
  if ( pstrProfileXml )
    WlanFreeMemory(pstrProfileXml);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_660af29b5b58392da31645ec246aada0_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007543c  mov     [rsp-18h+arg_8], rbx
0x180075441  mov     [rsp-18h+arg_10], rsi
0x180075446  push    rbp
0x180075447  push    rdi
0x180075448  push    r15
0x18007544a  mov     rbp, rsp
0x18007544d  sub     rsp, 50h
0x180075451  mov     rdi, r8
0x180075454  mov     rsi, rdx
0x180075457  mov     rbx, rcx
0x18007545a  mov     rcx, cs:WPP_GLOBAL_Control
0x180075461  lea     r15, WPP_GLOBAL_Control
0x180075468  cmp     rcx, r15
0x18007546b  jz      short loc_180075488
0x18007546d  test    byte ptr [rcx+1Ch], 40h
0x180075471  jz      short loc_180075488
0x180075473  mov     rcx, [rcx+10h]
0x180075477  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x18007547e  mov     edx, 29h ; ')'
0x180075483  call    WPP_SF_
0x180075488  mov     rcx, [rbx]; hClientHandle
0x18007548b  lea     rax, [rbp+arg_0]
0x18007548f  mov     [rsp+50h+pdwGrantedAccess], rax; pdwGrantedAccess
0x180075494  lea     r8, [rbx+18h]; strProfileName
0x180075498  lea     rax, [rbp+arg_18]
0x18007549c  mov     [rsp+50h+pdwFlags], rdi; pdwFlags
0x1800754a1  lea     rdx, [rbx+8]; pInterfaceGuid
0x1800754a5  mov     [rsp+50h+pstrProfileXml], rax; pstrProfileXml
0x1800754aa  xor     r9d, r9d; pReserved
0x1800754ad  mov     [rbp+arg_0], 0
0x1800754b4  mov     [rbp+arg_18], 0
0x1800754bc  call    cs:__imp_WlanGetProfile
0x1800754c2  mov     ebx, eax
0x1800754c4  mov     edi, 80070000h
0x1800754c9  test    eax, eax
0x1800754cb  jle     short loc_1800754D2
0x1800754cd  movzx   ebx, ax
0x1800754d0  or      ebx, edi
0x1800754d2  test    ebx, ebx
0x1800754d4  js      short loc_18007551E
0x1800754d6  mov     rcx, [rbp+arg_18]
0x1800754da  lea     rdx, [rbp+var_10]
0x1800754de  xor     r9d, r9d
0x1800754e1  mov     [rbp+var_10], 0
0x1800754e9  xor     r8d, r8d
0x1800754ec  call    cs:__imp_WpParseProfileXml
0x1800754f2  mov     ebx, eax
0x1800754f4  test    eax, eax
0x1800754f6  jle     short loc_1800754FD
0x1800754f8  movzx   ebx, ax
0x1800754fb  or      ebx, edi
0x1800754fd  test    ebx, ebx
0x1800754ff  js      short loc_18007551E
0x180075501  mov     rax, [rbp+var_10]
0x180075505  lea     rdx, [rbp+var_8]
0x180075509  mov     rcx, rsi
0x18007550c  mov     [rbp+var_8], rax
0x180075510  call    ??$?4Uppm_profile_deleter@Internal@UX@Networking@Windows@@$0A@@?$unique_ptr@U_PM_PROFILE@@Uppm_profile_deleter@Internal@UX@Networking@Windows@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter>::operator=<Windows::Networking::UX::Internal::ppm_profile_deleter,0>(std::unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter> &&)
0x180075515  lea     rcx, [rbp+var_8]
0x180075519  call    ??1?$unique_ptr@U_PM_PROFILE@@Uppm_profile_deleter@Internal@UX@Networking@Windows@@@std@@QEAA@XZ; std::unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter>::~unique_ptr<_PM_PROFILE,Windows::Networking::UX::Internal::ppm_profile_deleter>(void)
0x18007551e  mov     rcx, [rbp+arg_18]; pMemory
0x180075522  test    rcx, rcx
0x180075525  jz      short loc_18007552D
0x180075527  call    cs:__imp_WlanFreeMemory
0x18007552d  mov     rcx, cs:WPP_GLOBAL_Control
0x180075534  cmp     rcx, r15
0x180075537  jz      short loc_180075557
0x180075539  test    byte ptr [rcx+1Ch], 40h
0x18007553d  jz      short loc_180075557
0x18007553f  mov     rcx, [rcx+10h]
0x180075543  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x18007554a  mov     edx, 2Ah ; '*'
0x18007554f  mov     r9d, ebx
0x180075552  call    WPP_SF_d
0x180075557  lea     r11, [rsp+50h+var_s0]
0x18007555c  mov     eax, ebx
0x18007555e  mov     rbx, [r11+28h]
0x180075562  mov     rsi, [r11+30h]
0x180075566  mov     rsp, r11
0x180075569  pop     r15
0x18007556b  pop     rdi
0x18007556c  pop     rbp
0x18007556d  retn
```
