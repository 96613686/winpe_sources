# BfsFileOpenAsUserCallback

- ea: `0x1400069a0`
- end: `0x140006c7d`
- name: `BfsFileOpenAsUserCallback`
- size: `733`
- prototype: `__int64 __fastcall(PFLT_FILTER Filter, PFLT_INSTANCE Instance, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140001008`
- `0x1400069a0`
- `0x14000fdc8`
- `0x140010070`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ZwSetInformationFile` at `0x140006bbf`
- `ntoskrnl!ZwSetInformationFile` at `0x140006bbf`
- `ntoskrnl!ObfDereferenceObject` at `0x140006c3b`
- `ntoskrnl!ObfDereferenceObject` at `0x140006c3b`
- `FLTMGR!FltCreateFileEx` at `0x140006b1c`
- `FLTMGR!FltCreateFileEx` at `0x140006b1c`
- `FLTMGR!FltQueryInformationFile` at `0x140006b71`
- `FLTMGR!FltQueryInformationFile` at `0x140006b71`
- `FLTMGR!FltClose` at `0x140006bd5`
- `FLTMGR!FltClose` at `0x140006c50`
- `FLTMGR!FltClose` at `0x140006bd5`
- `FLTMGR!FltClose` at `0x140006c50`

## pseudocode

```c
__int64 __fastcall BfsFileOpenAsUserCallback(PFLT_FILTER Filter, PFLT_INSTANCE Instance, __int64 a3, __int64 *a4)
{
  __int64 v6; // rcx
  int v9; // eax
  int v10; // r8d
  int v11; // r9d
  NTSTATUS v12; // ebx
  __int64 v13; // rdx
  struct _UNICODE_STRING *v14; // rax
  unsigned int v15; // ecx
  int v16; // r8d
  ULONG CreateDisposition; // ecx
  ULONG CreateOptions; // r8d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int *v22; // rax
  ACCESS_MASK DesiredAccess; // [rsp+20h] [rbp-E0h]
  ACCESS_MASK DesiredAccessa; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+80h] [rbp-80h] BYREF
  NTSTATUS v27; // [rsp+84h] [rbp-7Ch] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  ULONG LengthReturned; // [rsp+90h] [rbp-70h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-50h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK v35; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD FileInformation[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v37; // [rsp+128h] [rbp+28h]
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+130h] [rbp+30h] BYREF
  int *v39; // [rsp+150h] [rbp+50h]
  __int64 v40; // [rsp+158h] [rbp+58h]

  FileHandle = 0;
  v37 = 0;
  v6 = *a4;
  memset(FileInformation, 0, sizeof(FileInformation));
  FileObject = 0;
  v32 = 0;
  v31 = 0;
  LengthReturned = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = BfsImpersonateUser(v6, &v31);
  v12 = v9;
  if ( v9 >= 0 )
  {
    v13 = *(_QWORD *)(a3 + 16);
    v14 = (struct _UNICODE_STRING *)(a4[1] + 8);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = v14;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 1536;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v15 = *(_DWORD *)(v13 + 32);
    v16 = v15 & 0x20041;
    CreateDisposition = HIBYTE(v15);
    CreateOptions = v16 | 0x20;
    switch ( CreateDisposition )
    {
      case 0u:
        goto LABEL_7;
      case 4u:
        CreateDisposition = 1;
        break;
      case 5u:
LABEL_7:
        CreateDisposition = 3;
        break;
    }
    v12 = FltCreateFileEx(
            Filter,
            Instance,
            &FileHandle,
            &FileObject,
            *(_DWORD *)(*(_QWORD *)(v13 + 24) + 16LL) & 0xFFE3FFFF | 0x100000,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            *(unsigned __int16 *)(v13 + 40),
            *(unsigned __int16 *)(v13 + 42),
            CreateDisposition,
            CreateOptions,
            0,
            0,
            0);
    if ( v12 < 0
      || (v12 = FltQueryInformationFile(
                  Instance,
                  FileObject,
                  FileInformation,
                  0x28u,
                  FileBasicInformation,
                  &LengthReturned),
          v12 < 0) )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v26 = v12;
        v22 = &v26;
LABEL_19:
        v39 = v22;
        v40 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v20, v21, DesiredAccessa, &v38);
      }
    }
    else
    {
      *((_DWORD *)a4 + 4) = ((v37 & 0x10) != 0) + 1;
      if ( IoStatusBlock.Information != 2
        || (v26 = 1,
            v35 = 0,
            v12 = ZwSetInformationFile(FileHandle, &v35, &v26, 4u, (FILE_INFORMATION_CLASS)64),
            v12 >= 0) )
      {
        v12 = FltClose(FileHandle);
        if ( v12 >= 0 )
        {
          FileHandle = 0;
          v12 = BfsRevertTokenImpersonation(&v31);
          if ( v12 >= 0 )
            goto LABEL_21;
        }
      }
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v22 = &v27;
        v27 = v12;
        goto LABEL_19;
      }
    }
    BfsRevertTokenImpersonation(&v31);
    goto LABEL_21;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v26 = v9;
    v40 = 4;
    v39 = &v26;
    tlgWriteTransfer_EtwWriteTransfer(dword_140019000, (int)&byte_140016D91, v10, v11, DesiredAccess, &v38);
  }
