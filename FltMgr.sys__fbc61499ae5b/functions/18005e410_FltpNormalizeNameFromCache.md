# FltpNormalizeNameFromCache

- ea: `0x18005e410`
- end: `0x18005e900`
- name: `FltpNormalizeNameFromCache`
- size: `1264`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180059a00`

## callees

- `0x180009f20`
- `0x18000dcb0`
- `0x18000e2e0`
- `0x18000eb80`
- `0x180014d80`
- `0x180024940`
- `0x180058380`
- `0x18005d850`
- `0x18005df50`
- `0x18005e410`
- `0x1800629c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18005e671`
- `ntoskrnl!ObfDereferenceObject` at `0x18005e671`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005e7eb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x18005e7eb`
- `ntoskrnl!ZwClose` at `0x18005e687`
- `ntoskrnl!ZwClose` at `0x18005e89a`
- `ntoskrnl!ZwClose` at `0x18005e687`
- `ntoskrnl!ZwClose` at `0x18005e89a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005e6bb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005e6bb`
- `ntoskrnl!IoFileObjectType` at `0x18005e698`
- `ntoskrnl!IoCreateFileEx` at `0x18005e5e1`
- `ntoskrnl!IoCreateFileEx` at `0x180079ae3`
- `ntoskrnl!IoCreateFileEx` at `0x18005e5e1`
- `ntoskrnl!IoCreateFileEx` at `0x180079ae3`
- `ntoskrnl!IoGetSilo` at `0x18005e533`
- `ntoskrnl!IoGetSilo` at `0x18005e533`
- `ntoskrnl!PsGetHostSilo` at `0x18005e548`
- `ntoskrnl!PsGetHostSilo` at `0x18005e548`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1800799c5`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1800799c5`

## string_xrefs

- `0x18005e4fa`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18005e614`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18005e6cd`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18005e738`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18005e76e`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18005e7a9`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18005e846`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x180079a5c`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x18005e8be`: `FltpNormalizeNameFromCache`

## pseudocode

