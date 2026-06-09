# av_buffer_ref

- ea: `0x18002f150`
- end: `0x18002f18c`
- name: `av_buffer_ref`
- size: `60`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f190`
- `0x18003b7d0`
- `0x18003bfe0`
- `0x18003f0e0`
- `0x18003f2d0`
- `0x18003f3e0`
- `0x18003f600`
- `0x180050760`
- `0x180050880`

## callees

- `0x18002f150`
- `0x180044aa0`

## pseudocode

```c
_QWORD *__fastcall av_buffer_ref(_QWORD *a1)
{
  _QWORD *result; // rax

  result = av_mallocz(0x18u);
  if ( result )
  {
    *(_OWORD *)result = *(_OWORD *)a1;
    result[2] = a1[2];
    _InterlockedIncrement64((volatile signed __int64 *)(*a1 + 16LL));
  }
  return result;
}

```

## disassembly

```asm
0x18002f150  push    rbx
0x18002f152  sub     rsp, 20h
0x18002f156  mov     rbx, rcx
0x18002f159  mov     ecx, 18h
0x18002f15e  call    av_mallocz
0x18002f163  mov     rdx, rax
0x18002f166  test    rax, rax
0x18002f169  jz      short loc_18002F186
0x18002f16b  movups  xmm0, xmmword ptr [rbx]
0x18002f16e  movups  xmmword ptr [rax], xmm0
0x18002f171  movsd   xmm1, qword ptr [rbx+10h]
0x18002f176  movsd   qword ptr [rax+10h], xmm1
0x18002f17b  mov     rax, [rbx]
0x18002f17e  lock inc qword ptr [rax+10h]
0x18002f183  mov     rax, rdx
0x18002f186  add     rsp, 20h
0x18002f18a  pop     rbx
0x18002f18b  retn
```
