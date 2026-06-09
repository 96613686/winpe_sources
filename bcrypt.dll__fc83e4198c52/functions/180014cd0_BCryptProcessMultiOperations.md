# BCryptProcessMultiOperations

- ea: `0x180014cd0`
- end: `0x180014d4b`
- name: `BCryptProcessMultiOperations`
- size: `123`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005060`
- `0x18000cac0`
- `0x180014cd0`
- `0x18001c010`

## string_xrefs

- `0x180014d2f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 BCryptProcessMultiOperations()
{
  __int64 v0; // rax
  __int64 v1; // r8
  __int64 v2; // r10
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rcx

  v0 = ValidateBaseHashHandle();
  if ( !v0 || (v2 = *(_QWORD *)(v0 + 8), *(_WORD *)(v2 + 48) < 2u) )
  {
    v3 = -1073741816;
    v4 = 6351;
    v5 = 3221225480LL;
    goto LABEL_7;
  }
  if ( !v1 )
  {
    v3 = -1073741811;
    v4 = 6358;
    v5 = 3221225485LL;
LABEL_7:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v4);
    return v3;
  }
  return (*(unsigned int (__fastcall **)(_QWORD))(v2 + 136))(*(_QWORD *)(v0 + 16));
}

```

## disassembly

```asm
0x180014cd0  push    rbx
0x180014cd2  sub     rsp, 30h
0x180014cd6  call    ValidateBaseHashHandle
0x180014cdb  test    rax, rax
0x180014cde  jz      short loc_180014D1F
0x180014ce0  mov     r10, [rax+8]
0x180014ce4  cmp     word ptr [r10+30h], 2
0x180014cea  jb      short loc_180014D1F
0x180014cec  test    r8, r8
0x180014cef  jnz     short loc_180014D03
0x180014cf1  mov     ebx, 0C000000Dh
0x180014cf6  mov     r9d, 18D6h
0x180014cfc  mov     ecx, 0C000000Dh
0x180014d01  jmp     short loc_180014D2F
0x180014d03  mov     ecx, [rsp+38h+arg_20]
0x180014d07  mov     [rsp+38h+var_18], ecx
0x180014d0b  mov     rcx, [rax+10h]
0x180014d0f  mov     rax, [r10+88h]
0x180014d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d1b  mov     ebx, eax
0x180014d1d  jmp     short loc_180014D42
0x180014d1f  mov     ebx, 0C0000008h
0x180014d24  mov     r9d, 18CFh
0x180014d2a  mov     ecx, 0C0000008h
0x180014d2f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014d36  lea     rdx, aStatus; "Status"
0x180014d3d  call    DebugTraceError
0x180014d42  mov     eax, ebx
0x180014d44  add     rsp, 30h
0x180014d48  pop     rbx
0x180014d49  retn
```
