# TsiFreeScheduleSid(_SCHEDULE_SID *)

- ea: `0x180005400`
- end: `0x18000542f`
- name: `?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(struct _SCHEDULE_SID *)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180002c04`
- `0x180004db0`
- `0x1800052e0`
- `0x180006410`
- `0x18000dc54`
- `0x180018dac`
- `0x18002005c`

## callees

- `0x180005400`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000541a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000541a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005411`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005411`

## pseudocode

```c
__int64 __fastcall TsiFreeScheduleSid(void **a1)
{
  if ( !a1 )
    return 2147500035LL;
  operator delete[](*a1);
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x180005400  push    rbx
0x180005402  sub     rsp, 20h
0x180005406  mov     rbx, rcx
0x180005409  test    rcx, rcx
0x18000540c  jz      short loc_180005428
0x18000540e  mov     rcx, [rcx]
0x180005411  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005417  mov     rcx, rbx
0x18000541a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005420  xor     eax, eax
0x180005422  add     rsp, 20h
0x180005426  pop     rbx
0x180005427  retn
0x180005428  mov     eax, 80004003h
0x18000542d  jmp     short loc_180005422
```
