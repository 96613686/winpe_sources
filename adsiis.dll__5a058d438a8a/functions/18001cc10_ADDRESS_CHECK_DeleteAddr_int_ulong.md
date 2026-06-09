# ADDRESS_CHECK::DeleteAddr(int,ulong)

- ea: `0x18001cc10`
- end: `0x18001ccda`
- name: `?DeleteAddr@ADDRESS_CHECK@@QEAAHHK@Z`
- size: `202`
- prototype: `__int64 __fastcall(ADDRESS_CHECK *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001cce0`

## callees

- `0x18001cb64`
- `0x18001cc10`
- `0x18001cff4`
- `0x18001d65e`

## pseudocode

```c
__int64 __fastcall ADDRESS_CHECK::DeleteAddr(ADDRESS_CHECK *this, int a2)
{
  unsigned __int8 *v3; // rsi
  unsigned int v4; // eax
  struct _ADDRESS_LIST_ENTRY *v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rcx
  int v8; // r8d
  ADDRESS_CHECK *v9; // rcx
  __int64 result; // rax
  int v11; // r10d
  struct _ADDRESS_LIST_ENTRY *v12; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+60h] [rbp+18h] BYREF
  struct _ADDRESS_HEADER *v14; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  v14 = 0;
  v13 = 0;
  if ( !(unsigned int)ADDRESS_CHECK::LocateAddr(this, a2, 0, &v14, &v12, &v13) )
    return 0;
  v3 = *(unsigned __int8 **)this;
  v4 = 0;
  v5 = v12;
  if ( *(_DWORD *)v12 == 2 )
    v4 = 4;
  v6 = v4;
  v7 = (*((_DWORD *)v12 + 4) & 0x7FFFFFFF) + v13 * v4;
  v8 = *((_DWORD *)this + 3) - v7;
  LODWORD(v7) = v7 & 0x7FFFFFFF;
  memmove_0(&v3[v7], &v3[v7 + v4], v8 - v4);
  *((_DWORD *)this + 3) -= v6;
  --*((_DWORD *)v5 + 1);
  ADDRESS_CHECK::AdjustRefs(v9, v3, (*((_DWORD *)v5 + 4) & 0x7FFFFFFF) + 1, -v6);
  result = 1;
  *((_DWORD *)v14 + 1) += v11;
  return result;
}

```

## disassembly

```asm
0x18001cc10  mov     r11, rsp
0x18001cc13  mov     [r11+10h], rbx
0x18001cc17  mov     [r11+18h], r8d
0x18001cc1b  push    rsi
0x18001cc1c  push    rdi
0x18001cc1d  push    r14
0x18001cc1f  sub     rsp, 30h
0x18001cc23  lea     rax, [r11+18h]
0x18001cc27  xor     ebx, ebx
0x18001cc29  mov     [r11-20h], rax
0x18001cc2d  lea     r9, [r11+20h]; struct _ADDRESS_HEADER **
0x18001cc31  lea     rax, [r11+8]
0x18001cc35  mov     [r11+8], rbx
0x18001cc39  xor     r8d, r8d; unsigned int
0x18001cc3c  mov     [r11-28h], rax
0x18001cc40  mov     r14, rcx
0x18001cc43  mov     [r11+20h], rbx
0x18001cc47  mov     [rsp+48h+arg_10], ebx
0x18001cc4b  call    ?LocateAddr@ADDRESS_CHECK@@QEAAHHKPEAPEAU_ADDRESS_HEADER@@PEAPEAU_ADDRESS_LIST_ENTRY@@PEAK@Z; ADDRESS_CHECK::LocateAddr(int,ulong,_ADDRESS_HEADER * *,_ADDRESS_LIST_ENTRY * *,ulong *)
0x18001cc50  test    eax, eax
0x18001cc52  jz      short loc_18001CCCA
0x18001cc54  mov     rsi, [r14]
0x18001cc57  lea     ecx, [rbx+4]
0x18001cc5a  mov     r8d, [r14+0Ch]
0x18001cc5e  mov     eax, ebx
0x18001cc60  mov     rbx, [rsp+48h+arg_0]
0x18001cc65  cmp     dword ptr [rbx], 2
0x18001cc68  cmovz   eax, ecx
0x18001cc6b  mov     edx, eax
0x18001cc6d  mov     edi, eax
0x18001cc6f  imul    edx, [rsp+48h+arg_10]
0x18001cc74  mov     eax, [rbx+10h]
0x18001cc77  btr     eax, 1Fh
0x18001cc7b  add     edx, eax
0x18001cc7d  mov     ecx, edx
0x18001cc7f  sub     r8d, edx
0x18001cc82  btr     ecx, 1Fh
0x18001cc86  sub     r8d, edi; Size
0x18001cc89  add     rcx, rsi; void *
0x18001cc8c  lea     rdx, [rcx+rdi]; Src
0x18001cc90  call    memmove_0
0x18001cc95  sub     [r14+0Ch], edi
0x18001cc99  or      r10d, 0FFFFFFFFh
0x18001cc9d  add     [rbx+4], r10d
0x18001cca1  neg     edi
0x18001cca3  mov     r8d, [rbx+10h]
0x18001cca7  mov     r9d, edi; unsigned int
0x18001ccaa  btr     r8d, 1Fh
0x18001ccaf  mov     rdx, rsi; unsigned __int8 *
0x18001ccb2  inc     r8d; unsigned int
0x18001ccb5  call    ?AdjustRefs@ADDRESS_CHECK@@QEAAXPEAEKK@Z; ADDRESS_CHECK::AdjustRefs(uchar *,ulong,ulong)
0x18001ccba  mov     r9, [rsp+48h+arg_18]
0x18001ccbf  mov     eax, 1
0x18001ccc4  add     [r9+4], r10d
0x18001ccc8  jmp     short loc_18001CCCC
0x18001ccca  xor     eax, eax
0x18001cccc  mov     rbx, [rsp+48h+arg_8]
0x18001ccd1  add     rsp, 30h
0x18001ccd5  pop     r14
0x18001ccd7  pop     rdi
0x18001ccd8  pop     rsi
0x18001ccd9  retn
```
