# BasepCopyFileExW

- ea: `0x1800f0120`
- end: `0x1800f21b5`
- name: `BasepCopyFileExW`
- size: `8341`
- prototype: ``
- caller_count: `4`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ef910`
- `0x1800efb50`
- `0x1800effe0`
- `0x1800f6f80`

## callees

- `0x1800134a0`
- `0x1800136b0`
- `0x1800138c0`
- `0x180013ec0`
- `0x1800149d0`
- `0x1800486a0`
- `0x180048f30`
- `0x18009d0d0`
- `0x1800b2b70`
- `0x1800cc960`
- `0x1800cd0f0`
- `0x1800cf810`
- `0x1800cfa60`
- `0x1800d061c`
- `0x1800ea710`
- `0x1800f0120`
- `0x1800f5fc8`
- `0x1800f9030`
- `0x1800fc214`
- `0x1800fc7c4`
- `0x18010508c`
- `0x180112e58`
- `0x18012d119`
- `0x18013299c`
- `0x180188f10`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800f0b8c`
- `ntdll!NtQueryInformationFile` at `0x1800f0bc7`
- `ntdll!NtQueryInformationFile` at `0x1800f0c4f`
- `ntdll!NtQueryInformationFile` at `0x1800f0b8c`
- `ntdll!NtQueryInformationFile` at `0x1800f0bc7`
- `ntdll!NtQueryInformationFile` at `0x1800f0c4f`
- `ntdll!wcslen` at `0x1800f07c0`
- `ntdll!wcslen` at `0x1800f07c0`
- `ntdll!NtSetInformationFile` at `0x1800f1591`
- `ntdll!NtSetInformationFile` at `0x1800f1a78`
- `ntdll!NtSetInformationFile` at `0x1800f1f16`
- `ntdll!NtSetInformationFile` at `0x1800f1fc6`
- `ntdll!NtSetInformationFile` at `0x1800f1591`
- `ntdll!NtSetInformationFile` at `0x1800f1a78`
- `ntdll!NtSetInformationFile` at `0x1800f1f16`
- `ntdll!NtSetInformationFile` at `0x1800f1fc6`
- `ntdll!NtFsControlFile` at `0x1800f1b49`
- `ntdll!NtFsControlFile` at `0x1800f1c05`
- `ntdll!NtFsControlFile` at `0x1800f1cfc`
- `ntdll!NtFsControlFile` at `0x1800f2062`
- `ntdll!NtFsControlFile` at `0x1800f1b49`
- `ntdll!NtFsControlFile` at `0x1800f1c05`
- `ntdll!NtFsControlFile` at `0x1800f1cfc`
- `ntdll!NtFsControlFile` at `0x1800f2062`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f0b1d`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f11a6`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f11ea`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f182e`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f189e`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f0b1d`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f11a6`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f11ea`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f182e`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800f189e`
- `ntdll!NtCreateFile` at `0x1800f078f`
- `ntdll!NtCreateFile` at `0x1800f1347`
- `ntdll!NtCreateFile` at `0x1800f13b4`
- `ntdll!NtCreateFile` at `0x1800f078f`
- `ntdll!NtCreateFile` at `0x1800f1347`
- `ntdll!NtCreateFile` at `0x1800f13b4`
- `ntdll!RtlSetLastWin32Error` at `0x1800f0440`
- `ntdll!RtlSetLastWin32Error` at `0x1800f07de`
- `ntdll!RtlSetLastWin32Error` at `0x1800f209e`
- `ntdll!RtlSetLastWin32Error` at `0x1800f0440`
- `ntdll!RtlSetLastWin32Error` at `0x1800f07de`
- `ntdll!RtlSetLastWin32Error` at `0x1800f209e`
- `ntdll!NtWaitForSingleObject` at `0x1800f197a`
- `ntdll!NtWaitForSingleObject` at `0x1800f1a17`
- `ntdll!NtWaitForSingleObject` at `0x1800f1b64`
- `ntdll!NtWaitForSingleObject` at `0x1800f1c20`
- `ntdll!NtWaitForSingleObject` at `0x1800f1d17`
- `ntdll!NtWaitForSingleObject` at `0x1800f197a`
- `ntdll!NtWaitForSingleObject` at `0x1800f1a17`
- `ntdll!NtWaitForSingleObject` at `0x1800f1b64`
- `ntdll!NtWaitForSingleObject` at `0x1800f1c20`
- `ntdll!NtWaitForSingleObject` at `0x1800f1d17`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f0557`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f2137`
- `ntdll!RtlSetCurrentTransaction` at `0x18018c5c2`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f0557`
- `ntdll!RtlSetCurrentTransaction` at `0x1800f2137`
- `ntdll!RtlSetCurrentTransaction` at `0x18018c5c2`
- `ntdll!NtCopyFileChunk` at `0x1800f1958`
- `ntdll!NtCopyFileChunk` at `0x1800f19fb`
- `ntdll!NtCopyFileChunk` at `0x1800f1958`
- `ntdll!NtCopyFileChunk` at `0x1800f19fb`
- `ntdll!RtlEqualUnicodeString` at `0x1800f10f1`
- `ntdll!RtlEqualUnicodeString` at `0x1800f10f1`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800f06a7`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800f06a7`
- `ntdll!RtlGetCurrentTransaction` at `0x1800f0430`
- `ntdll!RtlGetCurrentTransaction` at `0x1800f0430`
- `ntdll!RtlNtStatusToDosError` at `0x1800f16dd`
- `ntdll!RtlNtStatusToDosError` at `0x1800f16dd`
- `ntdll!NtClose` at `0x1800f155b`
- `ntdll!NtClose` at `0x1800f15a8`
- `ntdll!NtClose` at `0x1800f155b`
- `ntdll!NtClose` at `0x1800f15a8`
- `ntdll!RtlFreeHeap` at `0x1800f0c7c`
- `ntdll!RtlFreeHeap` at `0x1800f0cb1`
- `ntdll!RtlFreeHeap` at `0x1800f0efc`
- `ntdll!RtlFreeHeap` at `0x1800f2154`
- `ntdll!RtlFreeHeap` at `0x1800f217c`
- `ntdll!RtlFreeHeap` at `0x18018c5e3`
- `ntdll!RtlFreeHeap` at `0x18018c60a`
- `ntdll!RtlFreeHeap` at `0x1800f0c7c`
- `ntdll!RtlFreeHeap` at `0x1800f0cb1`
- `ntdll!RtlFreeHeap` at `0x1800f0efc`
- `ntdll!RtlFreeHeap` at `0x1800f2154`
- `ntdll!RtlFreeHeap` at `0x1800f217c`
- `ntdll!RtlFreeHeap` at `0x18018c5e3`
- `ntdll!RtlFreeHeap` at `0x18018c60a`
- `ntdll!RtlAllocateHeap` at `0x1800f0c16`
- `ntdll!RtlAllocateHeap` at `0x1800f0c16`

## pseudocode

```c
__int64 __fastcall BasepCopyFileExW(
        wchar_t *a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        HANDLE *a10,
        HANDLE *a11,
        __int64 a12,
        DWORD a13,
        int a14,
        unsigned int a15,
        __int128 *a16)
{
  __int128 *v17; // rsi
  unsigned int v18; // edi
  int v19; // ecx
  DWORD v20; // ebx
  BOOL v21; // eax
  DWORD v22; // edx
  int v23; // edx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 result; // rax
  int v28; // ebx
  int *v29; // rax
  int v30; // r8d
  int v31; // eax
  unsigned int v32; // r12d
  ULONG CreateOptions; // r14d
  int v34; // r13d
  NTSTATUS v35; // eax
  ULONG v36; // ecx
  __int64 v37; // rcx
  PVOID v38; // rsi
  signed int v39; // r15d
  ULONG v40; // ebx
  NTSTATUS v41; // eax
  NTSTATUS v42; // esi
  wchar_t *v43; // rsi
  size_t v44; // rax
  ULONG v45; // ecx
  NTSTATUS LastStatusValue; // esi
  HANDLE EventW; // rax
  void *v48; // rsi
  SECURITY_INFORMATION SecurityInfo; // r12d
  char v50; // r13
  unsigned int v51; // ebx
  PVOID Heap; // rax
  unsigned int *v53; // r8
  int v54; // ebx
  unsigned int v55; // eax
  int v56; // r13d
  __int64 v57; // rdx
  unsigned int *v58; // rcx
  int i; // eax
  unsigned int v60; // r13d
  char v61; // bl
  unsigned int *v62; // r14
  unsigned int v63; // edx
  __int64 v64; // rcx
  __int64 v65; // rax
  int v66; // eax
  ULONG v67; // ebx
  unsigned __int64 v68; // rdx
  __int16 v69; // bx
  HANDLE v70; // rcx
  int v71; // r15d
  int v72; // r14d
  HANDLE EventA; // rbx
  __int64 v74; // rbx
  struct _TEB *v75; // rsi
  int v76; // r13d
  unsigned int v77; // esi
  int v78; // eax
  NTSTATUS v79; // r12d
  int v80; // ecx
  NTSTATUS v81; // esi
  int v82; // eax
  NTSTATUS Status; // eax
  __int64 v84; // rax
  int v85; // eax
  HANDLE FileW; // rax
  ULONG LastErrorValue; // esi
  NTSTATUS v88; // ebx
  ULONG v89; // edx
  int AllocationSize; // [rsp+20h] [rbp-6C8h]
  int FileAttributes; // [rsp+28h] [rbp-6C0h]
  int ShareAccess; // [rsp+30h] [rbp-6B8h]
  int v93; // [rsp+B0h] [rbp-638h]
  HANDLE hObject; // [rsp+B8h] [rbp-630h] BYREF
  HANDLE FileHandle; // [rsp+C0h] [rbp-628h] BYREF
  PVOID P; // [rsp+C8h] [rbp-620h]
  int v97; // [rsp+D0h] [rbp-618h]
  char v98; // [rsp+D4h] [rbp-614h]
  char v99; // [rsp+D5h] [rbp-613h]
  __int64 v100; // [rsp+D8h] [rbp-610h] BYREF
  DWORD BytesReturned; // [rsp+E0h] [rbp-608h] BYREF
  __int64 v102; // [rsp+E4h] [rbp-604h] BYREF
  __int64 v103; // [rsp+ECh] [rbp-5FCh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-5F0h] BYREF
  unsigned int v105; // [rsp+108h] [rbp-5E0h]
  __int64 v106; // [rsp+10Ch] [rbp-5DCh] BYREF
  int v107; // [rsp+114h] [rbp-5D4h]
  wchar_t *String; // [rsp+118h] [rbp-5D0h] BYREF
  __int64 v109; // [rsp+120h] [rbp-5C8h]
  __int64 v110; // [rsp+128h] [rbp-5C0h] BYREF
  int v111; // [rsp+130h] [rbp-5B8h]
  __int64 v112; // [rsp+134h] [rbp-5B4h] BYREF
  unsigned int v113; // [rsp+13Ch] [rbp-5ACh]
  int v114; // [rsp+140h] [rbp-5A8h]
  _DWORD v115[3]; // [rsp+144h] [rbp-5A4h] BYREF
  ULONG v116; // [rsp+150h] [rbp-598h]
  HANDLE v117; // [rsp+158h] [rbp-590h] BYREF
  LPCWSTR lpFileName; // [rsp+160h] [rbp-588h]
  HANDLE Handle; // [rsp+168h] [rbp-580h] BYREF
  int v120[4]; // [rsp+170h] [rbp-578h] BYREF
  int v121; // [rsp+180h] [rbp-568h]
  int v122; // [rsp+184h] [rbp-564h]
  unsigned int v123; // [rsp+188h] [rbp-560h]
  int v124; // [rsp+18Ch] [rbp-55Ch]
  unsigned int v125; // [rsp+190h] [rbp-558h]
  int v126; // [rsp+194h] [rbp-554h]
  __int64 FsInformation; // [rsp+198h] [rbp-550h] BYREF
  int v128[2]; // [rsp+1A0h] [rbp-548h] BYREF
  int v129; // [rsp+1A8h] [rbp-540h]
  int v130; // [rsp+1ACh] [rbp-53Ch] BYREF
  PVOID v131[2]; // [rsp+1B0h] [rbp-538h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1C0h] [rbp-528h] BYREF
  __int128 EaBuffer; // [rsp+1F0h] [rbp-4F8h] BYREF
  __int128 v134; // [rsp+200h] [rbp-4E8h]
  struct _OVERLAPPED Overlapped; // [rsp+210h] [rbp-4D8h] BYREF
  HANDLE *v136; // [rsp+230h] [rbp-4B8h]
  HANDLE *v137; // [rsp+238h] [rbp-4B0h]
  __int64 v138; // [rsp+240h] [rbp-4A8h]
  __int64 v139; // [rsp+248h] [rbp-4A0h]
  __int64 v140; // [rsp+250h] [rbp-498h]
  _QWORD v141[2]; // [rsp+260h] [rbp-488h] BYREF
  int v142; // [rsp+270h] [rbp-478h]
  int v143; // [rsp+290h] [rbp-458h]
  int *v144; // [rsp+2D0h] [rbp-418h]
  __int64 v145; // [rsp+2D8h] [rbp-410h]
  __int64 v146; // [rsp+2E0h] [rbp-408h]
  __int64 v147; // [rsp+2E8h] [rbp-400h]
  __int64 v148; // [rsp+2F0h] [rbp-3F8h]
  __int64 v149; // [rsp+2F8h] [rbp-3F0h]
  __int128 OutputBuffer; // [rsp+310h] [rbp-3D8h] BYREF
  UNICODE_STRING String2; // [rsp+320h] [rbp-3C8h] BYREF
  __int128 FileInformation; // [rsp+330h] [rbp-3B8h] BYREF
  __int64 v153; // [rsp+340h] [rbp-3A8h]
  __int128 InBuffer; // [rsp+348h] [rbp-3A0h] BYREF
  __int64 v155; // [rsp+358h] [rbp-390h]
  __int64 v156[2]; // [rsp+360h] [rbp-388h] BYREF
  __int128 v157; // [rsp+370h] [rbp-378h]
  __int128 v158; // [rsp+380h] [rbp-368h]
  __int64 v159; // [rsp+390h] [rbp-358h]
  _QWORD InputBuffer[2]; // [rsp+398h] [rbp-350h] BYREF
  __int128 v161; // [rsp+3A8h] [rbp-340h] BYREF
  __int128 v162; // [rsp+3B8h] [rbp-330h]
  __int64 v163; // [rsp+3C8h] [rbp-320h]
  __int128 v164; // [rsp+3D0h] [rbp-318h] BYREF
  __int128 v165; // [rsp+3E0h] [rbp-308h] BYREF
  __int128 v166; // [rsp+3F0h] [rbp-2F8h]
  _BYTE v167[4]; // [rsp+400h] [rbp-2E8h] BYREF
  int v168; // [rsp+404h] [rbp-2E4h]
  _DWORD v169[136]; // [rsp+480h] [rbp-268h] BYREF

  *(_QWORD *)&OutputBuffer = a3;
  lpFileName = a2;
  String = a1;
  v17 = a16;
  v136 = a10;
  v138 = (__int64)a10;
  v137 = a11;
  v139 = (__int64)a11;
  v110 = a12;
  FileHandle = (HANDLE)-1LL;
  hObject = (HANDLE)-1LL;
  v18 = 0;
  v106 = 0;
  v103 = 0x100000000LL;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  v153 = 0;
  v161 = 0;
  v162 = 0;
  v163 = 0;
  FsInformation = 0;
  *(_OWORD *)v120 = 0;
  *(_OWORD *)v131 = 0;
  v117 = 0;
  Handle = 0;
  v130 = 0;
  memset_0(v141, 0, 0xA8u);
  v100 = 0;
  *(_OWORD *)v156 = 0;
  v157 = 0;
  v158 = 0;
  v159 = 0;
  v112 = 0;
  v115[0] = -1;
  *(_QWORD *)v128 = 0;
  EaBuffer = 0;
  v134 = 0;
  v165 = 0;
  v166 = 0;
  v102 = 0;
  v19 = a8;
  if ( (a8 & 0x411B0770) != 0 )
    goto LABEL_282;
  if ( (a9 & 0xFEC4780F) != 0 )
    goto LABEL_282;
  v20 = a13;
  if ( (a13 & 0xFFFFFFFC) != 0 )
    goto LABEL_282;
  if ( Feature_BlockCloningInCopy_Enabled == -1 )
  {
    v109 = (unsigned int)Feature_BlockCloningInCopy__private_featureState;
    if ( (Feature_BlockCloningInCopy__private_featureState & 0x10) == 0 )
    {
      LODWORD(v109) = Feature_BlockCloningInCopy__private_featureState | 1;
      wil_details_FeatureReporting_ReportUsageToService(Feature_BlockCloningInCopy__private_descriptor, v109, 3, 1);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
        v109,
        3,
        Feature_BlockCloningInCopy__private_descriptor);
      v18 = 0;
    }
    Feature_BlockCloningInCopy_Enabled = 1;
    v21 = 1;
    v19 = a8;
  }
  else
  {
    v21 = Feature_BlockCloningInCopy_Enabled == 1;
  }
  v22 = v20 | 2;
  if ( v21 )
    v22 = v20;
  if ( (BytesReturned = v22, a15 - 1 <= 0x1FE)
    || a14 && (unsigned int)(a14 - 4096) > 0x3FFFF000
    || (v19 & 0x4002) == 0x4002 )
  {
LABEL_282:
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  LODWORD(a8) = a9 | v19;
  if ( RtlGetCurrentTransaction() )
  {
    RtlSetLastWin32Error(0x1A45u);
    return 0;
  }
  result = BasepCloudFileCopy(v24, v23, v25, v26);
  if ( !(_DWORD)result )
    return result;
  v28 = 0;
  P = 0;
  LODWORD(v134) = 0;
  EaBuffer = 1u;
  if ( v17 )
  {
    v165 = *v17;
    v166 = v17[1];
    *((_QWORD *)&v134 + 1) = &v165;
  }
  if ( (_QWORD)OutputBuffer || a5 || a6 )
  {
    v141[1] = 0;
    v142 = 0;
    v29 = &v130;
    if ( a5 )
      v29 = a5;
    v144 = v29;
    v145 = a4;
    v146 = a6;
    v147 = a7;
    if ( (_QWORD)OutputBuffer )
    {
      v148 = *(_QWORD *)OutputBuffer;
      v149 = *(_QWORD *)(OutputBuffer + 8);
    }
    v100 = (__int64)v141;
  }
  RtlSetCurrentTransaction(v110);
  v143 = 1;
  v30 = a8;
  if ( (a8 & 0x1000) == 0 )
  {
    v31 = BasepCopyCheckNoBuffering();
    v30 = a8;
    if ( v31 )
    {
      v30 = a8 | 0x1000;
      LODWORD(a8) = a8 | 0x1000;
    }
  }
  if ( (v30 & 2) != 0 )
  {
    v30 &= 0xFFFEEFFF;
    LODWORD(a8) = v30;
  }
  if ( (v30 & 0x1000) != 0 )
    v28 = 1;
  HIDWORD(v103) = v28;
  v122 = v28;
  LODWORD(v110) = v30 & 0x180;
  LODWORD(v109) = (_DWORD)v110 != 0 ? 0x4000 : 0;
  v32 = ((v30 & 0xFC | 0xFFFFFFF8) << 28) | ((v30 & 0x2020) != 0 ? 0x1000000 : 0);
  v123 = v32;
  CreateOptions = v109 | 0x10200004 | (v28 != 0 ? 8 : 0) | ((_DWORD)v110 == 0 ? 0x40 : 0);
  v97 = CreateOptions;
  v111 = 0;
  v121 = 5;
  v34 = 5;
  if ( (v30 & 0x20000) != 0 )
    v34 = 7;
  v124 = v34;
  v121 = v34;
  v35 = RtlDosPathNameToNtPathName_U_WithStatus(String, v131, 0, 0);
  if ( v35 < 0 )
  {
    if ( v35 == -1073741801 || v35 == -1073741670 )
      goto LABEL_41;
    v36 = 3;
LABEL_270:
    RtlSetLastWin32Error(v36);
    goto LABEL_43;
  }
  while ( 2 )
  {
    v39 = v32;
    v105 = v32;
    v40 = v34;
    v116 = v34;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v131;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v41 = NtCreateFile(
                &FileHandle,
                v39 | 0x100080,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                0,
                v40,
                1u,
                CreateOptions,
                &EaBuffer,
                0x20u);
        v42 = v41;
        if ( v41 >= 0 )
          break;
        BaseSetLastNTError((unsigned int)v41);
        if ( v42 == -1073741638 )
        {
          v43 = String;
          v44 = wcslen(String);
          if ( v44 <= 1 || (v45 = 3, v43[v44 - 1] != 92) )
            v45 = 5;
          RtlSetLastWin32Error(v45);
        }
        FileHandle = (HANDLE)-1LL;
        if ( (NtCurrentTeb()->LastErrorValue == 1314 || NtCurrentTeb()->LastErrorValue == 5) && (v39 & 0x1000000) != 0 )
        {
          v39 &= ~0x1000000u;
          goto LABEL_60;
        }
        if ( (NtCurrentTeb()->LastErrorValue == 5 || NtCurrentTeb()->LastErrorValue == 32) && (v39 & 0x40000000) != 0 )
        {
          v39 &= ~0x40000000u;
          v105 = v39;
          if ( (v32 & 0x1000000) != 0 )
          {
            v39 |= 0x1000000u;
LABEL_60:
            v105 = v39;
          }
        }
        else
        {
          if ( (v40 & 2) != 0 )
          {
            if ( (CreateOptions & 0x200000) == 0 )
              goto LABEL_43;
            CreateOptions &= ~0x200000u;
            v97 = CreateOptions;
            v105 = v32;
            v40 = v34;
            v116 = v34;
          }
          else
          {
            v40 |= 2u;
            v116 = v40;
            v105 = v32;
            CreateOptions &= ~8u;
            v97 = CreateOptions;
            LODWORD(a8) = a8 & 0xFFFFEFFF;
            HIDWORD(v103) = 0;
            v122 = 0;
          }
          v39 = v32;
        }
      }
      if ( v111 )
        break;
      v143 = 6;
      v111 = 1;
      LastStatusValue = BasepProcessNameGrafting(FileHandle, v128, (__int64)v115, a8, BytesReturned);
      if ( LastStatusValue < 0 )
      {
        CloseHandle(FileHandle);
        FileHandle = (HANDLE)-1LL;
        goto LABEL_70;
      }
      if ( (_DWORD)v103 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        v48 = EventW;
        if ( EventW )
        {
          v93 = CopyNameGraftNow(
                  FileHandle,
                  (__int64)String,
                  (__int64)lpFileName,
                  (a8 & 0x80u) != 0LL ? 0x4001 : 0,
                  AllocationSize,
                  FileAttributes,
                  ShareAccess,
                  &a8,
                  EventW);
          CloseHandle(v48);
          CloseHandle(FileHandle);
          FileHandle = (HANDLE)-1LL;
          v18 = v93 != 0;
        }
        else
        {
          CloseHandle(FileHandle);
          FileHandle = (HANDLE)-1LL;
        }
        goto LABEL_43;
      }
      if ( HIDWORD(v106) )
        break;
      CreateOptions &= ~0x200000u;
      v97 = CreateOptions;
      CloseHandle(FileHandle);
      FileHandle = (HANDLE)-1LL;
    }
    SecurityInfo = 0;
    v107 = 0;
    if ( v39 < 0 )
    {
      SecurityInfo = 32;
      v107 = 32;
      if ( (a8 & 0x10) != 0 )
      {
        if ( (a8 & 0x400) == 0 )
          SecurityInfo = 36;
        v107 = SecurityInfo;
      }
      if ( (a8 & 0x40) != 0 )
      {
        SecurityInfo |= 3u;
        v107 = SecurityInfo;
      }
    }
    if ( (v39 & 0x1000000) != 0 && (a8 & 0x20) != 0 )
    {
      SecurityInfo |= 8u;
      v107 = SecurityInfo;
    }
    if ( (CreateOptions & 8) == 0 && (a8 & 2) == 0 )
    {
      v35 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
      if ( v35 >= 0 )
      {
        if ( (FsInformation & 0x1000000000LL) != 0 && (FsInformation & 0x100000000000LL) == 0 )
        {
          BasepDisableLocalFileBuffering(FileHandle);
          BasepRemotePrefetchSource(FileHandle);
        }
        goto LABEL_92;
      }
LABEL_41:
      v37 = (unsigned int)v35;
      goto LABEL_42;
    }
