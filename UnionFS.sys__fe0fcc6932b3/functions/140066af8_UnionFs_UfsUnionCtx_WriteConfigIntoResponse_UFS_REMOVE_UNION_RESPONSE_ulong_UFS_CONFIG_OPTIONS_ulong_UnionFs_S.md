# UnionFs::UfsUnionCtx::WriteConfigIntoResponse(UFS_REMOVE_UNION_RESPONSE &,ulong,UFS_CONFIG_OPTIONS,ulong *,UnionFs::StackEventTracer &)

- ea: `0x140066af8`
- end: `0x140067330`
- name: `?WriteConfigIntoResponse@UfsUnionCtx@UnionFs@@QEAAJAEAUUFS_REMOVE_UNION_RESPONSE@@KW4UFS_CONFIG_OPTIONS@@PEAKAEAVStackEventTracer@2@@Z`
- size: `2104`
- prototype: `int __high(struct UFS_REMOVE_UNION_RESPONSE *, unsigned int, enum UFS_CONFIG_OPTIONS, unsigned int *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140006a74`

## callees

- `0x140001220`
- `0x140005574`
- `0x14001014c`
- `0x140052904`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14005d040`
- `0x140066af8`
- `0x140079d44`
- `0x14007a0c0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bc40`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140066c5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066e77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066fa6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400672e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066c5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066c73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066d3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066e77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066fa6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400672e2`

## string_xrefs

