# LoadStringByReference

- ea: `0x1800c3400`
- end: `0x1800c3f15`
- name: `LoadStringByReference`
- size: `2837`
- prototype: `BOOL __stdcall(DWORD Flags, PCWSTR Language, PCWSTR SourceString, PWSTR Buffer, ULONG cchBuffer, PCWSTR Directory, PULONG pcchBufferOut)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001eec0`
- `0x1800c2ec0`
- `0x1800c3210`

## callees

- `0x1800145c0`
- `0x1800147a0`
- `0x18006fad0`
- `0x18006fd7c`
- `0x180077680`
- `0x1800a4090`
- `0x1800c3400`
- `0x1800d7ff0`
- `0x1800d9360`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800c3650`
- `ntdll!RtlInitUnicodeString` at `0x1800c366e`
- `ntdll!RtlInitUnicodeString` at `0x1800c3650`
- `ntdll!RtlInitUnicodeString` at `0x1800c366e`
- `ntdll!_wcsnicmp` at `0x1800c382a`
- `ntdll!_wcsnicmp` at `0x1800c382a`
- `ntdll!RtlSetLastWin32Error` at `0x1800c3895`
- `ntdll!RtlSetLastWin32Error` at `0x1800c3ece`
- `ntdll!RtlSetLastWin32Error` at `0x1800c3eea`
- `ntdll!RtlSetLastWin32Error` at `0x1800c3895`
- `ntdll!RtlSetLastWin32Error` at `0x1800c3ece`
- `ntdll!RtlSetLastWin32Error` at `0x1800c3eea`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3550`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3873`
- `ntdll!RtlNtStatusToDosError` at `0x1800c39ba`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3a0f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3adc`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3b85`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3bdc`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3c00`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3d1a`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3550`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3873`
- `ntdll!RtlNtStatusToDosError` at `0x1800c39ba`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3a0f`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3adc`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3b85`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3bdc`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3c00`
- `ntdll!RtlNtStatusToDosError` at `0x1800c3d1a`
- `ntdll!RtlUnicodeStringToInteger` at `0x1800c3ad0`
- `ntdll!RtlUnicodeStringToInteger` at `0x1800c3ad0`
- `ntdll!RtlLocaleNameToLcid` at `0x1800c352b`
- `ntdll!RtlLocaleNameToLcid` at `0x1800c352b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800c3796`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x1800c3796`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800c3727`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800c3727`
- `ntdll!RtlLoadString` at `0x1800c3d08`
- `ntdll!RtlLoadString` at `0x1800c3d08`
- `ntdll!RtlAppendUnicodeToString` at `0x1800c3710`
- `ntdll!RtlAppendUnicodeToString` at `0x1800c3bd0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800c3bf4`
- `ntdll!RtlAppendUnicodeToString` at `0x1800c3710`
- `ntdll!RtlAppendUnicodeToString` at `0x1800c3bd0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800c3bf4`
- `ntdll!RtlCopyUnicodeString` at `0x1800c36fe`
- `ntdll!RtlCopyUnicodeString` at `0x1800c3bbb`
- `ntdll!RtlCopyUnicodeString` at `0x1800c36fe`
- `ntdll!RtlCopyUnicodeString` at `0x1800c3bbb`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800c3971`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800c3a03`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800c3971`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x1800c3a03`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800c3ab4`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800c3ab4`
- `ntdll!NtClose` at `0x1800c3eaa`
- `ntdll!NtClose` at `0x1800c3eaa`
- `ntdll!RtlFreeHeap` at `0x1800c375d`
- `ntdll!RtlFreeHeap` at `0x1800c3e0c`
- `ntdll!RtlFreeHeap` at `0x1800c3e43`
- `ntdll!RtlFreeHeap` at `0x1800c3e6b`
- `ntdll!RtlFreeHeap` at `0x1800c3e9a`
- `ntdll!RtlFreeHeap` at `0x1800c375d`
- `ntdll!RtlFreeHeap` at `0x1800c3e0c`
- `ntdll!RtlFreeHeap` at `0x1800c3e43`
- `ntdll!RtlFreeHeap` at `0x1800c3e6b`
- `ntdll!RtlFreeHeap` at `0x1800c3e9a`
- `ntdll!RtlAllocateHeap` at `0x1800c36cc`
- `ntdll!RtlAllocateHeap` at `0x1800c39a7`
- `ntdll!RtlAllocateHeap` at `0x1800c3b6d`
- `ntdll!RtlAllocateHeap` at `0x1800c3db8`
- `ntdll!RtlAllocateHeap` at `0x1800c36cc`
- `ntdll!RtlAllocateHeap` at `0x1800c39a7`
- `ntdll!RtlAllocateHeap` at `0x1800c3b6d`
- `ntdll!RtlAllocateHeap` at `0x1800c3db8`

