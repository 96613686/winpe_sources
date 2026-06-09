# CPenProcess::StaticWatchDogThreadProc(void *)

- ea: `0x180003170`
- end: `0x1800037bd`
- name: `?StaticWatchDogThreadProc@CPenProcess@@CAKPEAX@Z`
- size: `1613`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003170`
- `0x1800037d0`
- `0x18001bbe0`
- `0x18001c684`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002b4cc`
- `0x18002e5f0`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800035df`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800035df`
- `ntdll!RtlInitUnicodeString` at `0x180003356`
- `ntdll!RtlInitUnicodeString` at `0x1800033c7`
- `ntdll!RtlInitUnicodeString` at `0x180003356`
- `ntdll!RtlInitUnicodeString` at `0x1800033c7`
- `ntdll!NtClose` at `0x180003424`
- `ntdll!NtClose` at `0x180003424`
- `ntdll!NtOpenDirectoryObject` at `0x18000338d`
- `ntdll!NtOpenDirectoryObject` at `0x18000338d`
- `ntdll!NtOpenMutant` at `0x1800033fc`
- `ntdll!NtOpenMutant` at `0x1800033fc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003612`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003612`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003592`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003592`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003475`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003624`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003475`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003624`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180003605`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180003605`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000359b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000359b`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180003587`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180003587`

## string_xrefs

- `0x1800034d6`: `PENSERVICE_CPenProcess::OpenProcessMutexInSession`
- `0x18000353c`: `PENSERVICE_CPenProcess::OpenProcessMutexInSession`
- `0x1800036d9`: `PENSERVICE_CPenProcess::OpenProcessMutexInSession`
- `0x180003689`: `PENSERVICE_CPenProcess::StaticWatchDogThreadProc`
- `0x1800036b1`: `PENSERVICE_CPenProcess::StaticWatchDogThreadProc`
- `0x180003730`: `PENSERVICE__OpenSessionDirectory`
- `0x180003772`: `PENSERVICE__OpenSessionDirectory`
- `0x1800034a8`: `PENSERVICE_OpenMutexInSession`
- `0x180003501`: `PENSERVICE_OpenMutexInSession`
- `0x1800036fa`: `PENSERVICE_OpenMutexInSession`
- `0x180003797`: `PENSERVICE_OpenMutexInSession`

## pseudocode

