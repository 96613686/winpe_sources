# AdvancedProgressHandler<std::function<void (uint,LanguagePackInstallProgressState)>>::Invoke(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *,IInspectable *)

- ea: `0x1800526c0`
- end: `0x180052a2a`
- name: `?Invoke@?$AdvancedProgressHandler@V?$function@$$A6AXIW4LanguagePackInstallProgressState@@@Z@std@@@@UEAAJPEAUIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInspectable@@@Z`
- size: `874`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a00`
- `0x180009084`
- `0x1800120b0`
- `0x1800526c0`
- `0x180059b20`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005281c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180052848`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005281c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180052848`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800528f3`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800528f3`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18005293c`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x18005293c`
- `msvcp_win!_Mtx_unlock` at `0x180052998`
- `msvcp_win!_Mtx_unlock` at `0x180052998`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005296d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180052989`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005296d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180052989`
- `msvcp_win!_Mtx_lock` at `0x18005295e`
- `msvcp_win!_Mtx_lock` at `0x18005295e`

## string_xrefs

- `0x180052711`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052770`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x1800527cb`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x180052894`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x18005290a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`
- `0x18005294a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagefeaturesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AdvancedProgressHandler<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>::Invoke(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  int *v11; // rdx
  BOOL v12; // eax
  const char *v13; // r9
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  BOOL v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  BOOL v19; // eax
  unsigned int v20; // r14d
  const char *v21; // r9
  __int64 v22; // rbx
  __int64 v23; // r8
  __int64 v24; // rcx
  int lpArgToCompletionRoutine; // [rsp+20h] [rbp-40h]
  __int64 v26; // [rsp+30h] [rbp-30h] BYREF
  int v27; // [rsp+38h] [rbp-28h] BYREF
  double v28; // [rsp+40h] [rbp-20h] BYREF
  LARGE_INTEGER DueTime; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v26 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 80LL))(a2, &v26);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
      (const char *)(unsigned int)v3,
      lpArgToCompletionRoutine);
    v5 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return v4;
  }
  v27 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 48LL))(v26, &v27);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
      (const char *)(unsigned int)v7,
      lpArgToCompletionRoutine);
    v8 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v4;
  }
  v28 = 0.0;
  v9 = (*(__int64 (__fastcall **)(__int64, double *))(*(_QWORD *)v26 + 72LL))(v26, &v28);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
      (const char *)(unsigned int)v9,
      lpArgToCompletionRoutine);
    v10 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v4;
  }
  v11 = (int *)(a1 + 200);
  if ( v27 == 6 )
  {
    *v11 = 0;
    v12 = SetEvent(*(HANDLE *)(a1 + 184));
    v14 = retaddr;
    if ( !v12 )
    {
      v15 = 105;
LABEL_26:
      wil::details::in1diag3::_Log_GetLastError(
        v14,
        (void *)v15,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
        v13);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  if ( v27 != 7 )
  {
    if ( v27 == 9 )
    {
      *(_DWORD *)(a1 + 204) = (int)v28;
      v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 80LL))(v26, v11);
      v4 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
          (const char *)(unsigned int)v17,
          lpArgToCompletionRoutine);
        v18 = v26;
        if ( v26 )
        {
          v26 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        return v4;
      }
      DueTime.QuadPart = -1200000000;
      v19 = SetWaitableTimer(*(HANDLE *)(a1 + 192), &DueTime, 0, 0, 0, 1);
      v14 = retaddr;
      if ( !v19 )
      {
        v15 = 211;
        goto LABEL_26;
      }
      goto LABEL_47;
    }
    v20 = (int)v28;
    if ( *v11 < 0 && v20 > *(_DWORD *)(a1 + 204) )
    {
      *v11 = 0;
      if ( !CancelWaitableTimer(*(HANDLE *)(a1 + 192)) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagefeaturesprovider.cpp",
          v21);
    }
    if ( _Mtx_lock((_Mtx_t)(a1 + 16)) )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    if ( *(_DWORD *)(a1 + 92) == 0x7FFFFFFF )
    {
      *(_DWORD *)(a1 + 92) = 2147483646;
      std::_Throw_Cpp_error(6);
      __debugbreak();
    }
    v22 = *(_QWORD *)(a1 + 96);
    _Mtx_unlock((_Mtx_t)(a1 + 16));
    if ( !v22 )
      goto LABEL_47;
    if ( v27 )
    {
      switch ( v27 )
      {
        case 1:
        case 2:
          v23 = 1;
          goto LABEL_46;
        case 3:
        case 4:
          v23 = 2;
          goto LABEL_46;
        case 5:
          v23 = 3;
LABEL_46:
          AdvancedProgressHandler<std::function<void (unsigned int,enum LanguagePackInstallProgressState)>>::_NotifyProgressChanged(
            a1,
            v20,
            v23);
          goto LABEL_47;
      }
    }
    v23 = 0;
    goto LABEL_46;
  }
  *v11 = -2147467260;
  v16 = SetEvent(*(HANDLE *)(a1 + 184));
  v14 = retaddr;
  if ( !v16 )
  {
    v15 = 110;
    goto LABEL_26;
  }
