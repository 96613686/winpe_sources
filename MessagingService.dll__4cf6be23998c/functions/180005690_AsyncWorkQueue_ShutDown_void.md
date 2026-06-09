# AsyncWorkQueue::ShutDown(void)

- ea: `0x180005690`
- end: `0x1800056ba`
- name: `?ShutDown@AsyncWorkQueue@@UEAAXXZ`
- size: `42`
- prototype: `void __fastcall(struct _TP_WORK **this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005690`
- `0x1800058c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800056ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800056ae`

## pseudocode

```c
void __fastcall AsyncWorkQueue::ShutDown(struct _TP_WORK **this)
{
  struct _TP_WORK *v2; // rcx

  AsyncWorkQueue::_CancelAllAsync((AsyncWorkQueue *)this, 1);
  v2 = this[12];
  if ( v2 )
    WaitForThreadpoolWorkCallbacks(v2, 0);
}

```

## disassembly

```asm
0x180005690  push    rbx
0x180005692  sub     rsp, 20h
0x180005696  mov     edx, 1; int
0x18000569b  mov     rbx, rcx
0x18000569e  call    ?_CancelAllAsync@AsyncWorkQueue@@AEAAXH@Z; AsyncWorkQueue::_CancelAllAsync(int)
0x1800056a3  mov     rcx, [rbx+60h]; pwk
0x1800056a7  test    rcx, rcx
0x1800056aa  jz      short loc_1800056B4
0x1800056ac  xor     edx, edx; fCancelPendingCallbacks
0x1800056ae  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800056b4  add     rsp, 20h
0x1800056b8  pop     rbx
0x1800056b9  retn
```
