# UnionFs::UfsShadowFileObject::RequestLowerOplockImpl(UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *,ulong *)

- ea: `0x140058bb0`
- end: `0x140059134`
- name: `?RequestLowerOplockImpl@UfsShadowFileObject@UnionFs@@AEBAJAEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@PEAK@Z`
- size: `1412`
- prototype: `int(UnionFs::UfsShadowFileObject *__hidden this, struct UnionFs::StackEventTracer *, const struct _FLT_CALLBACK_DATA *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x14000a368`
- `0x14002a758`

## callees

- `0x14000f81c`
- `0x140056c44`
- `0x140056c7c`
- `0x140057b24`
- `0x140058bb0`
- `0x14005a0ec`
- `0x14006f124`
- `0x140076860`
- `0x140079cc4`
- `0x140079d44`
- `0x14007a0c0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140058efa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140058f53`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140058efa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140058f53`
- `ntoskrnl!ObfReferenceObject` at `0x140058d6d`
- `ntoskrnl!ObfReferenceObject` at `0x140058d87`
- `ntoskrnl!ObfReferenceObject` at `0x140058d6d`
- `ntoskrnl!ObfReferenceObject` at `0x140058d87`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058c8d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058fcb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058c8d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058fcb`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140058d51`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140058d51`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14005901b`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14005901b`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140058d2b`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140058d2b`
- `FLTMGR!FltObjectReference` at `0x140058cea`
- `FLTMGR!FltObjectReference` at `0x140058cea`
- `FLTMGR!FltObjectDereference` at `0x140058f0e`
- `FLTMGR!FltObjectDereference` at `0x140059084`
- `FLTMGR!FltObjectDereference` at `0x140058f0e`
- `FLTMGR!FltObjectDereference` at `0x140059084`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsShadowFileObject::RequestLowerOplockImpl(
        UnionFs::UfsShadowFileObject *this,
        struct UnionFs::StackEventTracer *a2,
        struct _FLT_CALLBACK_DATA *a3,
        unsigned int *a4)
{
  __int64 v4; // r15
  __int64 v8; // r14
  const struct _FLT_CALLBACK_DATA *v9; // rdx
  int BackingLayer; // ebx
  const char *v11; // rax
  __int64 v12; // r8
  unsigned int LowerOplockLevelForUpperOplockRequest; // r13d
  unsigned int v14; // ebx
  unsigned int v15; // edi
  void *v16; // rbx
  unsigned __int64 *v17; // rdx
  FsFltWil::Details *v18; // rcx
  void *v19; // r12
  struct _FLT_GENERIC_WORKITEM *GenericWorkItem; // r15
  _QWORD *v21; // r14
  struct _FILE_OBJECT *v22; // rdx
  struct _FLT_INSTANCE *v23; // rcx
  int v24; // r15d
  unsigned int v25; // ecx
  unsigned int v26; // edi
  unsigned int v27; // edi
  unsigned int v28; // edi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  DWORD LowPart; // ecx
  _DWORD *Parameters; // r8
  char v32; // dl
  bool v33; // zf
  unsigned int v34; // eax
  unsigned int v35; // edi
  unsigned int v36; // edi
  unsigned int v37; // edi
  PVOID v38; // r14
  PVOID v39; // rbx
  __int64 v41; // rbx
  struct _FAST_MUTEX *v42; // rcx
  char *v43; // [rsp+28h] [rbp-58h]
  char *v44; // [rsp+28h] [rbp-58h]
  PVOID Entry[2]; // [rsp+40h] [rbp-40h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+50h] [rbp-30h] BYREF
  __int64 v47; // [rsp+58h] [rbp-28h]
  __int64 v48; // [rsp+60h] [rbp-20h]
  utl::_RefCountBase *v49[2]; // [rsp+68h] [rbp-18h] BYREF
  PVOID Object; // [rsp+C0h] [rbp+40h] BYREF
  struct _FLT_CALLBACK_DATA *v51; // [rsp+D0h] [rbp+50h]

  v51 = a3;
  Object = this;
  v4 = *((_QWORD *)this + 4);
  v47 = v4;
  if ( (*(_DWORD *)(v4 + 40) & 8) == 0 )
  {
    BackingLayer = -1073740519;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000519LL,
      (int)a2,
      (struct UnionFs::StackEventTracer *)0x6E5001D052DLL,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::RequestLowerOplockImpl",
      "ORIGIN: Cannot request oplock on layer file",
      v43);
    return (unsigned int)BackingLayer;
  }
  v8 = *((_QWORD *)this + 3);
  v48 = v8;
  *(_OWORD *)v49 = 0;
  BackingLayer = UnionFs::UfsFsContext2::TryGetBackingLayer(v4, v49, a2);
  if ( BackingLayer < 0 )
  {
    v11 = "PUSH: No backing layer";
    v12 = 0x6E7001D0533LL;
LABEL_4:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)BackingLayer,
      (int)a2,
      (struct UnionFs::StackEventTracer *)v12,
      (unsigned __int64)"UnionFs::UfsShadowFileObject::RequestLowerOplockImpl",
      v11,
      v43);
    if ( v49[1] )
      utl::_RefCountBase::_DecStrong(v49[1]);
    return (unsigned int)BackingLayer;
  }
  if ( a3 )
    LowerOplockLevelForUpperOplockRequest = UnionFs::Utils::GetLowerOplockLevelForUpperOplockRequest(
                                              (UnionFs::Utils *)a3,
                                              v9);
  else
    LowerOplockLevelForUpperOplockRequest = *a4;
  FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(v8 + 120) + 216LL);
  v14 = *(_DWORD *)(v8 + 216);
  if ( FastMutex )
    ExReleaseFastMutex(FastMutex);
  if ( v14 < LowerOplockLevelForUpperOplockRequest )
  {
    if ( a4 )
    {
      v15 = *a4;
    }
    else
    {
      v15 = 7;
      if ( v14 )
        v15 = LowerOplockLevelForUpperOplockRequest;
    }
    while ( 1 )
    {
      *(_OWORD *)Entry = 0;
      BackingLayer = UnionFs::UfsFsContext2::TryGetBackingLayer(*((_QWORD *)Object + 4), Entry, a2);
      if ( BackingLayer < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)BackingLayer,
          (int)a2,
          (struct UnionFs::StackEventTracer *)0x633001D0396LL,
          (unsigned __int64)"UnionFs::UfsShadowFileObject::GetBackingInstance",
          "PUSH: Getting backing layer",
          v43);
        if ( Entry[1] )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Entry[1]);
        v11 = "PUSH: Getting backing instance";
        v12 = 0x6E8001D0560LL;
        goto LABEL_4;
      }
      v16 = (void *)**((_QWORD **)Entry[0] + 1);
      FltObjectReference(v16);
      if ( Entry[1] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Entry[1]);
      FsFltWil::AcquirePushLockShared(&FastMutex, v4 + 32);
      v18 = (FsFltWil::Details *)FastMutex;
      v19 = *(void **)(v4 + 24);
      FastMutex = 0;
      if ( v18 )
        FsFltWil::Details::ReleasePushLockShared(v18, v17);
      GenericWorkItem = FltAllocateGenericWorkItem();
      if ( !GenericWorkItem )
        break;
      v21 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 27);
      if ( !v21 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a2,
          (struct UnionFs::StackEventTracer *)0x6EC00212601LL,
          (unsigned __int64)"UnionFs::Utils::RequestOplockContext::AllocAndInit",
          "ORIGIN: Allocating RequestOplockContext",
          v43);
        FltFreeGenericWorkItem(GenericWorkItem);
