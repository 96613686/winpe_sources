# WofRelativeStreamOpen

- ea: `0x140039aa0`
- end: `0x140039f0d`
- name: `WofRelativeStreamOpen`
- size: `1133`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140008d30`
- `0x14000ac54`

## callees

- `0x140009770`
- `0x140011560`
- `0x1400116c0`
- `0x140039aa0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140039c83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039c83`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140039b99`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140039b99`
- `ntoskrnl!ObfDereferenceObject` at `0x140039d59`
- `ntoskrnl!ObfDereferenceObject` at `0x140039efc`
- `ntoskrnl!ObfDereferenceObject` at `0x140039d59`
- `ntoskrnl!ObfDereferenceObject` at `0x140039efc`
- `FLTMGR!FltQueryInformationFile` at `0x140039b3d`
- `FLTMGR!FltQueryInformationFile` at `0x140039dfb`
- `FLTMGR!FltQueryInformationFile` at `0x140039b3d`
- `FLTMGR!FltQueryInformationFile` at `0x140039dfb`
- `FLTMGR!FltCreateFileEx2` at `0x140039c6f`
- `FLTMGR!FltCreateFileEx2` at `0x140039d30`
- `FLTMGR!FltCreateFileEx2` at `0x140039ea6`
- `FLTMGR!FltCreateFileEx2` at `0x140039c6f`
- `FLTMGR!FltCreateFileEx2` at `0x140039d30`
- `FLTMGR!FltCreateFileEx2` at `0x140039ea6`
- `FLTMGR!FltSetInformationFile` at `0x140039e3a`
- `FLTMGR!FltSetInformationFile` at `0x140039ed2`
- `FLTMGR!FltSetInformationFile` at `0x140039e3a`
- `FLTMGR!FltSetInformationFile` at `0x140039ed2`
- `FLTMGR!FltClose` at `0x140039d49`
- `FLTMGR!FltClose` at `0x140039ee7`
- `FLTMGR!FltClose` at `0x140039d49`
- `FLTMGR!FltClose` at `0x140039ee7`

## pseudocode

```c
NTSTATUS __fastcall WofRelativeStreamOpen(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        char a4,
        __int64 a5,
        PFILE_OBJECT *a6,
        HANDLE *a7)
{
  struct _FLT_INSTANCE *v9; // rcx
  NTSTATUS result; // eax
  PVOID PoolWithTag; // rax
  struct _FLT_INSTANCE *v13; // rdx
  struct _FLT_FILTER *v14; // rcx
  NTSTATUS v15; // edi
  struct _FLT_INSTANCE *v16; // rdx
  struct _FLT_FILTER *v17; // rcx
  ULONG CreateDisposition; // esi
  struct _FLT_INSTANCE *v19; // rcx
  struct _FLT_INSTANCE *v20; // rcx
  NTSTATUS v21; // eax
  struct _FLT_INSTANCE *v22; // rcx
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-80h] BYREF
  HANDLE v24; // [rsp+88h] [rbp-78h] BYREF
  PFILE_OBJECT v25; // [rsp+90h] [rbp-70h] BYREF
  PVOID P[2]; // [rsp+98h] [rbp-68h] BYREF
  ULONG LengthReturned; // [rsp+A8h] [rbp-58h] BYREF
  ULONG v28; // [rsp+ACh] [rbp-54h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  __int64 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v33; // [rsp+110h] [rbp+10h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v35[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v36; // [rsp+148h] [rbp+48h]

  LOWORD(v33) = 0;
  FileHandle = 0;
  v9 = *(struct _FLT_INSTANCE **)(a1 + 120);
  *(_OWORD *)P = 0;
  FileObject = 0;
  memset(&ObjectAttributes, 0, 44);
  v24 = 0;
  v25 = 0;
  IoStatusBlock = 0;
  LengthReturned = 0;
  FileInformation = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  result = FltQueryInformationFile(v9, a2, &FileInformation, 8u, FileInternalInformation, &LengthReturned);
  if ( result >= 0 )
  {
    memset(&DriverContext, 0, sizeof(DriverContext));
    DriverContext.Size = 40;
    v33 = 1;
    WofPropagateSiloContext(a2, &DriverContext);
    WORD1(P[0]) = *(_WORD *)(a1 + 64) + 10;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, WORD1(P[0]), 0x47666F57u);
    P[1] = PoolWithTag;
    if ( PoolWithTag )
    {
      memmove(PoolWithTag, *(const void **)(a1 + 72), *(unsigned __int16 *)(a1 + 64));
      *((_WORD *)P[1] + ((unsigned __int64)*(unsigned __int16 *)(a1 + 64) >> 1)) = 92;
      *(_QWORD *)((char *)P[1] + *(unsigned __int16 *)(a1 + 64) + 2) = FileInformation;
      v13 = *(struct _FLT_INSTANCE **)(a1 + 120);
      v14 = *(struct _FLT_FILTER **)(a1 + 104);
      LOWORD(P[0]) = WORD1(P[0]);
      ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v15 = FltCreateFileEx2(
              v14,
              v13,
              &FileHandle,
              &FileObject,
              0x100080u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              1u,
              0x202020u,
              0,
              0,
              0,
              &DriverContext);
      ExFreePoolWithTag(P[1], 0);
      if ( v15 < 0 )
        return v15;
      v16 = *(struct _FLT_INSTANCE **)(a1 + 120);
      v17 = *(struct _FLT_FILTER **)(a1 + 104);
      ObjectAttributes.RootDirectory = FileHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &CompressedStream;
      CreateDisposition = 5;
      ObjectAttributes.Attributes = 512;
      if ( !a4 )
        CreateDisposition = 1;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v15 = FltCreateFileEx2(
              v17,
              v16,
              &v24,
              &v25,
              0x100081u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              CreateDisposition,
              0x208020u,
              0,
              0,
              0,
              &DriverContext);
      if ( v15 == -1073741790 )
      {
        if ( a4 )
        {
          v19 = *(struct _FLT_INSTANCE **)(a1 + 120);
          v36 = 0;
          v28 = 0;
          memset(v35, 0, sizeof(v35));
          if ( FltQueryInformationFile(v19, FileObject, v35, 0x28u, FileBasicInformation, &v28) >= 0 && (v36 & 1) != 0 )
          {
            v20 = *(struct _FLT_INSTANCE **)(a1 + 120);
            LODWORD(v36) = v36 & 0xFFFFFFFE;
            FltSetInformationFile(v20, FileObject, v35, 0x28u, FileBasicInformation);
            v21 = FltCreateFileEx2(
                    *(PFLT_FILTER *)(a1 + 104),
                    *(PFLT_INSTANCE *)(a1 + 120),
                    &v24,
                    &v25,
                    0x100081u,
                    &ObjectAttributes,
                    &IoStatusBlock,
                    0,
                    0,
                    7u,
                    CreateDisposition,
                    0x208020u,
                    0,
                    0,
                    0,
                    &DriverContext);
            v22 = *(struct _FLT_INSTANCE **)(a1 + 120);
            LODWORD(v36) = v36 | 1;
            v15 = v21;
            FltSetInformationFile(v22, FileObject, v35, 0x28u, FileBasicInformation);
          }
        }
      }
      FltClose(FileHandle);
      ObfDereferenceObject(FileObject);
      if ( v15 >= 0 )
      {
        if ( a7 )
          *a7 = v24;
        else
          FltClose(v24);
        if ( a6 )
          *a6 = v25;
        else
          ObfDereferenceObject(v25);
        return 0;
      }
      else
      {
        return v15;
      }
    }
    else
    {
      return -1073741670;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140039aa0  push    rbp
0x140039aa2  push    rbx
0x140039aa3  push    rdi
0x140039aa4  push    r12
0x140039aa6  push    r13
0x140039aa8  push    r14
0x140039aaa  push    r15
0x140039aac  lea     rbp, [rsp-60h]
0x140039ab1  sub     rsp, 160h
0x140039ab8  mov     rax, cs:__security_cookie
0x140039abf  xor     rax, rsp
0x140039ac2  mov     [rbp+90h+var_40], rax
0x140039ac6  mov     r14, [rbp+90h+arg_28]
0x140039acd  lea     r8, [rbp+90h+FileInformation]; FileInformation
0x140039ad1  mov     r15, [rbp+90h+arg_30]
0x140039ad8  xorps   xmm0, xmm0
0x140039adb  xor     r13d, r13d
0x140039ade  xor     eax, eax
0x140039ae0  mov     word ptr [rbp+90h+var_80], ax
0x140039ae4  movzx   r12d, r9b
0x140039ae8  lea     rax, [rbp+90h+var_E8]
0x140039aec  mov     [rbp+90h+FileHandle], r13
0x140039af0  mov     rbx, rcx
0x140039af3  mov     [rsp+190h+LengthReturned], rax; LengthReturned
0x140039af8  mov     rcx, [rcx+78h]; Instance
0x140039afc  mov     r9d, 8; Length
0x140039b02  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x140039b06  mov     [rsp+190h+FileInformationClass], 6; FileInformationClass
0x140039b0e  mov     rdi, rdx
0x140039b11  movups  xmmword ptr [rbp+90h+P], xmm0
0x140039b15  mov     [rbp+90h+FileObject], r13
0x140039b19  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x140039b1d  mov     [rbp+90h+var_108], r13
0x140039b21  movups  xmmword ptr [rbp+90h+ObjectAttributes+1Ch], xmm0
0x140039b25  mov     [rbp+90h+var_100], r13
0x140039b29  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x140039b2d  mov     [rbp+90h+var_E8], r13d
0x140039b31  mov     [rbp+90h+FileInformation], r13
0x140039b35  movups  xmmword ptr [rbp+90h+var_A0.Size], xmm0
0x140039b39  movups  xmmword ptr [rbp+90h+var_A0.DeviceObjectHint], xmm0
0x140039b3d  call    cs:__imp_FltQueryInformationFile
0x140039b44  nop     dword ptr [rax+rax+00h]
0x140039b49  test    eax, eax
0x140039b4b  js      loc_140039D73
0x140039b51  xorps   xmm0, xmm0
0x140039b54  mov     [rsp+190h+arg_10], rsi
0x140039b5c  mov     eax, 28h ; '('
0x140039b61  lea     rdx, [rbp+90h+var_A0]
0x140039b65  movups  xmmword ptr [rbp+90h+var_A0.Size], xmm0
0x140039b69  mov     esi, 1
0x140039b6e  mov     [rbp+90h+var_A0.Size], ax
0x140039b72  mov     rcx, rdi
0x140039b75  mov     [rbp+90h+var_80], rsi
0x140039b79  movups  xmmword ptr [rbp+90h+var_A0.DeviceObjectHint], xmm0
0x140039b7d  call    WofPropagateSiloContext
0x140039b82  movzx   eax, word ptr [rbx+40h]
0x140039b86  mov     r8d, 47666F57h; Tag
0x140039b8c  add     ax, 0Ah
0x140039b90  mov     ecx, esi; PoolType
0x140039b92  movzx   edx, ax; NumberOfBytes
0x140039b95  mov     word ptr [rbp+90h+P+2], dx
0x140039b99  call    cs:__imp_ExAllocatePoolWithTag
0x140039ba0  nop     dword ptr [rax+rax+00h]
0x140039ba5  mov     [rbp+90h+P+8], rax
0x140039ba9  test    rax, rax
0x140039bac  jz      loc_140039DB7
0x140039bb2  movzx   r8d, word ptr [rbx+40h]; Size
0x140039bb7  mov     rcx, rax; void *
0x140039bba  mov     rdx, [rbx+48h]; Src
0x140039bbe  call    memmove
0x140039bc3  movzx   ecx, word ptr [rbx+40h]
0x140039bc7  lea     r9, [rbp+90h+FileObject]; FileObject
0x140039bcb  mov     rax, [rbp+90h+P+8]
0x140039bcf  lea     r8, [rbp+90h+FileHandle]; FileHandle
0x140039bd3  shr     rcx, 1
0x140039bd6  xorps   xmm0, xmm0
0x140039bd9  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x140039bdf  mov     rax, [rbp+90h+P+8]
0x140039be3  movzx   edx, word ptr [rbx+40h]
0x140039be7  mov     rcx, [rbp+90h+FileInformation]
0x140039beb  mov     [rdx+rax+2], rcx
0x140039bf0  movzx   eax, word ptr [rbp+90h+P+2]
0x140039bf4  mov     rdx, [rbx+78h]; Instance
0x140039bf8  mov     rcx, [rbx+68h]; Filter
0x140039bfc  mov     word ptr [rbp+90h+P], ax
0x140039c00  lea     rax, [rbp+90h+P]
0x140039c04  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x140039c08  lea     rax, [rbp+90h+var_A0]
0x140039c0c  mov     [rsp+190h+DriverContext], rax; DriverContext
0x140039c11  lea     rax, [rbp+90h+var_78]
0x140039c15  mov     [rsp+190h+Flags], r13d; Flags
0x140039c1a  mov     [rsp+190h+EaLength], r13d; EaLength
0x140039c1f  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x140039c24  mov     [rsp+190h+CreateOptions], 202020h; CreateOptions
0x140039c2c  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x140039c30  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x140039c38  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x140039c3d  mov     [rsp+190h+AllocationSize], r13; AllocationSize
0x140039c42  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140039c47  lea     rax, [rbp+90h+ObjectAttributes]
0x140039c4b  mov     [rsp+190h+LengthReturned], rax; ObjectAttributes
0x140039c50  mov     [rsp+190h+FileInformationClass], 100080h; DesiredAccess
0x140039c58  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x140039c5f  mov     [rbp+90h+ObjectAttributes.RootDirectory], r13
0x140039c63  mov     [rbp+90h+ObjectAttributes.Attributes], 200h
0x140039c6a  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x140039c6f  call    cs:__imp_FltCreateFileEx2
0x140039c76  nop     dword ptr [rax+rax+00h]
0x140039c7b  mov     rcx, [rbp+90h+P+8]; P
0x140039c7f  xor     edx, edx; Tag
0x140039c81  mov     edi, eax
0x140039c83  call    cs:__imp_ExFreePoolWithTag
0x140039c8a  nop     dword ptr [rax+rax+00h]
0x140039c8f  test    edi, edi
0x140039c91  js      loc_140039D69
0x140039c97  mov     rax, [rbp+90h+FileHandle]
0x140039c9b  lea     r9, [rbp+90h+var_100]; FileObject
0x140039c9f  mov     rdx, [rbx+78h]; Instance
0x140039ca3  lea     r8, [rbp+90h+var_108]; FileHandle
0x140039ca7  mov     rcx, [rbx+68h]; Filter
0x140039cab  xorps   xmm0, xmm0
0x140039cae  mov     [rbp+90h+ObjectAttributes.RootDirectory], rax
0x140039cb2  test    r12b, r12b
0x140039cb5  lea     rax, CompressedStream
0x140039cbc  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x140039cc3  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x140039cc7  mov     esi, 5
0x140039ccc  mov     eax, 1
0x140039cd1  mov     [rbp+90h+ObjectAttributes.Attributes], 200h
0x140039cd8  cmovz   esi, eax
0x140039cdb  lea     rax, [rbp+90h+var_A0]
0x140039cdf  mov     [rsp+190h+DriverContext], rax; DriverContext
0x140039ce4  lea     rax, [rbp+90h+var_78]
0x140039ce8  mov     [rsp+190h+Flags], r13d; Flags
0x140039ced  mov     [rsp+190h+EaLength], r13d; EaLength
0x140039cf2  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x140039cf7  mov     [rsp+190h+CreateOptions], 208020h; CreateOptions
0x140039cff  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x140039d03  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x140039d0b  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x140039d10  mov     [rsp+190h+AllocationSize], r13; AllocationSize
0x140039d15  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140039d1a  lea     rax, [rbp+90h+ObjectAttributes]
0x140039d1e  mov     [rsp+190h+LengthReturned], rax; ObjectAttributes
0x140039d23  mov     [rsp+190h+FileInformationClass], 100081h; DesiredAccess
0x140039d2b  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x140039d30  call    cs:__imp_FltCreateFileEx2
0x140039d37  nop     dword ptr [rax+rax+00h]
0x140039d3c  mov     edi, eax
0x140039d3e  cmp     eax, 0C0000022h
0x140039d43  jz      short loc_140039DBE
0x140039d45  mov     rcx, [rbp+90h+FileHandle]; FileHandle
0x140039d49  call    cs:__imp_FltClose
0x140039d50  nop     dword ptr [rax+rax+00h]
0x140039d55  mov     rcx, [rbp+90h+FileObject]; Object
0x140039d59  call    cs:__imp_ObfDereferenceObject
0x140039d60  nop     dword ptr [rax+rax+00h]
0x140039d65  test    edi, edi
0x140039d67  jns     short loc_140039D93
0x140039d69  mov     eax, edi
0x140039d6b  mov     rsi, [rsp+190h+arg_10]
0x140039d73  mov     rcx, [rbp+90h+var_40]
0x140039d77  xor     rcx, rsp; StackCookie
0x140039d7a  call    __security_check_cookie
0x140039d7f  add     rsp, 160h
0x140039d86  pop     r15
0x140039d88  pop     r14
0x140039d8a  pop     r13
0x140039d8c  pop     r12
0x140039d8e  pop     rdi
0x140039d8f  pop     rbx
0x140039d90  pop     rbp
0x140039d91  retn
0x140039d93  test    r15, r15
0x140039d96  jz      loc_140039EE3
0x140039d9c  mov     rax, [rbp+90h+var_108]
0x140039da0  mov     [r15], rax
0x140039da3  test    r14, r14
0x140039da6  jz      loc_140039EF8
0x140039dac  mov     rax, [rbp+90h+var_100]
0x140039db0  mov     [r14], rax
0x140039db3  xor     eax, eax
0x140039db5  jmp     short loc_140039D6B
0x140039db7  mov     eax, 0C000009Ah
0x140039dbc  jmp     short loc_140039D6B
0x140039dbe  test    r12b, r12b
0x140039dc1  jz      short loc_140039D45
0x140039dc3  mov     rdx, [rbp+90h+FileObject]; FileObject
0x140039dc7  lea     r8, [rbp+90h+var_68]; FileInformation
0x140039dcb  mov     rcx, [rbx+78h]; Instance
0x140039dcf  xor     eax, eax
0x140039dd1  xorps   xmm0, xmm0
0x140039dd4  mov     [rbp+90h+var_48], rax
0x140039dd8  lea     rax, [rbp+90h+var_E4]
0x140039ddc  mov     [rbp+90h+var_E4], r13d
0x140039de0  mov     [rsp+190h+LengthReturned], rax; LengthReturned
0x140039de5  mov     r9d, 28h ; '('; Length
0x140039deb  mov     [rsp+190h+FileInformationClass], 4; FileInformationClass
0x140039df3  movups  [rbp+90h+var_68], xmm0
0x140039df7  movups  [rbp+90h+var_58], xmm0
0x140039dfb  call    cs:__imp_FltQueryInformationFile
0x140039e02  nop     dword ptr [rax+rax+00h]
0x140039e07  test    eax, eax
0x140039e09  js      loc_140039D45
0x140039e0f  mov     eax, dword ptr [rbp+90h+var_48]
0x140039e12  test    al, 1
0x140039e14  jz      loc_140039D45
0x140039e1a  mov     rdx, [rbp+90h+FileObject]; FileObject
0x140039e1e  lea     r8, [rbp+90h+var_68]; FileInformation
0x140039e22  mov     rcx, [rbx+78h]; Instance
0x140039e26  and     eax, 0FFFFFFFEh
0x140039e29  mov     r9d, 28h ; '('; Length
0x140039e2f  mov     dword ptr [rbp+90h+var_48], eax
0x140039e32  mov     [rsp+190h+FileInformationClass], 4; FileInformationClass
0x140039e3a  call    cs:__imp_FltSetInformationFile
0x140039e41  nop     dword ptr [rax+rax+00h]
0x140039e46  mov     rdx, [rbx+78h]; Instance
0x140039e4a  lea     rax, [rbp+90h+var_A0]
0x140039e4e  mov     rcx, [rbx+68h]; Filter
0x140039e52  lea     r9, [rbp+90h+var_100]; FileObject
0x140039e56  mov     [rsp+190h+DriverContext], rax; DriverContext
0x140039e5b  lea     r8, [rbp+90h+var_108]; FileHandle
0x140039e5f  mov     [rsp+190h+Flags], r13d; Flags
0x140039e64  lea     rax, [rbp+90h+var_78]
0x140039e68  mov     [rsp+190h+EaLength], r13d; EaLength
0x140039e6d  mov     [rsp+190h+EaBuffer], r13; EaBuffer
0x140039e72  mov     [rsp+190h+CreateOptions], 208020h; CreateOptions
0x140039e7a  mov     [rsp+190h+CreateDisposition], esi; CreateDisposition
0x140039e7e  mov     [rsp+190h+ShareAccess], 7; ShareAccess
0x140039e86  mov     [rsp+190h+FileAttributes], r13d; FileAttributes
0x140039e8b  mov     [rsp+190h+AllocationSize], r13; AllocationSize
0x140039e90  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x140039e95  lea     rax, [rbp+90h+ObjectAttributes]
0x140039e99  mov     [rsp+190h+LengthReturned], rax; ObjectAttributes
0x140039e9e  mov     [rsp+190h+FileInformationClass], 100081h; DesiredAccess
0x140039ea6  call    cs:__imp_FltCreateFileEx2
0x140039ead  nop     dword ptr [rax+rax+00h]
0x140039eb2  mov     rdx, [rbp+90h+FileObject]; FileObject
0x140039eb6  lea     r8, [rbp+90h+var_68]; FileInformation
0x140039eba  mov     rcx, [rbx+78h]; Instance
0x140039ebe  mov     r9d, 28h ; '('; Length
0x140039ec4  or      dword ptr [rbp+90h+var_48], 1
0x140039ec8  mov     edi, eax
0x140039eca  mov     [rsp+190h+FileInformationClass], 4; FileInformationClass
0x140039ed2  call    cs:__imp_FltSetInformationFile
0x140039ed9  nop     dword ptr [rax+rax+00h]
0x140039ede  jmp     loc_140039D45
0x140039ee3  mov     rcx, [rbp+90h+var_108]; FileHandle
0x140039ee7  call    cs:__imp_FltClose
0x140039eee  nop     dword ptr [rax+rax+00h]
0x140039ef3  jmp     loc_140039DA3
0x140039ef8  mov     rcx, [rbp+90h+var_100]; Object
0x140039efc  call    cs:__imp_ObfDereferenceObject
0x140039f03  nop     dword ptr [rax+rax+00h]
0x140039f08  jmp     loc_140039DB3
```