```c
__int64 __fastcall FltpNormalizeNameFromCache(__int64 a1)
{
  void **v1; // rsi
  bool v2; // r15
  _BYTE *v4; // rdi
  __int64 *v5; // r9
  int v6; // r12d
  __int64 v7; // rax
  int v8; // r8d
  __int64 *v9; // rdx
  void *v10; // rcx
  int v11; // r8d
  __int64 ECP; // r14
  int v13; // eax
  __int64 v14; // rcx
  char v15; // al
  void *v17; // rcx
  _QWORD *v18; // r12
  int v19; // eax
  _QWORD *v20; // r13
  struct _FLT_FILE_NAME_INFORMATION *v21; // rcx
  unsigned __int16 *v22; // r10
  unsigned int v23; // edx
  __int64 v24; // rax
  __int64 *v25; // r9
  __int64 *v26; // rdx
  void *v27; // rcx
  int v28; // eax
  __int64 v29; // r11
  int v30; // eax
  unsigned __int16 *v31; // r9
  __int64 v32; // rax
  int v33; // eax
  __int16 v34; // cx
  __int64 v35; // rax
  __int64 v36; // rcx
  _WORD *v37; // rcx
  PLARGE_INTEGER AllocationSize; // [rsp+28h] [rbp-A9h]
  PLARGE_INTEGER AllocationSizea; // [rsp+28h] [rbp-A9h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-49h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-39h] BYREF
  __int64 Silo; // [rsp+B8h] [rbp-19h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-11h] BYREF
  _BYTE *v44; // [rsp+138h] [rbp+67h] BYREF
  PVOID Entry; // [rsp+140h] [rbp+6Fh] BYREF

  v1 = (void **)(a1 + 232);
  Entry = 0;
  v2 = 0;
  v44 = 0;
  v4 = 0;
  LOWORD(Silo) = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  if ( *(_QWORD *)(a1 + 232) )
  {
    v18 = (_QWORD *)(a1 + 240);
  }
  else
  {
    v5 = *(__int64 **)(a1 + 8);
    DriverContext.Size = 40;
    v6 = 16777218;
    DriverContext.DeviceObjectHint = *(PVOID *)a1;
    Silo = 1;
    if ( v5 )
    {
      v7 = *(_QWORD *)(a1 + 16);
      if ( v7 )
      {
        v8 = *(_DWORD *)(a1 + 108);
        v9 = 0;
        v10 = *(void **)(v7 + 72);
        v11 = 2 * (v8 & 0x1000000 | 0x800000);
      }
      else
      {
        v11 = 16777218;
        v10 = 0;
        v7 = 0;
        v9 = v5;
      }
      ECP = (unsigned int)TargetedIOCtrlGenerateECP(
                            (PVOID *)&v44,
                            0,
                            v11,
                            v5[13],
                            v10,
                            v7,
                            v9,
                            &DriverContext.ExtraCreateParameter,
                            0);
      v13 = FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7006, 0);
      v4 = v44;
      if ( v13 < 0 )
        goto LABEL_11;
      v2 = (v44[6] & 8) != 0;
    }
    v14 = *(_QWORD *)(a1 + 64);
    DriverContext.TxnParameters = *(PTXN_PARAMETER_BLOCK *)(a1 + 72);
    Silo = IoGetSilo(v14);
    if ( !Silo )
      Silo = PsGetHostSilo();
    v15 = 2 * *(_DWORD *)(a1 + 40);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = ~v15 & 0x40 | 0x200;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 176);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(ECP) = IoCreateFileEx(
                     v1,
                     0x100001u,
                     &ObjectAttributes,
                     &IoStatusBlock,
                     0,
                     0x90u,
                     7u,
                     1u,
                     0x4021u,
                     0,
                     0,
                     CreateFileTypeNone,
                     0,
                     0x800u,
                     &DriverContext);
    if ( (_DWORD)ECP == -1073741191
      && (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(LODWORD(IoStatusBlock.Information)) )
    {
      if ( v4 )
      {
        CleanupTargetedIo(0, &DriverContext.ExtraCreateParameter, v2);
        v24 = *(_QWORD *)(a1 + 16);
        v25 = *(__int64 **)(a1 + 8);
        v44 = 0;
        if ( v24 )
        {
          v26 = 0;
          v27 = *(void **)(v24 + 72);
          v6 = 2 * (*(_DWORD *)(a1 + 108) & 0x1000000 | 0x800000);
        }
        else
        {
          v27 = 0;
          v24 = 0;
          v26 = v25;
        }
        LODWORD(ECP) = TargetedIOCtrlGenerateECP(
                         (PVOID *)&v44,
                         0,
                         v6,
                         v25[13],
                         v27,
                         v24,
                         v26,
                         &DriverContext.ExtraCreateParameter,
                         0);
        v28 = FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7131, 0);
        v4 = v44;
        if ( v28 < 0 )
          goto LABEL_11;
        v2 = (v44[6] & 8) != 0;
      }
      LODWORD(ECP) = IoCreateFileEx(
                       v1,
                       0x100001u,
                       &ObjectAttributes,
                       &IoStatusBlock,
                       0,
                       0x90u,
                       7u,
                       1u,
                       0x204021u,
                       0,
                       0,
                       CreateFileTypeNone,
                       0,
                       0x800u,
                       &DriverContext);
    }
    if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7169, 3221226344LL) < 0 )
      goto LABEL_11;
    v18 = (_QWORD *)(a1 + 240);
    LODWORD(ECP) = ObReferenceObjectByHandle(*v1, 0, (POBJECT_TYPE)IoFileObjectType, 0, (PVOID *)(a1 + 240), 0);
    if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7196, 0) < 0 )
    {
      ZwClose(*v1);
      *v1 = 0;
      goto LABEL_11;
    }
  }
  LODWORD(AllocationSize) = *(_DWORD *)(a1 + 108) & 0x1000000 | 0x201;
  LODWORD(ECP) = FltpAllocateInitializeNameGenerationContext(
                   &Entry,
                   *(_QWORD *)(a1 + 16),
                   *v18,
                   0,
                   AllocationSize,
                   0,
                   0,
                   0,
                   0);
  v19 = FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7232, 3221225626LL);
  v20 = Entry;
  if ( v19 >= 0 )
  {
    AllocationSizea = 0;
    ECP = (unsigned int)FltpGetFileNameInformation(Entry);
    if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7240, 3223060504LL) >= 0
      && !RtlEqualUnicodeString((PCUNICODE_STRING)(v20[15] + 8LL), (PCUNICODE_STRING)(a1 + 176), 0) )
    {
      if ( (byte_180040A43 & 4) != 0 )
        McTemplateU0sww_EtwWriteTransfer(
          *(unsigned __int16 *)(v20[15] + 8LL) >> 1,
          (unsigned int)NameCacheSup_c7265,
          (unsigned int)"FltpNormalizeNameFromCache",
          *(unsigned __int16 *)(a1 + 176) >> 1,
          *(_QWORD *)(a1 + 184),
          *(_WORD *)(v20[15] + 8LL) >> 1,
          *(_QWORD *)(v20[15] + 16LL));
      v22 = *(unsigned __int16 **)(a1 + 112);
      v23 = *v22 + *(unsigned __int16 *)(v20[15] + 8LL) - *(unsigned __int16 *)(a1 + 176);
      LODWORD(v44) = v23;
      if ( v23 > 0xFFFE )
      {
        LODWORD(ECP) = -1073741562;
      }
      else if ( v23 > (unsigned __int64)*((unsigned int *)v22 + 5) - 2 )
      {
        LODWORD(ECP) = FltpReallocNameControl(v22, v23 + 514, 0, 0, AllocationSizea);
      }
      else
      {
        LODWORD(ECP) = 0;
      }
      if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7295, 0) >= 0 )
      {
        v29 = *(unsigned __int16 *)(a1 + 176);
        v30 = (*(unsigned __int16 *)(v20[15] + 8LL) - (int)v29) / 2;
        if ( v30 )
        {
          v31 = *(unsigned __int16 **)(a1 + 112);
          if ( *v31 - (int)v29 > 0 )
            memmove(
              (void *)(*((_QWORD *)v31 + 1) + 2LL * (((unsigned int)v29 >> 1) + v30)),
              (const void *)(*((_QWORD *)v31 + 1) + 2LL * ((unsigned int)v29 >> 1)),
              *v31 - v29);
        }
        memmove(
          *(void **)(*(_QWORD *)(a1 + 112) + 8LL),
          *(const void **)(v20[15] + 16LL),
          *(unsigned __int16 *)(v20[15] + 8LL));
        **(_WORD **)(a1 + 112) = (_WORD)v44;
        v32 = *(_QWORD *)(a1 + 24);
        if ( v32 )
          v33 = *(_DWORD *)(v32 + 56);
        else
          v33 = **(_DWORD **)(a1 + 32);
        if ( (v33 & 1) != 0 )
        {
          v34 = *(_WORD *)(v20[15] + 40LL);
          v35 = *(_QWORD *)(a1 + 112);
          if ( *(_WORD *)(v35 + 24) != v34 )
          {
            *(_WORD *)(v35 + 24) = v34;
            v36 = *(_QWORD *)(a1 + 24);
            if ( v36 )
              v37 = (_WORD *)(v36 + 112);
            else
              v37 = (_WORD *)(*(_QWORD *)(a1 + 32) + 8LL);
            *(_WORD *)(a1 + 168) = *v37 + *(_WORD *)(*(_QWORD *)(a1 + 112) + 24LL);
          }
        }
      }
    }
  }
  if ( v20 )
  {
    v21 = (struct _FLT_FILE_NAME_INFORMATION *)v20[15];
    if ( v21 )
      FltReleaseFileNameInformation(v21);
    FltpFreeNameGenerationContext(v20);
  }
LABEL_11:
  if ( v4 )
  {
    if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 7390, 0) < 0 )
      v4 = 0;
    CleanupTargetedIo(v4, &DriverContext.ExtraCreateParameter, v2);
  }
  if ( *v1 && (*(_DWORD *)(a1 + 40) & 0x100) == 0 )
  {
    ObfDereferenceObject(*(PVOID *)(a1 + 240));
    v17 = *v1;
    *(_QWORD *)(a1 + 240) = 0;
    ZwClose(v17);
    *v1 = 0;
  }
  return (unsigned int)ECP;
}

```

