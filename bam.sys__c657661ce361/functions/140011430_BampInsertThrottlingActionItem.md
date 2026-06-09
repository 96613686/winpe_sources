# BampInsertThrottlingActionItem

- ea: `0x140011430`
- end: `0x1400114db`
- name: `BampInsertThrottlingActionItem`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b2f0`
- `0x14000ba5c`
- `0x14000c18c`
- `0x14000f460`
- `0x14001022c`
- `0x140010274`
- `0x140011160`

## callees

- `0x140011430`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400114c9`
- `ntoskrnl!KeSetEvent` at `0x1400114c9`

## pseudocode

```c
int __fastcall BampInsertThrottlingActionItem(__int64 **a1)
{
  __int64 *v1; // rax
  unsigned __int64 v3; // rcx
  _QWORD *v4; // r9
  bool v5; // dl
  __int64 **v6; // rcx

  v1 = (__int64 *)qword_140007598;
  if ( (__int64 *)qword_140007598 != &qword_140007598 )
  {
    v3 = (unsigned __int64)a1[2] & 0xFFFFFFFFFFFFFFFEuLL;
    do
    {
      if ( (v1[2] & 0xFFFFFFFFFFFFFFFEuLL) > v3 )
        break;
      v1 = (__int64 *)*v1;
    }
    while ( v1 != &qword_140007598 );
  }
  v4 = a1 + 2;
  v5 = (__int64 *)qword_140007598 == &qword_140007598
    || (*v4 & 0xFFFFFFFFFFFFFFFEuLL) < (*(_QWORD *)(qword_140007598 + 16) & 0xFFFFFFFFFFFFFFFEuLL);
  v6 = (__int64 **)v1[1];
  if ( *v6 != v1 )
    __fastfail(3u);
  *a1 = v1;
  a1[1] = (__int64 *)v6;
  *v6 = (__int64 *)a1;
  v1[1] = (__int64)a1;
  *v4 |= 1uLL;
  if ( v5 )
    LODWORD(v1) = KeSetEvent(&BampThrottlingWorkerState, 0, 0);
  return (int)v1;
}

```

## disassembly

```asm
0x140011430  sub     rsp, 28h
0x140011434  mov     rax, cs:qword_140007598
0x14001143b  lea     r9, qword_140007598
0x140011442  mov     r8, rcx
0x140011445  cmp     rax, r9
0x140011448  jz      short loc_14001145F
0x14001144a  mov     rcx, [rcx+10h]
0x14001144e  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140011452  mov     rdx, [rax+10h]
0x140011456  and     rdx, 0FFFFFFFFFFFFFFFEh
0x14001145a  cmp     rdx, rcx
0x14001145d  jbe     short loc_140011499
0x14001145f  mov     rdx, cs:qword_140007598
0x140011466  cmp     rdx, r9
0x140011469  lea     r9, [r8+10h]
0x14001146d  jz      short loc_1400114A3
0x14001146f  mov     rdx, [rdx+10h]
0x140011473  mov     rcx, [r9]
0x140011476  and     rdx, 0FFFFFFFFFFFFFFFEh
0x14001147a  and     rcx, 0FFFFFFFFFFFFFFFEh
0x14001147e  cmp     rcx, rdx
0x140011481  jnb     short loc_140011495
0x140011483  mov     dl, 1
0x140011485  mov     rcx, [rax+8]
0x140011489  cmp     [rcx], rax
0x14001148c  jz      short loc_1400114A7
0x14001148e  mov     ecx, 3
0x140011493  int     29h; Win8: RtlFailFast(ecx)
0x140011495  xor     dl, dl
0x140011497  jmp     short loc_140011485
0x140011499  mov     rax, [rax]
0x14001149c  cmp     rax, r9
0x14001149f  jz      short loc_14001145F
0x1400114a1  jmp     short loc_140011452
0x1400114a3  mov     dl, 1
0x1400114a5  jmp     short loc_140011485
0x1400114a7  mov     [r8], rax
0x1400114aa  mov     [r8+8], rcx
0x1400114ae  mov     [rcx], r8
0x1400114b1  mov     [rax+8], r8
0x1400114b5  or      qword ptr [r9], 1
0x1400114b9  test    dl, dl
0x1400114bb  jz      short loc_1400114D5
0x1400114bd  xor     r8d, r8d; Wait
0x1400114c0  lea     rcx, BampThrottlingWorkerState; Event
0x1400114c7  xor     edx, edx; Increment
0x1400114c9  call    cs:__imp_KeSetEvent
0x1400114d0  nop     dword ptr [rax+rax+00h]
0x1400114d5  add     rsp, 28h
0x1400114d9  retn
```
