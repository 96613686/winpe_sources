# VersionedDataGuard::BeginUpdate(bool,unsigned __int64 &)

- ea: `0x18002388c`
- end: `0x180023916`
- name: `?BeginUpdate@VersionedDataGuard@@QEAA?AW4VersionedDataStatus@@_NAEA_K@Z`
- size: `138`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000643c`
- `0x180008424`
- `0x18000b0c0`
- `0x18000b260`
- `0x18000b3fc`
- `0x18000b5a0`

## callees

- `0x18000d68c`
- `0x18002388c`

## pseudocode

```c
__int64 __fastcall VersionedDataGuard::BeginUpdate(
        volatile signed __int64 *a1,
        unsigned __int8 a2,
        unsigned __int64 *a3)
{
  unsigned __int64 v3; // r10
  unsigned __int64 v4; // r9
  bool v5; // zf
  signed __int64 v6; // rax

  v3 = *a1;
  while ( (v3 & 2) == 0 )
  {
    v4 = (v3 >> 3) + 1;
    if ( v4 > 0x1FFFFFFFFFFFFFFFLL )
    {
      GameInputFailFast(2147549183LL, 39);
      JUMPOUT(0x180023915LL);
    }
    v6 = _InterlockedCompareExchange64(a1, v3 & 1 | (4 * (a2 | (2 * v4))) | 2, v3);
    v5 = v3 == v6;
    v3 = v6;
    if ( v5 )
    {
      *a3 = v4;
      return 0;
    }
  }
  *a3 = 0;
  return 1;
}

```

## disassembly

```asm
0x18002388c  mov     [rsp+arg_0], rbx
0x180023891  push    rdi
0x180023892  sub     rsp, 20h
0x180023896  mov     r10, [rcx]
0x180023899  mov     r11, r8
0x18002389c  nop
0x18002389d  movzx   edi, dl
0x1800238a0  test    r10b, 2
0x1800238a4  jnz     short loc_1800238EE
0x1800238a6  mov     r9, r10
0x1800238a9  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800238b3  shr     r9, 3
0x1800238b7  inc     r9
0x1800238ba  cmp     r9, rax
0x1800238bd  ja      short loc_180023906
0x1800238bf  mov     r8, r10
0x1800238c2  lea     rdx, [r9+r9]
0x1800238c6  or      rdx, rdi
0x1800238c9  and     r8d, 1
0x1800238cd  shl     rdx, 2
0x1800238d1  nop
0x1800238d2  or      rdx, 2
0x1800238d6  mov     rax, r10
0x1800238d9  or      rdx, r8
0x1800238dc  lock cmpxchg [rcx], rdx
0x1800238e1  mov     r10, rax
0x1800238e4  nop
0x1800238e5  jnz     short loc_1800238A0
0x1800238e7  mov     [r11], r9
0x1800238ea  xor     eax, eax
0x1800238ec  jmp     short loc_1800238FA
0x1800238ee  mov     qword ptr [r11], 0
0x1800238f5  mov     eax, 1
0x1800238fa  mov     rbx, [rsp+28h+arg_0]
0x1800238ff  add     rsp, 20h
0x180023903  pop     rdi
0x180023904  retn
0x180023906  mov     edx, 27h ; '''
0x18002390b  mov     ecx, 8000FFFFh
0x180023910  call    GameInputFailFast
```
