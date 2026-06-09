# BfsOpenPolicyDirectory

- ea: `0x140008d3c`
- end: `0x140008e7d`
- name: `BfsOpenPolicyDirectory`
- size: `321`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140007e5c`
- `0x140008598`
- `0x140008e84`
- `0x140009114`
- `0x14000a4bc`
- `0x14000cd20`

## callees

- `0x140001008`
- `0x140008d3c`
- `0x140013730`
- `0x14001e008`

## import_xrefs

- `FLTMGR!FltCreateFileEx2` at `0x140008e15`
- `FLTMGR!FltCreateFileEx2` at `0x140008e15`

## pseudocode

```c
__int64 __fastcall BfsOpenPolicyDirectory(__int64 a1, __int64 a2, __int64 a3, __int64 a4, void **a5)
{
  char v5; // r9
  struct _UNICODE_STRING *v6; // r8
  PFLT_INSTANCE v7; // rdx
  PFLT_FILTER v8; // rcx
  NTSTATUS v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  ACCESS_MASK DesiredAccess; // [rsp+20h] [rbp-E0h]
  NTSTATUS v15; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+D0h] [rbp-30h] BYREF
  NTSTATUS *v20; // [rsp+F0h] [rbp-10h]
  __int64 v21; // [rsp+F8h] [rbp-8h]

  FileHandle = 0;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a5 = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = (HANDLE)BfsGetRootDirectory();
  ObjectAttributes.SecurityDescriptor = gBfsPolicyStorageDirectoryDescriptor;
  ObjectAttributes.ObjectName = v6;
  ObjectAttributes.SecurityQualityOfService = 0;
  v9 = FltCreateFileEx2(
         v8,
         v7,
         &FileHandle,
         0,
         0x100047u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x10u,
         3u,
         v5 != 0 ? 1 : 3,
         0x21u,
         0,
         0,
         0x100u,
         0);
  v12 = v9;
  if ( v9 >= 0 )
  {
    *a5 = FileHandle;
  }
  else if ( (unsigned int)dword_140019000 > 3 )
  {
    v15 = v9;
    v21 = 4;
    v20 = &v15;
    tlgWriteTransfer_EtwWriteTransfer(
      (unsigned int)dword_140019000,
      (unsigned __int8 *)&byte_140016D91,
      v10,
      v11,
      DesiredAccess,
      &v19);
  }
  return v12;
}

```

## disassembly

```asm
0x140008d3c  push    rbp
0x140008d3e  push    rbx
0x140008d3f  push    rdi
0x140008d40  lea     rbp, [rsp-10h]
0x140008d45  sub     rsp, 110h
0x140008d4c  mov     rax, cs:__security_cookie
0x140008d53  xor     rax, rsp
0x140008d56  mov     [rbp+20h+var_20], rax
0x140008d5a  mov     rdi, [rbp+20h+arg_20]
0x140008d5e  xor     eax, eax
0x140008d60  xorps   xmm0, xmm0
0x140008d63  mov     [rbp+20h+FileHandle], 0
0x140008d6b  movups  xmmword ptr [rbp+20h+var_60], xmm0
0x140008d6f  mov     qword ptr [rbp+20h+var_90.Length], 30h ; '0'
0x140008d77  mov     [rdi], rax
0x140008d7a  mov     qword ptr [rbp+20h+var_90.Attributes], 240h
0x140008d82  call    BfsGetRootDirectory
0x140008d87  mov     [rsp+120h+DriverContext], 0; DriverContext
0x140008d90  neg     r9b
0x140008d93  mov     [rsp+120h+Flags], 100h; Flags
0x140008d9b  mov     [rsp+120h+EaLength], 0; EaLength
0x140008da3  mov     [rsp+120h+EaBuffer], 0; EaBuffer
0x140008dac  mov     [rbp+20h+var_90.RootDirectory], rax
0x140008db0  lea     rax, gBfsPolicyStorageDirectoryDescriptor
0x140008db7  mov     [rsp+120h+CreateOptions], 21h ; '!'; CreateOptions
0x140008dbf  mov     [rbp+20h+var_90.SecurityDescriptor], rax
0x140008dc3  sbb     eax, eax
0x140008dc5  and     eax, 0FFFFFFFEh
0x140008dc8  mov     [rbp+20h+var_90.ObjectName], r8
0x140008dcc  add     eax, 3
0x140008dcf  mov     [rbp+20h+var_90.SecurityQualityOfService], 0
0x140008dd7  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x140008ddb  lea     r8, [rbp+20h+FileHandle]; FileHandle
0x140008ddf  mov     [rsp+120h+ShareAccess], 3; ShareAccess
0x140008de7  lea     rax, [rbp+20h+var_60]
0x140008deb  mov     [rsp+120h+FileAttributes], 10h; FileAttributes
0x140008df3  xor     r9d, r9d; FileObject
0x140008df6  mov     [rsp+120h+AllocationSize], 0; AllocationSize
0x140008dff  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x140008e04  lea     rax, [rbp+20h+var_90]
0x140008e08  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x140008e0d  mov     [rsp+120h+DesiredAccess], 100047h; int
0x140008e15  call    cs:__imp_FltCreateFileEx2
0x140008e1c  nop     dword ptr [rax+rax+00h]
0x140008e21  mov     ebx, eax
0x140008e23  test    eax, eax
0x140008e25  jns     short loc_140008E5C
0x140008e27  mov     ecx, cs:dword_140019000; int
0x140008e2d  cmp     ecx, 3
0x140008e30  jbe     short loc_140008E63
0x140008e32  mov     [rbp+20h+var_A0], eax
0x140008e35  lea     rdx, byte_140016D91; int
0x140008e3c  lea     rax, [rbp+20h+var_A0]
0x140008e40  mov     [rbp+20h+var_28], 4
0x140008e48  mov     [rbp+20h+var_30], rax
0x140008e4c  lea     rax, [rbp+20h+var_50]
0x140008e50  mov     [rsp+120h+ObjectAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x140008e55  call    _tlgWriteTransfer_EtwWriteTransfer
0x140008e5a  jmp     short loc_140008E63
0x140008e5c  mov     rax, [rbp+20h+FileHandle]
0x140008e60  mov     [rdi], rax
0x140008e63  mov     eax, ebx
0x140008e65  mov     rcx, [rbp+20h+var_20]
0x140008e69  xor     rcx, rsp; StackCookie
0x140008e6c  call    __security_check_cookie
0x140008e71  add     rsp, 110h
0x140008e78  pop     rdi
0x140008e79  pop     rbx
0x140008e7a  pop     rbp
0x140008e7b  retn
```
