# OefspIterateThroughStreams(void *,OEFS_FILE_INFORMATION const &,wistd::function<long (void *)>,bool *)

- ea: `0x18004fec8`
- end: `0x1800505e6`
- name: `?OefspIterateThroughStreams@@YAJPEAXAEBUOEFS_FILE_INFORMATION@@V?$function@$$A6AJPEAX@Z@wistd@@PEA_N@Z`
- size: `1822`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f244`
- `0x18004f4f8`

## callees

- `0x180004f86`
- `0x18000505d`
- `0x180007c60`
- `0x18000b10c`
- `0x18000b12c`
- `0x18000dc68`
- `0x18000dc8c`
- `0x18000ef20`
- `0x18000ef44`
- `0x180045f68`
- `0x180047508`
- `0x18004d800`
- `0x18004fec8`
- `0x180050af8`
- `0x180050b38`
- `0x180051820`
- `0x180067b98`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800502d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800503b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800503fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050465`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800504b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800504fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800505a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800502d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800503b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800503fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050465`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800504b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800504fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800505a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800502e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800503c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005040a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050473`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800504c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005050b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800505b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800502e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800503c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005040a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050473`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800504c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005050b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800505b1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180050169`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180050169`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180050237`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180050237`
- `ntdll!NtCreateFile` at `0x180050102`
- `ntdll!NtCreateFile` at `0x1800501d0`
- `ntdll!NtCreateFile` at `0x180050102`
- `ntdll!NtCreateFile` at `0x1800501d0`
- `ntdll!RtlInitUnicodeString` at `0x18005008f`
- `ntdll!RtlInitUnicodeString` at `0x18005008f`

## string_xrefs

- `0x18004ff55`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004ff73`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x180050427`: `Failed to open ADS '%ws': NTSTATUS: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OefspIterateThroughStreams(HANDLE FileHandle, _BYTE *a2, __int64 a3, char *a4)
{
  HANDLE v7; // rbx
  int v8; // r13d
  char v9; // al
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int StreamInformation; // eax
  const char *v15; // r9
  char v16; // si
  _DWORD *v17; // r14
  unsigned int v18; // eax
  unsigned int v19; // ecx
  __int64 v20; // r13
  _DWORD *v21; // rbx
  __int64 v22; // rdx
  int v23; // r13d
  NTSTATUS v24; // eax
  const char *v25; // r9
  NTSTATUS v26; // eax
  const char *v27; // r9
  int v28; // eax
  HANDLE v29; // rax
  int v30; // eax
  int v31; // edi
  int LastError; // eax
  __int64 v33; // rdx
  void *v34; // rbx
  HANDLE v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rdx
  void *v38; // rbx
  HANDLE v39; // rax
  int v40; // esi
  __int64 v41; // rdx
  void *v42; // rbx
  HANDLE v43; // rax
  unsigned int v45; // edi
  void *v46; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int AllocationSize; // [rsp+20h] [rbp-E0h]
  int AllocationSizea; // [rsp+20h] [rbp-E0h]
  ULONG ShareAccess[2]; // [rsp+30h] [rbp-D0h]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandlea; // [rsp+68h] [rbp-98h] BYREF
  int v53; // [rsp+70h] [rbp-90h]
  void *Buf1; // [rsp+78h] [rbp-88h] BYREF
  __int16 InBuffer; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hDevice; // [rsp+88h] [rbp-78h] BYREF
  int v57; // [rsp+90h] [rbp-70h]
  DWORD BytesReturned; // [rsp+94h] [rbp-6Ch] BYREF
  HANDLE v59; // [rsp+98h] [rbp-68h]
  char *v60; // [rsp+A0h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  LPVOID *p_lpMem; // [rsp+F8h] [rbp-8h]
  char v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v60 = a4;
  v7 = FileHandle;
  v59 = FileHandle;
  v66 = a3;
  v8 = 3;
  v57 = 3;
  if ( dword_1801173AC != 3 || (v9 = 1, a2[48]) )
    v9 = 0;
  *a4 = v9;
  if ( !*a2 )
  {
    v10 = wistd::function<long (void *)>::operator()(a3, FileHandle);
LABEL_71:
    v12 = v10;
    goto LABEL_76;
  }
  if ( !a2[50] )
    goto LABEL_11;
  v11 = wistd::function<long (void *)>::operator()(a3, FileHandle);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 522;
LABEL_75:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
      (const char *)(unsigned int)v11,
      AllocationSize);
    goto LABEL_76;
  }
  if ( *a4 )
  {
LABEL_77:
    wistd::function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>::~function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>(a3);
    return 0;
  }
  v7 = v59;
  while ( 1 )
  {
LABEL_11:
    lpMem = 0;
    p_lpMem = &lpMem;
    v65 = 1;
    v53 = 0;
    StreamInformation = GetStreamInformation(v7);
    if ( StreamInformation < 0 )
    {
      v45 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x220,
              (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
              (const char *)(unsigned int)StreamInformation,
              AllocationSize);
      v46 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v46);
        lpMem = 0;
      }
      wistd::function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>::~function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>(a3);
      return v45;
    }
    v16 = 1;
    v17 = lpMem;
    v53 = 0;
    if ( lpMem )
      break;
