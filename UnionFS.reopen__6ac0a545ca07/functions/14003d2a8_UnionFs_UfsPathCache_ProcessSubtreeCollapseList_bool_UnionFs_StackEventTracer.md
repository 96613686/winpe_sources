# UnionFs::UfsPathCache::ProcessSubtreeCollapseList(bool *,UnionFs::StackEventTracer &)

- ea: `0x14003d2a8`
- end: `0x14003d54b`
- name: `?ProcessSubtreeCollapseList@UfsPathCache@UnionFs@@SAJPEA_NAEAVStackEventTracer@2@@Z`
- size: `675`
- prototype: `static int(bool *, struct UnionFs::StackEventTracer *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14005c2b0`
- `0x14006383c`
- `0x1400645d4`

## callees

- `0x140005574`
- `0x14000efa0`
- `0x14000f81c`
- `0x14003bd34`
- `0x14003c50c`
- `0x14003d2a8`
- `0x14003dc14`
- `0x140056c7c`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14003d31e`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14003d31e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d35b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d4e6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d35b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003d4e6`

## string_xrefs

- `0x14003d49c`: `UnionFs::UfsPathCache::ProcessSubtreeCollapseList`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCache::ProcessSubtreeCollapseList(bool *a1, struct UnionFs::StackEventTracer *a2)
{
  _QWORD *v4; // rbx
  PLIST_ENTRY v5; // rax
  _QWORD *v6; // rdi
  utl::_RefCountBase *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  const struct _FLT_INSTANCE *v10; // rdx
  UnionFs::UfsPathCache *v11; // rcx
  int v12; // esi
  __int16 v13; // ax
  unsigned __int16 v14; // ax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 *v17; // rcx
  utl::_RefCountBase *v18; // rcx
  const char *v20; // [rsp+28h] [rbp-D8h]
  bool v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v25; // [rsp+50h] [rbp-B0h] BYREF
  char v26; // [rsp+58h] [rbp-A8h]
  _BYTE v27[120]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 (__fastcall **v29)(); // [rsp+E0h] [rbp-20h] BYREF
  wistd *v30; // [rsp+148h] [rbp+48h]

  v23 = &v22;
  *a1 = 0;
  v22 = (__int64)&v22;
  v4 = 0;
  v25 = &v22;
  v26 = 1;
  while ( 1 )
  {
    v5 = ExInterlockedRemoveHeadList(
           (PLIST_ENTRY)((char *)UnionFs::g_FilterState + 168),
           (PKSPIN_LOCK)UnionFs::g_FilterState + 23);
    v6 = (_QWORD *)((unsigned __int64)&v5[-2] & -(__int64)(v5 != 0));
    if ( v4 )
    {
      v7 = (utl::_RefCountBase *)v4[3];
      if ( v7 )
        utl::_RefCountBase::_DecStrong(v7);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1088), v4);
    }
    if ( !v6 )
    {
      v26 = 0;
      lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()(&v25);
      return 0;
    }
    v29 = off_14007E9B8;
    v30 = (wistd *)&v29;
    v8 = wistd::function<void (bool)>::function<void (bool)>(v27, v28);
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a2, v8);
    v9 = v6[2];
    v10 = (const struct _FLT_INSTANCE *)*v6;
    v11 = (UnionFs::UfsPathCache *)v6[1];
    v21 = 0;
    v12 = UnionFs::UfsPathCache::CollapseSubtree(v11, v10, *(const struct UnionFs::UfsPathName **)(v9 + 208), &v21, a2);
    v13 = *((_WORD *)a2 + 245);
    if ( v13 )
    {
      v14 = v13 - 1;
      *((_WORD *)a2 + 245) = v14;
      v15 = 120 * (v14 + 1LL);
      v16 = *(_QWORD *)((char *)a2 + v15);
      *(_QWORD *)((char *)a2 + v15) = 0;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
    }
    if ( v12 < 0 )
    {
      v24 = v12;
      if ( !v30 )
        wistd::__throw_bad_function_call(0);
      if ( !(*(unsigned __int8 (__fastcall **)(wistd *, int *))(*(_QWORD *)v30 + 32LL))(v30, &v24) )
        break;
    }
    v4 = v6;
    if ( v12 == -1073741267 )
    {
      v17 = v23;
      if ( (__int64 *)*v23 != &v22 )
        __fastfail(3u);
      v4 = 0;
      v6[5] = v23;
      v6[4] = &v22;
      *v17 = (__int64)(v6 + 4);
      v23 = v6 + 4;
    }
    if ( v21 )
      *a1 = 1;
    if ( v30 )
      (*(void (__fastcall **)(wistd *))(*(_QWORD *)v30 + 24LL))(v30);
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v12,
    (int)a2,
    (struct UnionFs::StackEventTracer *)0x34700100200LL,
    (unsigned __int64)"UnionFs::UfsPathCache::ProcessSubtreeCollapseList",
    "PUSH: Collapsing subtree",
    v20);
  if ( v30 )
    (*(void (__fastcall **)(wistd *))(*(_QWORD *)v30 + 24LL))(v30);
  v18 = (utl::_RefCountBase *)v6[3];
  if ( v18 )
    utl::_RefCountBase::_DecStrong(v18);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1088), v6);
  v26 = 0;
  lambda_b53eba2d477466c9c18b3d9d5c4fa37a_::operator()(&v25);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14003d2a8  mov     [rsp-8+arg_10], rbx
