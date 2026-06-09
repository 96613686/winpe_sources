# UnionFs::UfsShadowFileObject::RequestLowerOplockImpl(UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *,ulong *)

- ea: `0x140058a30`
- end: `0x140058fb4`
- name: `?RequestLowerOplockImpl@UfsShadowFileObject@UnionFs@@AEBAJAEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@PEAK@Z`
- size: `1412`
- prototype: `int(UnionFs::UfsShadowFileObject *__hidden this, struct UnionFs::StackEventTracer *, const struct _FLT_CALLBACK_DATA *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x14000a398`
- `0x14002a6b8`

## callees

- `0x14000f7fc`
- `0x140056ac4`
- `0x140056afc`
- `0x1400579a4`
- `0x140058a30`
- `0x140059f6c`
- `0x14006ef34`
- `0x140076660`
- `0x1400799a4`
- `0x140079a24`
- `0x140079da0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140058d7a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140058dd3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140058d7a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140058dd3`
- `ntoskrnl!ObfReferenceObject` at `0x140058bed`
- `ntoskrnl!ObfReferenceObject` at `0x140058c07`
- `ntoskrnl!ObfReferenceObject` at `0x140058bed`
- `ntoskrnl!ObfReferenceObject` at `0x140058c07`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058b0d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058e4b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058b0d`
- `ntoskrnl!ExReleaseFastMutex` at `0x140058e4b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140058bd1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140058bd1`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140058e9b`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140058e9b`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140058bab`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x140058bab`
- `FLTMGR!FltObjectReference` at `0x140058b6a`
- `FLTMGR!FltObjectReference` at `0x140058b6a`
- `FLTMGR!FltObjectDereference` at `0x140058d8e`
- `FLTMGR!FltObjectDereference` at `0x140058f04`
- `FLTMGR!FltObjectDereference` at `0x140058d8e`
- `FLTMGR!FltObjectDereference` at `0x140058f04`

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
          (struct UnionFs::StackEventTracer *)0x6EC002125CBLL,
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
      (struct UnionFs::StackEventTracer *)0x6EB002125BDLL,
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
0x140058a30  mov     [rsp-38h+arg_8], rbx
0x140058a35  mov     [rsp-38h+arg_10], r8
0x140058a3a  mov     [rsp-38h+Object], rcx
0x140058a3f  push    rbp
0x140058a40  push    rsi
0x140058a41  push    rdi
0x140058a42  push    r12
0x140058a44  push    r13
0x140058a46  push    r14
0x140058a48  push    r15
0x140058a4a  mov     rbp, rsp
0x140058a4d  sub     rsp, 80h
0x140058a54  mov     r15, [rcx+20h]
0x140058a58  mov     rdi, r9
0x140058a5b  mov     r12, r8
0x140058a5e  mov     [rbp+var_28], r15
0x140058a62  mov     rsi, rdx
0x140058a65  mov     eax, [r15+28h]
0x140058a69  test    al, 8
0x140058a6b  jz      loc_140058F6D
0x140058a71  mov     r14, [rcx+18h]
0x140058a75  xorps   xmm0, xmm0
0x140058a78  mov     r8, rdx
0x140058a7b  mov     [rbp+var_20], r14
0x140058a7f  lea     rdx, [rbp+var_18]
0x140058a83  mov     rcx, r15
0x140058a86  movdqu  xmmword ptr [rbp+var_18], xmm0
0x140058a8b  call    ?TryGetBackingLayer@UfsFsContext2@UnionFs@@QEBAJAEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext2::TryGetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx> &,UnionFs::StackEventTracer &)
0x140058a90  mov     ebx, eax
0x140058a92  test    eax, eax
0x140058a94  jns     short loc_140058AD4
0x140058a96  lea     rax, aPushNoBackingL; "PUSH: No backing layer"
0x140058a9d  mov     r8, 6E7001D0533h; struct UnionFs::StackEventTracer *
0x140058aa7  lea     r9, aUnionfsUfsshad_0; "UnionFs::UfsShadowFileObject::RequestLo"...
0x140058aae  mov     [rsp+80h+var_60], rax; char *
0x140058ab3  mov     rdx, rsi; int
0x140058ab6  mov     ecx, ebx; this
0x140058ab8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058abd  mov     rcx, [rbp+var_18+8]; this
0x140058ac1  test    rcx, rcx
0x140058ac4  jz      loc_140058F96
0x140058aca  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058acf  jmp     loc_140058F96
0x140058ad4  test    r12, r12
0x140058ad7  jz      short loc_140058AE6
0x140058ad9  mov     rcx, r12; this
0x140058adc  call    ?GetLowerOplockLevelForUpperOplockRequest@Utils@UnionFs@@YAKAEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::GetLowerOplockLevelForUpperOplockRequest(_FLT_CALLBACK_DATA const &)
0x140058ae1  mov     r13d, eax
0x140058ae4  jmp     short loc_140058AE9
0x140058ae6  mov     r13d, [rdi]
0x140058ae9  mov     rdx, [r14+78h]
0x140058aed  lea     rcx, [rbp+FastMutex]
0x140058af1  add     rdx, 0D8h
0x140058af8  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140058afd  mov     rcx, [rbp+FastMutex]; FastMutex
0x140058b01  mov     ebx, [r14+0D8h]
0x140058b08  test    rcx, rcx
0x140058b0b  jz      short loc_140058B19
0x140058b0d  call    cs:__imp_ExReleaseFastMutex
0x140058b14  nop     dword ptr [rax+rax+00h]
0x140058b19  cmp     ebx, r13d
0x140058b1c  jnb     loc_140058E57
0x140058b22  test    rdi, rdi
0x140058b25  jz      short loc_140058B2B
0x140058b27  mov     edi, [rdi]
0x140058b29  jmp     short loc_140058B36
0x140058b2b  test    ebx, ebx
0x140058b2d  mov     edi, 7
0x140058b32  cmovnz  edi, r13d
0x140058b36  mov     rcx, [rbp+Object]
0x140058b3a  lea     rdx, [rbp+Entry]
0x140058b3e  xorps   xmm0, xmm0
0x140058b41  mov     r8, rsi
0x140058b44  movdqu  xmmword ptr [rbp+Entry], xmm0
0x140058b49  mov     rcx, [rcx+20h]
0x140058b4d  call    ?TryGetBackingLayer@UfsFsContext2@UnionFs@@QEBAJAEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsFsContext2::TryGetBackingLayer(utl::shared_ptr<UnionFs::UfsLayerCtx> &,UnionFs::StackEventTracer &)
0x140058b52  mov     ebx, eax
0x140058b54  test    eax, eax
0x140058b56  js      loc_140058F22
0x140058b5c  mov     rax, [rbp+Entry]
0x140058b60  mov     rbx, [rax+8]
0x140058b64  mov     rbx, [rbx]
0x140058b67  mov     rcx, rbx; FltObject
0x140058b6a  call    cs:__imp_FltObjectReference
0x140058b71  nop     dword ptr [rax+rax+00h]
0x140058b76  mov     rcx, [rbp+Entry+8]; this
0x140058b7a  test    rcx, rcx
0x140058b7d  jz      short loc_140058B84
0x140058b7f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058b84  lea     rdx, [r15+20h]
0x140058b88  lea     rcx, [rbp+FastMutex]
0x140058b8c  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140058b91  mov     rcx, [rbp+FastMutex]; this
0x140058b95  mov     r12, [r15+18h]
0x140058b99  mov     [rbp+FastMutex], 0
0x140058ba1  test    rcx, rcx
0x140058ba4  jz      short loc_140058BAB
0x140058ba6  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140058bab  call    cs:__imp_FltAllocateGenericWorkItem
0x140058bb2  nop     dword ptr [rax+rax+00h]
0x140058bb7  mov     r15, rax
0x140058bba  test    rax, rax
0x140058bbd  jz      loc_140058EA9
0x140058bc3  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140058bca  add     rcx, 0A20h; Lookaside
0x140058bd1  call    cs:__imp_ExAllocateFromLookasideListEx
0x140058bd8  nop     dword ptr [rax+rax+00h]
0x140058bdd  mov     r14, rax
0x140058be0  test    rax, rax
0x140058be3  jz      loc_140058E6C
0x140058be9  mov     rcx, [rbp+Object]; Object
0x140058bed  call    cs:__imp_ObfReferenceObject
0x140058bf4  nop     dword ptr [rax+rax+00h]
0x140058bf9  mov     rax, [rbp+Object]
0x140058bfd  mov     rcx, r12; Object
0x140058c00  mov     [r14], rax
0x140058c03  mov     [r14+8], rbx
0x140058c07  call    cs:__imp_ObfReferenceObject
0x140058c0e  nop     dword ptr [rax+rax+00h]
0x140058c13  mov     [r14+10h], r12
0x140058c17  xor     eax, eax
0x140058c19  mov     [r14+18h], rax
0x140058c1d  mov     r9d, edi
0x140058c20  mov     [r14+28h], rax
0x140058c24  lea     rax, [rbp+Entry]
0x140058c28  mov     [r14+20h], r15
0x140058c2c  mov     r8d, [r14+18h]
0x140058c30  mov     rdx, [r14+10h]; FileObject
0x140058c34  mov     rcx, [r14+8]; Instance
0x140058c38  mov     [rsp+80h+var_58], rsi; char *
0x140058c3d  mov     [rsp+80h+var_60], rax; __int64
0x140058c42  mov     [rbp+Entry], r14
0x140058c46  call    ?RequestOplock@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@W4RequestOplockOperation@12@K$$QEAV?$unique_ptr@VRequestOplockContext@Utils@UnionFs@@U?$default_delete@VRequestOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z; UnionFs::Utils::RequestOplock(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::Utils::RequestOplockOperation,ulong,utl::unique_ptr<UnionFs::Utils::RequestOplockContext,utl::default_delete<UnionFs::Utils::RequestOplockContext>> &&,UnionFs::StackEventTracer &,ulong)
0x140058c4b  xor     ebx, ebx
0x140058c4d  mov     r15d, eax
0x140058c50  cmp     eax, 0C00000E2h
0x140058c55  jnz     loc_140058D58
0x140058c5b  cmp     edi, r13d
0x140058c5e  jbe     loc_140058DB1
0x140058c64  xor     edx, edx
0x140058c66  xor     ecx, ecx
0x140058c68  sub     edi, 1
0x140058c6b  jz      short loc_140058C8D
0x140058c6d  sub     edi, 2
0x140058c70  jz      short loc_140058C88
0x140058c72  sub     edi, 2
0x140058c75  jz      short loc_140058C81
0x140058c77  cmp     edi, 2
0x140058c7a  jnz     short loc_140058C8D
0x140058c7c  lea     ecx, [rbx+5]
0x140058c7f  jmp     short loc_140058C8D
0x140058c81  mov     ecx, 3
0x140058c86  jmp     short loc_140058C8D
0x140058c88  mov     ecx, 1
0x140058c8d  mov     edi, ecx
0x140058c8f  cmp     ecx, r13d
0x140058c92  jb      loc_140058D58
0x140058c98  mov     r12, [rbp+arg_10]
0x140058c9c  mov     r9d, 90240h
0x140058ca2  test    r12, r12
0x140058ca5  jz      loc_140058D58
0x140058cab  mov     rax, [r12+10h]
0x140058cb0  mov     ecx, [rax+28h]
0x140058cb3  mov     r8, [rax+30h]
0x140058cb7  cmp     ecx, r9d
0x140058cba  jnz     short loc_140058CC6
0x140058cbc  cmp     [r8+4], ebx
0x140058cc0  jnz     short loc_140058CC6
0x140058cc2  mov     dl, 1
0x140058cc4  jmp     short loc_140058D22
0x140058cc6  mov     dl, 1
0x140058cc8  mov     eax, edi
0x140058cca  test    edi, edi
0x140058ccc  jz      short loc_140058D20
0x140058cce  sub     eax, 1
0x140058cd1  jz      short loc_140058D0C
0x140058cd3  sub     eax, 2
0x140058cd6  jz      short loc_140058CFA
0x140058cd8  cmp     eax, 2
0x140058cdb  jnz     short loc_140058D22
0x140058cdd  cmp     ecx, r9d
0x140058ce0  jnz     short loc_140058CF0
0x140058ce2  mov     eax, [r8+4]
0x140058ce6  sub     eax, 3
0x140058ce9  test    eax, 0FFFFFFFBh
0x140058cee  jz      short loc_140058D20
0x140058cf0  cmp     ecx, 90008h
0x140058cf6  jnz     short loc_140058D22
0x140058cf8  jmp     short loc_140058D20
0x140058cfa  cmp     ecx, r9d
0x140058cfd  jnz     short loc_140058D18
0x140058cff  mov     eax, [r8+4]
0x140058d03  dec     eax
0x140058d05  test    eax, 0FFFFFFFDh
0x140058d0a  jmp     short loc_140058D16
0x140058d0c  cmp     ecx, r9d
0x140058d0f  jnz     short loc_140058D18
0x140058d11  cmp     dword ptr [r8+4], 1
0x140058d16  jz      short loc_140058D22
0x140058d18  cmp     ecx, 90004h
0x140058d1e  jz      short loc_140058D22
0x140058d20  xor     dl, dl
0x140058d22  test    dl, dl
0x140058d24  jnz     short loc_140058D58
0x140058d26  xor     eax, eax
0x140058d28  sub     edi, 1
0x140058d2b  jz      short loc_140058D4D
0x140058d2d  sub     edi, 2
0x140058d30  jz      short loc_140058D48
0x140058d32  sub     edi, 2
0x140058d35  jz      short loc_140058D41
0x140058d37  cmp     edi, 2
0x140058d3a  jnz     short loc_140058D4D
0x140058d3c  lea     eax, [rdi+3]
0x140058d3f  jmp     short loc_140058D4D
0x140058d41  mov     eax, 3
0x140058d46  jmp     short loc_140058D4D
0x140058d48  mov     eax, 1
0x140058d4d  mov     edi, eax
0x140058d4f  cmp     eax, r13d
0x140058d52  jnb     loc_140058CA2
0x140058d58  mov     r14, [rbp+Entry]
0x140058d5c  test    r14, r14
0x140058d5f  jz      short loc_140058D86
0x140058d61  mov     rcx, r14; this
0x140058d64  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140058d69  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140058d70  mov     rdx, r14; Entry
0x140058d73  add     rcx, 0A20h; Lookaside
0x140058d7a  call    cs:__imp_ExFreeToLookasideListEx
0x140058d81  nop     dword ptr [rax+rax+00h]
0x140058d86  test    rbx, rbx
0x140058d89  jz      short loc_140058D9A
0x140058d8b  mov     rcx, rbx; FltObject
0x140058d8e  call    cs:__imp_FltObjectDereference
0x140058d95  nop     dword ptr [rax+rax+00h]
0x140058d9a  cmp     r15d, 0C00000E2h
0x140058da1  jnz     short loc_140058DE1
0x140058da3  cmp     edi, r13d
0x140058da6  jb      short loc_140058DE6
0x140058da8  mov     r15, [rbp+var_28]
0x140058dac  jmp     loc_140058B36
0x140058db1  mov     rbx, [rbp+Entry]
0x140058db5  test    rbx, rbx
0x140058db8  jz      short loc_140058DE6
0x140058dba  mov     rcx, rbx; this
0x140058dbd  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140058dc2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140058dc9  mov     rdx, rbx; Entry
0x140058dcc  add     rcx, 0A20h; Lookaside
0x140058dd3  call    cs:__imp_ExFreeToLookasideListEx
0x140058dda  nop     dword ptr [rax+rax+00h]
0x140058ddf  jmp     short loc_140058DE6
0x140058de1  test    r15d, r15d
0x140058de4  jns     short loc_140058E24
0x140058de6  lea     rax, aPushCouldNotGe_0; "PUSH: Could not get minimum lower oploc"...
0x140058ded  mov     r8, 6C0001D0598h; struct UnionFs::StackEventTracer *
0x140058df7  lea     r9, aUnionfsUfsshad_0; "UnionFs::UfsShadowFileObject::RequestLo"...
0x140058dfe  mov     [rsp+80h+var_60], rax; char *
0x140058e03  mov     rdx, rsi; int
0x140058e06  mov     ecx, r15d; this
0x140058e09  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058e0e  mov     rcx, [rbp+var_18+8]; this
0x140058e12  test    rcx, rcx
0x140058e15  jz      short loc_140058E1C
0x140058e17  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058e1c  mov     eax, r15d
0x140058e1f  jmp     loc_140058F98
0x140058e24  mov     rbx, [rbp+var_20]
0x140058e28  lea     rcx, [rbp+Object]
0x140058e2c  mov     rdx, [rbx+78h]
0x140058e30  add     rdx, 0D8h
0x140058e37  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140058e3c  mov     rcx, [rbp+Object]; FastMutex
0x140058e40  mov     [rbx+0D8h], edi
0x140058e46  test    rcx, rcx
0x140058e49  jz      short loc_140058E57
0x140058e4b  call    cs:__imp_ExReleaseFastMutex
0x140058e52  nop     dword ptr [rax+rax+00h]
0x140058e57  mov     rcx, [rbp+var_18+8]; this
0x140058e5b  test    rcx, rcx
0x140058e5e  jz      short loc_140058E65
0x140058e60  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140058e65  xor     eax, eax
0x140058e67  jmp     loc_140058F98
0x140058e6c  lea     rax, aOriginAllocati_34; "ORIGIN: Allocating RequestOplockContext"
0x140058e73  mov     edi, 0C000009Ah
0x140058e78  mov     ecx, edi; this
0x140058e7a  mov     [rsp+80h+var_60], rax; char *
0x140058e7f  lea     r9, aUnionfsUtilsRe_6; "UnionFs::Utils::RequestOplockContext::A"...
0x140058e86  mov     r8, 6EC002125CBh; struct UnionFs::StackEventTracer *
0x140058e90  mov     rdx, rsi; int
0x140058e93  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140058e98  mov     rcx, r15; FltWorkItem
0x140058e9b  call    cs:__imp_FltFreeGenericWorkItem
0x140058ea2  nop     dword ptr [rax+rax+00h]
0x140058ea7  jmp     short loc_140058ED5
0x140058ea9  lea     rax, aOriginAllocati_92; "ORIGIN: Allocating oplock context work "...
0x140058eb0  mov     edi, 0C000009Ah
0x140058eb5  mov     ecx, edi; this
  ... truncated ...
```
