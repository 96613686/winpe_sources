# EfsOpenFileRawInternal

- ea: `0x1801e6c58`
- end: `0x1801e71c2`
- name: `EfsOpenFileRawInternal`
- size: `1386`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801e71c8`

## callees

- `0x18000465c`
- `0x18006cb78`
- `0x180095fdc`
- `0x180098bf4`
- `0x1800a0104`
- `0x1800a021c`
- `0x1800a4444`
- `0x1800a5970`
- `0x1800a9078`
- `0x1800baaac`
- `0x1800bacb0`
- `0x1800cfaac`
- `0x1800cfaf4`
- `0x1800de0ac`
- `0x1800f0260`
- `0x1801e6c58`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1801e7189`
- `ntdll!RtlFreeUnicodeString` at `0x1801e7189`
- `ntdll!NtCreateFile` at `0x1801e6e4b`
- `ntdll!NtCreateFile` at `0x1801e6fe7`
- `ntdll!NtCreateFile` at `0x1801e6e4b`
- `ntdll!NtCreateFile` at `0x1801e6fe7`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1801e6cbb`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1801e6cbb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1801e70e7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1801e70e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801e714a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801e714a`

## string_xrefs

- `0x1801e6cd1`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1801e6db0`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1801e70a0`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1801e70f6`: `onecore\admin\appmodel\common\encryption.cpp`
- `0x1801e6f8c`: `EfsOpenFileRawInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EfsOpenFileRawInternal(const WCHAR *a1, int a2, __int64 a3, _QWORD *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  ULONG CreateDisposition; // edi
  int v9; // r14d
  int v10; // r13d
  int v11; // edx
  ACCESS_MASK v12; // ebx
  ULONG CreateOptions; // esi
  int v14; // eax
  int v15; // r15d
  NTSTATUS v16; // r15d
  const struct _tlgProvider_t *v17; // rax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  const WCHAR *v23; // r15
  ULONG v24; // r12d
  const struct _tlgProvider_t *v25; // rax
  int v26; // r8d
  int v27; // r9d
  unsigned int LastError; // eax
  const char *v29; // r9
  __int64 v30; // rdx
  void *v31; // rax
  int AllocationSize; // [rsp+20h] [rbp-E0h]
  int AllocationSizea; // [rsp+20h] [rbp-E0h]
  ULONG InBuffer; // [rsp+60h] [rbp-A0h] BYREF
  DWORD BytesReturned; // [rsp+64h] [rbp-9Ch] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG FileAttributes; // [rsp+70h] [rbp-90h]
  LPCWSTR lpFileName; // [rsp+78h] [rbp-88h]
  LPCWSTR v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  __int64 v43; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v44; // [rsp+A0h] [rbp-60h] BYREF
  void *TokenHandle[2]; // [rsp+A8h] [rbp-58h] BYREF
  char v46; // [rsp+B8h] [rbp-48h]
  char v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  _QWORD *v49; // [rsp+D0h] [rbp-30h]
  char v50[8]; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+E0h] [rbp-20h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-10h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+120h] [rbp+20h] BYREF
  _OWORD FileInformation[2]; // [rsp+130h] [rbp+30h] BYREF
  int v55; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v49 = a4;
  lpFileName = a1;
  wil::run_as_self_failfast(v50);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  UnicodeString = 0;
  v6 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &UnicodeString, 0, 0);
  if ( v6 >= 0 )
  {
    FileAttributes = 128;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    CreateDisposition = 1;
    v9 = a2 & 2;
    v10 = a2 & 1;
    if ( (a2 & 1) != 0 )
    {
      InBuffer = 0;
      v11 = 18;
      CreateDisposition = 3;
      if ( (a2 & 2) != 0 )
      {
        v12 = 1048963;
        CreateOptions = 32801;
        FileAttributes = 144;
      }
      else
      {
        v12 = 1048962;
        CreateOptions = 2132000;
        if ( (a2 & 4) != 0 )
          FileAttributes = 130;
      }
    }
    else
    {
      v11 = 17;
      InBuffer = 5;
      if ( (a2 & 2) != 0 )
      {
        v12 = 129;
        CreateOptions = 1;
      }
      else
      {
        CreateOptions = 2099232;
        v12 = 1048704;
      }
    }
    *(_OWORD *)TokenHandle = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v14 = Common::Deployment::Privilege::Initialize(TokenHandle, v11);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecore\\admin\\appmodel\\common\\encryption.cpp",
        (const char *)(unsigned int)v14,
        AllocationSize);
      Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
      v7 = v15;
      goto LABEL_45;
    }
    if ( Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)TokenHandle) >= 0 )
    {
      CreateOptions |= 0x4000u;
      if ( (a2 & 2) == 0 )
        v12 |= 0x10000u;
    }
    else
    {
      v12 |= v10 + 1;
    }
    FileHandle = (void *)-1LL;
    IoStatusBlock = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &FileHandle,
      -1);
    v16 = NtCreateFile(
            &FileHandle,
            v12,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            FileAttributes,
            InBuffer,
            CreateDisposition,
            CreateOptions,
            0,
            0);
    if ( v16 == -1073741757 )
    {
      v17 = AppXDeploymentServerTelemetry::Provider();
      v20 = *(_DWORD *)v17;
      if ( a2 )
      {
        if ( v20 <= 5 )
        {
          v23 = lpFileName;
        }
        else
        {
          v44 = (LPCWSTR)CreateOptions;
          v43 = CreateDisposition;
          v42 = InBuffer;
          v41 = v12;
          v23 = lpFileName;
          v40 = lpFileName;
          BytesReturned = -1073741757;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (_DWORD)v17,
            (unsigned int)byte_1802B6903,
            v18,
            v19,
            (__int64)&BytesReturned,
            (__int64)&v40,
            (__int64)&v41,
            (__int64)&v42,
            (__int64)&v43,
            (__int64)&v44);
        }
        Common::Deployment::LogFileInUse<AppXDeploymentServerTelemetry::FileInUse>(v23);
      }
      else
      {
        if ( v20 > 5 && (unsigned __int8)tlgKeywordOn(v17, 0x400000000000LL) )
        {
          v40 = (LPCWSTR)CreateOptions;
          v41 = CreateDisposition;
          v42 = InBuffer;
          v43 = v12;
          v44 = lpFileName;
          BytesReturned = -1073741757;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v21,
            (unsigned int)&byte_1802B6887,
            v21,
            v22,
            (__int64)&BytesReturned,
            (__int64)&v44,
            (__int64)&v43,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v40);
        }
        v12 = 1179785;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &FileHandle,
        -1);
      v24 = InBuffer;
      v16 = NtCreateFile(
              &FileHandle,
              v12,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              FileAttributes,
              InBuffer,
              CreateDisposition,
              CreateOptions,
              0,
              0);
    }
    else
    {
      v24 = InBuffer;
    }
    if ( v16 < 0 )
    {
      v25 = AppXDeploymentServerTelemetry::Provider();
      if ( *(_DWORD *)v25 > 5u && (unsigned __int8)tlgKeywordOn(v25, 0x400000000000LL) )
      {
        v44 = (LPCWSTR)CreateOptions;
        v43 = CreateDisposition;
        v42 = v24;
        v41 = v12;
        v40 = lpFileName;
        BytesReturned = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v26,
          (unsigned int)&byte_1802B6987,
          v26,
          v27,
          (__int64)&BytesReturned,
          (__int64)&v40,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v44);
      }
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x177,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\encryption.cpp",
                    (const char *)(unsigned int)v16,
                    AllocationSizea);
      goto LABEL_34;
    }
    v7 = 0;
    if ( v10 && v9 )
    {
      memset(FileInformation, 0, sizeof(FileInformation));
      v55 = 0;
      if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, FileInformation) )
      {
        v30 = 387;
LABEL_39:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v30,
                      (unsigned int)"onecore\\admin\\appmodel\\common\\encryption.cpp",
                      v29);
