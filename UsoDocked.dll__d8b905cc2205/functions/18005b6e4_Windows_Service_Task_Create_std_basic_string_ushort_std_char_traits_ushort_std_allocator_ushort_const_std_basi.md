# Windows::Service::Task::Create(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005b6e4`
- end: `0x18005bb1f`
- name: `?Create@Task@Service@Windows@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `1083`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x18005c8f0`

## callees

- `0x1800209fc`
- `0x180023a34`
- `0x180023ac4`
- `0x18005afc0`
- `0x18005b6e4`
- `0x18005e98c`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005b8b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b90f`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b8b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b90f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b8f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b94e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b9e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b9f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ba2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b8f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b94e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b9e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005b9f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ba2e`

## string_xrefs

- `0x18005bae6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005bb0d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005bad4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005ba56`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005ba6b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005ba80`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005ba95`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005baaa`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005babf`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005bafb`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Windows::Service::Task::Create(__int64 a1, __int64 a2, OLECHAR *a3, const OLECHAR *a4)
{
  PCNZWCH *v7; // rdx
  __int64 v8; // rax
  int v9; // eax
  const OLECHAR *v10; // rdi
  OLECHAR **v11; // rdx
  const OLECHAR *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 *v21; // rsi
  __int64 v22; // r14
  BSTR v23; // rax
  const char *v24; // r9
  OLECHAR *v25; // rdi
  int v26; // eax
  __int64 *v27; // rdi
  __int64 v28; // rsi
  BSTR v29; // rax
  const char *v30; // r9
  OLECHAR *v31; // rbx
  int v32; // eax
  __int64 v33; // r9
  BSTR v35; // [rsp+28h] [rbp-58h] BYREF
  __int64 *v36; // [rsp+30h] [rbp-50h] BYREF
  __int64 v37; // [rsp+38h] [rbp-48h] BYREF
  __int64 *v38; // [rsp+40h] [rbp-40h] BYREF
  __int64 v39; // [rsp+48h] [rbp-38h] BYREF
  int v40[2]; // [rsp+50h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-28h] BYREF
  BSTR v42; // [rsp+60h] [rbp-20h] BYREF
  BSTR v43[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  OLECHAR *v45; // [rsp+C0h] [rbp+40h] BYREF

  v45 = a3;
  v7 = &Windows::Service::Task::c_taskFolder;
  if ( (unsigned __int64)qword_180097688 > 7 )
    v7 = (PCNZWCH *)Windows::Service::Task::c_taskFolder;
  wil::make_bstr(v43, v7);
  v43[1] = 0;
  Windows::Service::Task::TaskService((int)v40);
  v45 = 0;
  v8 = **(_QWORD **)v40;
  v45 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, OLECHAR **))(v8 + 72))(*(_QWORD *)v40, 0, &v45);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v9,
      0);
  v10 = (const OLECHAR *)&Windows::Service::Task::c_usoclientExePath;
  v11 = &Windows::Service::Task::c_usoclientExePath;
  if ( (unsigned __int64)qword_1800975C8 > 7 )
    v11 = (OLECHAR **)Windows::Service::Task::c_usoclientExePath;
  wil::make_bstr(&v42, v11);
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v12 = a4;
  else
    v12 = *(const OLECHAR **)a4;
  wil::make_bstr(&bstrString, v12);
  v39 = 0;
  v13 = *(_QWORD *)v45;
  v39 = 0;
  v14 = (*(__int64 (__fastcall **)(OLECHAR *, __int64 *))(v13 + 88))(v45, &v39);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v14,
      0);
  v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 176LL))(v39, 0xFFFFFFFFLL);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v15,
      0);
  v38 = 0;
  v16 = *(_QWORD *)v45;
  v38 = 0;
  v17 = (*(__int64 (__fastcall **)(OLECHAR *, __int64 **))(v16 + 136))(v45, &v38);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v17,
      0);
  v37 = 0;
  v18 = *v38;
  v37 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v18 + 96))(v38, 0, &v37);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v19,
      0);
  v36 = 0;
  v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v37)(
          v37,
          &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
          &v36);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v20,
      0);
  v21 = v36;
  v22 = *v36;
  if ( (unsigned __int64)qword_1800975C8 > 7 )
    v10 = Windows::Service::Task::c_usoclientExePath;
  v23 = SysAllocString(v10);
  v25 = v23;
  v35 = v23;
  if ( !v23 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v24);
  v26 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v22 + 88))(v21, v23);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v26,
      48);
  SysFreeString(v25);
  v27 = v36;
  v28 = *v36;
  if ( *((_QWORD *)a4 + 3) > 7u )
    a4 = *(const OLECHAR **)a4;
  v29 = SysAllocString(a4);
  v31 = v29;
  v35 = v29;
  if ( !v29 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v30);
  v32 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v28 + 104))(v27, v29);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v32,
      80);
  SysFreeString(v31);
  v35 = v45;
  if ( v45 )
    (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v45 + 8LL))(v45);
  LOBYTE(v33) = 1;
  ((void (__fastcall *)(__int64, __int64, BSTR *, __int64, int))Windows::Service::Task::Task)(a1, a2, &v35, v33, 80);
  if ( v36 )
    (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v38 )
    (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v42 )
    SysFreeString(v42);
  if ( v45 )
    (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v45 + 16LL))(v45);
  if ( *(_QWORD *)v40 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
  if ( v43[0] )
    SysFreeString(v43[0]);
  return a1;
}

```

