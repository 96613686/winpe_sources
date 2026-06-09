# ResourceLoader6::ResourceCache::GetModule(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180042c1c`
- end: `0x180042dc9`
- name: `?GetModule@ResourceCache@ResourceLoader6@@QEAAPEAUHINSTANCE__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `429`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18002b820`

## callees

- `0x180022c40`
- `0x180022c6c`
- `0x180041d5c`
- `0x180042c1c`
- `0x180042f6c`
- `0x18004336c`
- `0x18006144c`
- `0x18008b074`
- `0x180095774`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180042d2a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180042d2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042c9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042cb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042c9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180042cb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042db0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180042db0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180042c3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180042c3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042cc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180042cc2`

## pseudocode

```c
__int64 __fastcall ResourceLoader6::ResourceCache::GetModule(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rax
  std::_Ref_count_base *v6; // rcx
  __int64 v7; // rdi
  _QWORD *v8; // rdi
  const WCHAR *v9; // rcx
  _QWORD *v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v16; // [rsp+20h] [rbp-40h] BYREF
  std::_Ref_count_base *v17; // [rsp+28h] [rbp-38h]
  char v18[8]; // [rsp+30h] [rbp-30h] BYREF
  std::_Ref_count_base *v19; // [rsp+38h] [rbp-28h]
  _BYTE v20[16]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h]
  _QWORD *v22; // [rsp+80h] [rbp+20h] BYREF
  RTL_SRWLOCK *v23; // [rsp+98h] [rbp+38h]

  v22 = a1;
  AcquireSRWLockShared(&SRWLock);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
    &xmmword_180120A28,
    v20,
    a2);
  v3 = v21;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring const,std::shared_ptr<Windows::Globalization::Spelling::CWordlist>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Globalization::Spelling::CWordlist>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                          v4,
                          v21,
                          a2)
    && v3 != (_QWORD)xmmword_180120A28 )
  {
    v5 = *(_QWORD *)(v3 + 72);
    if ( v5 )
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
    v6 = *(std::_Ref_count_base **)(v3 + 72);
    v7 = *(_QWORD *)(*(_QWORD *)(v3 + 64) + 8LL);
    if ( v7 )
    {
      if ( v6 )
        std::_Ref_count_base::_Decref(v6);
      ReleaseSRWLockShared(&SRWLock);
      return v7;
    }
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
  }
  ReleaseSRWLockShared(&SRWLock);
  v23 = &SRWLock;
  AcquireSRWLockExclusive(&SRWLock);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
    &xmmword_180120A28,
    &v22,
    a2);
  if ( v22 == (_QWORD *)xmmword_180120A28 || (v7 = *(_QWORD *)(v22[8] + 8LL)) == 0 )
  {
    v8 = operator new(0x10u);
    v22 = v8;
    *v8 = &ResourceLoader6::ResourceHolder::`vftable';
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v9 = (const WCHAR *)a2;
    else
      v9 = *(const WCHAR **)a2;
    v8[1] = LoadLibraryExW(v9, 0, 2u);
    std::shared_ptr<ResourceLoader6::ResourceHolder>::shared_ptr<ResourceLoader6::ResourceHolder>(&v16, v8);
    v7 = *(_QWORD *)(v16 + 8);
    if ( v7 )
    {
      v10 = (_QWORD *)std::map<std::wstring const,std::shared_ptr<Windows::Globalization::Spelling::CWordlist>>::_Try_emplace<std::wstring const &,>(
                        &xmmword_180120A28,
                        v20,
                        a2);
      v11 = (__int64 *)std::shared_ptr<Windows::Globalization::Spelling::CWordlist>::shared_ptr<Windows::Globalization::Spelling::CWordlist>(
                         v18,
                         &v16,
                         *v10);
      v12 = *v11;
      *v11 = *(_QWORD *)(v13 + 64);
      *(_QWORD *)(v13 + 64) = v12;
      v14 = v11[1];
      v11[1] = *(_QWORD *)(v13 + 72);
      *(_QWORD *)(v13 + 72) = v14;
      if ( v19 )
        std::_Ref_count_base::_Decref(v19);
    }
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
  }
  ReleaseSRWLockExclusive(&SRWLock);
  return v7;
}

```

## disassembly

```asm
0x180042c1c  mov     [rsp-18h+arg_8], rbx
0x180042c21  mov     [rsp-18h+arg_0], rcx
0x180042c26  push    rbp
0x180042c27  push    rsi
0x180042c28  push    rdi
0x180042c29  mov     rbp, rsp
0x180042c2c  sub     rsp, 60h
0x180042c30  mov     rbx, rdx
0x180042c33  lea     rsi, SRWLock
0x180042c3a  mov     rcx, rsi; SRWLock
0x180042c3d  call    cs:__imp_AcquireSRWLockShared
0x180042c43  mov     r8, rbx
0x180042c46  lea     rdx, [rbp+var_20]
0x180042c4a  lea     rcx, xmmword_180120A28
0x180042c51  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180042c56  mov     r8, rbx
0x180042c59  mov     rdi, [rbp+var_10]
0x180042c5d  mov     rdx, rdi
0x180042c60  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCWordlist@Spelling@Globalization@Windows@@@2@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCWordlist@Spelling@Globalization@Windows@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCWordlist@Spelling@Globalization@Windows@@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::shared_ptr<Windows::Globalization::Spelling::CWordlist>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Globalization::Spelling::CWordlist>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<Windows::Globalization::Spelling::CWordlist>>,void *> * const,std::wstring const &)
0x180042c65  test    al, al
0x180042c67  jz      short loc_180042CB2
0x180042c69  cmp     rdi, qword ptr cs:xmmword_180120A28
0x180042c70  jz      short loc_180042CB2
0x180042c72  mov     rax, [rdi+48h]
0x180042c76  test    rax, rax
0x180042c79  jz      short loc_180042C7F
0x180042c7b  lock inc dword ptr [rax+8]
0x180042c7f  mov     rcx, [rdi+48h]; this
0x180042c83  mov     rax, [rdi+40h]
0x180042c87  mov     rdi, [rax+8]
0x180042c8b  test    rdi, rdi
0x180042c8e  jz      short loc_180042CA8
0x180042c90  test    rcx, rcx
0x180042c93  jz      short loc_180042C9A
0x180042c95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042c9a  mov     rcx, rsi; SRWLock
0x180042c9d  call    cs:__imp_ReleaseSRWLockShared
0x180042ca3  jmp     loc_180042DB6
0x180042ca8  test    rcx, rcx
0x180042cab  jz      short loc_180042CB2
0x180042cad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042cb2  mov     rcx, rsi; SRWLock
0x180042cb5  call    cs:__imp_ReleaseSRWLockShared
0x180042cbb  mov     [rbp+arg_18], rsi
0x180042cbf  mov     rcx, rsi; SRWLock
0x180042cc2  call    cs:__imp_AcquireSRWLockExclusive
0x180042cc8  nop
0x180042cc9  mov     r8, rbx
0x180042ccc  lea     rdx, [rbp+arg_0]
0x180042cd0  lea     rcx, xmmword_180120A28
0x180042cd7  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180042cdc  mov     rax, [rbp+arg_0]
0x180042ce0  cmp     rax, qword ptr cs:xmmword_180120A28
0x180042ce7  jz      short loc_180042CFA
0x180042ce9  mov     rcx, [rax+40h]
0x180042ced  mov     rdi, [rcx+8]
0x180042cf1  test    rdi, rdi
0x180042cf4  jnz     loc_180042DAD
0x180042cfa  mov     ecx, 10h; Size
0x180042cff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042d04  mov     rdi, rax
0x180042d07  mov     [rbp+arg_0], rax
0x180042d0b  lea     rax, ??_7ResourceHolder@ResourceLoader6@@6B@; const ResourceLoader6::ResourceHolder::`vftable'
0x180042d12  mov     [rdi], rax
0x180042d15  cmp     qword ptr [rbx+18h], 7
0x180042d1a  jbe     short loc_180042D21
0x180042d1c  mov     rcx, [rbx]
0x180042d1f  jmp     short loc_180042D24
0x180042d21  mov     rcx, rbx; lpLibFileName
0x180042d24  xor     edx, edx; hFile
0x180042d26  lea     r8d, [rdx+2]; dwFlags
0x180042d2a  call    cs:__imp_LoadLibraryExW
0x180042d30  mov     [rdi+8], rax
0x180042d34  mov     rdx, rdi
0x180042d37  lea     rcx, [rbp+var_40]
0x180042d3b  call    ??$?0VResourceHolder@ResourceLoader6@@$0A@@?$shared_ptr@VResourceHolder@ResourceLoader6@@@std@@QEAA@PEAVResourceHolder@ResourceLoader6@@@Z; std::shared_ptr<ResourceLoader6::ResourceHolder>::shared_ptr<ResourceLoader6::ResourceHolder>(ResourceLoader6::ResourceHolder *)
0x180042d40  nop
0x180042d41  mov     rax, [rbp+var_40]
0x180042d45  mov     rdi, [rax+8]
0x180042d49  test    rdi, rdi
0x180042d4c  jz      short loc_180042D9E
0x180042d4e  mov     r8, rbx
0x180042d51  lea     rdx, [rbp+var_20]
0x180042d55  lea     rcx, xmmword_180120A28
0x180042d5c  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCWordlist@Spelling@Globalization@Windows@@@2@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCWordlist@Spelling@Globalization@Windows@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCWordlist@Spelling@Globalization@Windows@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring const,std::shared_ptr<Windows::Globalization::Spelling::CWordlist>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180042d61  mov     r8, [rax]
0x180042d64  lea     rdx, [rbp+var_40]
0x180042d68  lea     rcx, [rbp+var_30]
0x180042d6c  call    ??0?$shared_ptr@VCWordlist@Spelling@Globalization@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Globalization::Spelling::CWordlist>::shared_ptr<Windows::Globalization::Spelling::CWordlist>(std::shared_ptr<Windows::Globalization::Spelling::CWordlist> const &)
0x180042d71  mov     rdx, [rax]
0x180042d74  mov     rcx, [r8+40h]
0x180042d78  mov     [rax], rcx
0x180042d7b  mov     [r8+40h], rdx
0x180042d7f  mov     rdx, [rax+8]
0x180042d83  mov     rcx, [r8+48h]
0x180042d87  mov     [rax+8], rcx
0x180042d8b  mov     [r8+48h], rdx
0x180042d8f  mov     rcx, [rbp+var_28]; this
0x180042d93  test    rcx, rcx
0x180042d96  jz      short loc_180042D9E
0x180042d98  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042d9d  nop
0x180042d9e  mov     rcx, [rbp+var_38]; this
0x180042da2  test    rcx, rcx
0x180042da5  jz      short loc_180042DAD
0x180042da7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180042dac  nop
0x180042dad  mov     rcx, rsi; SRWLock
0x180042db0  call    cs:__imp_ReleaseSRWLockExclusive
0x180042db6  mov     rax, rdi
0x180042db9  mov     rbx, [rsp+60h+arg_8]
0x180042dc1  add     rsp, 60h
0x180042dc5  pop     rdi
0x180042dc6  pop     rsi
0x180042dc7  pop     rbp
0x180042dc8  retn
```
