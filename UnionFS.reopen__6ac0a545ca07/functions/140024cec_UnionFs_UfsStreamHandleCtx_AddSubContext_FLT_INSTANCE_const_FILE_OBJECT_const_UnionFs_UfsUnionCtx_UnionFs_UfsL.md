# UnionFs::UfsStreamHandleCtx::AddSubContext(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsUnionCtx &,UnionFs::UfsLayerCtx const &,ulong,_FILE_INFORMATION_CLASS,_UNICODE_STRING const &,uchar,UnionFs::StackEventTracer &,bool)

- ea: `0x140024cec`
- end: `0x140025027`
- name: `?AddSubContext@UfsStreamHandleCtx@UnionFs@@AEBAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAVUfsUnionCtx@2@AEBVUfsLayerCtx@2@KW4_FILE_INFORMATION_CLASS@@AEBU_UNICODE_STRING@@EAEAVStackEventTracer@2@_N@Z`
- size: `827`
- prototype: `__int64 __fastcall(UnionFs::UfsStreamHandleCtx *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, struct UnionFs::UfsUnionCtx *, const struct UnionFs::UfsLayerCtx *, unsigned int, enum _FILE_INFORMATION_CLASS, const struct _UNICODE_STRING *, unsigned __int8, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140029f08`

## callees

- `0x14000f81c`
- `0x14001accc`
- `0x14001bf60`
- `0x14001c020`
- `0x140024cec`
- `0x14002ad6c`
- `0x14002b058`
- `0x140056c44`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024e48`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024ec3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024f56`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024e48`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024ec3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140024f56`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140024d74`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140024d74`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsStreamHandleCtx::AddSubContext(
        UnionFs::UfsStreamHandleCtx *this,
        const struct _FLT_INSTANCE *a2,
        const struct _FILE_OBJECT *a3,
        struct UnionFs::UfsUnionCtx *a4,
        const struct UnionFs::UfsLayerCtx *a5,
        unsigned int a6,
        enum _FILE_INFORMATION_CLASS a7,
        const struct _UNICODE_STRING *a8,
        unsigned __int8 a9,
        struct UnionFs::StackEventTracer *a10,
        bool a11)
{
  unsigned int v16; // edi
  UnionFs::UfsEnumContext *v17; // rax
  UnionFs::UfsEnumContext *v18; // rbx
  int v19; // esi
  int v20; // edi
  int v21; // eax
  __int64 *v22; // rdi
  UnionFs::UfsEnumContext **v23; // rax
  UnionFs::UfsEnumContext *v24; // rsi
  __int64 v25; // r14
  UnionFs::UfsEnumContext **v26; // r8
  __int64 v27; // rdx
  char *v28; // rcx
  char *v29; // rax
  struct UnionFs::StackEventTracer *v30; // [rsp+28h] [rbp-38h]
  struct UnionFs::StackEventTracer *v31; // [rsp+28h] [rbp-38h]
  struct UnionFs::StackEventTracer *v32; // [rsp+28h] [rbp-38h]
  UnionFs::UfsEnumContext *v33; // [rsp+40h] [rbp-20h] BYREF
  __int64 v34; // [rsp+48h] [rbp-18h] BYREF
  utl::_RefCountBase *v35; // [rsp+50h] [rbp-10h]

  UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(this, &v34);
  if ( !v34 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0008LL,
      (int)a10,
      (struct UnionFs::StackEventTracer *)0x3D1000A0A86LL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::AddSubContext",
      "ORIGIN: Can't get scratch layer",
      (const char *)v30);
    if ( v35 )
      utl::_RefCountBase::_DecStrong(v35);
    return 3236757512LL;
  }
  v16 = *((_DWORD *)this + 43);
  v17 = (UnionFs::UfsEnumContext *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState
                                                                                    + 1184));
  v18 = v17;
  if ( !v17 )
  {
    v19 = (int)a10;
    v20 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a10,
      (struct UnionFs::StackEventTracer *)0x1D000040030LL,
      (unsigned __int64)"UnionFs::UfsEnumContext::AllocAndInit",
      "ORIGIN: Allocating UfsEnumContext",
      (const char *)v30);
    goto LABEL_29;
  }
  *((_QWORD *)v17 + 1) = a3;
  *(_QWORD *)v17 = a2;
  *((_QWORD *)v17 + 3) = a4;
  v19 = (int)a10;
  *((_QWORD *)v17 + 2) = a5;
  *((_QWORD *)v17 + 4) = 0;
  *((_DWORD *)v17 + 18) = a11;
  *((_QWORD *)v17 + 5) = 0;
  *((_QWORD *)v17 + 6) = 0;
  *((_QWORD *)v17 + 7) = 0;
  *((_DWORD *)v17 + 16) = 0;
  *((_BYTE *)v17 + 68) = 0;
  v20 = UnionFs::UfsEnumContext::ResetBuffer(v17, a6, a7, a9, v16, a10, 0);
  if ( v20 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v20,
      (int)a10,
      (struct UnionFs::StackEventTracer *)0x1D30004003ALL,
      (unsigned __int64)"UnionFs::UfsEnumContext::AllocAndInit",
      "PUSH: Resetting buffer",
      (const char *)v31);
    UnionFs::UfsEnumContext::~UfsEnumContext(v18);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1184), v18);
