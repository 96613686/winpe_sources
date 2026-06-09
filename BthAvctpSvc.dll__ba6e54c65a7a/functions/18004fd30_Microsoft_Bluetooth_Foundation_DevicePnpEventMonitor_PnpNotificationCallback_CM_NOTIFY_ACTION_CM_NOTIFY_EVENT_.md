# Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::PnpNotificationCallback(_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA const &)

- ea: `0x18004fd30`
- end: `0x18004feb9`
- name: `?PnpNotificationCallback@DevicePnpEventMonitor@Foundation@Bluetooth@Microsoft@@IEAAXW4_CM_NOTIFY_ACTION@@AEBU_CM_NOTIFY_EVENT_DATA@@@Z`
- size: `393`
- prototype: `void __high(enum _CM_NOTIFY_ACTION, const struct _CM_NOTIFY_EVENT_DATA *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004fec0`

## callees

- `0x180004060`
- `0x180015b58`
- `0x180019c68`
- `0x180019d90`
- `0x180019fd4`
- `0x18004fc60`
- `0x18004fd30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004fdb4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004fdb4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004fdc9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004fdc9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004fe8f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004fe8f`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::DevicePnpEventMonitor::PnpNotificationCallback(
        __int64 a1,
        int a2,
        const struct _CM_NOTIFY_EVENT_DATA *a3)
{
  __int64 v5; // rax
  __int64 v6; // r8
  int v7; // esi
  int v8; // esi
  int v9; // esi
  int v10; // eax
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+20h] BYREF

  if ( *(_BYTE *)(a1 + 48) && (a2 == 1 || a2 == 2 || a2 == 3 || a2 == 4 || (unsigned int)(a2 - 5) <= 1) )
  {
    if ( a2 == 6 )
    {
      if ( *(_BYTE *)(a1 + 224) )
        Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::Dispatch((PSRWLOCK)(a1 + 120), a3);
      return;
    }
    if ( *(_QWORD *)(a1 + 112) )
    {
      if ( a2 != 1
        || (v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 16),
            !(unsigned int)_o__wcsicmp(v5, v6 + 24)) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
        v12 = a1 + 8;
        v7 = a2 - 1;
        if ( !v7 )
          goto LABEL_17;
        v8 = v7 - 1;
        if ( !v8 )
        {
          if ( !*(_DWORD *)(a1 + 252) )
            *(_DWORD *)(a1 + 252) = 1;
          goto LABEL_25;
        }
        v9 = v8 - 1;
        if ( !v9 )
        {
          if ( *(_DWORD *)(a1 + 252) == 1 )
            *(_DWORD *)(a1 + 252) = 0;
          goto LABEL_25;
        }
        if ( (unsigned int)(v9 - 1) <= 1 )
        {
LABEL_17:
          v10 = *(_DWORD *)(a1 + 252);
          if ( v10 == 1 )
          {
            *(_DWORD *)(a1 + 252) = 2;
          }
          else if ( !v10 )
          {
            *(_DWORD *)(a1 + 252) = 3;
          }
        }
LABEL_25:
        wil::operation_guard::acquire(a1 + 232, &v11);
        if ( v11 && *(_DWORD *)(a1 + 248) != *(_DWORD *)(a1 + 252) && !*(_BYTE *)(a1 + 244) )
        {
          *(_BYTE *)(a1 + 244) = 1;
          v11 = 0;
          wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
            &v12,
            0);
          SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 256));
        }
        __1__unique_storage_U__resource_policy_PEAVoperation_guard_wil__P6AXPEAV12___E_1_release_operation_guard_reference_details_2_YAX0_ZU__integral_constant__K_00_wistd__PEAV12_PEAV12__0A___T_details_wil___details_wil__QEAA_XZ(&v11);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
      }
    }
  }
}

