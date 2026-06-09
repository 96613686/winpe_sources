# CBrowserBrokerInstance::RepairEdgeFolderPermissions(void)

- ea: `0x18000bc20`
- end: `0x18000bcb9`
- name: `?RepairEdgeFolderPermissions@CBrowserBrokerInstance@@UEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180002ce0`
- `0x18000bc20`
- `0x18000e428`
- `0x180020678`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000bc8b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18000bc8b`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000bc5d`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000bc7d`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000bc5d`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x18000bc7d`
- `profapi!__imp_GetAppContainerPath` at `0x18000bc71`
- `profapi!__imp_GetAppContainerPath` at `0x18000bc71`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::RepairEdgeFolderPermissions(CBrowserBrokerInstance *this)
{
  __int64 result; // rax
  __int64 String; // rax
  const unsigned __int16 *v3; // rbx
  char Bool; // al
  unsigned int v5[4]; // [rsp+20h] [rbp-238h] BYREF
  unsigned __int16 v6[264]; // [rsp+30h] [rbp-228h] BYREF

  v5[0] = 0;
  result = BrokerAuthenticateAttachedCallerGetPIC(1, v5);
  if ( (int)result >= 0 )
  {
    String = IEConfiguration_GetString(268435506);
    result = GetAppContainerPath(String, v6, 260);
    if ( (int)result >= 0 )
    {
      v3 = (const unsigned __int16 *)IEConfiguration_GetString(268435506);
      Bool = IEConfiguration_GetBool(268435519);
      return SetFilePathFullControlByTrustedAC(v6, Bool, v3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bc20  push    rbx
0x18000bc22  sub     rsp, 250h
0x18000bc29  mov     rax, cs:__security_cookie
0x18000bc30  xor     rax, rsp
0x18000bc33  mov     [rsp+258h+var_18], rax
0x18000bc3b  lea     rdx, [rsp+258h+var_238]; unsigned int *
0x18000bc40  mov     [rsp+258h+var_238], 0
0x18000bc48  mov     ecx, 1; unsigned int
0x18000bc4d  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000bc52  test    eax, eax
0x18000bc54  js      short loc_18000BCA0
0x18000bc56  mov     ebx, 10000032h
0x18000bc5b  mov     ecx, ebx
0x18000bc5d  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18000bc63  mov     r8d, 104h
0x18000bc69  lea     rdx, [rsp+258h+var_228]
0x18000bc6e  mov     rcx, rax
0x18000bc71  call    cs:__imp_GetAppContainerPath
0x18000bc77  test    eax, eax
0x18000bc79  js      short loc_18000BCA0
0x18000bc7b  mov     ecx, ebx
0x18000bc7d  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18000bc83  mov     ecx, 1000003Fh
0x18000bc88  mov     rbx, rax
0x18000bc8b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18000bc91  mov     r8, rbx; unsigned __int16 *
0x18000bc94  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18000bc99  mov     dl, al; bool
0x18000bc9b  call    ?SetFilePathFullControlByTrustedAC@@YAJPEBG_N0@Z; SetFilePathFullControlByTrustedAC(ushort const *,bool,ushort const *)
0x18000bca0  mov     rcx, [rsp+258h+var_18]
0x18000bca8  xor     rcx, rsp; StackCookie
0x18000bcab  call    __security_check_cookie
0x18000bcb0  add     rsp, 250h
0x18000bcb7  pop     rbx
0x18000bcb8  retn
```
