# ReplaceFileExInternal

- ea: `0x1800cd450`
- end: `0x1800ceb50`
- name: `ReplaceFileExInternal`
- size: `5888`
- prototype: `__int64 __usercall@<rax>(PCWSTR DosPathName@<rcx>, PCWSTR@<rdx>, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cd3f0`

## callees

- `0x1800134a0`
- `0x180013ec0`
- `0x1800486a0`
- `0x180048f30`
- `0x1800cd0f0`
- `0x1800cd124`
- `0x1800cd450`
- `0x1800ceb58`
- `0x1800cf0f4`
- `0x1800cfa60`
- `0x1800cfdf0`
- `0x180110c48`
- `0x18012d119`
- `0x18012daf0`
- `0x18012eecc`
- `0x180188eb9`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800cd56c`
- `ntdll!RtlInitUnicodeString` at `0x1800cd608`
- `ntdll!RtlInitUnicodeString` at `0x1800cd56c`
- `ntdll!RtlInitUnicodeString` at `0x1800cd608`
- `ntdll!NtQueryInformationFile` at `0x1800cd8b5`
- `ntdll!NtQueryInformationFile` at `0x1800cdc4f`
- `ntdll!NtQueryInformationFile` at `0x1800ce55c`
- `ntdll!NtQueryInformationFile` at `0x1800cd8b5`
- `ntdll!NtQueryInformationFile` at `0x1800cdc4f`
- `ntdll!NtQueryInformationFile` at `0x1800ce55c`
- `ntdll!NtOpenFile` at `0x1800cd6b3`
- `ntdll!NtOpenFile` at `0x1800cd6fe`
- `ntdll!NtOpenFile` at `0x1800cd743`
- `ntdll!NtOpenFile` at `0x1800cd81d`
- `ntdll!NtOpenFile` at `0x1800cd858`
- `ntdll!NtOpenFile` at `0x1800ce141`
- `ntdll!NtOpenFile` at `0x1800ce5c4`
- `ntdll!NtOpenFile` at `0x1800ce621`
- `ntdll!NtOpenFile` at `0x1800ce65c`
- `ntdll!NtOpenFile` at `0x1800ce6a6`
- `ntdll!NtOpenFile` at `0x1800ce752`
- `ntdll!NtOpenFile` at `0x1800ce78d`
- `ntdll!NtOpenFile` at `0x1800ce7d6`
- `ntdll!NtOpenFile` at `0x1800cd6b3`
- `ntdll!NtOpenFile` at `0x1800cd6fe`
- `ntdll!NtOpenFile` at `0x1800cd743`
- `ntdll!NtOpenFile` at `0x1800cd81d`
- `ntdll!NtOpenFile` at `0x1800cd858`
- `ntdll!NtOpenFile` at `0x1800ce141`
- `ntdll!NtOpenFile` at `0x1800ce5c4`
- `ntdll!NtOpenFile` at `0x1800ce621`
- `ntdll!NtOpenFile` at `0x1800ce65c`
- `ntdll!NtOpenFile` at `0x1800ce6a6`
- `ntdll!NtOpenFile` at `0x1800ce752`
- `ntdll!NtOpenFile` at `0x1800ce78d`
- `ntdll!NtOpenFile` at `0x1800ce7d6`
- `ntdll!wcslen` at `0x1800cda1a`
- `ntdll!wcslen` at `0x1800cddce`
- `ntdll!wcslen` at `0x1800cda1a`
- `ntdll!wcslen` at `0x1800cddce`
- `ntdll!NtSetInformationFile` at `0x1800cdc98`
- `ntdll!NtSetInformationFile` at `0x1800cdf5f`
- `ntdll!NtSetInformationFile` at `0x1800ce001`
- `ntdll!NtSetInformationFile` at `0x1800ce08f`
- `ntdll!NtSetInformationFile` at `0x1800ce1bb`
- `ntdll!NtSetInformationFile` at `0x1800ce365`
- `ntdll!NtSetInformationFile` at `0x1800ce39f`
- `ntdll!NtSetInformationFile` at `0x1800ce3d9`
- `ntdll!NtSetInformationFile` at `0x1800ce41e`
- `ntdll!NtSetInformationFile` at `0x1800cdc98`
- `ntdll!NtSetInformationFile` at `0x1800cdf5f`
- `ntdll!NtSetInformationFile` at `0x1800ce001`
- `ntdll!NtSetInformationFile` at `0x1800ce08f`
- `ntdll!NtSetInformationFile` at `0x1800ce1bb`
- `ntdll!NtSetInformationFile` at `0x1800ce365`
- `ntdll!NtSetInformationFile` at `0x1800ce39f`
- `ntdll!NtSetInformationFile` at `0x1800ce3d9`
- `ntdll!NtSetInformationFile` at `0x1800ce41e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800cd61f`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800cd766`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800cde81`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800cd61f`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800cd766`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800cde81`
- `ntdll!wcscpy_s` at `0x1800cdac3`
- `ntdll!wcscpy_s` at `0x1800ce2c1`
- `ntdll!wcscpy_s` at `0x1800ce2d8`
- `ntdll!wcscpy_s` at `0x1800cdac3`
- `ntdll!wcscpy_s` at `0x1800ce2c1`
- `ntdll!wcscpy_s` at `0x1800ce2d8`
- `ntdll!wcscat_s` at `0x1800cdad7`
- `ntdll!wcscat_s` at `0x1800cdad7`
- `ntdll!swprintf_s` at `0x1800cdaa7`
- `ntdll!swprintf_s` at `0x1800ce2a8`
- `ntdll!swprintf_s` at `0x1800cdaa7`
- `ntdll!swprintf_s` at `0x1800ce2a8`
- `ntdll!NtFsControlFile` at `0x1800cdd89`
- `ntdll!NtFsControlFile` at `0x1800ce489`
- `ntdll!NtFsControlFile` at `0x1800ce503`
- `ntdll!NtFsControlFile` at `0x1800ce913`
- `ntdll!NtFsControlFile` at `0x1800ceb33`
- `ntdll!NtFsControlFile` at `0x18018b82c`
- `ntdll!NtFsControlFile` at `0x18018b985`
- `ntdll!NtFsControlFile` at `0x1800cdd89`
- `ntdll!NtFsControlFile` at `0x1800ce489`
- `ntdll!NtFsControlFile` at `0x1800ce503`
- `ntdll!NtFsControlFile` at `0x1800ce913`
- `ntdll!NtFsControlFile` at `0x1800ceb33`
- `ntdll!NtFsControlFile` at `0x18018b82c`
- `ntdll!NtFsControlFile` at `0x18018b985`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800cd8f9`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800cd8f9`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce1eb`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce220`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce265`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce51c`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce717`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce807`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce897`
- `ntdll!RtlSetLastWin32Error` at `0x1800cea71`
- `ntdll!RtlSetLastWin32Error` at `0x1800cea9b`
- `ntdll!RtlSetLastWin32Error` at `0x18018b7bb`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce1eb`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce220`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce265`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce51c`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce717`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce807`
- `ntdll!RtlSetLastWin32Error` at `0x1800ce897`
- `ntdll!RtlSetLastWin32Error` at `0x1800cea71`
- `ntdll!RtlSetLastWin32Error` at `0x1800cea9b`
- `ntdll!RtlSetLastWin32Error` at `0x18018b7bb`
- `ntdll!NtClose` at `0x1800ce0c2`
- `ntdll!NtClose` at `0x1800ce587`
- `ntdll!NtClose` at `0x1800ce8c3`
- `ntdll!NtClose` at `0x1800ce91e`
- `ntdll!NtClose` at `0x18018b7cf`
- `ntdll!NtClose` at `0x18018b836`
- `ntdll!NtClose` at `0x1800ce0c2`
- `ntdll!NtClose` at `0x1800ce587`
- `ntdll!NtClose` at `0x1800ce8c3`
- `ntdll!NtClose` at `0x1800ce91e`
- `ntdll!NtClose` at `0x18018b7cf`
- `ntdll!NtClose` at `0x18018b836`
- `ntdll!NtDuplicateObject` at `0x1800cdb84`
- `ntdll!NtDuplicateObject` at `0x1800cdb84`
- `ntdll!RtlFreeHeap` at `0x1800ce93b`
- `ntdll!RtlFreeHeap` at `0x1800ce958`
- `ntdll!RtlFreeHeap` at `0x1800ce975`
- `ntdll!RtlFreeHeap` at `0x1800ce98d`
- `ntdll!RtlFreeHeap` at `0x1800ce9a5`
- `ntdll!RtlFreeHeap` at `0x1800cea14`
- `ntdll!RtlFreeHeap` at `0x18018b853`
- `ntdll!RtlFreeHeap` at `0x18018b86f`
- `ntdll!RtlFreeHeap` at `0x18018b88b`
- `ntdll!RtlFreeHeap` at `0x18018b8a7`
- `ntdll!RtlFreeHeap` at `0x18018b8c3`
- `ntdll!RtlFreeHeap` at `0x18018b9b7`
- `ntdll!RtlFreeHeap` at `0x1800ce93b`
- `ntdll!RtlFreeHeap` at `0x1800ce958`
- `ntdll!RtlFreeHeap` at `0x1800ce975`
- `ntdll!RtlFreeHeap` at `0x1800ce98d`
- `ntdll!RtlFreeHeap` at `0x1800ce9a5`
- `ntdll!RtlFreeHeap` at `0x1800cea14`
- `ntdll!RtlFreeHeap` at `0x18018b853`
- `ntdll!RtlFreeHeap` at `0x18018b86f`
- `ntdll!RtlFreeHeap` at `0x18018b88b`
- `ntdll!RtlFreeHeap` at `0x18018b8a7`
- `ntdll!RtlFreeHeap` at `0x18018b8c3`
- `ntdll!RtlFreeHeap` at `0x18018b9b7`
- `ntdll!RtlAllocateHeap` at `0x1800cda52`
- `ntdll!RtlAllocateHeap` at `0x1800cdeaf`
- `ntdll!RtlAllocateHeap` at `0x1800cdee9`
- `ntdll!RtlAllocateHeap` at `0x1800cda52`
- `ntdll!RtlAllocateHeap` at `0x1800cdeaf`
- `ntdll!RtlAllocateHeap` at `0x1800cdee9`
- `ext-ms-win-kernel32-file-l1-1-0!BasepSetFileEncryptionCompression` at `0x1800cdd11`
- `ext-ms-win-kernel32-file-l1-1-0!BasepSetFileEncryptionCompression` at `0x1800cdd11`

## pseudocode

```c
__int64 __fastcall ReplaceFileExInternal(
        wchar_t *DosPathName,
        PCWSTR a2,
        const WCHAR *a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  int v11; // esi
  WCHAR *v12; // r14
  int v13; // ebx
  _QWORD *v14; // r12
  int v15; // r13d
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  ACCESS_MASK v18; // r15d
  NTSTATUS v19; // eax
  int v20; // edi
  DWORD v21; // r14d
  __int64 v22; // rsi
  BOOL v23; // ebx
  int v24; // r15d
  int v25; // r13d
  __int64 FileW; // r14
  unsigned int v27; // esi
  int v28; // eax
  int v29; // edi
  unsigned int v30; // r13d
  unsigned __int64 v31; // rbx
  rsize_t v32; // rbx
  wchar_t *v33; // r14
  HANDLE StandardError; // rdx
  NTSTATUS v35; // eax
  int v36; // ecx
  bool v37; // zf
  int v38; // eax
  int v39; // eax
  unsigned int v40; // edi
  wchar_t *v41; // rbx
  __int16 v42; // dx
  __int16 i; // cx
  __int64 v44; // rax
  unsigned __int16 v45; // dx
  wchar_t *v46; // rsi
  int v47; // ebx
  unsigned __int64 v48; // r13
  _DWORD *Heap; // r15
  HANDLE v50; // rbx
  NTSTATUS v51; // eax
  HANDLE v52; // rbx
  NTSTATUS v53; // eax
  HANDLE v54; // r14
  NTSTATUS v55; // eax
  NTSTATUS v56; // ebx
  HANDLE v57; // r14
  NTSTATUS v58; // eax
  ULONG v59; // ecx
  int v60; // esi
  int v61; // eax
  ULONG v62; // ecx
  __int64 v63; // rcx
  ULONG LastErrorValue; // ebx
  HANDLE v66; // rbx
  __int64 ShareAccess; // [rsp+88h] [rbp-4C8h]
  __int64 OpenOptions; // [rsp+90h] [rbp-4C0h]
  unsigned int v69; // [rsp+C8h] [rbp-488h]
  int v70; // [rsp+CCh] [rbp-484h]
  HANDLE hDevice; // [rsp+D8h] [rbp-478h] BYREF
  wchar_t *Destination; // [rsp+E0h] [rbp-470h]
  HANDLE FileHandle; // [rsp+E8h] [rbp-468h] BYREF
  PVOID v74; // [rsp+F0h] [rbp-460h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-458h] BYREF
  int v76; // [rsp+108h] [rbp-448h]
  __int16 v77; // [rsp+10Ch] [rbp-444h]
  DWORD BytesReturned; // [rsp+110h] [rbp-440h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+118h] [rbp-438h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+128h] [rbp-428h]
  int v81; // [rsp+12Ch] [rbp-424h]
  unsigned int v82; // [rsp+130h] [rbp-420h]
  int v83; // [rsp+134h] [rbp-41Ch]
  int v84; // [rsp+138h] [rbp-418h]
  HANDLE TargetHandle; // [rsp+140h] [rbp-410h] BYREF
  wchar_t *String; // [rsp+148h] [rbp-408h]
  int v87; // [rsp+150h] [rbp-400h]
  struct _UNICODE_STRING DestinationString; // [rsp+158h] [rbp-3F8h] BYREF
  int v89[2]; // [rsp+168h] [rbp-3E8h]
  PVOID P; // [rsp+170h] [rbp-3E0h]
  PVOID v91; // [rsp+178h] [rbp-3D8h]
  int v92; // [rsp+180h] [rbp-3D0h]
  int v93; // [rsp+184h] [rbp-3CCh]
  __int64 OutputBuffer; // [rsp+188h] [rbp-3C8h] BYREF
  struct _OBJECT_ATTRIBUTES v95; // [rsp+190h] [rbp-3C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1C0h] [rbp-390h] BYREF
  _QWORD *v97; // [rsp+1F0h] [rbp-360h]
  __int64 v98; // [rsp+1F8h] [rbp-358h] BYREF
  PCWSTR DosPathNamea; // [rsp+200h] [rbp-350h]
  __int128 v100; // [rsp+208h] [rbp-348h] BYREF
  __int64 v101; // [rsp+218h] [rbp-338h]
  struct _UNICODE_STRING v102; // [rsp+220h] [rbp-330h] BYREF
  const WCHAR *v103; // [rsp+230h] [rbp-320h]
  int v104; // [rsp+238h] [rbp-318h]
  __int128 InputBuffer; // [rsp+240h] [rbp-310h] BYREF
  __int64 v106; // [rsp+250h] [rbp-300h]
  __int128 v107; // [rsp+258h] [rbp-2F8h] BYREF
  __int64 v108; // [rsp+268h] [rbp-2E8h]
  _OWORD FileInformation[2]; // [rsp+270h] [rbp-2E0h] BYREF
  int v110[2]; // [rsp+290h] [rbp-2C0h]
  _OWORD v111[2]; // [rsp+298h] [rbp-2B8h] BYREF
  __int64 v112; // [rsp+2B8h] [rbp-298h]
  char FsInformation[544]; // [rsp+2C8h] [rbp-288h] BYREF
  wchar_t Buffer[8]; // [rsp+4E8h] [rbp-68h] BYREF
  PVOID hTemplateFile; // [rsp+4F8h] [rbp-58h]

  DosPathNamea = a3;
  *(_QWORD *)v89 = a2;
  String = DosPathName;
  v103 = a3;
  FileHandle = (HANDLE)-1LL;
  hDevice = (HANDLE)-1LL;
  NtPathName = 0;
  v102 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v95, 0, 44);
  IoStatusBlock = 0;
  v11 = 0;
  v69 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  *(_QWORD *)v110 = 0;
  memset(v111, 0, sizeof(v111));
  v112 = 0;
  v12 = 0;
  Destination = 0;
  v98 = 0;
  memset_0(FsInformation, 0, 0x218u);
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !DosPathName )
    goto LABEL_175;
  if ( !a2 )
    goto LABEL_175;
  if ( a7 )
    goto LABEL_175;
  if ( a8 )
    goto LABEL_175;
  P = 0;
  v91 = 0;
  v13 = 0;
  v74 = 0;
  v14 = 0;
  v97 = 0;
  BytesReturned = 0;
  v81 = 0;
  v93 = 1;
  v84 = 0;
  v87 = 0;
  if ( (a4 & 0xFFFFFFF8) != 0 )
  {
LABEL_175:
    RtlSetLastWin32Error(0x57u);
    return v69;
  }
  RtlInitUnicodeString(&NtPathName, 0);
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
    goto LABEL_120;
  P = NtPathName.Buffer;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15 = 18022538;
  DesiredAccess = 18022538;
  if ( NtOpenFile(&FileHandle, 0x113008Au, &ObjectAttributes, &IoStatusBlock, 7u, 0x200060u) < 0 )
  {
    v15 = 1245322;
    DesiredAccess = 1245322;
    if ( NtOpenFile(&FileHandle, 0x13008Au, &ObjectAttributes, &IoStatusBlock, 7u, 0x200060u) < 0 )
    {
      v15 = 1245320;
      DesiredAccess = 1245320;
      v16 = NtOpenFile(&FileHandle, 0x130088u, &ObjectAttributes, &IoStatusBlock, 7u, 0x200060u);
      if ( v16 < 0 )
      {
        BaseSetLastNTError((unsigned int)v16);
        goto LABEL_98;
      }
    }
  }
  if ( !RtlDosPathNameToNtPathName_U(a2, &v102, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    goto LABEL_98;
  }
  LODWORD(TargetHandle) = v15 & 2;
  v91 = v102.Buffer;
  v95.Length = 48;
  v95.RootDirectory = 0;
  v95.Attributes = 64;
  v95.ObjectName = &v102;
  *(_OWORD *)&v95.SecurityDescriptor = 0;
  if ( (v15 & 0x1000000) != 0 )
  {
    v13 = -1055064064;
    v76 = -1055064064;
    v17 = NtOpenFile(&hDevice, 0xC11D0000, &v95, &IoStatusBlock, 0, 0x60u);
    if ( v17 < 0 )
    {
      v13 = -1055588352;
      v76 = -1055588352;
      v17 = NtOpenFile(&hDevice, 0xC1150000, &v95, &IoStatusBlock, 0, 0x60u);
    }
  }
  else
  {
    v17 = -1073741790;
  }
  if ( v17 < 0 )
  {
    v13 = -1071841280;
    v76 = -1071841280;
    v17 = NtOpenFile(&hDevice, 0xC01D0000, &v95, &IoStatusBlock, 0, 0x60u);
    if ( v17 < 0 )
    {
      v13 = -1072365568;
      v76 = -1072365568;
      v17 = NtOpenFile(&hDevice, 0xC0150000, &v95, &IoStatusBlock, 0, 0x60u);
    }
  }
  if ( v17 == -1073741790 )
  {
    if ( (a4 & 6) != 0 )
    {
      v13 = -1072627712;
      v76 = -1072627712;
      v17 = NtOpenFile(&hDevice, 0xC0110000, &v95, &IoStatusBlock, 0, 0x60u);
    }
    if ( v17 == -1073741790 )
    {
      if ( (a4 & 2) != 0 )
      {
        v13 = -2145583104;
        v76 = -2145583104;
        v17 = NtOpenFile(&hDevice, 0x801D0000, &v95, &IoStatusBlock, 0, 0x60u);
        if ( v17 < 0 )
        {
          v13 = -2146107392;
          v76 = -2146107392;
          v17 = NtOpenFile(&hDevice, 0x80150000, &v95, &IoStatusBlock, 0, 0x60u);
        }
      }
      if ( v17 == -1073741790 && (a4 & 2) != 0 )
      {
        v13 = -2146369536;
        v76 = -2146369536;
        v17 = NtOpenFile(&hDevice, 0x80110000, &v95, &IoStatusBlock, 0, 0x60u);
      }
    }
  }
  if ( v17 < 0 )
    goto LABEL_62;
  if ( a6 )
  {
    InputBuffer = 0;
    v106 = 0;
    LODWORD(InputBuffer) = a6;
    v19 = NtFsControlFile(hDevice, 0, 0, 0, &IoStatusBlock, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
    if ( v19 < 0 )
      goto LABEL_117;
  }
  v18 = DesiredAccess;
  while ( 1 )
  {
    v19 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    if ( v19 < 0 )
    {
      v20 = a4 & 2;
      if ( !v20 )
        goto LABEL_117;
      v21 = 1;
      goto LABEL_23;
    }
    if ( v11 || (v110[0] & 0x400) == 0 )
    {
      if ( a5 )
      {
        v107 = 0;
        v108 = 0;
        LODWORD(v107) = a5;
        v19 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900FCu, &v107, 0x18u, 0, 0);
        if ( v19 < 0 )
          goto LABEL_117;
      }
      if ( (v110[0] & 1) != 0 )
      {
        v63 = 3221225506LL;
LABEL_145:
        BaseSetLastNTError(v63);
        goto LABEL_97;
      }
      v19 = NtQueryInformationFile(hDevice, &IoStatusBlock, v111, 0x28u, FileBasicInformation);
      v20 = a4 & 2;
      if ( v19 < 0 )
      {
        if ( !v20 )
          goto LABEL_117;
        v81 = 1;
        v104 = 1;
      }
      memset((char *)FileInformation + 8, 0, 24);
      v19 = NtSetInformationFile(hDevice, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      if ( v19 < 0 && !v20 )
      {
LABEL_117:
        v63 = (unsigned int)v19;
        goto LABEL_145;
      }
      v21 = BytesReturned;
LABEL_23:
      v19 = NtQueryVolumeInformationFile(hDevice, &IoStatusBlock, FsInformation, 0x218u, FileFsAttributeInformation);
      if ( v19 < 0 )
      {
        if ( !v20 )
          goto LABEL_117;
        v22 = *(_QWORD *)v89;
      }
      else
      {
        BytesReturned = 0;
        v22 = *(_QWORD *)v89;
        if ( !(unsigned int)BasepCopySecurityInformation(
                              (int)String,
                              (int)FileHandle,
                              v18,
                              v89[0],
                              hDevice,
                              v13,
                              0x3Cu,
                              0,
                              FsInformation[0],
                              (__int64)&BytesReturned,
                              1) )
          goto LABEL_97;
      }
      v23 = v20 != 0;
      if ( !(unsigned int)BasepCopyAlternateDataStreams(FileHandle, ShareAccess, OpenOptions) )
        goto LABEL_97;
      if ( v21 )
      {
        v24 = -1;
      }
      else
      {
        v24 = -1;
        v37 = (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() == 0;
        v38 = v112;
        if ( v37 )
        {
          if ( v81 )
            v38 = -1;
          v39 = BasepTransferEncryption(&hDevice, &v95, v110[0], v38, v23);
        }
        else
        {
          if ( v81 )
            v38 = -1;
          v39 = BasepSetFileEncryptionCompression(FileHandle, &hDevice, &v95, String, v22, v110[0], v38, v23);
        }
        if ( !v39 )
        {
LABEL_97:
          v12 = Destination;
          goto LABEL_98;
        }
        if ( a6 )
        {
          *(_OWORD *)Buffer = 0;
          hTemplateFile = 0;
          *(_DWORD *)Buffer = a6;
          v25 = 0;
          v17 = NtFsControlFile(hDevice, 0, 0, 0, &IoStatusBlock, 0x900FCu, Buffer, 0x18u, 0, 0);
          if ( v17 < 0 )
            goto LABEL_62;
LABEL_29:
          DeviceIoControl(hDevice, 0x900A0u, 0, 0, 0, 0, &BytesReturned, 0);
          if ( (_DWORD)TargetHandle )
          {
            TargetHandle = (HANDLE)-1LL;
            StandardError = FileHandle;
            switch ( (_DWORD)FileHandle )
            {
              case 0xFFFFFFF4:
                StandardError = NtCurrentPeb()->ProcessParameters->StandardError;
                break;
              case 0xFFFFFFF5:
                StandardError = NtCurrentPeb()->ProcessParameters->StandardOutput;
                break;
              case 0xFFFFFFF6:
                StandardError = NtCurrentPeb()->ProcessParameters->StandardInput;
                break;
            }
            v35 = NtDuplicateObject(
                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                    StandardError,
                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                    &TargetHandle,
                    0,
                    0,
                    2u);
            if ( v35 < 0 )
            {
              BaseSetLastNTError((unsigned int)v35);
            }
            else
            {
              v70 = BasepNotifyTrackingService(&TargetHandle, &ObjectAttributes);
              v36 = v84;
              if ( v70 >= 0 )
                v36 = 1;
              v84 = v36;
              v87 = v36;
              if ( TargetHandle != (HANDLE)-1LL )
                CloseHandle(TargetHandle);
            }
          }
          if ( !DosPathNamea )
          {
            FileW = -1;
            v27 = 0;
            v82 = 0;
            v28 = wcslen(String);
            v29 = 0;
            v92 = 0;
            v30 = 2 * v28 + 32;
            v31 = v30;
            TargetHandle = (HANDLE)v30;
            Destination = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v30);
            if ( Destination )
            {
              while ( 1 )
              {
                if ( FileW != -1 )
                  goto LABEL_72;
                if ( v27 >= 0x10 )
                  break;
                swprintf_s(
                  Buffer,
                  0x10u,
                  L"~RF%4x.TMP",
                  v27 + (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24));
                v32 = v31 >> 1;
                v33 = Destination;
                wcscpy_s(Destination, v32, String);
                wcscat_s(v33, v32, Buffer);
                FileW = (__int64)CreateFileW(v33, 0x40010000u, 0, 0, 1u, 0x102u, 0);
                if ( FileW == -1 )
                {
                  if ( NtCurrentTeb()->LastErrorValue == 80 )
                    v29 = 1;
                  v92 = v29;
                }
                v82 = ++v27;
                v31 = v30;
              }
              if ( !v29 )
              {
                v40 = 0;
                v77 = 0;
                v41 = String;
                v42 = wcslen(String);
                *(_QWORD *)v89 = 0;
                for ( i = v42 - 1; ; --i )
                {
                  v77 = i;
                  v44 = i;
                  if ( i < 0 || v41[i] == 92 )
                    break;
                }
                v45 = v42 - i - 1;
                if ( v45 )
                {
                  if ( v45 < 8u )
                    v24 = (1 << (4 * v45)) - 1;
                  v46 = &Destination[v44 + 1];
                  *(_QWORD *)v89 = v46;
                  v47 = v30 - (v44 * 2 + 2);
                  v82 = 0;
                  v48 = (unsigned __int64)TargetHandle;
                  while ( FileW == -1 )
                  {
                    if ( v40 >= 0x10 )
                      goto LABEL_96;
                    swprintf_s(
                      Buffer,
                      0x10u,
                      L"%x",
                      v24 & (v40 + (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24)));
                    wcscpy_s(Destination, v48 >> 1, String);
                    wcscpy_s(v46, (unsigned __int64)v47 >> 1, Buffer);
                    FileW = (__int64)CreateFileW(Destination, 0x40010000u, 0, 0, 1u, 0x102u, 0);
                    v82 = ++v40;
                  }
LABEL_72:
                  CloseHandle((HANDLE)FileW);
                  v12 = Destination;
                  v25 = 0;
                  goto LABEL_73;
                }
              }
            }
LABEL_96:
            RtlSetLastWin32Error(0x497u);
            goto LABEL_97;
          }
          v12 = (WCHAR *)DosPathNamea;
          Destination = (wchar_t *)DosPathNamea;
LABEL_73:
          if ( RtlDosPathNameToNtPathName_U(v12, &DestinationString, 0, 0) )
          {
            Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, DestinationString.Length + 24LL);
            v74 = Heap;
            if ( Heap )
            {
              v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, NtPathName.Length + 24LL);
              v97 = v14;
              if ( v14 )
              {
                v50 = FileHandle;
                *((_QWORD *)Heap + 1) = 0;
                Heap[4] = DestinationString.Length;
                memcpy_0(Heap + 5, DestinationString.Buffer, DestinationString.Length);
                *Heap = 5;
                v51 = NtSetInformationFile(
                        v50,
                        &IoStatusBlock,
                        Heap,
                        DestinationString.Length + 24,
                        (FILE_INFORMATION_CLASS)65);
                if ( v51 == -1073741811 || v51 == -1073741637 )
                {
                  v83 = 0;
                  *(_BYTE *)Heap = 1;
                  v51 = NtSetInformationFile(
                          v50,
                          &IoStatusBlock,
                          Heap,
                          DestinationString.Length + 24,
                          FileRenameInformation);
                }
                else
                {
                  v25 = v93;
                }
                if ( v51 < 0 )
                {
                  RtlSetLastWin32Error(0x497u);
                  goto LABEL_99;
                }
                v52 = hDevice;
                v14[1] = 0;
                *((_DWORD *)v14 + 4) = NtPathName.Length;
                memcpy_0((char *)v14 + 20, NtPathName.Buffer, NtPathName.Length);
                if ( v25 )
                {
                  *(_DWORD *)v14 = 5;
                  v53 = NtSetInformationFile(
                          v52,
                          &IoStatusBlock,
                          v14,
                          NtPathName.Length + 24,
                          (FILE_INFORMATION_CLASS)65);
                  if ( v53 != -1073741811 && v53 != -1073741637 )
                  {
LABEL_83:
                    if ( v53 >= 0 )
                    {
                      v61 = 1;
                      v69 = 1;
                      Heap = v74;
                      v60 = 0;
                      goto LABEL_157;
                    }
                    v54 = FileHandle;
                    v14[1] = 0;
                    *((_DWORD *)v14 + 4) = NtPathName.Length;
                    memcpy_0((char *)v14 + 20, NtPathName.Buffer, NtPathName.Length);
                    if ( v25 )
                    {
                      *(_DWORD *)v14 = 5;
                      v55 = NtSetInformationFile(
                              v54,
                              &IoStatusBlock,
                              v14,
                              NtPathName.Length + 24,
                              (FILE_INFORMATION_CLASS)65);
                      v56 = v55;
                      if ( v55 != -1073741811 && v55 != -1073741637 )
                      {
LABEL_87:
                        if ( v56 != -1073741611 )
                          goto LABEL_92;
                        NtClose(FileHandle);
                        FileHandle = (HANDLE)-1LL;
                        ObjectAttributes.Length = 48;
                        ObjectAttributes.RootDirectory = 0;
                        ObjectAttributes.Attributes = 64;
                        ObjectAttributes.ObjectName = &DestinationString;
                        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                        if ( NtOpenFile(&FileHandle, DesiredAccess, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u) < 0 )
                          goto LABEL_92;
                        v57 = FileHandle;
                        v14[1] = 0;
                        *((_DWORD *)v14 + 4) = NtPathName.Length;
                        memcpy_0((char *)v14 + 20, NtPathName.Buffer, NtPathName.Length);
                        if ( v25 )
                        {
                          *(_DWORD *)v14 = 5;
                          v58 = NtSetInformationFile(
                                  v57,
                                  &IoStatusBlock,
                                  v14,
                                  NtPathName.Length + 24,
                                  (FILE_INFORMATION_CLASS)65);
                          v56 = v58;
                          if ( v58 != -1073741811 && v58 != -1073741637 )
                            goto LABEL_92;
                          v83 = 0;
                        }
                        *(_BYTE *)v14 = 1;
                        v56 = NtSetInformationFile(
                                v57,
                                &IoStatusBlock,
                                v14,
                                NtPathName.Length + 24,
                                FileRenameInformation);
LABEL_92:
                        v59 = 1177;
                        if ( v56 >= 0 )
                          v59 = 1176;
                        RtlSetLastWin32Error(v59);
                        v60 = 1;
                        v12 = Destination;
                        Heap = v74;
                        goto LABEL_100;
                      }
                      v25 = 0;
                      v83 = 0;
                    }
                    *(_BYTE *)v14 = 1;
                    v56 = NtSetInformationFile(v54, &IoStatusBlock, v14, NtPathName.Length + 24, FileRenameInformation);
                    goto LABEL_87;
                  }
                  v25 = 0;
                  v83 = 0;
                }
                *(_BYTE *)v14 = 1;
                v53 = NtSetInformationFile(v52, &IoStatusBlock, v14, NtPathName.Length + 24, FileRenameInformation);
                goto LABEL_83;
              }
              v62 = 1176;
            }
            else
            {
              v62 = 1175;
            }
            RtlSetLastWin32Error(v62);
            goto LABEL_99;
          }
LABEL_120:
          RtlSetLastWin32Error(3u);
          goto LABEL_98;
        }
      }
      v25 = 0;
      goto LABEL_29;
    }
    v11 = 1;
    v17 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v98, 8u, FileAttributeTagInformation);
    if ( v17 < 0 || (v98 & 0x2000000000000000LL) != 0 )
      break;
    NtClose(FileHandle);
    FileHandle = (HANDLE)-1LL;
    v19 = NtOpenFile(&FileHandle, v18, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
    if ( v19 < 0 )
      goto LABEL_117;
  }
  if ( v17 < 0 )
  {
LABEL_62:
    BaseSetLastNTError((unsigned int)v17);
    goto LABEL_63;
  }
  RtlSetLastWin32Error(0x5B8u);
