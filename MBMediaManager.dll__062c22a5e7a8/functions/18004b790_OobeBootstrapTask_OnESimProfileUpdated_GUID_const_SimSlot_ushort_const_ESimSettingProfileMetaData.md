# OobeBootstrapTask::OnESimProfileUpdated(_GUID const &,SimSlot,ushort const *,ESimSettingProfileMetaData)

- ea: `0x18004b790`
- end: `0x18004b9f4`
- name: `?OnESimProfileUpdated@OobeBootstrapTask@@UEAAJAEBU_GUID@@W4SimSlot@@PEBGUESimSettingProfileMetaData@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int, const wchar_t *, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000ad20`
- `0x18001ad74`
- `0x18001bd80`
- `0x18001f34c`
- `0x18001f5b8`
- `0x180022a1c`
- `0x180022e9c`
- `0x18002cd20`
- `0x1800485a4`
- `0x18004a8a4`
- `0x18004b790`
- `0x18004be88`
- `0x18004c374`
- `0x180059010`

## string_xrefs

- `0x18004b85d`: `Profile Added. profileId=%ls, profileName=%ls, serviceProviderName=%ls, Enabled=%hs`
- `0x18004b925`: `Profile Removed. profileId=%ls, profileClass=%d, Enabled=%hs`
- `0x18004b7f1`: `OobeBootstrapTask::OnESimProfileUpdated`
- `0x18004b869`: `OobeBootstrapTask::OnESimProfileUpdated`
- `0x18004b8bd`: `OobeBootstrapTask::OnESimProfileUpdated`
- `0x18004b901`: `OobeBootstrapTask::OnESimProfileUpdated`
- `0x18004b931`: `OobeBootstrapTask::OnESimProfileUpdated`
- `0x18004b972`: `OobeBootstrapTask::OnESimProfileUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall OobeBootstrapTask::OnESimProfileUpdated(
        __int64 a1,
        _QWORD *a2,
        int a3,
        const wchar_t *a4,
        __int64 a5)
{
  __int64 v7; // rax
  char v9; // si
  int v10; // eax
  char v11; // cl
  const char *v12; // rdx
  __int64 v13; // r8
  char v14; // dl
  int v15; // eax
  int v16; // ebx
  int v17; // [rsp+20h] [rbp-88h]
  int v18; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v19[16]; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v7 = *(_QWORD *)(a1 + 72) - *a2;
  if ( !v7 )
    v7 = *(_QWORD *)(a1 + 80) - a2[1];
  if ( v7 )
    return 0;
  if ( *(_DWORD *)(a1 + 100) == a3 )
  {
    v9 = 0;
    wil::EnterCriticalSection(&v18, a1 + 32);
    v10 = *(_DWORD *)(a5 + 896);
    v11 = *(_BYTE *)(a5 + 888);
    v12 = "true";
    if ( v10 )
    {
      if ( !v11 )
        v12 = "false";
      MBSettingUXLogging::Info(
        "OobeBootstrapTask::OnESimProfileUpdated",
        0xB2u,
        "Profile Removed. profileId=%ls, profileClass=%d, Enabled=%hs",
        a4,
        v10,
        v12);
      std::wstring::wstring(v20, a4);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
        a1 + 112,
        v20);
      std::wstring::_Tidy_deallocate(v20);
    }
    else
    {
      if ( !v11 )
        v12 = "false";
      MBSettingUXLogging::Info(
        "OobeBootstrapTask::OnESimProfileUpdated",
        0x9Au,
        "Profile Added. profileId=%ls, profileName=%ls, serviceProviderName=%ls, Enabled=%hs",
        a4,
        (const wchar_t *)(a5 + 42),
        (const wchar_t *)(a5 + 302),
        v12);
      std::wstring::wstring(v20, a4);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
        a1 + 112,
        v19,
        v20);
      std::wstring::_Tidy_deallocate(v20);
      if ( *(_BYTE *)(a5 + 888) )
      {
        MBSettingUXLogging::Info(
          "OobeBootstrapTask::OnESimProfileUpdated",
          0xA0u,
          "Active profile detected. profileId=%ls",
          a4);
        v13 = -1;
        do
          ++v13;
        while ( a4[v13] );
        std::wstring::_Assign<unsigned short>(a1 + 128, a4);
        v9 = OobeBootstrapTask::ShouldDeleteProfile(a1, v14);
        if ( v9 )
        {
          MBSettingUXLogging::Info(
            "OobeBootstrapTask::OnESimProfileUpdated",
            0xA6u,
            "Changing state to 'RunningDeletion'");
          *(_DWORD *)(a1 + 96) = 1;
        }
      }
    }
    MBSettingUXLogging::Info(
      "OobeBootstrapTask::OnESimProfileUpdated",
      0xB6u,
      "newProfileCount=%d",
      *(_DWORD *)(a1 + 120));
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
    if ( v9 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**(_QWORD **)(a1 + 24) + 56LL))(
              *(_QWORD *)(a1 + 24),
              a4,
              0);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobebootstraptask.cpp",
          (const char *)(unsigned int)v15,
          v17);
        MBSettingUXLogging::BootstrapProfileDeletion(v16, 0);
      }
    }
    return 0;
  }
  else
  {
    MBSettingUXLogging::Info(
      "OobeBootstrapTask::OnESimProfileUpdated",
      0x8Cu,
      "Discarding notification for slot %d",
      a3);
    return 0;
  }
}

```

