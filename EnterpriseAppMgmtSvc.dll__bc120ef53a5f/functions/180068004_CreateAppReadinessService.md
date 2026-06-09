# CreateAppReadinessService

- ea: `0x180068004`
- end: `0x1800681ca`
- name: `CreateAppReadinessService`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800681d0`

## callees

- `0x180068004`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006814b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006814b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006810a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006810a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800680cf`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800680cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068063`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068063`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006818a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006818a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800680a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800680a7`

## string_xrefs

- `0x180068059`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness`

## pseudocode

```c
__int64 __fastcall CreateAppReadinessService(LPVOID *a1)
{
  LSTATUS v2; // eax
  int v3; // ebx
  LSTATUS v4; // eax
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR Data[264]; // [rsp+70h] [rbp-90h] BYREF

  *a1 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\AppReadiness", 0, 1u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    cbData = 520;
    v4 = RegQueryValueExW(hKey, L"NotifyObject", 0, 0, (LPBYTE)Data, &cbData);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
    }
    else
    {
      pclsid = 0;
      v3 = CLSIDFromString(Data, &pclsid);
      if ( v3 >= 0 )
      {
        ppv = 0;
        v3 = CoCreateInstance(&pclsid, 0, 4u, &GUID_29b6a139_cf48_4840_8d2f_e08c7c949b44, &ppv);
        if ( v3 >= 0 )
        {
          v3 = CoSetProxyBlanket((IUnknown *)ppv, 0xFFFFFFFF, 0xFFFFFFFF, 0, 4u, 2u, 0, 0x40u);
          if ( v3 < 0 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          else
            *a1 = ppv;
        }
      }
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180068004  mov     [rsp-8+arg_8], rbx
0x180068009  mov     [rsp-8+arg_10], rdi
0x18006800e  push    rbp
0x18006800f  lea     rbp, [rsp-190h]
0x180068017  sub     rsp, 290h
0x18006801e  mov     rax, cs:__security_cookie
0x180068025  xor     rax, rsp
0x180068028  mov     [rbp+190h+var_10], rax
0x18006802f  mov     rdi, rcx
0x180068032  mov     qword ptr [rcx], 0
0x180068039  lea     rax, [rsp+290h+hKey]
0x18006803e  mov     [rsp+290h+hKey], 0
0x180068047  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006804e  mov     [rsp+290h+phkResult], rax; phkResult
0x180068053  mov     r9d, 1; samDesired
0x180068059  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180068060  xor     r8d, r8d; ulOptions
0x180068063  call    cs:__imp_RegOpenKeyExW
0x18006806a  nop     dword ptr [rax+rax+00h]
0x18006806f  mov     ebx, eax
0x180068071  test    eax, eax
0x180068073  jnz     loc_180068198
0x180068079  mov     rcx, [rsp+290h+hKey]; hKey
0x18006807e  lea     rax, [rsp+290h+cbData]
0x180068083  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180068088  lea     rdx, aNotifyobject; "NotifyObject"
0x18006808f  lea     rax, [rsp+290h+Data]
0x180068094  mov     [rsp+290h+cbData], 208h
0x18006809c  xor     r9d, r9d; lpType
0x18006809f  mov     [rsp+290h+phkResult], rax; lpData
0x1800680a4  xor     r8d, r8d; lpReserved
0x1800680a7  call    cs:__imp_RegQueryValueExW
0x1800680ae  nop     dword ptr [rax+rax+00h]
0x1800680b3  mov     ebx, eax
0x1800680b5  test    eax, eax
0x1800680b7  jnz     loc_18006817A
0x1800680bd  xorps   xmm0, xmm0
0x1800680c0  lea     rdx, [rsp+290h+pclsid]; pclsid
0x1800680c5  lea     rcx, [rsp+290h+Data]; lpsz
0x1800680ca  movups  xmmword ptr [rsp+290h+pclsid.Data1], xmm0
0x1800680cf  call    cs:__imp_CLSIDFromString
0x1800680d6  nop     dword ptr [rax+rax+00h]
0x1800680db  mov     ebx, eax
0x1800680dd  test    eax, eax
0x1800680df  js      loc_180068185
0x1800680e5  xor     edx, edx; pUnkOuter
0x1800680e7  mov     [rsp+290h+ppv], 0
0x1800680f0  lea     rax, [rsp+290h+ppv]
0x1800680f5  lea     r9, _GUID_29b6a139_cf48_4840_8d2f_e08c7c949b44; riid
0x1800680fc  mov     [rsp+290h+phkResult], rax; ppv
0x180068101  lea     rcx, [rsp+290h+pclsid]; rclsid
0x180068106  lea     r8d, [rdx+4]; dwClsContext
0x18006810a  call    cs:__imp_CoCreateInstance
0x180068111  nop     dword ptr [rax+rax+00h]
0x180068116  mov     ebx, eax
0x180068118  test    eax, eax
0x18006811a  js      short loc_180068185
0x18006811c  mov     rcx, [rsp+290h+ppv]; pProxy
0x180068121  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180068124  mov     [rsp+290h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18006812c  mov     r8d, edx; dwAuthzSvc
0x18006812f  mov     [rsp+290h+pAuthInfo], 0; pAuthInfo
0x180068138  xor     r9d, r9d; pServerPrincName
0x18006813b  mov     dword ptr [rsp+290h+lpcbData], 2; dwImpLevel
0x180068143  mov     dword ptr [rsp+290h+phkResult], 4; dwAuthnLevel
0x18006814b  call    cs:__imp_CoSetProxyBlanket
0x180068152  nop     dword ptr [rax+rax+00h]
0x180068157  mov     ebx, eax
0x180068159  test    eax, eax
0x18006815b  js      short loc_180068167
0x18006815d  mov     rax, [rsp+290h+ppv]
0x180068162  mov     [rdi], rax
0x180068165  jmp     short loc_180068185
0x180068167  mov     rcx, [rsp+290h+ppv]
0x18006816c  mov     rax, [rcx]
0x18006816f  mov     rax, [rax+10h]
0x180068173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068178  jmp     short loc_180068185
0x18006817a  jle     short loc_180068185
0x18006817c  movzx   ebx, ax
0x18006817f  or      ebx, 80070000h
0x180068185  mov     rcx, [rsp+290h+hKey]; hKey
0x18006818a  call    cs:__imp_RegCloseKey
0x180068191  nop     dword ptr [rax+rax+00h]
0x180068196  jmp     short loc_1800681A3
0x180068198  jle     short loc_1800681A3
0x18006819a  movzx   ebx, ax
0x18006819d  or      ebx, 80070000h
0x1800681a3  mov     eax, ebx
0x1800681a5  mov     rcx, [rbp+190h+var_10]
0x1800681ac  xor     rcx, rsp; StackCookie
0x1800681af  call    __security_check_cookie
0x1800681b4  lea     r11, [rsp+290h+var_s0]
0x1800681bc  mov     rbx, [r11+18h]
0x1800681c0  mov     rdi, [r11+20h]
0x1800681c4  mov     rsp, r11
0x1800681c7  pop     rbp
0x1800681c8  retn
```