LABEL_21:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400069a0  push    rbp
0x1400069a2  push    rbx
0x1400069a3  push    rsi
0x1400069a4  push    rdi
0x1400069a5  push    r12
0x1400069a7  push    r14
0x1400069a9  push    r15
0x1400069ab  lea     rbp, [rsp-70h]
0x1400069b0  sub     rsp, 170h
0x1400069b7  mov     rax, cs:__security_cookie
0x1400069be  xor     rax, rsp
0x1400069c1  mov     [rbp+0A0h+var_40], rax
0x1400069c5  xorps   xmm0, xmm0
0x1400069c8  xorps   xmm1, xmm1
0x1400069cb  xor     r12d, r12d
0x1400069ce  xor     eax, eax
0x1400069d0  mov     r14, rdx
0x1400069d3  mov     [rbp+0A0h+FileHandle], r12
0x1400069d7  mov     r15, rcx
0x1400069da  mov     [rbp+0A0h+var_78], rax
0x1400069de  mov     rcx, [r9]
0x1400069e1  lea     rdx, [rbp+0A0h+var_100]
0x1400069e5  movups  [rbp+0A0h+FileInformation], xmm0
0x1400069e9  mov     [rbp+0A0h+FileObject], r12
0x1400069ed  mov     rsi, r9
0x1400069f0  movups  [rbp+0A0h+var_88], xmm0
0x1400069f4  mov     [rbp+0A0h+var_F0], rax
0x1400069f8  mov     rdi, r8
0x1400069fb  movups  [rbp+0A0h+var_100], xmm0
0x1400069ff  mov     [rbp+0A0h+LengthReturned], r12d
0x140006a03  movups  xmmword ptr [rbp+0A0h+var_E8], xmm0
0x140006a07  movups  xmmword ptr [rbp+0A0h+var_D8.Length], xmm1
0x140006a0b  movups  xmmword ptr [rbp+0A0h+var_D8.ObjectName], xmm1
0x140006a0f  movups  xmmword ptr [rbp+0A0h+var_D8.SecurityDescriptor], xmm1
0x140006a13  call    BfsImpersonateUser
0x140006a18  mov     ebx, eax
0x140006a1a  test    eax, eax
0x140006a1c  jns     short loc_140006A5A
0x140006a1e  mov     ecx, cs:dword_140019000; int
0x140006a24  cmp     ecx, 3
0x140006a27  jbe     loc_140006C32
0x140006a2d  mov     [rbp+0A0h+var_120], eax
0x140006a30  lea     rdx, byte_140016D91; int
0x140006a37  lea     rax, [rbp+0A0h+var_120]
0x140006a3b  mov     [rbp+0A0h+var_48], 4
0x140006a43  mov     [rbp+0A0h+var_50], rax
0x140006a47  lea     rax, [rbp+0A0h+var_70]
0x140006a4b  mov     [rsp+1A0h+ObjectAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x140006a50  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006a55  jmp     loc_140006C32
0x140006a5a  mov     rdx, [rdi+10h]
0x140006a5e  xorps   xmm0, xmm0
0x140006a61  mov     rax, [rsi+8]
0x140006a65  mov     edi, 4
0x140006a6a  add     rax, 8
0x140006a6e  mov     [rbp+0A0h+var_D8.Length], 30h ; '0'
0x140006a75  mov     [rbp+0A0h+var_D8.ObjectName], rax
0x140006a79  mov     [rbp+0A0h+var_D8.RootDirectory], r12
0x140006a7d  mov     [rbp+0A0h+var_D8.Attributes], 600h
0x140006a84  movdqu  xmmword ptr [rbp+0A0h+var_D8.SecurityDescriptor], xmm0
0x140006a89  mov     rax, [rdx+18h]
0x140006a8d  mov     r8d, [rdx+20h]
0x140006a91  mov     ecx, r8d
0x140006a94  and     r8d, 20041h
0x140006a9b  shr     ecx, 18h
0x140006a9e  or      r8d, 20h
0x140006aa2  mov     r9d, [rax+10h]
0x140006aa6  mov     eax, ecx
0x140006aa8  and     r9d, 0FFF3FFFFh
0x140006aaf  bts     r9d, 14h
0x140006ab4  test    ecx, ecx
0x140006ab6  jz      short loc_140006AC5
0x140006ab8  sub     eax, edi
0x140006aba  jz      loc_140006B49
0x140006ac0  cmp     eax, 1
0x140006ac3  jnz     short loc_140006ACA
0x140006ac5  mov     ecx, 3
0x140006aca  movzx   eax, word ptr [rdx+2Ah]
0x140006ace  movzx   edx, word ptr [rdx+28h]
0x140006ad2  mov     [rsp+1A0h+Flags], r12d; Flags
0x140006ad7  mov     [rsp+1A0h+EaLength], r12d; EaLength
0x140006adc  mov     [rsp+1A0h+EaBuffer], r12; EaBuffer
0x140006ae1  mov     [rsp+1A0h+CreateOptions], r8d; CreateOptions
0x140006ae6  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x140006aea  mov     [rsp+1A0h+CreateDisposition], ecx; CreateDisposition
0x140006aee  mov     rcx, r15; Filter
0x140006af1  mov     [rsp+1A0h+ShareAccess], eax; ShareAccess
0x140006af5  lea     rax, [rbp+0A0h+var_E8]
0x140006af9  mov     [rsp+1A0h+FileAttributes], edx; FileAttributes
0x140006afd  mov     rdx, r14; Instance
0x140006b00  mov     [rsp+1A0h+AllocationSize], r12; AllocationSize
0x140006b05  mov     [rsp+1A0h+IoStatusBlock], rax; IoStatusBlock
0x140006b0a  lea     rax, [rbp+0A0h+var_D8]
0x140006b0e  mov     [rsp+1A0h+ObjectAttributes], rax; ObjectAttributes
0x140006b13  mov     [rsp+1A0h+DesiredAccess], r9d; DesiredAccess
0x140006b18  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x140006b1c  call    cs:__imp_FltCreateFileEx
0x140006b23  nop     dword ptr [rax+rax+00h]
0x140006b28  mov     ebx, eax
0x140006b2a  test    eax, eax
0x140006b2c  jns     short loc_140006B53
0x140006b2e  mov     eax, cs:dword_140019000
0x140006b34  cmp     eax, 3
0x140006b37  jbe     loc_140006C29
0x140006b3d  mov     [rbp+0A0h+var_120], ebx
0x140006b40  lea     rax, [rbp+0A0h+var_120]
0x140006b44  jmp     loc_140006C0C
0x140006b49  mov     ecx, 1
0x140006b4e  jmp     loc_140006ACA
0x140006b53  mov     rdx, [rbp+0A0h+FileObject]; FileObject
0x140006b57  lea     rax, [rbp+0A0h+LengthReturned]
0x140006b5b  mov     [rsp+1A0h+ObjectAttributes], rax; LengthReturned
0x140006b60  lea     r8, [rbp+0A0h+FileInformation]; FileInformation
0x140006b64  mov     r9d, 28h ; '('; Length
0x140006b6a  mov     [rsp+1A0h+DesiredAccess], edi; FileInformationClass
0x140006b6e  mov     rcx, r14; Instance
0x140006b71  call    cs:__imp_FltQueryInformationFile
0x140006b78  nop     dword ptr [rax+rax+00h]
0x140006b7d  mov     ebx, eax
0x140006b7f  test    eax, eax
0x140006b81  js      short loc_140006B2E
0x140006b83  mov     eax, dword ptr [rbp+0A0h+var_78]
0x140006b86  and     al, 10h
0x140006b88  neg     al
0x140006b8a  sbb     ecx, ecx
0x140006b8c  neg     ecx
0x140006b8e  inc     ecx
0x140006b90  mov     [rsi+10h], ecx
0x140006b93  cmp     [rbp+0A0h+var_E8.Information], 2
0x140006b98  jnz     short loc_140006BD1
0x140006b9a  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x140006b9e  lea     r8, [rbp+0A0h+var_120]; FileInformation
0x140006ba2  xorps   xmm0, xmm0
0x140006ba5  mov     [rbp+0A0h+var_120], 1
0x140006bac  mov     r9d, edi; Length
0x140006baf  mov     [rsp+1A0h+DesiredAccess], 40h ; '@'; int
0x140006bb7  lea     rdx, [rbp+0A0h+var_A8]; IoStatusBlock
0x140006bbb  movups  xmmword ptr [rbp+0A0h+var_A8], xmm0
0x140006bbf  call    cs:__imp_ZwSetInformationFile
0x140006bc6  nop     dword ptr [rax+rax+00h]
0x140006bcb  mov     ebx, eax
0x140006bcd  test    eax, eax
0x140006bcf  js      short loc_140006BFA
0x140006bd1  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x140006bd5  call    cs:__imp_FltClose
0x140006bdc  nop     dword ptr [rax+rax+00h]
0x140006be1  mov     ebx, eax
0x140006be3  test    eax, eax
0x140006be5  js      short loc_140006BFA
0x140006be7  lea     rcx, [rbp+0A0h+var_100]
0x140006beb  mov     [rbp+0A0h+FileHandle], r12
0x140006bef  call    BfsRevertTokenImpersonation
0x140006bf4  mov     ebx, eax
0x140006bf6  test    eax, eax
0x140006bf8  jns     short loc_140006C32
0x140006bfa  mov     eax, cs:dword_140019000
0x140006c00  cmp     eax, 3
0x140006c03  jbe     short loc_140006C29
0x140006c05  lea     rax, [rbp+0A0h+var_11C]
0x140006c09  mov     [rbp+0A0h+var_11C], ebx
0x140006c0c  mov     [rbp+0A0h+var_50], rax
0x140006c10  lea     rdx, byte_140016D91; int
0x140006c17  lea     rax, [rbp+0A0h+var_70]
0x140006c1b  mov     [rbp+0A0h+var_48], rdi
0x140006c1f  mov     [rsp+1A0h+ObjectAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x140006c24  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006c29  lea     rcx, [rbp+0A0h+var_100]
0x140006c2d  call    BfsRevertTokenImpersonation
0x140006c32  mov     rcx, [rbp+0A0h+FileObject]; Object
0x140006c36  test    rcx, rcx
0x140006c39  jz      short loc_140006C47
0x140006c3b  call    cs:__imp_ObfDereferenceObject
0x140006c42  nop     dword ptr [rax+rax+00h]
0x140006c47  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x140006c4b  test    rcx, rcx
0x140006c4e  jz      short loc_140006C5C
0x140006c50  call    cs:__imp_FltClose
0x140006c57  nop     dword ptr [rax+rax+00h]
0x140006c5c  mov     eax, ebx
0x140006c5e  mov     rcx, [rbp+0A0h+var_40]
0x140006c62  xor     rcx, rsp; StackCookie
0x140006c65  call    __security_check_cookie
0x140006c6a  add     rsp, 170h
0x140006c71  pop     r15
0x140006c73  pop     r14
0x140006c75  pop     r12
0x140006c77  pop     rdi
0x140006c78  pop     rsi
0x140006c79  pop     rbx
0x140006c7a  pop     rbp
0x140006c7b  retn
```
