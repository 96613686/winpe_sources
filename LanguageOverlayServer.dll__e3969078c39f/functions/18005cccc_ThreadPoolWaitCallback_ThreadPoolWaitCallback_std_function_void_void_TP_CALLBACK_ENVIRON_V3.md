# ThreadPoolWaitCallback::ThreadPoolWaitCallback(std::function<void (void)> &&,_TP_CALLBACK_ENVIRON_V3 *)

- ea: `0x18005cccc`
- end: `0x18005ced5`
- name: `??0ThreadPoolWaitCallback@@QEAA@$$QEAV?$function@$$A6AXXZ@std@@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z`
- size: `521`
- prototype: `char *__fastcall(char *pv, __int64, struct _TP_CALLBACK_ENVIRON_V3 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18004fa80`

## callees

- `0x18000a008`
- `0x18000a6cc`
- `0x180011318`
- `0x18005cccc`
- `0x18005cff4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cde4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ce2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cde4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ce2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cdce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ce76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cdce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ce76`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005ce25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005ce65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005ce25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005ce65`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005cd7c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005cd7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005ce4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005ce4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005ce1c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005ce5c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005ce1c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005ce5c`

## string_xrefs

- `0x18005ce9f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005cec3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18005ceb1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\threadpoolwaitcallback.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
char *__fastcall ThreadPoolWaitCallback::ThreadPoolWaitCallback(
        char *pv,
        __int64 a2,
        struct _TP_CALLBACK_ENVIRON_V3 *a3)
{
  struct _TP_WAIT **v6; // rsi
  HANDLE *v7; // r14
  struct _TP_WAIT *ThreadpoolWait; // rdi
  const char *v9; // r9
  HANDLE v10; // rbp
  HANDLE v11; // rbx
  DWORD LastError; // r12d
  const char *v13; // r9
  struct _TP_WAIT *v14; // rbp
  DWORD v15; // ebx
  const char *v16; // r9
  HANDLE hObject; // [rsp+20h] [rbp-38h] BYREF
  struct _TP_WAIT *v19; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v21; // [rsp+78h] [rbp+20h] BYREF

  *(_QWORD *)pv = &ThreadPoolWaitCallback::`vftable';
  v6 = (struct _TP_WAIT **)(pv + 8);
  *((_QWORD *)pv + 1) = 0;
  *((_QWORD *)pv + 9) = 0;
  *((_QWORD *)pv + 10) = 258;
  *(_OWORD *)(pv + 104) = 0;
  *(_OWORD *)(pv + 120) = 0;
  *(_OWORD *)(pv + 136) = 0;
  *((_QWORD *)pv + 11) = 0;
  *((_QWORD *)pv + 12) = 0;
  *((_DWORD *)pv + 38) = -1;
  *((_DWORD *)pv + 39) = 0;
  v7 = (HANDLE *)(pv + 160);
  *((_QWORD *)pv + 20) = 0;
  v21 = 0;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    &hObject,
    &v21);
  ThreadpoolWait = CreateThreadpoolWait(ThreadPoolWaitCallback::_OnWaitCallback, pv, a3);
  v19 = ThreadpoolWait;
  if ( !ThreadpoolWait )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\threadpoolwaitcallback.cpp",
      v9);
  std::function<void (void)>::operator=(pv + 16, a2);
  if ( v7 != &hObject )
  {
    v10 = hObject;
    v11 = *v7;
    if ( *v7 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v13);
      SetLastError(LastError);
    }
    *v7 = v10;
    hObject = 0;
  }
  if ( v6 != &v19 )
  {
    v14 = *v6;
    if ( *v6 )
    {
      v15 = GetLastError();
      WaitForThreadpoolWaitCallbacks(v14, 1);
      CloseThreadpoolWait(v14);
      SetLastError(v15);
    }
    *v6 = ThreadpoolWait;
    v19 = 0;
    ThreadpoolWait = 0;
  }
  SetThreadpoolWait(*v6, *v7, 0);
  if ( ThreadpoolWait )
  {
    WaitForThreadpoolWaitCallbacks(ThreadpoolWait, 1);
    CloseThreadpoolWait(ThreadpoolWait);
  }
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v16);
  return pv;
}

