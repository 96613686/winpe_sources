# InternalBroadcastDriverMessage

- ea: `0x180001cb0`
- end: `0x180001dbd`
- name: `InternalBroadcastDriverMessage`
- size: `269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800011e4`
- `0x180001564`
- `0x180001c30`
- `0x180001f30`
- `0x1800027d8`
- `0x180002a20`
- `0x180002eb0`

## callees

- `0x180001cb0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001cfa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001cfa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001d3c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001da6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001d3c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001da6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001cd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001cd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001db3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001db3`

## pseudocode

```c
__int64 __fastcall InternalBroadcastDriverMessage(int a1, unsigned int a2, __int64 a3, __int64 a4)
{
  char *v8; // rax
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD, __int64, __int64); // rsi

  EnterCriticalSection(&DriverListCritSec);
  if ( hInstalledDriverList && a1 <= cInstalledDrivers && a1 && (v8 = (char *)GlobalLock(hInstalledDriverList)) != 0 )
  {
    v9 = a1 - 1;
    while ( v9 != a1 )
    {
      v10 = 32LL * v9++;
      if ( *(_QWORD *)&v8[v10 + 16] )
      {
        v11 = *(_QWORD *)&v8[v10 + 8];
        v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64))&v8[v10 + 24];
        GlobalUnlock(hInstalledDriverList);
        LeaveCriticalSection(&DriverListCritSec);
        return v12(v11, v9, a2, a3, a4);
      }
    }
    GlobalUnlock(hInstalledDriverList);
    LeaveCriticalSection(&DriverListCritSec);
    return 0;
  }
  else
  {
    LeaveCriticalSection(&DriverListCritSec);
    return 0;
  }
}

```

## disassembly

```asm
0x180001cb0  mov     [rsp+arg_10], rbp
0x180001cb5  push    rdi
0x180001cb6  push    r14
0x180001cb8  push    r15
0x180001cba  sub     rsp, 30h
0x180001cbe  mov     edi, ecx
0x180001cc0  mov     rbp, r9
0x180001cc3  lea     rcx, DriverListCritSec; lpCriticalSection
0x180001cca  mov     r14, r8
0x180001ccd  mov     r15d, edx
0x180001cd0  call    cs:__imp_EnterCriticalSection
0x180001cd6  mov     rcx, cs:hInstalledDriverList; hMem
0x180001cdd  test    rcx, rcx
0x180001ce0  jz      loc_180001D81
0x180001ce6  cmp     edi, cs:cInstalledDrivers
0x180001cec  jg      loc_180001D81
0x180001cf2  test    edi, edi
0x180001cf4  jz      loc_180001D81
0x180001cfa  call    cs:__imp_GlobalLock
0x180001d00  test    rax, rax
0x180001d03  jz      short loc_180001D81
0x180001d05  mov     [rsp+48h+arg_0], rbx
0x180001d0a  lea     ebx, [rdi-1]
0x180001d0d  cmp     ebx, edi
0x180001d0f  jz      loc_180001D9F
0x180001d15  movsxd  rdx, ebx
0x180001d18  shl     rdx, 5
0x180001d1c  inc     ebx
0x180001d1e  cmp     qword ptr [rdx+rax+10h], 0
0x180001d24  jz      short loc_180001D0D
0x180001d26  mov     rcx, cs:hInstalledDriverList; hMem
0x180001d2d  mov     rdi, [rdx+rax+8]
0x180001d32  mov     [rsp+48h+arg_8], rsi
0x180001d37  mov     rsi, [rdx+rax+18h]
0x180001d3c  call    cs:__imp_GlobalUnlock
0x180001d42  lea     rcx, DriverListCritSec; lpCriticalSection
0x180001d49  call    cs:__imp_LeaveCriticalSection
0x180001d4f  movsxd  rdx, ebx
0x180001d52  mov     r9, r14
0x180001d55  mov     r8d, r15d
0x180001d58  mov     [rsp+48h+var_28], rbp
0x180001d5d  mov     rcx, rdi
0x180001d60  mov     rax, rsi
0x180001d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d68  mov     rsi, [rsp+48h+arg_8]
0x180001d6d  mov     rbx, [rsp+48h+arg_0]
0x180001d72  mov     rbp, [rsp+48h+arg_10]
0x180001d77  add     rsp, 30h
0x180001d7b  pop     r15
0x180001d7d  pop     r14
0x180001d7f  pop     rdi
0x180001d80  retn
0x180001d81  lea     rcx, DriverListCritSec; lpCriticalSection
0x180001d88  call    cs:__imp_LeaveCriticalSection
0x180001d8e  mov     rbp, [rsp+48h+arg_10]
0x180001d93  xor     eax, eax
0x180001d95  add     rsp, 30h
0x180001d99  pop     r15
0x180001d9b  pop     r14
0x180001d9d  pop     rdi
0x180001d9e  retn
0x180001d9f  mov     rcx, cs:hInstalledDriverList; hMem
0x180001da6  call    cs:__imp_GlobalUnlock
0x180001dac  lea     rcx, DriverListCritSec; lpCriticalSection
0x180001db3  call    cs:__imp_LeaveCriticalSection
0x180001db9  xor     eax, eax
0x180001dbb  jmp     short loc_180001D6D
```