LABEL_34:
        v7 = LastError;
LABEL_44:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
        Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
        goto LABEL_45;
      }
      if ( (FileInformation[0] & 0x800) != 0 )
      {
        LOWORD(InBuffer) = 0;
        BytesReturned = 0;
        if ( !DeviceIoControl(FileHandle, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
        {
          v30 = 400;
          goto LABEL_39;
        }
      }
    }
    v31 = FileHandle;
    FileHandle = (void *)-1LL;
    *v49 = v31;
    goto LABEL_44;
  }
  v7 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0xC2,
         (unsigned int)"onecore\\admin\\appmodel\\common\\encryption.cpp",
         (const char *)(unsigned int)v6,
         AllocationSize);
LABEL_45:
  RtlFreeUnicodeString(&UnicodeString);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v50);
  return v7;
}

```

## disassembly

```asm
0x1801e6c58  mov     [rsp-8+arg_8], rbx
0x1801e6c5d  push    rbp
0x1801e6c5e  push    rsi
0x1801e6c5f  push    rdi
0x1801e6c60  push    r12
0x1801e6c62  push    r13
0x1801e6c64  push    r14
0x1801e6c66  push    r15
0x1801e6c68  lea     rbp, [rsp-60h]
0x1801e6c6d  sub     rsp, 160h
0x1801e6c74  mov     rax, cs:__security_cookie
0x1801e6c7b  xor     rax, rsp
0x1801e6c7e  mov     [rbp+90h+var_38], rax
0x1801e6c82  mov     [rbp+90h+var_C0], r9
0x1801e6c86  mov     r12d, edx
0x1801e6c89  mov     rbx, rcx
0x1801e6c8c  mov     [rsp+190h+lpFileName], rcx
0x1801e6c91  lea     rcx, [rbp+90h+var_B8]
0x1801e6c95  call    ?run_as_self_failfast@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self_failfast(void)
0x1801e6c9a  nop
0x1801e6c9b  xorps   xmm0, xmm0
0x1801e6c9e  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x1801e6ca2  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x1801e6ca6  movups  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801e6caa  movups  xmmword ptr [rbp+90h+UnicodeString.Length], xmm0
0x1801e6cae  xor     r9d, r9d
0x1801e6cb1  xor     r8d, r8d
0x1801e6cb4  lea     rdx, [rbp+90h+UnicodeString]
0x1801e6cb8  mov     rcx, rbx
0x1801e6cbb  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1801e6cc1  xor     ecx, ecx
0x1801e6cc3  test    eax, eax
0x1801e6cc5  jns     short loc_1801E6CE9
0x1801e6cc7  mov     rcx, [rbp+98h]; this
0x1801e6cce  mov     r9d, eax; char *
0x1801e6cd1  lea     r8, aOnecoreAdminAp_73; "onecore\\admin\\appmodel\\common\\encry"...
0x1801e6cd8  mov     edx, 0C2h; void *
0x1801e6cdd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801e6ce2  mov     ebx, eax
0x1801e6ce4  jmp     loc_1801E7185
0x1801e6ce9  mov     [rsp+190h+var_120], 80h
0x1801e6cf1  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x1801e6cf8  mov     [rbp+90h+ObjectAttributes.RootDirectory], rcx
0x1801e6cfc  mov     [rbp+90h+ObjectAttributes.Attributes], 40h ; '@'
0x1801e6d03  lea     rax, [rbp+90h+UnicodeString]
0x1801e6d07  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x1801e6d0b  xorps   xmm0, xmm0
0x1801e6d0e  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801e6d13  mov     r13d, r12d
0x1801e6d16  mov     edi, 1
0x1801e6d1b  mov     r14d, r12d
0x1801e6d1e  and     r14d, 2
0x1801e6d22  and     r13d, edi
0x1801e6d25  jz      short loc_1801E6D64
0x1801e6d27  mov     [rsp+190h+InBuffer], ecx
0x1801e6d2b  lea     edx, [rdi+11h]
0x1801e6d2e  lea     edi, [rdx-0Fh]
0x1801e6d31  test    r14d, r14d
0x1801e6d34  jz      short loc_1801E6D4A
0x1801e6d36  mov     ebx, 100183h
0x1801e6d3b  mov     esi, 8021h
0x1801e6d40  mov     [rsp+190h+var_120], 90h
0x1801e6d48  jmp     short loc_1801E6D87
0x1801e6d4a  mov     ebx, 100182h
0x1801e6d4f  mov     esi, 208820h
0x1801e6d54  test    r12b, 4
0x1801e6d58  jz      short loc_1801E6D87
0x1801e6d5a  mov     [rsp+190h+var_120], 82h
0x1801e6d62  jmp     short loc_1801E6D87
0x1801e6d64  mov     edx, 11h; int
0x1801e6d69  mov     [rsp+190h+InBuffer], 5
0x1801e6d71  test    r14d, r14d
0x1801e6d74  jz      short loc_1801E6D7D
0x1801e6d76  lea     ebx, [rdx+70h]
0x1801e6d79  mov     esi, edi
0x1801e6d7b  jmp     short loc_1801E6D87
0x1801e6d7d  mov     esi, 200820h
0x1801e6d82  mov     ebx, 100080h
0x1801e6d87  movdqu  xmmword ptr [rbp+90h+TokenHandle], xmm0
0x1801e6d8c  mov     [rbp+90h+var_D8], cl
0x1801e6d8f  mov     [rbp+90h+var_D0], cl
0x1801e6d92  mov     [rbp+90h+var_C8], rcx
0x1801e6d96  lea     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x1801e6d9a  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x1801e6d9f  mov     r15d, eax
0x1801e6da2  test    eax, eax
0x1801e6da4  jns     short loc_1801E6DD3
0x1801e6da6  mov     rcx, [rbp+98h]; this
0x1801e6dad  mov     r9d, eax; char *
0x1801e6db0  lea     r8, aOnecoreAdminAp_73; "onecore\\admin\\appmodel\\common\\encry"...
0x1801e6db7  mov     edx, 113h; void *
0x1801e6dbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e6dc1  nop
0x1801e6dc2  lea     rcx, [rbp+90h+TokenHandle]; this
0x1801e6dc6  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x1801e6dcb  mov     ebx, r15d
0x1801e6dce  jmp     loc_1801E7185
0x1801e6dd3  lea     rcx, [rbp+90h+TokenHandle]; this
0x1801e6dd7  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x1801e6ddc  xor     r15d, r15d
0x1801e6ddf  test    eax, eax
0x1801e6de1  jns     short loc_1801E6DEB
0x1801e6de3  lea     eax, [r13+1]
0x1801e6de7  or      ebx, eax
0x1801e6de9  jmp     short loc_1801E6DF8
0x1801e6deb  bts     esi, 0Eh
0x1801e6def  test    r14d, r14d
0x1801e6df2  jnz     short loc_1801E6DF8
0x1801e6df4  bts     ebx, 10h
0x1801e6df8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801e6dfc  mov     [rsp+190h+FileHandle], rax
0x1801e6e01  xorps   xmm0, xmm0
0x1801e6e04  movups  xmmword ptr [rbp+90h+IoStatusBlock], xmm0
0x1801e6e08  mov     rdx, rax
0x1801e6e0b  lea     rcx, [rsp+190h+FileHandle]
0x1801e6e10  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801e6e15  mov     [rsp+190h+EaLength], r15d; EaLength
0x1801e6e1a  mov     [rsp+190h+EaBuffer], r15; EaBuffer
0x1801e6e1f  mov     [rsp+190h+CreateOptions], esi; CreateOptions
0x1801e6e23  mov     [rsp+190h+CreateDisposition], edi; CreateDisposition
0x1801e6e27  mov     eax, [rsp+190h+InBuffer]
0x1801e6e2b  mov     [rsp+190h+ShareAccess], eax; ShareAccess
0x1801e6e2f  mov     eax, [rsp+190h+var_120]
0x1801e6e33  mov     [rsp+190h+FileAttributes], eax; FileAttributes
0x1801e6e37  mov     [rsp+190h+AllocationSize], r15; AllocationSize
0x1801e6e3c  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x1801e6e40  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1801e6e44  mov     edx, ebx; DesiredAccess
0x1801e6e46  lea     rcx, [rsp+190h+FileHandle]; FileHandle
0x1801e6e4b  call    cs:__imp_NtCreateFile
0x1801e6e51  mov     r15d, eax
0x1801e6e54  cmp     eax, 0C0000043h
0x1801e6e59  jnz     loc_1801E6FF2
0x1801e6e5f  call    ?Provider@AppXDeploymentServerTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppXDeploymentServerTelemetry::Provider(void)
0x1801e6e64  mov     ecx, [rax]
0x1801e6e66  test    r12d, r12d
0x1801e6e69  jnz     loc_1801E6F0C
0x1801e6e6f  mov     r8, rax
0x1801e6e72  cmp     ecx, 5
0x1801e6e75  jbe     loc_1801E6F02
0x1801e6e7b  mov     rdx, 400000000000h
0x1801e6e85  mov     rcx, rax
0x1801e6e88  call    _tlgKeywordOn
0x1801e6e8d  test    al, al
0x1801e6e8f  jz      short loc_1801E6F02
0x1801e6e91  mov     ecx, esi
0x1801e6e93  mov     [rbp+90h+var_110], rcx
0x1801e6e97  mov     eax, edi
0x1801e6e99  mov     [rbp+90h+var_108], rax
0x1801e6e9d  mov     eax, [rsp+190h+InBuffer]
0x1801e6ea1  mov     [rbp+90h+var_100], rax
0x1801e6ea5  mov     eax, ebx
0x1801e6ea7  mov     [rbp+90h+var_F8], rax
0x1801e6eab  mov     r15, [rsp+190h+lpFileName]
0x1801e6eb0  mov     [rbp+90h+var_F0], r15
0x1801e6eb4  mov     [rsp+190h+BytesReturned], 0C0000043h
0x1801e6ebc  lea     rax, [rbp+90h+var_110]
0x1801e6ec0  mov     [rsp+190h+EaBuffer], rax
0x1801e6ec5  lea     rax, [rbp+90h+var_108]
0x1801e6ec9  mov     qword ptr [rsp+190h+CreateOptions], rax
0x1801e6ece  lea     rax, [rbp+90h+var_100]
0x1801e6ed2  mov     qword ptr [rsp+190h+CreateDisposition], rax
0x1801e6ed7  lea     rax, [rbp+90h+var_F8]
0x1801e6edb  mov     qword ptr [rsp+190h+ShareAccess], rax
0x1801e6ee0  lea     rax, [rbp+90h+var_F0]
0x1801e6ee4  mov     qword ptr [rsp+190h+FileAttributes], rax
0x1801e6ee9  lea     rax, [rsp+190h+BytesReturned]
0x1801e6eee  mov     [rsp+190h+AllocationSize], rax
0x1801e6ef3  lea     rdx, byte_1802B6887
0x1801e6efa  mov     rcx, r8
0x1801e6efd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1801e6f02  mov     ebx, 120089h
0x1801e6f07  jmp     loc_1801E6FA0
0x1801e6f0c  cmp     ecx, 5
0x1801e6f0f  jbe     short loc_1801E6F84
0x1801e6f11  mov     ecx, esi
0x1801e6f13  mov     [rbp+90h+var_F0], rcx
0x1801e6f17  mov     ecx, edi
0x1801e6f19  mov     [rbp+90h+var_F8], rcx
0x1801e6f1d  mov     ecx, [rsp+190h+InBuffer]
0x1801e6f21  mov     [rbp+90h+var_100], rcx
0x1801e6f25  mov     ecx, ebx
0x1801e6f27  mov     [rbp+90h+var_108], rcx
0x1801e6f2b  mov     r15, [rsp+190h+lpFileName]
0x1801e6f30  mov     [rbp+90h+var_110], r15
0x1801e6f34  mov     [rsp+190h+BytesReturned], 0C0000043h
0x1801e6f3c  lea     rcx, [rbp+90h+var_F0]
0x1801e6f40  mov     [rsp+190h+EaBuffer], rcx
0x1801e6f45  lea     rcx, [rbp+90h+var_F8]
0x1801e6f49  mov     qword ptr [rsp+190h+CreateOptions], rcx
0x1801e6f4e  lea     rcx, [rbp+90h+var_100]
0x1801e6f52  mov     qword ptr [rsp+190h+CreateDisposition], rcx
0x1801e6f57  lea     rcx, [rbp+90h+var_108]
0x1801e6f5b  mov     qword ptr [rsp+190h+ShareAccess], rcx
0x1801e6f60  lea     rcx, [rbp+90h+var_110]
0x1801e6f64  mov     qword ptr [rsp+190h+FileAttributes], rcx
0x1801e6f69  lea     rcx, [rsp+190h+BytesReturned]
0x1801e6f6e  mov     [rsp+190h+AllocationSize], rcx
0x1801e6f73  lea     rdx, byte_1802B6903
0x1801e6f7a  mov     rcx, rax
0x1801e6f7d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1801e6f82  jmp     short loc_1801E6F89
0x1801e6f84  mov     r15, [rsp+190h+lpFileName]
0x1801e6f89  xor     r9d, r9d
0x1801e6f8c  lea     r8, aEfsopenfileraw; "EfsOpenFileRawInternal"
0x1801e6f93  mov     edx, 0D0000043h
0x1801e6f98  mov     rcx, r15; lpFileName
0x1801e6f9b  call    ??$LogFileInUse@VFileInUse@AppXDeploymentServerTelemetry@@@Deployment@Common@@YAXPEBGJ0_N@Z; Common::Deployment::LogFileInUse<AppXDeploymentServerTelemetry::FileInUse>(ushort const *,long,ushort const *,bool)
0x1801e6fa0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1801e6fa4  lea     rcx, [rsp+190h+FileHandle]
0x1801e6fa9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801e6fae  xor     ecx, ecx
0x1801e6fb0  mov     [rsp+190h+EaLength], ecx; EaLength
0x1801e6fb4  mov     [rsp+190h+EaBuffer], rcx; EaBuffer
0x1801e6fb9  mov     [rsp+190h+CreateOptions], esi; CreateOptions
0x1801e6fbd  mov     [rsp+190h+CreateDisposition], edi; CreateDisposition
0x1801e6fc1  mov     r12d, [rsp+190h+InBuffer]
0x1801e6fc6  mov     [rsp+190h+ShareAccess], r12d; ShareAccess
0x1801e6fcb  mov     eax, [rsp+190h+var_120]
0x1801e6fcf  mov     [rsp+190h+FileAttributes], eax; FileAttributes
0x1801e6fd3  mov     [rsp+190h+AllocationSize], rcx; AllocationSize
0x1801e6fd8  lea     r9, [rbp+90h+IoStatusBlock]; IoStatusBlock
0x1801e6fdc  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1801e6fe0  mov     edx, ebx; DesiredAccess
0x1801e6fe2  lea     rcx, [rsp+190h+FileHandle]; FileHandle
0x1801e6fe7  call    cs:__imp_NtCreateFile
0x1801e6fed  mov     r15d, eax
0x1801e6ff0  jmp     short loc_1801E6FF7
0x1801e6ff2  mov     r12d, [rsp+190h+InBuffer]
0x1801e6ff7  test    r15d, r15d
0x1801e6ffa  jns     loc_1801E70B8
0x1801e7000  call    ?Provider@AppXDeploymentServerTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppXDeploymentServerTelemetry::Provider(void)
0x1801e7005  mov     r8, rax
0x1801e7008  mov     ecx, [rax]
0x1801e700a  cmp     ecx, 5
0x1801e700d  jbe     loc_1801E7096
0x1801e7013  mov     rdx, 400000000000h
0x1801e701d  mov     rcx, rax
0x1801e7020  call    _tlgKeywordOn
0x1801e7025  test    al, al
0x1801e7027  jz      short loc_1801E7096
0x1801e7029  mov     ecx, esi
0x1801e702b  mov     [rbp+90h+var_F0], rcx
0x1801e702f  mov     eax, edi
0x1801e7031  mov     [rbp+90h+var_F8], rax
0x1801e7035  mov     eax, r12d
0x1801e7038  mov     [rbp+90h+var_100], rax
0x1801e703c  mov     eax, ebx
0x1801e703e  mov     [rbp+90h+var_108], rax
0x1801e7042  mov     rax, [rsp+190h+lpFileName]
0x1801e7047  mov     [rbp+90h+var_110], rax
0x1801e704b  mov     [rsp+190h+BytesReturned], r15d
0x1801e7050  lea     rax, [rbp+90h+var_F0]
0x1801e7054  mov     [rsp+190h+EaBuffer], rax
0x1801e7059  lea     rax, [rbp+90h+var_F8]
0x1801e705d  mov     qword ptr [rsp+190h+CreateOptions], rax
0x1801e7062  lea     rax, [rbp+90h+var_100]
0x1801e7066  mov     qword ptr [rsp+190h+CreateDisposition], rax
0x1801e706b  lea     rax, [rbp+90h+var_108]
0x1801e706f  mov     qword ptr [rsp+190h+ShareAccess], rax
0x1801e7074  lea     rax, [rbp+90h+var_110]
0x1801e7078  mov     qword ptr [rsp+190h+FileAttributes], rax
0x1801e707d  lea     rax, [rsp+190h+BytesReturned]
0x1801e7082  mov     [rsp+190h+AllocationSize], rax; int
0x1801e7087  lea     rdx, byte_1802B6987
0x1801e708e  mov     rcx, r8
0x1801e7091  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1801e7096  mov     rcx, [rbp+98h]; this
0x1801e709d  mov     r9d, r15d; char *
0x1801e70a0  lea     r8, aOnecoreAdminAp_73; "onecore\\admin\\appmodel\\common\\encry"...
0x1801e70a7  mov     edx, 177h; void *
0x1801e70ac  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801e70b1  mov     ebx, eax
0x1801e70b3  jmp     loc_1801E7170
0x1801e70b8  xor     ebx, ebx
0x1801e70ba  test    r13d, r13d
0x1801e70bd  jz      loc_1801E715B
0x1801e70c3  test    r14d, r14d
0x1801e70c6  jz      loc_1801E715B
0x1801e70cc  xorps   xmm0, xmm0
0x1801e70cf  xor     eax, eax
0x1801e70d1  movups  [rbp+90h+FileInformation], xmm0
0x1801e70d5  movups  [rbp+90h+var_50], xmm0
0x1801e70d9  mov     [rbp+90h+var_40], eax
0x1801e70dc  lea     r8, [rbp+90h+FileInformation]; lpFileInformation
0x1801e70e0  xor     edx, edx; fInfoLevelId
0x1801e70e2  mov     rcx, [rsp+190h+lpFileName]; lpFileName
0x1801e70e7  call    cs:__imp_GetFileAttributesExW
0x1801e70ed  test    eax, eax
0x1801e70ef  jnz     short loc_1801E710B
0x1801e70f1  mov     edx, 183h; void *
0x1801e70f6  lea     r8, aOnecoreAdminAp_73; "onecore\\admin\\appmodel\\common\\encry"...
0x1801e70fd  mov     rcx, [rbp+98h]; this
0x1801e7104  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e7109  jmp     short loc_1801E70B1
0x1801e710b  test    dword ptr [rbp+90h+FileInformation], 800h
0x1801e7112  jz      short loc_1801E715B
0x1801e7114  mov     word ptr [rsp+190h+InBuffer], bx
0x1801e7119  mov     [rsp+190h+BytesReturned], ebx
0x1801e711d  mov     qword ptr [rsp+190h+CreateDisposition], rbx; lpOverlapped
  ... truncated ...
```
