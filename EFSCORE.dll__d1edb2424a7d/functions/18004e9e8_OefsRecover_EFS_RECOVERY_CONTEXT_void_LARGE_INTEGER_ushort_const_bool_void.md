# OefsRecover(_EFS_RECOVERY_CONTEXT *,void *,_LARGE_INTEGER *,ushort const *,bool,void *)

- ea: `0x18004e9e8`
- end: `0x18004eeff`
- name: `?OefsRecover@@YAJPEAU_EFS_RECOVERY_CONTEXT@@PEAXPEAT_LARGE_INTEGER@@PEBG_N1@Z`
- size: `1303`
- prototype: `int(struct _EFS_RECOVERY_CONTEXT *, void *, union _LARGE_INTEGER *, const unsigned __int16 *, bool, void *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023dc4`

## callees

- `0x180005045`
- `0x180006cec`
- `0x18000b10c`
- `0x18000b12c`
- `0x18000dc68`
- `0x18000ef20`
- `0x18000ef44`
- `0x180017510`
- `0x180018fcc`
- `0x180025694`
- `0x180047508`
- `0x18004c61c`
- `0x18004d01c`
- `0x18004d25c`
- `0x18004d2d0`
- `0x18004d314`
- `0x18004d944`
- `0x18004dcbc`
- `0x18004e9e8`
- `0x18004f244`
- `0x18004f4f8`
- `0x18004f9cc`
- `0x180051820`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18004ed9d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18004ed9d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004ea4a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004ea4a`
- `ntdll!NtCreateFile` at `0x18004eb68`
- `ntdll!NtCreateFile` at `0x18004ec2d`
- `ntdll!NtCreateFile` at `0x18004eb68`
- `ntdll!NtCreateFile` at `0x18004ec2d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18004eac1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18004eac1`

## string_xrefs

- `0x18004ea55`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall OefsRecover(
        HANDLE *a1,
        void *a2,
        union _LARGE_INTEGER *a3,
        const unsigned __int16 *a4,
        bool a5,
        void *a6)
{
  const char *v10; // r9
  __int64 v11; // rdx
  _QWORD *v12; // rax
  const char *v13; // r9
  unsigned int v14; // ebx
  NTSTATUS v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  int LastError; // eax
  const char *v23; // r9
  unsigned int v24; // ebx
  int v25; // eax
  __int64 v26; // rdx
  int AllocationSize; // [rsp+20h] [rbp-E0h]
  PLARGE_INTEGER AllocationSizea; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h]
  char v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h] BYREF
  char v36; // [rsp+98h] [rbp-68h]
  _QWORD v37[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v41; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v42[24]; // [rsp+108h] [rbp+8h] BYREF
  char v43[8]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v44[112]; // [rsp+128h] [rbp+28h] BYREF
  char v45; // [rsp+198h] [rbp+98h]
  _BYTE v46[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v47; // [rsp+1A8h] [rbp+A8h]
  __int64 v48; // [rsp+1B0h] [rbp+B0h]
  DWORD dwFileAttributes; // [rsp+1B8h] [rbp+B8h]
  const unsigned __int16 *v50; // [rsp+1C0h] [rbp+C0h]
  struct _UNICODE_STRING *p_NtPathName; // [rsp+1C8h] [rbp+C8h]
  char v52; // [rsp+1D0h] [rbp+D0h]
  char v53; // [rsp+1D1h] [rbp+D1h]
  bool v54; // [rsp+1D2h] [rbp+D2h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+3E0h] [rbp+2E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+468h] [rbp+368h]

  v43[0] = 0;
  memset_0(v44, 0, sizeof(v44));
  v45 = 0;
  if ( !ImpersonateLoggedOnUser(a1[1]) )
  {
    v11 = 1225;
LABEL_3:
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
      v10);
    goto LABEL_7;
  }
  v43[0] = 1;
  if ( !(unsigned __int8)EfsGetUserInfo((struct _EFS_USER_INFO *)v44) )
  {
    v11 = 1227;
    goto LABEL_3;
  }
  v45 = 1;
LABEL_7:
  NtPathName = 0;
  v12 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
          &v41,
          (__int64)&NtPathName);
  wil::ScopeExit__lambda_a7ca0a91241e9ab77aa2572ce8686cf0___(v42, v12);
  if ( RtlDosPathNameToNtPathName_U(a4, &NtPathName, 0, 0) )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.Attributes, 0, 24);
    v37[0] = 524296;
    v37[1] = a3;
    ObjectAttributes.RootDirectory = a2;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v37;
    FileHandle = 0;
    IoStatusBlock = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &FileHandle,
      0);
    v15 = NtCreateFile(&FileHandle, 0x100180u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x202060u, 0, 0);
    if ( v15 == -1073741638 )
    {
      MarkFileForDelete(a6);
      v16 = 3221225659LL;
      v17 = 1289;
LABEL_11:
      v14 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)v17,
              (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
              (const char *)v16,
              AllocationSize);
LABEL_12:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
      goto LABEL_45;
    }
    if ( v15 == -1073741811 )
    {
      wil::details::in1diag3::Log_NtStatus(
        retaddr,
        (void *)0x50D,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)0xC000000DLL,
        AllocationSize);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &NtPathName;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &FileHandle,
        0);
      v15 = NtCreateFile(&FileHandle, 0x100180u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x200060u, 0, 0);
      if ( v15 == -1073741766 || v15 == -1073741772 )
      {
        wil::details::in1diag3::Log_NtStatus(
          retaddr,
          (void *)0x515,
          (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
          (const char *)(unsigned int)v15,
          AllocationSize);
        MarkFileForDelete(a6);
LABEL_44:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
        v14 = 0;
        goto LABEL_45;
      }
    }
    if ( v15 < 0 )
    {
      v16 = (unsigned int)v15;
      v17 = 1306;
      goto LABEL_11;
    }
    memset_0(v46, 0, 0x240u);
    v18 = OefspGetFileInformation(FileHandle, (struct OEFS_FILE_INFORMATION *)v46);
    v14 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51E,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)(unsigned int)v18,
        AllocationSize);
      goto LABEL_12;
    }
    v50 = a4;
    p_NtPathName = &NtPathName;
    v52 = 1;
    v54 = a5;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    LOBYTE(v30) = 0;
    AllocationSizea = (PLARGE_INTEGER)&v30;
    v19 = OefsExclusiveOperationContext::Acquire(&v32, v47, v48, !a5);
    v14 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x528,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)(unsigned int)v19,
        (int)&v30);
LABEL_23:
      OefsExclusiveOperationContext::~OefsExclusiveOperationContext((OefsExclusiveOperationContext *)&v32);
      goto LABEL_12;
    }
    if ( !(_BYTE)v30 )
    {
      v20 = 32;
      v21 = 1324;
LABEL_26:
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v21,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                    (const char *)v20,
                    (unsigned int)&v30);
LABEL_27:
      v14 = LastError;
      goto LABEL_23;
    }
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( !GetFileInformationByHandle(FileHandle, &FileInformation) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x531,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                    v23);
      goto LABEL_27;
    }
    dwFileAttributes = FileInformation.dwFileAttributes;
    v24 = EfspCheckReparseTag(FileHandle);
    if ( v24 )
    {
      MarkFileForDelete(a6);
      v20 = v24;
      v21 = 1337;
      goto LABEL_26;
    }
    v35 = 0;
    v36 = 1;
    if ( (FileInformation.dwFileAttributes & 0x4000) != 0 )
    {
      v25 = EfsStreamAndFileKey::GetFromFile((EfsStreamAndFileKey *)&v35, (struct _EFS_USER_INFO *)v44, FileHandle);
      v14 = v25;
      if ( v25 < 0 )
      {
        v26 = 1345;
LABEL_35:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
          (const char *)(unsigned int)v25,
          (int)AllocationSizea);
        EfsStreamAndFileKey::~EfsStreamAndFileKey((EfsStreamAndFileKey *)&v35);
        goto LABEL_23;
      }
      v53 = 1;
      if ( (_QWORD)v35 && *((_QWORD *)&v35 + 1) )
      {
        if ( a5 )
        {
          v25 = OefspEncryptFile(
                  FileHandle,
                  (const struct OEFS_FILE_INFORMATION *)v46,
                  (struct EfsStreamAndFileKey *)&v35,
                  0,
                  0);
          v14 = v25;
          if ( v25 < 0 )
          {
            v26 = 1353;
            goto LABEL_35;
          }
        }
        else
        {
          v25 = OefspDecryptFile(
                  FileHandle,
                  (const struct OEFS_FILE_INFORMATION *)v46,
                  (struct EfsStreamAndFileKey *)&v35,
                  0,
                  0);
          v14 = v25;
          if ( v25 < 0 )
          {
            v26 = 1357;
            goto LABEL_35;
          }
        }
      }
    }
    MarkFileForDelete(a6);
    EfsStreamAndFileKey::~EfsStreamAndFileKey((EfsStreamAndFileKey *)&v35);
    OefsExclusiveOperationContext::~OefsExclusiveOperationContext((OefsExclusiveOperationContext *)&v32);
    goto LABEL_44;
  }
  v14 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x4FA,
          (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
          v13);
LABEL_45:
  wil::details::ScopeExitFn__lambda_a7ca0a91241e9ab77aa2572ce8686cf0___::_ScopeExitFn__lambda_a7ca0a91241e9ab77aa2572ce8686cf0___(v42);
  ImpersonationHelper::~ImpersonationHelper((ImpersonationHelper *)v43);
  return v14;
}

```

