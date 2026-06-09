# Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::Dispatch(_CM_NOTIFY_EVENT_DATA const &)

- ea: `0x18004fc60`
- end: `0x18004fd29`
- name: `?Dispatch@PnpCustomNotificationDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAAXAEBU_CM_NOTIFY_EVENT_DATA@@@Z`
- size: `201`
- prototype: `void __fastcall(PSRWLOCK SRWLock, const struct _CM_NOTIFY_EVENT_DATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004fd30`

## callees

- `0x1800021dc`
- `0x180002f4d`
- `0x180004060`
- `0x180019fd4`
- `0x18004fc60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004fcb4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004fcb4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004fd08`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004fd08`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::Details::PnpCustomNotificationDispatcher::Dispatch(
        PSRWLOCK SRWLock,
        const struct _CM_NOTIFY_EVENT_DATA *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  _QWORD *v6; // rax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSRWLOCK v9; // [rsp+38h] [rbp+10h] BYREF

  try
  {
    v4 = operator new(*((unsigned int *)a2 + 7) + 40LL);
    v4[1] = v4;
    *v4 = v4;
    *((_OWORD *)v4 + 1) = *(_OWORD *)((char *)a2 + 8);
    *((_DWORD *)v4 + 8) = *((_DWORD *)a2 + 6);
    *((_DWORD *)v4 + 9) = *((_DWORD *)a2 + 7);
    memcpy_0(v4 + 5, (char *)a2 + 32, *((unsigned int *)a2 + 7));
    AcquireSRWLockExclusive(SRWLock);
    v9 = SRWLock;
    v5 = (unsigned __int64)&SRWLock[11] & ((unsigned __int128)-(__int128)(unsigned __int64)&SRWLock[13] >> 64);
    v6 = *(_QWORD **)(v5 + 8);
    if ( *v6 != v5 )
      __fastfail(3u);
    *v4 = v5;
    v4[1] = v6;
    *v6 = v4;
    *(_QWORD *)(((unsigned __int64)&SRWLock[11] & ((unsigned __int128)-(__int128)(unsigned __int64)&SRWLock[13] >> 64))
              + 8) = v4;
    if ( !LOBYTE(SRWLock[1].Ptr) )
    {
      LOBYTE(SRWLock[1].Ptr) = 1;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
        &v9,
        0);
      SubmitThreadpoolWork((PTP_WORK)SRWLock[10].Ptr);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x646,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
      v7);
  }
}

```

## disassembly

```asm
0x18004fc60  mov     [rsp+arg_0], rbx
0x18004fc65  mov     [rsp+arg_10], rsi
0x18004fc6a  push    rdi
0x18004fc6b  sub     rsp, 20h
0x18004fc6f  mov     rsi, rdx
0x18004fc72  mov     rdi, rcx
0x18004fc75  mov     ecx, [rdx+1Ch]
0x18004fc78  add     rcx, 28h ; '('; Size
0x18004fc7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fc81  mov     rbx, rax
0x18004fc84  mov     [rax+8], rax
0x18004fc88  mov     [rax], rax
0x18004fc8b  movups  xmm0, xmmword ptr [rsi+8]
0x18004fc8f  movdqu  xmmword ptr [rax+10h], xmm0
0x18004fc94  mov     ecx, [rsi+18h]
0x18004fc97  mov     [rax+20h], ecx
0x18004fc9a  mov     ecx, [rsi+1Ch]
0x18004fc9d  mov     [rax+24h], ecx
0x18004fca0  mov     r8d, [rsi+1Ch]; Size
0x18004fca4  lea     rdx, [rsi+20h]; Src
0x18004fca8  lea     rcx, [rax+28h]; void *
0x18004fcac  call    memcpy_0
0x18004fcb1  mov     rcx, rdi; SRWLock
0x18004fcb4  call    cs:__imp_AcquireSRWLockExclusive
0x18004fcba  mov     [rsp+28h+arg_8], rdi
0x18004fcbf  lea     rax, [rdi+68h]
0x18004fcc3  lea     rcx, [rax-10h]
0x18004fcc7  neg     rax
0x18004fcca  sbb     rdx, rdx
0x18004fccd  and     rdx, rcx
0x18004fcd0  mov     rax, [rdx+8]
0x18004fcd4  cmp     [rax], rdx
0x18004fcd7  jz      short loc_18004FCE0
0x18004fcd9  mov     ecx, 3
0x18004fcde  int     29h; Win8: RtlFailFast(ecx)
0x18004fce0  mov     [rbx], rdx
0x18004fce3  mov     [rbx+8], rax
0x18004fce7  mov     [rax], rbx
0x18004fcea  mov     [rdx+8], rbx
0x18004fcee  cmp     byte ptr [rdi+8], 0
0x18004fcf2  jnz     short loc_18004FD0E
0x18004fcf4  mov     byte ptr [rdi+8], 1
0x18004fcf8  xor     edx, edx
0x18004fcfa  lea     rcx, [rsp+28h+arg_8]
0x18004fcff  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18004fd04  mov     rcx, [rdi+50h]; pwk
0x18004fd08  call    cs:__imp_SubmitThreadpoolWork
0x18004fd0e  lea     rcx, [rsp+28h+arg_8]
0x18004fd13  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004fd18  nop
0x18004fd19  mov     rbx, [rsp+28h+arg_0]
0x18004fd1e  mov     rsi, [rsp+28h+arg_10]
0x18004fd23  add     rsp, 20h
0x18004fd27  pop     rdi
0x18004fd28  retn
```
