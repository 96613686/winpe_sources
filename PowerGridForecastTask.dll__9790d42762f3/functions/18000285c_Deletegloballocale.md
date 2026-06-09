# _Deletegloballocale

- ea: `0x18000285c`
- end: `0x180002894`
- name: `_Deletegloballocale`
- size: `56`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028a0`

## callees

- `0x18000285c`
- `0x180037010`

## pseudocode

```c
void __fastcall Deletegloballocale(__int64 *a1)
{
  __int64 v1; // rcx
  void (__fastcall ***v2)(_QWORD, __int64); // rax

  v1 = *a1;
  if ( v1 )
  {
    v2 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
    if ( v2 )
      (**v2)(v2, 1);
  }
}

```

## disassembly

```asm
0x18000285c  sub     rsp, 28h
0x180002860  mov     rcx, [rcx]
0x180002863  test    rcx, rcx
0x180002866  jz      short loc_18000288F
0x180002868  mov     rax, [rcx]
0x18000286b  mov     rax, [rax+10h]
0x18000286f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002874  mov     r8, rax
0x180002877  test    rax, rax
0x18000287a  jz      short loc_18000288F
0x18000287c  mov     rcx, [rax]
0x18000287f  mov     edx, 1
0x180002884  mov     rax, [rcx]
0x180002887  mov     rcx, r8
0x18000288a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000288f  add     rsp, 28h
0x180002893  retn
```
