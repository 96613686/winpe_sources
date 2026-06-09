# PerflibciEnsureCounterSetList(void)

- ea: `0x180006ad4`
- end: `0x180006fd5`
- name: `?PerflibciEnsureCounterSetList@@YAKXZ`
- size: `1281`
- prototype: `unsigned int(void)`
- caller_count: `6`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002ef8`
- `0x180004980`
- `0x180004ec0`
- `0x180005b20`
- `0x18000a440`
- `0x18000c6f0`

## callees

- `0x180002e40`
- `0x180006ad4`
- `0x180006fe0`
- `0x18000a5d8`
- `0x18000c03c`
- `0x18000ecf0`
- `0x18002e164`
- `0x1800344d4`
- `0x18007205a`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180006c08`
- `ntdll!NtOpenKey` at `0x180006caa`
- `ntdll!NtOpenKey` at `0x180006dd9`
- `ntdll!NtOpenKey` at `0x180006f8d`
- `ntdll!NtOpenKey` at `0x180006c08`
- `ntdll!NtOpenKey` at `0x180006caa`
- `ntdll!NtOpenKey` at `0x180006dd9`
- `ntdll!NtOpenKey` at `0x180006f8d`
- `ntdll!NtEnumerateKey` at `0x180006e44`
- `ntdll!NtEnumerateKey` at `0x180006e44`
- `ntdll!RtlNtStatusToDosError` at `0x180006c16`
- `ntdll!RtlNtStatusToDosError` at `0x180006cb8`
- `ntdll!RtlNtStatusToDosError` at `0x180006de7`
- `ntdll!RtlNtStatusToDosError` at `0x180006f9b`
- `ntdll!RtlNtStatusToDosError` at `0x180006fb8`
- `ntdll!RtlNtStatusToDosError` at `0x180006c16`
- `ntdll!RtlNtStatusToDosError` at `0x180006cb8`
- `ntdll!RtlNtStatusToDosError` at `0x180006de7`
- `ntdll!RtlNtStatusToDosError` at `0x180006f9b`
- `ntdll!RtlNtStatusToDosError` at `0x180006fb8`
- `ntdll!RtlInitUnicodeString` at `0x180006bd4`
- `ntdll!RtlInitUnicodeString` at `0x180006c76`
- `ntdll!RtlInitUnicodeString` at `0x180006da5`
- `ntdll!RtlInitUnicodeString` at `0x180006f59`
- `ntdll!RtlInitUnicodeString` at `0x180006bd4`
- `ntdll!RtlInitUnicodeString` at `0x180006c76`
- `ntdll!RtlInitUnicodeString` at `0x180006da5`
- `ntdll!RtlInitUnicodeString` at `0x180006f59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006ee2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006f18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006ee2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006f18`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006b32`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006b32`
- `KERNEL32!LocalFree` at `0x180006e7f`
- `KERNEL32!LocalFree` at `0x180006e7f`
- `KERNEL32!WaitForSingleObject` at `0x180006b1b`
- `KERNEL32!WaitForSingleObject` at `0x180006b1b`
- `KERNEL32!ReleaseMutex` at `0x180006c43`
- `KERNEL32!ReleaseMutex` at `0x180006c43`

## string_xrefs

