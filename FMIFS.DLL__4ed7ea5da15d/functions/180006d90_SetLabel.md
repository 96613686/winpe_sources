# SetLabel

- ea: `0x180006d90`
- end: `0x18000700d`
- name: `SetLabel`
- size: `637`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003b70`
- `0x180006d90`
- `0x180009780`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180006f29`
- `ntdll!RtlNtStatusToDosError` at `0x180006fc2`
- `ntdll!RtlNtStatusToDosError` at `0x180006f29`
- `ntdll!RtlNtStatusToDosError` at `0x180006fc2`
- `ntdll!NtClose` at `0x180006f5e`
- `ntdll!NtClose` at `0x180006fe2`
- `ntdll!NtClose` at `0x180006f5e`
- `ntdll!NtClose` at `0x180006fe2`
- `ntdll!NtSetVolumeInformationFile` at `0x180006fb4`
- `ntdll!NtSetVolumeInformationFile` at `0x180006fb4`
- `ntdll!NtOpenFile` at `0x180006f08`
- `ntdll!NtOpenFile` at `0x180006f08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006fd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006fd7`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180006e0f`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180006f4f`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180006e0f`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180006f4f`
- `ulib!?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z` at `0x180006e46`
- `ulib!?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z` at `0x180006f83`
- `ulib!?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z` at `0x180006e46`
- `ulib!?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z` at `0x180006f83`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006dc2`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006dcc`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006dfe`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006dc2`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006dcc`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180006dfe`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006e63`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006e6d`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006e77`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006fec`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006ff6`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180007000`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006e63`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006e6d`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006e77`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006fec`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180006ff6`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180007000`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180006ea5`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180006f8d`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180006ea5`
- `ulib!?QueryChCount@WSTRING@@QEBAKXZ` at `0x180006f8d`
- `IfsUtil!?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z` at `0x180006e21`
- `IfsUtil!?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z` at `0x180006e21`

## pseudocode

```c
char __fastcall SetLabel(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char v4; // bl
  DWORD v5; // ecx
  int v7; // edi
  int v8; // eax
  DWORD v9; // eax
  void *FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  void *v11[2]; // [rsp+38h] [rbp-C8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v14[48]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v15[48]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v16[56]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int FsInformation; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v18[262]; // [rsp+124h] [rbp+24h] BYREF

  DSTRING::DSTRING((DSTRING *)v16);
  DSTRING::DSTRING((DSTRING *)v15);
  FileHandle = 0;
  *(_OWORD *)v11 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  DSTRING::DSTRING((DSTRING *)v14);
  if ( !WSTRING::Initialize((WSTRING *)v16, a1, 0xFFFFFFFF)
    || !IFS_SYSTEM::DosDriveNameToNtDriveName((const struct WSTRING *)v16, (struct WSTRING *)v15) )
  {
    goto LABEL_6;
  }
  v4 = 1;
  v11[1] = WSTRING::QueryWSTR((WSTRING *)v15, 0, 0xFFFFFFFF, 0, 0, 1u);
  if ( !v11[1] )
  {
    v5 = 8;
LABEL_5:
    SetLastError(v5);
LABEL_6:
    DSTRING::~DSTRING((DSTRING *)v14);
    DSTRING::~DSTRING((DSTRING *)v15);
    DSTRING::~DSTRING((DSTRING *)v16);
    return 0;
  }
  ObjectAttributes.Length = 48;
  LOWORD(v11[0]) = 2 * WSTRING::QueryChCount((WSTRING *)v15);
  WORD1(v11[0]) = v11[0];
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v11;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x100003u, &ObjectAttributes, &IoStatusBlock, 3u, 0x12u);
  if ( v7 < 0 )
  {
    operator delete(v11[1]);
    v11[1] = 0;
    v5 = RtlNtStatusToDosError(v7);
    goto LABEL_5;
  }
  operator delete(v11[1]);
  v11[1] = 0;
  if ( !WSTRING::Initialize((WSTRING *)v14, a2, 0xFFFFFFFF) )
  {
    NtClose(FileHandle);
    goto LABEL_6;
  }
  WSTRING::QueryWSTR((WSTRING *)v14, 0, 0xFFFFFFFF, v18, 0x106u, 1u);
  FsInformation = 2 * WSTRING::QueryChCount((WSTRING *)v14);
  v8 = NtSetVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x210u, FileFsLabelInformation);
  if ( v8 < 0 )
  {
    v4 = 0;
    v9 = RtlNtStatusToDosError(v8);
    if ( v9 == 154 )
      v9 = 123;
    SetLastError(v9);
  }
  NtClose(FileHandle);
  DSTRING::~DSTRING((DSTRING *)v14);
  DSTRING::~DSTRING((DSTRING *)v15);
  DSTRING::~DSTRING((DSTRING *)v16);
  return v4;
}

