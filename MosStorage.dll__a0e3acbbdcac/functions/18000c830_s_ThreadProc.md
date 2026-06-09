# s_ThreadProc

- ea: `0x18000c830`
- end: `0x18000c858`
- name: `s_ThreadProc`
- size: `40`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c060`

## pseudocode

```c
__int64 __fastcall s_ThreadProc(_DWORD *Parameter)
{
  Parameter[8] = StoragePerfGetAverageSpeedForId(
                   *(_QWORD *)Parameter,
                   *((_QWORD *)Parameter + 1),
                   Parameter + 4,
                   Parameter + 6);
  return 0;
}

```

## disassembly

```asm
0x18000c830  push    rbx
0x18000c832  sub     rsp, 20h
0x18000c836  mov     rdx, [rcx+8]
0x18000c83a  lea     r9, [rcx+18h]
0x18000c83e  mov     rbx, rcx
0x18000c841  lea     r8, [rcx+10h]
0x18000c845  mov     rcx, [rcx]
0x18000c848  call    StoragePerfGetAverageSpeedForId
0x18000c84d  mov     [rbx+20h], eax
0x18000c850  xor     eax, eax
0x18000c852  add     rsp, 20h
0x18000c856  pop     rbx
0x18000c857  retn
```
