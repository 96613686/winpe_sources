# BfsCreateStorage

- ea: `0x140010b30`
- end: `0x140010ff5`
- name: `BfsCreateStorage`
- size: `1221`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140007e5c`
- `0x140008598`
- `0x14000cd20`

## callees

- `0x140001008`
- `0x1400105ac`
- `0x140010b30`
- `0x14001226c`
- `0x140012418`
- `0x140012ab0`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x140010c79`
- `ntoskrnl!ExInitializePushLock` at `0x140010d75`
- `ntoskrnl!ExInitializePushLock` at `0x140010e82`
- `ntoskrnl!ExInitializePushLock` at `0x140010c79`
- `ntoskrnl!ExInitializePushLock` at `0x140010d75`
- `ntoskrnl!ExInitializePushLock` at `0x140010e82`
- `ntoskrnl!ZwQueryInformationFile` at `0x140010cc9`
- `ntoskrnl!ZwQueryInformationFile` at `0x140010cc9`
- `ntoskrnl!RtlInitializeBitMap` at `0x140010d53`
- `ntoskrnl!RtlInitializeBitMap` at `0x140010e72`
- `ntoskrnl!RtlInitializeBitMap` at `0x140010d53`
- `ntoskrnl!RtlInitializeBitMap` at `0x140010e72`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010d9f`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010eac`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010d9f`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010eac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010dbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010fca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010dbc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010fca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010fe4`
- `ntoskrnl!ExAllocatePool2` at `0x140010c30`
- `ntoskrnl!ExAllocatePool2` at `0x140010d08`
- `ntoskrnl!ExAllocatePool2` at `0x140010e05`
- `ntoskrnl!ExAllocatePool2` at `0x140010f0e`
- `ntoskrnl!ExAllocatePool2` at `0x140010c30`
- `ntoskrnl!ExAllocatePool2` at `0x140010d08`
- `ntoskrnl!ExAllocatePool2` at `0x140010e05`
- `ntoskrnl!ExAllocatePool2` at `0x140010f0e`
- `FLTMGR!FltClose` at `0x140010fb4`
- `FLTMGR!FltClose` at `0x140010fb4`
- `FLTMGR!FltCreateFileEx2` at `0x140010bf9`
- `FLTMGR!FltCreateFileEx2` at `0x140010bf9`

## pseudocode