LABEL_63:
  v12 = Destination;
LABEL_98:
  Heap = v74;
LABEL_99:
  v60 = 0;
LABEL_100:
  v61 = 0;
LABEL_157:
  if ( !v61 && v84 && hDevice != (HANDLE)-1LL && FileHandle != (HANDLE)-1LL )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    BasepNotifyTrackingService(&hDevice, &v95);
    RtlSetLastWin32Error(LastErrorValue);
  }
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  if ( hDevice != (HANDLE)-1LL )
  {
    OutputBuffer = 0;
    NtFsControlFile(hDevice, 0, 0, 0, &IoStatusBlock, 0x900EFu, 0, 0, &OutputBuffer, 8u);
    NtClose(hDevice);
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v91);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v12 && v12 != DosPathNamea )
  {
    if ( !v60 )
    {
      if ( a5 )
      {
        v66 = CreateFileW(v12, 0x10000u, 0, 0, 3u, 0x200080u, 0);
        if ( v66 != (HANDLE)-1LL )
        {
          v100 = 0;
          v101 = 0;
          LODWORD(v100) = a5;
          NtFsControlFile(v66, 0, 0, 0, &IoStatusBlock, 0x900FCu, &v100, 0x18u, 0, 0);
          BaseMarkFileForDelete(v66);
          CloseHandle(v66);
        }
      }
      else if ( !(unsigned int)InternalDeleteFileW(v12, 0) && NtCurrentTeb()->LastErrorValue )
      {
        IsBrokeredCreateDirectoryWPresent();
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  }
  return v69;
}

```

## disassembly

```asm
0x1800cd450  mov     r11, rsp
0x1800cd453  push    rbx
0x1800cd454  push    rsi
0x1800cd455  push    rdi
0x1800cd456  push    r12
0x1800cd458  push    r13
0x1800cd45a  push    r14
0x1800cd45c  push    r15
0x1800cd45e  sub     rsp, 4B0h
0x1800cd465  mov     rax, cs:__security_cookie
0x1800cd46c  xor     rax, rsp
0x1800cd46f  mov     [rsp+4E8h+var_48], rax
0x1800cd477  mov     edi, r9d
0x1800cd47a  mov     rax, r8
0x1800cd47d  mov     [rsp+4E8h+DosPathName], rax
0x1800cd485  mov     r15, rdx
0x1800cd488  mov     qword ptr [rsp+4E8h+var_3E8], rdx
0x1800cd490  mov     r13, rcx
0x1800cd493  mov     [rsp+4E8h+String], rcx
0x1800cd49b  mov     [rsp+4E8h+var_320], rax
0x1800cd4a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cd4a7  mov     [r11-468h], rax
0x1800cd4ae  mov     [rsp+4E8h+hDevice], rax
0x1800cd4b3  xorps   xmm0, xmm0
0x1800cd4b6  movups  xmmword ptr [rsp+4E8h+NtPathName.Length], xmm0
0x1800cd4be  xorps   xmm1, xmm1
0x1800cd4c1  movups  xmmword ptr [rsp+4E8h+var_330.Length], xmm1
0x1800cd4c9  movups  xmmword ptr [rsp+4E8h+DestinationString.Length], xmm0
0x1800cd4d1  xor     eax, eax
0x1800cd4d3  movups  xmmword ptr [rsp+4E8h+ObjectAttributes.Length], xmm0
0x1800cd4db  movups  xmmword ptr [rsp+4E8h+ObjectAttributes.ObjectName], xmm0
0x1800cd4e3  movups  xmmword ptr [rsp+4E8h+ObjectAttributes+1Ch], xmm0
0x1800cd4eb  movups  xmmword ptr [rsp+4E8h+var_3C0.Length], xmm0
0x1800cd4f3  movups  xmmword ptr [rsp+4E8h+var_3C0.ObjectName], xmm0
0x1800cd4fb  movups  xmmword ptr [rsp+4E8h+var_3C0+1Ch], xmm0
0x1800cd503  movups  xmmword ptr [rsp+4E8h+IoStatusBlock], xmm0
0x1800cd50b  xor     esi, esi
0x1800cd50d  mov     [rsp+4E8h+var_488], esi
0x1800cd511  movups  [rsp+4E8h+FileInformation], xmm0
0x1800cd519  movups  [rsp+4E8h+var_2D0], xmm0
0x1800cd521  mov     [r11-2C0h], rax
0x1800cd528  movups  [rsp+4E8h+var_2B8], xmm1
0x1800cd530  movups  [rsp+4E8h+var_2A8], xmm1
0x1800cd538  mov     [r11-298h], rax
0x1800cd53f  mov     r14d, esi
0x1800cd542  mov     [rsp+4E8h+Destination], rsi
0x1800cd547  mov     [r11-358h], rsi
0x1800cd54e  xor     edx, edx; Val
0x1800cd550  mov     r8d, 218h; Size
0x1800cd556  lea     rcx, [r11-288h]; void *
0x1800cd55d  call    memset_0
0x1800cd562  xor     edx, edx; SourceString
0x1800cd564  lea     rcx, [rsp+4E8h+DestinationString]; DestinationString
0x1800cd56c  call    cs:__imp_RtlInitUnicodeString
0x1800cd572  test    r13, r13
0x1800cd575  jz      loc_1800CEA96
0x1800cd57b  test    r15, r15
0x1800cd57e  jz      loc_1800CEA96
0x1800cd584  cmp     [rsp+4E8h+arg_30], rsi
0x1800cd58c  jnz     loc_1800CEA96
0x1800cd592  cmp     [rsp+4E8h+arg_38], rsi
0x1800cd59a  jnz     loc_1800CEA96
0x1800cd5a0  mov     [rsp+4E8h+P], rsi
0x1800cd5a8  mov     [rsp+4E8h+var_3D8], rsi
0x1800cd5b0  mov     ebx, esi
0x1800cd5b2  mov     [rsp+4E8h+var_460], rsi
0x1800cd5ba  mov     r12d, esi
0x1800cd5bd  mov     [rsp+4E8h+var_360], rsi
0x1800cd5c5  mov     [rsp+4E8h+BytesReturned], esi
0x1800cd5cc  mov     [rsp+4E8h+var_424], esi
0x1800cd5d3  mov     [rsp+4E8h+var_3CC], 1
0x1800cd5de  xor     eax, eax
0x1800cd5e0  mov     [rsp+4E8h+var_480], eax
0x1800cd5e4  mov     [rsp+4E8h+var_418], eax
0x1800cd5eb  mov     [rsp+4E8h+var_400], eax
0x1800cd5f2  test    edi, 0FFFFFFF8h
0x1800cd5f8  jnz     loc_1800CEA96
0x1800cd5fe  xor     edx, edx; SourceString
0x1800cd600  lea     rcx, [rsp+4E8h+NtPathName]; DestinationString
0x1800cd608  call    cs:__imp_RtlInitUnicodeString
0x1800cd60e  xor     r9d, r9d; DirectoryInfo
0x1800cd611  xor     r8d, r8d; NtFileNamePart
0x1800cd614  lea     rdx, [rsp+4E8h+NtPathName]; NtPathName
0x1800cd61c  mov     rcx, r13; DosPathName
0x1800cd61f  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800cd625  xor     r13d, r13d
0x1800cd628  test    al, al
0x1800cd62a  jz      loc_1800CE517
0x1800cd630  mov     rax, [rsp+4E8h+NtPathName.Buffer]
0x1800cd638  mov     [rsp+4E8h+P], rax
0x1800cd640  mov     [rsp+4E8h+ObjectAttributes.Length], 30h ; '0'
0x1800cd64b  mov     [rsp+4E8h+ObjectAttributes.RootDirectory], r13
0x1800cd653  mov     [rsp+4E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800cd65e  lea     rax, [rsp+4E8h+NtPathName]
0x1800cd666  mov     [rsp+4E8h+ObjectAttributes.ObjectName], rax
0x1800cd66e  xorps   xmm0, xmm0
0x1800cd671  movdqu  xmmword ptr [rsp+4E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800cd67a  mov     r13d, 113008Ah
0x1800cd680  mov     [rsp+4E8h+DesiredAccess], r13d
0x1800cd688  mov     dword ptr [rsp+4E8h+OpenOptions], 200060h; OpenOptions
0x1800cd690  mov     [rsp+4E8h+ShareAccess], 7; ShareAccess
0x1800cd698  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800cd6a0  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x1800cd6a8  mov     edx, r13d; DesiredAccess
0x1800cd6ab  lea     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800cd6b3  call    cs:__imp_NtOpenFile
0x1800cd6b9  mov     [rsp+4E8h+var_484], eax
0x1800cd6bd  test    eax, eax
0x1800cd6bf  jns     loc_1800CD755
0x1800cd6c5  mov     r13d, 13008Ah
0x1800cd6cb  mov     [rsp+4E8h+DesiredAccess], r13d
0x1800cd6d3  mov     dword ptr [rsp+4E8h+OpenOptions], 200060h; OpenOptions
0x1800cd6db  mov     [rsp+4E8h+ShareAccess], 7; ShareAccess
0x1800cd6e3  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800cd6eb  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x1800cd6f3  mov     edx, r13d; DesiredAccess
0x1800cd6f6  lea     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800cd6fe  call    cs:__imp_NtOpenFile
0x1800cd704  mov     [rsp+4E8h+var_484], eax
0x1800cd708  test    eax, eax
0x1800cd70a  jns     short loc_1800CD755
0x1800cd70c  and     r13d, 0FFFFFFFDh
0x1800cd710  mov     [rsp+4E8h+DesiredAccess], r13d
0x1800cd718  mov     dword ptr [rsp+4E8h+OpenOptions], 200060h; OpenOptions
0x1800cd720  mov     [rsp+4E8h+ShareAccess], 7; ShareAccess
0x1800cd728  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800cd730  lea     r8, [rsp+4E8h+ObjectAttributes]; ObjectAttributes
0x1800cd738  mov     edx, r13d; DesiredAccess
0x1800cd73b  lea     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800cd743  call    cs:__imp_NtOpenFile
0x1800cd749  mov     [rsp+4E8h+var_484], eax
0x1800cd74d  test    eax, eax
0x1800cd74f  js      loc_1800CE3E6
0x1800cd755  xor     r9d, r9d; DirectoryInfo
0x1800cd758  xor     r8d, r8d; NtFileNamePart
0x1800cd75b  lea     rdx, [rsp+4E8h+var_330]; NtPathName
0x1800cd763  mov     rcx, r15; DosPathName
0x1800cd766  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800cd76c  xor     ecx, ecx
0x1800cd76e  test    al, al
0x1800cd770  jz      loc_1800CE712
0x1800cd776  mov     eax, r13d
0x1800cd779  and     eax, 2
0x1800cd77c  mov     dword ptr [rsp+4E8h+TargetHandle], eax
0x1800cd783  mov     rax, [rsp+4E8h+var_330.Buffer]
0x1800cd78b  mov     [rsp+4E8h+var_3D8], rax
0x1800cd793  mov     [rsp+4E8h+var_3C0.Length], 30h ; '0'
0x1800cd79e  mov     [rsp+4E8h+var_3C0.RootDirectory], rcx
0x1800cd7a6  mov     [rsp+4E8h+var_3C0.Attributes], 40h ; '@'
0x1800cd7b1  lea     rax, [rsp+4E8h+var_330]
0x1800cd7b9  mov     [rsp+4E8h+var_3C0.ObjectName], rax
0x1800cd7c1  xorps   xmm0, xmm0
0x1800cd7c4  movdqu  xmmword ptr [rsp+4E8h+var_3C0.SecurityDescriptor], xmm0
0x1800cd7cd  lea     r15d, [rcx+60h]
0x1800cd7d1  bt      r13d, 18h
0x1800cd7d6  jb      loc_1800CE722
0x1800cd7dc  mov     r14d, 0C0000022h
0x1800cd7e2  mov     eax, r14d
0x1800cd7e5  xor     r13d, r13d
0x1800cd7e8  mov     [rsp+4E8h+var_484], eax
0x1800cd7ec  test    eax, eax
0x1800cd7ee  jns     short loc_1800CD862
0x1800cd7f0  mov     ebx, 0C01D0000h
0x1800cd7f5  mov     [rsp+4E8h+var_448], ebx
0x1800cd7fc  mov     dword ptr [rsp+4E8h+OpenOptions], r15d; OpenOptions
0x1800cd801  mov     [rsp+4E8h+ShareAccess], r13d; ShareAccess
0x1800cd806  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800cd80e  lea     r8, [rsp+4E8h+var_3C0]; ObjectAttributes
0x1800cd816  mov     edx, ebx; DesiredAccess
0x1800cd818  lea     rcx, [rsp+4E8h+hDevice]; FileHandle
0x1800cd81d  call    cs:__imp_NtOpenFile
0x1800cd823  mov     [rsp+4E8h+var_484], eax
0x1800cd827  test    eax, eax
0x1800cd829  jns     short loc_1800CD862
0x1800cd82b  mov     ebx, 0C0150000h
0x1800cd830  mov     [rsp+4E8h+var_448], ebx
0x1800cd837  mov     dword ptr [rsp+4E8h+OpenOptions], r15d; OpenOptions
0x1800cd83c  mov     [rsp+4E8h+ShareAccess], r13d; ShareAccess
0x1800cd841  lea     r9, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800cd849  lea     r8, [rsp+4E8h+var_3C0]; ObjectAttributes
0x1800cd851  mov     edx, ebx; DesiredAccess
0x1800cd853  lea     rcx, [rsp+4E8h+hDevice]; FileHandle
0x1800cd858  call    cs:__imp_NtOpenFile
0x1800cd85e  mov     [rsp+4E8h+var_484], eax
0x1800cd862  cmp     eax, r14d
0x1800cd865  jz      loc_1800CE5DB
0x1800cd86b  test    eax, eax
0x1800cd86d  js      loc_1800CDD9B
0x1800cd873  mov     r13d, [rsp+4E8h+arg_28]
0x1800cd87b  xor     r15d, r15d
0x1800cd87e  test    r13d, r13d
0x1800cd881  jnz     loc_1800CE42B
0x1800cd887  mov     r15d, [rsp+4E8h+DesiredAccess]
0x1800cd88f  mov     [rsp+4E8h+ShareAccess], 4; FileInformationClass
0x1800cd897  mov     r9d, 28h ; '('; Length
0x1800cd89d  lea     r8, [rsp+4E8h+FileInformation]; FileInformation
0x1800cd8a5  lea     rdx, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800cd8ad  mov     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800cd8b5  call    cs:__imp_NtQueryInformationFile
0x1800cd8bb  mov     [rsp+4E8h+var_484], eax
0x1800cd8bf  test    eax, eax
0x1800cd8c1  jns     loc_1800CDBF7
0x1800cd8c7  and     edi, 2
0x1800cd8ca  jz      loc_1800CE49B
0x1800cd8d0  xor     esi, esi
0x1800cd8d2  lea     r14d, [rsi+1]
0x1800cd8d6  mov     [rsp+4E8h+ShareAccess], 5; FsInformationClass
0x1800cd8de  mov     r9d, 218h; Length
0x1800cd8e4  lea     r8, [rsp+4E8h+FsInformation]; FsInformation
0x1800cd8ec  lea     rdx, [rsp+4E8h+IoStatusBlock]; IoStatusBlock
0x1800cd8f4  mov     rcx, [rsp+4E8h+hDevice]; FileHandle
0x1800cd8f9  call    cs:__imp_NtQueryVolumeInformationFile
0x1800cd8ff  mov     [rsp+4E8h+var_484], eax
0x1800cd903  test    eax, eax
0x1800cd905  js      loc_1800CE832
0x1800cd90b  mov     [rsp+4E8h+BytesReturned], esi
0x1800cd912  mov     [rsp+4E8h+var_498], 1; int
0x1800cd91a  lea     rax, [rsp+4E8h+BytesReturned]
0x1800cd922  mov     qword ptr [rsp+4E8h+OutputBufferLength], rax; __int64
0x1800cd927  mov     eax, dword ptr [rsp+4E8h+FsInformation]
0x1800cd92e  mov     dword ptr [rsp+4E8h+OutputBuffer], eax; char
0x1800cd932  mov     [rsp+4E8h+lpOverlapped], rsi; __int64
0x1800cd937  mov     dword ptr [rsp+4E8h+lpBytesReturned], 3Ch ; '<'; SecurityInfo
0x1800cd93f  mov     dword ptr [rsp+4E8h+OpenOptions], ebx; __int64
0x1800cd943  mov     rax, [rsp+4E8h+hDevice]
0x1800cd948  mov     qword ptr [rsp+4E8h+ShareAccess], rax; __int64
0x1800cd94d  mov     rsi, qword ptr [rsp+4E8h+var_3E8]
0x1800cd955  mov     r9, rsi; int
0x1800cd958  mov     r8d, r15d; int
0x1800cd95b  mov     rdx, [rsp+4E8h+FileHandle]; int
0x1800cd963  mov     rcx, [rsp+4E8h+String]; int
0x1800cd96b  call    BasepCopySecurityInformation
0x1800cd970  test    eax, eax
0x1800cd972  jz      loc_1800CE226
0x1800cd978  xor     eax, eax
0x1800cd97a  mov     ebx, eax
0x1800cd97c  test    edi, edi
0x1800cd97e  setnz   bl
0x1800cd981  mov     r8d, ebx
0x1800cd984  mov     rdx, [rsp+4E8h+hDevice]
0x1800cd989  mov     rcx, [rsp+4E8h+FileHandle]; FileHandle
0x1800cd991  call    BasepCopyAlternateDataStreams
0x1800cd996  xor     edi, edi
0x1800cd998  test    eax, eax
0x1800cd99a  jz      loc_1800CE226
0x1800cd9a0  test    r14d, r14d
0x1800cd9a3  jz      loc_1800CDCB7
0x1800cd9a9  or      r15d, 0FFFFFFFFh
0x1800cd9ad  xor     r13d, r13d
0x1800cd9b0  mov     [rsp+4E8h+lpOverlapped], r13; lpOverlapped
0x1800cd9b5  lea     rax, [rsp+4E8h+BytesReturned]
0x1800cd9bd  mov     [rsp+4E8h+lpBytesReturned], rax; lpBytesReturned
0x1800cd9c2  mov     dword ptr [rsp+4E8h+OpenOptions], r13d; nOutBufferSize
0x1800cd9c7  mov     qword ptr [rsp+4E8h+ShareAccess], r13; lpOutBuffer
0x1800cd9cc  xor     r9d, r9d; nInBufferSize
0x1800cd9cf  xor     r8d, r8d; lpInBuffer
0x1800cd9d2  mov     edx, 900A0h; dwIoControlCode
0x1800cd9d7  mov     rcx, [rsp+4E8h+hDevice]; hDevice
0x1800cd9dc  call    DeviceIoControl
0x1800cd9e1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cd9e5  cmp     dword ptr [rsp+4E8h+TargetHandle], r13d
0x1800cd9ed  jnz     loc_1800CDB39
0x1800cd9f3  mov     rax, [rsp+4E8h+DosPathName]
0x1800cd9fb  test    rax, rax
0x1800cd9fe  jnz     loc_1800CDDAC
0x1800cda04  mov     r14, rbx
0x1800cda07  mov     esi, r13d
0x1800cda0a  mov     [rsp+4E8h+var_420], r13d
0x1800cda12  mov     rcx, [rsp+4E8h+String]; String
0x1800cda1a  call    cs:__imp_wcslen
0x1800cda20  add     eax, eax
0x1800cda22  mov     edi, r13d
0x1800cda25  mov     [rsp+4E8h+var_3D0], r13d
0x1800cda2d  lea     r13d, [rax+20h]
0x1800cda31  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800cda37  mov     ebx, r13d
0x1800cda3a  mov     [rsp+4E8h+TargetHandle], rbx
0x1800cda42  mov     rcx, gs:60h
0x1800cda4b  mov     r8d, r13d; Size
0x1800cda4e  mov     rcx, [rcx+30h]; HeapHandle
0x1800cda52  call    cs:__imp_RtlAllocateHeap
0x1800cda58  mov     [rsp+4E8h+Destination], rax
0x1800cda5d  test    rax, rax
0x1800cda60  jz      loc_1800CE21B
0x1800cda66  mov     eax, 7FFE0320h
0x1800cda6b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800cda6f  jnz     loc_1800CDE60
0x1800cda75  cmp     esi, 10h
0x1800cda78  jnb     loc_1800CE209
0x1800cda7e  mov     rax, [rax]
0x1800cda81  mov     r9d, ds:7FFE0004h
0x1800cda89  imul    r9, rax
0x1800cda8d  shr     r9, 18h
0x1800cda91  add     r9d, esi
0x1800cda94  lea     r8, aRf4xTmp; "~RF%4x.TMP"
0x1800cda9b  lea     edx, [r14+11h]; BufferCount
0x1800cda9f  lea     rcx, [rsp+4E8h+Buffer]; Buffer
0x1800cdaa7  call    cs:__imp_swprintf_s
0x1800cdaad  shr     rbx, 1
0x1800cdab0  mov     r8, [rsp+4E8h+String]; Source
  ... truncated ...
```
