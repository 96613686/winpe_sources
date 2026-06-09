# BfCreateFile

- ea: `0x140002904`
- end: `0x140002d1f`
- name: `BfCreateFile`
- size: `1051`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400157a0`

## callees

- `0x140002904`
- `0x140004b90`
- `0x140004fc0`
- `0x140011eb0`
- `0x140022e5c`

## import_xrefs

- `ntoskrnl!PsRevertToSelf` at `0x140002c12`
- `ntoskrnl!PsRevertToSelf` at `0x140002c12`
- `ntoskrnl!IoIsFileObjectIgnoringSharing` at `0x140002c8b`
- `ntoskrnl!IoIsFileObjectIgnoringSharing` at `0x140002c8b`
- `ntoskrnl!SeImpersonateClientEx` at `0x140002ad5`
- `ntoskrnl!SeImpersonateClientEx` at `0x140002ad5`
- `ntoskrnl!PsGetParentSilo` at `0x140002b4c`
- `ntoskrnl!PsGetParentSilo` at `0x140002b4c`
- `ntoskrnl!PsImpersonateClient` at `0x140002ccb`
- `ntoskrnl!PsImpersonateClient` at `0x140002ccb`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140002c34`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140002c34`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140002b21`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140002b21`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x140002ab6`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x140002ab6`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140002cda`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140002cda`
- `ntoskrnl!IoGetSilo` at `0x140002b34`
- `ntoskrnl!IoGetSilo` at `0x140002b34`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140002a77`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140002a77`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140002b08`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140002b08`
- `FLTMGR!FltCreateFileEx2` at `0x140002be1`
- `FLTMGR!FltCreateFileEx2` at `0x140002be1`

## pseudocode

```c
__int64 __fastcall BfCreateFile(
        struct _UNICODE_STRING *a1,
        struct _FLT_CALLBACK_DATA *a2,
        __int64 a3,
        struct _FLT_INSTANCE *a4,
        char a5,
        char a6,
        void **a7,
        PFILE_OBJECT *a8)
{
  KPROCESSOR_MODE RequestorMode; // r9
  char v12; // r12
  int v13; // r8d
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  ULONG v15; // ecx
  char OperationFlags; // al
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  ULONG Options; // esi
  ULONG Flags; // edi
  PFILE_OBJECT *v20; // r14
  char v21; // si
  PACCESS_TOKEN v22; // rax
  PFLT_IO_PARAMETER_BLOCK v23; // rcx
  struct _SECURITY_SUBJECT_CONTEXT *v24; // rcx
  NTSTATUS EcpListFromCallbackData; // ebx
  __int64 v26; // r8
  __int64 v27; // r9
  struct _TXN_PARAMETER_BLOCK *TransactionParameterBlock; // rax
  PFILE_OBJECT v29; // rcx
  __int64 Silo; // rax
  PACCESS_TOKEN v31; // rdi
  int DesiredAccess; // [rsp+20h] [rbp-E0h]
  char v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+81h] [rbp-7Fh] BYREF
  USHORT ShareAccess; // [rsp+86h] [rbp-7Ah]
  USHORT FileAttributes; // [rsp+88h] [rbp-78h]
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+8Ch] [rbp-74h] BYREF
  ULONG v39; // [rsp+90h] [rbp-70h]
  ULONG EaLength; // [rsp+94h] [rbp-6Ch]
  ACCESS_MASK v41; // [rsp+98h] [rbp-68h]
  PACCESS_TOKEN Token; // [rsp+A0h] [rbp-60h]
  struct _IO_DRIVER_CREATE_CONTEXT EcpList; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-38h]
  PVOID EaBuffer; // [rsp+D0h] [rbp-30h]
  PFILE_OBJECT *FileObject; // [rsp+D8h] [rbp-28h]
  PHANDLE FileHandle; // [rsp+E0h] [rbp-20h]
  PFLT_INSTANCE Instance; // [rsp+E8h] [rbp-18h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-10h] BYREF
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+120h] [rbp+20h] BYREF
  _SECURITY_CLIENT_CONTEXT ClientContext; // [rsp+130h] [rbp+30h] BYREF

  FileHandle = a7;
  FileObject = a8;
  Instance = a4;
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&ClientContext, 0, 0x44u);
  RequestorMode = a2->RequestorMode;
  memset(&EcpList, 0, sizeof(EcpList));
  v12 = 0;
  ImpersonationLevel = SecurityImpersonation;
  v35 = 0;
  v34 = 0;
  EcpList.Size = 40;
  v44 = 1;
  Token = 0;
  if ( RequestorMode == 1 || (v13 = 512, !RequestorMode) && (a2->Iopb->OperationFlags & 1) != 0 )
    v13 = 1536;
  Iopb = a2->Iopb;
  v15 = v13 | 0x40;
  OperationFlags = Iopb->OperationFlags;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a1;
  if ( OperationFlags < 0 )
    v15 = v13;
  ObjectAttributes.Attributes = v15;
  ObjectAttributes.SecurityDescriptor = *(PVOID *)(*(_QWORD *)(Iopb->Parameters.WMI.ProviderId + 8) + 64LL);
  ObjectAttributes.SecurityQualityOfService = 0;
  SecurityContext = Iopb->Parameters.Create.SecurityContext;
  Options = Iopb->Parameters.Create.Options;
  v39 = Options;
  v41 = SecurityContext->DesiredAccess;
  FileAttributes = Iopb->Parameters.Create.FileAttributes;
  ShareAccess = Iopb->Parameters.Create.ShareAccess;
  EaBuffer = Iopb->Parameters.Create.EaBuffer;
  EaLength = Iopb->Parameters.Create.EaLength;
  Flags = Iopb->OperationFlags | 1;
  v20 = (PFILE_OBJECT *)(a3 + 32);
  if ( RequestorMode != 1 )
    Flags = Iopb->OperationFlags;
  if ( !RequestorMode && IoIsFileObjectIgnoringSharing(*v20) )
    Flags |= 0x800u;
  if ( a2->RequestorMode == 1 )
  {
    v21 = 0;
    v22 = PsReferenceImpersonationToken(
            KeGetCurrentThread(),
            (PBOOLEAN)&v35 + 3,
            (PBOOLEAN)&v35 + 2,
            &ImpersonationLevel);
    v23 = a2->Iopb;
    Token = v22;
    v24 = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(v23->Parameters.WMI.ProviderId + 8) + 32LL);
    ClientSecurityQos.Length = 12;
    ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
    *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 1;
    EcpListFromCallbackData = SeCreateClientSecurityFromSubjectContext(v24, &ClientSecurityQos, 0, &ClientContext);
    if ( EcpListFromCallbackData < 0 )
      goto LABEL_20;
    v12 = 1;
    EcpListFromCallbackData = SeImpersonateClientEx(&ClientContext, 0);
    if ( EcpListFromCallbackData < 0 )
      goto LABEL_20;
    Options = v39;
  }
  if ( a6 )
    Flags |= 8u;
  EcpListFromCallbackData = FltGetEcpListFromCallbackData(*(PFLT_FILTER *)(a3 + 8), a2, &EcpList.ExtraCreateParameter);
  if ( EcpListFromCallbackData >= 0 )
  {
    TransactionParameterBlock = IoGetTransactionParameterBlock(*v20);
    v29 = *v20;
    EcpList.TxnParameters = TransactionParameterBlock;
    Silo = IoGetSilo(v29);
    if ( (a5 & 4) == 0 )
      Silo = PsGetParentSilo(Silo);
    v44 = Silo;
    if ( (a5 & 0x20) == 0
      || (EcpListFromCallbackData = BfAddCloudFileECPs(a2, (__int64)&v35, (__int64)&v34), EcpListFromCallbackData >= 0) )
    {
      EcpListFromCallbackData = FltCreateFileEx2(
                                  *(PFLT_FILTER *)(a3 + 8),
                                  Instance,
                                  FileHandle,
                                  FileObject,
                                  v41,
                                  &ObjectAttributes,
                                  &a2->IoStatus,
                                  &a2->Iopb->Parameters.Create.AllocationSize,
                                  FileAttributes,
                                  ShareAccess,
                                  HIBYTE(Options),
                                  Options & 0xFFFFFF,
                                  EaBuffer,
                                  EaLength,
                                  Flags,
                                  &EcpList);
    }
  }
  v21 = v12;
