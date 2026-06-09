# uudecode_filter_read

- ea: `0x1800c4100`
- end: `0x1800c4800`
- name: `uudecode_filter_read`
- size: `1792`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180005914`
- `0x180005c7c`
- `0x180006c00`
- `0x1800aba54`
- `0x1800aba6c`
- `0x1800c3bc0`
- `0x1800c3c60`
- `0x1800c4100`
- `0x18011996e`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c4690`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c4690`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c469b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c469b`

## string_xrefs

- `0x1800c43d2`: `Insufficient compressed data`

## pseudocode

```c
__int64 __fastcall uudecode_filter_read(__int64 *a1, _QWORD *a2)
{
  __int64 v2; // rbx
  _QWORD *v4; // r13
  _QWORD *v5; // r14
  _WORD *filter_ahead; // rsi
  __int64 v7; // rcx
  __int64 v8; // r15
  signed __int64 v9; // r12
  __int64 v10; // rax
  __int64 i; // rbp
  __int64 line; // rax
  size_t v13; // r13
  __int64 v14; // r8
  int v15; // edx
  int v16; // edx
  int v17; // edx
  unsigned __int8 *v18; // rdx
  __int64 v19; // rcx
  bool v20; // zf
  _BYTE *v21; // r10
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // rcx
  int v25; // r8d
  _BYTE *v26; // r10
  __int64 v27; // r9
  int v28; // r9d
  _BYTE *v29; // r10
  __int64 v30; // rcx
  __int64 v31; // rax
  bool v32; // zf
  int v33; // ecx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  _BYTE *v37; // r10
  unsigned __int8 *v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rcx
  int v42; // r8d
  _BYTE *v43; // r10
  __int64 v44; // rax
  char v45; // r9
  _BYTE *v46; // r10
  __int64 v47; // rcx
  __int64 v48; // rax
  int v49; // ecx
  __int64 v50; // r15
  __int64 v51; // rcx
  int v52; // eax
  __int64 v53; // r12
  __int16 v54; // cx
  void *v55; // rcx
  char *v56; // rax
  _WORD *v57; // rcx
  const char *v58; // r8
  __int64 result; // rax
  __int64 v60; // [rsp+20h] [rbp-68h]
  __int64 v61; // [rsp+28h] [rbp-60h] BYREF
  __int64 v62[11]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v63; // [rsp+90h] [rbp+8h]
  _BYTE *v65; // [rsp+A0h] [rbp+18h]
  __int64 v66; // [rsp+A8h] [rbp+20h]

  v2 = a1[5];
  v61 = 0;
  v62[0] = 0;
  v4 = (_QWORD *)(v2 + 32);
  v5 = (_QWORD *)(v2 + 32);
LABEL_2:
  filter_ahead = _archive_read_filter_ahead(a1[2], 1u, (size_t *)&v61);
  if ( filter_ahead )
  {
    v7 = v61;
  }
  else
  {
    if ( v61 < 0 )
      return -30;
    v7 = 0;
    v5 = v4;
    v61 = 0;
  }
  v8 = 0;
  v66 = v7;
  v9 = v7;
  v63 = 0;
  v60 = v7;
  if ( *(_DWORD *)(v2 + 40) == 4 )
  {
    i = v7;
LABEL_102:
    if ( v9 >= v7 )
      v4 = v5;
    else
      i += v9 - v7;
    _archive_read_filter_consume(a1[2], i);
    *a2 = *v4;
    result = v8;
    *(_QWORD *)v2 += v8;
  }
  else
  {
    v5 = (_QWORD *)(v2 + 32);
    v65 = *(_BYTE **)(v2 + 32);
    v10 = *(_QWORD *)(v2 + 16);
    if ( !v10 )
    {
LABEL_11:
      for ( i = 0; ; i += v13 )
      {
        if ( i >= v7 )
          goto LABEL_100;
        line = get_line(filter_ahead, v7 - i, v62);
        v13 = line;
        if ( line < 0 )
        {
          if ( *(_DWORD *)(v2 + 40) || *(__int64 *)v2 <= 0 && v8 <= 0 )
          {
LABEL_41:
            archive_set_error(a1[3], 0xFFFFFFFFLL, "Insufficient compressed data");
            return -30;
          }
          v7 = v66;
          i = v66;
          *(_DWORD *)(v2 + 40) = 4;
          goto LABEL_100;
        }
        v14 = v62[0];
        if ( !v62[0] && *(_DWORD *)(v2 + 40) != 2 )
        {
          v9 = v60;
          if ( !v8 && v60 <= 0 )
          {
            v58 = "Missing format data";
            goto LABEL_95;
          }
          if ( (unsigned int)ensure_in_buff_size(a1, v2, line) )
            return -30;
          v57 = *(_WORD **)(v2 + 8);
          if ( v57 != filter_ahead )
            memmove_0(v57, filter_ahead, v13);
          *(_QWORD *)(v2 + 16) = v13;
          if ( !v8 )
          {
            _archive_read_filter_consume(a1[2], v60);
            v4 = (_QWORD *)(v2 + 32);
            goto LABEL_2;
          }
          v7 = v66;
          i += v13;
          goto LABEL_101;
        }
        v15 = *(_DWORD *)(v2 + 40);
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( !v16 )
          {
            if ( v8 + 2 * line > 0x10000 )
            {
LABEL_99:
              v7 = v66;
LABEL_100:
              v9 = v60;
LABEL_101:
              v4 = (_QWORD *)(v2 + 32);
              goto LABEL_102;
            }
            v34 = *(unsigned __int8 *)filter_ahead;
            if ( !byte_180131B20[v34 + 256] )
              goto LABEL_41;
            v35 = line - v62[0];
            if ( (__int64)(v13 - v62[0]) <= 0 )
              goto LABEL_41;
            v36 = ((_BYTE)v34 - 32) & 0x3F;
            if ( v36 > v35 - 1 )
              goto LABEL_41;
            if ( !v36 )
            {
              *(_DWORD *)(v2 + 40) = 2;
              goto LABEL_86;
            }
            v37 = v65;
            v38 = (unsigned __int8 *)filter_ahead + 1;
            do
            {
              v39 = *v38;
              if ( !byte_180131B20[v39 + 256] )
                break;
              v40 = v38[1];
              if ( !byte_180131B20[v40 + 256] )
                break;
              v63 = ++v8;
              v41 = v36 - 1;
              v42 = (((_DWORD)v40 << 12) - 126977) & 0x3F000 | (((_DWORD)v39 << 18) - 8126465) & 0xFC0000;
              *v37 = BYTE2(v42);
              v43 = v37 + 1;
              v65 = v43;
              v32 = v41 == 0;
              if ( v41 <= 0 )
                goto LABEL_40;
              v44 = v38[2];
              if ( !byte_180131B20[v44 + 256] )
                goto LABEL_41;
              v45 = v42 | (((_BYTE)v44 << 6) + 63) & 0xC0;
              *v43 = (unsigned __int16)(v42 | (((_WORD)v44 << 6) - 1985) & 0xFC0) >> 8;
              v46 = v43 + 1;
              ++v8;
              v65 = v46;
              v47 = v41 - 1;
              v63 = v8;
              v32 = v47 == 0;
              if ( v47 <= 0 )
                goto LABEL_40;
              v48 = v38[3];
              if ( !byte_180131B20[v48 + 256] )
                goto LABEL_41;
              v38 += 4;
              *v46 = v45 | (v48 - 32) & 0x3F;
              v37 = v46 + 1;
              ++v8;
              v65 = v37;
              v36 = v47 - 1;
              v63 = v8;
            }
            while ( v36 > 0 );
            v32 = v36 == 0;
            goto LABEL_40;
          }
          v17 = v16 - 1;
          if ( !v17 )
          {
            if ( line - v62[0] != 3 )
              goto LABEL_41;
            v33 = (unsigned __int16)*filter_ahead - 28261;
            if ( *filter_ahead == 28261 )
              v33 = *((unsigned __int8 *)filter_ahead + 2) - 100;
            if ( v33 )
              goto LABEL_41;
LABEL_46:
            *(_DWORD *)(v2 + 40) = 0;
            goto LABEL_86;
          }
          if ( v17 == 1 )
          {
            if ( v8 + 2 * line > 0x10000 )
              goto LABEL_99;
            v18 = (unsigned __int8 *)filter_ahead;
            v19 = line - v62[0];
            if ( line - v62[0] < 3 )
            {
              v20 = line == v62[0];
              if ( v19 > 0 )
                goto LABEL_27;
LABEL_38:
              if ( v20 )
                goto LABEL_86;
            }
            else
            {
              if ( *(_BYTE *)filter_ahead == 61
                && *((_BYTE *)filter_ahead + 1) == 61
                && *((_BYTE *)filter_ahead + 2) == 61 )
              {
                goto LABEL_46;
              }
LABEL_27:
              v21 = v65;
              while ( 1 )
              {
                v22 = *v18;
                if ( !byte_180131B20[v22] )
                  break;
                v23 = v18[1];
                if ( byte_180131B20[v23] )
                {
                  ++v8;
                  v18 += 2;
                  v24 = v19 - 2;
                  v25 = (dword_180131920[v23] | (dword_180131920[v22] << 6)) << 12;
                  v63 = v8;
                  *v21 = BYTE2(v25);
                  v26 = v21 + 1;
                  v65 = v26;
                  v20 = v24 == 0;
                  if ( v24 <= 0 )
                    goto LABEL_38;
                  if ( *v18 == 61 )
                    goto LABEL_86;
                  v27 = *v18;
                  if ( !byte_180131B20[v27] )
                    break;
                  ++v8;
                  v28 = v25 | (dword_180131920[v27] << 6);
                  v63 = v8;
                  ++v18;
                  *v26 = BYTE1(v28);
                  v29 = v26 + 1;
                  v30 = v24 - 1;
                  v65 = v29;
                  v20 = v30 == 0;
                  if ( v30 <= 0 )
                    goto LABEL_38;
                  if ( *v18 == 61 )
                    goto LABEL_86;
                  v31 = *v18;
                  if ( !byte_180131B20[v31] )
                    break;
                  v63 = ++v8;
                  *v29 = v28 | LOBYTE(dword_180131920[v31]);
                  ++v18;
                  v21 = v29 + 1;
                  v19 = v30 - 1;
                  v65 = v21;
                  if ( v19 > 0 )
                    continue;
                }
                v20 = v19 == 0;
                goto LABEL_38;
              }
            }
            v32 = *v18 == 61;
LABEL_40:
            if ( !v32 )
              goto LABEL_41;
            goto LABEL_86;
          }
        }
        if ( v8 + line >= 0x20000 )
          goto LABEL_94;
        if ( line - v62[0] < 11 )
          goto LABEL_72;
        v49 = *(_DWORD *)filter_ahead - 1768383842;
        if ( *(_DWORD *)filter_ahead == 1768383842 )
          v49 = (unsigned __int16)filter_ahead[2] - 8302;
        if ( v49 )
        {
LABEL_72:
          if ( line - v62[0] < 18 )
            goto LABEL_86;
          v51 = *(_QWORD *)filter_ahead - 0x61622D6E69676562LL;
          if ( *(_QWORD *)filter_ahead == 0x61622D6E69676562LL )
          {
            v51 = *((unsigned int *)filter_ahead + 2) - 875980147LL;
            if ( *((_DWORD *)filter_ahead + 2) == 875980147 )
              v51 = *((unsigned __int8 *)filter_ahead + 12) - 32LL;
          }
          if ( v51 )
            goto LABEL_86;
          v50 = 13;
        }
        else
        {
          v50 = 6;
        }
        if ( (unsigned __int8)(*((_BYTE *)filter_ahead + v50) - 48) <= 7u
          && (unsigned __int8)(*((_BYTE *)filter_ahead + v50 + 1) - 48) <= 7u
          && (unsigned __int8)(*((_BYTE *)filter_ahead + v50 + 2) - 48) <= 7u
          && *((_BYTE *)filter_ahead + v50 + 3) == 32 )
        {
          v52 = 1;
          if ( v50 != 6 )
            v52 = 3;
          *(_DWORD *)(v2 + 40) = v52;
          v53 = v13 - v50 - v14 - 4;
          v54 = *((unsigned __int8 *)filter_ahead + v50 + 2)
              + 8 * (*((unsigned __int8 *)filter_ahead + v50 + 1) + 8 * *((unsigned __int8 *)filter_ahead + v50));
          *(_DWORD *)(v2 + 48) = 1;
          *(_WORD *)(v2 + 44) = v54 - 3504;
          if ( v53 > 1 )
          {
            v55 = *(void **)(v2 + 56);
            if ( v55 )
              free(v55);
            v56 = (char *)malloc(v53 + 1);
            *(_QWORD *)(v2 + 56) = v56;
            if ( !v56 )
            {
              archive_set_error(a1[3], 12, "Can't allocate data for uudecode");
              return -30;
            }
            strncpy_0(v56, (const char *)filter_ahead + v50 + 4, (unsigned int)v53);
            *(_BYTE *)(v53 + *(_QWORD *)(v2 + 56)) = 0;
          }
        }
        v8 = v63;
LABEL_86:
        v7 = v66;
        filter_ahead = (_WORD *)((char *)filter_ahead + v13);
      }
    }
    if ( v10 <= 34816 )
    {
      if ( (unsigned int)ensure_in_buff_size(a1, v2, v10 + v7) )
        return -30;
      memcpy_0((void *)(*(_QWORD *)(v2 + 8) + *(_QWORD *)(v2 + 16)), filter_ahead, v9);
      filter_ahead = *(_WORD **)(v2 + 8);
      v66 = v9 + *(_QWORD *)(v2 + 16);
      v7 = v66;
      *(_QWORD *)(v2 + 16) = 0;
      v61 = v66;
      goto LABEL_11;
    }
LABEL_94:
    v58 = "Invalid format data";
LABEL_95:
    archive_set_error(a1[3], 42, v58);
    return -30;
  }
  return result;
}

```

