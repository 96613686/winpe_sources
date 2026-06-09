# FontCacheServiceConfiguration::GetFileCacheSizeCap(wchar_t const *)

- ea: `0x1800b1050`
- end: `0x1800b10e8`
- name: `?GetFileCacheSizeCap@FontCacheServiceConfiguration@@SAIPEB_W@Z`
- size: `152`
- prototype: `unsigned int __fastcall(LPCWSTR lpDirectoryName)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800b1734`

## callees

- `0x180068da0`
- `0x1800b1050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1800b109c`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1800b109c`

## string_xrefs

- `0x1800b1072`: `SYSTEM\CurrentControlSet\Services\FontCache\Parameters`

## pseudocode

```c
__int64 __fastcall FontCacheServiceConfiguration::GetFileCacheSizeCap(LPCWSTR lpDirectoryName)
{
  __int64 result; // rax
  ULONGLONG v3; // rax
  unsigned int v4; // [rsp+38h] [rbp+10h] BYREF
  _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  RegistryKey::TryGetNumber(
    2147483650LL,
    L"SYSTEM\\CurrentControlSet\\Services\\FontCache\\Parameters",
    L"FileStorageCap",
    &v4);
  result = v4;
  if ( !v4 )
  {
    TotalNumberOfBytes.QuadPart = 0;
    if ( GetDiskFreeSpaceExW(lpDirectoryName, 0, &TotalNumberOfBytes, 0) )
    {
      v3 = TotalNumberOfBytes.QuadPart >> 30;
      if ( TotalNumberOfBytes.QuadPart >> 30 < 0x80 )
      {
        if ( v3 < 0x40 )
          return v3 < 0x20 ? 52428800 : 104857600;
        else
          return 209715200;
      }
      else
      {
        return 524288000;
      }
    }
    else
    {
      return 52428800;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b1050  push    rbx
0x1800b1052  sub     rsp, 20h
0x1800b1056  mov     rbx, rcx
0x1800b1059  mov     [rsp+28h+arg_8], 0
0x1800b1061  mov     ecx, 80000002h
0x1800b1066  lea     r9, [rsp+28h+arg_8]
0x1800b106b  lea     r8, ?FileStorageCapValueName@@3QB_WB; "FileStorageCap"
0x1800b1072  lea     rdx, ?FontCacheServiceConfigurationKey@@3QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Fo"...
0x1800b1079  call    ?TryGetNumber@RegistryKey@@SA_NW4RegistryHive@@PEB_W1PEAI@Z; RegistryKey::TryGetNumber(RegistryHive,wchar_t const *,wchar_t const *,uint *)
0x1800b107e  mov     eax, [rsp+28h+arg_8]
0x1800b1082  test    eax, eax
0x1800b1084  jnz     short loc_1800B10E2
0x1800b1086  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x1800b1089  mov     qword ptr [rsp+28h+TotalNumberOfBytes], 0
0x1800b1092  lea     r8, [rsp+28h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1800b1097  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1800b1099  mov     rcx, rbx; lpDirectoryName
0x1800b109c  call    cs:__imp_GetDiskFreeSpaceExW
0x1800b10a2  test    eax, eax
0x1800b10a4  jz      short loc_1800B10DD
0x1800b10a6  mov     rax, qword ptr [rsp+28h+TotalNumberOfBytes]
0x1800b10ab  shr     rax, 1Eh
0x1800b10af  cmp     rax, 80h
0x1800b10b5  jb      short loc_1800B10BE
0x1800b10b7  mov     eax, 1F400000h
0x1800b10bc  jmp     short loc_1800B10E2
0x1800b10be  cmp     rax, 40h ; '@'
0x1800b10c2  jb      short loc_1800B10CB
0x1800b10c4  mov     eax, 0C800000h
0x1800b10c9  jmp     short loc_1800B10E2
0x1800b10cb  cmp     rax, 20h ; ' '
0x1800b10cf  sbb     eax, eax
0x1800b10d1  and     eax, 0FCE00000h
0x1800b10d6  add     eax, 6400000h
0x1800b10db  jmp     short loc_1800B10E2
0x1800b10dd  mov     eax, 3200000h
0x1800b10e2  add     rsp, 20h
0x1800b10e6  pop     rbx
0x1800b10e7  retn
```
