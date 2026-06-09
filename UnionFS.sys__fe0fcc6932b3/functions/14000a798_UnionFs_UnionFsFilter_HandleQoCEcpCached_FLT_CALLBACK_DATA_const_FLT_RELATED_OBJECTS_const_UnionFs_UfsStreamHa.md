# UnionFs::UnionFsFilter::HandleQoCEcpCached(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsUnionCtx &,UnionFs::UfsPathCachePayload &,UnionFs::StackEventTracer &)

- ea: `0x14000a798`
- end: `0x14000ac90`
- name: `?HandleQoCEcpCached@UnionFsFilter@UnionFs@@AEAAXAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVUfsUnionCtx@2@AEAVUfsPathCachePayload@2@AEAVStackEventTracer@2@@Z`
- size: `1272`
- prototype: `void __fastcall(UnionFs::UnionFsFilter *this, struct _FLT_CALLBACK_DATA *, struct _FLT_RELATED_OBJECTS *, const struct UnionFs::UfsStreamHandleCtx *, struct _FLT_RELATED_OBJECTS *, PVOID *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013b60`
- `0x14001568c`

## callees

- `0x14000a798`
- `0x14000ac98`
- `0x14000ed24`
- `0x14000f81c`
- `0x140056974`
- `0x140056c7c`
- `0x14006f9ec`
- `0x140078afc`
- `0x140078c58`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ac3c`
- `ntoskrnl!ExAllocatePool2` at `0x14000abe0`
- `ntoskrnl!ExAllocatePool2` at `0x14000abe0`
- `ntoskrnl!ObfReferenceObject` at `0x14000a82c`
- `ntoskrnl!ObfReferenceObject` at `0x14000aa18`
- `ntoskrnl!ObfReferenceObject` at `0x14000a82c`
- `ntoskrnl!ObfReferenceObject` at `0x14000aa18`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000abad`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000ac10`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000abad`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14000ac10`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a96f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000aaab`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a96f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000aaab`
- `FLTMGR!FltQueryInformationFile` at `0x14000a881`
- `FLTMGR!FltQueryInformationFile` at `0x14000a881`
- `FLTMGR!FltAcknowledgeEcp` at `0x14000ac65`
- `FLTMGR!FltAcknowledgeEcp` at `0x14000ac65`

## string_xrefs

- `0x14000a8a1`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000a92c`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000a9d2`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000aa64`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000ab07`: `UnionFs::UnionFsFilter::HandleQoCEcpCached`
- `0x14000a920`: `PUSH: VirtualizeQoCEcpStatInfo cached`
- `0x14000a9c6`: `PUSH: HandleQoCEcpEaInfo cached`
- `0x14000aafb`: `PUSH: VirtualizeQoCEcpUsnInfo cached`

## pseudocode

```c
void __fastcall UnionFs::UnionFsFilter::HandleQoCEcpCached(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        const struct UnionFs::UfsStreamHandleCtx *a4,
        struct _FLT_RELATED_OBJECTS *a5,
        PVOID *a6,
        struct UnionFs::StackEventTracer *a7)
{
  struct _FLT_RELATED_OBJECTS *v7; // r15
  const struct _FLT_CALLBACK_DATA *v8; // rsi
  struct _FLT_RELATED_OBJECTS *v9; // r13
  UnionFs::UnionFsFilter *v10; // rcx
  _DWORD *v11; // rbx
  volatile signed __int32 *v12; // rsi
  struct _FILE_OBJECT *v13; // r15
  PFLT_INSTANCE **v14; // r13
  NTSTATUS InformationFile; // eax
  struct UnionFs::UfsUnionCtx *v16; // r8
  UnionFs::Utils *v17; // rcx
  struct _FLT_RELATED_OBJECTS *v18; // rdx
  int v19; // eax
  int v20; // eax
  UnionFs::UnionFsFilter *v21; // rcx
  volatile signed __int32 *v22; // rsi
  struct _FILE_OBJECT *v23; // r15
  const struct _FLT_INSTANCE ***v24; // rdx
  int BackingEAsForQoC; // eax
  int v26; // eax
  int v27; // eax
  unsigned int v28; // r14d
  void *Pool2; // rax
  void *v30; // rdi
  char *LengthReturned; // [rsp+28h] [rbp-89h]
  struct UnionFs::StackEventTracer *LengthReturneda; // [rsp+28h] [rbp-89h]
  const char *LengthReturnedb; // [rsp+28h] [rbp-89h]
  struct _QUERY_ON_CREATE_ECP_CONTEXT *Length; // [rsp+30h] [rbp-81h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+38h] [rbp-79h] BYREF
  struct _FLT_RELATED_OBJECTS *v36; // [rsp+40h] [rbp-71h]
  PVOID EcpContext; // [rsp+48h] [rbp-69h] BYREF
  UnionFs::Utils *v38; // [rsp+50h] [rbp-61h]
  struct _FLT_CALLBACK_DATA *v39; // [rsp+58h] [rbp-59h]
  _OWORD FileInformation[5]; // [rsp+60h] [rbp-51h] BYREF