## disassembly

```asm
0x18005b6e4  mov     [rsp-28h+arg_0], rbx
0x18005b6e9  mov     [rsp-28h+arg_8], rsi
0x18005b6ee  mov     [rsp-28h+arg_10], r8
0x18005b6f3  push    rbp
0x18005b6f4  push    rdi
0x18005b6f5  push    r12
0x18005b6f7  push    r14
0x18005b6f9  push    r15
0x18005b6fb  mov     rbp, rsp
0x18005b6fe  sub     rsp, 80h
0x18005b705  mov     rbx, r9
0x18005b708  mov     r12, rdx
0x18005b70b  mov     r15, rcx
0x18005b70e  mov     [rbp+var_60], 0
0x18005b715  lea     rdx, ?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005b71c  cmp     cs:qword_180097688, 7
0x18005b724  cmova   rdx, cs:?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005b72c  lea     rcx, [rbp+var_18]
0x18005b730  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005b735  nop
0x18005b736  mov     [rbp+var_10], 0
0x18005b73e  lea     rcx, [rbp+var_30]; int
0x18005b742  call    ?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::TaskService(void)
0x18005b747  nop
0x18005b748  mov     [rbp+arg_10], 0
0x18005b750  mov     rcx, qword ptr [rbp+var_30]
0x18005b754  mov     rax, [rcx]
0x18005b757  mov     [rbp+arg_10], 0
0x18005b75f  lea     r8, [rbp+arg_10]
0x18005b763  xor     edx, edx
0x18005b765  mov     rax, [rax+48h]
0x18005b769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b76e  mov     rcx, [rbp+28h]; this
0x18005b772  test    eax, eax
0x18005b774  js      loc_18005BA68
0x18005b77a  lea     rdi, ?c_usoclientExePath@Task@Service@Windows@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_usoclientExePath
0x18005b781  mov     rdx, rdi
0x18005b784  cmp     cs:qword_1800975C8, 7
0x18005b78c  cmova   rdx, cs:?c_usoclientExePath@Task@Service@Windows@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_usoclientExePath
0x18005b794  lea     rcx, [rbp+var_20]
0x18005b798  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005b79d  nop
0x18005b79e  cmp     qword ptr [rbx+18h], 7
0x18005b7a3  jbe     short loc_18005B7AA
0x18005b7a5  mov     rdx, [rbx]
0x18005b7a8  jmp     short loc_18005B7AD
0x18005b7aa  mov     rdx, rbx
0x18005b7ad  lea     rcx, [rbp+bstrString]
0x18005b7b1  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005b7b6  nop
0x18005b7b7  mov     [rbp+var_38], 0
0x18005b7bf  mov     rcx, [rbp+arg_10]
0x18005b7c3  mov     rax, [rcx]
0x18005b7c6  mov     [rbp+var_38], 0
0x18005b7ce  lea     rdx, [rbp+var_38]
0x18005b7d2  mov     rax, [rax+58h]
0x18005b7d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b7db  mov     rcx, [rbp+28h]; this
0x18005b7df  test    eax, eax
0x18005b7e1  js      loc_18005BA7D
0x18005b7e7  mov     rcx, [rbp+var_38]
0x18005b7eb  mov     rax, [rcx]
0x18005b7ee  or      edx, 0FFFFFFFFh
0x18005b7f1  mov     rax, [rax+0B0h]
0x18005b7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b7fd  mov     rcx, [rbp+28h]; this
0x18005b801  test    eax, eax
0x18005b803  js      loc_18005BA92
0x18005b809  mov     [rbp+var_40], 0
0x18005b811  mov     rcx, [rbp+arg_10]
0x18005b815  mov     rax, [rcx]
0x18005b818  mov     [rbp+var_40], 0
0x18005b820  lea     rdx, [rbp+var_40]
0x18005b824  mov     rax, [rax+88h]
0x18005b82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b830  mov     rcx, [rbp+28h]; this
0x18005b834  test    eax, eax
0x18005b836  js      loc_18005BAA7
0x18005b83c  mov     [rbp+var_48], 0
0x18005b844  mov     rcx, [rbp+var_40]
0x18005b848  mov     rax, [rcx]
0x18005b84b  mov     [rbp+var_48], 0
0x18005b853  lea     r8, [rbp+var_48]
0x18005b857  xor     edx, edx
0x18005b859  mov     rax, [rax+60h]
0x18005b85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b862  mov     rcx, [rbp+28h]; this
0x18005b866  test    eax, eax
0x18005b868  js      loc_18005BABC
0x18005b86e  mov     rcx, [rbp+var_48]
0x18005b872  mov     [rbp+var_50], 0
0x18005b87a  mov     rax, [rcx]
0x18005b87d  lea     r8, [rbp+var_50]
0x18005b881  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x18005b888  mov     rax, [rax]
0x18005b88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b890  mov     rcx, [rbp+28h]; this
0x18005b894  test    eax, eax
0x18005b896  js      loc_18005BAD1
0x18005b89c  mov     rsi, [rbp+var_50]
0x18005b8a0  mov     r14, [rsi]
0x18005b8a3  cmp     cs:qword_1800975C8, 7
0x18005b8ab  cmova   rdi, cs:?c_usoclientExePath@Task@Service@Windows@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_usoclientExePath
0x18005b8b3  mov     rcx, rdi; psz
0x18005b8b6  call    cs:__imp_SysAllocString
0x18005b8bc  mov     rdi, rax
0x18005b8bf  mov     [rbp+var_58], rax
0x18005b8c3  mov     [rbp+var_60], 30h ; '0'
0x18005b8ca  mov     rcx, [rbp+28h]; this
0x18005b8ce  test    rax, rax
0x18005b8d1  jz      loc_18005BAE6
0x18005b8d7  mov     rdx, rax
0x18005b8da  mov     rcx, rsi
0x18005b8dd  mov     rax, [r14+58h]
0x18005b8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8e6  mov     rcx, [rbp+28h]; this
0x18005b8ea  test    eax, eax
0x18005b8ec  js      loc_18005BAF8
0x18005b8f2  mov     rcx, rdi; bstrString
0x18005b8f5  call    cs:__imp_SysFreeString
0x18005b8fb  mov     rdi, [rbp+var_50]
0x18005b8ff  mov     rsi, [rdi]
0x18005b902  cmp     qword ptr [rbx+18h], 7
0x18005b907  jbe     short loc_18005B90C
0x18005b909  mov     rbx, [rbx]
0x18005b90c  mov     rcx, rbx; psz
0x18005b90f  call    cs:__imp_SysAllocString
0x18005b915  mov     rbx, rax
0x18005b918  mov     [rbp+var_58], rax
0x18005b91c  mov     [rbp+var_60], 50h ; 'P'
0x18005b923  mov     rcx, [rbp+28h]; this
0x18005b927  test    rax, rax
0x18005b92a  jz      loc_18005BB0D
0x18005b930  mov     rdx, rax
0x18005b933  mov     rcx, rdi
0x18005b936  mov     rax, [rsi+68h]
0x18005b93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b93f  mov     rcx, [rbp+28h]; this
0x18005b943  test    eax, eax
0x18005b945  js      loc_18005BA53
0x18005b94b  mov     rcx, rbx; bstrString
0x18005b94e  call    cs:__imp_SysFreeString
0x18005b954  mov     rcx, [rbp+arg_10]
0x18005b958  mov     [rbp+var_58], rcx
0x18005b95c  test    rcx, rcx
0x18005b95f  jz      short loc_18005B96E
0x18005b961  mov     rax, [rcx]
0x18005b964  mov     rax, [rax+8]
0x18005b968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b96d  nop
0x18005b96e  mov     r9b, 1
0x18005b971  lea     r8, [rbp+var_58]
0x18005b975  mov     rdx, r12
0x18005b978  mov     rcx, r15
0x18005b97b  call    ??0Task@Service@Windows@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UITaskDefinition@@Uerr_exception_policy@wil@@@wil@@_N@Z; Windows::Service::Task::Task(std::wstring const &,wil::com_ptr_t<ITaskDefinition,wil::err_exception_policy>,bool)
0x18005b980  nop
0x18005b981  mov     rcx, [rbp+var_50]
0x18005b985  test    rcx, rcx
0x18005b988  jz      short loc_18005B997
0x18005b98a  mov     rax, [rcx]
0x18005b98d  mov     rax, [rax+10h]
0x18005b991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b996  nop
0x18005b997  mov     rcx, [rbp+var_48]
0x18005b99b  test    rcx, rcx
0x18005b99e  jz      short loc_18005B9AD
0x18005b9a0  mov     rax, [rcx]
0x18005b9a3  mov     rax, [rax+10h]
0x18005b9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9ac  nop
0x18005b9ad  mov     rcx, [rbp+var_40]
0x18005b9b1  test    rcx, rcx
0x18005b9b4  jz      short loc_18005B9C3
0x18005b9b6  mov     rax, [rcx]
0x18005b9b9  mov     rax, [rax+10h]
0x18005b9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9c2  nop
0x18005b9c3  mov     rcx, [rbp+var_38]
0x18005b9c7  test    rcx, rcx
0x18005b9ca  jz      short loc_18005B9D9
0x18005b9cc  mov     rax, [rcx]
0x18005b9cf  mov     rax, [rax+10h]
0x18005b9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9d8  nop
0x18005b9d9  mov     rcx, [rbp+bstrString]; bstrString
0x18005b9dd  test    rcx, rcx
0x18005b9e0  jz      short loc_18005B9E9
0x18005b9e2  call    cs:__imp_SysFreeString
0x18005b9e8  nop
0x18005b9e9  mov     rcx, [rbp+var_20]; bstrString
0x18005b9ed  test    rcx, rcx
0x18005b9f0  jz      short loc_18005B9F9
0x18005b9f2  call    cs:__imp_SysFreeString
0x18005b9f8  nop
0x18005b9f9  mov     rcx, [rbp+arg_10]
0x18005b9fd  test    rcx, rcx
0x18005ba00  jz      short loc_18005BA0F
0x18005ba02  mov     rax, [rcx]
0x18005ba05  mov     rax, [rax+10h]
0x18005ba09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba0e  nop
0x18005ba0f  mov     rcx, qword ptr [rbp+var_30]
0x18005ba13  test    rcx, rcx
0x18005ba16  jz      short loc_18005BA25
0x18005ba18  mov     rax, [rcx]
0x18005ba1b  mov     rax, [rax+10h]
0x18005ba1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba24  nop
0x18005ba25  mov     rcx, [rbp+var_18]; bstrString
0x18005ba29  test    rcx, rcx
0x18005ba2c  jz      short loc_18005BA34
0x18005ba2e  call    cs:__imp_SysFreeString
0x18005ba34  mov     rax, r15
0x18005ba37  lea     r11, [rsp+80h+var_s0]
0x18005ba3f  mov     rbx, [r11+30h]
0x18005ba43  mov     rsi, [r11+38h]
0x18005ba47  mov     rsp, r11
0x18005ba4a  pop     r15
0x18005ba4c  pop     r14
0x18005ba4e  pop     r12
0x18005ba50  pop     rdi
0x18005ba51  pop     rbp
0x18005ba52  retn
0x18005ba53  mov     r9d, eax; char *
0x18005ba56  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005ba5d  mov     edx, 1BAh; void *
0x18005ba62  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ba68  mov     r9d, eax; char *
0x18005ba6b  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005ba72  mov     edx, 1A6h; void *
0x18005ba77  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ba7d  mov     r9d, eax; char *
0x18005ba80  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005ba87  mov     edx, 1ADh; void *
0x18005ba8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ba92  mov     r9d, eax; char *
0x18005ba95  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005ba9c  mov     edx, 1AEh; void *
0x18005baa1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005baa7  mov     r9d, eax; char *
0x18005baaa  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005bab1  mov     edx, 1B1h; void *
0x18005bab6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005babc  mov     r9d, eax; char *
0x18005babf  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005bac6  mov     edx, 1B4h; void *
0x18005bacb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005bad1  mov     r9d, eax; char *
0x18005bad4  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005badb  mov     edx, 1CBEh; void *
0x18005bae0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005bae6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005baed  mov     edx, 15F3h; void *
0x18005baf2  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005baf8  mov     r9d, eax; char *
0x18005bafb  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005bb02  mov     edx, 1B8h; void *
0x18005bb07  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005bb0d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005bb14  mov     edx, 15F3h; void *
0x18005bb19  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
