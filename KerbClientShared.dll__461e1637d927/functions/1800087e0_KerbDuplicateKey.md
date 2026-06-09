# KerbDuplicateKey

- ea: `0x1800087e0`
- end: `0x18000884d`
- name: `KerbDuplicateKey`
- size: `109`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180007e30`
- `0x18000d784`
- `0x18000d814`
- `0x180015010`
- `0x1800164e4`
- `0x180016680`

## callees

- `0x1800087e0`
- `0x1800283fc`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall KerbDuplicateKey(__int64 a1, __int64 a2)
{
  void *v4; // rax

  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 16) = *(_OWORD *)(a2 + 16);
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a2 + 32);
  v4 = (void *)((__int64 (__fastcall *)(_QWORD))qword_1800334A0)(*(unsigned int *)(a2 + 16));
  *(_QWORD *)(a1 + 24) = v4;
  if ( !v4 )
    return 60;
  memcpy_0(v4, *(const void **)(a2 + 24), *(unsigned int *)(a2 + 16));
  return 0;
}

```

## disassembly

```asm
0x1800087e0  mov     [rsp+arg_0], rbx
0x1800087e5  push    rdi
0x1800087e6  sub     rsp, 20h
0x1800087ea  movups  xmm0, xmmword ptr [rdx]
0x1800087ed  mov     rdi, rcx
0x1800087f0  mov     rbx, rdx
0x1800087f3  movups  xmmword ptr [rcx], xmm0
0x1800087f6  movups  xmm1, xmmword ptr [rdx+10h]
0x1800087fa  movups  xmmword ptr [rcx+10h], xmm1
0x1800087fe  movsd   xmm0, qword ptr [rdx+20h]
0x180008803  movsd   qword ptr [rcx+20h], xmm0
0x180008808  mov     ecx, [rdx+10h]
0x18000880b  mov     rax, cs:qword_1800334A0
0x180008812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008817  mov     [rdi+18h], rax
0x18000881b  test    rax, rax
0x18000881e  jz      short loc_18000883D
0x180008820  mov     r8d, [rbx+10h]; Size
0x180008824  mov     rcx, rax; void *
0x180008827  mov     rdx, [rbx+18h]; Src
0x18000882b  call    memcpy_0
0x180008830  xor     eax, eax
0x180008832  mov     rbx, [rsp+28h+arg_0]
0x180008837  add     rsp, 20h
0x18000883b  pop     rdi
0x18000883c  retn
0x18000883d  mov     rbx, [rsp+28h+arg_0]
0x180008842  mov     eax, 3Ch ; '<'
0x180008847  add     rsp, 20h
0x18000884b  pop     rdi
0x18000884c  retn
```
