# ApplicationInstanceManager::GetAppSpecifiedInstanceList(void *,unsigned __int64,ushort const *,uint *,ushort * * *)

- ea: `0x180074ac0`
- end: `0x180074d1d`
- name: `?GetAppSpecifiedInstanceList@ApplicationInstanceManager@@UEAAJPEAX_KPEBGPEAIPEAPEAPEAG@Z`
- size: `605`
- prototype: `int(ApplicationInstanceManager *__hidden this, void *, unsigned __int64, const unsigned __int16 *, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180027150`
- `0x18002b6a0`
- `0x180033b34`
- `0x180045078`
- `0x180045174`
- `0x180045a1c`
- `0x180045aa4`
- `0x18004670c`
- `0x180046a34`
- `0x180056208`
- `0x18005ae90`
- `0x18005ba40`
- `0x1800741c4`
- `0x1800744c0`
- `0x180074ac0`
- `0x1800763c8`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180074c67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180074c67`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180074b02`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180074b02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180074ba2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180074ba2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ApplicationInstanceManager::GetAppSpecifiedInstanceList(
        ApplicationInstanceManager *this,
        void *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int16 ***a6)
{
  DWORD ProcessId; // r12d
  __int64 v10; // r8
  int *i; // rbx
  __int64 v12; // rax
  size_t v13; // rbx
  void *v14; // rax
  const char *v15; // r9
  __int64 j; // rbx
  unsigned __int64 v17; // rax
  _QWORD *v18; // rdi
  const WCHAR *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  int v24[2]; // [rsp+20h] [rbp-98h] BYREF
  _QWORD **v25; // [rsp+28h] [rbp-90h] BYREF
  __int64 v26; // [rsp+30h] [rbp-88h]
  __int64 v27; // [rsp+38h] [rbp-80h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-78h] BYREF
  int *v29; // [rsp+48h] [rbp-70h] BYREF
  int *v30; // [rsp+50h] [rbp-68h]
  char v31; // [rsp+58h] [rbp-60h]
  __int64 v32; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v33[32]; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  ProcessId = GetProcessId(a2);
  std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>(&v25);
  ApplicationInstanceManager::Key::Key((ApplicationInstanceManager::Key *)&v32);
  v32 = a3;
  v10 = std::_WChar_traits<unsigned short>::length(a4);
  std::wstring::_Assign<unsigned short>(v33, a4, v10);
  *a5 = 0;
  *a6 = 0;
  wil::AcquireSRWLockExclusive(&SRWLock, (char *)this + 152);
  std::_Hash<std::_Umap_traits<ApplicationInstanceManager::Key,Microsoft::WRL::ComPtr<IApplicationInstanceInfo>,std::_Uhash_compare<ApplicationInstanceManager::Key,ApplicationInstanceManager::Key::Hash,std::equal_to<ApplicationInstanceManager::Key>>,std::allocator<std::pair<ApplicationInstanceManager::Key const,Microsoft::WRL::ComPtr<IApplicationInstanceInfo>>>,1>>::equal_range(
    (char *)this + 32,
    &v29,
    &v32);
  for ( i = v29; i != v30; i = *(int **)i )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)i + 7) + 24LL))(*((_QWORD *)i + 7)) != ProcessId
      && (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)i + 7) + 72LL))(*((_QWORD *)i + 7)) )
    {
      *(_QWORD *)v24 = *((_QWORD *)i + 7);
      std::vector<Microsoft::WRL::ComPtr<IApplicationInstanceInfo>>::emplace_back<IApplicationInstanceInfo *>(
        (__int64 *)&v25,
        (__int64 *)v24);
    }
  }
  v12 = (v26 - (__int64)v25) >> 3;
  if ( v12 )
  {
    v13 = 8 * v12;
    v14 = CoTaskMemAlloc(8 * v12);
    *(_QWORD *)v24 = v14;
    if ( !v14 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
        v15);
    memset_0(v14, 0, v13);
    v29 = v24;
    v30 = (int *)&v25;
    v31 = 1;
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      v17 = (v26 - (__int64)v25) >> 3;
      if ( (unsigned int)j >= v17 )
        break;
      v18 = (_QWORD *)(*(_QWORD *)v24 + 8 * j);
      v19 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(*v25[j] + 48LL))(v25[j]);
      v22 = _AllocString<CTCoAllocPolicy>(v21, v20, v19, v18);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BE,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
          (const char *)(unsigned int)v22,
          v24[0]);
    }
    *a5 = v17;
    *a6 = *(unsigned __int16 ***)v24;
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  std::wstring::_Tidy_deallocate(v33);
  if ( v25 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IApplicationInstanceInfo>>>((__int64)v25, v26);
    std::_Deallocate<16>(v25, (struct std::nothrow_t *)((v27 - (_QWORD)v25) & 0xFFFFFFFFFFFFFFF8uLL));
  }
  return 0;
}