- `0x1400670ce`: `API: Computing required root ID size`
- `0x1400670b3`: `UnionFs::UfsPathName::AsContainerRootId`
- `0x1400670e1`: `UnionFs::UfsPathName::AsContainerRootId`
- `0x140066cf2`: `PUSH: Reading persisted tombstones`
- `0x140066bd8`: `UnionFs::UfsUnionCtx::WriteConfigIntoResponse`
- `0x140066d03`: `UnionFs::UfsUnionCtx::WriteConfigIntoResponse`
- `0x140066e08`: `UnionFs::UfsUnionCtx::WriteConfigIntoResponse`
- `0x140066ef9`: `UnionFs::UfsUnionCtx::WriteConfigIntoResponse`
- `0x140066f81`: `UnionFs::UfsUnionCtx::WriteConfigIntoResponse`
- `0x14006710b`: `UnionFs::UfsUnionCtx::WriteConfigIntoResponse`
- `0x1400672bb`: `UnionFs::UfsUnionCtx::WriteConfigIntoResponse`
- `0x1400670fa`: `PUSH: Formatting path into response`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::WriteConfigIntoResponse(
        __int64 a1,
        _DWORD *a2,
        unsigned int a3,
        char a4,
        char *a5,
        __int64 a6)
{
  unsigned int v9; // r15d
  __int64 v11; // r8
  __int64 v12; // rax
  unsigned int v13; // r9d
  __int64 v14; // rcx
  unsigned __int16 v15; // dx
  __int64 v16; // r8
  const char *v17; // rax
  unsigned int v18; // ebx
  unsigned __int64 *v19; // rdx
  int v20; // ecx
  int v21; // r12d
  __int64 v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  PVOID v25; // rcx
  __int64 *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r9
  _WORD *v31; // rax
  unsigned __int16 v32; // cx
  unsigned __int16 v33; // cx
  __int64 v34; // rcx
  __int64 v35; // r8
  const char *v36; // rax
  PVOID v37; // rcx
  unsigned __int64 *v38; // rdx
  __int64 v39; // rbx
  __int64 v40; // r13
  __int64 v41; // rdi
  unsigned int v42; // r12d
  unsigned __int16 *v43; // rcx
  const void **v44; // rdx
  unsigned __int16 v45; // r13
  __int64 v46; // rax
  unsigned int *v47; // rbx
  unsigned __int16 v48; // ax
  unsigned __int16 v49; // ax
  __int64 v50; // rcx
  unsigned __int16 v51; // ax
  unsigned __int16 v52; // ax
  __int64 v53; // rax
  const char *v54; // rax
  __int64 v55; // r8
  const char *v56; // [rsp+28h] [rbp-D8h]
  const char *v57; // [rsp+28h] [rbp-D8h]
  PVOID P; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v59; // [rsp+58h] [rbp-A8h] BYREF
  FsFltWil::Details *v60; // [rsp+60h] [rbp-A0h] BYREF
  int v61; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v62; // [rsp+6Ch] [rbp-94h] BYREF
  int v63; // [rsp+70h] [rbp-90h] BYREF
  const char *v64; // [rsp+78h] [rbp-88h] BYREF
  PVOID v65; // [rsp+80h] [rbp-80h] BYREF
  char *v66; // [rsp+88h] [rbp-78h] BYREF
  char v67[120]; // [rsp+90h] [rbp-70h] BYREF
  char v68[8]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v69[13]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v70; // [rsp+178h] [rbp+78h]

  v9 = 28;
  *(_DWORD *)a5 = 28;
  LODWORD(v64) = a3;
  v66 = a5;
  memset(a2, 0, a3);
  FsFltWil::AcquirePushLockShared(&v60, a1 + 72);
  v12 = *(_QWORD *)(a1 + 48);
  v13 = 0;
  v14 = *(_QWORD *)(a1 + 56);
  while ( 1 )
  {
    v59 = v13;
    if ( v12 == v14 )
      break;
    v15 = **(_WORD **)(*(_QWORD *)v12 + 16LL) + 6;
    if ( v15 < 6u )
    {
      v17 = "API: Root ID Size";
      v16 = 0x50700200123LL;
      goto LABEL_9;
    }
    LODWORD(v11) = v9 + 8;
    if ( v9 + 8 < v9 )
    {
      v16 = 0x50600200128LL;
LABEL_8:
      v17 = "API: Response Size";
LABEL_9:
      v18 = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        a6,
        (struct UnionFs::StackEventTracer *)v16,
        (unsigned __int64)"UnionFs::UfsUnionCtx::WriteConfigIntoResponse",
        v17,
        v56);
LABEL_24:
      if ( v60 )
        FsFltWil::Details::ReleasePushLockShared(v60, v19);
      return v18;
    }
    v9 = v11 + v15;
    if ( v9 < (unsigned int)v11 )
    {
      v16 = 0x5D70020012DLL;
      goto LABEL_8;
    }
    ++v13;
    v12 += 16;
  }
  v20 = 0;
  P = 0;
  v21 = 0;
  v63 = 0;
  v61 = 0;
  v22 = 4;
  if ( (a4 & 1) == 0 )
  {
    v63 = 1024;
    v23 = (void **)utl::make_unique_pool<enum gsl::byte [0],256,1668630101,0>(&v65);
    v24 = *v23;
    *v23 = 0;
    v25 = P;
    P = v24;
    if ( v25 )
      ExFreePoolWithTag(v25, 0);
    if ( v65 )
      ExFreePoolWithTag(v65, 0);
    if ( !P )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a6,
        (struct UnionFs::StackEventTracer *)0x8300200148LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::WriteConfigIntoResponse",
        "ORIGIN: Allocating tombstone info buffer",
        v56);
      if ( v60 )
        FsFltWil::Details::ReleasePushLockShared(v60, v38);
      return 3221225626LL;
    }
    v62 = 0;
    v69[0] = off_14007ED00;
    v69[1] = &v62;
    v69[2] = &v63;
    v69[3] = &P;
    v70 = v69;
    v26 = (__int64 *)*((_QWORD *)UnionFs::g_FilterState + 15);
    v27 = wistd::function<void (bool)>::function<void (bool)>(v67, v68);
    v18 = UnionFs::UfsPersistenceManager::ReadPersistedPayloads(v26, a1, v27, &v61, a6);
    if ( (v18 & 0x80000000) != 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)v18,
        a6,
        (struct UnionFs::StackEventTracer *)0x8200200184LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::WriteConfigIntoResponse",
        "PUSH: Reading persisted tombstones",
        v56);
LABEL_20:
      if ( v70 )
        (*(void (__fastcall **)(_QWORD *))(*v70 + 24LL))(v70);
