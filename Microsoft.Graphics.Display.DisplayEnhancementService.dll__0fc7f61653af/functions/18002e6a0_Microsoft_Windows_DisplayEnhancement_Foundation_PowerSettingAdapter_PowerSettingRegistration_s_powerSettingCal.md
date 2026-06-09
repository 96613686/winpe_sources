# Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration::s_powerSettingCallbackWrapper(void *,ulong,void *)

- ea: `0x18002e6a0`
- end: `0x18002e75f`
- name: `?s_powerSettingCallbackWrapper@PowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@KAKPEAXK0@Z`
- size: `191`
- prototype: `unsigned int __fastcall(void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800058bc`
- `0x18002af90`
- `0x18002e6a0`
- `0x1800753fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e72d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e72d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002e702`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002e702`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002e71c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002e71c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002e725`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002e725`

## string_xrefs

- `0x18002e738`: `Microsoft.Graphics.Display.DisplayEnhancementService.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration::s_powerSettingCallbackWrapper(
        _QWORD *a1,
        int a2,
        _DWORD *a3)
{
  _QWORD *v5; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v7; // rbx
  __int64 LastError; // rdx
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  _QWORD *v12; // [rsp+48h] [rbp+20h] BYREF

  if ( a2 == 32787 && a3 && a3[4] == 4 )
  {
    try
    {
      v5 = operator new(0x10u);
      v5[1] = 0;
      v12 = v5;
      *v5 = a1;
      *((_DWORD *)v5 + 2) = a3[5];
      ThreadpoolWork = CreateThreadpoolWork(
                         Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration::ProcessPowerSettingCallback,
                         v5,
                         (PTP_CALLBACK_ENVIRON)(a1[10] + 16LL));
      v7 = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        v12 = 0;
        SubmitThreadpoolWork(ThreadpoolWork);
        CloseThreadpoolWork(v7);
      }
      else
      {
        LastError = GetLastError();
        MicrosoftTelemetryAssertTriggeredArgs("Microsoft.Graphics.Display.DisplayEnhancementService.dll", LastError, 0);
      }
      std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration::PowerSettingThreadpoolContext>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration::PowerSettingThreadpoolContext>(&v12);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x60,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\DisplayEnhancement\\foundation\\lib\\PowerSettingAdapter.h",
        v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002e6a0  mov     [rsp+arg_0], rbx
0x18002e6a5  push    rdi
0x18002e6a6  sub     rsp, 20h
0x18002e6aa  mov     rbx, r8
0x18002e6ad  mov     rdi, rcx
0x18002e6b0  cmp     edx, 8013h
0x18002e6b6  jnz     loc_18002E750
0x18002e6bc  test    rbx, rbx
0x18002e6bf  jz      loc_18002E750
0x18002e6c5  cmp     dword ptr [r8+10h], 4
0x18002e6ca  jnz     loc_18002E750
0x18002e6d0  mov     ecx, 10h; Size
0x18002e6d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e6da  mov     qword ptr [rax+8], 0
0x18002e6e2  mov     [rsp+28h+arg_18], rax
0x18002e6e7  mov     [rax], rdi
0x18002e6ea  mov     ecx, [rbx+14h]
0x18002e6ed  mov     [rax+8], ecx
0x18002e6f0  mov     r8, [rdi+50h]
0x18002e6f4  add     r8, 10h; pcbe
0x18002e6f8  mov     rdx, rax; pv
0x18002e6fb  lea     rcx, ?ProcessPowerSettingCallback@PowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002e702  call    cs:__imp_CreateThreadpoolWork
0x18002e708  mov     rbx, rax
0x18002e70b  test    rax, rax
0x18002e70e  jz      short loc_18002E72D
0x18002e710  mov     [rsp+28h+arg_18], 0
0x18002e719  mov     rcx, rax; pwk
0x18002e71c  call    cs:__imp_SubmitThreadpoolWork
0x18002e722  mov     rcx, rbx; pwk
0x18002e725  call    cs:__imp_CloseThreadpoolWork
0x18002e72b  jmp     short loc_18002E745
0x18002e72d  call    cs:__imp_GetLastError
0x18002e733  mov     edx, eax
0x18002e735  xor     r8d, r8d
0x18002e738  lea     rcx, aMicrosoftGraph_0; "Microsoft.Graphics.Display.DisplayEnhan"...
0x18002e73f  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002e744  nop
0x18002e745  lea     rcx, [rsp+28h+arg_18]
0x18002e74a  call    ??1?$unique_ptr@UPowerSettingThreadpoolContext@PowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@UPowerSettingThreadpoolContext@PowerSettingRegistration@PowerSettingAdapter@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration::PowerSettingThreadpoolContext>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::PowerSettingAdapter::PowerSettingRegistration::PowerSettingThreadpoolContext>(void)
0x18002e74f  nop
0x18002e750  jmp     short $+2
0x18002e752  xor     eax, eax
0x18002e754  mov     rbx, [rsp+28h+arg_0]
0x18002e759  add     rsp, 20h
0x18002e75d  pop     rdi
0x18002e75e  retn
```
