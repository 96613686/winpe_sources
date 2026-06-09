# UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone(utl::shared_ptr<UnionFs::UfsUnionCtx> &&,UnionFs::UfsPathName const &,UnionFs::TombstoneState,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,UnionFs::UfsPathName const *,bool)

- ea: `0x1400411c8`
- end: `0x140041488`
- name: `?AllocAndInitSharedForTombstone@UfsPathCachePayload@UnionFs@@SAJ$$QEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBVUfsPathName@2@W4TombstoneState@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@4@AEAVStackEventTracer@2@PEBV52@_N@Z`
- size: `704`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14005b650`
- `0x140061a00`

## callees

- `0x14000f81c`
- `0x140040ff4`
- `0x1400411c8`
- `0x1400448c8`
- `0x140056c44`
- `0x140056c7c`
- `0x140079f68`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140041345`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400413d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041345`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400413d6`

## string_xrefs

- `0x14004123d`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone`
- `0x1400412a4`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone`
- `0x140041305`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone`
- `0x140041435`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone`
- `0x140041265`: `Renamed tombstone without OriginalPath`
- `0x1400412fe`: `PUSH: Getting copy of Path`
- `0x14004142e`: `PUSH: Making copy of original path`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone(
        __int64 *a1,
        const UNICODE_STRING *a2,
        __int16 a3,
        utl::_RefCountBase **a4,
        __int64 a5,
        PCUNICODE_STRING SourceString)
{
  utl::_RefCountBase *v7; // rcx
  unsigned int inited; // ebx
  int v13; // esi
  struct _UNICODE_STRING *v14; // rdx
  struct _UNICODE_STRING *v15; // rbx
  utl::_RefCountBase *v16; // rbx
  __int64 v17; // rax
  struct _UNICODE_STRING *v18; // rdx
  utl::_RefCountBase *v19; // rcx
  __int64 v20; // rsi
  utl::_RefCountBase *v21; // rcx
  utl::_RefCountBase *v22; // rax
  const char *v23; // [rsp+28h] [rbp-30h]
  utl::_RefCountBase *v24[2]; // [rsp+30h] [rbp-28h] BYREF
  PVOID P; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  v7 = a4[1];
  a4[1] = 0;
  if ( v7 )
    utl::_RefCountBase::_DecStrong(v7);
  if ( (unsigned __int16)(a3 - 2) > 1u )
  {
    if ( a3 != 4 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Unexpected tombstone type");
      inited = -1058209788;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0ED0004LL,
        a5,
        (struct UnionFs::StackEventTracer *)0x6F00120137LL,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone",
        "ORIGIN: Unexpected tombstone type",
        v23);
      return inited;
    }
    if ( !SourceString )
      MicrosoftTelemetryAssertTriggeredMsgKM("Renamed tombstone without OriginalPath");
  }
  *(_OWORD *)v24 = 0;
  inited = UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(v24, a5, 0);
  if ( (inited & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)inited,
      a5,
      (struct UnionFs::StackEventTracer *)0x2C100120143LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone",
      "PUSH: Allocating tombstone payload",
      v23);
    if ( v24[1] )
      utl::_RefCountBase::_DecStrong(v24[1]);
    return inited;
  }
  P = 0;
  v13 = UnionFs::UfsPathName::Copy(a2, (__int64 *)&P, a5);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      a5,
      (struct UnionFs::StackEventTracer *)0x2E300120148LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone",
      "PUSH: Getting copy of Path",
      v23);
    v15 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v15, v14);
      ExFreePoolWithTag(v15, 0);
    }
    goto LABEL_17;
  }
  v16 = v24[0];
  v17 = *a1;
  v18 = (struct _UNICODE_STRING *)a1[1];
  *a1 = 0;
  a1[1] = 0;
  v19 = (utl::_RefCountBase *)*((_QWORD *)v16 + 25);
  *((_QWORD *)v16 + 24) = v17;
  *((_QWORD *)v16 + 25) = v18;
  if ( v19 )
    utl::_RefCountBase::_DecStrong(v19);
  v20 = *((_QWORD *)v16 + 26);
  *((_QWORD *)v16 + 26) = P;
  if ( v20 )
  {
    if ( !*(_BYTE *)(v20 + 16) )
      *(_OWORD *)v20 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v20, v18);
    ExFreePoolWithTag((PVOID)v20, 0);
  }
  *((_WORD *)v16 + 84) = a3;
  _mm_mfence();
  *((_BYTE *)v16 + 172) = 0;
  _mm_mfence();
  if ( SourceString )
  {
    v13 = UnionFs::UfsPathName::Copy(SourceString, (__int64 *)v16 + 27, a5);
    if ( v13 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v13,
        a5,
        (struct UnionFs::StackEventTracer *)0x35D00120154LL,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedForTombstone",
        "PUSH: Making copy of original path",
        v23);
LABEL_17:
      if ( v24[1] )
        utl::_RefCountBase::_DecStrong(v24[1]);
      return (unsigned int)v13;
    }
  }
  v21 = a4[1];
  v22 = v24[1];
  *a4 = v16;
  a4[1] = v22;
  if ( v21 )
    utl::_RefCountBase::_DecStrong(v21);
  return 0;
}