```

## disassembly

```asm
0x18005cccc  mov     r11, rsp
0x18005cccf  mov     [r11+10h], rbx
0x18005ccd3  mov     [r11+18h], rbp
0x18005ccd7  mov     [r11+8], rcx
0x18005ccdb  push    rsi
0x18005ccdc  push    rdi
0x18005ccdd  push    r12
0x18005ccdf  push    r14
0x18005cce1  push    r15
0x18005cce3  sub     rsp, 30h
0x18005cce7  mov     rbx, r8
0x18005ccea  mov     r12, rdx
0x18005cced  mov     r15, rcx
0x18005ccf0  lea     rax, ??_7ThreadPoolWaitCallback@@6B@; const ThreadPoolWaitCallback::`vftable'
0x18005ccf7  mov     [rcx], rax
0x18005ccfa  lea     rsi, [rcx+8]
0x18005ccfe  mov     qword ptr [rsi], 0
0x18005cd05  mov     qword ptr [rcx+48h], 0
0x18005cd0d  mov     qword ptr [rcx+50h], 102h
0x18005cd15  xorps   xmm0, xmm0
0x18005cd18  movups  xmmword ptr [rcx+68h], xmm0
0x18005cd1c  movups  xmmword ptr [rcx+78h], xmm0
0x18005cd20  movups  xmmword ptr [rcx+88h], xmm0
0x18005cd27  mov     qword ptr [rcx+58h], 0
0x18005cd2f  mov     qword ptr [rcx+60h], 0
0x18005cd37  mov     dword ptr [rcx+98h], 0FFFFFFFFh
0x18005cd41  mov     dword ptr [rcx+9Ch], 0
0x18005cd4b  lea     r14, [rcx+0A0h]
0x18005cd52  mov     qword ptr [r14], 0
0x18005cd59  mov     [rsp+58h+arg_18], 0
0x18005cd61  lea     rdx, [r11+20h]
0x18005cd65  lea     rcx, [r11-38h]
0x18005cd69  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18005cd6e  nop
0x18005cd6f  mov     r8, rbx; pcbe
0x18005cd72  mov     rdx, r15; pv
0x18005cd75  lea     rcx, ?_OnWaitCallback@ThreadPoolWaitCallback@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005cd7c  call    cs:__imp_CreateThreadpoolWait
0x18005cd82  mov     rdi, rax
0x18005cd85  mov     [rsp+58h+var_30], rax
0x18005cd8a  xor     eax, eax
0x18005cd8c  test    rdi, rdi
0x18005cd8f  setnz   al
0x18005cd92  mov     rcx, [rsp+58h]; this
0x18005cd97  test    eax, eax
0x18005cd99  jz      loc_18005CEB1
0x18005cd9f  mov     rdx, r12
0x18005cda2  lea     rcx, [r15+10h]
0x18005cda6  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18005cdab  lea     rax, [rsp+58h+hObject]
0x18005cdb0  cmp     r14, rax
0x18005cdb3  jz      short loc_18005CDF6
0x18005cdb5  mov     rbp, [rsp+58h+hObject]
0x18005cdba  mov     rbx, [r14]
0x18005cdbd  test    rbx, rbx
0x18005cdc0  jz      short loc_18005CDEA
0x18005cdc2  call    cs:__imp_GetLastError
0x18005cdc8  mov     r12d, eax
0x18005cdcb  mov     rcx, rbx; hObject
0x18005cdce  call    cs:__imp_CloseHandle
0x18005cdd4  mov     rcx, [rsp+58h]; this
0x18005cdd9  test    eax, eax
0x18005cddb  jz      loc_18005CEC3
0x18005cde1  mov     ecx, r12d; dwErrCode
0x18005cde4  call    cs:__imp_SetLastError
0x18005cdea  mov     [r14], rbp
0x18005cded  mov     [rsp+58h+hObject], 0
0x18005cdf6  lea     rax, [rsp+58h+var_30]
0x18005cdfb  mov     r12d, 1
0x18005ce01  cmp     rsi, rax
0x18005ce04  jz      short loc_18005CE41
0x18005ce06  mov     rbp, [rsi]
0x18005ce09  test    rbp, rbp
0x18005ce0c  jz      short loc_18005CE33
0x18005ce0e  call    cs:__imp_GetLastError
0x18005ce14  mov     ebx, eax
0x18005ce16  mov     edx, r12d; fCancelPendingCallbacks
0x18005ce19  mov     rcx, rbp; pwa
0x18005ce1c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005ce22  mov     rcx, rbp; pwa
0x18005ce25  call    cs:__imp_CloseThreadpoolWait
0x18005ce2b  mov     ecx, ebx; dwErrCode
0x18005ce2d  call    cs:__imp_SetLastError
0x18005ce33  mov     [rsi], rdi
0x18005ce36  mov     [rsp+58h+var_30], 0
0x18005ce3f  xor     edi, edi
0x18005ce41  xor     r8d, r8d; pftTimeout
0x18005ce44  mov     rdx, [r14]; h
0x18005ce47  mov     rcx, [rsi]; pwa
0x18005ce4a  call    cs:__imp_SetThreadpoolWait
0x18005ce50  nop
0x18005ce51  test    rdi, rdi
0x18005ce54  jz      short loc_18005CE6C
0x18005ce56  mov     edx, r12d; fCancelPendingCallbacks
0x18005ce59  mov     rcx, rdi; pwa
0x18005ce5c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005ce62  mov     rcx, rdi; pwa
0x18005ce65  call    cs:__imp_CloseThreadpoolWait
0x18005ce6b  nop
0x18005ce6c  mov     rcx, [rsp+58h+hObject]; hObject
0x18005ce71  test    rcx, rcx
0x18005ce74  jz      short loc_18005CE85
0x18005ce76  call    cs:__imp_CloseHandle
0x18005ce7c  mov     rcx, [rsp+58h]; this
0x18005ce81  test    eax, eax
0x18005ce83  jz      short loc_18005CE9F
0x18005ce85  mov     rax, r15
0x18005ce88  mov     rbx, [rsp+58h+arg_8]
0x18005ce8d  mov     rbp, [rsp+58h+arg_10]
0x18005ce92  add     rsp, 30h
0x18005ce96  pop     r15
0x18005ce98  pop     r14
0x18005ce9a  pop     r12
0x18005ce9c  pop     rdi
0x18005ce9d  pop     rsi
0x18005ce9e  retn
0x18005ce9f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005cea6  mov     edx, 0A0Bh; void *
0x18005ceab  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005ceb1  lea     r8, aOnecoreBaseLan_7; "onecore\\base\\languageoverlay\\service"...
0x18005ceb8  mov     edx, 3Fh ; '?'; void *
0x18005cebd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005cec3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005ceca  mov     edx, 0A0Bh; void *
0x18005cecf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
