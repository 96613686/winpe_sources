# ADDRESS_CHECK::DeleteName(int,ulong)

- ea: `0x18001cd48`
- end: `0x18001ce7d`
- name: `?DeleteName@ADDRESS_CHECK@@QEAAHHK@Z`
- size: `309`
- prototype: `__int64 __fastcall(ADDRESS_CHECK *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001cd14`

## callees

- `0x18001cb64`
- `0x18001cd48`
- `0x18001d064`
- `0x18001d65e`

## pseudocode

```c
__int64 __fastcall ADDRESS_CHECK::DeleteName(ADDRESS_CHECK *this, int a2)
{
  char v3; // r11
  __int64 v4; // r15
  struct _NAME_LIST_ENTRY *v5; // rbp
  __int64 v6; // rsi
  __int64 v7; // r13
  __int64 v8; // rax
  unsigned int v9; // r14d
  __int64 v10; // rbx
  _BYTE *v11; // rcx
  int v12; // ebx
  ADDRESS_CHECK *v13; // rcx
  ADDRESS_CHECK *v14; // rcx
  struct _NAME_HEADER *v15; // rax
  int v16; // r9d
  struct _NAME_LIST_ENTRY *v18; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+18h] BYREF
  struct _NAME_HEADER *v20; // [rsp+88h] [rbp+20h] BYREF

  v18 = 0;
  v20 = 0;
  v19 = 0;
  if ( !(unsigned int)ADDRESS_CHECK::LocateName(this, a2, 0, &v20, &v18, &v19) )
    return 0;
  v4 = v19;
  v5 = v18;
  v6 = *(_QWORD *)this;
  v7 = 4LL * v19;
  v8 = *(unsigned int *)((char *)v18 + v7 + 8);
  LODWORD(v8) = v8 & 0x7FFFFFFF;
  v9 = v8;
  v10 = -1;
  v11 = (_BYTE *)(v8 + *(_QWORD *)this);
  do
    ++v10;
  while ( v11[v10] != v3 );
  v12 = v10 + 1;
  memmove_0(v11, &v11[v12], (unsigned int)(*((_DWORD *)this + 3) - v8 - v12));
  ADDRESS_CHECK::AdjustRefs(v13, (unsigned __int8 *)v6, v9, -v12);
  *((_DWORD *)this + 3) -= v12;
  memmove_0(
    (char *)v5 + v7 + 8,
    (char *)v5 + 4 * v4 + 12,
    (unsigned int)(*((_DWORD *)this + 3) - 8 + v6 - 4 * v4 - (_DWORD)v5) - 4LL);
  *(_DWORD *)(v6 + 20) -= 4;
  ADDRESS_CHECK::AdjustRefs(v14, (unsigned __int8 *)v6, (_DWORD)v5 - v6, 0xFFFFFFFC);
  v15 = v20;
  *((_DWORD *)this + 3) += v16;
  --*((_DWORD *)v5 + 1);
  --*((_DWORD *)v15 + 1);
  return 1;
}

```

## disassembly