LABEL_78:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)0xC000009ALL,
          (int)a2,
          (struct UnionFs::StackEventTracer *)0x6E9001D056BLL,
          (unsigned __int64)"UnionFs::UfsShadowFileObject::RequestLowerOplockImpl",
          "PUSH: Allocating oplock context",
          v44);
        if ( v16 )
          FltObjectDereference(v16);
        if ( v49[1] )
          utl::_RefCountBase::_DecStrong(v49[1]);
        return 3221225626LL;
      }
      ObfReferenceObject(Object);
      *v21 = Object;
      v21[1] = v16;
      ObfReferenceObject(v19);
      v21[2] = v19;
      v21[3] = 0;
      v21[5] = 0;
      v21[4] = GenericWorkItem;
      v22 = (struct _FILE_OBJECT *)v21[2];
      v23 = (struct _FLT_INSTANCE *)v21[1];
      Entry[0] = v21;
      v24 = UnionFs::Utils::RequestOplock(v23, v22, (__int64)Entry, (int)a2);
      if ( v24 == -1073741598 )
      {
        if ( v15 <= LowerOplockLevelForUpperOplockRequest )
        {
          v39 = Entry[0];
          if ( Entry[0] )
          {
            UnionFs::Utils::RequestOplockContext::~RequestOplockContext((UnionFs::Utils::RequestOplockContext *)Entry[0]);
            ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 27, v39);
          }
          goto LABEL_68;
        }
        v25 = 0;
        v26 = v15 - 1;
        if ( v26 )
        {
          v27 = v26 - 2;
          if ( v27 )
          {
            v28 = v27 - 2;
            if ( v28 )
            {
              if ( v28 == 2 )
                v25 = 5;
            }
            else
            {
              v25 = 3;
            }
          }
          else
          {
            v25 = 1;
          }
        }
        v15 = v25;
        if ( v25 >= LowerOplockLevelForUpperOplockRequest )
        {
          while ( 1 )
          {
            if ( !v51 )
              goto LABEL_60;
            Iopb = v51->Iopb;
            LowPart = Iopb->Parameters.Read.ByteOffset.LowPart;
            Parameters = Iopb->Parameters.CreatePipe.Parameters;
            if ( LowPart == 590400 && !Parameters[1] )
            {
              v32 = 1;
              goto LABEL_51;
            }
            v32 = 1;
            if ( !v15 )
              goto LABEL_50;
            if ( v15 == 1 )
              break;
            if ( v15 == 3 )
            {
              if ( LowPart == 590400 )
              {
                v33 = ((Parameters[1] - 1) & 0xFFFFFFFD) == 0;
LABEL_48:
                if ( v33 )
                  goto LABEL_51;
              }
              goto LABEL_49;
            }
            if ( LowPart == 590400 && ((Parameters[1] - 3) & 0xFFFFFFFB) == 0 || LowPart == 589832 )
              goto LABEL_50;
LABEL_51:
            if ( !v32 )
            {
              v34 = 0;
              v35 = v15 - 1;
              if ( v35 )
              {
                v36 = v35 - 2;
                if ( v36 )
                {
                  v37 = v36 - 2;
                  if ( v37 )
                  {
                    if ( v37 == 2 )
                      v34 = 5;
                  }
                  else
                  {
                    v34 = 3;
                  }
                }
                else
                {
                  v34 = 1;
                }
              }
              v15 = v34;
              if ( v34 >= LowerOplockLevelForUpperOplockRequest )
                continue;
            }
            goto LABEL_60;
          }
          if ( LowPart == 590400 )
          {
            v33 = Parameters[1] == 1;
            goto LABEL_48;
          }
LABEL_49:
          if ( LowPart == 589828 )
            goto LABEL_51;
LABEL_50:
          v32 = 0;
          goto LABEL_51;
        }
      }
