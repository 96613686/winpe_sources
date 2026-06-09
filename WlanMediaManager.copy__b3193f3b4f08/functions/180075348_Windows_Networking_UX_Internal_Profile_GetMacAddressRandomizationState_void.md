# Windows::Networking::UX::Internal::Profile::GetMacAddressRandomizationState(void)

- ea: `0x180075348`
- end: `0x180075435`
- name: `?GetMacAddressRandomizationState@Profile@Internal@UX@Networking@Windows@@QEAA?AW4MacAddressRandomizationState@2345@XZ`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005c7b0`

## callees

- `0x180075284`
- `0x180075348`
- `0x1800757ac`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18007541e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18007541e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x1800753b1`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x1800753b1`
- `wlanapi!WpFreeProfile` at `0x180075414`
- `wlanapi!WpFreeProfile` at `0x180075414`
- `wlanapi!WpParseProfileXml` at `0x1800753e7`
- `wlanapi!WpParseProfileXml` at `0x1800753e7`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::Profile::GetMacAddressRandomizationState(__int64 a1)
{
  unsigned int v2; // ebx
  int MacAddressRandomizationFeatureState; // eax
  void *v4; // rcx
  signed int Profile; // eax
  bool v6; // sf
  int v7; // eax
  bool v8; // sf
  __int64 v9; // rdx
  LPWSTR pstrProfileXml; // [rsp+40h] [rbp-10h] BYREF
  __int64 v12; // [rsp+48h] [rbp-8h] BYREF
  DWORD pdwGrantedAccess; // [rsp+78h] [rbp+28h] BYREF
  DWORD pdwFlags; // [rsp+80h] [rbp+30h] BYREF
  int v15; // [rsp+88h] [rbp+38h] BYREF

  v2 = 3;
  MacAddressRandomizationFeatureState = Windows::Networking::UX::Internal::Profile::GetMacAddressRandomizationFeatureState(a1);
  if ( MacAddressRandomizationFeatureState != 1 )
  {
    if ( MacAddressRandomizationFeatureState == 2 )
    {
      return 4;
    }
    else
    {
      v4 = *(void **)a1;
      pstrProfileXml = 0;
      pdwFlags = 0;
      pdwGrantedAccess = 0;
      Profile = WlanGetProfile(
                  v4,
                  (const GUID *)(a1 + 8),
                  (LPCWSTR)(a1 + 24),
                  0,
                  &pstrProfileXml,
                  &pdwFlags,
                  &pdwGrantedAccess);
      v6 = Profile < 0;
      if ( Profile > 0 )
        v6 = 1;
      if ( !v6 )
      {
        v12 = 0;
        v15 = 0;
        v7 = WpParseProfileXml(pstrProfileXml, &v12, 0, &v15);
        v8 = v7 < 0;
        if ( v7 > 0 )
          v8 = 1;
        if ( !v8 )
        {
          v9 = v12;
          if ( *(_QWORD *)(v12 + 552) )
            v2 = Windows::Networking::UX::Internal::Profile::MacAddressRandomizationStateFromDot11AcProfile();
          WpFreeProfile(v9);
        }
        WlanFreeMemory(pstrProfileXml);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180075348  push    rbp
0x18007534a  push    rbx
0x18007534b  push    rdi
0x18007534c  mov     rbp, rsp
0x18007534f  sub     rsp, 50h
0x180075353  mov     rdi, rcx
0x180075356  mov     ebx, 3
0x18007535b  call    ?GetMacAddressRandomizationFeatureState@Profile@Internal@UX@Networking@Windows@@AEAA?AW4_DOT11_MAC_RANDOMIZATION_STATUS@@XZ; Windows::Networking::UX::Internal::Profile::GetMacAddressRandomizationFeatureState(void)
0x180075360  cmp     eax, 1
0x180075363  jz      loc_18007542B
0x180075369  cmp     eax, 2
0x18007536c  jz      loc_180075426
0x180075372  mov     rcx, [rdi]; hClientHandle
0x180075375  lea     rax, [rbp+arg_8]
0x180075379  mov     [rsp+50h+pdwGrantedAccess], rax; pdwGrantedAccess
0x18007537e  lea     r8, [rdi+18h]; strProfileName
0x180075382  lea     rax, [rbp+arg_10]
0x180075386  mov     [rbp+var_10], 0
0x18007538e  mov     [rsp+50h+pdwFlags], rax; pdwFlags
0x180075393  lea     rdx, [rdi+8]; pInterfaceGuid
0x180075397  lea     rax, [rbp+var_10]
0x18007539b  mov     [rbp+arg_10], 0
0x1800753a2  xor     r9d, r9d; pReserved
0x1800753a5  mov     [rsp+50h+pstrProfileXml], rax; pstrProfileXml
0x1800753aa  mov     [rbp+arg_8], 0
0x1800753b1  call    cs:__imp_WlanGetProfile
0x1800753b7  mov     edi, 80070000h
0x1800753bc  test    eax, eax
0x1800753be  jle     short loc_1800753C7
0x1800753c0  movzx   eax, ax
0x1800753c3  or      eax, edi
0x1800753c5  test    eax, eax
0x1800753c7  js      short loc_18007542B
0x1800753c9  mov     rcx, [rbp+var_10]
0x1800753cd  lea     r9, [rbp+arg_18]
0x1800753d1  xor     r8d, r8d
0x1800753d4  mov     [rbp+var_8], 0
0x1800753dc  lea     rdx, [rbp+var_8]
0x1800753e0  mov     [rbp+arg_18], 0
0x1800753e7  call    cs:__imp_WpParseProfileXml
0x1800753ed  test    eax, eax
0x1800753ef  jle     short loc_1800753F8
0x1800753f1  movzx   eax, ax
0x1800753f4  or      eax, edi
0x1800753f6  test    eax, eax
0x1800753f8  js      short loc_18007541A
0x1800753fa  mov     rdx, [rbp+var_8]
0x1800753fe  mov     rcx, [rdx+228h]
0x180075405  test    rcx, rcx
0x180075408  jz      short loc_180075411
0x18007540a  call    ?MacAddressRandomizationStateFromDot11AcProfile@Profile@Internal@UX@Networking@Windows@@CA?AW4MacAddressRandomizationState@2345@PEAU_DOT11_AC_PROFILE@@@Z; Windows::Networking::UX::Internal::Profile::MacAddressRandomizationStateFromDot11AcProfile(_DOT11_AC_PROFILE *)
0x18007540f  mov     ebx, eax
0x180075411  mov     rcx, rdx
0x180075414  call    cs:__imp_WpFreeProfile
0x18007541a  mov     rcx, [rbp+var_10]; pMemory
0x18007541e  call    cs:__imp_WlanFreeMemory
0x180075424  jmp     short loc_18007542B
0x180075426  mov     ebx, 4
0x18007542b  mov     eax, ebx
0x18007542d  add     rsp, 50h
0x180075431  pop     rdi
0x180075432  pop     rbx
0x180075433  pop     rbp
0x180075434  retn
```
