# pplx::details::_Task_impl<bool>::_FinalizeAndRunContinuations(bool)

- ea: `0x180014cc8`
- end: `0x180014d25`
- name: `?_FinalizeAndRunContinuations@?$_Task_impl@_N@details@pplx@@QEAAX_N@Z`
- size: `93`
- prototype: `__int64 __fastcall(pplx::details::_Task_impl_base *this)`
- caller_count: `31`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180014434`
- `0x18001c7fc`
- `0x18002731c`
- `0x180027488`
- `0x1800275d8`
- `0x1800276cc`
- `0x180027774`
- `0x1800278d8`
- `0x1800279d8`
- `0x180027abc`
- `0x180027bb4`
- `0x180027c80`
- `0x180027df0`
- `0x1800290a0`
- `0x180029160`
- `0x180029dfc`
- `0x18002e890`
- `0x18002f8e8`
- `0x18002fc64`
- `0x180035268`
- `0x180035350`
- `0x180035444`
- `0x1800385f0`
- `0x1800386b0`
- `0x180038770`
- `0x180049d50`
- `0x180049ea0`
- `0x180049ff0`
- `0x18004a2e0`
- `0x18004a388`
- `0x18004da30`

## callees

- `0x180014cc8`
- `0x1800154c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ce2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ce2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014cf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014cf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014d02`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014d0c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014d0c`

## pseudocode

```c
void __fastcall pplx::details::_Task_impl<bool>::_FinalizeAndRunContinuations(
        pplx::details::_Task_impl_base *this,
        char a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  *((_BYTE *)this + 192) = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_DWORD *)this + 2) == 4 )
  {
    LeaveCriticalSection(v2);
  }
  else
  {
    *((_DWORD *)this + 2) = 3;
    LeaveCriticalSection(v2);
    SetEvent(*((HANDLE *)this + 15));
    pplx::details::_Task_impl_base::_RunTaskContinuations(this);
  }
}

```

## disassembly

```asm
0x180014cc8  mov     [rsp+arg_0], rbx
0x180014ccd  push    rdi
0x180014cce  sub     rsp, 20h
0x180014cd2  lea     rdi, [rcx+20h]
0x180014cd6  mov     [rcx+0C0h], dl
0x180014cdc  mov     rbx, rcx
0x180014cdf  mov     rcx, rdi; lpCriticalSection
0x180014ce2  call    cs:__imp_EnterCriticalSection
0x180014ce8  mov     eax, [rbx+8]
0x180014ceb  mov     rcx, rdi; lpCriticalSection
0x180014cee  cmp     eax, 4
0x180014cf1  jnz     short loc_180014CFB
0x180014cf3  call    cs:__imp_LeaveCriticalSection
0x180014cf9  jmp     short loc_180014D1A
0x180014cfb  mov     dword ptr [rbx+8], 3
0x180014d02  call    cs:__imp_LeaveCriticalSection
0x180014d08  mov     rcx, [rbx+78h]; hEvent
0x180014d0c  call    cs:__imp_SetEvent
0x180014d12  mov     rcx, rbx; this
0x180014d15  call    ?_RunTaskContinuations@_Task_impl_base@details@pplx@@QEAAXXZ; pplx::details::_Task_impl_base::_RunTaskContinuations(void)
0x180014d1a  mov     rbx, [rsp+28h+arg_0]
0x180014d1f  add     rsp, 20h
0x180014d23  pop     rdi
0x180014d24  retn
```
