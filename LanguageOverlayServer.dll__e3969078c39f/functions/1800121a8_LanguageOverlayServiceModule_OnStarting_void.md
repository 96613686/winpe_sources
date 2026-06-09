# LanguageOverlayServiceModule::_OnStarting(void)

- ea: `0x1800121a8`
- end: `0x180012424`
- name: `?_OnStarting@LanguageOverlayServiceModule@@AEAAXXZ`
- size: `636`
- prototype: `void __fastcall(LanguageOverlayServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001021c`

## callees

- `0x180003a00`
- `0x18000a024`
- `0x18000a9cc`
- `0x18001190c`
- `0x180011bec`
- `0x1800121a8`
- `0x180012a98`
- `0x180012b20`
- `0x1800277c0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800122b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012322`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800122f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012357`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800122f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012357`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18001232e`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800123cc`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x18001232e`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800123cc`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800121f5`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800122c9`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18001239b`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800121f5`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800122c9`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18001239b`
- `msvcp_win!_Mtx_unlock` at `0x18001236c`
- `msvcp_win!_Mtx_unlock` at `0x18001236c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001224b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012266`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001224b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012266`
- `msvcp_win!_Mtx_lock` at `0x18001223e`
- `msvcp_win!_Mtx_lock` at `0x18001223e`

## string_xrefs

- `0x1800122de`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x180012343`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x1800123b0`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x1800123e1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.h`
- `0x180012411`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\raiiutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall LanguageOverlayServiceModule::_OnStarting(LanguageOverlayServiceModule *this)
{
  const unsigned __int16 *v2; // rdx
  unsigned int ServiceParameterOrDefault; // eax
  int v4; // eax
  __int64 v5; // rdx
  int v6; // ebx
  struct _Mtx_internal_imp_t *v7; // rsi
  struct IContextCallback *v8; // rax
  __int64 v9; // rcx
  int *v10; // r14
  int v11; // r15d
  DWORD LastError; // r12d
  int v13; // eax
  wil **v14; // rdi
  wil *v15; // r15
  wil *v16; // r14
  DWORD v17; // r12d
  int v18; // eax
  struct IContextCallback *v19; // rcx
  int v20; // eax
  wil *v21; // rcx
  int v22; // eax
  int v23; // eax
  void *v24; // rdx
  unsigned int v25; // r8d
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-68h] BYREF
  LanguageOverlayServiceModule *v28; // [rsp+28h] [rbp-60h]
  struct IContextCallback *v29; // [rsp+30h] [rbp-58h] BYREF
  wil *v30; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    v28 = this;
    LanguageOverlayServiceModule::_UpdateStatus(this, 2u, 0);
    raii::AddMTAUsageReference(&v30);
    ServiceParameterOrDefault = LanguageOverlayServiceModule::_GetServiceParameterOrDefault(this, v2);
    v4 = CoRegisterServerShutdownDelay(*((_QWORD *)this + 18), ServiceParameterOrDefault);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.cpp",
        (const char *)(unsigned int)v4,
        v27);
    v6 = 1;
    v27 = 1;
    raii::CreateComInstance<IContextCallback>((LPVOID *)&v29, v5, 0x17u);
    LanguageOverlayServiceModule::_DipatchCallInContext(
      this,
      v29,
      (int (*)(struct tagComCallData *))LanguageOverlayServiceModule::_RegisterObjectsCallback);
    v7 = (LanguageOverlayServiceModule *)((char *)this + 16);
    if ( _Mtx_lock((LanguageOverlayServiceModule *)((char *)this + 16)) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 23) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 23) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v8 = v29;
    v29 = 0;
    v9 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = v8;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v10 = (int *)((char *)this + 160);
    if ( (int *)((char *)this + 160) != &v27 )
    {
      v11 = *v10;
      if ( *v10 != -2147467259 )
      {
        LastError = GetLastError();
        if ( v11 >= 0 )
        {
          v13 = CoRegisterServerShutdownDelay(0, 0);
          if ( v13 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x21,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
              (const char *)(unsigned int)v13,
              v27);
        }
        SetLastError(LastError);
      }
      *v10 = 1;
      v6 = -2147467259;
      v27 = -2147467259;
    }
    v14 = (wil **)((char *)this + 176);
    if ( v14 != &v30 )
    {
      v15 = v30;
      v16 = *v14;
      if ( *v14 )
      {
        v17 = GetLastError();
        v18 = CoDecrementMTAUsage(v16);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x11,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
            (const char *)(unsigned int)v18,
            v27);
        SetLastError(v17);
      }
      *v14 = v15;
      v30 = 0;
    }
    _Mtx_unlock(v7);
    v19 = v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(struct IContextCallback *))v19->lpVtbl->Release)(v19);
    }
    if ( v6 >= 0 )
    {
      v20 = CoRegisterServerShutdownDelay(0, 0);
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x21,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
          (const char *)(unsigned int)v20,
          v27);
    }
    v21 = v30;
    if ( v30 )
    {
      v22 = CoDecrementMTAUsage(v30);
      v21 = retaddr;
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x11,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\raiiutils.h",
          (const char *)(unsigned int)v22,
          v27);
    }
  }
  catch ( ... )
  {
    v23 = wil::ResultFromCaughtException(v21);
    LanguageOverlayServiceModule::_OnStopped(v28, v23);
    wil::details::in1diag3::Throw_CaughtException(retaddr, v24, v25, v26);
  }
}

