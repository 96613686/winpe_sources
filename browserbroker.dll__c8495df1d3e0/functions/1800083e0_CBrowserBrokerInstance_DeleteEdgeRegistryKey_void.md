# CBrowserBrokerInstance::DeleteEdgeRegistryKey(void)

- ea: `0x1800083e0`
- end: `0x180008526`
- name: `?DeleteEdgeRegistryKey@CBrowserBrokerInstance@@UEAAJXZ`
- size: `326`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002ce0`
- `0x1800083e0`
- `0x18000d088`
- `0x18000e428`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180008420`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180008420`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000844c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800084fd`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000844c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800084fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800084d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800084d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180008488`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180008488`
- `profapi!__imp_GetAppContainerRegistryPath` at `0x18000843c`
- `profapi!__imp_GetAppContainerRegistryPath` at `0x18000843c`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::DeleteEdgeRegistryKey(CBrowserBrokerInstance *this)
{
  int PIC; // ebx
  LSTATUS Key; // eax
  bool v3; // cc
  HKEY hKey[2]; // [rsp+50h] [rbp-438h] BYREF
  WCHAR SubKey[520]; // [rsp+60h] [rbp-428h] BYREF

  LODWORD(hKey[0]) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)hKey);
  if ( PIC >= 0 )
  {
    PIC = CoImpersonateClient();
    if ( PIC >= 0 )
    {
      PIC = GetAppContainerRegistryPath(SubKey, 520);
      if ( PIC < 0 )
      {
        CoRevertToSelf();
      }
      else
      {
        PIC = CoRevertToSelf();
        if ( PIC >= 0 )
        {
          PIC = StringCchCatW(SubKey, 0x208u, L"\\MicrosoftEdge");
          if ( PIC >= 0 )
          {
            Key = RegDeleteTreeW(HKEY_USERS, SubKey);
            v3 = Key <= 0;
            if ( Key
              || (hKey[0] = 0,
                  Key = RegCreateKeyExW(HKEY_USERS, SubKey, 0, 0, 0, 0x20006u, 0, hKey, 0),
                  v3 = Key <= 0,
                  Key) )
            {
              if ( v3 )
                return (unsigned int)Key;
              else
                return (unsigned __int16)Key | 0x80070000;
            }
            else
            {
              RegCloseKey(hKey[0]);
            }
          }
        }
      }
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x1800083e0  mov     [rsp+arg_0], rbx
0x1800083e5  push    rsi
0x1800083e6  sub     rsp, 480h
0x1800083ed  mov     rax, cs:__security_cookie
0x1800083f4  xor     rax, rsp
0x1800083f7  mov     [rsp+488h+var_18], rax
0x1800083ff  lea     rdx, [rsp+488h+hKey]; unsigned int *
0x180008404  mov     dword ptr [rsp+488h+hKey], 0
0x18000840c  mov     ecx, 1; unsigned int
0x180008411  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180008416  mov     ebx, eax
0x180008418  test    eax, eax
0x18000841a  js      loc_180008503
0x180008420  call    cs:__imp_CoImpersonateClient
0x180008426  mov     ebx, eax
0x180008428  test    eax, eax
0x18000842a  js      loc_180008503
0x180008430  mov     esi, 208h
0x180008435  lea     rcx, [rsp+488h+SubKey]
0x18000843a  mov     edx, esi
0x18000843c  call    cs:__imp_GetAppContainerRegistryPath
0x180008442  mov     ebx, eax
0x180008444  test    eax, eax
0x180008446  js      loc_1800084FD
0x18000844c  call    cs:__imp_CoRevertToSelf
0x180008452  mov     ebx, eax
0x180008454  test    eax, eax
0x180008456  js      loc_180008503
0x18000845c  lea     r8, aMicrosoftedge; "\\MicrosoftEdge"
0x180008463  mov     edx, esi; unsigned __int64
0x180008465  lea     rcx, [rsp+488h+SubKey]; unsigned __int16 *
0x18000846a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000846f  mov     ebx, eax
0x180008471  test    eax, eax
0x180008473  js      loc_180008503
0x180008479  mov     rsi, 0FFFFFFFF80000003h
0x180008480  lea     rdx, [rsp+488h+SubKey]; lpSubKey
0x180008485  mov     rcx, rsi; hKey
0x180008488  call    cs:__imp_RegDeleteTreeW
0x18000848e  test    eax, eax
0x180008490  jnz     short loc_1800084EC
0x180008492  mov     [rsp+488h+lpdwDisposition], 0; lpdwDisposition
0x18000849b  lea     rax, [rsp+488h+hKey]
0x1800084a0  mov     [rsp+488h+phkResult], rax; phkResult
0x1800084a5  lea     rdx, [rsp+488h+SubKey]; lpSubKey
0x1800084aa  mov     [rsp+488h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800084b3  xor     r9d, r9d; lpClass
0x1800084b6  mov     [rsp+488h+samDesired], 20006h; samDesired
0x1800084be  xor     r8d, r8d; Reserved
0x1800084c1  mov     rcx, rsi; hKey
0x1800084c4  mov     [rsp+488h+dwOptions], 0; dwOptions
0x1800084cc  mov     [rsp+488h+hKey], 0
0x1800084d5  call    cs:__imp_RegCreateKeyExW
0x1800084db  test    eax, eax
0x1800084dd  jnz     short loc_1800084EC
0x1800084df  mov     rcx, [rsp+488h+hKey]; hKey
0x1800084e4  call    cs:__imp_RegCloseKey
0x1800084ea  jmp     short loc_180008503
0x1800084ec  jg      short loc_1800084F2
0x1800084ee  mov     ebx, eax
0x1800084f0  jmp     short loc_180008503
0x1800084f2  movzx   ebx, ax
0x1800084f5  or      ebx, 80070000h
0x1800084fb  jmp     short loc_180008503
0x1800084fd  call    cs:__imp_CoRevertToSelf
0x180008503  mov     eax, ebx
0x180008505  mov     rcx, [rsp+488h+var_18]
0x18000850d  xor     rcx, rsp; StackCookie
0x180008510  call    __security_check_cookie
0x180008515  mov     rbx, [rsp+488h+arg_0]
0x18000851d  add     rsp, 480h
0x180008524  pop     rsi
0x180008525  retn
```