```

## disassembly

```asm
0x180006d90  mov     [rsp-8+arg_10], rbx
0x180006d95  push    rbp
0x180006d96  push    rsi
0x180006d97  push    rdi
0x180006d98  lea     rbp, [rsp-240h]
0x180006da0  sub     rsp, 340h
0x180006da7  mov     rax, cs:__security_cookie
0x180006dae  xor     rax, rsp
0x180006db1  mov     [rbp+250h+var_20], rax
0x180006db8  mov     rbx, rcx
0x180006dbb  mov     rsi, rdx
0x180006dbe  lea     rcx, [rbp+250h+var_268]
0x180006dc2  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180006dc8  lea     rcx, [rbp+250h+var_298]
0x180006dcc  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180006dd2  xorps   xmm1, xmm1
0x180006dd5  mov     [rsp+350h+FileHandle], 0
0x180006dde  xorps   xmm0, xmm0
0x180006de1  lea     rcx, [rbp+250h+var_2C8]
0x180006de5  movups  xmmword ptr [rsp+350h+var_318], xmm0
0x180006dea  movups  xmmword ptr [rsp+350h+ObjectAttributes.Length], xmm1
0x180006def  movups  xmmword ptr [rsp+350h+ObjectAttributes.ObjectName], xmm1
0x180006df4  movups  xmmword ptr [rsp+350h+ObjectAttributes.SecurityDescriptor], xmm1
0x180006df9  movups  xmmword ptr [rsp+350h+IoStatusBlock], xmm0
0x180006dfe  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180006e04  or      r8d, 0FFFFFFFFh
0x180006e08  lea     rcx, [rbp+250h+var_268]
0x180006e0c  mov     rdx, rbx
0x180006e0f  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180006e15  test    al, al
0x180006e17  jz      short loc_180006E5F
0x180006e19  lea     rdx, [rbp+250h+var_298]
0x180006e1d  lea     rcx, [rbp+250h+var_268]
0x180006e21  call    cs:__imp_?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z; IFS_SYSTEM::DosDriveNameToNtDriveName(WSTRING const *,WSTRING *)
0x180006e27  test    al, al
0x180006e29  jz      short loc_180006E5F
0x180006e2b  mov     bl, 1
0x180006e2d  lea     rcx, [rbp+250h+var_298]
0x180006e31  mov     byte ptr [rsp+350h+OpenOptions], bl
0x180006e35  xor     r9d, r9d
0x180006e38  or      r8d, 0FFFFFFFFh
0x180006e3c  mov     [rsp+350h+ShareAccess], 0
0x180006e44  xor     edx, edx
0x180006e46  call    cs:__imp_?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z; WSTRING::QueryWSTR(ulong,ulong,ushort *,ulong,uchar)
0x180006e4c  mov     [rsp+350h+var_318+8], rax
0x180006e51  test    rax, rax
0x180006e54  jnz     short loc_180006EA1
0x180006e56  lea     ecx, [rax+8]; dwErrCode
0x180006e59  call    cs:__imp_SetLastError
0x180006e5f  lea     rcx, [rbp+250h+var_2C8]
0x180006e63  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180006e69  lea     rcx, [rbp+250h+var_298]
0x180006e6d  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180006e73  lea     rcx, [rbp+250h+var_268]
0x180006e77  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180006e7d  xor     al, al
0x180006e7f  mov     rcx, [rbp+250h+var_20]
0x180006e86  xor     rcx, rsp; StackCookie
0x180006e89  call    __security_check_cookie
0x180006e8e  mov     rbx, [rsp+350h+arg_10]
0x180006e96  add     rsp, 340h
0x180006e9d  pop     rdi
0x180006e9e  pop     rsi
0x180006e9f  pop     rbp
0x180006ea0  retn
0x180006ea1  lea     rcx, [rbp+250h+var_298]
0x180006ea5  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x180006eab  xorps   xmm0, xmm0
0x180006eae  mov     [rsp+350h+OpenOptions], 12h; OpenOptions
0x180006eb6  add     ax, ax
0x180006eb9  mov     [rsp+350h+ObjectAttributes.Length], 30h ; '0'
0x180006ec1  mov     word ptr [rsp+350h+var_318], ax
0x180006ec6  lea     r9, [rsp+350h+IoStatusBlock]; IoStatusBlock
0x180006ecb  mov     word ptr [rsp+350h+var_318+2], ax
0x180006ed0  lea     r8, [rsp+350h+ObjectAttributes]; ObjectAttributes
0x180006ed5  lea     rax, [rsp+350h+var_318]
0x180006eda  mov     [rsp+350h+ObjectAttributes.RootDirectory], 0
0x180006ee3  mov     edx, 100003h; DesiredAccess
0x180006ee8  mov     [rsp+350h+ObjectAttributes.ObjectName], rax
0x180006eed  lea     rcx, [rsp+350h+FileHandle]; FileHandle
0x180006ef2  mov     [rsp+350h+ObjectAttributes.Attributes], 40h ; '@'
0x180006efa  movdqu  xmmword ptr [rsp+350h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006f00  mov     [rsp+350h+ShareAccess], 3; ShareAccess
0x180006f08  call    cs:__imp_NtOpenFile
0x180006f0e  mov     rcx, [rsp+350h+var_318+8]; void *
0x180006f13  mov     edi, eax
0x180006f15  test    eax, eax
0x180006f17  jns     short loc_180006F36
0x180006f19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006f1e  mov     ecx, edi; Status
0x180006f20  mov     [rsp+350h+var_318+8], 0
0x180006f29  call    cs:__imp_RtlNtStatusToDosError
0x180006f2f  mov     ecx, eax
0x180006f31  jmp     loc_180006E59
0x180006f36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006f3b  or      r8d, 0FFFFFFFFh
0x180006f3f  mov     [rsp+350h+var_318+8], 0
0x180006f48  mov     rdx, rsi
0x180006f4b  lea     rcx, [rbp+250h+var_2C8]
0x180006f4f  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180006f55  test    al, al
0x180006f57  jnz     short loc_180006F69
0x180006f59  mov     rcx, [rsp+350h+FileHandle]; Handle
0x180006f5e  call    cs:__imp_NtClose
0x180006f64  jmp     loc_180006E5F
0x180006f69  mov     byte ptr [rsp+350h+OpenOptions], bl
0x180006f6d  lea     r9, [rbp+250h+var_22C]
0x180006f71  or      r8d, 0FFFFFFFFh
0x180006f75  mov     [rsp+350h+ShareAccess], 106h
0x180006f7d  xor     edx, edx
0x180006f7f  lea     rcx, [rbp+250h+var_2C8]
0x180006f83  call    cs:__imp_?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z; WSTRING::QueryWSTR(ulong,ulong,ushort *,ulong,uchar)
0x180006f89  lea     rcx, [rbp+250h+var_2C8]
0x180006f8d  call    cs:__imp_?QueryChCount@WSTRING@@QEBAKXZ; WSTRING::QueryChCount(void)
0x180006f93  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x180006f98  lea     r8, [rbp+250h+FsInformation]; FsInformation
0x180006f9c  add     eax, eax
0x180006f9e  mov     [rsp+350h+ShareAccess], 2; FsInformationClass
0x180006fa6  mov     r9d, 210h; Length
0x180006fac  mov     [rbp+250h+FsInformation], eax
0x180006faf  lea     rdx, [rsp+350h+IoStatusBlock]; IoStatusBlock
0x180006fb4  call    cs:__imp_NtSetVolumeInformationFile
0x180006fba  test    eax, eax
0x180006fbc  jns     short loc_180006FDD
0x180006fbe  mov     ecx, eax; Status
0x180006fc0  xor     bl, bl
0x180006fc2  call    cs:__imp_RtlNtStatusToDosError
0x180006fc8  mov     ecx, 7Bh ; '{'
0x180006fcd  cmp     eax, 9Ah
0x180006fd2  cmovz   eax, ecx
0x180006fd5  mov     ecx, eax; dwErrCode
0x180006fd7  call    cs:__imp_SetLastError
0x180006fdd  mov     rcx, [rsp+350h+FileHandle]; Handle
0x180006fe2  call    cs:__imp_NtClose
0x180006fe8  lea     rcx, [rbp+250h+var_2C8]
0x180006fec  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180006ff2  lea     rcx, [rbp+250h+var_298]
0x180006ff6  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180006ffc  lea     rcx, [rbp+250h+var_268]
0x180007000  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180007006  mov     al, bl
0x180007008  jmp     loc_180006E7F
```