```c
__int64 __fastcall CPenProcess::StaticWatchDogThreadProc(_QWORD *Parameter)
{
  bool v1; // si
  char v3; // r14
  struct _GUID *v4; // rcx
  __int64 v5; // rcx
  wchar_t v6; // ax
  bool v7; // cf
  wchar_t v8; // ax
  int v9; // edi
  __int64 v10; // rcx
  const wchar_t *v11; // rdx
  __int64 v12; // r9
  WCHAR *v13; // r8
  WCHAR *v14; // rcx
  int v15; // ebx
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  unsigned int v18; // ebx
  struct _GUID *v19; // rdi
  NTSTATUS v20; // eax
  struct _GUID *v21; // rcx
  void *v22; // rbx
  NTSTATUS v23; // eax
  int v24; // r8d
  void *v25; // rbx
  DWORD v26; // edi
  DWORD v27; // edi
  DWORD v28; // edi
  int v29; // ebx
  int v30; // edi
  struct _SLIST_ENTRY *v31; // rax
  __int64 v33; // [rsp+28h] [rbp-D8h]
  void *MutantHandle; // [rsp+30h] [rbp-D0h] BYREF
  void *FileHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v37; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES v40; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR SourceString[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR v42[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v1 = 0;
  v3 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      39,
      WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      "PENSERVICE_CPenProcess::StaticWatchDogThreadProc");
    v4 = WPP_GLOBAL_Control;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v4 != (struct _GUID *)&WPP_GLOBAL_Control && (v4[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&v4[1].Data1,
          35,
          WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
          "PENSERVICE_CPenProcess::OpenProcessMutexInSession");
      v5 = -1;
      while ( 1 )
      {
        v6 = *((_WORD *)Parameter + v5 + 280);
        v7 = v6 < aWinlogon[v5 + 1];
        if ( v6 != aWinlogon[v5 + 1] )
        {
LABEL_9:
          v9 = v7 ? -1 : 1;
          goto LABEL_18;
        }
        v5 += 2;
        if ( v5 == 9 )
          break;
        v8 = *((_WORD *)Parameter + v5 + 279);
        v7 = v8 < aWinlogon[v5];
        if ( v8 != aWinlogon[v5] )
          goto LABEL_9;
      }
      v9 = 0;
LABEL_18:
      memset_0(v42, 0, 0x208u);
      v15 = *((_DWORD *)Parameter + 8);
      v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*Parameter + 32LL))(*Parameter);
      LODWORD(v33) = v15;
      v17 = L"Winlogon";
      if ( v9 )
        v17 = L"Default";
      StringCchPrintfW(v42, 0x104u, L"%s%s%d", v16, v17, v33);
      v18 = *((_DWORD *)Parameter + 8);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      {
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          12,
          WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
          "PENSERVICE_OpenMutexInSession");
        v19 = WPP_GLOBAL_Control;
      }
      MutantHandle = 0;
      FileHandle = 0;
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      memset_0(SourceString, 0, 0x208u);
      if ( v18 )
      {
        StringCchPrintfW(SourceString, 0x104u, L"\\Sessions\\%d\\BaseNamedObjects", v18);
        v19 = WPP_GLOBAL_Control;
      }
      else
      {
        v10 = 2147483646;
        v11 = L"\\BaseNamedObjects";
        v12 = 260;
        v13 = SourceString;
        do
        {
          if ( !v10 )
            break;
          if ( !*v11 )
            break;
          *v13++ = *v11++;
          --v10;
          --v12;
        }
        while ( v12 );
        v14 = v13 - 1;
        if ( v12 )
          v14 = v13;
        *v14 = 0;
      }
      if ( v19 != (struct _GUID *)&WPP_GLOBAL_Control && (v19[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sS(
          *(_QWORD *)&v19[1].Data1,
          10,
          (unsigned int)WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
          (unsigned int)"PENSERVICE__OpenSessionDirectory",
          (__int64)SourceString);
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v20 = NtOpenDirectoryObject(&FileHandle, 4u, &ObjectAttributes);
      if ( v20 >= 0 )
        goto LABEL_29;
      FileHandle = 0;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
      {
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          11,
          (unsigned int)WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
          (unsigned int)"PENSERVICE__OpenSessionDirectory",
          v20);
LABEL_29:
        v21 = WPP_GLOBAL_Control;
      }
      v22 = FileHandle;
      if ( FileHandle )
      {
        v37 = 0;
        RtlInitUnicodeString(&v37, v42);
        *(_QWORD *)&v40.Length = 48;
        v40.ObjectName = &v37;
        memset(&v40.Attributes, 0, 24);
        v40.RootDirectory = v22;
        v23 = NtOpenMutant(&MutantHandle, 0x100000u, &v40);
        if ( v23 < 0 )
        {
          if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
            WPP_SF_sSd(
              *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
              13,
              v24,
              (unsigned int)"PENSERVICE_OpenMutexInSession",
              (__int64)v42,
              v23);
          MutantHandle = 0;
        }
        NtClose(v22);
        v21 = WPP_GLOBAL_Control;
      }
      if ( !MutantHandle )
      {
        if ( v21 == (struct _GUID *)&WPP_GLOBAL_Control )
          goto LABEL_39;
        if ( (v21[1].Data4[4] & 4) != 0 )
        {
          WPP_SF_s(
            *(_QWORD *)&v21[1].Data1,
            14,
            WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
            "PENSERVICE_OpenMutexInSession");
          v21 = WPP_GLOBAL_Control;
        }
      }
      if ( v21 != (struct _GUID *)&WPP_GLOBAL_Control && (v21[1].Data4[4] & 0x10) != 0 )
      {
        WPP_SF_s(
          *(_QWORD *)&v21[1].Data1,
          15,
          WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
          "PENSERVICE_OpenMutexInSession");
        v21 = WPP_GLOBAL_Control;
      }
LABEL_39:
      v25 = MutantHandle;
      if ( MutantHandle )
        goto LABEL_40;
      if ( v21 == (struct _GUID *)&WPP_GLOBAL_Control )
        break;
      if ( (v21[1].Data4[4] & 4) != 0 )
      {
        WPP_SF_s(
          *(_QWORD *)&v21[1].Data1,
          36,
          WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
          "PENSERVICE_CPenProcess::OpenProcessMutexInSession");
        v21 = WPP_GLOBAL_Control;
      }
LABEL_40:
      if ( v21 != (struct _GUID *)&WPP_GLOBAL_Control && (v21[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&v21[1].Data1,
          37,
          WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
          "PENSERVICE_CPenProcess::OpenProcessMutexInSession");
      if ( !v25 )
        break;
      Handles[0] = *((HANDLE *)Parameter + 142);
      Handles[1] = v25;
      v3 = 0;
      v26 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      ReleaseMutex(v25);
      CloseHandle(v25);
      if ( !v26 )
        goto LABEL_66;
      v27 = v26 - 1;
      if ( !v27 )
        goto LABEL_62;
      v28 = v27 - 127;
      if ( !v28 )
        goto LABEL_66;
      if ( v28 == 1 )
        goto LABEL_62;
LABEL_44:
      if ( v1 )
        goto LABEL_66;
      v4 = WPP_GLOBAL_Control;
    }
    if ( !v3 )
    {
      v3 = 1;
      v1 = WaitForSingleObject((HANDLE)Parameter[142], 0x1388u) != 258;
      goto LABEL_44;
    }
    v3 = 0;
LABEL_62:
    v29 = *((_DWORD *)Parameter + 8);
    v30 = *(_DWORD *)(*Parameter + 8LL);
    v31 = (struct _SLIST_ENTRY *)_aligned_malloc(0x30u, 0x10u);
    if ( v31 )
    {
      LODWORD(v31[1].Next) = 130;
      HIDWORD(v31[1].Next) = v30;
      *((_DWORD *)&v31[1].Next + 2) = v29;
      v31[2].Next = 0;
      InterlockedPushEntrySList(&ListHead, v31);
      SetEvent(hEvent);
    }
    if ( WaitForSingleObject((HANDLE)Parameter[142], 0x1388u) != 258 )
      break;
    v4 = WPP_GLOBAL_Control;
    v1 = 0;
  }
LABEL_66:
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      40,
      WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      "PENSERVICE_CPenProcess::StaticWatchDogThreadProc");
  return 0;
}

```

