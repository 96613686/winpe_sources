# MbbIpFindRouteInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_IPFORWARD_ROW2 *,ulong *)

- ea: `0x14004323c`
- end: `0x1400432e6`
- name: `?MbbIpFindRouteInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_IPFORWARD_ROW2@@PEAK@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MIB_IPFORWARD_ROW2 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140042e30`
- `0x1400448c8`

## callees

- `0x14004323c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140043282`
- `ntoskrnl!RtlCompareMemory` at `0x1400432b6`
- `ntoskrnl!RtlCompareMemory` at `0x140043282`
- `ntoskrnl!RtlCompareMemory` at `0x1400432b6`

## pseudocode

```c
__int64 __fastcall MbbIpFindRouteInTable(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        struct _MIB_IPFORWARD_ROW2 *a3,
        unsigned int *a4)
{
  __int64 v4; // rbx
  ADDRESS_FAMILY sin_family; // dx
  __int64 v10; // rcx
  bool v11; // zf

  v4 = 0;
  if ( !a2 )
    return 3221225473LL;
  while ( 1 )
  {
    sin_family = a3->NextHop.Ipv4.sin_family;
    v10 = 3 * v4;
    if ( sin_family != 2 )
      break;
    if ( (*((_DWORD *)a1 + 6 * v4) & 1) == 0 )
    {
      v11 = RtlCompareMemory(&a3->NextHop.si_family + 2, (char *)a1 + 8 * v10 + 8, 4u) == 4;
      goto LABEL_8;
    }
LABEL_9:
    v4 = (unsigned int)(v4 + 1);
    if ( (unsigned int)v4 >= a2 )
      return 3221225473LL;
  }
  if ( sin_family != 23 || (*((_DWORD *)a1 + 6 * v4) & 1) == 0 )
    goto LABEL_9;
  v11 = RtlCompareMemory(&a3->NextHop.si_family + 4, (char *)a1 + 8 * v10 + 8, 0x10u) == 16;
LABEL_8:
  if ( !v11 )
    goto LABEL_9;
  *a4 = v4;
  return 0;
}

```

## disassembly

```asm
0x14004323c  push    rbx
0x14004323e  push    rbp
0x14004323f  push    rsi
0x140043240  push    rdi
0x140043241  push    r14
0x140043243  sub     rsp, 20h
0x140043247  xor     ebx, ebx
0x140043249  mov     r14, r9
0x14004324c  mov     rbp, r8
0x14004324f  mov     esi, edx
0x140043251  mov     rdi, rcx
0x140043254  test    edx, edx
0x140043256  jz      short loc_1400432CE
0x140043258  movzx   edx, word ptr [rbp+2Ch]
0x14004325c  lea     rcx, [rbx+rbx*2]
0x140043260  mov     eax, 2
0x140043265  cmp     ax, dx
0x140043268  jnz     short loc_140043294
0x14004326a  mov     eax, [rdi+rcx*8]
0x14004326d  test    al, 1
0x14004326f  jnz     short loc_1400432C8
0x140043271  inc     rcx
0x140043274  mov     r8d, 4; Length
0x14004327a  lea     rdx, [rdi+rcx*8]; Source2
0x14004327e  lea     rcx, [rbp+30h]; Source1
0x140043282  call    cs:__imp_RtlCompareMemory
0x140043289  nop     dword ptr [rax+rax+00h]
0x14004328e  cmp     rax, 4
0x140043292  jmp     short loc_1400432C6
0x140043294  mov     eax, 17h
0x140043299  cmp     ax, dx
0x14004329c  jnz     short loc_1400432C8
0x14004329e  mov     eax, [rdi+rcx*8]
0x1400432a1  test    al, 1
0x1400432a3  jz      short loc_1400432C8
0x1400432a5  inc     rcx
0x1400432a8  mov     r8d, 10h; Length
0x1400432ae  lea     rdx, [rdi+rcx*8]; Source2
0x1400432b2  lea     rcx, [rbp+34h]; Source1
0x1400432b6  call    cs:__imp_RtlCompareMemory
0x1400432bd  nop     dword ptr [rax+rax+00h]
0x1400432c2  cmp     rax, 10h
0x1400432c6  jz      short loc_1400432DF
0x1400432c8  inc     ebx
0x1400432ca  cmp     ebx, esi
0x1400432cc  jb      short loc_140043258
0x1400432ce  mov     eax, 0C0000001h
0x1400432d3  add     rsp, 20h
0x1400432d7  pop     r14
0x1400432d9  pop     rdi
0x1400432da  pop     rsi
0x1400432db  pop     rbp
0x1400432dc  pop     rbx
0x1400432dd  retn
0x1400432df  mov     [r14], ebx
0x1400432e2  xor     eax, eax
0x1400432e4  jmp     short loc_1400432D3
```
