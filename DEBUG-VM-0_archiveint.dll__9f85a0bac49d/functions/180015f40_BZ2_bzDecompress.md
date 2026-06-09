# BZ2_bzDecompress

- ea: `0x180015f40`
- end: `0x180016123`
- name: `BZ2_bzDecompress`
- size: `483`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008860`
- `0x1800c1cb0`
- `0x1800e3c44`
- `0x1800eb144`

## callees

- `0x1800158b8`
- `0x180015f40`
- `0x180016920`
- `0x180016e70`
- `0x18001c4e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180015fe3`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180016009`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x1800160d4`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180015fe3`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x180016009`
- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x1800160d4`

## string_xrefs

- `0x1800160dd`: `\n    combined CRCs: stored = 0x%08x, computed = 0x%08x`

## pseudocode

```c
__int64 __fastcall BZ2_bzDecompress(__int64 a1)
{
  __int64 v1; // rbx
  int v2; // eax
  char v3; // al
  bool v4; // cc
  int v5; // esi
  int v6; // edi
  FILE *v7; // rax
  FILE *v8; // rax
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // ecx
  __int64 result; // rax
  int v13; // edi
  int v14; // esi
  FILE *v15; // rax

  if ( !a1 )
    return 4294967294LL;
  v1 = *(_QWORD *)(a1 + 48);
  if ( !v1 || *(_QWORD *)v1 != a1 )
    return 4294967294LL;
  v2 = *(_DWORD *)(v1 + 8);
  if ( v2 == 1 )
    return 0xFFFFFFFFLL;
  while ( v2 != 2 )
  {
    if ( v2 >= 10 )
      goto LABEL_19;
  }
  while ( 1 )
  {
    if ( *(_BYTE *)(v1 + 44) )
      v3 = unRLE_obuf_to_output_SMALL(v1);
    else
      v3 = unRLE_obuf_to_output_FAST(v1);
    if ( v3 )
      return 4294967292LL;
    if ( *(_DWORD *)(v1 + 1092) != *(_DWORD *)(v1 + 64080) + 1 || *(_DWORD *)(v1 + 16) )
      return 0;
    v4 = *(_DWORD *)(v1 + 52) < 3;
    v5 = ~*(_DWORD *)(v1 + 3184);
    *(_DWORD *)(v1 + 3184) = v5;
    if ( !v4 )
    {
      v6 = *(_DWORD *)(v1 + 3176);
      v7 = __acrt_iob_func(2u);
      fprintf(v7, " {0x%08x, 0x%08x}", v6, v5);
    }
    if ( *(int *)(v1 + 52) >= 2 )
    {
      v8 = __acrt_iob_func(2u);
      fprintf(v8, "]");
    }
    v9 = *(_DWORD *)(v1 + 3184);
    if ( v9 != *(_DWORD *)(v1 + 3176) )
      return 4294967292LL;
    v10 = v9 ^ __ROR4__(*(_DWORD *)(v1 + 3188), 31);
    *(_DWORD *)(v1 + 8) = 14;
    *(_DWORD *)(v1 + 3188) = v10;
LABEL_19:
    v11 = BZ2_decompress(v1);
    if ( v11 == 4 )
      break;
    if ( *(_DWORD *)(v1 + 8) != 2 )
      return v11;
  }
  if ( *(int *)(v1 + 52) >= 3 )
  {
    v13 = *(_DWORD *)(v1 + 3188);
    v14 = *(_DWORD *)(v1 + 3180);
    v15 = __acrt_iob_func(2u);
    fprintf(v15, "\n    combined CRCs: stored = 0x%08x, computed = 0x%08x", v14, v13);
  }
  result = 4;
  if ( *(_DWORD *)(v1 + 3188) != *(_DWORD *)(v1 + 3180) )
    return 4294967292LL;
  return result;
}

```

## disassembly