```

## disassembly

```asm
0x1400411c8  mov     [rsp+arg_0], rbx
0x1400411cd  mov     [rsp+arg_8], rsi
0x1400411d2  push    rdi
0x1400411d3  push    r12
0x1400411d5  push    r14
0x1400411d7  sub     rsp, 40h
0x1400411db  mov     r12, rcx
0x1400411de  mov     qword ptr [r9], 0
0x1400411e5  mov     rcx, [r9+8]; this
0x1400411e9  mov     rdi, r9
0x1400411ec  mov     qword ptr [r9+8], 0
0x1400411f4  movzx   r14d, r8w
0x1400411f8  mov     rsi, rdx
0x1400411fb  test    rcx, rcx
0x1400411fe  jz      short loc_140041205
0x140041200  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041205  lea     eax, [r14-2]
0x140041209  cmp     ax, 1
0x14004120d  jbe     short loc_140041271
0x14004120f  cmp     r14w, 4
0x140041214  jz      short loc_14004125A
0x140041216  lea     rcx, aUnexpectedTomb; "Unexpected tombstone type"
0x14004121d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140041222  mov     rdx, [rsp+58h+arg_20]; int
0x14004122a  lea     rax, aOriginUnexpect_3; "ORIGIN: Unexpected tombstone type"
0x140041231  mov     ebx, 0C0ED0004h
0x140041236  mov     [rsp+58h+var_38], rax; char *
0x14004123b  mov     ecx, ebx; this
0x14004123d  lea     r9, aUnionfsUfspath_6; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140041244  mov     r8, 6F00120137h; struct UnionFs::StackEventTracer *
0x14004124e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041253  mov     eax, ebx
0x140041255  jmp     loc_140041473
0x14004125a  cmp     [rsp+58h+SourceString], 0
0x140041263  jnz     short loc_140041271
0x140041265  lea     rcx, aRenamedTombsto; "Renamed tombstone without OriginalPath"
0x14004126c  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140041271  mov     rdx, [rsp+58h+arg_20]
0x140041279  lea     rcx, [rsp+58h+var_28]
0x14004127e  xorps   xmm0, xmm0
0x140041281  xor     r8d, r8d
0x140041284  movdqu  xmmword ptr [rsp+58h+var_28], xmm0
0x14004128a  call    ?AllocAndInitSharedEmpty@UfsPathCachePayload@UnionFs@@SAJAEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,bool)
0x14004128f  mov     ebx, eax
0x140041291  test    eax, eax
0x140041293  jns     short loc_1400412D2
0x140041295  mov     rdx, [rsp+58h+arg_20]; int
0x14004129d  lea     rax, aPushAllocating_33; "PUSH: Allocating tombstone payload"
0x1400412a4  lea     r9, aUnionfsUfspath_6; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x1400412ab  mov     [rsp+58h+var_38], rax; char *
0x1400412b0  mov     r8, 2C100120143h; struct UnionFs::StackEventTracer *
0x1400412ba  mov     ecx, ebx; this
0x1400412bc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400412c1  mov     rcx, [rsp+58h+var_28+8]; this
0x1400412c6  test    rcx, rcx
0x1400412c9  jz      short loc_140041253
0x1400412cb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400412d0  jmp     short loc_140041253
0x1400412d2  mov     r8, [rsp+58h+arg_20]
0x1400412da  lea     rdx, [rsp+58h+P]
0x1400412df  mov     rcx, rsi; SourceString
0x1400412e2  mov     [rsp+58h+P], 0
0x1400412eb  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400412f0  mov     esi, eax
0x1400412f2  test    eax, eax
0x1400412f4  jns     short loc_140041367
0x1400412f6  mov     rdx, [rsp+58h+arg_20]; int
0x1400412fe  lea     rax, aPushGettingCop_0; "PUSH: Getting copy of Path"
0x140041305  lea     r9, aUnionfsUfspath_6; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x14004130c  mov     [rsp+58h+var_38], rax; char *
0x140041311  mov     r8, 2E300120148h; struct UnionFs::StackEventTracer *
0x14004131b  mov     ecx, esi; this
0x14004131d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041322  mov     rbx, [rsp+58h+P]
0x140041327  test    rbx, rbx
0x14004132a  jz      short loc_140041351
0x14004132c  cmp     byte ptr [rbx+10h], 0
0x140041330  jnz     short loc_140041338
0x140041332  xorps   xmm0, xmm0
0x140041335  movups  xmmword ptr [rbx], xmm0
0x140041338  mov     rcx, rbx; UnicodeString
0x14004133b  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140041340  xor     edx, edx; Tag
0x140041342  mov     rcx, rbx; P
0x140041345  call    cs:__imp_ExFreePoolWithTag
0x14004134c  nop     dword ptr [rax+rax+00h]
0x140041351  mov     rcx, [rsp+58h+var_28+8]; this
0x140041356  test    rcx, rcx
0x140041359  jz      short loc_140041360
0x14004135b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041360  mov     eax, esi
0x140041362  jmp     loc_140041473
0x140041367  mov     rbx, [rsp+58h+var_28]
0x14004136c  mov     rax, [r12]
0x140041370  mov     rdx, [r12+8]
0x140041375  mov     qword ptr [r12], 0
0x14004137d  mov     qword ptr [r12+8], 0
0x140041386  mov     rcx, [rbx+0C8h]; this
0x14004138d  mov     [rbx+0C0h], rax
0x140041394  mov     [rbx+0C8h], rdx
0x14004139b  test    rcx, rcx
0x14004139e  jz      short loc_1400413A5
0x1400413a0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400413a5  mov     rsi, [rbx+0D0h]
0x1400413ac  mov     rax, [rsp+58h+P]
0x1400413b1  mov     [rbx+0D0h], rax
0x1400413b8  test    rsi, rsi
0x1400413bb  jz      short loc_1400413E2
0x1400413bd  cmp     byte ptr [rsi+10h], 0
0x1400413c1  jnz     short loc_1400413C9
0x1400413c3  xorps   xmm0, xmm0
0x1400413c6  movups  xmmword ptr [rsi], xmm0
0x1400413c9  mov     rcx, rsi; UnicodeString
0x1400413cc  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400413d1  xor     edx, edx; Tag
0x1400413d3  mov     rcx, rsi; P
0x1400413d6  call    cs:__imp_ExFreePoolWithTag
0x1400413dd  nop     dword ptr [rax+rax+00h]
0x1400413e2  nop
0x1400413e3  mov     [rbx+0A8h], r14w
0x1400413eb  mfence
0x1400413ee  nop
0x1400413ef  mov     byte ptr [rbx+0ACh], 0
0x1400413f6  mfence
0x1400413f9  cmp     [rsp+58h+SourceString], 0
0x140041402  jz      short loc_140041457
0x140041404  mov     r8, [rsp+58h+arg_20]
0x14004140c  lea     rdx, [rbx+0D8h]
0x140041413  mov     rcx, [rsp+58h+SourceString]; SourceString
0x14004141b  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140041420  mov     esi, eax
0x140041422  test    eax, eax
0x140041424  jns     short loc_140041457
0x140041426  mov     rdx, [rsp+58h+arg_20]; int
0x14004142e  lea     rax, aPushMakingCopy; "PUSH: Making copy of original path"
0x140041435  lea     r9, aUnionfsUfspath_6; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x14004143c  mov     [rsp+58h+var_38], rax; char *
0x140041441  mov     r8, 35D00120154h; struct UnionFs::StackEventTracer *
0x14004144b  mov     ecx, esi; this
0x14004144d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041452  jmp     loc_140041351
0x140041457  mov     rcx, [rdi+8]; this
0x14004145b  mov     rax, [rsp+58h+var_28+8]
0x140041460  mov     [rdi], rbx
0x140041463  mov     [rdi+8], rax
0x140041467  test    rcx, rcx
0x14004146a  jz      short loc_140041471
0x14004146c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041471  xor     eax, eax
0x140041473  mov     rbx, [rsp+58h+arg_0]
0x140041478  mov     rsi, [rsp+58h+arg_8]
0x14004147d  add     rsp, 40h
0x140041481  pop     r14
0x140041483  pop     r12
0x140041485  pop     rdi
0x140041486  retn
```
