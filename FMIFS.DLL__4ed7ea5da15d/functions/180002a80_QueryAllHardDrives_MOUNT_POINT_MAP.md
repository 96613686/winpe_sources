# QueryAllHardDrives(MOUNT_POINT_MAP *)

- ea: `0x180002a80`
- end: `0x180002e83`
- name: `?QueryAllHardDrives@@YAEPEAVMOUNT_POINT_MAP@@@Z`
- size: `1027`
- prototype: `unsigned __int8 __fastcall(struct MOUNT_POINT_MAP *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800015d0`

## callees

- `0x180002a80`
- `0x180009780`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002e70`
- `ntdll!RtlNtStatusToDosError` at `0x180002e70`
- `ntdll!NtClose` at `0x180002d05`
- `ntdll!NtClose` at `0x180002d05`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180002cd5`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180002cd5`
- `ntdll!RtlEqualUnicodeString` at `0x180002c51`
- `ntdll!RtlEqualUnicodeString` at `0x180002c51`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180002cf8`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180002cf8`
- `ntdll!RtlInitUnicodeString` at `0x180002b5e`
- `ntdll!RtlInitUnicodeString` at `0x180002b6f`
- `ntdll!RtlInitUnicodeString` at `0x180002b80`
- `ntdll!RtlInitUnicodeString` at `0x180002b91`
- `ntdll!RtlInitUnicodeString` at `0x180002ba2`
- `ntdll!RtlInitUnicodeString` at `0x180002b5e`
- `ntdll!RtlInitUnicodeString` at `0x180002b6f`
- `ntdll!RtlInitUnicodeString` at `0x180002b80`
- `ntdll!RtlInitUnicodeString` at `0x180002b91`
- `ntdll!RtlInitUnicodeString` at `0x180002ba2`
- `ntdll!RtlPrefixUnicodeString` at `0x180002c69`
- `ntdll!RtlPrefixUnicodeString` at `0x180002d1b`
- `ntdll!RtlPrefixUnicodeString` at `0x180002df0`
- `ntdll!RtlPrefixUnicodeString` at `0x180002c69`
- `ntdll!RtlPrefixUnicodeString` at `0x180002d1b`
- `ntdll!RtlPrefixUnicodeString` at `0x180002df0`
- `ntdll!NtOpenDirectoryObject` at `0x180002bdf`
- `ntdll!NtOpenDirectoryObject` at `0x180002bdf`
- `ntdll!NtQueryDirectoryObject` at `0x180002c2a`
- `ntdll!NtQueryDirectoryObject` at `0x180002c2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e78`
- `ulib!?InsertString@WSTRING@@QEAAEKPEBV1@KK@Z` at `0x180002d83`
- `ulib!?InsertString@WSTRING@@QEAAEKPEBV1@KK@Z` at `0x180002d83`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180002b28`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180002d3b`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180002d5b`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180002b28`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180002d3b`
- `ulib!?Initialize@WSTRING@@QEAAEPEBGK@Z` at `0x180002d5b`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002af3`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002afd`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002b07`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002b11`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002af3`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002afd`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002b07`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002b11`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002dbc`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002dc6`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002dd0`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002dda`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002e07`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002e11`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002e1b`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002e25`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002dbc`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002dc6`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002dd0`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002dda`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002e07`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002e11`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002e1b`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x180002e25`
- `IfsUtil!?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z` at `0x180002d95`
- `IfsUtil!?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z` at `0x180002d95`
- `IfsUtil!?Initialize@MOUNT_POINT_MAP@@QEAAEXZ` at `0x180002b39`
- `IfsUtil!?Initialize@MOUNT_POINT_MAP@@QEAAEXZ` at `0x180002b39`
- `IfsUtil!?AddVolumeName@MOUNT_POINT_MAP@@QEAAEPEAVWSTRING@@0@Z` at `0x180002daa`
- `IfsUtil!?AddVolumeName@MOUNT_POINT_MAP@@QEAAEPEAVWSTRING@@0@Z` at `0x180002daa`
- `IfsUtil!?AddDriveName@MOUNT_POINT_MAP@@QEAAEPEAVWSTRING@@0@Z` at `0x180002e63`
- `IfsUtil!?AddDriveName@MOUNT_POINT_MAP@@QEAAEPEAVWSTRING@@0@Z` at `0x180002e63`

