# GetCngHandle

- ea: `0x18004d650`
- end: `0x18004d736`
- name: `GetCngHandle`
- size: `230`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004d5a0`
- `0x1800582ec`
- `0x1800638c8`
- `0x180063944`

## callees

- `0x18004d650`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004d698`
- `ntdll!RtlInitUnicodeString` at `0x18004d698`
- `ntdll!NtOpenFile` at `0x18004d6e7`
- `ntdll!NtOpenFile` at `0x18004d6e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d728`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d728`

## pseudocode

```c
HANDLE GetCngHandle()
{
  HANDLE v0; // rbx
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+10h] BYREF

  v0 = g_hCNGDriver;
  FileHandle = g_hCNGDriver;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !g_hCNGDriver )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\CNG");
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u) >= 0
      && (v0 = (HANDLE)_InterlockedCompareExchange64(
                         (volatile signed __int64 *)&g_hCNGDriver,
                         (signed __int64)FileHandle,
                         0)) != 0 )
    {
      CloseHandle(FileHandle);
    }
    else
    {
      return FileHandle;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18004d650  mov     [rsp-8+arg_8], rbx
0x18004d655  push    rbp
0x18004d656  mov     rbp, rsp
0x18004d659  sub     rsp, 80h
0x18004d660  mov     rbx, cs:g_hCNGDriver
0x18004d667  xorps   xmm0, xmm0
0x18004d66a  xor     eax, eax
0x18004d66c  mov     [rbp+FileHandle], rbx
0x18004d670  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004d674  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18004d678  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004d67c  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004d680  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18004d684  test    rbx, rbx
0x18004d687  jnz     loc_18004D70F
0x18004d68d  lea     rdx, SourceString; "\\Device\\CNG"
0x18004d694  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004d698  call    cs:__imp_RtlInitUnicodeString
0x18004d69f  nop     dword ptr [rax+rax+00h]
0x18004d6a4  lea     rax, [rbp+DestinationString]
0x18004d6a8  mov     [rsp+80h+OpenOptions], 20h ; ' '; OpenOptions
0x18004d6b0  xorps   xmm0, xmm0
0x18004d6b3  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004d6b7  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18004d6bb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004d6c2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004d6c6  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18004d6ca  mov     edx, 100001h; DesiredAccess
0x18004d6cf  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004d6d6  lea     rcx, [rbp+FileHandle]; FileHandle
0x18004d6da  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x18004d6e2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004d6e7  call    cs:__imp_NtOpenFile
0x18004d6ee  nop     dword ptr [rax+rax+00h]
0x18004d6f3  test    eax, eax
0x18004d6f5  js      short loc_18004D70B
0x18004d6f7  mov     rcx, [rbp+FileHandle]
0x18004d6fb  xor     eax, eax
0x18004d6fd  lock cmpxchg cs:g_hCNGDriver, rcx
0x18004d706  mov     rbx, rax
0x18004d709  jnz     short loc_18004D724
0x18004d70b  mov     rbx, [rbp+FileHandle]
0x18004d70f  mov     rax, rbx
0x18004d712  mov     rbx, [rsp+80h+arg_8]
0x18004d71a  add     rsp, 80h
0x18004d721  pop     rbp
0x18004d722  retn
0x18004d724  mov     rcx, [rbp+FileHandle]; hObject
0x18004d728  call    cs:__imp_CloseHandle
0x18004d72f  nop     dword ptr [rax+rax+00h]
0x18004d734  jmp     short loc_18004D70F
```
