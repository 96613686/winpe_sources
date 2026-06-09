# SdbRegisterDatabaseEx

- ea: `0x18004a010`
- end: `0x18004a612`
- name: `SdbRegisterDatabaseEx`
- size: `1538`
- prototype: `__int64 __fastcall(PCWSTR SourceString, ULONG, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004a000`

## callees

- `0x18000f114`
- `0x180018f20`
- `0x18001ab9c`
- `0x18002f8e0`
- `0x1800476c0`
- `0x180047710`
- `0x18004a010`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!NtSetValueKey` at `0x18004a3a8`
- `ntdll!NtSetValueKey` at `0x18004a40d`
- `ntdll!NtSetValueKey` at `0x18004a45c`
- `ntdll!NtSetValueKey` at `0x18004a4c2`
- `ntdll!NtSetValueKey` at `0x18004a535`
- `ntdll!NtSetValueKey` at `0x18004a3a8`
- `ntdll!NtSetValueKey` at `0x18004a40d`
- `ntdll!NtSetValueKey` at `0x18004a45c`
- `ntdll!NtSetValueKey` at `0x18004a4c2`
- `ntdll!NtSetValueKey` at `0x18004a535`
- `ntdll!NtCreateKey` at `0x18004a2e6`
- `ntdll!NtCreateKey` at `0x18004a366`
- `ntdll!NtCreateKey` at `0x18004a2e6`
- `ntdll!NtCreateKey` at `0x18004a366`
- `ntdll!NtSetInformationKey` at `0x18004a573`
- `ntdll!NtSetInformationKey` at `0x18004a573`
- `ntdll!NtClose` at `0x18004a5d0`
- `ntdll!NtClose` at `0x18004a5df`
- `ntdll!NtClose` at `0x18004a5d0`
- `ntdll!NtClose` at `0x18004a5df`
- `ntdll!RtlInitUnicodeString` at `0x18004a0d3`
- `ntdll!RtlInitUnicodeString` at `0x18004a1c4`
- `ntdll!RtlInitUnicodeString` at `0x18004a29a`
- `ntdll!RtlInitUnicodeString` at `0x18004a0d3`
- `ntdll!RtlInitUnicodeString` at `0x18004a1c4`
- `ntdll!RtlInitUnicodeString` at `0x18004a29a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004a280`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004a280`
- `ntdll!wcschr` at `0x18004a0b8`
- `ntdll!wcschr` at `0x18004a0b8`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18004a0e9`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18004a188`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18004a0e9`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x18004a188`
- `ntdll!RtlAppendUnicodeToString` at `0x18004a25f`
- `ntdll!RtlAppendUnicodeToString` at `0x18004a271`
- `ntdll!RtlAppendUnicodeToString` at `0x18004a25f`
- `ntdll!RtlAppendUnicodeToString` at `0x18004a271`
- `ntdll!RtlAllocateHeap` at `0x18004a139`
- `ntdll!RtlAllocateHeap` at `0x18004a139`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004a4fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004a4fb`

## string_xrefs

- `0x18004a14d`: `Failed to allocate 0x%lx bytes for the path buffer "%ws"`
- `0x18004a24f`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x18004a28f`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x18004a2fe`: `Failed to create key "%ws" [%x]`
- `0x18004a581`: `Failed to set last write time on key [%x]`
- `0x18004a3c2`: `DatabasePath`
- `0x18004a54a`: `DatabaseInstallTimeStamp`

## pseudocode

```c
__int64 __fastcall SdbRegisterDatabaseEx(PCWSTR SourceString, ULONG a2, struct _FILETIME *a3)
{
  unsigned int v5; // r15d
  NTSTATUS v6; // eax
  int v8; // r14d
  NTSTATUS v9; // eax
  int DatabaseInformationByName; // eax
  _BYTE *v11; // rbx
  const char *v12; // r9
  __int64 v13; // r8
  int v14; // eax
  NTSTATUS v15; // eax
  __int64 v16; // r8
  PWSTR Buffer; // rax
  NTSTATUS v18; // eax
  NTSTATUS v19; // eax
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  _WORD *v22; // rcx
  __int64 v23; // rax
  NTSTATUS v24; // eax
  struct _FILETIME v25; // rax
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  PUNICODE_STRING Class; // [rsp+20h] [rbp-E0h]
  ULONG CreateOptions[2]; // [rsp+28h] [rbp-D8h]
  ULONG CreateOptionsa[2]; // [rsp+28h] [rbp-D8h]
  ULONG CreateOptionsb[2]; // [rsp+28h] [rbp-D8h]
  ULONG CreateOptionsc[2]; // [rsp+28h] [rbp-D8h]
  PULONG Disposition; // [rsp+30h] [rbp-D0h]
  ULONG Length; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v37; // [rsp+60h] [rbp-A0h] BYREF
  ULONG Data; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME v39; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v40; // [rsp+78h] [rbp-88h] BYREF
  _BYTE *v41; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME KeySetInformation; // [rsp+98h] [rbp-68h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v48; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v49[528]; // [rsp+110h] [rbp+10h] BYREF

  Data = a2;
  v41 = 0;
  v5 = 0;
  DestinationString = 0;
  Destination = 0;
  v48 = 0;
  v40 = 0;
  Source = 0;
  memset_0(v49, 0, 0x208u);
  KeyHandle = 0;
  Handle = 0;
  v37 = 0;
  Length = 0;
  SystemTimeAsFileTime = 0;
  memset(&ObjectAttributes, 0, 44);
  v39 = 0;
  KeySetInformation = 0;
  if ( !wcschr(SourceString, 0x25u) )
  {
    v8 = 0;
    RtlInitUnicodeString(&Destination, SourceString);
    goto LABEL_10;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v6 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length);
  if ( v6 != -1073741789 )
  {
    AslLogCallPrintf(
      1,
      "SdbRegisterDatabaseEx",
      994,
      "Failed to expand environment strings for \"%ws\" [%x]",
      SourceString,
      v6);
    return 0;
  }
  Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
  if ( !Destination.Buffer )
  {
    AslLogCallPrintf(
      1,
      "SdbRegisterDatabaseEx",
      1004,
      "Failed to allocate 0x%lx bytes for the path buffer \"%ws\"",
      Length,
      SourceString);
    return 0;
  }
  Destination.MaximumLength = Length;
  Destination.Length = 0;
  v8 = 1;
  v9 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length);
  if ( v9 >= 0 )
  {
LABEL_10:
    DatabaseInformationByName = SdbGetDatabaseInformationByName(Destination.Buffer, &v41);
    v11 = v41;
    if ( !DatabaseInformationByName )
    {
      v12 = "Cannot obtain database information for \"%ws\"";
      v13 = 1030;
LABEL_12:
      AslLogCallPrintf(1, "SdbRegisterDatabaseEx", v13, v12, Destination.Buffer);
      goto LABEL_44;
    }
    if ( (*v41 & 1) == 0 )
    {
      v12 = "Cannot register database with no id \"%ws\"";
      v13 = 1035;
      goto LABEL_12;
    }
    v14 = AslGuidToString_UStr(&Source, v41 + 24);
    if ( v14 < 0 )
    {
      AslLogCallPrintf(1, "SdbRegisterDatabaseEx", 1041, "Cannot convert guid to unicode string [%x]", v14);
      goto LABEL_44;
    }
    *(_DWORD *)&v40.Length = 34078720;
    v40.Buffer = (PWSTR)v49;
    RtlAppendUnicodeToString(
      &v40,
      L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
    RtlAppendUnicodeToString(&v40, L"\\");
    RtlAppendUnicodeStringToString(&v40, &Source);
    AslUnicodeStringFree(&Source);
    RtlInitUnicodeString(
      &v48,
      L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v15 = NtCreateKey(&KeyHandle, 0x2010Fu, &ObjectAttributes, 0, 0, 0, &v37);
    if ( v15 >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v40;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v18 = NtCreateKey(&Handle, 0x2010Fu, &ObjectAttributes, 0, 0, 0, &v37);
      if ( v18 >= 0 )
      {
        v19 = NtSetValueKey(
                Handle,
                (PUNICODE_STRING)&g_ustrDatabasePath,
                0,
                1u,
                Destination.Buffer,
                Destination.MaximumLength);
        if ( v19 >= 0 )
        {
          v20 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrDatabaseType, 0, 4u, &Data, 4u);
          if ( v20 >= 0 )
          {
            v21 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrRuntimePlatform, 0, 4u, v11 + 40, 4u);
            if ( v21 >= 0 )
            {
              v22 = (_WORD *)*((_QWORD *)v11 + 2);
              if ( !v22 )
                goto LABEL_36;
              v23 = -1;
              do
                ++v23;
              while ( v22[v23] );
              v24 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrDatabaseDescription, 0, 1u, v22, 2 * v23 + 2);
              if ( v24 < 0 )
              {
                LODWORD(Disposition) = v24;
                AslLogCallPrintf(
                  1,
                  "SdbRegisterDatabaseEx",
                  1160,
                  "Failed to set value \"%ws\" to %ws [%x]",
                  L"DatabaseDescription",
                  *((_QWORD *)v11 + 2),
                  Disposition);
              }
              else
              {
LABEL_36:
                if ( a3 )
                {
                  v25 = *a3;
                }
                else
                {
                  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                  v25 = SystemTimeAsFileTime;
                }
                v39 = v25;
                v26 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrInstallTimeStamp, 0, 0xBu, &v39, 8u);
                if ( v26 >= 0 )
                {
                  KeySetInformation = v39;
                  v27 = NtSetInformationKey(Handle, KeyWriteTimeInformation, &KeySetInformation, 8u);
                  if ( v27 >= 0 )
                  {
                    v5 = 1;
                  }
                  else
                  {
                    LODWORD(Class) = v27;
                    AslLogCallPrintf(
                      1,
                      "SdbRegisterDatabaseEx",
                      1199,
                      "Failed to set last write time on key [%x]",
                      Class);
                  }
                }
                else
                {
                  CreateOptionsc[0] = v26;
                  AslLogCallPrintf(
                    1,
                    "SdbRegisterDatabaseEx",
                    1184,
                    "Failed to set value \"%ws\" [%x]",
                    L"DatabaseInstallTimeStamp",
                    *(_QWORD *)CreateOptionsc);
                }
              }
            }
            else
            {
              LODWORD(Disposition) = v21;
              CreateOptionsb[0] = *((_DWORD *)v11 + 10);
              AslLogCallPrintf(
                1,
                "SdbRegisterDatabaseEx",
                1147,
                "Failed to set value \"%ws\" to 0x%lx [%x]",
                L"DatabaseRuntimePlatform",
                *(_QWORD *)CreateOptionsb,
                Disposition);
            }
          }
          else
          {
            LODWORD(Disposition) = v20;
            CreateOptionsa[0] = Data;
            AslLogCallPrintf(
              1,
              "SdbRegisterDatabaseEx",
              1135,
              "Failed to set value \"%ws\" to 0x%lx [%x]",
              L"DatabaseType",
              *(_QWORD *)CreateOptionsa,
              Disposition);
          }
        }
        else
        {
          LODWORD(Disposition) = v19;
          AslLogCallPrintf(
            1,
            "SdbRegisterDatabaseEx",
            1123,
            "Failed to set value \"%ws\" to \"%ws\" [%x]",
            L"DatabasePath",
            SourceString,
            Disposition);
        }
LABEL_44:
        if ( v11 )
          SdbFreeDatabaseInformation(v11);
        if ( !v8 )
          goto LABEL_49;
        goto LABEL_47;
      }
      CreateOptions[0] = v18;
      v16 = 1108;
      Buffer = v40.Buffer;
    }
    else
    {
      CreateOptions[0] = v15;
      v16 = 1084;
      Buffer = v48.Buffer;
    }
    AslLogCallPrintf(
      1,
      "SdbRegisterDatabaseEx",
      v16,
      "Failed to create key \"%ws\" [%x]",
      Buffer,
      *(_QWORD *)CreateOptions);
    goto LABEL_44;
  }
  AslLogCallPrintf(
    1,
    "SdbRegisterDatabaseEx",
    1017,
    "Failed to expand environment strings for \"%ws\" [%x]",
    SourceString,
    v9);
