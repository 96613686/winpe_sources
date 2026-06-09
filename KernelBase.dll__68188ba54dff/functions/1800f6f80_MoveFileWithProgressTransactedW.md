# MoveFileWithProgressTransactedW

- ea: `0x1800f6f80`
- end: `0x1800f7d70`
- name: `MoveFileWithProgressTransactedW`
- size: `3568`
- prototype: `__int64 __usercall@<rax>(PCWSTR DosPathName@<rcx>, LPCWSTR lpFileName@<rdx>, int, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f6ee0`
- `0x1800f6f30`

## callees

- `0x1800134a0`
- `0x180048f30`
- `0x1800cd0f0`
- `0x1800cfdf0`
- `0x1800ea710`
- `0x1800f0120`
- `0x1800f6f80`
- `0x1801006c0`
- `0x18010d080`
- `0x1801102f4`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800f7347`
- `ntdll!RtlInitUnicodeString` at `0x1800f7347`
- `ntdll!NtQueryInformationFile` at `0x1800f7220`
- `ntdll!NtQueryInformationFile` at `0x1800f7aab`
- `ntdll!NtQueryInformationFile` at `0x1800f7220`
- `ntdll!NtQueryInformationFile` at `0x1800f7aab`
- `ntdll!NtOpenFile` at `0x1800f7176`
- `ntdll!NtOpenFile` at `0x1800f71e5`
- `ntdll!NtOpenFile` at `0x1800f72da`
- `ntdll!NtOpenFile` at `0x1800f7323`
- `ntdll!NtOpenFile` at `0x1800f745d`
- `ntdll!NtOpenFile` at `0x1800f759d`
- `ntdll!NtOpenFile` at `0x1800f7176`
- `ntdll!NtOpenFile` at `0x1800f71e5`
- `ntdll!NtOpenFile` at `0x1800f72da`
- `ntdll!NtOpenFile` at `0x1800f7323`
- `ntdll!NtOpenFile` at `0x1800f745d`
- `ntdll!NtOpenFile` at `0x1800f759d`
- `ntdll!NtSetInformationFile` at `0x1800f7a3d`
- `ntdll!NtSetInformationFile` at `0x1800f7a3d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f70be`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f7360`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f70be`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f7360`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f7b50`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f7bdd`
- `ntdll!RtlSetCurrentTransaction` at `0x18018c65a`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f7b50`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f7bdd`
- `ntdll!RtlSetCurrentTransaction` at `0x18018c65a`
- `ntdll!RtlGetCurrentTransaction` at `0x1800f7af3`
- `ntdll!RtlGetCurrentTransaction` at `0x1800f7af3`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800f7094`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800f7094`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x1800f78e2`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x1800f78e2`
- `ntdll!NtClose` at `0x1800f729e`
- `ntdll!NtClose` at `0x1800f7ad1`
- `ntdll!NtClose` at `0x1800f7cd9`
- `ntdll!NtClose` at `0x1800f7ced`
- `ntdll!NtClose` at `0x18018c684`
- `ntdll!NtClose` at `0x18018c698`
- `ntdll!NtClose` at `0x1800f729e`
- `ntdll!NtClose` at `0x1800f7ad1`
- `ntdll!NtClose` at `0x1800f7cd9`
- `ntdll!NtClose` at `0x1800f7ced`
- `ntdll!NtClose` at `0x18018c684`
- `ntdll!NtClose` at `0x18018c698`
- `ntdll!RtlFreeHeap` at `0x1800f75ca`
- `ntdll!RtlFreeHeap` at `0x1800f777f`
- `ntdll!RtlFreeHeap` at `0x1800f7891`
- `ntdll!RtlFreeHeap` at `0x1800f78b3`
- `ntdll!RtlFreeHeap` at `0x1800f7a57`
- `ntdll!RtlFreeHeap` at `0x1800f7d14`
- `ntdll!RtlFreeHeap` at `0x1800f7d3b`
- `ntdll!RtlFreeHeap` at `0x18018c6bf`
- `ntdll!RtlFreeHeap` at `0x18018c6e6`
- `ntdll!RtlFreeHeap` at `0x1800f75ca`
- `ntdll!RtlFreeHeap` at `0x1800f777f`
- `ntdll!RtlFreeHeap` at `0x1800f7891`
- `ntdll!RtlFreeHeap` at `0x1800f78b3`
- `ntdll!RtlFreeHeap` at `0x1800f7a57`
- `ntdll!RtlFreeHeap` at `0x1800f7d14`
- `ntdll!RtlFreeHeap` at `0x1800f7d3b`
- `ntdll!RtlFreeHeap` at `0x18018c6bf`
- `ntdll!RtlFreeHeap` at `0x18018c6e6`
- `ntdll!RtlAllocateHeap` at `0x1800f74ab`
- `ntdll!RtlAllocateHeap` at `0x1800f76d1`
- `ntdll!RtlAllocateHeap` at `0x1800f79be`
- `ntdll!RtlAllocateHeap` at `0x1800f74ab`
- `ntdll!RtlAllocateHeap` at `0x1800f76d1`
- `ntdll!RtlAllocateHeap` at `0x1800f79be`

