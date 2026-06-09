# UnionFs::UfsLayerCtx::AllocAndInitShared(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,int,utl::shared_ptr<UnionFs::UfsLayerCtx> &,UnionFs::StackEventTracer &)

- ea: `0x140035f78`
- end: `0x14003625f`
- name: `?AllocAndInitShared@UfsLayerCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@HAEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `743`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PCUNICODE_STRING SourceString@<rdx>, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x14005e5ec`

## callees

- `0x14000f81c`
- `0x140027764`
- `0x140035e54`
- `0x140035f78`
- `0x1400448c8`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079c90`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400361f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400361f1`
- `ntoskrnl!ExAllocatePool2` at `0x14003602a`
- `ntoskrnl!ExAllocatePool2` at `0x14003602a`
- `ntoskrnl!ExUuidCreate` at `0x140036107`
- `ntoskrnl!ExUuidCreate` at `0x140036107`
- `FLTMGR!FltReleaseContext` at `0x140036155`
- `FLTMGR!FltReleaseContext` at `0x1400361cd`
- `FLTMGR!FltReleaseContext` at `0x140036243`
- `FLTMGR!FltReleaseContext` at `0x140036155`
- `FLTMGR!FltReleaseContext` at `0x1400361cd`
- `FLTMGR!FltReleaseContext` at `0x140036243`

## string_xrefs

- `0x14003618a`: `PUSH: Duplicating path name`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsLayerCtx::AllocAndInitShared(
        PFLT_INSTANCE Instance,
        PCUNICODE_STRING SourceString,
        int a3,
        __int64 *a4,
        int a5)
{
  utl::_RefCountBase *v6; // rcx
  unsigned int v10; // ebx
  __int64 Pool2; // rax
  const struct std::nothrow_t *v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rax
  volatile signed __int32 *v15; // rax
  utl::_RefCountBase *v16; // rdi
  volatile signed __int32 *v17; // rcx
  int v18; // ebp
  utl::_RefCountBase *v20; // rcx
  const char *v21; // [rsp+28h] [rbp-40h]

  *a4 = 0;
  v6 = (utl::_RefCountBase *)a4[1];
  a4[1] = 0;
  if ( v6 )
    utl::_RefCountBase::_DecStrong(v6);
  v10 = UnionFs::UfsInstanceCtx::FltGet(Instance);
  if ( (v10 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v10,
      a5,
      (struct UnionFs::StackEventTracer *)0x26000D004ALL,
      (unsigned __int64)"UnionFs::UfsLayerCtx::AllocAndInitShared",
      "PUSH: Getting instance context",
      v21);
    return v10;
  }
  Pool2 = ExAllocatePool2(66, 72, 1668040277);
  v13 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_QWORD *)(Pool2 + 16) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_QWORD *)(Pool2 + 40) = 0;
    *(_QWORD *)Pool2 = 0;
    *(_WORD *)(Pool2 + 24) = 2;
    *(_OWORD *)(Pool2 + 48) = 0;
    v14 = *(_QWORD *)(Pool2 + 8);
    *(_DWORD *)(v13 + 64) = a3;
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 44));
  }
  else
  {
    v13 = 0;
  }
  v15 = (volatile signed __int32 *)operator new(0x18u, v12);
  v16 = (utl::_RefCountBase *)v15;
  if ( !v15 )
  {
    v16 = 0;
    if ( v13 )
    {
      UnionFs::UfsLayerCtx::~UfsLayerCtx((UnionFs::UfsLayerCtx *)v13);
      ExFreePoolWithTag((PVOID)v13, 0);
    }
    goto LABEL_27;
  }
  *((_DWORD *)v15 + 2) = 1;
  *((_DWORD *)v15 + 3) = 1;
  *(_QWORD *)v15 = &utl::_RefCountVtable<utl::_RefCountNormal<UnionFs::UfsLayerCtx *,utl::default_delete<UnionFs::UfsLayerCtx>,utl::allocator<int>>,0>::`vftable';
  *((_QWORD *)v15 + 2) = v13;
  if ( !v13 )
  {
LABEL_27:
    v10 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x27000D0055LL,
      (unsigned __int64)"UnionFs::UfsLayerCtx::AllocAndInitShared",
      "ORIGIN: Allocating layer context",
      v21);
    if ( v16 )
      utl::_RefCountBase::_DecStrong(v16);
    return v10;
  }
  if ( !*(_QWORD *)v13 )
  {
    _InterlockedIncrement(v15 + 3);
LABEL_12:
    *(_QWORD *)v13 = v16;
    goto LABEL_17;
  }
  if ( !*(_DWORD *)(*(_QWORD *)v13 + 8LL) )
  {
    _InterlockedIncrement(v15 + 3);
    v17 = *(volatile signed __int32 **)v13;
    if ( *(_DWORD *)(*(_QWORD *)v13 + 12LL) == 1 || _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    goto LABEL_12;
  }
LABEL_17:
  v18 = ExUuidCreate((UUID *)(v13 + 48));
  if ( v18 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v18,
      a5,
      (struct UnionFs::StackEventTracer *)0x1AA000D005BLL,
      (unsigned __int64)"UnionFs::UfsLayerCtx::AllocAndInitShared",
      "API: Generating layer ID",
      v21);
LABEL_19:
    utl::_RefCountBase::_DecStrong(v16);
    return (unsigned int)v18;
  }
  v18 = UnionFs::UfsPathName::Copy(SourceString, (__int64 *)(v13 + 16), a5);
  if ( v18 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v18,
      a5,
      (struct UnionFs::StackEventTracer *)0xD6000D0061LL,
      (unsigned __int64)"UnionFs::UfsLayerCtx::AllocAndInitShared",
      "PUSH: Duplicating path name",
      v21);
    goto LABEL_19;
  }
  v20 = (utl::_RefCountBase *)a4[1];
  *a4 = v13;
  a4[1] = (__int64)v16;
  if ( v20 )
    utl::_RefCountBase::_DecStrong(v20);
  return 0;
}

```

