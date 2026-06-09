# BfsFileOpenAsUserCallback

- ea: `0x140006810`
- end: `0x140006aed`
- name: `BfsFileOpenAsUserCallback`
- size: `733`
- prototype: `__int64 __fastcall(PFLT_FILTER Filter, PFLT_INSTANCE Instance)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140001008`
- `0x140006810`
- `0x14000fc24`
- `0x14000fecc`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ZwSetInformationFile` at `0x140006a2f`
- `ntoskrnl!ZwSetInformationFile` at `0x140006a2f`
- `ntoskrnl!ObfDereferenceObject` at `0x140006aab`
- `ntoskrnl!ObfDereferenceObject` at `0x140006aab`
- `FLTMGR!FltCreateFileEx` at `0x14000698c`
- `FLTMGR!FltCreateFileEx` at `0x14000698c`
- `FLTMGR!FltQueryInformationFile` at `0x1400069e1`
- `FLTMGR!FltQueryInformationFile` at `0x1400069e1`
- `FLTMGR!FltClose` at `0x140006a45`
- `FLTMGR!FltClose` at `0x140006ac0`
- `FLTMGR!FltClose` at `0x140006a45`
- `FLTMGR!FltClose` at `0x140006ac0`

## pseudocode

```c
__int64 __fastcall BfsFileOpenAsUserCallback(PFLT_FILTER Filter, PFLT_INSTANCE Instance, __int64 a3, __int64 a4)
{
  void *v6; // rcx
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  NTSTATUS v12; // ebx
  __int64 v13; // rdx
  struct _UNICODE_STRING *v14; // rax
  unsigned int v15; // ecx
  int v16; // r8d
  ULONG CreateDisposition; // ecx
  ULONG CreateOptions; // r8d
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
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
  v6 = *(void **)a4;
  memset(FileInformation, 0, sizeof(FileInformation));
  FileObject = 0;
  v32 = 0;
  v31 = 0;
  LengthReturned = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v9 = BfsImpersonateUser(v6, (__int64)&v31);
  v12 = v9;
  if ( v9 >= 0 )
  {
    v13 = *(_QWORD *)(a3 + 16);
    v14 = (struct _UNICODE_STRING *)(*(_QWORD *)(a4 + 8) + 8LL);
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
        tlgWriteTransfer_EtwWriteTransfer(v19, (unsigned __int8 *)&byte_140016D91, v20, v21, DesiredAccessa, &v38);
      }
    }
    else
    {
      *(_DWORD *)(a4 + 16) = ((v37 & 0x10) != 0) + 1;
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
    tlgWriteTransfer_EtwWriteTransfer(
      (unsigned int)dword_140019000,
      (unsigned __int8 *)&byte_140016D91,
      v10,
      v11,
      DesiredAccess,
      &v38);
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
0x140006810  push    rbp
0x140006812  push    rbx
0x140006813  push    rsi
0x140006814  push    rdi
0x140006815  push    r12
0x140006817  push    r14
0x140006819  push    r15
0x14000681b  lea     rbp, [rsp-70h]
0x140006820  sub     rsp, 170h
0x140006827  mov     rax, cs:__security_cookie
0x14000682e  xor     rax, rsp
0x140006831  mov     [rbp+0A0h+var_40], rax
0x140006835  xorps   xmm0, xmm0
0x140006838  xorps   xmm1, xmm1
0x14000683b  xor     r12d, r12d
0x14000683e  xor     eax, eax
0x140006840  mov     r14, rdx
0x140006843  mov     [rbp+0A0h+FileHandle], r12
0x140006847  mov     r15, rcx
0x14000684a  mov     [rbp+0A0h+var_78], rax
0x14000684e  mov     rcx, [r9]
0x140006851  lea     rdx, [rbp+0A0h+var_100]
0x140006855  movups  [rbp+0A0h+FileInformation], xmm0
0x140006859  mov     [rbp+0A0h+FileObject], r12
0x14000685d  mov     rsi, r9
0x140006860  movups  [rbp+0A0h+var_88], xmm0
0x140006864  mov     [rbp+0A0h+var_F0], rax
0x140006868  mov     rdi, r8
0x14000686b  movups  [rbp+0A0h+var_100], xmm0
0x14000686f  mov     [rbp+0A0h+LengthReturned], r12d
0x140006873  movups  xmmword ptr [rbp+0A0h+var_E8], xmm0
0x140006877  movups  xmmword ptr [rbp+0A0h+var_D8.Length], xmm1
0x14000687b  movups  xmmword ptr [rbp+0A0h+var_D8.ObjectName], xmm1
0x14000687f  movups  xmmword ptr [rbp+0A0h+var_D8.SecurityDescriptor], xmm1
0x140006883  call    BfsImpersonateUser
0x140006888  mov     ebx, eax
0x14000688a  test    eax, eax
0x14000688c  jns     short loc_1400068CA
0x14000688e  mov     ecx, cs:dword_140019000; int
0x140006894  cmp     ecx, 3
0x140006897  jbe     loc_140006AA2
0x14000689d  mov     [rbp+0A0h+var_120], eax
0x1400068a0  lea     rdx, byte_140016D91; int
0x1400068a7  lea     rax, [rbp+0A0h+var_120]
0x1400068ab  mov     [rbp+0A0h+var_48], 4
0x1400068b3  mov     [rbp+0A0h+var_50], rax
0x1400068b7  lea     rax, [rbp+0A0h+var_70]
0x1400068bb  mov     [rsp+1A0h+ObjectAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x1400068c0  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400068c5  jmp     loc_140006AA2
0x1400068ca  mov     rdx, [rdi+10h]
0x1400068ce  xorps   xmm0, xmm0
0x1400068d1  mov     rax, [rsi+8]
0x1400068d5  mov     edi, 4
0x1400068da  add     rax, 8
0x1400068de  mov     [rbp+0A0h+var_D8.Length], 30h ; '0'
0x1400068e5  mov     [rbp+0A0h+var_D8.ObjectName], rax
0x1400068e9  mov     [rbp+0A0h+var_D8.RootDirectory], r12
0x1400068ed  mov     [rbp+0A0h+var_D8.Attributes], 600h
0x1400068f4  movdqu  xmmword ptr [rbp+0A0h+var_D8.SecurityDescriptor], xmm0
0x1400068f9  mov     rax, [rdx+18h]
0x1400068fd  mov     r8d, [rdx+20h]
0x140006901  mov     ecx, r8d
0x140006904  and     r8d, 20041h
0x14000690b  shr     ecx, 18h
0x14000690e  or      r8d, 20h
0x140006912  mov     r9d, [rax+10h]
0x140006916  mov     eax, ecx
0x140006918  and     r9d, 0FFF3FFFFh
0x14000691f  bts     r9d, 14h
0x140006924  test    ecx, ecx
0x140006926  jz      short loc_140006935
0x140006928  sub     eax, edi
0x14000692a  jz      loc_1400069B9
0x140006930  cmp     eax, 1
0x140006933  jnz     short loc_14000693A
0x140006935  mov     ecx, 3
0x14000693a  movzx   eax, word ptr [rdx+2Ah]
0x14000693e  movzx   edx, word ptr [rdx+28h]
0x140006942  mov     [rsp+1A0h+Flags], r12d; Flags
0x140006947  mov     [rsp+1A0h+EaLength], r12d; EaLength
0x14000694c  mov     [rsp+1A0h+EaBuffer], r12; EaBuffer
0x140006951  mov     [rsp+1A0h+CreateOptions], r8d; CreateOptions
0x140006956  lea     r8, [rbp+0A0h+FileHandle]; FileHandle
0x14000695a  mov     [rsp+1A0h+CreateDisposition], ecx; CreateDisposition
0x14000695e  mov     rcx, r15; Filter
0x140006961  mov     [rsp+1A0h+ShareAccess], eax; ShareAccess
0x140006965  lea     rax, [rbp+0A0h+var_E8]
0x140006969  mov     [rsp+1A0h+FileAttributes], edx; FileAttributes
0x14000696d  mov     rdx, r14; Instance
0x140006970  mov     [rsp+1A0h+AllocationSize], r12; AllocationSize
0x140006975  mov     [rsp+1A0h+IoStatusBlock], rax; IoStatusBlock
0x14000697a  lea     rax, [rbp+0A0h+var_D8]
0x14000697e  mov     [rsp+1A0h+ObjectAttributes], rax; ObjectAttributes
0x140006983  mov     [rsp+1A0h+DesiredAccess], r9d; DesiredAccess
0x140006988  lea     r9, [rbp+0A0h+FileObject]; FileObject
0x14000698c  call    cs:__imp_FltCreateFileEx
0x140006993  nop     dword ptr [rax+rax+00h]
0x140006998  mov     ebx, eax
0x14000699a  test    eax, eax
0x14000699c  jns     short loc_1400069C3
0x14000699e  mov     eax, cs:dword_140019000
0x1400069a4  cmp     eax, 3
0x1400069a7  jbe     loc_140006A99
0x1400069ad  mov     [rbp+0A0h+var_120], ebx
0x1400069b0  lea     rax, [rbp+0A0h+var_120]
0x1400069b4  jmp     loc_140006A7C
0x1400069b9  mov     ecx, 1
0x1400069be  jmp     loc_14000693A
0x1400069c3  mov     rdx, [rbp+0A0h+FileObject]; FileObject
0x1400069c7  lea     rax, [rbp+0A0h+LengthReturned]
0x1400069cb  mov     [rsp+1A0h+ObjectAttributes], rax; LengthReturned
0x1400069d0  lea     r8, [rbp+0A0h+FileInformation]; FileInformation
0x1400069d4  mov     r9d, 28h ; '('; Length
0x1400069da  mov     [rsp+1A0h+DesiredAccess], edi; FileInformationClass
0x1400069de  mov     rcx, r14; Instance
0x1400069e1  call    cs:__imp_FltQueryInformationFile
0x1400069e8  nop     dword ptr [rax+rax+00h]
0x1400069ed  mov     ebx, eax
0x1400069ef  test    eax, eax
0x1400069f1  js      short loc_14000699E
0x1400069f3  mov     eax, dword ptr [rbp+0A0h+var_78]
0x1400069f6  and     al, 10h
0x1400069f8  neg     al
0x1400069fa  sbb     ecx, ecx
0x1400069fc  neg     ecx
0x1400069fe  inc     ecx
0x140006a00  mov     [rsi+10h], ecx
0x140006a03  cmp     [rbp+0A0h+var_E8.Information], 2
0x140006a08  jnz     short loc_140006A41
0x140006a0a  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x140006a0e  lea     r8, [rbp+0A0h+var_120]; FileInformation
0x140006a12  xorps   xmm0, xmm0
0x140006a15  mov     [rbp+0A0h+var_120], 1
0x140006a1c  mov     r9d, edi; Length
0x140006a1f  mov     [rsp+1A0h+DesiredAccess], 40h ; '@'; int
0x140006a27  lea     rdx, [rbp+0A0h+var_A8]; IoStatusBlock
0x140006a2b  movups  xmmword ptr [rbp+0A0h+var_A8], xmm0
0x140006a2f  call    cs:__imp_ZwSetInformationFile
0x140006a36  nop     dword ptr [rax+rax+00h]
0x140006a3b  mov     ebx, eax
0x140006a3d  test    eax, eax
0x140006a3f  js      short loc_140006A6A
0x140006a41  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x140006a45  call    cs:__imp_FltClose
0x140006a4c  nop     dword ptr [rax+rax+00h]
0x140006a51  mov     ebx, eax
0x140006a53  test    eax, eax
0x140006a55  js      short loc_140006A6A
0x140006a57  lea     rcx, [rbp+0A0h+var_100]
0x140006a5b  mov     [rbp+0A0h+FileHandle], r12
0x140006a5f  call    BfsRevertTokenImpersonation
0x140006a64  mov     ebx, eax
0x140006a66  test    eax, eax
0x140006a68  jns     short loc_140006AA2
0x140006a6a  mov     eax, cs:dword_140019000
0x140006a70  cmp     eax, 3
0x140006a73  jbe     short loc_140006A99
0x140006a75  lea     rax, [rbp+0A0h+var_11C]
0x140006a79  mov     [rbp+0A0h+var_11C], ebx
0x140006a7c  mov     [rbp+0A0h+var_50], rax
0x140006a80  lea     rdx, byte_140016D91; int
0x140006a87  lea     rax, [rbp+0A0h+var_70]
0x140006a8b  mov     [rbp+0A0h+var_48], rdi
0x140006a8f  mov     [rsp+1A0h+ObjectAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x140006a94  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006a99  lea     rcx, [rbp+0A0h+var_100]
0x140006a9d  call    BfsRevertTokenImpersonation
0x140006aa2  mov     rcx, [rbp+0A0h+FileObject]; Object
0x140006aa6  test    rcx, rcx
0x140006aa9  jz      short loc_140006AB7
0x140006aab  call    cs:__imp_ObfDereferenceObject
0x140006ab2  nop     dword ptr [rax+rax+00h]
0x140006ab7  mov     rcx, [rbp+0A0h+FileHandle]; FileHandle
0x140006abb  test    rcx, rcx
0x140006abe  jz      short loc_140006ACC
0x140006ac0  call    cs:__imp_FltClose
0x140006ac7  nop     dword ptr [rax+rax+00h]
0x140006acc  mov     eax, ebx
0x140006ace  mov     rcx, [rbp+0A0h+var_40]
0x140006ad2  xor     rcx, rsp; StackCookie
0x140006ad5  call    __security_check_cookie
0x140006ada  add     rsp, 170h
0x140006ae1  pop     r15
0x140006ae3  pop     r14
0x140006ae5  pop     r12
0x140006ae7  pop     rdi
0x140006ae8  pop     rsi
0x140006ae9  pop     rbx
0x140006aea  pop     rbp
0x140006aeb  retn
```
