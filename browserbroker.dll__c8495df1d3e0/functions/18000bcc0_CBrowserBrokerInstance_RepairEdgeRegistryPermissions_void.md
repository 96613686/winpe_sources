# CBrowserBrokerInstance::RepairEdgeRegistryPermissions(void)

- ea: `0x18000bcc0`
- end: `0x18000bd74`
- name: `?RepairEdgeRegistryPermissions@CBrowserBrokerInstance@@UEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180002ce0`
- `0x18000bcc0`
- `0x18000e428`
- `0x180020844`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000bd39`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000bd39`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000bd2b`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000bd2b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000bcf8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000bcf8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000bd1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000bd53`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000bd1a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000bd53`
- `profapi!__imp_GetAppContainerRegistryPath` at `0x18000bd0e`
- `profapi!__imp_GetAppContainerRegistryPath` at `0x18000bd0e`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::RepairEdgeRegistryPermissions(CBrowserBrokerInstance *this)
{
  int PIC; // ebx
  const unsigned __int16 *String; // rbx
  char Bool; // al
  HKEY v4; // rcx
  unsigned int v6[4]; // [rsp+20h] [rbp-438h] BYREF
  unsigned __int16 v7[520]; // [rsp+30h] [rbp-428h] BYREF

  v6[0] = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, v6);
  if ( PIC >= 0 )
  {
    PIC = CoImpersonateClient();
    if ( PIC >= 0 )
    {
      PIC = GetAppContainerRegistryPath(v7, 520);
      if ( PIC < 0 )
      {
        CoRevertToSelf();
      }
      else
      {
        PIC = CoRevertToSelf();
        if ( PIC >= 0 )
        {
          String = (const unsigned __int16 *)IEConfiguration_GetString(268435506);
          Bool = IEConfiguration_GetBool(268435519);
          return (unsigned int)SetRegistryPathFullControlByTrustedAC(v4, v7, Bool, String);
        }
      }
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x18000bcc0  push    rbx
0x18000bcc2  sub     rsp, 450h
0x18000bcc9  mov     rax, cs:__security_cookie
0x18000bcd0  xor     rax, rsp
0x18000bcd3  mov     [rsp+458h+var_18], rax
0x18000bcdb  lea     rdx, [rsp+458h+var_438]; unsigned int *
0x18000bce0  mov     [rsp+458h+var_438], 0
0x18000bce8  mov     ecx, 1; unsigned int
0x18000bced  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000bcf2  mov     ebx, eax
0x18000bcf4  test    eax, eax
0x18000bcf6  js      short loc_18000BD59
0x18000bcf8  call    cs:__imp_CoImpersonateClient
0x18000bcfe  mov     ebx, eax
0x18000bd00  test    eax, eax
0x18000bd02  js      short loc_18000BD59
0x18000bd04  mov     edx, 208h
0x18000bd09  lea     rcx, [rsp+458h+var_428]
0x18000bd0e  call    cs:__imp_GetAppContainerRegistryPath
0x18000bd14  mov     ebx, eax
0x18000bd16  test    eax, eax
0x18000bd18  js      short loc_18000BD53
0x18000bd1a  call    cs:__imp_CoRevertToSelf
0x18000bd20  mov     ebx, eax
0x18000bd22  test    eax, eax
0x18000bd24  js      short loc_18000BD59
0x18000bd26  mov     ecx, 10000032h
0x18000bd2b  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18000bd31  mov     ecx, 1000003Fh
0x18000bd36  mov     rbx, rax
0x18000bd39  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18000bd3f  mov     r9, rbx; unsigned __int16 *
0x18000bd42  lea     rdx, [rsp+458h+var_428]; unsigned __int16 *
0x18000bd47  mov     r8b, al; bool
0x18000bd4a  call    ?SetRegistryPathFullControlByTrustedAC@@YAJPEAUHKEY__@@PEBG_N1@Z; SetRegistryPathFullControlByTrustedAC(HKEY__ *,ushort const *,bool,ushort const *)
0x18000bd4f  mov     ebx, eax
0x18000bd51  jmp     short loc_18000BD59
0x18000bd53  call    cs:__imp_CoRevertToSelf
0x18000bd59  mov     eax, ebx
0x18000bd5b  mov     rcx, [rsp+458h+var_18]
0x18000bd63  xor     rcx, rsp; StackCookie
0x18000bd66  call    __security_check_cookie
0x18000bd6b  add     rsp, 450h
0x18000bd72  pop     rbx
0x18000bd73  retn
```
