# UnionFs::UfsLayerCtx::AllocAndInitShared(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,int,utl::shared_ptr<UnionFs::UfsLayerCtx> &,UnionFs::StackEventTracer &)

- ea: `0x140035e38`
- end: `0x14003611f`
- name: `?AllocAndInitShared@UfsLayerCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@HAEAV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `743`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PCUNICODE_STRING SourceString@<rdx>, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x14005e46c`

## callees

- `0x14000f7fc`
- `0x1400276c4`
- `0x140035d14`
- `0x140035e38`
- `0x140044748`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079970`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400360b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400360b1`
- `ntoskrnl!ExAllocatePool2` at `0x140035eea`
- `ntoskrnl!ExAllocatePool2` at `0x140035eea`
- `ntoskrnl!ExUuidCreate` at `0x140035fc7`
- `ntoskrnl!ExUuidCreate` at `0x140035fc7`
- `FLTMGR!FltReleaseContext` at `0x140036015`
- `FLTMGR!FltReleaseContext` at `0x14003608d`
- `FLTMGR!FltReleaseContext` at `0x140036103`
- `FLTMGR!FltReleaseContext` at `0x140036015`
- `FLTMGR!FltReleaseContext` at `0x14003608d`
- `FLTMGR!FltReleaseContext` at `0x140036103`

## string_xrefs

