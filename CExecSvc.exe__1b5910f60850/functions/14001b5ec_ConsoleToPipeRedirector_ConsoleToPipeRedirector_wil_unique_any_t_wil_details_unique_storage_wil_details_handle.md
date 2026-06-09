# ConsoleToPipeRedirector::ConsoleToPipeRedirector(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ushort,ushort,ushort,ushort)

- ea: `0x14001b5ec`
- end: `0x14001b7fe`
- name: `??0ConsoleToPipeRedirector@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@00GGGG@Z`
- size: `530`
- prototype: `char *__fastcall(char *pv, __int64 *, _QWORD *, _QWORD *, __int16, __int16, __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140016cc0`

## callees

- `0x14000e828`
- `0x140014f3c`
- `0x14001b5ec`
- `0x14001eb64`
- `0x14001ed38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b6ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b6ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b744`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001b6ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001b71c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001b756`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001b6ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001b71c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001b756`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001b6d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001b6d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001b6fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001b6fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001b714`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001b714`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x14001b689`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x14001b689`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14001b6a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x14001b6a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001b70b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001b70b`

## string_xrefs

- `0x14001b7c8`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`
- `0x14001b7da`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`
- `0x14001b7ec`: `onecore\vm\compute\service\cexec\lib\consoletostream.cpp`

## pseudocode

```c
char *__fastcall ConsoleToPipeRedirector::ConsoleToPipeRedirector(
        char *pv,
        __int64 *a2,
        _QWORD *a3,
        _QWORD *a4,
        __int16 a5,
        __int16 a6,
        __int16 a7,
        unsigned __int16 a8)
{
  char *v10; // rcx
  PTP_IO ThreadpoolIo; // rsi
  const char *v12; // r9
  struct _TP_IO *v13; // rbp
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rbp
  const char *v16; // r9
  struct _TP_TIMER *v17; // rsi
  DWORD v18; // ebx
  __int64 v19; // rbp
  void *v20; // rsi
  DWORD v21; // ebx
  int Console; // eax
  int v24; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)pv = 0;
  *((_WORD *)pv + 4) = 0;
  *((_DWORD *)pv + 3) = 0;
  *((_QWORD *)pv + 2) = 0;
  *((_DWORD *)pv + 6) = 0;
  *((_QWORD *)pv + 4) = 0;
  *((_QWORD *)pv + 5) = 0;
  *((_QWORD *)pv + 6) = *a3;
  *a3 = -1;
  *((_QWORD *)pv + 7) = *a4;
  *a4 = -1;
  *((_QWORD *)pv + 8) = 0;
  *((_QWORD *)pv + 9) = 0;
  *((_QWORD *)pv + 10) = 0;
  *(_OWORD *)(pv + 344) = 0;
  *(_OWORD *)(pv + 360) = 0;
  pv[376] = 0;
  v10 = (char *)*((_QWORD *)pv + 6);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ThreadpoolIo = CreateThreadpoolIo(v10, ConsoleToPipeRedirector::ReadCompleteCallback, pv, 0);
    v13 = (struct _TP_IO *)*((_QWORD *)pv + 8);
    if ( v13 )
    {
      LastError = GetLastError();
      CloseThreadpoolIo(v13);
      SetLastError(LastError);
    }
    *((_QWORD *)pv + 8) = ThreadpoolIo;
    if ( !ThreadpoolIo )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x99,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\consoletostream.cpp",
        v12);
    ThreadpoolTimer = CreateThreadpoolTimer(lambda_1f9302160d04f2df91acab1b083512b3_::_lambda_invoker_cdecl_, pv, 0);
    v17 = (struct _TP_TIMER *)*((_QWORD *)pv + 9);
    if ( v17 )
    {
      v18 = GetLastError();
      SetThreadpoolTimer(v17, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v17, 1);
      CloseThreadpoolTimer(v17);
      SetLastError(v18);
    }
    *((_QWORD *)pv + 9) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\consoletostream.cpp",
        v16);
  }
  v19 = *a2;
  v20 = *(void **)pv;
  if ( *(_QWORD *)pv )
  {
    v21 = GetLastError();
    CsCloseConsole(v20);
    SetLastError(v21);
  }
  *(_QWORD *)pv = 0;
  LOWORD(v24) = a7;
  Console = CsCreateConsole(pv, v19, pv, a8);
  if ( Console < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\consoletostream.cpp",
      (const char *)(unsigned int)Console,
      v24);
  *a2 = -1;
  pv[376] = 1;
  return pv;
}