- `0x180006bb9`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`
- `0x180006c5b`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
DWORD PerflibciEnsureCounterSetList(void)
{
  DWORD result; // eax
  ULONG v1; // ebx
  char v2; // si
  NTSTATUS v3; // eax
  __int64 v4; // rcx
  unsigned int *v5; // r8
  NTSTATUS v6; // eax
  unsigned int *v7; // r8
  unsigned int v8; // eax
  HANDLE v9; // rbx
  NTSTATUS v10; // eax
  char *v11; // rdi
  ULONG v12; // ebx
  int i; // r14d
  int v14; // eax
  unsigned int v15; // eax
  HANDLE v16; // rbx
  NTSTATUS v17; // eax
  HANDLE KeyHandle; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int8 v19[8]; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v20; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-31h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-21h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+Fh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int Data; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v26; // [rsp+F8h] [rbp+6Fh] BYREF
  unsigned int v27; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v28; // [rsp+108h] [rbp+7Fh] BYREF

  KeyHandle = 0;
  v20 = 0;
  ResultLength = 0;
  v27 = 0;
  *(_DWORD *)v19 = 0;
  Data = 0;
  SystemTimeAsFileTime = 0;
  if ( !g_hGlobalMutex )
    return 87;
  result = WaitForSingleObject(g_hGlobalMutex, 0xEA60u);
  if ( !result )
  {
    v1 = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( *(_QWORD *)&SystemTimeAsFileTime < g_LastRefreshTime + 18000000000LL )
    {
LABEL_4:
      PerflibciLocalReleaseMutex(g_hGlobalMutex);
      if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        PerflibciCloseKey(KeyHandle);
      return v1;
    }
    PerflibciSetObjectsValidityState(0);
    if ( (unsigned int)PerfpAcquireInstallationMutex() )
    {
      v2 = 0;
    }
    else
    {
      KeyHandle = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      DestinationString = 0;
      RtlInitUnicodeString(
        &DestinationString,
        L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = NtOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
      v2 = 1;
      if ( !RtlNtStatusToDosError(v6) )
      {
LABEL_15:
        v26 = 0;
        v28 = 4;
        v1 = PrivateRegQueryValueExT((HKEY)KeyHandle, L"Last Counter", v5, &v26, (unsigned __int8 *)&v27, &v28, 1);
        if ( v1 )
          goto LABEL_12;
        if ( v26 != 4 )
          goto LABEL_41;
        v26 = 0;
        v28 = 4;
        v1 = PrivateRegQueryValueExT((HKEY)KeyHandle, L"Last Help", v7, &v26, v19, &v28, 1);
        if ( v1 )
          goto LABEL_12;
        if ( v26 == 4 )
        {
          v8 = *(_DWORD *)v19;
          if ( v27 > *(_DWORD *)v19 )
            v8 = v27;
          Data = v8;
          if ( v2 )
          {
            v9 = KeyHandle;
            v20 = 0;
            memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
            DestinationString = 0;
            RtlInitUnicodeString(&DestinationString, L"_V2Providers");
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &DestinationString;
            ObjectAttributes.RootDirectory = v9;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v10 = NtOpenKey(&v20, 0x2001Fu, &ObjectAttributes);
            if ( !RtlNtStatusToDosError(v10) )
              goto LABEL_44;
          }
          v16 = KeyHandle;
          v20 = 0;
          memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"_V2Providers");
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.RootDirectory = v16;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v17 = NtOpenKey(&v20, 0x20019u, &ObjectAttributes);
          v1 = RtlNtStatusToDosError(v17);
          if ( !v1 )
          {
LABEL_44:
            v11 = (char *)operator new(1048);
            if ( v11 )
            {
              v12 = 0;
              for ( i = 0; ; ++i )
              {
                memset_0(v11, 0, 0x418u);
                v14 = NtEnumerateKey(v20, v12, KeyBasicInformation, v11, 0x418u, &ResultLength);
                v12 = i + 1;
                if ( v14 < 0 )
                  break;
                PerflibciBuildProvider(v20, v11 + 16, &Data);
              }
              v1 = v14 == -2147483622 ? 0 : RtlNtStatusToDosError(v14);
              LocalFree(v11);
            }
            else
            {
              v1 = 14;
            }
            PerflibciCloseKey(v20);
            if ( !v1 )
            {
              g_LastRefreshTime = (unsigned __int64)SystemTimeAsFileTime;
              if ( !v2 )
                goto LABEL_4;
              v15 = *(_DWORD *)v19;
              if ( v27 > *(_DWORD *)v19 )
                v15 = v27;
              if ( v15 != Data && !RegSetValueExW((HKEY)KeyHandle, L"Last Counter", 0, 4u, (const BYTE *)&Data, 4u) )
              {
                ++Data;
                RegSetValueExW((HKEY)KeyHandle, L"Last Help", 0, 4u, (const BYTE *)&Data, 4u);
              }
              goto LABEL_13;
            }
          }
        }
        else
        {
LABEL_41:
          v1 = 13;
        }
LABEL_12:
        LOBYTE(v4) = 1;
        PerflibciSetObjectsValidityState(v4);
        if ( !v2 )
          goto LABEL_4;
LABEL_13:
        ReleaseMutex(hHandle);
        goto LABEL_4;
      }
    }
    KeyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    DestinationString = 0;
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v3 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    v1 = RtlNtStatusToDosError(v3);
    if ( v1 )
      goto LABEL_12;
    goto LABEL_15;
  }
  return result;
}

```