## disassembly

```asm
0x1800c4100  mov     [rsp+arg_8], rdx
0x1800c4105  push    rbx
0x1800c4106  push    rbp
0x1800c4107  push    rsi
0x1800c4108  push    rdi
0x1800c4109  push    r12
0x1800c410b  push    r13
0x1800c410d  push    r14
0x1800c410f  push    r15
0x1800c4111  sub     rsp, 48h
0x1800c4115  mov     rbx, [rcx+28h]
0x1800c4119  mov     rdi, rcx
0x1800c411c  mov     [rsp+88h+var_60], 0
0x1800c4125  mov     [rsp+88h+var_58], 0
0x1800c412e  lea     r13, [rbx+20h]
0x1800c4132  mov     r14, r13
0x1800c4135  mov     rcx, [rdi+10h]
0x1800c4139  lea     r8, [rsp+88h+var_60]
0x1800c413e  mov     edx, 1
0x1800c4143  call    __archive_read_filter_ahead
0x1800c4148  xor     r11d, r11d
0x1800c414b  mov     rsi, rax
0x1800c414e  test    rax, rax
0x1800c4151  jnz     short loc_1800C416B
0x1800c4153  cmp     [rsp+88h+var_60], r11
0x1800c4158  jl      loc_1800C474C
0x1800c415e  mov     ecx, r11d
0x1800c4161  mov     r14, r13
0x1800c4164  mov     [rsp+88h+var_60], rcx
0x1800c4169  jmp     short loc_1800C4170
0x1800c416b  mov     rcx, [rsp+88h+var_60]
0x1800c4170  cmp     dword ptr [rbx+28h], 4
0x1800c4174  mov     r15, r11
0x1800c4177  mov     [rsp+88h+arg_18], rcx
0x1800c417f  mov     r12, rcx
0x1800c4182  mov     [rsp+88h+arg_0], r11
0x1800c418a  mov     [rsp+88h+var_68], rcx
0x1800c418f  jz      loc_1800C47C6
0x1800c4195  lea     r14, [rbx+20h]
0x1800c4199  mov     rax, [r14]
0x1800c419c  mov     [rsp+88h+arg_10], rax
0x1800c41a4  mov     rax, [rbx+10h]
0x1800c41a8  test    rax, rax
0x1800c41ab  jz      short loc_1800C4202
0x1800c41ad  cmp     rax, 8800h
0x1800c41b3  jg      loc_1800C4737
0x1800c41b9  lea     r8, [rax+rcx]
0x1800c41bd  mov     rdx, rbx
0x1800c41c0  mov     rcx, rdi
0x1800c41c3  call    ensure_in_buff_size
0x1800c41c8  test    eax, eax
0x1800c41ca  jnz     loc_1800C474C
0x1800c41d0  mov     rcx, [rbx+10h]
0x1800c41d4  mov     r8, r12; Size
0x1800c41d7  add     rcx, [rbx+8]; void *
0x1800c41db  mov     rdx, rsi; Src
0x1800c41de  call    memcpy_0
0x1800c41e3  mov     rcx, [rbx+10h]
0x1800c41e7  mov     rsi, [rbx+8]
0x1800c41eb  add     rcx, r12
0x1800c41ee  xor     r11d, r11d
0x1800c41f1  mov     [rsp+88h+arg_18], rcx
0x1800c41f9  mov     [rbx+10h], r11
0x1800c41fd  mov     [rsp+88h+var_60], rcx
0x1800c4202  mov     rbp, r11
0x1800c4205  cmp     rbp, rcx
0x1800c4208  jge     loc_1800C4776
0x1800c420e  mov     rdx, rcx
0x1800c4211  lea     r8, [rsp+88h+var_58]
0x1800c4216  sub     rdx, rbp
0x1800c4219  mov     rcx, rsi
0x1800c421c  call    get_line
0x1800c4221  xor     r11d, r11d
0x1800c4224  mov     r13, rax
0x1800c4227  test    rax, rax
0x1800c422a  js      loc_1800C479A
0x1800c4230  mov     r8, [rsp+88h+var_58]
0x1800c4235  test    r8, r8
0x1800c4238  jnz     short loc_1800C4244
0x1800c423a  cmp     dword ptr [rbx+28h], 2
0x1800c423e  jnz     loc_1800C46E4
0x1800c4244  mov     edx, [rbx+28h]
0x1800c4247  test    edx, edx
0x1800c4249  jz      loc_1800C4575
0x1800c424f  sub     edx, 1
0x1800c4252  jz      loc_1800C440A
0x1800c4258  sub     edx, 1
0x1800c425b  jz      loc_1800C43E1
0x1800c4261  cmp     edx, 1
0x1800c4264  jnz     loc_1800C4575
0x1800c426a  lea     rax, [r15+rax*2]
0x1800c426e  cmp     rax, 10000h
0x1800c4274  jg      loc_1800C476E
0x1800c427a  mov     rcx, r13
0x1800c427d  mov     rdx, rsi
0x1800c4280  sub     rcx, r8
0x1800c4283  cmp     rcx, 3
0x1800c4287  jl      short loc_1800C429F
0x1800c4289  cmp     byte ptr [rsi], 3Dh ; '='
0x1800c428c  jnz     short loc_1800C42A8
0x1800c428e  cmp     byte ptr [rsi+1], 3Dh ; '='
0x1800c4292  jnz     short loc_1800C42A8
0x1800c4294  cmp     byte ptr [rsi+2], 3Dh ; '='
0x1800c4298  jnz     short loc_1800C42A8
0x1800c429a  jmp     loc_1800C4401
0x1800c429f  test    rcx, rcx
0x1800c42a2  jle     loc_1800C43C3
0x1800c42a8  mov     r10, [rsp+88h+arg_10]
0x1800c42b0  lea     r12, cs:180000000h
0x1800c42b7  movzx   r8d, byte ptr [rdx]
0x1800c42bb  cmp     [r8+r12+131B20h], r11b
0x1800c42c3  jz      loc_1800C43C9
0x1800c42c9  movzx   eax, byte ptr [rdx+1]
0x1800c42cd  cmp     [rax+r12+131B20h], r11b
0x1800c42d5  jz      loc_1800C43C0
0x1800c42db  mov     r8d, ds:rva dword_180131920[r12+r8*4]
0x1800c42e3  inc     r15
0x1800c42e6  shl     r8d, 6
0x1800c42ea  add     rdx, 2
0x1800c42ee  or      r8d, ds:rva dword_180131920[r12+rax*4]
0x1800c42f6  sub     rcx, 2
0x1800c42fa  shl     r8d, 0Ch
0x1800c42fe  mov     eax, r8d
0x1800c4301  mov     [rsp+88h+arg_0], r15
0x1800c4309  sar     eax, 10h
0x1800c430c  mov     [r10], al
0x1800c430f  inc     r10
0x1800c4312  mov     [rsp+88h+arg_10], r10
0x1800c431a  test    rcx, rcx
0x1800c431d  jle     loc_1800C43C3
0x1800c4323  cmp     byte ptr [rdx], 3Dh ; '='
0x1800c4326  jz      loc_1800C46D1
0x1800c432c  movzx   r9d, byte ptr [rdx]
0x1800c4330  cmp     [r9+r12+131B20h], r11b
0x1800c4338  jz      loc_1800C43C9
0x1800c433e  mov     r9d, ds:rva dword_180131920[r12+r9*4]
0x1800c4346  inc     r15
0x1800c4349  shl     r9d, 6
0x1800c434d  or      r9d, r8d
0x1800c4350  mov     [rsp+88h+arg_0], r15
0x1800c4358  inc     rdx
0x1800c435b  mov     eax, r9d
0x1800c435e  sar     eax, 8
0x1800c4361  mov     [r10], al
0x1800c4364  inc     r10
0x1800c4367  dec     rcx
0x1800c436a  mov     [rsp+88h+arg_10], r10
0x1800c4372  test    rcx, rcx
0x1800c4375  jle     short loc_1800C43C3
0x1800c4377  cmp     byte ptr [rdx], 3Dh ; '='
0x1800c437a  jz      loc_1800C46D1
0x1800c4380  movzx   eax, byte ptr [rdx]
0x1800c4383  cmp     [rax+r12+131B20h], r11b
0x1800c438b  jz      short loc_1800C43C9
0x1800c438d  mov     al, byte ptr ds:rva dword_180131920[r12+rax*4]
0x1800c4395  inc     r15
0x1800c4398  or      al, r9b
0x1800c439b  mov     [rsp+88h+arg_0], r15
0x1800c43a3  mov     [r10], al
0x1800c43a6  inc     rdx
0x1800c43a9  inc     r10
0x1800c43ac  dec     rcx
0x1800c43af  mov     [rsp+88h+arg_10], r10
0x1800c43b7  test    rcx, rcx
0x1800c43ba  jg      loc_1800C42B7
0x1800c43c0  test    rcx, rcx
0x1800c43c3  jz      loc_1800C46D1
0x1800c43c9  cmp     byte ptr [rdx], 3Dh ; '='
0x1800c43cc  jz      loc_1800C46D1
0x1800c43d2  lea     r8, aInsufficientCo; "Insufficient compressed data"
0x1800c43d9  or      edx, 0FFFFFFFFh
0x1800c43dc  jmp     loc_1800C4743
0x1800c43e1  sub     rax, r8
0x1800c43e4  cmp     rax, 3
0x1800c43e8  jnz     short loc_1800C43D2
0x1800c43ea  movzx   ecx, word ptr [rsi]
0x1800c43ed  mov     eax, 6E65h
0x1800c43f2  sub     ecx, eax
0x1800c43f4  jnz     short loc_1800C43FD
0x1800c43f6  movzx   ecx, byte ptr [rsi+2]
0x1800c43fa  sub     ecx, 64h ; 'd'
0x1800c43fd  test    ecx, ecx
0x1800c43ff  jnz     short loc_1800C43D2
0x1800c4401  mov     [rbx+28h], r11d
0x1800c4405  jmp     loc_1800C46D1
0x1800c440a  lea     rax, [r15+rax*2]
0x1800c440e  cmp     rax, 10000h
0x1800c4414  jg      loc_1800C476E
0x1800c441a  movzx   ecx, byte ptr [rsi]
0x1800c441d  lea     r12, cs:180000000h
0x1800c4424  cmp     [rcx+r12+131C20h], r11b
0x1800c442c  jz      short loc_1800C43D2
0x1800c442e  mov     rax, r13
0x1800c4431  sub     rax, r8
0x1800c4434  test    rax, rax
0x1800c4437  jle     short loc_1800C43D2
0x1800c4439  add     rcx, 0FFFFFFFFFFFFFFE0h
0x1800c443d  and     ecx, 3Fh
0x1800c4440  dec     rax
0x1800c4443  cmp     rcx, rax
0x1800c4446  jg      short loc_1800C43D2
0x1800c4448  test    rcx, rcx
0x1800c444b  jnz     short loc_1800C4459
0x1800c444d  mov     dword ptr [rbx+28h], 2
0x1800c4454  jmp     loc_1800C46D1
0x1800c4459  mov     r10, [rsp+88h+arg_10]
0x1800c4461  lea     rdx, [rsi+1]
0x1800c4465  movzx   r8d, byte ptr [rdx]
0x1800c4469  cmp     [r8+r12+131C20h], r11b
0x1800c4471  jz      loc_1800C456D
0x1800c4477  movzx   eax, byte ptr [rdx+1]
0x1800c447b  cmp     [rax+r12+131C20h], r11b
0x1800c4483  jz      loc_1800C456D
0x1800c4489  shl     eax, 0Ch
0x1800c448c  inc     r15
0x1800c448f  shl     r8d, 12h
0x1800c4493  sub     eax, 1F001h
0x1800c4498  and     eax, 3F000h
0x1800c449d  mov     [rsp+88h+arg_0], r15
0x1800c44a5  sub     r8d, 7C0001h
0x1800c44ac  dec     rcx
0x1800c44af  and     r8d, 0FC0000h
0x1800c44b6  or      r8d, eax
0x1800c44b9  mov     eax, r8d
0x1800c44bc  shr     eax, 10h
0x1800c44bf  mov     [r10], al
0x1800c44c2  inc     r10
0x1800c44c5  mov     [rsp+88h+arg_10], r10
0x1800c44cd  test    rcx, rcx
0x1800c44d0  jle     loc_1800C43CC
0x1800c44d6  movzx   eax, byte ptr [rdx+2]
0x1800c44da  cmp     [rax+r12+131C20h], r11b
0x1800c44e2  jz      loc_1800C43D2
0x1800c44e8  mov     r9d, eax
0x1800c44eb  shl     r9d, 6
0x1800c44ef  sub     r9d, 7C1h
0x1800c44f6  and     r9d, 0FC0h
0x1800c44fd  or      r9d, r8d
0x1800c4500  mov     eax, r9d
0x1800c4503  shr     eax, 8
0x1800c4506  mov     [r10], al
0x1800c4509  inc     r10
0x1800c450c  inc     r15
0x1800c450f  mov     [rsp+88h+arg_10], r10
0x1800c4517  dec     rcx
0x1800c451a  mov     [rsp+88h+arg_0], r15
0x1800c4522  test    rcx, rcx
0x1800c4525  jle     loc_1800C43CC
0x1800c452b  movzx   eax, byte ptr [rdx+3]
0x1800c452f  cmp     [rax+r12+131C20h], r11b
0x1800c4537  jz      loc_1800C43D2
0x1800c453d  sub     al, 20h ; ' '
0x1800c453f  add     rdx, 4
0x1800c4543  and     al, 3Fh
0x1800c4545  or      al, r9b
0x1800c4548  mov     [r10], al
0x1800c454b  inc     r10
0x1800c454e  inc     r15
0x1800c4551  mov     [rsp+88h+arg_10], r10
0x1800c4559  dec     rcx
0x1800c455c  mov     [rsp+88h+arg_0], r15
0x1800c4564  test    rcx, rcx
0x1800c4567  jg      loc_1800C4465
0x1800c456d  test    rcx, rcx
0x1800c4570  jmp     loc_1800C43CC
0x1800c4575  add     rax, r15
0x1800c4578  cmp     rax, 20000h
0x1800c457e  jge     loc_1800C4737
0x1800c4584  mov     rdx, r13
0x1800c4587  sub     rdx, r8
0x1800c458a  cmp     rdx, 0Bh
0x1800c458e  jl      short loc_1800C45AF
0x1800c4590  mov     ecx, [rsi]
0x1800c4592  sub     ecx, 69676562h
0x1800c4598  jnz     short loc_1800C45A5
0x1800c459a  movzx   ecx, word ptr [rsi+4]
0x1800c459e  mov     eax, 206Eh
0x1800c45a3  sub     ecx, eax
0x1800c45a5  test    ecx, ecx
0x1800c45a7  jnz     short loc_1800C45AF
0x1800c45a9  lea     r15d, [rcx+6]
0x1800c45ad  jmp     short loc_1800C45F4
0x1800c45af  cmp     rdx, 12h
0x1800c45b3  jl      loc_1800C46D1
0x1800c45b9  mov     rcx, [rsi]
0x1800c45bc  mov     rax, 61622D6E69676562h
0x1800c45c6  sub     rcx, rax
0x1800c45c9  jnz     short loc_1800C45E7
0x1800c45cb  mov     ecx, [rsi+8]
0x1800c45ce  mov     eax, 34366573h
0x1800c45d3  sub     rcx, rax
0x1800c45d6  jnz     short loc_1800C45E7
0x1800c45d8  movzx   ecx, byte ptr [rsi+0Ch]
0x1800c45dc  mov     eax, 20h ; ' '
0x1800c45e1  movzx   eax, al
0x1800c45e4  sub     rcx, rax
0x1800c45e7  test    rcx, rcx
0x1800c45ea  jnz     loc_1800C46D1
0x1800c45f0  lea     r15d, [rcx+0Dh]
0x1800c45f4  mov     al, [r15+rsi]
  ... truncated ...
```
