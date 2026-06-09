# FaxInitializeEventQueue

- ea: `0x18000a710`
- end: `0x18000a763`
- name: `FaxInitializeEventQueue`
- size: `83`
- prototype: `BOOL __stdcall(HANDLE FaxHandle, HANDLE CompletionPort, ULONG_PTR CompletionKey, HWND hWnd, UINT MessageStart)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004394`
- `0x18000a710`

## pseudocode

```c
BOOL __stdcall FaxInitializeEventQueue(
        HANDLE FaxHandle,
        HANDLE CompletionPort,
        ULONG_PTR CompletionKey,
        HWND hWnd,
        UINT MessageStart)
{
  if ( hWnd && CompletionKey == -1 )
    return 1;
  else
    return FaxStartServerNotification(
             FaxHandle,
             0,
             0,
             0,
             CompletionPort,
             CompletionKey,
             hWnd,
             MessageStart,
             0x10000u,
             0);
}

```

## disassembly

```asm
0x18000a710  sub     rsp, 58h
0x18000a714  test    r9, r9
0x18000a717  jz      short loc_18000A725
0x18000a719  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a71d  jnz     short loc_18000A725
0x18000a71f  lea     eax, [r8+2]
0x18000a723  jmp     short loc_18000A75D
0x18000a725  mov     eax, [rsp+58h+MessageStart]
0x18000a72c  mov     [rsp+58h+var_10], 0; void **
0x18000a735  mov     [rsp+58h+var_18], 10000h; unsigned int
0x18000a73d  mov     [rsp+58h+var_20], eax; unsigned int
0x18000a741  mov     [rsp+58h+var_28], r9; HWND
0x18000a746  xor     r9d, r9d; unsigned int
0x18000a749  mov     [rsp+58h+var_30], r8; unsigned __int64
0x18000a74e  xor     r8d, r8d; unsigned int
0x18000a751  mov     [rsp+58h+var_38], rdx; void *
0x18000a756  xor     edx, edx; unsigned __int16 *
0x18000a758  call    ?FaxStartServerNotification@@YAHPEAXPEBGKK0_KPEAUHWND__@@KKPEAPEAX@Z; FaxStartServerNotification(void *,ushort const *,ulong,ulong,void *,unsigned __int64,HWND__ *,ulong,ulong,void * *)
0x18000a75d  add     rsp, 58h
0x18000a761  retn
```
