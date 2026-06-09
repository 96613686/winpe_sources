# Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::OnWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800575d0`
- end: `0x180057674`
- name: `?OnWaitCallback@?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `164`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b07c`
- `0x180010350`
- `0x1800575d0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005764e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005764e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005762d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005762d`

## pseudocode

```c
void __fastcall Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::OnWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  __int64 v4; // rcx
  signed __int32 v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  TP_WAIT_RESULT v11; // [rsp+48h] [rbp+20h] BYREF

  v4 = *((_QWORD *)Context + 9);
  v11 = WaitResult;
  if ( !v4 )
    std::_Xbad_function_call();
  if ( (*(unsigned __int8 (__fastcall **)(__int64, TP_WAIT_RESULT *, PTP_WAIT))(*(_QWORD *)v4 + 16LL))(v4, &v11, Wait) )
  {
    while ( 1 )
    {
      v6 = *((_DWORD *)Context + 44);
      if ( (v6 & 0x40000000) != 0 )
        break;
      if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)Context + 44, v6 + 1, v6) )
      {
        v7 = (void *)*((_QWORD *)Context + 10);
        if ( v7 )
          SetThreadpoolWait(*((PTP_WAIT *)Context + 1), v7, *((PFILETIME *)Context + 24));
        if ( _InterlockedDecrement((volatile signed __int32 *)Context + 44) == 0x40000000
          && !SetEvent(*((HANDLE *)Context + 21)) )
        {
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v8, v9);
        }
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x1800575d0  push    rbx
0x1800575d2  sub     rsp, 20h
0x1800575d6  mov     rcx, [rdx+48h]
0x1800575da  mov     rbx, rdx
0x1800575dd  mov     [rsp+28h+arg_18], r9d
0x1800575e2  test    rcx, rcx
0x1800575e5  jz      loc_18005766E
0x1800575eb  mov     rax, [rcx]
0x1800575ee  lea     rdx, [rsp+28h+arg_18]
0x1800575f3  mov     rax, [rax+10h]
0x1800575f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800575fc  test    al, al
0x1800575fe  jz      short loc_180057658
0x180057600  mov     eax, [rbx+0B0h]
0x180057606  bt      eax, 1Eh
0x18005760a  jb      short loc_180057658
0x18005760c  lea     ecx, [rax+1]
0x18005760f  lock cmpxchg [rbx+0B0h], ecx
0x180057617  jnz     short loc_180057600
0x180057619  mov     rdx, [rbx+50h]; h
0x18005761d  test    rdx, rdx
0x180057620  jz      short loc_180057633
0x180057622  mov     r8, [rbx+0C0h]; pftTimeout
0x180057629  mov     rcx, [rbx+8]; pwa
0x18005762d  call    cs:__imp_SetThreadpoolWait
0x180057633  or      eax, 0FFFFFFFFh
0x180057636  lock xadd [rbx+0B0h], eax
0x18005763e  dec     eax
0x180057640  cmp     eax, 40000000h
0x180057645  jnz     short loc_180057658
0x180057647  mov     rcx, [rbx+0A8h]; hEvent
0x18005764e  call    cs:__imp_SetEvent
0x180057654  test    eax, eax
0x180057656  jz      short loc_18005765E
0x180057658  add     rsp, 20h
0x18005765c  pop     rbx
0x18005765d  retn
0x18005765e  mov     rcx, [rsp+28h]; this
0x180057663  mov     edx, 0A01h; void *
0x180057668  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005766e  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