- `0x14003604a`: `PUSH: Duplicating path name`

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
0x140035e38  push    rbx
0x140035e3a  push    rbp
0x140035e3b  push    rsi
0x140035e3c  push    rdi
0x140035e3d  push    r12
0x140035e3f  push    r14
0x140035e41  sub     rsp, 38h
0x140035e45  mov     rbx, rcx
0x140035e48  mov     qword ptr [r9], 0
0x140035e4f  mov     rcx, [r9+8]; this
0x140035e53  mov     r14, r9
0x140035e56  mov     qword ptr [r9+8], 0
0x140035e5e  mov     edi, r8d
0x140035e61  mov     r12, rdx
0x140035e64  test    rcx, rcx
0x140035e67  jz      short loc_140035E6E
0x140035e69  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140035e6e  mov     r9, qword ptr [rsp+68h+arg_20]
0x140035e76  lea     r8, [rsp+68h+arg_18]
0x140035e7e  xor     edx, edx
0x140035e80  mov     [rsp+68h+arg_18], 0
0x140035e8c  mov     rcx, rbx; Instance
0x140035e8f  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140035e94  mov     ebx, eax
0x140035e96  test    eax, eax
0x140035e98  jns     short loc_140035EDC
0x140035e9a  mov     rdx, qword ptr [rsp+68h+arg_20]; int
0x140035ea2  lea     rax, aPushGettingIns_0; "PUSH: Getting instance context"
0x140035ea9  lea     r9, aUnionfsUfslaye; "UnionFs::UfsLayerCtx::AllocAndInitShare"...
0x140035eb0  mov     [rsp+68h+var_48], rax; char *
0x140035eb5  mov     r8, 26000D004Ah; struct UnionFs::StackEventTracer *
0x140035ebf  mov     ecx, ebx; this
0x140035ec1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140035ec6  mov     rcx, [rsp+68h+arg_18]
0x140035ece  test    rcx, rcx
0x140035ed1  jz      loc_14003610F
0x140035ed7  jmp     loc_140036103
0x140035edc  mov     edx, 48h ; 'H'
0x140035ee1  mov     r8d, 636C4655h
0x140035ee7  lea     ecx, [rdx-6]
0x140035eea  call    cs:__imp_ExAllocatePool2
0x140035ef1  nop     dword ptr [rax+rax+00h]
0x140035ef6  mov     rbx, rax
0x140035ef9  test    rax, rax
0x140035efc  jz      short loc_140035F37
0x140035efe  mov     rax, [rsp+68h+arg_18]
0x140035f06  xor     esi, esi
0x140035f08  mov     [rbx+8], rax
0x140035f0c  xorps   xmm0, xmm0
0x140035f0f  mov     [rbx+10h], rsi
0x140035f13  mov     [rbx+20h], rsi
0x140035f17  mov     [rbx+28h], rsi
0x140035f1b  mov     [rbx], rsi
0x140035f1e  mov     word ptr [rbx+18h], 2
0x140035f24  movups  xmmword ptr [rbx+30h], xmm0
0x140035f28  mov     rax, [rbx+8]
0x140035f2c  mov     [rbx+40h], edi
0x140035f2f  nop
0x140035f30  lock inc dword ptr [rax+2Ch]
0x140035f34  nop
0x140035f35  jmp     short loc_140035F41
0x140035f37  mov     rsi, [rsp+68h+arg_18]
0x140035f3f  xor     ebx, ebx
0x140035f41  mov     ecx, 18h; unsigned __int64
0x140035f46  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140035f4b  mov     rdi, rax
0x140035f4e  test    rax, rax
0x140035f51  jz      loc_14003609D
0x140035f57  mov     edx, 1
0x140035f5c  mov     [rax+8], edx
0x140035f5f  mov     [rax+0Ch], edx
0x140035f62  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountNormal@PEAVUfsLayerCtx@UnionFs@@U?$default_delete@VUfsLayerCtx@UnionFs@@@utl@@V?$allocator@H@4@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountNormal<UnionFs::UfsLayerCtx *,utl::default_delete<UnionFs::UfsLayerCtx>,utl::allocator<int>>,0>::`vftable'
0x140035f69  mov     [rdi], rax
0x140035f6c  mov     [rdi+10h], rbx
0x140035f70  test    rbx, rbx
0x140035f73  jz      loc_1400360BD
0x140035f79  mov     rax, [rbx]
0x140035f7c  test    rax, rax
0x140035f7f  jnz     short loc_140035F8A
0x140035f81  lock inc dword ptr [rdi+0Ch]
0x140035f85  mov     [rbx], rdi
0x140035f88  jmp     short loc_140035FC3
0x140035f8a  mov     eax, [rax+8]
0x140035f8d  test    eax, eax
0x140035f8f  jnz     short loc_140035FBA
0x140035f91  lock inc dword ptr [rdi+0Ch]
0x140035f95  mov     rcx, [rbx]
0x140035f98  mov     eax, [rcx+0Ch]
0x140035f9b  cmp     eax, edx
0x140035f9d  jz      short loc_140035FAB
0x140035f9f  or      eax, 0FFFFFFFFh
0x140035fa2  lock xadd [rcx+0Ch], eax
0x140035fa7  cmp     eax, edx
0x140035fa9  jnz     short loc_140035F85
0x140035fab  nop
0x140035fac  mov     rax, [rcx]
0x140035faf  mov     rax, [rax+8]
0x140035fb3  call    _guard_dispatch_icall
0x140035fb8  jmp     short loc_140035F85
0x140035fba  test    rbx, rbx
0x140035fbd  jz      loc_1400360BD
0x140035fc3  lea     rcx, [rbx+30h]; Uuid
0x140035fc7  call    cs:__imp_ExUuidCreate
0x140035fce  nop     dword ptr [rax+rax+00h]
0x140035fd3  mov     ebp, eax
0x140035fd5  test    eax, eax
0x140035fd7  jns     short loc_140036028
0x140035fd9  mov     rdx, qword ptr [rsp+68h+arg_20]; int
0x140035fe1  lea     rax, aApiGeneratingL; "API: Generating layer ID"
0x140035fe8  lea     r9, aUnionfsUfslaye; "UnionFs::UfsLayerCtx::AllocAndInitShare"...
0x140035fef  mov     [rsp+68h+var_48], rax; char *
0x140035ff4  mov     r8, 1AA000D005Bh; struct UnionFs::StackEventTracer *
0x140035ffe  mov     ecx, ebp; this
0x140036000  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036005  mov     rcx, rdi; this
0x140036008  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003600d  test    rsi, rsi
0x140036010  jz      short loc_140036021
0x140036012  mov     rcx, rsi; Context
0x140036015  call    cs:__imp_FltReleaseContext
0x14003601c  nop     dword ptr [rax+rax+00h]
0x140036021  mov     eax, ebp
0x140036023  jmp     loc_140036111
0x140036028  mov     r8, qword ptr [rsp+68h+arg_20]
0x140036030  lea     rdx, [rbx+10h]
0x140036034  mov     rcx, r12; SourceString
0x140036037  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14003603c  mov     ebp, eax
0x14003603e  test    eax, eax
0x140036040  jns     short loc_140036070
0x140036042  mov     rdx, qword ptr [rsp+68h+arg_20]; int
0x14003604a  lea     rax, aPushDuplicatin; "PUSH: Duplicating path name"
0x140036051  lea     r9, aUnionfsUfslaye; "UnionFs::UfsLayerCtx::AllocAndInitShare"...
0x140036058  mov     [rsp+68h+var_48], rax; char *
0x14003605d  mov     r8, 0D6000D0061h; struct UnionFs::StackEventTracer *
0x140036067  mov     ecx, ebp; this
0x140036069  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003606e  jmp     short loc_140036005
0x140036070  mov     rcx, [r14+8]; this
0x140036074  mov     [r14], rbx
0x140036077  mov     [r14+8], rdi
0x14003607b  test    rcx, rcx
0x14003607e  jz      short loc_140036085
0x140036080  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140036085  test    rsi, rsi
0x140036088  jz      short loc_140036099
0x14003608a  mov     rcx, rsi; Context
0x14003608d  call    cs:__imp_FltReleaseContext
0x140036094  nop     dword ptr [rax+rax+00h]
0x140036099  xor     eax, eax
0x14003609b  jmp     short loc_140036111
0x14003609d  xor     edi, edi
0x14003609f  test    rbx, rbx
0x1400360a2  jz      short loc_1400360BD
0x1400360a4  mov     rcx, rbx; this
0x1400360a7  call    ??1UfsLayerCtx@UnionFs@@QEAA@XZ; UnionFs::UfsLayerCtx::~UfsLayerCtx(void)
0x1400360ac  xor     edx, edx; Tag
0x1400360ae  mov     rcx, rbx; P
0x1400360b1  call    cs:__imp_ExFreePoolWithTag
0x1400360b8  nop     dword ptr [rax+rax+00h]
0x1400360bd  mov     rdx, qword ptr [rsp+68h+arg_20]; int
0x1400360c5  lea     rax, aOriginAllocati; "ORIGIN: Allocating layer context"
0x1400360cc  mov     ebx, 0C000009Ah
0x1400360d1  mov     [rsp+68h+var_48], rax; char *
0x1400360d6  mov     ecx, ebx; this
0x1400360d8  lea     r9, aUnionfsUfslaye; "UnionFs::UfsLayerCtx::AllocAndInitShare"...
0x1400360df  mov     r8, 27000D0055h; struct UnionFs::StackEventTracer *
0x1400360e9  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400360ee  test    rdi, rdi
0x1400360f1  jz      short loc_1400360FB
0x1400360f3  mov     rcx, rdi; this
0x1400360f6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400360fb  test    rsi, rsi
0x1400360fe  jz      short loc_14003610F
0x140036100  mov     rcx, rsi; Context
0x140036103  call    cs:__imp_FltReleaseContext
0x14003610a  nop     dword ptr [rax+rax+00h]
0x14003610f  mov     eax, ebx
0x140036111  add     rsp, 38h
0x140036115  pop     r14
0x140036117  pop     r12
0x140036119  pop     rdi
0x14003611a  pop     rsi
0x14003611b  pop     rbp
0x14003611c  pop     rbx
0x14003611d  retn
```
