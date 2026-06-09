# CProfileCache::QueryInterface(_GUID const &,void * *)

- ea: `0x180006920`
- end: `0x18000697a`
- name: `?QueryInterface@CProfileCache@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `90`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006920`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CProfileCache::QueryInterface(CProfileCache *this, const struct _GUID *a2, void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_22d2e146_1a68_40b8_949c_8fd848b415e6.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_22d2e146_1a68_40b8_949c_8fd848b415e6.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CProfileCache *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180006920  sub     rsp, 28h
0x180006924  mov     rax, [rdx]
0x180006927  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x18000692e  jnz     short loc_18000693D
0x180006930  mov     rax, [rdx+8]
0x180006934  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000693b  jz      short loc_180006956
0x18000693d  mov     rax, [rdx]
0x180006940  cmp     rax, qword ptr cs:_GUID_22d2e146_1a68_40b8_949c_8fd848b415e6.Data1
0x180006947  jnz     short loc_180006969
0x180006949  mov     rax, [rdx+8]
0x18000694d  cmp     rax, qword ptr cs:_GUID_22d2e146_1a68_40b8_949c_8fd848b415e6.Data4
0x180006954  jnz     short loc_180006969
0x180006956  mov     [r8], rcx
0x180006959  mov     rax, [rcx]
0x18000695c  mov     rax, [rax+8]
0x180006960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006965  xor     eax, eax
0x180006967  jmp     short loc_180006975
0x180006969  mov     qword ptr [r8], 0
0x180006970  mov     eax, 80004002h
0x180006975  add     rsp, 28h
0x180006979  retn
```