0x14003d2ad  push    rbp
0x14003d2ae  push    rsi
0x14003d2af  push    rdi
0x14003d2b0  push    r12
0x14003d2b2  push    r13
0x14003d2b4  push    r14
0x14003d2b6  push    r15
0x14003d2b8  lea     rbp, [rsp-60h]
0x14003d2bd  sub     rsp, 160h
0x14003d2c4  mov     rax, cs:__security_cookie
0x14003d2cb  xor     rax, rsp
0x14003d2ce  mov     [rbp+90h+var_40], rax
0x14003d2d2  xor     r12d, r12d
0x14003d2d5  lea     rax, [rsp+190h+var_158]
0x14003d2da  mov     [rsp+190h+var_150], rax
0x14003d2df  mov     r14, rdx
0x14003d2e2  lea     rax, [rsp+190h+var_158]
0x14003d2e7  mov     [rcx], r12b
0x14003d2ea  mov     [rsp+190h+var_158], rax
0x14003d2ef  mov     r15, rcx
0x14003d2f2  lea     rax, [rsp+190h+var_158]
0x14003d2f7  mov     ebx, r12d
0x14003d2fa  lea     r13d, [r12+1]
0x14003d2ff  mov     [rsp+190h+var_140], rax
0x14003d304  mov     [rsp+190h+var_138], r13b
0x14003d309  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003d310  lea     rdx, [rcx+0B8h]; Lock
0x14003d317  add     rcx, 0A8h; ListHead
0x14003d31e  call    cs:__imp_ExInterlockedRemoveHeadList
0x14003d325  nop     dword ptr [rax+rax+00h]
0x14003d32a  lea     rcx, [rax-20h]
0x14003d32e  neg     rax
0x14003d331  sbb     rdi, rdi
0x14003d334  and     rdi, rcx
0x14003d337  test    rbx, rbx
0x14003d33a  jz      short loc_14003D367
0x14003d33c  mov     rcx, [rbx+18h]; this
0x14003d340  test    rcx, rcx
0x14003d343  jz      short loc_14003D34A
0x14003d345  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003d34a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003d351  mov     rdx, rbx; Entry
0x14003d354  add     rcx, 440h; Lookaside
0x14003d35b  call    cs:__imp_ExFreeToLookasideListEx
0x14003d362  nop     dword ptr [rax+rax+00h]
0x14003d367  test    rdi, rdi
0x14003d36a  jz      loc_14003D50C
0x14003d370  lea     rax, off_14007E9B8
0x14003d377  mov     [rbp+90h+var_B0], rax
0x14003d37b  lea     rdx, [rbp+90h+var_B8]
0x14003d37f  lea     rax, [rbp+90h+var_B0]
0x14003d383  lea     rcx, [rsp+190h+var_130]
0x14003d388  mov     [rbp+90h+var_48], rax
0x14003d38c  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14003d391  mov     rdx, rax
0x14003d394  mov     rcx, r14
0x14003d397  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x14003d39c  mov     r8, [rdi+10h]
0x14003d3a0  lea     r9, [rsp+190h+var_160]; bool *
0x14003d3a5  mov     rdx, [rdi]; struct _FLT_INSTANCE *
0x14003d3a8  mov     rcx, [rdi+8]; this
0x14003d3ac  mov     [rsp+190h+var_160], r12b
0x14003d3b1  mov     r8, [r8+0D0h]; struct UnionFs::UfsPathName *
0x14003d3b8  mov     [rsp+190h+var_170], r14; struct UnionFs::StackEventTracer *
0x14003d3bd  call    ?CollapseSubtree@UfsPathCache@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@PEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::CollapseSubtree(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,bool *,UnionFs::StackEventTracer &)
0x14003d3c2  mov     esi, eax
0x14003d3c4  movzx   eax, word ptr [r14+1EAh]
0x14003d3cc  test    ax, ax
0x14003d3cf  jz      short loc_14003D400
0x14003d3d1  sub     ax, r13w
0x14003d3d5  movzx   ecx, ax
0x14003d3d8  mov     [r14+1EAh], cx
0x14003d3e0  add     rcx, r13
0x14003d3e3  imul    rdx, rcx, 78h ; 'x'
0x14003d3e7  mov     rcx, [rdx+r14]
0x14003d3eb  mov     [rdx+r14], r12
0x14003d3ef  test    rcx, rcx
0x14003d3f2  jz      short loc_14003D400
0x14003d3f4  mov     rax, [rcx]
0x14003d3f7  mov     rax, [rax+18h]
0x14003d3fb  call    _guard_dispatch_icall
0x14003d400  test    esi, esi
0x14003d402  jns     short loc_14003D42A
0x14003d404  mov     rcx, [rbp+90h+var_48]; this
0x14003d408  mov     [rsp+190h+var_148], esi
0x14003d40c  test    rcx, rcx
0x14003d40f  jz      loc_14003D545
0x14003d415  mov     rax, [rcx]
0x14003d418  lea     rdx, [rsp+190h+var_148]
0x14003d41d  mov     rax, [rax+20h]
0x14003d421  call    _guard_dispatch_icall
0x14003d426  test    al, al
0x14003d428  jz      short loc_14003D48B
0x14003d42a  mov     rbx, rdi
0x14003d42d  cmp     esi, 0C000022Dh
0x14003d433  jnz     short loc_14003D463
0x14003d435  mov     rcx, [rsp+190h+var_150]
0x14003d43a  lea     rax, [rsp+190h+var_158]
0x14003d43f  cmp     [rcx], rax
0x14003d442  jnz     loc_14003D505
0x14003d448  lea     rax, [rdi+20h]
0x14003d44c  mov     rbx, r12
0x14003d44f  mov     [rax+8], rcx
0x14003d453  lea     rdx, [rsp+190h+var_158]
0x14003d458  mov     [rax], rdx
0x14003d45b  mov     [rcx], rax
0x14003d45e  mov     [rsp+190h+var_150], rax
0x14003d463  cmp     [rsp+190h+var_160], r12b
0x14003d468  jz      short loc_14003D46D
0x14003d46a  mov     [r15], r13b
0x14003d46d  mov     rcx, [rbp+90h+var_48]
0x14003d471  test    rcx, rcx
0x14003d474  jz      loc_14003D309
0x14003d47a  mov     rax, [rcx]
0x14003d47d  mov     rax, [rax+18h]
0x14003d481  call    _guard_dispatch_icall
0x14003d486  jmp     loc_14003D309
0x14003d48b  lea     rax, aPushCollapsing; "PUSH: Collapsing subtree"
0x14003d492  mov     r8, 34700100200h; struct UnionFs::StackEventTracer *
0x14003d49c  lea     r9, aUnionfsUfspath_37; "UnionFs::UfsPathCache::ProcessSubtreeCo"...
0x14003d4a3  mov     [rsp+190h+var_170], rax; char *
0x14003d4a8  mov     rdx, r14; int
0x14003d4ab  mov     ecx, esi; this
0x14003d4ad  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003d4b2  mov     rcx, [rbp+90h+var_48]
0x14003d4b6  test    rcx, rcx
0x14003d4b9  jz      short loc_14003D4C7
0x14003d4bb  mov     rax, [rcx]
0x14003d4be  mov     rax, [rax+18h]
0x14003d4c2  call    _guard_dispatch_icall
0x14003d4c7  mov     rcx, [rdi+18h]; this
0x14003d4cb  test    rcx, rcx
0x14003d4ce  jz      short loc_14003D4D5
0x14003d4d0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003d4d5  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003d4dc  mov     rdx, rdi; Entry
0x14003d4df  add     rcx, 440h; Lookaside
0x14003d4e6  call    cs:__imp_ExFreeToLookasideListEx
0x14003d4ed  nop     dword ptr [rax+rax+00h]
0x14003d4f2  lea     rcx, [rsp+190h+var_140]
0x14003d4f7  mov     [rsp+190h+var_138], r12b
0x14003d4fc  call    _lambda_b53eba2d477466c9c18b3d9d5c4fa37a___operator__
0x14003d501  mov     eax, esi
0x14003d503  jmp     short loc_14003D51D
0x14003d505  mov     ecx, 3
0x14003d50a  int     29h; Win8: RtlFailFast(ecx)
0x14003d50c  lea     rcx, [rsp+190h+var_140]
0x14003d511  mov     [rsp+190h+var_138], r12b
0x14003d516  call    _lambda_b53eba2d477466c9c18b3d9d5c4fa37a___operator__
0x14003d51b  xor     eax, eax
0x14003d51d  mov     rcx, [rbp+90h+var_40]
0x14003d521  xor     rcx, rsp; StackCookie
0x14003d524  call    __security_check_cookie
0x14003d529  mov     rbx, [rsp+190h+arg_10]
0x14003d531  add     rsp, 160h
0x14003d538  pop     r15
0x14003d53a  pop     r14
0x14003d53c  pop     r13
0x14003d53e  pop     r12
0x14003d540  pop     rdi
0x14003d541  pop     rsi
0x14003d542  pop     rbp
0x14003d543  retn
0x14003d545  call    ?__throw_bad_function_call@wistd@@YAXXZ; wistd::__throw_bad_function_call(void)
```