## disassembly

```asm
0x180003170  push    rbp
0x180003172  push    rbx
0x180003173  push    rsi
0x180003174  push    rdi
0x180003175  push    r12
0x180003177  push    r13
0x180003179  push    r14
0x18000317b  push    r15
0x18000317d  lea     rbp, [rsp-408h]
0x180003185  sub     rsp, 508h
0x18000318c  mov     rax, cs:__security_cookie
0x180003193  xor     rax, rsp
0x180003196  mov     [rbp+440h+var_50], rax
0x18000319d  xor     sil, sil
0x1800031a0  mov     r15, rcx
0x1800031a3  xor     r14b, r14b
0x1800031a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031ad  lea     rdi, WPP_GLOBAL_Control
0x1800031b4  cmp     rcx, rdi
0x1800031b7  jnz     loc_1800036A3
0x1800031bd  lea     r12, aWinlogon; "Winlogon"
0x1800031c4  xor     r13d, r13d
0x1800031c7  cmp     rcx, rdi
0x1800031ca  jz      short loc_1800031D6
0x1800031cc  test    byte ptr [rcx+1Ch], 10h
0x1800031d0  jnz     loc_1800036D5
0x1800031d6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800031dd  nop     dword ptr [rax]
0x1800031e0  movzx   eax, word ptr [r15+rcx*2+230h]
0x1800031e9  cmp     ax, [r12+rcx*2+2]
0x1800031ef  jnz     short loc_18000320B
0x1800031f1  add     rcx, 2
0x1800031f5  cmp     rcx, 9
0x1800031f9  jz      short loc_18000325E
0x1800031fb  movzx   eax, word ptr [r15+rcx*2+22Eh]
0x180003204  cmp     ax, [r12+rcx*2]
0x180003209  jz      short loc_1800031E0
0x18000320b  sbb     edi, edi
0x18000320d  or      edi, 1
0x180003210  jmp     short loc_180003261
0x180003212  mov     ecx, 7FFFFFFEh
0x180003217  lea     rdx, aBasenamedobjec; "\\BaseNamedObjects"
0x18000321e  mov     r9d, 104h
0x180003224  lea     r8, [rbp+440h+SourceString]
0x180003228  test    rcx, rcx
0x18000322b  jz      short loc_18000324A
0x18000322d  movzx   eax, word ptr [rdx]
0x180003230  test    ax, ax
0x180003233  jz      short loc_18000324A
0x180003235  mov     [r8], ax
0x180003239  add     rdx, 2
0x18000323d  add     r8, 2
0x180003241  dec     rcx
0x180003244  sub     r9, 1
0x180003248  jnz     short loc_180003228
0x18000324a  test    r9, r9
0x18000324d  lea     rcx, [r8-2]
0x180003251  cmovnz  rcx, r8
0x180003255  mov     [rcx], r13w
0x180003259  jmp     loc_18000332F
0x18000325e  mov     edi, r13d
0x180003261  xor     edx, edx; Val
0x180003263  lea     rcx, [rbp+440h+var_260]; void *
0x18000326a  mov     r8d, 208h; Size
0x180003270  call    memset_0
0x180003275  mov     rcx, [r15]
0x180003278  mov     ebx, [r15+20h]
0x18000327c  mov     rax, [rcx]
0x18000327f  mov     rax, [rax+20h]
0x180003283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003288  test    edi, edi
0x18000328a  mov     dword ptr [rsp+540h+var_518], ebx
0x18000328e  lea     rdx, aDefault; "Default"
0x180003295  mov     rcx, r12
0x180003298  cmovnz  rcx, rdx
0x18000329c  lea     r8, aSSD; "%s%s%d"
0x1800032a3  mov     [rsp+540h+var_520], rcx
0x1800032a8  mov     r9, rax
0x1800032ab  lea     rcx, [rbp+440h+var_260]; unsigned __int16 *
0x1800032b2  mov     edx, 104h; unsigned __int64
0x1800032b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800032bc  mov     ebx, [r15+20h]
0x1800032c0  mov     rdi, cs:WPP_GLOBAL_Control
0x1800032c7  lea     rax, WPP_GLOBAL_Control
0x1800032ce  cmp     rdi, rax
0x1800032d1  jz      short loc_1800032DD
0x1800032d3  test    byte ptr [rdi+1Ch], 10h
0x1800032d7  jnz     loc_1800036F6
0x1800032dd  xorps   xmm0, xmm0
0x1800032e0  mov     [rsp+540h+MutantHandle], r13
0x1800032e5  xor     edx, edx; Val
0x1800032e7  mov     [rsp+540h+FileHandle], r13
0x1800032ec  mov     r8d, 208h; Size
0x1800032f2  lea     rcx, [rbp+440h+SourceString]; void *
0x1800032f6  movups  xmmword ptr [rsp+540h+ObjectAttributes.Length], xmm0
0x1800032fb  movups  xmmword ptr [rbp+440h+ObjectAttributes.ObjectName], xmm0
0x1800032ff  movups  xmmword ptr [rbp+440h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003303  call    memset_0
0x180003308  test    ebx, ebx
0x18000330a  jz      loc_180003212
0x180003310  mov     r9d, ebx
0x180003313  lea     r8, aSessionsDBasen; "\\Sessions\\%d\\BaseNamedObjects"
0x18000331a  mov     edx, 104h; unsigned __int64
0x18000331f  lea     rcx, [rbp+440h+SourceString]; unsigned __int16 *
0x180003323  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003328  mov     rdi, cs:WPP_GLOBAL_Control
0x18000332f  lea     rax, WPP_GLOBAL_Control
0x180003336  cmp     rdi, rax
0x180003339  jz      short loc_180003345
0x18000333b  test    byte ptr [rdi+1Ch], 10h
0x18000333f  jnz     loc_18000371E
0x180003345  xorps   xmm0, xmm0
0x180003348  lea     rdx, [rbp+440h+SourceString]; SourceString
0x18000334c  lea     rcx, [rsp+540h+DestinationString]; DestinationString
0x180003351  movups  xmmword ptr [rsp+540h+DestinationString.Length], xmm0
0x180003356  call    cs:__imp_RtlInitUnicodeString
0x18000335c  lea     rax, [rsp+540h+DestinationString]
0x180003361  mov     [rsp+540h+ObjectAttributes.Length], 30h ; '0'
0x180003369  xorps   xmm0, xmm0
0x18000336c  mov     [rbp+440h+ObjectAttributes.ObjectName], rax
0x180003370  lea     r8, [rsp+540h+ObjectAttributes]; ObjectAttributes
0x180003375  mov     [rsp+540h+ObjectAttributes.RootDirectory], r13
0x18000337a  mov     edx, 4; DesiredAccess
0x18000337f  mov     [rbp+440h+ObjectAttributes.Attributes], r13d
0x180003383  lea     rcx, [rsp+540h+FileHandle]; FileHandle
0x180003388  movdqu  xmmword ptr [rbp+440h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000338d  call    cs:__imp_NtOpenDirectoryObject
0x180003393  test    eax, eax
0x180003395  js      loc_180003748
0x18000339b  lea     rdi, WPP_GLOBAL_Control
0x1800033a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033a9  mov     rbx, [rsp+540h+FileHandle]
0x1800033ae  test    rbx, rbx
0x1800033b1  jz      short loc_180003431
0x1800033b3  xorps   xmm0, xmm0
0x1800033b6  lea     rdx, [rbp+440h+var_260]; SourceString
0x1800033bd  lea     rcx, [rsp+540h+var_4F0]; DestinationString
0x1800033c2  movups  xmmword ptr [rsp+540h+var_4F0.Length], xmm0
0x1800033c7  call    cs:__imp_RtlInitUnicodeString
0x1800033cd  lea     rax, [rsp+540h+var_4F0]
0x1800033d2  mov     qword ptr [rbp+440h+var_4A0.Length], 30h ; '0'
0x1800033da  xorps   xmm0, xmm0
0x1800033dd  mov     [rbp+440h+var_4A0.ObjectName], rax
0x1800033e1  lea     r8, [rbp+440h+var_4A0]; ObjectAttributes
0x1800033e5  mov     qword ptr [rbp+440h+var_4A0.Attributes], r13
0x1800033e9  mov     edx, 100000h; DesiredAccess
0x1800033ee  mov     [rbp+440h+var_4A0.RootDirectory], rbx
0x1800033f2  lea     rcx, [rsp+540h+MutantHandle]; MutantHandle
0x1800033f7  movdqu  xmmword ptr [rbp+440h+var_4A0.SecurityDescriptor], xmm0
0x1800033fc  call    cs:__imp_NtOpenMutant
0x180003402  test    eax, eax
0x180003404  jns     short loc_180003421
0x180003406  mov     rcx, cs:WPP_GLOBAL_Control
0x18000340d  cmp     rcx, rdi
0x180003410  jz      short loc_18000341C
0x180003412  test    byte ptr [rcx+1Ch], 4
0x180003416  jnz     loc_180003793
0x18000341c  mov     [rsp+540h+MutantHandle], r13
0x180003421  mov     rcx, rbx; Handle
0x180003424  call    cs:__imp_NtClose
0x18000342a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003431  cmp     [rsp+540h+MutantHandle], r13
0x180003436  jz      short loc_180003499
0x180003438  cmp     rcx, rdi
0x18000343b  jnz     loc_1800034F3
0x180003441  mov     rbx, [rsp+540h+MutantHandle]
0x180003446  test    rbx, rbx
0x180003449  jz      loc_180003525
0x18000344f  cmp     rcx, rdi
0x180003452  jnz     short loc_1800034CC
0x180003454  test    rbx, rbx
0x180003457  jnz     loc_180003560
0x18000345d  test    r14b, r14b
0x180003460  jnz     loc_1800035C8
0x180003466  mov     rcx, [r15+470h]; hHandle
0x18000346d  mov     edx, 1388h; dwMilliseconds
0x180003472  mov     r14b, 1
0x180003475  call    cs:__imp_WaitForSingleObject
0x18000347b  cmp     eax, 102h
0x180003480  setnz   sil
0x180003484  test    sil, sil
0x180003487  jnz     loc_180003647
0x18000348d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003494  jmp     loc_1800031C7
0x180003499  cmp     rcx, rdi
0x18000349c  jz      short loc_180003441
0x18000349e  test    byte ptr [rcx+1Ch], 4
0x1800034a2  jz      short loc_180003438
0x1800034a4  mov     rcx, [rcx+10h]
0x1800034a8  lea     r9, aPenserviceOpen_1; "PENSERVICE_OpenMutexInSession"
0x1800034af  mov     edx, 0Eh
0x1800034b4  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x1800034bb  call    WPP_SF_s
0x1800034c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034c7  jmp     loc_180003438
0x1800034cc  test    byte ptr [rcx+1Ch], 10h
0x1800034d0  jz      short loc_180003454
0x1800034d2  mov     rcx, [rcx+10h]
0x1800034d6  lea     r9, aPenserviceCpen_3; "PENSERVICE_CPenProcess::OpenProcessMute"...
0x1800034dd  mov     edx, 25h ; '%'
0x1800034e2  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x1800034e9  call    WPP_SF_s
0x1800034ee  jmp     loc_180003454
0x1800034f3  test    byte ptr [rcx+1Ch], 10h
0x1800034f7  jz      loc_180003441
0x1800034fd  mov     rcx, [rcx+10h]
0x180003501  lea     r9, aPenserviceOpen_1; "PENSERVICE_OpenMutexInSession"
0x180003508  mov     edx, 0Fh
0x18000350d  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x180003514  call    WPP_SF_s
0x180003519  mov     rcx, cs:WPP_GLOBAL_Control
0x180003520  jmp     loc_180003441
0x180003525  cmp     rcx, rdi
0x180003528  jz      loc_18000345D
0x18000352e  test    byte ptr [rcx+1Ch], 4
0x180003532  jz      loc_18000344F
0x180003538  mov     rcx, [rcx+10h]
0x18000353c  lea     r9, aPenserviceCpen_3; "PENSERVICE_CPenProcess::OpenProcessMute"...
0x180003543  mov     edx, 24h ; '$'
0x180003548  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18000354f  call    WPP_SF_s
0x180003554  mov     rcx, cs:WPP_GLOBAL_Control
0x18000355b  jmp     loc_18000344F
0x180003560  mov     rax, [r15+470h]
0x180003567  lea     rdx, [rsp+540h+Handles]; lpHandles
0x18000356c  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180003572  mov     [rsp+540h+Handles], rax
0x180003577  xor     r8d, r8d; bWaitAll
0x18000357a  mov     [rsp+540h+var_4D8], rbx
0x18000357f  mov     ecx, 2; nCount
0x180003584  xor     r14b, r14b
0x180003587  call    cs:__imp_WaitForMultipleObjects
0x18000358d  mov     rcx, rbx; hMutex
0x180003590  mov     edi, eax
0x180003592  call    cs:__imp_ReleaseMutex
0x180003598  mov     rcx, rbx; hObject
0x18000359b  call    cs:__imp_CloseHandle
0x1800035a1  test    edi, edi
0x1800035a3  jz      loc_180003647
0x1800035a9  sub     edi, 1
0x1800035ac  jz      short loc_1800035CB
0x1800035ae  sub     edi, 7Fh
0x1800035b1  jz      loc_180003647
0x1800035b7  cmp     edi, 1
0x1800035ba  jz      short loc_1800035CB
0x1800035bc  lea     rdi, WPP_GLOBAL_Control
0x1800035c3  jmp     loc_180003484
0x1800035c8  xor     r14b, r14b
0x1800035cb  mov     rax, [r15]
0x1800035ce  mov     edx, 10h; Alignment
0x1800035d3  mov     ebx, [r15+20h]
0x1800035d7  mov     ecx, 30h ; '0'; Size
0x1800035dc  mov     edi, [rax+8]
0x1800035df  call    cs:__imp__aligned_malloc
0x1800035e5  test    rax, rax
0x1800035e8  jz      short loc_180003618
0x1800035ea  mov     rdx, rax; ListEntry
0x1800035ed  mov     dword ptr [rax+10h], 82h
0x1800035f4  lea     rcx, ListHead; ListHead
0x1800035fb  mov     [rax+14h], edi
0x1800035fe  mov     [rax+18h], ebx
0x180003601  mov     [rax+20h], r13
0x180003605  call    cs:__imp_InterlockedPushEntrySList
0x18000360b  mov     rcx, cs:hEvent; hEvent
0x180003612  call    cs:__imp_SetEvent
0x180003618  mov     rcx, [r15+470h]; hHandle
0x18000361f  mov     edx, 1388h; dwMilliseconds
0x180003624  call    cs:__imp_WaitForSingleObject
0x18000362a  cmp     eax, 102h
0x18000362f  jnz     short loc_180003647
0x180003631  mov     rcx, cs:WPP_GLOBAL_Control
0x180003638  lea     rdi, WPP_GLOBAL_Control
0x18000363f  xor     sil, sil
0x180003642  jmp     loc_1800031C7
0x180003647  mov     rcx, cs:WPP_GLOBAL_Control
0x18000364e  lea     rax, WPP_GLOBAL_Control
0x180003655  cmp     rcx, rax
0x180003658  jnz     short loc_18000367F
0x18000365a  xor     eax, eax
0x18000365c  mov     rcx, [rbp+440h+var_50]
0x180003663  xor     rcx, rsp; StackCookie
0x180003666  call    __security_check_cookie
0x18000366b  add     rsp, 508h
0x180003672  pop     r15
0x180003674  pop     r14
0x180003676  pop     r13
0x180003678  pop     r12
0x18000367a  pop     rdi
0x18000367b  pop     rsi
0x18000367c  pop     rbx
0x18000367d  pop     rbp
0x18000367e  retn
0x18000367f  test    byte ptr [rcx+1Ch], 10h
0x180003683  jz      short loc_18000365A
0x180003685  mov     rcx, [rcx+10h]
0x180003689  lea     r9, aPenserviceCpen; "PENSERVICE_CPenProcess::StaticWatchDogT"...
0x180003690  mov     edx, 28h ; '('
0x180003695  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18000369c  call    WPP_SF_s
0x1800036a1  jmp     short loc_18000365A
  ... truncated ...
```
