# FltpGetFileNameOpenByIdWorker

- ea: `0x18005b920`
- end: `0x18005bf87`
- name: `FltpGetFileNameOpenByIdWorker`
- size: `1639`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18001d680`
- `0x18005a2e0`

## callees

- `0x180009f20`
- `0x180009f80`
- `0x18000dcb0`
- `0x18000e2e0`
- `0x18000f5b0`
- `0x180058380`
- `0x18005a460`
- `0x18005b920`
- `0x18005c5a0`
- `0x18005d850`
- `0x18005df50`
- `0x180063440`
- `0x18006ed90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005be8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005be8d`
- `ntoskrnl!ObfDereferenceObject` at `0x18005be09`
- `ntoskrnl!ObfDereferenceObject` at `0x18005be09`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005ba58`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005ba58`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18005ba7c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18005ba7c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005ba93`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005ba93`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18005b98d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18005b98d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18005bdbe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18005bdbe`
- `ntoskrnl!ZwClose` at `0x18005be1e`
- `ntoskrnl!ZwClose` at `0x18005be1e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005bc75`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18005bc75`
- `ntoskrnl!IoFileObjectType` at `0x18005bc54`
- `ntoskrnl!IoCreateFileEx` at `0x18005bc16`
- `ntoskrnl!IoCreateFileEx` at `0x18005bc16`
- `ntoskrnl!IoGetSilo` at `0x18005bb40`
- `ntoskrnl!IoGetSilo` at `0x18005bb40`
- `ntoskrnl!PsGetHostSilo` at `0x18005bb55`
- `ntoskrnl!PsGetHostSilo` at `0x18005bb55`

## pseudocode

```c
__int64 __fastcall FltpGetFileNameOpenByIdWorker(__int64 a1)
{
  __int64 ECP; // r12
  _DWORD *v3; // r14
  void *v4; // rsi
  _BYTE *v5; // r15
  UNICODE_STRING *v6; // rax
  UNICODE_STRING *v7; // rbx
  bool v8; // r13
  int v9; // edx
  __int64 v10; // rax
  unsigned __int16 *v11; // rax
  unsigned int v12; // edx
  const UNICODE_STRING *v13; // rax
  const UNICODE_STRING *v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  char v19; // al
  __int64 v20; // rcx
  ULONG Options; // eax
  __int64 v22; // rsi
  unsigned int StreamListCtrl; // r12d
  int v24; // eax
  int v25; // eax
  __int64 v27; // r8
  int v28; // edx
  void *v29; // [rsp+88h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+90h] [rbp-78h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+98h] [rbp-70h] BYREF
  __int64 Silo; // [rsp+B8h] [rbp-50h]
  _QWORD *v33; // [rsp+C0h] [rbp-48h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE *v36; // [rsp+150h] [rbp+48h] BYREF
  PVOID Object; // [rsp+158h] [rbp+50h] BYREF
  _DWORD *v38; // [rsp+160h] [rbp+58h]

  LODWORD(ECP) = 0;
  FileHandle = 0;
  LOWORD(Silo) = 0;
  v3 = 0;
  memset(&ObjectAttributes, 0, 44);
  Object = 0;
  v4 = 0;
  v38 = 0;
  v5 = 0;
  IoStatusBlock = 0;
  v29 = 0;
  v36 = 0;
  memset(&DriverContext, 0, sizeof(DriverContext));
  v6 = (UNICODE_STRING *)ExAllocateFromNPagedLookasideList(&stru_18003F340);
  v7 = v6;
  if ( v6 )
  {
    *(_DWORD *)&v6[1].Length = 0;
    LODWORD(v6[1].Buffer) = 0;
    *(_DWORD *)(&v6[1].MaximumLength + 1) = 254;
    *v6 = 0;
    v6->MaximumLength = 254;
    v6->Buffer = (wchar_t *)&v6[1].Buffer + 2;
    v8 = 0;
    v9 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 64) + 88LL);
    if ( (_WORD)v9 )
    {
      v10 = *(_QWORD *)(a1 + 24);
      v33 = (_QWORD *)(a1 + 32);
      if ( v10 )
      {
        v11 = (unsigned __int16 *)(v10 + 112);
      }
      else
      {
        v11 = (unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 8LL);
        v33 = (_QWORD *)(a1 + 32);
      }
      v12 = v9 + 2 + *v11;
      if ( v12 > 0xFFFE )
      {
        LODWORD(ECP) = -1073741562;
      }
      else if ( v12 > (unsigned __int64)*(unsigned int *)(&v7[1].MaximumLength + 1) - 2 )
      {
        LODWORD(ECP) = FltpReallocNameControl(v7, v12 + 514, 0, 0);
      }
      if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 2854, 0) >= 0 )
      {
        v13 = *(const UNICODE_STRING **)(a1 + 24);
        if ( v13 )
          v14 = v13 + 7;
        else
          v14 = (const UNICODE_STRING *)(*v33 + 8LL);
        RtlCopyUnicodeString(v7, v14);
        if ( **(_WORD **)(*(_QWORD *)(a1 + 64) + 96LL) != 92 )
          RtlAppendUnicodeToString(v7, L"\\");
        RtlAppendUnicodeStringToString(v7, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 64) + 88LL));
        v15 = *(_QWORD *)(a1 + 8);
        Silo = 1;
        memset(&DriverContext, 0, sizeof(DriverContext));
        DriverContext.Size = 40;
        DriverContext.DeviceObjectHint = *(PVOID *)(v15 + 64);
        ECP = (unsigned int)TargetedIOCtrlGenerateECP(
                              (PVOID *)&v36,
                              0,
                              1,
                              *(_QWORD *)(v15 + 104),
                              *(PVOID *)(*(_QWORD *)(a1 + 16) + 72LL),
                              0,
                              0,
                              &DriverContext.ExtraCreateParameter,
                              0);
        v16 = FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 2894, 0);
        v5 = v36;
        if ( v16 >= 0 )
        {
          v17 = *(_QWORD *)(a1 + 64);
          v8 = (v36[6] & 8) != 0;
          DriverContext.TxnParameters = *(PTXN_PARAMETER_BLOCK *)(a1 + 72);
          Silo = IoGetSilo(v17);
          if ( !Silo )
            Silo = PsGetHostSilo();
          v18 = *(_QWORD *)(a1 + 80);
          v19 = ~(2 * *(_DWORD *)(a1 + 40));
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.ObjectName = v7;
          ObjectAttributes.Attributes = v19 & 0x40 | 0x200;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( v18
            && (v20 = *(_QWORD *)(v18 + 16),
                (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v20 + 4) + 22)) & 2) != 0)
            && (*(_BYTE *)(v20 + 6) & 8) != 0 )
          {
            Options = 2056;
          }
          else
          {
            Options = 2048;
          }
          LODWORD(ECP) = IoCreateFileEx(
                           &FileHandle,
                           0x100000u,
                           &ObjectAttributes,
                           &IoStatusBlock,
                           0,
                           0,
                           7u,
                           1u,
                           0x202000u,
                           0,
                           0,
                           CreateFileTypeNone,
                           0,
                           Options,
                           &DriverContext);
          if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 2957, 3221225485LL) < 0 )
          {
            if ( (_DWORD)ECP == -2147483603 && IoStatusBlock.Information )
              ExFreePoolWithTag((PVOID)IoStatusBlock.Information, 0);
          }
          else
          {
            ECP = (unsigned int)ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
            if ( (int)FltpDbgStatus(ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 2992, 0) < 0 )
            {
              Object = 0;
            }
            else
            {
              v22 = *(_QWORD *)(a1 + 80);
              if ( *(_QWORD *)(v22 - 72) )
              {
                LOBYTE(v36) = 0;
                FltpIsOpenByObjectId(a1, &v36);
                if ( (_BYTE)v36 )
                  goto LABEL_47;
                StreamListCtrl = FltpGetStreamListCtrl(*(PVOID *)(a1 + 8));
                v24 = FltpDbgStatus(StreamListCtrl, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 3047, 3221225659LL);
                v3 = v38;
                if ( v24 >= 0 && (v38[16] & 0x400) == 0 && ((v38[16] & 0x300) == 0 || (v38[16] & 0x30) == 0) )
                {
                  v27 = *(_QWORD *)(*(_QWORD *)(v22 - 72) + 16LL);
                  if ( v27 )
                    v28 = 1;
                  else
                    v28 = 3;
                  StreamListCtrl = FltpSetStreamListStandardInformationFlags(
                                     *(_QWORD *)(a1 + 8),
                                     v28,
                                     v27,
                                     (_DWORD)Object,
                                     (__int64)v38);
                }
                if ( (int)FltpDbgStatus(StreamListCtrl, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 3098, 0) < 0
                  || (v3[16] & 0x100) != 0 )
                {
LABEL_47:
                  **(_DWORD **)(v22 - 72) |= 4u;
                }
              }
              LODWORD(ECP) = FltpAllocateInitializeNameGenerationContext(
                               &v29,
                               *(_QWORD *)(a1 + 16),
                               Object,
                               0,
                               *(_DWORD *)(a1 + 108),
                               *(_QWORD *)(a1 + 112),
                               0,
                               0,
                               0);
              v25 = FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 3122, 3221225626LL);
              v4 = v29;
              if ( v25 >= 0 )
                LODWORD(ECP) = FltpGetFileName(v29);
            }
          }
        }
      }
    }
    else
    {
      LODWORD(ECP) = -1073741773;
    }
    FltpCleanupNameControl(v7);
    ExFreeToNPagedLookasideList(&stru_18003F340, v7);
    if ( v5 )
    {
      if ( (int)FltpDbgStatus((unsigned int)ECP, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 3148, 0) < 0 )
        v5 = 0;
      CleanupTargetedIo(v5, &DriverContext.ExtraCreateParameter, v8);
    }
    if ( v3 )
      FltpReleaseStreamListCtrl(v3);
  }
  else
  {
    LODWORD(ECP) = -1073741670;
  }
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v4 )
    FltpFreeNameGenerationContext(v4);
  return (unsigned int)ECP;
}