```

## disassembly

```asm
0x18004fd30  mov     [rsp+arg_8], rbx
0x18004fd35  mov     [rsp+arg_10], rsi
0x18004fd3a  push    rdi
0x18004fd3b  sub     rsp, 20h
0x18004fd3f  mov     al, [rcx+30h]
0x18004fd42  mov     esi, edx
0x18004fd44  mov     rdi, rcx
0x18004fd47  nop
0x18004fd48  test    al, al
0x18004fd4a  jz      loc_18004FEA9
0x18004fd50  mov     ecx, edx
0x18004fd52  sub     ecx, 1
0x18004fd55  jz      short loc_18004FD74
0x18004fd57  sub     ecx, 1
0x18004fd5a  jz      short loc_18004FD74
0x18004fd5c  sub     ecx, 1
0x18004fd5f  jz      short loc_18004FD74
0x18004fd61  sub     ecx, 1
0x18004fd64  jz      short loc_18004FD74
0x18004fd66  sub     ecx, 1
0x18004fd69  jz      short loc_18004FD74
0x18004fd6b  cmp     ecx, 1
0x18004fd6e  jnz     loc_18004FEA9
0x18004fd74  cmp     esi, 6
0x18004fd77  jnz     short loc_18004FD94
0x18004fd79  lea     rcx, [rdi+78h]; SRWLock
0x18004fd7d  cmp     byte ptr [rcx+68h], 0
0x18004fd81  jz      loc_18004FEA9
0x18004fd87  mov     rdx, r8; struct _CM_NOTIFY_EVENT_DATA *
0x18004fd8a  call    ?Dispatch@PnpCustomNotificationDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAAXAEBU_CM_NOTIFY_EVENT_DATA@@@Z; Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::Dispatch(_CM_NOTIFY_EVENT_DATA const &)
0x18004fd8f  jmp     loc_18004FEA9
0x18004fd94  cmp     qword ptr [rdi+70h], 0
0x18004fd99  jz      loc_18004FEA9
0x18004fd9f  cmp     esi, 1
0x18004fda2  jnz     short loc_18004FDC2
0x18004fda4  lea     rcx, [rdi+10h]
0x18004fda8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fdad  mov     rcx, rax
0x18004fdb0  lea     rdx, [r8+18h]
0x18004fdb4  call    cs:__imp__o__wcsicmp
0x18004fdba  test    eax, eax
0x18004fdbc  jnz     loc_18004FEA9
0x18004fdc2  lea     rbx, [rdi+8]
0x18004fdc6  mov     rcx, rbx; SRWLock
0x18004fdc9  call    cs:__imp_AcquireSRWLockExclusive
0x18004fdcf  mov     [rsp+28h+arg_18], rbx
0x18004fdd4  sub     esi, 1
0x18004fdd7  jz      short loc_18004FDED
0x18004fdd9  sub     esi, 1
0x18004fddc  jz      short loc_18004FE19
0x18004fdde  sub     esi, 1
0x18004fde1  jz      short loc_18004FE04
0x18004fde3  sub     esi, 1
0x18004fde6  jz      short loc_18004FDED
0x18004fde8  cmp     esi, 1
0x18004fdeb  jnz     short loc_18004FE3C
0x18004fded  mov     eax, [rdi+0FCh]
0x18004fdf3  cmp     eax, 1
0x18004fdf6  jnz     short loc_18004FE2E
0x18004fdf8  mov     dword ptr [rdi+0FCh], 2
0x18004fe02  jmp     short loc_18004FE3C
0x18004fe04  cmp     dword ptr [rdi+0FCh], 1
0x18004fe0b  jnz     short loc_18004FE3C
0x18004fe0d  mov     dword ptr [rdi+0FCh], 0
0x18004fe17  jmp     short loc_18004FE3C
0x18004fe19  cmp     dword ptr [rdi+0FCh], 0
0x18004fe20  jnz     short loc_18004FE3C
0x18004fe22  mov     dword ptr [rdi+0FCh], 1
0x18004fe2c  jmp     short loc_18004FE3C
0x18004fe2e  test    eax, eax
0x18004fe30  jnz     short loc_18004FE3C
0x18004fe32  mov     dword ptr [rdi+0FCh], 3
0x18004fe3c  lea     rcx, [rdi+0E8h]
0x18004fe43  lea     rdx, [rsp+28h+arg_0]
0x18004fe48  call    ?acquire@operation_guard@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@@2@XZ
0x18004fe4d  cmp     [rsp+28h+arg_0], 0
0x18004fe53  jz      short loc_18004FE95
0x18004fe55  mov     eax, [rdi+0FCh]
0x18004fe5b  cmp     [rdi+0F8h], eax
0x18004fe61  jz      short loc_18004FE95
0x18004fe63  cmp     byte ptr [rdi+0F4h], 0
0x18004fe6a  jnz     short loc_18004FE95
0x18004fe6c  xor     edx, edx
0x18004fe6e  mov     byte ptr [rdi+0F4h], 1
0x18004fe75  lea     rcx, [rsp+28h+arg_18]
0x18004fe7a  mov     [rsp+28h+arg_0], 0
0x18004fe83  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18004fe88  mov     rcx, [rdi+100h]; pwk
0x18004fe8f  call    cs:__imp_SubmitThreadpoolWork
0x18004fe95  lea     rcx, [rsp+28h+arg_0]
0x18004fe9a  call    ??1?$unique_storage@U?$resource_policy@PEAVoperation_guard@wil@@P6AXPEAV12@@_E$1?release_operation_guard_reference@details@2@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAV12@PEAV12@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004fe9f  lea     rcx, [rsp+28h+arg_18]
0x18004fea4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004fea9  mov     rbx, [rsp+28h+arg_8]
0x18004feae  mov     rsi, [rsp+28h+arg_10]
0x18004feb3  add     rsp, 20h
0x18004feb7  pop     rdi
0x18004feb8  retn
```
