# AsyncWorkQueue::WaitForCallbacksToComplete(void)

- ea: `0x1800056c0`
- end: `0x1800056da`
- name: `?WaitForCallbacksToComplete@AsyncWorkQueue@@UEAAXXZ`
- size: `26`
- prototype: `void __fastcall(AsyncWorkQueue *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800056c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800056cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800056cf`

## pseudocode

```c
void __fastcall AsyncWorkQueue::WaitForCallbacksToComplete(AsyncWorkQueue *this)
{
  struct _TP_WORK *v1; // rcx

  v1 = (struct _TP_WORK *)*((_QWORD *)this + 12);
  if ( v1 )
    WaitForThreadpoolWorkCallbacks(v1, 0);
}

```

## disassembly

```asm
0x1800056c0  sub     rsp, 28h
0x1800056c4  mov     rcx, [rcx+60h]; pwk
0x1800056c8  test    rcx, rcx
0x1800056cb  jz      short loc_1800056D5
0x1800056cd  xor     edx, edx; fCancelPendingCallbacks
0x1800056cf  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800056d5  add     rsp, 28h
0x1800056d9  retn
```