```c
__int64 __fastcall BfsCreateStorage(
        struct _FLT_FILTER *a1,
        struct _FLT_INSTANCE *a2,
        void *a3,
        struct _UNICODE_STRING *a4,
        unsigned __int64 **a5)
{
  _DWORD *v5; // rsi
  _DWORD *v6; // r15
  __int64 v7; // rcx
  NTSTATUS Block; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int64 *v11; // rdi
  unsigned __int64 *Pool2; // rax
  struct _EVENT_DATA_DESCRIPTOR *p_FileInformation; // rax
  ULONG_PTR Information; // rax
  __int64 v15; // rax
  bool v16; // cc
  _DWORD *v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // r13d
  __int64 v21; // rax
  __int64 v22; // rdx
  int DesiredAccess; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v25; // [rsp+84h] [rbp-7Ch] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 **v28; // [rsp+A0h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK v30; // [rsp+D8h] [rbp-28h] BYREF
  char v31; // [rsp+E8h] [rbp-18h] BYREF
  int *v32; // [rsp+108h] [rbp+8h]
  __int64 v33; // [rsp+110h] [rbp+10h]
  __int128 FileInformation; // [rsp+118h] [rbp+18h] BYREF
  __int64 v35; // [rsp+128h] [rbp+28h]
  int *v36; // [rsp+138h] [rbp+38h]
  __int64 v37; // [rsp+140h] [rbp+40h]

  v28 = a5;
  v5 = 0;
  v6 = 0;
  *a5 = 0;
  ObjectAttributes.SecurityDescriptor = gBfsPolicyStorageFileDescriptor;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.ObjectName = a4;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  FileHandle = 0;
  ObjectAttributes.SecurityQualityOfService = 0;
  Block = FltCreateFileEx2(
            a1,
            a2,
            &FileHandle,
            0,
            0xC0110000,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x80u,
            0,
            3u,
            0x860u,
            0,
            0,
            0x100u,
            0);
  if ( Block < 0 )
  {
    v11 = 0;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v24 = Block;
LABEL_7:
      v37 = 4;
      v36 = &v24;
      p_FileInformation = (struct _EVENT_DATA_DESCRIPTOR *)&FileInformation;
LABEL_37:
      tlgWriteTransfer_EtwWriteTransfer(
        v7,
        (unsigned __int8 *)&byte_140016D91,
        v9,
        v10,
        DesiredAccess,
        p_FileInformation);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  Pool2 = (unsigned __int64 *)ExAllocatePool2(256, 200, 1936942658);
  v11 = Pool2;
  if ( Pool2 )
  {
    ExInitializePushLock(Pool2);
    v11[1] = (unsigned __int64)FileHandle;
    if ( IoStatusBlock.Information == 2 )
      goto LABEL_22;
    v30 = 0;
    v35 = 0;
    FileInformation = 0;
    Block = ZwQueryInformationFile(FileHandle, &v30, &FileInformation, 0x18u, FileStandardInformation);
    if ( Block < 0 )
      goto LABEL_34;
    Information = IoStatusBlock.Information;
    if ( !*((_QWORD *)&FileInformation + 1) )
      Information = 2;
    IoStatusBlock.Information = Information;
    if ( Information == 2 )
    {
LABEL_22:
      v25 = 0;
      v24 = 0;
      v18 = (_DWORD *)ExAllocatePool2(256, 0x4000, 1668507202);
      v5 = v18;
      if ( !v18 )
        goto LABEL_23;
      memset(v18, 0, 0x4000u);
      v19 = v5[1] & 0xFF000001;
      *v5 = 1131636290;
      v5[2] = 0x4000;
      v5[1] = v19 | 1;
      *((_BYTE *)v5 + 7) = 0;
      v11[2] = (unsigned __int64)v5;
      RtlInitializeBitMap((PRTL_BITMAP)(v11 + 3), v5 + 6, 0x1FF40u);
      ExInitializePushLock(v11 + 9);
      RtlInitializeGenericTableAvl(
        (PRTL_AVL_TABLE)(v11 + 10),
        BfsCompareTableEntries,
        BfsAllocateTableEntry,
        BfsFreeTableEntry,
        0);
      Block = BfsAllocateBlock(v11, &v25);
      if ( Block < 0 )
        goto LABEL_34;
      if ( v25 )
      {
        Block = -1073741774;
        goto LABEL_34;
      }
      Block = BfsAllocateBlock(v11, &v24);
      if ( Block < 0 )
        goto LABEL_34;
      v20 = v24;
      *(_DWORD *)(v11[2] + 12) = v24;
      v21 = ExAllocatePool2(256, 0x4000, 1651729986);
      v6 = (_DWORD *)v21;
      if ( !v21 )
      {
LABEL_23:
        v16 = (unsigned int)dword_140019000 <= 3;
        goto LABEL_24;
      }
      memset((void *)(v21 + 4), 0, 0x3FFCu);
      v22 = v25;
      *v6 = 1148413506;
      Block = BfsWriteBlock(v11, v22, v5);
      if ( Block >= 0 )
      {
        Block = BfsWriteBlock(v11, v20, v6);
        if ( Block >= 0 )
        {
          Block = BfsOpenRootDirectory(v11);
          if ( Block >= 0 )
            goto LABEL_18;
        }
      }
    }
    else
    {
      v15 = ExAllocatePool2(256, 0x4000, 1668507202);
      v5 = (_DWORD *)v15;
      if ( !v15 )
      {
        v7 = (unsigned int)dword_140019000;
        v16 = (unsigned int)dword_140019000 <= 3;
LABEL_24:
        Block = -1073741801;
        if ( v16 )
          goto LABEL_38;
        v24 = -1073741801;
LABEL_36:
        v33 = 4;
        v32 = &v24;
        p_FileInformation = (struct _EVENT_DATA_DESCRIPTOR *)&v31;
        goto LABEL_37;
      }
      Block = BfsReadBlock(v11, 0, v15);
      if ( Block >= 0 )
      {
        v11[2] = (unsigned __int64)v5;
        RtlInitializeBitMap((PRTL_BITMAP)(v11 + 3), v5 + 6, 0x1FF40u);
        Block = BfsOpenRootDirectory(v11);
        if ( Block >= 0 )
        {
          ExInitializePushLock(v11 + 9);
          RtlInitializeGenericTableAvl(
            (PRTL_AVL_TABLE)(v11 + 10),
            BfsCompareTableEntries,
            BfsAllocateTableEntry,
            BfsFreeTableEntry,
            0);
LABEL_18:
          *v28 = v11;
          goto LABEL_19;
        }
      }
    }
LABEL_34:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_38;
    v24 = Block;
    goto LABEL_36;
  }
  Block = -1073741801;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v24 = -1073741801;
    goto LABEL_7;
  }
LABEL_38:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
LABEL_19:
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return (unsigned int)Block;
}

```

