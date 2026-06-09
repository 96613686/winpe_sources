# wil::details::functor_wrapper_void__lambda_69d4ebafcdfc875e4eef5671220ca470___::Run

- ea: `0x18002a4e0`
- end: `0x18002a572`
- name: `wil::details::functor_wrapper_void__lambda_69d4ebafcdfc875e4eef5671220ca470___::Run`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180029640`

## callees

- `0x18001d95c`
- `0x18002a4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a511`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a532`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a532`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002a4ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002a4ff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a548`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002a548`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002a521`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002a521`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a52a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a52a`

## string_xrefs

- `0x18002a560`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingcontroller.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_69d4ebafcdfc875e4eef5671220ca470___::Run(__int64 a1)
{
  PVOID *v1; // r14
  PVOID v2; // rdi
  PTP_WORK ThreadpoolWork; // rax
  const char *v4; // r9
  struct _TP_WORK *v5; // rsi
  PTP_WORK v6; // rbp
  DWORD LastError; // ebx
  struct _TP_WORK *v8; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = *(PVOID **)(a1 + 8);
  v2 = *v1;
  ThreadpoolWork = CreateThreadpoolWork(
                     (PTP_WORK_CALLBACK)Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::s_PairingWorkerCallback,
                     *v1,
                     0);
  v5 = (struct _TP_WORK *)*((_QWORD *)v2 + 2);
  v6 = ThreadpoolWork;
  if ( v5 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v5, 1);
    CloseThreadpoolWork(v5);
    SetLastError(LastError);
  }
  *((_QWORD *)v2 + 2) = v6;
  v8 = (struct _TP_WORK *)*((_QWORD *)*v1 + 2);
  if ( !v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingcontroller.cpp",
      v4);
  SubmitThreadpoolWork(v8);
  return 0;
}

```

## disassembly

```asm
0x18002a4e0  push    rbx
0x18002a4e2  push    rbp
0x18002a4e3  push    rsi
0x18002a4e4  push    rdi
0x18002a4e5  push    r14
0x18002a4e7  sub     rsp, 20h
0x18002a4eb  mov     r14, [rcx+8]
0x18002a4ef  xor     r8d, r8d; pcbe
0x18002a4f2  lea     rcx, ?s_PairingWorkerCallback@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002a4f9  mov     rdi, [r14]
0x18002a4fc  mov     rdx, rdi; pv
0x18002a4ff  call    cs:__imp_CreateThreadpoolWork
0x18002a505  mov     rsi, [rdi+10h]
0x18002a509  mov     rbp, rax
0x18002a50c  test    rsi, rsi
0x18002a50f  jz      short loc_18002A538
0x18002a511  call    cs:__imp_GetLastError
0x18002a517  mov     edx, 1; fCancelPendingCallbacks
0x18002a51c  mov     rcx, rsi; pwk
0x18002a51f  mov     ebx, eax
0x18002a521  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002a527  mov     rcx, rsi; pwk
0x18002a52a  call    cs:__imp_CloseThreadpoolWork
0x18002a530  mov     ecx, ebx; dwErrCode
0x18002a532  call    cs:__imp_SetLastError
0x18002a538  mov     [rdi+10h], rbp
0x18002a53c  mov     rax, [r14]
0x18002a53f  mov     rcx, [rax+10h]; pwk
0x18002a543  test    rcx, rcx
0x18002a546  jz      short loc_18002A55B
0x18002a548  call    cs:__imp_SubmitThreadpoolWork
0x18002a54e  xor     eax, eax
0x18002a550  add     rsp, 20h
0x18002a554  pop     r14
0x18002a556  pop     rdi
0x18002a557  pop     rsi
0x18002a558  pop     rbp
0x18002a559  pop     rbx
0x18002a55a  retn
0x18002a55b  mov     rcx, [rsp+48h]; this
0x18002a560  lea     r8, aOnecoreDrivers_12; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002a567  mov     edx, 138h; void *
0x18002a56c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
