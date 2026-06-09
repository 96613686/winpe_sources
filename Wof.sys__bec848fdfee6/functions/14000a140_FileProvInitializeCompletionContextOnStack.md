# FileProvInitializeCompletionContextOnStack

- ea: `0x14000a140`
- end: `0x14000a1d6`
- name: `FileProvInitializeCompletionContextOnStack`
- size: `150`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140038b10`

## callees

- `0x14000a140`
- `0x14000d3fc`
- `0x1400119c0`

## pseudocode

```c
__int64 __fastcall FileProvInitializeCompletionContextOnStack(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  memset((void *)a3, 0, 0xE0u);
  *(_OWORD *)(a3 + 24) = *(_OWORD *)a1;
  *(_OWORD *)(a3 + 40) = *(_OWORD *)(a1 + 16);
  *(_OWORD *)(a3 + 56) = *(_OWORD *)(a1 + 32);
  *(_OWORD *)(a3 + 72) = *(_OWORD *)(a1 + 48);
  *(_OWORD *)(a3 + 88) = *(_OWORD *)(a1 + 64);
  *(_QWORD *)(a3 + 104) = *(_QWORD *)(a1 + 80);
  *(_DWORD *)(a3 + 100) |= 1u;
  *(_DWORD *)(a3 + 16) = 1;
  result = HIDWORD(WPP_GLOBAL_Control->Timer);
  if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    return WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids, a3);
  return result;
}

```

## disassembly

```asm
0x14000a140  mov     [rsp+arg_0], rbx
0x14000a145  push    rdi
0x14000a146  sub     rsp, 20h
0x14000a14a  mov     rdi, r8
0x14000a14d  mov     rbx, rcx
0x14000a150  mov     rcx, rdi; void *
0x14000a153  xor     edx, edx; Val
0x14000a155  mov     r8d, 0E0h; Size
0x14000a15b  call    memset
0x14000a160  movups  xmm0, xmmword ptr [rbx]
0x14000a163  movups  xmmword ptr [rdi+18h], xmm0
0x14000a167  movups  xmm1, xmmword ptr [rbx+10h]
0x14000a16b  movups  xmmword ptr [rdi+28h], xmm1
0x14000a16f  movups  xmm0, xmmword ptr [rbx+20h]
0x14000a173  movups  xmmword ptr [rdi+38h], xmm0
0x14000a177  movups  xmm1, xmmword ptr [rbx+30h]
0x14000a17b  movups  xmmword ptr [rdi+48h], xmm1
0x14000a17f  movups  xmm0, xmmword ptr [rbx+40h]
0x14000a183  movups  xmmword ptr [rdi+58h], xmm0
0x14000a187  movsd   xmm1, qword ptr [rbx+50h]
0x14000a18c  movsd   qword ptr [rdi+68h], xmm1
0x14000a191  or      dword ptr [rdi+64h], 1
0x14000a195  mov     dword ptr [rdi+10h], 1
0x14000a19c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a1a3  mov     eax, [rcx+2Ch]
0x14000a1a6  test    al, 20h
0x14000a1a8  jnz     short loc_14000A1B6
0x14000a1aa  mov     rbx, [rsp+28h+arg_0]
0x14000a1af  add     rsp, 20h
0x14000a1b3  pop     rdi
0x14000a1b4  retn
0x14000a1b6  cmp     byte ptr [rcx+29h], 5
0x14000a1ba  jb      short loc_14000A1AA
0x14000a1bc  mov     rcx, [rcx+18h]
0x14000a1c0  lea     r8, WPP_eaaba969f297373d9ffb29335f34480c_Traceguids
0x14000a1c7  mov     edx, 0Ah
0x14000a1cc  mov     r9, rdi
0x14000a1cf  call    WPP_SF_q
0x14000a1d4  jmp     short loc_14000A1AA
```
