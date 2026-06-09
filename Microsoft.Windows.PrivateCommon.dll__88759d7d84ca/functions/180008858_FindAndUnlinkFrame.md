# _FindAndUnlinkFrame

- ea: `0x180008858`
- end: `0x1800088ab`
- name: `_FindAndUnlinkFrame`
- size: `83`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a530`

## callees

- `0x180007268`
- `0x180008858`
- `0x180008fc8`

## pseudocode

```c
__int64 __fastcall FindAndUnlinkFrame(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != *(_QWORD *)(_vcrt_getptd() + 88) || (v2 = *(_QWORD *)(_vcrt_getptd() + 88)) == 0 )
LABEL_7:
    abort_0();
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
0x180008858  mov     [rsp+arg_0], rbx
0x18000885d  push    rdi
0x18000885e  sub     rsp, 20h
0x180008862  mov     rdi, rcx
0x180008865  call    __vcrt_getptd
0x18000886a  cmp     rdi, [rax+58h]
0x18000886e  jnz     short loc_1800088A5
0x180008870  call    __vcrt_getptd
0x180008875  mov     rdx, [rax+58h]
0x180008879  test    rdx, rdx
0x18000887c  jz      short loc_1800088A5
0x18000887e  mov     rbx, [rdx+8]
0x180008882  cmp     rdi, rdx
0x180008885  jz      short loc_180008891
0x180008887  mov     rdx, rbx
0x18000888a  test    rbx, rbx
0x18000888d  jz      short loc_1800088A5
0x18000888f  jmp     short loc_18000887E
0x180008891  call    __vcrt_getptd
0x180008896  mov     [rax+58h], rbx
0x18000889a  mov     rbx, [rsp+28h+arg_0]
0x18000889f  add     rsp, 20h
0x1800088a3  pop     rdi
0x1800088a4  retn
0x1800088a5  call    abort_0
```