LABEL_22:
      if ( P )
        ExFreePoolWithTag(P, 0);
      goto LABEL_24;
    }
    if ( v61 )
    {
      v31 = P;
      LOWORD(v11) = 6;
      v29 = 4;
      while ( 1 )
      {
        if ( !v31 )
          goto LABEL_51;
        v32 = v31[3] + 6;
        if ( v32 < 6u )
        {
          v36 = "API: Root ID Size";
          v35 = 0x50900200192LL;
          goto LABEL_43;
        }
        v28 = v9 + 8;
        if ( (unsigned int)v28 < v9 )
          break;
        v9 = v28 + v32;
        if ( v9 < (unsigned int)v28 )
        {
          v35 = 0x50A0020019ELL;
LABEL_42:
          v36 = "API: Response Size";
LABEL_43:
          v18 = -1073741675;
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)0xC0000095LL,
            a6,
            (struct UnionFs::StackEventTracer *)v35,
            (unsigned __int64)"UnionFs::UfsUnionCtx::WriteConfigIntoResponse",
            v36,
            v56);
          goto LABEL_20;
        }
        if ( v31[2] == 4 )
        {
          v33 = v31[4] + 6;
          if ( v33 < 6u )
          {
            v36 = "API: Root ID Size";
            v35 = 0x50C002001AELL;
            goto LABEL_43;
          }
          v28 = v9 + 8;
          if ( (unsigned int)v28 < v9 )
          {
            v35 = 0x50B002001B5LL;
            goto LABEL_42;
          }
          v9 = v28 + v33;
          if ( v9 < (unsigned int)v28 )
          {
            v35 = 0x50D002001BALL;
            goto LABEL_42;
          }
          ++v21;
        }
        v34 = *(unsigned int *)v31;
        if ( (_DWORD)v34 )
          v31 = (_WORD *)((char *)v31 + v34);
        else
          v31 = 0;
      }
      v35 = 0x50800200199LL;
      goto LABEL_42;
    }
    v37 = P;
    P = 0;
    if ( v37 )
      ExFreePoolWithTag(v37, 0);
LABEL_51:
    if ( v70 )
      (*(void (__fastcall **)(_QWORD *, __int64, __int64, __int64))(*v70 + 24LL))(v70, v28, v11, v29);
    v13 = v59;
    v22 = 4;
    v20 = v61;
  }
  a2[1] = v9;
  if ( a3 >= v9 )
  {
    if ( (*(_DWORD *)(a1 + 24) & 1) != 0 )
      a2[2] |= 4u;
    if ( (*(_DWORD *)(a1 + 24) & 0x20) != 0 )
      a2[2] |= 8u;
    if ( (*(_DWORD *)(a1 + 24) & 0x80u) != 0 )
      a2[2] |= 0x10u;
    a2[3] = v13;
    v39 = *(_QWORD *)(a1 + 48);
    v40 = 0;
    v41 = *(_QWORD *)(a1 + 56);
    v62 = v21 + v20;
    v42 = 8 * (v21 + v20 + v13) + 20;
    while ( 1 )
    {
      v59 = v40;
      if ( v39 == v41 )
        break;
      v43 = (unsigned __int16 *)((char *)a2 + v42);
      if ( !v43 && (_DWORD)v64 != v42 )
      {
        gsl::details::terminate(0);
        JUMPOUT(0x14006732FLL);
      }
      v44 = *(const void ***)(*(_QWORD *)v39 + 16LL);
      v45 = *(_WORD *)v44 + 6;
      if ( v45 < 6u )
      {
        v18 = -1073741675;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)0xC0000095LL,
          a6,
          (struct UnionFs::StackEventTracer *)0x62E001301A7LL,
          (unsigned __int64)"UnionFs::UfsPathName::AsContainerRootId",
          "API: Computing required root ID size",
          v56);
        goto LABEL_78;
      }
      if ( (unsigned int)v64 - v42 < (unsigned __int64)v45 )
      {
        v18 = -1073741789;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000023LL,
          a6,
          (struct UnionFs::StackEventTracer *)0x62F001301ADLL,
          (unsigned __int64)"UnionFs::UfsPathName::AsContainerRootId",
          "ORIGIN: Buffer too small",
          v56);
