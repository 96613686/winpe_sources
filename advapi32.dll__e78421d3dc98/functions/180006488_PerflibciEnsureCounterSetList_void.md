# PerflibciEnsureCounterSetList(void)

- ea: `0x180006488`
- end: `0x180006922`
- name: `?PerflibciEnsureCounterSetList@@YAKXZ`
- size: `1178`
- prototype: `unsigned int(void)`
- caller_count: `6`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800017f4`
- `0x180004470`
- `0x180004990`
- `0x1800055a0`
- `0x1800160c0`
- `0x18002c0d4`

## callees

- `0x180001ca4`
- `0x180003494`
- `0x180006488`
- `0x180015e40`
- `0x180017100`
- `0x18002aeb4`
- `0x180030430`
- `0x18006505a`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800065bb`
- `ntdll!NtOpenKey` at `0x180006645`
- `ntdll!NtOpenKey` at `0x180006762`
- `ntdll!NtOpenKey` at `0x1800068ec`
- `ntdll!NtOpenKey` at `0x1800065bb`
- `ntdll!NtOpenKey` at `0x180006645`
- `ntdll!NtOpenKey` at `0x180006762`
- `ntdll!NtOpenKey` at `0x1800068ec`
- `ntdll!NtEnumerateKey` at `0x1800067c1`
- `ntdll!NtEnumerateKey` at `0x1800067c1`
- `ntdll!RtlNtStatusToDosError` at `0x1800065c3`
- `ntdll!RtlNtStatusToDosError` at `0x18000664d`
- `ntdll!RtlNtStatusToDosError` at `0x18000676a`
- `ntdll!RtlNtStatusToDosError` at `0x1800068f4`
- `ntdll!RtlNtStatusToDosError` at `0x18000690b`
- `ntdll!RtlNtStatusToDosError` at `0x1800065c3`
- `ntdll!RtlNtStatusToDosError` at `0x18000664d`
- `ntdll!RtlNtStatusToDosError` at `0x18000676a`
- `ntdll!RtlNtStatusToDosError` at `0x1800068f4`
- `ntdll!RtlNtStatusToDosError` at `0x18000690b`
- `ntdll!RtlInitUnicodeString` at `0x18000658d`
- `ntdll!RtlInitUnicodeString` at `0x180006617`
- `ntdll!RtlInitUnicodeString` at `0x180006734`
- `ntdll!RtlInitUnicodeString` at `0x1800068be`
- `ntdll!RtlInitUnicodeString` at `0x18000658d`
- `ntdll!RtlInitUnicodeString` at `0x180006617`
- `ntdll!RtlInitUnicodeString` at `0x180006734`
- `ntdll!RtlInitUnicodeString` at `0x1800068be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006853`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006883`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006853`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006883`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800064e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800064e0`
- `KERNEL32!LocalFree` at `0x1800067f6`
- `KERNEL32!LocalFree` at `0x1800067f6`
- `KERNEL32!GetLastError` at `0x180006535`
- `KERNEL32!GetLastError` at `0x180006535`
- `KERNEL32!WaitForSingleObject` at `0x1800064cf`
- `KERNEL32!WaitForSingleObject` at `0x1800064cf`
- `KERNEL32!ReleaseMutex` at `0x180006509`
- `KERNEL32!ReleaseMutex` at `0x1800065ea`
- `KERNEL32!ReleaseMutex` at `0x180006509`
- `KERNEL32!ReleaseMutex` at `0x1800065ea`

## string_xrefs