LABEL_47:
  v24 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x1800526c0  mov     [rsp-18h+arg_10], rbx
0x1800526c5  mov     [rsp-18h+arg_18], rsi
0x1800526ca  push    rbp
0x1800526cb  push    rdi
0x1800526cc  push    r14
0x1800526ce  mov     rbp, rsp
0x1800526d1  sub     rsp, 60h
0x1800526d5  mov     rax, cs:__security_cookie
0x1800526dc  xor     rax, rsp
0x1800526df  mov     [rbp+var_10], rax
0x1800526e3  mov     r8, rdx
0x1800526e6  mov     rdi, rcx
0x1800526e9  mov     [rbp+var_30], 0
0x1800526f1  mov     rax, [rdx]
0x1800526f4  lea     rdx, [rbp+var_30]
0x1800526f8  mov     rcx, r8
0x1800526fb  mov     rax, [rax+50h]
0x1800526ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052704  mov     ebx, eax
0x180052706  test    eax, eax
0x180052708  jns     short loc_180052748
0x18005270a  mov     rcx, [rbp+18h]; this
0x18005270e  mov     r9d, eax; char *
0x180052711  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052718  mov     edx, 5Eh ; '^'; void *
0x18005271d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052722  nop
0x180052723  mov     rcx, [rbp+var_30]
0x180052727  test    rcx, rcx
0x18005272a  jz      short loc_180052741
0x18005272c  mov     [rbp+var_30], 0
0x180052734  mov     rax, [rcx]
0x180052737  mov     rax, [rax+10h]
0x18005273b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052740  nop
0x180052741  mov     eax, ebx
0x180052743  jmp     loc_180052A09
0x180052748  mov     [rbp+var_28], 0
0x18005274f  mov     rcx, [rbp+var_30]
0x180052753  mov     rax, [rcx]
0x180052756  lea     rdx, [rbp+var_28]
0x18005275a  mov     rax, [rax+30h]
0x18005275e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052763  mov     ebx, eax
0x180052765  test    eax, eax
0x180052767  jns     short loc_1800527A2
0x180052769  mov     rcx, [rbp+18h]; this
0x18005276d  mov     r9d, eax; char *
0x180052770  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052777  mov     edx, 61h ; 'a'; void *
0x18005277c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052781  nop
0x180052782  mov     rcx, [rbp+var_30]
0x180052786  test    rcx, rcx
0x180052789  jz      short loc_1800527A0
0x18005278b  mov     [rbp+var_30], 0
0x180052793  mov     rax, [rcx]
0x180052796  mov     rax, [rax+10h]
0x18005279a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005279f  nop
0x1800527a0  jmp     short loc_180052741
0x1800527a2  xorps   xmm0, xmm0
0x1800527a5  movsd   [rbp+var_20], xmm0
0x1800527aa  mov     rcx, [rbp+var_30]
0x1800527ae  mov     rax, [rcx]
0x1800527b1  lea     rdx, [rbp+var_20]
0x1800527b5  mov     rax, [rax+48h]
0x1800527b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527be  mov     ebx, eax
0x1800527c0  test    eax, eax
0x1800527c2  jns     short loc_180052800
0x1800527c4  mov     rcx, [rbp+18h]; this
0x1800527c8  mov     r9d, eax; char *
0x1800527cb  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x1800527d2  mov     edx, 64h ; 'd'; void *
0x1800527d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800527dc  nop
0x1800527dd  mov     rcx, [rbp+var_30]
0x1800527e1  test    rcx, rcx
0x1800527e4  jz      short loc_1800527FB
0x1800527e6  mov     [rbp+var_30], 0
0x1800527ee  mov     rax, [rcx]
0x1800527f1  mov     rax, [rax+10h]
0x1800527f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527fa  nop
0x1800527fb  jmp     loc_180052741
0x180052800  lea     rdx, [rdi+0C8h]
0x180052807  mov     eax, [rbp+var_28]
0x18005280a  cmp     eax, 6
0x18005280d  jnz     short loc_180052836
0x18005280f  mov     dword ptr [rdx], 0
0x180052815  mov     rcx, [rdi+0B8h]; hEvent
0x18005281c  call    cs:__imp_SetEvent
0x180052822  mov     rcx, [rbp+18h]
0x180052826  test    eax, eax
0x180052828  jnz     loc_1800529E9
0x18005282e  lea     edx, [rax+69h]
0x180052831  jmp     loc_18005290A
0x180052836  cmp     eax, 7
0x180052839  jnz     short loc_180052862
0x18005283b  mov     dword ptr [rdx], 80004004h
0x180052841  mov     rcx, [rdi+0B8h]; hEvent
0x180052848  call    cs:__imp_SetEvent
0x18005284e  mov     rcx, [rbp+18h]
0x180052852  test    eax, eax
0x180052854  jnz     loc_1800529E9
0x18005285a  lea     edx, [rax+6Eh]
0x18005285d  jmp     loc_18005290A
0x180052862  cmp     eax, 9
0x180052865  jnz     loc_18005291B
0x18005286b  cvttsd2si rax, [rbp+var_20]
0x180052871  mov     [rdi+0CCh], eax
0x180052877  mov     rcx, [rbp+var_30]
0x18005287b  mov     rax, [rcx]
0x18005287e  mov     rax, [rax+50h]
0x180052882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052887  mov     ebx, eax
0x180052889  test    eax, eax
0x18005288b  jns     short loc_1800528C9
0x18005288d  mov     rcx, [rbp+18h]; this
0x180052891  mov     r9d, eax; char *
0x180052894  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x18005289b  mov     edx, 74h ; 't'; void *
0x1800528a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800528a5  nop
0x1800528a6  mov     rcx, [rbp+var_30]
0x1800528aa  test    rcx, rcx
0x1800528ad  jz      short loc_1800528C4
0x1800528af  mov     [rbp+var_30], 0
0x1800528b7  mov     rax, [rcx]
0x1800528ba  mov     rax, [rax+10h]
0x1800528be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528c3  nop
0x1800528c4  jmp     loc_180052741
0x1800528c9  mov     qword ptr [rbp+DueTime], 0FFFFFFFFB8797400h
0x1800528d1  mov     [rsp+60h+fResume], 1; fResume
0x1800528d9  mov     [rsp+60h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x1800528e2  xor     r9d, r9d; pfnCompletionRoutine
0x1800528e5  xor     r8d, r8d; lPeriod
0x1800528e8  lea     rdx, [rbp+DueTime]; lpDueTime
0x1800528ec  mov     rcx, [rdi+0C0h]; hTimer
0x1800528f3  call    cs:__imp_SetWaitableTimer
0x1800528f9  mov     rcx, [rbp+18h]; this
0x1800528fd  test    eax, eax
0x1800528ff  jnz     loc_1800529E9
0x180052905  mov     edx, 0D3h; void *
0x18005290a  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052911  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180052916  jmp     loc_1800529E9
0x18005291b  cvttsd2si r14, [rbp+var_20]
0x180052921  cmp     dword ptr [rdx], 0
0x180052924  jge     short loc_18005295A
0x180052926  cmp     r14d, [rdi+0CCh]
0x18005292d  jbe     short loc_18005295A
0x18005292f  mov     dword ptr [rdx], 0
0x180052935  mov     rcx, [rdi+0C0h]; hTimer
0x18005293c  call    cs:__imp_CancelWaitableTimer
0x180052942  mov     rcx, [rbp+18h]; this
0x180052946  test    eax, eax
0x180052948  jnz     short loc_18005295A
0x18005294a  lea     r8, aOnecoreBaseLan_23; "onecore\\base\\languageoverlay\\service"...
0x180052951  lea     edx, [rax+7Fh]; void *
0x180052954  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180052959  nop
0x18005295a  lea     rcx, [rdi+10h]; _Mtx_t
0x18005295e  call    cs:__imp__Mtx_lock
0x180052964  test    eax, eax
0x180052966  jz      short loc_180052974
0x180052968  mov     ecx, 5
0x18005296d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180052973  int     3; Trap to Debugger
0x180052974  cmp     dword ptr [rdi+5Ch], 7FFFFFFFh
0x18005297b  jnz     short loc_180052990
0x18005297d  mov     dword ptr [rdi+5Ch], 7FFFFFFEh
0x180052984  mov     ecx, 6
0x180052989  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005298f  int     3; Trap to Debugger
0x180052990  mov     rbx, [rdi+60h]
0x180052994  lea     rcx, [rdi+10h]; _Mtx_t
0x180052998  call    cs:__imp__Mtx_unlock
0x18005299e  nop
0x18005299f  test    rbx, rbx
0x1800529a2  jz      short loc_1800529E9
0x1800529a4  mov     ecx, [rbp+var_28]
0x1800529a7  test    ecx, ecx
0x1800529a9  jz      short loc_1800529DA
0x1800529ab  sub     ecx, 1
0x1800529ae  jz      short loc_1800529D2
0x1800529b0  sub     ecx, 1
0x1800529b3  jz      short loc_1800529D2
0x1800529b5  sub     ecx, 1
0x1800529b8  jz      short loc_1800529CA
0x1800529ba  sub     ecx, 1
0x1800529bd  jz      short loc_1800529CA
0x1800529bf  cmp     ecx, 1
0x1800529c2  jnz     short loc_1800529DA
0x1800529c4  lea     r8d, [rcx+2]
0x1800529c8  jmp     short loc_1800529DD
0x1800529ca  mov     r8d, 2
0x1800529d0  jmp     short loc_1800529DD
0x1800529d2  mov     r8d, 1
0x1800529d8  jmp     short loc_1800529DD
0x1800529da  xor     r8d, r8d
0x1800529dd  mov     edx, r14d
0x1800529e0  mov     rcx, rdi
0x1800529e3  call    ?_NotifyProgressChanged@?$AdvancedProgressHandler@V?$function@$$A6AXIW4LanguagePackInstallProgressState@@@Z@std@@@@AEAAXIW4LanguagePackInstallProgressState@@@Z; AdvancedProgressHandler<std::function<void (uint,LanguagePackInstallProgressState)>>::_NotifyProgressChanged(uint,LanguagePackInstallProgressState)
0x1800529e8  nop
0x1800529e9  mov     rcx, [rbp+var_30]
0x1800529ed  test    rcx, rcx
0x1800529f0  jz      short loc_180052A07
0x1800529f2  mov     [rbp+var_30], 0
0x1800529fa  mov     rax, [rcx]
0x1800529fd  mov     rax, [rax+10h]
0x180052a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a06  nop
0x180052a07  xor     eax, eax
0x180052a09  mov     rcx, [rbp+var_10]
0x180052a0d  xor     rcx, rsp; StackCookie
0x180052a10  call    __security_check_cookie
0x180052a15  lea     r11, [rsp+60h+var_s0]
0x180052a1a  mov     rbx, [r11+30h]
0x180052a1e  mov     rsi, [r11+38h]
0x180052a22  mov     rsp, r11
0x180052a25  pop     r14
0x180052a27  pop     rdi
0x180052a28  pop     rbp
0x180052a29  retn
```