LABEL_46:
    v65 = 0;
    if ( v17 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v17);
    }
    if ( v16 )
    {
      if ( !a2[50] )
      {
        v11 = wistd::function<long (void *)>::operator()(a3, v7);
        v12 = v11;
        if ( v11 < 0 )
        {
          v13 = 651;
          goto LABEL_75;
        }
      }
      goto LABEL_77;
    }
    if ( v8 <= 0 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x285,
              (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
              (const char *)2,
              AllocationSize);
      goto LABEL_71;
    }
    v57 = --v8;
  }
  while ( 1 )
  {
    v18 = v17[1];
    v19 = v18 + 2;
    if ( v18 + 2 < v18 )
    {
      v40 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x229,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)0x80070216LL,
        AllocationSize);
      v42 = lpMem;
      if ( lpMem )
      {
LABEL_68:
        v43 = GetProcessHeap();
        HeapFree(v43, 0, v42);
        lpMem = 0;
      }
LABEL_69:
      v12 = v40;
      goto LABEL_76;
    }
    v20 = v19;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &Buf1,
      0,
      v19,
      v15);
    v21 = Buf1;
    if ( !Buf1 )
    {
      v40 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)0x8007000ELL,
        AllocationSize);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
        &Buf1,
        v41);
      v42 = lpMem;
      if ( lpMem )
        goto LABEL_68;
      goto LABEL_69;
    }
    memcpy_0(Buf1, v17 + 6, (unsigned int)v17[1]);
    *(_WORD *)((char *)v21 + (v20 & 0xFFFFFFFFFFFFFFFEuLL) - 2) = 0;
    if ( v17[1] == 14 && *(_QWORD *)v21 == 0x440024003A003ALL && v21[2] == 5505089 && *((_WORD *)v21 + 6) == 65 )
      goto LABEL_41;
    if ( v17[1] == 34 )
    {
      v23 = 0;
      if ( !memcmp_0(v21, L":$EfsBackup:$DATA", 0x22u) )
        goto LABEL_41;
    }
    else
    {
      v23 = 0;
    }
    IoStatusBlock = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    FileHandlea = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)v21);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v59;
    ObjectAttributes.Attributes = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &FileHandlea,
      0);
    v24 = NtCreateFile(&FileHandlea, 0x100180u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x200060u, 0, 0);
    if ( v24 == -1073741772 )
    {
      wil::details::in1diag3::Log_NtStatus(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)0xC0000034LL,
        AllocationSize);
      v16 = 0;
      goto LABEL_37;
    }
    if ( v24 < 0 )
    {
      ShareAccess[0] = v24;
      LastError = wil::details::in1diag3::Return_NtStatusMsg(
                    retaddr,
                    (void *)0x245,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                    (const char *)(unsigned int)v24,
                    (int)"Failed to open ADS '%ws': NTSTATUS: 0x%x",
                    (const char *)v21,
                    *(_QWORD *)ShareAccess);
      goto LABEL_61;
    }
    if ( v16 )
      break;
