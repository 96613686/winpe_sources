# SIPolicyPmReadPolicy

- ea: `0x180022a30`
- end: `0x180022bb0`
- name: `SIPolicyPmReadPolicy`
- size: `384`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, _QWORD *, ULONG *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ad4c`
- `0x18001c714`
- `0x180021bd8`
- `0x180021e34`

## callees

- `0x180002a90`
- `0x180022a30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022b76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022b1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022b1a`
- `ntdll!ZwQueryInformationFile` at `0x180022afb`
- `ntdll!ZwQueryInformationFile` at `0x180022afb`
- `ntdll!ZwClose` at `0x180022b85`
- `ntdll!ZwClose` at `0x180022b85`
- `ntdll!ZwReadFile` at `0x180022b5f`
- `ntdll!ZwReadFile` at `0x180022b5f`
- `ntdll!ZwCreateFile` at `0x180022ad3`
- `ntdll!ZwCreateFile` at `0x180022ad3`

## pseudocode

```c
__int64 __fastcall SIPolicyPmReadPolicy(__int64 a1, struct _UNICODE_STRING *a2, _QWORD *a3, ULONG *a4)
{
  NTSTATUS v6; // ebx
  ULONG v7; // edi
  HLOCAL v8; // rsi
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-21h] BYREF
  __int128 FileInformation; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v14; // [rsp+B8h] [rbp+1Fh]

  ObjectAttributes.ObjectName = a2;
  v14 = 0;
  ObjectAttributes.RootDirectory = 0;
  FileHandle = 0;
  FileInformation = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x20u, 0, 0);
  if ( v6 >= 0 )
  {
    v6 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v6 >= 0 )
    {
      v7 = DWORD2(FileInformation);
      if ( DWORD2(FileInformation) )
      {
        v8 = LocalAlloc(0x40u, DWORD2(FileInformation));
        if ( v8 )
        {
          v6 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, v8, v7, 0, 0);
          if ( v6 < 0 )
          {
            LocalFree(v8);
          }
          else
          {
            *a4 = v7;
            *a3 = v8;
          }
        }
        else
        {
          v6 = -1073741670;
        }
      }
      else
      {
        v6 = -1073741275;
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022a30  mov     [rsp-8+arg_0], rbx
0x180022a35  push    rbp
0x180022a36  push    rsi
0x180022a37  push    rdi
0x180022a38  push    r14
0x180022a3a  push    r15
0x180022a3c  lea     rbp, [rsp-37h]
0x180022a41  sub     rsp, 0D0h
0x180022a48  mov     rax, cs:__security_cookie
0x180022a4f  xor     rax, rsp
0x180022a52  mov     [rbp+57h+var_30], rax
0x180022a56  xor     eax, eax
0x180022a58  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x180022a5c  mov     [rsp+0F0h+EaLength], eax; EaLength
0x180022a60  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180022a64  mov     [rsp+0F0h+EaBuffer], rax; EaBuffer
0x180022a69  xorps   xmm0, xmm0
0x180022a6c  mov     [rsp+0F0h+CreateOptions], 20h ; ' '; CreateOptions
0x180022a74  mov     r15, r9
0x180022a77  lea     esi, [rax+40h]
0x180022a7a  mov     [rbp+57h+var_38], rax
0x180022a7e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180022a82  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180022a86  lea     eax, [rsi-3Fh]
0x180022a89  mov     [rbp+57h+FileHandle], 0
0x180022a91  mov     [rsp+0F0h+CreateDisposition], eax; CreateDisposition
0x180022a95  mov     r14, r8
0x180022a98  mov     [rsp+0F0h+ShareAccess], eax; ShareAccess
0x180022a9c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180022aa0  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x180022aa8  mov     edx, 120089h; DesiredAccess
0x180022aad  mov     [rsp+0F0h+AllocationSize], 0; AllocationSize
0x180022ab6  movups  [rbp+57h+FileInformation], xmm0
0x180022aba  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180022ac2  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180022ac6  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180022ace  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180022ad3  call    cs:__imp_ZwCreateFile
0x180022ad9  mov     ebx, eax
0x180022adb  test    eax, eax
0x180022add  js      loc_180022B7C
0x180022ae3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180022ae7  lea     r9d, [rsi-28h]; Length
0x180022aeb  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180022aef  mov     dword ptr [rsp+0F0h+AllocationSize], 5; FileInformationClass
0x180022af7  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180022afb  call    cs:__imp_ZwQueryInformationFile
0x180022b01  mov     ebx, eax
0x180022b03  test    eax, eax
0x180022b05  js      short loc_180022B7C
0x180022b07  mov     edi, dword ptr [rbp+57h+FileInformation+8]
0x180022b0a  test    edi, edi
0x180022b0c  jnz     short loc_180022B15
0x180022b0e  mov     ebx, 0C0000225h
0x180022b13  jmp     short loc_180022B7C
0x180022b15  mov     rdx, rdi; uBytes
0x180022b18  mov     ecx, esi; uFlags
0x180022b1a  call    cs:__imp_LocalAlloc
0x180022b20  mov     rsi, rax
0x180022b23  test    rax, rax
0x180022b26  jnz     short loc_180022B2F
0x180022b28  mov     ebx, 0C000009Ah
0x180022b2d  jmp     short loc_180022B7C
0x180022b2f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180022b33  lea     rax, [rbp+57h+IoStatusBlock]
0x180022b37  mov     qword ptr [rsp+0F0h+CreateOptions], 0; Key
0x180022b40  xor     r9d, r9d; ApcContext
0x180022b43  mov     qword ptr [rsp+0F0h+CreateDisposition], 0; ByteOffset
0x180022b4c  xor     r8d, r8d; ApcRoutine
0x180022b4f  mov     [rsp+0F0h+ShareAccess], edi; Length
0x180022b53  xor     edx, edx; Event
0x180022b55  mov     qword ptr [rsp+0F0h+FileAttributes], rsi; Buffer
0x180022b5a  mov     [rsp+0F0h+AllocationSize], rax; IoStatusBlock
0x180022b5f  call    cs:__imp_ZwReadFile
0x180022b65  mov     ebx, eax
0x180022b67  test    eax, eax
0x180022b69  js      short loc_180022B73
0x180022b6b  mov     [r15], edi
0x180022b6e  mov     [r14], rsi
0x180022b71  jmp     short loc_180022B7C
0x180022b73  mov     rcx, rsi; hMem
0x180022b76  call    cs:__imp_LocalFree
0x180022b7c  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180022b80  test    rcx, rcx
0x180022b83  jz      short loc_180022B8B
0x180022b85  call    cs:__imp_ZwClose
0x180022b8b  mov     eax, ebx
0x180022b8d  mov     rcx, [rbp+57h+var_30]
0x180022b91  xor     rcx, rsp; StackCookie
0x180022b94  call    __security_check_cookie
0x180022b99  mov     rbx, [rsp+0F0h+arg_0]
0x180022ba1  add     rsp, 0D0h
0x180022ba8  pop     r15
0x180022baa  pop     r14
0x180022bac  pop     rdi
0x180022bad  pop     rsi
0x180022bae  pop     rbp
0x180022baf  retn
```
