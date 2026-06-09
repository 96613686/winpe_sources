# ApplicationInstanceManager::SetActivatedEventArgsForCentennialActivation(void *,IInspectable *)

- ea: `0x180025630`
- end: `0x18002599c`
- name: `?SetActivatedEventArgsForCentennialActivation@ApplicationInstanceManager@@UEAAJPEAXPEAUIInspectable@@@Z`
- size: `876`
- prototype: `int(ApplicationInstanceManager *__hidden this, void *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180011328`
- `0x180025630`
- `0x180025a20`
- `0x18003a338`
- `0x180047284`
- `0x180056208`
- `0x18005ae90`
- `0x18005b3c4`
- `0x18005b840`
- `0x180074788`
- `0x1800763ec`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025954`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025954`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025805`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025805`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002568a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18002568a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002596a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002596a`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18002572e`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18002576e`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18002572e`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18002576e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800258c6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800258c6`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800257d5`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800257d5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x1800256ac`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x1800256ac`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800256dc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800256dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ApplicationInstanceManager::SetActivatedEventArgsForCentennialActivation(
        RTL_SRWLOCK *this,
        void *a2,
        struct IInspectable *a3)
{
  RTL_SRWLOCK *v5; // rdi
  __int64 ProcessId; // r15
  int v7; // eax
  int UserContext; // eax
  HANDLE v9; // rsi
  unsigned __int64 v10; // r13
  int SecurityAttributesToken; // ebx
  _QWORD *v12; // rdi
  int v13; // ebx
  unsigned int ApplicationUserModelIdFromToken; // eax
  RTL_SRWLOCK *v15; // rsi
  __int64 *v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rax
  int v19; // r14d
  ApplicationInstanceManager *v20; // r12
  _QWORD *v21; // rax
  __int64 v22; // rbx
  struct IApplicationInstanceInfo *v23; // rcx
  int v25; // [rsp+20h] [rbp-1C8h]
  unsigned int v26; // [rsp+20h] [rbp-1C8h]
  size_t Size; // [rsp+40h] [rbp-1A8h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+48h] [rbp-1A0h] BYREF
  HANDLE token; // [rsp+50h] [rbp-198h] BYREF
  struct IApplicationInstanceInfo *v30; // [rsp+58h] [rbp-190h] BYREF
  ApplicationInstanceManager *v31; // [rsp+60h] [rbp-188h] BYREF
  int v32; // [rsp+68h] [rbp-180h]
  int v33; // [rsp+6Ch] [rbp-17Ch]
  unsigned __int64 v34[2]; // [rsp+70h] [rbp-178h] BYREF
  _QWORD v35[2]; // [rsp+80h] [rbp-168h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+90h] [rbp-158h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v5 = this;
  v31 = (ApplicationInstanceManager *)this;
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)0x80070057LL,
      v25);
  ProcessId = GetProcessId(a2);
  v34[0] = 0;
  applicationUserModelIdLength = 130;
  token = 0;
  v7 = UMgrOpenProcessTokenForQuery(ProcessId, &token);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)(unsigned int)v7,
      v25);
  UserContext = UMgrQueryUserContext(token, v34);
  if ( UserContext < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)(unsigned int)UserContext,
      v25);
  v9 = token;
  v10 = -1;
  LODWORD(Size) = 0;
  v26 = 0;
  SecurityAttributesToken = NtQuerySecurityAttributesToken(token, &qword_1800A12E8, 1, 0);
  if ( SecurityAttributesToken == -1073741789 )
  {
    v12 = operator new((unsigned int)Size);
    v26 = Size;
    SecurityAttributesToken = NtQuerySecurityAttributesToken(v9, &qword_1800A12E8, 1, v12);
    if ( SecurityAttributesToken >= 0 )
    {
      if ( *((_DWORD *)v12 + 1) )
        v10 = **(_QWORD **)(v12[1] + 32LL);
      else
        SecurityAttributesToken = -1073741275;
    }
    operator delete(v12);
    v5 = (RTL_SRWLOCK *)v31;
  }
  v13 = SecurityAttributesToken | 0x10000000;
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)(unsigned int)v13,
      v26);
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancemanager.cpp",
      (const char *)ApplicationUserModelIdFromToken,
      v26);
  v15 = v5 + 19;
  AcquireSRWLockExclusive(v5 + 19);
  v34[1] = (unsigned __int64)&v5[19];
  v30 = 0;
  v16 = (__int64 *)&v5[-18];
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  ApplicationInstanceManager::CreateOrGetApplicationInstanceFromMap(
    (ApplicationInstanceManager *)v16,
    ProcessId,
    a2,
    v34[0],
    applicationUserModelId,
    v10,
    &v30);
  v31 = (ApplicationInstanceManager *)a3;
  LODWORD(Size) = ProcessId;
  v17 = v16[32];
  v18 = *(_QWORD *)(v17 + 8);
  v19 = 0;
  if ( *(_BYTE *)(v18 + 25) )
  {
    v20 = *(ApplicationInstanceManager **)(v17 + 8);
  }
  else
  {
    do
    {
      v20 = (ApplicationInstanceManager *)v18;
      if ( *(_DWORD *)(v18 + 32) >= (unsigned int)ProcessId )
      {
        v19 = 1;
        v17 = v18;
        v18 = *(_QWORD *)v18;
      }
      else
      {
        v19 = 0;
        v18 = *(_QWORD *)(v18 + 16);
      }
    }
    while ( !*(_BYTE *)(v18 + 25) );
  }
  if ( *(_BYTE *)(v17 + 25) || (unsigned int)ProcessId < *(_DWORD *)(v17 + 32) )
  {
    if ( v16[33] == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v21 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,Microsoft::WRL::ComPtr<IInspectable>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,Microsoft::WRL::ComPtr<IInspectable>>,void *>>>(
            v35,
            (__int64)(v16 + 32),
            v16[32],
            &Size,
            &v31);
    v22 = v21[1];
    v21[1] = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<IInspectable>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<IInspectable>>,void *>>>(v35);
    v31 = v20;
    v32 = v19;
    v33 = 0;
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>>>::_Insert_node(
      v16 + 32,
      &v31,
      v22);
  }
  v23 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(struct IApplicationInstanceInfo *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( v15 )
    ReleaseSRWLockExclusive(v15);
  if ( (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(token);
  return 0;
}

```

## disassembly

```asm
0x180025630  push    rbx
0x180025632  push    rsi
0x180025633  push    rdi
0x180025634  push    r12
0x180025636  push    r13
0x180025638  push    r14
0x18002563a  push    r15
0x18002563c  sub     rsp, 1B0h
0x180025643  mov     rax, cs:__security_cookie
0x18002564a  xor     rax, rsp
0x18002564d  mov     [rsp+1E8h+var_48], rax
0x180025655  mov     r14, r8
0x180025658  mov     r12, rdx
0x18002565b  mov     rdi, rcx
0x18002565e  mov     [rsp+1E8h+var_188], rcx
0x180025663  mov     rcx, [rsp+1E8h]; this
0x18002566b  xor     ebx, ebx
0x18002566d  test    r8, r8
0x180025670  jnz     short loc_180025687
0x180025672  mov     r9d, 80070057h; char *
0x180025678  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002567f  lea     edx, [rbx+63h]; void *
0x180025682  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025687  mov     rcx, r12; Process
0x18002568a  call    cs:__imp_GetProcessId
0x180025690  mov     r15d, eax
0x180025693  mov     [rsp+1E8h+var_178], rbx
0x180025698  mov     [rsp+1E8h+applicationUserModelIdLength], 82h
0x1800256a0  mov     [rsp+1E8h+token], rbx
0x1800256a5  lea     rdx, [rsp+1E8h+token]
0x1800256aa  mov     ecx, eax
0x1800256ac  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x1800256b2  mov     rcx, [rsp+1E8h]; this
0x1800256ba  test    eax, eax
0x1800256bc  jns     short loc_1800256D2
0x1800256be  mov     r9d, eax; char *
0x1800256c1  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800256c8  mov     edx, 6Ch ; 'l'; void *
0x1800256cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800256d2  lea     rdx, [rsp+1E8h+var_178]
0x1800256d7  mov     rcx, [rsp+1E8h+token]
0x1800256dc  call    cs:__imp_UMgrQueryUserContext
0x1800256e2  mov     rcx, [rsp+1E8h]; this
0x1800256ea  test    eax, eax
0x1800256ec  jns     short loc_180025702
0x1800256ee  mov     r9d, eax; char *
0x1800256f1  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800256f8  mov     edx, 6Dh ; 'm'; void *
0x1800256fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025702  mov     rsi, [rsp+1E8h+token]
0x180025707  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002570b  mov     dword ptr [rsp+1E8h+Size], ebx
0x18002570f  lea     rax, [rsp+1E8h+Size]
0x180025714  mov     [rsp+1E8h+var_1C0], rax
0x180025719  mov     dword ptr [rsp+1E8h+var_1C8], ebx
0x18002571d  xor     r9d, r9d
0x180025720  lea     r8d, [r13+2]
0x180025724  lea     rdx, qword_1800A12E8
0x18002572b  mov     rcx, rsi
0x18002572e  call    cs:__imp_NtQuerySecurityAttributesToken
0x180025734  mov     ebx, eax
0x180025736  cmp     eax, 0C0000023h
0x18002573b  jnz     short loc_18002579F
0x18002573d  mov     ecx, dword ptr [rsp+1E8h+Size]; Size
0x180025741  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025746  mov     rdi, rax
0x180025749  mov     r8d, dword ptr [rsp+1E8h+Size]
0x18002574e  lea     rax, [rsp+1E8h+Size]
0x180025753  mov     [rsp+1E8h+var_1C0], rax
0x180025758  mov     dword ptr [rsp+1E8h+var_1C8], r8d; unsigned int
0x18002575d  mov     r9, rdi
0x180025760  lea     r8d, [r13+2]
0x180025764  lea     rdx, qword_1800A12E8
0x18002576b  mov     rcx, rsi
0x18002576e  call    cs:__imp_NtQuerySecurityAttributesToken
0x180025774  mov     ebx, eax
0x180025776  test    eax, eax
0x180025778  js      short loc_180025792
0x18002577a  cmp     dword ptr [rdi+4], 0
0x18002577e  jz      short loc_18002578D
0x180025780  mov     rcx, [rdi+8]
0x180025784  mov     rdx, [rcx+20h]
0x180025788  mov     r13, [rdx]
0x18002578b  jmp     short loc_180025792
0x18002578d  mov     ebx, 0C0000225h
0x180025792  mov     rcx, rdi; Block
0x180025795  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002579a  mov     rdi, [rsp+1E8h+var_188]
0x18002579f  or      ebx, 10000000h
0x1800257a5  mov     rcx, [rsp+1E8h]; this
0x1800257ad  jge     short loc_1800257C3
0x1800257af  mov     r9d, ebx; char *
0x1800257b2  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800257b9  mov     edx, 6Eh ; 'n'; void *
0x1800257be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800257c3  lea     r8, [rsp+1E8h+applicationUserModelId]; applicationUserModelId
0x1800257cb  lea     rdx, [rsp+1E8h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800257d0  mov     rcx, [rsp+1E8h+token]; token
0x1800257d5  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800257db  mov     rcx, [rsp+1E8h]; this
0x1800257e3  xor     ebx, ebx
0x1800257e5  test    eax, eax
0x1800257e7  jz      short loc_1800257FB
0x1800257e9  mov     r9d, eax; char *
0x1800257ec  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800257f3  lea     edx, [rbx+6Fh]; void *
0x1800257f6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800257fb  lea     rsi, [rdi+98h]
0x180025802  mov     rcx, rsi; SRWLock
0x180025805  call    cs:__imp_AcquireSRWLockExclusive
0x18002580b  mov     [rsp+1E8h+var_170], rsi
0x180025810  mov     [rsp+1E8h+var_190], rbx
0x180025815  add     rdi, 0FFFFFFFFFFFFFF70h
0x18002581c  lea     rcx, [rsp+1E8h+var_190]
0x180025821  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180025826  lea     rax, [rsp+1E8h+var_190]
0x18002582b  mov     [rsp+1E8h+var_1B8], rax; struct IApplicationInstanceInfo **
0x180025830  mov     [rsp+1E8h+var_1C0], r13; unsigned __int64
0x180025835  lea     rax, [rsp+1E8h+applicationUserModelId]
0x18002583d  mov     [rsp+1E8h+var_1C8], rax; unsigned __int16 *
0x180025842  mov     r9, [rsp+1E8h+var_178]; unsigned __int64
0x180025847  mov     r8, r12; void *
0x18002584a  mov     edx, r15d; unsigned int
0x18002584d  mov     rcx, rdi; this
0x180025850  call    ?CreateOrGetApplicationInstanceFromMap@ApplicationInstanceManager@@AEAAXKPEAX_KPEBG1PEAPEAUIApplicationInstanceInfo@@@Z; ApplicationInstanceManager::CreateOrGetApplicationInstanceFromMap(ulong,void *,unsigned __int64,ushort const *,unsigned __int64,IApplicationInstanceInfo * *)
0x180025855  mov     [rsp+1E8h+var_188], r14
0x18002585a  mov     dword ptr [rsp+1E8h+Size], r15d
0x18002585f  mov     rcx, [rdi+100h]
0x180025866  mov     rax, [rcx+8]
0x18002586a  mov     r14d, ebx
0x18002586d  xor     r13d, r13d
0x180025870  cmp     [rax+19h], bl
0x180025873  jnz     short loc_18002589A
0x180025875  mov     r12, rax
0x180025878  cmp     [rax+20h], r15d
0x18002587c  jnb     short loc_180025887
0x18002587e  mov     r14d, ebx
0x180025881  mov     rax, [rax+10h]
0x180025885  jmp     short loc_180025893
0x180025887  mov     r14d, 1
0x18002588d  mov     rcx, rax
0x180025890  mov     rax, [rax]
0x180025893  cmp     [rax+19h], bl
0x180025896  jz      short loc_180025875
0x180025898  jmp     short loc_18002589D
0x18002589a  mov     r12, rax
0x18002589d  cmp     [rcx+19h], bl
0x1800258a0  jnz     short loc_1800258AC
0x1800258a2  cmp     r15d, [rcx+20h]
0x1800258a6  jnb     loc_180025930
0x1800258ac  mov     rax, 555555555555555h
0x1800258b6  cmp     [rdi+108h], rax
0x1800258bd  jnz     short loc_1800258CC
0x1800258bf  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800258c6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800258cc  lea     rax, [rsp+1E8h+var_188]
0x1800258d1  mov     [rsp+1E8h+var_1C8], rax
0x1800258d6  lea     r9, [rsp+1E8h+Size]
0x1800258db  mov     r8, [rdi+100h]
0x1800258e2  lea     rdx, [rdi+100h]
0x1800258e9  lea     rcx, [rsp+1E8h+var_168]
0x1800258f1  call    ??$?0AEAKAEAPEAUIInspectable@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$ComPtr@UIInspectable@@@WRL@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$ComPtr@UIInspectable@@@WRL@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$ComPtr@UIInspectable@@@WRL@Microsoft@@@std@@PEAX@1@AEAKAEAPEAUIInspectable@@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,Microsoft::WRL::ComPtr<IInspectable>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,Microsoft::WRL::ComPtr<IInspectable>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,Microsoft::WRL::ComPtr<IInspectable>>,void *>> &,std::_Tree_node<std::pair<ulong const,Microsoft::WRL::ComPtr<IInspectable>>,void *> *,ulong &,IInspectable * &)
0x1800258f6  mov     rbx, [rax+8]
0x1800258fa  mov     [rax+8], r13
0x1800258fe  lea     rcx, [rsp+1E8h+var_168]
0x180025906  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$ComPtr@UIInspectable@@@WRL@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<IInspectable>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<IInspectable>>,void *>>>(void)
0x18002590b  mov     [rsp+1E8h+var_188], r12
0x180025910  mov     [rsp+1E8h+var_180], r14d
0x180025915  mov     [rsp+1E8h+var_17C], r13d
0x18002591a  mov     r8, rbx
0x18002591d  lea     rdx, [rsp+1E8h+var_188]
0x180025922  lea     rcx, [rdi+100h]
0x180025929  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKV?$com_ptr_t@VAutoCloseHamActivity@@Uerr_returncode_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>,void *> *>,std::_Tree_node<std::pair<ulong const,wil::com_ptr_t<AutoCloseHamActivity,wil::err_returncode_policy>>,void *> * const)
0x18002592e  xor     ebx, ebx
0x180025930  mov     rcx, [rsp+1E8h+var_190]
0x180025935  test    rcx, rcx
0x180025938  jz      short loc_18002594C
0x18002593a  mov     [rsp+1E8h+var_190], rbx
0x18002593f  mov     rax, [rcx]
0x180025942  mov     rax, [rax+10h]
0x180025946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002594b  nop
0x18002594c  test    rsi, rsi
0x18002594f  jz      short loc_18002595B
0x180025951  mov     rcx, rsi; SRWLock
0x180025954  call    cs:__imp_ReleaseSRWLockExclusive
0x18002595a  nop
0x18002595b  mov     rcx, [rsp+1E8h+token]; hObject
0x180025960  lea     rax, [rcx-1]
0x180025964  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180025968  ja      short loc_180025970
0x18002596a  call    cs:__imp_CloseHandle
0x180025970  xor     eax, eax
0x180025972  jmp     short loc_180025978
0x180025974  mov     eax, [rsp+1E8h+applicationUserModelIdLength]
0x180025978  mov     rcx, [rsp+1E8h+var_48]
0x180025980  xor     rcx, rsp; StackCookie
0x180025983  call    __security_check_cookie
0x180025988  add     rsp, 1B0h
0x18002598f  pop     r15
0x180025991  pop     r14
0x180025993  pop     r13
0x180025995  pop     r12
0x180025997  pop     rdi
0x180025998  pop     rsi
0x180025999  pop     rbx
0x18002599a  retn
```