  v7 = a5;
  v8 = a2;
  v9 = a3;
  v38 = (UnionFs::Utils *)a3;
  v39 = a2;
  ObjectsSecurityDescriptor = a4;
  v36 = a5;
  EcpContext = 0;
  LODWORD(Length) = 0;
  if ( UnionFs::Utils::GetQueryOnCreateEcp(
         a2,
         (const struct _FLT_CALLBACK_DATA *)&EcpContext,
         &Length,
         (unsigned int *)a4) )
  {
    v11 = EcpContext;
    LOBYTE(v10) = 0;
    if ( (*(_DWORD *)EcpContext & 1) == 0 )
      goto LABEL_18;
    if ( (unsigned int)Length < 0x58 )
    {
      *((_DWORD *)EcpContext + 2) |= 1u;
LABEL_17:
      v11[1] |= 1u;
      LOBYTE(v10) = 1;
LABEL_18:
      if ( (*v11 & 4) != 0 )
      {
        if ( (unsigned int)Length >= 0x88 )
        {
          v20 = UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(
                  v10,
                  v8,
                  v9,
                  (struct UnionFs::UfsUnionCtx *)v7,
                  (struct _QUERY_ON_CREATE_ECP_CONTEXT *)v11,
                  a7);
          if ( v20 >= 0 )
          {
            if ( (v11[1] & 4) == 0 )
            {
              ObfReferenceObject(a6[8]);
              v22 = (volatile signed __int32 *)a6[5];
              v23 = (struct _FILE_OBJECT *)a6[8];
              v24 = (const struct _FLT_INSTANCE ***)a6[4];
              if ( v22 )
                _InterlockedIncrement(v22 + 2);
              BackingEAsForQoC = UnionFs::UnionFsFilter::QueryBackingEAsForQoC(
                                   v21,
                                   *v24[1],
                                   v23,
                                   (struct _QUERY_ON_CREATE_ECP_CONTEXT *)v11,
                                   a7);
              if ( BackingEAsForQoC < 0 )
              {
                v11[2] |= 4u;
                UnionFs::ProcessTraceStatusPushLocation(
                  (UnionFs *)(unsigned int)BackingEAsForQoC,
                  (int)a7,
                  (struct UnionFs::StackEventTracer *)0x7BA0001136ALL,
                  (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
                  "PUSH: QueryBackingEAsForQoC",
                  LengthReturned);
                UnionFs::StackEventTracer::LogError(a7);
                *(_DWORD *)a7 = 0;
                *((_WORD *)a7 + 274) = 0;
              }
              if ( v22 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v22);
              if ( v23 )
                ObfDereferenceObject(v23);
            }
          }
          else
          {
            v11[2] |= 4u;
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v20,
              (int)a7,
              (struct UnionFs::StackEventTracer *)0x7BB00011359LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
              "PUSH: HandleQoCEcpEaInfo cached",
              LengthReturned);
            UnionFs::StackEventTracer::LogError(a7);
            *(_DWORD *)a7 = 0;
            *((_WORD *)a7 + 274) = 0;
          }
        }
        else
        {
          v11[2] |= 4u;
        }
        v11[1] |= 4u;
        LOBYTE(v10) = 1;
      }
      if ( (*v11 & 8) != 0 )
      {
        if ( (unsigned int)Length >= 0xB0 )
        {
          v26 = UnionFs::Utils::VirtualizeQoCEcpUsnInfo(
                  (UnionFs::Utils *)v9,
                  v36,
                  (struct UnionFs::UfsUnionCtx *)ObjectsSecurityDescriptor,
                  (const struct UnionFs::UfsStreamHandleCtx *)(v11 + 38),
                  a7,
                  (struct UnionFs::StackEventTracer *)LengthReturned);
          if ( v26 < 0 )
          {
            v11[2] |= 8u;
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v26,
              (int)a7,
              (struct UnionFs::StackEventTracer *)0x7B900011387LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
              "PUSH: VirtualizeQoCEcpUsnInfo cached",
              LengthReturnedb);
            UnionFs::StackEventTracer::LogError(a7);
            *(_DWORD *)a7 = 0;
            *((_WORD *)a7 + 274) = 0;
          }
        }
        else
        {
          v11[2] |= 8u;
        }
        v11[1] |= 8u;
        LOBYTE(v10) = 1;
      }
      v27 = *v11;
      if ( (*v11 & 2) != 0 )
      {
        v11[1] |= 2u;
        LOBYTE(v10) = 1;
        v11[2] |= 2u;
      }
      if ( (v27 & 0x10) == 0 )
      {
        if ( !(_BYTE)v10 )
          return;
        goto LABEL_54;
      }
      if ( (unsigned int)Length >= 0xC8 )
      {
        ObjectsSecurityDescriptor = a6[10];
        if ( !v11[44] )
        {
          v11[3] |= 0x10u;
LABEL_52:
          v11[1] |= 0x10u;
LABEL_54:
          FltAcknowledgeEcp(*(PFLT_FILTER *)UnionFs::g_FilterState, v11);
          return;
        }
        LODWORD(Length) = 0;
        if ( SeQuerySecurityDescriptorInfo(v11 + 44, 0, (PULONG)&Length, &ObjectsSecurityDescriptor) == -1073741789 )
        {
          if ( (_DWORD)Length )
          {
            v28 = (unsigned int)Length;
            Pool2 = (void *)ExAllocatePool2(256, (unsigned int)Length, 1936803413);
            v30 = Pool2;
            if ( Pool2 )
            {
              memset(Pool2, 0, v28);
              if ( SeQuerySecurityDescriptorInfo(v11 + 44, v30, (PULONG)&Length, &ObjectsSecurityDescriptor) < 0 )
              {
                v11[2] |= 0x10u;
                ExFreePoolWithTag(v30, 0);
              }
              else
              {
                *((_QWORD *)v11 + 24) = v30;
                v11[47] = (_DWORD)Length;
              }
              goto LABEL_52;
            }
          }
        }
      }
      v11[2] |= 0x10u;
      goto LABEL_52;
    }
    ObfReferenceObject(a6[8]);
    v12 = (volatile signed __int32 *)a6[5];
    v13 = (struct _FILE_OBJECT *)a6[8];
    v14 = (PFLT_INSTANCE **)a6[4];
    if ( v12 )
      _InterlockedIncrement(v12 + 2);
    memset(FileInformation, 0, 0x48u);
    InformationFile = FltQueryInformationFile(*v14[1], v13, FileInformation, 0x48u, (FILE_INFORMATION_CLASS)68, 0);
    if ( InformationFile >= 0 )
    {
      v9 = (struct _FLT_RELATED_OBJECTS *)v38;
      v16 = (struct UnionFs::UfsUnionCtx *)ObjectsSecurityDescriptor;
      v17 = v38;
      v18 = v36;
      *((_OWORD *)v11 + 1) = FileInformation[0];
      *((_OWORD *)v11 + 2) = FileInformation[1];
      *((_OWORD *)v11 + 3) = FileInformation[2];
      *((_OWORD *)v11 + 4) = FileInformation[3];
      *((_QWORD *)v11 + 10) = *(_QWORD *)&FileInformation[4];
      v19 = UnionFs::Utils::VirtualizeQoCEcpStatInfo(
              v17,
              v18,
              v16,
              (const struct UnionFs::UfsStreamHandleCtx *)(v11 + 4),
              a7,
              LengthReturneda);
      if ( v19 >= 0 )
      {
LABEL_12:
        if ( v12 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v12);
        if ( v13 )
          ObfDereferenceObject(v13);
        v7 = v36;
        v8 = v39;
        goto LABEL_17;
      }
      v11[2] |= 1u;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v19,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x7BC00011341LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
        "PUSH: VirtualizeQoCEcpStatInfo cached",
        LengthReturned);
      UnionFs::StackEventTracer::LogError(a7);
    }
    else
    {
      v11[2] |= 1u;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)InformationFile,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x7BD0001132BLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::HandleQoCEcpCached",
        "PUSH: FltQueryInformationFile for stat QoC",
        (const char *)LengthReturneda);
      UnionFs::StackEventTracer::LogError(a7);
      v9 = (struct _FLT_RELATED_OBJECTS *)v38;
    }
    *((_WORD *)a7 + 274) = 0;
    *(_DWORD *)a7 = 0;
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x14000a798  push    rbp
0x14000a79a  push    rbx
0x14000a79b  push    rsi
0x14000a79c  push    rdi
0x14000a79d  push    r13
0x14000a79f  push    r14
0x14000a7a1  push    r15
0x14000a7a3  lea     rbp, [rsp-0Fh]
0x14000a7a8  sub     rsp, 0C0h
0x14000a7af  mov     rax, cs:__security_cookie
0x14000a7b6  xor     rax, rsp
0x14000a7b9  mov     [rbp+3Fh+var_40], rax
0x14000a7bd  mov     r15, [rbp+3Fh+arg_20]
0x14000a7c1  mov     rsi, rdx
0x14000a7c4  mov     rdi, [rbp+3Fh+arg_30]
0x14000a7c8  mov     r13, r8
0x14000a7cb  mov     r14, [rbp+3Fh+arg_28]
0x14000a7cf  mov     rcx, rsi; CallbackData
0x14000a7d2  mov     [rbp+3Fh+var_A0], r8
0x14000a7d6  lea     r8, [rsp+0F0h+Length]; struct _QUERY_ON_CREATE_ECP_CONTEXT **
0x14000a7db  mov     [rbp+3Fh+var_98], rdx
0x14000a7df  lea     rdx, [rbp+3Fh+EcpContext]; struct _FLT_CALLBACK_DATA *
0x14000a7e3  mov     [rbp+3Fh+ObjectsSecurityDescriptor], r9
0x14000a7e7  mov     [rbp+3Fh+var_B0], r15
0x14000a7eb  mov     [rbp+3Fh+EcpContext], 0
0x14000a7f3  mov     dword ptr [rsp+0F0h+Length], 0
0x14000a7fb  call    ?GetQueryOnCreateEcp@Utils@UnionFs@@YA_NAEBU_FLT_CALLBACK_DATA@@PEAPEAU_QUERY_ON_CREATE_ECP_CONTEXT@@PEAK@Z; UnionFs::Utils::GetQueryOnCreateEcp(_FLT_CALLBACK_DATA const &,_QUERY_ON_CREATE_ECP_CONTEXT * *,ulong *)
0x14000a800  test    al, al
0x14000a802  jz      loc_14000AC71
0x14000a808  mov     rbx, [rbp+3Fh+EcpContext]
0x14000a80c  xor     cl, cl
0x14000a80e  mov     eax, [rbx]
0x14000a810  test    al, 1
0x14000a812  jz      loc_14000A989
0x14000a818  cmp     dword ptr [rsp+0F0h+Length], 58h ; 'X'
0x14000a81d  jnb     short loc_14000A828
0x14000a81f  or      dword ptr [rbx+8], 1
0x14000a823  jmp     loc_14000A983
0x14000a828  mov     rcx, [r14+40h]; Object
0x14000a82c  call    cs:__imp_ObfReferenceObject
0x14000a833  nop     dword ptr [rax+rax+00h]
0x14000a838  mov     rsi, [r14+28h]
0x14000a83c  mov     r15, [r14+40h]
0x14000a840  mov     r13, [r14+20h]
0x14000a844  test    rsi, rsi
0x14000a847  jz      short loc_14000A84D
0x14000a849  lock inc dword ptr [rsi+8]
0x14000a84d  xor     edx, edx; Val
0x14000a84f  lea     rcx, [rbp+3Fh+FileInformation]; void *
0x14000a853  lea     r8d, [rdx+48h]; Size
0x14000a857  call    memset
0x14000a85c  mov     rcx, [r13+8]
0x14000a860  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x14000a864  mov     [rsp+0F0h+LengthReturned], 0; char *
0x14000a86d  mov     r9d, 48h ; 'H'; Length
0x14000a873  mov     rdx, r15; FileObject
0x14000a876  mov     [rsp+0F0h+FileInformationClass], 44h ; 'D'; FileInformationClass
0x14000a87e  mov     rcx, [rcx]; Instance
0x14000a881  call    cs:__imp_FltQueryInformationFile
0x14000a888  nop     dword ptr [rax+rax+00h]
0x14000a88d  test    eax, eax
0x14000a88f  jns     short loc_14000A8CD
0x14000a891  or      dword ptr [rbx+8], 1
0x14000a895  lea     rcx, aPushFltqueryin; "PUSH: FltQueryInformationFile for stat "...
0x14000a89c  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000a8a1  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000a8a8  mov     ecx, eax; this
0x14000a8aa  mov     r8, 7BD0001132Bh; struct UnionFs::StackEventTracer *
0x14000a8b4  mov     rdx, rdi; int
0x14000a8b7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000a8bc  mov     rcx, rdi; this
0x14000a8bf  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000a8c4  mov     r13, [rbp+3Fh+var_A0]
0x14000a8c8  jmp     loc_14000A94F
0x14000a8cd  movaps  xmm0, [rbp+3Fh+FileInformation]
0x14000a8d1  lea     r9, [rbx+10h]; struct UnionFs::UfsStreamHandleCtx *
0x14000a8d5  mov     r13, [rbp+3Fh+var_A0]
0x14000a8d9  mov     r8, [rbp+3Fh+ObjectsSecurityDescriptor]; struct UnionFs::UfsUnionCtx *
0x14000a8dd  mov     rcx, r13; this
0x14000a8e0  mov     rdx, [rbp+3Fh+var_B0]; struct _FLT_RELATED_OBJECTS *
0x14000a8e4  movups  xmmword ptr [r9], xmm0
0x14000a8e8  mov     qword ptr [rsp+0F0h+FileInformationClass], rdi; struct _QUERY_ON_CREATE_FILE_STAT_INFORMATION *
0x14000a8ed  movaps  xmm1, [rbp+3Fh+var_80]
0x14000a8f1  movups  xmmword ptr [r9+10h], xmm1
0x14000a8f6  movaps  xmm0, [rbp+3Fh+var_70]
0x14000a8fa  movups  xmmword ptr [r9+20h], xmm0
0x14000a8ff  movaps  xmm1, [rbp+3Fh+var_60]
0x14000a903  movups  xmmword ptr [r9+30h], xmm1
0x14000a908  movsd   xmm0, [rbp+3Fh+var_50]
0x14000a90d  movsd   qword ptr [r9+40h], xmm0
0x14000a913  call    ?VirtualizeQoCEcpStatInfo@Utils@UnionFs@@YAJAEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@AEBVUfsStreamHandleCtx@2@AEAU_QUERY_ON_CREATE_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::VirtualizeQoCEcpStatInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,_QUERY_ON_CREATE_FILE_STAT_INFORMATION &,UnionFs::StackEventTracer &)
0x14000a918  test    eax, eax
0x14000a91a  jns     short loc_14000A95A
0x14000a91c  or      dword ptr [rbx+8], 1
0x14000a920  lea     rcx, aPushVirtualize_0; "PUSH: VirtualizeQoCEcpStatInfo cached"
0x14000a927  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000a92c  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000a933  mov     ecx, eax; this
0x14000a935  mov     r8, 7BC00011341h; struct UnionFs::StackEventTracer *
0x14000a93f  mov     rdx, rdi; int
0x14000a942  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000a947  mov     rcx, rdi; this
0x14000a94a  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000a94f  xor     eax, eax
0x14000a951  mov     [rdi+224h], ax
0x14000a958  mov     [rdi], eax
0x14000a95a  test    rsi, rsi
0x14000a95d  jz      short loc_14000A967
0x14000a95f  mov     rcx, rsi; this
0x14000a962  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14000a967  test    r15, r15
0x14000a96a  jz      short loc_14000A97B
0x14000a96c  mov     rcx, r15; Object
0x14000a96f  call    cs:__imp_ObfDereferenceObject
0x14000a976  nop     dword ptr [rax+rax+00h]
0x14000a97b  mov     r15, [rbp+3Fh+var_B0]
0x14000a97f  mov     rsi, [rbp+3Fh+var_98]
0x14000a983  or      dword ptr [rbx+4], 1
0x14000a987  mov     cl, 1; this
0x14000a989  mov     eax, [rbx]
0x14000a98b  test    al, 4
0x14000a98d  jz      loc_14000AABD
0x14000a993  cmp     dword ptr [rsp+0F0h+Length], 88h
0x14000a99b  jnb     short loc_14000A9A6
0x14000a99d  or      dword ptr [rbx+8], 4
0x14000a9a1  jmp     loc_14000AAB7
0x14000a9a6  mov     [rsp+0F0h+LengthReturned], rdi; char *
0x14000a9ab  mov     r9, r15; struct UnionFs::UfsUnionCtx *
0x14000a9ae  mov     r8, r13; struct _FLT_RELATED_OBJECTS *
0x14000a9b1  mov     qword ptr [rsp+0F0h+FileInformationClass], rbx; struct _QUERY_ON_CREATE_ECP_CONTEXT *
0x14000a9b6  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x14000a9b9  call    ?HandleQoCEcpEaInfo@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,_QUERY_ON_CREATE_ECP_CONTEXT *,UnionFs::StackEventTracer &)
0x14000a9be  test    eax, eax
0x14000a9c0  jns     short loc_14000AA09
0x14000a9c2  or      dword ptr [rbx+8], 4
0x14000a9c6  lea     rcx, aPushHandleqoce; "PUSH: HandleQoCEcpEaInfo cached"
0x14000a9cd  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000a9d2  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000a9d9  mov     ecx, eax; this
0x14000a9db  mov     r8, 7BB00011359h; struct UnionFs::StackEventTracer *
0x14000a9e5  mov     rdx, rdi; int
0x14000a9e8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000a9ed  mov     rcx, rdi; this
0x14000a9f0  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000a9f5  xor     eax, eax
0x14000a9f7  mov     dword ptr [rdi], 0
0x14000a9fd  mov     [rdi+224h], ax
0x14000aa04  jmp     loc_14000AAB7
0x14000aa09  mov     eax, [rbx+4]
0x14000aa0c  test    al, 4
0x14000aa0e  jnz     loc_14000AAB7
0x14000aa14  mov     rcx, [r14+40h]; Object
0x14000aa18  call    cs:__imp_ObfReferenceObject
0x14000aa1f  nop     dword ptr [rax+rax+00h]
0x14000aa24  mov     rsi, [r14+28h]
0x14000aa28  mov     r15, [r14+40h]
0x14000aa2c  mov     rdx, [r14+20h]
0x14000aa30  test    rsi, rsi
0x14000aa33  jz      short loc_14000AA39
0x14000aa35  lock inc dword ptr [rsi+8]
0x14000aa39  mov     rdx, [rdx+8]
0x14000aa3d  mov     r9, rbx; struct _QUERY_ON_CREATE_ECP_CONTEXT *
0x14000aa40  mov     r8, r15; struct _FILE_OBJECT *
0x14000aa43  mov     qword ptr [rsp+0F0h+FileInformationClass], rdi; struct UnionFs::StackEventTracer *
0x14000aa48  mov     rdx, [rdx]; struct _FLT_INSTANCE *
0x14000aa4b  call    ?QueryBackingEAsForQoC@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAU_QUERY_ON_CREATE_ECP_CONTEXT@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::QueryBackingEAsForQoC(_FLT_INSTANCE const &,_FILE_OBJECT const &,_QUERY_ON_CREATE_ECP_CONTEXT *,UnionFs::StackEventTracer &)
0x14000aa50  test    eax, eax
0x14000aa52  jns     short loc_14000AA96
0x14000aa54  or      dword ptr [rbx+8], 4
0x14000aa58  lea     rcx, aPushQuerybacki; "PUSH: QueryBackingEAsForQoC"
0x14000aa5f  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000aa64  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000aa6b  mov     ecx, eax; this
0x14000aa6d  mov     r8, 7BA0001136Ah; struct UnionFs::StackEventTracer *
0x14000aa77  mov     rdx, rdi; int
0x14000aa7a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000aa7f  mov     rcx, rdi; this
0x14000aa82  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000aa87  xor     eax, eax
0x14000aa89  mov     dword ptr [rdi], 0
0x14000aa8f  mov     [rdi+224h], ax
0x14000aa96  test    rsi, rsi
0x14000aa99  jz      short loc_14000AAA3
0x14000aa9b  mov     rcx, rsi; this
0x14000aa9e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14000aaa3  test    r15, r15
0x14000aaa6  jz      short loc_14000AAB7
0x14000aaa8  mov     rcx, r15; Object
0x14000aaab  call    cs:__imp_ObfDereferenceObject
0x14000aab2  nop     dword ptr [rax+rax+00h]
0x14000aab7  or      dword ptr [rbx+4], 4
0x14000aabb  mov     cl, 1
0x14000aabd  mov     eax, [rbx]
0x14000aabf  test    al, 8
0x14000aac1  jz      loc_14000AB47
0x14000aac7  cmp     dword ptr [rsp+0F0h+Length], 0B0h
0x14000aacf  jnb     short loc_14000AAD7
0x14000aad1  or      dword ptr [rbx+8], 8
0x14000aad5  jmp     short loc_14000AB39
0x14000aad7  mov     r8, [rbp+3Fh+ObjectsSecurityDescriptor]; struct UnionFs::UfsUnionCtx *
0x14000aadb  lea     r9, [rbx+98h]; struct UnionFs::UfsStreamHandleCtx *
0x14000aae2  mov     rdx, [rbp+3Fh+var_B0]; struct _FLT_RELATED_OBJECTS *
0x14000aae6  mov     rcx, r13; this
0x14000aae9  mov     qword ptr [rsp+0F0h+FileInformationClass], rdi; struct _QUERY_ON_CREATE_USN_INFORMATION *
0x14000aaee  call    ?VirtualizeQoCEcpUsnInfo@Utils@UnionFs@@YAJAEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@AEBVUfsStreamHandleCtx@2@AEAU_QUERY_ON_CREATE_USN_INFORMATION@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::VirtualizeQoCEcpUsnInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,_QUERY_ON_CREATE_USN_INFORMATION &,UnionFs::StackEventTracer &)
0x14000aaf3  test    eax, eax
0x14000aaf5  jns     short loc_14000AB39
0x14000aaf7  or      dword ptr [rbx+8], 8
0x14000aafb  lea     rcx, aPushVirtualize_1; "PUSH: VirtualizeQoCEcpUsnInfo cached"
0x14000ab02  mov     qword ptr [rsp+0F0h+FileInformationClass], rcx; char *
0x14000ab07  lea     r9, aUnionfsUnionfs_4; "UnionFs::UnionFsFilter::HandleQoCEcpCac"...
0x14000ab0e  mov     ecx, eax; this
0x14000ab10  mov     r8, 7B900011387h; struct UnionFs::StackEventTracer *
0x14000ab1a  mov     rdx, rdi; int
0x14000ab1d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000ab22  mov     rcx, rdi; this
0x14000ab25  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x14000ab2a  xor     eax, eax
0x14000ab2c  mov     dword ptr [rdi], 0
0x14000ab32  mov     [rdi+224h], ax
0x14000ab39  or      dword ptr [rbx+4], 8
0x14000ab3d  mov     edi, 1
0x14000ab42  mov     cl, dil
0x14000ab45  jmp     short loc_14000AB4C
0x14000ab47  mov     edi, 1
0x14000ab4c  mov     eax, [rbx]
0x14000ab4e  test    al, 2
0x14000ab50  jz      short loc_14000AB5D
0x14000ab52  or      dword ptr [rbx+4], 2
0x14000ab56  mov     cl, dil
0x14000ab59  or      dword ptr [rbx+8], 2
0x14000ab5d  mov     r15d, 10h
0x14000ab63  test    r15b, al
0x14000ab66  jz      loc_14000AC54
0x14000ab6c  cmp     dword ptr [rsp+0F0h+Length], 0C8h
0x14000ab74  jb      loc_14000AC4A
0x14000ab7a  mov     rax, [r14+50h]
0x14000ab7e  lea     rsi, [rbx+0B0h]
0x14000ab85  mov     [rbp+3Fh+ObjectsSecurityDescriptor], rax
0x14000ab89  cmp     dword ptr [rsi], 0
0x14000ab8c  jnz     short loc_14000AB97
0x14000ab8e  or      [rbx+0Ch], r15d
0x14000ab92  jmp     loc_14000AC4E
0x14000ab97  lea     r9, [rbp+3Fh+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x14000ab9b  mov     dword ptr [rsp+0F0h+Length], 0
0x14000aba3  lea     r8, [rsp+0F0h+Length]; Length
0x14000aba8  xor     edx, edx; SecurityDescriptor
0x14000abaa  mov     rcx, rsi; SecurityInformation
0x14000abad  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x14000abb4  nop     dword ptr [rax+rax+00h]
0x14000abb9  cmp     eax, 0C0000023h
0x14000abbe  jnz     loc_14000AC4A
0x14000abc4  mov     eax, dword ptr [rsp+0F0h+Length]
0x14000abc8  test    eax, eax
0x14000abca  jz      short loc_14000AC4A
0x14000abcc  mov     edx, eax
0x14000abce  mov     ecx, 100h
0x14000abd3  cmovz   rdx, rdi
0x14000abd7  mov     r8d, 73714655h
0x14000abdd  mov     r14d, eax
0x14000abe0  call    cs:__imp_ExAllocatePool2
0x14000abe7  nop     dword ptr [rax+rax+00h]
0x14000abec  mov     rdi, rax
0x14000abef  test    rax, rax
0x14000abf2  jz      short loc_14000AC4A
0x14000abf4  mov     r8d, r14d; Size
0x14000abf7  xor     edx, edx; Val
0x14000abf9  mov     rcx, rax; void *
0x14000abfc  call    memset
0x14000ac01  lea     r9, [rbp+3Fh+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x14000ac05  mov     rdx, rdi; SecurityDescriptor
0x14000ac08  lea     r8, [rsp+0F0h+Length]; Length
0x14000ac0d  mov     rcx, rsi; SecurityInformation
0x14000ac10  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x14000ac17  nop     dword ptr [rax+rax+00h]
0x14000ac1c  test    eax, eax
0x14000ac1e  js      short loc_14000AC33
0x14000ac20  mov     [rbx+0C0h], rdi
0x14000ac27  mov     eax, dword ptr [rsp+0F0h+Length]
0x14000ac2b  mov     [rbx+0BCh], eax
0x14000ac31  jmp     short loc_14000AC4E
0x14000ac33  or      [rbx+8], r15d
0x14000ac37  xor     edx, edx; Tag
0x14000ac39  mov     rcx, rdi; P
0x14000ac3c  call    cs:__imp_ExFreePoolWithTag
0x14000ac43  nop     dword ptr [rax+rax+00h]
0x14000ac48  jmp     short loc_14000AC4E
0x14000ac4a  or      [rbx+8], r15d
0x14000ac4e  or      [rbx+4], r15d
0x14000ac52  jmp     short loc_14000AC58
0x14000ac54  test    cl, cl
0x14000ac56  jz      short loc_14000AC71
0x14000ac58  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000ac5f  mov     rdx, rbx; EcpContext
0x14000ac62  mov     rcx, [rcx]; Filter
0x14000ac65  call    cs:__imp_FltAcknowledgeEcp
0x14000ac6c  nop     dword ptr [rax+rax+00h]
0x14000ac71  mov     rcx, [rbp+3Fh+var_40]
0x14000ac75  xor     rcx, rsp; StackCookie
0x14000ac78  call    __security_check_cookie
  ... truncated ...
```