```

## disassembly

```asm
0x14001b5ec  mov     [rsp+arg_0], rcx
0x14001b5f1  push    rbx
0x14001b5f2  push    rbp
0x14001b5f3  push    rsi
0x14001b5f4  push    rdi
0x14001b5f5  push    r12
0x14001b5f7  push    r14
0x14001b5f9  sub     rsp, 48h
0x14001b5fd  mov     r14, rdx
0x14001b600  mov     rdi, rcx
0x14001b603  mov     qword ptr [rcx], 0
0x14001b60a  xor     eax, eax
0x14001b60c  mov     [rcx+8], ax
0x14001b610  mov     [rcx+0Ch], eax
0x14001b613  mov     [rcx+10h], rax
0x14001b617  mov     [rcx+18h], eax
0x14001b61a  mov     [rcx+20h], rax
0x14001b61e  mov     [rcx+28h], rax
0x14001b622  mov     rax, [r8]
0x14001b625  mov     [rcx+30h], rax
0x14001b629  or      r12, 0FFFFFFFFFFFFFFFFh
0x14001b62d  mov     [r8], r12
0x14001b630  mov     rax, [r9]
0x14001b633  mov     [rcx+38h], rax
0x14001b637  mov     [r9], r12
0x14001b63a  mov     qword ptr [rcx+40h], 0
0x14001b642  mov     qword ptr [rcx+48h], 0
0x14001b64a  mov     qword ptr [rcx+50h], 0
0x14001b652  xorps   xmm0, xmm0
0x14001b655  movups  xmmword ptr [rcx+158h], xmm0
0x14001b65c  movups  xmmword ptr [rcx+168h], xmm0
0x14001b663  mov     byte ptr [rcx+178h], 0
0x14001b66a  mov     rcx, [rcx+30h]; fl
0x14001b66e  lea     rax, [rcx-1]
0x14001b672  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001b676  ja      loc_14001B739
0x14001b67c  xor     r9d, r9d; pcbe
0x14001b67f  mov     r8, rdi; pv
0x14001b682  lea     rdx, ?ReadCompleteCallback@ConsoleToPipeRedirector@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x14001b689  call    cs:__imp_CreateThreadpoolIo
0x14001b68f  mov     rsi, rax
0x14001b692  mov     rbp, [rdi+40h]
0x14001b696  test    rbp, rbp
0x14001b699  jz      short loc_14001B6B4
0x14001b69b  call    cs:__imp_GetLastError
0x14001b6a1  mov     ebx, eax
0x14001b6a3  mov     rcx, rbp; pio
0x14001b6a6  call    cs:__imp_CloseThreadpoolIo
0x14001b6ac  mov     ecx, ebx; dwErrCode
0x14001b6ae  call    cs:__imp_SetLastError
0x14001b6b4  mov     [rdi+40h], rsi
0x14001b6b8  test    rsi, rsi
0x14001b6bb  setz    al
0x14001b6be  mov     rcx, [rsp+78h]; this
0x14001b6c3  test    al, al
0x14001b6c5  jnz     loc_14001B7DA
0x14001b6cb  xor     r8d, r8d; pcbe
0x14001b6ce  mov     rdx, rdi; pv
0x14001b6d1  lea     rcx, _lambda_1f9302160d04f2df91acab1b083512b3____lambda_invoker_cdecl_; pfnti
0x14001b6d8  call    cs:__imp_CreateThreadpoolTimer
0x14001b6de  mov     rbp, rax
0x14001b6e1  mov     rsi, [rdi+48h]
0x14001b6e5  test    rsi, rsi
0x14001b6e8  jz      short loc_14001B722
0x14001b6ea  call    cs:__imp_GetLastError
0x14001b6f0  mov     ebx, eax
0x14001b6f2  xor     r9d, r9d; msWindowLength
0x14001b6f5  xor     r8d, r8d; msPeriod
0x14001b6f8  xor     edx, edx; pftDueTime
0x14001b6fa  mov     rcx, rsi; pti
0x14001b6fd  call    cs:__imp_SetThreadpoolTimer
0x14001b703  mov     edx, 1; fCancelPendingCallbacks
0x14001b708  mov     rcx, rsi; pti
0x14001b70b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14001b711  mov     rcx, rsi; pti
0x14001b714  call    cs:__imp_CloseThreadpoolTimer
0x14001b71a  mov     ecx, ebx; dwErrCode
0x14001b71c  call    cs:__imp_SetLastError
0x14001b722  mov     [rdi+48h], rbp
0x14001b726  test    rbp, rbp
0x14001b729  setz    al
0x14001b72c  mov     rcx, [rsp+78h]; this
0x14001b731  test    al, al
0x14001b733  jnz     loc_14001B7EC
0x14001b739  mov     rbp, [r14]
0x14001b73c  mov     rsi, [rdi]
0x14001b73f  test    rsi, rsi
0x14001b742  jz      short loc_14001B75D
0x14001b744  call    cs:__imp_GetLastError
0x14001b74a  mov     ebx, eax
0x14001b74c  mov     rcx, rsi; P
0x14001b74f  call    CsCloseConsole
0x14001b754  mov     ecx, ebx; dwErrCode
0x14001b756  call    cs:__imp_SetLastError
0x14001b75c  nop
0x14001b75d  mov     qword ptr [rdi], 0
0x14001b764  movzx   eax, [rsp+78h+arg_20]
0x14001b76c  mov     [rsp+78h+var_48], ax
0x14001b771  movzx   eax, [rsp+78h+arg_28]
0x14001b779  mov     [rsp+78h+var_50], ax
0x14001b77e  movzx   eax, [rsp+78h+arg_30]
0x14001b786  mov     word ptr [rsp+78h+var_58], ax; int
0x14001b78b  movzx   r9d, [rsp+78h+arg_38]
0x14001b794  mov     r8, rdi
0x14001b797  mov     rdx, rbp
0x14001b79a  mov     rcx, rdi
0x14001b79d  call    CsCreateConsole
0x14001b7a2  mov     rcx, [rsp+78h]; this
0x14001b7a7  test    eax, eax
0x14001b7a9  js      short loc_14001B7C5
0x14001b7ab  mov     [r14], r12
0x14001b7ae  mov     byte ptr [rdi+178h], 1
0x14001b7b5  mov     rax, rdi
0x14001b7b8  add     rsp, 48h
0x14001b7bc  pop     r14
0x14001b7be  pop     r12
0x14001b7c0  pop     rdi
0x14001b7c1  pop     rsi
0x14001b7c2  pop     rbp
0x14001b7c3  pop     rbx
0x14001b7c4  retn
0x14001b7c5  mov     r9d, eax; char *
0x14001b7c8  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001b7cf  mov     edx, 0AAh; void *
0x14001b7d4  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14001b7da  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001b7e1  mov     edx, 99h; void *
0x14001b7e6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14001b7ec  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14001b7f3  mov     edx, 0A0h; void *
0x14001b7f8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