LABEL_92:
    v35 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v35 < 0 )
      goto LABEL_41;
    v35 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &v161, 0x28u, FileBasicInformation);
    if ( v35 < 0 )
      goto LABEL_41;
    v50 = v163;
    v141[0] = *((_QWORD *)&FileInformation + 1);
    v51 = 4096;
    v129 = 4096;
    while ( 2 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v51);
      v38 = Heap;
      P = Heap;
      if ( !Heap )
      {
        BaseSetLastNTError(3221225495LL);
        goto LABEL_272;
      }
      LastStatusValue = NtQueryInformationFile(FileHandle, &IoStatusBlock, Heap, v51 - 2, FileStreamInformation);
      v53 = (unsigned int *)P;
      if ( LastStatusValue < 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        P = 0;
        v51 *= 2;
        v129 = v51;
        goto LABEL_100;
      }
      if ( !IoStatusBlock.Information )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        P = 0;
LABEL_100:
        v53 = 0;
      }
      if ( LastStatusValue == -2147483643 || LastStatusValue == -1073741789 )
        continue;
      break;
    }
    if ( (_QWORD)OutputBuffer || (a8 & 0x4002) != 0 )
    {
      LOWORD(v156[0]) = (a8 & 2) != 0 ? 31387 : 19139;
      WORD1(v156[0]) = 56;
      v156[1] = v161;
      *(_QWORD *)&v157 = v162;
      *((_QWORD *)&v157 + 1) = *((_QWORD *)&FileInformation + 1);
      v158 = *((unsigned __int64 *)&FileInformation + 1);
      HIDWORD(v156[0]) = 0;
      LODWORD(v159) = 0;
      if ( v53 )
      {
        v57 = 0;
        v140 = 0;
        v58 = v53;
        *(_QWORD *)&v115[1] = v53;
        for ( i = 0; ; ++i )
        {
          v57 += *((_QWORD *)v58 + 1);
          v140 = v57;
          HIDWORD(v156[0]) = i + 1;
          if ( !*v58 )
            break;
          v58 = (unsigned int *)((char *)v58 + *v58);
          *(_QWORD *)&v115[1] = v58;
        }
        v141[0] = v57;
        *(_QWORD *)&v158 = v57;
        HIDWORD(v156[0]) = i;
      }
    }
    v161 = 0;
    LODWORD(v163) = 0;
    if ( (a8 & 2) != 0 && ((__int64)v158 < 0x80000 || (v50 & 0x10) != 0) )
    {
      LODWORD(a8) = a8 & 0xFFFFFFFD;
      LOWORD(v156[0]) = 19139;
    }
    v54 = HIDWORD(v102);
    v55 = BaseCopyStream(
            String,
            &FileHandle,
            v39,
            lpFileName,
            0,
            0,
            (__int64 *)&FileInformation + 1,
            (int *)&a8,
            &hObject,
            (int *)&v106,
            (_DWORD *)&v112 + 1,
            &v100,
            v156,
            SHIDWORD(v102),
            v128[1],
            SecurityInfo,
            (__int64)&v112,
            BytesReturned,
            a14,
            a15,
            SHIDWORD(v103),
            &v102);
    v18 = v55;
    if ( !v54 )
      goto LABEL_127;
    if ( !v55 )
    {
      if ( NtCurrentTeb()->LastErrorValue != 80 || (a8 & 1) == 0 )
      {
        v56 = v50 & 1;
        if ( !v56 )
          BaseMarkFileForDelete(hObject);
        if ( hObject != (HANDLE)-1LL )
        {
          CloseHandle(hObject);
          hObject = (HANDLE)-1LL;
        }
        if ( v56 )
        {
          SetFileAttributesW(lpFileName, 0x80u);
          DeleteFileW(lpFileName);
        }
        if ( FileHandle != (HANDLE)-1LL )
        {
          CloseHandle(FileHandle);
          FileHandle = (HANDLE)-1LL;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        P = 0;
        CreateOptions &= ~0x200000u;
        v97 = CreateOptions;
        HIDWORD(v102) = 0;
        v32 = v123;
        v34 = v124;
        continue;
      }
LABEL_127:
      if ( !v55 )
        goto LABEL_175;
    }
    break;
  }
  if ( (a8 & 0x8000) != 0 )
    goto LABEL_175;
  v143 = 1;
  if ( !P )
    goto LABEL_175;
  v60 = 0;
  v125 = 0;
  v61 = 0;
  v99 = 0;
  v98 = 0;
  v62 = (unsigned int *)P;
  for ( *(_QWORD *)&v115[1] = P; ; *(_QWORD *)&v115[1] = v62 )
  {
LABEL_131:
    while ( 1 )
    {
      LastStatusValue = 0;
      v143 = 1;
      v63 = v62[1];
      if ( v63 > 2 && *((_WORD *)v62 + 13) != 58 )
        break;
      if ( !*v62 )
        goto LABEL_175;
      v62 = (unsigned int *)((char *)v62 + *v62);
      *(_QWORD *)&v115[1] = v62;
    }
    *(_DWORD *)(&String2.MaximumLength + 1) = 0;
    *(_DWORD *)&String2.Length = 786444;
    String2.Buffer = (PWSTR)((char *)v62 + v63 + 12);
    if ( v63 <= 0xC || RtlEqualUnicodeString(&DataStreamTypeName, &String2, 1u) )
      break;
    if ( !*v62 )
      goto LABEL_175;
    v62 = (unsigned int *)((char *)v62 + *v62);
  }
  v125 = ++v60;
  if ( v18 == 2 )
  {
    v64 = v100;
    if ( v100 )
    {
      if ( v60 >= (unsigned int)v159 )
      {
        v64 = v100;
        v65 = *((_QWORD *)&v158 + 1);
      }
      else
      {
        v65 = *((_QWORD *)v62 + 1);
      }
      *(_QWORD *)(v64 + 8) += v65;
    }
  }
  if ( !v61 )
  {
    memset_0(v169, 0, 0x218u);
    v99 = 1;
    v66 = NtQueryVolumeInformationFile(hObject, &IoStatusBlock, v169, 0x218u, FileFsAttributeInformation);
    if ( v66 >= 0 )
    {
      if ( (v169[0] & 0x40000) != 0 )
        v66 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, v169, 0x218u, FileFsAttributeInformation);
      if ( v66 >= 0 && (v169[0] & 0x40000) != 0 )
      {
        v98 = 1;
        goto LABEL_150;
      }
    }
    if ( v66 >= 0 )
      v66 = -1073741637;
    if ( (a8 & 0x13B87F0) != 0 )
    {
      if ( v100 )
      {
        *(_DWORD *)(v100 + 20) = 1;
        v74 = v100;
        *(_DWORD *)(v74 + 24) = RtlNtStatusToDosError(v66);
        *(_QWORD *)(v100 + 64) = 0;
        *(_QWORD *)(v100 + 32) = FileHandle;
        *(_QWORD *)(v100 + 40) = hObject;
      }
      if ( !(unsigned int)BasepCopyFileCallback(8) )
      {
        v75 = NtCurrentTeb();
        if ( v75 )
          LastStatusValue = v75->LastStatusValue;
        else
          LastStatusValue = -1073741811;
        v18 = 0;
        goto LABEL_167;
      }
    }