## disassembly

```asm
0x18004e9e8  push    rbp
0x18004e9ea  push    rbx
0x18004e9eb  push    rsi
0x18004e9ec  push    rdi
0x18004e9ed  push    r12
0x18004e9ef  push    r13
0x18004e9f1  push    r14
0x18004e9f3  push    r15
0x18004e9f5  lea     rbp, [rsp-328h]
0x18004e9fd  sub     rsp, 428h
0x18004ea04  mov     rax, cs:__security_cookie
0x18004ea0b  xor     rax, rsp
0x18004ea0e  mov     [rbp+360h+var_48], rax
0x18004ea15  mov     rdi, r9
0x18004ea18  mov     r15, r8
0x18004ea1b  mov     r14, rdx
0x18004ea1e  mov     rbx, rcx
0x18004ea21  mov     rsi, [rbp+360h+arg_28]
0x18004ea28  xor     r12d, r12d
0x18004ea2b  mov     [rbp+360h+var_340], r12b
0x18004ea2f  xor     edx, edx; Val
0x18004ea31  lea     r8d, [r12+70h]; Size
0x18004ea36  lea     rcx, [rbp+360h+var_338]; void *
0x18004ea3a  call    memset_0
0x18004ea3f  mov     [rbp+360h+var_2C8], r12b
0x18004ea46  mov     rcx, [rbx+8]; hToken
0x18004ea4a  call    cs:__imp_ImpersonateLoggedOnUser
0x18004ea50  lea     ebx, [r12+1]
0x18004ea55  lea     r13, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004ea5c  test    eax, eax
0x18004ea5e  jnz     short loc_18004EA76
0x18004ea60  mov     edx, 4C9h; void *
0x18004ea65  mov     r8, r13; unsigned int
0x18004ea68  mov     rcx, [rbp+368h]; this
0x18004ea6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004ea74  jmp     short loc_18004EA93
0x18004ea76  mov     [rbp+360h+var_340], bl
0x18004ea79  lea     rcx, [rbp+360h+var_338]
0x18004ea7d  call    EfsGetUserInfo
0x18004ea82  test    al, al
0x18004ea84  jnz     short loc_18004EA8D
0x18004ea86  mov     edx, 4CBh
0x18004ea8b  jmp     short loc_18004EA65
0x18004ea8d  mov     [rbp+360h+var_2C8], bl
0x18004ea93  xorps   xmm0, xmm0
0x18004ea96  movups  xmmword ptr [rbp+360h+NtPathName.Length], xmm0
0x18004ea9a  lea     rdx, [rbp+360h+NtPathName]
0x18004ea9e  lea     rcx, [rbp+360h+var_360]
0x18004eaa2  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18004eaa7  mov     rdx, rax
0x18004eaaa  lea     rcx, [rbp+360h+var_358]
0x18004eaae  call    wil__ScopeExit__lambda_a7ca0a91241e9ab77aa2572ce8686cf0___
0x18004eab3  nop
0x18004eab4  xor     r9d, r9d; DirectoryInfo
0x18004eab7  xor     r8d, r8d; NtFileNamePart
0x18004eaba  lea     rdx, [rbp+360h+NtPathName]; NtPathName
0x18004eabe  mov     rcx, rdi; DosPathName
0x18004eac1  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18004eac7  test    al, al
0x18004eac9  jnz     short loc_18004EAE6
0x18004eacb  mov     rcx, [rbp+368h]; this
0x18004ead2  mov     r8, r13; unsigned int
0x18004ead5  mov     edx, 4FAh; void *
0x18004eada  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004eadf  mov     ebx, eax
0x18004eae1  jmp     loc_18004EEC7
0x18004eae6  mov     qword ptr [rbp+360h+ObjectAttributes.Length], 30h ; '0'
0x18004eaee  mov     qword ptr [rbp+360h+ObjectAttributes.Attributes], r12
0x18004eaf2  mov     [rbp+360h+var_3C0], 80008h
0x18004eafa  mov     [rbp+360h+var_3B8], r15
0x18004eafe  mov     r15d, 30h ; '0'
0x18004eb04  mov     [rbp+360h+ObjectAttributes.RootDirectory], r14
0x18004eb08  lea     rax, [rbp+360h+var_3C0]
0x18004eb0c  mov     [rbp+360h+ObjectAttributes.ObjectName], rax
0x18004eb10  xorps   xmm0, xmm0
0x18004eb13  movdqu  xmmword ptr [rbp+360h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004eb18  mov     [rsp+460h+FileHandle], r12
0x18004eb1d  movups  xmmword ptr [rbp+360h+IoStatusBlock], xmm0
0x18004eb21  xor     edx, edx
0x18004eb23  lea     rcx, [rsp+460h+FileHandle]
0x18004eb28  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004eb2d  mov     [rsp+460h+EaLength], r12d; EaLength
0x18004eb32  mov     [rsp+460h+EaBuffer], r12; EaBuffer
0x18004eb37  mov     [rsp+460h+CreateOptions], 202060h; CreateOptions
0x18004eb3f  mov     [rsp+460h+CreateDisposition], ebx; CreateDisposition
0x18004eb43  lea     r14d, [r15-29h]
0x18004eb47  mov     [rsp+460h+ShareAccess], r14d; ShareAccess
0x18004eb4c  mov     [rsp+460h+FileAttributes], r12d; FileAttributes
0x18004eb51  mov     [rsp+460h+AllocationSize], r12; int
0x18004eb56  lea     r9, [rbp+360h+IoStatusBlock]; IoStatusBlock
0x18004eb5a  lea     r8, [rbp+360h+ObjectAttributes]; ObjectAttributes
0x18004eb5e  mov     edx, 100180h; DesiredAccess
0x18004eb63  lea     rcx, [rsp+460h+FileHandle]; FileHandle
0x18004eb68  call    cs:__imp_NtCreateFile
0x18004eb6e  cmp     eax, 0C00000BAh
0x18004eb73  jnz     short loc_18004EBA8
0x18004eb75  mov     rcx, rsi
0x18004eb78  call    MarkFileForDelete
0x18004eb7d  mov     r9d, 0C00000BBh; char *
0x18004eb83  mov     edx, 509h; void *
0x18004eb88  mov     r8, r13; unsigned int
0x18004eb8b  mov     rcx, [rbp+368h]; this
0x18004eb92  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004eb97  mov     ebx, eax
0x18004eb99  lea     rcx, [rsp+460h+FileHandle]
0x18004eb9e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004eba3  jmp     loc_18004EEC7
0x18004eba8  mov     r9d, 0C000000Dh; char *
0x18004ebae  cmp     eax, r9d
0x18004ebb1  jnz     loc_18004EC65
0x18004ebb7  mov     rcx, [rbp+368h]; this
0x18004ebbe  mov     r8, r13; unsigned int
0x18004ebc1  mov     edx, 50Dh; void *
0x18004ebc6  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x18004ebcb  mov     [rbp+360h+ObjectAttributes.Length], r15d
0x18004ebcf  mov     [rbp+360h+ObjectAttributes.RootDirectory], r12
0x18004ebd3  mov     [rbp+360h+ObjectAttributes.Attributes], 40h ; '@'
0x18004ebda  lea     rax, [rbp+360h+NtPathName]
0x18004ebde  mov     [rbp+360h+ObjectAttributes.ObjectName], rax
0x18004ebe2  xorps   xmm0, xmm0
0x18004ebe5  movdqu  xmmword ptr [rbp+360h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004ebea  xor     edx, edx
0x18004ebec  lea     rcx, [rsp+460h+FileHandle]
0x18004ebf1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004ebf6  mov     [rsp+460h+EaLength], r12d; EaLength
0x18004ebfb  mov     [rsp+460h+EaBuffer], r12; EaBuffer
0x18004ec00  mov     [rsp+460h+CreateOptions], 200060h; CreateOptions
0x18004ec08  mov     [rsp+460h+CreateDisposition], ebx; CreateDisposition
0x18004ec0c  mov     [rsp+460h+ShareAccess], r14d; ShareAccess
0x18004ec11  mov     [rsp+460h+FileAttributes], r12d; FileAttributes
0x18004ec16  mov     [rsp+460h+AllocationSize], r12; int
0x18004ec1b  lea     r9, [rbp+360h+IoStatusBlock]; IoStatusBlock
0x18004ec1f  lea     r8, [rbp+360h+ObjectAttributes]; ObjectAttributes
0x18004ec23  mov     edx, 100180h; DesiredAccess
0x18004ec28  lea     rcx, [rsp+460h+FileHandle]; FileHandle
0x18004ec2d  call    cs:__imp_NtCreateFile
0x18004ec33  cmp     eax, 0C000003Ah
0x18004ec38  jz      short loc_18004EC41
0x18004ec3a  cmp     eax, 0C0000034h
0x18004ec3f  jnz     short loc_18004EC65
0x18004ec41  mov     rcx, [rbp+368h]; this
0x18004ec48  mov     r9d, eax; char *
0x18004ec4b  mov     r8, r13; unsigned int
0x18004ec4e  mov     edx, 515h; void *
0x18004ec53  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x18004ec58  mov     rcx, rsi
0x18004ec5b  call    MarkFileForDelete
0x18004ec60  jmp     loc_18004EEBA
0x18004ec65  test    eax, eax
0x18004ec67  jns     short loc_18004EC76
0x18004ec69  mov     r9d, eax
0x18004ec6c  mov     edx, 51Ah
0x18004ec71  jmp     loc_18004EB88
0x18004ec76  xor     edx, edx; Val
0x18004ec78  mov     r8d, 240h; Size
0x18004ec7e  lea     rcx, [rbp+360h+var_2C0]; void *
0x18004ec85  call    memset_0
0x18004ec8a  lea     rdx, [rbp+360h+var_2C0]; struct OEFS_FILE_INFORMATION *
0x18004ec91  mov     rcx, [rsp+460h+FileHandle]; FileHandle
0x18004ec96  call    ?OefspGetFileInformation@@YAJPEAXPEAUOEFS_FILE_INFORMATION@@@Z; OefspGetFileInformation(void *,OEFS_FILE_INFORMATION *)
0x18004ec9b  mov     ebx, eax
0x18004ec9d  test    eax, eax
0x18004ec9f  jns     short loc_18004ECBD
0x18004eca1  mov     rcx, [rbp+368h]; this
0x18004eca8  mov     r9d, eax; char *
0x18004ecab  mov     r8, r13; unsigned int
0x18004ecae  mov     edx, 51Eh; void *
0x18004ecb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ecb8  jmp     loc_18004EB99
0x18004ecbd  mov     [rbp+360h+var_2A0], rdi
0x18004ecc4  lea     rax, [rbp+360h+NtPathName]
0x18004ecc8  mov     [rbp+360h+var_298], rax
0x18004eccf  mov     [rbp+360h+var_290], 1
0x18004ecd6  movzx   edi, [rbp+360h+arg_20]
0x18004ecdd  mov     [rbp+360h+var_28E], dil
0x18004ece4  mov     [rsp+460h+var_3F0], r12d
0x18004ece9  mov     [rsp+460h+var_3E8], r12
0x18004ecee  mov     [rbp+360h+var_3E0], r12b
0x18004ecf2  mov     byte ptr [rsp+460h+var_400], r12b
0x18004ecf7  mov     r9d, edi
0x18004ecfa  xor     r9d, 1
0x18004ecfe  lea     rax, [rsp+460h+var_400]
0x18004ed03  mov     [rsp+460h+AllocationSize], rax; int
0x18004ed08  mov     r8, [rbp+360h+var_2B0]
0x18004ed0f  mov     edx, [rbp+360h+var_2B8]
0x18004ed15  lea     rcx, [rsp+460h+var_3F0]
0x18004ed1a  call    ?Acquire@OefsExclusiveOperationContext@@QEAAJK_JW4_OEFS_EXCLUSIVE_OPERATION@@PEA_N@Z; OefsExclusiveOperationContext::Acquire(ulong,__int64,_OEFS_EXCLUSIVE_OPERATION,bool *)
0x18004ed1f  mov     ebx, eax
0x18004ed21  test    eax, eax
0x18004ed23  jns     short loc_18004ED4C
0x18004ed25  mov     rcx, [rbp+368h]; this
0x18004ed2c  mov     r9d, eax; char *
0x18004ed2f  mov     r8, r13; unsigned int
0x18004ed32  mov     edx, 528h; void *
0x18004ed37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ed3c  nop
0x18004ed3d  lea     rcx, [rsp+460h+var_3F0]; this
0x18004ed42  call    ??1OefsExclusiveOperationContext@@QEAA@XZ; OefsExclusiveOperationContext::~OefsExclusiveOperationContext(void)
0x18004ed47  jmp     loc_18004EB99
0x18004ed4c  cmp     byte ptr [rsp+460h+var_400], r12b
0x18004ed51  jnz     short loc_18004ED71
0x18004ed53  mov     r9d, 20h ; ' '; char *
0x18004ed59  mov     edx, 52Ch; void *
0x18004ed5e  mov     r8, r13; unsigned int
0x18004ed61  mov     rcx, [rbp+368h]; this
0x18004ed68  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004ed6d  mov     ebx, eax
0x18004ed6f  jmp     short loc_18004ED3D
0x18004ed71  xorps   xmm0, xmm0
0x18004ed74  xor     eax, eax
0x18004ed76  movups  xmmword ptr [rbp+360h+FileInformation.dwFileAttributes], xmm0
0x18004ed7d  movups  xmmword ptr [rbp+360h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18004ed84  movups  xmmword ptr [rbp+360h+FileInformation.nFileSizeHigh], xmm0
0x18004ed8b  mov     [rbp+360h+FileInformation.nFileIndexLow], eax
0x18004ed91  lea     rdx, [rbp+360h+FileInformation]; lpFileInformation
0x18004ed98  mov     rcx, [rsp+460h+FileHandle]; hFile
0x18004ed9d  call    cs:__imp_GetFileInformationByHandle
0x18004eda3  test    eax, eax
0x18004eda5  jnz     short loc_18004EDBD
0x18004eda7  mov     rcx, [rbp+368h]; this
0x18004edae  mov     r8, r13; unsigned int
0x18004edb1  mov     edx, 531h; void *
0x18004edb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004edbb  jmp     short loc_18004ED6D
0x18004edbd  mov     eax, [rbp+360h+FileInformation.dwFileAttributes]
0x18004edc3  mov     [rbp+360h+var_2A8], eax
0x18004edc9  mov     rcx, [rsp+460h+FileHandle]; FileHandle
0x18004edce  call    EfspCheckReparseTag
0x18004edd3  mov     ebx, eax
0x18004edd5  test    eax, eax
0x18004edd7  jz      short loc_18004EDEE
0x18004edd9  mov     rcx, rsi
0x18004eddc  call    MarkFileForDelete
0x18004ede1  mov     r9d, ebx
0x18004ede4  mov     edx, 539h
0x18004ede9  jmp     loc_18004ED5E
0x18004edee  xorps   xmm0, xmm0
0x18004edf1  movdqu  [rbp+360h+var_3D8], xmm0
0x18004edf6  mov     [rbp+360h+var_3C8], 1
0x18004edfa  test    [rbp+360h+FileInformation.dwFileAttributes], 4000h
0x18004ee04  jz      loc_18004EE9C
0x18004ee0a  mov     r8, [rsp+460h+FileHandle]; void *
0x18004ee0f  lea     rdx, [rbp+360h+var_338]; struct _EFS_USER_INFO *
0x18004ee13  lea     rcx, [rbp+360h+var_3D8]; this
0x18004ee17  call    ?GetFromFile@EfsStreamAndFileKey@@QEAAJPEAU_EFS_USER_INFO@@PEAX@Z; EfsStreamAndFileKey::GetFromFile(_EFS_USER_INFO *,void *)
0x18004ee1c  mov     ebx, eax
0x18004ee1e  test    eax, eax
0x18004ee20  jns     short loc_18004EE48
0x18004ee22  mov     edx, 541h; void *
0x18004ee27  mov     rcx, [rbp+368h]; this
0x18004ee2e  mov     r9d, eax; char *
0x18004ee31  mov     r8, r13; unsigned int
0x18004ee34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ee39  nop
0x18004ee3a  lea     rcx, [rbp+360h+var_3D8]; this
0x18004ee3e  call    ??1EfsStreamAndFileKey@@QEAA@XZ; EfsStreamAndFileKey::~EfsStreamAndFileKey(void)
0x18004ee43  jmp     loc_18004ED3D
0x18004ee48  mov     [rbp+360h+var_28F], 1
0x18004ee4f  cmp     qword ptr [rbp+360h+var_3D8], r12
0x18004ee53  jz      short loc_18004EE9C
0x18004ee55  cmp     qword ptr [rbp+360h+var_3D8+8], r12
0x18004ee59  jz      short loc_18004EE9C
0x18004ee5b  mov     [rsp+460h+AllocationSize], r12; unsigned __int8 *
0x18004ee60  xor     r9d, r9d; void *
0x18004ee63  lea     r8, [rbp+360h+var_3D8]; struct EfsStreamAndFileKey *
0x18004ee67  lea     rdx, [rbp+360h+var_2C0]; struct OEFS_FILE_INFORMATION *
0x18004ee6e  mov     rcx, [rsp+460h+FileHandle]; void *
0x18004ee73  test    dil, dil
0x18004ee76  jz      short loc_18004EE8A
0x18004ee78  call    ?OefspEncryptFile@@YAJPEAXAEBUOEFS_FILE_INFORMATION@@AEAVEfsStreamAndFileKey@@0PEAE@Z; OefspEncryptFile(void *,OEFS_FILE_INFORMATION const &,EfsStreamAndFileKey &,void *,uchar *)
0x18004ee7d  mov     ebx, eax
0x18004ee7f  test    eax, eax
0x18004ee81  jns     short loc_18004EE9C
0x18004ee83  mov     edx, 549h
0x18004ee88  jmp     short loc_18004EE27
0x18004ee8a  call    ?OefspDecryptFile@@YAJPEAXAEBUOEFS_FILE_INFORMATION@@AEAVEfsStreamAndFileKey@@0PEAE@Z; OefspDecryptFile(void *,OEFS_FILE_INFORMATION const &,EfsStreamAndFileKey &,void *,uchar *)
0x18004ee8f  mov     ebx, eax
0x18004ee91  test    eax, eax
0x18004ee93  jns     short loc_18004EE9C
0x18004ee95  mov     edx, 54Dh
0x18004ee9a  jmp     short loc_18004EE27
0x18004ee9c  mov     rcx, rsi
0x18004ee9f  call    MarkFileForDelete
0x18004eea4  nop
0x18004eea5  lea     rcx, [rbp+360h+var_3D8]; this
0x18004eea9  call    ??1EfsStreamAndFileKey@@QEAA@XZ; EfsStreamAndFileKey::~EfsStreamAndFileKey(void)
0x18004eeae  nop
0x18004eeaf  lea     rcx, [rsp+460h+var_3F0]; this
0x18004eeb4  call    ??1OefsExclusiveOperationContext@@QEAA@XZ; OefsExclusiveOperationContext::~OefsExclusiveOperationContext(void)
0x18004eeb9  nop
0x18004eeba  lea     rcx, [rsp+460h+FileHandle]
0x18004eebf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004eec4  mov     ebx, r12d
0x18004eec7  lea     rcx, [rbp+360h+var_358]
0x18004eecb  call    wil__details__ScopeExitFn__lambda_a7ca0a91241e9ab77aa2572ce8686cf0______ScopeExitFn__lambda_a7ca0a91241e9ab77aa2572ce8686cf0___
0x18004eed0  nop
0x18004eed1  lea     rcx, [rbp+360h+var_340]; this
0x18004eed5  call    ??1ImpersonationHelper@@QEAA@XZ; ImpersonationHelper::~ImpersonationHelper(void)
0x18004eeda  mov     eax, ebx
0x18004eedc  mov     rcx, [rbp+360h+var_48]
  ... truncated ...
```
