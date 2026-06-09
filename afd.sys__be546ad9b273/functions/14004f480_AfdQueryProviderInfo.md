# AfdQueryProviderInfo

- ea: `0x14004f480`
- end: `0x14004f6cb`
- name: `AfdQueryProviderInfo`
- size: `587`
- prototype: `__int64 __fastcall(PVOID VirtualAddress, const UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x140037394`
- `0x14003ce90`

## callees

- `0x14002c770`
- `0x14002de4c`
- `0x140039898`
- `0x14004f000`
- `0x14004f480`
- `0x140067cac`
- `0x140072840`
- `0x140093304`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x14004f555`
- `ntoskrnl!IoCreateFile` at `0x14004f555`
- `ntoskrnl!ZwClose` at `0x14004f5f1`
- `ntoskrnl!ZwClose` at `0x14004f5f1`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f5e0`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f5e0`
- `ntoskrnl!IoFileObjectType` at `0x14004f56b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f593`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004f593`

## pseudocode

```c
__int64 __fastcall AfdQueryProviderInfo(PVOID VirtualAddress, const UNICODE_STRING *a2)
{
  struct _UNICODE_STRING *v2; // rsi
  char IsWellKnownProviderDeviceName; // r15
  int v6; // ebx
  struct _FILE_OBJECT *v7; // rdi
  __int64 v8; // r8
  __int64 v9; // r9
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  PVOID Object; // [rsp+78h] [rbp-88h] BYREF
  _QWORD Src[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD *v17; // [rsp+F0h] [rbp-10h]
  __int64 v18; // [rsp+F8h] [rbp-8h]
  PWSTR Buffer; // [rsp+100h] [rbp+0h]
  _DWORD v20[2]; // [rsp+108h] [rbp+8h] BYREF

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
    v6 = AfdTdiValidateTransportFileObject(a2, Object);
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
    v18 = 2;
    v17 = v20;
    Buffer = v2->Buffer;
    v20[0] = v2->Length;
    v20[1] = 0;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140087240, (unsigned __int8 *)&word_14007FE4A, v8, v9, 4u, &v16);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14004f480  mov     [rsp-8+arg_10], rbx
0x14004f485  push    rbp
0x14004f486  push    rsi
0x14004f487  push    rdi
0x14004f488  push    r12
0x14004f48a  push    r13
0x14004f48c  push    r14
0x14004f48e  push    r15
0x14004f490  lea     rbp, [rsp-20h]
0x14004f495  sub     rsp, 120h
0x14004f49c  mov     rax, cs:__security_cookie
0x14004f4a3  xor     rax, rsp
0x14004f4a6  mov     [rbp+50h+var_40], rax
0x14004f4aa  xorps   xmm0, xmm0
0x14004f4ad  lea     rsi, [rdx+20h]
0x14004f4b1  mov     r12, rcx
0x14004f4b4  xor     r13d, r13d
0x14004f4b7  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x14004f4bb  mov     rcx, rsi; String1
0x14004f4be  mov     [rsp+150h+FileHandle], r13
0x14004f4c3  xor     eax, eax
0x14004f4c5  mov     r14, rdx
0x14004f4c8  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x14004f4cc  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x14004f4d0  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x14004f4d4  call    AfdIsWellKnownProviderDeviceName
0x14004f4d9  mov     [rsp+150h+Options], 101h; Options
0x14004f4e1  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x14004f4e5  mov     [rsp+150h+InternalParameters], r13; InternalParameters
0x14004f4ea  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x14004f4ee  mov     [rsp+150h+CreateFileType], r13d; CreateFileType
0x14004f4f3  lea     rcx, [rsp+150h+FileHandle]; FileHandle
0x14004f4f8  mov     [rsp+150h+EaLength], r13d; EaLength
0x14004f4fd  mov     r15b, al
0x14004f500  mov     [rsp+150h+EaBuffer], r13; EaBuffer
0x14004f505  lea     eax, [r13+2]
0x14004f509  mov     [rsp+150h+CreateOptions], r13d; CreateOptions
0x14004f50e  xorps   xmm0, xmm0
0x14004f511  mov     [rsp+150h+Disposition], eax; Disposition
0x14004f515  mov     edi, 2000000h
0x14004f51a  mov     [rsp+150h+ShareAccess], 3; ShareAccess
0x14004f522  mov     edx, edi; DesiredAccess
0x14004f524  mov     [rsp+150h+FileAttributes], r13d; FileAttributes
0x14004f529  mov     [rsp+150h+AllocationSize], r13; AllocationSize
0x14004f52e  mov     [rbp+50h+Src], 2
0x14004f536  mov     [rbp+50h+var_C8], r13
0x14004f53a  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x14004f541  mov     [rbp+50h+ObjectAttributes.RootDirectory], r13
0x14004f545  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x14004f54c  mov     [rbp+50h+ObjectAttributes.ObjectName], rsi
0x14004f550  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004f555  call    cs:__imp_IoCreateFile
0x14004f55c  nop     dword ptr [rax+rax+00h]
0x14004f561  mov     ebx, eax
0x14004f563  test    eax, eax
0x14004f565  js      loc_14004F67B
0x14004f56b  mov     r8, cs:__imp_IoFileObjectType
0x14004f572  lea     rax, [rsp+150h+Object]
0x14004f577  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14004f57c  xor     r9d, r9d; AccessMode
0x14004f57f  mov     qword ptr [rsp+150h+FileAttributes], r13; HandleInformation
0x14004f584  mov     edx, edi; DesiredAccess
0x14004f586  mov     [rsp+150h+Object], r13
0x14004f58b  mov     r8, [r8]; ObjectType
0x14004f58e  mov     [rsp+150h+AllocationSize], rax; Object
0x14004f593  call    cs:__imp_ObReferenceObjectByHandle
0x14004f59a  nop     dword ptr [rax+rax+00h]
0x14004f59f  mov     ebx, eax
0x14004f5a1  test    eax, eax
0x14004f5a3  js      short loc_14004F5EC
0x14004f5a5  mov     rdi, [rsp+150h+Object]
0x14004f5aa  mov     rcx, r14
0x14004f5ad  mov     rdx, rdi
0x14004f5b0  call    AfdTdiValidateTransportFileObject
0x14004f5b5  mov     ebx, eax
0x14004f5b7  test    eax, eax
0x14004f5b9  js      short loc_14004F5DD
0x14004f5bb  mov     byte ptr [rsp+150h+FileAttributes], 0Ch; char
0x14004f5c0  lea     r8d, [r13+10h]; Size
0x14004f5c4  mov     r9, r12; VirtualAddress
0x14004f5c7  mov     dword ptr [rsp+150h+AllocationSize], 28h ; '('; Length
0x14004f5cf  lea     rdx, [rbp+50h+Src]; Src
0x14004f5d3  mov     rcx, rdi; FileObject
0x14004f5d6  call    AfdIssueDeviceControl
0x14004f5db  mov     ebx, eax
0x14004f5dd  mov     rcx, rdi; Object
0x14004f5e0  call    cs:__imp_ObfDereferenceObject
0x14004f5e7  nop     dword ptr [rax+rax+00h]
0x14004f5ec  mov     rcx, [rsp+150h+FileHandle]; Handle
0x14004f5f1  call    cs:__imp_ZwClose
0x14004f5f8  nop     dword ptr [rax+rax+00h]
0x14004f5fd  test    ebx, ebx
0x14004f5ff  js      short loc_14004F67B
0x14004f601  test    r15b, r15b
0x14004f604  jnz     loc_14004F6A1
0x14004f60a  mov     eax, cs:dword_140087240
0x14004f610  cmp     eax, 5
0x14004f613  jbe     loc_14004F6A1
0x14004f619  mov     rdx, 400000000000h
0x14004f623  lea     rcx, dword_140087240
0x14004f62a  call    _tlgKeywordOn
0x14004f62f  test    al, al
0x14004f631  jz      short loc_14004F6A1
0x14004f633  lea     rax, [rbp+50h+var_48]
0x14004f637  mov     [rbp+50h+var_58], 2
0x14004f63f  mov     [rbp+50h+var_60], rax
0x14004f643  lea     rdx, word_14007FE4A; int
0x14004f64a  mov     rax, [rsi+8]
0x14004f64e  lea     rcx, dword_140087240; int
0x14004f655  mov     [rbp+50h+var_50], rax
0x14004f659  movzx   eax, word ptr [rsi]
0x14004f65c  mov     [rbp+50h+var_48], eax
0x14004f65f  lea     rax, [rbp+50h+var_80]
0x14004f663  mov     qword ptr [rsp+150h+FileAttributes], rax; __int64
0x14004f668  mov     dword ptr [rsp+150h+AllocationSize], 4; ULONG
0x14004f670  mov     [rbp+50h+var_44], r13d
0x14004f674  call    _tlgWriteTransfer_EtwWriteTransfer
0x14004f679  jmp     short loc_14004F6A1
0x14004f67b  test    byte ptr cs:xmmword_1400875D0+0Ah, 40h
0x14004f682  jz      short loc_14004F6A1
0x14004f684  mov     edx, 1Ah
0x14004f689  mov     dword ptr [rsp+150h+AllocationSize], ebx
0x14004f68d  mov     ecx, 316h
0x14004f692  lea     r8, WPP_f5726d6c7e42399356e7224fda59383d_Traceguids
0x14004f699  mov     r9, rsi
0x14004f69c  call    WPP_SF_ZL
0x14004f6a1  mov     eax, ebx
0x14004f6a3  mov     rcx, [rbp+50h+var_40]
0x14004f6a7  xor     rcx, rsp; StackCookie
0x14004f6aa  call    __security_check_cookie
0x14004f6af  mov     rbx, [rsp+150h+arg_10]
0x14004f6b7  add     rsp, 120h
0x14004f6be  pop     r15
0x14004f6c0  pop     r14
0x14004f6c2  pop     r13
0x14004f6c4  pop     r12
0x14004f6c6  pop     rdi
0x14004f6c7  pop     rsi
0x14004f6c8  pop     rbp
0x14004f6c9  retn
```
