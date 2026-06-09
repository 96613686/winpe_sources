# ContainerManager::_CreateContainer(_GUID const &)

- ea: `0x180014c70`
- end: `0x180014de8`
- name: `?_CreateContainer@ContainerManager@@AEAA?AV?$shared_ptr@VContainer@@@std@@AEBU_GUID@@@Z`
- size: `376`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001580c`
- `0x1800196b8`
- `0x180019794`
- `0x180026414`
- `0x180026618`
- `0x1800266a8`

## callees

- `0x180008dcc`
- `0x180012cbc`
- `0x18001370c`
- `0x180013c1c`
- `0x180014c70`
- `0x180015474`
- `0x1800160c0`
- `0x180025bd8`
- `0x180027284`
- `0x18002748c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014c92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014c92`

## string_xrefs

- `0x180014caf`: `onecoreuap\base\devices\setup\dsm\service\containermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ContainerManager::_CreateContainer(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  std::_Ref_count_base *v9; // rcx
  _QWORD *v10; // rax
  PVOID v11; // rcx
  _BYTE v13[8]; // [rsp+28h] [rbp-18h] BYREF
  std::_Ref_count_base *v14; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v16; // [rsp+70h] [rbp+30h] BYREF
  _QWORD *v17; // [rsp+78h] [rbp+38h]
  __int64 v18; // [rsp+88h] [rbp+48h] BYREF

  v17 = a2;
  AcquireSRWLockExclusive((PSRWLOCK)a1);
  v18 = a1;
  if ( *(_DWORD *)(a1 + 152) == 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\containermanager.cpp",
      (const char *)0x80004004LL,
      0);
  *a2 = 0;
  a2[1] = 0;
  std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<Container>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<Container>>>,0>>::find(
    a1 + 8,
    &v16,
    a3);
  if ( v16 == *(_QWORD *)(a1 + 16) )
  {
    LODWORD(v16) = *(_DWORD *)(a1 + 152) == 0 ? 0x11 : 0;
    v6 = (__int64 *)std::make_shared<Container,_GUID const &,enum DSM_INSTALL_BEHAVIOR_FLAGS>(v13, a3, &v16);
    v7 = *v6;
    v8 = v6[1];
    *v6 = 0;
    v6[1] = 0;
    *a2 = v7;
    v9 = (std::_Ref_count_base *)a2[1];
    a2[1] = v8;
    if ( v9 )
      std::_Ref_count_base::_Decref(v9);
    if ( v14 )
      std::_Ref_count_base::_Decref(v14);
    v10 = (_QWORD *)std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<Container>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<Container>>>,0>>::_Try_emplace<_GUID const &,>(
                      a1 + 8,
                      v13,
                      a3);
    std::shared_ptr<Job>::operator=(*v10 + 32LL, a2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_12025944dd5e3a7e3168b2cc2e6c0bb5_Traceguids, a3);
    }
    if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
      McTemplateU0j_EventWriteTransfer(v11, &ContainerSetupQueued, a3);
  }
  else
  {
    std::shared_ptr<Job>::operator=(a2, v16 + 32);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
  return a2;
}

