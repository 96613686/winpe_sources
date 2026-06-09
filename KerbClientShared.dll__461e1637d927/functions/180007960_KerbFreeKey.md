# KerbFreeKey

- ea: `0x180007960`
- end: `0x1800079b8`
- name: `KerbFreeKey`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bdb8`
- `0x18000c8c0`
- `0x18000d53c`
- `0x18000d784`
- `0x180015e10`
- `0x180016c20`

## callees

- `0x180007960`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall KerbFreeKey(__int64 a1)
{
  _BYTE *v1; // rax
  __int64 v3; // rdx
  __int64 result; // rax

  v1 = *(_BYTE **)(a1 + 24);
  if ( v1 )
  {
    v3 = *(unsigned int *)(a1 + 16);
    if ( *(_DWORD *)(a1 + 16) )
    {
      do
      {
        *v1++ = 0;
        --v3;
      }
      while ( v3 );
    }
    if ( *(_QWORD *)(a1 + 24) )
      ((void (*)(void))qword_1800334A8)();
  }
  result = 0;
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  return result;
}

```

## disassembly

```asm
0x180007960  push    rbx
0x180007962  sub     rsp, 20h
0x180007966  mov     rax, [rcx+18h]
0x18000796a  mov     rbx, rcx
0x18000796d  test    rax, rax
0x180007970  jz      short loc_1800079A2
0x180007972  mov     edx, [rcx+10h]
0x180007975  test    rdx, rdx
0x180007978  jz      short loc_18000798D
0x18000797a  nop     word ptr [rax+rax+00h]
0x180007980  mov     byte ptr [rax], 0
0x180007983  lea     rax, [rax+1]
0x180007987  sub     rdx, 1
0x18000798b  jnz     short loc_180007980
0x18000798d  mov     rcx, [rcx+18h]
0x180007991  test    rcx, rcx
0x180007994  jz      short loc_1800079A2
0x180007996  mov     rax, cs:qword_1800334A8
0x18000799d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079a2  xorps   xmm0, xmm0
0x1800079a5  xor     eax, eax
0x1800079a7  movups  xmmword ptr [rbx], xmm0
0x1800079aa  movups  xmmword ptr [rbx+10h], xmm0
0x1800079ae  mov     [rbx+20h], rax
0x1800079b2  add     rsp, 20h
0x1800079b6  pop     rbx
0x1800079b7  retn
```