LABEL_150:
    LastStatusValue = 0;
  }
  if ( v18 != 1 && (v18 != 2 || (_DWORD)v159 != v60) )
    goto LABEL_167;
  if ( v18 != 2 )
  {
    LODWORD(v159) = v60;
    *((_QWORD *)&v158 + 1) = 0;
  }
  *(_QWORD *)&v120[2] = v62 + 6;
  LOWORD(v120[0]) = *((_WORD *)v62 + 2);
  HIWORD(v120[0]) = v120[0];
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = FileHandle;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v120;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v67 = 268435460;
  v97 = 268435460;
  if ( (_DWORD)v110 )
    v67 = 268451844;
  v97 = v67;
  if ( HIDWORD(v102) )
  {
    v67 |= 0x200000u;
    v97 = v67;
  }
  LastStatusValue = NtCreateFile(
                      &Handle,
                      0x80100000,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      0,
                      5u,
                      1u,
                      v67,
                      &EaBuffer,
                      0x20u);
  if ( LastStatusValue == -1073741757 )
    LastStatusValue = NtCreateFile(
                        &Handle,
                        0x80100000,
                        &ObjectAttributes,
                        &IoStatusBlock,
                        0,
                        0,
                        7u,
                        1u,
                        v67,
                        &EaBuffer,
                        0x20u);
  if ( LastStatusValue < 0 )
    goto LABEL_168;
  LODWORD(v103) = 0;
  HIDWORD(v106) = 0;
  v68 = (unsigned __int64)LOWORD(v120[0]) >> 1;
  v69 = *(_WORD *)(*(_QWORD *)&v120[2] + 2 * v68);
  *(_WORD *)(*(_QWORD *)&v120[2] + 2 * v68) = 0;
  v117 = (HANDLE)-1LL;
  LODWORD(v103) = a8 & 0xFFFEEFFE;
  HIDWORD(v106) = v102;
  v18 = BaseCopyStream(
          String,
          &Handle,
          v39,
          *(const WCHAR **)&v120[2],
          hObject,
          v106,
          (__int64 *)v62 + 1,
          (int *)&v103,
          &v117,
          0,
          (_DWORD *)&v112 + 1,
          &v100,
          v156,
          SHIDWORD(v102),
          v128[1],
          SecurityInfo,
          (__int64)&v112,
          BytesReturned | 2,
          a14,
          a15,
          0,
          (_DWORD *)&v106 + 1);
  *(_WORD *)(*(_QWORD *)&v120[2] + 2 * ((unsigned __int64)LOWORD(v120[0]) >> 1)) = v69;
  NtClose(Handle);
  v70 = v117;
  if ( v117 != (HANDLE)-1LL )
  {
    if ( v18 )
    {
      LastStatusValue = NtSetInformationFile(v117, &IoStatusBlock, &v161, 0x28u, FileBasicInformation);
      v70 = v117;
    }
    NtClose(v70);
  }
