# Windows::Power::Manager::PreventSystemSleep(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool)

- ea: `0x180066d80`
- end: `0x180067167`
- name: `?PreventSystemSleep@Manager@Power@Windows@@UEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `999`
- prototype: `__int64 __fastcall(Windows::Power::Manager *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update`

## callees

- `0x180007660`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800209fc`
- `0x180044ed0`
- `0x180045bd4`
- `0x1800665d4`
- `0x180066d80`
- `0x1800671b0`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800670e6`
- `msvcp_win!_Mtx_unlock` at `0x1800670e6`
- `msvcp_win!_Mtx_lock` at `0x180066dc1`
- `msvcp_win!_Mtx_lock` at `0x180066dc1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180066dd3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180066df5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180066dd3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180066df5`

## string_xrefs

- `0x180066f31`: `TaskClient`
- `0x180067027`: `USO task`
- `0x180067116`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\power.cpp`
- `0x18006712b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\power.cpp`
- `0x180067140`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\power.cpp`
- `0x180067155`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\power.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
int __fastcall Windows::Power::Manager::PreventSystemSleep(Windows::Power::Manager *this, HMODULE a2, char a3)
{
  Windows::DockedHelpers *DockedPower; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  _QWORD *System; // rax
  __int64 v14; // rax
  __int64 v15; // rdi
  void (__fastcall *v16)(__int64, _QWORD *, HMODULE, _OWORD *); // r15
  const wchar_t *v17; // rdx
  __int64 v18; // r8
  volatile signed __int32 *v19; // rdi
  volatile signed __int32 *v20; // rdi
  int v21; // eax
  int v22; // eax
  __int64 *v23; // rax
  __int64 v24; // rcx
  void (__fastcall ***v25)(_QWORD, __int64); // r8
  int v27; // [rsp+20h] [rbp-59h]
  int v28; // [rsp+30h] [rbp-49h] BYREF
  int v29; // [rsp+34h] [rbp-45h] BYREF
  __int64 v30; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v31[2]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v32[8]; // [rsp+50h] [rbp-29h] BYREF
  volatile signed __int32 *v33; // [rsp+58h] [rbp-21h]
  _BYTE v34[8]; // [rsp+60h] [rbp-19h] BYREF
  volatile signed __int32 *v35; // [rsp+68h] [rbp-11h]
  _OWORD v36[2]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v31[1] = &Windows::Power::Manager::s_requestLock;
  if ( _Mtx_lock((_Mtx_t)&Windows::Power::Manager::s_requestLock) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_18009531C == 0x7FFFFFFF )
  {
    dword_18009531C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !*((_QWORD *)this + 3) )
  {
    DockedPower = Windows::DockedHelpers::GetDockedPower((Windows::DockedHelpers *)&v30);
    v7 = *(_QWORD *)DockedPower;
    *(_QWORD *)DockedPower = 0;
    v8 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v7;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v29 = 0;
  v28 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 3) + 40LL))(*((_QWORD *)this + 3), &v29);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\power.cpp",
      (const char *)(unsigned int)v9,
      v27);
  v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 3) + 64LL))(*((_QWORD *)this + 3), &v28);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\power.cpp",
      (const char *)(unsigned int)v10,
      v27);
  if ( !v28 || a3 != (v29 != 0) )
  {
    v11 = *((_QWORD *)this + 2);
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 8LL))(v11, &v30);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
      v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = 0;
      if ( v12 )
        (**v12)(v12, 1);
      if ( v30 )
        (**(void (__fastcall ***)(__int64, __int64))v30)(v30, 1);
    }
    System = (_QWORD *)SystemInterface::Service::GetSystem(v34);
    v14 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 96LL))(*System, v32);
    v15 = *(_QWORD *)v14;
    v16 = *(void (__fastcall **)(__int64, _QWORD *, HMODULE, _OWORD *))(**(_QWORD **)v14 + 16LL);
    v17 = L"TaskClient";
    if ( !a3 )
      v17 = L"PdcActivatorWithNetwork";
    memset(v36, 0, sizeof(v36));
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    std::wstring::_Construct<1,unsigned short const *>(v36, v17);
    v16(v15, v31, a2, v36);
    std::wstring::_Tidy_deallocate(v36);
    v19 = v33;
    if ( v33 )
    {
      if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    v20 = v35;
    if ( v35 )
    {
      if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    Windows::Power::Manager::CreatePowerRequest((__int64)this, a2);
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(HMODULE *)a2;
    v21 = (*(__int64 (__fastcall **)(_QWORD, HMODULE, const wchar_t *))(**((_QWORD **)this + 3) + 48LL))(
            *((_QWORD *)this + 3),
            a2,
            L"USO task");
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\power.cpp",
        (const char *)(unsigned int)v21,
        v27);
    if ( a3 )
    {
      v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\power.cpp",
          (const char *)(unsigned int)v22,
          v27);
    }
    else
    {
      Windows::Power::Manager::ReleasePDCTask(this);
    }
    v23 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v31[0] + 16LL))(v31[0], &v30);
    v24 = *v23;
    *v23 = 0;
    v25 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v24;
    if ( v25 )
      (**v25)(v25, 1);
    if ( v30 )
      (**(void (__fastcall ***)(__int64, __int64))v30)(v30, 1);
    if ( v31[0] )
      (**(void (__fastcall ***)(_QWORD, __int64))v31[0])(v31[0], 1);
  }
  return _Mtx_unlock((_Mtx_t)&Windows::Power::Manager::s_requestLock);
}

```

## disassembly

```asm
0x180066d80  mov     [rsp-8+arg_10], rbx
0x180066d85  push    rbp
0x180066d86  push    rsi
0x180066d87  push    rdi
0x180066d88  push    r12
0x180066d8a  push    r13
0x180066d8c  push    r14
0x180066d8e  push    r15
0x180066d90  lea     rbp, [rsp-27h]
0x180066d95  sub     rsp, 0A0h
0x180066d9c  mov     rax, cs:__security_cookie
0x180066da3  xor     rax, rsp
0x180066da6  mov     [rbp+57h+var_40], rax
0x180066daa  mov     r14b, r8b
0x180066dad  mov     rsi, rdx
0x180066db0  mov     rbx, rcx
0x180066db3  lea     rax, ?s_requestLock@Manager@Power@Windows@@0Vmutex@std@@A; std::mutex Windows::Power::Manager::s_requestLock
0x180066dba  mov     [rbp+57h+var_88], rax
0x180066dbe  mov     rcx, rax; _Mtx_t
0x180066dc1  call    cs:__imp__Mtx_lock
0x180066dc7  xor     r12d, r12d
0x180066dca  test    eax, eax
0x180066dcc  jz      short loc_180066DDA
0x180066dce  lea     ecx, [r12+5]
0x180066dd3  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180066dd9  int     3; Trap to Debugger
0x180066dda  cmp     cs:dword_18009531C, 7FFFFFFFh
0x180066de4  jnz     short loc_180066DFC
0x180066de6  mov     cs:dword_18009531C, 7FFFFFFEh
0x180066df0  mov     ecx, 6
0x180066df5  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180066dfb  nop
0x180066dfc  cmp     [rbx+18h], r12
0x180066e00  jnz     short loc_180066E44
0x180066e02  lea     rcx, [rbp+57h+var_98]
0x180066e06  call    ?GetDockedPower@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedPower@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedPower(void)
0x180066e0b  mov     rcx, [rax]
0x180066e0e  mov     [rax], r12
0x180066e11  mov     rdx, [rbx+18h]
0x180066e15  mov     [rbx+18h], rcx
0x180066e19  test    rdx, rdx
0x180066e1c  jz      short loc_180066E2E
0x180066e1e  mov     rax, [rdx]
0x180066e21  mov     rcx, rdx
0x180066e24  mov     rax, [rax+10h]
0x180066e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e2d  nop
0x180066e2e  mov     rcx, [rbp+57h+var_98]
0x180066e32  test    rcx, rcx
0x180066e35  jz      short loc_180066E44
0x180066e37  mov     rax, [rcx]
0x180066e3a  mov     rax, [rax+10h]
0x180066e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e43  nop
0x180066e44  mov     [rbp+57h+var_9C], r12d
0x180066e48  mov     [rbp+57h+var_A0], r12d
0x180066e4c  mov     rcx, [rbx+18h]
0x180066e50  mov     rax, [rcx]
0x180066e53  lea     rdx, [rbp+57h+var_9C]
0x180066e57  mov     rax, [rax+28h]
0x180066e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e60  mov     rcx, [rbp+5Fh]; this
0x180066e64  test    eax, eax
0x180066e66  js      loc_18006713D
0x180066e6c  mov     rcx, [rbx+18h]
0x180066e70  mov     rax, [rcx]
0x180066e73  lea     rdx, [rbp+57h+var_A0]
0x180066e77  mov     rax, [rax+40h]
0x180066e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e80  mov     rcx, [rbp+5Fh]; this
0x180066e84  test    eax, eax
0x180066e86  js      loc_180067152
0x180066e8c  cmp     [rbp+57h+var_A0], r12d
0x180066e90  jz      short loc_180066EA2
0x180066e92  cmp     [rbp+57h+var_9C], r12d
0x180066e96  setnz   al
0x180066e99  cmp     r14b, al
0x180066e9c  jz      loc_1800670DF
0x180066ea2  mov     rcx, [rbx+10h]
0x180066ea6  mov     edi, 1
0x180066eab  test    rcx, rcx
0x180066eae  jz      short loc_180066F02
0x180066eb0  mov     rax, [rcx]
0x180066eb3  lea     rdx, [rbp+57h+var_98]
0x180066eb7  mov     rax, [rax+8]
0x180066ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ec0  nop
0x180066ec1  mov     rcx, [rbx+10h]
0x180066ec5  mov     rax, [rcx]
0x180066ec8  mov     rax, [rax+18h]
0x180066ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ed1  mov     rcx, [rbx+10h]
0x180066ed5  mov     [rbx+10h], r12
0x180066ed9  test    rcx, rcx
0x180066edc  jz      short loc_180066EEC
0x180066ede  mov     rax, [rcx]
0x180066ee1  mov     edx, edi
0x180066ee3  mov     rax, [rax]
0x180066ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066eeb  nop
0x180066eec  mov     rcx, [rbp+57h+var_98]
0x180066ef0  test    rcx, rcx
0x180066ef3  jz      short loc_180066F02
0x180066ef5  mov     rax, [rcx]
0x180066ef8  mov     edx, edi
0x180066efa  mov     rax, [rax]
0x180066efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f02  lea     rcx, [rbp+57h+var_70]
0x180066f06  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180066f0b  nop
0x180066f0c  mov     rcx, [rax]
0x180066f0f  mov     rax, [rcx]
0x180066f12  lea     rdx, [rbp+57h+var_80]
0x180066f16  mov     rax, [rax+60h]
0x180066f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f1f  nop
0x180066f20  mov     rdi, [rax]
0x180066f23  mov     rax, [rdi]
0x180066f26  mov     r15, [rax+10h]
0x180066f2a  lea     rax, aPdcactivatorwi; "PdcActivatorWithNetwork"
0x180066f31  lea     rdx, aTaskclient; "TaskClient"
0x180066f38  test    r14b, r14b
0x180066f3b  cmovz   rdx, rax
0x180066f3f  xorps   xmm0, xmm0
0x180066f42  movups  [rbp+57h+var_60], xmm0
0x180066f46  xorps   xmm1, xmm1
0x180066f49  movdqu  [rbp+57h+var_50], xmm1
0x180066f4e  or      r13, 0FFFFFFFFFFFFFFFFh
0x180066f52  mov     r8, r13
0x180066f55  inc     r8
0x180066f58  cmp     [rdx+r8*2], r12w
0x180066f5d  jnz     short loc_180066F55
0x180066f5f  lea     rcx, [rbp+57h+var_60]
0x180066f63  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180066f68  nop
0x180066f69  lea     r9, [rbp+57h+var_60]
0x180066f6d  mov     r8, rsi
0x180066f70  lea     rdx, [rbp+57h+var_90]
0x180066f74  mov     rcx, rdi
0x180066f77  mov     rax, r15
0x180066f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f7f  nop
0x180066f80  lea     rcx, [rbp+57h+var_60]
0x180066f84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066f89  nop
0x180066f8a  mov     rdi, [rbp+57h+var_78]
0x180066f8e  test    rdi, rdi
0x180066f91  jz      short loc_180066FCB
0x180066f93  mov     eax, r13d
0x180066f96  lock xadd [rdi+8], eax
0x180066f9b  add     eax, r13d
0x180066f9e  jnz     short loc_180066FCB
0x180066fa0  mov     rax, [rdi]
0x180066fa3  mov     rcx, rdi
0x180066fa6  mov     rax, [rax]
0x180066fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fae  mov     eax, r13d
0x180066fb1  lock xadd [rdi+0Ch], eax
0x180066fb6  add     eax, r13d
0x180066fb9  jnz     short loc_180066FCB
0x180066fbb  mov     rax, [rdi]
0x180066fbe  mov     rcx, rdi
0x180066fc1  mov     rax, [rax+8]
0x180066fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fca  nop
0x180066fcb  mov     rdi, [rbp+57h+var_68]
0x180066fcf  test    rdi, rdi
0x180066fd2  jz      short loc_18006700B
0x180066fd4  mov     eax, r13d
0x180066fd7  lock xadd [rdi+8], eax
0x180066fdc  add     eax, r13d
0x180066fdf  jnz     short loc_18006700B
0x180066fe1  mov     rax, [rdi]
0x180066fe4  mov     rcx, rdi
0x180066fe7  mov     rax, [rax]
0x180066fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066fef  mov     eax, r13d
0x180066ff2  lock xadd [rdi+0Ch], eax
0x180066ff7  add     eax, r13d
0x180066ffa  jnz     short loc_18006700B
0x180066ffc  mov     rax, [rdi]
0x180066fff  mov     rcx, rdi
0x180067002  mov     rax, [rax+8]
0x180067006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006700b  mov     rdx, rsi
0x18006700e  mov     rcx, rbx
0x180067011  call    ?CreatePowerRequest@Manager@Power@Windows@@AEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Power::Manager::CreatePowerRequest(std::wstring &)
0x180067016  mov     rcx, [rbx+18h]
0x18006701a  mov     rax, [rcx]
0x18006701d  cmp     qword ptr [rsi+18h], 7
0x180067022  jbe     short loc_180067027
0x180067024  mov     rsi, [rsi]
0x180067027  lea     r8, aUsoTask; "USO task"
0x18006702e  mov     rdx, rsi
0x180067031  mov     rax, [rax+30h]
0x180067035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006703a  mov     rcx, [rbp+5Fh]; this
0x18006703e  test    eax, eax
0x180067040  js      loc_180067113
0x180067046  test    r14b, r14b
0x180067049  jz      short loc_180067069
0x18006704b  mov     rcx, [rbx+18h]
0x18006704f  mov     rax, [rcx]
0x180067052  mov     rax, [rax+18h]
0x180067056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006705b  mov     rcx, [rbp+5Fh]; this
0x18006705f  test    eax, eax
0x180067061  js      loc_180067128
0x180067067  jmp     short loc_180067071
0x180067069  mov     rcx, rbx; this
0x18006706c  call    ?ReleasePDCTask@Manager@Power@Windows@@AEAAXXZ; Windows::Power::Manager::ReleasePDCTask(void)
0x180067071  mov     rcx, [rbp+57h+var_90]
0x180067075  mov     rax, [rcx]
0x180067078  lea     rdx, [rbp+57h+var_98]
0x18006707c  mov     rax, [rax+10h]
0x180067080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067085  mov     rcx, [rax]
0x180067088  mov     [rax], r12
0x18006708b  mov     r8, [rbx+10h]
0x18006708f  mov     [rbx+10h], rcx
0x180067093  test    r8, r8
0x180067096  jz      short loc_1800670AB
0x180067098  mov     rax, [r8]
0x18006709b  mov     edx, 1
0x1800670a0  mov     rcx, r8
0x1800670a3  mov     rax, [rax]
0x1800670a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670ab  mov     rcx, [rbp+57h+var_98]
0x1800670af  test    rcx, rcx
0x1800670b2  jz      short loc_1800670C5
0x1800670b4  mov     rax, [rcx]
0x1800670b7  mov     edx, 1
0x1800670bc  mov     rax, [rax]
0x1800670bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670c4  nop
0x1800670c5  mov     rcx, [rbp+57h+var_90]
0x1800670c9  test    rcx, rcx
0x1800670cc  jz      short loc_1800670DF
0x1800670ce  mov     rax, [rcx]
0x1800670d1  mov     edx, 1
0x1800670d6  mov     rax, [rax]
0x1800670d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800670de  nop
0x1800670df  lea     rcx, ?s_requestLock@Manager@Power@Windows@@0Vmutex@std@@A; _Mtx_t
0x1800670e6  call    cs:__imp__Mtx_unlock
0x1800670ec  mov     rcx, [rbp+57h+var_40]
0x1800670f0  xor     rcx, rsp; StackCookie
0x1800670f3  call    __security_check_cookie
0x1800670f8  mov     rbx, [rsp+0D0h+arg_10]
0x180067100  add     rsp, 0A0h
0x180067107  pop     r15
0x180067109  pop     r14
0x18006710b  pop     r13
0x18006710d  pop     r12
0x18006710f  pop     rdi
0x180067110  pop     rsi
0x180067111  pop     rbp
0x180067112  retn
0x180067113  mov     r9d, eax; char *
0x180067116  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18006711d  mov     edx, 44h ; 'D'; void *
0x180067122  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067128  mov     r9d, eax; char *
0x18006712b  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067132  mov     edx, 39h ; '9'; void *
0x180067137  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006713d  mov     r9d, eax; char *
0x180067140  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180067147  mov     edx, 5Bh ; '['; void *
0x18006714c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180067152  mov     r9d, eax; char *
0x180067155  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18006715c  mov     edx, 5Ch ; '\'; void *
0x180067161  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