## disassembly

```asm
0x18004b790  push    rbx
0x18004b792  push    rsi
0x18004b793  push    rdi
0x18004b794  push    r14
0x18004b796  push    r15
0x18004b798  sub     rsp, 80h
0x18004b79f  mov     rax, cs:__security_cookie
0x18004b7a6  xor     rax, rsp
0x18004b7a9  mov     [rsp+0A8h+var_30], rax
0x18004b7ae  mov     rdi, r9
0x18004b7b1  mov     rbx, rcx
0x18004b7b4  mov     r14, [rsp+0A8h+arg_20]
0x18004b7bc  mov     rax, [rcx+48h]
0x18004b7c0  sub     rax, [rdx]
0x18004b7c3  jnz     short loc_18004B7CD
0x18004b7c5  mov     rax, [rcx+50h]
0x18004b7c9  sub     rax, [rdx+8]
0x18004b7cd  xor     r15d, r15d
0x18004b7d0  test    rax, rax
0x18004b7d3  jz      short loc_18004B7DC
0x18004b7d5  xor     eax, eax
0x18004b7d7  jmp     loc_18004B9D7
0x18004b7dc  cmp     [rcx+64h], r8d
0x18004b7e0  jz      short loc_18004B804
0x18004b7e2  mov     r9d, r8d
0x18004b7e5  lea     r8, aDiscardingNoti; "Discarding notification for slot %d"
0x18004b7ec  mov     edx, 8Ch; unsigned int
0x18004b7f1  lea     rcx, aOobebootstrapt_0; "OobeBootstrapTask::OnESimProfileUpdated"
0x18004b7f8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b7fd  xor     eax, eax
0x18004b7ff  jmp     loc_18004B9D7
0x18004b804  mov     sil, r15b
0x18004b807  lea     rdx, [rcx+20h]
0x18004b80b  lea     rcx, [rsp+0A8h+var_68]
0x18004b810  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004b815  nop
0x18004b816  mov     eax, [r14+380h]
0x18004b81d  mov     cl, [r14+378h]
0x18004b824  lea     r8, aFalse; "false"
0x18004b82b  lea     rdx, aTrue; "true"
0x18004b832  mov     r9, rdi
0x18004b835  test    eax, eax
0x18004b837  jnz     loc_18004B916
0x18004b83d  test    cl, cl
0x18004b83f  cmovz   rdx, r8
0x18004b843  lea     rax, [r14+12Eh]
0x18004b84a  lea     rcx, [r14+2Ah]
0x18004b84e  mov     [rsp+0A8h+var_78], rdx
0x18004b853  mov     [rsp+0A8h+var_80], rax
0x18004b858  mov     qword ptr [rsp+0A8h+var_88], rcx
0x18004b85d  lea     r8, aProfileAddedPr; "Profile Added. profileId=%ls, profileNa"...
0x18004b864  mov     edx, 9Ah; unsigned int
0x18004b869  lea     rcx, aOobebootstrapt_0; "OobeBootstrapTask::OnESimProfileUpdated"
0x18004b870  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b875  mov     rdx, rdi
0x18004b878  lea     rcx, [rsp+0A8h+var_50]
0x18004b87d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004b882  nop
0x18004b883  lea     rcx, [rbx+70h]
0x18004b887  lea     r8, [rsp+0A8h+var_50]
0x18004b88c  lea     rdx, [rsp+0A8h+var_60]
0x18004b891  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x18004b896  nop
0x18004b897  lea     rcx, [rsp+0A8h+var_50]
0x18004b89c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b8a1  cmp     [r14+378h], r15b
0x18004b8a8  jz      loc_18004B962
0x18004b8ae  mov     r9, rdi
0x18004b8b1  lea     r8, aActiveProfileD; "Active profile detected. profileId=%ls"
0x18004b8b8  mov     edx, 0A0h; unsigned int
0x18004b8bd  lea     rcx, aOobebootstrapt_0; "OobeBootstrapTask::OnESimProfileUpdated"
0x18004b8c4  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b8c9  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004b8cd  inc     r8
0x18004b8d0  cmp     [rdi+r8*2], r15w
0x18004b8d5  jnz     short loc_18004B8CD
0x18004b8d7  lea     rcx, [rbx+80h]
0x18004b8de  mov     rdx, rdi
0x18004b8e1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004b8e6  mov     rcx, rbx
0x18004b8e9  call    ?ShouldDeleteProfile@OobeBootstrapTask@@AEAA_NUwrite_lock_required@wil@@@Z; OobeBootstrapTask::ShouldDeleteProfile(wil::write_lock_required)
0x18004b8ee  mov     sil, al
0x18004b8f1  test    al, al
0x18004b8f3  jz      short loc_18004B962
0x18004b8f5  lea     r8, aChangingStateT_2; "Changing state to 'RunningDeletion'"
0x18004b8fc  mov     edx, 0A6h; unsigned int
0x18004b901  lea     rcx, aOobebootstrapt_0; "OobeBootstrapTask::OnESimProfileUpdated"
0x18004b908  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b90d  mov     dword ptr [rbx+60h], 1
0x18004b914  jmp     short loc_18004B962
0x18004b916  test    cl, cl
0x18004b918  cmovz   rdx, r8
0x18004b91c  mov     [rsp+0A8h+var_80], rdx
0x18004b921  mov     [rsp+0A8h+var_88], eax; int
0x18004b925  lea     r8, aProfileRemoved_0; "Profile Removed. profileId=%ls, profile"...
0x18004b92c  mov     edx, 0B2h; unsigned int
0x18004b931  lea     rcx, aOobebootstrapt_0; "OobeBootstrapTask::OnESimProfileUpdated"
0x18004b938  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b93d  mov     rdx, rdi
0x18004b940  lea     rcx, [rsp+0A8h+var_50]
0x18004b945  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004b94a  lea     rcx, [rbx+70h]
0x18004b94e  lea     rdx, [rsp+0A8h+var_50]
0x18004b953  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::wstring const &)
0x18004b958  lea     rcx, [rsp+0A8h+var_50]
0x18004b95d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b962  mov     r9d, [rbx+78h]
0x18004b966  lea     r8, aNewprofilecoun; "newProfileCount=%d"
0x18004b96d  mov     edx, 0B6h; unsigned int
0x18004b972  lea     rcx, aOobebootstrapt_0; "OobeBootstrapTask::OnESimProfileUpdated"
0x18004b979  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b97e  nop
0x18004b97f  lea     rcx, [rsp+0A8h+var_68]
0x18004b984  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004b989  test    sil, sil
0x18004b98c  jz      short loc_18004B9CF
0x18004b98e  mov     rcx, [rbx+18h]
0x18004b992  mov     rax, [rcx]
0x18004b995  xor     r8d, r8d
0x18004b998  mov     rdx, rdi
0x18004b99b  mov     rax, [rax+38h]
0x18004b99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9a4  mov     ebx, eax
0x18004b9a6  test    eax, eax
0x18004b9a8  jns     short loc_18004B9CF
0x18004b9aa  mov     rcx, [rsp+0A8h]; this
0x18004b9b2  mov     r9d, eax; char *
0x18004b9b5  lea     r8, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; unsigned int
0x18004b9bc  mov     edx, 0BFh; void *
0x18004b9c1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004b9c6  xor     edx, edx; unsigned int
0x18004b9c8  mov     ecx, ebx; int
0x18004b9ca  call    ?BootstrapProfileDeletion@MBSettingUXLogging@@SAXJK@Z; MBSettingUXLogging::BootstrapProfileDeletion(long,ulong)
0x18004b9cf  xor     eax, eax
0x18004b9d1  jmp     short loc_18004B9D7
0x18004b9d3  mov     eax, [rsp+0A8h+var_68]
0x18004b9d7  mov     rcx, [rsp+0A8h+var_30]
0x18004b9dc  xor     rcx, rsp; StackCookie
0x18004b9df  call    __security_check_cookie
0x18004b9e4  add     rsp, 80h
0x18004b9eb  pop     r15
0x18004b9ed  pop     r14
0x18004b9ef  pop     rdi
0x18004b9f0  pop     rsi
0x18004b9f1  pop     rbx
0x18004b9f2  retn
```