```asm
0x18001cd48  mov     rax, rsp
0x18001cd4b  mov     [rax+10h], rbx
0x18001cd4f  mov     [rax+18h], r8d
0x18001cd53  push    rbp
0x18001cd54  push    rsi
0x18001cd55  push    rdi
0x18001cd56  push    r12
0x18001cd58  push    r13
0x18001cd5a  push    r14
0x18001cd5c  push    r15
0x18001cd5e  sub     rsp, 30h
0x18001cd62  xor     r11d, r11d
0x18001cd65  lea     r9, [rsp+68h+arg_18]; struct _NAME_HEADER **
0x18001cd6d  mov     [rax+8], r11
0x18001cd71  xor     r8d, r8d; unsigned int
0x18001cd74  mov     [rax+20h], r11
0x18001cd78  mov     rdi, rcx
0x18001cd7b  mov     [rax+18h], r11d
0x18001cd7f  lea     rax, [rax+18h]
0x18001cd83  mov     [rsp+68h+var_40], rax; unsigned int *
0x18001cd88  lea     rax, [rsp+68h+arg_0]
0x18001cd8d  mov     [rsp+68h+var_48], rax; struct _NAME_LIST_ENTRY **
0x18001cd92  call    ?LocateName@ADDRESS_CHECK@@QEAAHHKPEAPEAU_NAME_HEADER@@PEAPEAU_NAME_LIST_ENTRY@@PEAK@Z; ADDRESS_CHECK::LocateName(int,ulong,_NAME_HEADER * *,_NAME_LIST_ENTRY * *,ulong *)
0x18001cd97  test    eax, eax
0x18001cd99  jz      loc_18001CE66
0x18001cd9f  mov     r15d, [rsp+68h+arg_10]
0x18001cda7  mov     rbp, [rsp+68h+arg_0]
0x18001cdac  mov     rsi, [rdi]
0x18001cdaf  lea     r13, ds:0[r15*4]
0x18001cdb7  mov     eax, [r13+rbp+8]
0x18001cdbc  btr     eax, 1Fh
0x18001cdc0  mov     r14d, eax
0x18001cdc3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001cdc7  lea     rcx, [rax+rsi]; void *
0x18001cdcb  inc     rbx
0x18001cdce  cmp     [rcx+rbx], r11b
0x18001cdd2  jnz     short loc_18001CDCB
0x18001cdd4  mov     r8d, [rdi+0Ch]
0x18001cdd8  inc     ebx
0x18001cdda  sub     r8d, r14d
0x18001cddd  mov     edx, ebx
0x18001cddf  sub     r8d, ebx; Size
0x18001cde2  add     rdx, rcx; Src
0x18001cde5  call    memmove_0
0x18001cdea  mov     r9d, ebx
0x18001cded  mov     r8d, r14d; unsigned int
0x18001cdf0  neg     r9d; unsigned int
0x18001cdf3  mov     rdx, rsi; unsigned __int8 *
0x18001cdf6  call    ?AdjustRefs@ADDRESS_CHECK@@QEAAXPEAEKK@Z; ADDRESS_CHECK::AdjustRefs(uchar *,ulong,ulong)
0x18001cdfb  sub     [rdi+0Ch], ebx
0x18001cdfe  lea     eax, ds:0[r15*4]
0x18001ce06  mov     r9d, [rdi+0Ch]
0x18001ce0a  lea     rdx, [rbp+0Ch]
0x18001ce0e  mov     r8d, esi
0x18001ce11  lea     rcx, [rbp+8]
0x18001ce15  sub     r8d, eax
0x18001ce18  lea     rdx, [rdx+r15*4]; Src
0x18001ce1c  sub     r8d, ebp
0x18001ce1f  add     r9d, 0FFFFFFF8h
0x18001ce23  add     r8d, r9d
0x18001ce26  add     rcx, r13; void *
0x18001ce29  sub     r8, 4; Size
0x18001ce2d  call    memmove_0
0x18001ce32  mov     r8d, ebp
0x18001ce35  mov     r9d, 0FFFFFFFCh; unsigned int
0x18001ce3b  add     [rsi+14h], r9d
0x18001ce3f  sub     r8d, esi; unsigned int
0x18001ce42  mov     rdx, rsi; unsigned __int8 *
0x18001ce45  call    ?AdjustRefs@ADDRESS_CHECK@@QEAAXPEAEKK@Z; ADDRESS_CHECK::AdjustRefs(uchar *,ulong,ulong)
0x18001ce4a  mov     rax, [rsp+68h+arg_18]
0x18001ce52  or      ecx, 0FFFFFFFFh
0x18001ce55  add     [rdi+0Ch], r9d
0x18001ce59  add     [rbp+4], ecx
0x18001ce5c  add     [rax+4], ecx
0x18001ce5f  mov     eax, 1
0x18001ce64  jmp     short loc_18001CE68
0x18001ce66  xor     eax, eax
0x18001ce68  mov     rbx, [rsp+68h+arg_8]
0x18001ce6d  add     rsp, 30h
0x18001ce71  pop     r15
0x18001ce73  pop     r14
0x18001ce75  pop     r13
0x18001ce77  pop     r12
0x18001ce79  pop     rdi
0x18001ce7a  pop     rsi
0x18001ce7b  pop     rbp
0x18001ce7c  retn
```