```

## disassembly

```asm
0x18005b920  mov     rax, rsp
0x18005b923  push    rbp
0x18005b924  push    rsi
0x18005b925  push    r12
0x18005b927  lea     rbp, [rax-38h]
0x18005b92b  sub     rsp, 120h
0x18005b932  xor     r12d, r12d
0x18005b935  mov     [rax+8], rbx
0x18005b939  xorps   xmm0, xmm0
0x18005b93c  mov     [rax-20h], rdi
0x18005b940  mov     [rax-30h], r14
0x18005b944  mov     rdi, rcx
0x18005b947  mov     [rax-38h], r15
0x18005b94b  lea     rcx, stru_18003F340; Lookaside
0x18005b952  xor     eax, eax
0x18005b954  mov     [rbp+30h+FileHandle], r12
0x18005b958  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x18005b95c  mov     word ptr [rbp+30h+var_80], ax
0x18005b960  mov     r14d, r12d
0x18005b963  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x18005b967  mov     [rbp+30h+Object], r12
0x18005b96b  mov     esi, r12d
0x18005b96e  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x18005b972  mov     [rbp+30h+arg_18], r12
0x18005b976  mov     r15d, r12d
0x18005b979  movups  xmmword ptr [rbp-10h], xmm0
0x18005b97d  mov     [rbp+30h+var_B0], r12
0x18005b981  mov     [rbp+30h+arg_8], r12
0x18005b985  movups  xmmword ptr [rbp+30h+DriverContext.Size], xmm0
0x18005b989  movups  xmmword ptr [rbp+30h+DriverContext.DeviceObjectHint], xmm0
0x18005b98d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18005b994  nop     dword ptr [rax+rax+00h]
0x18005b999  mov     rbx, rax
0x18005b99c  test    rax, rax
0x18005b99f  jz      loc_18005BF61
0x18005b9a5  mov     [rax+10h], r12d
0x18005b9a9  xorps   xmm0, xmm0
0x18005b9ac  mov     [rax+18h], r12d
0x18005b9b0  mov     eax, 0FEh
0x18005b9b5  mov     [rbx+14h], eax
0x18005b9b8  movups  xmmword ptr [rbx], xmm0
0x18005b9bb  mov     [rbx+2], ax
0x18005b9bf  lea     rax, [rbx+1Ch]
0x18005b9c3  mov     [rbx+8], rax
0x18005b9c7  mov     rax, [rdi+40h]
0x18005b9cb  mov     [rsp+130h+var_20], r13
0x18005b9d3  xor     r13b, r13b
0x18005b9d6  movzx   edx, word ptr [rax+58h]
0x18005b9da  test    dx, dx
0x18005b9dd  jz      loc_18005BF6C
0x18005b9e3  mov     rax, [rdi+18h]
0x18005b9e7  lea     rcx, [rdi+20h]
0x18005b9eb  mov     [rbp+30h+var_78], rcx
0x18005b9ef  test    rax, rax
0x18005b9f2  jz      loc_18005BE51
0x18005b9f8  add     rax, 70h ; 'p'
0x18005b9fc  mov     ecx, edx
0x18005b9fe  movzx   edx, word ptr [rax]
0x18005ba01  add     ecx, 2
0x18005ba04  add     edx, ecx
0x18005ba06  cmp     edx, 0FFFEh
0x18005ba0c  ja      loc_18005BF05
0x18005ba12  mov     ecx, [rbx+14h]
0x18005ba15  sub     rcx, 2
0x18005ba19  mov     eax, edx
0x18005ba1b  cmp     rax, rcx
0x18005ba1e  ja      loc_18005BE9E
0x18005ba24  mov     r8d, 0B26h
0x18005ba2a  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005ba31  xor     r9d, r9d
0x18005ba34  mov     ecx, r12d
0x18005ba37  call    FltpDbgStatus
0x18005ba3c  test    eax, eax
0x18005ba3e  js      loc_18005BDAC
0x18005ba44  mov     rax, [rdi+18h]
0x18005ba48  test    rax, rax
0x18005ba4b  jz      loc_18005BE61
0x18005ba51  lea     rdx, [rax+70h]; SourceString
0x18005ba55  mov     rcx, rbx; DestinationString
0x18005ba58  call    cs:__imp_RtlCopyUnicodeString
0x18005ba5f  nop     dword ptr [rax+rax+00h]
0x18005ba64  mov     rax, [rdi+40h]
0x18005ba68  mov     rcx, [rax+60h]
0x18005ba6c  cmp     word ptr [rcx], 5Ch ; '\'
0x18005ba70  jz      short loc_18005BA88
0x18005ba72  lea     rdx, Source; "\\"
0x18005ba79  mov     rcx, rbx; Destination
0x18005ba7c  call    cs:__imp_RtlAppendUnicodeToString
0x18005ba83  nop     dword ptr [rax+rax+00h]
0x18005ba88  mov     rdx, [rdi+40h]
0x18005ba8c  mov     rcx, rbx; Destination
0x18005ba8f  add     rdx, 58h ; 'X'; Source
0x18005ba93  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005ba9a  nop     dword ptr [rax+rax+00h]
0x18005ba9f  mov     r9, [rdi+8]
0x18005baa3  lea     rcx, [rbp+30h+DriverContext.ExtraCreateParameter]
0x18005baa7  mov     [rbp+30h+var_80], 1
0x18005baaf  xor     edx, edx; int
0x18005bab1  mov     qword ptr [rsp+130h+CreateOptions], rdx; __int64
0x18005bab6  xorps   xmm0, xmm0
0x18005bab9  movups  xmmword ptr [rbp+30h+DriverContext.Size], xmm0
0x18005babd  mov     qword ptr [rsp+130h+Disposition], rcx; EcpList
0x18005bac2  mov     eax, 28h ; '('
0x18005bac7  movups  xmmword ptr [rbp+30h+DriverContext.DeviceObjectHint], xmm0
0x18005bacb  mov     [rbp+30h+DriverContext.Size], ax
0x18005bacf  lea     rcx, [rbp+30h+arg_8]; int
0x18005bad3  mov     rax, [r9+40h]
0x18005bad7  mov     r8d, 1; int
0x18005badd  mov     [rbp+30h+DriverContext.DeviceObjectHint], rax
0x18005bae1  mov     rax, [rdi+10h]
0x18005bae5  mov     r9, [r9+68h]; int
0x18005bae9  mov     qword ptr [rsp+130h+ShareAccess], rdx; PVOID
0x18005baee  mov     qword ptr [rsp+130h+FileAttributes], rdx; __int64
0x18005baf3  mov     rax, [rax+48h]
0x18005baf7  mov     [rsp+130h+AllocationSize], rax; FltObject
0x18005bafc  call    TargetedIOCtrlGenerateECP
0x18005bb01  mov     r8d, 0B4Eh
0x18005bb07  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005bb0e  xor     r9d, r9d
0x18005bb11  mov     ecx, eax
0x18005bb13  mov     r12d, eax
0x18005bb16  call    FltpDbgStatus
0x18005bb1b  mov     r15, [rbp+30h+arg_8]
0x18005bb1f  test    eax, eax
0x18005bb21  js      loc_18005BDAC
0x18005bb27  movzx   r13d, byte ptr [r15+6]
0x18005bb2c  mov     rax, [rdi+48h]
0x18005bb30  mov     rcx, [rdi+40h]
0x18005bb34  shr     r13b, 3
0x18005bb38  and     r13b, 1
0x18005bb3c  mov     [rbp+30h+DriverContext.TxnParameters], rax
0x18005bb40  call    cs:__imp_IoGetSilo
0x18005bb47  nop     dword ptr [rax+rax+00h]
0x18005bb4c  mov     [rbp+30h+var_80], rax
0x18005bb50  test    rax, rax
0x18005bb53  jnz     short loc_18005BB65
0x18005bb55  call    cs:__imp_PsGetHostSilo
0x18005bb5c  nop     dword ptr [rax+rax+00h]
0x18005bb61  mov     [rbp+30h+var_80], rax
0x18005bb65  mov     eax, [rdi+28h]
0x18005bb68  xor     r8d, r8d
0x18005bb6b  mov     rcx, [rdi+50h]
0x18005bb6f  add     eax, eax
0x18005bb71  not     eax
0x18005bb73  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x18005bb7a  and     eax, 40h
0x18005bb7d  mov     [rbp+30h+ObjectAttributes.RootDirectory], r8
0x18005bb81  bts     eax, 9
0x18005bb85  mov     [rbp+30h+ObjectAttributes.ObjectName], rbx
0x18005bb89  mov     [rbp+30h+ObjectAttributes.Attributes], eax
0x18005bb8c  xorps   xmm0, xmm0
0x18005bb8f  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005bb94  test    rcx, rcx
0x18005bb97  jz      short loc_18005BBBD
0x18005bb99  mov     rcx, [rcx+10h]
0x18005bb9d  lea     rdx, FltpOperationFlags
0x18005bba4  movzx   eax, byte ptr [rcx+4]
0x18005bba8  add     al, 16h
0x18005bbaa  movzx   eax, al
0x18005bbad  test    byte ptr [rax+rdx], 2
0x18005bbb1  jz      short loc_18005BBBD
0x18005bbb3  test    byte ptr [rcx+6], 8
0x18005bbb7  jnz     loc_18005BEFB
0x18005bbbd  mov     eax, 800h
0x18005bbc2  lea     rcx, [rbp+30h+DriverContext]
0x18005bbc6  mov     edx, 100000h; DesiredAccess
0x18005bbcb  mov     [rsp+70h], rcx; DriverContext
0x18005bbd0  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x18005bbd4  mov     [rsp+130h+Options], eax; Options
0x18005bbd8  lea     rcx, [rbp+30h+FileHandle]; FileHandle
0x18005bbdc  mov     [rsp+130h+InternalParameters], r8; InternalParameters
0x18005bbe1  mov     [rsp+130h+CreateFileType], r8d; CreateFileType
0x18005bbe6  mov     [rsp+130h+EaLength], r8d; EaLength
0x18005bbeb  mov     [rsp+130h+EaBuffer], r8; EaBuffer
0x18005bbf0  mov     [rsp+130h+CreateOptions], 202000h; CreateOptions
0x18005bbf8  mov     [rsp+130h+Disposition], 1; Disposition
0x18005bc00  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x18005bc08  mov     [rsp+130h+FileAttributes], r8d; FileAttributes
0x18005bc0d  mov     [rsp+130h+AllocationSize], r8; AllocationSize
0x18005bc12  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x18005bc16  call    cs:__imp_IoCreateFileEx
0x18005bc1d  nop     dword ptr [rax+rax+00h]
0x18005bc22  mov     r8d, 0B8Dh
0x18005bc28  mov     qword ptr [rsp+130h+FileAttributes], rsi
0x18005bc2d  mov     ecx, eax
0x18005bc2f  mov     dword ptr [rsp+130h+AllocationSize], 0C0000056h
0x18005bc37  mov     r9d, 0C000000Dh
0x18005bc3d  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005bc44  mov     r12d, eax
0x18005bc47  call    FltpDbgStatus
0x18005bc4c  test    eax, eax
0x18005bc4e  js      loc_18005BE71
0x18005bc54  mov     r8, cs:__imp_IoFileObjectType
0x18005bc5b  lea     rax, [rbp+30h+Object]
0x18005bc5f  mov     rcx, [rbp+30h+FileHandle]; Handle
0x18005bc63  xor     r9d, r9d; AccessMode
0x18005bc66  mov     qword ptr [rsp+130h+FileAttributes], rsi; HandleInformation
0x18005bc6b  xor     edx, edx; DesiredAccess
0x18005bc6d  mov     [rsp+130h+AllocationSize], rax; Object
0x18005bc72  mov     r8, [r8]; ObjectType
0x18005bc75  call    cs:__imp_ObReferenceObjectByHandle
0x18005bc7c  nop     dword ptr [rax+rax+00h]
0x18005bc81  mov     r8d, 0BB0h
0x18005bc87  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005bc8e  mov     ecx, eax
0x18005bc90  xor     r9d, r9d
0x18005bc93  mov     r12d, eax
0x18005bc96  call    FltpDbgStatus
0x18005bc9b  test    eax, eax
0x18005bc9d  js      loc_18005BF77
0x18005bca3  mov     rsi, [rdi+50h]
0x18005bca7  cmp     [rsi-48h], r14
0x18005bcab  jz      loc_18005BD3B
0x18005bcb1  lea     rdx, [rbp+30h+arg_8]
0x18005bcb5  mov     byte ptr [rbp+30h+arg_8], r14b
0x18005bcb9  mov     rcx, rdi
0x18005bcbc  call    FltpIsOpenByObjectId
0x18005bcc1  cmp     byte ptr [rbp+30h+arg_8], r14b
0x18005bcc5  jnz     loc_18005BEEF
0x18005bccb  mov     rdx, [rbp+30h+Object]
0x18005bccf  lea     r9, [rbp+30h+arg_18]
0x18005bcd3  mov     rcx, [rdi+8]; OwnerId
0x18005bcd7  mov     r8b, 1
0x18005bcda  call    FltpGetStreamListCtrl
0x18005bcdf  mov     r8d, 0BE7h
0x18005bce5  mov     [rsp+130h+AllocationSize], r14
0x18005bcea  mov     r9d, 0C00000BBh
0x18005bcf0  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005bcf7  mov     ecx, eax
0x18005bcf9  mov     r12d, eax
0x18005bcfc  call    FltpDbgStatus
0x18005bd01  mov     r14, [rbp+30h+arg_18]
0x18005bd05  test    eax, eax
0x18005bd07  jns     loc_18005BF10
0x18005bd0d  mov     r8d, 0C1Ah
0x18005bd13  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005bd1a  xor     r9d, r9d
0x18005bd1d  mov     ecx, r12d
0x18005bd20  call    FltpDbgStatus
0x18005bd25  test    eax, eax
0x18005bd27  js      loc_18005BEEF
0x18005bd2d  test    dword ptr [r14+40h], 100h
0x18005bd35  jnz     loc_18005BEEF
0x18005bd3b  mov     rax, [rdi+70h]
0x18005bd3f  lea     rcx, [rbp+30h+var_B0]
0x18005bd43  mov     r8, [rbp+30h+Object]
0x18005bd47  xor     esi, esi
0x18005bd49  mov     rdx, [rdi+10h]
0x18005bd4d  xor     r9d, r9d
0x18005bd50  mov     [rsp+130h+EaLength], 1
0x18005bd58  mov     [rsp+130h+CreateOptions], esi
0x18005bd5c  mov     qword ptr [rsp+130h+Disposition], rsi
0x18005bd61  mov     qword ptr [rsp+130h+ShareAccess], rsi
0x18005bd66  mov     qword ptr [rsp+130h+FileAttributes], rax
0x18005bd6b  mov     eax, [rdi+6Ch]
0x18005bd6e  mov     dword ptr [rsp+130h+AllocationSize], eax
0x18005bd72  call    FltpAllocateInitializeNameGenerationContext
0x18005bd77  mov     r8d, 0C32h
0x18005bd7d  mov     [rsp+130h+AllocationSize], rsi
0x18005bd82  mov     r9d, 0C000009Ah
0x18005bd88  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005bd8f  mov     ecx, eax
0x18005bd91  mov     r12d, eax
0x18005bd94  call    FltpDbgStatus
0x18005bd99  mov     rsi, [rbp+30h+var_B0]
0x18005bd9d  test    eax, eax
0x18005bd9f  js      short loc_18005BDAC
0x18005bda1  mov     rcx, rsi
0x18005bda4  call    FltpGetFileName
0x18005bda9  mov     r12d, eax
0x18005bdac  mov     rcx, rbx
0x18005bdaf  call    FltpCleanupNameControl
0x18005bdb4  mov     rdx, rbx; Entry
0x18005bdb7  lea     rcx, stru_18003F340; Lookaside
0x18005bdbe  call    cs:__imp_ExFreeToNPagedLookasideList
0x18005bdc5  nop     dword ptr [rax+rax+00h]
0x18005bdca  test    r15, r15
0x18005bdcd  jnz     loc_18005BEBA
0x18005bdd3  mov     r13, [rsp+130h+var_20]
0x18005bddb  test    r14, r14
0x18005bdde  jnz     short loc_18005BE47
0x18005bde0  mov     rcx, [rbp+30h+Object]; Object
0x18005bde4  mov     r15, [rsp+130h+var_30]
0x18005bdec  mov     r14, [rsp+130h+var_28]
0x18005bdf4  mov     rdi, [rsp+118h]
0x18005bdfc  mov     rbx, [rsp+130h+arg_0]
0x18005be04  test    rcx, rcx
0x18005be07  jz      short loc_18005BE15
0x18005be09  call    cs:__imp_ObfDereferenceObject
0x18005be10  nop     dword ptr [rax+rax+00h]
0x18005be15  mov     rcx, [rbp+30h+FileHandle]; Handle
0x18005be19  test    rcx, rcx
0x18005be1c  jz      short loc_18005BE2A
0x18005be1e  call    cs:__imp_ZwClose
0x18005be25  nop     dword ptr [rax+rax+00h]
0x18005be2a  test    rsi, rsi
0x18005be2d  jz      short loc_18005BE37
0x18005be2f  mov     rcx, rsi; Entry
0x18005be32  call    FltpFreeNameGenerationContext
0x18005be37  mov     eax, r12d
  ... truncated ...
```
