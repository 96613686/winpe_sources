# SetEKPubInUEFI(uchar *,uint *)

- ea: `0x180041cf4`
- end: `0x180041f19`
- name: `?SetEKPubInUEFI@@YAJPEAEPEAI@Z`
- size: `549`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800408c0`
- `0x180040c54`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18004128c`
- `0x180041c64`
- `0x180041cf4`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x180041db9`
- `ntdll!RtlAcquirePrivilege` at `0x180041db9`
- `ntdll!RtlReleasePrivilege` at `0x180041ee3`
- `ntdll!RtlReleasePrivilege` at `0x180041ee3`
- `ntdll!RtlComputeCrc32` at `0x180041e89`
- `ntdll!RtlComputeCrc32` at `0x180041e89`
- `ntdll!RtlNtStatusToDosError` at `0x180041ebe`
- `ntdll!RtlNtStatusToDosError` at `0x180041ebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180041d8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180041d8a`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180041df6`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180041df6`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x180041e33`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x180041eb0`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x180041e33`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableExW` at `0x180041eb0`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180041e0d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180041e0d`

## pseudocode

```c
__int64 __fastcall SetEKPubInUEFI(unsigned __int8 *a1, unsigned int *a2)
{
  int v4; // edi
  unsigned int v5; // ebx
  unsigned __int8 *v6; // rdx
  unsigned int v7; // ecx
  signed int LastError; // eax
  signed int v9; // eax
  ULONG v11; // [rsp+30h] [rbp-D0h] BYREF
  ULONG Privilege; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v13; // [rsp+38h] [rbp-C8h] BYREF
  PVOID ReturnedState; // [rsp+40h] [rbp-C0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  UCHAR Buffer[16]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v17; // [rsp+180h] [rbp+80h]
  _BYTE pBuffer[256]; // [rsp+190h] [rbp+90h] BYREF

  Privilege = 22;
  ReturnedState = 0;
  v11 = 0;
  memset_0(pBuffer, 0, sizeof(pBuffer));
  v13 = 32;
  *(_OWORD *)Buffer = 0;
  v17 = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  GetVersionExW(&VersionInformation);
  if ( VersionInformation.dwMajorVersion >= 6
    && (VersionInformation.dwMajorVersion != 6 || VersionInformation.dwMinorVersion >= 2) )
  {
    v4 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
    if ( (unsigned __int8)IsUEFIFW() )
    {
      if ( v4 < 0 )
      {
        v9 = RtlNtStatusToDosError(v4);
        v5 = v9;
        if ( v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
        return v5;
      }
      v5 = 0;
      if ( !GetFirmwareEnvironmentVariableW(
              L"OfflineUniqueIDEKPub",
              L"{eaec226f-c9a3-477a-a826-ddc716cdc0e3}",
              pBuffer,
              0x100u)
        || (unsigned int)RtlCompareMemory(pBuffer, a1, *a2) != *a2 )
      {
        if ( !(unsigned int)SetFirmwareEnvironmentVariableExW(
                              L"OfflineUniqueIDEKPub",
                              L"{eaec226f-c9a3-477a-a826-ddc716cdc0e3}",
                              a1,
                              *a2,
                              7)
          || GenerateOfflineDeviceID(v7, v6, *a2, a1, Buffer, &v13) >= 0
          && (v11 = RtlComputeCrc32(0, Buffer, 0x20u),
              !(unsigned int)SetFirmwareEnvironmentVariableExW(
                               L"OfflineUniqueIDEKPubCRC",
                               L"{eaec226f-c9a3-477a-a826-ddc716cdc0e3}",
                               &v11,
                               4,
                               7)) )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    else
    {
      v5 = -2147023091;
      if ( v4 < 0 )
        return v5;
    }
    RtlReleasePrivilege(ReturnedState);
    return v5;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180041cf4  mov     [rsp-8+arg_10], rbx
0x180041cf9  mov     [rsp-8+arg_18], rsi
0x180041cfe  push    rbp
0x180041cff  push    rdi
0x180041d00  push    r14
0x180041d02  lea     rbp, [rsp-1A0h]
0x180041d0a  sub     rsp, 2A0h
0x180041d11  mov     rax, cs:__security_cookie
0x180041d18  xor     rax, rsp
0x180041d1b  mov     [rbp+1B0h+var_20], rax
0x180041d22  mov     rsi, rdx
0x180041d25  mov     [rsp+2B0h+Privilege], 16h
0x180041d2d  mov     r14, rcx
0x180041d30  mov     [rsp+2B0h+ReturnedState], 0
0x180041d39  xor     edx, edx; Val
0x180041d3b  mov     [rsp+2B0h+var_280], 0
0x180041d43  lea     rcx, [rbp+1B0h+pBuffer]; void *
0x180041d4a  mov     r8d, 100h; Size
0x180041d50  call    memset_0
0x180041d55  xorps   xmm0, xmm0
0x180041d58  mov     [rsp+2B0h+var_278], 20h ; ' '
0x180041d60  xor     edx, edx; Val
0x180041d62  lea     rcx, [rsp+2B0h+VersionInformation.dwMajorVersion]; void *
0x180041d67  mov     r8d, 110h; Size
0x180041d6d  movups  xmmword ptr [rbp+1B0h+Buffer], xmm0
0x180041d71  movups  [rbp+1B0h+var_130], xmm0
0x180041d78  call    memset_0
0x180041d7d  lea     rcx, [rsp+2B0h+VersionInformation]; lpVersionInformation
0x180041d82  mov     [rsp+2B0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180041d8a  call    cs:__imp_GetVersionExW
0x180041d90  cmp     [rsp+2B0h+VersionInformation.dwMajorVersion], 6
0x180041d95  jb      loc_180041EED
0x180041d9b  jnz     short loc_180041DA8
0x180041d9d  cmp     [rsp+2B0h+VersionInformation.dwMinorVersion], 2
0x180041da2  jb      loc_180041EED
0x180041da8  xor     r8d, r8d; Flags
0x180041dab  lea     r9, [rsp+2B0h+ReturnedState]; ReturnedState
0x180041db0  lea     rcx, [rsp+2B0h+Privilege]; Privilege
0x180041db5  lea     edx, [r8+1]; NumPriv
0x180041db9  call    cs:__imp_RtlAcquirePrivilege
0x180041dbf  mov     edi, eax
0x180041dc1  call    IsUEFIFW
0x180041dc6  test    al, al
0x180041dc8  jz      loc_180041ED5
0x180041dce  test    edi, edi
0x180041dd0  js      loc_180041EBC
0x180041dd6  lea     rdi, Guid; "{eaec226f-c9a3-477a-a826-ddc716cdc0e3}"
0x180041ddd  mov     r9d, 100h; nSize
0x180041de3  mov     rdx, rdi; lpGuid
0x180041de6  lea     r8, [rbp+1B0h+pBuffer]; pBuffer
0x180041ded  lea     rcx, aOfflineuniquei_1; "OfflineUniqueIDEKPub"
0x180041df4  xor     ebx, ebx
0x180041df6  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180041dfc  test    eax, eax
0x180041dfe  jz      short loc_180041E1B
0x180041e00  mov     r8d, [rsi]; Length
0x180041e03  lea     rcx, [rbp+1B0h+pBuffer]; Source1
0x180041e0a  mov     rdx, r14; Source2
0x180041e0d  call    cs:__imp_RtlCompareMemory
0x180041e13  cmp     eax, [rsi]
0x180041e15  jz      loc_180041EDE
0x180041e1b  mov     r9d, [rsi]
0x180041e1e  lea     rcx, aOfflineuniquei_1; "OfflineUniqueIDEKPub"
0x180041e25  mov     r8, r14
0x180041e28  mov     dword ptr [rsp+2B0h+var_290], 7
0x180041e30  mov     rdx, rdi
0x180041e33  call    cs:__imp_SetFirmwareEnvironmentVariableExW
0x180041e39  test    eax, eax
0x180041e3b  jnz     short loc_180041E5B
0x180041e3d  call    cs:__imp_GetLastError
0x180041e43  mov     ebx, eax
0x180041e45  test    eax, eax
0x180041e47  jle     loc_180041EDE
0x180041e4d  movzx   ebx, ax
0x180041e50  or      ebx, 80070000h
0x180041e56  jmp     loc_180041EDE
0x180041e5b  mov     r8d, [rsi]; unsigned int
0x180041e5e  lea     rax, [rsp+2B0h+var_278]
0x180041e63  mov     [rsp+2B0h+var_288], rax; unsigned int *
0x180041e68  mov     r9, r14; unsigned __int8 *
0x180041e6b  lea     rax, [rbp+1B0h+Buffer]
0x180041e6f  mov     [rsp+2B0h+var_290], rax; unsigned __int8 *
0x180041e74  call    ?GenerateOfflineDeviceID@@YAJIPEAEI00PEAI@Z; GenerateOfflineDeviceID(uint,uchar *,uint,uchar *,uchar *,uint *)
0x180041e79  test    eax, eax
0x180041e7b  js      short loc_180041EDE
0x180041e7d  mov     r8d, 20h ; ' '; Length
0x180041e83  lea     rdx, [rbp+1B0h+Buffer]; Buffer
0x180041e87  xor     ecx, ecx; InitialCrc
0x180041e89  call    cs:__imp_RtlComputeCrc32
0x180041e8f  mov     r9d, 4
0x180041e95  mov     dword ptr [rsp+2B0h+var_290], 7
0x180041e9d  lea     r8, [rsp+2B0h+var_280]
0x180041ea2  mov     [rsp+2B0h+var_280], eax
0x180041ea6  mov     rdx, rdi
0x180041ea9  lea     rcx, aOfflineuniquei_2; "OfflineUniqueIDEKPubCRC"
0x180041eb0  call    cs:__imp_SetFirmwareEnvironmentVariableExW
0x180041eb6  test    eax, eax
0x180041eb8  jnz     short loc_180041EDE
0x180041eba  jmp     short loc_180041E3D
0x180041ebc  mov     ecx, edi; Status
0x180041ebe  call    cs:__imp_RtlNtStatusToDosError
0x180041ec4  mov     ebx, eax
0x180041ec6  test    eax, eax
0x180041ec8  jle     short loc_180041EE9
0x180041eca  movzx   ebx, ax
0x180041ecd  or      ebx, 80070000h
0x180041ed3  jmp     short loc_180041EE9
0x180041ed5  mov     ebx, 8007070Dh
0x180041eda  test    edi, edi
0x180041edc  js      short loc_180041EE9
0x180041ede  mov     rcx, [rsp+2B0h+ReturnedState]; ReturnedState
0x180041ee3  call    cs:__imp_RtlReleasePrivilege
0x180041ee9  mov     eax, ebx
0x180041eeb  jmp     short loc_180041EF2
0x180041eed  mov     eax, 80004005h
0x180041ef2  mov     rcx, [rbp+1B0h+var_20]
0x180041ef9  xor     rcx, rsp; StackCookie
0x180041efc  call    __security_check_cookie
0x180041f01  lea     r11, [rsp+2B0h+var_10]
0x180041f09  mov     rbx, [r11+30h]
0x180041f0d  mov     rsi, [r11+38h]
0x180041f11  mov     rsp, r11
0x180041f14  pop     r14
0x180041f16  pop     rdi
0x180041f17  pop     rbp
0x180041f18  retn
```
