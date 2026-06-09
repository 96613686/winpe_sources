# Container::Manager::Agent::Core::_anonymous_namespace_::PurgeRdrCache

- ea: `0x180019624`
- end: `0x1800197c4`
- name: `Container::Manager::Agent::Core::_anonymous_namespace_::PurgeRdrCache`
- size: `416`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fb70`

## callees

- `0x180002140`
- `0x180009eb8`
- `0x18000a768`
- `0x180019624`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019707`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019707`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019798`
- `ntdll!RtlInitUnicodeString` at `0x180019652`
- `ntdll!RtlInitUnicodeString` at `0x180019652`
- `ntdll!NtCreateFile` at `0x1800196cf`
- `ntdll!NtCreateFile` at `0x1800196cf`
- `ntdll!NtFsControlFile` at `0x180019770`
- `ntdll!NtFsControlFile` at `0x180019770`

## string_xrefs

- `0x1800196e4`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::_anonymous_namespace_::PurgeRdrCache(PCWSTR SourceString)
{
  void **v1; // rax
  NTSTATUS v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  int AllocationSize; // [rsp+20h] [rbp-69h]
  HANDLE hObject; // [rsp+60h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-1h] BYREF
  _OWORD InputBuffer[2]; // [rsp+B8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  hObject = 0;
  v1 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  v2 = NtCreateFile(v1, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x4000u, 0, 0);
  if ( v2 < 0 )
  {
    v3 = 281;
LABEL_3:
    v4 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v3,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
           (const char *)(unsigned int)v2,
           AllocationSize);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v4;
  }
  memset(InputBuffer, 0, sizeof(InputBuffer));
  LOWORD(InputBuffer[0]) = 32;
  DWORD1(InputBuffer[0]) = 1;
  BYTE8(InputBuffer[0]) = 1;
  IoStatusBlock = 0;
  v2 = NtFsControlFile(hObject, 0, 0, 0, &IoStatusBlock, 0x1401F0u, InputBuffer, 0x20u, 0, 0);
  if ( v2 < 0 )
  {
    v3 = 302;
    goto LABEL_3;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180019624  mov     [rsp-8+arg_8], rbx
0x180019629  push    rbp
0x18001962a  lea     rbp, [rsp-57h]
0x18001962f  sub     rsp, 0E0h
0x180019636  mov     rax, cs:__security_cookie
0x18001963d  xor     rax, rsp
0x180019640  mov     [rbp+57h+var_8], rax
0x180019644  xorps   xmm0, xmm0
0x180019647  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001964b  mov     rdx, rcx; SourceString
0x18001964e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180019652  call    cs:__imp_RtlInitUnicodeString
0x180019659  nop     dword ptr [rax+rax+00h]
0x18001965e  xor     ebx, ebx
0x180019660  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180019668  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180019670  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x180019674  lea     rax, [rbp+57h+DestinationString]
0x180019678  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001967c  xorps   xmm0, xmm0
0x18001967f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180019684  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180019688  mov     [rbp+57h+hObject], rbx
0x18001968c  lea     rcx, [rbp+57h+hObject]
0x180019690  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180019695  mov     rcx, rax; FileHandle
0x180019698  mov     [rsp+0E0h+EaLength], ebx; EaLength
0x18001969c  mov     [rsp+0E0h+EaBuffer], rbx; EaBuffer
0x1800196a1  mov     [rsp+0E0h+CreateOptions], 4000h; CreateOptions
0x1800196a9  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x1800196b1  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1800196b9  mov     [rsp+0E0h+FileAttributes], ebx; FileAttributes
0x1800196bd  mov     [rsp+0E0h+AllocationSize], rbx; int
0x1800196c2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800196c6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800196ca  mov     edx, 120089h; DesiredAccess
0x1800196cf  call    cs:__imp_NtCreateFile
0x1800196d6  nop     dword ptr [rax+rax+00h]
0x1800196db  test    eax, eax
0x1800196dd  jns     short loc_18001971A
0x1800196df  mov     edx, 119h; void *
0x1800196e4  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800196eb  mov     r9d, eax; char *
0x1800196ee  mov     rcx, [rbp+5Fh]; this
0x1800196f2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800196f7  mov     ebx, eax
0x1800196f9  mov     rcx, [rbp+57h+hObject]; hObject
0x1800196fd  lea     rdx, [rcx-1]
0x180019701  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019705  ja      short loc_180019713
0x180019707  call    cs:__imp_CloseHandle
0x18001970e  nop     dword ptr [rax+rax+00h]
0x180019713  mov     eax, ebx
0x180019715  jmp     loc_1800197A6
0x18001971a  xorps   xmm0, xmm0
0x18001971d  movups  [rbp+57h+InputBuffer], xmm0
0x180019721  movups  [rbp+57h+var_18], xmm0
0x180019725  mov     eax, 20h ; ' '
0x18001972a  mov     word ptr [rbp+57h+InputBuffer], ax
0x18001972e  mov     dword ptr [rbp+57h+InputBuffer+4], 1
0x180019735  mov     byte ptr [rbp+57h+InputBuffer+8], 1
0x180019739  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001973d  mov     dword ptr [rsp+0E0h+EaBuffer], ebx; OutputBufferLength
0x180019741  mov     qword ptr [rsp+0E0h+CreateOptions], rbx; OutputBuffer
0x180019746  mov     [rsp+0E0h+CreateDisposition], eax; InputBufferLength
0x18001974a  lea     rax, [rbp+57h+InputBuffer]
0x18001974e  mov     qword ptr [rsp+0E0h+ShareAccess], rax; InputBuffer
0x180019753  mov     [rsp+0E0h+FileAttributes], 1401F0h; FsControlCode
0x18001975b  lea     rax, [rbp+57h+IoStatusBlock]
0x18001975f  mov     [rsp+0E0h+AllocationSize], rax; IoStatusBlock
0x180019764  xor     r9d, r9d; ApcContext
0x180019767  xor     r8d, r8d; ApcRoutine
0x18001976a  xor     edx, edx; Event
0x18001976c  mov     rcx, [rbp+57h+hObject]; FileHandle
0x180019770  call    cs:__imp_NtFsControlFile
0x180019777  nop     dword ptr [rax+rax+00h]
0x18001977c  test    eax, eax
0x18001977e  jns     short loc_18001978A
0x180019780  mov     edx, 12Eh
0x180019785  jmp     loc_1800196E4
0x18001978a  mov     rcx, [rbp+57h+hObject]; hObject
0x18001978e  lea     rax, [rcx-1]
0x180019792  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019796  ja      short loc_1800197A4
0x180019798  call    cs:__imp_CloseHandle
0x18001979f  nop     dword ptr [rax+rax+00h]
0x1800197a4  xor     eax, eax
0x1800197a6  mov     rcx, [rbp+57h+var_8]
0x1800197aa  xor     rcx, rsp; StackCookie
0x1800197ad  call    __security_check_cookie
0x1800197b2  mov     rbx, [rsp+0E0h+arg_8]
0x1800197ba  add     rsp, 0E0h
0x1800197c1  pop     rbp
0x1800197c2  retn
```
