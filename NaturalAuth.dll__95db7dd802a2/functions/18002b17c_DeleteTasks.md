# DeleteTasks

- ea: `0x18002b17c`
- end: `0x18002b3b3`
- name: `DeleteTasks`
- size: `567`
- prototype: `__int64 __fastcall(__int64 ***)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029698`
- `0x1800297e8`
- `0x18002a584`
- `0x18002a978`

## callees

- `0x18000b5b0`
- `0x180014e7c`
- `0x18001f634`
- `0x18001fb2c`
- `0x18002072c`
- `0x180028fa0`
- `0x18002b17c`
- `0x18002be88`
- `0x18002ccac`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b1a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b1a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b21e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b21e`

## string_xrefs

- `0x18002b22a`: `CoCreateInstance(CLSID_TaskScheduler, NULL, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(&taskService))`
- `0x18002b29e`: `taskService->Connect({}, {}, {}, {})`
- `0x18002b301`: `taskService->GetFolder(_bstr_t(NA_TASK_FOLDER), &folder)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeleteTasks(__int64 ***a1)
{
  __int64 v2; // rcx
  __int64 **v3; // rsi
  __int64 **i; // rbx
  __int64 v5; // rcx
  HRESULT v6; // eax
  int v7; // ebx
  const char *v8; // rcx
  __int64 v9; // rdx
  LPVOID v10; // rbx
  __int64 (__fastcall *v11)(LPVOID, _QWORD *, __int64 *); // rsi
  _QWORD *v12; // rdx
  __int64 **v13; // rsi
  __int64 **j; // rbx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int128 v18; // [rsp+38h] [rbp-59h] BYREF
  __int64 v19; // [rsp+48h] [rbp-49h]
  __int128 v20; // [rsp+58h] [rbp-39h] BYREF
  __int64 v21; // [rsp+68h] [rbp-29h]
  __int128 v22; // [rsp+78h] [rbp-19h] BYREF
  __int64 v23; // [rsp+88h] [rbp-9h]
  __int128 v24; // [rsp+98h] [rbp+7h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+17h]
  LPVOID ppv; // [rsp+F8h] [rbp+67h] BYREF
  __int64 v27; // [rsp+100h] [rbp+6Fh] BYREF
  RTL_SRWLOCK *v28; // [rsp+108h] [rbp+77h] BYREF

  AcquireSRWLockExclusive(&stru_18005FCC8);
  v28 = &stru_18005FCC8;
  v3 = a1[1];
  for ( i = *a1; i != v3; ++i )
  {
    v18 = *(_OWORD *)std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Eqrange<_bstr_t>(
                       v2,
                       &v20,
                       i);
    std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Erase(
      v5,
      &v18);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v28);
  ppv = 0;
  v27 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "CoCreateInstance(CLSID_TaskScheduler, NULL, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(&taskService))";
LABEL_8:
    v9 = (unsigned int)v6;
LABEL_9:
    LogOpFailure(v8, v9);
    goto LABEL_27;
  }
  v20 = 0;
  v21 = 0;
  v18 = 0;
  v19 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v24,
         &v22,
         &v18,
         &v20);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = "taskService->Connect({}, {}, {}, {})";
    goto LABEL_8;
  }
  v10 = ppv;
  v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *))(*(_QWORD *)ppv + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v12 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v28, L"\\Microsoft\\Windows\\NaturalAuthentication");
  if ( v12 )
    v12 = (_QWORD *)*v12;
  v7 = v11(v10, v12, &v27);
  _bstr_t::_Free((_bstr_t *)&v28);
  if ( v7 < 0 )
  {
    v9 = (unsigned int)v7;
    v8 = "taskService->GetFolder(_bstr_t(NA_TASK_FOLDER), &folder)";
    goto LABEL_9;
  }
  v13 = a1[1];
  for ( j = *a1; j != v13; ++j )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( *j )
        v15 = **j;
      else
        v15 = 0;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids, v15);
    }
    if ( *j )
      v16 = **j;
    else
      v16 = 0;
    (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v27 + 120LL))(v27, v16, 0);
  }
  v7 = 0;