```

## disassembly

```asm
0x180074ac0  mov     [rsp+arg_10], rbx
0x180074ac5  push    rsi
0x180074ac6  push    rdi
0x180074ac7  push    r12
0x180074ac9  push    r14
0x180074acb  push    r15
0x180074acd  sub     rsp, 90h
0x180074ad4  mov     rax, cs:__security_cookie
0x180074adb  xor     rax, rsp
0x180074ade  mov     [rsp+0B8h+var_30], rax
0x180074ae6  mov     rdi, r9
0x180074ae9  mov     r15, r8
0x180074aec  mov     rbx, rcx
0x180074aef  mov     rsi, [rsp+0B8h+arg_20]
0x180074af7  mov     r14, [rsp+0B8h+arg_28]
0x180074aff  mov     rcx, rdx; Process
0x180074b02  call    cs:__imp_GetProcessId
0x180074b08  mov     r12d, eax
0x180074b0b  lea     rcx, [rsp+0B8h+var_90]
0x180074b10  call    ??0?$vector@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@V?$allocator@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>(void)
0x180074b15  nop
0x180074b16  lea     rcx, [rsp+0B8h+var_58]; this
0x180074b1b  call    ??0Key@ApplicationInstanceManager@@QEAA@XZ; ApplicationInstanceManager::Key::Key(void)
0x180074b20  nop
0x180074b21  mov     [rsp+0B8h+var_58], r15
0x180074b26  mov     rcx, rdi
0x180074b29  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180074b2e  mov     r8, rax
0x180074b31  mov     rdx, rdi
0x180074b34  lea     rcx, [rsp+0B8h+var_50]
0x180074b39  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180074b3e  mov     dword ptr [rsi], 0
0x180074b44  mov     qword ptr [r14], 0
0x180074b4b  lea     rdx, [rbx+98h]
0x180074b52  lea     rcx, [rsp+0B8h+SRWLock]
0x180074b57  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180074b5c  nop
0x180074b5d  lea     rcx, [rbx+20h]
0x180074b61  lea     r8, [rsp+0B8h+var_58]
0x180074b66  lea     rdx, [rsp+0B8h+var_70]
0x180074b6b  call    ?equal_range@?$_Hash@V?$_Umap_traits@UKey@ApplicationInstanceManager@@V?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@V?$_Uhash_compare@UKey@ApplicationInstanceManager@@UHash@12@U?$equal_to@UKey@ApplicationInstanceManager@@@std@@@std@@V?$allocator@U?$pair@$$CBUKey@ApplicationInstanceManager@@V?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@@std@@@7@$00@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUKey@ApplicationInstanceManager@@V?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@V12@@2@AEBUKey@ApplicationInstanceManager@@@Z; std::_Hash<std::_Umap_traits<ApplicationInstanceManager::Key,Microsoft::WRL::ComPtr<IApplicationInstanceInfo>,std::_Uhash_compare<ApplicationInstanceManager::Key,ApplicationInstanceManager::Key::Hash,std::equal_to<ApplicationInstanceManager::Key>>,std::allocator<std::pair<ApplicationInstanceManager::Key const,Microsoft::WRL::ComPtr<IApplicationInstanceInfo>>>,1>>::equal_range(ApplicationInstanceManager::Key const &)
0x180074b70  mov     rbx, [rsp+0B8h+var_70]
0x180074b75  cmp     rbx, [rsp+0B8h+var_68]
0x180074b7a  jnz     loc_180074CA7
0x180074b80  mov     rax, [rsp+0B8h+var_88]
0x180074b85  sub     rax, [rsp+0B8h+var_90]
0x180074b8a  sar     rax, 3
0x180074b8e  test    rax, rax
0x180074b91  jz      loc_180074C5D
0x180074b97  lea     rbx, ds:0[rax*8]
0x180074b9f  mov     rcx, rbx; cb
0x180074ba2  call    cs:__imp_CoTaskMemAlloc
0x180074ba8  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180074bad  mov     rcx, [rsp+0B8h]; this
0x180074bb5  test    rax, rax
0x180074bb8  jnz     short loc_180074BCB
0x180074bba  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180074bc1  mov     edx, 1AAh; void *
0x180074bc6  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180074bcb  mov     r8, rbx; Size
0x180074bce  xor     edx, edx; Val
0x180074bd0  mov     rcx, rax; void *
0x180074bd3  call    memset_0
0x180074bd8  lea     rax, [rsp+0B8h+var_98]
0x180074bdd  mov     [rsp+0B8h+var_70], rax
0x180074be2  lea     rax, [rsp+0B8h+var_90]
0x180074be7  mov     [rsp+0B8h+var_68], rax
0x180074bec  mov     [rsp+0B8h+var_60], 1
0x180074bf1  xor     ebx, ebx
0x180074bf3  mov     ecx, ebx
0x180074bf5  mov     rax, [rsp+0B8h+var_88]
0x180074bfa  mov     rdx, [rsp+0B8h+var_90]
0x180074bff  sub     rax, rdx
0x180074c02  sar     rax, 3
0x180074c06  cmp     rcx, rax
0x180074c09  jnb     short loc_180074C53
0x180074c0b  mov     rax, qword ptr [rsp+0B8h+var_98]
0x180074c10  lea     rdi, [rax+rbx*8]
0x180074c14  mov     rcx, [rdx+rbx*8]
0x180074c18  mov     rax, [rcx]
0x180074c1b  mov     rax, [rax+30h]
0x180074c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074c24  mov     r9, rdi
0x180074c27  mov     r8, rax
0x180074c2a  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180074c2f  mov     rcx, [rsp+0B8h]; this
0x180074c37  test    eax, eax
0x180074c39  jns     short loc_180074C4F
0x180074c3b  mov     r9d, eax; char *
0x180074c3e  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180074c45  mov     edx, 1BEh; void *
0x180074c4a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074c4f  inc     ebx
0x180074c51  jmp     short loc_180074BF3
0x180074c53  mov     [rsi], eax
0x180074c55  mov     rax, qword ptr [rsp+0B8h+var_98]
0x180074c5a  mov     [r14], rax
0x180074c5d  mov     rcx, [rsp+0B8h+SRWLock]; SRWLock
0x180074c62  test    rcx, rcx
0x180074c65  jz      short loc_180074C6E
0x180074c67  call    cs:__imp_ReleaseSRWLockExclusive
0x180074c6d  nop
0x180074c6e  lea     rcx, [rsp+0B8h+var_50]
0x180074c73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074c78  nop
0x180074c79  mov     rcx, [rsp+0B8h+var_90]
0x180074c7e  test    rcx, rcx
0x180074c81  jz      short loc_180074CA3
0x180074c83  mov     rdx, [rsp+0B8h+var_88]
0x180074c88  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IApplicationInstanceInfo>>>(Microsoft::WRL::ComPtr<IApplicationInstanceInfo> *,Microsoft::WRL::ComPtr<IApplicationInstanceInfo> * const,std::allocator<Microsoft::WRL::ComPtr<IApplicationInstanceInfo>> &)
0x180074c8d  mov     rcx, [rsp+0B8h+var_90]
0x180074c92  mov     rdx, [rsp+0B8h+var_80]
0x180074c97  sub     rdx, rcx
0x180074c9a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180074c9e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180074ca3  xor     eax, eax
0x180074ca5  jmp     short loc_180074CF4
0x180074ca7  mov     rcx, [rbx+38h]
0x180074cab  mov     rax, [rcx]
0x180074cae  mov     rax, [rax+18h]
0x180074cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074cb7  cmp     eax, r12d
0x180074cba  jz      short loc_180074CE8
0x180074cbc  mov     rcx, [rbx+38h]
0x180074cc0  mov     rax, [rcx]
0x180074cc3  mov     rax, [rax+48h]
0x180074cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074ccc  test    al, al
0x180074cce  jz      short loc_180074CE8
0x180074cd0  mov     rax, [rbx+38h]
0x180074cd4  mov     qword ptr [rsp+0B8h+var_98], rax
0x180074cd9  lea     rdx, [rsp+0B8h+var_98]
0x180074cde  lea     rcx, [rsp+0B8h+var_90]
0x180074ce3  call    ??$emplace_back@PEAUIApplicationInstanceInfo@@@?$vector@V?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@@std@@@std@@QEAAAEAV?$ComPtr@UIApplicationInstanceInfo@@@WRL@Microsoft@@$$QEAPEAUIApplicationInstanceInfo@@@Z; std::vector<Microsoft::WRL::ComPtr<IApplicationInstanceInfo>>::emplace_back<IApplicationInstanceInfo *>(IApplicationInstanceInfo * &&)
0x180074ce8  mov     rbx, [rbx]
0x180074ceb  jmp     loc_180074B75
0x180074cf0  mov     eax, [rsp+0B8h+var_98]
0x180074cf4  mov     rcx, [rsp+0B8h+var_30]
0x180074cfc  xor     rcx, rsp; StackCookie
0x180074cff  call    __security_check_cookie
0x180074d04  mov     rbx, [rsp+0B8h+arg_10]
0x180074d0c  add     rsp, 90h
0x180074d13  pop     r15
0x180074d15  pop     r14
0x180074d17  pop     r12
0x180074d19  pop     rdi
0x180074d1a  pop     rsi
0x180074d1b  retn
```
