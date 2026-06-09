# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800121cc`
- end: `0x18001227a`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `174`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014024`

## callees

- `0x1800121cc`
- `0x18001695c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180012259`
- `KERNEL32!SetThreadpoolTimer` at `0x180012259`
- `KERNEL32!CreateThreadpoolTimer` at `0x18001220d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18001220d`
- `KERNEL32!GetLastError` at `0x1800121f2`
- `KERNEL32!GetLastError` at `0x1800121f2`
- `KERNEL32!SetLastError` at `0x180012227`
- `KERNEL32!SetLastError` at `0x180012227`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    v2 = pv + 6;
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v2,
        ThreadpoolTimer);
      SetLastError(LastError);
    }
    v5 = *v2;
    if ( *v2 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v5, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x1800121cc  mov     [rsp+arg_8], rbx
0x1800121d1  mov     [rsp+arg_10], rsi
0x1800121d6  push    rdi
0x1800121d7  sub     rsp, 20h
0x1800121db  mov     rdi, rcx
0x1800121de  cmp     byte ptr [rcx+41h], 0
0x1800121e2  jnz     loc_180012269
0x1800121e8  lea     rsi, [rcx+30h]
0x1800121ec  cmp     qword ptr [rsi], 0
0x1800121f0  jnz     short loc_180012234
0x1800121f2  call    cs:__imp_GetLastError
0x1800121f9  nop     dword ptr [rax+rax+00h]
0x1800121fe  mov     ebx, eax
0x180012200  xor     r8d, r8d; pcbe
0x180012203  mov     rdx, rdi; pv
0x180012206  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001220d  call    cs:__imp_CreateThreadpoolTimer
0x180012214  nop     dword ptr [rax+rax+00h]
0x180012219  mov     rdx, rax
0x18001221c  mov     rcx, rsi
0x18001221f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180012224  nop
0x180012225  mov     ecx, ebx; dwErrCode
0x180012227  call    cs:__imp_SetLastError
0x18001222e  nop     dword ptr [rax+rax+00h]
0x180012233  nop
0x180012234  mov     rcx, [rsi]; pti
0x180012237  test    rcx, rcx
0x18001223a  jz      short loc_180012269
0x18001223c  mov     rax, 0FFFFFFFF4D2FA200h
0x180012246  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18001224b  mov     r9d, 124F8h; msWindowLength
0x180012251  xor     r8d, r8d; msPeriod
0x180012254  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180012259  call    cs:__imp_SetThreadpoolTimer
0x180012260  nop     dword ptr [rax+rax+00h]
0x180012265  mov     byte ptr [rdi+41h], 1
0x180012269  mov     rbx, [rsp+28h+arg_8]
0x18001226e  mov     rsi, [rsp+28h+arg_10]
0x180012273  add     rsp, 20h
0x180012277  pop     rdi
0x180012278  retn
```
