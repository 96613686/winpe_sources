# SectionCache::GetSection(wchar_t const *)

- ea: `0x180037a14`
- end: `0x180037c4b`
- name: `?GetSection@SectionCache@@QEAA?AV?$unique_ptr@VRecordCache@@U?$default_delete@VRecordCache@@@utl@@@utl@@PEB_W@Z`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180036698`

## callees

- `0x180007180`
- `0x18000c374`
- `0x18002265c`
- `0x180023548`
- `0x180035f58`
- `0x1800369c0`
- `0x180037a14`
- `0x180037cbc`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037c19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037c19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037c2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037c2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
RecordCache **__fastcall SectionCache::GetSection(__int64 a1, RecordCache **a2, __int64 a3)
{
  __int64 v5; // rdi
  __int64 v6; // rbx
  RecordCache *v7; // rax
  RecordCache *v8; // rbx
  __int64 v9; // rax
  RecordCache *v10; // rbx
  RTL_SRWLOCK *v11; // rdi
  unsigned __int64 v12; // rdx
  bool v13; // r8
  _QWORD v15[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+50h] [rbp-20h]
  int v18; // [rsp+58h] [rbp-18h]
  int v19; // [rsp+5Ch] [rbp-14h]
  int v20; // [rsp+60h] [rbp-10h]
  __int64 v21; // [rsp+A0h] [rbp+30h] BYREF

  v21 = a3;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 87);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = 87;
    v19 = -1;
    v20 = 549;
    throw (EvtException *)&pExceptionObject;
  }
  v5 = a1 + 1088;
  v6 = utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_FindImpl<wchar_t const *>(
         a1 + 1088,
         &v21);
  if ( v5 == v6 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 1168);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = 1168;
    v19 = -1;
    v20 = 556;
    throw (EvtException *)&pExceptionObject;
  }
  v7 = (RecordCache *)MIDL_user_allocate(0x438u);
  v21 = (__int64)v7;
  if ( v7 )
    v8 = RecordCache::RecordCache(v7, *(_QWORD *)(v6 + 64), *(_QWORD *)(v6 + 72));
  else
    v8 = 0;
  *a2 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids, 14);
    }
    pExceptionObject = 0;
    v17 = 0;
    v18 = 14;
    v19 = -1;
    v20 = 564;
    throw (EvtException *)&pExceptionObject;
  }
  v15[0] = *(_QWORD *)(a1 + 24);
  v15[1] = (__int64)(*(_QWORD *)(a1 + 32) - v15[0]) >> 1;
  v9 = MakeOrThrowOOM(&pExceptionObject, v15);
  RecordCache::OpenFile(v8, v9);
  v10 = *a2;
  v11 = (RTL_SRWLOCK *)((char *)*a2 + 64);
  v21 = (__int64)v11;
  AcquireSRWLockExclusive(v11);
  RecordCache::InternalSyncFileHeader(v10, v12, v13);
  ReleaseSRWLockExclusive(v11);
  return a2;
}

```

## disassembly

