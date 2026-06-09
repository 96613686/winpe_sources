# VersionedDataGuard::BeginUpdateToVersion(bool,unsigned __int64)

- ea: `0x18002391c`
- end: `0x18002399c`
- name: `?BeginUpdateToVersion@VersionedDataGuard@@QEAA?AW4VersionedDataStatus@@_N_K@Z`
- size: `128`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000643c`
- `0x18000b0c0`
- `0x18000b260`
- `0x18000b3fc`
- `0x18000b5a0`
- `0x18002433c`

## callees

- `0x18000d68c`
- `0x18002391c`

## pseudocode

```c
__int64 __fastcall VersionedDataGuard::BeginUpdateToVersion(
        volatile signed __int64 *a1,
        unsigned __int8 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // r9
  bool v4; // zf
  signed __int64 v5; // rax

  if ( a3 > 0x1FFFFFFFFFFFFFFFLL )
  {
    GameInputFailFast(2147549183LL, 70);
    JUMPOUT(0x18002399BLL);
  }
  v3 = *a1;
  while ( (v3 & 2) == 0 )
  {
    if ( a3 <= v3 >> 3 )
      return 2;
    v5 = _InterlockedCompareExchange64(a1, v3 & 1 | (4 * (a2 | (2 * a3))) | 2, v3);
    v4 = v3 == v5;
    v3 = v5;
    if ( v4 )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18002391c  push    rbx
0x18002391e  sub     rsp, 20h
0x180023922  mov     rax, 1FFFFFFFFFFFFFFFh
0x18002392c  movzx   ebx, dl
0x18002392f  mov     r10, r8
0x180023932  cmp     r8, rax
0x180023935  ja      short loc_18002398C
0x180023937  mov     r9, [rcx]
0x18002393a  nop
0x18002393b  test    r9b, 2
0x18002393f  jnz     short loc_180023980
0x180023941  mov     rax, r9
0x180023944  shr     rax, 3
0x180023948  cmp     r10, rax
0x18002394b  jbe     short loc_180023979
0x18002394d  mov     r8, r9
0x180023950  lea     rdx, [r10+r10]
0x180023954  or      rdx, rbx
0x180023957  and     r8d, 1
0x18002395b  shl     rdx, 2
0x18002395f  nop
0x180023960  or      rdx, 2
0x180023964  mov     rax, r9
0x180023967  or      rdx, r8
0x18002396a  lock cmpxchg [rcx], rdx
0x18002396f  mov     r9, rax
0x180023972  nop
0x180023973  jnz     short loc_18002393B
0x180023975  xor     eax, eax
0x180023977  jmp     short loc_180023985
0x180023979  mov     eax, 2
0x18002397e  jmp     short loc_180023985
0x180023980  mov     eax, 1
0x180023985  add     rsp, 20h
0x180023989  pop     rbx
0x18002398a  retn
0x18002398c  mov     edx, 46h ; 'F'
0x180023991  mov     ecx, 8000FFFFh
0x180023996  call    GameInputFailFast
```
