# ConnectedStorage::ContainerIndex::PreMerge(std::vector<ConnectedStorage::ContainerInfo,std::allocator<ConnectedStorage::ContainerInfo>> const *,_FILETIME *,_FILETIME *)

- ea: `0x180065134`
- end: `0x180065541`
- name: `?PreMerge@ContainerIndex@ConnectedStorage@@QEBAXPEBV?$vector@UContainerInfo@ConnectedStorage@@V?$allocator@UContainerInfo@ConnectedStorage@@@std@@@std@@PEAU_FILETIME@@1@Z`
- size: `1037`
- prototype: `__int64 __fastcall(ConnectedStorage::ContainerIndex *this)`
- caller_count: `2`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800537a0`
- `0x180061b3c`

## callees

- `0x180004078`
- `0x180007888`
- `0x1800078e8`
- `0x18000cb9c`
- `0x180012f7c`
- `0x18001303c`
- `0x1800190f0`
- `0x18001a700`
- `0x18003006c`
- `0x18003cdd4`
- `0x18003f300`
- `0x180052df4`
- `0x1800632fc`
- `0x180063334`
- `0x1800635c8`
- `0x18006364c`
- `0x180063678`
- `0x180063a08`
- `0x180063a68`
- `0x180064be0`
- `0x180065134`
- `0x1800656b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065520`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065430`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006522f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800652a4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800653d1`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006522f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800652a4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800653d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ConnectedStorage::ContainerIndex::PreMerge(
        ConnectedStorage::ContainerIndex *this,
        __int64 *a2,
        char *a3,
        FILETIME *a4)
{
  ConnectedStorage::ContainerIndex *v7; // r15
  size_t size_of; // rax
  _QWORD *v9; // rax
  __int64 *v10; // rbx
  __int64 *v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // r14
  FILETIME *v15; // r15
  __int64 v16; // rsi
  __int64 v17; // rcx
  bool IsModified; // bl
  __int64 v19; // rcx
  char v20; // al
  bool v21; // zf
  HSTRING *v22; // rax
  __int64 v23; // rcx
  int v24; // eax
  ConnectedStorage::ContainerIndex *v25; // rax
  const struct ConnectedStorage::SimpleHStringWrapper *v26; // rbx
  __int64 v27; // r8
  unsigned __int64 v28; // rax
  const FILETIME *v29; // rdx
  ConnectedStorage::ContainerIndex *v30; // rax
  ConnectedStorage::MergedEntry *v31; // r8
  ConnectedStorage::MergedEntry *v32; // rdx
  ConnectedStorage::MergedEntry *v33; // rcx
  std::_Ref_count_base *v34; // rcx
  ConnectedStorage::MergedEntry *v35[2]; // [rsp+38h] [rbp-59h] BYREF
  ConnectedStorage::MergedEntry *v36; // [rsp+48h] [rbp-49h]
  _QWORD v37[2]; // [rsp+50h] [rbp-41h] BYREF
  _BYTE v38[32]; // [rsp+60h] [rbp-31h] BYREF
  int v39; // [rsp+80h] [rbp-11h]
  struct _FILETIME v40; // [rsp+90h] [rbp-1h] BYREF
  __int64 v41; // [rsp+A0h] [rbp+Fh]
  LPCRITICAL_SECTION lpCriticalSection[8]; // [rsp+A8h] [rbp+17h] BYREF
  ConnectedStorage::ContainerIndex *v43; // [rsp+F8h] [rbp+67h] BYREF
  __int64 v44; // [rsp+100h] [rbp+6Fh] BYREF
  FILETIME *lpFileTime1; // [rsp+110h] [rbp+7Fh]

  lpFileTime1 = a4;
  v43 = this;
  v7 = this;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 64),
    a3);
  *(_QWORD *)a3 = 0;
  *a4 = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v37[1] = 0;
  size_of = std::_Get_size_of_n<48>(1);
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  v37[0] = v9;
  v10 = (__int64 *)*((_QWORD *)v7 + 20);
  v11 = (__int64 *)*((_QWORD *)v7 + 21);
  while ( v10 != v11 )
  {
    v12 = *v10;
    *(_QWORD *)(*(_QWORD *)std::map<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::ContainerIndexEntry const *>::_Try_emplace<ConnectedStorage::SimpleHStringWrapper const &,>(
                             v37,
                             &v40,
                             *v10++)
              + 40LL) = v12;
  }
  v13 = *a2;
  v14 = a2[1];
  if ( v13 != v14 )
  {
    v15 = lpFileTime1;
    while ( 1 )
    {
      ConnectedStorage::MergedEntry::MergedEntry(
        (ConnectedStorage::MergedEntry *)v38,
        (const struct ConnectedStorage::SimpleHStringWrapper *)v13,
        (const struct ConnectedStorage::SimpleHStringWrapper *)(v13 + 8),
        (const struct _FILETIME *)(v13 + 24),
        (const struct ConnectedStorage::SimpleHStringWrapper *)(v13 + 16),
        *(_QWORD *)(v13 + 32));
      if ( CompareFileTime(v15, (const FILETIME *)(v13 + 24)) < 0 )
        *v15 = *(FILETIME *)(v13 + 24);
      std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (enum ConnectedStorage::WebService::Status)>>>>,0>>::_Find_lower_bound<ConnectedStorage::SimpleHStringWrapper>(
        (__int64)v37,
        &v40,
        v13);
      v16 = v41;
      if ( !std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,enum ConnectedStorage::WebService::Status,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,enum ConnectedStorage::WebService::Status>>,0>>::_Lower_bound_duplicate<ConnectedStorage::SimpleHStringWrapper>(
              v17,
              v41,
              v13)
        || v16 == v37[0] )
      {
        v24 = 2;
        v39 = 2;
        goto LABEL_19;
      }
      IsModified = ConnectedStorage::ContainerIndexEntry::IsModified(*(ConnectedStorage::ContainerIndexEntry **)(v16 + 40));
      v20 = ConnectedStorage::SimpleHStringWrapper::operator==(v19 + 16, v13 + 16);
      if ( IsModified )
      {
        if ( !v20 )
        {
          v39 = 4;
          if ( CompareFileTime((const FILETIME *)a3, (const FILETIME *)(*(_QWORD *)(v16 + 40) + 48LL)) < 0 )
            *(_QWORD *)a3 = *(_QWORD *)(*(_QWORD *)(v16 + 40) + 48LL);
          goto LABEL_17;
        }
      }
      else if ( !v20 )
      {
        goto LABEL_16;
      }
      v21 = *(_DWORD *)(*(_QWORD *)(v16 + 40) + 28LL) == 4;
      v39 = 1;
      if ( v21 )
LABEL_16:
        v39 = 2;
LABEL_17:
      v22 = (HSTRING *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>::_Extract(
                         v37,
                         v16);
      std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,enum ConnectedStorage::WebService::Status>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,enum ConnectedStorage::WebService::Status>,void *>>>(
        v23,
        v22);
      v24 = v39;
LABEL_19:
      if ( v24 != 1 )
      {
        if ( v35[1] == v36 )
        {
          std::vector<ConnectedStorage::MergedEntry>::_Emplace_reallocate<ConnectedStorage::MergedEntry const &>(
            v35,
            v35[1],
            v38);
        }
        else
        {
          ConnectedStorage::MergedEntry::MergedEntry(v35[1], (const struct ConnectedStorage::MergedEntry *)v38);
          v35[1] = (ConnectedStorage::MergedEntry *)((char *)v35[1] + 48);
        }
      }
      ConnectedStorage::MergedEntry::~MergedEntry((ConnectedStorage::MergedEntry *)v38);
      v13 += 40;
      if ( v13 == v14 )
      {
        v7 = v43;
        break;
      }
    }
  }
  v25 = *(ConnectedStorage::ContainerIndex **)v37[0];
  v43 = *(ConnectedStorage::ContainerIndex **)v37[0];
  while ( !*((_BYTE *)v25 + 25) )
  {
    v26 = (ConnectedStorage::ContainerIndex *)((char *)v25 + 32);
    v40 = 0;
    v44 = 0;
    v27 = *((_QWORD *)v25 + 5);
    v28 = 0;
    if ( *(_DWORD *)(v27 + 28) != 3 )
      v28 = *(_QWORD *)(v27 + 64);
    ConnectedStorage::MergedEntry::MergedEntry(
      (ConnectedStorage::MergedEntry *)v38,
      v26,
      (const struct ConnectedStorage::SimpleHStringWrapper *)(v27 + 8),
      &v40,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&v44,
      v28);
    v29 = (const FILETIME *)*((_QWORD *)v26 + 1);
    if ( v29[3].dwHighDateTime != 1 )
    {
      if ( v29[3].dwHighDateTime == 2 )
        goto LABEL_34;
      if ( v29[3].dwHighDateTime != 3 )
      {
        if ( v29[3].dwHighDateTime == 5 )
        {
          v39 = 1;
          goto LABEL_41;
        }
LABEL_34:
        v39 = 5;
        if ( CompareFileTime((const FILETIME *)a3, v29 + 6) < 0 )
          *(_QWORD *)a3 = *(_QWORD *)(*((_QWORD *)v26 + 1) + 48LL);
        goto LABEL_37;
      }
    }
    v39 = 3;
LABEL_37:
    if ( v39 != 1 )
    {
      if ( v35[1] == v36 )
      {
        std::vector<ConnectedStorage::MergedEntry>::_Emplace_reallocate<ConnectedStorage::MergedEntry const &>(
          v35,
          v35[1],
          v38);
      }
      else
      {
        ConnectedStorage::MergedEntry::MergedEntry(v35[1], (const struct ConnectedStorage::MergedEntry *)v38);
        v35[1] = (ConnectedStorage::MergedEntry *)((char *)v35[1] + 48);
      }
    }
LABEL_41:
    ConnectedStorage::MergedEntry::~MergedEntry((ConnectedStorage::MergedEntry *)v38);
    WindowsDeleteString(0);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::ContainerIndexEntry const *>>>,std::_Iterator_base0>::operator++(&v43);
    v25 = v43;
  }
  v30 = (ConnectedStorage::ContainerIndex *)operator new(0x28u);
  v43 = v30;
  *(_OWORD *)v30 = 0;
  *((_DWORD *)v30 + 2) = 1;
  *((_DWORD *)v30 + 3) = 1;
  *(_QWORD *)v30 = &std::_Ref_count_obj2<ConnectedStorage::PartiallyMergedContainerIndex>::`vftable';
  v31 = v36;
  v36 = 0;
  v32 = v35[1];
  v35[1] = 0;
  v33 = v35[0];
  v35[0] = 0;
  *((_QWORD *)v30 + 2) = v33;
  *((_QWORD *)v30 + 3) = v32;
  *((_QWORD *)v30 + 4) = v31;
  *((_QWORD *)v7 + 23) = (char *)v30 + 16;
  v34 = (std::_Ref_count_base *)*((_QWORD *)v7 + 24);
  *((_QWORD *)v7 + 24) = v30;
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  ConnectedStorage::ContainerIndex::ResolveLocal(v7);
  std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,enum ConnectedStorage::WebService::Status,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,enum ConnectedStorage::WebService::Status>>,0>>::~_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,enum ConnectedStorage::WebService::Status,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,enum ConnectedStorage::WebService::Status>>,0>>(v37);
  if ( v35[0] )
  {
    std::_Destroy_range<std::allocator<ConnectedStorage::MergedEntry>>(v35[0]);
    std::_Deallocate<16>(v35[0], 16 * ((v36 - v35[0]) >> 4));
    *(_OWORD *)v35 = 0;
    v36 = 0;
  }
  LeaveCriticalSection(lpCriticalSection[0]);
}