## disassembly

```asm
0x140010b30  push    rbp
0x140010b32  push    rbx
0x140010b33  push    rsi
0x140010b34  push    rdi
0x140010b35  push    r13
0x140010b37  push    r14
0x140010b39  push    r15
0x140010b3b  lea     rbp, [rsp-50h]
0x140010b40  sub     rsp, 150h
0x140010b47  mov     rax, cs:__security_cookie
0x140010b4e  xor     rax, rsp
0x140010b51  mov     [rbp+80h+var_38], rax
0x140010b55  mov     rax, [rbp+80h+arg_20]
0x140010b5c  xor     r13d, r13d
0x140010b5f  mov     [rsp+180h+DriverContext], r13; DriverContext
0x140010b64  xorps   xmm0, xmm0
0x140010b67  mov     [rbp+80h+var_E0], rax
0x140010b6b  mov     edi, 100h
0x140010b70  mov     [rsp+180h+Flags], edi; Flags
0x140010b74  mov     esi, r13d
0x140010b77  mov     [rsp+180h+EaLength], r13d; EaLength
0x140010b7c  mov     r15d, r13d
0x140010b7f  mov     [rsp+180h+EaBuffer], r13; EaBuffer
0x140010b84  mov     [rsp+180h+CreateOptions], 860h; CreateOptions
0x140010b8c  mov     [rsp+180h+CreateDisposition], 3; CreateDisposition
0x140010b94  mov     [rsp+180h+ShareAccess], r13d; ShareAccess
0x140010b99  mov     [rax], r13
0x140010b9c  lea     rax, gBfsPolicyStorageFileDescriptor
0x140010ba3  mov     [rsp+180h+FileAttributes], 80h; FileAttributes
0x140010bab  mov     [rbp+80h+var_D8.SecurityDescriptor], rax
0x140010baf  lea     rax, [rbp+80h+var_F0]
0x140010bb3  mov     [rsp+180h+AllocationSize], r13; AllocationSize
0x140010bb8  mov     [rsp+180h+IoStatusBlock], rax; IoStatusBlock
0x140010bbd  lea     rax, [rbp+80h+var_D8]
0x140010bc1  mov     [rbp+80h+var_D8.RootDirectory], r8
0x140010bc5  lea     r8, [rbp+80h+FileHandle]; FileHandle
0x140010bc9  mov     [rbp+80h+var_D8.ObjectName], r9
0x140010bcd  xor     r9d, r9d; FileObject
0x140010bd0  mov     [rsp+180h+ObjectAttributes], rax; ObjectAttributes
0x140010bd5  mov     [rsp+180h+DesiredAccess], 0C0110000h; DesiredAccess
0x140010bdd  movups  xmmword ptr [rbp+80h+var_F0], xmm0
0x140010be1  mov     qword ptr [rbp+80h+var_D8.Length], 30h ; '0'
0x140010be9  mov     qword ptr [rbp+80h+var_D8.Attributes], 240h
0x140010bf1  mov     [rbp+80h+FileHandle], r13
0x140010bf5  mov     [rbp+80h+var_D8.SecurityQualityOfService], r13
0x140010bf9  call    cs:__imp_FltCreateFileEx2
0x140010c00  nop     dword ptr [rax+rax+00h]
0x140010c05  mov     ebx, eax
0x140010c07  test    eax, eax
0x140010c09  jns     short loc_140010C22
0x140010c0b  mov     eax, cs:dword_140019000
0x140010c11  mov     edi, r13d
0x140010c14  cmp     eax, 3
0x140010c17  jbe     loc_140010FAB
0x140010c1d  mov     [rbp+80h+var_100], ebx
0x140010c20  jmp     short loc_140010C5D
0x140010c22  mov     edx, 0C8h
0x140010c27  mov     r8d, 73736642h
0x140010c2d  mov     rcx, rdi
0x140010c30  call    cs:__imp_ExAllocatePool2
0x140010c37  nop     dword ptr [rax+rax+00h]
0x140010c3c  mov     rdi, rax
0x140010c3f  test    rax, rax
0x140010c42  jnz     short loc_140010C76
0x140010c44  mov     eax, cs:dword_140019000
0x140010c4a  mov     edx, 0C0000017h
0x140010c4f  mov     ebx, edx
0x140010c51  cmp     eax, 3
0x140010c54  jbe     loc_140010FAB
0x140010c5a  mov     [rbp+80h+var_100], edx
0x140010c5d  lea     rax, [rbp+80h+var_100]
0x140010c61  mov     [rbp+80h+var_40], 4
0x140010c69  mov     [rbp+80h+var_48], rax
0x140010c6d  lea     rax, [rbp+80h+FileInformation]
0x140010c71  jmp     loc_140010F9A
0x140010c76  mov     rcx, rdi; PushLock
0x140010c79  call    cs:__imp_ExInitializePushLock
0x140010c80  nop     dword ptr [rax+rax+00h]
0x140010c85  mov     rax, [rbp+80h+FileHandle]
0x140010c89  mov     r14d, 2
0x140010c8f  mov     [rdi+8], rax
0x140010c93  cmp     [rbp+80h+var_F0.Information], r14
0x140010c97  jz      loc_140010DE9
0x140010c9d  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140010ca1  lea     r9d, [r14+16h]; Length
0x140010ca5  xorps   xmm0, xmm0
0x140010ca8  mov     [rsp+180h+DesiredAccess], 5; FileInformationClass
0x140010cb0  xorps   xmm1, xmm1
0x140010cb3  lea     r8, [rbp+80h+FileInformation]; FileInformation
0x140010cb7  xor     eax, eax
0x140010cb9  lea     rdx, [rbp+80h+var_A8]; IoStatusBlock
0x140010cbd  movups  xmmword ptr [rbp+80h+var_A8], xmm0
0x140010cc1  mov     [rbp+80h+var_58], rax
0x140010cc5  movups  [rbp+80h+FileInformation], xmm1
0x140010cc9  call    cs:__imp_ZwQueryInformationFile
0x140010cd0  nop     dword ptr [rax+rax+00h]
0x140010cd5  mov     ebx, eax
0x140010cd7  test    eax, eax
0x140010cd9  js      loc_140010F78
0x140010cdf  cmp     qword ptr [rbp+80h+FileInformation+8], r13
0x140010ce3  mov     rax, [rbp+80h+var_F0.Information]
0x140010ce7  cmovz   rax, r14
0x140010ceb  mov     [rbp+80h+var_F0.Information], rax
0x140010cef  cmp     rax, r14
0x140010cf2  jz      loc_140010DE9
0x140010cf8  mov     edx, 4000h
0x140010cfd  mov     ecx, 100h
0x140010d02  mov     r8d, 63736642h
0x140010d08  call    cs:__imp_ExAllocatePool2
0x140010d0f  nop     dword ptr [rax+rax+00h]
0x140010d14  mov     rsi, rax
0x140010d17  test    rax, rax
0x140010d1a  jnz     short loc_140010D2A
0x140010d1c  mov     ecx, cs:dword_140019000
0x140010d22  cmp     ecx, 3
0x140010d25  jmp     loc_140010E22
0x140010d2a  mov     r8, rsi
0x140010d2d  xor     edx, edx
0x140010d2f  mov     rcx, rdi
0x140010d32  call    BfsReadBlock
0x140010d37  mov     ebx, eax
0x140010d39  test    eax, eax
0x140010d3b  js      loc_140010F78
0x140010d41  lea     rdx, [rsi+18h]; BitMapBuffer
0x140010d45  mov     [rdi+10h], rsi
0x140010d49  lea     rcx, [rdi+18h]; BitMapHeader
0x140010d4d  mov     r8d, 1FF40h; SizeOfBitMap
0x140010d53  call    cs:__imp_RtlInitializeBitMap
0x140010d5a  nop     dword ptr [rax+rax+00h]
0x140010d5f  mov     rcx, rdi
0x140010d62  call    BfsOpenRootDirectory
0x140010d67  mov     ebx, eax
0x140010d69  test    eax, eax
0x140010d6b  js      loc_140010F78
0x140010d71  lea     rcx, [rdi+48h]; PushLock
0x140010d75  call    cs:__imp_ExInitializePushLock
0x140010d7c  nop     dword ptr [rax+rax+00h]
0x140010d81  lea     rcx, [rdi+50h]; Table
0x140010d85  mov     qword ptr [rsp+180h+DesiredAccess], r13; TableContext
0x140010d8a  lea     r9, BfsFreeTableEntry; FreeRoutine
0x140010d91  lea     r8, BfsAllocateTableEntry; AllocateRoutine
0x140010d98  lea     rdx, BfsCompareTableEntries; CompareRoutine
0x140010d9f  call    cs:__imp_RtlInitializeGenericTableAvl
0x140010da6  nop     dword ptr [rax+rax+00h]
0x140010dab  mov     rax, [rbp+80h+var_E0]
0x140010daf  mov     [rax], rdi
0x140010db2  test    r15, r15
0x140010db5  jz      short loc_140010DC8
0x140010db7  xor     edx, edx; Tag
0x140010db9  mov     rcx, r15; P
0x140010dbc  call    cs:__imp_ExFreePoolWithTag
0x140010dc3  nop     dword ptr [rax+rax+00h]
0x140010dc8  mov     eax, ebx
0x140010dca  mov     rcx, [rbp+80h+var_38]
0x140010dce  xor     rcx, rsp; StackCookie
0x140010dd1  call    __security_check_cookie
0x140010dd6  add     rsp, 150h
0x140010ddd  pop     r15
0x140010ddf  pop     r14
0x140010de1  pop     r13
0x140010de3  pop     rdi
0x140010de4  pop     rsi
0x140010de5  pop     rbx
0x140010de6  pop     rbp
0x140010de7  retn
0x140010de9  mov     r14d, 4000h
0x140010def  mov     [rbp+80h+var_FC], r13d
0x140010df3  mov     edx, r14d
0x140010df6  mov     [rbp+80h+var_100], r13d
0x140010dfa  mov     r8d, 63736642h
0x140010e00  mov     ecx, 100h
0x140010e05  call    cs:__imp_ExAllocatePool2
0x140010e0c  nop     dword ptr [rax+rax+00h]
0x140010e11  mov     rsi, rax
0x140010e14  test    rax, rax
0x140010e17  jnz     short loc_140010E37
0x140010e19  mov     eax, cs:dword_140019000
0x140010e1f  cmp     eax, 3
0x140010e22  mov     edx, 0C0000017h
0x140010e27  mov     ebx, edx
0x140010e29  jbe     loc_140010FAB
0x140010e2f  mov     [rbp+80h+var_100], edx
0x140010e32  jmp     loc_140010F86
0x140010e37  mov     r8, r14; Size
0x140010e3a  xor     edx, edx; Val
0x140010e3c  mov     rcx, rsi; void *
0x140010e3f  call    memset
0x140010e44  mov     eax, [rsi+4]
0x140010e47  lea     rdx, [rsi+18h]; BitMapBuffer
0x140010e4b  and     eax, 0FF000001h
0x140010e50  mov     dword ptr [rsi], 43736642h
0x140010e56  or      eax, 1
0x140010e59  mov     [rsi+8], r14d
0x140010e5d  mov     [rsi+4], eax
0x140010e60  lea     rcx, [rdi+18h]; BitMapHeader
0x140010e64  mov     [rsi+7], r13b
0x140010e68  mov     r8d, 1FF40h; SizeOfBitMap
0x140010e6e  mov     [rdi+10h], rsi
0x140010e72  call    cs:__imp_RtlInitializeBitMap
0x140010e79  nop     dword ptr [rax+rax+00h]
0x140010e7e  lea     rcx, [rdi+48h]; PushLock
0x140010e82  call    cs:__imp_ExInitializePushLock
0x140010e89  nop     dword ptr [rax+rax+00h]
0x140010e8e  lea     rcx, [rdi+50h]; Table
0x140010e92  mov     qword ptr [rsp+180h+DesiredAccess], r13; int
0x140010e97  lea     r9, BfsFreeTableEntry; FreeRoutine
0x140010e9e  lea     r8, BfsAllocateTableEntry; AllocateRoutine
0x140010ea5  lea     rdx, BfsCompareTableEntries; CompareRoutine
0x140010eac  call    cs:__imp_RtlInitializeGenericTableAvl
0x140010eb3  nop     dword ptr [rax+rax+00h]
0x140010eb8  lea     rdx, [rbp+80h+var_FC]
0x140010ebc  mov     rcx, rdi
0x140010ebf  call    BfsAllocateBlock
0x140010ec4  mov     ebx, eax
0x140010ec6  test    eax, eax
0x140010ec8  js      loc_140010F78
0x140010ece  cmp     [rbp+80h+var_FC], r13d
0x140010ed2  jz      short loc_140010EDE
0x140010ed4  mov     ebx, 0C0000032h
0x140010ed9  jmp     loc_140010F78
0x140010ede  lea     rdx, [rbp+80h+var_100]
0x140010ee2  mov     rcx, rdi
0x140010ee5  call    BfsAllocateBlock
0x140010eea  mov     ebx, eax
0x140010eec  test    eax, eax
0x140010eee  js      loc_140010F78
0x140010ef4  mov     rax, [rdi+10h]
0x140010ef8  mov     r8d, 62736642h
0x140010efe  mov     r13d, [rbp+80h+var_100]
0x140010f02  mov     rdx, r14
0x140010f05  mov     ecx, 100h
0x140010f0a  mov     [rax+0Ch], r13d
0x140010f0e  call    cs:__imp_ExAllocatePool2
0x140010f15  nop     dword ptr [rax+rax+00h]
0x140010f1a  mov     r15, rax
0x140010f1d  test    rax, rax
0x140010f20  jz      loc_140010E19
0x140010f26  lea     rcx, [rax+4]; void *
0x140010f2a  xor     edx, edx; Val
0x140010f2c  mov     r8d, 3FFCh; Size
0x140010f32  call    memset
0x140010f37  mov     edx, [rbp+80h+var_FC]
0x140010f3a  mov     r8, rsi
0x140010f3d  mov     rcx, rdi
0x140010f40  mov     dword ptr [r15], 44736642h
0x140010f47  call    BfsWriteBlock
0x140010f4c  mov     ebx, eax
0x140010f4e  test    eax, eax
0x140010f50  js      short loc_140010F78
0x140010f52  mov     r8, r15
0x140010f55  mov     edx, r13d
0x140010f58  mov     rcx, rdi
0x140010f5b  call    BfsWriteBlock
0x140010f60  mov     ebx, eax
0x140010f62  test    eax, eax
0x140010f64  js      short loc_140010F78
0x140010f66  mov     rcx, rdi
0x140010f69  call    BfsOpenRootDirectory
0x140010f6e  mov     ebx, eax
0x140010f70  test    eax, eax
0x140010f72  jns     loc_140010DAB
0x140010f78  mov     eax, cs:dword_140019000
0x140010f7e  cmp     eax, 3
0x140010f81  jbe     short loc_140010FAB
0x140010f83  mov     [rbp+80h+var_100], ebx
0x140010f86  lea     rax, [rbp+80h+var_100]
0x140010f8a  mov     [rbp+80h+var_70], 4
0x140010f92  mov     [rbp+80h+var_78], rax
0x140010f96  lea     rax, [rbp+80h+var_98]
0x140010f9a  lea     rdx, byte_140016D91; int
0x140010fa1  mov     [rsp+180h+ObjectAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x140010fa6  call    _tlgWriteTransfer_EtwWriteTransfer
0x140010fab  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140010faf  test    rcx, rcx
0x140010fb2  jz      short loc_140010FC0
0x140010fb4  call    cs:__imp_FltClose
0x140010fbb  nop     dword ptr [rax+rax+00h]
0x140010fc0  test    rdi, rdi
0x140010fc3  jz      short loc_140010FD6
0x140010fc5  xor     edx, edx; Tag
0x140010fc7  mov     rcx, rdi; P
0x140010fca  call    cs:__imp_ExFreePoolWithTag
0x140010fd1  nop     dword ptr [rax+rax+00h]
0x140010fd6  test    rsi, rsi
0x140010fd9  jz      loc_140010DB2
0x140010fdf  xor     edx, edx; Tag
0x140010fe1  mov     rcx, rsi; P
0x140010fe4  call    cs:__imp_ExFreePoolWithTag
0x140010feb  nop     dword ptr [rax+rax+00h]
0x140010ff0  jmp     loc_140010DB2
```