```asm
0x180015f40  push    rbx
0x180015f42  sub     rsp, 20h
0x180015f46  test    rcx, rcx
0x180015f49  jz      loc_180016118
0x180015f4f  mov     rbx, [rcx+30h]
0x180015f53  test    rbx, rbx
0x180015f56  jz      loc_180016118
0x180015f5c  cmp     [rbx], rcx
0x180015f5f  jnz     loc_180016118
0x180015f65  mov     eax, [rbx+8]
0x180015f68  mov     [rsp+28h+arg_0], rsi
0x180015f6d  mov     [rsp+28h+arg_8], rdi
0x180015f72  cmp     eax, 1
0x180015f75  jz      loc_180016081
0x180015f7b  nop     dword ptr [rax+rax+00h]
0x180015f80  cmp     eax, 2
0x180015f83  jnz     loc_180016046
0x180015f89  cmp     byte ptr [rbx+2Ch], 0
0x180015f8d  mov     rcx, rbx
0x180015f90  jz      short loc_180015F99
0x180015f92  call    unRLE_obuf_to_output_SMALL
0x180015f97  jmp     short loc_180015F9E
0x180015f99  call    unRLE_obuf_to_output_FAST
0x180015f9e  test    al, al
0x180015fa0  jnz     loc_1800160A8
0x180015fa6  mov     eax, [rbx+0FA50h]
0x180015fac  inc     eax
0x180015fae  cmp     [rbx+444h], eax
0x180015fb4  jnz     loc_180016096
0x180015fba  cmp     dword ptr [rbx+10h], 0
0x180015fbe  jnz     loc_180016096
0x180015fc4  cmp     dword ptr [rbx+34h], 3
0x180015fc8  mov     esi, [rbx+0C70h]
0x180015fce  not     esi
0x180015fd0  mov     [rbx+0C70h], esi
0x180015fd6  jl      short loc_180015FFE
0x180015fd8  mov     edi, [rbx+0C68h]
0x180015fde  mov     ecx, 2; Ix
0x180015fe3  call    cs:__imp___acrt_iob_func
0x180015fe9  mov     r9d, esi
0x180015fec  lea     rdx, Format; " {0x%08x, 0x%08x}"
0x180015ff3  mov     rcx, rax; Stream
0x180015ff6  mov     r8d, edi
0x180015ff9  call    fprintf
0x180015ffe  cmp     dword ptr [rbx+34h], 2
0x180016002  jl      short loc_18001601E
0x180016004  mov     ecx, 2; Ix
0x180016009  call    cs:__imp___acrt_iob_func
0x18001600f  mov     rcx, rax; Stream
0x180016012  lea     rdx, asc_180122E4C; "]"
0x180016019  call    fprintf
0x18001601e  mov     ecx, [rbx+0C70h]
0x180016024  cmp     ecx, [rbx+0C68h]
0x18001602a  jnz     short loc_1800160A8
0x18001602c  mov     eax, [rbx+0C74h]
0x180016032  ror     eax, 1Fh
0x180016035  xor     eax, ecx
0x180016037  mov     dword ptr [rbx+8], 0Eh
0x18001603e  mov     [rbx+0C74h], eax
0x180016044  jmp     short loc_18001604B
0x180016046  cmp     eax, 0Ah
0x180016049  jl      short loc_180016078
0x18001604b  mov     rcx, rbx
0x18001604e  call    BZ2_decompress
0x180016053  mov     ecx, eax
0x180016055  cmp     eax, 4
0x180016058  jz      short loc_1800160BD
0x18001605a  mov     eax, [rbx+8]
0x18001605d  cmp     eax, 2
0x180016060  jz      loc_180015F89
0x180016066  mov     rsi, [rsp+28h+arg_0]
0x18001606b  mov     eax, ecx
0x18001606d  mov     rdi, [rsp+28h+arg_8]
0x180016072  add     rsp, 20h
0x180016076  pop     rbx
0x180016077  retn
0x180016078  cmp     eax, 1
0x18001607b  jnz     loc_180015F80
0x180016081  mov     rsi, [rsp+28h+arg_0]
0x180016086  mov     eax, 0FFFFFFFFh
0x18001608b  mov     rdi, [rsp+28h+arg_8]
0x180016090  add     rsp, 20h
0x180016094  pop     rbx
0x180016095  retn
0x180016096  mov     rsi, [rsp+28h+arg_0]
0x18001609b  xor     eax, eax
0x18001609d  mov     rdi, [rsp+28h+arg_8]
0x1800160a2  add     rsp, 20h
0x1800160a6  pop     rbx
0x1800160a7  retn
0x1800160a8  mov     rsi, [rsp+28h+arg_0]
0x1800160ad  mov     eax, 0FFFFFFFCh
0x1800160b2  mov     rdi, [rsp+28h+arg_8]
0x1800160b7  add     rsp, 20h
0x1800160bb  pop     rbx
0x1800160bc  retn
0x1800160bd  cmp     dword ptr [rbx+34h], 3
0x1800160c1  jl      short loc_1800160EF
0x1800160c3  mov     edi, [rbx+0C74h]
0x1800160c9  mov     ecx, 2; Ix
0x1800160ce  mov     esi, [rbx+0C6Ch]
0x1800160d4  call    cs:__imp___acrt_iob_func
0x1800160da  mov     r9d, edi
0x1800160dd  lea     rdx, aCombinedCrcsSt; "\n    combined CRCs: stored = 0x%08x, c"...
0x1800160e4  mov     rcx, rax; Stream
0x1800160e7  mov     r8d, esi
0x1800160ea  call    fprintf
0x1800160ef  mov     ecx, [rbx+0C6Ch]
0x1800160f5  mov     eax, 4
0x1800160fa  cmp     [rbx+0C74h], ecx
0x180016100  mov     edx, 0FFFFFFFCh
0x180016105  mov     rsi, [rsp+28h+arg_0]
0x18001610a  mov     rdi, [rsp+28h+arg_8]
0x18001610f  cmovnz  eax, edx
0x180016112  add     rsp, 20h
0x180016116  pop     rbx
0x180016117  retn
0x180016118  mov     eax, 0FFFFFFFEh
0x18001611d  add     rsp, 20h
0x180016121  pop     rbx
0x180016122  retn
```
