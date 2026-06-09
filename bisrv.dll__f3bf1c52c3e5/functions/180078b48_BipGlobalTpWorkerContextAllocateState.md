# BipGlobalTpWorkerContextAllocateState

- ea: `0x180078b48`
- end: `0x180078bf3`
- name: `BipGlobalTpWorkerContextAllocateState`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18007a320`

## callees

- `0x180078b48`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x180078bd7`
- `ntdll!TpAllocTimer` at `0x180078bd7`
- `ntdll!TpSetPoolMaxThreads` at `0x180078b70`
- `ntdll!TpSetPoolMaxThreads` at `0x180078b91`
- `ntdll!TpSetPoolMaxThreads` at `0x180078b70`
- `ntdll!TpSetPoolMaxThreads` at `0x180078b91`
- `ntdll!TpAllocPool` at `0x180078b5b`
- `ntdll!TpAllocPool` at `0x180078b7c`
- `ntdll!TpAllocPool` at `0x180078b9d`
- `ntdll!TpAllocPool` at `0x180078b5b`
- `ntdll!TpAllocPool` at `0x180078b7c`
- `ntdll!TpAllocPool` at `0x180078b9d`
- `ntdll!TpAllocWork` at `0x180078bba`
- `ntdll!TpAllocWork` at `0x180078bba`

## pseudocode

```c
__int64 __fastcall BipGlobalTpWorkerContextAllocateState(__int64 a1)
{
  int v2; // edx

  v2 = TpAllocPool(a1 + 16, 0);
  if ( v2 >= 0 )
  {
    TpSetPoolMaxThreads(*(_QWORD *)(a1 + 16), 16);
    v2 = TpAllocPool(a1 + 24, 0);
    if ( v2 >= 0 )
    {
      TpSetPoolMaxThreads(*(_QWORD *)(a1 + 24), 16);
      v2 = TpAllocPool(a1 + 32, 0);
      if ( v2 >= 0 )
      {
        v2 = TpAllocWork(a1 + 40, &BipEventDestroyWorker, a1, 0);
        if ( v2 >= 0 )
        {
          v2 = TpAllocTimer(a1 + 72, &BipGlobalTpActivityTimerCallback, a1, 0);
          if ( v2 >= 0 )
            return 0;
        }
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180078b48  mov     [rsp+arg_0], rbx
0x180078b4d  push    rdi
0x180078b4e  sub     rsp, 20h
0x180078b52  mov     rbx, rcx
0x180078b55  xor     edx, edx
0x180078b57  add     rcx, 10h
0x180078b5b  call    cs:__imp_TpAllocPool
0x180078b61  mov     edx, eax
0x180078b63  test    eax, eax
0x180078b65  js      short loc_180078BE6
0x180078b67  mov     rcx, [rbx+10h]
0x180078b6b  mov     edx, 10h
0x180078b70  call    cs:__imp_TpSetPoolMaxThreads
0x180078b76  xor     edx, edx
0x180078b78  lea     rcx, [rbx+18h]
0x180078b7c  call    cs:__imp_TpAllocPool
0x180078b82  mov     edx, eax
0x180078b84  test    eax, eax
0x180078b86  js      short loc_180078BE6
0x180078b88  mov     rcx, [rbx+18h]
0x180078b8c  mov     edx, 10h
0x180078b91  call    cs:__imp_TpSetPoolMaxThreads
0x180078b97  lea     rcx, [rbx+20h]
0x180078b9b  xor     edx, edx
0x180078b9d  call    cs:__imp_TpAllocPool
0x180078ba3  mov     edx, eax
0x180078ba5  test    eax, eax
0x180078ba7  js      short loc_180078BE6
0x180078ba9  lea     rcx, [rbx+28h]
0x180078bad  xor     r9d, r9d
0x180078bb0  mov     r8, rbx
0x180078bb3  lea     rdx, BipEventDestroyWorker
0x180078bba  call    cs:__imp_TpAllocWork
0x180078bc0  mov     edx, eax
0x180078bc2  test    eax, eax
0x180078bc4  js      short loc_180078BE6
0x180078bc6  lea     rcx, [rbx+48h]
0x180078bca  xor     r9d, r9d
0x180078bcd  mov     r8, rbx
0x180078bd0  lea     rdx, BipGlobalTpActivityTimerCallback
0x180078bd7  call    cs:__imp_TpAllocTimer
0x180078bdd  mov     edx, eax
0x180078bdf  xor     eax, eax
0x180078be1  test    edx, edx
0x180078be3  cmovns  edx, eax
0x180078be6  mov     rbx, [rsp+28h+arg_0]
0x180078beb  mov     eax, edx
0x180078bed  add     rsp, 20h
0x180078bf1  pop     rdi
0x180078bf2  retn
```
