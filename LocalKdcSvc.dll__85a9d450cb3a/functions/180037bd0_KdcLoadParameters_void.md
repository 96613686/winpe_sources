# KdcLoadParameters(void)

- ea: `0x180037bd0`
- end: `0x180037d13`
- name: `?KdcLoadParameters@@YAXXZ`
- size: `323`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a5fc`

## callees

- `0x1800101ec`
- `0x180037bd0`
- `0x18006e434`
- `0x180071f0c`
- `0x180072014`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037ce7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037ce7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037cac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037cac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037cf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037cf3`

## pseudocode

```c
void __fastcall KdcLoadParameters(__int64 a1, __int64 a2, HKEY a3)
{
  unsigned int v3; // eax
  HKEY *v4; // rbx
  unsigned int ConfigBool; // eax
  LSTATUS v6; // ebx
  HKEY *Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  Data = 0;
  hKey = 0;
  v3 = NetpOpenConfigDataEx(&Data, a2, a3);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, v3);
  }
  else
  {
    v4 = Data;
    ConfigBool = NetpGetConfigBool(Data);
    if ( ConfigBool
      && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, ConfigBool);
    }
    if ( v4 )
    {
      RegCloseKey(*v4);
      NetpMemoryFree(v4);
    }
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SafeBoot\\Option", 0, 0x20019u, &hKey) )
    {
      LODWORD(Data) = 0;
      Type = 0;
      cbData = 4;
      v6 = RegQueryValueExW(hKey, L"OptionValue", 0, &Type, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
      if ( !v6 )
      {
        if ( (_DWORD)Data )
          KdcGlobalGlobalSafeBoot = 1;
      }
    }
  }
}

```

## disassembly

```asm
0x180037bd0  push    rbp
0x180037bd2  push    rbx
0x180037bd3  mov     rbp, rsp
0x180037bd6  sub     rsp, 38h
0x180037bda  lea     rcx, [rbp+Data]
0x180037bde  mov     [rbp+Data], 0
0x180037be6  mov     [rbp+hKey], 0
0x180037bee  call    NetpOpenConfigDataEx
0x180037bf3  test    eax, eax
0x180037bf5  jz      short loc_180037C35
0x180037bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180037bfe  lea     rdx, WPP_GLOBAL_Control
0x180037c05  cmp     rcx, rdx
0x180037c08  jz      loc_180037D0C
0x180037c0e  test    byte ptr [rcx+1Ch], 2
0x180037c12  jz      loc_180037D0C
0x180037c18  mov     rcx, [rcx+10h]
0x180037c1c  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180037c23  mov     edx, 1Fh
0x180037c28  mov     r9d, eax
0x180037c2b  call    WPP_SF_d
0x180037c30  jmp     loc_180037D0C
0x180037c35  mov     rbx, [rbp+Data]
0x180037c39  mov     rcx, rbx
0x180037c3c  call    NetpGetConfigBool
0x180037c41  test    eax, eax
0x180037c43  jz      short loc_180037C76
0x180037c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180037c4c  lea     rdx, WPP_GLOBAL_Control
0x180037c53  cmp     rcx, rdx
0x180037c56  jz      short loc_180037C76
0x180037c58  test    byte ptr [rcx+1Ch], 2
0x180037c5c  jz      short loc_180037C76
0x180037c5e  mov     rcx, [rcx+10h]
0x180037c62  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180037c69  mov     edx, 20h ; ' '
0x180037c6e  mov     r9d, eax
0x180037c71  call    WPP_SF_d
0x180037c76  test    rbx, rbx
0x180037c79  jz      short loc_180037C8C
0x180037c7b  mov     rcx, [rbx]; hKey
0x180037c7e  call    cs:__imp_RegCloseKey
0x180037c84  mov     rcx, rbx
0x180037c87  call    NetpMemoryFree
0x180037c8c  lea     rax, [rbp+hKey]
0x180037c90  mov     r9d, 20019h; samDesired
0x180037c96  xor     r8d, r8d; ulOptions
0x180037c99  mov     [rsp+38h+phkResult], rax; phkResult
0x180037c9e  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Saf"...
0x180037ca5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037cac  call    cs:__imp_RegOpenKeyExW
0x180037cb2  test    eax, eax
0x180037cb4  jnz     short loc_180037D0C
0x180037cb6  mov     rcx, [rbp+hKey]; hKey
0x180037cba  lea     r9, [rbp+Type]; lpType
0x180037cbe  mov     dword ptr [rbp+Data], eax
0x180037cc1  lea     rdx, aOptionvalue; "OptionValue"
0x180037cc8  mov     [rbp+Type], eax
0x180037ccb  xor     r8d, r8d; lpReserved
0x180037cce  lea     rax, [rbp+cbData]
0x180037cd2  mov     [rbp+cbData], 4
0x180037cd9  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180037cde  lea     rax, [rbp+Data]
0x180037ce2  mov     [rsp+38h+phkResult], rax; lpData
0x180037ce7  call    cs:__imp_RegQueryValueExW
0x180037ced  mov     rcx, [rbp+hKey]; hKey
0x180037cf1  mov     ebx, eax
0x180037cf3  call    cs:__imp_RegCloseKey
0x180037cf9  test    ebx, ebx
0x180037cfb  jnz     short loc_180037D0C
0x180037cfd  cmp     dword ptr [rbp+Data], ebx
0x180037d00  jz      short loc_180037D0C
0x180037d02  mov     cs:?KdcGlobalGlobalSafeBoot@@3HA, 1; int KdcGlobalGlobalSafeBoot
0x180037d0c  add     rsp, 38h
0x180037d10  pop     rbx
0x180037d11  pop     rbp
0x180037d12  retn
```
