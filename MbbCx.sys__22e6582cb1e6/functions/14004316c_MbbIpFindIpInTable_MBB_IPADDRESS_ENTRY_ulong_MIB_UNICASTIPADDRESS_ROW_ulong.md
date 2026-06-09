# MbbIpFindIpInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MIB_UNICASTIPADDRESS_ROW *,ulong *)

- ea: `0x14004316c`
- end: `0x140043234`
- name: `?MbbIpFindIpInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@KPEAU_MIB_UNICASTIPADDRESS_ROW@@PEAK@Z`
- size: `200`
- prototype: `__int64 __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MIB_UNICASTIPADDRESS_ROW *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140042bf4`
- `0x1400445e8`

## callees

- `0x14004316c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400431c1`
- `ntoskrnl!RtlCompareMemory` at `0x140043200`
- `ntoskrnl!RtlCompareMemory` at `0x1400431c1`
- `ntoskrnl!RtlCompareMemory` at `0x140043200`

## pseudocode

```c
__int64 __fastcall MbbIpFindIpInTable(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        struct _MIB_UNICASTIPADDRESS_ROW *a3,
        unsigned int *a4)
{
  __int64 v4; // rbx
  __int64 v9; // rcx
  bool v10; // zf

  v4 = 0;
  if ( !a2 )
    return 3221225473LL;
  while ( 1 )
  {
    v9 = 3 * v4;
    if ( a3->Address.Ipv4.sin_family == 2 )
    {
      if ( (*((_DWORD *)a1 + 6 * v4) & 1) != 0 || a3->OnLinkPrefixLength != *((_DWORD *)a1 + 6 * v4 + 1) )
        goto LABEL_11;
      v10 = RtlCompareMemory(&a3->Address.si_family + 2, (char *)a1 + 8 * v9 + 8, 4u) == 4;
    }
    else
    {
      if ( a3->Address.Ipv4.sin_family != 23
        || (*((_DWORD *)a1 + 6 * v4) & 1) == 0
        || a3->OnLinkPrefixLength != *((_DWORD *)a1 + 6 * v4 + 1) )
      {
        goto LABEL_11;
      }
      v10 = RtlCompareMemory(&a3->Address.si_family + 4, (char *)a1 + 8 * v9 + 8, 0x10u) == 16;
    }
    if ( v10 )
      break;
LABEL_11:
    v4 = (unsigned int)(v4 + 1);
    if ( (unsigned int)v4 >= a2 )
      return 3221225473LL;
  }
  *a4 = v4;
  return 0;
}

```

## disassembly

```asm
0x14004316c  push    rbx
0x14004316e  push    rbp
0x14004316f  push    rsi
0x140043170  push    rdi
0x140043171  push    r14
0x140043173  sub     rsp, 20h
0x140043177  xor     ebx, ebx
0x140043179  mov     r14, r9
0x14004317c  mov     rsi, r8
0x14004317f  mov     ebp, edx
0x140043181  mov     rdi, rcx
0x140043184  test    edx, edx
0x140043186  jz      loc_14004321C
0x14004318c  movzx   r8d, word ptr [rsi]
0x140043190  lea     rcx, [rbx+rbx*2]
0x140043194  mov     eax, 2
0x140043199  cmp     ax, r8w
0x14004319d  jnz     short loc_1400431D3
0x14004319f  mov     eax, [rdi+rcx*8]
0x1400431a2  test    al, 1
0x1400431a4  jnz     short loc_140043212
0x1400431a6  movzx   eax, byte ptr [rsi+3Ch]
0x1400431aa  cmp     eax, [rdi+rcx*8+4]
0x1400431ae  jnz     short loc_140043212
0x1400431b0  inc     rcx
0x1400431b3  mov     r8d, 4; Length
0x1400431b9  lea     rdx, [rdi+rcx*8]; Source2
0x1400431bd  lea     rcx, [rsi+4]; Source1
0x1400431c1  call    cs:__imp_RtlCompareMemory
0x1400431c8  nop     dword ptr [rax+rax+00h]
0x1400431cd  cmp     rax, 4
0x1400431d1  jmp     short loc_140043210
0x1400431d3  mov     eax, 17h
0x1400431d8  cmp     ax, r8w
0x1400431dc  jnz     short loc_140043212
0x1400431de  mov     eax, [rdi+rcx*8]
0x1400431e1  test    al, 1
0x1400431e3  jz      short loc_140043212
0x1400431e5  movzx   eax, byte ptr [rsi+3Ch]
0x1400431e9  cmp     eax, [rdi+rcx*8+4]
0x1400431ed  jnz     short loc_140043212
0x1400431ef  inc     rcx
0x1400431f2  mov     r8d, 10h; Length
0x1400431f8  lea     rdx, [rdi+rcx*8]; Source2
0x1400431fc  lea     rcx, [rsi+8]; Source1
0x140043200  call    cs:__imp_RtlCompareMemory
0x140043207  nop     dword ptr [rax+rax+00h]
0x14004320c  cmp     rax, 10h
0x140043210  jz      short loc_14004322D
0x140043212  inc     ebx
0x140043214  cmp     ebx, ebp
0x140043216  jb      loc_14004318C
0x14004321c  mov     eax, 0C0000001h
0x140043221  add     rsp, 20h
0x140043225  pop     r14
0x140043227  pop     rdi
0x140043228  pop     rsi
0x140043229  pop     rbp
0x14004322a  pop     rbx
0x14004322b  retn
0x14004322d  mov     [r14], ebx
0x140043230  xor     eax, eax
0x140043232  jmp     short loc_140043221
```
