# UnionFs::UfsStreamHandleCtx::FltAllocAndInit(UnionFs::UfsLayerCtx const &,_FILE_OBJECT const &,UnionFs::UfsPathName const &,_UNICODE_STRING const &,UnionFs::HandleCtxFlags,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140027218`
- end: `0x1400274c3`
- name: `?FltAllocAndInit@UfsStreamHandleCtx@UnionFs@@SAJAEBVUfsLayerCtx@2@AEBU_FILE_OBJECT@@AEBVUfsPathName@2@AEBU_UNICODE_STRING@@W4HandleCtxFlags@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `683`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140011e20`
- `0x1400271d0`
- `0x1400620ac`
- `0x140062a64`

## callees

- `0x140024b70`
- `0x140027218`
- `0x1400448c8`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079f68`
- `0x14007a02c`
- `0x14007b2b0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1400273c2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400273c2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002743b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002743b`
- `FLTMGR!FltAllocateContext` at `0x14002728a`
- `FLTMGR!FltAllocateContext` at `0x14002728a`
- `FLTMGR!FltReleaseContext` at `0x14002724e`
- `FLTMGR!FltReleaseContext` at `0x140027352`
- `FLTMGR!FltReleaseContext` at `0x1400274a0`
- `FLTMGR!FltReleaseContext` at `0x14002724e`
- `FLTMGR!FltReleaseContext` at `0x140027352`
- `FLTMGR!FltReleaseContext` at `0x1400274a0`

## string_xrefs

- `0x140027321`: `ORIGIN: OpenedScratchRoot empty`
- `0x140027382`: `PUSH: Copying OpenedScratchRoot`
- `0x140027417`: `ORIGIN: Allocating OpenedRelativePath`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsStreamHandleCtx::FltAllocAndInit(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        unsigned int a5,
        PFLT_CONTEXT ReturnedContext,
        int a7)
{
  void **v7; // r14
  void *v12; // rcx
  NTSTATUS v13; // ebx
  _DWORD *v15; // rbx
  int v16; // edx
  const char *v17; // rax
  __int64 v18; // r8
  unsigned int v19; // edi
  int v20; // ebp
  __int128 *UniqueUnicodeString; // rax
  struct _UNICODE_STRING *v22; // rdx
  unsigned __int16 *v23; // rdi
  __int128 v24; // xmm6
  unsigned int v25; // edx
  unsigned __int16 i; // dx
  __int16 v27; // cx
  void *v28; // rcx
  const char *v29; // [rsp+28h] [rbp-60h]
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-58h] BYREF

  v7 = (void **)ReturnedContext;
  v12 = *(void **)ReturnedContext;
  *(_QWORD *)ReturnedContext = 0;
  if ( v12 )
    FltReleaseContext(v12);
  ReturnedContext = 0;
  v13 = FltAllocateContext(*(PFLT_FILTER *)UnionFs::g_FilterState, 0x10u, 0x2F8u, (POOL_TYPE)512, &ReturnedContext);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v13,
      a7,
      (struct UnionFs::StackEventTracer *)0x122000A056BLL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::FltAllocAndInit",
      "API: FltAllocateContext",
      v29);
    return (unsigned int)v13;
  }
  memset(ReturnedContext, 0, 0x2F8u);
  v15 = (_DWORD *)UnionFs::UfsStreamHandleCtx::UfsStreamHandleCtx(ReturnedContext, a1, a2, a5);
  if ( !v15 )
    MicrosoftTelemetryAssertTriggeredMsgKM("Placement-new for streamhandle context failed.");
  if ( !a3->Length )
  {
    v16 = a7;
    v17 = "ORIGIN: OpenedScratchRoot empty";
    v18 = 0x619000A057BLL;
    v19 = -1073741811;
LABEL_9:
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)v19,
      v16,
      (struct UnionFs::StackEventTracer *)v18,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::FltAllocAndInit",
      v17,
      v29);
LABEL_10:
    if ( v15 )
      FltReleaseContext(v15);
    return v19;
  }
  v20 = a7;
  v19 = UnionFs::UfsPathName::Copy(a3, (__int64 *)v15 + 5, a7);
  if ( (v19 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v19,
      v20,
      (struct UnionFs::StackEventTracer *)0xF0000A0581LL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::FltAllocAndInit",
      "PUSH: Copying OpenedScratchRoot",
      v29);
    goto LABEL_10;
  }
  if ( a4->Length >= 2u && !RtlEqualUnicodeString(a4, &UnionFs::g_RootName, 1u) )
  {
    UniqueUnicodeString = (__int128 *)FsFltWil::MakeUniqueUnicodeString(&UnicodeString, a4->Length, 1667778133);
    v23 = (unsigned __int16 *)(v15 + 12);
    if ( v15 + 12 != (_DWORD *)UniqueUnicodeString )
    {
      v24 = *UniqueUnicodeString;
      *UniqueUnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v15 + 3, v22);
      *(_OWORD *)v23 = v24;
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v22);
    if ( !*((_QWORD *)v15 + 7) )
    {
      v17 = "ORIGIN: Allocating OpenedRelativePath";
      v18 = 0xF1000A0595LL;
      v16 = v20;
      v19 = -1073741670;
      goto LABEL_9;
    }
    RtlCopyUnicodeString((PUNICODE_STRING)v15 + 3, a4);
    v25 = *v23;
    if ( v25 > 2 && *(_WORD *)(*((_QWORD *)v15 + 7) + 2 * ((unsigned __int64)*v23 >> 1) - 2) == 92 )
    {
      LOWORD(v25) = v25 - 2;
      *v23 = v25;
    }
    for ( i = (unsigned __int16)v25 >> 1; i; --i )
    {
      v27 = *(_WORD *)(*((_QWORD *)v15 + 7) + 2LL * i - 2);
      if ( v27 == 92 )
        break;
      if ( v27 == 58 )
      {
        *v15 |= 0x80u;
        break;
      }
    }
  }
  v28 = *v7;
  *v7 = v15;
  if ( v28 )
    FltReleaseContext(v28);
  return 0;
}

```

