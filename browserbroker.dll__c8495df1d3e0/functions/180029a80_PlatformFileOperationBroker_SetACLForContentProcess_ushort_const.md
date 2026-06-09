# PlatformFileOperationBroker::SetACLForContentProcess(ushort const *)

- ea: `0x180029a80`
- end: `0x180029b27`
- name: `?SetACLForContentProcess@PlatformFileOperationBroker@@UEAAJPEBG@Z`
- size: `167`
- prototype: `__int64 __fastcall(PlatformFileOperationBroker *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000e428`
- `0x180029a80`
- `0x180029ce8`
- `0x18002af4c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029aef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029af7`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180029ad0`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180029ad0`

## pseudocode

```c
__int64 __fastcall PlatformFileOperationBroker::SetACLForContentProcess(
        PlatformFileOperationBroker *this,
        const unsigned __int16 *a2)
{
  int PIC; // ebx
  void *File2; // rax
  void *v5; // rdi
  signed int LastError; // eax
  unsigned int v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v8);
  if ( PIC >= 0 )
  {
    SetFolderFullControl(a2);
    File2 = (void *)CreateFile2(a2, 917504, 0, 3, 0);
    v5 = File2;
    if ( File2 == (void *)-1LL )
    {
      LastError = GetLastError();
      PIC = LastError;
      if ( LastError > 0 )
        PIC = (unsigned __int16)LastError | 0x80070000;
      if ( PIC == -2147024891 )
        return 1;
    }
    else
    {
      PIC = 0;
      anonymous_namespace_::SetFileIntegrityLevel(File2);
      CloseHandle(v5);
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180029a80  mov     rax, rsp
0x180029a83  mov     [rax+8], rbx
0x180029a87  mov     [rax+10h], rsi
0x180029a8b  push    rdi
0x180029a8c  sub     rsp, 30h
0x180029a90  mov     rdi, rdx
0x180029a93  mov     dword ptr [rax+18h], 0
0x180029a9a  mov     esi, 1
0x180029a9f  lea     rdx, [rax+18h]; unsigned int *
0x180029aa3  mov     ecx, esi; unsigned int
0x180029aa5  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180029aaa  mov     ebx, eax
0x180029aac  test    eax, eax
0x180029aae  js      short loc_180029B15
0x180029ab0  mov     rcx, rdi; unsigned __int16 *
0x180029ab3  call    ?SetFolderFullControl@@YAJPEBG@Z; SetFolderFullControl(ushort const *)
0x180029ab8  lea     r9d, [rsi+2]
0x180029abc  mov     [rsp+38h+var_18], 0
0x180029ac5  xor     r8d, r8d
0x180029ac8  mov     edx, 0E0000h
0x180029acd  mov     rcx, rdi
0x180029ad0  call    cs:__imp_CreateFile2
0x180029ad6  mov     rdi, rax
0x180029ad9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029add  jz      short loc_180029AF7
0x180029adf  mov     dl, sil
0x180029ae2  mov     rcx, rax; Handle
0x180029ae5  xor     ebx, ebx
0x180029ae7  call    _anonymous_namespace___SetFileIntegrityLevel
0x180029aec  mov     rcx, rdi; hObject
0x180029aef  call    cs:__imp_CloseHandle
0x180029af5  jmp     short loc_180029B15
0x180029af7  call    cs:__imp_GetLastError
0x180029afd  mov     ebx, eax
0x180029aff  test    eax, eax
0x180029b01  jle     short loc_180029B0C
0x180029b03  movzx   ebx, ax
0x180029b06  or      ebx, 80070000h
0x180029b0c  cmp     ebx, 80070005h
0x180029b12  cmovz   ebx, esi
0x180029b15  mov     rsi, [rsp+38h+arg_8]
0x180029b1a  mov     eax, ebx
0x180029b1c  mov     rbx, [rsp+38h+arg_0]
0x180029b21  add     rsp, 30h
0x180029b25  pop     rdi
0x180029b26  retn
```
