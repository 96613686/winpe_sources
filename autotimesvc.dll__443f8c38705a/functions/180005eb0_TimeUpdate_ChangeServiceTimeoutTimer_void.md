# TimeUpdate::ChangeServiceTimeoutTimer(void)

- ea: `0x180005eb0`
- end: `0x180005f0e`
- name: `?ChangeServiceTimeoutTimer@TimeUpdate@@AEAAXXZ`
- size: `94`
- prototype: `void __fastcall(TimeUpdate *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800084c4`
- `0x180008798`

## callees

- `0x180005840`
- `0x180005eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ecd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ecd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ef3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ef3`

## pseudocode

```c
void __fastcall TimeUpdate::ChangeServiceTimeoutTimer(TimeUpdate *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v5; // [rsp+38h] [rbp+10h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  pftDueTime = (struct _FILETIME)-600000000LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 31);
  v5 = v1;
  if ( v3 )
    SetThreadpoolTimer(v3, &pftDueTime, 0xFFFFFFFF, 0x1770u);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x180005eb0  mov     [rsp+arg_10], rbx
0x180005eb5  push    rdi
0x180005eb6  sub     rsp, 20h
0x180005eba  lea     rbx, [rcx+10h]
0x180005ebe  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x180005ec7  mov     rdi, rcx
0x180005eca  mov     rcx, rbx; lpCriticalSection
0x180005ecd  call    cs:__imp_EnterCriticalSection
0x180005ed3  mov     rcx, [rdi+0F8h]; pti
0x180005eda  mov     [rsp+28h+arg_8], rbx
0x180005edf  test    rcx, rcx
0x180005ee2  jz      short loc_180005EF9
0x180005ee4  mov     r9d, 1770h; msWindowLength
0x180005eea  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180005eef  or      r8d, 0FFFFFFFFh; msPeriod
0x180005ef3  call    cs:__imp_SetThreadpoolTimer
0x180005ef9  lea     rcx, [rsp+28h+arg_8]
0x180005efe  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180005f03  mov     rbx, [rsp+28h+arg_10]
0x180005f08  add     rsp, 20h
0x180005f0c  pop     rdi
0x180005f0d  retn
```