## disassembly

```asm
0x18005e410  mov     rax, rsp
0x18005e413  push    rbp
0x18005e414  push    rbx
0x18005e415  push    rsi
0x18005e416  push    r13
0x18005e418  push    r14
0x18005e41a  lea     rbp, [rax-5Fh]
0x18005e41e  sub     rsp, 100h
0x18005e425  xorps   xmm0, xmm0
0x18005e428  mov     [rax+18h], rdi
0x18005e42c  xor     r13d, r13d
0x18005e42f  mov     [rax-30h], r12
0x18005e433  mov     [rax-38h], r15
0x18005e437  lea     rsi, [rcx+0E8h]
0x18005e43e  xor     eax, eax
0x18005e440  mov     [rbp+57h+Entry], r13
0x18005e444  xor     r15b, r15b
0x18005e447  mov     [rbp+57h+arg_0], r13
0x18005e44b  mov     rbx, rcx
0x18005e44e  mov     edi, r13d
0x18005e451  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18005e455  mov     word ptr [rbp+57h+var_70], ax
0x18005e459  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18005e45d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18005e461  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18005e465  movups  xmmword ptr [rbp+57h+DriverContext.Size], xmm0
0x18005e469  movups  xmmword ptr [rbp+57h+DriverContext.DeviceObjectHint], xmm0
0x18005e46d  cmp     [rsi], rax
0x18005e470  jnz     loc_18005E8AE
0x18005e476  mov     r9, [rcx+8]
0x18005e47a  mov     eax, 28h ; '('
0x18005e47f  mov     [rbp+57h+DriverContext.Size], ax
0x18005e483  mov     r12d, 1000002h
0x18005e489  mov     rax, [rcx]
0x18005e48c  mov     [rbp+57h+DriverContext.DeviceObjectHint], rax
0x18005e490  mov     [rbp+57h+var_70], 1
0x18005e498  test    r9, r9
0x18005e49b  jz      loc_18005E527
0x18005e4a1  mov     rax, [rcx+10h]
0x18005e4a5  test    rax, rax
0x18005e4a8  jz      loc_18005E886
0x18005e4ae  mov     r8d, [rcx+6Ch]
0x18005e4b2  mov     edx, r13d
0x18005e4b5  mov     rcx, [rax+48h]
0x18005e4b9  and     r8d, 1000000h
0x18005e4c0  bts     r8d, 17h
0x18005e4c5  add     r8d, r8d; int
0x18005e4c8  mov     r9, [r9+68h]; int
0x18005e4cc  lea     r10, [rbp+57h+DriverContext.ExtraCreateParameter]
0x18005e4d0  mov     qword ptr [rsp+120h+CreateOptions], r13; __int64
0x18005e4d5  mov     qword ptr [rsp+120h+Disposition], r10; EcpList
0x18005e4da  mov     qword ptr [rsp+120h+ShareAccess], rdx; PVOID
0x18005e4df  xor     edx, edx; int
0x18005e4e1  mov     qword ptr [rsp+120h+FileAttributes], rax; __int64
0x18005e4e6  mov     [rsp+120h+AllocationSize], rcx; FltObject
0x18005e4eb  lea     rcx, [rbp+57h+arg_0]; int
0x18005e4ef  call    TargetedIOCtrlGenerateECP
0x18005e4f4  mov     r8d, 1B5Eh
0x18005e4fa  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x18005e501  xor     r9d, r9d
0x18005e504  mov     ecx, eax
0x18005e506  mov     r14d, eax
0x18005e509  call    FltpDbgStatus
0x18005e50e  mov     rdi, [rbp+57h+arg_0]
0x18005e512  test    eax, eax
0x18005e514  js      loc_18005E627
0x18005e51a  movzx   r15d, byte ptr [rdi+6]
0x18005e51f  shr     r15b, 3
0x18005e523  and     r15b, 1
0x18005e527  mov     rax, [rbx+48h]
0x18005e52b  mov     rcx, [rbx+40h]
0x18005e52f  mov     [rbp+57h+DriverContext.TxnParameters], rax
0x18005e533  call    cs:__imp_IoGetSilo
0x18005e53a  nop     dword ptr [rax+rax+00h]
0x18005e53f  mov     [rbp+57h+var_70], rax
0x18005e543  test    rax, rax
0x18005e546  jnz     short loc_18005E558
0x18005e548  call    cs:__imp_PsGetHostSilo
0x18005e54f  nop     dword ptr [rax+rax+00h]
0x18005e554  mov     [rbp+57h+var_70], rax
0x18005e558  mov     eax, [rbx+28h]
0x18005e55b  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18005e55f  add     eax, eax
0x18005e561  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005e568  not     eax
0x18005e56a  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x18005e56e  and     eax, 40h
0x18005e571  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e575  bts     eax, 9
0x18005e579  xorps   xmm0, xmm0
0x18005e57c  mov     [rbp+57h+ObjectAttributes.Attributes], eax
0x18005e57f  mov     edx, 100001h; DesiredAccess
0x18005e584  lea     rax, [rbx+0B0h]
0x18005e58b  mov     rcx, rsi; FileHandle
0x18005e58e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005e592  lea     rax, [rbp+57h+DriverContext]
0x18005e596  mov     [rsp+70h], rax; DriverContext
0x18005e59b  mov     [rsp+120h+Options], 800h; Options
0x18005e5a3  mov     [rsp+120h+InternalParameters], r13; InternalParameters
0x18005e5a8  mov     [rsp+120h+CreateFileType], r13d; CreateFileType
0x18005e5ad  mov     [rsp+120h+EaLength], r13d; EaLength
0x18005e5b2  mov     [rsp+120h+EaBuffer], r13; EaBuffer
0x18005e5b7  mov     [rsp+120h+CreateOptions], 4021h; CreateOptions
0x18005e5bf  mov     [rsp+120h+Disposition], 1; Disposition
0x18005e5c7  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x18005e5cf  mov     [rsp+120h+FileAttributes], 90h; FileAttributes
0x18005e5d7  mov     [rsp+120h+AllocationSize], r13; AllocationSize
0x18005e5dc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e5e1  call    cs:__imp_IoCreateFileEx
0x18005e5e8  nop     dword ptr [rax+rax+00h]
0x18005e5ed  mov     r14d, eax
0x18005e5f0  cmp     eax, 0C0000279h
0x18005e5f5  jz      loc_1800799C2
0x18005e5fb  mov     r8d, 1C01h
0x18005e601  mov     qword ptr [rsp+120h+FileAttributes], r13
0x18005e606  mov     r9d, 0C0000368h
0x18005e60c  mov     dword ptr [rsp+120h+AllocationSize], 0C000003Ah
0x18005e614  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x18005e61b  mov     ecx, r14d
0x18005e61e  call    FltpDbgStatus
0x18005e623  test    eax, eax
0x18005e625  jns     short loc_18005E698
0x18005e627  mov     r12, [rsp+0F8h]
0x18005e62f  test    rdi, rdi
0x18005e632  jnz     loc_18005E7A6
0x18005e638  cmp     qword ptr [rsi], 0
0x18005e63c  mov     r15, [rsp+120h+var_30]
0x18005e644  mov     rdi, [rsp+120h+arg_10]
0x18005e64c  jnz     short loc_18005E661
0x18005e64e  mov     eax, r14d
0x18005e651  add     rsp, 100h
0x18005e658  pop     r14
0x18005e65a  pop     r13
0x18005e65c  pop     rsi
0x18005e65d  pop     rbx
0x18005e65e  pop     rbp
0x18005e65f  retn
0x18005e661  test    dword ptr [rbx+28h], 100h
0x18005e668  jnz     short loc_18005E64E
0x18005e66a  mov     rcx, [rbx+0F0h]; Object
0x18005e671  call    cs:__imp_ObfDereferenceObject
0x18005e678  nop     dword ptr [rax+rax+00h]
0x18005e67d  mov     rcx, [rsi]; Handle
0x18005e680  mov     [rbx+0F0h], r13
0x18005e687  call    cs:__imp_ZwClose
0x18005e68e  nop     dword ptr [rax+rax+00h]
0x18005e693  mov     [rsi], r13
0x18005e696  jmp     short loc_18005E64E
0x18005e698  mov     r8, cs:__imp_IoFileObjectType
0x18005e69f  lea     r12, [rbx+0F0h]
0x18005e6a6  mov     rcx, [rsi]; Handle
0x18005e6a9  xor     r9d, r9d; AccessMode
0x18005e6ac  mov     qword ptr [rsp+120h+FileAttributes], r13; HandleInformation
0x18005e6b1  xor     edx, edx; DesiredAccess
0x18005e6b3  mov     [rsp+120h+AllocationSize], r12; Object
0x18005e6b8  mov     r8, [r8]; ObjectType
0x18005e6bb  call    cs:__imp_ObReferenceObjectByHandle
0x18005e6c2  nop     dword ptr [rax+rax+00h]
0x18005e6c7  mov     r8d, 1C1Ch
0x18005e6cd  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x18005e6d4  mov     ecx, eax
0x18005e6d6  xor     r9d, r9d
0x18005e6d9  mov     r14d, eax
0x18005e6dc  call    FltpDbgStatus
0x18005e6e1  test    eax, eax
0x18005e6e3  js      loc_18005E897
0x18005e6e9  mov     eax, [rbx+6Ch]
0x18005e6ec  lea     rcx, [rbp+57h+Entry]
0x18005e6f0  mov     r8, [r12]
0x18005e6f4  and     eax, 1000000h
0x18005e6f9  mov     rdx, [rbx+10h]
0x18005e6fd  or      eax, 201h
0x18005e702  mov     [rsp+120h+EaLength], r13d
0x18005e707  xor     r9d, r9d
0x18005e70a  mov     [rsp+120h+CreateOptions], r13d
0x18005e70f  mov     qword ptr [rsp+120h+Disposition], r13
0x18005e714  mov     qword ptr [rsp+120h+ShareAccess], r13
0x18005e719  mov     qword ptr [rsp+120h+FileAttributes], r13
0x18005e71e  mov     dword ptr [rsp+120h+AllocationSize], eax
0x18005e722  call    FltpAllocateInitializeNameGenerationContext
0x18005e727  mov     r8d, 1C40h
0x18005e72d  mov     [rsp+120h+AllocationSize], r13
0x18005e732  mov     r9d, 0C000009Ah
0x18005e738  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x18005e73f  mov     ecx, eax
0x18005e741  mov     r14d, eax
0x18005e744  call    FltpDbgStatus
0x18005e749  mov     r13, [rbp+57h+Entry]
0x18005e74d  test    eax, eax
0x18005e74f  js      short loc_18005E783
0x18005e751  mov     rcx, r13
0x18005e754  call    FltpGetFileNameInformation
0x18005e759  mov     r8d, 1C48h
0x18005e75f  mov     [rsp+120h+AllocationSize], 0
0x18005e768  mov     r9d, 0C01C0018h
0x18005e76e  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x18005e775  mov     ecx, eax
0x18005e777  mov     r14d, eax
0x18005e77a  call    FltpDbgStatus
0x18005e77f  test    eax, eax
0x18005e781  jns     short loc_18005E7D9
0x18005e783  test    r13, r13
0x18005e786  jz      short loc_18005E79E
0x18005e788  mov     rcx, [r13+78h]; FileNameInformation
0x18005e78c  test    rcx, rcx
0x18005e78f  jz      short loc_18005E796
0x18005e791  call    FltReleaseFileNameInformation
0x18005e796  mov     rcx, r13; Entry
0x18005e799  call    FltpFreeNameGenerationContext
0x18005e79e  xor     r13d, r13d
0x18005e7a1  jmp     loc_18005E627
0x18005e7a6  xor     r9d, r9d
0x18005e7a9  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x18005e7b0  mov     r8d, 1CDEh
0x18005e7b6  mov     ecx, r14d
0x18005e7b9  call    FltpDbgStatus
0x18005e7be  test    eax, eax
0x18005e7c0  lea     rdx, [rbp+57h+DriverContext.ExtraCreateParameter]
0x18005e7c4  movzx   r8d, r15b
0x18005e7c8  cmovs   rdi, r13
0x18005e7cc  mov     rcx, rdi
0x18005e7cf  call    CleanupTargetedIo
0x18005e7d4  jmp     loc_18005E638
0x18005e7d9  mov     rcx, [r13+78h]
0x18005e7dd  lea     rdx, [rbx+0B0h]; String2
0x18005e7e4  add     rcx, 8; String1
0x18005e7e8  xor     r8d, r8d; CaseInSensitive
0x18005e7eb  call    cs:__imp_RtlEqualUnicodeString
0x18005e7f2  nop     dword ptr [rax+rax+00h]
0x18005e7f7  test    al, al
0x18005e7f9  jnz     short loc_18005E783
0x18005e7fb  test    cs:byte_180040A43, 4
0x18005e802  jnz     loc_18005E8BA
0x18005e808  mov     rax, [r13+78h]
0x18005e80c  mov     r10, [rbx+70h]
0x18005e810  movzx   edx, word ptr [rax+8]
0x18005e814  movzx   eax, word ptr [rbx+0B0h]
0x18005e81b  sub     edx, eax
0x18005e81d  movzx   eax, word ptr [r10]
0x18005e821  add     edx, eax
0x18005e823  mov     dword ptr [rbp+57h+arg_0], edx
0x18005e826  cmp     edx, 0FFFEh
0x18005e82c  ja      short loc_18005E87E
0x18005e82e  mov     ecx, [r10+14h]
0x18005e832  sub     rcx, 2
0x18005e836  mov     eax, edx
0x18005e838  cmp     rax, rcx
0x18005e83b  ja      short loc_18005E865
0x18005e83d  xor     r14d, r14d
0x18005e840  mov     r8d, 1C7Fh
0x18005e846  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x18005e84d  xor     r9d, r9d
0x18005e850  mov     ecx, r14d
0x18005e853  call    FltpDbgStatus
0x18005e858  test    eax, eax
0x18005e85a  js      loc_18005E783
0x18005e860  jmp     loc_180079AF7
0x18005e865  add     edx, 202h
0x18005e86b  xor     r9d, r9d
0x18005e86e  xor     r8d, r8d
0x18005e871  mov     rcx, r10
0x18005e874  call    FltpReallocNameControl
0x18005e879  mov     r14d, eax
0x18005e87c  jmp     short loc_18005E840
0x18005e87e  mov     r14d, 0C0000106h
0x18005e884  jmp     short loc_18005E840
0x18005e886  mov     r8d, r12d
0x18005e889  mov     rcx, r13
0x18005e88c  mov     rax, r13
0x18005e88f  mov     rdx, r9
0x18005e892  jmp     loc_18005E4C8
0x18005e897  mov     rcx, [rsi]; Handle
0x18005e89a  call    cs:__imp_ZwClose
0x18005e8a1  nop     dword ptr [rax+rax+00h]
0x18005e8a6  mov     [rsi], r13
0x18005e8a9  jmp     loc_18005E627
0x18005e8ae  lea     r12, [rcx+0F0h]
0x18005e8b5  jmp     loc_18005E6E9
0x18005e8ba  mov     rax, [r13+78h]
0x18005e8be  lea     r8, aFltpnormalizen; "FltpNormalizeNameFromCache"
0x18005e8c5  movzx   r9d, word ptr [rbx+0B0h]
0x18005e8cd  lea     rdx, NameCacheSup_c7265
0x18005e8d4  shr     r9d, 1
0x18005e8d7  movzx   ecx, word ptr [rax+8]
0x18005e8db  mov     rax, [rax+10h]
0x18005e8df  mov     qword ptr [rsp+120h+ShareAccess], rax
0x18005e8e4  mov     rax, [rbx+0B8h]
0x18005e8eb  shr     ecx, 1
0x18005e8ed  mov     [rsp+120h+FileAttributes], ecx
0x18005e8f1  mov     [rsp+120h+AllocationSize], rax
0x18005e8f6  call    McTemplateU0sww_EtwWriteTransfer
0x18005e8fb  jmp     loc_18005E808
0x1800799c2  mov     ecx, dword ptr [rbp+57h+IoStatusBlock.Information]
0x1800799c5  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x1800799cc  nop     dword ptr [rax+rax+00h]
0x1800799d1  test    al, al
0x1800799d3  jz      loc_18005E5FB
0x1800799d9  test    rdi, rdi
0x1800799dc  jz      loc_180079A89
0x1800799e2  movzx   r8d, r15b
  ... truncated ...
```
