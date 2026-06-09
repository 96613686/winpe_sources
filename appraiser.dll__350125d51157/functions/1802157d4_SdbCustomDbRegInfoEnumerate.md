# SdbCustomDbRegInfoEnumerate

- ea: `0x1802157d4`
- end: `0x180215e98`
- name: `SdbCustomDbRegInfoEnumerate`
- size: `1732`
- prototype: `__int64 __fastcall(ULONG Index)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801fb6a4`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x1800178f8`
- `0x180017ce8`
- `0x180017e58`
- `0x180017f48`
- `0x180019308`
- `0x18001a2f4`
- `0x18001b4c0`
- `0x18001b860`
- `0x1802157d4`
- `0x180215ea0`
- `0x180216448`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180215d07`
- `ntdll!RtlInitUnicodeStringEx` at `0x180215d07`
- `ntdll!RtlAllocateHeap` at `0x180215b73`
- `ntdll!RtlAllocateHeap` at `0x180215b73`
- `ntdll!NtClose` at `0x180215a11`
- `ntdll!NtClose` at `0x180215dd9`
- `ntdll!NtClose` at `0x180215e5c`
- `ntdll!NtClose` at `0x180215a11`
- `ntdll!NtClose` at `0x180215dd9`
- `ntdll!NtClose` at `0x180215e5c`
- `ntdll!RtlDoesFileExists_U` at `0x180215e33`
- `ntdll!RtlDoesFileExists_U` at `0x180215e33`
- `ntdll!RtlNtStatusToDosError` at `0x180215887`
- `ntdll!RtlNtStatusToDosError` at `0x1802158f8`
- `ntdll!RtlNtStatusToDosError` at `0x1802159e8`
- `ntdll!RtlNtStatusToDosError` at `0x180215a1d`
- `ntdll!RtlNtStatusToDosError` at `0x180215aa0`
- `ntdll!RtlNtStatusToDosError` at `0x180215ad4`
- `ntdll!RtlNtStatusToDosError` at `0x180215b0a`
- `ntdll!RtlNtStatusToDosError` at `0x180215b3f`
- `ntdll!RtlNtStatusToDosError` at `0x180215bbf`
- `ntdll!RtlNtStatusToDosError` at `0x180215bed`
- `ntdll!RtlNtStatusToDosError` at `0x180215c26`
- `ntdll!RtlNtStatusToDosError` at `0x180215c74`
- `ntdll!RtlNtStatusToDosError` at `0x180215cc0`
- `ntdll!RtlNtStatusToDosError` at `0x180215d53`
- `ntdll!RtlNtStatusToDosError` at `0x180215da6`
- `ntdll!RtlNtStatusToDosError` at `0x180215de5`
- `ntdll!RtlNtStatusToDosError` at `0x180215887`
- `ntdll!RtlNtStatusToDosError` at `0x1802158f8`
- `ntdll!RtlNtStatusToDosError` at `0x1802159e8`
- `ntdll!RtlNtStatusToDosError` at `0x180215a1d`
- `ntdll!RtlNtStatusToDosError` at `0x180215aa0`
- `ntdll!RtlNtStatusToDosError` at `0x180215ad4`
- `ntdll!RtlNtStatusToDosError` at `0x180215b0a`
- `ntdll!RtlNtStatusToDosError` at `0x180215b3f`
- `ntdll!RtlNtStatusToDosError` at `0x180215bbf`
- `ntdll!RtlNtStatusToDosError` at `0x180215bed`
- `ntdll!RtlNtStatusToDosError` at `0x180215c26`
- `ntdll!RtlNtStatusToDosError` at `0x180215c74`
- `ntdll!RtlNtStatusToDosError` at `0x180215cc0`
- `ntdll!RtlNtStatusToDosError` at `0x180215d53`
- `ntdll!RtlNtStatusToDosError` at `0x180215da6`
- `ntdll!RtlNtStatusToDosError` at `0x180215de5`
- `ntdll!NtEnumerateKey` at `0x1802158ea`
- `ntdll!NtEnumerateKey` at `0x1802158ea`

## string_xrefs

