# UnionFs::UfsStreamHandleCtx::FltAllocAndInit(UnionFs::UfsLayerCtx const &,_FILE_OBJECT const &,UnionFs::UfsPathName const &,_UNICODE_STRING const &,UnionFs::HandleCtxFlags,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x140027178`
- end: `0x140027423`
- name: `?FltAllocAndInit@UfsStreamHandleCtx@UnionFs@@SAJAEBVUfsLayerCtx@2@AEBU_FILE_OBJECT@@AEBVUfsPathName@2@AEBU_UNICODE_STRING@@W4HandleCtxFlags@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `683`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140011e00`
- `0x140027130`
- `0x140061f2c`
- `0x1400628e4`

## callees

- `0x140024ad0`
- `0x140027178`
- `0x140044748`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`
- `0x140079d0c`
- `0x14007af90`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140027322`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140027322`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002739b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002739b`
- `FLTMGR!FltAllocateContext` at `0x1400271ea`
- `FLTMGR!FltAllocateContext` at `0x1400271ea`
- `FLTMGR!FltReleaseContext` at `0x1400271ae`
- `FLTMGR!FltReleaseContext` at `0x1400272b2`
- `FLTMGR!FltReleaseContext` at `0x140027400`
- `FLTMGR!FltReleaseContext` at `0x1400271ae`
- `FLTMGR!FltReleaseContext` at `0x1400272b2`
- `FLTMGR!FltReleaseContext` at `0x140027400`

## string_xrefs