## string_xrefs

- `0x180002b4e`: `SymbolicLink`

## pseudocode

```c
unsigned __int8 __fastcall QueryAllHardDrives(struct MOUNT_POINT_MAP *a1)
{
  int v2; // eax
  BOOLEAN RestartScan; // al
  BOOLEAN v4; // di
  NTSTATUS v5; // ebx
  unsigned __int8 v6; // al
  DWORD v8; // eax
  struct _UNICODE_STRING LinkTarget; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  void *SymbolicLinkHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v13[48]; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v14; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  UNICODE_STRING v16; // [rsp+E0h] [rbp-20h] BYREF
  UNICODE_STRING v17; // [rsp+F0h] [rbp-10h] BYREF
  UNICODE_STRING v18; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v19[48]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v20[48]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v21[48]; // [rsp+170h] [rbp+70h] BYREF
  UNICODE_STRING Buffer; // [rsp+1A0h] [rbp+A0h] BYREF
  UNICODE_STRING String1; // [rsp+1B0h] [rbp+B0h] BYREF
  char v24; // [rsp+5A0h] [rbp+4A0h] BYREF

  ReturnLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SymbolicLinkHandle = 0;
  LinkTarget = 0;
  DestinationString = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v14 = 0;
  DSTRING::DSTRING((DSTRING *)v19);
  DSTRING::DSTRING((DSTRING *)v13);
  DSTRING::DSTRING((DSTRING *)v21);
  DSTRING::DSTRING((DSTRING *)v20);
  if ( !WSTRING::Initialize((WSTRING *)v20, L"\\\\?\\", 0xFFFFFFFF) || !MOUNT_POINT_MAP::Initialize(a1) )
    goto LABEL_21;
  LinkTarget.Buffer = (PWSTR)&v24;
  RtlInitUnicodeString(&DestinationString, L"SymbolicLink");
  RtlInitUnicodeString(&v17, L"\\Device\\Volume");
  RtlInitUnicodeString(&v18, L"\\Device\\Harddisk");
  RtlInitUnicodeString(&v16, L"Volume{");
  RtlInitUnicodeString(&v14, L"\\Global??");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v14;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtOpenDirectoryObject(&DirectoryHandle, 1u, &ObjectAttributes);
  if ( v2 < 0 )
  {
LABEL_26:
    v8 = RtlNtStatusToDosError(v2);
    SetLastError(v8);
LABEL_21:
    DSTRING::~DSTRING((DSTRING *)v20);
    DSTRING::~DSTRING((DSTRING *)v21);
    DSTRING::~DSTRING((DSTRING *)v13);
    DSTRING::~DSTRING((DSTRING *)v19);
    return 0;
  }
  for ( RestartScan = 1; ; RestartScan = 0 )
  {
    v2 = NtQueryDirectoryObject(DirectoryHandle, &Buffer, 0x400u, 1u, RestartScan, &Context, &ReturnLength);
    if ( v2 == -2147483622 )
      break;
    if ( v2 < 0 )
      goto LABEL_26;
    if ( RtlEqualUnicodeString(&String1, &DestinationString, 1u) )
    {
      v4 = RtlPrefixUnicodeString(&v16, &Buffer, 1u);
      if ( v4 || Buffer.Buffer[((unsigned __int64)Buffer.Length >> 1) - 1] == 58 )
      {
        ObjectAttributes.RootDirectory = DirectoryHandle;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 64;
        ObjectAttributes.ObjectName = &Buffer;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v2 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes);
        if ( v2 < 0 )
          goto LABEL_26;
        *(_DWORD *)&LinkTarget.Length = 0x2000000;
        v5 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, 0);
        NtClose(SymbolicLinkHandle);
        if ( v5 >= 0 && (RtlPrefixUnicodeString(&v17, &LinkTarget, 1u) || RtlPrefixUnicodeString(&v18, &LinkTarget, 1u)) )
        {
          if ( !WSTRING::Initialize((WSTRING *)v19, LinkTarget.Buffer, LinkTarget.Length >> 1)
            || !WSTRING::Initialize((WSTRING *)v13, Buffer.Buffer, Buffer.Length >> 1) )
          {
            goto LABEL_21;
          }
          if ( v4 )
          {
            if ( !WSTRING::InsertString((WSTRING *)v13, 0, (const struct WSTRING *)v20, 0, 0xFFFFFFFF)
              || !IFS_SYSTEM::DosDriveNameToNtDriveName((const struct WSTRING *)v13, (struct WSTRING *)v21) )
            {
              goto LABEL_21;
            }
            v6 = MOUNT_POINT_MAP::AddVolumeName(a1, (struct WSTRING *)v19, (struct WSTRING *)v21);
          }
          else
          {
            v6 = MOUNT_POINT_MAP::AddDriveName(a1, (struct WSTRING *)v19, (struct WSTRING *)v13);
          }
          if ( !v6 )
            goto LABEL_21;
        }
      }
    }
  }
  DSTRING::~DSTRING((DSTRING *)v20);
  DSTRING::~DSTRING((DSTRING *)v21);
  DSTRING::~DSTRING((DSTRING *)v13);
  DSTRING::~DSTRING((DSTRING *)v19);
  return 1;
}

```

