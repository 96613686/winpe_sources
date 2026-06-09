# AddUserAgentString(ulong)

- ea: `0x180013560`
- end: `0x18001366b`
- name: `?AddUserAgentString@@YAJK@Z`
- size: `267`
- prototype: `LSTATUS __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800197dc`

## callees

- `0x180013560`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013622`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013622`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800135a3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800135a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800135d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800135d8`

## string_xrefs

- `0x18001359c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\5.0\User Agent\Post Platform`
- `0x180013601`: `PENSERVICE_AddUserAgentString`
- `0x180013647`: `PENSERVICE_AddUserAgentString`

## pseudocode

```c
LSTATUS __fastcall AddUserAgentString(int a1)
{
  LSTATUS result; // eax
  LSTATUS v2; // ebx
  LSTATUS v3; // eax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\5.0\\User Agent\\Post Platform",
             0,
             0,
             0,
             a1 | 0x20006,
             0,
             &hKey,
             0);
  v2 = result;
  if ( !result )
  {
    v3 = RegSetValueExW(hKey, L"Tablet PC 2.0", 0, 1u, (const BYTE *)&Data, 2u);
    v2 = v3;
    if ( v3 && WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        19,
        (unsigned int)WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
        (unsigned int)"PENSERVICE_AddUserAgentString",
        v3);
    RegCloseKey(hKey);
    return v2;
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      20,
      (unsigned int)WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
      (unsigned int)"PENSERVICE_AddUserAgentString",
      result);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x180013560  push    rbx
0x180013562  sub     rsp, 50h
0x180013566  xor     edx, edx
0x180013568  lea     rax, [rsp+58h+hKey]
0x18001356d  mov     [rsp+58h+lpdwDisposition], rdx; lpdwDisposition
0x180013572  or      ecx, 20006h
0x180013578  mov     [rsp+58h+phkResult], rax; phkResult
0x18001357d  xor     r9d, r9d; lpClass
0x180013580  mov     [rsp+58h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x180013585  xor     r8d, r8d; Reserved
0x180013588  mov     [rsp+58h+samDesired], ecx; samDesired
0x18001358c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013593  mov     [rsp+58h+dwOptions], edx; dwOptions
0x180013597  mov     [rsp+58h+hKey], rdx
0x18001359c  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800135a3  call    cs:__imp_RegCreateKeyExW
0x1800135a9  mov     ebx, eax
0x1800135ab  test    eax, eax
0x1800135ad  jnz     short loc_18001362A
0x1800135af  mov     rcx, [rsp+58h+hKey]; hKey
0x1800135b4  lea     rax, Data
0x1800135bb  mov     [rsp+58h+samDesired], 2; cbData
0x1800135c3  lea     rdx, aTabletPc20; "Tablet PC 2.0"
0x1800135ca  mov     r9d, 1; dwType
0x1800135d0  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800135d5  xor     r8d, r8d; Reserved
0x1800135d8  call    cs:__imp_RegSetValueExW
0x1800135de  mov     ebx, eax
0x1800135e0  test    eax, eax
0x1800135e2  jz      short loc_18001361D
0x1800135e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135eb  lea     rdx, WPP_GLOBAL_Control
0x1800135f2  cmp     rcx, rdx
0x1800135f5  jz      short loc_18001361D
0x1800135f7  test    byte ptr [rcx+1Ch], 10h
0x1800135fb  jz      short loc_18001361D
0x1800135fd  mov     rcx, [rcx+10h]
0x180013601  lea     r9, aPenserviceAddu; "PENSERVICE_AddUserAgentString"
0x180013608  mov     edx, 13h
0x18001360d  mov     [rsp+58h+dwOptions], eax
0x180013611  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x180013618  call    WPP_SF_sd
0x18001361d  mov     rcx, [rsp+58h+hKey]; hKey
0x180013622  call    cs:__imp_RegCloseKey
0x180013628  jmp     short loc_180013663
0x18001362a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013631  lea     rdx, WPP_GLOBAL_Control
0x180013638  cmp     rcx, rdx
0x18001363b  jz      short loc_180013665
0x18001363d  test    byte ptr [rcx+1Ch], 10h
0x180013641  jz      short loc_180013665
0x180013643  mov     rcx, [rcx+10h]
0x180013647  lea     r9, aPenserviceAddu; "PENSERVICE_AddUserAgentString"
0x18001364e  mov     edx, 14h
0x180013653  mov     [rsp+58h+dwOptions], ebx
0x180013657  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x18001365e  call    WPP_SF_sd
0x180013663  mov     eax, ebx
0x180013665  add     rsp, 50h
0x180013669  pop     rbx
0x18001366a  retn
```
