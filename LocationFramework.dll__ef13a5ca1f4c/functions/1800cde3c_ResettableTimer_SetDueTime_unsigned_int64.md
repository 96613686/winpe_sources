# ResettableTimer::SetDueTime(unsigned __int64)

- ea: `0x1800cde3c`
- end: `0x1800cdf04`
- name: `?SetDueTime@ResettableTimer@@QEAAJ_K@Z`
- size: `200`
- prototype: `__int64 __fastcall(PVOID pv, unsigned __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800a0a88`
- `0x1800f9a80`
- `0x1800fbd30`
- `0x1800fbe80`
- `0x1800fc2d0`

## callees

- `0x18000c974`
- `0x18003b92c`
- `0x18003eb64`
- `0x1800a98c0`
- `0x1800cde3c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cded5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cded5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800cde8d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800cde8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800cde9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800cde9e`

## pseudocode

```c
__int64 __fastcall ResettableTimer::SetDueTime(char *pv, ULONGLONG a2)
{
  PTP_TIMER ThreadpoolTimer; // rax
  ULONGLONG TickCount64; // rax
  struct _FILETIME v6; // rdx
  DWORD v7; // r9d
  struct _TP_TIMER *v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-20h] BYREF

  v10 = 0;
  wil::EnterCriticalSection(&v10, pv + 104);
  if ( !*((_QWORD *)pv + 12) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ResettableTimer::TimerCallback, pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      pv + 96,
      ThreadpoolTimer);
  }
  TickCount64 = GetTickCount64();
  if ( (__int64)(a2 - TickCount64) <= 0 )
  {
    v6 = 0;
    a2 = TickCount64;
  }
  else
  {
    v6 = (struct _FILETIME)(-10000LL * (a2 - TickCount64));
  }
  *((_QWORD *)pv + 11) = a2;
  v7 = *((_DWORD *)pv + 2);
  v8 = (struct _TP_TIMER *)*((_QWORD *)pv + 12);
  pftDueTime = v6;
  SetThreadpoolTimer(v8, &pftDueTime, 0, v7);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v10);
  return 0;
}

```

## disassembly

```asm
0x1800cde3c  mov     r11, rsp
0x1800cde3f  mov     [r11+18h], rbx
0x1800cde43  mov     [r11+20h], rsi
0x1800cde47  push    rdi
0x1800cde48  sub     rsp, 40h
0x1800cde4c  mov     rax, cs:__security_cookie
0x1800cde53  xor     rax, rsp
0x1800cde56  mov     [rsp+48h+var_18], rax
0x1800cde5b  mov     rdi, rdx
0x1800cde5e  mov     qword ptr [r11-28h], 0
0x1800cde66  lea     rdx, [rcx+68h]
0x1800cde6a  mov     rbx, rcx
0x1800cde6d  lea     rcx, [r11-28h]
0x1800cde71  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800cde76  lea     rsi, [rbx+60h]
0x1800cde7a  cmp     qword ptr [rsi], 0
0x1800cde7e  jnz     short loc_1800CDE9E
0x1800cde80  xor     r8d, r8d; pcbe
0x1800cde83  lea     rcx, ?TimerCallback@ResettableTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800cde8a  mov     rdx, rbx; pv
0x1800cde8d  call    cs:__imp_CreateThreadpoolTimer
0x1800cde93  mov     rdx, rax
0x1800cde96  mov     rcx, rsi
0x1800cde99  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800cde9e  call    cs:__imp_GetTickCount64
0x1800cdea4  mov     rcx, rdi
0x1800cdea7  sub     rcx, rax
0x1800cdeaa  test    rcx, rcx
0x1800cdead  jle     short loc_1800CDEB8
0x1800cdeaf  imul    rdx, rcx, 0FFFFFFFFFFFFD8F0h
0x1800cdeb6  jmp     short loc_1800CDEBD
0x1800cdeb8  xor     edx, edx
0x1800cdeba  mov     rdi, rax
0x1800cdebd  mov     [rbx+58h], rdi
0x1800cdec1  xor     r8d, r8d; msPeriod
0x1800cdec4  mov     r9d, [rbx+8]; msWindowLength
0x1800cdec8  mov     rcx, [rsi]; pti
0x1800cdecb  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x1800cded0  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800cded5  call    cs:__imp_SetThreadpoolTimer
0x1800cdedb  lea     rcx, [rsp+48h+var_28]
0x1800cdee0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800cdee5  xor     eax, eax
0x1800cdee7  mov     rcx, [rsp+48h+var_18]
0x1800cdeec  xor     rcx, rsp; StackCookie
0x1800cdeef  call    __security_check_cookie
0x1800cdef4  mov     rbx, [rsp+48h+arg_10]
0x1800cdef9  mov     rsi, [rsp+48h+arg_18]
0x1800cdefe  add     rsp, 40h
0x1800cdf02  pop     rdi
0x1800cdf03  retn
```