```

## disassembly

```asm
0x180065134  mov     rax, rsp
0x180065137  mov     [rax+18h], rbx
0x18006513b  mov     [rax+20h], r9
0x18006513f  mov     [rax+8], rcx
0x180065143  push    rbp
0x180065144  push    rsi
0x180065145  push    rdi
0x180065146  push    r12
0x180065148  push    r13
0x18006514a  push    r14
0x18006514c  push    r15
0x18006514e  lea     rbp, [rax-5Fh]
0x180065152  sub     rsp, 0B0h
0x180065159  mov     rbx, r9
0x18006515c  mov     r13, r8
0x18006515f  mov     r14, rdx
0x180065162  mov     r15, rcx
0x180065165  xor     r12d, r12d
0x180065168  lea     rdx, [rcx+40h]; struct ConnectedStorage::Mutex *
0x18006516c  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x180065170  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180065175  nop
0x180065176  xor     eax, eax
0x180065178  mov     [r13+0], rax
0x18006517c  mov     [rbx], rax
0x18006517f  xorps   xmm0, xmm0
0x180065182  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x180065187  mov     [rbp+57h+var_A0], r12
0x18006518b  mov     [rbp+57h+var_98], r12
0x18006518f  mov     [rbp+57h+var_90], r12
0x180065193  lea     ecx, [rax+1]
0x180065196  call    ??$_Get_size_of_n@$0DA@@std@@YA_K_K@Z; std::_Get_size_of_n<48>(unsigned __int64)
0x18006519b  mov     rcx, rax
0x18006519e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800651a3  mov     [rax], rax
0x1800651a6  mov     [rax+8], rax
0x1800651aa  mov     [rax+10h], rax
0x1800651ae  mov     word ptr [rax+18h], 101h
0x1800651b4  mov     [rbp+57h+var_98], rax
0x1800651b8  mov     rbx, [r15+0A0h]
0x1800651bf  mov     rdi, [r15+0A8h]
0x1800651c6  cmp     rbx, rdi
0x1800651c9  jz      short loc_1800651EB
0x1800651cb  mov     rsi, [rbx]
0x1800651ce  mov     r8, rsi
0x1800651d1  lea     rdx, [rbp+57h+var_58]
0x1800651d5  lea     rcx, [rbp+57h+var_98]
0x1800651d9  call    ??$_Try_emplace@AEBVSimpleHStringWrapper@ConnectedStorage@@$$V@?$map@VSimpleHStringWrapper@ConnectedStorage@@PEBVContainerIndexEntry@2@U?$less@VSimpleHStringWrapper@ConnectedStorage@@@std@@V?$allocator@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@PEBVContainerIndexEntry@2@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@PEBVContainerIndexEntry@2@@std@@PEAX@std@@_N@1@AEBVSimpleHStringWrapper@ConnectedStorage@@@Z; std::map<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::ContainerIndexEntry const *>::_Try_emplace<ConnectedStorage::SimpleHStringWrapper const &,>(ConnectedStorage::SimpleHStringWrapper const &)
0x1800651de  mov     rcx, [rax]
0x1800651e1  mov     [rcx+28h], rsi
0x1800651e5  add     rbx, 8
0x1800651e9  jmp     short loc_1800651C6
0x1800651eb  mov     rdi, [r14]
0x1800651ee  mov     r14, [r14+8]
0x1800651f2  cmp     rdi, r14
0x1800651f5  jz      loc_180065349
0x1800651fb  mov     r15, [rbp+57h+lpFileTime1]
0x1800651ff  lea     r12, [rdi+10h]
0x180065203  lea     rbx, [rdi+18h]
0x180065207  lea     r8, [rdi+8]; struct ConnectedStorage::SimpleHStringWrapper *
0x18006520b  mov     rax, [rdi+20h]
0x18006520f  mov     [rsp+28h], rax; unsigned __int64
0x180065214  mov     [rsp+0E0h+var_C0], r12; struct ConnectedStorage::SimpleHStringWrapper *
0x180065219  mov     r9, rbx; struct _FILETIME *
0x18006521c  mov     rdx, rdi; struct ConnectedStorage::SimpleHStringWrapper *
0x18006521f  lea     rcx, [rbp+57h+var_88]; this
0x180065223  call    ??0MergedEntry@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0AEBU_FILETIME@@0_K@Z; ConnectedStorage::MergedEntry::MergedEntry(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_FILETIME const &,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64)
0x180065228  nop
0x180065229  mov     rdx, rbx; lpFileTime2
0x18006522c  mov     rcx, r15; lpFileTime1
0x18006522f  call    cs:__imp_CompareFileTime
0x180065235  test    eax, eax
0x180065237  jns     short loc_18006523F
0x180065239  mov     rax, [rbx]
0x18006523c  mov     [r15], rax
0x18006523f  mov     r8, rdi
0x180065242  lea     rdx, [rbp+57h+var_58]
0x180065246  lea     rcx, [rbp+57h+var_98]
0x18006524a  call    ??$_Find_lower_bound@VSimpleHStringWrapper@ConnectedStorage@@@?$_Tree@V?$_Tmap_traits@VSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@U?$less@VSimpleHStringWrapper@ConnectedStorage@@@4@V?$allocator@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@V?$list@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@V?$allocator@V?$function@$$A6AXW4Status@WebService@ConnectedStorage@@@Z@std@@@2@@std@@@std@@PEAX@std@@@1@AEBVSimpleHStringWrapper@ConnectedStorage@@@Z; std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,std::list<std::function<void (ConnectedStorage::WebService::Status)>>,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,std::list<std::function<void (ConnectedStorage::WebService::Status)>>>>,0>>::_Find_lower_bound<ConnectedStorage::SimpleHStringWrapper>(ConnectedStorage::SimpleHStringWrapper const &)
0x18006524f  mov     r8, rdi
0x180065252  mov     rsi, [rbp+57h+var_48]
0x180065256  mov     rdx, rsi
0x180065259  call    ??$_Lower_bound_duplicate@VSimpleHStringWrapper@ConnectedStorage@@@?$_Tree@V?$_Tmap_traits@VSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@U?$less@VSimpleHStringWrapper@ConnectedStorage@@@std@@V?$allocator@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@@6@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@PEAX@1@AEBVSimpleHStringWrapper@ConnectedStorage@@@Z; std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::WebService::Status,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>>,0>>::_Lower_bound_duplicate<ConnectedStorage::SimpleHStringWrapper>(std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *> * const,ConnectedStorage::SimpleHStringWrapper const &)
0x18006525e  test    al, al
0x180065260  jz      loc_1800652F1
0x180065266  cmp     rsi, [rbp+57h+var_98]
0x18006526a  jz      loc_1800652F1
0x180065270  mov     rcx, [rsi+28h]; this
0x180065274  call    ?IsModified@ContainerIndexEntry@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::ContainerIndexEntry::IsModified(void)
0x180065279  mov     bl, al
0x18006527b  add     rcx, 10h
0x18006527f  mov     rdx, r12
0x180065282  call    ??8SimpleHStringWrapper@ConnectedStorage@@QEBA_NAEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator==(ConnectedStorage::SimpleHStringWrapper const &)
0x180065287  xor     r12d, r12d
0x18006528a  test    bl, bl
0x18006528c  jz      short loc_1800652BC
0x18006528e  test    al, al
0x180065290  jnz     short loc_1800652C0
0x180065292  mov     [rbp+57h+var_68], 4
0x180065299  mov     rdx, [rsi+28h]
0x18006529d  add     rdx, 30h ; '0'; lpFileTime2
0x1800652a1  mov     rcx, r13; lpFileTime1
0x1800652a4  call    cs:__imp_CompareFileTime
0x1800652aa  test    eax, eax
0x1800652ac  jns     short loc_1800652D8
0x1800652ae  mov     rax, [rsi+28h]
0x1800652b2  mov     rcx, [rax+30h]
0x1800652b6  mov     [r13+0], rcx
0x1800652ba  jmp     short loc_1800652D8
0x1800652bc  test    al, al
0x1800652be  jz      short loc_1800652D1
0x1800652c0  mov     rax, [rsi+28h]
0x1800652c4  cmp     dword ptr [rax+1Ch], 4
0x1800652c8  mov     [rbp+57h+var_68], 1
0x1800652cf  jnz     short loc_1800652D8
0x1800652d1  mov     [rbp+57h+var_68], 2
0x1800652d8  mov     rdx, rsi
0x1800652db  lea     rcx, [rbp+57h+var_98]
0x1800652df  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,ConnectedStorage::Handle>>>,std::_Iterator_base0>)
0x1800652e4  mov     rdx, rax
0x1800652e7  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *>>>(std::allocator<std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *>> &,std::_Tree_node<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>,void *> *)
0x1800652ec  mov     eax, [rbp+57h+var_68]
0x1800652ef  jmp     short loc_1800652FC
0x1800652f1  mov     eax, 2
0x1800652f6  mov     [rbp+57h+var_68], eax
0x1800652f9  xor     r12d, r12d
0x1800652fc  cmp     eax, 1
0x1800652ff  jz      short loc_18006532F
0x180065301  mov     rax, [rbp+57h+var_B0+8]
0x180065305  cmp     rax, [rbp+57h+var_A0]
0x180065309  jz      short loc_18006531E
0x18006530b  lea     rdx, [rbp+57h+var_88]; struct ConnectedStorage::MergedEntry *
0x18006530f  mov     rcx, rax; this
0x180065312  call    ??0MergedEntry@ConnectedStorage@@QEAA@AEBU01@@Z; ConnectedStorage::MergedEntry::MergedEntry(ConnectedStorage::MergedEntry const &)
0x180065317  add     [rbp+57h+var_B0+8], 30h ; '0'
0x18006531c  jmp     short loc_18006532F
0x18006531e  lea     r8, [rbp+57h+var_88]
0x180065322  mov     rdx, rax
0x180065325  lea     rcx, [rbp+57h+var_B0]
0x180065329  call    ??$_Emplace_reallocate@AEBUMergedEntry@ConnectedStorage@@@?$vector@UMergedEntry@ConnectedStorage@@V?$allocator@UMergedEntry@ConnectedStorage@@@std@@@std@@AEAAPEAUMergedEntry@ConnectedStorage@@QEAU23@AEBU23@@Z; std::vector<ConnectedStorage::MergedEntry>::_Emplace_reallocate<ConnectedStorage::MergedEntry const &>(ConnectedStorage::MergedEntry * const,ConnectedStorage::MergedEntry const &)
0x18006532e  nop
0x18006532f  lea     rcx, [rbp+57h+var_88]; this
0x180065333  call    ??1MergedEntry@ConnectedStorage@@QEAA@XZ; ConnectedStorage::MergedEntry::~MergedEntry(void)
0x180065338  add     rdi, 28h ; '('
0x18006533c  cmp     rdi, r14
0x18006533f  jnz     loc_1800651FF
0x180065345  mov     r15, [rbp+57h+arg_0]
0x180065349  mov     rax, [rbp+57h+var_98]
0x18006534d  mov     rax, [rax]
0x180065350  mov     [rbp+57h+arg_0], rax
0x180065354  cmp     [rax+19h], r12b
0x180065358  jnz     loc_180065448
0x18006535e  lea     rbx, [rax+20h]
0x180065362  mov     qword ptr [rbp+57h+var_58.dwLowDateTime], r12
0x180065366  mov     [rbp+57h+arg_8], r12
0x18006536a  mov     r8, [rbx+8]
0x18006536e  cmp     dword ptr [r8+1Ch], 3
0x180065373  mov     rax, r12
0x180065376  jz      short loc_18006537C
0x180065378  mov     rax, [r8+40h]
0x18006537c  add     r8, 8; struct ConnectedStorage::SimpleHStringWrapper *
0x180065380  mov     [rsp+28h], rax; unsigned __int64
0x180065385  lea     rax, [rbp+57h+arg_8]
0x180065389  mov     [rsp+0E0h+var_C0], rax; struct ConnectedStorage::SimpleHStringWrapper *
0x18006538e  lea     r9, [rbp+57h+var_58]; struct _FILETIME *
0x180065392  mov     rdx, rbx; struct ConnectedStorage::SimpleHStringWrapper *
0x180065395  lea     rcx, [rbp+57h+var_88]; this
0x180065399  call    ??0MergedEntry@ConnectedStorage@@QEAA@AEBVSimpleHStringWrapper@1@0AEBU_FILETIME@@0_K@Z; ConnectedStorage::MergedEntry::MergedEntry(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_FILETIME const &,ConnectedStorage::SimpleHStringWrapper const &,unsigned __int64)
0x18006539e  nop
0x18006539f  mov     rdx, [rbx+8]
0x1800653a3  mov     ecx, [rdx+1Ch]
0x1800653a6  sub     ecx, 1
0x1800653a9  jz      short loc_1800653E9
0x1800653ab  sub     ecx, 1
0x1800653ae  jz      short loc_1800653C3
0x1800653b0  sub     ecx, 1
0x1800653b3  jz      short loc_1800653E9
0x1800653b5  cmp     ecx, 2
0x1800653b8  jnz     short loc_1800653C3
0x1800653ba  mov     [rbp+57h+var_68], 1
0x1800653c1  jmp     short loc_180065424
0x1800653c3  mov     [rbp+57h+var_68], 5
0x1800653ca  add     rdx, 30h ; '0'; lpFileTime2
0x1800653ce  mov     rcx, r13; lpFileTime1
0x1800653d1  call    cs:__imp_CompareFileTime
0x1800653d7  test    eax, eax
0x1800653d9  jns     short loc_1800653F0
0x1800653db  mov     rax, [rbx+8]
0x1800653df  mov     rcx, [rax+30h]
0x1800653e3  mov     [r13+0], rcx
0x1800653e7  jmp     short loc_1800653F0
0x1800653e9  mov     [rbp+57h+var_68], 3
0x1800653f0  cmp     [rbp+57h+var_68], 1
0x1800653f4  jz      short loc_180065424
0x1800653f6  mov     rax, [rbp+57h+var_B0+8]
0x1800653fa  cmp     rax, [rbp+57h+var_A0]
0x1800653fe  jz      short loc_180065413
0x180065400  lea     rdx, [rbp+57h+var_88]; struct ConnectedStorage::MergedEntry *
0x180065404  mov     rcx, rax; this
0x180065407  call    ??0MergedEntry@ConnectedStorage@@QEAA@AEBU01@@Z; ConnectedStorage::MergedEntry::MergedEntry(ConnectedStorage::MergedEntry const &)
0x18006540c  add     [rbp+57h+var_B0+8], 30h ; '0'
0x180065411  jmp     short loc_180065424
0x180065413  lea     r8, [rbp+57h+var_88]
0x180065417  mov     rdx, rax
0x18006541a  lea     rcx, [rbp+57h+var_B0]
0x18006541e  call    ??$_Emplace_reallocate@AEBUMergedEntry@ConnectedStorage@@@?$vector@UMergedEntry@ConnectedStorage@@V?$allocator@UMergedEntry@ConnectedStorage@@@std@@@std@@AEAAPEAUMergedEntry@ConnectedStorage@@QEAU23@AEBU23@@Z; std::vector<ConnectedStorage::MergedEntry>::_Emplace_reallocate<ConnectedStorage::MergedEntry const &>(ConnectedStorage::MergedEntry * const,ConnectedStorage::MergedEntry const &)
0x180065423  nop
0x180065424  lea     rcx, [rbp+57h+var_88]; this
0x180065428  call    ??1MergedEntry@ConnectedStorage@@QEAA@XZ; ConnectedStorage::MergedEntry::~MergedEntry(void)
0x18006542d  nop
0x18006542e  xor     ecx, ecx; string
0x180065430  call    cs:__imp_WindowsDeleteString
0x180065436  lea     rcx, [rbp+57h+arg_0]
0x18006543a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@PEBVContainerIndexEntry@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::ContainerIndexEntry const *>>>,std::_Iterator_base0>::operator++(void)
0x18006543f  mov     rax, [rbp+57h+arg_0]
0x180065443  jmp     loc_180065354
0x180065448  mov     ecx, 28h ; '('; Size
0x18006544d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180065452  mov     [rbp+57h+arg_0], rax
0x180065456  xorps   xmm0, xmm0
0x180065459  movups  xmmword ptr [rax], xmm0
0x18006545c  mov     dword ptr [rax+8], 1
0x180065463  mov     dword ptr [rax+0Ch], 1
0x18006546a  lea     rcx, ??_7?$_Ref_count_obj2@VPartiallyMergedContainerIndex@ConnectedStorage@@@std@@6B@; const std::_Ref_count_obj2<ConnectedStorage::PartiallyMergedContainerIndex>::`vftable'
0x180065471  mov     [rax], rcx
0x180065474  lea     r9, [rax+10h]
0x180065478  mov     r8, [rbp+57h+var_A0]
0x18006547c  mov     [rbp+57h+var_A0], r12
0x180065480  mov     rdx, [rbp+57h+var_B0+8]
0x180065484  mov     [rbp+57h+var_B0+8], r12
0x180065488  mov     rcx, [rbp+57h+var_B0]
0x18006548c  mov     [rbp+57h+var_B0], r12
0x180065490  mov     [r9], rcx
0x180065493  mov     [r9+8], rdx
0x180065497  mov     [r9+10h], r8
0x18006549b  mov     [r15+0B8h], r9
0x1800654a2  mov     rcx, [r15+0C0h]; this
0x1800654a9  mov     [r15+0C0h], rax
0x1800654b0  test    rcx, rcx
0x1800654b3  jz      short loc_1800654BA
0x1800654b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800654ba  mov     rdx, [r15+0B8h]
0x1800654c1  mov     rcx, r15; this
0x1800654c4  call    ?ResolveLocal@ContainerIndex@ConnectedStorage@@QEBAXPEAV?$vector@UMergedEntry@ConnectedStorage@@V?$allocator@UMergedEntry@ConnectedStorage@@@std@@@std@@@Z; ConnectedStorage::ContainerIndex::ResolveLocal(std::vector<ConnectedStorage::MergedEntry> *)
0x1800654c9  nop
0x1800654ca  lea     rcx, [rbp+57h+var_98]
0x1800654ce  call    ??1?$_Tree@V?$_Tmap_traits@VSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@U?$less@VSimpleHStringWrapper@ConnectedStorage@@@std@@V?$allocator@U?$pair@$$CBVSimpleHStringWrapper@ConnectedStorage@@W4Status@WebService@2@@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::WebService::Status,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>>,0>>::~_Tree<std::_Tmap_traits<ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::WebService::Status,std::less<ConnectedStorage::SimpleHStringWrapper>,std::allocator<std::pair<ConnectedStorage::SimpleHStringWrapper const,ConnectedStorage::WebService::Status>>,0>>(void)
0x1800654d3  nop
0x1800654d4  mov     rcx, [rbp+57h+var_B0]; this
0x1800654d8  test    rcx, rcx
0x1800654db  jz      short loc_18006551C
0x1800654dd  mov     rdx, [rbp+57h+var_B0+8]
0x1800654e1  call    ??$_Destroy_range@V?$allocator@UMergedEntry@ConnectedStorage@@@std@@@std@@YAXPEAUMergedEntry@ConnectedStorage@@QEAU12@AEAV?$allocator@UMergedEntry@ConnectedStorage@@@0@@Z; std::_Destroy_range<std::allocator<ConnectedStorage::MergedEntry>>(ConnectedStorage::MergedEntry *,ConnectedStorage::MergedEntry * const,std::allocator<ConnectedStorage::MergedEntry> &)
0x1800654e6  mov     rcx, [rbp+57h+var_B0]
0x1800654ea  mov     rax, [rbp+57h+var_A0]
0x1800654ee  sub     rax, rcx
0x1800654f1  sar     rax, 4
0x1800654f5  mov     rdx, 0AAAAAAAAAAAAAAABh
0x1800654ff  imul    rax, rdx
0x180065503  lea     rdx, [rax+rax*2]
0x180065507  shl     rdx, 4
0x18006550b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180065510  xorps   xmm0, xmm0
0x180065513  movdqu  xmmword ptr [rbp+57h+var_B0], xmm0
0x180065518  mov     [rbp+57h+var_A0], r12
0x18006551c  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180065520  call    cs:__imp_LeaveCriticalSection
0x180065526  mov     rbx, [rsp+0E0h+arg_10]
0x18006552e  add     rsp, 0B0h
0x180065535  pop     r15
0x180065537  pop     r14
0x180065539  pop     r13
0x18006553b  pop     r12
0x18006553d  pop     rdi
0x18006553e  pop     rsi
0x18006553f  pop     rbp
0x180065540  retn
```