LABEL_20:
  LOBYTE(v26) = BYTE1(v35);
  LOBYTE(v27) = v35;
  LOBYTE(DesiredAccess) = v34;
  BfRemoveCloudFileECPs(a3, EcpList.ExtraCreateParameter, v26, v27, DesiredAccess);
  if ( v21 )
    PsRevertToSelf();
  v31 = Token;
  if ( Token )
  {
    if ( v21 )
      PsImpersonateClient(KeGetCurrentThread(), Token, HIBYTE(v35), BYTE2(v35), ImpersonationLevel);
    PsDereferenceImpersonationToken(v31);
  }
  if ( v12 )
    SeDeleteClientSecurity(&ClientContext);
  return (unsigned int)EcpListFromCallbackData;
}

```

## disassembly

```asm
0x140002904  push    rbp
0x140002906  push    rbx
0x140002907  push    rsi
0x140002908  push    rdi
0x140002909  push    r12
0x14000290b  push    r13
0x14000290d  push    r14
0x14000290f  push    r15
0x140002911  lea     rbp, [rsp-98h]
0x140002919  sub     rsp, 198h
0x140002920  mov     rax, cs:__security_cookie
0x140002927  xor     rax, rsp
0x14000292a  mov     [rbp+0D0h+var_50], rax
0x140002931  mov     rax, [rbp+0D0h+arg_30]
0x140002938  xorps   xmm0, xmm0
0x14000293b  mov     [rbp+0D0h+FileHandle], rax
0x14000293f  mov     r13, r8
0x140002942  mov     rax, [rbp+0D0h+arg_38]
0x140002949  mov     r15, rdx
0x14000294c  mov     [rbp+0D0h+FileObject], rax
0x140002950  mov     rbx, rcx
0x140002953  xor     eax, eax
0x140002955  mov     [rbp+0D0h+Instance], r9
0x140002959  movups  xmmword ptr [rbp+0D0h+var_E0.ObjectName], xmm0
0x14000295d  xor     edx, edx; Val
0x14000295f  mov     qword ptr [rbp+0D0h+ClientSecurityQos.Length], rax
0x140002963  lea     rcx, [rbp+0D0h+ClientContext]; void *
0x140002967  mov     dword ptr [rbp+0D0h+ClientSecurityQos.ContextTrackingMode], eax
0x14000296a  lea     r8d, [rax+44h]; Size
0x14000296e  mov     dword ptr [rbp+0D0h+ClientContext+0Ch], eax
0x140002971  movups  xmmword ptr [rbp+0D0h+var_E0.Length], xmm0
0x140002975  movups  xmmword ptr [rbp+0D0h+var_E0+1Ch], xmm0
0x140002979  call    memset
0x14000297e  mov     r9b, [r15+50h]
0x140002982  xor     r10d, r10d
0x140002985  xorps   xmm0, xmm0
0x140002988  mov     byte ptr [rbp+0D0h+var_150+4], r10b
0x14000298c  movups  xmmword ptr [rbp+0D0h+EcpList], xmm0
0x140002990  mov     r12b, r10b
0x140002993  mov     byte ptr [rbp+0D0h+var_150+3], r10b
0x140002997  lea     r14d, [r10+1]
0x14000299b  mov     [rbp+0D0h+ImpersonationLevel], 2
0x1400029a2  mov     byte ptr [rbp+0D0h+var_150+2], r10b
0x1400029a6  lea     eax, [r10+28h]
0x1400029aa  mov     byte ptr [rbp+0D0h+var_150+1], r10b
0x1400029ae  mov     byte ptr [rbp+0D0h+var_150], r10b
0x1400029b2  mov     word ptr [rbp+0D0h+EcpList], ax
0x1400029b6  mov     [rbp+0D0h+var_108], r14
0x1400029ba  mov     [rbp+0D0h+Token], r10
0x1400029be  movups  [rbp+0D0h+var_118], xmm0
0x1400029c2  cmp     r9b, r14b
0x1400029c5  jnz     loc_140002C66
0x1400029cb  mov     r8d, 600h
0x1400029d1  mov     rdx, [r15+10h]
0x1400029d5  mov     ecx, r8d
0x1400029d8  or      ecx, 40h
0x1400029db  mov     al, [rdx+6]
0x1400029de  test    al, al
0x1400029e0  mov     [rbp+0D0h+var_E0.Length], 30h ; '0'
0x1400029e7  mov     [rbp+0D0h+var_E0.RootDirectory], r10
0x1400029eb  mov     [rbp+0D0h+var_E0.ObjectName], rbx
0x1400029ef  cmovs   ecx, r8d
0x1400029f3  mov     [rbp+0D0h+var_E0.Attributes], ecx
0x1400029f6  mov     rax, [rdx+18h]
0x1400029fa  mov     rcx, [rax+8]
0x1400029fe  mov     rax, [rcx+40h]
0x140002a02  mov     [rbp+0D0h+var_E0.SecurityDescriptor], rax
0x140002a06  mov     [rbp+0D0h+var_E0.SecurityQualityOfService], r10
0x140002a0a  mov     rax, [rdx+18h]
0x140002a0e  mov     esi, [rdx+20h]
0x140002a11  mov     [rbp+0D0h+var_140], esi
0x140002a14  mov     eax, [rax+10h]
0x140002a17  mov     [rbp+0D0h+var_138], eax
0x140002a1a  movzx   eax, word ptr [rdx+28h]
0x140002a1e  mov     [rbp+0D0h+var_148], ax
0x140002a22  movzx   eax, word ptr [rdx+2Ah]
0x140002a26  mov     word ptr [rbp+0D0h+var_150+6], ax
0x140002a2a  mov     rax, [rdx+38h]
0x140002a2e  mov     [rbp+0D0h+var_100], rax
0x140002a32  mov     eax, [rdx+30h]
0x140002a35  mov     [rbp+0D0h+var_13C], eax
0x140002a38  movzx   eax, byte ptr [rdx+6]
0x140002a3c  mov     edi, eax
0x140002a3e  or      edi, r14d
0x140002a41  cmp     r9b, r14b
0x140002a44  lea     r14, [r13+20h]
0x140002a48  cmovnz  edi, eax
0x140002a4b  test    r9b, r9b
0x140002a4e  jz      loc_140002C88
0x140002a54  cmp     byte ptr [r15+50h], 1
0x140002a59  jnz     loc_140002AF1
0x140002a5f  mov     rcx, gs:188h; Thread
0x140002a68  lea     r9, [rbp+0D0h+ImpersonationLevel]; ImpersonationLevel
0x140002a6c  lea     r8, [rbp+0D0h+var_150+3]; EffectiveOnly
0x140002a70  mov     sil, r10b
0x140002a73  lea     rdx, [rbp+0D0h+var_150+4]; CopyOnOpen
0x140002a77  call    cs:__imp_PsReferenceImpersonationToken
0x140002a7e  nop     dword ptr [rax+rax+00h]
0x140002a83  mov     rcx, [r15+10h]
0x140002a87  lea     r9, [rbp+0D0h+ClientContext]; ClientContext
0x140002a8b  xor     r8d, r8d; ServerIsRemote
0x140002a8e  mov     [rbp+0D0h+Token], rax
0x140002a92  mov     rdx, [rcx+18h]
0x140002a96  mov     rcx, [rdx+8]
0x140002a9a  lea     rdx, [rbp+0D0h+ClientSecurityQos]; ClientSecurityQos
0x140002a9e  add     rcx, 20h ; ' '; SubjectContext
0x140002aa2  mov     [rbp+0D0h+ClientSecurityQos.Length], 0Ch
0x140002aa9  mov     [rbp+0D0h+ClientSecurityQos.ImpersonationLevel], 2
0x140002ab0  mov     word ptr [rbp+0D0h+ClientSecurityQos.ContextTrackingMode], 1
0x140002ab6  call    cs:__imp_SeCreateClientSecurityFromSubjectContext
0x140002abd  nop     dword ptr [rax+rax+00h]
0x140002ac2  mov     ebx, eax
0x140002ac4  test    eax, eax
0x140002ac6  js      loc_140002BF2
0x140002acc  xor     edx, edx; ServerThread
0x140002ace  lea     rcx, [rbp+0D0h+ClientContext]; ClientContext
0x140002ad2  mov     r12b, 1
0x140002ad5  call    cs:__imp_SeImpersonateClientEx
0x140002adc  nop     dword ptr [rax+rax+00h]
0x140002ae1  xor     r10d, r10d
0x140002ae4  mov     ebx, eax
0x140002ae6  test    eax, eax
0x140002ae8  js      loc_140002BF2
0x140002aee  mov     esi, [rbp+0D0h+var_140]
0x140002af1  cmp     [rbp+0D0h+arg_28], r10b
0x140002af8  jz      short loc_140002AFD
0x140002afa  or      edi, 8
0x140002afd  mov     rcx, [r13+8]; Filter
0x140002b01  lea     r8, [rbp+0D0h+EcpList+8]; EcpList
0x140002b05  mov     rdx, r15; CallbackData
0x140002b08  call    cs:__imp_FltGetEcpListFromCallbackData
0x140002b0f  nop     dword ptr [rax+rax+00h]
0x140002b14  mov     ebx, eax
0x140002b16  test    eax, eax
0x140002b18  js      loc_140002BEF
0x140002b1e  mov     rcx, [r14]; FileObject
0x140002b21  call    cs:__imp_IoGetTransactionParameterBlock
0x140002b28  nop     dword ptr [rax+rax+00h]
0x140002b2d  mov     rcx, [r14]
0x140002b30  mov     qword ptr [rbp+0D0h+var_118+8], rax
0x140002b34  call    cs:__imp_IoGetSilo
0x140002b3b  nop     dword ptr [rax+rax+00h]
0x140002b40  test    [rbp+0D0h+arg_20], 4
0x140002b47  jnz     short loc_140002B58
0x140002b49  mov     rcx, rax
0x140002b4c  call    cs:__imp_PsGetParentSilo
0x140002b53  nop     dword ptr [rax+rax+00h]
0x140002b58  test    [rbp+0D0h+arg_20], 20h
0x140002b5f  mov     [rbp+0D0h+var_108], rax
0x140002b63  jnz     loc_140002CEB
0x140002b69  movzx   ecx, word ptr [rbp+0D0h+var_150+6]
0x140002b6d  lea     rdx, [rbp+0D0h+EcpList]
0x140002b71  mov     r11, [r15+10h]
0x140002b75  lea     rax, [r15+18h]
0x140002b79  movzx   r10d, [rbp+0D0h+var_148]
0x140002b7e  mov     ebx, esi
0x140002b80  mov     r9, [rbp+0D0h+FileObject]; FileObject
0x140002b84  and     ebx, 0FFFFFFh
0x140002b8a  mov     r8, [rbp+0D0h+FileHandle]; FileHandle
0x140002b8e  add     r11, 40h ; '@'
0x140002b92  mov     [rsp+1D0h+DriverContext], rdx; DriverContext
0x140002b97  mov     rdx, [rbp+0D0h+Instance]; Instance
0x140002b9b  mov     [rsp+1D0h+Flags], edi; Flags
0x140002b9f  mov     edi, [rbp+0D0h+var_13C]
0x140002ba2  mov     [rsp+1D0h+EaLength], edi; EaLength
0x140002ba6  mov     rdi, [rbp+0D0h+var_100]
0x140002baa  mov     [rsp+1D0h+EaBuffer], rdi; EaBuffer
0x140002baf  mov     [rsp+1D0h+CreateOptions], ebx; CreateOptions
0x140002bb3  shr     esi, 18h
0x140002bb6  mov     [rsp+1D0h+CreateDisposition], esi; CreateDisposition
0x140002bba  mov     [rsp+1D0h+ShareAccess], ecx; ShareAccess
0x140002bbe  mov     rcx, [r13+8]; Filter
0x140002bc2  mov     [rsp+1D0h+FileAttributes], r10d; FileAttributes
0x140002bc7  mov     [rsp+1D0h+AllocationSize], r11; AllocationSize
0x140002bcc  mov     [rsp+1D0h+IoStatusBlock], rax; IoStatusBlock
0x140002bd1  lea     rax, [rbp+0D0h+var_E0]
0x140002bd5  mov     [rsp+1D0h+ObjectAttributes], rax; ObjectAttributes
0x140002bda  mov     eax, [rbp+0D0h+var_138]
0x140002bdd  mov     [rsp+1D0h+DesiredAccess], eax; DesiredAccess
0x140002be1  call    cs:__imp_FltCreateFileEx2
0x140002be8  nop     dword ptr [rax+rax+00h]
0x140002bed  mov     ebx, eax
0x140002bef  mov     sil, r12b
0x140002bf2  mov     al, byte ptr [rbp+0D0h+var_150]
0x140002bf5  mov     rcx, r13
0x140002bf8  mov     r9b, byte ptr [rbp+0D0h+var_150+1]
0x140002bfc  mov     r8b, byte ptr [rbp+0D0h+var_150+2]
0x140002c00  mov     rdx, [rbp+0D0h+EcpList+8]
0x140002c04  mov     byte ptr [rsp+1D0h+DesiredAccess], al
0x140002c08  call    BfRemoveCloudFileECPs
0x140002c0d  test    sil, sil
0x140002c10  jz      short loc_140002C1E
0x140002c12  call    cs:__imp_PsRevertToSelf
0x140002c19  nop     dword ptr [rax+rax+00h]
0x140002c1e  mov     rdi, [rbp+0D0h+Token]
0x140002c22  test    rdi, rdi
0x140002c25  jnz     loc_140002CAB
0x140002c2b  test    r12b, r12b
0x140002c2e  jz      short loc_140002C40
0x140002c30  lea     rcx, [rbp+0D0h+ClientContext]
0x140002c34  call    cs:__imp_SeDeleteClientSecurity
0x140002c3b  nop     dword ptr [rax+rax+00h]
0x140002c40  mov     eax, ebx
0x140002c42  mov     rcx, [rbp+0D0h+var_50]
0x140002c49  xor     rcx, rsp; StackCookie
0x140002c4c  call    __security_check_cookie
0x140002c51  add     rsp, 198h
0x140002c58  pop     r15
0x140002c5a  pop     r14
0x140002c5c  pop     r13
0x140002c5e  pop     r12
0x140002c60  pop     rdi
0x140002c61  pop     rsi
0x140002c62  pop     rbx
0x140002c63  pop     rbp
0x140002c64  retn
0x140002c66  mov     r8d, 200h
0x140002c6c  test    r9b, r9b
0x140002c6f  jnz     loc_1400029D1
0x140002c75  mov     rax, [r15+10h]
0x140002c79  test    [rax+6], r14b
0x140002c7d  jz      loc_1400029D1
0x140002c83  jmp     loc_1400029CB
0x140002c88  mov     rcx, [r14]; FileObject
0x140002c8b  call    cs:__imp_IoIsFileObjectIgnoringSharing
0x140002c92  nop     dword ptr [rax+rax+00h]
0x140002c97  xor     r10d, r10d
0x140002c9a  test    al, al
0x140002c9c  jz      loc_140002A54
0x140002ca2  bts     edi, 0Bh
0x140002ca6  jmp     loc_140002A54
0x140002cab  test    sil, sil
0x140002cae  jz      short loc_140002CD7
0x140002cb0  mov     rcx, gs:188h; Thread
0x140002cb9  mov     rdx, rdi; Token
0x140002cbc  mov     eax, [rbp+0D0h+ImpersonationLevel]
0x140002cbf  mov     r9b, byte ptr [rbp+0D0h+var_150+3]; EffectiveOnly
0x140002cc3  mov     r8b, byte ptr [rbp+0D0h+var_150+4]; CopyOnOpen
0x140002cc7  mov     [rsp+1D0h+DesiredAccess], eax; ImpersonationLevel
0x140002ccb  call    cs:__imp_PsImpersonateClient
0x140002cd2  nop     dword ptr [rax+rax+00h]
0x140002cd7  mov     rcx, rdi; ImpersonationToken
0x140002cda  call    cs:__imp_PsDereferenceImpersonationToken
0x140002ce1  nop     dword ptr [rax+rax+00h]
0x140002ce6  jmp     loc_140002C2B
0x140002ceb  lea     rax, [rbp+0D0h+var_150]
0x140002cef  mov     rdx, r13
0x140002cf2  mov     [rsp+1D0h+ObjectAttributes], rax; __int64
0x140002cf7  lea     r9, [rbp+0D0h+var_150+2]
0x140002cfb  lea     rax, [rbp+0D0h+var_150+1]
0x140002cff  mov     rcx, r15; CallbackData
0x140002d02  lea     r8, [rbp+0D0h+EcpList]
0x140002d06  mov     qword ptr [rsp+1D0h+DesiredAccess], rax; __int64
0x140002d0b  call    BfAddCloudFileECPs
0x140002d10  mov     ebx, eax
0x140002d12  test    eax, eax
0x140002d14  js      loc_140002BEF
0x140002d1a  jmp     loc_140002B69
```
