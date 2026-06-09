# MbbIpFindDnsInTable(_MBB_IPADDRESS_ENTRY *,ulong,_MBB_IPADDRESS_ENTRY *,ulong *)

- ea: `0x1400430d0`
- end: `0x140043165`
- name: `?MbbIpFindDnsInTable@@YAHPEAU_MBB_IPADDRESS_ENTRY@@K0PEAK@Z`
- size: `149`
- prototype: `__int64 __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, struct _MBB_IPADDRESS_ENTRY *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400429a0`

## callees

- `0x1400430d0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14004310e`
- `ntoskrnl!RtlCompareMemory` at `0x140043135`
- `ntoskrnl!RtlCompareMemory` at `0x14004310e`
- `ntoskrnl!RtlCompareMemory` at `0x140043135`

## pseudocode

```c
__int64 __fastcall MbbIpFindDnsInTable(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        struct _MBB_IPADDRESS_ENTRY *a3,
        unsigned int *a4)
{
  __int64 v4; // rbx
  __int64 v9; // rcx
  int v10; // eax
  bool v11; // zf

  v4 = 0;
  if ( !a2 )
    return 3221225473LL;
  while ( 1 )
  {
    v9 = 3 * v4;
    v10 = *((_DWORD *)a1 + 6 * v4);
    if ( (*(_DWORD *)a3 & 1) != 0 )
      break;
    if ( (v10 & 1) == 0 )
    {
      v11 = RtlCompareMemory((char *)a1 + 8 * v9 + 8, (char *)a3 + 8, 4u) == 4;
      goto LABEL_7;
    }
LABEL_8:
    v4 = (unsigned int)(v4 + 1);
    if ( (unsigned int)v4 >= a2 )
      return 3221225473LL;
  }
  if ( (v10 & 1) == 0 )
    goto LABEL_8;
  v11 = RtlCompareMemory((char *)a1 + 8 * v9 + 8, (char *)a3 + 8, 0x10u) == 16;
LABEL_7:
  if ( !v11 )
    goto LABEL_8;
  *a4 = v4;
  return 0;
}

```

## disassembly

```asm
0x1400430d0  push    rbx
0x1400430d2  push    rbp
0x1400430d3  push    rsi
0x1400430d4  push    rdi
0x1400430d5  push    r14
0x1400430d7  sub     rsp, 20h
0x1400430db  xor     ebx, ebx
0x1400430dd  mov     r14, r9
0x1400430e0  mov     rsi, r8
0x1400430e3  mov     ebp, edx
0x1400430e5  mov     rdi, rcx
0x1400430e8  test    edx, edx
0x1400430ea  jz      short loc_14004314D
0x1400430ec  mov     eax, [rsi]
0x1400430ee  lea     rcx, [rbx+rbx*2]
0x1400430f2  test    al, 1
0x1400430f4  mov     eax, [rdi+rcx*8]
0x1400430f7  jnz     short loc_140043120
0x1400430f9  test    al, 1
0x1400430fb  jnz     short loc_140043147
0x1400430fd  inc     rcx
0x140043100  lea     rdx, [rsi+8]; Source2
0x140043104  mov     r8d, 4; Length
0x14004310a  lea     rcx, [rdi+rcx*8]; Source1
0x14004310e  call    cs:__imp_RtlCompareMemory
0x140043115  nop     dword ptr [rax+rax+00h]
0x14004311a  cmp     rax, 4
0x14004311e  jmp     short loc_140043145
0x140043120  test    al, 1
0x140043122  jz      short loc_140043147
0x140043124  inc     rcx
0x140043127  lea     rdx, [rsi+8]; Source2
0x14004312b  mov     r8d, 10h; Length
0x140043131  lea     rcx, [rdi+rcx*8]; Source1
0x140043135  call    cs:__imp_RtlCompareMemory
0x14004313c  nop     dword ptr [rax+rax+00h]
0x140043141  cmp     rax, 10h
0x140043145  jz      short loc_14004315E
0x140043147  inc     ebx
0x140043149  cmp     ebx, ebp
0x14004314b  jb      short loc_1400430EC
0x14004314d  mov     eax, 0C0000001h
0x140043152  add     rsp, 20h
0x140043156  pop     r14
0x140043158  pop     rdi
0x140043159  pop     rsi
0x14004315a  pop     rbp
0x14004315b  pop     rbx
0x14004315c  retn
0x14004315e  mov     [r14], ebx
0x140043161  xor     eax, eax
0x140043163  jmp     short loc_140043152
```