## disassembly

```asm
0x180002a80  mov     [rsp-8+arg_8], rbx
0x180002a85  mov     [rsp-8+arg_10], rsi
0x180002a8a  push    rbp
0x180002a8b  push    rdi
0x180002a8c  push    r12
0x180002a8e  push    r14
0x180002a90  push    r15
0x180002a92  lea     rbp, [rsp-6B0h]
0x180002a9a  sub     rsp, 7B0h
0x180002aa1  mov     rax, cs:__security_cookie
0x180002aa8  xor     rax, rsp
0x180002aab  mov     [rbp+6D0h+var_30], rax
0x180002ab2  xorps   xmm0, xmm0
0x180002ab5  xorps   xmm1, xmm1
0x180002ab8  mov     rsi, rcx
0x180002abb  xor     r15d, r15d
0x180002abe  lea     rcx, [rbp+6D0h+var_6C0]
0x180002ac2  mov     [rsp+7D0h+var_780], r15d
0x180002ac7  movups  xmmword ptr [rsp+7D0h+ObjectAttributes.Length], xmm0
0x180002acc  mov     [rsp+7D0h+SymbolicLinkHandle], r15
0x180002ad1  movups  xmmword ptr [rsp+7D0h+ObjectAttributes.ObjectName], xmm0
0x180002ad6  movups  xmmword ptr [rbp+6D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002ada  movups  xmmword ptr [rsp+7D0h+LinkTarget.Length], xmm0
0x180002adf  movups  xmmword ptr [rbp+6D0h+DestinationString.Length], xmm1
0x180002ae3  movups  xmmword ptr [rbp+6D0h+var_6F0.Length], xmm0
0x180002ae7  movups  xmmword ptr [rbp+6D0h+var_6E0.Length], xmm1
0x180002aeb  movups  xmmword ptr [rbp+6D0h+var_6D0.Length], xmm0
0x180002aef  movups  xmmword ptr [rbp+6D0h+var_710.Length], xmm1
0x180002af3  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180002af9  lea     rcx, [rbp+6D0h+var_740]
0x180002afd  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180002b03  lea     rcx, [rbp+6D0h+var_660]
0x180002b07  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180002b0d  lea     rcx, [rbp+6D0h+var_690]
0x180002b11  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180002b17  mov     r8d, 0FFFFFFFFh
0x180002b1d  lea     rdx, asc_18000BB18; "\\\\?\\"
0x180002b24  lea     rcx, [rbp+6D0h+var_690]
0x180002b28  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180002b2e  test    al, al
0x180002b30  jz      loc_180002DB8
0x180002b36  mov     rcx, rsi
0x180002b39  call    cs:__imp_?Initialize@MOUNT_POINT_MAP@@QEAAEXZ; MOUNT_POINT_MAP::Initialize(void)
0x180002b3f  test    al, al
0x180002b41  jz      loc_180002DB8
0x180002b47  lea     rax, [rbp+6D0h+var_230]
0x180002b4e  lea     rdx, SourceString; "SymbolicLink"
0x180002b55  mov     [rsp+7D0h+LinkTarget.Buffer], rax
0x180002b5a  lea     rcx, [rbp+6D0h+DestinationString]; DestinationString
0x180002b5e  call    cs:__imp_RtlInitUnicodeString
0x180002b64  lea     rdx, aDeviceVolume; "\\Device\\Volume"
0x180002b6b  lea     rcx, [rbp+6D0h+var_6E0]; DestinationString
0x180002b6f  call    cs:__imp_RtlInitUnicodeString
0x180002b75  lea     rdx, aDeviceHarddisk; "\\Device\\Harddisk"
0x180002b7c  lea     rcx, [rbp+6D0h+var_6D0]; DestinationString
0x180002b80  call    cs:__imp_RtlInitUnicodeString
0x180002b86  lea     rdx, aVolume; "Volume{"
0x180002b8d  lea     rcx, [rbp+6D0h+var_6F0]; DestinationString
0x180002b91  call    cs:__imp_RtlInitUnicodeString
0x180002b97  lea     rdx, aGlobal; "\\Global??"
0x180002b9e  lea     rcx, [rbp+6D0h+var_710]; DestinationString
0x180002ba2  call    cs:__imp_RtlInitUnicodeString
0x180002ba8  lea     rax, [rbp+6D0h+var_710]
0x180002bac  mov     [rsp+7D0h+ObjectAttributes.Length], 30h ; '0'
0x180002bb4  xorps   xmm0, xmm0
0x180002bb7  mov     [rsp+7D0h+ObjectAttributes.ObjectName], rax
0x180002bbc  lea     r8, [rsp+7D0h+ObjectAttributes]; ObjectAttributes
0x180002bc1  mov     [rsp+7D0h+ObjectAttributes.RootDirectory], r15
0x180002bc6  mov     edx, 1; DesiredAccess
0x180002bcb  mov     [rsp+7D0h+ObjectAttributes.Attributes], 40h ; '@'
0x180002bd3  lea     rcx, DirectoryHandle; FileHandle
0x180002bda  movdqu  xmmword ptr [rbp+6D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002bdf  call    cs:__imp_NtOpenDirectoryObject
0x180002be5  test    eax, eax
0x180002be7  js      loc_180002E6E
0x180002bed  mov     al, 1
0x180002bef  lea     r14, Context
0x180002bf6  nop     word ptr [rax+rax+00000000h]
0x180002c00  lea     rcx, [rsp+7D0h+var_780]
0x180002c05  mov     r9b, 1; ReturnSingleEntry
0x180002c08  mov     [rsp+7D0h+ReturnLength], rcx; ReturnLength
0x180002c0d  lea     rdx, [rbp+6D0h+Buffer]; Buffer
0x180002c14  mov     rcx, cs:DirectoryHandle; DirectoryHandle
0x180002c1b  mov     r8d, 400h; BufferLength
0x180002c21  mov     [rsp+7D0h+Context], r14; Context
0x180002c26  mov     [rsp+7D0h+RestartScan], al; RestartScan
0x180002c2a  call    cs:__imp_NtQueryDirectoryObject
0x180002c30  cmp     eax, 8000001Ah
0x180002c35  jz      loc_180002E03
0x180002c3b  test    eax, eax
0x180002c3d  js      loc_180002E6E
0x180002c43  mov     r8b, 1; CaseInsensitive
0x180002c46  lea     rdx, [rbp+6D0h+DestinationString]; String2
0x180002c4a  lea     rcx, [rbp+6D0h+String1]; String1
0x180002c51  call    cs:__imp_RtlEqualUnicodeString
0x180002c57  test    al, al
0x180002c59  jz      short loc_180002C8F
0x180002c5b  mov     r8b, 1; CaseInsensitive
0x180002c5e  lea     rdx, [rbp+6D0h+Buffer]; String2
0x180002c65  lea     rcx, [rbp+6D0h+var_6F0]; String1
0x180002c69  call    cs:__imp_RtlPrefixUnicodeString
0x180002c6f  movzx   edi, al
0x180002c72  test    al, al
0x180002c74  jnz     short loc_180002C96
0x180002c76  movzx   edx, [rbp+6D0h+Buffer]
0x180002c7d  mov     rcx, [rbp+6D0h+var_628]
0x180002c84  shr     rdx, 1
0x180002c87  cmp     word ptr [rcx+rdx*2-2], 3Ah ; ':'
0x180002c8d  jz      short loc_180002C96
0x180002c8f  xor     al, al
0x180002c91  jmp     loc_180002C00
0x180002c96  mov     rcx, cs:DirectoryHandle
0x180002c9d  lea     rax, [rbp+6D0h+Buffer]
0x180002ca4  mov     [rsp+7D0h+ObjectAttributes.RootDirectory], rcx
0x180002ca9  lea     r8, [rsp+7D0h+ObjectAttributes]; ObjectAttributes
0x180002cae  xorps   xmm0, xmm0
0x180002cb1  mov     [rsp+7D0h+ObjectAttributes.Length], 30h ; '0'
0x180002cb9  lea     rcx, [rsp+7D0h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180002cbe  mov     [rsp+7D0h+ObjectAttributes.Attributes], 40h ; '@'
0x180002cc6  mov     edx, 0F0001h; DesiredAccess
0x180002ccb  mov     [rsp+7D0h+ObjectAttributes.ObjectName], rax
0x180002cd0  movdqu  xmmword ptr [rbp+6D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002cd5  call    cs:__imp_NtOpenSymbolicLinkObject
0x180002cdb  test    eax, eax
0x180002cdd  js      loc_180002E6E
0x180002ce3  mov     rcx, [rsp+7D0h+SymbolicLinkHandle]; SymLinkObjHandle
0x180002ce8  lea     rdx, [rsp+7D0h+LinkTarget]; LinkTarget
0x180002ced  xor     r8d, r8d; DataWritten
0x180002cf0  mov     dword ptr [rsp+7D0h+LinkTarget.Length], 2000000h
0x180002cf8  call    cs:__imp_NtQuerySymbolicLinkObject
0x180002cfe  mov     rcx, [rsp+7D0h+SymbolicLinkHandle]; Handle
0x180002d03  mov     ebx, eax
0x180002d05  call    cs:__imp_NtClose
0x180002d0b  test    ebx, ebx
0x180002d0d  js      short loc_180002C8F
0x180002d0f  mov     r8b, 1; CaseInsensitive
0x180002d12  lea     rdx, [rsp+7D0h+LinkTarget]; String2
0x180002d17  lea     rcx, [rbp+6D0h+var_6E0]; String1
0x180002d1b  call    cs:__imp_RtlPrefixUnicodeString
0x180002d21  test    al, al
0x180002d23  jz      loc_180002DE4
0x180002d29  movzx   r8d, [rsp+7D0h+LinkTarget.Length]
0x180002d2f  lea     rcx, [rbp+6D0h+var_6C0]
0x180002d33  mov     rdx, [rsp+7D0h+LinkTarget.Buffer]
0x180002d38  shr     r8d, 1
0x180002d3b  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180002d41  test    al, al
0x180002d43  jz      short loc_180002DB8
0x180002d45  movzx   r8d, [rbp+6D0h+Buffer]
0x180002d4d  lea     rcx, [rbp+6D0h+var_740]
0x180002d51  mov     rdx, [rbp+6D0h+var_628]
0x180002d58  shr     r8d, 1
0x180002d5b  call    cs:__imp_?Initialize@WSTRING@@QEAAEPEBGK@Z; WSTRING::Initialize(ushort const *,ulong)
0x180002d61  test    al, al
0x180002d63  jz      short loc_180002DB8
0x180002d65  test    dil, dil
0x180002d68  jz      loc_180002E58
0x180002d6e  xor     r9d, r9d
0x180002d71  mov     dword ptr [rsp+7D0h+RestartScan], 0FFFFFFFFh
0x180002d79  lea     r8, [rbp+6D0h+var_690]
0x180002d7d  xor     edx, edx
0x180002d7f  lea     rcx, [rbp+6D0h+var_740]
0x180002d83  call    cs:__imp_?InsertString@WSTRING@@QEAAEKPEBV1@KK@Z; WSTRING::InsertString(ulong,WSTRING const *,ulong,ulong)
0x180002d89  test    al, al
0x180002d8b  jz      short loc_180002DB8
0x180002d8d  lea     rdx, [rbp+6D0h+var_660]
0x180002d91  lea     rcx, [rbp+6D0h+var_740]
0x180002d95  call    cs:__imp_?DosDriveNameToNtDriveName@IFS_SYSTEM@@SAEPEBVWSTRING@@PEAV2@@Z; IFS_SYSTEM::DosDriveNameToNtDriveName(WSTRING const *,WSTRING *)
0x180002d9b  test    al, al
0x180002d9d  jz      short loc_180002DB8
0x180002d9f  lea     r8, [rbp+6D0h+var_660]
0x180002da3  mov     rcx, rsi
0x180002da6  lea     rdx, [rbp+6D0h+var_6C0]
0x180002daa  call    cs:__imp_?AddVolumeName@MOUNT_POINT_MAP@@QEAAEPEAVWSTRING@@0@Z; MOUNT_POINT_MAP::AddVolumeName(WSTRING *,WSTRING *)
0x180002db0  test    al, al
0x180002db2  jnz     loc_180002C8F
0x180002db8  lea     rcx, [rbp+6D0h+var_690]
0x180002dbc  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002dc2  lea     rcx, [rbp+6D0h+var_660]
0x180002dc6  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002dcc  lea     rcx, [rbp+6D0h+var_740]
0x180002dd0  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002dd6  lea     rcx, [rbp+6D0h+var_6C0]
0x180002dda  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002de0  xor     al, al
0x180002de2  jmp     short loc_180002E2D
0x180002de4  mov     r8b, 1; CaseInsensitive
0x180002de7  lea     rdx, [rsp+7D0h+LinkTarget]; String2
0x180002dec  lea     rcx, [rbp+6D0h+var_6D0]; String1
0x180002df0  call    cs:__imp_RtlPrefixUnicodeString
0x180002df6  test    al, al
0x180002df8  jnz     loc_180002D29
0x180002dfe  jmp     loc_180002C8F
0x180002e03  lea     rcx, [rbp+6D0h+var_690]
0x180002e07  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002e0d  lea     rcx, [rbp+6D0h+var_660]
0x180002e11  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002e17  lea     rcx, [rbp+6D0h+var_740]
0x180002e1b  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002e21  lea     rcx, [rbp+6D0h+var_6C0]
0x180002e25  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180002e2b  mov     al, 1
0x180002e2d  mov     rcx, [rbp+6D0h+var_30]
0x180002e34  xor     rcx, rsp; StackCookie
0x180002e37  call    __security_check_cookie
0x180002e3c  lea     r11, [rsp+7D0h+var_20]
0x180002e44  mov     rbx, [r11+38h]
0x180002e48  mov     rsi, [r11+40h]
0x180002e4c  mov     rsp, r11
0x180002e4f  pop     r15
0x180002e51  pop     r14
0x180002e53  pop     r12
0x180002e55  pop     rdi
0x180002e56  pop     rbp
0x180002e57  retn
0x180002e58  lea     r8, [rbp+6D0h+var_740]
0x180002e5c  mov     rcx, rsi
0x180002e5f  lea     rdx, [rbp+6D0h+var_6C0]
0x180002e63  call    cs:__imp_?AddDriveName@MOUNT_POINT_MAP@@QEAAEPEAVWSTRING@@0@Z; MOUNT_POINT_MAP::AddDriveName(WSTRING *,WSTRING *)
0x180002e69  jmp     loc_180002DB0
0x180002e6e  mov     ecx, eax; Status
0x180002e70  call    cs:__imp_RtlNtStatusToDosError
0x180002e76  mov     ecx, eax; dwErrCode
0x180002e78  call    cs:__imp_SetLastError
0x180002e7e  jmp     loc_180002DB8
```
