# AfdQueryProviderInfo

- ea: `0x14004f3e0`
- end: `0x14004f62b`
- name: `AfdQueryProviderInfo`
- size: `587`
- prototype: `__int64 __fastcall(PVOID VirtualAddress, const UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x140037374`
- `0x14003ce70`

## callees

- `0x14002c770`
- `0x14002de4c`
- `0x140039878`
- `0x14004ef60`
- `0x14004f3e0`
- `0x140067b0c`
- `0x1400726a0`
- `0x140093304`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x14004f4b5`
- `ntoskrnl!IoCreateFile` at `0x14004f4b5`
- `ntoskrnl!ZwClose` at `0x14004f551`
- `ntoskrnl!ZwClose` at `0x14004f551`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f540`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f540`
- `ntoskrnl!IoFileObjectType` at `0x14004f4cb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f4f3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f4f3`

## pseudocode

```c
__int64 __fastcall AfdQueryProviderInfo(PVOID VirtualAddress, const UNICODE_STRING *a2)
{
  struct _UNICODE_STRING *v2; // rsi
  char IsWellKnownProviderDeviceName; // r15
  int v6; // ebx
  struct _FILE_OBJECT *v7; // rdi
  int v8; // r8d
  int v9; // r9d
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  PVOID Object; // [rsp+78h] [rbp-88h] BYREF
  _QWORD Src[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v16[7]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v17[2]; // [rsp+108h] [rbp+8h] BYREF

  v2 = (struct _UNICODE_STRING *)&a2[2];
  FileHandle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  *(&ObjectAttributes.Length + 1) = 0;
  IoStatusBlock = 0;
  IsWellKnownProviderDeviceName = AfdIsWellKnownProviderDeviceName(a2 + 2);
  Src[0] = 2;
  Src[1] = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = v2;
  v6 = IoCreateFile(
         &FileHandle,
         0x2000000u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0,
         3u,
         2u,
         0,
         0,
         0,
         CreateFileTypeNone,
         0,
         0x101u);
  if ( v6 < 0 )
    goto LABEL_11;
  Object = 0;
  v6 = ObReferenceObjectByHandle(FileHandle, 0x2000000u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  if ( v6 >= 0 )
  {
    v7 = (struct _FILE_OBJECT *)Object;
    v6 = AfdTdiValidateTransportFileObject(a2);
    if ( v6 >= 0 )
      v6 = AfdIssueDeviceControl(v7, Src, 0x10u, VirtualAddress, 0x28u, 0xCu);
    ObfDereferenceObject(v7);
  }
  ZwClose(FileHandle);
  if ( v6 < 0 )
  {
LABEL_11:
    if ( (BYTE10(xmmword_1400875D0) & 0x40) != 0 )
      WPP_SF_ZL(790, 26, (unsigned int)WPP_f5726d6c7e42399356e7224fda59383d_Traceguids, (_DWORD)v2, v6);
  }
  else if ( !IsWellKnownProviderDeviceName
         && (unsigned int)dword_140087240 > 5
         && (unsigned __int8)tlgKeywordOn(&dword_140087240, 0x400000000000LL) )
  {
    v16[5] = 2;
    v16[4] = (__int64)v17;
    v16[6] = (__int64)v2->Buffer;
    v17[0] = v2->Length;
    v17[1] = 0;
    tlgWriteTransfer_EtwWriteTransfer((int)&dword_140087240, (int)&word_14007FE4A, v8, v9, 4u, (__int64)v16);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14004f3e0  mov     [rsp-8+arg_10], rbx
0x14004f3e5  push    rbp
0x14004f3e6  push    rsi
0x14004f3e7  push    rdi
0x14004f3e8  push    r12
0x14004f3ea  push    r13
0x14004f3ec  push    r14
0x14004f3ee  push    r15
0x14004f3f0  lea     rbp, [rsp-20h]
0x14004f3f5  sub     rsp, 120h
0x14004f3fc  mov     rax, cs:__security_cookie
0x14004f403  xor     rax, rsp
0x14004f406  mov     [rbp+50h+var_40], rax
0x14004f40a  xorps   xmm0, xmm0
0x14004f40d  lea     rsi, [rdx+20h]
0x14004f411  mov     r12, rcx
0x14004f414  xor     r13d, r13d
0x14004f417  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x14004f41b  mov     rcx, rsi; String1
0x14004f41e  mov     [rsp+150h+FileHandle], r13
0x14004f423  xor     eax, eax
0x14004f425  mov     r14, rdx
0x14004f428  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x14004f42c  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x14004f430  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x14004f434  call    AfdIsWellKnownProviderDeviceName
0x14004f439  mov     [rsp+150h+Options], 101h; Options
0x14004f441  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x14004f445  mov     [rsp+150h+InternalParameters], r13; InternalParameters
0x14004f44a  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x14004f44e  mov     [rsp+150h+CreateFileType], r13d; CreateFileType
0x14004f453  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x14004f458  mov     [rsp+150h+EaLength], r13d; EaLength
0x14004f45d  mov     r15b, al
0x14004f460  mov     [rsp+150h+EaBuffer], r13; EaBuffer
0x14004f465  lea     eax, [r13+2]
0x14004f469  mov     [rsp+150h+CreateOptions], r13d; CreateOptions
0x14004f46e  xorps   xmm0, xmm0
0x14004f471  mov     [rsp+150h+Disposition], eax; Disposition
0x14004f475  mov     edi, 2000000h
0x14004f47a  mov     [rsp+150h+ShareAccess], 3; ShareAccess
0x14004f482  mov     edx, edi; DesiredAccess
0x14004f484  mov     [rsp+150h+FileAttributes], r13d; FileAttributes
0x14004f489  mov     [rsp+150h+AllocationSize], r13; AllocationSize
0x14004f48e  mov     [rbp+50h+Src], 2
0x14004f496  mov     [rbp+50h+var_C8], r13
0x14004f49a  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x14004f4a1  mov     [rbp+50h+ObjectAttributes.RootDirectory], r13
0x14004f4a5  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x14004f4ac  mov     [rbp+50h+ObjectAttributes.ObjectName], rsi
0x14004f4b0  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004f4b5  call    cs:__imp_IoCreateFile
0x14004f4bc  nop     dword ptr [rax+rax+00h]
0x14004f4c1  mov     ebx, eax
0x14004f4c3  test    eax, eax
0x14004f4c5  js      loc_14004F5DB
0x14004f4cb  mov     r8, cs:__imp_IoFileObjectType
0x14004f4d2  lea     rax, [rsp+150h+Object]
0x14004f4d7  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14004f4dc  xor     r9d, r9d; AccessMode
0x14004f4df  mov     qword ptr [rsp+150h+FileAttributes], r13; HandleInformation
0x14004f4e4  mov     edx, edi; DesiredAccess
0x14004f4e6  mov     [rsp+150h+Object], r13
0x14004f4eb  mov     r8, [r8]; ObjectType
0x14004f4ee  mov     [rsp+150h+AllocationSize], rax; Object
0x14004f4f3  call    cs:__imp_ObReferenceObjectByHandle
0x14004f4fa  nop     dword ptr [rax+rax+00h]
0x14004f4ff  mov     ebx, eax
0x14004f501  test    eax, eax
0x14004f503  js      short loc_14004F54C
0x14004f505  mov     rdi, [rsp+150h+Object]
0x14004f50a  mov     rcx, r14
0x14004f50d  mov     rdx, rdi
0x14004f510  call    AfdTdiValidateTransportFileObject
0x14004f515  mov     ebx, eax
0x14004f517  test    eax, eax
0x14004f519  js      short loc_14004F53D
0x14004f51b  mov     byte ptr [rsp+150h+FileAttributes], 0Ch; char
0x14004f520  lea     r8d, [r13+10h]; Size
0x14004f524  mov     r9, r12; VirtualAddress
0x14004f527  mov     dword ptr [rsp+150h+AllocationSize], 28h ; '('; Length
0x14004f52f  lea     rdx, [rbp+50h+Src]; Src
0x14004f533  mov     rcx, rdi; FileObject
0x14004f536  call    AfdIssueDeviceControl
0x14004f53b  mov     ebx, eax
0x14004f53d  mov     rcx, rdi; Object
0x14004f540  call    cs:__imp_ObfDereferenceObject
0x14004f547  nop     dword ptr [rax+rax+00h]
0x14004f54c  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14004f551  call    cs:__imp_ZwClose
0x14004f558  nop     dword ptr [rax+rax+00h]
0x14004f55d  test    ebx, ebx
0x14004f55f  js      short loc_14004F5DB
0x14004f561  test    r15b, r15b
0x14004f564  jnz     loc_14004F601
0x14004f56a  mov     eax, cs:dword_140087240
0x14004f570  cmp     eax, 5
0x14004f573  jbe     loc_14004F601
0x14004f579  mov     rdx, 400000000000h
0x14004f583  lea     rcx, dword_140087240
0x14004f58a  call    _tlgKeywordOn
0x14004f58f  test    al, al
0x14004f591  jz      short loc_14004F601
0x14004f593  lea     rax, [rbp+50h+var_48]
0x14004f597  mov     [rbp+50h+var_58], 2
0x14004f59f  mov     [rbp+50h+var_60], rax
0x14004f5a3  lea     rdx, word_14007FE4A; int
0x14004f5aa  mov     rax, [rsi+8]
0x14004f5ae  lea     rcx, dword_140087240; int
0x14004f5b5  mov     [rbp+50h+var_50], rax
0x14004f5b9  movzx   eax, word ptr [rsi]
0x14004f5bc  mov     [rbp+50h+var_48], eax
0x14004f5bf  lea     rax, [rbp+50h+var_80]
0x14004f5c3  mov     qword ptr [rsp+150h+FileAttributes], rax; __int64
0x14004f5c8  mov     dword ptr [rsp+150h+AllocationSize], 4; ULONG
0x14004f5d0  mov     [rbp+50h+var_44], r13d
0x14004f5d4  call    _tlgWriteTransfer_EtwWriteTransfer
0x14004f5d9  jmp     short loc_14004F601
0x14004f5db  test    byte ptr cs:xmmword_1400875D0+0Ah, 40h
0x14004f5e2  jz      short loc_14004F601
0x14004f5e4  mov     edx, 1Ah
0x14004f5e9  mov     dword ptr [rsp+150h+AllocationSize], ebx
0x14004f5ed  mov     ecx, 316h
0x14004f5f2  lea     r8, WPP_f5726d6c7e42399356e7224fda59383d_Traceguids
0x14004f5f9  mov     r9, rsi
0x14004f5fc  call    WPP_SF_ZL
0x14004f601  mov     eax, ebx
0x14004f603  mov     rcx, [rbp+50h+var_40]
0x14004f607  xor     rcx, rsp; StackCookie
0x14004f60a  call    __security_check_cookie
0x14004f60f  mov     rbx, [rsp+150h+arg_10]
0x14004f617  add     rsp, 120h
0x14004f61e  pop     r15
0x14004f620  pop     r14
0x14004f622  pop     r13
0x14004f624  pop     r12
0x14004f626  pop     rdi
0x14004f627  pop     rsi
0x14004f628  pop     rbp
0x14004f629  retn
```
