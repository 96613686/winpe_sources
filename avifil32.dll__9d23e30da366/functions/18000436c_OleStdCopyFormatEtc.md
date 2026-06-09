# OleStdCopyFormatEtc

- ea: `0x18000436c`
- end: `0x1800043bf`
- name: `OleStdCopyFormatEtc`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044d0`
- `0x180004700`

## callees

- `0x18000436c`
- `0x1800043c8`

## pseudocode

```c
__int64 __fastcall OleStdCopyFormatEtc(__int64 a1, __int64 a2)
{
  if ( !a1 || !a2 )
    return 0;
  *(_WORD *)a1 = *(_WORD *)a2;
  *(_QWORD *)(a1 + 8) = OleStdCopyTargetDevice(*(unsigned int **)(a2 + 8));
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(a2 + 16);
  *(_DWORD *)(a1 + 20) = *(_DWORD *)(a2 + 20);
  *(_DWORD *)(a1 + 24) = *(_DWORD *)(a2 + 24);
  return 1;
}

```

## disassembly

```asm
0x18000436c  mov     [rsp+arg_0], rbx
0x180004371  push    rdi
0x180004372  sub     rsp, 20h
0x180004376  mov     rbx, rdx
0x180004379  mov     rdi, rcx
0x18000437c  test    rcx, rcx
0x18000437f  jz      short loc_1800043B2
0x180004381  test    rdx, rdx
0x180004384  jz      short loc_1800043B2
0x180004386  movzx   eax, word ptr [rdx]
0x180004389  mov     [rcx], ax
0x18000438c  mov     rcx, [rdx+8]; Src
0x180004390  call    OleStdCopyTargetDevice
0x180004395  mov     [rdi+8], rax
0x180004399  mov     eax, [rbx+10h]
0x18000439c  mov     [rdi+10h], eax
0x18000439f  mov     eax, [rbx+14h]
0x1800043a2  mov     [rdi+14h], eax
0x1800043a5  mov     eax, [rbx+18h]
0x1800043a8  mov     [rdi+18h], eax
0x1800043ab  mov     eax, 1
0x1800043b0  jmp     short loc_1800043B4
0x1800043b2  xor     eax, eax
0x1800043b4  mov     rbx, [rsp+28h+arg_0]
0x1800043b9  add     rsp, 20h
0x1800043bd  pop     rdi
0x1800043be  retn
```
