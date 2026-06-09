# ConnectedStorage::ThreadPoolWork::Wait(ConnectedStorage::Mutex *)

- ea: `0x180017118`
- end: `0x18001714d`
- name: `?Wait@ThreadPoolWork@ConnectedStorage@@QEAAXPEAVMutex@2@@Z`
- size: `53`
- prototype: `void __fastcall(ConnectedStorage::ThreadPoolWork *__hidden this, struct ConnectedStorage::Mutex *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180016168`
- `0x180016b40`
- `0x18003a410`

## callees

- `0x180011c68`
- `0x180017118`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017141`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017141`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180017136`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180017136`

## pseudocode

```c
void __fastcall ConnectedStorage::ThreadPoolWork::Wait(
        ConnectedStorage::ThreadPoolWork *this,
        struct ConnectedStorage::Mutex *a2,
        char *a3)
{
  struct _TP_WORK *v3; // rbx
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  v3 = (struct _TP_WORK *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    ConnectedStorage::Mutex::Unlock::Unlock((ConnectedStorage::Mutex::Unlock *)lpCriticalSection, a2, a3);
    WaitForThreadpoolWorkCallbacks(v3, 0);
    EnterCriticalSection(lpCriticalSection[0]);
  }
}

```

## disassembly

```asm
0x180017118  push    rbx
0x18001711a  sub     rsp, 30h
0x18001711e  mov     rbx, [rcx+8]
0x180017122  test    rbx, rbx
0x180017125  jz      short loc_180017147
0x180017127  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x18001712c  call    ??0Unlock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Unlock::Unlock(ConnectedStorage::Mutex &,char *)
0x180017131  xor     edx, edx; fCancelPendingCallbacks
0x180017133  mov     rcx, rbx; pwk
0x180017136  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001713c  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180017141  call    cs:__imp_EnterCriticalSection
0x180017147  add     rsp, 30h
0x18001714b  pop     rbx
0x18001714c  retn
```