LABEL_29:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v20,
      v19,
      (struct UnionFs::StackEventTracer *)0x1CC000A0A98LL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::AddSubContext",
      "PUSH: UfsEnumContext::AllocAndInit",
      (const char *)v32);
    goto LABEL_30;
  }
  v21 = *((_DWORD *)this + 22);
  v33 = v18;
  if ( (v21 & 0x10) != 0 && (a9 & 1) == 0 )
  {
    v20 = UnionFs::UfsEnumContext::PrimeForEnumeration(v18, a9, a10, a8);
    if ( v20 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v20,
        (int)a10,
        (struct UnionFs::StackEventTracer *)0xC9000A0AA5LL,
        (unsigned __int64)"UnionFs::UfsStreamHandleCtx::AddSubContext",
        "PUSH: Error priming handle for resumed enumeration",
        (const char *)v31);
LABEL_12:
      UnionFs::UfsEnumContext::~UfsEnumContext(v18);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1184), v18);
LABEL_30:
      if ( v35 )
        utl::_RefCountBase::_DecStrong(v35);
      return (unsigned int)v20;
    }
    *((_DWORD *)v18 + 18) |= 2u;
  }
  v22 = (__int64 *)((char *)this + 144);
  v23 = (UnionFs::UfsEnumContext **)*((_QWORD *)this + 19);
  if ( v23 == *((UnionFs::UfsEnumContext ***)this + 20) )
  {
    v25 = *v22;
    if ( !(unsigned __int8)utl::vector<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>,utl::allocator<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>>>::_Grow(v22) )
    {
      v20 = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a10,
        (struct UnionFs::StackEventTracer *)0x1D1000A0AAFLL,
        (unsigned __int64)"UnionFs::UfsStreamHandleCtx::AddSubContext",
        "ORIGIN: Storing sub-context",
        (const char *)v31);
      if ( !v18 )
        goto LABEL_30;
      goto LABEL_12;
    }
    v26 = (UnionFs::UfsEnumContext **)v22[1];
    v27 = *v22;
    v28 = (char *)&v33 - v25;
    if ( (char *)&v33 - v25 >= (char *)v26 - *v22 )
    {
      v29 = (char *)&v33;
    }
    else
    {
      v29 = &v28[v27];
      v18 = *(UnionFs::UfsEnumContext **)&v28[v27];
    }
    *(_QWORD *)v29 = 0;
    v24 = v33;
    *v26 = v18;
  }
  else
  {
    v24 = 0;
    *v23 = v18;
  }
  v22[1] += 8;
  if ( v24 )
  {
    UnionFs::UfsEnumContext::~UfsEnumContext(v24);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1184), v24);
  }
  if ( v35 )
    utl::_RefCountBase::_DecStrong(v35);
  return 0;
}