LABEL_78:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)v18,
          a6,
          (struct UnionFs::StackEventTracer *)0x5D90020020CLL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::WriteConfigIntoResponse",
          "PUSH: Formatting path into response",
          v57);
        goto LABEL_22;
      }
      *v43 = v45;
      v43[1] = *((_WORD *)v44 + 12);
      v43[2] = *(_WORD *)v44;
      memmove(v43 + 3, v44[1], *(unsigned __int16 *)v44);
      v46 = v59;
      LOWORD(a2[2 * v59 + 6]) = v45;
      a2[2 * v46 + 5] = v42;
      v42 += v45;
      v40 = v59 + 1;
      v39 += 16;
    }
    if ( v61 )
    {
      v47 = (unsigned int *)P;
      a2[4] = v62;
      while ( 1 )
      {
        if ( !v47 )
          goto LABEL_98;
        a2[2 * v40 + 5] = v42;
        v48 = *((_WORD *)v47 + 3) + 6;
        if ( v48 < 6u )
          break;
        LOWORD(a2[2 * v40 + 6]) = v48;
        HIWORD(a2[2 * v40 + 6]) = *((_WORD *)v47 + 2);
        v49 = *((_WORD *)v47 + 3) + 6;
        if ( v49 < 6u )
        {
          *(_WORD *)((char *)a2 + v42) = -1;
          v54 = "API: Tombstone Id size";
          v55 = 0x50F0020023ALL;
          goto LABEL_97;
        }
        *(_WORD *)((char *)a2 + v42) = v49;
        *(_WORD *)((char *)a2 + v42 + 2) = 0;
        *(_WORD *)((char *)a2 + v42 + 4) = *((_WORD *)v47 + 3);
        memmove((char *)a2 + v42 + 6, v47 + 4, *((unsigned __int16 *)v47 + 3));
        v50 = v42 + LOWORD(a2[2 * v40 + 6]);
        v40 = (unsigned int)(v40 + 1);
        LODWORD(v64) = v50;
        if ( *((_WORD *)v47 + 2) == 4 )
        {
          a2[2 * v40 + 5] = v50;
          v51 = *((_WORD *)v47 + 4) + 6;
          if ( v51 < 6u )
          {
            v54 = "API: Root Id length";
            v55 = 0x51000200251LL;
LABEL_96:
            LOWORD(a2[2 * v40 + 6]) = -1;
            goto LABEL_97;
          }
          LOWORD(a2[2 * v40 + 6]) = v51;
          HIWORD(a2[2 * v40 + 6]) = 0;
          v52 = *((_WORD *)v47 + 4) + 6;
          if ( v52 < 6u )
          {
            *(_WORD *)((char *)a2 + v50) = -1;
            v54 = "API: Tombstone Id size";
            v55 = 0x5110020025FLL;
LABEL_97:
            v18 = -1073741675;
            UnionFs::ProcessTraceStatusFromApi(
              (UnionFs *)0xC0000095LL,
              a6,
              (struct UnionFs::StackEventTracer *)v55,
              (unsigned __int64)"UnionFs::UfsUnionCtx::WriteConfigIntoResponse",
              v54,
              v56);
            goto LABEL_22;
          }
          *(_WORD *)((char *)a2 + v50) = v52;
          *(_WORD *)((char *)a2 + v50 + 2) = 0;
          *(_WORD *)((char *)a2 + v50 + 4) = *((_WORD *)v47 + 4);
          memmove((char *)a2 + v50 + 6, (char *)v47 + v47[3], *((unsigned __int16 *)v47 + 4));
          v42 = (_DWORD)v64 + LOWORD(a2[2 * v40 + 6]);
          v40 = (unsigned int)(v40 + 1);
        }
        else
        {
          v42 = v50;
        }
        v53 = *v47;
        if ( (_DWORD)v53 )
          v47 = (unsigned int *)((char *)v47 + v53);
        else
          v47 = 0;
      }
      v54 = "API: Root Id Length";
      v55 = 0x50E0020022BLL;
      goto LABEL_96;
    }
LABEL_98:
    *(_DWORD *)v66 = v9;
  }
  else
  {
    if ( (unsigned int)dword_14009E178 > 3 )
    {
      v22 = 256;
      if ( (qword_14009E188 & 0x100) != 0 && (qword_14009E190 & 0x100) == qword_14009E190 )
      {
        v62 = v9;
        v65 = "onecore\\base\\fs\\unionfs\\sys\\unionctx.cpp";
        v59 = a3;
        v66 = "Buffer overflow";
        v61 = 474;
        v64 = "UnionFs::UfsUnionCtx::WriteConfigIntoResponse";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14009E190,
          (unsigned int)&unk_140099968,
          v11,
          (unsigned int)"UnionFs::UfsUnionCtx::WriteConfigIntoResponse",
          (__int64)&v66,
          (__int64)&v64,
          (__int64)&v65,
          (__int64)&v61,
          (__int64)&v59,
          (__int64)&v62);
      }
    }
    *a2 = -2147483643;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v60 )
    FsFltWil::Details::ReleasePushLockShared(v60, (unsigned __int64 *)v22);
  return 0;
}

