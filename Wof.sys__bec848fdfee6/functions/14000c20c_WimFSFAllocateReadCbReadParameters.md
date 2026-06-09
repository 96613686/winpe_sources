# WimFSFAllocateReadCbReadParameters

- ea: `0x14000c20c`
- end: `0x14000c246`
- name: `WimFSFAllocateReadCbReadParameters`
- size: `58`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002d6c8`
- `0x14003d320`

## callees

- `0x14000c20c`
- `0x14000c24c`

## pseudocode

```c
__int64 __fastcall WimFSFAllocateReadCbReadParameters(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  v5 = 0;
  result = WimFSFAllocateReadCompletionContext(a1, a2, &v5);
  if ( !(_DWORD)result )
    *a3 = v5 + 24;
  return result;
}

```

## disassembly

```asm
0x14000c20c  push    rbx
0x14000c20e  sub     rsp, 20h
0x14000c212  mov     rbx, r8
0x14000c215  mov     qword ptr [r8], 0
0x14000c21c  lea     r8, [rsp+28h+arg_10]
0x14000c221  mov     [rsp+28h+arg_10], 0
0x14000c22a  call    WimFSFAllocateReadCompletionContext
0x14000c22f  test    eax, eax
0x14000c231  jnz     short loc_14000C23F
0x14000c233  mov     rcx, [rsp+28h+arg_10]
0x14000c238  add     rcx, 18h
0x14000c23c  mov     [rbx], rcx
0x14000c23f  add     rsp, 20h
0x14000c243  pop     rbx
0x14000c244  retn
```
