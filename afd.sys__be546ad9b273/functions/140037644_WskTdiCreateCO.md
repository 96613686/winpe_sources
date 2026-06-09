# WskTdiCreateCO

- ea: `0x140037644`
- end: `0x14003781d`
- name: `WskTdiCreateCO`
- size: `473`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003ffdc`
- `0x140063e04`

## callees

- `0x14002c770`
- `0x140037644`
- `0x140067cac`
- `0x140072840`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x140037723`
- `ntoskrnl!IoCreateFile` at `0x140037723`
- `ntoskrnl!ZwClose` at `0x1400377ed`
- `ntoskrnl!ZwClose` at `0x1400377ed`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003778d`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003778d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400377d5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400377d5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037761`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037761`

## pseudocode

```c
__int64 __fastcall WskTdiCreateCO(struct _UNICODE_STRING *a1, void *a2, __int64 a3, __int64 a4)
{
  int Status; // edi
  void *v8; // rcx
  NTSTATUS v9; // eax
  PVOID v10; // rdx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  struct _FILE_OBJECT *v12; // rcx
  void *v14; // rcx
  PVOID Object; // [rsp+70h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-51h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-41h] BYREF
  _DWORD EaBuffer[2]; // [rsp+B8h] [rbp-11h] BYREF
  char v19[18]; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+D2h] [rbp+9h]

  *(_QWORD *)a4 = 0;
  *(_QWORD *)(a4 + 8) = 0;
  *(_QWORD *)(a4 + 16) = 0;
  IoStatusBlock = 0;
  ObjectAttributes.ObjectName = a1 + 2;
  strcpy(v19, "ConnectionContext");
  v20 = a3;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  EaBuffer[0] = 0;
  EaBuffer[1] = 528640;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Status = IoCreateFile(
             (PHANDLE)a4,
             0xC0100000,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0,
             0,
             2u,
             0,
             EaBuffer,
             0x22u,
             CreateFileTypeNone,
             0,
             0x100u);
  if ( Status >= 0 )
  {
    Status = IoStatusBlock.Status;
    if ( IoStatusBlock.Status >= 0 )
    {
      v8 = *(void **)a4;
      Object = 0;
      v9 = ObReferenceObjectByHandle(v8, 0, 0, 0, &Object, 0);
      v10 = Object;
      Status = v9;
      *(_QWORD *)(a4 + 8) = Object;
      if ( v9 >= 0 )
      {
        Status = AfdTdiValidateTransportFileObject(a1, v10);
        if ( Status >= 0 )
        {
          RelatedDeviceObject = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(a4 + 8));
          v12 = *(struct _FILE_OBJECT **)(a4 + 8);
          *(_QWORD *)(a4 + 16) = RelatedDeviceObject;
          Object = a2;
          Status = AfdIssueDeviceControl(v12, &Object, 8u, 0, 0, 1u);
          if ( Status >= 0 )
            return 0;
        }
      }
    }
  }
  v14 = *(void **)(a4 + 8);
  *(_QWORD *)(a4 + 16) = 0;
  if ( v14 )
  {
    ObfDereferenceObject(v14);
    *(_QWORD *)(a4 + 8) = 0;
  }
  if ( *(_QWORD *)a4 )
  {
    ZwClose(*(HANDLE *)a4);
    *(_QWORD *)a4 = 0;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140037644  push    rbp
0x140037646  push    rbx
0x140037647  push    rsi
0x140037648  push    rdi
0x140037649  push    r12
0x14003764b  push    r14
0x14003764d  push    r15
0x14003764f  lea     rbp, [rsp-27h]
0x140037654  sub     rsp, 0F0h
0x14003765b  mov     rax, cs:__security_cookie
0x140037662  xor     rax, rsp
0x140037665  mov     [rbp+57h+var_40], rax
0x140037669  xor     r15d, r15d
0x14003766c  mov     [rsp+120h+Options], 100h; Options
0x140037674  mov     [rsp+120h+InternalParameters], r15; InternalParameters
0x140037679  xorps   xmm0, xmm0
0x14003767c  mov     [rsp+120h+CreateFileType], r15d; CreateFileType
0x140037681  mov     rbx, r9
0x140037684  mov     [rsp+120h+EaLength], 22h ; '"'; EaLength
0x14003768c  mov     r14, rdx
0x14003768f  mov     [r9], r15
0x140037692  lea     r12d, [r15+8]
0x140037696  mov     [r9+8], r15
0x14003769a  mov     rsi, rcx
0x14003769d  mov     [r9+10h], r15
0x1400376a1  mov     edx, 0C0100000h; DesiredAccess
0x1400376a6  movzx   eax, word ptr cs:aConnectioncont+10h; "t"
0x1400376ad  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400376b1  mov     word ptr [rbp+57h+var_60+10h], ax
0x1400376b5  lea     rax, [rcx+20h]
0x1400376b9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400376bd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400376c1  lea     rax, [rbp+57h+var_68]
0x1400376c5  movups  xmm0, xmmword ptr cs:aConnectioncont; "ConnectionContext"
0x1400376cc  mov     [rsp+120h+EaBuffer], rax; EaBuffer
0x1400376d1  mov     rcx, rbx; FileHandle
0x1400376d4  mov     [rsp+120h+CreateOptions], r15d; CreateOptions
0x1400376d9  mov     [rsp+120h+Disposition], 2; Disposition
0x1400376e1  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1400376e5  mov     [rsp+120h+ShareAccess], r15d; ShareAccess
0x1400376ea  mov     [rbp+57h+var_4E], r8
0x1400376ee  xorps   xmm0, xmm0
0x1400376f1  mov     [rsp+120h+FileAttributes], r15d; FileAttributes
0x1400376f6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400376fa  mov     [rsp+120h+AllocationSize], r15; AllocationSize
0x1400376ff  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140037707  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14003770f  mov     [rbp+57h+var_68], r15d
0x140037713  mov     [rbp+57h+var_64], 81100h
0x14003771a  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x14003771e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140037723  call    cs:__imp_IoCreateFile
0x14003772a  nop     dword ptr [rax+rax+00h]
0x14003772f  mov     edi, eax
0x140037731  test    eax, eax
0x140037733  js      loc_1400377C8
0x140037739  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x14003773c  test    edi, edi
0x14003773e  js      loc_1400377C8
0x140037744  mov     rcx, [rbx]; Handle
0x140037747  lea     rax, [rbp+57h+Object]
0x14003774b  mov     qword ptr [rsp+120h+FileAttributes], r15; HandleInformation
0x140037750  xor     r9d, r9d; AccessMode
0x140037753  xor     r8d, r8d; ObjectType
0x140037756  mov     [rsp+120h+AllocationSize], rax; Object
0x14003775b  xor     edx, edx; DesiredAccess
0x14003775d  mov     [rbp+57h+Object], r15
0x140037761  call    cs:__imp_ObReferenceObjectByHandle
0x140037768  nop     dword ptr [rax+rax+00h]
0x14003776d  mov     rdx, [rbp+57h+Object]
0x140037771  mov     edi, eax
0x140037773  mov     [rbx+8], rdx
0x140037777  test    eax, eax
0x140037779  js      short loc_1400377C8
0x14003777b  mov     rcx, rsi
0x14003777e  call    AfdTdiValidateTransportFileObject
0x140037783  mov     edi, eax
0x140037785  test    eax, eax
0x140037787  js      short loc_1400377C8
0x140037789  mov     rcx, [rbx+8]; FileObject
0x14003778d  call    cs:__imp_IoGetRelatedDeviceObject
0x140037794  nop     dword ptr [rax+rax+00h]
0x140037799  mov     rcx, [rbx+8]; FileObject
0x14003779d  lea     rdx, [rbp+57h+Object]; Src
0x1400377a1  xor     r9d, r9d; VirtualAddress
0x1400377a4  mov     byte ptr [rsp+120h+FileAttributes], 1; char
0x1400377a9  mov     r8d, r12d; Size
0x1400377ac  mov     [rbx+10h], rax
0x1400377b0  mov     [rbp+57h+Object], r14
0x1400377b4  mov     dword ptr [rsp+120h+AllocationSize], r15d; Length
0x1400377b9  call    AfdIssueDeviceControl
0x1400377be  mov     edi, eax
0x1400377c0  test    eax, eax
0x1400377c2  js      short loc_1400377C8
0x1400377c4  xor     eax, eax
0x1400377c6  jmp     short loc_1400377FE
0x1400377c8  mov     rcx, [rbx+8]; Object
0x1400377cc  mov     [rbx+10h], r15
0x1400377d0  test    rcx, rcx
0x1400377d3  jz      short loc_1400377E5
0x1400377d5  call    cs:__imp_ObfDereferenceObject
0x1400377dc  nop     dword ptr [rax+rax+00h]
0x1400377e1  mov     [rbx+8], r15
0x1400377e5  mov     rcx, [rbx]; Handle
0x1400377e8  test    rcx, rcx
0x1400377eb  jz      short loc_1400377FC
0x1400377ed  call    cs:__imp_ZwClose
0x1400377f4  nop     dword ptr [rax+rax+00h]
0x1400377f9  mov     [rbx], r15
0x1400377fc  mov     eax, edi
0x1400377fe  mov     rcx, [rbp+57h+var_40]
0x140037802  xor     rcx, rsp; StackCookie
0x140037805  call    __security_check_cookie
0x14003780a  add     rsp, 0F0h
0x140037811  pop     r15
0x140037813  pop     r14
0x140037815  pop     r12
0x140037817  pop     rdi
0x140037818  pop     rsi
0x140037819  pop     rbx
0x14003781a  pop     rbp
0x14003781b  retn
```
