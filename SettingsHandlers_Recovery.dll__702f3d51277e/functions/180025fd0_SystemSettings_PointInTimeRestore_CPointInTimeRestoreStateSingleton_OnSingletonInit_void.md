# SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::OnSingletonInit(void)

- ea: `0x180025fd0`
- end: `0x1800261ea`
- name: `?OnSingletonInit@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@MEAAJXZ`
- size: `538`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180002890`
- `0x18000a49c`
- `0x18000bef4`
- `0x180025fd0`
- `0x1800262d0`
- `0x1800263d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180026178`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180026178`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180026097`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180026097`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002600d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002600d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002604d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002604d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002601f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002602e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002601f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002602e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026039`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002618b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026039`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002618b`
- `msvcp_win!_Thrd_id` at `0x1800260bc`
- `msvcp_win!_Thrd_id` at `0x1800260bc`
- `msvcp_win!_Thrd_join` at `0x1800260e2`
- `msvcp_win!_Thrd_join` at `0x1800260e2`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800260b5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800260cc`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800260f1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800261b1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800260b5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800260cc`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800260f1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800261b1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002616b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002616b`
- `WDSCORE!CurrentIP` at `0x180026108`
- `WDSCORE!CurrentIP` at `0x180026108`

## string_xrefs

- `0x1800261bc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800261d8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::OnSingletonInit(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *this)
{
  void *v2; // rdx
  HANDLE Event; // rsi
  unsigned int v4; // r8d
  const char *v5; // r9
  HANDLE v6; // rbx
  DWORD LastError; // edi
  const char *v8; // r9
  _QWORD *v9; // rax
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  unsigned int v13; // ebx
  const char *v14; // r9
  _Thrd_t v16; // [rsp+60h] [rbp-20h] BYREF
  _Thrd_t v17; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  unsigned int v19; // [rsp+B8h] [rbp+38h] BYREF
  HANDLE hObject; // [rsp+C0h] [rbp+40h] BYREF
  _QWORD *v21; // [rsp+C8h] [rbp+48h]

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl);
  v19 = 0;
  hObject = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  v6 = hObject;
  if ( hObject )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    SetLastError(LastError);
  }
  hObject = Event;
  v9 = operator new(0x18u);
  *v9 = this;
  v9[1] = &v19;
  v9[2] = &hObject;
  v21 = v9;
  v16._Hnd = (void *)_o__beginthreadex(
                       0,
                       0,
                       std::thread::_Invoke_std::tuple__lambda_069cc54278ae02eae492709c0472dee1____0_,
                       v9,
                       0,
                       &v16._Id);
  if ( !v16._Hnd )
  {
    v16._Id = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_18;
  }
  if ( !v16._Id )
  {
    std::_Throw_Cpp_error(1);
    __debugbreak();
  }
  if ( v16._Id == _Thrd_id() )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  v17 = v16;
  if ( _Thrd_join(&v17, 0) )
  {
    std::_Throw_Cpp_error(2);
    __debugbreak();
  }
  v16 = 0;
  v10 = GetLastError();
  v11 = CurrentIP();
  v12 = ConstructPartialMsgW(
          0x4000000u,
          "SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::OnSingletonInit: Exiting...");
  WdsSetupLogMessageW(
    v12,
    0,
    L"D",
    0,
    174,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestorestatesingleton.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::OnSingletonInit",
    v11,
    v10,
    0,
    0);
  if ( v16._Id )
    _o_terminate();
  v13 = v19;
  if ( hObject && !CloseHandle(hObject) )
LABEL_18:
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v14);
  return v13;
}

```

## disassembly