LABEL_37:
    v28 = ++v53;
    if ( *v60 && !a2[50] && v28 == 1 )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandlea);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
        &Buf1,
        v36);
      v34 = lpMem;
      if ( lpMem )
      {
LABEL_56:
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v34);
        lpMem = 0;
      }
LABEL_57:
      v12 = v23;
      goto LABEL_76;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandlea);
LABEL_41:
    if ( *v17 )
      v17 = (_DWORD *)((char *)v17 + (unsigned int)*v17);
    else
      v17 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
      &Buf1,
      v22);
    if ( !v17 )
    {
      v17 = lpMem;
      v7 = v59;
      v8 = v57;
      goto LABEL_46;
    }
  }
  if ( !a2[50] )
    goto LABEL_35;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileHandlea, &FileInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x24C,
                  (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                  v25);
LABEL_61:
    v31 = LastError;
    goto LABEL_62;
  }
  if ( (FileInformation.dwFileAttributes & 0x800) == 0 )
    goto LABEL_35;
  hDevice = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hDevice,
    0);
  v26 = NtCreateFile(&hDevice, 0x100183u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x200060u, 0, 0);
  if ( v26 == -1073741772 )
  {
    wil::details::in1diag3::Log_NtStatus(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
      (const char *)0xC0000034LL,
      AllocationSizea);
    v16 = 0;
    goto LABEL_34;
  }
  if ( v26 >= 0 )
  {
    InBuffer = 0;
    BytesReturned = 0;
    if ( !DeviceIoControl(hDevice, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
    {
      v30 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x261,
              (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
              v27);
      goto LABEL_53;
    }
LABEL_34:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
    if ( v16 )
    {
LABEL_35:
      v23 = wistd::function<long (void *)>::operator()(a3, FileHandlea);
      if ( v23 < 0 )
      {
        ShareAccess[0] = (unsigned __int8)a2[50];
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x269,
          (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
          (const char *)(unsigned int)v23,
          (int)"Failed invokedPerStream on ADS '%ws' IsEncrypting: %u",
          (const char *)v21,
          *(_QWORD *)ShareAccess);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandlea);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
          &Buf1,
          v33);
        v34 = lpMem;
        if ( lpMem )
          goto LABEL_56;
        goto LABEL_57;
      }
      v23 = 0;
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  v30 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0x25A,
          (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
          (const char *)(unsigned int)v26,
          AllocationSizea);
LABEL_53:
  v31 = v30;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
LABEL_62:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandlea);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
    &Buf1,
    v37);
  v38 = lpMem;
  if ( lpMem )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v38);
    lpMem = 0;
  }
  v12 = v31;
LABEL_76:
  wistd::function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>::~function<void (_EDP_DPL_WNF_KEYS_STATE_DATA const &)>(a3);
  return v12;
}

