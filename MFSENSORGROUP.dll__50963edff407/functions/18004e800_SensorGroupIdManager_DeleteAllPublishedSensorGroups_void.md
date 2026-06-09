# SensorGroupIdManager::DeleteAllPublishedSensorGroups(void)

- ea: `0x18004e800`
- end: `0x18004e9b3`
- name: `?DeleteAllPublishedSensorGroups@SensorGroupIdManager@@UEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(SensorGroupIdManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180005fa0`
- `0x18000ec30`
- `0x180044f30`
- `0x180045900`
- `0x18004e800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004e961`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004e973`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004e961`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004e973`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004e8da`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004e8da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e986`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e986`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004e908`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004e908`

## pseudocode

```c
__int64 __fastcall SensorGroupIdManager::DeleteAllPublishedSensorGroups(SensorGroupIdManager *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  DWORD i; // esi
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  __int64 v7; // rdx
  HKEY hKey; // [rsp+40h] [rbp-238h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-230h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-228h] BYREF

  hKey = 0;
  v2 = OpenSensorGroupRegistryKey(0, 983359, 0, &hKey);
  v3 = v2;
  if ( v2 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      memset_0(Name, 0, 0x208u);
      cchName = 260;
      v5 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v5 == 259 )
      {
        RegDeleteValueW(hKey, L"SGCH");
        RegDeleteValueW(hKey, L"SGCHTimeStamp");
        goto LABEL_21;
      }
      if ( v5 )
      {
        if ( v5 > 0 )
          v3 = (unsigned __int16)v5 | 0x80070000;
        else
          v3 = v5;
        if ( g_wppLevels )
        {
          v7 = 323;
          goto LABEL_19;
        }
        goto LABEL_21;
      }
      v6 = RegDeleteKeyW(hKey, Name);
      if ( v6 )
        break;
      v3 = 0;
    }
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    else
      v3 = v6;
    if ( g_wppLevels )
    {
      v7 = 324;
LABEL_19:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v3);
    }
  }
  else if ( g_wppLevels )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v2);
  }
LABEL_21:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18004e800  mov     [rsp+arg_8], rbx
0x18004e805  mov     [rsp+arg_10], rbp
0x18004e80a  push    rsi
0x18004e80b  sub     rsp, 270h
0x18004e812  mov     rax, cs:__security_cookie
0x18004e819  xor     rax, rsp
0x18004e81c  mov     [rsp+278h+var_18], rax
0x18004e824  mov     rbp, rcx
0x18004e827  mov     [rsp+278h+hKey], 0
0x18004e830  xor     ecx, ecx; unsigned __int16 *
0x18004e832  lea     r9, [rsp+278h+hKey]; HKEY *
0x18004e837  xor     r8d, r8d; bool *
0x18004e83a  mov     edx, 0F013Fh; unsigned int
0x18004e83f  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x18004e844  mov     ebx, eax
0x18004e846  test    eax, eax
0x18004e848  jns     short loc_18004E87F
0x18004e84a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004e851  jb      loc_18004E979
0x18004e857  mov     edx, 142h
0x18004e85c  mov     dword ptr [rsp+278h+lpReserved], eax
0x18004e860  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e867  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18004e86e  mov     r9, rbp
0x18004e871  mov     rcx, [rcx+10h]
0x18004e875  call    WPP_SF_qD
0x18004e87a  jmp     loc_18004E979
0x18004e87f  xor     eax, eax
0x18004e881  xor     esi, esi
0x18004e883  test    eax, eax
0x18004e885  jnz     loc_18004E955
0x18004e88b  xor     edx, edx; Val
0x18004e88d  lea     rcx, [rsp+278h+Name]; void *
0x18004e892  mov     r8d, 208h; Size
0x18004e898  call    memset_0
0x18004e89d  mov     rcx, [rsp+278h+hKey]; hKey
0x18004e8a2  lea     r9, [rsp+278h+cchName]; lpcchName
0x18004e8a7  mov     [rsp+278h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18004e8b0  lea     r8, [rsp+278h+Name]; lpName
0x18004e8b5  mov     [rsp+278h+lpcchClass], 0; lpcchClass
0x18004e8be  mov     edx, esi; dwIndex
0x18004e8c0  mov     [rsp+278h+lpClass], 0; lpClass
0x18004e8c9  mov     [rsp+278h+lpReserved], 0; lpReserved
0x18004e8d2  mov     [rsp+278h+cchName], 104h
0x18004e8da  call    cs:__imp_RegEnumKeyExW
0x18004e8e0  cmp     eax, 103h
0x18004e8e5  jz      short loc_18004E955
0x18004e8e7  test    eax, eax
0x18004e8e9  jz      short loc_18004E8FE
0x18004e8eb  jg      short loc_18004E8F1
0x18004e8ed  mov     ebx, eax
0x18004e8ef  jmp     short loc_18004E8FA
0x18004e8f1  movzx   ebx, ax
0x18004e8f4  or      ebx, 80070000h
0x18004e8fa  test    ebx, ebx
0x18004e8fc  js      short loc_18004E93E
0x18004e8fe  mov     rcx, [rsp+278h+hKey]; hKey
0x18004e903  lea     rdx, [rsp+278h+Name]; lpSubKey
0x18004e908  call    cs:__imp_RegDeleteKeyW
0x18004e90e  test    eax, eax
0x18004e910  jz      short loc_18004E935
0x18004e912  jg      short loc_18004E918
0x18004e914  mov     ebx, eax
0x18004e916  jmp     short loc_18004E921
0x18004e918  movzx   ebx, ax
0x18004e91b  or      ebx, 80070000h
0x18004e921  test    ebx, ebx
0x18004e923  jns     short loc_18004E937
0x18004e925  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004e92c  jb      short loc_18004E979
0x18004e92e  mov     edx, 144h
0x18004e933  jmp     short loc_18004E94C
0x18004e935  xor     ebx, ebx
0x18004e937  inc     esi
0x18004e939  jmp     loc_18004E883
0x18004e93e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004e945  jb      short loc_18004E979
0x18004e947  mov     edx, 143h
0x18004e94c  mov     dword ptr [rsp+278h+lpReserved], ebx
0x18004e950  jmp     loc_18004E860
0x18004e955  mov     rcx, [rsp+278h+hKey]; hKey
0x18004e95a  lea     rdx, aSgch; "SGCH"
0x18004e961  call    cs:__imp_RegDeleteValueW
0x18004e967  mov     rcx, [rsp+278h+hKey]; hKey
0x18004e96c  lea     rdx, aSgchtimestamp; "SGCHTimeStamp"
0x18004e973  call    cs:__imp_RegDeleteValueW
0x18004e979  cmp     [rsp+278h+hKey], 0
0x18004e97f  jz      short loc_18004E98C
0x18004e981  mov     rcx, [rsp+278h+hKey]; hKey
0x18004e986  call    cs:__imp_RegCloseKey
0x18004e98c  mov     eax, ebx
0x18004e98e  mov     rcx, [rsp+278h+var_18]
0x18004e996  xor     rcx, rsp; StackCookie
0x18004e999  call    __security_check_cookie
0x18004e99e  lea     r11, [rsp+278h+var_8]
0x18004e9a6  mov     rbx, [r11+18h]
0x18004e9aa  mov     rbp, [r11+20h]
0x18004e9ae  mov     rsp, r11
0x18004e9b1  pop     rsi
0x18004e9b2  retn
```
