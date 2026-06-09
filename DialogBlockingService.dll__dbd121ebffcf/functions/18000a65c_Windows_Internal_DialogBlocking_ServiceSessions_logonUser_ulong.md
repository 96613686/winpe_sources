# Windows::Internal::DialogBlocking::ServiceSessions::logonUser(ulong)

- ea: `0x18000a65c`
- end: `0x18000a9bf`
- name: `?logonUser@ServiceSessions@DialogBlocking@Internal@Windows@@QEAAXK@Z`
- size: `867`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::ServiceSessions *this, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006248`

## callees

- `0x180001644`
- `0x180001650`
- `0x180001c90`
- `0x180008658`
- `0x18000899c`
- `0x180008b04`
- `0x1800095d0`
- `0x18000a00c`
- `0x18000a23c`
- `0x18000a27c`
- `0x18000a328`
- `0x18000a65c`
- `0x18000ab90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a6da`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a6da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a739`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a990`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a6bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a724`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a97b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a6bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a724`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a97b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a76c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a78b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a83c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a855`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a76c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a78b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a83c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000a855`
- `msvcp_win!_Mtx_lock` at `0x18000a75d`
- `msvcp_win!_Mtx_lock` at `0x18000a82d`
- `msvcp_win!_Mtx_lock` at `0x18000a75d`
- `msvcp_win!_Mtx_lock` at `0x18000a82d`
- `msvcp_win!_Mtx_unlock` at `0x18000a7f8`
- `msvcp_win!_Mtx_unlock` at `0x18000a93c`
- `msvcp_win!_Mtx_unlock` at `0x18000a7f8`
- `msvcp_win!_Mtx_unlock` at `0x18000a93c`
- `WTSAPI32!WTSQueryUserToken` at `0x18000a689`
- `WTSAPI32!WTSQueryUserToken` at `0x18000a689`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logonUser(
        Windows::Internal::DialogBlocking::ServiceSessions *this,
        unsigned int a2)
{
  int v3; // r14d
  HLOCAL v4; // rdi
  DWORD LastError; // ebx
  char v6; // bl
  void *v7; // rcx
  Windows::Internal::DialogBlocking::HookProcess **v8; // rdi
  struct _Mtx_internal_imp_t *v9; // rbx
  __int64 *v10; // rdx
  __int64 *v11; // rax
  __int64 *v12; // rcx
  void *v13; // r13
  __int64 v14; // r15
  _QWORD *v15; // r12
  __int64 inserted; // rcx
  _QWORD *v17; // rax
  _DWORD *v18; // rax
  Windows::Internal::DialogBlocking::HookProcess **v19; // rsi
  void *v20; // rcx
  void *Block; // [rsp+20h] [rbp-40h] BYREF
  char v22; // [rsp+28h] [rbp-38h]
  HANDLE phToken; // [rsp+30h] [rbp-30h] BYREF
  int v24; // [rsp+38h] [rbp-28h]
  int v25; // [rsp+3Ch] [rbp-24h]
  Windows::Internal::DialogBlocking::ServiceSessions *v26; // [rsp+40h] [rbp-20h]
  __int64 v27; // [rsp+48h] [rbp-18h]
  unsigned int v28; // [rsp+A8h] [rbp+48h] BYREF
  Windows::Internal::DialogBlocking::HookProcess **v29; // [rsp+B0h] [rbp+50h]
  HLOCAL hMem; // [rsp+B8h] [rbp+58h] BYREF

  v28 = a2;
  v3 = 0;
  phToken = 0;
  if ( WTSQueryUserToken(a2, &phToken) )
  {
    hMem = 0;
    wil::get_token_information<_TOKEN_USER>(&Block, (__int64)phToken);
    v4 = hMem;
    if ( hMem )
    {
      LastError = GetLastError();
      LocalFree(v4);
      SetLastError(LastError);
    }
    hMem = 0;
    if ( ConvertSidToStringSidW(*(PSID *)Block, (LPWSTR *)&hMem) )
    {
      LODWORD(v29) = 0;
      if ( (int)GetAssignedAccessTypeForUser((unsigned __int16 *)hMem) < 0 || (v6 = 1, (_DWORD)v29 != 3) )
        v6 = 0;
      v7 = Block;
      Block = 0;
      if ( v7 )
        operator delete(v7);
      if ( hMem )
        LocalFree(hMem);
      if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(phToken);
      if ( v6 )
      {
        v8 = 0;
        v29 = 0;
        v9 = (Windows::Internal::DialogBlocking::ServiceSessions *)((char *)this + 16);
        Block = (char *)this + 16;
        v22 = 0;
        if ( _Mtx_lock((Windows::Internal::DialogBlocking::ServiceSessions *)((char *)this + 16)) )
        {
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        if ( *((_DWORD *)this + 23) == 0x7FFFFFFF )
        {
          *((_DWORD *)this + 23) = 2147483646;
          std::_Throw_Cpp_error(6);
          __debugbreak();
        }
        v22 = 1;
        v10 = *(__int64 **)this;
        v11 = *(__int64 **)(*(_QWORD *)this + 8LL);
        HIDWORD(v27) = 0;
        v12 = v10;
        while ( !*((_BYTE *)v11 + 25) )
        {
          if ( *((_DWORD *)v11 + 8) >= v28 )
          {
            v12 = v11;
            v11 = (__int64 *)*v11;
          }
          else
          {
            v11 = (__int64 *)v11[2];
          }
        }
        if ( !*((_BYTE *)v12 + 25) && v28 >= *((_DWORD *)v12 + 8) && v12 != v10 )
        {
          v8 = (Windows::Internal::DialogBlocking::HookProcess **)v12[5];
          v29 = v8;
          v12[5] = 0;
          std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::erase(
            this,
            &v28);
        }
        if ( this == (Windows::Internal::DialogBlocking::ServiceSessions *)-16LL )
          std::_Throw_system_error(1u);
        _Mtx_unlock((Windows::Internal::DialogBlocking::ServiceSessions *)((char *)this + 16));
        v22 = 0;
        hMem = operator new(0x28u);
        v13 = (void *)Windows::Internal::DialogBlocking::HookMgr::HookMgr(
                        (Windows::Internal::DialogBlocking::HookMgr *)hMem,
                        v28);
        phToken = v13;
        Windows::Internal::DialogBlocking::HookMgr::AttachHooks((Windows::Internal::DialogBlocking::HookMgr *)v13);
        if ( _Mtx_lock((Windows::Internal::DialogBlocking::ServiceSessions *)((char *)this + 16)) )
        {
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        if ( *((_DWORD *)this + 23) == 0x7FFFFFFF )
        {
          *((_DWORD *)this + 23) = 2147483646;
          std::_Throw_Cpp_error(6);
          __debugbreak();
        }
        v22 = 1;
        v14 = *(_QWORD *)this;
        v15 = *(_QWORD **)(*(_QWORD *)this + 8LL);
        hMem = 0;
        inserted = v14;
        v17 = v15;
        while ( !*((_BYTE *)v17 + 25) )
        {
          v15 = v17;
          if ( *((_DWORD *)v17 + 8) >= v28 )
          {
            v3 = 1;
            inserted = (__int64)v17;
            v17 = (_QWORD *)*v17;
          }
          else
          {
            v3 = 0;
            v17 = (_QWORD *)v17[2];
          }
        }
        if ( *(_BYTE *)(inserted + 25) || v28 < *(_DWORD *)(inserted + 32) )
        {
          if ( *((_QWORD *)this + 1) == 0x555555555555555LL )
            std::_Throw_tree_length_error();
          v26 = this;
          v27 = 0;
          v18 = operator new(0x30u);
          v18[8] = v28;
          *((_QWORD *)v18 + 5) = 0;
          *(_QWORD *)v18 = v14;
          *((_QWORD *)v18 + 1) = v14;
          *((_QWORD *)v18 + 2) = v14;
          *((_WORD *)v18 + 12) = 0;
          phToken = v15;
          v24 = v3;
          v25 = (int)hMem;
          inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Insert_node(
                       this,
                       (__int64)&phToken,
                       (__int64)v18);
        }
        v19 = *(Windows::Internal::DialogBlocking::HookProcess ***)(inserted + 40);
        *(_QWORD *)(inserted + 40) = v13;
        if ( v19 )
        {
          Windows::Internal::DialogBlocking::HookMgr::~HookMgr(v19);
          operator delete(v19);
        }
        _Mtx_unlock(v9);
        if ( v8 )
        {
          Windows::Internal::DialogBlocking::HookMgr::~HookMgr(v8);
          operator delete(v8);
        }
      }
      return;
    }
    v20 = Block;
    Block = 0;
    if ( v20 )
      operator delete(v20);
    if ( hMem )
      LocalFree(hMem);
  }
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
}

```

