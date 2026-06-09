# ProcessConnection::Initialize(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,IProcessConnectionCallback *)

- ea: `0x18004e870`
- end: `0x18004ebae`
- name: `?Initialize@ProcessConnection@@IEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAVIProcessConnectionCallback@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004e5cc`
- `0x18004f2bc`

## callees

- `0x180002520`
- `0x180002ee8`
- `0x1800050cd`
- `0x18000a444`
- `0x180010148`
- `0x18004e130`
- `0x18004e870`
- `0x18004f080`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e8c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e8c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eac3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e8d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ead6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e8d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ead6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004e8e3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004e8e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e8cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e8cc`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18004e903`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18004e903`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18004eaa1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18004eaa1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18004eace`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18004eace`

## string_xrefs

- `0x18004e914`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\processconnection.cpp`
- `0x18004eafe`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\processconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProcessConnection::Initialize(_QWORD *Context, void **a2, __int64 a3)
{
  HANDLE *v5; // r14
  void *v6; // r12
  HANDLE v7; // r15
  DWORD LastError; // ebx
  __int64 v9; // r8
  const char *v10; // r9
  char **v12; // rcx
  unsigned __int64 v13; // rdx
  char *v14; // rdi
  __int64 v15; // rbx
  char *v16; // rdi
  _QWORD *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  volatile signed __int32 *v20; // rcx
  __int64 v21; // rcx
  volatile signed __int32 *v22; // rbx
  __int64 v23; // rcx
  BOOL v24; // r13d
  void *v25; // r12
  void **v26; // r14
  void *v27; // r15
  DWORD v28; // ebx
  const char *v29; // r9
  unsigned int v30; // ebx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  char *v32; // [rsp+38h] [rbp-C8h] BYREF
  void **v33; // [rsp+40h] [rbp-C0h] BYREF
  void *phNewWaitObject; // [rsp+48h] [rbp-B8h] BYREF
  char v35; // [rsp+50h] [rbp-B0h]
  char *v36; // [rsp+58h] [rbp-A8h]
  char *v37; // [rsp+60h] [rbp-A0h]
  WCHAR ExeName[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  Context[10] = a3;
  v5 = (HANDLE *)(Context + 3);
  if ( Context + 3 != a2 )
  {
    v6 = *a2;
    v7 = *v5;
    if ( *v5 )
    {
      LastError = GetLastError();
      CloseHandle(v7);
      SetLastError(LastError);
    }
    *v5 = v6;
    *a2 = 0;
  }
  *((_DWORD *)Context + 16) = GetProcessId(*v5);
  dwSize = 260;
  if ( !QueryFullProcessImageNameW(*v5, 0, ExeName, &dwSize) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x35,
             (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\processconnection.cpp",
             v10);
  v12 = (char **)(Context + 4);
  v13 = -1;
  do
    ++v13;
  while ( ExeName[v13] );
  if ( v13 > Context[7] )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v12,
      v13,
      v9,
      ExeName);
  }
  else
  {
    if ( Context[7] <= 7u )
      v14 = (char *)(Context + 4);
    else
      v14 = *v12;
    Context[6] = v13;
    v15 = 2 * v13;
    memmove_0(v14, ExeName, 2 * v13);
    *(_WORD *)&v14[v15] = 0;
  }
  v16 = (char *)operator new(0x20u);
  v32 = v16;
  *(_OWORD *)v16 = 0;
  *((_DWORD *)v16 + 2) = 1;
  *((_DWORD *)v16 + 3) = 1;
  *(_QWORD *)v16 = &std::_Ref_count_obj2<ProcessConnection::ProcessExitCallbackContext>::`vftable';
  v17 = v16 + 16;
  *((_QWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 3) = 0;
  v36 = v16 + 16;
  v37 = v16;
  v18 = Context[2];
  if ( v18 )
  {
    v19 = Context[1];
    _InterlockedAdd((volatile signed __int32 *)(v18 + 12), 1u);
  }
  else
  {
    v18 = 0;
    v19 = 0;
  }
  *v17 = v19;
  v20 = (volatile signed __int32 *)*((_QWORD *)v16 + 3);
  *((_QWORD *)v16 + 3) = v18;
  if ( v20 && _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
  v32 = (char *)Context;
  v21 = *(_QWORD *)std::_Hash<std::_Umap_traits<void *,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>,0>>::_Try_emplace<void *,>(
                     (__int64)v20,
                     (__int64)&v33,
                     (__int64 *)&v32);
  _InterlockedAdd((volatile signed __int32 *)v16 + 2, 1u);
  *(_QWORD *)(v21 + 24) = v17;
  v22 = *(volatile signed __int32 **)(v21 + 32);
  *(_QWORD *)(v21 + 32) = v16;
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  v33 = (void **)(Context + 9);
  phNewWaitObject = 0;
  v35 = 1;
  v24 = RegisterWaitForSingleObject(
          &phNewWaitObject,
          *v5,
          ProcessConnection::ProcessExitCallback_NoLock,
          Context,
          0xFFFFFFFF,
          8u);
  if ( v35 )
  {
    v25 = phNewWaitObject;
    v26 = v33;
    v27 = *v33;
    if ( *v33 )
    {
      v28 = GetLastError();
      UnregisterWait(v27);
      SetLastError(v28);
    }
    *v26 = v25;
  }
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v16)(v16);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    return 0;
  }
  else
  {
    v32 = (char *)Context;
    std::_Hash<std::_Umap_traits<void *,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>,0>>::erase(
      v23,
      &v32);
    v30 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x50,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\processconnection.cpp",
            v29);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v16)(v16);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
    }
    return v30;
  }
}

```

## disassembly

```asm
0x18004e870  mov     [rsp-8+arg_10], rbx
0x18004e875  push    rbp
0x18004e876  push    rsi
0x18004e877  push    rdi
0x18004e878  push    r12
0x18004e87a  push    r13
0x18004e87c  push    r14
0x18004e87e  push    r15
0x18004e880  lea     rbp, [rsp-190h]
0x18004e888  sub     rsp, 290h
0x18004e88f  mov     rax, cs:__security_cookie
0x18004e896  xor     rax, rsp
0x18004e899  mov     [rbp+1C0h+var_40], rax
0x18004e8a0  mov     rdi, rdx
0x18004e8a3  mov     rsi, rcx
0x18004e8a6  xor     r13d, r13d
0x18004e8a9  mov     [rcx+50h], r8
0x18004e8ad  lea     r14, [rcx+18h]
0x18004e8b1  cmp     r14, rdx
0x18004e8b4  jz      short loc_18004E8E0
0x18004e8b6  mov     r12, [rdx]
0x18004e8b9  mov     r15, [r14]
0x18004e8bc  test    r15, r15
0x18004e8bf  jz      short loc_18004E8DA
0x18004e8c1  call    cs:__imp_GetLastError
0x18004e8c7  mov     ebx, eax
0x18004e8c9  mov     rcx, r15; hObject
0x18004e8cc  call    cs:__imp_CloseHandle
0x18004e8d2  mov     ecx, ebx; dwErrCode
0x18004e8d4  call    cs:__imp_SetLastError
0x18004e8da  mov     [r14], r12
0x18004e8dd  mov     [rdi], r13
0x18004e8e0  mov     rcx, [r14]; Process
0x18004e8e3  call    cs:__imp_GetProcessId
0x18004e8e9  mov     [rsi+40h], eax
0x18004e8ec  mov     [rsp+2C0h+dwSize], 104h
0x18004e8f4  lea     r9, [rsp+2C0h+dwSize]; lpdwSize
0x18004e8f9  lea     r8, [rsp+2C0h+ExeName]; lpExeName
0x18004e8fe  xor     edx, edx; dwFlags
0x18004e900  mov     rcx, [r14]; hProcess
0x18004e903  call    cs:__imp_QueryFullProcessImageNameW
0x18004e909  test    eax, eax
0x18004e90b  jnz     short loc_18004E928
0x18004e90d  mov     rcx, [rbp+1C8h]; this
0x18004e914  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004e91b  lea     edx, [rax+35h]; void *
0x18004e91e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e923  jmp     loc_18004EB84
0x18004e928  lea     rcx, [rsi+20h]
0x18004e92c  lea     rax, [rsp+2C0h+ExeName]
0x18004e931  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004e935  mov     rdx, r15
0x18004e938  inc     rdx
0x18004e93b  cmp     [rax+rdx*2], r13w
0x18004e940  jnz     short loc_18004E938
0x18004e942  cmp     rdx, [rcx+18h]
0x18004e946  ja      short loc_18004E976
0x18004e948  cmp     qword ptr [rcx+18h], 7
0x18004e94d  jbe     short loc_18004E954
0x18004e94f  mov     rdi, [rcx]
0x18004e952  jmp     short loc_18004E957
0x18004e954  mov     rdi, rcx
0x18004e957  mov     [rcx+10h], rdx
0x18004e95b  lea     rbx, [rdx+rdx]
0x18004e95f  mov     r8, rbx; Size
0x18004e962  lea     rdx, [rsp+2C0h+ExeName]; Src
0x18004e967  mov     rcx, rdi; void *
0x18004e96a  call    memmove_0
0x18004e96f  mov     [rbx+rdi], r13w
0x18004e974  jmp     short loc_18004E980
0x18004e976  lea     r9, [rsp+2C0h+ExeName]
0x18004e97b  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x18004e980  mov     ecx, 20h ; ' '; Size
0x18004e985  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e98a  mov     rdi, rax
0x18004e98d  mov     [rsp+2C0h+var_288], rax
0x18004e992  xorps   xmm0, xmm0
0x18004e995  movups  xmmword ptr [rax], xmm0
0x18004e998  mov     r12d, 1
0x18004e99e  mov     [rax+8], r12d
0x18004e9a2  mov     [rax+0Ch], r12d
0x18004e9a6  lea     rax, ??_7?$_Ref_count_obj2@UProcessExitCallbackContext@ProcessConnection@@@std@@6B@; const std::_Ref_count_obj2<ProcessConnection::ProcessExitCallbackContext>::`vftable'
0x18004e9ad  mov     [rdi], rax
0x18004e9b0  lea     rbx, [rdi+10h]
0x18004e9b4  mov     [rbx], r13
0x18004e9b7  mov     [rbx+8], r13
0x18004e9bb  mov     [rsp+2C0h+var_268], rbx
0x18004e9c0  mov     [rsp+2C0h+var_260], rdi
0x18004e9c5  mov     rax, [rsi+10h]
0x18004e9c9  test    rax, rax
0x18004e9cc  jz      short loc_18004E9D9
0x18004e9ce  mov     rcx, [rsi+8]
0x18004e9d2  lock add [rax+0Ch], r12d
0x18004e9d7  jmp     short loc_18004E9DF
0x18004e9d9  mov     rax, r13
0x18004e9dc  mov     rcx, r13
0x18004e9df  mov     [rbx], rcx
0x18004e9e2  mov     rcx, [rbx+8]
0x18004e9e6  mov     [rbx+8], rax
0x18004e9ea  test    rcx, rcx
0x18004e9ed  jz      short loc_18004EA08
0x18004e9ef  mov     eax, r15d
0x18004e9f2  lock xadd [rcx+0Ch], eax
0x18004e9f7  add     eax, r15d
0x18004e9fa  jnz     short loc_18004EA08
0x18004e9fc  mov     rax, [rcx]
0x18004e9ff  mov     rax, [rax+8]
0x18004ea03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea08  mov     [rsp+2C0h+var_288], rsi
0x18004ea0d  lea     r8, [rsp+2C0h+var_288]
0x18004ea12  lea     rdx, [rsp+2C0h+var_280]
0x18004ea17  call    ??$_Try_emplace@PEAX$$V@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@PEAX@std@@_N@1@$$QEAPEAX@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>,0>>::_Try_emplace<void *,>(void * &&)
0x18004ea1c  mov     rcx, [rax]
0x18004ea1f  lock add [rdi+8], r12d
0x18004ea24  mov     [rcx+18h], rbx
0x18004ea28  mov     rbx, [rcx+20h]
0x18004ea2c  mov     [rcx+20h], rdi
0x18004ea30  test    rbx, rbx
0x18004ea33  jz      short loc_18004EA6C
0x18004ea35  mov     eax, r15d
0x18004ea38  lock xadd [rbx+8], eax
0x18004ea3d  add     eax, r15d
0x18004ea40  jnz     short loc_18004EA6C
0x18004ea42  mov     rax, [rbx]
0x18004ea45  mov     rcx, rbx
0x18004ea48  mov     rax, [rax]
0x18004ea4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea50  mov     eax, r15d
0x18004ea53  lock xadd [rbx+0Ch], eax
0x18004ea58  add     eax, r15d
0x18004ea5b  jnz     short loc_18004EA6C
0x18004ea5d  mov     rax, [rbx]
0x18004ea60  mov     rcx, rbx
0x18004ea63  mov     rax, [rax+8]
0x18004ea67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea6c  lea     rax, [rsi+48h]
0x18004ea70  mov     [rsp+2C0h+var_280], rax
0x18004ea75  mov     [rsp+2C0h+phNewWaitObject], r13
0x18004ea7a  mov     [rsp+2C0h+var_270], r12b
0x18004ea7f  mov     [rsp+2C0h+dwFlags], 8; dwFlags
0x18004ea87  mov     [rsp+2C0h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18004ea8f  mov     r9, rsi; Context
0x18004ea92  lea     r8, ?ProcessExitCallback_NoLock@ProcessConnection@@CAXPEAXE@Z; Callback
0x18004ea99  mov     rdx, [r14]; hObject
0x18004ea9c  lea     rcx, [rsp+2C0h+phNewWaitObject]; phNewWaitObject
0x18004eaa1  call    cs:__imp_RegisterWaitForSingleObject
0x18004eaa7  mov     r13d, eax
0x18004eaaa  cmp     [rsp+2C0h+var_270], 0
0x18004eaaf  jz      short loc_18004EAE3
0x18004eab1  mov     r12, [rsp+2C0h+phNewWaitObject]
0x18004eab6  mov     r14, [rsp+2C0h+var_280]
0x18004eabb  mov     r15, [r14]
0x18004eabe  test    r15, r15
0x18004eac1  jz      short loc_18004EADC
0x18004eac3  call    cs:__imp_GetLastError
0x18004eac9  mov     ebx, eax
0x18004eacb  mov     rcx, r15; WaitHandle
0x18004eace  call    cs:__imp_UnregisterWait
0x18004ead4  mov     ecx, ebx; dwErrCode
0x18004ead6  call    cs:__imp_SetLastError
0x18004eadc  mov     [r14], r12
0x18004eadf  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004eae3  test    r13d, r13d
0x18004eae6  jnz     short loc_18004EB4B
0x18004eae8  mov     [rsp+2C0h+var_288], rsi
0x18004eaed  lea     rdx, [rsp+2C0h+var_288]
0x18004eaf2  call    ?erase@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@UProcessExitCallbackContext@ProcessConnection@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBQEAX@Z; std::_Hash<std::_Umap_traits<void *,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<ProcessConnection::ProcessExitCallbackContext>>>,0>>::erase(void * const &)
0x18004eaf7  mov     rcx, [rbp+1C8h]; this
0x18004eafe  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004eb05  lea     edx, [r13+50h]; void *
0x18004eb09  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004eb0e  mov     ebx, eax
0x18004eb10  mov     ecx, r15d
0x18004eb13  lock xadd [rdi+8], ecx
0x18004eb18  add     ecx, r15d
0x18004eb1b  jnz     short loc_18004EB47
0x18004eb1d  mov     rcx, [rdi]
0x18004eb20  mov     rax, [rcx]
0x18004eb23  mov     rcx, rdi
0x18004eb26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb2b  mov     eax, r15d
0x18004eb2e  lock xadd [rdi+0Ch], eax
0x18004eb33  add     eax, r15d
0x18004eb36  jnz     short loc_18004EB47
0x18004eb38  mov     rax, [rdi]
0x18004eb3b  mov     rcx, rdi
0x18004eb3e  mov     rax, [rax+8]
0x18004eb42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb47  mov     eax, ebx
0x18004eb49  jmp     short loc_18004EB84
0x18004eb4b  mov     eax, r15d
0x18004eb4e  lock xadd [rdi+8], eax
0x18004eb53  add     eax, r15d
0x18004eb56  jnz     short loc_18004EB82
0x18004eb58  mov     rax, [rdi]
0x18004eb5b  mov     rcx, rdi
0x18004eb5e  mov     rax, [rax]
0x18004eb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb66  mov     eax, r15d
0x18004eb69  lock xadd [rdi+0Ch], eax
0x18004eb6e  add     eax, r15d
0x18004eb71  jnz     short loc_18004EB82
0x18004eb73  mov     rax, [rdi]
0x18004eb76  mov     rcx, rdi
0x18004eb79  mov     rax, [rax+8]
0x18004eb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb82  xor     eax, eax
0x18004eb84  mov     rcx, [rbp+1C0h+var_40]
0x18004eb8b  xor     rcx, rsp; StackCookie
0x18004eb8e  call    __security_check_cookie
0x18004eb93  mov     rbx, [rsp+2C0h+arg_10]
0x18004eb9b  add     rsp, 290h
0x18004eba2  pop     r15
0x18004eba4  pop     r14
0x18004eba6  pop     r13
0x18004eba8  pop     r12
0x18004ebaa  pop     rdi
0x18004ebab  pop     rsi
0x18004ebac  pop     rbp
0x18004ebad  retn
```
