# FltCreateFileEx2

- ea: `0x18005d2b0`
- end: `0x18005d3b8`
- name: `FltCreateFileEx2`
- size: `264`
- prototype: `NTSTATUS __stdcall(PFLT_FILTER Filter, PFLT_INSTANCE Instance, PHANDLE FileHandle, PFILE_OBJECT *FileObject, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PIO_STATUS_BLOCK IoStatusBlock, PLARGE_INTEGER AllocationSize, ULONG FileAttributes, ULONG ShareAccess, ULONG CreateDisposition, ULONG CreateOptions, PVOID EaBuffer, ULONG EaLength, ULONG Flags, PIO_DRIVER_CREATE_CONTEXT DriverContext)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005d0c0`
- `0x18006d360`
- `0x180074ef0`
- `0x180076120`
- `0x1800835f0`

## callees

- `0x180009f20`
- `0x18005c1d0`
- `0x18005c3b0`
- `0x18005c450`
- `0x18005d2b0`
- `0x18005d470`
- `0x180066990`
- `0x1800718a0`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180079670`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x180079670`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x18007997e`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1800799a2`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x18007997e`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1800799a2`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x180079785`
- `ntoskrnl!FsRtlIsEcpAcknowledged` at `0x180079785`

## pseudocode

```c
NTSTATUS __stdcall FltCreateFileEx2(
        PFLT_FILTER Filter,
        PFLT_INSTANCE Instance,
        PHANDLE FileHandle,
        PFILE_OBJECT *FileObject,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PIO_STATUS_BLOCK IoStatusBlock,
        PLARGE_INTEGER AllocationSize,
        ULONG FileAttributes,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        ULONG CreateOptions,
        PVOID EaBuffer,
        ULONG EaLength,
        ULONG Flags,
        PIO_DRIVER_CREATE_CONTEXT DriverContext)
{
  PFLT_INSTANCE v16; // r12
  POBJECT_ATTRIBUTES v17; // r13
  __int64 v18; // r14
  __int64 v19; // rdi
  __int64 v20; // r15
  NTSTATUS File; // ebx
  struct _ECP_LIST *ExtraCreateParameter; // rcx
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r12
  _FLT_FILTER *v28; // rdx
  PVOID v29; // r12
  __int64 TargetInfo; // rdi
  _QWORD *v31; // rcx
  __int128 v32; // xmm0
  __int16 v33; // ax
  _QWORD *v34; // rcx
  char v35; // [rsp+80h] [rbp-69h]
  unsigned int v36; // [rsp+84h] [rbp-65h]
  __int16 v37; // [rsp+84h] [rbp-65h]
  unsigned int v38; // [rsp+88h] [rbp-61h]
  PVOID v39; // [rsp+90h] [rbp-59h] BYREF
  PVOID EcpContext; // [rsp+98h] [rbp-51h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-49h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-41h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-39h] BYREF
  OBJECT_ATTRIBUTES v44; // [rsp+B8h] [rbp-31h] BYREF

  v16 = Instance;
  v17 = ObjectAttributes;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  memset(&v44, 0, 44);
  v39 = 0;
  EcpContext = 0;
  v43 = 0;
  v41 = 0;
  v42 = 0;
  File = FltpCreateFile(
           Filter,
           (__int64)Instance,
           FileHandle,
           DesiredAccess,
           ObjectAttributes,
           IoStatusBlock,
           AllocationSize,
           FileAttributes,
           ShareAccess,
           CreateDisposition,
           CreateOptions,
           EaBuffer,
           EaLength,
           Flags,
           (ULONG)DriverContext);
  if ( (unsigned int)(File + 1073740952) > 1 )
    return File;
  if ( !DriverContext )
    return File;
  ExtraCreateParameter = DriverContext->ExtraCreateParameter;
  if ( !ExtraCreateParameter )
    return File;
  v24 = FsRtlFindExtraCreateParameter(ExtraCreateParameter, &GUID_ECP_FLT_CREATEFILE_TARGET, &EcpContext, 0);
  if ( (int)FltpDbgStatus(v24, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3320, 0) < 0 )
    return File;
  v36 = FltpGenerateDeviceHintEcp(&v39, ObjectAttributes->ObjectName->Length, DriverContext->ExtraCreateParameter);
  if ( (int)FltpDbgStatus(v36, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3333, 0) < 0 )
    return v36;
  v25 = FltpCreateFile(
          Filter,
          (__int64)v16,
          FileHandle,
          DesiredAccess,
          ObjectAttributes,
          IoStatusBlock,
          AllocationSize,
          FileAttributes,
          ShareAccess,
          CreateDisposition,
          CreateOptions,
          EaBuffer,
          EaLength,
          Flags,
          (ULONG)DriverContext);
  v38 = v25;
  if ( v25 + 1073740952 <= 1 || v25 == -1073740650 )
  {
    v37 = 1;
    while ( FsRtlIsEcpAcknowledged(v39) )
    {
      if ( v38 == -1073740650 )
      {
        LOBYTE(v26) = 1;
        v27 = (unsigned int)FltpResetDeviceHintEcp(v39, v26);
        if ( (int)FltpDbgStatus(v27, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3394, 0) < 0 )
        {
          File = v27;
          break;
        }
        v35 = 0;
      }
      else
      {
        v28 = v16->Filter;
        v29 = v39;
        TargetInfo = (unsigned int)FltpGetTargetInfo(
                                     (_DWORD)v39,
                                     (_DWORD)v28,
                                     (unsigned int)&v43,
                                     (unsigned int)&v41,
                                     (__int64)&v42);
        if ( (int)FltpDbgStatus(TargetInfo, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3419, 0) < 0 )
        {
          File = TargetInfo;
          break;
        }
        v19 = v43;
        v31 = EcpContext;
        if ( !v43 || (*((_BYTE *)EcpContext + 24) & 1) == 0 )
        {
          *((_QWORD *)EcpContext + 1) = v41;
          v31[2] = v42;
          *v31 = v19;
          FsRtlAcknowledgeEcp(v31);
          break;
        }
        FltpResetDeviceHintEcp(v29, 0);
        v20 = v41;
        v18 = v42;
        v35 = 1;
      }
      v16 = (PFLT_INSTANCE)v19;
      *(_OWORD *)&v44.Length = *(_OWORD *)&v17->Length;
      *(_OWORD *)&v44.ObjectName = *(_OWORD *)&v17->ObjectName;
      v32 = *(_OWORD *)&v17->SecurityDescriptor;
      v44.ObjectName = (PUNICODE_STRING)(v18 + 8);
      *(_OWORD *)&v44.SecurityDescriptor = v32;
      v38 = FltpCreateFile(
              Filter,
              v19,
              FileHandle,
              DesiredAccess,
              &v44,
              IoStatusBlock,
              AllocationSize,
              FileAttributes,
              ShareAccess,
              CreateDisposition,
              CreateOptions,
              EaBuffer,
              EaLength,
              Flags,
              (ULONG)DriverContext);
      if ( (int)FltpDbgStatus(v38, "minkernel\\fs\\filtermgr\\filter\\iosup.c", 3485, 0) >= 0 )
      {
        v34 = EcpContext;
        *(_QWORD *)EcpContext = v19;
        v34[1] = v20;
        v34[2] = v18;
        FsRtlAcknowledgeEcp(v34);
        File = v38;
        break;
      }
      if ( v38 + 1073740952 > 1 && v38 != -1073740650 )
      {
        File = v38;
        FltpCleanupTargetInfo(v19, v20, v18);
        break;
      }
      FltpCleanupTargetInfo(v19, v20, v18);
      v33 = v37 + 1;
      if ( !v35 )
        v33 = v37;
      if ( (unsigned __int16)v33 >= 0x40u )
        break;
      v17 = &v44;
      v37 = v33;
    }
    FltpCleanupDeviceHintEcp(DriverContext->ExtraCreateParameter);
    return File;
  }
  FltpCleanupDeviceHintEcp(DriverContext->ExtraCreateParameter);
  return v38;
}

