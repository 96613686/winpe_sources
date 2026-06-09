# EaEncodeBrokeredEvent

- ea: `0x180009250`
- end: `0x1800092f7`
- name: `EaEncodeBrokeredEvent`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002e30`
- `0x180003630`
- `0x180009250`
- `0x18000b78c`

## pseudocode

```c
__int64 __fastcall EaEncodeBrokeredEvent(__int64 a1, __int64 *a2, USHORT *a3)
{
  int v6; // ebx
  USHORT v7; // si
  __int64 v8; // rax
  __int64 v9; // rdi
  USHORT v11; // [rsp+60h] [rbp+8h] BYREF

  v11 = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-1073741811;
  v6 = BrpEncodeBrokeredEvent_V1(a1, 0, 0, &v11);
  if ( v6 == -1073741789 )
  {
    v7 = v11;
    v8 = EaLibAllocate(v11);
    v9 = v8;
    if ( !v8 )
      return (unsigned int)-1073741801;
    v6 = BrpEncodeBrokeredEvent_V1(a1, v7, v8, &v11);
  }
  else
  {
    v9 = 0;
    v7 = 0;
  }
  if ( v6 < 0 )
  {
    if ( v9 )
      EaLibFree(v9);
  }
  else
  {
    *a3 = v7;
    v6 = 0;
    *a2 = v9;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009250  push    rbx
0x180009252  push    rbp
0x180009253  push    rsi
0x180009254  push    rdi
0x180009255  push    r14
0x180009257  push    r15
0x180009259  sub     rsp, 28h
0x18000925d  xor     eax, eax
0x18000925f  mov     r15, r8
0x180009262  mov     [rsp+58h+arg_0], ax
0x180009267  mov     r14, rdx
0x18000926a  mov     rbp, rcx
0x18000926d  test    rcx, rcx
0x180009270  jz      short loc_1800092E3
0x180009272  test    rdx, rdx
0x180009275  jz      short loc_1800092E3
0x180009277  xor     edx, edx
0x180009279  lea     r9, [rsp+58h+arg_0]
0x18000927e  xor     r8d, r8d
0x180009281  call    BrpEncodeBrokeredEvent_V1
0x180009286  mov     ebx, eax
0x180009288  cmp     eax, 0C0000023h
0x18000928d  jnz     short loc_1800092C1
0x18000928f  movzx   esi, [rsp+58h+arg_0]
0x180009294  mov     ecx, esi
0x180009296  call    EaLibAllocate
0x18000929b  mov     rdi, rax
0x18000929e  test    rax, rax
0x1800092a1  jnz     short loc_1800092AA
0x1800092a3  mov     ebx, 0C0000017h
0x1800092a8  jmp     short loc_1800092E8
0x1800092aa  lea     r9, [rsp+58h+arg_0]
0x1800092af  mov     r8, rax
0x1800092b2  movzx   edx, si
0x1800092b5  mov     rcx, rbp
0x1800092b8  call    BrpEncodeBrokeredEvent_V1
0x1800092bd  mov     ebx, eax
0x1800092bf  jmp     short loc_1800092C5
0x1800092c1  xor     edi, edi
0x1800092c3  xor     esi, esi
0x1800092c5  test    ebx, ebx
0x1800092c7  js      short loc_1800092D4
0x1800092c9  mov     [r15], si
0x1800092cd  xor     ebx, ebx
0x1800092cf  mov     [r14], rdi
0x1800092d2  jmp     short loc_1800092E8
0x1800092d4  test    rdi, rdi
0x1800092d7  jz      short loc_1800092E8
0x1800092d9  mov     rcx, rdi
0x1800092dc  call    EaLibFree
0x1800092e1  jmp     short loc_1800092E8
0x1800092e3  mov     ebx, 0C000000Dh
0x1800092e8  mov     eax, ebx
0x1800092ea  add     rsp, 28h
0x1800092ee  pop     r15
0x1800092f0  pop     r14
0x1800092f2  pop     rdi
0x1800092f3  pop     rsi
0x1800092f4  pop     rbp
0x1800092f5  pop     rbx
0x1800092f6  retn
```