```

## disassembly

```asm
0x1800121a8  push    rbx
0x1800121aa  push    rsi
0x1800121ab  push    rdi
0x1800121ac  push    r12
0x1800121ae  push    r14
0x1800121b0  push    r15
0x1800121b2  sub     rsp, 58h
0x1800121b6  mov     rax, cs:__security_cookie
0x1800121bd  xor     rax, rsp
0x1800121c0  mov     [rsp+88h+var_48], rax
0x1800121c5  mov     rdi, rcx
0x1800121c8  mov     [rsp+88h+var_60], rcx
0x1800121cd  xor     r8d, r8d; int
0x1800121d0  lea     edx, [r8+2]; unsigned int
0x1800121d4  call    ?_UpdateStatus@LanguageOverlayServiceModule@@AEAAXKJ@Z; LanguageOverlayServiceModule::_UpdateStatus(ulong,long)
0x1800121d9  lea     rcx, [rsp+88h+var_50]
0x1800121de  call    ?AddMTAUsageReference@raii@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AXPEAU1@@Z$1?_ReleaseMTAReference@details@raii@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; raii::AddMTAUsageReference(void)
0x1800121e3  nop
0x1800121e4  mov     rcx, rdi; this
0x1800121e7  call    ?_GetServiceParameterOrDefault@LanguageOverlayServiceModule@@AEAAKPEBGK@Z; LanguageOverlayServiceModule::_GetServiceParameterOrDefault(ushort const *,ulong)
0x1800121ec  mov     edx, eax
0x1800121ee  mov     rcx, [rdi+90h]
0x1800121f5  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800121fb  mov     rcx, [rsp+88h]; this
0x180012203  test    eax, eax
0x180012205  js      loc_18001240E
0x18001220b  mov     ebx, 1
0x180012210  mov     [rsp+88h+var_68], ebx; int
0x180012214  lea     r8d, [rbx+16h]
0x180012218  lea     rcx, [rsp+88h+var_58]
0x18001221d  call    ??$CreateComInstance@UIContextCallback@@@raii@@YA?AV?$ComPtr@UIContextCallback@@@WRL@Microsoft@@AEBU_GUID@@KPEAUIUnknown@@@Z; raii::CreateComInstance<IContextCallback>(_GUID const &,ulong,IUnknown *)
0x180012222  nop
0x180012223  lea     r8, ?_RegisterObjectsCallback@LanguageOverlayServiceModule@@CAJPEAUtagComCallData@@@Z; int (*)(struct tagComCallData *)
0x18001222a  mov     rdx, [rsp+88h+var_58]; struct IContextCallback *
0x18001222f  mov     rcx, rdi; this
0x180012232  call    ?_DipatchCallInContext@LanguageOverlayServiceModule@@AEAAXPEAUIContextCallback@@P6AJPEAUtagComCallData@@@Z@Z; LanguageOverlayServiceModule::_DipatchCallInContext(IContextCallback *,long (*)(tagComCallData *))
0x180012237  lea     rsi, [rdi+10h]
0x18001223b  mov     rcx, rsi; _Mtx_t
0x18001223e  call    cs:__imp__Mtx_lock
0x180012244  test    eax, eax
0x180012246  jz      short loc_180012251
0x180012248  lea     ecx, [rbx+4]
0x18001224b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012251  cmp     dword ptr [rsi+4Ch], 7FFFFFFFh
0x180012258  jnz     short loc_18001226C
0x18001225a  mov     dword ptr [rsi+4Ch], 7FFFFFFEh
0x180012261  mov     ecx, 6
0x180012266  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001226c  mov     rax, [rsp+88h+var_58]
0x180012271  mov     [rsp+88h+var_58], 0
0x18001227a  mov     rcx, [rdi+0A8h]
0x180012281  mov     [rdi+0A8h], rax
0x180012288  test    rcx, rcx
0x18001228b  jz      short loc_18001229A
0x18001228d  mov     rax, [rcx]
0x180012290  mov     rax, [rax+10h]
0x180012294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012299  nop
0x18001229a  lea     r14, [rdi+0A0h]
0x1800122a1  lea     rax, [rsp+88h+var_68]
0x1800122a6  cmp     r14, rax
0x1800122a9  jz      short loc_180012304
0x1800122ab  mov     r15d, [r14]
0x1800122ae  cmp     r15d, 80004005h
0x1800122b5  jz      short loc_1800122F8
0x1800122b7  call    cs:__imp_GetLastError
0x1800122bd  mov     r12d, eax
0x1800122c0  test    r15d, r15d
0x1800122c3  js      short loc_1800122EF
0x1800122c5  xor     edx, edx
0x1800122c7  xor     ecx, ecx
0x1800122c9  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800122cf  mov     rcx, [rsp+88h]; this
0x1800122d7  test    eax, eax
0x1800122d9  jns     short loc_1800122EF
0x1800122db  mov     r9d, eax; char *
0x1800122de  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x1800122e5  mov     edx, 21h ; '!'; void *
0x1800122ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800122ef  mov     ecx, r12d; dwErrCode
0x1800122f2  call    cs:__imp_SetLastError
0x1800122f8  mov     [r14], ebx
0x1800122fb  mov     ebx, 80004005h
0x180012300  mov     [rsp+88h+var_68], ebx; int
0x180012304  add     rdi, 0B0h
0x18001230b  lea     rax, [rsp+88h+var_50]
0x180012310  cmp     rdi, rax
0x180012313  jz      short loc_180012369
0x180012315  mov     r15, [rsp+88h+var_50]
0x18001231a  mov     r14, [rdi]
0x18001231d  test    r14, r14
0x180012320  jz      short loc_18001235D
0x180012322  call    cs:__imp_GetLastError
0x180012328  mov     r12d, eax
0x18001232b  mov     rcx, r14
0x18001232e  call    cs:__imp_CoDecrementMTAUsage
0x180012334  mov     rcx, [rsp+88h]; this
0x18001233c  test    eax, eax
0x18001233e  jns     short loc_180012354
0x180012340  mov     r9d, eax; char *
0x180012343  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x18001234a  mov     edx, 11h; void *
0x18001234f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012354  mov     ecx, r12d; dwErrCode
0x180012357  call    cs:__imp_SetLastError
0x18001235d  mov     [rdi], r15
0x180012360  mov     [rsp+88h+var_50], 0
0x180012369  mov     rcx, rsi; _Mtx_t
0x18001236c  call    cs:__imp__Mtx_unlock
0x180012372  nop
0x180012373  mov     rcx, [rsp+88h+var_58]
0x180012378  test    rcx, rcx
0x18001237b  jz      short loc_180012393
0x18001237d  mov     [rsp+88h+var_58], 0
0x180012386  mov     rax, [rcx]
0x180012389  mov     rax, [rax+10h]
0x18001238d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012392  nop
0x180012393  test    ebx, ebx
0x180012395  js      short loc_1800123C2
0x180012397  xor     edx, edx
0x180012399  xor     ecx, ecx
0x18001239b  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800123a1  mov     rcx, [rsp+88h]; this
0x1800123a9  test    eax, eax
0x1800123ab  jns     short loc_1800123C2
0x1800123ad  mov     r9d, eax; char *
0x1800123b0  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x1800123b7  mov     edx, 21h ; '!'; void *
0x1800123bc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800123c1  nop
0x1800123c2  mov     rcx, [rsp+88h+var_50]
0x1800123c7  test    rcx, rcx
0x1800123ca  jz      short loc_1800123F3
0x1800123cc  call    cs:__imp_CoDecrementMTAUsage
0x1800123d2  mov     rcx, [rsp+88h]; this
0x1800123da  test    eax, eax
0x1800123dc  jns     short loc_1800123F3
0x1800123de  mov     r9d, eax; char *
0x1800123e1  lea     r8, aOnecoreBaseLan_22; "onecore\\base\\languageoverlay\\service"...
0x1800123e8  mov     edx, 11h; void *
0x1800123ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800123f2  nop
0x1800123f3  mov     rcx, [rsp+88h+var_48]
0x1800123f8  xor     rcx, rsp; StackCookie
0x1800123fb  call    __security_check_cookie
0x180012400  add     rsp, 58h
0x180012404  pop     r15
0x180012406  pop     r14
0x180012408  pop     r12
0x18001240a  pop     rdi
0x18001240b  pop     rsi
0x18001240c  pop     rbx
0x18001240d  retn
0x18001240e  mov     r9d, eax; char *
0x180012411  lea     r8, aOnecoreBaseLan_1; "onecore\\base\\languageoverlay\\service"...
0x180012418  mov     edx, 23h ; '#'; void *
0x18001241d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