```

## disassembly

```asm
0x18005d2b0  mov     [rsp-8+arg_8], rbx
0x18005d2b5  mov     [rsp-8+arg_18], r9
0x18005d2ba  mov     [rsp-8+FileHandle], r8
0x18005d2bf  mov     [rsp-8+FltObject], rcx
0x18005d2c4  push    rbp
0x18005d2c5  push    rsi
0x18005d2c6  push    rdi
0x18005d2c7  push    r12
0x18005d2c9  push    r13
0x18005d2cb  push    r14
0x18005d2cd  push    r15
0x18005d2cf  lea     rbp, [rsp-7]
0x18005d2d4  sub     rsp, 0F0h
0x18005d2db  mov     rsi, [rbp+37h+DriverContext]
0x18005d2e2  mov     r12, rdx
0x18005d2e5  mov     r13, [rbp+37h+ObjectAttributes]
0x18005d2e9  xor     edx, edx
0x18005d2eb  mov     edx, [rbp+37h+Flags]
0x18005d2f1  xor     r14d, r14d
0x18005d2f4  mov     qword ptr [rsp+120h+EcpContextSize], rsi; EcpContextSize
0x18005d2f9  xorps   xmm0, xmm0
0x18005d2fc  mov     [rsp+120h+var_B0], edx; ULONG
0x18005d300  mov     edi, r14d
0x18005d303  mov     edx, [rbp+37h+EaLength]
0x18005d309  mov     r15d, r14d
0x18005d30c  mov     [rsp+120h+var_B8], edx; ULONG
0x18005d310  mov     rdx, [rbp+37h+EaBuffer]
0x18005d317  mov     [rsp+120h+var_C0], rdx; PVOID
0x18005d31c  mov     edx, [rbp+37h+CreateOptions]
0x18005d322  mov     [rsp+120h+var_C8], edx; ULONG
0x18005d326  mov     edx, [rbp+37h+CreateDisposition]
0x18005d32c  mov     [rsp+120h+var_D0], edx; ULONG
0x18005d330  mov     edx, [rbp+37h+ShareAccess]
0x18005d336  mov     [rsp+120h+var_D8], edx; ULONG
0x18005d33a  mov     edx, [rbp+37h+FileAttributes]
0x18005d340  mov     [rsp+120h+var_E0], edx; ULONG
0x18005d344  mov     rdx, [rbp+37h+AllocationSize]
0x18005d348  mov     [rsp+120h+var_E8], rdx; PLARGE_INTEGER
0x18005d34d  mov     rdx, [rbp+37h+IoStatusBlock]
0x18005d351  mov     [rsp+120h+var_F0], rdx; IoStatusBlock
0x18005d356  mov     edx, [rbp+37h+DesiredAccess]
0x18005d359  movups  xmmword ptr [rbp+37h+var_68.ObjectName], xmm0
0x18005d35d  mov     [rsp+120h+var_F8], r13; ObjectAttributes
0x18005d362  mov     [rsp+120h+var_100], edx; DesiredAccess
0x18005d366  mov     rdx, r12; __int64
0x18005d369  movups  xmmword ptr [rbp+37h+var_68.Length], xmm0
0x18005d36d  mov     [rbp+37h+var_90], r14
0x18005d371  movups  xmmword ptr [rbp+37h+var_68+1Ch], xmm0
0x18005d375  mov     [rbp+37h+EcpContext], r14
0x18005d379  mov     [rbp+37h+var_70], r14
0x18005d37d  mov     [rbp+37h+var_80], r14
0x18005d381  mov     [rbp+37h+var_78], r14
0x18005d385  call    FltpCreateFile
0x18005d38a  mov     ebx, eax
0x18005d38c  add     eax, 3FFFFC98h
0x18005d391  cmp     eax, 1
0x18005d394  jbe     loc_18007964C
0x18005d39a  mov     eax, ebx
0x18005d39c  mov     rbx, [rsp+120h+arg_8]
0x18005d3a4  add     rsp, 0F0h
0x18005d3ab  pop     r15
0x18005d3ad  pop     r14
0x18005d3af  pop     r13
0x18005d3b1  pop     r12
0x18005d3b3  pop     rdi
0x18005d3b4  pop     rsi
0x18005d3b5  pop     rbp
0x18005d3b6  retn
0x18007964c  test    rsi, rsi
0x18007964f  jz      loc_18005D39A
0x180079655  mov     rcx, [rsi+8]; EcpList
0x180079659  test    rcx, rcx
0x18007965c  jz      loc_18005D39A
0x180079662  xor     r9d, r9d; EcpContextSize
0x180079665  lea     r8, [rbp+37h+EcpContext]; EcpContext
0x180079669  lea     rdx, GUID_ECP_FLT_CREATEFILE_TARGET; EcpType
0x180079670  call    cs:__imp_FsRtlFindExtraCreateParameter
0x180079677  nop     dword ptr [rax+rax+00h]
0x18007967c  mov     r8d, 0CF8h
0x180079682  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180079689  mov     ecx, eax
0x18007968b  xor     r9d, r9d
0x18007968e  call    FltpDbgStatus
0x180079693  test    eax, eax
0x180079695  js      loc_18005D39A
0x18007969b  mov     rdx, [r13+10h]
0x18007969f  lea     rcx, [rbp+37h+var_90]
0x1800796a3  mov     r8, [rsi+8]
0x1800796a7  movzx   edx, word ptr [rdx]
0x1800796aa  call    FltpGenerateDeviceHintEcp
0x1800796af  mov     r8d, 0D05h
0x1800796b5  mov     [rbp+37h+var_9C], eax
0x1800796b8  xor     r9d, r9d
0x1800796bb  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800796c2  mov     ecx, eax
0x1800796c4  call    FltpDbgStatus
0x1800796c9  test    eax, eax
0x1800796cb  jns     short loc_1800796D5
0x1800796cd  mov     eax, [rbp+37h+var_9C]
0x1800796d0  jmp     loc_18005D39C
0x1800796d5  mov     eax, [rbp+37h+Flags]
0x1800796db  mov     rdx, r12; __int64
0x1800796de  mov     r9, [rbp+37h+arg_18]
0x1800796e2  mov     r8, [rbp+37h+FileHandle]; FileHandle
0x1800796e6  mov     rcx, [rbp+37h+FltObject]; FltObject
0x1800796ea  mov     qword ptr [rsp+120h+EcpContextSize], rsi; EcpContextSize
0x1800796ef  mov     [rsp+120h+var_B0], eax; ULONG
0x1800796f3  mov     eax, [rbp+37h+EaLength]
0x1800796f9  mov     [rsp+120h+var_B8], eax; ULONG
0x1800796fd  mov     rax, [rbp+37h+EaBuffer]
0x180079704  mov     [rsp+120h+var_C0], rax; PVOID
0x180079709  mov     eax, [rbp+37h+CreateOptions]
0x18007970f  mov     [rsp+120h+var_C8], eax; ULONG
0x180079713  mov     eax, [rbp+37h+CreateDisposition]
0x180079719  mov     [rsp+120h+var_D0], eax; ULONG
0x18007971d  mov     eax, [rbp+37h+ShareAccess]
0x180079723  mov     [rsp+120h+var_D8], eax; ULONG
0x180079727  mov     eax, [rbp+37h+FileAttributes]
0x18007972d  mov     [rsp+120h+var_E0], eax; ULONG
0x180079731  mov     rax, [rbp+37h+AllocationSize]
0x180079735  mov     [rsp+120h+var_E8], rax; PLARGE_INTEGER
0x18007973a  mov     rax, [rbp+37h+IoStatusBlock]
0x18007973e  mov     [rsp+120h+var_F0], rax; IoStatusBlock
0x180079743  mov     eax, [rbp+37h+DesiredAccess]
0x180079746  mov     [rsp+120h+var_F8], r13; ObjectAttributes
0x18007974b  mov     [rsp+120h+var_100], eax; DesiredAccess
0x18007974f  call    FltpCreateFile
0x180079754  mov     [rbp+37h+var_98], eax
0x180079757  lea     ecx, [rax+3FFFFC98h]
0x18007975d  cmp     ecx, 1
0x180079760  jbe     short loc_18007977A
0x180079762  cmp     eax, 0C0000496h
0x180079767  jz      short loc_18007977A
0x180079769  mov     rcx, [rsi+8]
0x18007976d  call    FltpCleanupDeviceHintEcp
0x180079772  mov     eax, [rbp+37h+var_98]
0x180079775  jmp     loc_18005D39C
0x18007977a  mov     [rbp+37h+var_9C], 1
0x180079781  mov     rcx, [rbp+37h+var_90]; EcpContext
0x180079785  call    cs:__imp_FsRtlIsEcpAcknowledged
0x18007978c  nop     dword ptr [rax+rax+00h]
0x180079791  test    al, al
0x180079793  jz      loc_1800799B2
0x180079799  cmp     [rbp+37h+var_98], 0C0000496h
0x1800797a0  jnz     short loc_1800797D5
0x1800797a2  mov     rcx, [rbp+37h+var_90]
0x1800797a6  mov     dl, 1
0x1800797a8  call    FltpResetDeviceHintEcp
0x1800797ad  xor     r9d, r9d
0x1800797b0  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x1800797b7  mov     r8d, 0D42h
0x1800797bd  mov     ecx, eax
0x1800797bf  mov     r12d, eax
0x1800797c2  call    FltpDbgStatus
0x1800797c7  test    eax, eax
0x1800797c9  js      loc_18007996A
0x1800797cf  mov     [rbp+37h+var_A0], 0
0x1800797d3  jmp     short loc_180079849
0x1800797d5  mov     rdx, [r12+48h]
0x1800797da  lea     rax, [rbp+37h+var_78]
0x1800797de  mov     r12, [rbp+37h+var_90]
0x1800797e2  lea     r9, [rbp+37h+var_80]
0x1800797e6  mov     rcx, r12
0x1800797e9  mov     qword ptr [rsp+120h+var_100], rax
0x1800797ee  lea     r8, [rbp+37h+var_70]
0x1800797f2  call    FltpGetTargetInfo
0x1800797f7  xor     r9d, r9d
0x1800797fa  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180079801  mov     r8d, 0D5Bh
0x180079807  mov     ecx, eax
0x180079809  mov     edi, eax
0x18007980b  call    FltpDbgStatus
0x180079810  test    eax, eax
0x180079812  js      loc_1800799B0
0x180079818  mov     rdi, [rbp+37h+var_70]
0x18007981c  mov     rcx, [rbp+37h+EcpContext]; EcpContext
0x180079820  test    rdi, rdi
0x180079823  jz      loc_18007998F
0x180079829  test    byte ptr [rcx+18h], 1
0x18007982d  jz      loc_18007998F
0x180079833  xor     edx, edx
0x180079835  mov     rcx, r12
0x180079838  call    FltpResetDeviceHintEcp
0x18007983d  mov     r15, [rbp+37h+var_80]
0x180079841  mov     r14, [rbp+37h+var_78]
0x180079845  mov     [rbp+37h+var_A0], 1
0x180079849  movups  xmm0, xmmword ptr [r13+0]
0x18007984e  mov     r9, [rbp+37h+arg_18]
0x180079852  lea     rax, [r14+8]
0x180079856  mov     r8, [rbp+37h+FileHandle]; FileHandle
0x18007985a  mov     rdx, rdi; __int64
0x18007985d  mov     rcx, [rbp+37h+FltObject]; FltObject
0x180079861  mov     r12, rdi
0x180079864  mov     qword ptr [rsp+120h+EcpContextSize], rsi; EcpContextSize
0x180079869  movups  xmmword ptr [rbp+37h+var_68.Length], xmm0
0x18007986d  movups  xmm1, xmmword ptr [r13+10h]
0x180079872  movups  xmmword ptr [rbp+37h+var_68.ObjectName], xmm1
0x180079876  movups  xmm0, xmmword ptr [r13+20h]
0x18007987b  mov     [rbp+37h+var_68.ObjectName], rax
0x18007987f  mov     eax, [rbp+37h+Flags]
0x180079885  mov     [rsp+120h+var_B0], eax; ULONG
0x180079889  mov     eax, [rbp+37h+EaLength]
0x18007988f  mov     [rsp+120h+var_B8], eax; ULONG
0x180079893  mov     rax, [rbp+37h+EaBuffer]
0x18007989a  mov     [rsp+120h+var_C0], rax; PVOID
0x18007989f  mov     eax, [rbp+37h+CreateOptions]
0x1800798a5  mov     [rsp+120h+var_C8], eax; ULONG
0x1800798a9  mov     eax, [rbp+37h+CreateDisposition]
0x1800798af  mov     [rsp+120h+var_D0], eax; ULONG
0x1800798b3  mov     eax, [rbp+37h+ShareAccess]
0x1800798b9  mov     [rsp+120h+var_D8], eax; ULONG
0x1800798bd  mov     eax, [rbp+37h+FileAttributes]
0x1800798c3  mov     [rsp+120h+var_E0], eax; ULONG
0x1800798c7  mov     rax, [rbp+37h+AllocationSize]
0x1800798cb  mov     [rsp+120h+var_E8], rax; PLARGE_INTEGER
0x1800798d0  mov     rax, [rbp+37h+IoStatusBlock]
0x1800798d4  mov     [rsp+120h+var_F0], rax; IoStatusBlock
0x1800798d9  lea     rax, [rbp+37h+var_68]
0x1800798dd  mov     [rsp+120h+var_F8], rax; ObjectAttributes
0x1800798e2  mov     eax, [rbp+37h+DesiredAccess]
0x1800798e5  mov     [rsp+120h+var_100], eax; DesiredAccess
0x1800798e9  movups  xmmword ptr [rbp+37h+var_68.SecurityDescriptor], xmm0
0x1800798ed  call    FltpCreateFile
0x1800798f2  xor     r9d, r9d
0x1800798f5  mov     [rbp+37h+var_98], eax
0x1800798f8  mov     r8d, 0D9Dh
0x1800798fe  lea     rdx, aMinkernelFsFil_10; "minkernel\\fs\\filtermgr\\filter\\iosup"...
0x180079905  mov     ecx, eax
0x180079907  mov     r13d, eax
0x18007990a  call    FltpDbgStatus
0x18007990f  test    eax, eax
0x180079911  jns     short loc_18007996F
0x180079913  lea     eax, [r13+3FFFFC98h]
0x18007991a  cmp     eax, 1
0x18007991d  jbe     short loc_18007993B
0x18007991f  cmp     r13d, 0C0000496h
0x180079926  jz      short loc_18007993B
0x180079928  mov     r8, r14
0x18007992b  mov     rdx, r15
0x18007992e  mov     rcx, rdi
0x180079931  mov     ebx, r13d
0x180079934  call    FltpCleanupTargetInfo
0x180079939  jmp     short loc_1800799B2
0x18007993b  mov     r8, r14
0x18007993e  mov     rdx, r15
0x180079941  mov     rcx, rdi
0x180079944  call    FltpCleanupTargetInfo
0x180079949  mov     ecx, [rbp+37h+var_9C]
0x18007994c  cmp     [rbp+37h+var_A0], 0
0x180079950  lea     eax, [rcx+1]
0x180079953  cmovz   ax, cx
0x180079957  cmp     ax, 40h ; '@'
0x18007995b  jnb     short loc_1800799B2
0x18007995d  lea     r13, [rbp+37h+var_68]
0x180079961  mov     word ptr [rbp+37h+var_9C], ax
0x180079965  jmp     loc_180079781
0x18007996a  mov     ebx, r12d
0x18007996d  jmp     short loc_1800799B2
0x18007996f  mov     rcx, [rbp+37h+EcpContext]; EcpContext
0x180079973  mov     [rcx], rdi
0x180079976  mov     [rcx+8], r15
0x18007997a  mov     [rcx+10h], r14
0x18007997e  call    cs:__imp_FsRtlAcknowledgeEcp
0x180079985  nop     dword ptr [rax+rax+00h]
0x18007998a  mov     ebx, r13d
0x18007998d  jmp     short loc_1800799B2
0x18007998f  mov     rax, [rbp+37h+var_80]
0x180079993  mov     [rcx+8], rax
0x180079997  mov     rax, [rbp+37h+var_78]
0x18007999b  mov     [rcx+10h], rax
0x18007999f  mov     [rcx], rdi
0x1800799a2  call    cs:__imp_FsRtlAcknowledgeEcp
0x1800799a9  nop     dword ptr [rax+rax+00h]
0x1800799ae  jmp     short loc_1800799B2
0x1800799b0  mov     ebx, edi
0x1800799b2  mov     rcx, [rsi+8]
0x1800799b6  call    FltpCleanupDeviceHintEcp
0x1800799bb  nop
0x1800799bc  jmp     loc_18005D39A
```