LABEL_47:
  if ( Destination.Buffer )
    AslFree(NtCurrentPeb()->ProcessHeap, Destination.Buffer);
LABEL_49:
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v5;
}

```

## disassembly

```asm
0x18004a010  mov     [rsp-8+arg_18], rbx
0x18004a015  push    rbp
0x18004a016  push    rsi
0x18004a017  push    rdi
0x18004a018  push    r12
0x18004a01a  push    r13
0x18004a01c  push    r14
0x18004a01e  push    r15
0x18004a020  lea     rbp, [rsp-230h]
0x18004a028  sub     rsp, 330h
0x18004a02f  mov     rax, cs:__security_cookie
0x18004a036  xor     rax, rsp
0x18004a039  mov     [rbp+260h+var_40], rax
0x18004a040  xorps   xmm0, xmm0
0x18004a043  mov     [rsp+360h+Data], edx
0x18004a047  xorps   xmm1, xmm1
0x18004a04a  mov     rsi, r8
0x18004a04d  mov     rdi, rcx
0x18004a050  xor     r12d, r12d
0x18004a053  xor     edx, edx; Val
0x18004a055  mov     [rbp+260h+var_2D8], r12
0x18004a059  mov     r8d, 208h; Size
0x18004a05f  lea     rcx, [rbp+260h+var_250]; void *
0x18004a063  mov     r15d, r12d
0x18004a066  movups  xmmword ptr [rbp+260h+DestinationString.Length], xmm0
0x18004a06a  movups  xmmword ptr [rsp+360h+Destination.Length], xmm1
0x18004a06f  movups  xmmword ptr [rbp+260h+var_268.Length], xmm0
0x18004a073  movups  xmmword ptr [rsp+360h+var_2E8.Length], xmm1
0x18004a078  movups  xmmword ptr [rbp+260h+Source.Length], xmm0
0x18004a07c  call    memset_0
0x18004a081  xorps   xmm0, xmm0
0x18004a084  mov     [rbp+260h+KeyHandle], r12
0x18004a088  xor     eax, eax
0x18004a08a  mov     [rsp+360h+Handle], r12
0x18004a08f  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x18004a093  mov     rcx, rdi; Str
0x18004a096  mov     [rsp+360h+var_300], r12d
0x18004a09b  mov     [rsp+360h+Length], r12d
0x18004a0a0  lea     edx, [rax+25h]; Ch
0x18004a0a3  mov     qword ptr [rbp+260h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18004a0a7  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x18004a0ab  mov     [rsp+360h+var_2F0], r12
0x18004a0b0  movups  xmmword ptr [rbp+260h+ObjectAttributes+1Ch], xmm0
0x18004a0b4  mov     [rbp+260h+KeySetInformation], r12
0x18004a0b8  call    cs:__imp_wcschr
0x18004a0be  lea     r13d, [r12+1]
0x18004a0c3  mov     rdx, rdi; SourceString
0x18004a0c6  test    rax, rax
0x18004a0c9  jz      loc_18004A1BC
0x18004a0cf  lea     rcx, [rbp+260h+DestinationString]; DestinationString
0x18004a0d3  call    cs:__imp_RtlInitUnicodeString
0x18004a0d9  lea     r9, [rsp+360h+Length]; Length
0x18004a0de  xor     ecx, ecx; Environment
0x18004a0e0  lea     r8, [rsp+360h+Destination]; Destination
0x18004a0e5  lea     rdx, [rbp+260h+DestinationString]; Source
0x18004a0e9  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x18004a0ef  cmp     eax, 0C0000023h
0x18004a0f4  jz      short loc_18004A122
0x18004a0f6  mov     [rsp+360h+CreateOptions], eax
0x18004a0fa  lea     r9, aFailedToExpand_2; "Failed to expand environment strings fo"...
0x18004a101  mov     [rsp+360h+Class], rdi
0x18004a106  mov     r8d, 3E2h
0x18004a10c  lea     rdx, aSdbregisterdat_1; "SdbRegisterDatabaseEx"
0x18004a113  mov     ecx, r13d
0x18004a116  call    AslLogCallPrintf
0x18004a11b  xor     eax, eax
0x18004a11d  jmp     loc_18004A5E8
0x18004a122  mov     rcx, gs:60h
0x18004a12b  mov     edx, 8; Flags
0x18004a130  mov     r8d, [rsp+360h+Length]; Size
0x18004a135  mov     rcx, [rcx+30h]; HeapHandle
0x18004a139  call    cs:__imp_RtlAllocateHeap
0x18004a13f  mov     [rsp+360h+Destination.Buffer], rax
0x18004a144  test    rax, rax
0x18004a147  jnz     short loc_18004A165
0x18004a149  mov     eax, [rsp+360h+Length]
0x18004a14d  lea     r9, aFailedToAlloca_19; "Failed to allocate 0x%lx bytes for the "...
0x18004a154  mov     qword ptr [rsp+360h+CreateOptions], rdi
0x18004a159  mov     r8d, 3ECh
0x18004a15f  mov     dword ptr [rsp+360h+Class], eax
0x18004a163  jmp     short loc_18004A10C
0x18004a165  movzx   eax, word ptr [rsp+360h+Length]
0x18004a16a  lea     r9, [rsp+360h+Length]; Length
0x18004a16f  lea     r8, [rsp+360h+Destination]; Destination
0x18004a174  mov     [rsp+360h+Destination.MaximumLength], ax
0x18004a179  lea     rdx, [rbp+260h+DestinationString]; Source
0x18004a17d  mov     [rsp+360h+Destination.Length], r12w
0x18004a183  xor     ecx, ecx; Environment
0x18004a185  mov     r14d, r13d
0x18004a188  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x18004a18e  test    eax, eax
0x18004a190  jns     short loc_18004A1CA
0x18004a192  mov     [rsp+360h+CreateOptions], eax
0x18004a196  lea     r9, aFailedToExpand_2; "Failed to expand environment strings fo"...
0x18004a19d  mov     r8d, 3F9h
0x18004a1a3  mov     [rsp+360h+Class], rdi
0x18004a1a8  lea     rdx, aSdbregisterdat_1; "SdbRegisterDatabaseEx"
0x18004a1af  mov     ecx, r13d
0x18004a1b2  call    AslLogCallPrintf
0x18004a1b7  jmp     loc_18004A5A8
0x18004a1bc  lea     rcx, [rsp+360h+Destination]; DestinationString
0x18004a1c1  mov     r14d, r12d
0x18004a1c4  call    cs:__imp_RtlInitUnicodeString
0x18004a1ca  mov     rcx, [rsp+360h+Destination.Buffer]
0x18004a1cf  lea     rdx, [rbp+260h+var_2D8]
0x18004a1d3  call    SdbGetDatabaseInformationByName
0x18004a1d8  mov     rbx, [rbp+260h+var_2D8]
0x18004a1dc  test    eax, eax
0x18004a1de  jnz     short loc_18004A20B
0x18004a1e0  lea     r9, aCannotObtainDa_0; "Cannot obtain database information for "...
0x18004a1e7  mov     r8d, 406h
0x18004a1ed  mov     rax, [rsp+360h+Destination.Buffer]
0x18004a1f2  mov     [rsp+360h+Class], rax
0x18004a1f7  lea     rdx, aSdbregisterdat_1; "SdbRegisterDatabaseEx"
0x18004a1fe  mov     ecx, r13d
0x18004a201  call    AslLogCallPrintf
0x18004a206  jmp     loc_18004A596
0x18004a20b  test    [rbx], r13b
0x18004a20e  jnz     short loc_18004A21F
0x18004a210  lea     r9, aCannotRegister; "Cannot register database with no id \"%"...
0x18004a217  mov     r8d, 40Bh
0x18004a21d  jmp     short loc_18004A1ED
0x18004a21f  lea     rdx, [rbx+18h]
0x18004a223  lea     rcx, [rbp+260h+Source]
0x18004a227  call    AslGuidToString_UStr
0x18004a22c  test    eax, eax
0x18004a22e  jns     short loc_18004A243
0x18004a230  mov     dword ptr [rsp+360h+Class], eax
0x18004a234  lea     r9, aCannotConvertG; "Cannot convert guid to unicode string ["...
0x18004a23b  mov     r8d, 411h
0x18004a241  jmp     short loc_18004A1F7
0x18004a243  lea     rax, [rbp+260h+var_250]
0x18004a247  mov     dword ptr [rsp+360h+var_2E8.Length], 2080000h
0x18004a24f  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x18004a256  mov     [rbp+260h+var_2E8.Buffer], rax
0x18004a25a  lea     rcx, [rsp+360h+var_2E8]; Destination
0x18004a25f  call    cs:__imp_RtlAppendUnicodeToString
0x18004a265  lea     rdx, pszSrc; "\\"
0x18004a26c  lea     rcx, [rsp+360h+var_2E8]; Destination
0x18004a271  call    cs:__imp_RtlAppendUnicodeToString
0x18004a277  lea     rdx, [rbp+260h+Source]; Source
0x18004a27b  lea     rcx, [rsp+360h+var_2E8]; Destination
0x18004a280  call    cs:__imp_RtlAppendUnicodeStringToString
0x18004a286  lea     rcx, [rbp+260h+Source]
0x18004a28a  call    AslUnicodeStringFree
0x18004a28f  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\Software\\Microsof"...
0x18004a296  lea     rcx, [rbp+260h+var_268]; DestinationString
0x18004a29a  call    cs:__imp_RtlInitUnicodeString
0x18004a2a0  lea     rax, [rbp+260h+var_268]
0x18004a2a4  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x18004a2ab  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x18004a2af  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x18004a2b3  lea     rax, [rsp+360h+var_300]
0x18004a2b8  mov     [rbp+260h+ObjectAttributes.RootDirectory], r12
0x18004a2bc  mov     [rsp+360h+Disposition], rax; Disposition
0x18004a2c1  lea     rcx, [rbp+260h+KeyHandle]; KeyHandle
0x18004a2c5  xorps   xmm0, xmm0
0x18004a2c8  mov     [rsp+360h+CreateOptions], r12d; CreateOptions
0x18004a2cd  xor     r9d, r9d; TitleIndex
0x18004a2d0  mov     [rsp+360h+Class], r12; Class
0x18004a2d5  mov     edx, 2010Fh; DesiredAccess
0x18004a2da  mov     [rbp+260h+ObjectAttributes.Attributes], 40h ; '@'
0x18004a2e1  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004a2e6  call    cs:__imp_NtCreateKey
0x18004a2ec  test    eax, eax
0x18004a2ee  jns     short loc_18004A31E
0x18004a2f0  mov     [rsp+360h+CreateOptions], eax
0x18004a2f4  mov     r8d, 43Ch
0x18004a2fa  mov     rax, [rbp+260h+var_268.Buffer]
0x18004a2fe  lea     r9, aFailedToCreate_10; "Failed to create key \"%ws\" [%x]"
0x18004a305  lea     rdx, aSdbregisterdat_1; "SdbRegisterDatabaseEx"
0x18004a30c  mov     [rsp+360h+Class], rax
0x18004a311  mov     ecx, r13d
0x18004a314  call    AslLogCallPrintf
0x18004a319  jmp     loc_18004A596
0x18004a31e  lea     rax, [rsp+360h+var_2E8]
0x18004a323  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x18004a32a  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x18004a32e  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x18004a332  lea     rax, [rsp+360h+var_300]
0x18004a337  mov     [rbp+260h+ObjectAttributes.RootDirectory], r12
0x18004a33b  mov     [rsp+360h+Disposition], rax; Disposition
0x18004a340  lea     rcx, [rsp+360h+Handle]; KeyHandle
0x18004a345  xorps   xmm0, xmm0
0x18004a348  mov     [rsp+360h+CreateOptions], r12d; CreateOptions
0x18004a34d  xor     r9d, r9d; TitleIndex
0x18004a350  mov     [rsp+360h+Class], r12; Class
0x18004a355  mov     edx, 2010Fh; DesiredAccess
0x18004a35a  mov     [rbp+260h+ObjectAttributes.Attributes], 40h ; '@'
0x18004a361  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004a366  call    cs:__imp_NtCreateKey
0x18004a36c  test    eax, eax
0x18004a36e  jns     short loc_18004A383
0x18004a370  mov     [rsp+360h+CreateOptions], eax
0x18004a374  mov     r8d, 454h
0x18004a37a  mov     rax, [rbp+260h+var_2E8.Buffer]
0x18004a37e  jmp     loc_18004A2FE
0x18004a383  movzx   eax, [rsp+360h+Destination.MaximumLength]
0x18004a388  lea     rdx, g_ustrDatabasePath; ValueName
0x18004a38f  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x18004a394  mov     r9d, r13d; Type
0x18004a397  mov     [rsp+360h+CreateOptions], eax; DataSize
0x18004a39b  xor     r8d, r8d; TitleIndex
0x18004a39e  mov     rax, [rsp+360h+Destination.Buffer]
0x18004a3a3  mov     [rsp+360h+Class], rax; Data
0x18004a3a8  call    cs:__imp_NtSetValueKey
0x18004a3ae  test    eax, eax
0x18004a3b0  jns     short loc_18004A3E8
0x18004a3b2  mov     dword ptr [rsp+360h+Disposition], eax
0x18004a3b6  lea     r9, aFailedToSetVal_0; "Failed to set value \"%ws\" to \"%ws\" "...
0x18004a3bd  mov     qword ptr [rsp+360h+CreateOptions], rdi
0x18004a3c2  lea     rax, aDatabasepath; "DatabasePath"
0x18004a3c9  mov     r8d, 463h
0x18004a3cf  lea     rdx, aSdbregisterdat_1; "SdbRegisterDatabaseEx"
0x18004a3d6  mov     [rsp+360h+Class], rax
0x18004a3db  mov     ecx, r13d
0x18004a3de  call    AslLogCallPrintf
0x18004a3e3  jmp     loc_18004A596
0x18004a3e8  mov     ecx, 4
0x18004a3ed  lea     rax, [rsp+360h+Data]
0x18004a3f2  mov     [rsp+360h+CreateOptions], ecx; DataSize
0x18004a3f6  lea     rdx, g_ustrDatabaseType; ValueName
0x18004a3fd  mov     r9d, ecx; Type
0x18004a400  mov     [rsp+360h+Class], rax; Data
0x18004a405  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x18004a40a  xor     r8d, r8d; TitleIndex
0x18004a40d  call    cs:__imp_NtSetValueKey
0x18004a413  test    eax, eax
0x18004a415  jns     short loc_18004A439
0x18004a417  mov     dword ptr [rsp+360h+Disposition], eax
0x18004a41b  lea     r9, aFailedToSetVal_1; "Failed to set value \"%ws\" to 0x%lx [%"...
0x18004a422  mov     eax, [rsp+360h+Data]
0x18004a426  mov     r8d, 46Fh
0x18004a42c  mov     [rsp+360h+CreateOptions], eax
0x18004a430  lea     rax, aDatabasetype; "DatabaseType"
0x18004a437  jmp     short loc_18004A3CF
0x18004a439  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x18004a43e  lea     rdi, [rbx+28h]
0x18004a442  mov     r9d, 4; Type
0x18004a448  lea     rdx, g_ustrRuntimePlatform; ValueName
0x18004a44f  mov     [rsp+360h+CreateOptions], r9d; DataSize
0x18004a454  xor     r8d, r8d; TitleIndex
0x18004a457  mov     [rsp+360h+Class], rdi; Data
0x18004a45c  call    cs:__imp_NtSetValueKey
0x18004a462  test    eax, eax
0x18004a464  jns     short loc_18004A489
0x18004a466  mov     dword ptr [rsp+360h+Disposition], eax
0x18004a46a  lea     r9, aFailedToSetVal_1; "Failed to set value \"%ws\" to 0x%lx [%"...
0x18004a471  mov     eax, [rdi]
0x18004a473  mov     r8d, 47Bh
0x18004a479  mov     [rsp+360h+CreateOptions], eax
0x18004a47d  lea     rax, aDatabaseruntim; "DatabaseRuntimePlatform"
0x18004a484  jmp     loc_18004A3CF
0x18004a489  mov     rcx, [rbx+10h]
0x18004a48d  test    rcx, rcx
0x18004a490  jz      short loc_18004A4F2
0x18004a492  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a496  inc     rax
0x18004a499  cmp     [rcx+rax*2], r12w
0x18004a49e  jnz     short loc_18004A496
0x18004a4a0  lea     eax, ds:2[rax*2]
0x18004a4a7  mov     r9d, r13d; Type
0x18004a4aa  mov     [rsp+360h+CreateOptions], eax; DataSize
0x18004a4ae  lea     rdx, g_ustrDatabaseDescription; ValueName
0x18004a4b5  mov     [rsp+360h+Class], rcx; Data
0x18004a4ba  xor     r8d, r8d; TitleIndex
0x18004a4bd  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x18004a4c2  call    cs:__imp_NtSetValueKey
0x18004a4c8  test    eax, eax
0x18004a4ca  jns     short loc_18004A4F2
0x18004a4cc  mov     dword ptr [rsp+360h+Disposition], eax
0x18004a4d0  lea     r9, aFailedToSetVal_2; "Failed to set value \"%ws\" to %ws [%x]"
0x18004a4d7  mov     rax, [rbx+10h]
0x18004a4db  mov     r8d, 488h
0x18004a4e1  mov     qword ptr [rsp+360h+CreateOptions], rax
0x18004a4e6  lea     rax, aDatabasedescri; "DatabaseDescription"
0x18004a4ed  jmp     loc_18004A3CF
0x18004a4f2  test    rsi, rsi
0x18004a4f5  jnz     short loc_18004A507
0x18004a4f7  lea     rcx, [rbp+260h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004a4fb  call    cs:__imp_GetSystemTimeAsFileTime
0x18004a501  mov     rax, qword ptr [rbp+260h+SystemTimeAsFileTime.dwLowDateTime]
0x18004a505  jmp     short loc_18004A50A
0x18004a507  mov     rax, [rsi]
0x18004a50a  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x18004a50f  lea     rdx, g_ustrInstallTimeStamp; ValueName
0x18004a516  mov     edi, 8
0x18004a51b  mov     [rsp+360h+var_2F0], rax
0x18004a520  lea     rax, [rsp+360h+var_2F0]
0x18004a525  mov     [rsp+360h+CreateOptions], edi; DataSize
0x18004a529  xor     r8d, r8d; TitleIndex
0x18004a52c  mov     [rsp+360h+Class], rax; Data
0x18004a531  lea     r9d, [rdi+3]; Type
0x18004a535  call    cs:__imp_NtSetValueKey
0x18004a53b  test    eax, eax
0x18004a53d  jns     short loc_18004A55C
0x18004a53f  mov     [rsp+360h+CreateOptions], eax
0x18004a543  lea     r9, aFailedToSetVal; "Failed to set value \"%ws\" [%x]"
0x18004a54a  lea     rax, aDatabaseinstal; "DatabaseInstallTimeStamp"
0x18004a551  mov     r8d, 4A0h
  ... truncated ...
```
