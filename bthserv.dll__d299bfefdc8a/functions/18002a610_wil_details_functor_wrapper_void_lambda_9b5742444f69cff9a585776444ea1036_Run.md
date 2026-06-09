# wil::details::functor_wrapper_void__lambda_9b5742444f69cff9a585776444ea1036___::Run

- ea: `0x18002a610`
- end: `0x18002a733`
- name: `wil::details::functor_wrapper_void__lambda_9b5742444f69cff9a585776444ea1036___::Run`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800296c8`

## callees

- `0x180001b60`
- `0x180010e0c`
- `0x1800110fc`
- `0x180029920`
- `0x18002a610`
- `0x18002efa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a630`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a64e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a64e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002a63d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002a63d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a646`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a646`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_9b5742444f69cff9a585776444ea1036___::Run(__int64 a1)
{
  __int64 *v1; // rdi
  char v2; // si
  __int64 v3; // r14
  struct _TP_WORK *v4; // rbp
  DWORD LastError; // ebx
  __int64 **v6; // rcx
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *v7; // rbx
  _QWORD *v8; // rax

  v1 = *(__int64 **)(a1 + 8);
  v2 = 1;
  v3 = *v1;
  v4 = *(struct _TP_WORK **)(*v1 + 16);
  if ( v4 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v4, 1);
    CloseThreadpoolWork(v4);
    SetLastError(LastError);
  }
  *(_QWORD *)(v3 + 16) = 0;
  v6 = *(__int64 ***)(*v1 + 88);
  if ( v6 )
  {
    Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(v6);
    *(_QWORD *)(*v1 + 88) = 0;
  }
  v7 = *(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor **)(*v1 + 40);
  *(_QWORD *)(*v1 + 40) = 0;
  if ( v7 )
  {
    Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(v7);
    operator delete(v7, (const struct std::nothrow_t *)0x48);
  }
  v8 = *(_QWORD **)(*v1 + 24);
  if ( v8 && (unsigned __int64)(*v8 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      v2 = 0;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
      *v1 + 24,
      -1);
  }
  return 0;
}

```

## disassembly

```asm
0x18002a610  push    rbx
0x18002a612  push    rbp
0x18002a613  push    rsi
0x18002a614  push    rdi
0x18002a615  push    r14
0x18002a617  sub     rsp, 50h
0x18002a61b  mov     rdi, [rcx+8]
0x18002a61f  mov     esi, 1
0x18002a624  mov     r14, [rdi]
0x18002a627  mov     rbp, [r14+10h]
0x18002a62b  test    rbp, rbp
0x18002a62e  jz      short loc_18002A654
0x18002a630  call    cs:__imp_GetLastError
0x18002a636  mov     edx, esi; fCancelPendingCallbacks
0x18002a638  mov     rcx, rbp; pwk
0x18002a63b  mov     ebx, eax
0x18002a63d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002a643  mov     rcx, rbp; pwk
0x18002a646  call    cs:__imp_CloseThreadpoolWork
0x18002a64c  mov     ecx, ebx; dwErrCode
0x18002a64e  call    cs:__imp_SetLastError
0x18002a654  mov     qword ptr [r14+10h], 0
0x18002a65c  mov     rax, [rdi]
0x18002a65f  mov     rcx, [rax+58h]; this
0x18002a663  test    rcx, rcx
0x18002a666  jz      short loc_18002A678
0x18002a668  call    ?Stop@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(void)
0x18002a66d  mov     rax, [rdi]
0x18002a670  mov     qword ptr [rax+58h], 0
0x18002a678  mov     rax, [rdi]
0x18002a67b  mov     rbx, [rax+28h]
0x18002a67f  mov     qword ptr [rax+28h], 0
0x18002a687  test    rbx, rbx
0x18002a68a  jz      short loc_18002A6A1
0x18002a68c  mov     rcx, rbx; this
0x18002a68f  call    ??1BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(void)
0x18002a694  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x18002a699  mov     rcx, rbx; void *
0x18002a69c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a6a1  mov     rax, [rdi]
0x18002a6a4  mov     rax, [rax+18h]
0x18002a6a8  test    rax, rax
0x18002a6ab  jz      short loc_18002A726
0x18002a6ad  mov     rax, [rax]
0x18002a6b0  sub     rax, rsi
0x18002a6b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a6b7  ja      short loc_18002A726
0x18002a6b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6c0  lea     rax, WPP_GLOBAL_Control
0x18002a6c7  cmp     rcx, rax
0x18002a6ca  jz      short loc_18002A6D2
0x18002a6cc  cmp     byte ptr [rcx+19h], 4
0x18002a6d0  jnb     short loc_18002A6D5
0x18002a6d2  xor     sil, sil
0x18002a6d5  lea     rax, WPP_RECORDER_INITIALIZED
0x18002a6dc  mov     ebx, 18h
0x18002a6e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002a6e8  setnz   r8b
0x18002a6ec  test    sil, sil
0x18002a6ef  jnz     short loc_18002A6F6
0x18002a6f1  test    r8b, r8b
0x18002a6f4  jz      short loc_18002A717
0x18002a6f6  mov     r9, [rcx+28h]
0x18002a6fa  lea     rax, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a701  mov     rcx, [rcx+10h]
0x18002a705  mov     dl, sil
0x18002a708  mov     [rsp+78h+var_40], rax
0x18002a70d  mov     [rsp+78h+var_48], bx
0x18002a712  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002a717  mov     rcx, [rdi]
0x18002a71a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a71e  add     rcx, rbx
0x18002a721  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x18002a726  xor     eax, eax
0x18002a728  add     rsp, 50h
0x18002a72c  pop     r14
0x18002a72e  pop     rdi
0x18002a72f  pop     rsi
0x18002a730  pop     rbp
0x18002a731  pop     rbx
0x18002a732  retn
```