- `0x180215d24`: `AslRegistryGetUInt64`
- `0x180215867`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x180215cf3`: `DatabaseInstallTimeStamp`
- `0x180215d64`: `DatabaseInstallTimeStamp`
- `0x180215c0a`: `DatabasePath`
- `0x180215935`: `InstalledSDB child key was considerably larger than the size of a GUID string [%d]`
- `0x1802158a7`: `Failed to open key "%ws" [%d]`
- `0x180215b45`: `Failed to open InstalledSDB child key (index %d) [%d]`
- `0x180215aa6`: `RtlStringCchCopyW failed to copy installed sdb key path (index %d) [%d]`
- `0x180215ada`: `RtlStringCchCatW failed to append path separator (index %d) [%d]`
- `0x1802159ee`: `Failed to copy the InstalledSDB child key name (index %d) [%d]`
- `0x180215a29`: `Failed to close the InstalledSDB key [%d]`
- `0x180215922`: `Failed to enumerate key InstalledSDB index %d [%d]`
- `0x18021596b`: `InstalledSDB child key name was too long (index %d).`
- `0x180215bc5`: `Failed to duplicate reg key path string [%d]`

## pseudocode

```c
__int64 __fastcall SdbCustomDbRegInfoEnumerate(ULONG Index, _QWORD *a2)
{
  const WCHAR *v5; // r15
  NTSTATUS v6; // eax
  ULONG v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  int v11; // eax
  int v12; // edi
  ULONG v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rax
  wchar_t *v19; // rcx
  __int64 v20; // r8
  wchar_t *v21; // r9
  wchar_t *v22; // rdx
  ULONG v23; // eax
  int v24; // eax
  unsigned __int16 *v25; // r9
  __int64 v26; // r8
  unsigned __int16 *v27; // rdx
  NTSTATUS v28; // eax
  NTSTATUS v29; // eax
  NTSTATUS v30; // eax
  _DWORD *Heap; // rax
  _DWORD *v32; // r14
  NTSTATUS v33; // eax
  NTSTATUS v34; // eax
  int v35; // r15d
  NTSTATUS String; // eax
  NTSTATUS v37; // eax
  NTSTATUS UInt32; // eax
  HANDLE v39; // r12
  NTSTATUS inited; // eax
  NTSTATUS UInt64_UStr; // esi
  NTSTATUS v42; // eax
  int v43; // eax
  int v44; // eax
  const WCHAR *v45; // rcx
  int v46; // esi
  const WCHAR *Length; // [rsp+20h] [rbp-E0h]
  PULONG ResultLength; // [rsp+28h] [rbp-D8h]
  HANDLE KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  ULONG v50; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD *v51; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE KeyInformation[12]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v54; // [rsp+6Ch] [rbp-94h]
  char v55; // [rsp+70h] [rbp-90h] BYREF
  __int16 v56; // [rsp+27Eh] [rbp+17Eh]
  wchar_t String2[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v58[352]; // [rsp+490h] [rbp+390h] BYREF

  if ( !a2 )
    return 87;
  *a2 = 0;
  KeyHandle = 0;
  v50 = 0;
  v51 = 0;
  memset_0(String2, 0, 0x208u);
  memset_0(v58, 0, 0x2BEu);
  memset_0(KeyInformation, 0, 0x220u);
  v5 = L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB";
  v6 = AslRegistryOpenKey(
         &KeyHandle,
         L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB",
         2147483904LL);
  if ( v6 >= 0 )
  {
    v11 = NtEnumerateKey(KeyHandle, Index, KeyBasicInformation, KeyInformation, 0x220u, &v50);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = RtlNtStatusToDosError(v11);
      v8 = v13;
      if ( v12 != -2147483643 && v12 != -1073741789 )
      {
        if ( v13 == 259 )
          goto LABEL_71;
        LODWORD(ResultLength) = v13;
        v9 = "Failed to enumerate key InstalledSDB index %d [%d]";
        LODWORD(Length) = Index;
        v10 = 517;
        goto LABEL_7;
      }
      v14 = "InstalledSDB child key was considerably larger than the size of a GUID string [%d]";
      v15 = 515;
      v16 = 2;
LABEL_14:
      LODWORD(Length) = v13;
      AslLogCallPrintf(v16, "SdbCustomDbRegInfoEnumerate", v15, v14, Length);
      goto LABEL_71;
    }
    if ( v54 >= 0x208 )
    {
      v8 = 31;
      LODWORD(Length) = Index;
      AslLogCallPrintf(
        1,
        "SdbCustomDbRegInfoEnumerate",
        529,
        "InstalledSDB child key name was too long (index %d).",
        Length);
      goto LABEL_71;
    }
    v17 = 2147483646;
    v56 = 0;
    v18 = 2147483646;
    v19 = (wchar_t *)&v55;
    v20 = 260;
    v21 = String2;
    do
    {
      if ( !v18 )
        break;
      if ( !*v19 )
        break;
      *v21++ = *v19++;
      --v18;
      --v20;
    }
    while ( v20 );
    v22 = v21 - 1;
    if ( v20 )
      v22 = v21;
    *v22 = 0;
    if ( !v20 )
    {
      v23 = RtlNtStatusToDosError(-2147483643);
      v9 = "Failed to copy the InstalledSDB child key name (index %d) [%d]";
      v10 = 545;
LABEL_25:
      LODWORD(ResultLength) = v23;
      v8 = v23;
      LODWORD(Length) = Index;
      goto LABEL_7;
    }
    v24 = NtClose(KeyHandle);
    if ( v24 < 0 )
    {
      v13 = RtlNtStatusToDosError(v24);
      v15 = 556;
LABEL_28:
      v14 = "Failed to close the InstalledSDB key [%d]";
LABEL_29:
      v8 = v13;
      v16 = 1;
      goto LABEL_14;
    }
    KeyHandle = 0;
    memset_0(KeyInformation, 0, 0x220u);
    v25 = v58;
    v26 = 351;
    do
    {
      if ( !v17 )
        break;
      if ( !*v5 )
        break;
      *v25++ = *v5++;
      --v17;
      --v26;
    }
    while ( v26 );
    v27 = v25 - 1;
    if ( v26 )
      v27 = v25;
    *v27 = 0;
    if ( !v26 )
    {
      v23 = RtlNtStatusToDosError(-2147483643);
      v9 = "RtlStringCchCopyW failed to copy installed sdb key path (index %d) [%d]";
      v10 = 567;
      goto LABEL_25;
    }
    v28 = RtlStringCchCatW(v58, 0x15Fu, L"\\");
    if ( v28 < 0 )
    {
      v23 = RtlNtStatusToDosError(v28);
      v9 = "RtlStringCchCatW failed to append path separator (index %d) [%d]";
      v10 = 575;
      goto LABEL_25;
    }
    v29 = RtlStringCchCatW(v58, 0x15Fu, String2);
    if ( v29 < 0 )
    {
      v23 = RtlNtStatusToDosError(v29);
      v9 = "RtlStringCchCatW failed to append key name (index %d) [%d]";
      v10 = 583;
      goto LABEL_25;
    }
    v30 = AslRegistryOpenKey(&KeyHandle, v58, 2147483904LL);
    if ( v30 < 0 )
    {
      v23 = RtlNtStatusToDosError(v30);
      v9 = "Failed to open InstalledSDB child key (index %d) [%d]";
      v10 = 591;
      goto LABEL_25;
    }
    v8 = 8;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x48u);
    v32 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SdbCustomDbRegInfoEnumerate", 602, "Failed to allocate registration info");
      goto LABEL_71;
    }
    *Heap = 72;
    v51 = Heap;
    v33 = AslStringDuplicate(Heap + 2, v58);
    if ( v33 < 0 )
    {
      v13 = RtlNtStatusToDosError(v33);
      v14 = "Failed to duplicate reg key path string [%d]";
      v15 = 613;
      goto LABEL_29;
    }
    v34 = AslGuidFromString((GUID *)v32 + 1);
    if ( v34 < 0 )
    {
      v23 = RtlNtStatusToDosError(v34);
      v9 = "Failed to get SDB Guid from Key name (index %d) [%d]";
      v10 = 624;
      goto LABEL_25;
    }
    v35 = 0;
    String = AslRegistryGetString(v32 + 8, KeyHandle, L"DatabasePath");
    if ( String < 0 )
    {
      LODWORD(ResultLength) = RtlNtStatusToDosError(String);
      AslLogCallPrintf(
        1,
        "SdbCustomDbRegInfoEnumerate",
        639,
        "Failed trying to query value \"%ws\" [%d]",
        L"DatabasePath",
        ResultLength);
      v35 = 6;
    }
    v37 = AslRegistryGetString(v32 + 12, KeyHandle, L"DatabaseDescription");
    if ( v37 < 0 )
    {
      LODWORD(ResultLength) = RtlNtStatusToDosError(v37);
      AslLogCallPrintf(
        1,
        "SdbCustomDbRegInfoEnumerate",
        651,
        "Failed trying to query value \"%ws\" [%d]",
        L"DatabaseDescription",
        ResultLength);
      v35 |= 2u;
    }
    UInt32 = AslRegistryGetUInt32(v32 + 14, KeyHandle, L"DatabaseType");
    if ( UInt32 < 0 )
    {
      LODWORD(ResultLength) = RtlNtStatusToDosError(UInt32);
      AslLogCallPrintf(
        1,
        "SdbCustomDbRegInfoEnumerate",
        662,
        "Failed trying to query value \"%ws\" [%d]",
        L"DatabaseType",
        ResultLength);
      v35 |= 2u;
    }
    v39 = KeyHandle;
    DestinationString = 0;
    inited = RtlInitUnicodeStringEx(&DestinationString, L"DatabaseInstallTimeStamp");
    UInt64_UStr = inited;
    if ( inited >= 0 )
    {
      UInt64_UStr = AslRegistryGetUInt64_UStr(v32 + 10, v39, &DestinationString);
      if ( UInt64_UStr >= 0 )
      {
LABEL_60:
        v42 = AslRegistryGetUInt32(v32 + 17, KeyHandle, L"DatabaseRuntimePlatform");
        if ( v42 < 0 )
        {
          LODWORD(ResultLength) = RtlNtStatusToDosError(v42);
          AslLogCallPrintf(
            1,
            "SdbCustomDbRegInfoEnumerate",
            685,
            "Failed trying to query value \"%ws\" [%d]",
            L"DatabaseRuntimePlatform",
            ResultLength);
          v35 |= 2u;
        }
        v43 = NtClose(KeyHandle);
        if ( v43 >= 0 )
        {
          KeyHandle = 0;
          memset_0(KeyInformation, 0, 0x220u);
          v44 = SdbpCustomDbRegInfoCheckForExePointer(String2);
          v45 = (const WCHAR *)*((_QWORD *)v32 + 4);
          v46 = v35 | 8;
          if ( v44 )
            v46 = v35;
          if ( !v45 || !*v45 || !RtlDoesFileExists_U(v45) )
            v46 |= 4u;
          v51 = 0;
          v32[15] = v46 | 1;
          v8 = 0;
          *a2 = v32;
          goto LABEL_71;
        }
        v13 = RtlNtStatusToDosError(v43);
        v15 = 696;
        goto LABEL_28;
      }
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetUInt64", 1266, "RtlInitUnicodeStringEx failed [%x]", inited);
    }
    LODWORD(ResultLength) = RtlNtStatusToDosError(UInt64_UStr);
    AslLogCallPrintf(
      1,
      "SdbCustomDbRegInfoEnumerate",
      673,
      "Failed trying to query value \"%ws\" [%d]",
      L"DatabaseInstallTimeStamp",
      ResultLength);
    v35 |= 2u;
    goto LABEL_60;
  }
  v7 = RtlNtStatusToDosError(v6);
  v8 = v7;
  if ( v7 != 1168 && v7 != 2 )
  {
    LODWORD(ResultLength) = v7;
    v9 = "Failed to open key \"%ws\" [%d]";
    Length = L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\InstalledSDB";
    v10 = 499;
LABEL_7:
    AslLogCallPrintf(1, "SdbCustomDbRegInfoEnumerate", v10, v9, Length, ResultLength);
  }
