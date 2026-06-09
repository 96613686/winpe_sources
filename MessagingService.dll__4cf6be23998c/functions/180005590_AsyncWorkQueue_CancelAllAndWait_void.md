# AsyncWorkQueue::CancelAllAndWait(void)

- ea: `0x180005590`
- end: `0x1800055b7`
- name: `?CancelAllAndWait@AsyncWorkQueue@@UEAAXXZ`
- size: `39`
- prototype: `void __fastcall(struct _TP_WORK **this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005590`
- `0x1800058c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800055ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800055ab`

## pseudocode

```c
void __fastcall AsyncWorkQueue::CancelAllAndWait(struct _TP_WORK **this)
{
  struct _TP_WORK *v2; // rcx

  AsyncWorkQueue::_CancelAllAsync((AsyncWorkQueue *)this, 0);
  v2 = this[12];
  if ( v2 )
    WaitForThreadpoolWorkCallbacks(v2, 0);
}

```

## disassembly

```asm
0x180005590  push    rbx
0x180005592  sub     rsp, 20h
0x180005596  xor     edx, edx; int
0x180005598  mov     rbx, rcx
0x18000559b  call    ?_CancelAllAsync@AsyncWorkQueue@@AEAAXH@Z; AsyncWorkQueue::_CancelAllAsync(int)
0x1800055a0  mov     rcx, [rbx+60h]; pwk
0x1800055a4  test    rcx, rcx
0x1800055a7  jz      short loc_1800055B1
0x1800055a9  xor     edx, edx; fCancelPendingCallbacks
0x1800055ab  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800055b1  add     rsp, 20h
0x1800055b5  pop     rbx
0x1800055b6  retn
```
