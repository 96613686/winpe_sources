# PlatformFileOperationBroker::UnsetACLForContentProcess(ushort const *)

- ea: `0x180029e50`
- end: `0x180029f50`
- name: `?UnsetACLForContentProcess@PlatformFileOperationBroker@@UEAAJPEBG@Z`
- size: `256`
- prototype: `__int64 __fastcall(PlatformFileOperationBroker *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000e428`
- `0x180029b30`
- `0x180029c10`
- `0x180029e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029f18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f20`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180029e9c`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180029e9c`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180029ee5`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180029ee5`

## pseudocode

```c
__int64 __fastcall PlatformFileOperationBroker::UnsetACLForContentProcess(
        PlatformFileOperationBroker *this,
        const unsigned __int16 *a2)
{
  int PIC; // ebx
  void *File2; // rdi
  signed int LastError; // eax
  PACL pAcl; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(pAcl) = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, (unsigned int *)&pAcl);
  if ( PIC >= 0 )
  {
    File2 = (void *)CreateFile2(a2, 917504, 0, 3, 0);
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
      pAcl = 0;
      if ( GetSecurityInfo(File2, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, 0) || !pAcl )
      {
        PIC = 1;
      }
      else if ( (unsigned __int8)anonymous_namespace_::SetACSIDReadOnlyInAcl(pAcl) )
      {
        PIC = anonymous_namespace_::SetDacl(File2, pAcl);
      }
      CloseHandle(File2);
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180029e50  mov     rax, rsp
0x180029e53  mov     [rax+8], rbx
0x180029e57  mov     [rax+10h], rbp
0x180029e5b  push    rdi
0x180029e5c  sub     rsp, 40h
0x180029e60  mov     rdi, rdx
0x180029e63  mov     dword ptr [rax+18h], 0
0x180029e6a  mov     ebp, 1
0x180029e6f  lea     rdx, [rax+18h]; unsigned int *
0x180029e73  mov     ecx, ebp; unsigned int
0x180029e75  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180029e7a  mov     ebx, eax
0x180029e7c  test    eax, eax
0x180029e7e  js      loc_180029F3E
0x180029e84  lea     r9d, [rbp+2]
0x180029e88  mov     [rsp+48h+ppsidGroup], 0
0x180029e91  xor     r8d, r8d
0x180029e94  mov     edx, 0E0000h
0x180029e99  mov     rcx, rdi
0x180029e9c  call    cs:__imp_CreateFile2
0x180029ea2  mov     rdi, rax
0x180029ea5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029ea9  jz      short loc_180029F20
0x180029eab  mov     [rsp+48h+ppSecurityDescriptor], 0; ppSecurityDescriptor
0x180029eb4  lea     rax, [rsp+48h+pAcl]
0x180029eb9  mov     [rsp+48h+ppSacl], 0; ppSacl
0x180029ec2  lea     r8d, [rbp+3]; SecurityInfo
0x180029ec6  mov     [rsp+48h+ppDacl], rax; ppDacl
0x180029ecb  xor     r9d, r9d; ppsidOwner
0x180029ece  mov     edx, ebp; ObjectType
0x180029ed0  mov     [rsp+48h+ppsidGroup], 0; ppsidGroup
0x180029ed9  mov     rcx, rdi; handle
0x180029edc  mov     [rsp+48h+pAcl], 0
0x180029ee5  call    cs:__imp_GetSecurityInfo
0x180029eeb  test    eax, eax
0x180029eed  jnz     short loc_180029F13
0x180029eef  mov     rcx, [rsp+48h+pAcl]; pAcl
0x180029ef4  test    rcx, rcx
0x180029ef7  jz      short loc_180029F13
0x180029ef9  call    _anonymous_namespace___SetACSIDReadOnlyInAcl
0x180029efe  test    al, al
0x180029f00  jz      short loc_180029F15
0x180029f02  mov     rdx, [rsp+48h+pAcl]; Src
0x180029f07  mov     rcx, rdi; Handle
0x180029f0a  call    _anonymous_namespace___SetDacl
0x180029f0f  mov     ebx, eax
0x180029f11  jmp     short loc_180029F15
0x180029f13  mov     ebx, ebp
0x180029f15  mov     rcx, rdi; hObject
0x180029f18  call    cs:__imp_CloseHandle
0x180029f1e  jmp     short loc_180029F3E
0x180029f20  call    cs:__imp_GetLastError
0x180029f26  mov     ebx, eax
0x180029f28  test    eax, eax
0x180029f2a  jle     short loc_180029F35
0x180029f2c  movzx   ebx, ax
0x180029f2f  or      ebx, 80070000h
0x180029f35  cmp     ebx, 80070005h
0x180029f3b  cmovz   ebx, ebp
0x180029f3e  mov     rbp, [rsp+48h+arg_8]
0x180029f43  mov     eax, ebx
0x180029f45  mov     rbx, [rsp+48h+arg_0]
0x180029f4a  add     rsp, 40h
0x180029f4e  pop     rdi
0x180029f4f  retn
```
