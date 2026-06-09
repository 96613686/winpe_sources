# CfpReleaseSyncRoot

- ea: `0x18000b6c8`
- end: `0x18000b6f6`
- name: `CfpReleaseSyncRoot`
- size: `46`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800031d0`
- `0x180005710`
- `0x180005ba0`
- `0x180005f20`
- `0x180007cf0`
- `0x18000b8e0`
- `0x18000eb80`
- `0x180018404`

## callees

- `0x18000ac4c`
- `0x18000b6c8`

## pseudocode

```c
__int64 __fastcall CfpReleaseSyncRoot(volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  bool v2; // cc
  __int64 result; // rax

  v1 = _InterlockedExchangeAdd64(a1, 0xFFFFFFFFFFFFFFFFuLL);
  v2 = v1 <= 1;
  result = v1 - 1;
  if ( v2 )
  {
    if ( result )
      __fastfail(0xEu);
    return CfpFreeSyncRoot(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000b6c8  sub     rsp, 28h
0x18000b6cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b6d0  lock xadd [rcx], rax
0x18000b6d5  sub     rax, 1
0x18000b6d9  jg      short loc_18000B6F1
0x18000b6db  test    rax, rax
0x18000b6de  jz      short loc_18000B6EC
0x18000b6e0  mov     ecx, 0Eh
0x18000b6e5  int     29h; Win8: RtlFailFast(ecx)
0x18000b6e7  add     rsp, 28h
0x18000b6eb  retn
0x18000b6ec  call    CfpFreeSyncRoot
0x18000b6f1  add     rsp, 28h
0x18000b6f5  retn
```