## disassembly

```asm
0x140027218  push    rbx
0x14002721a  push    rbp
0x14002721b  push    rsi
0x14002721c  push    rdi
0x14002721d  push    r12
0x14002721f  push    r14
0x140027221  push    r15
0x140027223  sub     rsp, 50h
0x140027227  mov     r14, [rsp+88h+arg_28]
0x14002722f  xor     r12d, r12d
0x140027232  mov     r15, rcx
0x140027235  movaps  [rsp+88h+var_48], xmm6
0x14002723a  mov     rsi, r9
0x14002723d  mov     rdi, r8
0x140027240  mov     rbp, rdx
0x140027243  mov     rcx, [r14]; Context
0x140027246  mov     [r14], r12
0x140027249  test    rcx, rcx
0x14002724c  jz      short loc_14002725A
0x14002724e  call    cs:__imp_FltReleaseContext
0x140027255  nop     dword ptr [rax+rax+00h]
0x14002725a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140027261  lea     rax, [rsp+88h+arg_28]
0x140027269  mov     [rsp+88h+arg_28], r12
0x140027271  mov     edx, 10h; ContextType
0x140027276  mov     r9d, 200h; PoolType
0x14002727c  mov     [rsp+88h+ReturnedContext], rax; ReturnedContext
0x140027281  mov     r8d, 2F8h; ContextSize
0x140027287  mov     rcx, [rcx]; Filter
0x14002728a  call    cs:__imp_FltAllocateContext
0x140027291  nop     dword ptr [rax+rax+00h]
0x140027296  mov     ebx, eax
0x140027298  test    eax, eax
0x14002729a  jns     short loc_1400272CF
0x14002729c  mov     rdx, qword ptr [rsp+88h+arg_30]; int
0x1400272a4  lea     rax, aApiFltallocate_0; "API: FltAllocateContext"
0x1400272ab  lea     r9, aUnionfsUfsstre_0; "UnionFs::UfsStreamHandleCtx::FltAllocAn"...
0x1400272b2  mov     [rsp+88h+ReturnedContext], rax; char *
0x1400272b7  mov     r8, 122000A056Bh; struct UnionFs::StackEventTracer *
0x1400272c1  mov     ecx, ebx; this
0x1400272c3  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400272c8  mov     eax, ebx
0x1400272ca  jmp     loc_1400274AE
0x1400272cf  mov     rcx, [rsp+88h+arg_28]; void *
0x1400272d7  xor     edx, edx; Val
0x1400272d9  mov     r8d, 2F8h; Size
0x1400272df  call    memset
0x1400272e4  mov     r9d, [rsp+88h+arg_20]
0x1400272ec  mov     r8, rbp
0x1400272ef  mov     rcx, [rsp+88h+arg_28]
0x1400272f7  mov     rdx, r15
0x1400272fa  call    ??0UfsStreamHandleCtx@UnionFs@@AEAA@AEBVUfsLayerCtx@1@AEBU_FILE_OBJECT@@W4HandleCtxFlags@1@@Z; UnionFs::UfsStreamHandleCtx::UfsStreamHandleCtx(UnionFs::UfsLayerCtx const &,_FILE_OBJECT const &,UnionFs::HandleCtxFlags)
0x1400272ff  mov     rbx, rax
0x140027302  test    rax, rax
0x140027305  jnz     short loc_140027313
0x140027307  lea     rcx, aPlacementNewFo; "Placement-new for streamhandle context "...
0x14002730e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140027313  cmp     [rdi], r12w
0x140027317  jnz     short loc_140027365
0x140027319  mov     rdx, qword ptr [rsp+88h+arg_30]; int
0x140027321  lea     rax, aOriginOpenedsc; "ORIGIN: OpenedScratchRoot empty"
0x140027328  mov     r8, 619000A057Bh; struct UnionFs::StackEventTracer *
0x140027332  mov     edi, 0C000000Dh
0x140027337  lea     r9, aUnionfsUfsstre_0; "UnionFs::UfsStreamHandleCtx::FltAllocAn"...
0x14002733e  mov     [rsp+88h+ReturnedContext], rax; char *
0x140027343  mov     ecx, edi; this
0x140027345  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002734a  test    rbx, rbx
0x14002734d  jz      short loc_14002735E
0x14002734f  mov     rcx, rbx; Context
0x140027352  call    cs:__imp_FltReleaseContext
0x140027359  nop     dword ptr [rax+rax+00h]
0x14002735e  mov     eax, edi
0x140027360  jmp     loc_1400274AE
0x140027365  mov     rbp, qword ptr [rsp+88h+arg_30]
0x14002736d  lea     rdx, [rbx+28h]
0x140027371  mov     r8, rbp
0x140027374  mov     rcx, rdi; SourceString
0x140027377  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14002737c  mov     edi, eax
0x14002737e  test    eax, eax
0x140027380  jns     short loc_1400273AB
0x140027382  lea     rax, aPushCopyingOpe; "PUSH: Copying OpenedScratchRoot"
0x140027389  mov     r8, 0F0000A0581h; struct UnionFs::StackEventTracer *
0x140027393  lea     r9, aUnionfsUfsstre_0; "UnionFs::UfsStreamHandleCtx::FltAllocAn"...
0x14002739a  mov     [rsp+88h+ReturnedContext], rax; char *
0x14002739f  mov     rdx, rbp; int
0x1400273a2  mov     ecx, edi; this
0x1400273a4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400273a9  jmp     short loc_14002734A
0x1400273ab  cmp     word ptr [rsi], 2
0x1400273af  jb      loc_140027495
0x1400273b5  mov     r8b, 1; CaseInSensitive
0x1400273b8  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x1400273bf  mov     rcx, rsi; String1
0x1400273c2  call    cs:__imp_RtlEqualUnicodeString
0x1400273c9  nop     dword ptr [rax+rax+00h]
0x1400273ce  test    al, al
0x1400273d0  jnz     loc_140027495
0x1400273d6  movzx   edx, word ptr [rsi]
0x1400273d9  lea     rcx, [rsp+88h+UnicodeString]
0x1400273de  mov     r8d, 63684655h
0x1400273e4  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x1400273e9  lea     rdi, [rbx+30h]
0x1400273ed  cmp     rdi, rax
0x1400273f0  jz      short loc_140027407
0x1400273f2  movups  xmm6, xmmword ptr [rax]
0x1400273f5  mov     rcx, rdi; UnicodeString
0x1400273f8  xorps   xmm0, xmm0
0x1400273fb  movups  xmmword ptr [rax], xmm0
0x1400273fe  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140027403  movdqu  xmmword ptr [rdi], xmm6
0x140027407  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x14002740c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140027411  cmp     [rbx+38h], r12
0x140027415  jnz     short loc_140027435
0x140027417  lea     rax, aOriginAllocati_8; "ORIGIN: Allocating OpenedRelativePath"
0x14002741e  mov     r8, 0F1000A0595h
0x140027428  mov     rdx, rbp
0x14002742b  mov     edi, 0C000009Ah
0x140027430  jmp     loc_140027337
0x140027435  mov     rdx, rsi; SourceString
0x140027438  mov     rcx, rdi; DestinationString
0x14002743b  call    cs:__imp_RtlCopyUnicodeString
0x140027442  nop     dword ptr [rax+rax+00h]
0x140027447  movzx   edx, word ptr [rdi]
0x14002744a  cmp     edx, 2
0x14002744d  jbe     short loc_140027467
0x14002744f  mov     rax, [rdi+8]
0x140027453  mov     ecx, edx
0x140027455  shr     rcx, 1
0x140027458  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x14002745e  jnz     short loc_140027467
0x140027460  sub     dx, 2
0x140027464  mov     [rdi], dx
0x140027467  shr     dx, 1
0x14002746a  jz      short loc_140027495
0x14002746c  mov     r8, [rbx+38h]
0x140027470  movzx   eax, dx
0x140027473  movzx   ecx, word ptr [r8+rax*2-2]
0x140027479  cmp     cx, 5Ch ; '\'
0x14002747d  jz      short loc_140027495
0x14002747f  cmp     cx, 3Ah ; ':'
0x140027483  jz      short loc_140027491
0x140027485  mov     eax, 0FFFFh
0x14002748a  add     dx, ax
0x14002748d  jnz     short loc_140027470
0x14002748f  jmp     short loc_140027495
0x140027491  bts     dword ptr [rbx], 7
0x140027495  mov     rcx, [r14]; Context
0x140027498  mov     [r14], rbx
0x14002749b  test    rcx, rcx
0x14002749e  jz      short loc_1400274AC
0x1400274a0  call    cs:__imp_FltReleaseContext
0x1400274a7  nop     dword ptr [rax+rax+00h]
0x1400274ac  xor     eax, eax
0x1400274ae  movaps  xmm6, [rsp+88h+var_48]
0x1400274b3  add     rsp, 50h
0x1400274b7  pop     r15
0x1400274b9  pop     r14
0x1400274bb  pop     r12
0x1400274bd  pop     rdi
0x1400274be  pop     rsi
0x1400274bf  pop     rbp
0x1400274c0  pop     rbx
0x1400274c1  retn
```