```

## disassembly

```asm
0x140066af8  mov     [rsp-8+arg_18], rbx
0x140066afd  push    rbp
0x140066afe  push    rsi
0x140066aff  push    rdi
0x140066b00  push    r12
0x140066b02  push    r13
0x140066b04  push    r14
0x140066b06  push    r15
0x140066b08  lea     rbp, [rsp-90h]
0x140066b10  sub     rsp, 190h
0x140066b17  mov     rax, cs:__security_cookie
0x140066b1e  xor     rax, rsp
0x140066b21  mov     [rbp+0C0h+var_40], rax
0x140066b28  mov     rax, [rbp+0C0h+arg_20]
0x140066b2f  mov     rsi, rdx
0x140066b32  mov     r14, qword ptr [rbp+0C0h+arg_28]
0x140066b39  mov     rdi, rcx
0x140066b3c  mov     r13d, r8d
0x140066b3f  mov     r15d, 1Ch
0x140066b45  mov     r8d, r8d; Size
0x140066b48  xor     edx, edx; Val
0x140066b4a  mov     rcx, rsi; void *
0x140066b4d  mov     [rax], r15d
0x140066b50  mov     ebx, r9d
0x140066b53  mov     dword ptr [rsp+1C0h+var_148], r13d
0x140066b58  mov     [rbp+0C0h+var_138], rax
0x140066b5c  call    memset
0x140066b61  lea     rdx, [rdi+48h]
0x140066b65  lea     rcx, [rsp+1C0h+var_160]
0x140066b6a  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140066b6f  mov     rax, [rdi+30h]
0x140066b73  xor     r9d, r9d
0x140066b76  mov     rcx, [rdi+38h]
0x140066b7a  mov     [rsp+1C0h+var_168], r9d
0x140066b7f  cmp     rax, rcx
0x140066b82  jz      loc_140066C0B
0x140066b88  mov     rdx, [rax]
0x140066b8b  mov     r8, [rdx+10h]
0x140066b8f  movzx   edx, word ptr [r8]
0x140066b93  add     dx, 6
0x140066b97  cmp     dx, 6
0x140066b9b  jb      short loc_140066BF8
0x140066b9d  lea     r8d, [r15+8]
0x140066ba1  cmp     r8d, r15d
0x140066ba4  jb      short loc_140066BEC
0x140066ba6  movzx   r15d, dx
0x140066baa  add     r15d, r8d
0x140066bad  cmp     r15d, r8d
0x140066bb0  jb      short loc_140066BBB
0x140066bb2  inc     r9d
0x140066bb5  add     rax, 10h
0x140066bb9  jmp     short loc_140066B7A
0x140066bbb  mov     r8, 5D70020012Dh; struct UnionFs::StackEventTracer *
0x140066bc5  lea     rax, aApiResponseSiz; "API: Response Size"
0x140066bcc  mov     ebx, 0C0000095h
0x140066bd1  mov     [rsp+1C0h+var_1A0], rax; char *
0x140066bd6  mov     ecx, ebx; this
0x140066bd8  lea     r9, aUnionfsUfsunio_18; "UnionFs::UfsUnionCtx::WriteConfigIntoRe"...
0x140066bdf  mov     rdx, r14; int
0x140066be2  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140066be7  jmp     loc_140066D46
0x140066bec  mov     r8, 50600200128h
0x140066bf6  jmp     short loc_140066BC5
0x140066bf8  lea     rax, aApiRootIdSize_0; "API: Root ID Size"
0x140066bff  mov     r8, 50700200123h
0x140066c09  jmp     short loc_140066BCC
0x140066c0b  xor     ecx, ecx
0x140066c0d  mov     [rsp+1C0h+P], 0
0x140066c16  xor     r12d, r12d
0x140066c19  mov     [rsp+1C0h+var_150], 0
0x140066c21  mov     [rsp+1C0h+var_158], ecx
0x140066c25  lea     edx, [rcx+4]
0x140066c28  test    bl, 1
0x140066c2b  jnz     loc_140066EA6
0x140066c31  mov     edx, 400h
0x140066c36  lea     rcx, [rbp+0C0h+var_140]
0x140066c3a  mov     [rsp+1C0h+var_150], edx
0x140066c3e  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GDHFEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1668630101,0>(unsigned __int64)
0x140066c43  xor     ebx, ebx
0x140066c45  mov     rdx, [rax]
0x140066c48  mov     [rax], rbx
0x140066c4b  mov     rcx, [rsp+1C0h+P]; P
0x140066c50  mov     [rsp+1C0h+P], rdx
0x140066c55  test    rcx, rcx
0x140066c58  jz      short loc_140066C68
0x140066c5a  xor     edx, edx; Tag
0x140066c5c  call    cs:__imp_ExFreePoolWithTag
0x140066c63  nop     dword ptr [rax+rax+00h]
0x140066c68  mov     rcx, [rbp+0C0h+var_140]; P
0x140066c6c  test    rcx, rcx
0x140066c6f  jz      short loc_140066C7F
0x140066c71  xor     edx, edx; Tag
0x140066c73  call    cs:__imp_ExFreePoolWithTag
0x140066c7a  nop     dword ptr [rax+rax+00h]
0x140066c7f  cmp     [rsp+1C0h+P], rbx
0x140066c84  jz      loc_140066F6E
0x140066c8a  lea     rax, off_14007ED00
0x140066c91  mov     [rsp+1C0h+var_154], ebx
0x140066c95  mov     [rbp+0C0h+var_B0], rax
0x140066c99  lea     rdx, [rbp+0C0h+var_B8]
0x140066c9d  lea     rax, [rsp+1C0h+var_154]
0x140066ca2  mov     [rbp+0C0h+var_A8], rax
0x140066ca6  lea     rcx, [rbp+0C0h+var_130]
0x140066caa  lea     rax, [rsp+1C0h+var_150]
0x140066caf  mov     [rbp+0C0h+var_A0], rax
0x140066cb3  lea     rax, [rsp+1C0h+P]
0x140066cb8  mov     [rbp+0C0h+var_98], rax
0x140066cbc  lea     rax, [rbp+0C0h+var_B0]
0x140066cc0  mov     [rbp+0C0h+var_48], rax
0x140066cc4  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140066ccb  mov     rbx, [rax+78h]
0x140066ccf  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x140066cd4  lea     r9, [rsp+1C0h+var_158]
0x140066cd9  mov     [rsp+1C0h+var_1A0], r14
0x140066cde  mov     r8, rax
0x140066ce1  mov     rdx, rdi
0x140066ce4  mov     rcx, rbx
0x140066ce7  call    ?ReadPersistedPayloads@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@V?$function@$$A6AJAEBUUFS_PAYLOAD_INFORMATION@UnionFs@@AEBUUFS_PAYLOAD_VERSION_HEADER@2@AEAVStackEventTracer@2@@Z@wistd@@PEAKAEAVStackEventTracer@2@@Z; UnionFs::UfsPersistenceManager::ReadPersistedPayloads(UnionFs::UfsUnionCtx &,wistd::function<long (UnionFs::UFS_PAYLOAD_INFORMATION const &,UnionFs::UFS_PAYLOAD_VERSION_HEADER const &,UnionFs::StackEventTracer &)>,ulong *,UnionFs::StackEventTracer &)
0x140066cec  mov     ebx, eax
0x140066cee  test    eax, eax
0x140066cf0  jns     short loc_140066D5C
0x140066cf2  lea     rax, aPushReadingPer; "PUSH: Reading persisted tombstones"
0x140066cf9  mov     r8, 8200200184h; struct UnionFs::StackEventTracer *
0x140066d03  lea     r9, aUnionfsUfsunio_18; "UnionFs::UfsUnionCtx::WriteConfigIntoRe"...
0x140066d0a  mov     [rsp+1C0h+var_1A0], rax; char *
0x140066d0f  mov     rdx, r14; int
0x140066d12  mov     ecx, ebx; this
0x140066d14  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140066d19  mov     rcx, [rbp+0C0h+var_48]
0x140066d1d  test    rcx, rcx
0x140066d20  jz      short loc_140066D2E
0x140066d22  mov     rax, [rcx]
0x140066d25  mov     rax, [rax+18h]
0x140066d29  call    _guard_dispatch_icall
0x140066d2e  mov     rcx, [rsp+1C0h+P]; P
0x140066d33  test    rcx, rcx
0x140066d36  jz      short loc_140066D46
0x140066d38  xor     edx, edx; Tag
0x140066d3a  call    cs:__imp_ExFreePoolWithTag
0x140066d41  nop     dword ptr [rax+rax+00h]
0x140066d46  mov     rcx, [rsp+1C0h+var_160]; this
0x140066d4b  test    rcx, rcx
0x140066d4e  jz      short loc_140066D55
0x140066d50  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140066d55  mov     eax, ebx
0x140066d57  jmp     loc_1400672FF
0x140066d5c  cmp     [rsp+1C0h+var_158], r12d
0x140066d61  jbe     loc_140066E66
0x140066d67  mov     rax, [rsp+1C0h+P]
0x140066d6c  mov     r8w, 6
0x140066d71  mov     r9d, 4
0x140066d77  test    rax, rax
0x140066d7a  jz      loc_140066E83
0x140066d80  movzx   ecx, word ptr [rax+6]
0x140066d84  add     cx, r8w
0x140066d88  cmp     cx, r8w
0x140066d8c  jb      loc_140066E53
0x140066d92  lea     edx, [r15+8]
0x140066d96  cmp     edx, r15d
0x140066d99  jb      loc_140066E47
0x140066d9f  movzx   r15d, cx
0x140066da3  add     r15d, edx
0x140066da6  cmp     r15d, edx
0x140066da9  jb      loc_140066E3B
0x140066daf  cmp     [rax+4], r9w
0x140066db4  jnz     short loc_140066DDC
0x140066db6  movzx   ecx, word ptr [rax+8]
0x140066dba  add     cx, r8w
0x140066dbe  cmp     cx, r8w
0x140066dc2  jb      short loc_140066E28
0x140066dc4  lea     edx, [r15+8]
0x140066dc8  cmp     edx, r15d
0x140066dcb  jb      short loc_140066E1C
0x140066dcd  movzx   r15d, cx
0x140066dd1  add     r15d, edx
0x140066dd4  cmp     r15d, edx
0x140066dd7  jb      short loc_140066DEB
0x140066dd9  inc     r12d
0x140066ddc  mov     ecx, [rax]
0x140066dde  test    ecx, ecx
0x140066de0  jz      short loc_140066DE7
0x140066de2  add     rax, rcx
0x140066de5  jmp     short loc_140066D77
0x140066de7  xor     eax, eax
0x140066de9  jmp     short loc_140066D77
0x140066deb  mov     r8, 50D002001BAh; struct UnionFs::StackEventTracer *
0x140066df5  lea     rax, aApiResponseSiz; "API: Response Size"
0x140066dfc  mov     ebx, 0C0000095h
0x140066e01  mov     [rsp+1C0h+var_1A0], rax; char *
0x140066e06  mov     ecx, ebx; this
0x140066e08  lea     r9, aUnionfsUfsunio_18; "UnionFs::UfsUnionCtx::WriteConfigIntoRe"...
0x140066e0f  mov     rdx, r14; int
0x140066e12  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140066e17  jmp     loc_140066D19
0x140066e1c  mov     r8, 50B002001B5h
0x140066e26  jmp     short loc_140066DF5
0x140066e28  lea     rax, aApiRootIdSize_0; "API: Root ID Size"
0x140066e2f  mov     r8, 50C002001AEh
0x140066e39  jmp     short loc_140066DFC
0x140066e3b  mov     r8, 50A0020019Eh
0x140066e45  jmp     short loc_140066DF5
0x140066e47  mov     r8, 50800200199h
0x140066e51  jmp     short loc_140066DF5
0x140066e53  lea     rax, aApiRootIdSize_0; "API: Root ID Size"
0x140066e5a  mov     r8, 50900200192h
0x140066e64  jmp     short loc_140066DFC
0x140066e66  mov     rcx, [rsp+1C0h+P]; P
0x140066e6b  mov     [rsp+1C0h+P], r12
0x140066e70  test    rcx, rcx
0x140066e73  jz      short loc_140066E83
0x140066e75  xor     edx, edx; Tag
0x140066e77  call    cs:__imp_ExFreePoolWithTag
0x140066e7e  nop     dword ptr [rax+rax+00h]
0x140066e83  mov     rcx, [rbp+0C0h+var_48]
0x140066e87  test    rcx, rcx
0x140066e8a  jz      short loc_140066E98
0x140066e8c  mov     rax, [rcx]
0x140066e8f  mov     rax, [rax+18h]
0x140066e93  call    _guard_dispatch_icall
0x140066e98  mov     r9d, [rsp+1C0h+var_168]
0x140066e9d  mov     edx, 4
0x140066ea2  mov     ecx, [rsp+1C0h+var_158]
0x140066ea6  mov     [rsi+4], r15d
0x140066eaa  cmp     r13d, r15d
0x140066ead  jnb     loc_140066FC8
0x140066eb3  mov     eax, cs:dword_14009E178
0x140066eb9  cmp     eax, 3
0x140066ebc  jbe     loc_140066F63
0x140066ec2  mov     rcx, cs:qword_14009E190
0x140066ec9  mov     edx, 100h
0x140066ece  mov     rax, cs:qword_14009E188
0x140066ed5  test    rdx, rax
0x140066ed8  jz      loc_140066F63
0x140066ede  mov     rax, rcx
0x140066ee1  and     rax, rdx
0x140066ee4  cmp     rax, rcx
0x140066ee7  jnz     short loc_140066F63
0x140066ee9  lea     rax, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x140066ef0  mov     [rsp+1C0h+var_154], r15d
0x140066ef5  mov     [rbp+0C0h+var_140], rax
0x140066ef9  lea     r9, aUnionfsUfsunio_18; "UnionFs::UfsUnionCtx::WriteConfigIntoRe"...
0x140066f00  lea     rax, aBufferOverflow; "Buffer overflow"
0x140066f07  mov     [rsp+1C0h+var_168], r13d
0x140066f0c  mov     [rbp+0C0h+var_138], rax
0x140066f10  lea     rdx, unk_140099968
0x140066f17  lea     rax, [rsp+1C0h+var_154]
0x140066f1c  mov     [rsp+1C0h+var_158], 1DAh
0x140066f24  mov     [rsp+1C0h+var_178], rax
0x140066f29  lea     rax, [rsp+1C0h+var_168]
0x140066f2e  mov     [rsp+1C0h+var_180], rax
0x140066f33  lea     rax, [rsp+1C0h+var_158]
0x140066f38  mov     [rsp+1C0h+var_188], rax
0x140066f3d  lea     rax, [rbp+0C0h+var_140]
0x140066f41  mov     [rsp+1C0h+var_190], rax
0x140066f46  lea     rax, [rsp+1C0h+var_148]
0x140066f4b  mov     [rsp+1C0h+var_198], rax
0x140066f50  lea     rax, [rbp+0C0h+var_138]
0x140066f54  mov     [rsp+1C0h+var_1A0], rax
0x140066f59  mov     [rsp+1C0h+var_148], r9
0x140066f5e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140066f63  mov     dword ptr [rsi], 80000005h
0x140066f69  jmp     loc_1400672D6
0x140066f6e  lea     rax, aOriginAllocati_75; "ORIGIN: Allocating tombstone info buffe"...
0x140066f75  mov     edi, 0C000009Ah
0x140066f7a  mov     ecx, edi; this
0x140066f7c  mov     [rsp+1C0h+var_1A0], rax; char *
0x140066f81  lea     r9, aUnionfsUfsunio_18; "UnionFs::UfsUnionCtx::WriteConfigIntoRe"...
0x140066f88  mov     r8, 8300200148h; struct UnionFs::StackEventTracer *
0x140066f92  mov     rdx, r14; int
0x140066f95  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140066f9a  mov     rcx, [rsp+1C0h+P]; P
0x140066f9f  test    rcx, rcx
0x140066fa2  jz      short loc_140066FB2
0x140066fa4  xor     edx, edx; Tag
0x140066fa6  call    cs:__imp_ExFreePoolWithTag
0x140066fad  nop     dword ptr [rax+rax+00h]
0x140066fb2  mov     rcx, [rsp+1C0h+var_160]; this
0x140066fb7  test    rcx, rcx
0x140066fba  jz      short loc_140066FC1
0x140066fbc  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140066fc1  mov     eax, edi
0x140066fc3  jmp     loc_1400672FF
0x140066fc8  mov     eax, [rdi+18h]
0x140066fcb  test    al, 1
0x140066fcd  jz      short loc_140066FD2
0x140066fcf  or      [rsi+8], edx
0x140066fd2  mov     eax, [rdi+18h]
0x140066fd5  test    al, 20h
0x140066fd7  jz      short loc_140066FDD
0x140066fd9  or      dword ptr [rsi+8], 8
0x140066fdd  mov     eax, [rdi+18h]
0x140066fe0  test    al, al
0x140066fe2  jns     short loc_140066FE8
0x140066fe4  or      dword ptr [rsi+8], 10h
0x140066fe8  add     ecx, r12d
0x140066feb  mov     [rsi+0Ch], r9d
0x140066fef  mov     rbx, [rdi+30h]
0x140066ff3  xor     r13d, r13d
0x140066ff6  mov     rdi, [rdi+38h]
0x140066ffa  mov     [rsp+1C0h+var_154], ecx
  ... truncated ...
```
