# AipPluginInvokeIoctlCallback

- ea: `0x1400218c0`
- end: `0x14002191b`
- name: `AipPluginInvokeIoctlCallback`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001f340`

## callees

- `0x140006a60`
- `0x1400218c0`

## pseudocode

```c
__int64 __fastcall AipPluginInvokeIoctlCallback(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v5; // rcx
  __int64 (__fastcall *v7)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // r10

  result = 0;
  v5 = *(_QWORD *)(a3 + 16);
  if ( *a2 == v5 )
  {
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))(a1 + 48);
    if ( v7 )
    {
      result = v7(
                 v5,
                 *(unsigned int *)(a3 + 24),
                 *(_QWORD *)(a3 + 32),
                 *(unsigned int *)(a3 + 40),
                 *(_QWORD *)(a3 + 48),
                 *(_DWORD *)(a3 + 56),
                 *(_QWORD *)(a3 + 64));
      *(_DWORD *)(a3 + 72) = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400218c0  push    rbx
0x1400218c2  sub     rsp, 40h
0x1400218c6  mov     r10, rcx
0x1400218c9  xor     eax, eax
0x1400218cb  mov     rcx, [r8+10h]
0x1400218cf  mov     rbx, r8
0x1400218d2  cmp     [rdx], rcx
0x1400218d5  jnz     short loc_140021914
0x1400218d7  mov     r10, [r10+30h]
0x1400218db  test    r10, r10
0x1400218de  jz      short loc_140021914
0x1400218e0  mov     rax, [r8+40h]
0x1400218e4  mov     r9d, [r8+28h]
0x1400218e8  mov     edx, [rbx+18h]
0x1400218eb  mov     [rsp+48h+var_18], rax
0x1400218f0  mov     eax, [r8+38h]
0x1400218f4  mov     [rsp+48h+var_20], eax
0x1400218f8  mov     rax, [r8+30h]
0x1400218fc  mov     r8, [r8+20h]
0x140021900  mov     [rsp+48h+var_28], rax
0x140021905  mov     rax, r10
0x140021908  call    _guard_dispatch_icall
0x14002190d  mov     dword ptr [rbx+48h], 1
0x140021914  add     rsp, 40h
0x140021918  pop     rbx
0x140021919  retn
```
