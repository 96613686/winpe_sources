# NetSetupSvcDeviceManager::NetSetupSvcDeviceManager(void)

- ea: `0x18001d15c`
- end: `0x18001d251`
- name: `??0NetSetupSvcDeviceManager@@QEAA@XZ`
- size: `245`
- prototype: `NetSetupSvcDeviceManager *__fastcall(_DWORD *pv)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800088d4`

## callees

- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x18001a808`
- `0x18001d15c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001d1cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001d1cb`

## pseudocode

```c
NetSetupSvcDeviceManager *__fastcall NetSetupSvcDeviceManager::NetSetupSvcDeviceManager(_DWORD *pv)
{
  char *v2; // rbx
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // ebx
  _BYTE pExceptionObject[216]; // [rsp+20h] [rbp-D8h] BYREF
  int v7; // [rsp+108h] [rbp+10h] BYREF
  char *v8; // [rsp+110h] [rbp+18h]

  *(_QWORD *)pv = 0;
  v2 = (char *)(pv + 2);
  v8 = (char *)(pv + 2);
  pv[2] = 0;
  v7 = 3;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    (_QWORD *)pv + 2,
    &v7);
  v7 = 3;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    (_QWORD *)v2 + 2,
    &v7);
  *((_QWORD *)v2 + 3) = 0;
  ThreadpoolWork = CreateThreadpoolWork(
                     (PTP_WORK_CALLBACK)NetSetupSvcDeviceManager::SynchronizePnpDevicesWorkItemThunk,
                     pv,
                     0);
  *(_QWORD *)pv = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  return (NetSetupSvcDeviceManager *)pv;
}

```

## disassembly

```asm
0x18001d15c  mov     rax, rsp
0x18001d15f  mov     [rax+20h], rbx
0x18001d163  mov     [rax+8], rcx
0x18001d167  push    rdi
0x18001d168  sub     rsp, 0F0h
0x18001d16f  mov     rdi, rcx
0x18001d172  mov     qword ptr [rcx], 0
0x18001d179  lea     rbx, [rcx+8]
0x18001d17d  mov     [rax+18h], rbx
0x18001d181  mov     dword ptr [rbx], 0
0x18001d187  mov     dword ptr [rax+10h], 3
0x18001d18e  lea     rcx, [rbx+8]
0x18001d192  lea     rdx, [rax+10h]
0x18001d196  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18001d19b  nop
0x18001d19c  mov     [rsp+0F8h+arg_8], 3
0x18001d1a7  lea     rcx, [rbx+10h]
0x18001d1ab  lea     rdx, [rsp+0F8h+arg_8]
0x18001d1b3  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18001d1b8  xor     eax, eax
0x18001d1ba  mov     [rbx+18h], rax
0x18001d1be  xor     r8d, r8d; pcbe
0x18001d1c1  mov     rdx, rdi; pv
0x18001d1c4  lea     rcx, ?SynchronizePnpDevicesWorkItemThunk@NetSetupSvcDeviceManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001d1cb  call    cs:__imp_CreateThreadpoolWork
0x18001d1d1  mov     [rdi], rax
0x18001d1d4  test    rax, rax
0x18001d1d7  jnz     short loc_18001D23D
0x18001d1d9  call    cs:__imp_GetLastError
0x18001d1df  mov     ebx, eax
0x18001d1e1  lea     rax, WPP_GLOBAL_Control
0x18001d1e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1ef  cmp     rcx, rax
0x18001d1f2  jz      short loc_18001D212
0x18001d1f4  cmp     byte ptr [rcx+19h], 2
0x18001d1f8  jb      short loc_18001D212
0x18001d1fa  mov     edx, 0Bh
0x18001d1ff  mov     r9d, ebx
0x18001d202  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18001d209  mov     rcx, [rcx+10h]
0x18001d20d  call    WPP_SF_d
0x18001d212  test    ebx, ebx
0x18001d214  jle     short loc_18001D21F
0x18001d216  movzx   ebx, bx
0x18001d219  or      ebx, 80070000h
0x18001d21f  mov     edx, ebx; int
0x18001d221  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18001d226  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001d22b  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001d232  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18001d237  call    _CxxThrowException_0
0x18001d23d  mov     rax, rdi
0x18001d240  mov     rbx, [rsp+0F8h+arg_18]
0x18001d248  add     rsp, 0F0h
0x18001d24f  pop     rdi
0x18001d250  retn
```