## string_xrefs

- `0x1800c38ca`: `Software\Classes\Local Settings\ImmutableMuiCache`
- `0x1800c38c3`: `Software\Classes\Local Settings\MuiCache`

## pseudocode

```c
BOOL __stdcall LoadStringByReference(
        DWORD Flags,
        PCWSTR Language,
        PCWSTR SourceString,
        PWSTR Buffer,
        ULONG cchBuffer,
        PCWSTR Directory,
        PULONG pcchBufferOut)
{
  WCHAR *v10; // r13
  BOOL v11; // edi
  ULONG LastErrorValue; // ebx
  ULONG v13; // ecx
  __int64 v14; // rdx
  unsigned __int16 v15; // r8
  WCHAR v16; // r9
  int v17; // ecx
  WCHAR *v18; // rsi
  PCWSTR v19; // rax
  USHORT v20; // si
  int v21; // ebx
  int i; // edx
  int v23; // ecx
  const wchar_t *v24; // rcx
  int v25; // eax
  NTSTATUS v26; // ecx
  void *v27; // r12
  ULONG v28; // eax
  WCHAR *Heap; // rax
  int appended; // eax
  PWSTR v31; // r14
  int v32; // ebx
  PWSTR v33; // r15
  __int64 v34; // rdx
  int v35; // ecx
  const WCHAR *v36; // rdx
  int inited; // eax
  __int64 v38; // rax
  USHORT v39; // r14
  WCHAR *v40; // rax
  ULONG v41; // r12d
  void *v42; // r15
  HMODULE Library; // r14
  NTSTATUS v44; // eax
  __int64 v45; // r13
  unsigned int v46; // r14d
  int v47; // eax
  _WORD *v48; // rax
  _WORD *v49; // r15
  __int64 v51; // [rsp+40h] [rbp-348h] BYREF
  PCWSTR v52; // [rsp+48h] [rbp-340h]
  unsigned __int16 v53[2]; // [rsp+50h] [rbp-338h] BYREF
  ULONG Length; // [rsp+54h] [rbp-334h] BYREF
  DWORD v55; // [rsp+58h] [rbp-330h]
  unsigned int v56; // [rsp+5Ch] [rbp-32Ch] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-328h] BYREF
  unsigned int v58; // [rsp+68h] [rbp-320h] BYREF
  int v59; // [rsp+6Ch] [rbp-31Ch] BYREF
  ULONG Value; // [rsp+70h] [rbp-318h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+78h] [rbp-310h] BYREF
  PCWSTR SourceStringa; // [rsp+88h] [rbp-300h]
  void *v63; // [rsp+90h] [rbp-2F8h]
  HMODULE hLibModule; // [rsp+98h] [rbp-2F0h]
  struct _UNICODE_STRING v65; // [rsp+A0h] [rbp-2E8h] BYREF
  struct _UNICODE_STRING v66; // [rsp+B0h] [rbp-2D8h] BYREF
  int v67; // [rsp+C0h] [rbp-2C8h]
  int v68; // [rsp+C4h] [rbp-2C4h] BYREF
  void *Src; // [rsp+C8h] [rbp-2C0h] BYREF
  PCWSTR v70; // [rsp+D0h] [rbp-2B8h]
  PULONG v71; // [rsp+D8h] [rbp-2B0h]
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-2A8h] BYREF
  UNICODE_STRING v73; // [rsp+F0h] [rbp-298h] BYREF
  UNICODE_STRING String; // [rsp+100h] [rbp-288h] BYREF
  _BYTE v75[32]; // [rsp+110h] [rbp-278h] BYREF
  __int16 v76[264]; // [rsp+130h] [rbp-258h] BYREF

  v63 = Buffer;
  v70 = SourceString;
  LODWORD(v10) = Flags;
  v55 = Flags;
  hLibModule = (HMODULE)Language;
  v52 = SourceString;
  *(_QWORD *)&Destination.Length = Buffer;
  SourceStringa = Directory;
  v71 = pcchBufferOut;
  v11 = 0;
  Length = 0;
  Value = 0;
  LODWORD(v51) = 0;
  DestinationString = 0;
  v66 = 0;
  v73 = 0;
  v65 = 0;
  v53[0] = 0;
  Src = 0;
  v56 = 0;
  Handle = 0;
  v58 = 0;
  v59 = 260;
  v68 = 0;
  if ( !SourceString || !Buffer && (!pcchBufferOut || cchBuffer) || (Flags & 3) == 3 || (Flags & 0xFFFFFFE0) != 0 )
  {
    v13 = 87;
    goto LABEL_148;
  }
  LastErrorValue = 0;
  if ( Language )
  {
    if ( (int)RtlLocaleNameToLcid(Language, &v56, 3) >= 0 )
    {
      v56 = (unsigned __int16)v56;
    }
    else
    {
      LastErrorValue = 87;
      v67 = 87;
    }
  }
  if ( LastErrorValue )
  {
    v13 = LastErrorValue;
LABEL_148:
    RtlSetLastWin32Error(v13);
    return 0;
  }
  if ( *SourceString != 64 )
    goto LABEL_146;
  LODWORD(v14) = 0;
  v15 = 1;
  v16 = SourceString[1];
  if ( v16 )
  {
    do
    {
      v17 = v15;
      if ( SourceString[v15] != 44 )
        v17 = v14;
      LODWORD(v14) = v17;
      ++v15;
    }
    while ( SourceString[v15] );
  }
  if ( (_DWORD)v14 )
  {
    if ( SourceString[(unsigned int)v14] != 44
      || SourceString[(unsigned int)(v14 - 1)] == 34 && v16 != 34
      || ((unsigned __int8)v10 & 2) == 0 && (v14 = (unsigned int)(v14 + 1), SourceString[v14] != 45)
      || (unsigned __int16)(SourceString[(unsigned int)(v14 + 1)] - 48) > 9u )
    {
LABEL_146:
      v13 = 13;
      goto LABEL_148;
    }
  }
  v18 = 0;
  v52 = 0;
  hLibModule = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v19 = SourceStringa;
  if ( SourceStringa )
  {
    RtlInitUnicodeString(&v73, SourceStringa);
    v19 = SourceStringa;
  }
  if ( ((unsigned __int8)v10 & 8) != 0 || Language )
    goto LABEL_69;
  if ( v19 )
  {
    Destination = 0;
    v20 = v73.Length + DestinationString.Length + 4;
    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v20);
    if ( Destination.Buffer )
    {
      Destination.Length = 0;
      Destination.MaximumLength = v20;
      RtlCopyUnicodeString(&Destination, &v73);
      if ( RtlAppendUnicodeToString(&Destination, L",") < 0
        || RtlAppendUnicodeStringToString(&Destination, &DestinationString) < 0 )
      {
        if ( Destination.Buffer )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
        v18 = 0;
      }
      else
      {
        v18 = Destination.Buffer;
      }
    }
    else
    {
      v18 = 0;
    }
  }
  else
  {
    v18 = (WCHAR *)SourceString;
  }
  if ( !v18 )
    goto LABEL_129;
  v76[0] = 0;
  if ( (int)RtlGetThreadPreferredUILanguages(48, &v68, v76, &v59) < 0
    || NtCurrentTeb()->MergedPrefLanguages == (PVOID)-44LL )
  {
    goto LABEL_129;
  }
  if ( ((unsigned __int8)v10 & 0x10) == 0 )
  {
    v21 = 0;
    for ( i = 1; v18[i]; ++i )
    {
      v23 = i;
      if ( v18[i] != 44 )
        v23 = v21;
      v21 = v23;
    }
    if ( v18[v21] )
    {
      while ( 1 )
      {
        v24 = &v18[v21];
        if ( *v24 == 35 && !_wcsnicmp(v24, L"#IMMUTABLE", 0xAu) )
          break;
        if ( !v18[++v21] )
          goto LABEL_53;
      }
      LODWORD(v10) = (unsigned int)v10 | 0x10;
      v55 = (unsigned int)v10;
    }
  }
LABEL_53:
  if ( ((unsigned __int8)v10 & 0x10) != 0 )
  {
    v25 = RtlStringCchPrintfW(v75, 11, L"Strings");
  }
  else
  {
    v28 = LoadGlobalCacheGeneration(&v58);
    LastErrorValue = v28;
    if ( v28 )
    {
      RtlSetLastWin32Error(v28);
      v27 = 0;
      goto LABEL_130;
    }
    v25 = RtlStringCchPrintfW(v75, 11, L"%x", v58);
  }
  if ( v25 >= 0 )
  {
    if ( !(unsigned int)OpenMuiStringCache(&Handle)
      && ((unsigned __int8)v10 & 4) == 0
      && !(unsigned int)GetMUIStringFromCache(Handle, v18, cchBuffer, (__int64)&v51) )
    {
      if ( Buffer && (unsigned int)v51 > cchBuffer )
      {
        LastErrorValue = 122;
        v27 = 0;
      }
      else
      {
        LastErrorValue = 0;
        v27 = 0;
      }
      goto LABEL_130;
    }
LABEL_69:
    v26 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &v66, &Length);
    if ( (int)(v26 + 0x80000000) >= 0 && v26 != -1073741789 )
      goto LABEL_57;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
    v27 = Heap;
    if ( !Heap )
    {
LABEL_72:
      LastErrorValue = RtlNtStatusToDosError(-1073741801);
      goto LABEL_130;
    }
    v66.Buffer = Heap;
    v66.Length = 0;
    v66.MaximumLength = Length;
    v27 = 0;
    v52 = 0;
    appended = RtlExpandEnvironmentStrings_U(0, &DestinationString, &v66, &Length);
    if ( appended < 0 )
    {
LABEL_100:
      LastErrorValue = RtlNtStatusToDosError(appended);
      goto LABEL_130;
    }
    v31 = v66.Buffer;
    String = 0;
    if ( v66.Buffer && *v66.Buffer == 64 )
    {
      v32 = 0;
      v33 = v66.Buffer + 1;
      LODWORD(v34) = 1;
      if ( v66.Buffer[1] )
      {
        do
        {
          v35 = v34;
          if ( v66.Buffer[(unsigned int)v34] != 44 )
            v35 = v32;
          v32 = v35;
          v34 = (unsigned int)(v34 + 1);
        }
        while ( v66.Buffer[v34] );
      }
      if ( v32 )
      {
        if ( ((unsigned __int8)v10 & 2) != 0 )
        {
          v10 = &v66.Buffer[v32];
          v36 = v10 + 1;
LABEL_86:
          inited = RtlInitUnicodeStringEx(&String, v36);
          if ( inited >= 0 && (inited = RtlUnicodeStringToInteger(&String, 0xAu, &Value), inited >= 0) )
          {
            if ( *v33 == 34 && (v38 = (unsigned int)(v32 - 1), v31[v38] == 34) )
            {
              v31[v38] = 0;
              v33 = v31 + 2;
              LOWORD(v27) = v32 - 2;
              LastErrorValue = 0;
              LOBYTE(v10) = v55;
            }
            else
            {
              LOWORD(v27) = v32;
              *v10 = 0;
              LastErrorValue = 0;
              LOBYTE(v10) = v55;
            }
          }
          else
          {
            LastErrorValue = RtlNtStatusToDosError(inited);
            LOBYTE(v10) = v55;
          }
LABEL_95:
          if ( LastErrorValue )
            goto LABEL_58;
          if ( SourceStringa )
          {
            v39 = v73.Length + 2 * ((_WORD)v27 + 1);
            v40 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v39);
            v27 = v40;
            v52 = v40;
            if ( !v40 )
              goto LABEL_72;
            v65.Buffer = v40;
            v65.Length = 0;
            v65.MaximumLength = v39;
            RtlCopyUnicodeString(&v65, &v73);
            appended = RtlAppendUnicodeToString(&v65, L"\\");
            if ( appended < 0 )
              goto LABEL_100;
            appended = RtlAppendUnicodeToString(&v65, v33);
            if ( appended < 0 )
              goto LABEL_100;
          }
          else
          {
            v65.Buffer = v33;
            v27 = 0;
          }
          if ( ((unsigned __int8)v10 & 4) != 0 )
          {
            if ( GetFileAttributesW(v65.Buffer) == -1 )
            {
              LastErrorValue = 2;
              goto LABEL_130;
            }
            v41 = cchBuffer;
            v42 = v63;
            if ( Handle && !(unsigned int)GetMUIStringFromCache(Handle, v18, cchBuffer, (__int64)&v51) )
            {
              if ( v42 && (unsigned int)v51 > cchBuffer )
                LastErrorValue = 122;
              else
                LastErrorValue = 0;
LABEL_129:
              v27 = (void *)v52;
              goto LABEL_130;
            }
          }
          else
          {
            v42 = v63;
            v41 = cchBuffer;
          }
          Library = LoadLibraryExW(v65.Buffer, 0, 0x22u);
          hLibModule = Library;
          if ( Library )
          {
            v44 = RtlLoadString(Library, (unsigned __int16)Value, v56, 1, &Src, v53, 0, 0);
            if ( v53[0] )
            {
              v45 = v53[0];
              v46 = v53[0] + 1;
              LODWORD(v51) = v46;
              if ( v42 && v41 >= v46 )
              {
                memcpy_0(v42, Src, 2LL * v53[0]);
                *((_WORD *)v42 + v46 - 1) = 0;
              }
              else
              {
                v47 = 0;
                if ( v42 )
                  v47 = 122;
                LastErrorValue = v47;
              }
              if ( Handle )
              {
                if ( LastErrorValue || !v42 )
                {
                  v48 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * v46);
                  v49 = v48;
                  if ( v48 )
                  {
                    memcpy_0(v48, Src, 2 * v45);
                    v49[v46 - 1] = 0;
                    AddMUIStringToCache(Handle, v18, v49, (unsigned int)v51);
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v49);
                  }
                }
                else
                {
                  AddMUIStringToCache(Handle, v18, v42, (unsigned int)v51);
                }
              }
            }
            else
            {
              LastErrorValue = RtlNtStatusToDosError(v44);
              if ( !LastErrorValue )
                LastErrorValue = 1168;
            }
          }
          else
          {
            LastErrorValue = NtCurrentTeb()->LastErrorValue;
          }
          goto LABEL_129;
        }
        if ( v66.Buffer[v32 + 1] == 45 )
        {
          v10 = &v66.Buffer[v32];
          v36 = v10 + 2;
          goto LABEL_86;
        }
      }
    }
    else
    {
      v33 = 0;
    }
    LastErrorValue = 13;
    goto LABEL_95;
  }
  v26 = v25;
LABEL_57:
  LastErrorValue = RtlNtStatusToDosError(v26);
LABEL_58:
  v27 = 0;
LABEL_130:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( v27 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
  if ( v66.Buffer )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v66.Buffer);
    v66.Buffer = 0;
  }
  if ( v18 && v18 != v70 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
  if ( Handle )
    NtClose(Handle);
  if ( !LastErrorValue || LastErrorValue == 122 )
  {
    if ( v71 )
      *v71 = v51;
  }
  RtlSetLastWin32Error(LastErrorValue);
  LOBYTE(v11) = LastErrorValue == 0;
  return v11;
}

```