## pseudocode

```c
__int64 __fastcall MoveFileWithProgressTransactedW(
        PCWSTR DosPathName,
        LPCWSTR lpFileName,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  const WCHAR *v6; // r13
  unsigned __int8 v8; // si
  __int64 v9; // rcx
  char v10; // r12
  NTSTATUS v11; // eax
  int v12; // edx
  NTSTATUS v13; // ebx
  NTSTATUS v14; // eax
  int v15; // edx
  struct _UNICODE_STRING v16; // xmm6
  PVOID Heap; // rax
  int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r13
  unsigned int v23; // r15d
  unsigned __int16 v24; // r14
  _WORD *v25; // rax
  _WORD *v26; // r12
  __int64 v27; // rdx
  __int64 v28; // r14
  char *v29; // rax
  _QWORD *v30; // rdi
  __int64 CurrentTransaction; // rbx
  const WCHAR *v32; // rdi
  int v33; // ebx
  unsigned __int8 v35; // [rsp+80h] [rbp-1A8h]
  HANDLE FileHandle; // [rsp+88h] [rbp-1A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-198h] BYREF
  int v38; // [rsp+A0h] [rbp-188h]
  HANDLE v39; // [rsp+A8h] [rbp-180h] BYREF
  HANDLE hObject[2]; // [rsp+B0h] [rbp-178h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+C0h] [rbp-168h] BYREF
  PVOID P[2]; // [rsp+D0h] [rbp-158h] BYREF
  HANDLE Handle; // [rsp+E0h] [rbp-148h] BYREF
  PVOID v44[2]; // [rsp+F0h] [rbp-138h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp-128h] BYREF
  PVOID v46[2]; // [rsp+110h] [rbp-118h] BYREF
  int v47; // [rsp+120h] [rbp-108h]
  __int64 FileInformation; // [rsp+128h] [rbp-100h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+130h] [rbp-F8h] BYREF
  LPCWSTR v50; // [rsp+160h] [rbp-C8h]
  PCWSTR Path; // [rsp+168h] [rbp-C0h]
  __int64 v52[2]; // [rsp+170h] [rbp-B8h] BYREF
  __int128 v53; // [rsp+180h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+190h] [rbp-98h]
  __int64 v55; // [rsp+198h] [rbp-90h]
  __int64 v56; // [rsp+1A0h] [rbp-88h]
  __int64 v57; // [rsp+1A8h] [rbp-80h]
  _BYTE v58[32]; // [rsp+1B0h] [rbp-78h] BYREF
  __int64 v59; // [rsp+1D0h] [rbp-58h]

  v56 = a4;
  v55 = a3;
  v6 = lpFileName;
  v50 = lpFileName;
  Path = DosPathName;
  v52[0] = a6;
  memset(&ObjectAttributes, 0, 44);
  FileHandle = (HANDLE)-1LL;
  *(_QWORD *)&NtPathName.Length = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v8 = 0;
  v53 = 0;
  LODWORD(v54) = 0;
  memset(v58, 0, sizeof(v58));
  v59 = 0;
  Handle = (HANDLE)-1LL;
  LODWORD(hObject[0]) = 0;
  LODWORD(v39) = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v46 = 0;
  *(_OWORD *)v44 = 0;
  DestinationString.Buffer = 0;
  NtPathName.Buffer = 0;
  if ( lpFileName && RtlIsDosDeviceName_U(lpFileName) )
  {
    v9 = 3221225525LL;
LABEL_4:
    BaseSetLastNTError(v9);
    goto LABEL_124;
  }
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
LABEL_6:
    v9 = 3221225530LL;
    goto LABEL_4;
  }
  v10 = a5;
  if ( (a5 & 4) != 0 && (a5 & 0x10) != 0 )
  {
    v9 = 3221225485LL;
    goto LABEL_4;
  }
  v35 = a5 & 1;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenFile(&FileHandle, 0x110080u, &ObjectAttributes, &IoStatusBlock, 7u, ((a5 & 8 | 0x10080u) >> 2) | 0x200000);
  if ( v11 < 0 )
  {
    if ( (a5 & 4) != 0 && (unsigned int)(v11 + 1073741772) <= 0xF )
    {
      v12 = 32833;
      if ( _bittest(&v12, v11 + 1073741772) )
      {
        FileHandle = (HANDLE)-1LL;
        v13 = -1073741811;
        goto LABEL_34;
      }
    }
    v13 = -1073741811;
    if ( v11 == -1073741811 )
      v11 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 3u, (a5 & 8 | 0x10080u) >> 2);
    goto LABEL_17;
  }
  v14 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
  if ( v14 >= 0 || v14 == -1073741822 )
  {
    v13 = -1073741811;
  }
  else
  {
    v13 = -1073741811;
    if ( v14 != -1073741811 )
    {
      BaseSetLastNTError((unsigned int)v14);
      goto LABEL_124;
    }
  }
  if ( v14 >= 0 && (FileInformation & 0x400) != 0 )
  {
    if ( (unsigned int)(HIDWORD(FileInformation) + 1610612733) > 0x1A
      || (v15 = 67109377, !_bittest(&v15, HIDWORD(FileInformation) + 1610612733)) )
    {
      if ( (unsigned int)(HIDWORD(FileInformation) + 2147483613) > 3 )
      {
        NtClose(FileHandle);
        FileHandle = (HANDLE)-1LL;
        v11 = NtOpenFile(&FileHandle, 0x110000u, &ObjectAttributes, &IoStatusBlock, 3u, (a5 & 8 | 0x10080u) >> 2);
        if ( v11 < 0 )
        {
          if ( ((v11 + 1073741194) & 0xFFFFFFFC) == 0 && v11 != -1073741193 )
            v11 = NtOpenFile(
                    &FileHandle,
                    0x110000u,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    3u,
                    ((a5 & 8 | 0x10080u) >> 2) | 0x200000);
LABEL_17:
          if ( v11 < 0 )
          {
            v9 = (unsigned int)v11;
            goto LABEL_4;
          }
        }
      }
    }
  }
LABEL_34:
  if ( (a5 & 4) == 0 || v6 )
  {
    if ( !RtlDosPathNameToNtPathName_U(v6, &DestinationString, 0, 0) )
      goto LABEL_6;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
  }
  if ( (a5 & 4) != 0 )
  {
    if ( (NtCurrentPeb()->AppCompatFlags.QuadPart & 0x800000000LL) != 0 )
    {
      *(struct _UNICODE_STRING *)v46 = NtPathName;
      NtPathName.Buffer = 0;
      AssembleRegistryString(v46, 48, 0, &NtPathName);
      if ( !DestinationString.Length )
        goto LABEL_84;
      v16 = DestinationString;
      *(struct _UNICODE_STRING *)v44 = DestinationString;
      DestinationString.Buffer = 0;
      AssembleRegistryString(v44, 48, v35, &DestinationString);
      goto LABEL_83;
    }
    if ( FileHandle == (HANDLE)-1LL
      && NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u) < 0 )
    {
      FileHandle = (HANDLE)-1LL;
    }
    if ( v6 )
    {
      *(_OWORD *)P = 0;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, DestinationString.MaximumLength + 2LL);
      P[1] = Heap;
      if ( Heap )
      {
        memcpy_0(Heap, DestinationString.Buffer, DestinationString.Length);
        v18 = DestinationString.Length >> 1;
        v38 = v18;
        v19 = v18;
        LODWORD(v20) = v18;
        while ( v19 )
        {
          v20 = (unsigned int)(v20 - 1);
          if ( *((_WORD *)P[1] + v20) == 92 )
            break;
          LOWORD(v18) = v20;
          v38 = v20;
          v19 = v20;
        }
        *((_WORD *)P[1] + v19) = 0;
        LOWORD(P[0]) = 2 * v18;
        WORD1(P[0]) = 2 * v18 + 2;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenFile(&Handle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4020u) < 0 )
          Handle = (HANDLE)-1LL;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
        *(_OWORD *)P = 0;
      }
    }
    if ( FileHandle != (HANDLE)-1LL )
      LODWORD(hObject[0]) = RetrieveFinalPathName(FileHandle, (PUNICODE_STRING)v46);
    if ( Handle != (HANDLE)-1LL )
    {
      LODWORD(v39) = RetrieveFinalPathName(Handle, (PUNICODE_STRING)P);
      v47 = (int)v39;
      if ( (_DWORD)v39 && DestinationString.Length >= 2u )
      {
        v21 = (DestinationString.Length >> 1) - 1;
        v38 = (DestinationString.Length >> 1) - 1;
        while ( DestinationString.Buffer[v21] != 92 && (_DWORD)v21 )
        {
          v21 = (unsigned int)(v21 - 1);
          v38 = v21;
        }
        if ( (unsigned int)v21 <= 6 )
        {
          LODWORD(v21) = v21 + 1;
          v38 = v21;
        }
        v22 = (unsigned int)v21;
        v23 = (DestinationString.Length >> 1) - v21;
        v24 = LOWORD(P[0]) + 2 * ((DestinationString.Length >> 1) - v21);
        LOWORD(v44[0]) = v24;
        WORD1(v44[0]) = v24 + 2;
        v25 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, (unsigned __int16)(v24 + 2));
        v26 = v25;
        v44[1] = v25;
        if ( v25 )
        {
          memcpy_0(v25, P[1], LOWORD(P[0]));
          memcpy_0(&v26[(unsigned __int64)LOWORD(P[0]) >> 1], &DestinationString.Buffer[v22], 2LL * v23);
          v26[(unsigned __int64)v24 >> 1] = 0;
        }
        else
        {
          LODWORD(v39) = 0;
          v47 = 0;
        }
        v6 = v50;
        v10 = a5;
      }
      if ( P[1] )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    }
    if ( FileHandle == (HANDLE)-1LL || !LODWORD(hObject[0]) )
    {
      if ( !NtPathName.Length )
      {
LABEL_78:
        if ( Handle == (HANDLE)-1LL || !(_DWORD)v39 )
        {
          if ( DestinationString.Length )
          {
            v16 = DestinationString;
            *(struct _UNICODE_STRING *)v44 = DestinationString;
            DestinationString.Buffer = 0;
            AssembleRegistryString(v44, 50, v35, &DestinationString);
LABEL_83:
            v44[1] = (PVOID)_mm_srli_si128((__m128i)v16, 8).m128i_u64[0];
          }
        }
        else
        {
          AssembleRegistryString(v44, 49, v35, &DestinationString);
        }
LABEL_84:
        if ( v46[1] )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v46[1]);
        if ( v44[1] )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v44[1]);
        if ( NtPathName.Buffer && (!v6 || DestinationString.Buffer) )
        {
          if ( RtlDetermineDosPathNameType_U(Path) == RtlPathTypeUncAbsolute || (v10 & 2) != 0 )
            goto LABEL_98;
          v28 = v52[0];
          v13 = BasepMoveFileDelayed((unsigned int)&NtPathName, (unsigned int)&DestinationString, 2, 0, v52[0]);
          if ( v13 == -1073741772 )
          {
            v13 = BasepMoveFileDelayed((unsigned int)&NtPathName, (unsigned int)&DestinationString, 1, 1, v28);
            if ( v13 == -1073741670 )
              v13 = BasepMoveFileDelayed((unsigned int)&NtPathName, (unsigned int)&DestinationString, 2, 1, v28);
          }
        }
        else
        {
          v13 = -1073741670;
        }
        if ( v13 < 0 )
        {
LABEL_98:
          v9 = (unsigned int)v13;
          goto LABEL_4;
        }
        goto LABEL_99;
      }
      *(struct _UNICODE_STRING *)v46 = NtPathName;
      NtPathName.Buffer = 0;
      v27 = 50;
    }
    else
    {
      v27 = 49;
    }
    AssembleRegistryString(v46, v27, 0, &NtPathName);
    goto LABEL_78;
  }
  v29 = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, DestinationString.Length + 24LL);
  v30 = v29;
  if ( !v29 )
  {
    v9 = 3221225495LL;
    goto LABEL_4;
  }
  memcpy_0(v29 + 20, DestinationString.Buffer, DestinationString.Length);
  *(_BYTE *)v30 = v35;
  v30[1] = 0;
  *((_DWORD *)v30 + 4) = DestinationString.Length;
  v13 = NtSetInformationFile(
          FileHandle,
          &IoStatusBlock,
          v30,
          DestinationString.Length + 24,
          (FILE_INFORMATION_CLASS)((a5 & 0x10 | 0xA0u) >> 4));
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
  if ( v13 >= 0 )
  {
LABEL_99:
    v8 = 1;
    goto LABEL_124;
  }
  if ( v13 != -1073741612 && v13 != -1072103368 || (a5 & 2) == 0 )
    goto LABEL_98;
  if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, v58, 0x28u, FileBasicInformation) >= 0 && (v59 & 0x10) != 0 )
  {
    v9 = 3221225658LL;
    goto LABEL_4;
  }
  NtClose(FileHandle);
  FileHandle = (HANDLE)-1LL;
  v39 = (HANDLE)-1LL;
  hObject[0] = (HANDLE)-1LL;
  CurrentTransaction = RtlGetCurrentTransaction();
  v57 = CurrentTransaction;
  v52[0] = (__int64)BasepMoveFileCopyProgress;
  v52[1] = 0;
  LODWORD(v53) = a5;
  *((_QWORD *)&v53 + 1) = v55;
  v54 = v56;
  RtlSetCurrentTransaction(0);
  v32 = Path;
  v8 = BasepCopyFileExW(
         (_DWORD)Path,
         (_DWORD)v6,
         (unsigned int)v52,
         (unsigned int)&v53,
         0,
         0,
         0,
         !(a5 & 1) | 0x804u,
         0,
         (__int64)&v39,
         (__int64)hObject,
         CurrentTransaction,
         0,
         0,
         0,
         0);
  RtlSetCurrentTransaction(CurrentTransaction);
  if ( v8 )
  {
    if ( v39 != (HANDLE)-1LL && hObject[0] != (HANDLE)-1LL )
    {
      v33 = BasepNotifyTrackingService(&v39, &ObjectAttributes);
      if ( v33 < 0 && (a5 & 0x20) != 0 )
      {
        if ( hObject[0] != (HANDLE)-1LL )
          CloseHandle(hObject[0]);
        hObject[0] = (HANDLE)-1LL;
        DeleteFileW(v6);
        v8 = 0;
        BaseSetLastNTError((unsigned int)v33);
      }
    }
  }
  if ( v39 != (HANDLE)-1LL )
  {
    CloseHandle(v39);
    v39 = (HANDLE)-1LL;
  }
  if ( hObject[0] != (HANDLE)-1LL )
  {
    CloseHandle(hObject[0]);
    hObject[0] = (HANDLE)-1LL;
  }
  if ( v8 && !DeleteFileW(v32) )
  {
    SetFileAttributesW(v32, 0x80u);
    DeleteFileW(v32);
  }
LABEL_124:
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( Handle != (HANDLE)-1LL )
    NtClose(Handle);
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  return v8;
}

```