## disassembly

```asm
0x18000a65c  mov     [rsp-38h+arg_0], rbx
0x18000a661  mov     [rsp-38h+arg_8], edx
0x18000a665  push    rbp
0x18000a666  push    rsi
0x18000a667  push    rdi
0x18000a668  push    r12
0x18000a66a  push    r13
0x18000a66c  push    r14
0x18000a66e  push    r15
0x18000a670  mov     rbp, rsp
0x18000a673  sub     rsp, 60h
0x18000a677  mov     eax, edx
0x18000a679  mov     rsi, rcx
0x18000a67c  xor     r14d, r14d
0x18000a67f  mov     [rbp+phToken], r14
0x18000a683  lea     rdx, [rbp+phToken]; phToken
0x18000a687  mov     ecx, eax; SessionId
0x18000a689  call    cs:__imp_WTSQueryUserToken
0x18000a68f  test    eax, eax
0x18000a691  jz      loc_18000A982
0x18000a697  mov     [rbp+hMem], r14
0x18000a69b  mov     rdx, [rbp+phToken]
0x18000a69f  lea     rcx, [rbp+Block]
0x18000a6a3  call    ??$get_token_information@U_TOKEN_USER@@@wil@@YA?A_PPEAX@Z
0x18000a6a8  nop
0x18000a6a9  mov     rdi, [rbp+hMem]
0x18000a6ad  test    rdi, rdi
0x18000a6b0  jz      short loc_18000A6CB
0x18000a6b2  call    cs:__imp_GetLastError
0x18000a6b8  mov     ebx, eax
0x18000a6ba  mov     rcx, rdi; hMem
0x18000a6bd  call    cs:__imp_LocalFree
0x18000a6c3  mov     ecx, ebx; dwErrCode
0x18000a6c5  call    cs:__imp_SetLastError
0x18000a6cb  mov     [rbp+hMem], r14
0x18000a6cf  lea     rdx, [rbp+hMem]; StringSid
0x18000a6d3  mov     rcx, [rbp+Block]
0x18000a6d7  mov     rcx, [rcx]; Sid
0x18000a6da  call    cs:__imp_ConvertSidToStringSidW
0x18000a6e0  test    eax, eax
0x18000a6e2  jz      loc_18000A95F
0x18000a6e8  mov     dword ptr [rbp+arg_10], r14d
0x18000a6ec  lea     r8, [rbp+arg_10]
0x18000a6f0  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x18000a6f4  call    GetAssignedAccessTypeForUser
0x18000a6f9  test    eax, eax
0x18000a6fb  js      short loc_18000A705
0x18000a6fd  cmp     dword ptr [rbp+arg_10], 3
0x18000a701  mov     bl, 1
0x18000a703  jz      short loc_18000A708
0x18000a705  mov     bl, r14b
0x18000a708  mov     rcx, [rbp+Block]; Block
0x18000a70c  mov     [rbp+Block], r14
0x18000a710  test    rcx, rcx
0x18000a713  jz      short loc_18000A71B
0x18000a715  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a71a  nop
0x18000a71b  mov     rcx, [rbp+hMem]; hMem
0x18000a71f  test    rcx, rcx
0x18000a722  jz      short loc_18000A72B
0x18000a724  call    cs:__imp_LocalFree
0x18000a72a  nop
0x18000a72b  mov     rcx, [rbp+phToken]; hObject
0x18000a72f  lea     rax, [rcx-1]
0x18000a733  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a737  ja      short loc_18000A73F
0x18000a739  call    cs:__imp_CloseHandle
0x18000a73f  test    bl, bl
0x18000a741  jz      loc_18000A996
0x18000a747  mov     rdi, r14
0x18000a74a  mov     [rbp+arg_10], r14
0x18000a74e  lea     rbx, [rsi+10h]
0x18000a752  mov     [rbp+Block], rbx
0x18000a756  mov     [rbp+var_38], r14b
0x18000a75a  mov     rcx, rbx; _Mtx_t
0x18000a75d  call    cs:__imp__Mtx_lock
0x18000a763  test    eax, eax
0x18000a765  jz      short loc_18000A773
0x18000a767  mov     ecx, 5
0x18000a76c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a772  int     3; Trap to Debugger
0x18000a773  mov     eax, [rbx+4Ch]
0x18000a776  mov     r15d, 7FFFFFFFh
0x18000a77c  cmp     eax, r15d
0x18000a77f  jnz     short loc_18000A792
0x18000a781  dec     eax
0x18000a783  mov     [rbx+4Ch], eax
0x18000a786  mov     ecx, 6
0x18000a78b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a791  int     3; Trap to Debugger
0x18000a792  mov     [rbp+var_38], 1
0x18000a796  mov     rdx, [rsi]
0x18000a799  mov     rax, [rdx+8]
0x18000a79d  xor     ecx, ecx
0x18000a79f  mov     [rbp+var_14], ecx
0x18000a7a2  mov     rcx, rdx
0x18000a7a5  mov     r8d, [rbp+arg_8]
0x18000a7a9  jmp     short loc_18000A7BD
0x18000a7ab  cmp     [rax+20h], r8d
0x18000a7af  jnb     short loc_18000A7B7
0x18000a7b1  mov     rax, [rax+10h]
0x18000a7b5  jmp     short loc_18000A7BD
0x18000a7b7  mov     rcx, rax
0x18000a7ba  mov     rax, [rax]
0x18000a7bd  cmp     [rax+19h], r14b
0x18000a7c1  jz      short loc_18000A7AB
0x18000a7c3  cmp     [rcx+19h], r14b
0x18000a7c7  jnz     short loc_18000A7EC
0x18000a7c9  cmp     r8d, [rcx+20h]
0x18000a7cd  jb      short loc_18000A7EC
0x18000a7cf  cmp     rcx, rdx
0x18000a7d2  jz      short loc_18000A7EC
0x18000a7d4  mov     rdi, [rcx+28h]
0x18000a7d8  mov     [rbp+arg_10], rdi
0x18000a7dc  mov     [rcx+28h], r14
0x18000a7e0  lea     rdx, [rbp+arg_8]
0x18000a7e4  mov     rcx, rsi
0x18000a7e7  call    ?erase@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBK@Z; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::erase(ulong const &)
0x18000a7ec  test    rbx, rbx
0x18000a7ef  jz      loc_18000A9AE
0x18000a7f5  mov     rcx, rbx; _Mtx_t
0x18000a7f8  call    cs:__imp__Mtx_unlock
0x18000a7fe  mov     [rbp+var_38], r14b
0x18000a802  mov     ecx, 28h ; '('; Size
0x18000a807  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a80c  mov     [rbp+hMem], rax
0x18000a810  mov     edx, [rbp+arg_8]; unsigned int
0x18000a813  mov     rcx, rax; this
0x18000a816  call    ??0HookMgr@DialogBlocking@Internal@Windows@@QEAA@K@Z; Windows::Internal::DialogBlocking::HookMgr::HookMgr(ulong)
0x18000a81b  mov     r13, rax
0x18000a81e  mov     [rbp+phToken], rax
0x18000a822  mov     rcx, rax; this
0x18000a825  call    ?AttachHooks@HookMgr@DialogBlocking@Internal@Windows@@QEAAXXZ; Windows::Internal::DialogBlocking::HookMgr::AttachHooks(void)
0x18000a82a  mov     rcx, rbx; _Mtx_t
0x18000a82d  call    cs:__imp__Mtx_lock
0x18000a833  test    eax, eax
0x18000a835  jz      short loc_18000A843
0x18000a837  mov     ecx, 5
0x18000a83c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a842  int     3; Trap to Debugger
0x18000a843  mov     eax, [rbx+4Ch]
0x18000a846  cmp     eax, r15d
0x18000a849  jnz     short loc_18000A85C
0x18000a84b  dec     eax
0x18000a84d  mov     [rbx+4Ch], eax
0x18000a850  mov     ecx, 6
0x18000a855  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000a85b  int     3; Trap to Debugger
0x18000a85c  mov     [rbp+var_38], 1
0x18000a860  mov     r15, [rsi]
0x18000a863  mov     r12, [r15+8]
0x18000a867  xor     eax, eax
0x18000a869  mov     [rbp+hMem], rax
0x18000a86d  mov     rcx, r15
0x18000a870  mov     rax, r12
0x18000a873  mov     edx, [rbp+arg_8]
0x18000a876  cmp     byte ptr [r12+19h], 0
0x18000a87c  jnz     short loc_18000A8A1
0x18000a87e  mov     r12, rax
0x18000a881  cmp     [rax+20h], edx
0x18000a884  jnb     short loc_18000A88F
0x18000a886  xor     r14d, r14d
0x18000a889  mov     rax, [rax+10h]
0x18000a88d  jmp     short loc_18000A89B
0x18000a88f  mov     r14d, 1
0x18000a895  mov     rcx, rax
0x18000a898  mov     rax, [rax]
0x18000a89b  cmp     byte ptr [rax+19h], 0
0x18000a89f  jz      short loc_18000A87E
0x18000a8a1  cmp     byte ptr [rcx+19h], 0
0x18000a8a5  jnz     short loc_18000A8AC
0x18000a8a7  cmp     edx, [rcx+20h]
0x18000a8aa  jnb     short loc_18000A917
0x18000a8ac  mov     rax, 555555555555555h
0x18000a8b6  cmp     [rsi+8], rax
0x18000a8ba  jz      loc_18000A9B9
0x18000a8c0  mov     [rbp+var_20], rsi
0x18000a8c4  mov     qword ptr [rbp-18h], 0
0x18000a8cc  mov     ecx, 30h ; '0'; Size
0x18000a8d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a8d6  nop
0x18000a8d7  mov     ecx, [rbp+arg_8]
0x18000a8da  mov     [rax+20h], ecx
0x18000a8dd  mov     qword ptr [rax+28h], 0
0x18000a8e5  mov     [rax], r15
0x18000a8e8  mov     [rax+8], r15
0x18000a8ec  mov     [rax+10h], r15
0x18000a8f0  mov     word ptr [rax+18h], 0
0x18000a8f6  mov     [rbp+phToken], r12
0x18000a8fa  mov     [rbp+var_28], r14d
0x18000a8fe  mov     rcx, [rbp+hMem]
0x18000a902  mov     [rbp+var_24], ecx
0x18000a905  mov     r8, rax
0x18000a908  lea     rdx, [rbp+phToken]
0x18000a90c  mov     rcx, rsi
0x18000a90f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *> *>,std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *> * const)
0x18000a914  mov     rcx, rax
0x18000a917  mov     rsi, [rcx+28h]
0x18000a91b  mov     [rcx+28h], r13
0x18000a91f  test    rsi, rsi
0x18000a922  jz      short loc_18000A939
0x18000a924  mov     rcx, rsi; this
0x18000a927  call    ??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)
0x18000a92c  mov     edx, 28h ; '('; unsigned __int64
0x18000a931  mov     rcx, rsi; void *
0x18000a934  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a939  mov     rcx, rbx; _Mtx_t
0x18000a93c  call    cs:__imp__Mtx_unlock
0x18000a942  nop
0x18000a943  test    rdi, rdi
0x18000a946  jz      short loc_18000A996
0x18000a948  mov     rcx, rdi; this
0x18000a94b  call    ??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)
0x18000a950  mov     edx, 28h ; '('; unsigned __int64
0x18000a955  mov     rcx, rdi; void *
0x18000a958  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a95d  jmp     short loc_18000A996
0x18000a95f  mov     rcx, [rbp+Block]; Block
0x18000a963  mov     [rbp+Block], r14
0x18000a967  test    rcx, rcx
0x18000a96a  jz      short loc_18000A972
0x18000a96c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a971  nop
0x18000a972  mov     rcx, [rbp+hMem]; hMem
0x18000a976  test    rcx, rcx
0x18000a979  jz      short loc_18000A982
0x18000a97b  call    cs:__imp_LocalFree
0x18000a981  nop
0x18000a982  mov     rcx, [rbp+phToken]; hObject
0x18000a986  lea     rax, [rcx-1]
0x18000a98a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a98e  ja      short loc_18000A996
0x18000a990  call    cs:__imp_CloseHandle
0x18000a996  mov     rbx, [rsp+60h+arg_0]
0x18000a99e  add     rsp, 60h
0x18000a9a2  pop     r15
0x18000a9a4  pop     r14
0x18000a9a6  pop     r13
0x18000a9a8  pop     r12
0x18000a9aa  pop     rdi
0x18000a9ab  pop     rsi
0x18000a9ac  pop     rbp
0x18000a9ad  retn
0x18000a9ae  mov     ecx, 1
0x18000a9b3  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x18000a9b9  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