LABEL_167:
  if ( LastStatusValue < 0 )
  {
LABEL_168:
    v18 = 0;
    BaseSetLastNTError((unsigned int)LastStatusValue);
  }
  if ( v18 )
  {
LABEL_193:
    if ( !*v62 )
      goto LABEL_175;
    v62 = (unsigned int *)((char *)v62 + *v62);
    *(_QWORD *)&v115[1] = v62;
    v61 = v99;
    goto LABEL_131;
  }
  if ( !v98 )
  {
    LastStatusValue = 0;
    v18 = 1;
    goto LABEL_193;
  }
  if ( (!v100 || !*(_DWORD *)(v100 + 104)) && (a8 & 2) == 0 )
    BaseMarkFileForDelete(hObject);
LABEL_175:
  if ( !v18 || (a8 & 0x4002) == 0 )
    goto LABEL_249;
  v114 = 56;
  v113 = 0;
  v71 = 0;
  v126 = 0;
  v110 = 0;
  String = 0;
  v72 = 56;
  if ( *((_QWORD *)&FileInformation + 1) < 0x38u )
    v72 = DWORD2(FileInformation);
  v114 = v72;
  if ( !v72 )
    goto LABEL_249;
  EventA = CreateEventA(0, 1, 0, 0);
  if ( !EventA )
  {
    v18 = 0;
    goto LABEL_70;
  }
  v143 = 4;
  v76 = HIDWORD(v103);
  if ( !HIDWORD(v103) && !(_DWORD)v106 && (v102 & 1) == 0 )
  {
LABEL_211:
    v80 = v72;
    if ( (v102 & 1) != 0 )
      v80 = v71;
    v81 = NtCopyFileChunk(FileHandle, hObject, EventA, &IoStatusBlock, v80, &v110, &String, 0, 0, v102);
    if ( v81 == 259 )
      v81 = NtWaitForSingleObject(EventA, 0, 0);
    if ( v81 >= 0 )
      goto LABEL_286;
    v82 = v102;
    if ( (v102 & 1) != 0 )
    {
      LODWORD(v102) = v102 & 0xFFFFFFFE;
      v81 = NtCopyFileChunk(FileHandle, hObject, EventA, &IoStatusBlock, v72, &v110, &String, 0, 0, v82 & 0xFFFFFFFE);
      if ( v81 == 259 )
        v81 = NtWaitForSingleObject(EventA, 0, 0);
    }
    if ( v81 < 0 )
    {
      BaseMarkFileForDelete(hObject);
      v18 = 0;
      BaseSetLastNTError((unsigned int)v81);
    }
    else
    {
LABEL_286:
      if ( *((_QWORD *)&FileInformation + 1) < 0x38u )
      {
        *(_QWORD *)&OutputBuffer = *((_QWORD *)&FileInformation + 1);
        if ( NtSetInformationFile(hObject, &IoStatusBlock, &OutputBuffer, 8u, FileEndOfFileInformation) < 0 )
          BaseMarkFileForDelete(hObject);
      }
      v18 = 1;
      if ( (a8 & 0x20000000) != 0 )
      {
        String2 = 0;
        OutputBuffer = 0;
        InputBuffer[0] = 0;
        InputBuffer[1] = *((_QWORD *)&FileInformation + 1);
        Status = NtFsControlFile(
                   hObject,
                   EventA,
                   0,
                   0,
                   &IoStatusBlock,
                   0x940CFu,
                   InputBuffer,
                   0x10u,
                   &OutputBuffer,
                   0x10u);
        if ( Status == 259 )
        {
          Status = NtWaitForSingleObject(EventA, 1u, 0);
          if ( Status >= 0 )
            Status = IoStatusBlock.Status;
        }
        if ( Status < 0 && Status != -1073741789 && Status != -2147483643 )
          goto LABEL_230;
        Status = NtFsControlFile(
                   FileHandle,
                   EventA,
                   0,
                   0,
                   &IoStatusBlock,
                   0x940CFu,
                   InputBuffer,
                   0x10u,
                   &String2,
                   0x10u);
        if ( Status == 259 )
        {
          Status = NtWaitForSingleObject(EventA, 1u, 0);
          if ( Status >= 0 )
            Status = IoStatusBlock.Status;
        }
        if ( Status < 0 )
        {
          if ( Status != -1073741789 && Status != -2147483643 )
          {
LABEL_230:
            BaseSetLastNTError((unsigned int)Status);
            v18 = 0;
            BaseMarkFileForDelete(hObject);
            goto LABEL_43;
          }
          v18 = 1;
        }
        if ( *(_QWORD *)&String2.Length != (_QWORD)OutputBuffer || !IoStatusBlock.Information )
        {
          v164 = 0;
          v84 = *((_QWORD *)&FileInformation + 1);
          if ( IoStatusBlock.Information )
            v84 = *(_QWORD *)&String2.Length;
          *((_QWORD *)&v164 + 1) = v84;
          Status = NtFsControlFile(hObject, EventA, 0, 0, &IoStatusBlock, 0x980C8u, &v164, 0x10u, 0, 0);
          if ( Status == 259 )
          {
            Status = NtWaitForSingleObject(EventA, 1u, 0);
            if ( Status >= 0 )
              Status = IoStatusBlock.Status;
          }
          if ( Status < 0 )
            goto LABEL_230;
        }
      }
    }
    CloseHandle(EventA);
LABEL_249:
    if ( !v18 )
      goto LABEL_43;
    if ( v115[0] != -1 )
    {
      memset(&Overlapped, 0, sizeof(Overlapped));
      BytesReturned = 0;
      InBuffer = 0;
      Overlapped.hEvent = CreateEventA(0, 1, 0, 0);
      if ( Overlapped.hEvent )
      {
        if ( !DeviceIoControl(hObject, 0x900C4u, 0, 0, 0, 0, &BytesReturned, &Overlapped)
          && NtCurrentTeb()->LastErrorValue == 997 )
        {
          GetOverlappedResult(hObject, &Overlapped, &BytesReturned, 1);
        }
        ResetEvent(&Overlapped.hEvent);
        *((_QWORD *)&InBuffer + 1) = *((_QWORD *)&FileInformation + 1);
        if ( !DeviceIoControl(hObject, 0x980C8u, &InBuffer, 0x10u, 0, 0, &BytesReturned, &Overlapped)
          && NtCurrentTeb()->LastErrorValue == 997 )
        {
          GetOverlappedResult(hObject, &Overlapped, &BytesReturned, 1);
        }
        CloseHandle(Overlapped.hEvent);
      }
    }
    v143 = 4;
    if ( NtSetInformationFile(hObject, &IoStatusBlock, &v161, 0x28u, FileBasicInformation) == -1073741757 )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
      v85 = 128;
      v97 = 128;
      if ( HIDWORD(v102) )
        v85 = 2097280;
      v97 = v85;
      FileW = CreateFileW(lpFileName, 0x100u, 0, 0, 3u, v85 | (unsigned int)v109, 0);
      hObject = FileW;
      if ( FileW != (HANDLE)-1LL )
        NtSetInformationFile(FileW, &IoStatusBlock, &v161, 0x28u, FileBasicInformation);
    }
    memset_0(v167, 0, 0x74u);
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    if ( GetFileInformationByHandleEx(hObject, FileRemoteProtocolInfo, v167, 0x74u) )
    {
      if ( v168 == 3014656 )
      {
        v88 = NtFsControlFile(hObject, 0, 0, 0, &IoStatusBlock, 0x400007Fu, 0, 0, 0, 0);
        if ( v88 < 0 )
        {
          BaseMarkFileForDelete(hObject);
          v18 = 0;
          BaseSetLastNTError((unsigned int)v88);
        }
      }
    }
    if ( !v18 )
      goto LABEL_43;
    v36 = LastErrorValue;
    goto LABEL_270;
  }
  InBuffer = 0;
  v155 = 0;
  v18 = 0;
  LastStatusValue = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &InBuffer, 0x18u, FileFsSizeInformation);
  if ( LastStatusValue >= 0 )
  {
    v77 = HIDWORD(v155);
    v113 = HIDWORD(v155);
    v71 = HIDWORD(v155) * v155;
    v126 = HIDWORD(v155) * v155;
    v78 = v106;
    if ( (_DWORD)v106 )
    {
      v79 = NtQueryVolumeInformationFile(hObject, &IoStatusBlock, &InBuffer, 0x18u, FileFsSizeInformation);
      if ( v79 < 0 )
      {
        CloseHandle(EventA);
        v37 = (unsigned int)v79;
        goto LABEL_42;
      }
      if ( HIDWORD(v155) > v77 )
        v77 = HIDWORD(v155);
      v113 = v77;
      v78 = v106;
    }
    if ( v76 || v78 )
    {
      v72 = v77;
      v114 = v77;
    }
    goto LABEL_211;
  }
  CloseHandle(EventA);