```

## disassembly

```asm
0x140024cec  push    rbp
0x140024cee  push    rbx
0x140024cef  push    rsi
0x140024cf0  push    rdi
0x140024cf1  push    r12
0x140024cf3  push    r14
0x140024cf5  push    r15
0x140024cf7  mov     rbp, rsp
0x140024cfa  sub     rsp, 60h
0x140024cfe  mov     r12, rdx
0x140024d01  mov     rsi, r9
0x140024d04  lea     rdx, [rbp+var_18]
0x140024d08  mov     r15, r8
0x140024d0b  mov     r14, rcx
0x140024d0e  call    ?TryGetScratchLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@$$CBVUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(void)
0x140024d13  cmp     [rbp+var_18], 0
0x140024d18  jnz     short loc_140024D5F
0x140024d1a  mov     rdx, [rbp+arg_48]; int
0x140024d21  lea     rax, aOriginCanTGetS_0; "ORIGIN: Can't get scratch layer"
0x140024d28  mov     ebx, 0C0ED0008h
0x140024d2d  mov     [rsp+60h+var_40], rax; char *
0x140024d32  mov     ecx, ebx; this
0x140024d34  lea     r9, aUnionfsUfsstre_24; "UnionFs::UfsStreamHandleCtx::AddSubCont"...
0x140024d3b  mov     r8, 3D1000A0A86h; struct UnionFs::StackEventTracer *
0x140024d45  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024d4a  mov     rcx, [rbp+var_10]; this
0x140024d4e  test    rcx, rcx
0x140024d51  jz      short loc_140024D58
0x140024d53  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140024d58  mov     eax, ebx
0x140024d5a  jmp     loc_140025017
0x140024d5f  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140024d66  mov     edi, [r14+0ACh]
0x140024d6d  add     rcx, 4A0h; Lookaside
0x140024d74  call    cs:__imp_ExAllocateFromLookasideListEx
0x140024d7b  nop     dword ptr [rax+rax+00h]
0x140024d80  mov     rbx, rax
0x140024d83  test    rax, rax
0x140024d86  jz      loc_140024FAD
0x140024d8c  mov     r8d, [rbp+arg_30]; enum _FILE_INFORMATION_CLASS
0x140024d90  mov     rcx, rbx; this
0x140024d93  mov     edx, [rbp+arg_28]; unsigned int
0x140024d96  mov     [rax+8], r15
0x140024d9a  mov     r15b, [rbp+arg_40]
0x140024da1  mov     [rax], r12
0x140024da4  mov     r9b, r15b; unsigned __int8
0x140024da7  mov     rax, [rbp+arg_20]
0x140024dab  mov     [rbx+18h], rsi
0x140024daf  mov     rsi, [rbp+arg_48]
0x140024db6  mov     [rbx+10h], rax
0x140024dba  movzx   eax, [rbp+arg_50]
0x140024dc1  mov     [rsp+60h+var_30], 0; bool
0x140024dc6  mov     qword ptr [rbx+20h], 0
0x140024dce  mov     [rsp+60h+var_38], rsi; char *
0x140024dd3  mov     [rbx+48h], eax
0x140024dd6  mov     qword ptr [rbx+28h], 0
0x140024dde  mov     qword ptr [rbx+30h], 0
0x140024de6  mov     qword ptr [rbx+38h], 0
0x140024dee  mov     dword ptr [rbx+40h], 0
0x140024df5  mov     byte ptr [rbx+44h], 0
0x140024df9  mov     dword ptr [rsp+60h+var_40], edi; unsigned int
0x140024dfd  call    ?ResetBuffer@UfsEnumContext@UnionFs@@QEAAJKW4_FILE_INFORMATION_CLASS@@EKAEAVStackEventTracer@2@_N@Z; UnionFs::UfsEnumContext::ResetBuffer(ulong,_FILE_INFORMATION_CLASS,uchar,ulong,UnionFs::StackEventTracer &,bool)
0x140024e02  mov     edi, eax
0x140024e04  test    eax, eax
0x140024e06  jns     short loc_140024E59
0x140024e08  lea     rax, aPushResettingB; "PUSH: Resetting buffer"
0x140024e0f  mov     r8, 1D30004003Ah; struct UnionFs::StackEventTracer *
0x140024e19  lea     r9, aUnionfsUfsenum; "UnionFs::UfsEnumContext::AllocAndInit"
0x140024e20  mov     [rsp+60h+var_40], rax; char *
0x140024e25  mov     rdx, rsi; int
0x140024e28  mov     ecx, edi; this
0x140024e2a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024e2f  mov     rcx, rbx; this
0x140024e32  call    ??1UfsEnumContext@UnionFs@@QEAA@XZ; UnionFs::UfsEnumContext::~UfsEnumContext(void)
0x140024e37  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140024e3e  mov     rdx, rbx; Entry
0x140024e41  add     rcx, 4A0h; Lookaside
0x140024e48  call    cs:__imp_ExFreeToLookasideListEx
0x140024e4f  nop     dword ptr [rax+rax+00h]
0x140024e54  jmp     loc_140024FE0
0x140024e59  mov     eax, [r14+58h]
0x140024e5d  mov     [rbp+var_20], rbx
0x140024e61  test    al, 10h
0x140024e63  jz      short loc_140024ED8
0x140024e65  test    r15b, 1
0x140024e69  jnz     short loc_140024ED8
0x140024e6b  mov     r9, [rbp+arg_38]; struct _UNICODE_STRING *
0x140024e6f  mov     r8, rsi; struct UnionFs::StackEventTracer *
0x140024e72  mov     dl, r15b; unsigned __int8
0x140024e75  mov     rcx, rbx; this
0x140024e78  call    ?PrimeForEnumeration@UfsEnumContext@UnionFs@@QEBAJEAEAVStackEventTracer@2@PEBU_UNICODE_STRING@@@Z; UnionFs::UfsEnumContext::PrimeForEnumeration(uchar,UnionFs::StackEventTracer &,_UNICODE_STRING const *)
0x140024e7d  mov     edi, eax
0x140024e7f  test    eax, eax
0x140024e81  jns     short loc_140024ED4
0x140024e83  lea     rax, aPushErrorPrimi; "PUSH: Error priming handle for resumed "...
0x140024e8a  mov     r8, 0C9000A0AA5h; struct UnionFs::StackEventTracer *
0x140024e94  lea     r9, aUnionfsUfsstre_24; "UnionFs::UfsStreamHandleCtx::AddSubCont"...
0x140024e9b  mov     [rsp+60h+var_40], rax; char *
0x140024ea0  mov     rdx, rsi; int
0x140024ea3  mov     ecx, edi; this
0x140024ea5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024eaa  mov     rcx, rbx; this
0x140024ead  call    ??1UfsEnumContext@UnionFs@@QEAA@XZ; UnionFs::UfsEnumContext::~UfsEnumContext(void)
0x140024eb2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140024eb9  mov     rdx, rbx; Entry
0x140024ebc  add     rcx, 4A0h; Lookaside
0x140024ec3  call    cs:__imp_ExFreeToLookasideListEx
0x140024eca  nop     dword ptr [rax+rax+00h]
0x140024ecf  jmp     loc_140025007
0x140024ed4  or      dword ptr [rbx+48h], 2
0x140024ed8  lea     rdi, [r14+90h]
0x140024edf  mov     rax, [rdi+8]
0x140024ee3  cmp     rax, [rdi+10h]
0x140024ee7  jz      short loc_140024EF0
0x140024ee9  xor     esi, esi
0x140024eeb  mov     [rax], rbx
0x140024eee  jmp     short loc_140024F33
0x140024ef0  mov     r14, [rdi]
0x140024ef3  mov     rcx, rdi
0x140024ef6  call    ?_Grow@?$vector@V?$unique_ptr@VUfsEnumContext@UnionFs@@U?$default_delete@VUfsEnumContext@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsEnumContext@UnionFs@@U?$default_delete@VUfsEnumContext@UnionFs@@@utl@@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>,utl::allocator<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>>>::_Grow(void)
0x140024efb  test    al, al
0x140024efd  jz      short loc_140024F77
0x140024eff  mov     r8, [rdi+8]
0x140024f03  lea     rcx, [rbp+var_20]
0x140024f07  mov     rdx, [rdi]
0x140024f0a  mov     rax, r8
0x140024f0d  sub     rax, rdx
0x140024f10  sub     rcx, r14
0x140024f13  cmp     rcx, rax
0x140024f16  jnb     short loc_140024F21
0x140024f18  lea     rax, [rcx+rdx]
0x140024f1c  mov     rbx, [rax]
0x140024f1f  jmp     short loc_140024F25
0x140024f21  lea     rax, [rbp+var_20]
0x140024f25  mov     qword ptr [rax], 0
0x140024f2c  mov     rsi, [rbp+var_20]
0x140024f30  mov     [r8], rbx
0x140024f33  add     qword ptr [rdi+8], 8
0x140024f38  test    rsi, rsi
0x140024f3b  jz      short loc_140024F62
0x140024f3d  mov     rcx, rsi; this
0x140024f40  call    ??1UfsEnumContext@UnionFs@@QEAA@XZ; UnionFs::UfsEnumContext::~UfsEnumContext(void)
0x140024f45  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140024f4c  mov     rdx, rsi; Entry
0x140024f4f  add     rcx, 4A0h; Lookaside
0x140024f56  call    cs:__imp_ExFreeToLookasideListEx
0x140024f5d  nop     dword ptr [rax+rax+00h]
0x140024f62  mov     rcx, [rbp+var_10]; this
0x140024f66  test    rcx, rcx
0x140024f69  jz      short loc_140024F70
0x140024f6b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140024f70  xor     eax, eax
0x140024f72  jmp     loc_140025017
0x140024f77  lea     rax, aOriginStoringS; "ORIGIN: Storing sub-context"
0x140024f7e  mov     edi, 0C000009Ah
0x140024f83  mov     ecx, edi; this
0x140024f85  mov     [rsp+60h+var_40], rax; char *
0x140024f8a  lea     r9, aUnionfsUfsstre_24; "UnionFs::UfsStreamHandleCtx::AddSubCont"...
0x140024f91  mov     r8, 1D1000A0AAFh; struct UnionFs::StackEventTracer *
0x140024f9b  mov     rdx, rsi; int
0x140024f9e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024fa3  test    rbx, rbx
0x140024fa6  jz      short loc_140025007
0x140024fa8  jmp     loc_140024EAA
0x140024fad  mov     rsi, [rbp+arg_48]
0x140024fb4  lea     rax, aOriginAllocati_28; "ORIGIN: Allocating UfsEnumContext"
0x140024fbb  mov     edi, 0C000009Ah
0x140024fc0  mov     [rsp+60h+var_40], rax; char *
0x140024fc5  mov     rdx, rsi; int
0x140024fc8  lea     r9, aUnionfsUfsenum; "UnionFs::UfsEnumContext::AllocAndInit"
0x140024fcf  mov     ecx, edi; this
0x140024fd1  mov     r8, 1D000040030h; struct UnionFs::StackEventTracer *
0x140024fdb  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140024fe0  lea     rax, aPushUfsenumcon; "PUSH: UfsEnumContext::AllocAndInit"
0x140024fe7  mov     r8, 1CC000A0A98h; struct UnionFs::StackEventTracer *
0x140024ff1  lea     r9, aUnionfsUfsstre_24; "UnionFs::UfsStreamHandleCtx::AddSubCont"...
0x140024ff8  mov     [rsp+60h+var_40], rax; char *
0x140024ffd  mov     rdx, rsi; int
0x140025000  mov     ecx, edi; this
0x140025002  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140025007  mov     rcx, [rbp+var_10]; this
0x14002500b  test    rcx, rcx
0x14002500e  jz      short loc_140025015
0x140025010  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140025015  mov     eax, edi
0x140025017  add     rsp, 60h
0x14002501b  pop     r15
0x14002501d  pop     r14
0x14002501f  pop     r12
0x140025021  pop     rdi
0x140025022  pop     rsi
0x140025023  pop     rbx
0x140025024  pop     rbp
0x140025025  retn
```
