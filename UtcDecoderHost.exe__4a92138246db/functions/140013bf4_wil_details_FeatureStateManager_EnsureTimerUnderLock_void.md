# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140013bf4`
- end: `0x140013cc8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140014a90`

## callees

- `0x140013bf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013c73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013c7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013c73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c41`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013c62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140013c62`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140013c2f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140013c2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013c54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013cab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013c54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140013cab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013c6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013c6b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      v4 = pv[6];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[6] = v5;
      SetLastError(LastError);
    }
    v7 = pv[6];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x140013bf4  mov     [rsp+arg_8], rbx
0x140013bf9  mov     [rsp+arg_10], rbp
0x140013bfe  push    rsi
0x140013bff  push    rdi
0x140013c00  push    r14
0x140013c02  sub     rsp, 20h
0x140013c06  cmp     byte ptr [rcx+41h], 0
0x140013c0a  mov     rdi, rcx
0x140013c0d  jnz     loc_140013CB5
0x140013c13  cmp     qword ptr [rcx+30h], 0
0x140013c18  jnz     short loc_140013C85
0x140013c1a  call    cs:__imp_GetLastError
0x140013c20  xor     r8d, r8d; pcbe
0x140013c23  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140013c2a  mov     rdx, rdi; pv
0x140013c2d  mov     ebp, eax
0x140013c2f  call    cs:__imp_CreateThreadpoolTimer
0x140013c35  mov     rsi, [rdi+30h]
0x140013c39  mov     r14, rax
0x140013c3c  test    rsi, rsi
0x140013c3f  jz      short loc_140013C79
0x140013c41  call    cs:__imp_GetLastError
0x140013c47  xor     r9d, r9d; msWindowLength
0x140013c4a  xor     r8d, r8d; msPeriod
0x140013c4d  xor     edx, edx; pftDueTime
0x140013c4f  mov     rcx, rsi; pti
0x140013c52  mov     ebx, eax
0x140013c54  call    cs:__imp_SetThreadpoolTimer
0x140013c5a  mov     edx, 1; fCancelPendingCallbacks
0x140013c5f  mov     rcx, rsi; pti
0x140013c62  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013c68  mov     rcx, rsi; pti
0x140013c6b  call    cs:__imp_CloseThreadpoolTimer
0x140013c71  mov     ecx, ebx; dwErrCode
0x140013c73  call    cs:__imp_SetLastError
0x140013c79  mov     ecx, ebp; dwErrCode
0x140013c7b  mov     [rdi+30h], r14
0x140013c7f  call    cs:__imp_SetLastError
0x140013c85  mov     rcx, [rdi+30h]; pti
0x140013c89  test    rcx, rcx
0x140013c8c  jz      short loc_140013CB5
0x140013c8e  mov     rax, 0FFFFFFFF4D2FA200h
0x140013c98  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140013c9d  mov     r9d, 124F8h; msWindowLength
0x140013ca3  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140013ca8  xor     r8d, r8d; msPeriod
0x140013cab  call    cs:__imp_SetThreadpoolTimer
0x140013cb1  mov     byte ptr [rdi+41h], 1
0x140013cb5  mov     rbx, [rsp+38h+arg_8]
0x140013cba  mov     rbp, [rsp+38h+arg_10]
0x140013cbf  add     rsp, 20h
0x140013cc3  pop     r14
0x140013cc5  pop     rdi
0x140013cc6  pop     rsi
0x140013cc7  retn
```
