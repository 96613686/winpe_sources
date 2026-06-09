# SuCleanup(void)

- ea: `0x1400082e4`
- end: `0x1400083d3`
- name: `?SuCleanup@@YAHXZ`
- size: `239`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002ce8`
- `0x140002f8c`

## callees

- `0x140001caf`
- `0x14000353c`
- `0x140007db0`
- `0x1400082e4`
- `0x140009924`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000832f`
- `KERNEL32!CloseHandle` at `0x14000832f`
- `KERNEL32!SetLastError` at `0x140008300`
- `KERNEL32!SetLastError` at `0x140008300`
- `KERNEL32!GetLastError` at `0x14000834b`
- `KERNEL32!GetLastError` at `0x14000834b`
- `KERNEL32!CloseThreadpool` at `0x140008386`
- `KERNEL32!CloseThreadpool` at `0x140008386`

## pseudocode

```c
__int64 __fastcall SuCleanup(void **a1)
{
  unsigned int v1; // ebx
  const char *v2; // rdi
  char LastError; // al
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d

  SiAcquireSpinLock(a1);
  if ( ReferenceCount )
  {
    if ( ReferenceCount != 1 )
    {
      v1 = 1;
      --ReferenceCount;
      goto LABEL_10;
    }
    v1 = CloseHandle(Spaceport);
    if ( v1 )
    {
      Spaceport = (HANDLE)-1LL;
      CloseThreadpool(Threadpool);
      Threadpool = 0;
      memset_0(&ModuleName, 0, 0x208u);
      McGenEventUnregister_EventUnregister(SpaceApiProvider_Context);
      --ReferenceCount;
      goto LABEL_10;
    }
    v2 = "CloseHandle";
  }
  else
  {
    SetLastError(6u);
    v1 = 0;
    v2 = "ReferenceCount == 0";
  }
  if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    LastError = GetLastError();
    McTemplateK0zssq_EventWriteTransfer(
      v4,
      (unsigned int)CleanupApiFailed,
      v5,
      v6,
      (__int64)"SuCleanup",
      (__int64)v2,
      LastError);
  }
LABEL_10:
  _InterlockedExchange64((volatile __int64 *)&Lock, 0);
  return v1;
}

```

## disassembly

```asm
0x1400082e4  mov     [rsp+arg_0], rbx
0x1400082e9  push    rdi
0x1400082ea  sub     rsp, 40h
0x1400082ee  call    ?SiAcquireSpinLock@@YAXPEAPEAX@Z; SiAcquireSpinLock(void * *)
0x1400082f3  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1400082f9  test    eax, eax
0x1400082fb  jnz     short loc_140008311
0x1400082fd  lea     ecx, [rax+6]; dwErrCode
0x140008300  call    cs:__imp_SetLastError
0x140008306  xor     ebx, ebx
0x140008308  lea     rdi, aReferencecount; "ReferenceCount == 0"
0x14000830f  jmp     short loc_140008342
0x140008311  cmp     eax, 1
0x140008314  jz      short loc_140008328
0x140008316  dec     eax
0x140008318  mov     ebx, 1
0x14000831d  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x140008323  jmp     loc_1400083BD
0x140008328  mov     rcx, cs:?Spaceport@@3PEAXEA; hObject
0x14000832f  call    cs:__imp_CloseHandle
0x140008335  mov     ebx, eax
0x140008337  test    eax, eax
0x140008339  jnz     short loc_140008374
0x14000833b  lea     rdi, aClosehandle; "CloseHandle"
0x140008342  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x140008349  jz      short loc_1400083BD
0x14000834b  call    cs:__imp_GetLastError
0x140008351  mov     [rsp+48h+var_18], eax
0x140008355  lea     rdx, CleanupApiFailed
0x14000835c  lea     rax, aSucleanup; "SuCleanup"
0x140008363  mov     [rsp+48h+var_20], rdi
0x140008368  mov     [rsp+48h+var_28], rax
0x14000836d  call    McTemplateK0zssq_EventWriteTransfer
0x140008372  jmp     short loc_1400083BD
0x140008374  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x14000837b  mov     cs:?Spaceport@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * Spaceport
0x140008386  call    cs:__imp_CloseThreadpool
0x14000838c  xor     edx, edx; Val
0x14000838e  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * Threadpool
0x140008399  mov     r8d, 208h; Size
0x14000839f  lea     rcx, ?ModuleName@@3PAGA; void *
0x1400083a6  call    memset_0
0x1400083ab  lea     rcx, SpaceApiProvider_Context
0x1400083b2  call    McGenEventUnregister_EventUnregister
0x1400083b7  dec     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1400083bd  xor     eax, eax
0x1400083bf  xchg    rax, cs:?Lock@@3PEAXEA; void * Lock
0x1400083c6  mov     eax, ebx
0x1400083c8  mov     rbx, [rsp+48h+arg_0]
0x1400083cd  add     rsp, 40h
0x1400083d1  pop     rdi
0x1400083d2  retn
```
