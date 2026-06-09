# CGnssDriverWrapper::Release(void)

- ea: `0x1800e66d0`
- end: `0x1800e67a1`
- name: `?Release@CGnssDriverWrapper@@UEAAXXZ`
- size: `209`
- prototype: `void __fastcall(CGnssDriverWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180067394`
- `0x18008c07c`
- `0x1800e0070`
- `0x1800e5988`
- `0x1800e66d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800e674c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800e674c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800e675f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800e675f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6718`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e673d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e677b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6718`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e673d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e677b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e66e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e672d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6755`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e66e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e672d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6755`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e6784`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e6784`

## pseudocode

```c
void __fastcall CGnssDriverWrapper::Release(CGnssDriverWrapper *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  _QWORD *v3; // rdx
  unsigned int v4; // r8d
  int v5; // r9d
  unsigned int v6; // edx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_DWORD *)this + 12) = 1;
  v3 = (_QWORD *)*((_QWORD *)this + 8);
  if ( v3 )
    v3 = (_QWORD *)*v3;
  COverlappedList::CancelPendingIos((CGnssDriverWrapper *)((char *)this + 88), v3, 0);
  if ( *((_QWORD *)this + 14) )
  {
    LeaveCriticalSection(v1);
    wil::handle_wait(*((wil **)this + 15), (void *)0xFFFFFFFFLL, v4, v5);
    EnterCriticalSection(v1);
  }
  if ( *((_QWORD *)this + 10) )
  {
    LeaveCriticalSection(v1);
    WaitForThreadpoolIoCallbacks(*((PTP_IO *)this + 10), 1);
    EnterCriticalSection(v1);
    CloseThreadpoolIo(*((PTP_IO *)this + 10));
    *((_QWORD *)this + 10) = 0;
  }
  wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
    (char *)this + 64,
    0);
  LeaveCriticalSection(v1);
  DeleteCriticalSection(v1);
  CGnssDriverWrapper::`scalar deleting destructor'(this, v6);
}

```

## disassembly

```asm
0x1800e66d0  mov     [rsp+arg_0], rbx
0x1800e66d5  mov     [rsp+arg_8], rsi
0x1800e66da  push    rdi
0x1800e66db  sub     rsp, 20h
0x1800e66df  lea     rdi, [rcx+8]
0x1800e66e3  mov     rbx, rcx
0x1800e66e6  mov     rcx, rdi; lpCriticalSection
0x1800e66e9  call    cs:__imp_EnterCriticalSection
0x1800e66ef  mov     dword ptr [rbx+30h], 1
0x1800e66f6  mov     rdx, [rbx+40h]
0x1800e66fa  test    rdx, rdx
0x1800e66fd  jz      short loc_1800E6702
0x1800e66ff  mov     rdx, [rdx]; void *
0x1800e6702  lea     rcx, [rbx+58h]; this
0x1800e6706  xor     r8d, r8d; unsigned int
0x1800e6709  call    ?CancelPendingIos@COverlappedList@@QEAAKPEAXK@Z; COverlappedList::CancelPendingIos(void *,ulong)
0x1800e670e  cmp     qword ptr [rbx+70h], 0
0x1800e6713  jz      short loc_1800E6733
0x1800e6715  mov     rcx, rdi; lpCriticalSection
0x1800e6718  call    cs:__imp_LeaveCriticalSection
0x1800e671e  mov     rcx, [rbx+78h]; this
0x1800e6722  or      edx, 0FFFFFFFFh; void *
0x1800e6725  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800e672a  mov     rcx, rdi; lpCriticalSection
0x1800e672d  call    cs:__imp_EnterCriticalSection
0x1800e6733  cmp     qword ptr [rbx+50h], 0
0x1800e6738  jz      short loc_1800E676D
0x1800e673a  mov     rcx, rdi; lpCriticalSection
0x1800e673d  call    cs:__imp_LeaveCriticalSection
0x1800e6743  mov     rcx, [rbx+50h]; pio
0x1800e6747  mov     edx, 1; fCancelPendingCallbacks
0x1800e674c  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800e6752  mov     rcx, rdi; lpCriticalSection
0x1800e6755  call    cs:__imp_EnterCriticalSection
0x1800e675b  mov     rcx, [rbx+50h]; pio
0x1800e675f  call    cs:__imp_CloseThreadpoolIo
0x1800e6765  mov     qword ptr [rbx+50h], 0
0x1800e676d  xor     edx, edx
0x1800e676f  lea     rcx, [rbx+40h]
0x1800e6773  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x1800e6778  mov     rcx, rdi; lpCriticalSection
0x1800e677b  call    cs:__imp_LeaveCriticalSection
0x1800e6781  mov     rcx, rdi; lpCriticalSection
0x1800e6784  call    cs:__imp_DeleteCriticalSection
0x1800e678a  mov     rcx, rbx; this
0x1800e678d  mov     rbx, [rsp+28h+arg_0]
0x1800e6792  mov     rsi, [rsp+28h+arg_8]
0x1800e6797  add     rsp, 20h
0x1800e679b  pop     rdi
0x1800e679c  jmp     ??_GCGnssDriverWrapper@@QEAAPEAXI@Z; CGnssDriverWrapper::`scalar deleting destructor'(uint)
```