LABEL_27:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002b17c  mov     rax, rsp
0x18002b17f  mov     [rax+20h], rbx
0x18002b183  push    rbp
0x18002b184  push    rsi
0x18002b185  push    rdi
0x18002b186  lea     rbp, [rax-5Fh]
0x18002b18a  sub     rsp, 0D0h
0x18002b191  movaps  xmmword ptr [rax-28h], xmm6
0x18002b195  movaps  xmmword ptr [rax-38h], xmm7
0x18002b199  mov     rdi, rcx
0x18002b19c  lea     rbx, stru_18005FCC8
0x18002b1a3  mov     rcx, rbx; SRWLock
0x18002b1a6  call    cs:__imp_AcquireSRWLockExclusive
0x18002b1ac  mov     [rbp+57h+arg_10], rbx
0x18002b1b0  mov     rsi, [rdi+8]
0x18002b1b4  mov     rbx, [rdi]
0x18002b1b7  jmp     short loc_18002B1DA
0x18002b1b9  mov     r8, rbx
0x18002b1bc  lea     rdx, [rbp+57h+var_90]
0x18002b1c0  call    ??$_Eqrange@V_bstr_t@@@?$_Tree@V?$_Tmap_traits@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@std@@PEAU12@@1@AEBV_bstr_t@@@Z; std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Eqrange<_bstr_t>(_bstr_t const &)
0x18002b1c5  movups  xmm0, xmmword ptr [rax]
0x18002b1c8  movdqu  [rbp+57h+var_B0], xmm0
0x18002b1cd  lea     rdx, [rbp+57h+var_B0]
0x18002b1d1  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *> *,std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *> *>)
0x18002b1d6  add     rbx, 8
0x18002b1da  cmp     rbx, rsi
0x18002b1dd  jnz     short loc_18002B1B9
0x18002b1df  lea     rcx, [rbp+57h+arg_10]
0x18002b1e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b1e8  mov     [rbp+57h+arg_0], 0
0x18002b1f0  mov     [rbp+57h+arg_8], 0
0x18002b1f8  lea     rcx, [rbp+57h+arg_0]
0x18002b1fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b201  lea     rax, [rbp+57h+arg_0]
0x18002b205  mov     [rsp+0E0h+ppv], rax; ppv
0x18002b20a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18002b211  xor     edx, edx; pUnkOuter
0x18002b213  lea     r8d, [rdx+1]; dwClsContext
0x18002b217  lea     rcx, CLSID_TaskScheduler; rclsid
0x18002b21e  call    cs:__imp_CoCreateInstance
0x18002b224  mov     ebx, eax
0x18002b226  test    eax, eax
0x18002b228  jns     short loc_18002B233
0x18002b22a  lea     rcx, aCocreateinstan_0; "CoCreateInstance(CLSID_TaskScheduler, N"...
0x18002b231  jmp     short loc_18002B2A5
0x18002b233  mov     rcx, [rbp+57h+arg_0]
0x18002b237  xorps   xmm7, xmm7
0x18002b23a  xor     eax, eax
0x18002b23c  movq    xmm6, rax
0x18002b241  xorps   xmm5, xmm5
0x18002b244  movq    xmm4, rax
0x18002b249  xorps   xmm3, xmm3
0x18002b24c  movq    xmm2, rax
0x18002b251  xorps   xmm1, xmm1
0x18002b254  movaps  [rbp+57h+var_90], xmm7
0x18002b258  movsd   [rbp+57h+var_80], xmm6
0x18002b25d  movaps  [rbp+57h+var_B0], xmm5
0x18002b261  movsd   [rbp+57h+var_A0], xmm4
0x18002b266  movaps  [rbp+57h+var_70], xmm3
0x18002b26a  movsd   [rbp+57h+var_60], xmm2
0x18002b26f  movaps  [rbp+57h+var_50], xmm1
0x18002b273  mov     [rbp+57h+var_40], rax
0x18002b277  mov     rax, [rcx]
0x18002b27a  lea     rdx, [rbp+57h+var_90]
0x18002b27e  mov     [rsp+0E0h+ppv], rdx
0x18002b283  lea     r9, [rbp+57h+var_B0]
0x18002b287  lea     r8, [rbp+57h+var_70]
0x18002b28b  lea     rdx, [rbp+57h+var_50]
0x18002b28f  mov     rax, [rax+50h]
0x18002b293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b298  mov     ebx, eax
0x18002b29a  test    eax, eax
0x18002b29c  jns     short loc_18002B2B1
0x18002b29e  lea     rcx, aTaskserviceCon; "taskService->Connect({}, {}, {}, {})"
0x18002b2a5  mov     edx, eax
0x18002b2a7  call    LogOpFailure
0x18002b2ac  jmp     loc_18002B381
0x18002b2b1  mov     rbx, [rbp+57h+arg_0]
0x18002b2b5  mov     rax, [rbx]
0x18002b2b8  mov     rsi, [rax+38h]
0x18002b2bc  lea     rcx, [rbp+57h+arg_8]
0x18002b2c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b2c5  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\NaturalAuthentica"...
0x18002b2cc  lea     rcx, [rbp+57h+arg_10]; this
0x18002b2d0  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002b2d5  nop
0x18002b2d6  mov     rdx, [rax]
0x18002b2d9  test    rdx, rdx
0x18002b2dc  jz      short loc_18002B2E1
0x18002b2de  mov     rdx, [rdx]
0x18002b2e1  lea     r8, [rbp+57h+arg_8]
0x18002b2e5  mov     rcx, rbx
0x18002b2e8  mov     rax, rsi
0x18002b2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2f0  mov     ebx, eax
0x18002b2f2  lea     rcx, [rbp+57h+arg_10]; this
0x18002b2f6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002b2fb  test    ebx, ebx
0x18002b2fd  jns     short loc_18002B30A
0x18002b2ff  mov     edx, ebx
0x18002b301  lea     rcx, aTaskserviceGet; "taskService->GetFolder(_bstr_t(NA_TASK_"...
0x18002b308  jmp     short loc_18002B2A7
0x18002b30a  mov     rsi, [rdi+8]
0x18002b30e  mov     rbx, [rdi]
0x18002b311  jmp     short loc_18002B37A
0x18002b313  lea     rax, WPP_GLOBAL_Control
0x18002b31a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b321  cmp     rcx, rax
0x18002b324  jz      short loc_18002B351
0x18002b326  test    byte ptr [rcx+1Ch], 4
0x18002b32a  jz      short loc_18002B351
0x18002b32c  mov     rax, [rbx]
0x18002b32f  test    rax, rax
0x18002b332  jz      short loc_18002B339
0x18002b334  mov     r9, [rax]
0x18002b337  jmp     short loc_18002B33C
0x18002b339  xor     r9d, r9d
0x18002b33c  mov     edx, 1Ah
0x18002b341  lea     r8, WPP_590996888f423b0d9fe2c69d3835c5aa_Traceguids
0x18002b348  mov     rcx, [rcx+10h]
0x18002b34c  call    WPP_SF_S
0x18002b351  mov     rcx, [rbp+57h+arg_8]
0x18002b355  mov     rax, [rcx]
0x18002b358  mov     r9, [rax+78h]
0x18002b35c  mov     rax, [rbx]
0x18002b35f  test    rax, rax
0x18002b362  jz      short loc_18002B369
0x18002b364  mov     rdx, [rax]
0x18002b367  jmp     short loc_18002B36B
0x18002b369  xor     edx, edx
0x18002b36b  xor     r8d, r8d
0x18002b36e  mov     rax, r9
0x18002b371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b376  add     rbx, 8
0x18002b37a  cmp     rbx, rsi
0x18002b37d  jnz     short loc_18002B313
0x18002b37f  xor     ebx, ebx
0x18002b381  lea     rcx, [rbp+57h+arg_8]
0x18002b385  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b38a  nop
0x18002b38b  lea     rcx, [rbp+57h+arg_0]
0x18002b38f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002b394  mov     eax, ebx
0x18002b396  lea     r11, [rsp+0E0h+var_10]
0x18002b39e  mov     rbx, [r11+38h]
0x18002b3a2  movaps  xmm6, xmmword ptr [r11-10h]
0x18002b3a7  movaps  xmm7, xmmword ptr [r11-20h]
0x18002b3ac  mov     rsp, r11
0x18002b3af  pop     rdi
0x18002b3b0  pop     rsi
0x18002b3b1  pop     rbp
0x18002b3b2  retn
```
