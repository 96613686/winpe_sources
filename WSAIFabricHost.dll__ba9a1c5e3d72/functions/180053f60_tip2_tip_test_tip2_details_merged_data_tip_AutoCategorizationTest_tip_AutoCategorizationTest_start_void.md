# tip2::tip_test<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::start(void)

- ea: `0x180053f60`
- end: `0x1800541b0`
- name: `?start@?$tip_test@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ`
- size: `592`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f9e4`

## callees

- `0x180004ca0`
- `0x18002ff90`
- `0x180031950`
- `0x180053bb4`
- `0x180053f60`
- `0x180054cd8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180054128`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180054128`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180054111`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180054111`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005417d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005417d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054054`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800540e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800540e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054145`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054145`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005416f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053fd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005416f`

## string_xrefs

- `0x18005410a`: `kernelbase.dll`

## pseudocode

```c
_OWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::start(
        struct _RTL_CRITICAL_SECTION **a1,
        _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION **v5; // rax
  struct _RTL_CRITICAL_SECTION *v6; // rdx
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  int v11; // edx
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // r13
  __int64 v15; // r15
  DWORD LastError; // r14d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+49h] [rbp-B7h] BYREF
  char v24; // [rsp+4Dh] [rbp-B3h]
  char v25; // [rsp+4Eh] [rbp-B2h] BYREF
  char v26; // [rsp+849h] [rbp+749h] BYREF
  int *v27; // [rsp+850h] [rbp+750h]
  char *v28; // [rsp+858h] [rbp+758h]
  char *v29; // [rsp+860h] [rbp+760h]

  v4 = *a1;
  if ( *a1 && (*(_QWORD *)&v4[6].LockCount || (v4[1].SpinCount & 0x100) != 0) )
  {
    *a1 = 0;
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v4);
      CoTaskMemFree(v4);
    }
  }
  if ( !*a1 )
  {
    v5 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>,>(&pv);
    v6 = *v5;
    *v5 = 0;
    v7 = *a1;
    *a1 = v6;
    if ( v7 && _InterlockedExchangeAdd(&v7[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v7);
      CoTaskMemFree(v7);
    }
    v8 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v8);
      CoTaskMemFree(v8);
    }
  }
  v9 = *a1;
  v10 = *a1 + 5;
  EnterCriticalSection(v10);
  v21 = 0;
  v22 = 0;
  v27 = &v23;
  v29 = &v26;
  v23 = -2143256512;
  v24 = 0;
  v28 = &v25;
  if ( (v9[1].SpinCount & 0x800) != 0 )
    v13 = tip2::details::shared_data<0,0,0>::serialize_data(&v9->LockCount, &v21, 1);
  else
    v13 = 0;
  LOBYTE(v12) = v9[1].DebugInfo;
  v14 = TestCreate(v9->LockSemaphore, v11, v12, HIDWORD(v9->LockSemaphore), v13, (__int64)&v9[3].SpinCount);
  v15 = *(_QWORD *)&v9[6].LockCount;
  if ( v15 )
  {
    LastError = GetLastError();
    ProcAddress = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_21;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_21:
      ((void (__fastcall *)(__int64))ProcAddress)(v15);
    SetLastError(LastError);
  }
  *(_QWORD *)&v9[6].LockCount = v14;
  LODWORD(v9[4].SpinCount) = 1;
  *a2 = *(_OWORD *)&v9[3].SpinCount;
  if ( v21 )
    CoTaskMemFree(v21);
  if ( v10 )
    LeaveCriticalSection(v10);
  return a2;
}

```

## disassembly

