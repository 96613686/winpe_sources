# PhoneController::DispatchWork(IUnknown *)

- ea: `0x180024c00`
- end: `0x180024dcf`
- name: `?DispatchWork@PhoneController@@UEAAXPEAUIUnknown@@@Z`
- size: `463`
- prototype: `void __fastcall(PhoneController *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1800056a0`
- `0x18001d79c`
- `0x180024c00`
- `0x180025ae4`
- `0x18002c574`
- `0x18002c580`
- `0x180031f6c`
- `0x1800454bc`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024d63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024d63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024d7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024d7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180024d71`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180024d71`

## string_xrefs

- `0x180024c60`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180024cbb`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
void __fastcall PhoneController::DispatchWork(PhoneController *this, struct IUnknown *a2)
{
  struct ControllerMessage *v3; // r8
  int v4; // eax
  struct _TP_TIMER *v5; // rbx
  struct ControllerMessage *v6; // [rsp+30h] [rbp-9h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-1h] BYREF
  __int128 v8; // [rsp+48h] [rbp+Fh] BYREF
  _QWORD pv[2]; // [rsp+58h] [rbp+1Fh] BYREF
  PTP_TIMER pti; // [rsp+68h] [rbp+2Fh]
  __int64 v11; // [rsp+70h] [rbp+37h]
  HLOCAL hMem; // [rsp+78h] [rbp+3Fh]
  __int64 v13; // [rsp+80h] [rbp+47h]

  v6 = 0;
  if ( !a2
    || (((void (__fastcall *)(struct IUnknown *, GUID *, struct ControllerMessage **))a2->lpVtbl->QueryInterface)(
          a2,
          &GUID_e8fad244_598d_47b7_84a9_af5909879447,
          &v6),
        (v3 = v6) == 0) )
  {
    Log_AssertionEvent_3(this, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7921);
    v3 = v6;
    if ( !v6 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v3 = v6;
    }
  }
  Block[0] = &v8;
  v8 = 0;
  LOBYTE(v8) = 0;
  Block[1] = &v8;
  v4 = tlx::assign_sprintf<char,utl::char_traits<char>,utl::allocator<char>>(Block, "%u", *((_DWORD *)v3 + 6));
  if ( v4 < 0 )
    Log_HREvent_7((unsigned int)v4, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7924);
  pv[0] = &OperationWatchdog::`vftable';
  v11 = 0;
  v13 = 0;
  pv[1] = 0;
  pti = 0;
  hMem = 0;
  OperationWatchdog::Start(pv, 11, (const char *)Block[0], 10000);
  PhoneController::_ProcessControllerMessage((PhoneController *)((char *)this - 16), v6);
  OperationWatchdog::End((OperationWatchdog *)pv);
  pv[0] = &OperationWatchdog::`vftable';
  OperationWatchdog::End((OperationWatchdog *)pv);
  if ( hMem )
    LocalFree(hMem);
  v5 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
  }
  if ( Block[0] != &v8 )
    operator delete(Block[0]);
  if ( v6 )
    (*(void (__fastcall **)(struct ControllerMessage *))(*(_QWORD *)v6 + 16LL))(v6);
}

```

## disassembly

