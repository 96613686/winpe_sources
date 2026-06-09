# SdbRegisterDatabaseEx

- ea: `0x180061528`
- end: `0x180061b43`
- name: `SdbRegisterDatabaseEx`
- size: `1563`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800392b4`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x1800543c0`
- `0x18005453c`
- `0x1800546b8`
- `0x18005e5f0`
- `0x180061528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800615d0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800615d0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180061a13`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180061a13`
- `ntdll!NtClose` at `0x180061b01`
- `ntdll!NtClose` at `0x180061b10`
- `ntdll!NtClose` at `0x180061b01`
- `ntdll!NtClose` at `0x180061b10`
- `ntdll!RtlInitUnicodeString` at `0x1800615eb`
- `ntdll!RtlInitUnicodeString` at `0x1800616dc`
- `ntdll!RtlInitUnicodeString` at `0x1800617b2`
- `ntdll!RtlInitUnicodeString` at `0x1800615eb`
- `ntdll!RtlInitUnicodeString` at `0x1800616dc`
- `ntdll!RtlInitUnicodeString` at `0x1800617b2`
- `ntdll!RtlAllocateHeap` at `0x180061651`
- `ntdll!RtlAllocateHeap` at `0x180061651`
- `ntdll!RtlFreeHeap` at `0x180061acd`
- `ntdll!RtlFreeHeap` at `0x180061af1`
- `ntdll!RtlFreeHeap` at `0x180061acd`
- `ntdll!RtlFreeHeap` at `0x180061af1`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180061798`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180061798`
- `ntdll!RtlAppendUnicodeToString` at `0x180061777`
- `ntdll!RtlAppendUnicodeToString` at `0x180061789`
- `ntdll!RtlAppendUnicodeToString` at `0x180061777`
- `ntdll!RtlAppendUnicodeToString` at `0x180061789`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180061601`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800616a0`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180061601`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800616a0`
- `ntdll!NtCreateKey` at `0x1800617fe`
- `ntdll!NtCreateKey` at `0x18006187e`
- `ntdll!NtCreateKey` at `0x1800617fe`
- `ntdll!NtCreateKey` at `0x18006187e`
- `ntdll!NtSetValueKey` at `0x1800618c0`
- `ntdll!NtSetValueKey` at `0x180061925`
- `ntdll!NtSetValueKey` at `0x180061974`
- `ntdll!NtSetValueKey` at `0x1800619da`
- `ntdll!NtSetValueKey` at `0x180061a4d`
- `ntdll!NtSetValueKey` at `0x1800618c0`
- `ntdll!NtSetValueKey` at `0x180061925`
- `ntdll!NtSetValueKey` at `0x180061974`
- `ntdll!NtSetValueKey` at `0x1800619da`
- `ntdll!NtSetValueKey` at `0x180061a4d`
- `ntdll!NtSetInformationKey` at `0x180061a8b`
- `ntdll!NtSetInformationKey` at `0x180061a8b`

## string_xrefs

- `0x1800618da`: `DatabasePath`
- `0x180061a62`: `DatabaseInstallTimeStamp`
- `0x180061767`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x1800617a7`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x180061665`: `Failed to allocate 0x%lx bytes for the path buffer "%ws"`
- `0x180061816`: `Failed to create key "%ws" [%x]`
- `0x180061a99`: `Failed to set last write time on key [%x]`

## pseudocode

```c
__int64 __fastcall SdbRegisterDatabaseEx(PCWSTR SourceString, ULONG a2, struct _FILETIME *a3)
{
  unsigned int v5; // r15d
  NTSTATUS v6; // eax
  int v8; // r14d
  NTSTATUS v9; // eax
  int DatabaseInformationByName; // eax
  _QWORD *v11; // rbx
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
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME KeySetInformation; // [rsp+98h] [rbp-68h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  UNICODE_STRING Source; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v48; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v49[528]; // [rsp+110h] [rbp+10h] BYREF

  Data = a2;
  P = 0;
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
    DatabaseInformationByName = SdbGetDatabaseInformationByName(Destination.Buffer, &P);
    v11 = P;
    if ( !DatabaseInformationByName )
    {
      v12 = "Cannot obtain database information for \"%ws\"";
      v13 = 1030;
LABEL_12:
      AslLogCallPrintf(1, "SdbRegisterDatabaseEx", v13, v12, Destination.Buffer);
      goto LABEL_44;
    }
    if ( (*(_BYTE *)P & 1) == 0 )
    {
      v12 = "Cannot register database with no id \"%ws\"";
      v13 = 1035;
      goto LABEL_12;
    }
    v14 = AslGuidToString_UStr(&Source, (char *)P + 24);
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
    AslAnsiStringFree(&Source);
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
            v21 = NtSetValueKey(Handle, (PUNICODE_STRING)&g_ustrRuntimePlatform, 0, 4u, v11 + 5, 4u);
            if ( v21 >= 0 )
            {
              v22 = (_WORD *)v11[2];
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
                  v11[2],
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
        if ( v11 && (*(_DWORD *)v11 & 0x10000000) != 0 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
        if ( !v8 )
          goto LABEL_50;
        goto LABEL_48;
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
LABEL_48:
  if ( Destination.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
LABEL_50:
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v5;
}

```

## disassembly

```asm
0x180061528  mov     [rsp-8+arg_18], rbx
0x18006152d  push    rbp
0x18006152e  push    rsi
0x18006152f  push    rdi
0x180061530  push    r12
0x180061532  push    r13
0x180061534  push    r14
0x180061536  push    r15
0x180061538  lea     rbp, [rsp-230h]
0x180061540  sub     rsp, 330h
0x180061547  mov     rax, cs:__security_cookie
0x18006154e  xor     rax, rsp
0x180061551  mov     [rbp+260h+var_40], rax
0x180061558  xorps   xmm0, xmm0
0x18006155b  mov     [rsp+360h+Data], edx
0x18006155f  xorps   xmm1, xmm1
0x180061562  mov     rsi, r8
0x180061565  mov     rdi, rcx
0x180061568  xor     r12d, r12d
0x18006156b  xor     edx, edx; Val
0x18006156d  mov     [rbp+260h+P], r12
0x180061571  mov     r8d, 208h; Size
0x180061577  lea     rcx, [rbp+260h+var_250]; void *
0x18006157b  mov     r15d, r12d
0x18006157e  movups  xmmword ptr [rbp+260h+DestinationString.Length], xmm0
0x180061582  movups  xmmword ptr [rsp+360h+Destination.Length], xmm1
0x180061587  movups  xmmword ptr [rbp+260h+var_268.Length], xmm0
0x18006158b  movups  xmmword ptr [rsp+360h+var_2E8.Length], xmm1
0x180061590  movups  xmmword ptr [rbp+260h+Source.Length], xmm0
0x180061594  call    memset_0
0x180061599  xorps   xmm0, xmm0
0x18006159c  mov     [rbp+260h+KeyHandle], r12
0x1800615a0  xor     eax, eax
0x1800615a2  mov     [rsp+360h+Handle], r12
0x1800615a7  movups  xmmword ptr [rbp+260h+ObjectAttributes.ObjectName], xmm0
0x1800615ab  mov     rcx, rdi; Str
0x1800615ae  mov     [rsp+360h+var_300], r12d
0x1800615b3  mov     [rsp+360h+Length], r12d
0x1800615b8  lea     edx, [rax+25h]; Ch
0x1800615bb  mov     qword ptr [rbp+260h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800615bf  movups  xmmword ptr [rbp+260h+ObjectAttributes.Length], xmm0
0x1800615c3  mov     [rsp+360h+var_2F0], r12
0x1800615c8  movups  xmmword ptr [rbp+260h+ObjectAttributes+1Ch], xmm0
0x1800615cc  mov     [rbp+260h+KeySetInformation], r12
0x1800615d0  call    cs:__imp_wcschr
0x1800615d6  lea     r13d, [r12+1]
0x1800615db  mov     rdx, rdi; SourceString
0x1800615de  test    rax, rax
0x1800615e1  jz      loc_1800616D4
0x1800615e7  lea     rcx, [rbp+260h+DestinationString]; DestinationString
0x1800615eb  call    cs:__imp_RtlInitUnicodeString
0x1800615f1  lea     r9, [rsp+360h+Length]; Length
0x1800615f6  xor     ecx, ecx; Environment
0x1800615f8  lea     r8, [rsp+360h+Destination]; Destination
0x1800615fd  lea     rdx, [rbp+260h+DestinationString]; Source
0x180061601  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x180061607  cmp     eax, 0C0000023h
0x18006160c  jz      short loc_18006163A
0x18006160e  mov     [rsp+360h+CreateOptions], eax
0x180061612  lea     r9, aFailedToExpand_2
0x180061619  mov     [rsp+360h+Class], rdi
0x18006161e  mov     r8d, 3E2h
0x180061624  lea     rdx, aSdbregisterdat
0x18006162b  mov     ecx, r13d
0x18006162e  call    AslLogCallPrintf
0x180061633  xor     eax, eax
0x180061635  jmp     loc_180061B19
0x18006163a  mov     rcx, gs:60h
0x180061643  mov     edx, 8; Flags
0x180061648  mov     r8d, [rsp+360h+Length]; Size
0x18006164d  mov     rcx, [rcx+30h]; HeapHandle
0x180061651  call    cs:__imp_RtlAllocateHeap
0x180061657  mov     [rsp+360h+Destination.Buffer], rax
0x18006165c  test    rax, rax
0x18006165f  jnz     short loc_18006167D
0x180061661  mov     eax, [rsp+360h+Length]
0x180061665  lea     r9, aFailedToAlloca_6
0x18006166c  mov     qword ptr [rsp+360h+CreateOptions], rdi
0x180061671  mov     r8d, 3ECh
0x180061677  mov     dword ptr [rsp+360h+Class], eax
0x18006167b  jmp     short loc_180061624
0x18006167d  movzx   eax, word ptr [rsp+360h+Length]
0x180061682  lea     r9, [rsp+360h+Length]; Length
0x180061687  lea     r8, [rsp+360h+Destination]; Destination
0x18006168c  mov     [rsp+360h+Destination.MaximumLength], ax
0x180061691  lea     rdx, [rbp+260h+DestinationString]; Source
0x180061695  mov     [rsp+360h+Destination.Length], r12w
0x18006169b  xor     ecx, ecx; Environment
0x18006169d  mov     r14d, r13d
0x1800616a0  call    cs:__imp_RtlExpandEnvironmentStrings_U
0x1800616a6  test    eax, eax
0x1800616a8  jns     short loc_1800616E2
0x1800616aa  mov     [rsp+360h+CreateOptions], eax
0x1800616ae  lea     r9, aFailedToExpand_2
0x1800616b5  mov     r8d, 3F9h
0x1800616bb  mov     [rsp+360h+Class], rdi
0x1800616c0  lea     rdx, aSdbregisterdat
0x1800616c7  mov     ecx, r13d
0x1800616ca  call    AslLogCallPrintf
0x1800616cf  jmp     loc_180061AD8
0x1800616d4  lea     rcx, [rsp+360h+Destination]; DestinationString
0x1800616d9  mov     r14d, r12d
0x1800616dc  call    cs:__imp_RtlInitUnicodeString
0x1800616e2  mov     rcx, [rsp+360h+Destination.Buffer]
0x1800616e7  lea     rdx, [rbp+260h+P]
0x1800616eb  call    SdbGetDatabaseInformationByName
0x1800616f0  mov     rbx, [rbp+260h+P]
0x1800616f4  test    eax, eax
0x1800616f6  jnz     short loc_180061723
0x1800616f8  lea     r9, aCannotObtainDa
0x1800616ff  mov     r8d, 406h
0x180061705  mov     rax, [rsp+360h+Destination.Buffer]
0x18006170a  mov     [rsp+360h+Class], rax
0x18006170f  lea     rdx, aSdbregisterdat
0x180061716  mov     ecx, r13d
0x180061719  call    AslLogCallPrintf
0x18006171e  jmp     loc_180061AAE
0x180061723  test    [rbx], r13b
0x180061726  jnz     short loc_180061737
0x180061728  lea     r9, aCannotRegister
0x18006172f  mov     r8d, 40Bh
0x180061735  jmp     short loc_180061705
0x180061737  lea     rdx, [rbx+18h]
0x18006173b  lea     rcx, [rbp+260h+Source]
0x18006173f  call    AslGuidToString_UStr
0x180061744  test    eax, eax
0x180061746  jns     short loc_18006175B
0x180061748  mov     dword ptr [rsp+360h+Class], eax
0x18006174c  lea     r9, aCannotConvertG
0x180061753  mov     r8d, 411h
0x180061759  jmp     short loc_18006170F
0x18006175b  lea     rax, [rbp+260h+var_250]
0x18006175f  mov     dword ptr [rsp+360h+var_2E8.Length], 2080000h
0x180061767  lea     rdx, aRegistryMachin_2
0x18006176e  mov     [rbp+260h+var_2E8.Buffer], rax
0x180061772  lea     rcx, [rsp+360h+var_2E8]; Destination
0x180061777  call    cs:__imp_RtlAppendUnicodeToString
0x18006177d  lea     rdx, asc_18006E074
0x180061784  lea     rcx, [rsp+360h+var_2E8]; Destination
0x180061789  call    cs:__imp_RtlAppendUnicodeToString
0x18006178f  lea     rdx, [rbp+260h+Source]; Source
0x180061793  lea     rcx, [rsp+360h+var_2E8]; Destination
0x180061798  call    cs:__imp_RtlAppendUnicodeStringToString
0x18006179e  lea     rcx, [rbp+260h+Source]
0x1800617a2  call    AslAnsiStringFree
0x1800617a7  lea     rdx, aRegistryMachin_2
0x1800617ae  lea     rcx, [rbp+260h+var_268]; DestinationString
0x1800617b2  call    cs:__imp_RtlInitUnicodeString
0x1800617b8  lea     rax, [rbp+260h+var_268]
0x1800617bc  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x1800617c3  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x1800617c7  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x1800617cb  lea     rax, [rsp+360h+var_300]
0x1800617d0  mov     [rbp+260h+ObjectAttributes.RootDirectory], r12
0x1800617d4  mov     [rsp+360h+Disposition], rax; Disposition
0x1800617d9  lea     rcx, [rbp+260h+KeyHandle]; KeyHandle
0x1800617dd  xorps   xmm0, xmm0
0x1800617e0  mov     [rsp+360h+CreateOptions], r12d; CreateOptions
0x1800617e5  xor     r9d, r9d; TitleIndex
0x1800617e8  mov     [rsp+360h+Class], r12; Class
0x1800617ed  mov     edx, 2010Fh; DesiredAccess
0x1800617f2  mov     [rbp+260h+ObjectAttributes.Attributes], 40h ; '@'
0x1800617f9  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800617fe  call    cs:__imp_NtCreateKey
0x180061804  test    eax, eax
0x180061806  jns     short loc_180061836
0x180061808  mov     [rsp+360h+CreateOptions], eax
0x18006180c  mov     r8d, 43Ch
0x180061812  mov     rax, [rbp+260h+var_268.Buffer]
0x180061816  lea     r9, aFailedToCreate_3
0x18006181d  lea     rdx, aSdbregisterdat
0x180061824  mov     [rsp+360h+Class], rax
0x180061829  mov     ecx, r13d
0x18006182c  call    AslLogCallPrintf
0x180061831  jmp     loc_180061AAE
0x180061836  lea     rax, [rsp+360h+var_2E8]
0x18006183b  mov     [rbp+260h+ObjectAttributes.Length], 30h ; '0'
0x180061842  mov     [rbp+260h+ObjectAttributes.ObjectName], rax
0x180061846  lea     r8, [rbp+260h+ObjectAttributes]; ObjectAttributes
0x18006184a  lea     rax, [rsp+360h+var_300]
0x18006184f  mov     [rbp+260h+ObjectAttributes.RootDirectory], r12
0x180061853  mov     [rsp+360h+Disposition], rax; Disposition
0x180061858  lea     rcx, [rsp+360h+Handle]; KeyHandle
0x18006185d  xorps   xmm0, xmm0
0x180061860  mov     [rsp+360h+CreateOptions], r12d; CreateOptions
0x180061865  xor     r9d, r9d; TitleIndex
0x180061868  mov     [rsp+360h+Class], r12; Class
0x18006186d  mov     edx, 2010Fh; DesiredAccess
0x180061872  mov     [rbp+260h+ObjectAttributes.Attributes], 40h ; '@'
0x180061879  movdqu  xmmword ptr [rbp+260h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006187e  call    cs:__imp_NtCreateKey
0x180061884  test    eax, eax
0x180061886  jns     short loc_18006189B
0x180061888  mov     [rsp+360h+CreateOptions], eax
0x18006188c  mov     r8d, 454h
0x180061892  mov     rax, [rbp+260h+var_2E8.Buffer]
0x180061896  jmp     loc_180061816
0x18006189b  movzx   eax, [rsp+360h+Destination.MaximumLength]
0x1800618a0  lea     rdx, g_ustrDatabasePath; ValueName
0x1800618a7  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x1800618ac  mov     r9d, r13d; Type
0x1800618af  mov     [rsp+360h+CreateOptions], eax; DataSize
0x1800618b3  xor     r8d, r8d; TitleIndex
0x1800618b6  mov     rax, [rsp+360h+Destination.Buffer]
0x1800618bb  mov     [rsp+360h+Class], rax; Data
0x1800618c0  call    cs:__imp_NtSetValueKey
0x1800618c6  test    eax, eax
0x1800618c8  jns     short loc_180061900
0x1800618ca  mov     dword ptr [rsp+360h+Disposition], eax
0x1800618ce  lea     r9, aFailedToSetVal_0
0x1800618d5  mov     qword ptr [rsp+360h+CreateOptions], rdi
0x1800618da  lea     rax, aDatabasepath
0x1800618e1  mov     r8d, 463h
0x1800618e7  lea     rdx, aSdbregisterdat
0x1800618ee  mov     [rsp+360h+Class], rax
0x1800618f3  mov     ecx, r13d
0x1800618f6  call    AslLogCallPrintf
0x1800618fb  jmp     loc_180061AAE
0x180061900  mov     ecx, 4
0x180061905  lea     rax, [rsp+360h+Data]
0x18006190a  mov     [rsp+360h+CreateOptions], ecx; DataSize
0x18006190e  lea     rdx, g_ustrDatabaseType; ValueName
0x180061915  mov     r9d, ecx; Type
0x180061918  mov     [rsp+360h+Class], rax; Data
0x18006191d  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x180061922  xor     r8d, r8d; TitleIndex
0x180061925  call    cs:__imp_NtSetValueKey
0x18006192b  test    eax, eax
0x18006192d  jns     short loc_180061951
0x18006192f  mov     dword ptr [rsp+360h+Disposition], eax
0x180061933  lea     r9, aFailedToSetVal_1
0x18006193a  mov     eax, [rsp+360h+Data]
0x18006193e  mov     r8d, 46Fh
0x180061944  mov     [rsp+360h+CreateOptions], eax
0x180061948  lea     rax, aDatabasetype
0x18006194f  jmp     short loc_1800618E7
0x180061951  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x180061956  lea     rdi, [rbx+28h]
0x18006195a  mov     r9d, 4; Type
0x180061960  lea     rdx, g_ustrRuntimePlatform; ValueName
0x180061967  mov     [rsp+360h+CreateOptions], r9d; DataSize
0x18006196c  xor     r8d, r8d; TitleIndex
0x18006196f  mov     [rsp+360h+Class], rdi; Data
0x180061974  call    cs:__imp_NtSetValueKey
0x18006197a  test    eax, eax
0x18006197c  jns     short loc_1800619A1
0x18006197e  mov     dword ptr [rsp+360h+Disposition], eax
0x180061982  lea     r9, aFailedToSetVal_1
0x180061989  mov     eax, [rdi]
0x18006198b  mov     r8d, 47Bh
0x180061991  mov     [rsp+360h+CreateOptions], eax
0x180061995  lea     rax, aDatabaseruntim
0x18006199c  jmp     loc_1800618E7
0x1800619a1  mov     rcx, [rbx+10h]
0x1800619a5  test    rcx, rcx
0x1800619a8  jz      short loc_180061A0A
0x1800619aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800619ae  inc     rax
0x1800619b1  cmp     [rcx+rax*2], r12w
0x1800619b6  jnz     short loc_1800619AE
0x1800619b8  lea     eax, ds:2[rax*2]
0x1800619bf  mov     r9d, r13d; Type
0x1800619c2  mov     [rsp+360h+CreateOptions], eax; DataSize
0x1800619c6  lea     rdx, g_ustrDatabaseDescription; ValueName
0x1800619cd  mov     [rsp+360h+Class], rcx; Data
0x1800619d2  xor     r8d, r8d; TitleIndex
0x1800619d5  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x1800619da  call    cs:__imp_NtSetValueKey
0x1800619e0  test    eax, eax
0x1800619e2  jns     short loc_180061A0A
0x1800619e4  mov     dword ptr [rsp+360h+Disposition], eax
0x1800619e8  lea     r9, aFailedToSetVal_2
0x1800619ef  mov     rax, [rbx+10h]
0x1800619f3  mov     r8d, 488h
0x1800619f9  mov     qword ptr [rsp+360h+CreateOptions], rax
0x1800619fe  lea     rax, aDatabasedescri
0x180061a05  jmp     loc_1800618E7
0x180061a0a  test    rsi, rsi
0x180061a0d  jnz     short loc_180061A1F
0x180061a0f  lea     rcx, [rbp+260h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180061a13  call    cs:__imp_GetSystemTimeAsFileTime
0x180061a19  mov     rax, qword ptr [rbp+260h+SystemTimeAsFileTime.dwLowDateTime]
0x180061a1d  jmp     short loc_180061A22
0x180061a1f  mov     rax, [rsi]
0x180061a22  mov     rcx, [rsp+360h+Handle]; KeyHandle
0x180061a27  lea     rdx, g_ustrInstallTimeStamp; ValueName
0x180061a2e  mov     edi, 8
0x180061a33  mov     [rsp+360h+var_2F0], rax
0x180061a38  lea     rax, [rsp+360h+var_2F0]
0x180061a3d  mov     [rsp+360h+CreateOptions], edi; DataSize
0x180061a41  xor     r8d, r8d; TitleIndex
0x180061a44  mov     [rsp+360h+Class], rax; Data
0x180061a49  lea     r9d, [rdi+3]; Type
0x180061a4d  call    cs:__imp_NtSetValueKey
0x180061a53  test    eax, eax
0x180061a55  jns     short loc_180061A74
0x180061a57  mov     [rsp+360h+CreateOptions], eax
0x180061a5b  lea     r9, aFailedToSetVal
0x180061a62  lea     rax, aDatabaseinstal
0x180061a69  mov     r8d, 4A0h
  ... truncated ...
```