- `0x140027281`: `ORIGIN: OpenedScratchRoot empty`
- `0x1400272e2`: `PUSH: Copying OpenedScratchRoot`
- `0x140027377`: `ORIGIN: Allocating OpenedRelativePath`

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
0x140027178  push    rbx
0x14002717a  push    rbp
0x14002717b  push    rsi
0x14002717c  push    rdi
0x14002717d  push    r12
0x14002717f  push    r14
0x140027181  push    r15
0x140027183  sub     rsp, 50h
0x140027187  mov     r14, [rsp+88h+arg_28]
0x14002718f  xor     r12d, r12d
0x140027192  mov     r15, rcx
0x140027195  movaps  [rsp+88h+var_48], xmm6
0x14002719a  mov     rsi, r9
0x14002719d  mov     rdi, r8
0x1400271a0  mov     rbp, rdx
0x1400271a3  mov     rcx, [r14]; Context
0x1400271a6  mov     [r14], r12
0x1400271a9  test    rcx, rcx
0x1400271ac  jz      short loc_1400271BA
0x1400271ae  call    cs:__imp_FltReleaseContext
0x1400271b5  nop     dword ptr [rax+rax+00h]
0x1400271ba  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400271c1  lea     rax, [rsp+88h+arg_28]
0x1400271c9  mov     [rsp+88h+arg_28], r12
0x1400271d1  mov     edx, 10h; ContextType
0x1400271d6  mov     r9d, 200h; PoolType
0x1400271dc  mov     [rsp+88h+ReturnedContext], rax; ReturnedContext
0x1400271e1  mov     r8d, 2F8h; ContextSize
0x1400271e7  mov     rcx, [rcx]; Filter
0x1400271ea  call    cs:__imp_FltAllocateContext
0x1400271f1  nop     dword ptr [rax+rax+00h]
0x1400271f6  mov     ebx, eax
0x1400271f8  test    eax, eax
0x1400271fa  jns     short loc_14002722F
0x1400271fc  mov     rdx, qword ptr [rsp+88h+arg_30]; int
0x140027204  lea     rax, aApiFltallocate_0; "API: FltAllocateContext"
0x14002720b  lea     r9, aUnionfsUfsstre_0; "UnionFs::UfsStreamHandleCtx::FltAllocAn"...
0x140027212  mov     [rsp+88h+ReturnedContext], rax; char *
0x140027217  mov     r8, 122000A056Bh; struct UnionFs::StackEventTracer *
0x140027221  mov     ecx, ebx; this
0x140027223  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140027228  mov     eax, ebx
0x14002722a  jmp     loc_14002740E
0x14002722f  mov     rcx, [rsp+88h+arg_28]; void *
0x140027237  xor     edx, edx; Val
0x140027239  mov     r8d, 2F8h; Size
0x14002723f  call    memset
0x140027244  mov     r9d, [rsp+88h+arg_20]
0x14002724c  mov     r8, rbp
0x14002724f  mov     rcx, [rsp+88h+arg_28]
0x140027257  mov     rdx, r15
0x14002725a  call    ??0UfsStreamHandleCtx@UnionFs@@AEAA@AEBVUfsLayerCtx@1@AEBU_FILE_OBJECT@@W4HandleCtxFlags@1@@Z; UnionFs::UfsStreamHandleCtx::UfsStreamHandleCtx(UnionFs::UfsLayerCtx const &,_FILE_OBJECT const &,UnionFs::HandleCtxFlags)
0x14002725f  mov     rbx, rax
0x140027262  test    rax, rax
0x140027265  jnz     short loc_140027273
0x140027267  lea     rcx, aPlacementNewFo; "Placement-new for streamhandle context "...
0x14002726e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140027273  cmp     [rdi], r12w
0x140027277  jnz     short loc_1400272C5
0x140027279  mov     rdx, qword ptr [rsp+88h+arg_30]; int
0x140027281  lea     rax, aOriginOpenedsc; "ORIGIN: OpenedScratchRoot empty"
0x140027288  mov     r8, 619000A057Bh; struct UnionFs::StackEventTracer *
0x140027292  mov     edi, 0C000000Dh
0x140027297  lea     r9, aUnionfsUfsstre_0; "UnionFs::UfsStreamHandleCtx::FltAllocAn"...
0x14002729e  mov     [rsp+88h+ReturnedContext], rax; char *
0x1400272a3  mov     ecx, edi; this
0x1400272a5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400272aa  test    rbx, rbx
0x1400272ad  jz      short loc_1400272BE
0x1400272af  mov     rcx, rbx; Context
0x1400272b2  call    cs:__imp_FltReleaseContext
0x1400272b9  nop     dword ptr [rax+rax+00h]
0x1400272be  mov     eax, edi
0x1400272c0  jmp     loc_14002740E
0x1400272c5  mov     rbp, qword ptr [rsp+88h+arg_30]
0x1400272cd  lea     rdx, [rbx+28h]
0x1400272d1  mov     r8, rbp
0x1400272d4  mov     rcx, rdi; SourceString
0x1400272d7  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400272dc  mov     edi, eax
0x1400272de  test    eax, eax
0x1400272e0  jns     short loc_14002730B
0x1400272e2  lea     rax, aPushCopyingOpe; "PUSH: Copying OpenedScratchRoot"
0x1400272e9  mov     r8, 0F0000A0581h; struct UnionFs::StackEventTracer *
0x1400272f3  lea     r9, aUnionfsUfsstre_0; "UnionFs::UfsStreamHandleCtx::FltAllocAn"...
0x1400272fa  mov     [rsp+88h+ReturnedContext], rax; char *
0x1400272ff  mov     rdx, rbp; int
0x140027302  mov     ecx, edi; this
0x140027304  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140027309  jmp     short loc_1400272AA
0x14002730b  cmp     word ptr [rsi], 2
0x14002730f  jb      loc_1400273F5
0x140027315  mov     r8b, 1; CaseInSensitive
0x140027318  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14002731f  mov     rcx, rsi; String1
0x140027322  call    cs:__imp_RtlEqualUnicodeString
0x140027329  nop     dword ptr [rax+rax+00h]
0x14002732e  test    al, al
0x140027330  jnz     loc_1400273F5
0x140027336  movzx   edx, word ptr [rsi]
0x140027339  lea     rcx, [rsp+88h+UnicodeString]
0x14002733e  mov     r8d, 63684655h
0x140027344  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140027349  lea     rdi, [rbx+30h]
0x14002734d  cmp     rdi, rax
0x140027350  jz      short loc_140027367
0x140027352  movups  xmm6, xmmword ptr [rax]
0x140027355  mov     rcx, rdi; UnicodeString
0x140027358  xorps   xmm0, xmm0
0x14002735b  movups  xmmword ptr [rax], xmm0
0x14002735e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140027363  movdqu  xmmword ptr [rdi], xmm6
0x140027367  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x14002736c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140027371  cmp     [rbx+38h], r12
0x140027375  jnz     short loc_140027395
0x140027377  lea     rax, aOriginAllocati_8; "ORIGIN: Allocating OpenedRelativePath"
0x14002737e  mov     r8, 0F1000A0595h
0x140027388  mov     rdx, rbp
0x14002738b  mov     edi, 0C000009Ah
0x140027390  jmp     loc_140027297
0x140027395  mov     rdx, rsi; SourceString
0x140027398  mov     rcx, rdi; DestinationString
0x14002739b  call    cs:__imp_RtlCopyUnicodeString
0x1400273a2  nop     dword ptr [rax+rax+00h]
0x1400273a7  movzx   edx, word ptr [rdi]
0x1400273aa  cmp     edx, 2
0x1400273ad  jbe     short loc_1400273C7
0x1400273af  mov     rax, [rdi+8]
0x1400273b3  mov     ecx, edx
0x1400273b5  shr     rcx, 1
0x1400273b8  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400273be  jnz     short loc_1400273C7
0x1400273c0  sub     dx, 2
0x1400273c4  mov     [rdi], dx
0x1400273c7  shr     dx, 1
0x1400273ca  jz      short loc_1400273F5
0x1400273cc  mov     r8, [rbx+38h]
0x1400273d0  movzx   eax, dx
0x1400273d3  movzx   ecx, word ptr [r8+rax*2-2]
0x1400273d9  cmp     cx, 5Ch ; '\'
0x1400273dd  jz      short loc_1400273F5
0x1400273df  cmp     cx, 3Ah ; ':'
0x1400273e3  jz      short loc_1400273F1
0x1400273e5  mov     eax, 0FFFFh
0x1400273ea  add     dx, ax
0x1400273ed  jnz     short loc_1400273D0
0x1400273ef  jmp     short loc_1400273F5
0x1400273f1  bts     dword ptr [rbx], 7
0x1400273f5  mov     rcx, [r14]; Context
0x1400273f8  mov     [r14], rbx
0x1400273fb  test    rcx, rcx
0x1400273fe  jz      short loc_14002740C
0x140027400  call    cs:__imp_FltReleaseContext
0x140027407  nop     dword ptr [rax+rax+00h]
0x14002740c  xor     eax, eax
0x14002740e  movaps  xmm6, [rsp+88h+var_48]
0x140027413  add     rsp, 50h
0x140027417  pop     r15
0x140027419  pop     r14
0x14002741b  pop     r12
0x14002741d  pop     rdi
0x14002741e  pop     rsi
0x14002741f  pop     rbp
0x140027420  pop     rbx
0x140027421  retn
```