LABEL_60:
      v38 = Entry[0];
      if ( Entry[0] )
      {
        UnionFs::Utils::RequestOplockContext::~RequestOplockContext((UnionFs::Utils::RequestOplockContext *)Entry[0]);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 27, v38);
      }
      if ( v24 != -1073741598 )
      {
        if ( v24 < 0 )
        {
LABEL_68:
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v24,
            (int)a2,
            (struct UnionFs::StackEventTracer *)0x6C0001D0598LL,
            (unsigned __int64)"UnionFs::UfsShadowFileObject::RequestLowerOplockImpl",
            "PUSH: Could not get minimum lower oplock",
            v43);
          if ( v49[1] )
            utl::_RefCountBase::_DecStrong(v49[1]);
          return (unsigned int)v24;
        }
        v41 = v48;
        FsFltWil::AcquireFastMutex(&Object, *(_QWORD *)(v48 + 120) + 216LL);
        v42 = (struct _FAST_MUTEX *)Object;
        *(_DWORD *)(v41 + 216) = v15;
        if ( v42 )
          ExReleaseFastMutex(v42);
        goto LABEL_73;
      }
      if ( v15 < LowerOplockLevelForUpperOplockRequest )
        goto LABEL_68;
      v4 = v47;
    }
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a2,
      (struct UnionFs::StackEventTracer *)0x6EB002125F3LL,
      (unsigned __int64)"UnionFs::Utils::RequestOplockContext::AllocAndInit",
      "ORIGIN: Allocating oplock context work item",
      v43);
    goto LABEL_78;
  }