- `0x180006572`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`
- `0x1800065fc`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

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
  WCHAR *v11; // rdi
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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-21h] BYREF
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
      goto LABEL_4;
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
LABEL_18:
        v26 = 0;
        v28 = 4;
        v1 = PrivateRegQueryValueExT((HKEY)KeyHandle, L"Last Counter", v5, &v26, (unsigned __int8 *)&v27, &v28, 1);
        if ( v1 )
          goto LABEL_15;
        if ( v26 != 4 )
          goto LABEL_44;
        v26 = 0;
        v28 = 4;
        v1 = PrivateRegQueryValueExT((HKEY)KeyHandle, L"Last Help", v7, &v26, v19, &v28, 1);
        if ( v1 )
          goto LABEL_15;
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
              goto LABEL_47;
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
LABEL_47:
            v11 = (WCHAR *)operator new(1048);
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
                PerflibciBuildProvider((char *)v20, v11 + 8, (__int64)&Data);
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
              {
LABEL_4:
                if ( g_hGlobalMutex && !ReleaseMutex(g_hGlobalMutex) )
                  GetLastError();
                if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                  PerflibciCloseKey(KeyHandle);
                return v1;
              }
              v15 = *(_DWORD *)v19;
              if ( v27 > *(_DWORD *)v19 )
                v15 = v27;
              if ( v15 != Data && !RegSetValueExW((HKEY)KeyHandle, L"Last Counter", 0, 4u, (const BYTE *)&Data, 4u) )
              {
                ++Data;
                RegSetValueExW((HKEY)KeyHandle, L"Last Help", 0, 4u, (const BYTE *)&Data, 4u);
              }
LABEL_16:
              ReleaseMutex(hHandle);
              goto LABEL_4;
            }
          }
        }
        else
        {
LABEL_44:
          v1 = 13;
        }
LABEL_15:
        LOBYTE(v4) = 1;
        PerflibciSetObjectsValidityState(v4);
        if ( !v2 )
          goto LABEL_4;
        goto LABEL_16;
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
      goto LABEL_15;
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x180006488  push    rbp
0x18000648a  push    rbx
0x18000648b  push    rsi
0x18000648c  push    rdi
0x18000648d  push    r12
0x18000648f  push    r14
0x180006491  push    r15
0x180006493  lea     rbp, [rsp-27h]
0x180006498  sub     rsp, 0B0h
0x18000649f  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; hHandle
0x1800064a6  xor     r15d, r15d
0x1800064a9  mov     [rbp+57h+KeyHandle], r15
0x1800064ad  mov     [rbp+57h+var_90], r15
0x1800064b1  mov     [rbp+57h+var_48], r15d
0x1800064b5  mov     [rbp+57h+arg_10], r15d
0x1800064b9  mov     dword ptr [rbp+57h+var_98], r15d
0x1800064bd  mov     [rbp+57h+Data], r15d
0x1800064c1  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x1800064c5  test    rcx, rcx
0x1800064c8  jz      short loc_180006544
0x1800064ca  mov     edx, 0EA60h; dwMilliseconds
0x1800064cf  call    cs:__imp_WaitForSingleObject
0x1800064d5  test    eax, eax
0x1800064d7  jnz     short loc_180006523
0x1800064d9  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800064dd  mov     ebx, r15d
0x1800064e0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800064e6  mov     rcx, 430E23400h
0x1800064f0  add     rcx, cs:?g_LastRefreshTime@@3_KA; unsigned __int64 g_LastRefreshTime
0x1800064f7  cmp     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800064fb  jnb     short loc_18000654B
0x1800064fd  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; hMutex
0x180006504  test    rcx, rcx
0x180006507  jz      short loc_180006513
0x180006509  call    cs:__imp_ReleaseMutex
0x18000650f  test    eax, eax
0x180006511  jz      short loc_180006535
0x180006513  mov     rcx, [rbp+57h+KeyHandle]
0x180006517  lea     rax, [rcx-1]
0x18000651b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000651f  jbe     short loc_18000653D
0x180006521  mov     eax, ebx
0x180006523  add     rsp, 0B0h
0x18000652a  pop     r15
0x18000652c  pop     r14
0x18000652e  pop     r12
0x180006530  pop     rdi
0x180006531  pop     rsi
0x180006532  pop     rbx
0x180006533  pop     rbp
0x180006534  retn
0x180006535  call    cs:__imp_GetLastError
0x18000653b  jmp     short loc_180006513
0x18000653d  call    PerflibciCloseKey
0x180006542  jmp     short loc_180006521
0x180006544  mov     eax, 57h ; 'W'
0x180006549  jmp     short loc_180006523
0x18000654b  xor     ecx, ecx
0x18000654d  call    PerflibciSetObjectsValidityState
0x180006552  call    PerfpAcquireInstallationMutex
0x180006557  mov     edi, 30h ; '0'
0x18000655c  lea     r14d, [rdi+10h]
0x180006560  test    eax, eax
0x180006562  jz      loc_1800065F5
0x180006568  mov     sil, r15b
0x18000656b  xorps   xmm0, xmm0
0x18000656e  mov     [rbp+57h+KeyHandle], r15
0x180006572  lea     rdx, aRegistryMachin_9; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180006579  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000657d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006581  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006585  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006589  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000658d  call    cs:__imp_RtlInitUnicodeString
0x180006593  lea     rax, [rbp+57h+DestinationString]
0x180006597  mov     [rbp+57h+ObjectAttributes.Length], edi
0x18000659a  xorps   xmm0, xmm0
0x18000659d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800065a1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800065a5  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800065a9  mov     edx, 20019h; DesiredAccess
0x1800065ae  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x1800065b2  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800065b6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800065bb  call    cs:__imp_NtOpenKey
0x1800065c1  mov     ecx, eax; Status
0x1800065c3  call    cs:__imp_RtlNtStatusToDosError
0x1800065c9  mov     ebx, eax
0x1800065cb  test    eax, eax
0x1800065cd  jz      loc_18000665E
0x1800065d3  mov     cl, 1
0x1800065d5  call    PerflibciSetObjectsValidityState
0x1800065da  test    sil, sil
0x1800065dd  jz      loc_1800064FD
0x1800065e3  mov     rcx, cs:hHandle; hMutex
0x1800065ea  call    cs:__imp_ReleaseMutex
0x1800065f0  jmp     loc_1800064FD
0x1800065f5  xorps   xmm0, xmm0
0x1800065f8  mov     [rbp+57h+KeyHandle], r15
0x1800065fc  lea     rdx, aRegistryMachin_9; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180006603  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006607  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000660b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000660f  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006613  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006617  call    cs:__imp_RtlInitUnicodeString
0x18000661d  lea     rax, [rbp+57h+DestinationString]
0x180006621  mov     [rbp+57h+ObjectAttributes.Length], edi
0x180006624  xorps   xmm0, xmm0
0x180006627  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000662b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000662f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180006633  mov     edx, 2001Fh; DesiredAccess
0x180006638  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x18000663c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180006640  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006645  call    cs:__imp_NtOpenKey
0x18000664b  mov     ecx, eax; Status
0x18000664d  call    cs:__imp_RtlNtStatusToDosError
0x180006653  mov     sil, 1
0x180006656  test    eax, eax
0x180006658  jnz     loc_18000656B
0x18000665e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180006662  lea     rax, [rbp+57h+arg_18]
0x180006666  mov     [rsp+0E0h+var_B0], 1; int
0x18000666e  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x180006672  mov     [rsp+0E0h+ResultLength], rax; unsigned int *
0x180006677  lea     rdx, ?LastCounter@@3QBGB; "Last Counter"
0x18000667e  lea     rax, [rbp+57h+arg_10]
0x180006682  mov     [rbp+57h+arg_8], r15d
0x180006686  mov     r12d, 4
0x18000668c  mov     qword ptr [rsp+0E0h+Length], rax; unsigned __int8 *
0x180006691  mov     [rbp+57h+arg_18], r12d
0x180006695  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18000669a  mov     ebx, eax
0x18000669c  test    eax, eax
0x18000669e  jnz     loc_1800065D3
0x1800066a4  cmp     [rbp+57h+arg_8], r12d
0x1800066a8  jnz     loc_180006918
0x1800066ae  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800066b2  lea     rax, [rbp+57h+arg_18]
0x1800066b6  mov     [rsp+0E0h+var_B0], 1; int
0x1800066be  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x1800066c2  mov     [rsp+0E0h+ResultLength], rax; unsigned int *
0x1800066c7  lea     rdx, ?LastHelp@@3QBGB; "Last Help"
0x1800066ce  lea     rax, [rbp+57h+var_98]
0x1800066d2  mov     [rbp+57h+arg_8], r15d
0x1800066d6  mov     qword ptr [rsp+0E0h+Length], rax; unsigned __int8 *
0x1800066db  mov     [rbp+57h+arg_18], r12d
0x1800066df  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x1800066e4  mov     ebx, eax
0x1800066e6  test    eax, eax
0x1800066e8  jnz     loc_1800065D3
0x1800066ee  cmp     [rbp+57h+arg_8], r12d
0x1800066f2  jnz     loc_180006918
0x1800066f8  mov     eax, dword ptr [rbp+57h+var_98]
0x1800066fb  cmp     [rbp+57h+arg_10], eax
0x1800066fe  cmova   eax, [rbp+57h+arg_10]
0x180006702  mov     [rbp+57h+Data], eax
0x180006705  test    sil, sil
0x180006708  jz      loc_180006898
0x18000670e  mov     rbx, [rbp+57h+KeyHandle]
0x180006712  lea     rdx, aV2providers; "_V2Providers"
0x180006719  xorps   xmm0, xmm0
0x18000671c  mov     [rbp+57h+var_90], r15
0x180006720  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006724  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006728  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000672c  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006730  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006734  call    cs:__imp_RtlInitUnicodeString
0x18000673a  lea     rax, [rbp+57h+DestinationString]
0x18000673e  mov     [rbp+57h+ObjectAttributes.Length], edi
0x180006741  xorps   xmm0, xmm0
0x180006744  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006748  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000674c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180006750  mov     edx, 2001Fh; DesiredAccess
0x180006755  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x180006759  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x18000675d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006762  call    cs:__imp_NtOpenKey
0x180006768  mov     ecx, eax; Status
0x18000676a  call    cs:__imp_RtlNtStatusToDosError
0x180006770  test    eax, eax
0x180006772  jnz     loc_180006898
0x180006778  mov     ecx, 418h
0x18000677d  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180006782  mov     rdi, rax
0x180006785  test    rax, rax
0x180006788  jz      loc_18000688E
0x18000678e  mov     ebx, r15d
0x180006791  mov     r14d, r15d
0x180006794  xor     edx, edx; Val
0x180006796  mov     r8d, 418h; Size
0x18000679c  mov     rcx, rdi; void *
0x18000679f  call    memset_0
0x1800067a4  mov     rcx, [rbp+57h+var_90]; KeyHandle
0x1800067a8  lea     rax, [rbp+57h+var_48]
0x1800067ac  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800067b1  mov     r9, rdi; KeyInformation
0x1800067b4  xor     r8d, r8d; KeyInformationClass
0x1800067b7  mov     [rsp+0E0h+Length], 418h; Length
0x1800067bf  mov     edx, ebx; Index
0x1800067c1  call    cs:__imp_NtEnumerateKey
0x1800067c7  lea     ebx, [r14+1]
0x1800067cb  test    eax, eax
0x1800067cd  js      short loc_1800067E5
0x1800067cf  mov     rcx, [rbp+57h+var_90]
0x1800067d3  lea     rdx, [rdi+10h]
0x1800067d7  lea     r8, [rbp+57h+Data]
0x1800067db  call    PerflibciBuildProvider
0x1800067e0  mov     r14d, ebx
0x1800067e3  jmp     short loc_180006794
0x1800067e5  cmp     eax, 8000001Ah
0x1800067ea  jnz     loc_180006909
0x1800067f0  mov     ebx, r15d
0x1800067f3  mov     rcx, rdi; hMem
0x1800067f6  call    cs:__imp_LocalFree
0x1800067fc  mov     rcx, [rbp+57h+var_90]
0x180006800  call    PerflibciCloseKey
0x180006805  test    ebx, ebx
0x180006807  jnz     loc_1800065D3
0x18000680d  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180006811  mov     cs:?g_LastRefreshTime@@3_KA, rax; unsigned __int64 g_LastRefreshTime
0x180006818  test    sil, sil
0x18000681b  jz      loc_1800064FD
0x180006821  mov     eax, dword ptr [rbp+57h+var_98]
0x180006824  cmp     [rbp+57h+arg_10], eax
0x180006827  cmova   eax, [rbp+57h+arg_10]
0x18000682b  cmp     eax, [rbp+57h+Data]
0x18000682e  jz      loc_1800065E3
0x180006834  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x180006838  lea     rax, [rbp+57h+Data]
0x18000683c  mov     dword ptr [rsp+0E0h+ResultLength], r12d; cbData
0x180006841  lea     rdx, ?LastCounter@@3QBGB; "Last Counter"
0x180006848  mov     r9d, r12d; dwType
0x18000684b  mov     qword ptr [rsp+0E0h+Length], rax; lpData
0x180006850  xor     r8d, r8d; Reserved
0x180006853  call    cs:__imp_RegSetValueExW
0x180006859  test    eax, eax
0x18000685b  jnz     loc_1800065E3
0x180006861  inc     [rbp+57h+Data]
0x180006864  lea     rax, [rbp+57h+Data]
0x180006868  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x18000686c  lea     rdx, ?LastHelp@@3QBGB; "Last Help"
0x180006873  mov     dword ptr [rsp+0E0h+ResultLength], r12d; cbData
0x180006878  mov     r9d, r12d; dwType
0x18000687b  xor     r8d, r8d; Reserved
0x18000687e  mov     qword ptr [rsp+0E0h+Length], rax; lpData
0x180006883  call    cs:__imp_RegSetValueExW
0x180006889  jmp     loc_1800065E3
0x18000688e  mov     ebx, 0Eh
0x180006893  jmp     loc_1800067FC
0x180006898  mov     rbx, [rbp+57h+KeyHandle]
0x18000689c  lea     rdx, aV2providers; "_V2Providers"
0x1800068a3  xorps   xmm0, xmm0
0x1800068a6  mov     [rbp+57h+var_90], r15
0x1800068aa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800068ae  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800068b2  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800068b6  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800068ba  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800068be  call    cs:__imp_RtlInitUnicodeString
0x1800068c4  lea     rax, [rbp+57h+DestinationString]
0x1800068c8  mov     [rbp+57h+ObjectAttributes.Length], edi
0x1800068cb  xorps   xmm0, xmm0
0x1800068ce  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800068d2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800068d6  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800068da  mov     edx, 20019h; DesiredAccess
0x1800068df  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x1800068e3  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x1800068e7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800068ec  call    cs:__imp_NtOpenKey
0x1800068f2  mov     ecx, eax; Status
0x1800068f4  call    cs:__imp_RtlNtStatusToDosError
0x1800068fa  mov     ebx, eax
0x1800068fc  test    eax, eax
0x1800068fe  jz      loc_180006778
0x180006904  jmp     loc_1800065D3
0x180006909  mov     ecx, eax; Status
0x18000690b  call    cs:__imp_RtlNtStatusToDosError
0x180006911  mov     ebx, eax
0x180006913  jmp     loc_1800067F3
0x180006918  mov     ebx, 0Dh
0x18000691d  jmp     loc_1800065D3
```