```

## disassembly

```asm
0x180014c70  mov     [rsp-28h+arg_8], rdx
0x180014c75  push    rbp
0x180014c76  push    rbx
0x180014c77  push    rsi
0x180014c78  push    rdi
0x180014c79  push    r14
0x180014c7b  mov     rbp, rsp
0x180014c7e  sub     rsp, 40h
0x180014c82  mov     rsi, r8
0x180014c85  mov     rbx, rdx
0x180014c88  mov     rdi, rcx
0x180014c8b  mov     [rbp+var_20], 0
0x180014c92  call    cs:__imp_AcquireSRWLockExclusive
0x180014c98  mov     [rbp+arg_18], rdi
0x180014c9c  cmp     dword ptr [rdi+98h], 2
0x180014ca3  jnz     short loc_180014CC1
0x180014ca5  mov     rcx, [rbp+28h]; this
0x180014ca9  mov     r9d, 80004004h; char *
0x180014caf  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180014cb6  mov     edx, 18Bh; void *
0x180014cbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014cc1  mov     qword ptr [rbx], 0
0x180014cc8  mov     qword ptr [rbx+8], 0
0x180014cd0  mov     [rbp+var_20], 1
0x180014cd7  mov     r8, rsi
0x180014cda  lea     rdx, [rbp+arg_0]
0x180014cde  lea     rcx, [rdi+8]
0x180014ce2  call    ?find@?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VContainer@@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VContainer@@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@V?$shared_ptr@VContainer@@@std@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<Container>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<Container>>>,0>>::find(_GUID const &)
0x180014ce7  mov     rdx, [rbp+arg_0]
0x180014ceb  cmp     rdx, [rdi+10h]
0x180014cef  jnz     loc_180014DC3
0x180014cf5  mov     eax, [rdi+98h]
0x180014cfb  neg     eax
0x180014cfd  sbb     ecx, ecx
0x180014cff  not     ecx
0x180014d01  and     ecx, 11h
0x180014d04  mov     dword ptr [rbp+arg_0], ecx
0x180014d07  lea     r8, [rbp+arg_0]
0x180014d0b  mov     rdx, rsi
0x180014d0e  lea     rcx, [rbp+var_18]
0x180014d12  call    ??$make_shared@VContainer@@AEBU_GUID@@W4DSM_INSTALL_BEHAVIOR_FLAGS@@@std@@YA?AV?$shared_ptr@VContainer@@@0@AEBU_GUID@@$$QEAW4DSM_INSTALL_BEHAVIOR_FLAGS@@@Z; std::make_shared<Container,_GUID const &,DSM_INSTALL_BEHAVIOR_FLAGS>(_GUID const &,DSM_INSTALL_BEHAVIOR_FLAGS &&)
0x180014d17  mov     rcx, [rax]
0x180014d1a  mov     rdx, [rax+8]
0x180014d1e  mov     qword ptr [rax], 0
0x180014d25  mov     qword ptr [rax+8], 0
0x180014d2d  mov     [rbx], rcx
0x180014d30  mov     rcx, [rbx+8]; this
0x180014d34  mov     [rbx+8], rdx
0x180014d38  test    rcx, rcx
0x180014d3b  jz      short loc_180014D42
0x180014d3d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014d42  mov     rcx, [rbp+var_10]; this
0x180014d46  test    rcx, rcx
0x180014d49  jz      short loc_180014D50
0x180014d4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014d50  mov     r8, rsi
0x180014d53  lea     rdx, [rbp+var_18]
0x180014d57  lea     rcx, [rdi+8]
0x180014d5b  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$_Hash@V?$_Umap_traits@U_GUID@@V?$shared_ptr@VContainer@@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@VContainer@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$shared_ptr@VContainer@@@std@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,std::shared_ptr<Container>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::shared_ptr<Container>>>,0>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180014d60  mov     rcx, [rax]
0x180014d63  add     rcx, 20h ; ' '
0x180014d67  mov     rdx, rbx
0x180014d6a  call    ??4?$shared_ptr@VJob@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Job>::operator=(std::shared_ptr<Job> const &)
0x180014d6f  lea     rax, WPP_GLOBAL_Control
0x180014d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d7d  cmp     rcx, rax
0x180014d80  jz      short loc_180014DA9
0x180014d82  test    dword ptr [rcx+1Ch], 100h
0x180014d89  jz      short loc_180014DA9
0x180014d8b  cmp     byte ptr [rcx+19h], 4
0x180014d8f  jb      short loc_180014DA9
0x180014d91  mov     edx, 0Eh
0x180014d96  mov     r9, rsi
0x180014d99  lea     r8, WPP_12025944dd5e3a7e3168b2cc2e6c0bb5_Traceguids
0x180014da0  mov     rcx, [rcx+10h]
0x180014da4  call    WPP_SF__guid_
0x180014da9  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 1
0x180014db0  jz      short loc_180014DD0
0x180014db2  mov     r8, rsi
0x180014db5  lea     rdx, ContainerSetupQueued
0x180014dbc  call    McTemplateU0j_EventWriteTransfer
0x180014dc1  jmp     short loc_180014DD0
0x180014dc3  add     rdx, 20h ; ' '
0x180014dc7  mov     rcx, rbx
0x180014dca  call    ??4?$shared_ptr@VJob@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Job>::operator=(std::shared_ptr<Job> const &)
0x180014dcf  nop
0x180014dd0  lea     rcx, [rbp+arg_18]
0x180014dd4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014dd9  mov     rax, rbx
0x180014ddc  add     rsp, 40h
0x180014de0  pop     r14
0x180014de2  pop     rdi
0x180014de3  pop     rsi
0x180014de4  pop     rbx
0x180014de5  pop     rbp
0x180014de6  retn
```
