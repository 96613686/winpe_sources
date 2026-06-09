# _FindAndUnlinkFrame

- ea: `0x14000b8b4`
- end: `0x14000b907`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000d4b0`

## callees

- `0x14000a353`
- `0x14000b8b4`
- `0x14000be88`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort();
  while ( 1 )
  {
    v3 = *(_QWORD *)(v2 + 8);
    if ( a1 == v2 )
      break;
    v2 = *(_QWORD *)(v2 + 8);
    if ( !v3 )
      goto LABEL_7;
  }
  result = _vcrt_getptd();
  *(_QWORD *)(result + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x14000b8b4  mov     [rsp+arg_0], rbx
0x14000b8b9  push    rdi
0x14000b8ba  sub     rsp, 20h
0x14000b8be  mov     rdi, rcx
0x14000b8c1  call    __vcrt_getptd
0x14000b8c6  cmp     rdi, [rax+58h]
0x14000b8ca  jnz     short loc_14000B901
0x14000b8cc  call    __vcrt_getptd
0x14000b8d1  mov     rdx, [rax+58h]
0x14000b8d5  test    rdx, rdx
0x14000b8d8  jz      short loc_14000B901
0x14000b8da  mov     rbx, [rdx+8]
0x14000b8de  cmp     rdi, rdx
0x14000b8e1  jz      short loc_14000B8ED
0x14000b8e3  mov     rdx, rbx
0x14000b8e6  test    rbx, rbx
0x14000b8e9  jz      short loc_14000B901
0x14000b8eb  jmp     short loc_14000B8DA
0x14000b8ed  call    __vcrt_getptd
0x14000b8f2  mov     [rax+58h], rbx
0x14000b8f6  mov     rbx, [rsp+28h+arg_0]
0x14000b8fb  add     rsp, 20h
0x14000b8ff  pop     rdi
0x14000b900  retn
0x14000b901  call    abort
```
