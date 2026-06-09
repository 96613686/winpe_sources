# Windows::Compat::Inventory::Service::WinRtHost::SetTimer(void)

- ea: `0x1800c53d4`
- end: `0x1800c5460`
- name: `?SetTimer@WinRtHost@Service@Inventory@Compat@Windows@@QEAAXXZ`
- size: `140`
- prototype: `void __fastcall(Windows::Compat::Inventory::Service::WinRtHost *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c3e78`
- `0x1800c4d68`
- `0x1800c5be0`

## callees

- `0x1800108d4`
- `0x1800152d0`
- `0x1800c53d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c53e8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c53e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c5416`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c5416`

## string_xrefs

- `0x1800c544e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800c5433`: `Windows::Compat::Inventory::Service::WinRtHost::SetTimer`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::Service::WinRtHost::SetTimer(HANDLE *this)
{
  const char *v2; // r9
  struct _TP_TIMER *v3; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( this[4] )
  {
    if ( !ResetEvent(this[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA06,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v2);
    v3 = (struct _TP_TIMER *)this[4];
    pftDueTime.dwHighDateTime = -1;
    pftDueTime.dwLowDateTime = 1294967296;
    if ( v3 )
      SetThreadpoolTimer(v3, &pftDueTime, 0, 0);
    else
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::Service::WinRtHost::SetTimer",
        85,
        "timer does not exist [%#x]",
        -2147418113);
  }
}

```

## disassembly

```asm
0x1800c53d4  push    rbx
0x1800c53d6  sub     rsp, 30h
0x1800c53da  cmp     qword ptr [rcx+20h], 0
0x1800c53df  mov     rbx, rcx
0x1800c53e2  jz      short loc_1800C5443
0x1800c53e4  mov     rcx, [rcx+8]; hEvent
0x1800c53e8  call    cs:__imp_ResetEvent
0x1800c53ee  test    eax, eax
0x1800c53f0  jz      short loc_1800C5449
0x1800c53f2  mov     rcx, [rbx+20h]; pti
0x1800c53f6  mov     [rsp+38h+pftDueTime.dwHighDateTime], 0FFFFFFFFh
0x1800c53fe  mov     [rsp+38h+pftDueTime.dwLowDateTime], 4D2FA200h
0x1800c5406  test    rcx, rcx
0x1800c5409  jz      short loc_1800C541E
0x1800c540b  xor     r9d, r9d; msWindowLength
0x1800c540e  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800c5413  xor     r8d, r8d; msPeriod
0x1800c5416  call    cs:__imp_SetThreadpoolTimer
0x1800c541c  jmp     short loc_1800C5443
0x1800c541e  mov     r8d, 55h ; 'U'
0x1800c5424  mov     [rsp+38h+var_18], 8000FFFFh
0x1800c542c  lea     r9, aTimerDoesNotEx; "timer does not exist [%#x]"
0x1800c5433  lea     rdx, aWindowsCompatI_0; "Windows::Compat::Inventory::Service::Wi"...
0x1800c543a  lea     ecx, [r8-54h]
0x1800c543e  call    AslLogCallPrintf
0x1800c5443  add     rsp, 30h
0x1800c5447  pop     rbx
0x1800c5448  retn
0x1800c5449  mov     rcx, [rsp+38h]; this
0x1800c544e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800c5455  mov     edx, 0A06h; void *
0x1800c545a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
