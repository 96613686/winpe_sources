# SrpFreePlugin

- ea: `0x140024530`
- end: `0x140024595`
- name: `SrpFreePlugin`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14002459c`
- `0x14002bf44`

## callees

- `0x140020050`
- `0x140024530`
- `0x1400328b0`

## pseudocode

```c
__int64 __fastcall SrpFreePlugin(__int64 a1, unsigned int a2)
{
  unsigned int i; // ebx
  _OWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v7; // [rsp+40h] [rbp-18h]

  for ( i = 0; i < a2; ++i )
  {
    v7 = 0;
    memset(v6, 0, sizeof(v6));
    *((_QWORD *)&v7 + 1) = *(_QWORD *)(32LL * i + a1 + 24);
    SrpFreePolicy(v6);
  }
  return AiFree(a1);
}

```

## disassembly

```asm
0x140024530  mov     [rsp+arg_0], rbx
0x140024535  mov     [rsp+arg_8], rsi
0x14002453a  push    rdi
0x14002453b  sub     rsp, 50h
0x14002453f  xor     ebx, ebx
0x140024541  mov     esi, edx
0x140024543  mov     rdi, rcx
0x140024546  test    edx, edx
0x140024548  jz      short loc_14002457C
0x14002454a  xorps   xmm0, xmm0
0x14002454d  mov     eax, ebx
0x14002454f  shl     rax, 5
0x140024553  lea     rcx, [rsp+58h+var_38]
0x140024558  movups  [rsp+58h+var_18], xmm0
0x14002455d  movups  [rsp+58h+var_38], xmm0
0x140024562  mov     rax, [rax+rdi+18h]
0x140024567  mov     qword ptr [rsp+58h+var_18+8], rax
0x14002456c  movups  [rsp+58h+var_28], xmm0
0x140024571  call    SrpFreePolicy
0x140024576  inc     ebx
0x140024578  cmp     ebx, esi
0x14002457a  jb      short loc_14002454A
0x14002457c  mov     rcx, rdi
0x14002457f  call    AiFree
0x140024584  mov     rbx, [rsp+58h+arg_0]
0x140024589  mov     rsi, [rsp+58h+arg_8]
0x14002458e  add     rsp, 50h
0x140024592  pop     rdi
0x140024593  retn
```
