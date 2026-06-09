# DloadProtectSection

- ea: `0x18000b780`
- end: `0x18000b85b`
- name: `DloadProtectSection`
- size: `219`
- prototype: `__int64 __fastcall(DWORD flNewProtect, PDWORD lpflOldProtect)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b864`
- `0x18000ba60`

## callees

- `0x18000b6c0`
- `0x18000b780`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000b84a`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18000b84a`

## pseudocode

```c
void __fastcall DloadProtectSection(DWORD flNewProtect, PDWORD lpflOldProtect)
{
  __int64 v4; // r9
  unsigned int v5; // r10d
  int *v6; // rcx
  unsigned int v7; // r9d
  __int64 v8; // rdx
  unsigned __int64 v9; // r8
  char *v10; // rdi
  bool v11; // sf
  SIZE_T v12; // rbx

  if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 68] <= 0xDu )
    goto LABEL_7;
  v4 = *(unsigned int *)&byte_180000040[(int)off_18000003C + 176];
  if ( !(_DWORD)v4 )
    goto LABEL_7;
  v5 = *(_DWORD *)((char *)&word_18000000C + v4);
  v6 = (int *)((char *)&_ImageBase
             + (int)off_18000003C
             + *(unsigned __int16 *)((char *)&word_180000014 + (int)off_18000003C)
             + 24);
  v7 = 0;
  if ( !*(__int16 *)((char *)&word_180000006 + (int)off_18000003C) )
    goto LABEL_7;
  while ( 1 )
  {
    v8 = (unsigned int)v6[3];
    if ( v5 >= (unsigned int)v8 )
    {
      v9 = (unsigned int)v6[2];
      if ( v5 < (int)v9 + (int)v8 )
        break;
    }
    ++v7;
    v6 += 10;
    if ( v7 >= *(unsigned __int16 *)((char *)&word_180000006 + (int)off_18000003C) )
      goto LABEL_7;
  }
  v10 = (char *)&_ImageBase + v8;
  if ( (__int16 *)((char *)&_ImageBase + v8) )
  {
    if ( DloadSectionCommitPermanent )
    {
      v12 = (unsigned int)v6[2];
    }
    else
    {
      v11 = v6[9] < 0;
      DloadSectionCommitPermanent = 1;
      if ( !v11 )
        __fastfail(0x19u);
      v12 = v9;
      DloadMakePermanentImageCommit((unsigned __int64)v10, v9);
    }
    if ( !VirtualProtect(v10, v12, flNewProtect, lpflOldProtect) )
      __fastfail(0x19u);
  }
  else
  {
LABEL_7:
    *lpflOldProtect = 4;
  }
}

```

## disassembly

```asm
0x18000b780  push    rbx
0x18000b782  push    rbp
0x18000b783  push    rsi
0x18000b784  push    rdi
0x18000b785  sub     rsp, 28h
0x18000b789  movsxd  r8, cs:off_18000003C
0x18000b790  lea     rbx, __ImageBase
0x18000b797  add     r8, rbx
0x18000b79a  mov     rsi, rdx
0x18000b79d  mov     ebp, ecx
0x18000b79f  cmp     dword ptr [r8+84h], 0Dh
0x18000b7a7  jbe     short loc_18000B7F4
0x18000b7a9  mov     r9d, [r8+0F0h]
0x18000b7b0  test    r9d, r9d
0x18000b7b3  jz      short loc_18000B7F4
0x18000b7b5  movzx   ecx, word ptr [r8+14h]
0x18000b7ba  mov     r10d, [r9+rbx+0Ch]
0x18000b7bf  add     rcx, 18h
0x18000b7c3  movzx   r11d, word ptr [r8+6]
0x18000b7c8  add     rcx, r8
0x18000b7cb  xor     r9d, r9d
0x18000b7ce  test    r11d, r11d
0x18000b7d1  jz      short loc_18000B7F4
0x18000b7d3  mov     edx, [rcx+0Ch]
0x18000b7d6  cmp     r10d, edx
0x18000b7d9  jb      short loc_18000B7E8
0x18000b7db  mov     r8d, [rcx+8]
0x18000b7df  lea     eax, [r8+rdx]
0x18000b7e3  cmp     r10d, eax
0x18000b7e6  jb      short loc_18000B803
0x18000b7e8  inc     r9d
0x18000b7eb  add     rcx, 28h ; '('
0x18000b7ef  cmp     r9d, r11d
0x18000b7f2  jb      short loc_18000B7D3
0x18000b7f4  mov     dword ptr [rsi], 4
0x18000b7fa  add     rsp, 28h
0x18000b7fe  pop     rdi
0x18000b7ff  pop     rsi
0x18000b800  pop     rbp
0x18000b801  pop     rbx
0x18000b802  retn
0x18000b803  mov     rdi, rdx
0x18000b806  add     rdi, rbx
0x18000b809  jz      short loc_18000B7F4
0x18000b80b  cmp     cs:DloadSectionCommitPermanent, 0
0x18000b812  jnz     short loc_18000B83B
0x18000b814  cmp     dword ptr [rcx+24h], 0
0x18000b818  mov     cs:DloadSectionCommitPermanent, 1
0x18000b822  jl      short loc_18000B82B
0x18000b824  mov     ecx, 19h
0x18000b829  int     29h; Win8: RtlFailFast(ecx)
0x18000b82b  mov     rdx, r8
0x18000b82e  mov     rcx, rdi
0x18000b831  mov     rbx, r8
0x18000b834  call    DloadMakePermanentImageCommit
0x18000b839  jmp     short loc_18000B83E
0x18000b83b  mov     rbx, r8
0x18000b83e  mov     r9, rsi; lpflOldProtect
0x18000b841  mov     r8d, ebp; flNewProtect
0x18000b844  mov     rdx, rbx; dwSize
0x18000b847  mov     rcx, rdi; lpAddress
0x18000b84a  call    cs:__imp_VirtualProtect
0x18000b850  test    eax, eax
0x18000b852  jnz     short loc_18000B7FA
0x18000b854  lea     ecx, [rax+19h]
0x18000b857  int     29h; Win8: RtlFailFast(ecx)
0x18000b859  jmp     short loc_18000B7FA
```