## disassembly

```asm
0x180006ad4  push    rbp
0x180006ad6  push    rbx
0x180006ad7  push    rsi
0x180006ad8  push    rdi
0x180006ad9  push    r12
0x180006adb  push    r14
0x180006add  push    r15
0x180006adf  lea     rbp, [rsp-27h]
0x180006ae4  sub     rsp, 0B0h
0x180006aeb  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; hHandle
0x180006af2  xor     r15d, r15d
0x180006af5  mov     [rbp+57h+KeyHandle], r15
0x180006af9  mov     [rbp+57h+var_90], r15
0x180006afd  mov     [rbp+57h+var_48], r15d
0x180006b01  mov     [rbp+57h+arg_10], r15d
0x180006b05  mov     dword ptr [rbp+57h+var_98], r15d
0x180006b09  mov     [rbp+57h+Data], r15d
0x180006b0d  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180006b11  test    rcx, rcx
0x180006b14  jz      short loc_180006B8B
0x180006b16  mov     edx, 0EA60h; dwMilliseconds
0x180006b1b  call    cs:__imp_WaitForSingleObject
0x180006b22  nop     dword ptr [rax+rax+00h]
0x180006b27  test    eax, eax
0x180006b29  jnz     short loc_180006B71
0x180006b2b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006b2f  mov     ebx, r15d
0x180006b32  call    cs:__imp_GetSystemTimeAsFileTime
0x180006b39  nop     dword ptr [rax+rax+00h]
0x180006b3e  mov     rcx, 430E23400h
0x180006b48  add     rcx, cs:?g_LastRefreshTime@@3_KA; unsigned __int64 g_LastRefreshTime
0x180006b4f  cmp     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180006b53  jnb     short loc_180006B92
0x180006b55  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180006b5c  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x180006b61  mov     rcx, [rbp+57h+KeyHandle]
0x180006b65  lea     rax, [rcx-1]
0x180006b69  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006b6d  jbe     short loc_180006B84
0x180006b6f  mov     eax, ebx
0x180006b71  add     rsp, 0B0h
0x180006b78  pop     r15
0x180006b7a  pop     r14
0x180006b7c  pop     r12
0x180006b7e  pop     rdi
0x180006b7f  pop     rsi
0x180006b80  pop     rbx
0x180006b81  pop     rbp
0x180006b82  retn
0x180006b84  call    PerflibciCloseKey
0x180006b89  jmp     short loc_180006B6F
0x180006b8b  mov     eax, 57h ; 'W'
0x180006b90  jmp     short loc_180006B71
0x180006b92  xor     ecx, ecx
0x180006b94  call    PerflibciSetObjectsValidityState
0x180006b99  call    PerfpAcquireInstallationMutex
0x180006b9e  mov     edi, 30h ; '0'
0x180006ba3  lea     r14d, [rdi+10h]
0x180006ba7  test    eax, eax
0x180006ba9  jz      loc_180006C54
0x180006baf  mov     sil, r15b
0x180006bb2  xorps   xmm0, xmm0
0x180006bb5  mov     [rbp+57h+KeyHandle], r15
0x180006bb9  lea     rdx, SourceString; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180006bc0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006bc4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006bc8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006bcc  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006bd0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006bd4  call    cs:__imp_RtlInitUnicodeString
0x180006bdb  nop     dword ptr [rax+rax+00h]
0x180006be0  lea     rax, [rbp+57h+DestinationString]
0x180006be4  mov     [rbp+57h+ObjectAttributes.Length], edi
0x180006be7  xorps   xmm0, xmm0
0x180006bea  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006bee  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006bf2  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180006bf6  mov     edx, 20019h; DesiredAccess
0x180006bfb  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x180006bff  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180006c03  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006c08  call    cs:__imp_NtOpenKey
0x180006c0f  nop     dword ptr [rax+rax+00h]
0x180006c14  mov     ecx, eax; Status
0x180006c16  call    cs:__imp_RtlNtStatusToDosError
0x180006c1d  nop     dword ptr [rax+rax+00h]
0x180006c22  mov     ebx, eax
0x180006c24  test    eax, eax
0x180006c26  jz      loc_180006CCF
0x180006c2c  mov     cl, 1
0x180006c2e  call    PerflibciSetObjectsValidityState
0x180006c33  test    sil, sil
0x180006c36  jz      loc_180006B55
0x180006c3c  mov     rcx, cs:hHandle; hMutex
0x180006c43  call    cs:__imp_ReleaseMutex
0x180006c4a  nop     dword ptr [rax+rax+00h]
0x180006c4f  jmp     loc_180006B55
0x180006c54  xorps   xmm0, xmm0
0x180006c57  mov     [rbp+57h+KeyHandle], r15
0x180006c5b  lea     rdx, SourceString; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180006c62  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006c66  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006c6a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006c6e  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006c72  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006c76  call    cs:__imp_RtlInitUnicodeString
0x180006c7d  nop     dword ptr [rax+rax+00h]
0x180006c82  lea     rax, [rbp+57h+DestinationString]
0x180006c86  mov     [rbp+57h+ObjectAttributes.Length], edi
0x180006c89  xorps   xmm0, xmm0
0x180006c8c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006c90  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006c94  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180006c98  mov     edx, 2001Fh; DesiredAccess
0x180006c9d  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x180006ca1  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180006ca5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006caa  call    cs:__imp_NtOpenKey
0x180006cb1  nop     dword ptr [rax+rax+00h]
0x180006cb6  mov     ecx, eax; Status
0x180006cb8  call    cs:__imp_RtlNtStatusToDosError
0x180006cbf  nop     dword ptr [rax+rax+00h]
0x180006cc4  mov     sil, 1
0x180006cc7  test    eax, eax
0x180006cc9  jnz     loc_180006BB2
0x180006ccf  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180006cd3  lea     rax, [rbp+57h+arg_18]
0x180006cd7  mov     [rsp+0E0h+var_B0], 1; int
0x180006cdf  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x180006ce3  mov     [rsp+0E0h+ResultLength], rax; unsigned int *
0x180006ce8  lea     rdx, ?LastCounter@@3QBGB; "Last Counter"
0x180006cef  lea     rax, [rbp+57h+arg_10]
0x180006cf3  mov     [rbp+57h+arg_8], r15d
0x180006cf7  mov     r12d, 4
0x180006cfd  mov     qword ptr [rsp+0E0h+Length], rax; unsigned __int8 *
0x180006d02  mov     [rbp+57h+arg_18], r12d
0x180006d06  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180006d0b  mov     ebx, eax
0x180006d0d  test    eax, eax
0x180006d0f  jnz     loc_180006C2C
0x180006d15  cmp     [rbp+57h+arg_8], r12d
0x180006d19  jnz     loc_180006FCB
0x180006d1f  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180006d23  lea     rax, [rbp+57h+arg_18]
0x180006d27  mov     [rsp+0E0h+var_B0], 1; int
0x180006d2f  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x180006d33  mov     [rsp+0E0h+ResultLength], rax; unsigned int *
0x180006d38  lea     rdx, ?LastHelp@@3QBGB; "Last Help"
0x180006d3f  lea     rax, [rbp+57h+var_98]
0x180006d43  mov     [rbp+57h+arg_8], r15d
0x180006d47  mov     qword ptr [rsp+0E0h+Length], rax; unsigned __int8 *
0x180006d4c  mov     [rbp+57h+arg_18], r12d
0x180006d50  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180006d55  mov     ebx, eax
0x180006d57  test    eax, eax
0x180006d59  jnz     loc_180006C2C
0x180006d5f  cmp     [rbp+57h+arg_8], r12d
0x180006d63  jnz     loc_180006FCB
0x180006d69  mov     eax, dword ptr [rbp+57h+var_98]
0x180006d6c  cmp     [rbp+57h+arg_10], eax
0x180006d6f  cmova   eax, [rbp+57h+arg_10]
0x180006d73  mov     [rbp+57h+Data], eax
0x180006d76  test    sil, sil
0x180006d79  jz      loc_180006F33
0x180006d7f  mov     rbx, [rbp+57h+KeyHandle]
0x180006d83  lea     rdx, aV2providers; "_V2Providers"
0x180006d8a  xorps   xmm0, xmm0
0x180006d8d  mov     [rbp+57h+var_90], r15
0x180006d91  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006d95  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006d99  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006d9d  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006da1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006da5  call    cs:__imp_RtlInitUnicodeString
0x180006dac  nop     dword ptr [rax+rax+00h]
0x180006db1  lea     rax, [rbp+57h+DestinationString]
0x180006db5  mov     [rbp+57h+ObjectAttributes.Length], edi
0x180006db8  xorps   xmm0, xmm0
0x180006dbb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006dbf  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006dc3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180006dc7  mov     edx, 2001Fh; DesiredAccess
0x180006dcc  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x180006dd0  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x180006dd4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006dd9  call    cs:__imp_NtOpenKey
0x180006de0  nop     dword ptr [rax+rax+00h]
0x180006de5  mov     ecx, eax; Status
0x180006de7  call    cs:__imp_RtlNtStatusToDosError
0x180006dee  nop     dword ptr [rax+rax+00h]
0x180006df3  test    eax, eax
0x180006df5  jnz     loc_180006F33
0x180006dfb  mov     ecx, 418h
0x180006e00  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180006e05  mov     rdi, rax
0x180006e08  test    rax, rax
0x180006e0b  jz      loc_180006F29
0x180006e11  mov     ebx, r15d
0x180006e14  mov     r14d, r15d
0x180006e17  xor     edx, edx; Val
0x180006e19  mov     r8d, 418h; Size
0x180006e1f  mov     rcx, rdi; void *
0x180006e22  call    memset_0
0x180006e27  mov     rcx, [rbp+57h+var_90]; KeyHandle
0x180006e2b  lea     rax, [rbp+57h+var_48]
0x180006e2f  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x180006e34  mov     r9, rdi; KeyInformation
0x180006e37  xor     r8d, r8d; KeyInformationClass
0x180006e3a  mov     [rsp+0E0h+Length], 418h; Length
0x180006e42  mov     edx, ebx; Index
0x180006e44  call    cs:__imp_NtEnumerateKey
0x180006e4b  nop     dword ptr [rax+rax+00h]
0x180006e50  lea     ebx, [r14+1]
0x180006e54  test    eax, eax
0x180006e56  js      short loc_180006E6E
0x180006e58  mov     rcx, [rbp+57h+var_90]
0x180006e5c  lea     rdx, [rdi+10h]
0x180006e60  lea     r8, [rbp+57h+Data]
0x180006e64  call    PerflibciBuildProvider
0x180006e69  mov     r14d, ebx
0x180006e6c  jmp     short loc_180006E17
0x180006e6e  cmp     eax, 8000001Ah
0x180006e73  jnz     loc_180006FB6
0x180006e79  mov     ebx, r15d
0x180006e7c  mov     rcx, rdi; hMem
0x180006e7f  call    cs:__imp_LocalFree
0x180006e86  nop     dword ptr [rax+rax+00h]
0x180006e8b  mov     rcx, [rbp+57h+var_90]
0x180006e8f  call    PerflibciCloseKey
0x180006e94  test    ebx, ebx
0x180006e96  jnz     loc_180006C2C
0x180006e9c  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180006ea0  mov     cs:?g_LastRefreshTime@@3_KA, rax; unsigned __int64 g_LastRefreshTime
0x180006ea7  test    sil, sil
0x180006eaa  jz      loc_180006B55
0x180006eb0  mov     eax, dword ptr [rbp+57h+var_98]
0x180006eb3  cmp     [rbp+57h+arg_10], eax
0x180006eb6  cmova   eax, [rbp+57h+arg_10]
0x180006eba  cmp     eax, [rbp+57h+Data]
0x180006ebd  jz      loc_180006C3C
0x180006ec3  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x180006ec7  lea     rax, [rbp+57h+Data]
0x180006ecb  mov     dword ptr [rsp+0E0h+ResultLength], r12d; cbData
0x180006ed0  lea     rdx, ?LastCounter@@3QBGB; "Last Counter"
0x180006ed7  mov     r9d, r12d; dwType
0x180006eda  mov     qword ptr [rsp+0E0h+Length], rax; lpData
0x180006edf  xor     r8d, r8d; Reserved
0x180006ee2  call    cs:__imp_RegSetValueExW
0x180006ee9  nop     dword ptr [rax+rax+00h]
0x180006eee  test    eax, eax
0x180006ef0  jnz     loc_180006C3C
0x180006ef6  inc     [rbp+57h+Data]
0x180006ef9  lea     rax, [rbp+57h+Data]
0x180006efd  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x180006f01  lea     rdx, ?LastHelp@@3QBGB; "Last Help"
0x180006f08  mov     dword ptr [rsp+0E0h+ResultLength], r12d; cbData
0x180006f0d  mov     r9d, r12d; dwType
0x180006f10  xor     r8d, r8d; Reserved
0x180006f13  mov     qword ptr [rsp+0E0h+Length], rax; lpData
0x180006f18  call    cs:__imp_RegSetValueExW
0x180006f1f  nop     dword ptr [rax+rax+00h]
0x180006f24  jmp     loc_180006C3C
0x180006f29  mov     ebx, 0Eh
0x180006f2e  jmp     loc_180006E8B
0x180006f33  mov     rbx, [rbp+57h+KeyHandle]
0x180006f37  lea     rdx, aV2providers; "_V2Providers"
0x180006f3e  xorps   xmm0, xmm0
0x180006f41  mov     [rbp+57h+var_90], r15
0x180006f45  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006f49  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006f4d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006f51  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006f55  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006f59  call    cs:__imp_RtlInitUnicodeString
0x180006f60  nop     dword ptr [rax+rax+00h]
0x180006f65  lea     rax, [rbp+57h+DestinationString]
0x180006f69  mov     [rbp+57h+ObjectAttributes.Length], edi
0x180006f6c  xorps   xmm0, xmm0
0x180006f6f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006f73  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006f77  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180006f7b  mov     edx, 20019h; DesiredAccess
0x180006f80  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x180006f84  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x180006f88  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006f8d  call    cs:__imp_NtOpenKey
0x180006f94  nop     dword ptr [rax+rax+00h]
0x180006f99  mov     ecx, eax; Status
0x180006f9b  call    cs:__imp_RtlNtStatusToDosError
0x180006fa2  nop     dword ptr [rax+rax+00h]
0x180006fa7  mov     ebx, eax
0x180006fa9  test    eax, eax
0x180006fab  jz      loc_180006DFB
0x180006fb1  jmp     loc_180006C2C
0x180006fb6  mov     ecx, eax; Status
0x180006fb8  call    cs:__imp_RtlNtStatusToDosError
0x180006fbf  nop     dword ptr [rax+rax+00h]
0x180006fc4  mov     ebx, eax
0x180006fc6  jmp     loc_180006E7C
0x180006fcb  mov     ebx, 0Dh
  ... truncated ...
```