LABEL_70:
  v37 = (unsigned int)LastStatusValue;
LABEL_42:
  BaseSetLastNTError(v37);
LABEL_43:
  v38 = P;
LABEL_272:
  if ( !v18 && v100 && NtCurrentTeb()->LastErrorValue != 1235 && NtCurrentTeb()->LastErrorValue != 3050 )
  {
    v89 = NtCurrentTeb()->LastErrorValue;
    *(_DWORD *)(v100 + 92) = v89;
    *(_DWORD *)(v100 + 24) = v89;
    BasepCopyFileCallback(6);
  }
  *v136 = FileHandle;
  *v137 = hObject;
  RtlSetCurrentTransaction(0);
  if ( v38 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v38);
  if ( v131[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v131[1]);
  return v18;
}

```

## disassembly

```asm
0x1800f0120  mov     r11, rsp
0x1800f0123  push    rbx
0x1800f0124  push    rsi
0x1800f0125  push    rdi
0x1800f0126  push    r12
0x1800f0128  push    r13
0x1800f012a  push    r14
0x1800f012c  push    r15
0x1800f012e  sub     rsp, 6B0h
0x1800f0135  mov     rax, cs:__security_cookie
0x1800f013c  xor     rax, rsp
0x1800f013f  mov     [rsp+6E8h+var_48], rax
0x1800f0147  mov     r12, r9
0x1800f014a  mov     qword ptr [rsp+6E8h+OutputBuffer], r8
0x1800f0152  mov     [rsp+6E8h+lpFileName], rdx
0x1800f015a  mov     [rsp+6E8h+String], rcx
0x1800f0162  mov     rsi, [rsp+6E8h+arg_78]
0x1800f016a  mov     r14, [rsp+6E8h+arg_20]
0x1800f0172  mov     r15, [rsp+6E8h+arg_28]
0x1800f017a  mov     r13, [rsp+6E8h+arg_30]
0x1800f0182  mov     rax, [rsp+6E8h+arg_48]
0x1800f018a  mov     [rsp+6E8h+var_4B8], rax
0x1800f0192  mov     [rsp+6E8h+var_4A8], rax
0x1800f019a  mov     rax, [rsp+6E8h+arg_50]
0x1800f01a2  mov     [rsp+6E8h+var_4B0], rax
0x1800f01aa  mov     [rsp+6E8h+var_4A0], rax
0x1800f01b2  mov     rax, [rsp+6E8h+arg_58]
0x1800f01ba  mov     [rsp+6E8h+var_5C0], rax
0x1800f01c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f01c6  mov     [r11-628h], rax
0x1800f01cd  mov     [r11-630h], rax
0x1800f01d4  xor     edi, edi
0x1800f01d6  mov     dword ptr [rsp+6E8h+var_5DC], edi
0x1800f01dd  mov     dword ptr [rsp+6E8h+var_5FC], edi
0x1800f01e4  mov     dword ptr [rsp+6E8h+var_5DC+4], edi
0x1800f01eb  mov     dword ptr [rsp+6E8h+var_604+4], edi
0x1800f01f2  mov     dword ptr [rsp+6E8h+var_5B4+4], edi
0x1800f01f9  xor     eax, eax
0x1800f01fb  xorps   xmm0, xmm0
0x1800f01fe  movups  xmmword ptr [rsp+6E8h+ObjectAttributes.Length], xmm0
0x1800f0206  movups  xmmword ptr [rsp+6E8h+ObjectAttributes.ObjectName], xmm0
0x1800f020e  movups  xmmword ptr [rsp+6E8h+ObjectAttributes+1Ch], xmm0
0x1800f0216  movups  xmmword ptr [rsp+6E8h+IoStatusBlock], xmm0
0x1800f021e  xorps   xmm1, xmm1
0x1800f0221  movups  [rsp+6E8h+FileInformation], xmm1
0x1800f0229  mov     [r11-3A8h], rax
0x1800f0230  movups  [rsp+6E8h+var_340], xmm0
0x1800f0238  movups  [rsp+6E8h+var_330], xmm0
0x1800f0240  mov     [r11-320h], rax
0x1800f0247  mov     [r11-550h], rdi
0x1800f024e  movups  xmmword ptr [rsp+6E8h+var_578], xmm0
0x1800f0256  movups  xmmword ptr [rsp+6E8h+var_538], xmm1
0x1800f025e  mov     [r11-590h], rdi
0x1800f0265  mov     [r11-580h], rdi
0x1800f026c  mov     [rsp+6E8h+var_53C], edi
0x1800f0273  xor     edx, edx; Val
0x1800f0275  mov     r8d, 0A8h; Size
0x1800f027b  lea     rcx, [r11-488h]; void *
0x1800f0282  call    memset_0
0x1800f0287  mov     [rsp+6E8h+var_610], rdi
0x1800f028f  xorps   xmm0, xmm0
0x1800f0292  xor     eax, eax
0x1800f0294  movups  xmmword ptr [rsp+6E8h+var_388], xmm0
0x1800f029c  movups  [rsp+6E8h+var_378], xmm0
0x1800f02a4  movups  [rsp+6E8h+var_368], xmm0
0x1800f02ac  mov     [rsp+6E8h+var_358], rax
0x1800f02b4  mov     dword ptr [rsp+6E8h+var_5B4], edi
0x1800f02bb  or      eax, 0FFFFFFFFh
0x1800f02be  mov     dword ptr [rsp+6E8h+var_5A4], eax
0x1800f02c5  mov     qword ptr [rsp+6E8h+var_548], rdi
0x1800f02cd  lea     r8d, [rdi+1]
0x1800f02d1  mov     dword ptr [rsp+6E8h+var_5FC+4], r8d
0x1800f02d9  movups  [rsp+6E8h+var_4F8], xmm0
0x1800f02e1  movups  [rsp+6E8h+var_4E8], xmm0
0x1800f02e9  xorps   xmm1, xmm1
0x1800f02ec  movups  [rsp+6E8h+var_308], xmm1
0x1800f02f4  movups  [rsp+6E8h+var_2F8], xmm1
0x1800f02fc  mov     dword ptr [rsp+6E8h+var_604], edi
0x1800f0303  mov     ecx, dword ptr [rsp+6E8h+arg_38]
0x1800f030a  test    ecx, 411B0770h
0x1800f0310  jnz     loc_1800F2186
0x1800f0316  test    [rsp+6E8h+arg_40], 0FEC4780Fh
0x1800f0321  jnz     loc_1800F2186
0x1800f0327  mov     ebx, [rsp+6E8h+arg_60]
0x1800f032e  test    ebx, 0FFFFFFFCh
0x1800f0334  jnz     loc_1800F2186
0x1800f033a  mov     edx, cs:Feature_BlockCloningInCopy_Enabled
0x1800f0340  cmp     edx, eax
0x1800f0342  jnz     loc_1800F03C9
0x1800f0348  mov     [rsp+6E8h+var_5C8], rdi
0x1800f0350  mov     ecx, cs:Feature_BlockCloningInCopy__private_featureState
0x1800f0356  mov     dword ptr [rsp+6E8h+var_5C8], ecx
0x1800f035d  test    cl, 10h
0x1800f0360  jnz     short loc_1800F03B6
0x1800f0362  mov     rax, [rsp+6E8h+var_5C8]
0x1800f036a  mov     [rsp+6E8h+var_5C8], rax
0x1800f0372  or      ecx, r8d
0x1800f0375  mov     dword ptr [rsp+6E8h+var_5C8], ecx
0x1800f037c  mov     r9d, r8d
0x1800f037f  lea     edi, [r8+2]
0x1800f0383  mov     r8d, edi
0x1800f0386  mov     rdx, [rsp+6E8h+var_5C8]
0x1800f038e  lea     rcx, Feature_BlockCloningInCopy__private_descriptor
0x1800f0395  call    wil_details_FeatureReporting_ReportUsageToService
0x1800f039a  lea     r8, Feature_BlockCloningInCopy__private_descriptor
0x1800f03a1  mov     edx, edi
0x1800f03a3  mov     rcx, [rsp+6E8h+var_5C8]
0x1800f03ab  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1800f03b0  xor     edi, edi
0x1800f03b2  lea     r8d, [rdi+1]
0x1800f03b6  mov     cs:Feature_BlockCloningInCopy_Enabled, r8d
0x1800f03bd  mov     eax, r8d
0x1800f03c0  mov     ecx, dword ptr [rsp+6E8h+arg_38]
0x1800f03c7  jmp     short loc_1800F03D1
0x1800f03c9  mov     eax, edi
0x1800f03cb  cmp     edx, r8d
0x1800f03ce  setz    al
0x1800f03d1  mov     edx, ebx
0x1800f03d3  or      edx, 2
0x1800f03d6  test    eax, eax
0x1800f03d8  cmovnz  edx, ebx
0x1800f03db  mov     [rsp+6E8h+BytesReturned], edx
0x1800f03e2  mov     eax, [rsp+6E8h+arg_70]
0x1800f03e9  dec     eax
0x1800f03eb  cmp     eax, 1FEh
0x1800f03f0  jbe     loc_1800F2186
0x1800f03f6  mov     eax, [rsp+6E8h+arg_68]
0x1800f03fd  test    eax, eax
0x1800f03ff  jz      short loc_1800F0411
0x1800f0401  add     eax, 0FFFFF000h
0x1800f0406  cmp     eax, 3FFFF000h
0x1800f040b  ja      loc_1800F2186
0x1800f0411  mov     eax, ecx
0x1800f0413  mov     edx, 4002h
0x1800f0418  and     eax, edx
0x1800f041a  cmp     eax, edx
0x1800f041c  jz      loc_1800F2186
0x1800f0422  or      ecx, [rsp+6E8h+arg_40]
0x1800f0429  mov     dword ptr [rsp+6E8h+arg_38], ecx
0x1800f0430  call    cs:__imp_RtlGetCurrentTransaction
0x1800f0436  test    rax, rax
0x1800f0439  jz      short loc_1800F044B
0x1800f043b  mov     ecx, 1A45h; LastError
0x1800f0440  call    cs:__imp_RtlSetLastWin32Error
0x1800f0446  jmp     loc_1800F2190
0x1800f044b  lea     rax, [rsp+6E8h+var_5FC+4]
0x1800f0453  mov     qword ptr [rsp+6E8h+CreateOptions], rax
0x1800f0458  call    BasepCloudFileCopy
0x1800f045d  test    eax, eax
0x1800f045f  jz      loc_1800F2192
0x1800f0465  cmp     dword ptr [rsp+6E8h+var_5FC+4], edi
0x1800f046c  jz      loc_1800F2192
0x1800f0472  mov     ebx, edi
0x1800f0474  mov     [rsp+6E8h+var_634], edi
0x1800f047b  xor     edx, edx
0x1800f047d  mov     [rsp+6E8h+P], rdx
0x1800f0485  mov     qword ptr [rsp+6E8h+var_4F8+8], rdx
0x1800f048d  mov     dword ptr [rsp+6E8h+var_4E8], edx
0x1800f0494  mov     qword ptr [rsp+6E8h+var_4F8], 1
0x1800f04a0  test    rsi, rsi
0x1800f04a3  jz      short loc_1800F04CE
0x1800f04a5  movups  xmm0, xmmword ptr [rsi]
0x1800f04a8  movdqu  [rsp+6E8h+var_308], xmm0
0x1800f04b1  movups  xmm1, xmmword ptr [rsi+10h]
0x1800f04b5  movdqu  [rsp+6E8h+var_2F8], xmm1
0x1800f04be  lea     rax, [rsp+6E8h+var_308]
0x1800f04c6  mov     qword ptr [rsp+6E8h+var_4E8+8], rax
0x1800f04ce  mov     rcx, qword ptr [rsp+6E8h+OutputBuffer]
0x1800f04d6  test    rcx, rcx
0x1800f04d9  jnz     short loc_1800F04E5
0x1800f04db  test    r14, r14
0x1800f04de  jnz     short loc_1800F04E5
0x1800f04e0  test    r15, r15
0x1800f04e3  jz      short loc_1800F054F
0x1800f04e5  mov     [rsp+6E8h+var_480], rdx
0x1800f04ed  mov     [rsp+6E8h+var_478], edx
0x1800f04f4  lea     rax, [rsp+6E8h+var_53C]
0x1800f04fc  test    r14, r14
0x1800f04ff  cmovnz  rax, r14
0x1800f0503  mov     [rsp+6E8h+var_418], rax
0x1800f050b  mov     [rsp+6E8h+var_410], r12
0x1800f0513  mov     [rsp+6E8h+var_408], r15
0x1800f051b  mov     [rsp+6E8h+var_400], r13
0x1800f0523  test    rcx, rcx
0x1800f0526  jz      short loc_1800F053F
0x1800f0528  mov     rax, [rcx]
0x1800f052b  mov     [rsp+6E8h+var_3F8], rax
0x1800f0533  mov     rax, [rcx+8]
0x1800f0537  mov     [rsp+6E8h+var_3F0], rax
0x1800f053f  lea     rax, [rsp+6E8h+var_488]
0x1800f0547  mov     [rsp+6E8h+var_610], rax
0x1800f054f  mov     rcx, [rsp+6E8h+var_5C0]
0x1800f0557  call    cs:__imp_RtlSetCurrentTransaction
0x1800f055d  mov     eax, 1
0x1800f0562  mov     [rsp+6E8h+var_458], eax
0x1800f0569  mov     r8d, dword ptr [rsp+6E8h+arg_38]
0x1800f0571  mov     esi, 1000h
0x1800f0576  test    esi, r8d
0x1800f0579  jnz     short loc_1800F059C
0x1800f057b  call    BasepCopyCheckNoBuffering
0x1800f0580  mov     r8d, dword ptr [rsp+6E8h+arg_38]
0x1800f0588  test    eax, eax
0x1800f058a  mov     eax, 1
0x1800f058f  jz      short loc_1800F059C
0x1800f0591  or      r8d, esi
0x1800f0594  mov     dword ptr [rsp+6E8h+arg_38], r8d
0x1800f059c  test    r8b, 2
0x1800f05a0  jz      short loc_1800F05B1
0x1800f05a2  and     r8d, 0FFFEEFFFh
0x1800f05a9  mov     dword ptr [rsp+6E8h+arg_38], r8d
0x1800f05b1  test    esi, r8d
0x1800f05b4  cmovnz  ebx, eax
0x1800f05b7  mov     dword ptr [rsp+6E8h+var_5FC+4], ebx
0x1800f05be  mov     [rsp+6E8h+var_564], ebx
0x1800f05c5  mov     r9d, r8d
0x1800f05c8  and     r9d, 180h
0x1800f05cf  mov     dword ptr [rsp+6E8h+var_5C0], r9d
0x1800f05d7  mov     eax, r9d
0x1800f05da  neg     eax
0x1800f05dc  sbb     ecx, ecx
0x1800f05de  and     ecx, 4000h
0x1800f05e4  mov     dword ptr [rsp+6E8h+var_5C8], ecx
0x1800f05eb  mov     eax, r8d
0x1800f05ee  and     eax, 2020h
0x1800f05f3  neg     eax
0x1800f05f5  sbb     r12d, r12d
0x1800f05f8  and     r12d, 1000000h
0x1800f05ff  mov     eax, r8d
0x1800f0602  and     eax, 0FFFFFFFCh
0x1800f0605  or      eax, 0FFFFFFF8h
0x1800f0608  shl     eax, 1Ch
0x1800f060b  or      r12d, eax
0x1800f060e  mov     [rsp+6E8h+var_560], r12d
0x1800f0616  mov     [rsp+6E8h+var_618], 10000000h
0x1800f0621  or      ecx, 10200004h
0x1800f0627  mov     [rsp+6E8h+var_618], ecx
0x1800f062e  mov     eax, ebx
0x1800f0630  neg     eax
0x1800f0632  sbb     edx, edx
0x1800f0634  and     edx, 8
0x1800f0637  or      edx, ecx
0x1800f0639  mov     [rsp+6E8h+var_618], edx
0x1800f0640  mov     eax, r9d
0x1800f0643  neg     eax
0x1800f0645  sbb     r14d, r14d
0x1800f0648  not     r14d
0x1800f064b  and     r14d, 40h
0x1800f064f  or      r14d, edx
0x1800f0652  mov     [rsp+6E8h+var_618], r14d
0x1800f065a  mov     [rsp+6E8h+var_5B8], 0
0x1800f0665  mov     eax, 5
0x1800f066a  mov     [rsp+6E8h+var_568], eax
0x1800f0671  bt      r8d, 11h
0x1800f0676  mov     r13d, eax
0x1800f0679  lea     eax, [r13+2]
0x1800f067d  cmovb   r13d, eax
0x1800f0681  mov     [rsp+6E8h+var_55C], r13d
0x1800f0689  mov     [rsp+6E8h+var_568], r13d
0x1800f0691  xor     r9d, r9d
0x1800f0694  xor     r8d, r8d
0x1800f0697  lea     rdx, [rsp+6E8h+var_538]
0x1800f069f  mov     rcx, [rsp+6E8h+String]
0x1800f06a7  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800f06ad  mov     [rsp+6E8h+var_638], eax
0x1800f06b4  test    eax, eax
0x1800f06b6  jns     short loc_1800F06E4
0x1800f06b8  cmp     eax, 0C0000017h
0x1800f06bd  jz      short loc_1800F06D0
0x1800f06bf  cmp     eax, 0C000009Ah
0x1800f06c4  jz      short loc_1800F06D0
0x1800f06c6  mov     ecx, 3
0x1800f06cb  jmp     loc_1800F209E
0x1800f06d0  mov     ecx, eax
0x1800f06d2  call    BaseSetLastNTError
0x1800f06d7  mov     rsi, [rsp+6E8h+P]
0x1800f06df  jmp     loc_1800F20B4
0x1800f06e4  mov     r15d, r12d
0x1800f06e7  mov     [rsp+6E8h+var_5E0], r12d
0x1800f06ef  mov     ebx, r13d
0x1800f06f2  mov     [rsp+6E8h+var_598], ebx
0x1800f06f9  mov     [rsp+6E8h+ObjectAttributes.Length], 30h ; '0'
0x1800f0704  mov     [rsp+6E8h+ObjectAttributes.RootDirectory], 0
0x1800f0710  mov     [rsp+6E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f071b  lea     rax, [rsp+6E8h+var_538]
0x1800f0723  mov     [rsp+6E8h+ObjectAttributes.ObjectName], rax
0x1800f072b  xorps   xmm0, xmm0
0x1800f072e  movdqu  xmmword ptr [rsp+6E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f0737  mov     edx, r15d
0x1800f073a  or      edx, 100080h; DesiredAccess
0x1800f0740  mov     [rsp+6E8h+EaLength], 20h ; ' '; EaLength
0x1800f0748  lea     rax, [rsp+6E8h+var_4F8]
0x1800f0750  mov     [rsp+6E8h+EaBuffer], rax; EaBuffer
0x1800f0755  mov     [rsp+6E8h+CreateOptions], r14d; CreateOptions
0x1800f075a  mov     [rsp+6E8h+CreateDisposition], 1; CreateDisposition
0x1800f0762  mov     [rsp+6E8h+ShareAccess], ebx; ShareAccess
0x1800f0766  mov     [rsp+6E8h+FileAttributes], 0; FileAttributes
0x1800f076e  mov     [rsp+6E8h+AllocationSize], 0; AllocationSize
0x1800f0777  lea     r9, [rsp+6E8h+IoStatusBlock]; IoStatusBlock
0x1800f077f  lea     r8, [rsp+6E8h+ObjectAttributes]; ObjectAttributes
0x1800f0787  lea     rcx, [rsp+6E8h+FileHandle]; FileHandle
  ... truncated ...
```