LABEL_71:
  if ( KeyHandle )
    NtClose(KeyHandle);
  SdbCustomDbRegInfoFree(&v51);
  return v8;
}

```

## disassembly

```asm
0x1802157d4  mov     [rsp-8+arg_10], rbx
0x1802157d9  push    rbp
0x1802157da  push    rsi
0x1802157db  push    rdi
0x1802157dc  push    r12
0x1802157de  push    r13
0x1802157e0  push    r14
0x1802157e2  push    r15
0x1802157e4  lea     rbp, [rsp-660h]
0x1802157ec  sub     rsp, 760h
0x1802157f3  mov     rax, cs:__security_cookie
0x1802157fa  xor     rax, rsp
0x1802157fd  mov     [rbp+690h+var_40], rax
0x180215804  xor     r12d, r12d
0x180215807  mov     r13, rdx
0x18021580a  mov     esi, ecx
0x18021580c  test    rdx, rdx
0x18021580f  jnz     short loc_180215819
0x180215811  lea     eax, [rdx+57h]
0x180215814  jmp     loc_180215E6E
0x180215819  mov     [rdx], r12
0x18021581c  lea     rcx, [rbp+690h+String2]; void *
0x180215823  mov     ebx, 208h
0x180215828  mov     [rsp+790h+KeyHandle], r12
0x18021582d  mov     r8d, ebx; Size
0x180215830  mov     [rsp+790h+var_758], r12d
0x180215835  xor     edx, edx; Val
0x180215837  mov     [rsp+790h+var_750], r12
0x18021583c  call    memset_0
0x180215841  xor     edx, edx; Val
0x180215843  lea     rcx, [rbp+690h+var_300]; void *
0x18021584a  mov     r8d, 2BEh; Size
0x180215850  call    memset_0
0x180215855  lea     edi, [rbx+18h]
0x180215858  xor     edx, edx; Val
0x18021585a  mov     r8d, edi; Size
0x18021585d  lea     rcx, [rsp+790h+KeyInformation]; void *
0x180215862  call    memset_0
0x180215867  lea     r15, Source; "\\Registry\\Machine\\Software\\Microsof"...
0x18021586e  mov     r8d, 80000100h
0x180215874  mov     rdx, r15
0x180215877  lea     rcx, [rsp+790h+KeyHandle]
0x18021587c  call    AslRegistryOpenKey
0x180215881  test    eax, eax
0x180215883  jns     short loc_1802158CD
0x180215885  mov     ecx, eax; Status
0x180215887  call    cs:__imp_RtlNtStatusToDosError
0x18021588d  mov     ebx, eax
0x18021588f  cmp     eax, 490h
0x180215894  jz      loc_180215E52
0x18021589a  cmp     eax, 2
0x18021589d  jz      loc_180215E52
0x1802158a3  mov     dword ptr [rsp+790h+ResultLength], eax
0x1802158a7  lea     r9, aFailedToOpenKe_1; "Failed to open key \"%ws\" [%d]"
0x1802158ae  mov     qword ptr [rsp+790h+Length], r15
0x1802158b3  lea     r8d, [rdi-2Dh]
0x1802158b7  mov     ecx, 1
0x1802158bc  lea     rdx, aSdbcustomdbreg; "SdbCustomDbRegInfoEnumerate"
0x1802158c3  call    AslLogCallPrintf
0x1802158c8  jmp     loc_180215E52
0x1802158cd  mov     rcx, [rsp+790h+KeyHandle]; KeyHandle
0x1802158d2  lea     rax, [rsp+790h+var_758]
0x1802158d7  mov     [rsp+790h+ResultLength], rax; ResultLength
0x1802158dc  lea     r9, [rsp+790h+KeyInformation]; KeyInformation
0x1802158e1  xor     r8d, r8d; KeyInformationClass
0x1802158e4  mov     [rsp+790h+Length], edi; Length
0x1802158e8  mov     edx, esi; Index
0x1802158ea  call    cs:__imp_NtEnumerateKey
0x1802158f0  mov     edi, eax
0x1802158f2  test    eax, eax
0x1802158f4  jns     short loc_18021595C
0x1802158f6  mov     ecx, eax; Status
0x1802158f8  call    cs:__imp_RtlNtStatusToDosError
0x1802158fe  mov     r14d, 80000005h
0x180215904  mov     ebx, eax
0x180215906  cmp     edi, r14d
0x180215909  jz      short loc_180215935
0x18021590b  cmp     edi, 0C0000023h
0x180215911  jz      short loc_180215935
0x180215913  cmp     eax, 103h
0x180215918  jz      loc_180215E52
0x18021591e  mov     dword ptr [rsp+790h+ResultLength], eax
0x180215922  lea     r9, aFailedToEnumer_3; "Failed to enumerate key InstalledSDB in"...
0x180215929  mov     [rsp+790h+Length], esi
0x18021592d  mov     r8d, 205h
0x180215933  jmp     short loc_1802158B7
0x180215935  lea     r9, aInstalledsdbCh_0; "InstalledSDB child key was considerably"...
0x18021593c  mov     r8d, 203h
0x180215942  mov     ecx, 2
0x180215947  mov     [rsp+790h+Length], eax
0x18021594b  lea     rdx, aSdbcustomdbreg; "SdbCustomDbRegInfoEnumerate"
0x180215952  call    AslLogCallPrintf
0x180215957  jmp     loc_180215E52
0x18021595c  cmp     [rsp+790h+var_724], ebx
0x180215960  jb      short loc_18021597D
0x180215962  mov     ebx, 1Fh
0x180215967  mov     [rsp+790h+Length], esi
0x18021596b  lea     r9, aInstalledsdbCh; "InstalledSDB child key name was too lon"...
0x180215972  mov     r8d, 211h
0x180215978  lea     ecx, [rbx-1Eh]
0x18021597b  jmp     short loc_18021594B
0x18021597d  mov     ebx, 7FFFFFFEh
0x180215982  mov     [rbp+690h+var_512], r12w
0x18021598a  mov     eax, ebx
0x18021598c  lea     rcx, [rsp+790h+var_720]
0x180215991  mov     r8d, 104h
0x180215997  lea     r9, [rbp+690h+String2]
0x18021599e  mov     edi, 1
0x1802159a3  test    rax, rax
0x1802159a6  jz      short loc_1802159C4
0x1802159a8  movzx   edx, word ptr [rcx]
0x1802159ab  test    dx, dx
0x1802159ae  jz      short loc_1802159C4
0x1802159b0  mov     [r9], dx
0x1802159b4  add     rcx, 2
0x1802159b8  add     r9, 2
0x1802159bc  sub     rax, rdi
0x1802159bf  sub     r8, rdi
0x1802159c2  jnz     short loc_1802159A3
0x1802159c4  mov     rax, r8
0x1802159c7  lea     rdx, [r9-2]
0x1802159cb  neg     rax
0x1802159ce  mov     r14d, 80000005h
0x1802159d4  sbb     ecx, ecx
0x1802159d6  not     ecx
0x1802159d8  and     ecx, r14d; Status
0x1802159db  test    r8, r8
0x1802159de  cmovnz  rdx, r9
0x1802159e2  mov     [rdx], r12w
0x1802159e6  jnz     short loc_180215A0C
0x1802159e8  call    cs:__imp_RtlNtStatusToDosError
0x1802159ee  lea     r9, aFailedToCopyTh; "Failed to copy the InstalledSDB child k"...
0x1802159f5  mov     r8d, 221h
0x1802159fb  mov     dword ptr [rsp+790h+ResultLength], eax
0x1802159ff  mov     ebx, eax
0x180215a01  mov     [rsp+790h+Length], esi
0x180215a05  mov     ecx, edi
0x180215a07  jmp     loc_1802158BC
0x180215a0c  mov     rcx, [rsp+790h+KeyHandle]; Handle
0x180215a11  call    cs:__imp_NtClose
0x180215a17  test    eax, eax
0x180215a19  jns     short loc_180215A39
0x180215a1b  mov     ecx, eax; Status
0x180215a1d  call    cs:__imp_RtlNtStatusToDosError
0x180215a23  mov     r8d, 22Ch
0x180215a29  lea     r9, aFailedToCloseT; "Failed to close the InstalledSDB key [%"...
0x180215a30  mov     ebx, eax
0x180215a32  mov     ecx, edi
0x180215a34  jmp     loc_180215947
0x180215a39  xor     edx, edx; Val
0x180215a3b  mov     [rsp+790h+KeyHandle], r12
0x180215a40  mov     r8d, 220h; Size
0x180215a46  lea     rcx, [rsp+790h+KeyInformation]; void *
0x180215a4b  call    memset_0
0x180215a50  mov     r10d, 15Fh
0x180215a56  lea     r9, [rbp+690h+var_300]
0x180215a5d  mov     r8d, r10d
0x180215a60  test    rbx, rbx
0x180215a63  jz      short loc_180215A82
0x180215a65  movzx   eax, word ptr [r15]
0x180215a69  test    ax, ax
0x180215a6c  jz      short loc_180215A82
0x180215a6e  mov     [r9], ax
0x180215a72  add     r15, 2
0x180215a76  add     r9, 2
0x180215a7a  sub     rbx, rdi
0x180215a7d  sub     r8, rdi
0x180215a80  jnz     short loc_180215A60
0x180215a82  mov     rax, r8
0x180215a85  lea     rdx, [r9-2]
0x180215a89  neg     rax
0x180215a8c  sbb     ecx, ecx
0x180215a8e  not     ecx
0x180215a90  and     ecx, r14d; Status
0x180215a93  test    r8, r8
0x180215a96  cmovnz  rdx, r9
0x180215a9a  mov     [rdx], r12w
0x180215a9e  jnz     short loc_180215AB8
0x180215aa0  call    cs:__imp_RtlNtStatusToDosError
0x180215aa6  lea     r9, aRtlstringcchco_3; "RtlStringCchCopyW failed to copy instal"...
0x180215aad  mov     r8d, 237h
0x180215ab3  jmp     loc_1802159FB
0x180215ab8  lea     r8, SubBlock; "\\"
0x180215abf  mov     rdx, r10; unsigned __int64
0x180215ac2  lea     rcx, [rbp+690h+var_300]; unsigned __int16 *
0x180215ac9  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180215ace  test    eax, eax
0x180215ad0  jns     short loc_180215AEC
0x180215ad2  mov     ecx, eax; Status
0x180215ad4  call    cs:__imp_RtlNtStatusToDosError
0x180215ada  lea     r9, aRtlstringcchca_2; "RtlStringCchCatW failed to append path "...
0x180215ae1  mov     r8d, 23Fh
0x180215ae7  jmp     loc_1802159FB
0x180215aec  lea     r8, [rbp+690h+String2]; unsigned __int16 *
0x180215af3  mov     edx, 15Fh; unsigned __int64
0x180215af8  lea     rcx, [rbp+690h+var_300]; unsigned __int16 *
0x180215aff  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180215b04  test    eax, eax
0x180215b06  jns     short loc_180215B22
0x180215b08  mov     ecx, eax; Status
0x180215b0a  call    cs:__imp_RtlNtStatusToDosError
0x180215b10  lea     r9, aRtlstringcchca_0; "RtlStringCchCatW failed to append key n"...
0x180215b17  mov     r8d, 247h
0x180215b1d  jmp     loc_1802159FB
0x180215b22  mov     r8d, 80000100h
0x180215b28  lea     rdx, [rbp+690h+var_300]
0x180215b2f  lea     rcx, [rsp+790h+KeyHandle]
0x180215b34  call    AslRegistryOpenKey
0x180215b39  test    eax, eax
0x180215b3b  jns     short loc_180215B57
0x180215b3d  mov     ecx, eax; Status
0x180215b3f  call    cs:__imp_RtlNtStatusToDosError
0x180215b45  lea     r9, aFailedToOpenIn; "Failed to open InstalledSDB child key ("...
0x180215b4c  mov     r8d, 24Fh
0x180215b52  jmp     loc_1802159FB
0x180215b57  mov     rcx, gs:60h
0x180215b60  mov     r15d, 48h ; 'H'
0x180215b66  mov     r8d, r15d; Size
0x180215b69  mov     rcx, [rcx+30h]; HeapHandle
0x180215b6d  lea     ebx, [r15-40h]
0x180215b71  mov     edx, ebx; Flags
0x180215b73  call    cs:__imp_RtlAllocateHeap
0x180215b79  mov     r14, rax
0x180215b7c  test    rax, rax
0x180215b7f  jnz     short loc_180215BA1
0x180215b81  lea     r9, aFailedToAlloca; "Failed to allocate registration info"
0x180215b88  mov     r8d, 25Ah
0x180215b8e  lea     rdx, aSdbcustomdbreg; "SdbCustomDbRegInfoEnumerate"
0x180215b95  mov     ecx, edi
0x180215b97  call    AslLogCallPrintf
0x180215b9c  jmp     loc_180215E52
0x180215ba1  lea     rcx, [rax+8]
0x180215ba5  mov     [rax], r15d
0x180215ba8  lea     rdx, [rbp+690h+var_300]
0x180215baf  mov     [rsp+790h+var_750], r14
0x180215bb4  call    AslStringDuplicate
0x180215bb9  test    eax, eax
0x180215bbb  jns     short loc_180215BD7
0x180215bbd  mov     ecx, eax; Status
0x180215bbf  call    cs:__imp_RtlNtStatusToDosError
0x180215bc5  lea     r9, aFailedToDuplic_5; "Failed to duplicate reg key path string"...
0x180215bcc  mov     r8d, 265h
0x180215bd2  jmp     loc_180215A30
0x180215bd7  lea     rcx, [r14+10h]; Guid
0x180215bdb  lea     rdx, [rbp+690h+String2]
0x180215be2  call    AslGuidFromString
0x180215be7  test    eax, eax
0x180215be9  jns     short loc_180215C05
0x180215beb  mov     ecx, eax; Status
0x180215bed  call    cs:__imp_RtlNtStatusToDosError
0x180215bf3  lea     r9, aFailedToGetSdb_1; "Failed to get SDB Guid from Key name (i"...
0x180215bfa  mov     r8d, 270h
0x180215c00  jmp     loc_1802159FB
0x180215c05  mov     rdx, [rsp+790h+KeyHandle]
0x180215c0a  lea     rsi, aDatabasepath; "DatabasePath"
0x180215c11  mov     r8, rsi
0x180215c14  lea     rcx, [r14+20h]
0x180215c18  mov     r15d, r12d
0x180215c1b  call    AslRegistryGetString
0x180215c20  test    eax, eax
0x180215c22  jns     short loc_180215C56
0x180215c24  mov     ecx, eax; Status
0x180215c26  call    cs:__imp_RtlNtStatusToDosError
0x180215c2c  mov     dword ptr [rsp+790h+ResultLength], eax
0x180215c30  lea     r9, aFailedTryingTo; "Failed trying to query value \"%ws\" [%"...
0x180215c37  mov     r8d, 27Fh
0x180215c3d  mov     qword ptr [rsp+790h+Length], rsi
0x180215c42  lea     rdx, aSdbcustomdbreg; "SdbCustomDbRegInfoEnumerate"
0x180215c49  mov     ecx, edi
0x180215c4b  call    AslLogCallPrintf
0x180215c50  mov     r15d, 6
0x180215c56  mov     rdx, [rsp+790h+KeyHandle]
0x180215c5b  lea     rsi, aDatabasedescri; "DatabaseDescription"
0x180215c62  mov     r8, rsi
0x180215c65  lea     rcx, [r14+30h]
0x180215c69  call    AslRegistryGetString
0x180215c6e  test    eax, eax
0x180215c70  jns     short loc_180215CA2
0x180215c72  mov     ecx, eax; Status
0x180215c74  call    cs:__imp_RtlNtStatusToDosError
0x180215c7a  mov     dword ptr [rsp+790h+ResultLength], eax
0x180215c7e  lea     r9, aFailedTryingTo; "Failed trying to query value \"%ws\" [%"...
0x180215c85  mov     r8d, 28Bh
0x180215c8b  mov     qword ptr [rsp+790h+Length], rsi
0x180215c90  lea     rdx, aSdbcustomdbreg; "SdbCustomDbRegInfoEnumerate"
0x180215c97  mov     ecx, edi
0x180215c99  call    AslLogCallPrintf
0x180215c9e  or      r15d, 2
0x180215ca2  mov     rdx, [rsp+790h+KeyHandle]
0x180215ca7  lea     rsi, aDatabasetype; "DatabaseType"
0x180215cae  mov     r8, rsi
0x180215cb1  lea     rcx, [r14+38h]
0x180215cb5  call    AslRegistryGetUInt32
0x180215cba  test    eax, eax
0x180215cbc  jns     short loc_180215CEE
0x180215cbe  mov     ecx, eax; Status
0x180215cc0  call    cs:__imp_RtlNtStatusToDosError
0x180215cc6  mov     dword ptr [rsp+790h+ResultLength], eax
0x180215cca  lea     r9, aFailedTryingTo; "Failed trying to query value \"%ws\" [%"...
0x180215cd1  mov     r8d, 296h
  ... truncated ...
```
