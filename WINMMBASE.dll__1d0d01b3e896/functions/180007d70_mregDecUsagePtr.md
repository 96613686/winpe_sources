# mregDecUsagePtr

- ea: `0x180007d70`
- end: `0x180007dbd`
- name: `mregDecUsagePtr`
- size: `77`
- prototype: `__int64 __fastcall(struct _MMDRV *)`
- caller_count: `43`
- callee_count: `2`
- tags: ``

## callers

- `0x180001378`
- `0x180001660`
- `0x180003c80`
- `0x1800048e0`
- `0x180005030`
- `0x1800076b0`
- `0x1800077ec`
- `0x1800078f4`
- `0x180007b00`
- `0x1800093a0`
- `0x1800095bc`
- `0x180009820`
- `0x180009a8c`
- `0x18000a0d8`
- `0x18000a27c`
- `0x18000a790`
- `0x18000a960`
- `0x18000b364`
- `0x18000b584`
- `0x18000b8f4`
- `0x18000e000`
- `0x18000f2f8`
- `0x18000f638`
- `0x18000fd94`
- `0x18000ffc0`
- `0x18001705c`
- `0x1800170a4`
- `0x1800173c0`
- `0x180017b20`
- `0x180017d30`
- `0x180018a10`
- `0x180018ae0`
- `0x180018e40`
- `0x180019330`
- `0x180019400`
- `0x180019920`
- `0x18001a150`
- `0x18001a2b0`
- `0x18001a3c0`
- `0x18001a7a0`
- `0x18001d33c`
- `0x18001d404`
- `0x18001d590`

## callees

- `0x180001564`
- `0x180007d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007da0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007da0`

## pseudocode

```c
__int64 __fastcall mregDecUsagePtr(struct _MMDRV *a1)
{
  unsigned __int32 v2; // ebx

  EnterCriticalSection(&NumDevsCritSec);
  v2 = _InterlockedDecrement((volatile signed __int32 *)a1 + 23);
  if ( !v2 )
    mregRemoveDriver(a1);
  LeaveCriticalSection(&NumDevsCritSec);
  return v2;
}

```

## disassembly

```asm
0x180007d70  mov     [rsp+arg_0], rbx
0x180007d75  push    rdi
0x180007d76  sub     rsp, 20h
0x180007d7a  mov     rdi, rcx
0x180007d7d  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180007d84  call    cs:__imp_EnterCriticalSection
0x180007d8a  mov     ebx, 0FFFFFFFFh
0x180007d8f  lock xadd [rdi+5Ch], ebx
0x180007d94  sub     ebx, 1
0x180007d97  jz      short loc_180007DB3
0x180007d99  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180007da0  call    cs:__imp_LeaveCriticalSection
0x180007da6  mov     eax, ebx
0x180007da8  mov     rbx, [rsp+28h+arg_0]
0x180007dad  add     rsp, 20h
0x180007db1  pop     rdi
0x180007db2  retn
0x180007db3  mov     rcx, rdi; struct _MMDRV *
0x180007db6  call    ?mregRemoveDriver@@YAXPEAU_MMDRV@@@Z; mregRemoveDriver(_MMDRV *)
0x180007dbb  jmp     short loc_180007D99
```
