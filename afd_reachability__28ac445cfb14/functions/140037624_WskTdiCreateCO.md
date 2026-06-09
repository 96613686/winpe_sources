# WskTdiCreateCO

- ea: `0x140037624`
- end: `0x1400377fd`
- name: `WskTdiCreateCO`
- size: `473`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14003ffbc`
- `0x140063c64`

## callees

- `0x14002c770`
- `0x140037624`
- `0x140067b0c`
- `0x1400726a0`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x140037703`
- `ntoskrnl!IoCreateFile` at `0x140037703`
- `ntoskrnl!ZwClose` at `0x1400377cd`
- `ntoskrnl!ZwClose` at `0x1400377cd`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003776d`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14003776d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400377b5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400377b5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037741`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140037741`

## pseudocode

```c
__int64 __fastcall WskTdiCreateCO(struct _UNICODE_STRING *a1, void *a2, __int64 a3, __int64 a4)
{
  NTSTATUS Status; // edi
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
          Status = AfdIssueDeviceControl(v12, &Object, 8u, 0, 0, 1);
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
0x140037624  push    rbp
0x140037626  push    rbx
0x140037627  push    rsi
0x140037628  push    rdi
0x140037629  push    r12
0x14003762b  push    r14
0x14003762d  push    r15
0x14003762f  lea     rbp, [rsp-27h]
0x140037634  sub     rsp, 0F0h
0x14003763b  mov     rax, cs:__security_cookie
0x140037642  xor     rax, rsp
0x140037645  mov     [rbp+57h+var_40], rax
0x140037649  xor     r15d, r15d
0x14003764c  mov     [rsp+120h+Options], 100h; Options
0x140037654  mov     [rsp+120h+InternalParameters], r15; InternalParameters
0x140037659  xorps   xmm0, xmm0
0x14003765c  mov     [rsp+120h+CreateFileType], r15d; CreateFileType
0x140037661  mov     rbx, r9
0x140037664  mov     [rsp+120h+EaLength], 22h ; '"'; EaLength
0x14003766c  mov     r14, rdx
0x14003766f  mov     [r9], r15
0x140037672  lea     r12d, [r15+8]
0x140037676  mov     [r9+8], r15
0x14003767a  mov     rsi, rcx
0x14003767d  mov     [r9+10h], r15
0x140037681  mov     edx, 0C0100000h; DesiredAccess
0x140037686  movzx   eax, word ptr cs:aConnectioncont+10h; "t"
0x14003768d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140037691  mov     word ptr [rbp+57h+var_60+10h], ax
0x140037695  lea     rax, [rcx+20h]
0x140037699  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14003769d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400376a1  lea     rax, [rbp+57h+var_68]
0x1400376a5  movups  xmm0, xmmword ptr cs:aConnectioncont; "ConnectionContext"
0x1400376ac  mov     [rsp+120h+EaBuffer], rax; EaBuffer
0x1400376b1  mov     rcx, rbx; FileHandle
0x1400376b4  mov     [rsp+120h+CreateOptions], r15d; CreateOptions
0x1400376b9  mov     [rsp+120h+Disposition], 2; Disposition
0x1400376c1  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1400376c5  mov     [rsp+120h+ShareAccess], r15d; ShareAccess
0x1400376ca  mov     [rbp+57h+var_4E], r8
0x1400376ce  xorps   xmm0, xmm0
0x1400376d1  mov     [rsp+120h+FileAttributes], r15d; FileAttributes
0x1400376d6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400376da  mov     [rsp+120h+AllocationSize], r15; AllocationSize
0x1400376df  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400376e7  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400376ef  mov     [rbp+57h+var_68], r15d
0x1400376f3  mov     [rbp+57h+var_64], 81100h
0x1400376fa  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1400376fe  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140037703  call    cs:__imp_IoCreateFile
0x14003770a  nop     dword ptr [rax+rax+00h]
0x14003770f  mov     edi, eax
0x140037711  test    eax, eax
0x140037713  js      loc_1400377A8
0x140037719  mov     edi, dword ptr [rbp+57h+IoStatusBlock]
0x14003771c  test    edi, edi
0x14003771e  js      loc_1400377A8
0x140037724  mov     rcx, [rbx]; Handle
0x140037727  lea     rax, [rbp+57h+Object]
0x14003772b  mov     qword ptr [rsp+120h+FileAttributes], r15; HandleInformation
0x140037730  xor     r9d, r9d; AccessMode
0x140037733  xor     r8d, r8d; ObjectType
0x140037736  mov     [rsp+120h+AllocationSize], rax; Object
0x14003773b  xor     edx, edx; DesiredAccess
0x14003773d  mov     [rbp+57h+Object], r15
0x140037741  call    cs:__imp_ObReferenceObjectByHandle
0x140037748  nop     dword ptr [rax+rax+00h]
0x14003774d  mov     rdx, [rbp+57h+Object]
0x140037751  mov     edi, eax
0x140037753  mov     [rbx+8], rdx
0x140037757  test    eax, eax
0x140037759  js      short loc_1400377A8
0x14003775b  mov     rcx, rsi
0x14003775e  call    AfdTdiValidateTransportFileObject
0x140037763  mov     edi, eax
0x140037765  test    eax, eax
0x140037767  js      short loc_1400377A8
0x140037769  mov     rcx, [rbx+8]; FileObject
0x14003776d  call    cs:__imp_IoGetRelatedDeviceObject
0x140037774  nop     dword ptr [rax+rax+00h]
0x140037779  mov     rcx, [rbx+8]; FileObject
0x14003777d  lea     rdx, [rbp+57h+Object]; Src
0x140037781  xor     r9d, r9d; VirtualAddress
0x140037784  mov     byte ptr [rsp+120h+FileAttributes], 1; char
0x140037789  mov     r8d, r12d; Size
0x14003778c  mov     [rbx+10h], rax
0x140037790  mov     [rbp+57h+Object], r14
0x140037794  mov     dword ptr [rsp+120h+AllocationSize], r15d; Length
0x140037799  call    AfdIssueDeviceControl
0x14003779e  mov     edi, eax
0x1400377a0  test    eax, eax
0x1400377a2  js      short loc_1400377A8
0x1400377a4  xor     eax, eax
0x1400377a6  jmp     short loc_1400377DE
0x1400377a8  mov     rcx, [rbx+8]; Object
0x1400377ac  mov     [rbx+10h], r15
0x1400377b0  test    rcx, rcx
0x1400377b3  jz      short loc_1400377C5
0x1400377b5  call    cs:__imp_ObfDereferenceObject
0x1400377bc  nop     dword ptr [rax+rax+00h]
0x1400377c1  mov     [rbx+8], r15
0x1400377c5  mov     rcx, [rbx]; Handle
0x1400377c8  test    rcx, rcx
0x1400377cb  jz      short loc_1400377DC
0x1400377cd  call    cs:__imp_ZwClose
0x1400377d4  nop     dword ptr [rax+rax+00h]
0x1400377d9  mov     [rbx], r15
0x1400377dc  mov     eax, edi
0x1400377de  mov     rcx, [rbp+57h+var_40]
0x1400377e2  xor     rcx, rsp; StackCookie
0x1400377e5  call    __security_check_cookie
0x1400377ea  add     rsp, 0F0h
0x1400377f1  pop     r15
0x1400377f3  pop     r14
0x1400377f5  pop     r12
0x1400377f7  pop     rdi
0x1400377f8  pop     rsi
0x1400377f9  pop     rbx
0x1400377fa  pop     rbp
0x1400377fb  retn
```