## disassembly

```asm
0x1800c3400  mov     [rsp+arg_0], ecx
0x1800c3404  push    rbx
0x1800c3405  push    rsi
0x1800c3406  push    rdi
0x1800c3407  push    r12
0x1800c3409  push    r13
0x1800c340b  push    r14
0x1800c340d  push    r15
0x1800c340f  sub     rsp, 350h
0x1800c3416  mov     rax, cs:__security_cookie
0x1800c341d  xor     rax, rsp
0x1800c3420  mov     [rsp+388h+var_48], rax
0x1800c3428  mov     r12, r9
0x1800c342b  mov     [rsp+388h+var_2F8], r9
0x1800c3433  mov     r15, r8
0x1800c3436  mov     [rsp+388h+var_2B8], r8
0x1800c343e  mov     r14, rdx
0x1800c3441  mov     r13d, ecx
0x1800c3444  mov     [rsp+388h+var_330], ecx
0x1800c3448  mov     [rsp+388h+hLibModule], rdx
0x1800c3450  mov     [rsp+388h+var_340], r8
0x1800c3455  mov     qword ptr [rsp+388h+Destination.Length], r9
0x1800c345a  mov     rcx, [rsp+388h+Directory]
0x1800c3462  mov     [rsp+388h+SourceString], rcx
0x1800c346a  mov     rcx, [rsp+388h+pcchBufferOut]
0x1800c3472  mov     [rsp+388h+var_2B0], rcx
0x1800c347a  xor     edi, edi
0x1800c347c  mov     [rsp+388h+Length], edi
0x1800c3480  mov     [rsp+388h+Value], edi
0x1800c3484  mov     dword ptr [rsp+388h+var_348], edi
0x1800c3488  xorps   xmm0, xmm0
0x1800c348b  movups  xmmword ptr [rsp+388h+DestinationString.Length], xmm0
0x1800c3493  xorps   xmm1, xmm1
0x1800c3496  movups  xmmword ptr [rsp+388h+var_2D8.Length], xmm1
0x1800c349e  movups  xmmword ptr [rsp+388h+var_298.Length], xmm0
0x1800c34a6  movups  xmmword ptr [rsp+388h+var_2E8.Length], xmm1
0x1800c34ae  mov     [rsp+388h+var_338], di
0x1800c34b3  mov     [rsp+388h+Src], rdi
0x1800c34bb  mov     [rsp+388h+var_32C], edi
0x1800c34bf  mov     [rsp+388h+Handle], rdi
0x1800c34c4  mov     [rsp+388h+var_320], edi
0x1800c34c8  mov     [rsp+388h+var_31C], 104h
0x1800c34d0  mov     [rsp+388h+var_2C4], edi
0x1800c34d7  test    r8, r8
0x1800c34da  jz      loc_1800C3EE5
0x1800c34e0  test    r9, r9
0x1800c34e3  jnz     short loc_1800C34FB
0x1800c34e5  test    rcx, rcx
0x1800c34e8  jz      loc_1800C3EE5
0x1800c34ee  cmp     [rsp+388h+cchBuffer], edi
0x1800c34f5  jnz     loc_1800C3EE5
0x1800c34fb  mov     eax, r13d
0x1800c34fe  and     eax, 3
0x1800c3501  cmp     al, 3
0x1800c3503  jz      loc_1800C3EE5
0x1800c3509  test    r13d, 0FFFFFFE0h
0x1800c3510  jnz     loc_1800C3EE5
0x1800c3516  mov     ebx, edi
0x1800c3518  test    r14, r14
0x1800c351b  jz      short loc_1800C3590
0x1800c351d  mov     r8d, 3
0x1800c3523  lea     rdx, [rsp+388h+var_32C]
0x1800c3528  mov     rcx, r14
0x1800c352b  call    cs:__imp_RtlLocaleNameToLcid
0x1800c3531  test    eax, eax
0x1800c3533  jns     short loc_1800C3543
0x1800c3535  mov     ebx, 57h ; 'W'
0x1800c353a  mov     [rsp+388h+var_2C8], ebx
0x1800c3541  jmp     short loc_1800C354C
0x1800c3543  movzx   eax, word ptr [rsp+388h+var_32C]
0x1800c3548  mov     [rsp+388h+var_32C], eax
0x1800c354c  jmp     short loc_1800C3590
0x1800c354e  mov     ecx, eax; Status
0x1800c3550  call    cs:__imp_RtlNtStatusToDosError
0x1800c3556  mov     ebx, eax
0x1800c3558  mov     [rsp+388h+var_2C8], eax
0x1800c355f  xor     edi, edi
0x1800c3561  mov     r13d, [rsp+388h+arg_0]
0x1800c3569  mov     [rsp+388h+var_330], r13d
0x1800c356e  mov     r14, [rsp+388h+hLibModule]
0x1800c3576  mov     r15, [rsp+388h+var_340]
0x1800c357b  mov     [rsp+388h+var_2B8], r15
0x1800c3583  mov     r12, qword ptr [rsp+388h+Destination.Length]
0x1800c3588  mov     [rsp+388h+var_2F8], r12
0x1800c3590  test    ebx, ebx
0x1800c3592  jz      short loc_1800C359B
0x1800c3594  mov     ecx, ebx
0x1800c3596  jmp     loc_1800C3EEA
0x1800c359b  cmp     word ptr [r15], 40h ; '@'
0x1800c35a0  jnz     loc_1800C3EDE
0x1800c35a6  mov     edx, edi
0x1800c35a8  mov     r8d, 1
0x1800c35ae  movzx   r9d, word ptr [r15+2]
0x1800c35b3  test    r9w, r9w
0x1800c35b7  jz      short loc_1800C35E3
0x1800c35b9  nop     dword ptr [rax+00000000h]
0x1800c35c0  movzx   eax, r8w
0x1800c35c4  movzx   ecx, r8w
0x1800c35c8  cmp     word ptr [r15+rax*2], 2Ch ; ','
0x1800c35ce  cmovnz  ecx, edx
0x1800c35d1  mov     edx, ecx
0x1800c35d3  inc     r8w
0x1800c35d7  movzx   eax, r8w
0x1800c35db  cmp     word ptr [r15+rax*2], 0
0x1800c35e1  jnz     short loc_1800C35C0
0x1800c35e3  test    edx, edx
0x1800c35e5  jz      short loc_1800C3635
0x1800c35e7  mov     eax, edx
0x1800c35e9  cmp     word ptr [r15+rax*2], 2Ch ; ','
0x1800c35ef  jnz     loc_1800C3EDE
0x1800c35f5  lea     eax, [rdx-1]
0x1800c35f8  cmp     word ptr [r15+rax*2], 22h ; '"'
0x1800c35fe  jnz     short loc_1800C360B
0x1800c3600  cmp     r9w, 22h ; '"'
0x1800c3605  jnz     loc_1800C3EDE
0x1800c360b  test    r13b, 2
0x1800c360f  jnz     short loc_1800C361F
0x1800c3611  inc     edx
0x1800c3613  cmp     word ptr [r15+rdx*2], 2Dh ; '-'
0x1800c3619  jnz     loc_1800C3EDE
0x1800c361f  lea     eax, [rdx+1]
0x1800c3622  movzx   eax, word ptr [r15+rax*2]
0x1800c3627  sub     ax, 30h ; '0'
0x1800c362b  cmp     ax, 9
0x1800c362f  ja      loc_1800C3EDE
0x1800c3635  mov     rsi, rdi
0x1800c3638  mov     [rsp+388h+var_340], rdi
0x1800c363d  mov     [rsp+388h+hLibModule], rdi
0x1800c3645  mov     rdx, r15; SourceString
0x1800c3648  lea     rcx, [rsp+388h+DestinationString]; DestinationString
0x1800c3650  call    cs:__imp_RtlInitUnicodeString
0x1800c3656  mov     rax, [rsp+388h+SourceString]
0x1800c365e  test    rax, rax
0x1800c3661  jz      short loc_1800C367C
0x1800c3663  mov     rdx, rax; SourceString
0x1800c3666  lea     rcx, [rsp+388h+var_298]; DestinationString
0x1800c366e  call    cs:__imp_RtlInitUnicodeString
0x1800c3674  mov     rax, [rsp+388h+SourceString]
0x1800c367c  test    r13b, 8
0x1800c3680  jnz     loc_1800C395A
0x1800c3686  test    r14, r14
0x1800c3689  jnz     loc_1800C395A
0x1800c368f  test    rax, rax
0x1800c3692  jz      loc_1800C3768
0x1800c3698  xorps   xmm0, xmm0
0x1800c369b  movups  xmmword ptr [rsp+388h+Destination.Length], xmm0
0x1800c36a0  movzx   eax, [rsp+388h+DestinationString.Length]
0x1800c36a8  add     ax, 4
0x1800c36ac  add     ax, [rsp+388h+var_298.Length]
0x1800c36b4  movzx   esi, ax
0x1800c36b7  mov     r8d, esi; Size
0x1800c36ba  mov     rcx, gs:60h
0x1800c36c3  mov     edx, 8; Flags
0x1800c36c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800c36cc  call    cs:__imp_RtlAllocateHeap
0x1800c36d2  mov     [rsp+388h+Destination.Buffer], rax
0x1800c36da  test    rax, rax
0x1800c36dd  jnz     short loc_1800C36E7
0x1800c36df  mov     rsi, rdi
0x1800c36e2  jmp     loc_1800C376B
0x1800c36e7  mov     [rsp+388h+Destination.Length], di
0x1800c36ec  mov     [rsp+388h+Destination.MaximumLength], si
0x1800c36f1  lea     rdx, [rsp+388h+var_298]; SourceString
0x1800c36f9  lea     rcx, [rsp+388h+Destination]; DestinationString
0x1800c36fe  call    cs:__imp_RtlCopyUnicodeString
0x1800c3704  lea     rdx, asc_18029A9BC; ","
0x1800c370b  lea     rcx, [rsp+388h+Destination]; Destination
0x1800c3710  call    cs:__imp_RtlAppendUnicodeToString
0x1800c3716  test    eax, eax
0x1800c3718  js      short loc_1800C373B
0x1800c371a  lea     rdx, [rsp+388h+DestinationString]; Source
0x1800c3722  lea     rcx, [rsp+388h+Destination]; Destination
0x1800c3727  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800c372d  test    eax, eax
0x1800c372f  js      short loc_1800C373B
0x1800c3731  mov     rsi, [rsp+388h+Destination.Buffer]
0x1800c3739  jmp     short loc_1800C376B
0x1800c373b  cmp     [rsp+388h+Destination.Buffer], 0
0x1800c3744  jz      short loc_1800C3763
0x1800c3746  mov     rcx, gs:60h
0x1800c374f  mov     r8, [rsp+388h+Destination.Buffer]; P
0x1800c3757  xor     edx, edx; Flags
0x1800c3759  mov     rcx, [rcx+30h]; HeapHandle
0x1800c375d  call    cs:__imp_RtlFreeHeap
0x1800c3763  mov     rsi, rdi
0x1800c3766  jmp     short loc_1800C376B
0x1800c3768  mov     rsi, r15
0x1800c376b  test    rsi, rsi
0x1800c376e  jz      loc_1800C3E12
0x1800c3774  mov     [rsp+388h+var_258], di
0x1800c377c  lea     r9, [rsp+388h+var_31C]
0x1800c3781  lea     r8, [rsp+388h+var_258]
0x1800c3789  lea     rdx, [rsp+388h+var_2C4]
0x1800c3791  mov     ecx, 30h ; '0'
0x1800c3796  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x1800c379c  test    eax, eax
0x1800c379e  js      loc_1800C3E12
0x1800c37a4  mov     rax, gs:30h
0x1800c37ad  mov     r15, [rax+17E0h]
0x1800c37b4  add     r15, 2Ch ; ','
0x1800c37b8  jz      loc_1800C3E12
0x1800c37be  test    r13b, 10h
0x1800c37c2  jnz     loc_1800C384B
0x1800c37c8  mov     ebx, edi
0x1800c37ca  mov     edx, 1
0x1800c37cf  cmp     word ptr [rsi+2], 0
0x1800c37d4  jz      short loc_1800C37FB
0x1800c37d6  nop     word ptr [rax+rax+00000000h]
0x1800c37e0  movsxd  rax, edx
0x1800c37e3  mov     ecx, edx
0x1800c37e5  cmp     word ptr [rsi+rax*2], 2Ch ; ','
0x1800c37ea  cmovnz  ecx, ebx
0x1800c37ed  mov     ebx, ecx
0x1800c37ef  inc     edx
0x1800c37f1  movsxd  rax, edx
0x1800c37f4  cmp     word ptr [rsi+rax*2], 0
0x1800c37f9  jnz     short loc_1800C37E0
0x1800c37fb  movsxd  rax, ebx
0x1800c37fe  cmp     word ptr [rsi+rax*2], 0
0x1800c3803  jz      short loc_1800C384B
0x1800c3805  nop     word ptr [rax+rax+00000000h]
0x1800c3810  movsxd  rax, ebx
0x1800c3813  lea     rcx, [rsi+rax*2]; String1
0x1800c3817  cmp     word ptr [rcx], 23h ; '#'
0x1800c381b  jnz     short loc_1800C3834
0x1800c381d  mov     r8d, 0Ah; MaxCount
0x1800c3823  lea     rdx, aImmutable; "#IMMUTABLE"
0x1800c382a  call    cs:__imp__wcsnicmp
0x1800c3830  test    eax, eax
0x1800c3832  jz      short loc_1800C3842
0x1800c3834  inc     ebx
0x1800c3836  movsxd  rax, ebx
0x1800c3839  cmp     word ptr [rsi+rax*2], 0
0x1800c383e  jnz     short loc_1800C3810
0x1800c3840  jmp     short loc_1800C384B
0x1800c3842  or      r13d, 10h
0x1800c3846  mov     [rsp+388h+var_330], r13d
0x1800c384b  mov     r14d, r13d
0x1800c384e  and     r14d, 10h
0x1800c3852  jz      short loc_1800C3883
0x1800c3854  lea     r8, aStrings; "Strings"
0x1800c385b  mov     edx, 0Bh
0x1800c3860  lea     rcx, [rsp+388h+var_278]
0x1800c3868  call    RtlStringCchPrintfW
0x1800c386d  test    eax, eax
0x1800c386f  jns     short loc_1800C38C3
0x1800c3871  mov     ecx, eax; Status
0x1800c3873  call    cs:__imp_RtlNtStatusToDosError
0x1800c3879  mov     ebx, eax
0x1800c387b  mov     r12, rdi
0x1800c387e  jmp     loc_1800C3E17
0x1800c3883  lea     rcx, [rsp+388h+var_320]
0x1800c3888  call    _LoadGlobalCacheGeneration
0x1800c388d  mov     ebx, eax
0x1800c388f  test    eax, eax
0x1800c3891  jz      short loc_1800C38A3
0x1800c3893  mov     ecx, eax; LastError
0x1800c3895  call    cs:__imp_RtlSetLastWin32Error
0x1800c389b  mov     r12, rdi
0x1800c389e  jmp     loc_1800C3E17
0x1800c38a3  mov     r9d, [rsp+388h+var_320]
0x1800c38a8  lea     r8, asc_1802998E0; "%x"
0x1800c38af  mov     edx, 0Bh
0x1800c38b4  lea     rcx, [rsp+388h+var_278]
0x1800c38bc  call    RtlStringCchPrintfW
0x1800c38c1  jmp     short loc_1800C386D
0x1800c38c3  lea     rax, aSoftwareClasse; "Software\\Classes\\Local Settings\\MuiC"...
0x1800c38ca  lea     rdx, aSoftwareClasse_5; "Software\\Classes\\Local Settings\\Immu"...
0x1800c38d1  test    r14d, r14d
0x1800c38d4  cmovz   rdx, rax
0x1800c38d8  mov     eax, [rsp+388h+var_31C]
0x1800c38dc  mov     dword ptr [rsp+388h+var_360], eax
0x1800c38e0  lea     rax, [rsp+388h+var_258]
0x1800c38e8  mov     qword ptr [rsp+388h+var_368], rax
0x1800c38ed  mov     r9, r15
0x1800c38f0  lea     r8, [rsp+388h+var_278]
0x1800c38f8  lea     rcx, [rsp+388h+Handle]; KeyHandle
0x1800c38fd  call    _OpenMuiStringCache
0x1800c3902  test    eax, eax
0x1800c3904  jnz     short loc_1800C395A
0x1800c3906  test    r13b, 4
0x1800c390a  jnz     short loc_1800C395A
0x1800c390c  lea     rax, [rsp+388h+var_348]
0x1800c3911  mov     [rsp+388h+var_360], rax; __int64
0x1800c3916  mov     ebx, [rsp+388h+cchBuffer]
0x1800c391d  mov     [rsp+388h+var_368], ebx; int
0x1800c3921  mov     r9, r12
0x1800c3924  xor     r8d, r8d
0x1800c3927  mov     rdx, rsi; SourceString
0x1800c392a  mov     rcx, [rsp+388h+Handle]; KeyHandle
0x1800c392f  call    _GetMUIStringFromCache
0x1800c3934  test    eax, eax
0x1800c3936  jnz     short loc_1800C395A
0x1800c3938  test    r12, r12
0x1800c393b  jz      short loc_1800C3950
0x1800c393d  cmp     dword ptr [rsp+388h+var_348], ebx
0x1800c3941  jbe     short loc_1800C3950
0x1800c3943  mov     ebx, 7Ah ; 'z'
0x1800c3948  mov     r12, rdi
0x1800c394b  jmp     loc_1800C3E17
  ... truncated ...
```
