# SensorGroupId::CreateSensorGroupIdContainer(void)

- ea: `0x1800112d0`
- end: `0x1800114b9`
- name: `?CreateSensorGroupIdContainer@SensorGroupId@@SAJXZ`
- size: `489`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010a30`

## callees

- `0x180005fa0`
- `0x180009600`
- `0x1800112d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001146b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001146b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011382`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113f2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001136e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800113cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001136e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800113cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001140d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001140d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180011321`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180011321`

## pseudocode

```c
__int64 SensorGroupId::CreateSensorGroupIdContainer(void)
{
  LSTATUS v0; // eax
  signed int v1; // ebx
  LSTATUS v2; // eax
  __int64 v4; // rdx
  signed int LastError; // eax
  void **v6; // [rsp+50h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF

  hKey = 0;
  *(_QWORD *)&SecurityDescriptor.nLength = 24;
  v6 = &AutoSecurityAttributes::`vftable';
  *(_QWORD *)&SecurityDescriptor.bInheritHandle = 0;
  SecurityDescriptor.lpSecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)(A;;GRGX;;;WD)(A;;GRGX;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)",
          1u,
          &SecurityDescriptor.lpSecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
    {
      AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v6);
      if ( !g_wppLevels )
        goto LABEL_8;
      v4 = 43;
      goto LABEL_21;
    }
  }
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer",
         0,
         0,
         0,
         0x20106u,
         &SecurityDescriptor,
         &hKey,
         0);
  v1 = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
      v1 = (unsigned __int16)v0 | 0x80070000;
    if ( v1 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_8;
      v4 = 44;
      goto LABEL_21;
    }
  }
  RegCloseKey(hKey);
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer\\SensorGroups",
         0,
         0,
         0,
         0x20106u,
         &SecurityDescriptor,
         &hKey,
         0);
  v1 = v2;
  if ( !v2 )
    goto LABEL_7;
  if ( v2 > 0 )
    v1 = (unsigned __int16)v2 | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_7:
    RegCloseKey(hKey);
    hKey = 0;
    goto LABEL_8;
  }
  if ( g_wppLevels )
  {
    v4 = 45;
LABEL_21:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, v1);
  }
LABEL_8:
  v6 = &AutoSecurityAttributes::`vftable';
  if ( SecurityDescriptor.lpSecurityDescriptor )
    LocalFree(SecurityDescriptor.lpSecurityDescriptor);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800112d0  mov     [rsp-8+arg_8], rbx
0x1800112d5  mov     [rsp-8+arg_10], r13
0x1800112da  push    rbp
0x1800112db  mov     rbp, rsp
0x1800112de  sub     rsp, 70h
0x1800112e2  xor     eax, eax
0x1800112e4  mov     [rbp+hKey], 0
0x1800112ec  xorps   xmm0, xmm0
0x1800112ef  mov     [rbp+var_8], rax
0x1800112f3  movups  xmmword ptr [rbp+SecurityDescriptor], xmm0
0x1800112f7  lea     r13, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x1800112fe  mov     dword ptr [rbp+SecurityDescriptor], 18h
0x180011305  lea     edx, [rax+1]; StringSDRevision
0x180011308  mov     [rbp+var_20], r13
0x18001130c  xor     r9d, r9d; SecurityDescriptorSize
0x18001130f  mov     dword ptr [rbp+var_8], eax
0x180011312  lea     r8, [rbp+SecurityDescriptor+8]; SecurityDescriptor
0x180011316  mov     [rbp+SecurityDescriptor+8], rax
0x18001131a  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)("...
0x180011321  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180011327  test    eax, eax
0x180011329  jz      loc_18001146B
0x18001132f  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180011338  lea     rax, [rbp+hKey]
0x18001133c  mov     [rsp+70h+phkResult], rax; phkResult
0x180011341  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x180011348  lea     rax, [rbp+SecurityDescriptor]
0x18001134c  xor     r9d, r9d; lpClass
0x18001134f  mov     [rsp+70h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180011354  xor     r8d, r8d; Reserved
0x180011357  mov     [rsp+70h+samDesired], 20106h; samDesired
0x18001135f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011366  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18001136e  call    cs:__imp_RegCreateKeyExW
0x180011374  mov     ebx, eax
0x180011376  test    eax, eax
0x180011378  jnz     loc_180011427
0x18001137e  mov     rcx, [rbp+hKey]; hKey
0x180011382  call    cs:__imp_RegCloseKey
0x180011388  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180011391  lea     rax, [rbp+hKey]
0x180011395  mov     [rsp+70h+phkResult], rax; phkResult
0x18001139a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x1800113a1  lea     rax, [rbp+SecurityDescriptor]
0x1800113a5  mov     [rbp+hKey], 0
0x1800113ad  mov     [rsp+70h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800113b2  xor     r9d, r9d; lpClass
0x1800113b5  mov     [rsp+70h+samDesired], 20106h; samDesired
0x1800113bd  xor     r8d, r8d; Reserved
0x1800113c0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800113c7  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1800113cf  call    cs:__imp_RegCreateKeyExW
0x1800113d5  mov     ebx, eax
0x1800113d7  test    eax, eax
0x1800113d9  jz      short loc_1800113EE
0x1800113db  jle     short loc_1800113E6
0x1800113dd  movzx   ebx, ax
0x1800113e0  or      ebx, 80070000h
0x1800113e6  test    ebx, ebx
0x1800113e8  js      loc_1800114AA
0x1800113ee  mov     rcx, [rbp+hKey]; hKey
0x1800113f2  call    cs:__imp_RegCloseKey
0x1800113f8  mov     [rbp+hKey], 0
0x180011400  mov     rcx, [rbp+SecurityDescriptor+8]; hMem
0x180011404  mov     [rbp+var_20], r13
0x180011408  test    rcx, rcx
0x18001140b  jz      short loc_180011413
0x18001140d  call    cs:__imp_LocalFree
0x180011413  lea     r11, [rsp+70h+var_s0]
0x180011418  mov     eax, ebx
0x18001141a  mov     rbx, [r11+18h]
0x18001141e  mov     r13, [r11+20h]
0x180011422  mov     rsp, r11
0x180011425  pop     rbp
0x180011426  retn
0x180011427  jle     short loc_180011432
0x180011429  movzx   ebx, ax
0x18001142c  or      ebx, 80070000h
0x180011432  test    ebx, ebx
0x180011434  jns     loc_18001137E
0x18001143a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011441  jb      short loc_180011400
0x180011443  mov     edx, 2Ch ; ','
0x180011448  jmp     short loc_180011487
0x18001144a  test    ebx, ebx
0x18001144c  jns     loc_18001132F
0x180011452  lea     rcx, [rbp+var_20]; this
0x180011456  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18001145b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011462  jb      short loc_180011400
0x180011464  mov     edx, 2Bh ; '+'
0x180011469  jmp     short loc_180011487
0x18001146b  call    cs:__imp_GetLastError
0x180011471  mov     ebx, eax
0x180011473  test    eax, eax
0x180011475  jle     short loc_18001144A
0x180011477  movzx   ebx, ax
0x18001147a  or      ebx, 80070000h
0x180011480  jmp     short loc_18001144A
0x180011482  mov     edx, 2Dh ; '-'
0x180011487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001148e  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x180011495  xor     r9d, r9d
0x180011498  mov     [rsp+70h+dwOptions], ebx
0x18001149c  mov     rcx, [rcx+10h]
0x1800114a0  call    WPP_SF_qD
0x1800114a5  jmp     loc_180011400
0x1800114aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800114b1  jb      loc_180011400
0x1800114b7  jmp     short loc_180011482
```
