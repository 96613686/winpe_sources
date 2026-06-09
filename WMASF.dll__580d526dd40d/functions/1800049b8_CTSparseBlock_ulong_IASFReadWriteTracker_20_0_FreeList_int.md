# CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)

- ea: `0x1800049b8`
- end: `0x180004a14`
- name: `?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x18000431c`
- `0x1800057f0`
- `0x180009960`
- `0x18000fd20`
- `0x1800166b0`
- `0x18001f110`
- `0x18001fd98`
- `0x180022050`
- `0x1800239f0`
- `0x1800270f0`
- `0x180027210`
- `0x180028e20`
- `0x18002b5e0`
- `0x1800337f0`
- `0x180033844`
- `0x180033888`
- `0x1800350b4`
- `0x18003ba44`
- `0x18003d080`

## callees

- `0x1800049b8`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rdi
  __int64 v4; // rdx

  *(_DWORD *)(a1 + 12) &= ~1u;
  result = 0;
  *(_DWORD *)(a1 + 8) = 0;
  *(_WORD *)(a1 + 24) = 0;
  *(_BYTE *)(a1 + 26) = 0;
  v3 = *(_QWORD *)(a1 + 192);
  *(_QWORD *)(a1 + 192) = 0;
  do
  {
    if ( !v3 )
      break;
    v4 = v3;
    v3 = *(_QWORD *)(v3 + 192);
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, v4);
  }
  while ( (int)result >= 0 );
  return result;
}

```

## disassembly

```asm
0x1800049b8  mov     [rsp+arg_0], rbx
0x1800049bd  push    rdi
0x1800049be  sub     rsp, 20h
0x1800049c2  and     dword ptr [rcx+0Ch], 0FFFFFFFEh
0x1800049c6  mov     rbx, rcx
0x1800049c9  xor     eax, eax
0x1800049cb  mov     dword ptr [rcx+8], 0
0x1800049d2  mov     [rcx+18h], ax
0x1800049d6  mov     [rcx+1Ah], al
0x1800049d9  mov     rdi, [rcx+0C0h]
0x1800049e0  mov     [rcx+0C0h], rax
0x1800049e7  test    rdi, rdi
0x1800049ea  jz      short loc_180004A09
0x1800049ec  mov     rax, [rbx]
0x1800049ef  mov     rdx, rdi
0x1800049f2  mov     rdi, [rdi+0C0h]
0x1800049f9  mov     rcx, rbx
0x1800049fc  mov     rax, [rax+8]
0x180004a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a05  test    eax, eax
0x180004a07  jns     short loc_1800049E7
0x180004a09  mov     rbx, [rsp+28h+arg_0]
0x180004a0e  add     rsp, 20h
0x180004a12  pop     rdi
0x180004a13  retn
```