```asm
0x180025fd0  push    rbp
0x180025fd2  push    rbx
0x180025fd3  push    rsi
0x180025fd4  push    rdi
0x180025fd5  push    r14
0x180025fd7  mov     rbp, rsp
0x180025fda  sub     rsp, 80h
0x180025fe1  mov     r14, rcx
0x180025fe4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180025feb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180025ff0  mov     [rbp+arg_8], 0
0x180025ff7  mov     [rbp+hObject], 0
0x180025fff  xor     edx, edx; lpName
0x180026001  xor     ecx, ecx; lpEventAttributes
0x180026003  mov     r9d, 1F0003h; dwDesiredAccess
0x180026009  lea     r8d, [rdx+1]; dwFlags
0x18002600d  call    cs:__imp_CreateEventExW
0x180026013  mov     rsi, rax
0x180026016  test    rax, rax
0x180026019  jz      loc_1800261CE
0x18002601f  call    cs:__imp_GetLastError
0x180026025  mov     rbx, [rbp+hObject]
0x180026029  test    rbx, rbx
0x18002602c  jz      short loc_180026053
0x18002602e  call    cs:__imp_GetLastError
0x180026034  mov     edi, eax
0x180026036  mov     rcx, rbx; hObject
0x180026039  call    cs:__imp_CloseHandle
0x18002603f  mov     rcx, [rbp+28h]; this
0x180026043  test    eax, eax
0x180026045  jz      loc_1800261D8
0x18002604b  mov     ecx, edi; dwErrCode
0x18002604d  call    cs:__imp_SetLastError
0x180026053  mov     [rbp+hObject], rsi
0x180026057  mov     ecx, 18h; Size
0x18002605c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026061  mov     [rax], r14
0x180026064  lea     rcx, [rbp+arg_8]
0x180026068  mov     [rax+8], rcx
0x18002606c  lea     rcx, [rbp+hObject]
0x180026070  mov     [rax+10h], rcx
0x180026074  mov     [rbp+arg_18], rax
0x180026078  lea     rcx, [rbp+var_20+8]
0x18002607c  mov     [rsp+80h+var_58], rcx
0x180026081  mov     [rsp+80h+var_60], 0
0x180026089  mov     r9, rax
0x18002608c  lea     r8, std__thread___Invoke_std__tuple__lambda_069cc54278ae02eae492709c0472dee1____0_
0x180026093  xor     edx, edx
0x180026095  xor     ecx, ecx
0x180026097  call    cs:__imp__o__beginthreadex
0x18002609d  mov     qword ptr [rbp+var_20], rax
0x1800260a1  test    rax, rax
0x1800260a4  jz      loc_1800261A5
0x1800260aa  cmp     dword ptr [rbp+var_20+8], 0
0x1800260ae  jnz     short loc_1800260BC
0x1800260b0  mov     ecx, 1
0x1800260b5  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800260bb  int     3; Trap to Debugger
0x1800260bc  call    cs:__imp__Thrd_id
0x1800260c2  cmp     dword ptr [rbp+var_20+8], eax
0x1800260c5  jnz     short loc_1800260D3
0x1800260c7  mov     ecx, 5
0x1800260cc  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800260d2  int     3; Trap to Debugger
0x1800260d3  movaps  xmm0, [rbp+var_20]
0x1800260d7  movdqa  xmmword ptr [rbp+var_10._Hnd], xmm0
0x1800260dc  xor     edx, edx; int *
0x1800260de  lea     rcx, [rbp+var_10]; _Thrd_t
0x1800260e2  call    cs:__imp__Thrd_join
0x1800260e8  test    eax, eax
0x1800260ea  jz      short loc_1800260F8
0x1800260ec  mov     ecx, 2
0x1800260f1  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800260f7  int     3; Trap to Debugger
0x1800260f8  xorps   xmm0, xmm0
0x1800260fb  movdqa  [rbp+var_20], xmm0
0x180026100  call    cs:__imp_GetLastError
0x180026106  mov     edi, eax
0x180026108  call    cs:__imp_CurrentIP
0x18002610e  mov     rbx, rax
0x180026111  lea     rdx, aSystemsettings_120; "SystemSettings::PointInTimeRestore::CPo"...
0x180026118  mov     ecx, 4000000h; unsigned int
0x18002611d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180026122  mov     [rsp+80h+var_30], 0
0x18002612a  mov     [rsp+80h+var_38], 0
0x180026133  mov     [rsp+80h+var_40], edi
0x180026137  mov     [rsp+80h+var_48], rbx
0x18002613c  lea     rcx, aSystemsettings_7; "SystemSettings::PointInTimeRestore::CPo"...
0x180026143  mov     [rsp+80h+var_50], rcx
0x180026148  lea     rcx, aPcshellShellSy_4; "pcshell\\shell\\systemsettings\\recover"...
0x18002614f  mov     [rsp+80h+var_58], rcx
0x180026154  mov     [rsp+80h+var_60], 0AEh
0x18002615c  xor     r9d, r9d
0x18002615f  lea     r8, aD; "D"
0x180026166  xor     edx, edx
0x180026168  mov     rcx, rax
0x18002616b  call    cs:__imp_WdsSetupLogMessageW
0x180026171  nop
0x180026172  cmp     dword ptr [rbp+var_20+8], 0
0x180026176  jz      short loc_18002617F
0x180026178  call    cs:__imp__o_terminate
0x18002617e  nop
0x18002617f  mov     ebx, [rbp+arg_8]
0x180026182  mov     rcx, [rbp+hObject]; hObject
0x180026186  test    rcx, rcx
0x180026189  jz      short loc_180026195
0x18002618b  call    cs:__imp_CloseHandle
0x180026191  test    eax, eax
0x180026193  jz      short loc_1800261B8
0x180026195  mov     eax, ebx
0x180026197  add     rsp, 80h
0x18002619e  pop     r14
0x1800261a0  pop     rdi
0x1800261a1  pop     rsi
0x1800261a2  pop     rbx
0x1800261a3  pop     rbp
0x1800261a4  retn
0x1800261a5  mov     dword ptr [rbp+var_20+8], 0
0x1800261ac  mov     ecx, 6
0x1800261b1  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800261b7  nop
0x1800261b8  mov     rcx, [rbp+28h]; this
0x1800261bc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800261c3  mov     edx, 0A0Bh; void *
0x1800261c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800261ce  mov     rcx, [rbp+28h]; this
0x1800261d2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800261d8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800261df  mov     edx, 0A0Bh; void *
0x1800261e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
