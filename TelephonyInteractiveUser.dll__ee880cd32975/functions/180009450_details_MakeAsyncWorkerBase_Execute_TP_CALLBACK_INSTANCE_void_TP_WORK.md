# details::MakeAsyncWorkerBase::Execute(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180009450`
- end: `0x180009542`
- name: `?Execute@MakeAsyncWorkerBase@details@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `242`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009450`
- `0x18000cf20`
- `0x18000cf2c`
- `0x1800165c4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800094f2`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800094f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094c2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009498`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009498`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180009507`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180009507`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800094b8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800094b8`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000952c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000952c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18000946a`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18000946a`

## pseudocode

```c
void __fastcall details::MakeAsyncWorkerBase::Execute(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)
{
  __int64 v5; // rcx
  int v6; // ebx
  void *v7; // rdx
  signed int LastError; // eax
  bool v9; // sf
  HMODULE v10; // rdx
  void (__fastcall **v11)(_QWORD *, __int64); // rax

  v6 = RoInitialize(1, Context, Work);
  if ( v6 < 0 )
  {
    Log_AssertionEvent_1(v5, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h", 1182);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = (void *)Context[3];
  if ( !v7 || SetThreadToken(0, v7) )
  {
    (*(void (__fastcall **)(_QWORD *))(*Context + 8LL))(Context);
    if ( Context[3] )
    {
      if ( !RevertToSelf() )
      {
        LastError = GetLastError();
        v9 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v9 = LastError < 0;
        }
        if ( v9 )
          Log_HREvent_0((unsigned int)LastError, 0, "onecoreuap\\internal\\base\\inc\\wrlwinrthelpers.h");
      }
    }
  }
  CoDecrementMTAUsage(Context[4]);
  v10 = (HMODULE)Context[5];
  Context[4] = 0;
  FreeLibraryWhenCallbackReturns(Instance, v10);
  v11 = (void (__fastcall **)(_QWORD *, __int64))*Context;
  Context[5] = 0;
  (*v11)(Context, 1);
  if ( v6 >= 0 )
    RoUninitialize();
}

```

## disassembly

```asm
0x180009450  mov     [rsp+arg_0], rbx
0x180009455  mov     [rsp+arg_8], rsi
0x18000945a  push    rdi
0x18000945b  sub     rsp, 30h
0x18000945f  mov     rsi, rcx
0x180009462  mov     rdi, rdx
0x180009465  mov     ecx, 1
0x18000946a  call    cs:__imp_RoInitialize
0x180009470  mov     ebx, eax
0x180009472  test    eax, eax
0x180009474  jns     short loc_18000948D
0x180009476  mov     r8d, 49Eh
0x18000947c  lea     rdx, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x180009483  call    Log_AssertionEvent_1
0x180009488  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000948d  mov     rdx, [rdi+18h]; Token
0x180009491  test    rdx, rdx
0x180009494  jz      short loc_1800094A2
0x180009496  xor     ecx, ecx; Thread
0x180009498  call    cs:__imp_SetThreadToken
0x18000949e  test    eax, eax
0x1800094a0  jz      short loc_1800094EE
0x1800094a2  mov     rax, [rdi]
0x1800094a5  mov     rcx, rdi
0x1800094a8  mov     rax, [rax+8]
0x1800094ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b1  cmp     qword ptr [rdi+18h], 0
0x1800094b6  jz      short loc_1800094EE
0x1800094b8  call    cs:__imp_RevertToSelf
0x1800094be  test    eax, eax
0x1800094c0  jnz     short loc_1800094EE
0x1800094c2  call    cs:__imp_GetLastError
0x1800094c8  test    eax, eax
0x1800094ca  jle     short loc_1800094D6
0x1800094cc  movzx   eax, ax
0x1800094cf  or      eax, 80070000h
0x1800094d4  test    eax, eax
0x1800094d6  jns     short loc_1800094EE
0x1800094d8  mov     r9d, 48Bh
0x1800094de  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\base\\inc\\wrlwin"...
0x1800094e5  xor     edx, edx
0x1800094e7  mov     ecx, eax
0x1800094e9  call    Log_HREvent_0
0x1800094ee  mov     rcx, [rdi+20h]
0x1800094f2  call    cs:__imp_CoDecrementMTAUsage
0x1800094f8  mov     rdx, [rdi+28h]; mod
0x1800094fc  mov     rcx, rsi; pci
0x1800094ff  mov     qword ptr [rdi+20h], 0
0x180009507  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x18000950d  mov     rax, [rdi]
0x180009510  mov     edx, 1
0x180009515  mov     rcx, rdi
0x180009518  mov     qword ptr [rdi+28h], 0
0x180009520  mov     rax, [rax]
0x180009523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009528  test    ebx, ebx
0x18000952a  js      short loc_180009532
0x18000952c  call    cs:__imp_RoUninitialize
0x180009532  mov     rbx, [rsp+38h+arg_0]
0x180009537  mov     rsi, [rsp+38h+arg_8]
0x18000953c  add     rsp, 30h
0x180009540  pop     rdi
0x180009541  retn
```