```asm
0x180024c00  mov     [rsp-8+arg_10], rbx
0x180024c05  mov     [rsp-8+arg_18], rdi
0x180024c0a  push    rbp
0x180024c0b  lea     rbp, [rsp-57h]
0x180024c10  sub     rsp, 90h
0x180024c17  mov     rax, cs:__security_cookie
0x180024c1e  xor     rax, rsp
0x180024c21  mov     [rbp+57h+var_8], rax
0x180024c25  mov     [rbp+57h+var_60], 0
0x180024c2d  mov     r9, rdx
0x180024c30  mov     rbx, rcx
0x180024c33  test    rdx, rdx
0x180024c36  jz      short loc_180024C5A
0x180024c38  mov     rax, [rdx]
0x180024c3b  lea     r8, [rbp+57h+var_60]
0x180024c3f  lea     rdx, _GUID_e8fad244_598d_47b7_84a9_af5909879447
0x180024c46  mov     rcx, r9
0x180024c49  mov     rax, [rax]
0x180024c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c51  mov     r8, [rbp+57h+var_60]
0x180024c55  test    r8, r8
0x180024c58  jnz     short loc_180024C7E
0x180024c5a  mov     r8d, 1EF1h
0x180024c60  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180024c67  call    Log_AssertionEvent_3
0x180024c6c  mov     r8, [rbp+57h+var_60]
0x180024c70  test    r8, r8
0x180024c73  jnz     short loc_180024C7E
0x180024c75  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024c7a  mov     r8, [rbp+57h+var_60]
0x180024c7e  xorps   xmm0, xmm0
0x180024c81  lea     rax, [rbp+57h+var_48]
0x180024c85  movups  xmmword ptr [rbp+57h+Block], xmm0
0x180024c89  mov     [rbp+57h+Block], rax
0x180024c8d  lea     rdx, aU_0; "%u"
0x180024c94  movups  [rbp+57h+var_48], xmm0
0x180024c98  lea     rax, [rbp+57h+var_48]
0x180024c9c  mov     byte ptr [rbp+57h+var_48], 0
0x180024ca0  mov     [rbp+57h+Block+8], rax
0x180024ca4  lea     rcx, [rbp+57h+Block]
0x180024ca8  mov     r8d, [r8+18h]
0x180024cac  call    ??$assign_sprintf@DU?$char_traits@D@utl@@V?$allocator@D@2@@tlx@@YAJAEAV?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@PEBDZZ; tlx::assign_sprintf<char,utl::char_traits<char>,utl::allocator<char>>(utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>> &,char const *,...)
0x180024cb1  test    eax, eax
0x180024cb3  jns     short loc_180024CCB
0x180024cb5  mov     r9d, 1EF4h
0x180024cbb  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180024cc2  xor     edx, edx
0x180024cc4  mov     ecx, eax
0x180024cc6  call    Log_HREvent_7
0x180024ccb  mov     r8, [rbp+57h+Block]; char *
0x180024ccf  lea     rdi, ??_7OperationWatchdog@@6B@; const OperationWatchdog::`vftable'
0x180024cd6  mov     [rbp+57h+pv], rdi
0x180024cda  lea     rcx, [rbp+57h+pv]; pv
0x180024cde  mov     [rbp+57h+var_20], 0
0x180024ce6  mov     r9d, 2710h; unsigned int
0x180024cec  mov     [rbp+57h+var_10], 0
0x180024cf4  mov     edx, 0Bh; unsigned int
0x180024cf9  mov     [rbp+57h+var_30], 0
0x180024d01  mov     [rbp+57h+pti], 0
0x180024d09  mov     [rbp+57h+hMem], 0
0x180024d11  mov     dword ptr [rbp+57h+var_10+4], 0
0x180024d18  call    ?Start@OperationWatchdog@@QEAAXIPEBDKK@Z; OperationWatchdog::Start(uint,char const *,ulong,ulong)
0x180024d1d  mov     rdx, [rbp+57h+var_60]; struct ControllerMessage *
0x180024d21  lea     rcx, [rbx-10h]; this
0x180024d25  call    ?_ProcessControllerMessage@PhoneController@@IEAAXPEAVControllerMessage@@@Z; PhoneController::_ProcessControllerMessage(ControllerMessage *)
0x180024d2a  lea     rcx, [rbp+57h+pv]; this
0x180024d2e  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180024d33  lea     rcx, [rbp+57h+pv]; this
0x180024d37  mov     [rbp+57h+pv], rdi
0x180024d3b  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180024d40  mov     rcx, [rbp+57h+hMem]; hMem
0x180024d44  test    rcx, rcx
0x180024d47  jz      short loc_180024D4F
0x180024d49  call    cs:__imp_LocalFree
0x180024d4f  mov     rbx, [rbp+57h+pti]
0x180024d53  test    rbx, rbx
0x180024d56  jz      short loc_180024D80
0x180024d58  xor     r9d, r9d; msWindowLength
0x180024d5b  xor     r8d, r8d; msPeriod
0x180024d5e  xor     edx, edx; pftDueTime
0x180024d60  mov     rcx, rbx; pti
0x180024d63  call    cs:__imp_SetThreadpoolTimer
0x180024d69  mov     edx, 1; fCancelPendingCallbacks
0x180024d6e  mov     rcx, rbx; pti
0x180024d71  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180024d77  mov     rcx, rbx; pti
0x180024d7a  call    cs:__imp_CloseThreadpoolTimer
0x180024d80  mov     rcx, [rbp+57h+Block]; Block
0x180024d84  lea     rax, [rbp+57h+var_48]
0x180024d88  cmp     rcx, rax
0x180024d8b  jz      short loc_180024D99
0x180024d8d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180024d94  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024d99  mov     rcx, [rbp+57h+var_60]
0x180024d9d  test    rcx, rcx
0x180024da0  jz      short loc_180024DAE
0x180024da2  mov     rax, [rcx]
0x180024da5  mov     rax, [rax+10h]
0x180024da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dae  mov     rcx, [rbp+57h+var_8]
0x180024db2  xor     rcx, rsp; StackCookie
0x180024db5  call    __security_check_cookie
0x180024dba  lea     r11, [rsp+90h+var_s0]
0x180024dc2  mov     rbx, [r11+20h]
0x180024dc6  mov     rdi, [r11+28h]
0x180024dca  mov     rsp, r11
0x180024dcd  pop     rbp
0x180024dce  retn
```
