# ProcessRefCount::Release(void)

- ea: `0x180021150`
- end: `0x1800211c9`
- name: `?Release@ProcessRefCount@@UEAAKXZ`
- size: `121`
- prototype: `unsigned int __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011afc`
- `0x180021150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800211a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800211a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002118b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002118b`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180021191`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180021191`

## string_xrefs

- `0x1800211b7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall ProcessRefCount::Release(ProcessRefCount *this)
{
  unsigned __int32 v1; // ebx
  struct _TP_TIMER *v2; // rcx
  void *v4; // rcx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v1 && *((_BYTE *)this + 20) )
  {
    if ( *((_QWORD *)this + 4) )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 2);
      v2 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v2, &pftDueTime, 0, 0);
      CoFreeUnusedLibraries();
    }
    else
    {
      v4 = (void *)*((_QWORD *)this + 3);
      if ( v4 && !SetEvent(v4) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v5);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180021150  push    rbx
0x180021152  sub     rsp, 20h
0x180021156  or      ebx, 0FFFFFFFFh
0x180021159  lock xadd [rcx+10h], ebx
0x18002115e  sub     ebx, 1
0x180021161  jnz     short loc_180021197
0x180021163  cmp     [rcx+14h], bl
0x180021166  jz      short loc_180021197
0x180021168  cmp     qword ptr [rcx+20h], 0
0x18002116d  jz      short loc_18002119F
0x18002116f  lock inc dword ptr [rcx+8]
0x180021173  mov     rcx, [rcx+20h]; pti
0x180021177  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18002117c  xor     r9d, r9d; msWindowLength
0x18002117f  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180021188  xor     r8d, r8d; msPeriod
0x18002118b  call    cs:__imp_SetThreadpoolTimer
0x180021191  call    cs:__imp_CoFreeUnusedLibraries
0x180021197  mov     eax, ebx
0x180021199  add     rsp, 20h
0x18002119d  pop     rbx
0x18002119e  retn
0x18002119f  mov     rcx, [rcx+18h]; hEvent
0x1800211a3  test    rcx, rcx
0x1800211a6  jz      short loc_180021197
0x1800211a8  call    cs:__imp_SetEvent
0x1800211ae  test    eax, eax
0x1800211b0  jnz     short loc_180021197
0x1800211b2  mov     rcx, [rsp+28h]; this
0x1800211b7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800211be  mov     edx, 0A01h; void *
0x1800211c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