```

## disassembly

```asm
0x18004fec8  push    rbp
0x18004feca  push    rbx
0x18004fecb  push    rsi
0x18004fecc  push    rdi
0x18004fecd  push    r12
0x18004fecf  push    r13
0x18004fed1  push    r14
0x18004fed3  push    r15
0x18004fed5  lea     rbp, [rsp-58h]
0x18004feda  sub     rsp, 158h
0x18004fee1  mov     rax, cs:__security_cookie
0x18004fee8  xor     rax, rsp
0x18004feeb  mov     [rbp+90h+var_48], rax
0x18004feef  mov     rdi, r9
0x18004fef2  mov     [rbp+90h+var_F0], r9
0x18004fef6  mov     r15, r8
0x18004fef9  mov     r12, rdx
0x18004fefc  mov     rbx, rcx
0x18004feff  mov     [rbp+90h+var_F8], rcx
0x18004ff03  mov     [rbp+90h+var_88], r8
0x18004ff07  xor     r14d, r14d
0x18004ff0a  lea     r13d, [r14+3]
0x18004ff0e  mov     [rbp+90h+var_100], r13d
0x18004ff12  cmp     cs:dword_1801173AC, r13d
0x18004ff19  jnz     short loc_18004FF23
0x18004ff1b  cmp     [rdx+30h], r14b
0x18004ff1f  mov     al, 1
0x18004ff21  jz      short loc_18004FF26
0x18004ff23  mov     al, r14b
0x18004ff26  mov     [r9], al
0x18004ff29  cmp     [rdx], r14b
0x18004ff2c  jnz     short loc_18004FF3E
0x18004ff2e  mov     rdx, rcx
0x18004ff31  mov     rcx, r15
0x18004ff34  call    ??R?$function@$$A6AJPEAX@Z@wistd@@QEBAJPEAX@Z; wistd::function<long (void *)>::operator()(void *)
0x18004ff39  jmp     loc_180050534
0x18004ff3e  cmp     [rdx+32h], r14b
0x18004ff42  jz      short loc_18004FF73
0x18004ff44  mov     rdx, rcx
0x18004ff47  mov     rcx, r15
0x18004ff4a  call    ??R?$function@$$A6AJPEAX@Z@wistd@@QEBAJPEAX@Z; wistd::function<long (void *)>::operator()(void *)
0x18004ff4f  mov     ebx, eax
0x18004ff51  test    eax, eax
0x18004ff53  jns     short loc_18004FF66
0x18004ff55  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004ff5c  mov     edx, 20Ah
0x18004ff61  jmp     loc_180050558
0x18004ff66  cmp     [rdi], r14b
0x18004ff69  jnz     loc_180050574
0x18004ff6f  mov     rbx, [rbp+90h+var_F8]
0x18004ff73  lea     rdi, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004ff7a  mov     [rsp+190h+lpMem], r14
0x18004ff7f  lea     rax, [rsp+190h+lpMem]
0x18004ff84  mov     [rbp+90h+var_98], rax
0x18004ff88  mov     [rbp+90h+var_90], 1
0x18004ff8c  mov     [rsp+190h+var_120], r14d
0x18004ff91  lea     r8, [rsp+190h+var_120]
0x18004ff96  lea     rdx, [rsp+190h+lpMem]
0x18004ff9b  mov     rcx, rbx; FileHandle
0x18004ff9e  call    GetStreamInformation
0x18004ffa3  test    eax, eax
0x18004ffa5  js      loc_180050580
0x18004ffab  mov     sil, 1
0x18004ffae  mov     r14, [rsp+190h+lpMem]
0x18004ffb3  mov     [rsp+190h+var_120], 0
0x18004ffbb  test    r14, r14
0x18004ffbe  jz      loc_1800502D0
0x18004ffc4  xor     r13d, r13d
0x18004ffc7  mov     eax, [r14+4]
0x18004ffcb  lea     ecx, [rax+2]
0x18004ffce  cmp     ecx, eax
0x18004ffd0  jb      loc_1800504D6
0x18004ffd6  mov     r13d, ecx
0x18004ffd9  mov     r8d, ecx
0x18004ffdc  xor     edx, edx
0x18004ffde  lea     rcx, [rsp+190h+Buf1]
0x18004ffe3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004ffe8  nop
0x18004ffe9  mov     rbx, [rsp+190h+Buf1]
0x18004ffee  test    rbx, rbx
0x18004fff1  jz      loc_180050485
0x18004fff7  mov     r8d, [r14+4]; Size
0x18004fffb  lea     rdx, [r14+18h]; Src
0x18004ffff  mov     rcx, rbx; void *
0x180050002  call    memcpy_0
0x180050007  and     r13, 0FFFFFFFFFFFFFFFEh
0x18005000b  xor     eax, eax
0x18005000d  mov     [rbx+r13-2], ax
0x180050013  cmp     dword ptr [r14+4], 0Eh
0x180050018  jnz     short loc_18005003D
0x18005001a  mov     rax, 440024003A003Ah
0x180050024  cmp     [rbx], rax
0x180050027  jnz     short loc_18005003D
0x180050029  cmp     dword ptr [rbx+8], 540041h
0x180050030  jnz     short loc_18005003D
0x180050032  cmp     word ptr [rbx+0Ch], 41h ; 'A'
0x180050037  jz      loc_18005029D
0x18005003d  cmp     dword ptr [r14+4], 22h ; '"'
0x180050042  jnz     short loc_180050066
0x180050044  mov     r8d, 22h ; '"'; Size
0x18005004a  lea     rdx, aEfsbackupData; ":$EfsBackup:$DATA"
0x180050051  mov     rcx, rbx; Buf1
0x180050054  call    memcmp_0
0x180050059  xor     r13d, r13d
0x18005005c  test    eax, eax
0x18005005e  jz      loc_1800502A0
0x180050064  jmp     short loc_180050069
0x180050066  xor     r13d, r13d
0x180050069  xorps   xmm0, xmm0
0x18005006c  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x180050070  xorps   xmm1, xmm1
0x180050073  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm1
0x180050077  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm1
0x18005007b  movups  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm1
0x18005007f  mov     [rsp+190h+FileHandle], r13
0x180050084  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x180050088  mov     rdx, rbx; SourceString
0x18005008b  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x18005008f  call    cs:__imp_RtlInitUnicodeString
0x180050095  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x18005009c  mov     rax, [rbp+90h+var_F8]
0x1800500a0  mov     [rbp+90h+ObjectAttributes.RootDirectory], rax
0x1800500a4  mov     [rbp+90h+ObjectAttributes.Attributes], r13d
0x1800500a8  lea     rax, [rbp+90h+DestinationString]
0x1800500ac  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x1800500b0  xorps   xmm0, xmm0
0x1800500b3  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800500b8  xor     edx, edx
0x1800500ba  lea     rcx, [rsp+190h+FileHandle]
0x1800500bf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800500c4  mov     [rsp+190h+EaLength], r13d; EaLength
0x1800500c9  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x1800500ce  mov     [rsp+190h+CreateOptions], 200060h; CreateOptions
0x1800500d6  mov     [rsp+190h+CreateDisposition], 1; CreateDisposition
0x1800500de  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x1800500e6  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x1800500eb  mov     [rsp+190h+AllocationSize], r13; int
0x1800500f0  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x1800500f4  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1800500f8  mov     edx, 100180h; DesiredAccess
0x1800500fd  lea     rcx, [rsp+190h+FileHandle]; FileHandle
0x180050102  call    cs:__imp_NtCreateFile
0x180050108  mov     edx, 0C0000034h
0x18005010d  cmp     eax, edx
0x18005010f  jnz     short loc_180050130
0x180050111  mov     rcx, [rbp+98h]; this
0x180050118  mov     r9d, edx; char *
0x18005011b  mov     r8, rdi; unsigned int
0x18005011e  mov     edx, 241h; void *
0x180050123  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x180050128  mov     sil, r13b
0x18005012b  jmp     loc_18005026E
0x180050130  test    eax, eax
0x180050132  js      loc_180050417
0x180050138  test    sil, sil
0x18005013b  jz      loc_18005026E
0x180050141  cmp     [r12+32h], r13b
0x180050146  jz      loc_180050253
0x18005014c  xorps   xmm0, xmm0
0x18005014f  xor     eax, eax
0x180050151  movups  xmmword ptr [rbp+90h+FileInformation.dwFileAttributes], xmm0
0x180050155  movups  xmmword ptr [rbp+90h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180050159  movups  xmmword ptr [rbp+90h+FileInformation.nFileSizeHigh], xmm0
0x18005015d  mov     [rbp+90h+FileInformation.nFileIndexLow], eax
0x180050160  lea     rdx, [rbp+90h+FileInformation]; lpFileInformation
0x180050164  mov     rcx, [rsp+190h+FileHandle]; hFile
0x180050169  call    cs:__imp_GetFileInformationByHandle
0x18005016f  test    eax, eax
0x180050171  jz      loc_18005034B
0x180050177  test    [rbp+90h+FileInformation.dwFileAttributes], 800h
0x18005017e  jz      loc_180050253
0x180050184  mov     [rbp+90h+hDevice], r13
0x180050188  xor     edx, edx
0x18005018a  lea     rcx, [rbp+90h+hDevice]
0x18005018e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180050193  mov     [rsp+190h+EaLength], r13d; EaLength
0x180050198  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x18005019d  mov     [rsp+190h+CreateOptions], 200060h; CreateOptions
0x1800501a5  mov     [rsp+190h+CreateDisposition], 1; CreateDisposition
0x1800501ad  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x1800501b5  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x1800501ba  mov     [rsp+190h+AllocationSize], r13; int
0x1800501bf  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x1800501c3  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1800501c7  mov     edx, 100183h; DesiredAccess
0x1800501cc  lea     rcx, [rbp+90h+hDevice]; FileHandle
0x1800501d0  call    cs:__imp_NtCreateFile
0x1800501d6  mov     edx, 0C0000034h
0x1800501db  cmp     eax, edx
0x1800501dd  jnz     short loc_1800501FB
0x1800501df  mov     rcx, [rbp+98h]; this
0x1800501e6  mov     r9d, edx; char *
0x1800501e9  mov     r8, rdi; unsigned int
0x1800501ec  mov     edx, 256h; void *
0x1800501f1  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x1800501f6  mov     sil, r13b
0x1800501f9  jmp     short loc_180050245
0x1800501fb  test    eax, eax
0x1800501fd  js      loc_180050324
0x180050203  mov     [rbp+90h+InBuffer], r13w
0x180050208  mov     [rbp+90h+BytesReturned], r13d
0x18005020c  mov     qword ptr [rsp+190h+CreateDisposition], r13; lpOverlapped
0x180050211  lea     rax, [rbp+90h+BytesReturned]
0x180050215  mov     qword ptr [rsp+190h+ShareAccess], rax; lpBytesReturned
0x18005021a  mov     [rsp+190h+FileAttributes], r13d; nOutBufferSize
0x18005021f  mov     [rsp+190h+AllocationSize], r13; lpOutBuffer
0x180050224  mov     r9d, 2; nInBufferSize
0x18005022a  lea     r8, [rbp+90h+InBuffer]; lpInBuffer
0x18005022e  mov     edx, 9C040h; dwIoControlCode
0x180050233  mov     rcx, [rbp+90h+hDevice]; hDevice
0x180050237  call    cs:__imp_DeviceIoControl
0x18005023d  test    eax, eax
0x18005023f  jz      loc_18005030E
0x180050245  lea     rcx, [rbp+90h+hDevice]
0x180050249  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005024e  test    sil, sil
0x180050251  jz      short loc_18005026E
0x180050253  mov     rdx, [rsp+190h+FileHandle]
0x180050258  mov     rcx, r15
0x18005025b  call    ??R?$function@$$A6AJPEAX@Z@wistd@@QEBAJPEAX@Z; wistd::function<long (void *)>::operator()(void *)
0x180050260  mov     r13d, eax
0x180050263  test    eax, eax
0x180050265  js      loc_180050364
0x18005026b  xor     r13d, r13d
0x18005026e  mov     eax, [rsp+190h+var_120]
0x180050272  inc     eax
0x180050274  mov     [rsp+190h+var_120], eax
0x180050278  mov     rcx, [rbp+90h+var_F0]
0x18005027c  cmp     [rcx], r13b
0x18005027f  jz      short loc_180050291
0x180050281  cmp     [r12+32h], r13b
0x180050286  jnz     short loc_180050291
0x180050288  cmp     eax, 1
0x18005028b  jz      loc_1800503DC
0x180050291  lea     rcx, [rsp+190h+FileHandle]
0x180050296  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005029b  jmp     short loc_1800502A0
0x18005029d  xor     r13d, r13d
0x1800502a0  cmp     [r14], r13d
0x1800502a3  jz      short loc_1800502AD
0x1800502a5  mov     eax, [r14]
0x1800502a8  add     r14, rax
0x1800502ab  jmp     short loc_1800502B0
0x1800502ad  mov     r14, r13
0x1800502b0  lea     rcx, [rsp+190h+Buf1]
0x1800502b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800502ba  test    r14, r14
0x1800502bd  jnz     loc_18004FFC7
0x1800502c3  mov     r14, [rsp+190h+lpMem]
0x1800502c8  mov     rbx, [rbp+90h+var_F8]
0x1800502cc  mov     r13d, [rbp+90h+var_100]
0x1800502d0  mov     [rbp+90h+var_90], 0
0x1800502d4  test    r14, r14
0x1800502d7  jz      short loc_1800502ED
0x1800502d9  call    cs:__imp_GetProcessHeap
0x1800502df  mov     r8, r14; lpMem
0x1800502e2  xor     edx, edx; dwFlags
0x1800502e4  mov     rcx, rax; hHeap
0x1800502e7  call    cs:__imp_HeapFree
0x1800502ed  xor     r14d, r14d
0x1800502f0  test    sil, sil
0x1800502f3  jnz     loc_180050538
0x1800502f9  test    r13d, r13d
0x1800502fc  jle     loc_18005051A
0x180050302  dec     r13d
0x180050305  mov     [rbp+90h+var_100], r13d
0x180050309  jmp     loc_18004FF7A
0x18005030e  mov     rcx, [rbp+98h]; this
0x180050315  mov     r8, rdi; unsigned int
0x180050318  mov     edx, 261h; void *
0x18005031d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050322  jmp     short loc_18005033B
0x180050324  mov     rcx, [rbp+98h]; this
0x18005032b  mov     r9d, eax; char *
0x18005032e  mov     r8, rdi; unsigned int
0x180050331  mov     edx, 25Ah; void *
0x180050336  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005033b  mov     edi, eax
0x18005033d  lea     rcx, [rbp+90h+hDevice]
0x180050341  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180050346  jmp     loc_180050445
0x18005034b  mov     rcx, [rbp+98h]; this
0x180050352  mov     r8, rdi; unsigned int
0x180050355  mov     edx, 24Ch; void *
0x18005035a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005035f  jmp     loc_180050443
0x180050364  movzx   eax, byte ptr [r12+32h]
0x18005036a  mov     rcx, [rbp+98h]; this
0x180050371  mov     [rsp+190h+ShareAccess], eax
0x180050375  mov     qword ptr [rsp+190h+FileAttributes], rbx; char *
0x18005037a  lea     rax, aFailedInvokedp; "Failed invokedPerStream on ADS '%ws' Is"...
0x180050381  mov     [rsp+190h+AllocationSize], rax; int
0x180050386  mov     r9d, r13d; char *
0x180050389  mov     r8, rdi; unsigned int
0x18005038c  mov     edx, 269h; void *
0x180050391  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050396  nop
0x180050397  lea     rcx, [rsp+190h+FileHandle]
0x18005039c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800503a1  nop
  ... truncated ...
```
