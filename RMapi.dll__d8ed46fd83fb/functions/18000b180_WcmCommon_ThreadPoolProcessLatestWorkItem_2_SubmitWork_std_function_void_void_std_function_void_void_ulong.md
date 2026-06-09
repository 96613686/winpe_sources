# WcmCommon::ThreadPoolProcessLatestWorkItem<2>::SubmitWork<std::function<void (void)>>(std::function<void (void)> &&,ulong)

- ea: `0x18000b180`
- end: `0x18000b235`
- name: `??$SubmitWork@V?$function@$$A6AXXZ@std@@@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAAX$$QEAV?$function@$$A6AXXZ@std@@K@Z`
- size: `181`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800201ac`
- `0x18002214c`
- `0x1800222d0`

## callees

- `0x18000b180`
- `0x18000b23c`
- `0x18000c2a4`
- `0x18000c5f8`
- `0x18001b488`
- `0x18001c624`
- `0x180022b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b1a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b1a5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b21f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b21f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WcmCommon::ThreadPoolProcessLatestWorkItem<2>::SubmitWork<std::function<void (void)>>(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2,
        unsigned int a3)
{
  unsigned __int64 v3; // rbx
  __int64 v6; // rcx
  unsigned __int64 v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // rax
  LPCRITICAL_SECTION v10; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v11[96]; // [rsp+28h] [rbp-60h] BYREF

  v3 = a3;
  if ( !(unsigned __int8)WcmCommon::ThreadPoolProcessLatestWorkItem<2>::BackoffTimerNotReady() )
  {
    EnterCriticalSection(lpCriticalSection);
    v10 = lpCriticalSection;
    if ( LOBYTE(lpCriticalSection[7].DebugInfo) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
    }
    else
    {
      if ( v3 >= 2 )
        std::array<std::any,2>::_Xran(v6);
      v7 = v3 << 6;
      v8 = *((_QWORD *)&lpCriticalSection[5].LockCount + 8 * v3);
      v9 = std::make_any<std::function<void (void)>,std::function<void (void)>,0>(v11, a2);
      std::any::operator=((char *)&lpCriticalSection[3].SpinCount + v7, v9);
      std::any::reset((std::any *)v11);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
      if ( !v8 )
        SubmitThreadpoolWork((PTP_WORK)lpCriticalSection[3].DebugInfo);
    }
  }
}

```

## disassembly

```asm
0x18000b180  mov     [rsp+arg_18], rbx
0x18000b185  push    rbp
0x18000b186  push    rsi
0x18000b187  push    rdi
0x18000b188  sub     rsp, 70h
0x18000b18c  mov     ebx, r8d
0x18000b18f  mov     rbp, rdx
0x18000b192  mov     rdi, rcx
0x18000b195  call    ?BackoffTimerNotReady@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@AEAA_NXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<2>::BackoffTimerNotReady(void)
0x18000b19a  test    al, al
0x18000b19c  jnz     loc_18000B225
0x18000b1a2  mov     rcx, rdi; lpCriticalSection
0x18000b1a5  call    cs:__imp_EnterCriticalSection
0x18000b1ab  mov     [rsp+88h+var_68], rdi
0x18000b1b0  cmp     byte ptr [rdi+118h], 0
0x18000b1b7  jz      short loc_18000B1C5
0x18000b1b9  lea     rcx, [rsp+88h+var_68]
0x18000b1be  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000b1c3  jmp     short loc_18000B225
0x18000b1c5  mov     rsi, rbx
0x18000b1c8  cmp     rbx, 2
0x18000b1cc  jb      short loc_18000B1D4
0x18000b1ce  call    ?_Xran@?$array@Vany@std@@$01@std@@CAXXZ; std::array<std::any,2>::_Xran(void)
0x18000b1d4  shl     rsi, 6
0x18000b1d8  mov     rbx, [rsi+rdi+0D0h]
0x18000b1e0  mov     rdx, rbp
0x18000b1e3  lea     rcx, [rsp+88h+var_60]
0x18000b1e8  call    ??$make_any@V?$function@$$A6AXXZ@std@@V12@$0A@@std@@YA?AVany@0@$$QEAV?$function@$$A6AXXZ@0@@Z; std::make_any<std::function<void (void)>,std::function<void (void)>,0>(std::function<void (void)> &&)
0x18000b1ed  nop
0x18000b1ee  lea     rcx, [rdi+98h]
0x18000b1f5  add     rcx, rsi
0x18000b1f8  mov     rdx, rax
0x18000b1fb  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x18000b200  nop
0x18000b201  lea     rcx, [rsp+88h+var_60]; this
0x18000b206  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x18000b20b  nop
0x18000b20c  lea     rcx, [rsp+88h+var_68]
0x18000b211  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000b216  test    rbx, rbx
0x18000b219  jnz     short loc_18000B225
0x18000b21b  mov     rcx, [rdi+78h]; pwk
0x18000b21f  call    cs:__imp_SubmitThreadpoolWork
0x18000b225  mov     rbx, [rsp+88h+arg_18]
0x18000b22d  add     rsp, 70h
0x18000b231  pop     rdi
0x18000b232  pop     rsi
0x18000b233  pop     rbp
0x18000b234  retn
```