```asm
0x180037a14  mov     rax, rsp
0x180037a17  mov     [rax+8], rbx
0x180037a1b  mov     [rax+20h], rsi
0x180037a1f  mov     [rax+18h], r8
0x180037a23  mov     [rax+10h], rdx
0x180037a27  push    rbp
0x180037a28  push    rdi
0x180037a29  push    r14
0x180037a2b  mov     rbp, rsp
0x180037a2e  sub     rsp, 70h
0x180037a32  mov     rsi, rdx
0x180037a35  mov     r14, rcx
0x180037a38  mov     [rbp+var_50], 0
0x180037a3f  test    r8, r8
0x180037a42  jnz     short loc_180037AAF
0x180037a44  lea     rax, WPP_GLOBAL_Control
0x180037a4b  lea     ebx, [r8+57h]
0x180037a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a56  cmp     rcx, rax
0x180037a59  jz      short loc_180037A7D
0x180037a5b  test    byte ptr [rcx+1Ch], 1
0x180037a5f  jz      short loc_180037A7D
0x180037a61  cmp     byte ptr [rcx+19h], 2
0x180037a65  jb      short loc_180037A7D
0x180037a67  lea     edx, [rbx-3Dh]
0x180037a6a  mov     r9d, ebx
0x180037a6d  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037a74  mov     rcx, [rcx+10h]
0x180037a78  call    WPP_SF_D
0x180037a7d  xorps   xmm0, xmm0
0x180037a80  movdqu  [rbp+pExceptionObject], xmm0
0x180037a85  mov     [rbp+var_20], 0
0x180037a8d  mov     [rbp+var_18], ebx
0x180037a90  mov     [rbp+var_14], 0FFFFFFFFh
0x180037a97  mov     [rbp+var_10], 225h
0x180037a9e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037aa5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037aa9  call    _CxxThrowException_0
0x180037aaf  lea     rdi, [rcx+440h]
0x180037ab6  lea     rdx, [rbp+arg_10]
0x180037aba  mov     rcx, rdi
0x180037abd  call    ??$_FindImpl@PEB_W@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@2@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@USectionHeader@SectionCache@@@utl@@@1@AEBQEB_W@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,SectionCache::SectionHeader>>,0>::_FindImpl<wchar_t const *>(wchar_t const * const &)
0x180037ac2  mov     rbx, rax
0x180037ac5  cmp     rdi, rax
0x180037ac8  jnz     short loc_180037B38
0x180037aca  lea     rax, WPP_GLOBAL_Control
0x180037ad1  mov     ebx, 490h
0x180037ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x180037add  cmp     rcx, rax
0x180037ae0  jz      short loc_180037B06
0x180037ae2  test    byte ptr [rcx+1Ch], 1
0x180037ae6  jz      short loc_180037B06
0x180037ae8  cmp     byte ptr [rcx+19h], 2
0x180037aec  jb      short loc_180037B06
0x180037aee  mov     edx, 1Bh
0x180037af3  mov     r9d, ebx
0x180037af6  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037afd  mov     rcx, [rcx+10h]
0x180037b01  call    WPP_SF_D
0x180037b06  xorps   xmm0, xmm0
0x180037b09  movdqu  [rbp+pExceptionObject], xmm0
0x180037b0e  mov     [rbp+var_20], 0
0x180037b16  mov     [rbp+var_18], ebx
0x180037b19  mov     [rbp+var_14], 0FFFFFFFFh
0x180037b20  mov     [rbp+var_10], 22Ch
0x180037b27  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037b2e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037b32  call    _CxxThrowException_0
0x180037b38  mov     ecx, 438h; size
0x180037b3d  call    MIDL_user_allocate
0x180037b42  mov     [rbp+arg_10], rax
0x180037b46  test    rax, rax
0x180037b49  jz      short loc_180037B60
0x180037b4b  mov     r8, [rbx+48h]; unsigned __int64
0x180037b4f  mov     rdx, [rbx+40h]; unsigned __int64
0x180037b53  mov     rcx, rax; this
0x180037b56  call    ??0RecordCache@@QEAA@_K0@Z; RecordCache::RecordCache(unsigned __int64,unsigned __int64)
0x180037b5b  mov     rbx, rax
0x180037b5e  jmp     short loc_180037B62
0x180037b60  xor     ebx, ebx
0x180037b62  mov     [rsi], rbx
0x180037b65  mov     [rbp+var_50], 3
0x180037b6c  test    rbx, rbx
0x180037b6f  jnz     short loc_180037BDD
0x180037b71  lea     rax, WPP_GLOBAL_Control
0x180037b78  mov     ebx, 0Eh
0x180037b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180037b84  cmp     rcx, rax
0x180037b87  jz      short loc_180037BAB
0x180037b89  test    byte ptr [rcx+1Ch], 1
0x180037b8d  jz      short loc_180037BAB
0x180037b8f  cmp     byte ptr [rcx+19h], 2
0x180037b93  jb      short loc_180037BAB
0x180037b95  lea     edx, [rbx+0Eh]
0x180037b98  mov     r9d, ebx
0x180037b9b  lea     r8, WPP_ed4ad13171c934ad5ef7c6740982dc1b_Traceguids
0x180037ba2  mov     rcx, [rcx+10h]
0x180037ba6  call    WPP_SF_D
0x180037bab  xorps   xmm0, xmm0
0x180037bae  movdqu  [rbp+pExceptionObject], xmm0
0x180037bb3  mov     [rbp+var_20], 0
0x180037bbb  mov     [rbp+var_18], ebx
0x180037bbe  mov     [rbp+var_14], 0FFFFFFFFh
0x180037bc5  mov     [rbp+var_10], 234h
0x180037bcc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180037bd3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180037bd7  call    _CxxThrowException_0
0x180037bdd  mov     rax, [r14+18h]
0x180037be1  mov     [rbp+var_40], rax
0x180037be5  mov     rcx, [r14+20h]
0x180037be9  sub     rcx, rax
0x180037bec  sar     rcx, 1
0x180037bef  mov     [rbp+var_38], rcx
0x180037bf3  lea     rdx, [rbp+var_40]
0x180037bf7  lea     rcx, [rbp+pExceptionObject]
0x180037bfb  call    ?MakeOrThrowOOM@@YA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; MakeOrThrowOOM(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180037c00  mov     rdx, rax
0x180037c03  mov     rcx, rbx; this
0x180037c06  call    ?OpenFile@RecordCache@@QEAAXV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N1@Z; RecordCache::OpenFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,bool,bool)
0x180037c0b  mov     rbx, [rsi]
0x180037c0e  lea     rdi, [rbx+40h]
0x180037c12  mov     [rbp+arg_10], rdi
0x180037c16  mov     rcx, rdi; SRWLock
0x180037c19  call    cs:__imp_AcquireSRWLockExclusive
0x180037c1f  nop
0x180037c20  mov     rcx, rbx; this
0x180037c23  call    ?InternalSyncFileHeader@RecordCache@@AEAAX_K_N@Z; RecordCache::InternalSyncFileHeader(unsigned __int64,bool)
0x180037c28  nop
0x180037c29  mov     rcx, rdi; SRWLock
0x180037c2c  call    cs:__imp_ReleaseSRWLockExclusive
0x180037c32  mov     rax, rsi
0x180037c35  lea     r11, [rsp+70h+var_s0]
0x180037c3a  mov     rbx, [r11+20h]
0x180037c3e  mov     rsi, [r11+38h]
0x180037c42  mov     rsp, r11
0x180037c45  pop     r14
0x180037c47  pop     rdi
0x180037c48  pop     rbp
0x180037c49  retn
```
