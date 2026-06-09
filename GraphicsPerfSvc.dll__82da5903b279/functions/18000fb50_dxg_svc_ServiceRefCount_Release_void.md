# dxg::svc::ServiceRefCount::Release(void)

- ea: `0x18000fb50`
- end: `0x18000fbb3`
- name: `?Release@ServiceRefCount@svc@dxg@@UEAAKXZ`
- size: `99`
- prototype: `unsigned int __fastcall(dxg::svc::ServiceRefCount *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e418`
- `0x18000e700`
- `0x18000fb50`
- `0x180026074`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fb8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fb8b`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x18000fb91`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x18000fb91`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall dxg::svc::ServiceRefCount::Release(dxg::svc::ServiceRefCount *this)
{
  struct _TP_TIMER *v3; // rcx
  unsigned int v4; // ebx
  _BYTE v6[24]; // [rsp+20h] [rbp-18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v6, (char *)this + 16);
  if ( (*((_DWORD *)this + 2))-- == 1 )
  {
    v3 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
    if ( v3 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v3, &pftDueTime, 0, 0);
      CoFreeUnusedLibraries();
    }
    else
    {
      dxg::svc::Host::ShutdownService();
    }
  }
  v4 = *((_DWORD *)this + 2);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v6);
  return v4;
}

```

## disassembly

```asm
0x18000fb50  push    rbx
0x18000fb52  sub     rsp, 30h
0x18000fb56  mov     rbx, rcx
0x18000fb59  lea     rdx, [rcx+10h]
0x18000fb5d  lea     rcx, [rsp+38h+var_18]
0x18000fb62  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18000fb67  nop
0x18000fb68  sub     dword ptr [rbx+8], 1
0x18000fb6c  jnz     short loc_18000FB9E
0x18000fb6e  mov     rcx, [rbx+60h]; pti
0x18000fb72  test    rcx, rcx
0x18000fb75  jz      short loc_18000FB99
0x18000fb77  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000fb80  xor     r9d, r9d; msWindowLength
0x18000fb83  xor     r8d, r8d; msPeriod
0x18000fb86  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000fb8b  call    cs:__imp_SetThreadpoolTimer
0x18000fb91  call    cs:__imp_CoFreeUnusedLibraries
0x18000fb97  jmp     short loc_18000FB9E
0x18000fb99  call    ?ShutdownService@Host@svc@dxg@@SAXXZ; dxg::svc::Host::ShutdownService(void)
0x18000fb9e  mov     ebx, [rbx+8]
0x18000fba1  lea     rcx, [rsp+38h+var_18]
0x18000fba6  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18000fbab  mov     eax, ebx
0x18000fbad  add     rsp, 30h
0x18000fbb1  pop     rbx
0x18000fbb2  retn
```