## disassembly

```asm
0x140035f78  push    rbx
0x140035f7a  push    rbp
0x140035f7b  push    rsi
0x140035f7c  push    rdi
0x140035f7d  push    r12
0x140035f7f  push    r14
0x140035f81  sub     rsp, 38h
0x140035f85  mov     rbx, rcx
0x140035f88  mov     qword ptr [r9], 0
0x140035f8f  mov     rcx, [r9+8]; this
0x140035f93  mov     r14, r9
0x140035f96  mov     qword ptr [r9+8], 0
0x140035f9e  mov     edi, r8d
0x140035fa1  mov     r12, rdx
0x140035fa4  test    rcx, rcx
0x140035fa7  jz      short loc_140035FAE
0x140035fa9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140035fae  mov     r9, qword ptr [rsp+68h+arg_20]
0x140035fb6  lea     r8, [rsp+68h+arg_18]
0x140035fbe  xor     edx, edx
0x140035fc0  mov     [rsp+68h+arg_18], 0
0x140035fcc  mov     rcx, rbx; Instance
0x140035fcf  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140035fd4  mov     ebx, eax
0x140035fd6  test    eax, eax
0x140035fd8  jns     short loc_14003601C
0x140035fda  mov     rdx, qword ptr [rsp+68h+arg_20]; int
0x140035fe2  lea     rax, aPushGettingIns_0; "PUSH: Getting instance context"
0x140035fe9  lea     r9, aUnionfsUfslaye; "UnionFs::UfsLayerCtx::AllocAndInitShare"...
0x140035ff0  mov     [rsp+68h+var_48], rax; char *
0x140035ff5  mov     r8, 26000D004Ah; struct UnionFs::StackEventTracer *
0x140035fff  mov     ecx, ebx; this
0x140036001  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036006  mov     rcx, [rsp+68h+arg_18]
0x14003600e  test    rcx, rcx
0x140036011  jz      loc_14003624F
0x140036017  jmp     loc_140036243
0x14003601c  mov     edx, 48h ; 'H'
0x140036021  mov     r8d, 636C4655h
0x140036027  lea     ecx, [rdx-6]
0x14003602a  call    cs:__imp_ExAllocatePool2
0x140036031  nop     dword ptr [rax+rax+00h]
0x140036036  mov     rbx, rax
0x140036039  test    rax, rax
0x14003603c  jz      short loc_140036077
0x14003603e  mov     rax, [rsp+68h+arg_18]
0x140036046  xor     esi, esi
0x140036048  mov     [rbx+8], rax
0x14003604c  xorps   xmm0, xmm0
0x14003604f  mov     [rbx+10h], rsi
0x140036053  mov     [rbx+20h], rsi
0x140036057  mov     [rbx+28h], rsi
0x14003605b  mov     [rbx], rsi
0x14003605e  mov     word ptr [rbx+18h], 2
0x140036064  movups  xmmword ptr [rbx+30h], xmm0
0x140036068  mov     rax, [rbx+8]
0x14003606c  mov     [rbx+40h], edi
0x14003606f  nop
0x140036070  lock inc dword ptr [rax+2Ch]
0x140036074  nop
0x140036075  jmp     short loc_140036081
0x140036077  mov     rsi, [rsp+68h+arg_18]
0x14003607f  xor     ebx, ebx
0x140036081  mov     ecx, 18h; unsigned __int64
0x140036086  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003608b  mov     rdi, rax
0x14003608e  test    rax, rax
0x140036091  jz      loc_1400361DD
0x140036097  mov     edx, 1
0x14003609c  mov     [rax+8], edx
0x14003609f  mov     [rax+0Ch], edx
0x1400360a2  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountNormal@PEAVUfsLayerCtx@UnionFs@@U?$default_delete@VUfsLayerCtx@UnionFs@@@utl@@V?$allocator@H@4@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountNormal<UnionFs::UfsLayerCtx *,utl::default_delete<UnionFs::UfsLayerCtx>,utl::allocator<int>>,0>::`vftable'
0x1400360a9  mov     [rdi], rax
0x1400360ac  mov     [rdi+10h], rbx
0x1400360b0  test    rbx, rbx
0x1400360b3  jz      loc_1400361FD
0x1400360b9  mov     rax, [rbx]
0x1400360bc  test    rax, rax
0x1400360bf  jnz     short loc_1400360CA
0x1400360c1  lock inc dword ptr [rdi+0Ch]
0x1400360c5  mov     [rbx], rdi
0x1400360c8  jmp     short loc_140036103
0x1400360ca  mov     eax, [rax+8]
0x1400360cd  test    eax, eax
0x1400360cf  jnz     short loc_1400360FA
0x1400360d1  lock inc dword ptr [rdi+0Ch]
0x1400360d5  mov     rcx, [rbx]
0x1400360d8  mov     eax, [rcx+0Ch]
0x1400360db  cmp     eax, edx
0x1400360dd  jz      short loc_1400360EB
0x1400360df  or      eax, 0FFFFFFFFh
0x1400360e2  lock xadd [rcx+0Ch], eax
0x1400360e7  cmp     eax, edx
0x1400360e9  jnz     short loc_1400360C5
0x1400360eb  nop
0x1400360ec  mov     rax, [rcx]
0x1400360ef  mov     rax, [rax+8]
0x1400360f3  call    _guard_dispatch_icall
0x1400360f8  jmp     short loc_1400360C5
0x1400360fa  test    rbx, rbx
0x1400360fd  jz      loc_1400361FD
0x140036103  lea     rcx, [rbx+30h]; Uuid
0x140036107  call    cs:__imp_ExUuidCreate
0x14003610e  nop     dword ptr [rax+rax+00h]
0x140036113  mov     ebp, eax
0x140036115  test    eax, eax
0x140036117  jns     short loc_140036168
0x140036119  mov     rdx, qword ptr [rsp+68h+arg_20]; int
0x140036121  lea     rax, aApiGeneratingL; "API: Generating layer ID"
0x140036128  lea     r9, aUnionfsUfslaye; "UnionFs::UfsLayerCtx::AllocAndInitShare"...
0x14003612f  mov     [rsp+68h+var_48], rax; char *
0x140036134  mov     r8, 1AA000D005Bh; struct UnionFs::StackEventTracer *
0x14003613e  mov     ecx, ebp; this
0x140036140  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036145  mov     rcx, rdi; this
0x140036148  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003614d  test    rsi, rsi
0x140036150  jz      short loc_140036161
0x140036152  mov     rcx, rsi; Context
0x140036155  call    cs:__imp_FltReleaseContext
0x14003615c  nop     dword ptr [rax+rax+00h]
0x140036161  mov     eax, ebp
0x140036163  jmp     loc_140036251
0x140036168  mov     r8, qword ptr [rsp+68h+arg_20]
0x140036170  lea     rdx, [rbx+10h]
0x140036174  mov     rcx, r12; SourceString
0x140036177  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14003617c  mov     ebp, eax
0x14003617e  test    eax, eax
0x140036180  jns     short loc_1400361B0
0x140036182  mov     rdx, qword ptr [rsp+68h+arg_20]; int
0x14003618a  lea     rax, aPushDuplicatin; "PUSH: Duplicating path name"
0x140036191  lea     r9, aUnionfsUfslaye; "UnionFs::UfsLayerCtx::AllocAndInitShare"...
0x140036198  mov     [rsp+68h+var_48], rax; char *
0x14003619d  mov     r8, 0D6000D0061h; struct UnionFs::StackEventTracer *
0x1400361a7  mov     ecx, ebp; this
0x1400361a9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400361ae  jmp     short loc_140036145
0x1400361b0  mov     rcx, [r14+8]; this
0x1400361b4  mov     [r14], rbx
0x1400361b7  mov     [r14+8], rdi
0x1400361bb  test    rcx, rcx
0x1400361be  jz      short loc_1400361C5
0x1400361c0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400361c5  test    rsi, rsi
0x1400361c8  jz      short loc_1400361D9
0x1400361ca  mov     rcx, rsi; Context
0x1400361cd  call    cs:__imp_FltReleaseContext
0x1400361d4  nop     dword ptr [rax+rax+00h]
0x1400361d9  xor     eax, eax
0x1400361db  jmp     short loc_140036251
0x1400361dd  xor     edi, edi
0x1400361df  test    rbx, rbx
0x1400361e2  jz      short loc_1400361FD
0x1400361e4  mov     rcx, rbx; this
0x1400361e7  call    ??1UfsLayerCtx@UnionFs@@QEAA@XZ; UnionFs::UfsLayerCtx::~UfsLayerCtx(void)
0x1400361ec  xor     edx, edx; Tag
0x1400361ee  mov     rcx, rbx; P
0x1400361f1  call    cs:__imp_ExFreePoolWithTag
0x1400361f8  nop     dword ptr [rax+rax+00h]
0x1400361fd  mov     rdx, qword ptr [rsp+68h+arg_20]; int
0x140036205  lea     rax, aOriginAllocati; "ORIGIN: Allocating layer context"
0x14003620c  mov     ebx, 0C000009Ah
0x140036211  mov     [rsp+68h+var_48], rax; char *
0x140036216  mov     ecx, ebx; this
0x140036218  lea     r9, aUnionfsUfslaye; "UnionFs::UfsLayerCtx::AllocAndInitShare"...
0x14003621f  mov     r8, 27000D0055h; struct UnionFs::StackEventTracer *
0x140036229  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003622e  test    rdi, rdi
0x140036231  jz      short loc_14003623B
0x140036233  mov     rcx, rdi; this
0x140036236  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003623b  test    rsi, rsi
0x14003623e  jz      short loc_14003624F
0x140036240  mov     rcx, rsi; Context
0x140036243  call    cs:__imp_FltReleaseContext
0x14003624a  nop     dword ptr [rax+rax+00h]
0x14003624f  mov     eax, ebx
0x140036251  add     rsp, 38h
0x140036255  pop     r14
0x140036257  pop     r12
0x140036259  pop     rdi
0x14003625a  pop     rsi
0x14003625b  pop     rbp
0x14003625c  pop     rbx
0x14003625d  retn
```