LABEL_73:
  if ( v49[1] )
    utl::_RefCountBase::_DecStrong(v49[1]);
  return 0;
}

```

## disassembly

```asm
0x140058bb0  mov     [rsp-38h+arg_8], rbx
0x140058bb5  mov     [rsp-38h+arg_10], r8
0x140058bba  mov     [rsp-38h+Object], rcx
0x140058bbf  push    rbp
0x140058bc0  push    rsi
0x140058bc1  push    rdi
0x140058bc2  push    r12
0x140058bc4  push    r13
0x140058bc6  push    r14
0x140058bc8  push    r15
0x140058bca  mov     rbp, rsp
0x140058bcd  sub     rsp, 80h
0x140058bd4  mov     r15, [rcx+20h]
0x140058bd8  mov     rdi, r9
0x140058bdb  mov     r12, r8
0x140058bde  mov     [rbp+var_28], r15
0x140058be2  mov     rsi, rdx
0x140058be5  mov     eax, [r15+28h]
0x140058be9  test    al, 8
0x140058beb  jz      loc_1400590ED
0x140058bf1  mov     r14, [rcx+18h]
0x140058bf5  xorps   xmm0, xmm0
0x140058bf8  mov     r8, rdx
0x140058bfb  mov     [rbp+var_20], r14
0x140058bff  lea     rdx, [rbp+var_18]
0x140058c03  mov     rcx, r15
0x140058c06  movdqu  xmmword ptr [rbp+var_18], xmm0
0x140058c0b  call    ?TryGetBackingLayer@UfsFsContext2@UnionFs@@QEBAJAEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext2::TryGetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx> &,UnionFs::StackEventTracer &)
0x140058c10  mov     ebx, eax
0x140058c12  test    eax, eax
0x140058c14  jns     short loc_140058C54
0x140058c16  lea     rax, aPushNoBackingL; "PUSH: No backing layer"
0x140058c1d  mov     r8, 6E7001D0533h; struct UnionFs::StackEventTracer *
0x140058c27  lea     r9, aUnionfsUfsshad_0; "UnionFs::UfsShadowFileObject::RequestLo"...
0x140058c2e  mov     [rsp+80h+var_60], rax; char *
0x140058c33  mov     rdx, rsi; int
0x140058c36  mov     ecx, ebx; this
0x140058c38  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058c3d  mov     rcx, [rbp+var_18+8]; this
0x140058c41  test    rcx, rcx
0x140058c44  jz      loc_140059116
0x140058c4a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058c4f  jmp     loc_140059116
0x140058c54  test    r12, r12
0x140058c57  jz      short loc_140058C66
0x140058c59  mov     rcx, r12; this
0x140058c5c  call    ?GetLowerOplockLevelForUpperOplockRequest@Utils@UnionFs@@YAKAEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::GetLowerOplockLevelForUpperOplockRequest(_FLT_CALLBACK_DATA const &)
0x140058c61  mov     r13d, eax
0x140058c64  jmp     short loc_140058C69
0x140058c66  mov     r13d, [rdi]
0x140058c69  mov     rdx, [r14+78h]
0x140058c6d  lea     rcx, [rbp+FastMutex]
0x140058c71  add     rdx, 0D8h
0x140058c78  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140058c7d  mov     rcx, [rbp+FastMutex]; FastMutex
0x140058c81  mov     ebx, [r14+0D8h]
0x140058c88  test    rcx, rcx
0x140058c8b  jz      short loc_140058C99
0x140058c8d  call    cs:__imp_ExReleaseFastMutex
0x140058c94  nop     dword ptr [rax+rax+00h]
0x140058c99  cmp     ebx, r13d
0x140058c9c  jnb     loc_140058FD7
0x140058ca2  test    rdi, rdi
0x140058ca5  jz      short loc_140058CAB
0x140058ca7  mov     edi, [rdi]
0x140058ca9  jmp     short loc_140058CB6
0x140058cab  test    ebx, ebx
0x140058cad  mov     edi, 7
0x140058cb2  cmovnz  edi, r13d
0x140058cb6  mov     rcx, [rbp+Object]
0x140058cba  lea     rdx, [rbp+Entry]
0x140058cbe  xorps   xmm0, xmm0
0x140058cc1  mov     r8, rsi
0x140058cc4  movdqu  xmmword ptr [rbp+Entry], xmm0
0x140058cc9  mov     rcx, [rcx+20h]
0x140058ccd  call    ?TryGetBackingLayer@UfsFsContext2@UnionFs@@QEBAJAEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext2::TryGetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx> &,UnionFs::StackEventTracer &)
0x140058cd2  mov     ebx, eax
0x140058cd4  test    eax, eax
0x140058cd6  js      loc_1400590A2
0x140058cdc  mov     rax, [rbp+Entry]
0x140058ce0  mov     rbx, [rax+8]
0x140058ce4  mov     rbx, [rbx]
0x140058ce7  mov     rcx, rbx; FltObject
0x140058cea  call    cs:__imp_FltObjectReference
0x140058cf1  nop     dword ptr [rax+rax+00h]
0x140058cf6  mov     rcx, [rbp+Entry+8]; this
0x140058cfa  test    rcx, rcx
0x140058cfd  jz      short loc_140058D04
0x140058cff  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058d04  lea     rdx, [r15+20h]
0x140058d08  lea     rcx, [rbp+FastMutex]
0x140058d0c  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140058d11  mov     rcx, [rbp+FastMutex]; this
0x140058d15  mov     r12, [r15+18h]
0x140058d19  mov     [rbp+FastMutex], 0
0x140058d21  test    rcx, rcx
0x140058d24  jz      short loc_140058D2B
0x140058d26  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140058d2b  call    cs:__imp_FltAllocateGenericWorkItem
0x140058d32  nop     dword ptr [rax+rax+00h]
0x140058d37  mov     r15, rax
0x140058d3a  test    rax, rax
0x140058d3d  jz      loc_140059029
0x140058d43  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140058d4a  add     rcx, 0A20h; Lookaside
0x140058d51  call    cs:__imp_ExAllocateFromLookasideListEx
0x140058d58  nop     dword ptr [rax+rax+00h]
0x140058d5d  mov     r14, rax
0x140058d60  test    rax, rax
0x140058d63  jz      loc_140058FEC
0x140058d69  mov     rcx, [rbp+Object]; Object
0x140058d6d  call    cs:__imp_ObfReferenceObject
0x140058d74  nop     dword ptr [rax+rax+00h]
0x140058d79  mov     rax, [rbp+Object]
0x140058d7d  mov     rcx, r12; Object
0x140058d80  mov     [r14], rax
0x140058d83  mov     [r14+8], rbx
0x140058d87  call    cs:__imp_ObfReferenceObject
0x140058d8e  nop     dword ptr [rax+rax+00h]
0x140058d93  mov     [r14+10h], r12
0x140058d97  xor     eax, eax
0x140058d99  mov     [r14+18h], rax
0x140058d9d  mov     r9d, edi
0x140058da0  mov     [r14+28h], rax
0x140058da4  lea     rax, [rbp+Entry]
0x140058da8  mov     [r14+20h], r15
0x140058dac  mov     r8d, [r14+18h]
0x140058db0  mov     rdx, [r14+10h]; FileObject
0x140058db4  mov     rcx, [r14+8]; Instance
0x140058db8  mov     [rsp+80h+var_58], rsi; char *
0x140058dbd  mov     [rsp+80h+var_60], rax; __int64
0x140058dc2  mov     [rbp+Entry], r14
0x140058dc6  call    ?RequestOplock@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@W4RequestOplockOperation@12@K$$QEAV?$unique_ptr@VRequestOplockContext@Utils@UnionFs@@U?$default_delete@VRequestOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z; UnionFs::Utils::RequestOplock(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::Utils::RequestOplockOperation,ulong,utl::unique_ptr<UnionFs::Utils::RequestOplockContext,utl::default_delete<UnionFs::Utils::RequestOplockContext>> &&,UnionFs::StackEventTracer &,ulong)
0x140058dcb  xor     ebx, ebx
0x140058dcd  mov     r15d, eax
0x140058dd0  cmp     eax, 0C00000E2h
0x140058dd5  jnz     loc_140058ED8
0x140058ddb  cmp     edi, r13d
0x140058dde  jbe     loc_140058F31
0x140058de4  xor     edx, edx
0x140058de6  xor     ecx, ecx
0x140058de8  sub     edi, 1
0x140058deb  jz      short loc_140058E0D
0x140058ded  sub     edi, 2
0x140058df0  jz      short loc_140058E08
0x140058df2  sub     edi, 2
0x140058df5  jz      short loc_140058E01
0x140058df7  cmp     edi, 2
0x140058dfa  jnz     short loc_140058E0D
0x140058dfc  lea     ecx, [rbx+5]
0x140058dff  jmp     short loc_140058E0D
0x140058e01  mov     ecx, 3
0x140058e06  jmp     short loc_140058E0D
0x140058e08  mov     ecx, 1
0x140058e0d  mov     edi, ecx
0x140058e0f  cmp     ecx, r13d
0x140058e12  jb      loc_140058ED8
0x140058e18  mov     r12, [rbp+arg_10]
0x140058e1c  mov     r9d, 90240h
0x140058e22  test    r12, r12
0x140058e25  jz      loc_140058ED8
0x140058e2b  mov     rax, [r12+10h]
0x140058e30  mov     ecx, [rax+28h]
0x140058e33  mov     r8, [rax+30h]
0x140058e37  cmp     ecx, r9d
0x140058e3a  jnz     short loc_140058E46
0x140058e3c  cmp     [r8+4], ebx
0x140058e40  jnz     short loc_140058E46
0x140058e42  mov     dl, 1
0x140058e44  jmp     short loc_140058EA2
0x140058e46  mov     dl, 1
0x140058e48  mov     eax, edi
0x140058e4a  test    edi, edi
0x140058e4c  jz      short loc_140058EA0
0x140058e4e  sub     eax, 1
0x140058e51  jz      short loc_140058E8C
0x140058e53  sub     eax, 2
0x140058e56  jz      short loc_140058E7A
0x140058e58  cmp     eax, 2
0x140058e5b  jnz     short loc_140058EA2
0x140058e5d  cmp     ecx, r9d
0x140058e60  jnz     short loc_140058E70
0x140058e62  mov     eax, [r8+4]
0x140058e66  sub     eax, 3
0x140058e69  test    eax, 0FFFFFFFBh
0x140058e6e  jz      short loc_140058EA0
0x140058e70  cmp     ecx, 90008h
0x140058e76  jnz     short loc_140058EA2
0x140058e78  jmp     short loc_140058EA0
0x140058e7a  cmp     ecx, r9d
0x140058e7d  jnz     short loc_140058E98
0x140058e7f  mov     eax, [r8+4]
0x140058e83  dec     eax
0x140058e85  test    eax, 0FFFFFFFDh
0x140058e8a  jmp     short loc_140058E96
0x140058e8c  cmp     ecx, r9d
0x140058e8f  jnz     short loc_140058E98
0x140058e91  cmp     dword ptr [r8+4], 1
0x140058e96  jz      short loc_140058EA2
0x140058e98  cmp     ecx, 90004h
0x140058e9e  jz      short loc_140058EA2
0x140058ea0  xor     dl, dl
0x140058ea2  test    dl, dl
0x140058ea4  jnz     short loc_140058ED8
0x140058ea6  xor     eax, eax
0x140058ea8  sub     edi, 1
0x140058eab  jz      short loc_140058ECD
0x140058ead  sub     edi, 2
0x140058eb0  jz      short loc_140058EC8
0x140058eb2  sub     edi, 2
0x140058eb5  jz      short loc_140058EC1
0x140058eb7  cmp     edi, 2
0x140058eba  jnz     short loc_140058ECD
0x140058ebc  lea     eax, [rdi+3]
0x140058ebf  jmp     short loc_140058ECD
0x140058ec1  mov     eax, 3
0x140058ec6  jmp     short loc_140058ECD
0x140058ec8  mov     eax, 1
0x140058ecd  mov     edi, eax
0x140058ecf  cmp     eax, r13d
0x140058ed2  jnb     loc_140058E22
0x140058ed8  mov     r14, [rbp+Entry]
0x140058edc  test    r14, r14
0x140058edf  jz      short loc_140058F06
0x140058ee1  mov     rcx, r14; this
0x140058ee4  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140058ee9  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140058ef0  mov     rdx, r14; Entry
0x140058ef3  add     rcx, 0A20h; Lookaside
0x140058efa  call    cs:__imp_ExFreeToLookasideListEx
0x140058f01  nop     dword ptr [rax+rax+00h]
0x140058f06  test    rbx, rbx
0x140058f09  jz      short loc_140058F1A
0x140058f0b  mov     rcx, rbx; FltObject
0x140058f0e  call    cs:__imp_FltObjectDereference
0x140058f15  nop     dword ptr [rax+rax+00h]
0x140058f1a  cmp     r15d, 0C00000E2h
0x140058f21  jnz     short loc_140058F61
0x140058f23  cmp     edi, r13d
0x140058f26  jb      short loc_140058F66
0x140058f28  mov     r15, [rbp+var_28]
0x140058f2c  jmp     loc_140058CB6
0x140058f31  mov     rbx, [rbp+Entry]
0x140058f35  test    rbx, rbx
0x140058f38  jz      short loc_140058F66
0x140058f3a  mov     rcx, rbx; this
0x140058f3d  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140058f42  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140058f49  mov     rdx, rbx; Entry
0x140058f4c  add     rcx, 0A20h; Lookaside
0x140058f53  call    cs:__imp_ExFreeToLookasideListEx
0x140058f5a  nop     dword ptr [rax+rax+00h]
0x140058f5f  jmp     short loc_140058F66
0x140058f61  test    r15d, r15d
0x140058f64  jns     short loc_140058FA4
0x140058f66  lea     rax, aPushCouldNotGe_0; "PUSH: Could not get minimum lower oploc"...
0x140058f6d  mov     r8, 6C0001D0598h; struct UnionFs::StackEventTracer *
0x140058f77  lea     r9, aUnionfsUfsshad_0; "UnionFs::UfsShadowFileObject::RequestLo"...
0x140058f7e  mov     [rsp+80h+var_60], rax; char *
0x140058f83  mov     rdx, rsi; int
0x140058f86  mov     ecx, r15d; this
0x140058f89  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058f8e  mov     rcx, [rbp+var_18+8]; this
0x140058f92  test    rcx, rcx
0x140058f95  jz      short loc_140058F9C
0x140058f97  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058f9c  mov     eax, r15d
0x140058f9f  jmp     loc_140059118
0x140058fa4  mov     rbx, [rbp+var_20]
0x140058fa8  lea     rcx, [rbp+Object]
0x140058fac  mov     rdx, [rbx+78h]
0x140058fb0  add     rdx, 0D8h
0x140058fb7  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140058fbc  mov     rcx, [rbp+Object]; FastMutex
0x140058fc0  mov     [rbx+0D8h], edi
0x140058fc6  test    rcx, rcx
0x140058fc9  jz      short loc_140058FD7
0x140058fcb  call    cs:__imp_ExReleaseFastMutex
0x140058fd2  nop     dword ptr [rax+rax+00h]
0x140058fd7  mov     rcx, [rbp+var_18+8]; this
0x140058fdb  test    rcx, rcx
0x140058fde  jz      short loc_140058FE5
0x140058fe0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058fe5  xor     eax, eax
0x140058fe7  jmp     loc_140059118
0x140058fec  lea     rax, aOriginAllocati_34; "ORIGIN: Allocating RequestOplockContext"
0x140058ff3  mov     edi, 0C000009Ah
0x140058ff8  mov     ecx, edi; this
0x140058ffa  mov     [rsp+80h+var_60], rax; char *
0x140058fff  lea     r9, aUnionfsUtilsRe_6; "UnionFs::Utils::RequestOplockContext::A"...
0x140059006  mov     r8, 6EC00212601h; struct UnionFs::StackEventTracer *
0x140059010  mov     rdx, rsi; int
0x140059013  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140059018  mov     rcx, r15; FltWorkItem
0x14005901b  call    cs:__imp_FltFreeGenericWorkItem
0x140059022  nop     dword ptr [rax+rax+00h]
0x140059027  jmp     short loc_140059055
0x140059029  lea     rax, aOriginAllocati_93; "ORIGIN: Allocating oplock context work "...
0x140059030  mov     edi, 0C000009Ah
0x140059035  mov     ecx, edi; this
  ... truncated ...
```