```asm
0x180053f60  mov     [rsp-8+arg_10], rbx
0x180053f65  push    rbp
0x180053f66  push    rsi
0x180053f67  push    rdi
0x180053f68  push    r12
0x180053f6a  push    r13
0x180053f6c  push    r14
0x180053f6e  push    r15
0x180053f70  lea     rbp, [rsp-780h]
0x180053f78  sub     rsp, 880h
0x180053f7f  mov     rax, cs:__security_cookie
0x180053f86  xor     rax, rsp
0x180053f89  mov     [rbp+7B0h+var_40], rax
0x180053f90  mov     rsi, rdx
0x180053f93  mov     rdi, rcx
0x180053f96  mov     rbx, [rcx]
0x180053f99  or      r15d, 0FFFFFFFFh
0x180053f9d  xor     r14d, r14d
0x180053fa0  test    rbx, rbx
0x180053fa3  jz      short loc_180053FDB
0x180053fa5  cmp     [rbx+0F8h], r14
0x180053fac  jnz     short loc_180053FB7
0x180053fae  test    dword ptr [rbx+48h], 100h
0x180053fb5  jz      short loc_180053FDB
0x180053fb7  mov     [rcx], r14
0x180053fba  mov     eax, r15d
0x180053fbd  lock xadd [rbx+120h], eax
0x180053fc5  add     eax, r15d
0x180053fc8  jnz     short loc_180053FDB
0x180053fca  mov     rcx, rbx
0x180053fcd  call    ??1?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(void)
0x180053fd2  mov     rcx, rbx; pv
0x180053fd5  call    cs:__imp_CoTaskMemFree
0x180053fdb  cmp     [rdi], r14
0x180053fde  jnz     short loc_180054047
0x180053fe0  lea     rcx, [rsp+8B0h+pv]
0x180053fe5  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>,>(void)
0x180053fea  mov     rdx, [rax]
0x180053fed  mov     [rax], r14
0x180053ff0  mov     rbx, [rdi]
0x180053ff3  mov     [rdi], rdx
0x180053ff6  test    rbx, rbx
0x180053ff9  jz      short loc_18005401C
0x180053ffb  mov     eax, r15d
0x180053ffe  lock xadd [rbx+120h], eax
0x180054006  add     eax, r15d
0x180054009  jnz     short loc_18005401C
0x18005400b  mov     rcx, rbx
0x18005400e  call    ??1?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(void)
0x180054013  mov     rcx, rbx; pv
0x180054016  call    cs:__imp_CoTaskMemFree
0x18005401c  mov     rbx, [rsp+8B0h+pv]
0x180054021  test    rbx, rbx
0x180054024  jz      short loc_180054047
0x180054026  mov     eax, r15d
0x180054029  lock xadd [rbx+120h], eax
0x180054031  add     eax, r15d
0x180054034  jnz     short loc_180054047
0x180054036  mov     rcx, rbx
0x180054039  call    ??1?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(void)
0x18005403e  mov     rcx, rbx; pv
0x180054041  call    cs:__imp_CoTaskMemFree
0x180054047  mov     rbx, [rdi]
0x18005404a  lea     rdi, [rbx+0C8h]
0x180054051  mov     rcx, rdi; lpCriticalSection
0x180054054  call    cs:__imp_EnterCriticalSection
0x18005405a  mov     [rsp+8B0h+var_870], r14
0x18005405f  mov     [rsp+8B0h+var_868], r14b
0x180054064  lea     rax, [rsp+8B0h+var_867]
0x180054069  mov     [rbp+7B0h+var_60], rax
0x180054070  lea     rax, [rbp+7B0h+var_67]
0x180054077  mov     [rbp+7B0h+var_50], rax
0x18005407e  mov     [rsp+8B0h+var_867], 80408040h
0x180054086  mov     [rsp+8B0h+var_863], r14b
0x18005408b  lea     rax, [rsp+8B0h+var_862]
0x180054090  mov     [rbp+7B0h+var_58], rax
0x180054097  lea     r12, [rbx+98h]
0x18005409e  test    dword ptr [rbx+48h], 800h
0x1800540a5  jz      short loc_1800540BD
0x1800540a7  mov     r8d, 1
0x1800540ad  lea     rdx, [rsp+8B0h+var_870]
0x1800540b2  lea     rcx, [rbx+8]
0x1800540b6  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800540bb  jmp     short loc_1800540C0
0x1800540bd  mov     rax, r14
0x1800540c0  mov     [rsp+8B0h+var_888], r12
0x1800540c5  mov     [rsp+8B0h+var_890], rax
0x1800540ca  mov     r9d, [rbx+1Ch]
0x1800540ce  mov     r8b, [rbx+28h]
0x1800540d2  mov     ecx, [rbx+18h]
0x1800540d5  call    TestCreate
0x1800540da  mov     r13, rax
0x1800540dd  mov     r15, [rbx+0F8h]
0x1800540e4  test    r15, r15
0x1800540e7  jz      short loc_18005414B
0x1800540e9  call    cs:__imp_GetLastError
0x1800540ef  mov     r14d, eax
0x1800540f2  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x1800540f9  test    rax, rax
0x1800540fc  jnz     short loc_18005413A
0x1800540fe  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180054105  test    rax, rax
0x180054108  jnz     short loc_18005411E
0x18005410a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180054111  call    cs:__imp_GetModuleHandleW
0x180054117  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18005411e  lea     rdx, aTestclose; "TestClose"
0x180054125  mov     rcx, rax; hModule
0x180054128  call    cs:__imp_GetProcAddress
0x18005412e  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x180054135  test    rax, rax
0x180054138  jz      short loc_180054142
0x18005413a  mov     rcx, r15
0x18005413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054142  mov     ecx, r14d; dwErrCode
0x180054145  call    cs:__imp_SetLastError
0x18005414b  mov     [rbx+0F8h], r13
0x180054152  mov     dword ptr [rbx+0C0h], 1
0x18005415c  movups  xmm0, xmmword ptr [r12]
0x180054161  movdqu  xmmword ptr [rsi], xmm0
0x180054165  mov     rcx, [rsp+8B0h+var_870]; pv
0x18005416a  test    rcx, rcx
0x18005416d  jz      short loc_180054175
0x18005416f  call    cs:__imp_CoTaskMemFree
0x180054175  test    rdi, rdi
0x180054178  jz      short loc_180054183
0x18005417a  mov     rcx, rdi; lpCriticalSection
0x18005417d  call    cs:__imp_LeaveCriticalSection
0x180054183  mov     rax, rsi
0x180054186  mov     rcx, [rbp+7B0h+var_40]
0x18005418d  xor     rcx, rsp; StackCookie
0x180054190  call    __security_check_cookie
0x180054195  mov     rbx, [rsp+8B0h+arg_10]
0x18005419d  add     rsp, 880h
0x1800541a4  pop     r15
0x1800541a6  pop     r14
0x1800541a8  pop     r13
0x1800541aa  pop     r12
0x1800541ac  pop     rdi
0x1800541ad  pop     rsi
0x1800541ae  pop     rbp
0x1800541af  retn
```