## disassembly

```asm
0x1800f6f80  mov     r11, rsp
0x1800f6f83  push    rbx
0x1800f6f84  push    rsi
0x1800f6f85  push    rdi
0x1800f6f86  push    r12
0x1800f6f88  push    r13
0x1800f6f8a  push    r14
0x1800f6f8c  push    r15
0x1800f6f8e  sub     rsp, 1F0h
0x1800f6f95  movaps  xmmword ptr [r11-48h], xmm6
0x1800f6f9a  mov     rax, cs:__security_cookie
0x1800f6fa1  xor     rax, rsp
0x1800f6fa4  mov     [rsp+228h+var_50], rax
0x1800f6fac  mov     [rsp+228h+var_88], r9
0x1800f6fb4  mov     [rsp+228h+var_90], r8
0x1800f6fbc  mov     r13, rdx
0x1800f6fbf  mov     [rsp+228h+var_C8], rdx
0x1800f6fc7  mov     rbx, rcx
0x1800f6fca  mov     [rsp+228h+Path], rcx
0x1800f6fd2  mov     rax, [rsp+228h+arg_28]
0x1800f6fda  mov     qword ptr [rsp+228h+var_B8], rax
0x1800f6fe2  xor     eax, eax
0x1800f6fe4  xorps   xmm0, xmm0
0x1800f6fe7  movups  xmmword ptr [rsp+228h+ObjectAttributes.Length], xmm0
0x1800f6fef  movups  xmmword ptr [rsp+228h+ObjectAttributes.ObjectName], xmm0
0x1800f6ff7  movups  xmmword ptr [rsp+228h+ObjectAttributes+1Ch], xmm0
0x1800f6fff  mov     qword ptr [r11-1A0h], 0FFFFFFFFFFFFFFFFh
0x1800f700a  xor     r15d, r15d
0x1800f700d  mov     [r11-168h], r15
0x1800f7014  mov     [r11-198h], r15
0x1800f701b  movups  xmmword ptr [rsp+228h+IoStatusBlock], xmm0
0x1800f7023  mov     [r11-100h], r15
0x1800f702a  mov     sil, r15b
0x1800f702d  movups  [rsp+228h+var_A8], xmm0
0x1800f7035  mov     dword ptr [rsp+228h+var_98], eax
0x1800f703c  xorps   xmm1, xmm1
0x1800f703f  movups  xmmword ptr [r11-78h], xmm1
0x1800f7044  movups  xmmword ptr [r11-68h], xmm1
0x1800f7049  mov     [r11-58h], rax
0x1800f704d  mov     qword ptr [r11-148h], 0FFFFFFFFFFFFFFFFh
0x1800f7058  mov     [r11-178h], r15d
0x1800f705f  mov     [r11-180h], r15d
0x1800f7066  movups  xmmword ptr [rsp+228h+P], xmm0
0x1800f706e  movups  xmmword ptr [rsp+228h+var_118], xmm1
0x1800f7076  movups  xmmword ptr [rsp+228h+var_138], xmm0
0x1800f707e  mov     [r11-190h], r15
0x1800f7085  mov     [r11-160h], r15
0x1800f708c  test    rdx, rdx
0x1800f708f  jz      short loc_1800F70AD
0x1800f7091  mov     rcx, rdx; Name
0x1800f7094  call    cs:__imp_RtlIsDosDeviceName_U
0x1800f709a  test    eax, eax
0x1800f709c  jz      short loc_1800F70AD
0x1800f709e  mov     ecx, 0C0000035h
0x1800f70a3  call    BaseSetLastNTError
0x1800f70a8  jmp     loc_1800F7CCB
0x1800f70ad  xor     r9d, r9d; DirectoryInfo
0x1800f70b0  xor     r8d, r8d; NtFileNamePart
0x1800f70b3  lea     rdx, [rsp+228h+NtPathName]; NtPathName
0x1800f70bb  mov     rcx, rbx; DosPathName
0x1800f70be  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800f70c4  test    al, al
0x1800f70c6  jnz     short loc_1800F70CF
0x1800f70c8  mov     ecx, 0C000003Ah
0x1800f70cd  jmp     short loc_1800F70A3
0x1800f70cf  mov     r12d, [rsp+228h+arg_20]
0x1800f70d7  mov     edi, r12d
0x1800f70da  and     edi, 4
0x1800f70dd  jz      short loc_1800F70EC
0x1800f70df  test    r12b, 10h
0x1800f70e3  jz      short loc_1800F70EC
0x1800f70e5  mov     ecx, 0C000000Dh
0x1800f70ea  jmp     short loc_1800F70A3
0x1800f70ec  mov     al, r12b
0x1800f70ef  and     al, 1
0x1800f70f1  mov     [rsp+228h+var_1A8], al
0x1800f70f8  mov     [rsp+228h+ObjectAttributes.Length], 30h ; '0'
0x1800f7103  mov     [rsp+228h+ObjectAttributes.RootDirectory], r15
0x1800f710b  mov     [rsp+228h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f7116  lea     rax, [rsp+228h+NtPathName]
0x1800f711e  mov     [rsp+228h+ObjectAttributes.ObjectName], rax
0x1800f7126  xorps   xmm0, xmm0
0x1800f7129  movdqu  xmmword ptr [rsp+228h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f7132  mov     r14d, r12d
0x1800f7135  and     r14d, 8
0x1800f7139  or      r14d, 10080h
0x1800f7140  shr     r14d, 2
0x1800f7144  mov     r15d, r14d
0x1800f7147  bts     r15d, 15h
0x1800f714c  mov     [rsp+228h+OpenOptions], r15d; OpenOptions
0x1800f7151  mov     [rsp+228h+ShareAccess], 7; ShareAccess
0x1800f7159  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1800f7161  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x1800f7169  mov     edx, 110080h; DesiredAccess
0x1800f716e  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x1800f7176  call    cs:__imp_NtOpenFile
0x1800f717c  test    eax, eax
0x1800f717e  jns     short loc_1800F71FA
0x1800f7180  xor     r15d, r15d
0x1800f7183  test    edi, edi
0x1800f7185  jz      short loc_1800F71B2
0x1800f7187  lea     ecx, [rax+3FFFFFCCh]
0x1800f718d  cmp     ecx, 0Fh
0x1800f7190  ja      short loc_1800F71B2
0x1800f7192  mov     edx, 8041h
0x1800f7197  bt      edx, ecx
0x1800f719a  jnb     short loc_1800F71B2
0x1800f719c  mov     [rsp+228h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800f71a8  mov     ebx, 0C000000Dh
0x1800f71ad  jmp     loc_1800F7334
0x1800f71b2  mov     ebx, 0C000000Dh
0x1800f71b7  cmp     eax, ebx
0x1800f71b9  jnz     short loc_1800F71EB
0x1800f71bb  mov     [rsp+228h+OpenOptions], r14d; OpenOptions
0x1800f71c0  mov     [rsp+228h+ShareAccess], 3; ShareAccess
0x1800f71c8  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1800f71d0  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x1800f71d8  mov     edx, 110000h; DesiredAccess
0x1800f71dd  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x1800f71e5  call    cs:__imp_NtOpenFile
0x1800f71eb  test    eax, eax
0x1800f71ed  jns     loc_1800F7334
0x1800f71f3  mov     ecx, eax
0x1800f71f5  jmp     loc_1800F70A3
0x1800f71fa  mov     [rsp+228h+ShareAccess], 23h ; '#'; FileInformationClass
0x1800f7202  mov     r9d, 8; Length
0x1800f7208  lea     r8, [rsp+228h+FileInformation]; FileInformation
0x1800f7210  lea     rdx, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1800f7218  mov     rcx, [rsp+228h+FileHandle]; FileHandle
0x1800f7220  call    cs:__imp_NtQueryInformationFile
0x1800f7226  test    eax, eax
0x1800f7228  jns     short loc_1800F7249
0x1800f722a  cmp     eax, 0C0000002h
0x1800f722f  jz      short loc_1800F7249
0x1800f7231  mov     ebx, 0C000000Dh
0x1800f7236  cmp     eax, ebx
0x1800f7238  jz      short loc_1800F724E
0x1800f723a  mov     ecx, eax
0x1800f723c  call    BaseSetLastNTError
0x1800f7241  xor     r15d, r15d
0x1800f7244  jmp     loc_1800F7CCB
0x1800f7249  mov     ebx, 0C000000Dh
0x1800f724e  test    eax, eax
0x1800f7250  js      loc_1800F7331
0x1800f7256  test    [rsp+228h+FileInformation], 400h
0x1800f7261  jz      loc_1800F7331
0x1800f7267  mov     ecx, [rsp+228h+var_FC]
0x1800f726e  lea     eax, [rcx+5FFFFFFDh]
0x1800f7274  cmp     eax, 1Ah
0x1800f7277  ja      short loc_1800F7287
0x1800f7279  mov     edx, 4000201h
0x1800f727e  bt      edx, eax
0x1800f7281  jb      loc_1800F7331
0x1800f7287  lea     eax, [rcx+7FFFFFDDh]
0x1800f728d  cmp     eax, 3
0x1800f7290  jbe     loc_1800F7331
0x1800f7296  mov     rcx, [rsp+228h+FileHandle]; Handle
0x1800f729e  call    cs:__imp_NtClose
0x1800f72a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f72a8  mov     [rsp+228h+FileHandle], rax
0x1800f72b0  mov     [rsp+228h+OpenOptions], r14d; OpenOptions
0x1800f72b5  mov     [rsp+228h+ShareAccess], 3; ShareAccess
0x1800f72bd  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1800f72c5  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x1800f72cd  mov     edx, 110000h; DesiredAccess
0x1800f72d2  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x1800f72da  call    cs:__imp_NtOpenFile
0x1800f72e0  test    eax, eax
0x1800f72e2  jns     short loc_1800F7331
0x1800f72e4  lea     ecx, [rax+3FFFFD8Ah]
0x1800f72ea  test    ecx, 0FFFFFFFCh
0x1800f72f0  jnz     short loc_1800F7329
0x1800f72f2  cmp     eax, 0C0000277h
0x1800f72f7  jz      short loc_1800F7329
0x1800f72f9  mov     [rsp+228h+OpenOptions], r15d; OpenOptions
0x1800f72fe  mov     [rsp+228h+ShareAccess], 3; ShareAccess
0x1800f7306  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1800f730e  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x1800f7316  mov     edx, 110000h; DesiredAccess
0x1800f731b  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x1800f7323  call    cs:__imp_NtOpenFile
0x1800f7329  xor     r15d, r15d
0x1800f732c  jmp     loc_1800F71EB
0x1800f7331  xor     r15d, r15d
0x1800f7334  test    edi, edi
0x1800f7336  jz      short loc_1800F734F
0x1800f7338  test    r13, r13
0x1800f733b  jnz     short loc_1800F734F
0x1800f733d  xor     edx, edx; SourceString
0x1800f733f  lea     rcx, [rsp+228h+DestinationString]; DestinationString
0x1800f7347  call    cs:__imp_RtlInitUnicodeString
0x1800f734d  jmp     short loc_1800F736E
0x1800f734f  xor     r9d, r9d; DirectoryInfo
0x1800f7352  xor     r8d, r8d; NtFileNamePart
0x1800f7355  lea     rdx, [rsp+228h+DestinationString]; NtPathName
0x1800f735d  mov     rcx, r13; DosPathName
0x1800f7360  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800f7366  test    al, al
0x1800f7368  jz      loc_1800F70C8
0x1800f736e  test    edi, edi
0x1800f7370  jz      loc_1800F799E
0x1800f7376  mov     rax, gs:60h
0x1800f737f  mov     rcx, 800000000h
0x1800f7389  test    [rax+2C8h], rcx
0x1800f7390  jz      loc_1800F7425
0x1800f7396  movaps  xmm0, xmmword ptr [rsp+228h+NtPathName.Length]
0x1800f739e  movdqa  xmmword ptr [rsp+228h+var_118], xmm0
0x1800f73a7  mov     [rsp+228h+NtPathName.Buffer], r15
0x1800f73af  mov     edi, 30h ; '0'
0x1800f73b4  mov     edx, edi
0x1800f73b6  lea     r9, [rsp+228h+NtPathName]
0x1800f73be  xor     r8d, r8d
0x1800f73c1  lea     rcx, [rsp+228h+var_118]
0x1800f73c9  call    AssembleRegistryString
0x1800f73ce  cmp     [rsp+228h+DestinationString.Length], r15w
0x1800f73d7  jz      short loc_1800F741B
0x1800f73d9  movaps  xmm6, xmmword ptr [rsp+228h+DestinationString.Length]
0x1800f73e1  movaps  xmmword ptr [rsp+228h+var_138], xmm6
0x1800f73e9  mov     [rsp+228h+DestinationString.Buffer], r15
0x1800f73f1  movzx   r8d, [rsp+228h+var_1A8]
0x1800f73fa  mov     edx, edi
0x1800f73fc  lea     r9, [rsp+228h+DestinationString]
0x1800f7404  lea     rcx, [rsp+228h+var_138]
0x1800f740c  call    AssembleRegistryString
0x1800f7411  mov     edi, 2
0x1800f7416  jmp     loc_1800F7862
0x1800f741b  mov     edi, 2
0x1800f7420  jmp     loc_1800F7870
0x1800f7425  cmp     [rsp+228h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800f742e  jnz     short loc_1800F7473
0x1800f7430  mov     [rsp+228h+OpenOptions], 4020h; OpenOptions
0x1800f7438  mov     [rsp+228h+ShareAccess], 7; ShareAccess
0x1800f7440  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1800f7448  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x1800f7450  mov     edx, 100080h; DesiredAccess
0x1800f7455  lea     rcx, [rsp+228h+FileHandle]; FileHandle
0x1800f745d  call    cs:__imp_NtOpenFile
0x1800f7463  test    eax, eax
0x1800f7465  jns     short loc_1800F7473
0x1800f7467  mov     [rsp+228h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800f7473  mov     edi, 2
0x1800f7478  test    r13, r13
0x1800f747b  jz      loc_1800F75DB
0x1800f7481  xorps   xmm0, xmm0
0x1800f7484  movups  xmmword ptr [rsp+228h+P], xmm0
0x1800f748c  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800f7492  movzx   r8d, [rsp+228h+DestinationString.MaximumLength]
0x1800f749b  add     r8, rdi; Size
0x1800f749e  mov     rcx, gs:60h
0x1800f74a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800f74ab  call    cs:__imp_RtlAllocateHeap
0x1800f74b1  mov     [rsp+228h+P+8], rax
0x1800f74b9  test    rax, rax
0x1800f74bc  jz      loc_1800F75DB
0x1800f74c2  movzx   r8d, [rsp+228h+DestinationString.Length]; Size
0x1800f74cb  mov     rdx, [rsp+228h+DestinationString.Buffer]; Src
0x1800f74d3  mov     rcx, rax; void *
0x1800f74d6  call    memcpy_0
0x1800f74db  movzx   edx, [rsp+228h+DestinationString.Length]
0x1800f74e3  shr     edx, 1
0x1800f74e5  mov     [rsp+228h+var_188], edx
0x1800f74ec  mov     r8d, edx
0x1800f74ef  mov     ecx, edx
0x1800f74f1  mov     r9, [rsp+228h+P+8]
0x1800f74f9  test    r8d, r8d
0x1800f74fc  jz      short loc_1800F7518
0x1800f74fe  dec     ecx
0x1800f7500  mov     eax, ecx
0x1800f7502  cmp     word ptr [r9+rcx*2], 5Ch ; '\'
0x1800f7508  jz      short loc_1800F7518
0x1800f750a  mov     edx, ecx
0x1800f750c  mov     [rsp+228h+var_188], ecx
0x1800f7513  mov     r8d, ecx
0x1800f7516  jmp     short loc_1800F74F9
0x1800f7518  mov     ecx, r8d
0x1800f751b  mov     [r9+rcx*2], r15w
0x1800f7520  add     dx, dx
0x1800f7523  mov     word ptr [rsp+228h+P], dx
0x1800f752b  add     dx, di
0x1800f752e  mov     word ptr [rsp+228h+P+2], dx
0x1800f7536  mov     [rsp+228h+ObjectAttributes.Length], 30h ; '0'
0x1800f7541  mov     [rsp+228h+ObjectAttributes.RootDirectory], r15
0x1800f7549  mov     [rsp+228h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f7554  lea     rax, [rsp+228h+P]
0x1800f755c  mov     [rsp+228h+ObjectAttributes.ObjectName], rax
0x1800f7564  xorps   xmm0, xmm0
0x1800f7567  movdqu  xmmword ptr [rsp+228h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f7570  mov     [rsp+228h+OpenOptions], 4020h; OpenOptions
0x1800f7578  mov     [rsp+228h+ShareAccess], 7; ShareAccess
0x1800f7580  lea     r9, [rsp+228h+IoStatusBlock]; IoStatusBlock
0x1800f7588  lea     r8, [rsp+228h+ObjectAttributes]; ObjectAttributes
0x1800f7590  mov     edx, 100080h; DesiredAccess
0x1800f7595  lea     rcx, [rsp+228h+Handle]; FileHandle
0x1800f759d  call    cs:__imp_NtOpenFile
0x1800f75a3  test    eax, eax
0x1800f75a5  jns     short loc_1800F75B3
0x1800f75a7  mov     [rsp+228h+Handle], 0FFFFFFFFFFFFFFFFh
0x1800f75b3  mov     rcx, gs:60h
0x1800f75bc  mov     r8, [rsp+228h+P+8]; P
0x1800f75c4  xor     edx, edx; Flags
  ... truncated ...
```
