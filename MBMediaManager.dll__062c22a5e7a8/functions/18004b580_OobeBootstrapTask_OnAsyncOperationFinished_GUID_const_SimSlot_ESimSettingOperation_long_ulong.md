# OobeBootstrapTask::OnAsyncOperationFinished(_GUID const &,SimSlot,ESimSettingOperation,long,ulong)

- ea: `0x18004b580`
- end: `0x18004b690`
- name: `?OnAsyncOperationFinished@OobeBootstrapTask@@UEAAJAEBU_GUID@@W4SimSlot@@W4ESimSettingOperation@@JK@Z`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000ad20`
- `0x18000bde0`
- `0x180022a1c`
- `0x180022e9c`
- `0x1800485a4`
- `0x18004b580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b66d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b66d`

## string_xrefs

- `0x18004b5c2`: `OobeBootstrapTask::OnAsyncOperationFinished`
- `0x18004b608`: `OobeBootstrapTask::OnAsyncOperationFinished`
- `0x18004b61a`: `OobeBootstrapTask::OnAsyncOperationFinished`
- `0x18004b645`: `changing state to CompleteWithDeletion`

## pseudocode

```c
__int64 __fastcall OobeBootstrapTask::OnAsyncOperationFinished(
        __int64 a1,
        _QWORD *a2,
        int a3,
        int a4,
        int a5,
        unsigned int a6)
{
  __int64 v8; // rax
  unsigned int v10; // esi
  int v11; // edi
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+60h] [rbp+8h] BYREF

  v8 = *(_QWORD *)(a1 + 72) - *a2;
  if ( !v8 )
    v8 = *(_QWORD *)(a1 + 80) - a2[1];
  if ( v8 )
    return 0;
  if ( *(_DWORD *)(a1 + 100) == a3 )
  {
    wil::EnterCriticalSection(&v12, a1 + 32);
    v10 = a6;
    v11 = a5;
    MBSettingUXLogging::Info(
      "OobeBootstrapTask::OnAsyncOperationFinished",
      239,
      "operation=%d, HRESULT=0x%x, errorDetail=%d",
      a4,
      a5,
      a6);
    if ( a4 == 4 )
    {
      if ( v11 >= 0 )
      {
        MBSettingUXLogging::Info(
          "OobeBootstrapTask::OnAsyncOperationFinished",
          255,
          "changing state to CompleteWithDeletion");
        MBSettingUXLogging::BootstrapProfileDeletion(v11, v10);
        *(_DWORD *)(a1 + 96) = 3;
      }
      else
      {
        MBSettingUXLogging::Warn("OobeBootstrapTask::OnAsyncOperationFinished", 246, "changing state to Error");
        MBSettingUXLogging::BootstrapProfileDeletion(v11, v10);
        *(_DWORD *)(a1 + 96) = 4;
      }
      SetEvent(**(HANDLE **)(a1 + 88));
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
    return 0;
  }
  else
  {
    MBSettingUXLogging::Info(
      "OobeBootstrapTask::OnAsyncOperationFinished",
      234,
      "Discarding notification for slot %d",
      a3);
    return 0;
  }
}

```

## disassembly

```asm
0x18004b580  push    rbx
0x18004b582  push    rsi
0x18004b583  push    rdi
0x18004b584  push    r14
0x18004b586  sub     rsp, 38h
0x18004b58a  mov     r14d, r9d
0x18004b58d  mov     rbx, rcx
0x18004b590  mov     rax, [rcx+48h]
0x18004b594  sub     rax, [rdx]
0x18004b597  jnz     short loc_18004B5A1
0x18004b599  mov     rax, [rcx+50h]
0x18004b59d  sub     rax, [rdx+8]
0x18004b5a1  test    rax, rax
0x18004b5a4  jz      short loc_18004B5AD
0x18004b5a6  xor     eax, eax
0x18004b5a8  jmp     loc_18004B685
0x18004b5ad  cmp     [rcx+64h], r8d
0x18004b5b1  jz      short loc_18004B5D5
0x18004b5b3  mov     r9d, r8d
0x18004b5b6  lea     r8, aDiscardingNoti; "Discarding notification for slot %d"
0x18004b5bd  mov     edx, 0EAh; unsigned int
0x18004b5c2  lea     rcx, aOobebootstrapt_2; "OobeBootstrapTask::OnAsyncOperationFini"...
0x18004b5c9  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b5ce  xor     eax, eax
0x18004b5d0  jmp     loc_18004B685
0x18004b5d5  lea     rdx, [rcx+20h]
0x18004b5d9  lea     rcx, [rsp+58h+arg_0]
0x18004b5de  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004b5e3  mov     esi, [rsp+58h+arg_28]
0x18004b5ea  mov     [rsp+58h+var_30], esi
0x18004b5ee  mov     edi, [rsp+58h+arg_20]
0x18004b5f5  mov     [rsp+58h+var_38], edi
0x18004b5f9  mov     r9d, r14d
0x18004b5fc  lea     r8, aOperationDHres; "operation=%d, HRESULT=0x%x, errorDetail"...
0x18004b603  mov     edx, 0EFh; unsigned int
0x18004b608  lea     rcx, aOobebootstrapt_2; "OobeBootstrapTask::OnAsyncOperationFini"...
0x18004b60f  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b614  cmp     r14d, 4
0x18004b618  jnz     short loc_18004B673
0x18004b61a  lea     rcx, aOobebootstrapt_2; "OobeBootstrapTask::OnAsyncOperationFini"...
0x18004b621  test    edi, edi
0x18004b623  jns     short loc_18004B645
0x18004b625  lea     r8, aChangingStateT_6; "changing state to Error"
0x18004b62c  mov     edx, 0F6h; unsigned int
0x18004b631  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x18004b636  mov     edx, esi; unsigned int
0x18004b638  mov     ecx, edi; int
0x18004b63a  call    ?BootstrapProfileDeletion@MBSettingUXLogging@@SAXJK@Z; MBSettingUXLogging::BootstrapProfileDeletion(long,ulong)
0x18004b63f  mov     [rbx+60h], r14d
0x18004b643  jmp     short loc_18004B666
0x18004b645  lea     r8, aChangingStateT; "changing state to CompleteWithDeletion"
0x18004b64c  mov     edx, 0FFh; unsigned int
0x18004b651  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004b656  mov     edx, esi; unsigned int
0x18004b658  mov     ecx, edi; int
0x18004b65a  call    ?BootstrapProfileDeletion@MBSettingUXLogging@@SAXJK@Z; MBSettingUXLogging::BootstrapProfileDeletion(long,ulong)
0x18004b65f  mov     dword ptr [rbx+60h], 3
0x18004b666  mov     rcx, [rbx+58h]
0x18004b66a  mov     rcx, [rcx]; hEvent
0x18004b66d  call    cs:__imp_SetEvent
0x18004b673  lea     rcx, [rsp+58h+arg_0]
0x18004b678  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004b67d  xor     eax, eax
0x18004b67f  jmp     short loc_18004B685
0x18004b681  mov     eax, dword ptr [rsp+58h+arg_0]
0x18004b685  add     rsp, 38h
0x18004b689  pop     r14
0x18004b68b  pop     rdi
0x18004b68c  pop     rsi
0x18004b68d  pop     rbx
0x18004b68e  retn
```
