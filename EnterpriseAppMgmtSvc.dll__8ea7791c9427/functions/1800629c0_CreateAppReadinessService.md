# CreateAppReadinessService

- ea: `0x1800629c0`
- end: `0x180062b61`
- name: `CreateAppReadinessService`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180062b68`

## callees

- `0x1800629c0`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180062aef`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180062aef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062ab4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062ab4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180062a7f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180062a7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062a1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062a1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062b28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062b28`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062a5d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062a5d`

## string_xrefs

- `0x180062a15`: `Software\Microsoft\Windows\CurrentVersion\AppReadiness`

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
0x1800629c0  mov     [rsp-8+arg_8], rbx
0x1800629c5  mov     [rsp-8+arg_10], rdi
0x1800629ca  push    rbp
0x1800629cb  lea     rbp, [rsp-190h]
0x1800629d3  sub     rsp, 290h
0x1800629da  mov     rax, cs:__security_cookie
0x1800629e1  xor     rax, rsp
0x1800629e4  mov     [rbp+190h+var_10], rax
0x1800629eb  mov     rdi, rcx
0x1800629ee  mov     qword ptr [rcx], 0
0x1800629f5  lea     rax, [rsp+290h+hKey]
0x1800629fa  mov     [rsp+290h+hKey], 0
0x180062a03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180062a0a  mov     [rsp+290h+phkResult], rax; phkResult
0x180062a0f  mov     r9d, 1; samDesired
0x180062a15  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180062a1c  xor     r8d, r8d; ulOptions
0x180062a1f  call    cs:__imp_RegOpenKeyExW
0x180062a25  mov     ebx, eax
0x180062a27  test    eax, eax
0x180062a29  jnz     loc_180062B30
0x180062a2f  mov     rcx, [rsp+290h+hKey]; hKey
0x180062a34  lea     rax, [rsp+290h+cbData]
0x180062a39  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180062a3e  lea     rdx, aNotifyobject; "NotifyObject"
0x180062a45  lea     rax, [rsp+290h+Data]
0x180062a4a  mov     [rsp+290h+cbData], 208h
0x180062a52  xor     r9d, r9d; lpType
0x180062a55  mov     [rsp+290h+phkResult], rax; lpData
0x180062a5a  xor     r8d, r8d; lpReserved
0x180062a5d  call    cs:__imp_RegQueryValueExW
0x180062a63  mov     ebx, eax
0x180062a65  test    eax, eax
0x180062a67  jnz     loc_180062B18
0x180062a6d  xorps   xmm0, xmm0
0x180062a70  lea     rdx, [rsp+290h+pclsid]; pclsid
0x180062a75  lea     rcx, [rsp+290h+Data]; lpsz
0x180062a7a  movups  xmmword ptr [rsp+290h+pclsid.Data1], xmm0
0x180062a7f  call    cs:__imp_CLSIDFromString
0x180062a85  mov     ebx, eax
0x180062a87  test    eax, eax
0x180062a89  js      loc_180062B23
0x180062a8f  xor     edx, edx; pUnkOuter
0x180062a91  mov     [rsp+290h+ppv], 0
0x180062a9a  lea     rax, [rsp+290h+ppv]
0x180062a9f  lea     r9, _GUID_29b6a139_cf48_4840_8d2f_e08c7c949b44; riid
0x180062aa6  mov     [rsp+290h+phkResult], rax; ppv
0x180062aab  lea     rcx, [rsp+290h+pclsid]; rclsid
0x180062ab0  lea     r8d, [rdx+4]; dwClsContext
0x180062ab4  call    cs:__imp_CoCreateInstance
0x180062aba  mov     ebx, eax
0x180062abc  test    eax, eax
0x180062abe  js      short loc_180062B23
0x180062ac0  mov     rcx, [rsp+290h+ppv]; pProxy
0x180062ac5  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180062ac8  mov     [rsp+290h+dwCapabilities], 40h ; '@'; dwCapabilities
0x180062ad0  mov     r8d, edx; dwAuthzSvc
0x180062ad3  mov     [rsp+290h+pAuthInfo], 0; pAuthInfo
0x180062adc  xor     r9d, r9d; pServerPrincName
0x180062adf  mov     dword ptr [rsp+290h+lpcbData], 2; dwImpLevel
0x180062ae7  mov     dword ptr [rsp+290h+phkResult], 4; dwAuthnLevel
0x180062aef  call    cs:__imp_CoSetProxyBlanket
0x180062af5  mov     ebx, eax
0x180062af7  test    eax, eax
0x180062af9  js      short loc_180062B05
0x180062afb  mov     rax, [rsp+290h+ppv]
0x180062b00  mov     [rdi], rax
0x180062b03  jmp     short loc_180062B23
0x180062b05  mov     rcx, [rsp+290h+ppv]
0x180062b0a  mov     rax, [rcx]
0x180062b0d  mov     rax, [rax+10h]
0x180062b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b16  jmp     short loc_180062B23
0x180062b18  jle     short loc_180062B23
0x180062b1a  movzx   ebx, ax
0x180062b1d  or      ebx, 80070000h
0x180062b23  mov     rcx, [rsp+290h+hKey]; hKey
0x180062b28  call    cs:__imp_RegCloseKey
0x180062b2e  jmp     short loc_180062B3B
0x180062b30  jle     short loc_180062B3B
0x180062b32  movzx   ebx, ax
0x180062b35  or      ebx, 80070000h
0x180062b3b  mov     eax, ebx
0x180062b3d  mov     rcx, [rbp+190h+var_10]
0x180062b44  xor     rcx, rsp; StackCookie
0x180062b47  call    __security_check_cookie
0x180062b4c  lea     r11, [rsp+290h+var_s0]
0x180062b54  mov     rbx, [r11+18h]
0x180062b58  mov     rdi, [r11+20h]
0x180062b5c  mov     rsp, r11
0x180062b5f  pop     rbp
0x180062b60  retn
```
