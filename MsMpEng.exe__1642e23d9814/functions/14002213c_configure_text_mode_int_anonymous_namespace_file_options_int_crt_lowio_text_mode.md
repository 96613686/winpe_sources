# configure_text_mode(int,`anonymous namespace'::file_options,int,__crt_lowio_text_mode &)

- ea: `0x14002213c`
- end: `0x1400223bb`
- name: `?configure_text_mode@@YAHHUfile_options@?A0xa9d50aae@@HAEAW4__crt_lowio_text_mode@@@Z`
- size: `639`
- prototype: `__int64 __fastcall(unsigned int, __int64, int, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140022694`

## callees

- `0x1400160bc`
- `0x140016ea0`
- `0x140018784`
- `0x140021700`
- `0x14002213c`
- `0x140023a2c`
- `0x14002411c`

## pseudocode

```c
__int64 __fastcall configure_text_mode(unsigned int a1, __int64 a2, int a3, _BYTE *a4)
{
  int v5; // ebx
  int v7; // esi
  int v9; // ecx
  int v10; // edi
  unsigned int v11; // eax
  int v12; // ecx
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int v20; // eax
  int v21; // eax
  int v22; // [rsp+50h] [rbp+8h] BYREF

  v5 = 0;
  *a4 = 0;
  v7 = a3;
  if ( *(char *)(qword_14003E600[(__int64)(int)a1 >> 6] + 72LL * (a1 & 0x3F) + 56) >= 0 )
    return 0;
  if ( (a3 & 0x74000) == 0 )
  {
    v22 = 0;
    if ( get_fmode(&v22) )
      invoke_watson(0, 0, 0, 0, 0);
    if ( (v22 & 0x74000) != 0 )
      v7 |= v22 & 0x74000;
    else
      v7 |= 0x4000u;
  }
  v9 = v7 & 0x74000;
  v10 = 2;
  if ( (v7 & 0x74000) == 0x4000 )
  {
    *a4 = 0;
    goto LABEL_15;
  }
  if ( ((v9 - 0x10000) & 0xFFFFBFFF) == 0 )
  {
    if ( (v7 & 0x301) != 0x301 )
      goto LABEL_15;
LABEL_13:
    *a4 = 2;
    goto LABEL_15;
  }
  if ( ((v9 - 0x20000) & 0xFFFFBFFF) == 0 )
    goto LABEL_13;
  if ( ((v9 - 0x40000) & 0xFFFFBFFF) == 0 )
    *a4 = 1;
LABEL_15:
  if ( (v7 & 0x70000) == 0 || (*(_BYTE *)a2 & 0x40) != 0 )
    return 0;
  v11 = *(_DWORD *)(a2 + 4) & 0xC0000000;
  if ( v11 != 0x40000000 )
  {
    if ( v11 == 0x80000000 )
      goto LABEL_32;
    if ( v11 != -1073741824 )
      return 0;
  }
  if ( *(_DWORD *)(a2 + 8) != 1 && *(_DWORD *)(a2 + 8) != 2 )
  {
    if ( *(_DWORD *)(a2 + 8) != 3 && *(_DWORD *)(a2 + 8) != 4 )
    {
      if ( *(_DWORD *)(a2 + 8) != 5 )
        return 0;
      goto LABEL_25;
    }
    if ( lseeki64_nolock(a1, 0, 2) )
    {
      if ( lseeki64_nolock(a1, 0, 0) == -1 )
        return *(unsigned int *)sub_140016EA0(v16, v15, v17, v18);
      if ( (*(_DWORD *)(a2 + 4) & 0x80000000) == 0 )
        return 0;
LABEL_32:
      v22 = 0;
      v20 = sub_14002411C(a1, &v22, 3);
      if ( v20 == -1 )
        return *(unsigned int *)sub_140016EA0(v16, v15, v17, v18);
      if ( v20 != 2 )
      {
        if ( v20 != 3 )
          goto LABEL_42;
        if ( v22 == 12565487 )
        {
          *a4 = 1;
          return 0;
        }
      }
      if ( (unsigned __int16)v22 == 65534 )
      {
        *(_DWORD *)sub_140016EA0((unsigned __int16)v22, v15, v17, v18) = 22;
        return *(unsigned int *)sub_140016EA0(v16, v15, v17, v18);
      }
      if ( (unsigned __int16)v22 == 65279 )
      {
        if ( lseeki64_nolock(a1, 2, 0) != -1 )
        {
          *a4 = 2;
          return 0;
        }
        return *(unsigned int *)sub_140016EA0(v16, v15, v17, v18);
      }
LABEL_42:
      if ( lseeki64_nolock(a1, 0, 0) != -1 )
        return 0;
      return *(unsigned int *)sub_140016EA0(v16, v15, v17, v18);
    }
  }
LABEL_25:
  v12 = (char)*a4;
  v22 = 0;
  v13 = v12 - 1;
  if ( !v13 )
  {
    v10 = 3;
    v14 = 12565487;
LABEL_45:
    v22 = v14;
    while ( 1 )
    {
      v21 = write(a1, (char *)&v22 + v5, v10 - v5);
      if ( v21 == -1 )
        break;
      v5 += v21;
      if ( v10 <= v5 )
        return 0;
    }
    return *(unsigned int *)sub_140016EA0(v16, v15, v17, v18);
  }
  if ( v13 == 1 )
  {
    v14 = 65279;
    goto LABEL_45;
  }
  return 0;
}

```

## disassembly

```asm
0x14002213c  mov     r11, rsp
0x14002213f  mov     [r11+10h], rbx
0x140022143  mov     [r11+18h], rbp
0x140022147  mov     [r11+20h], rsi
0x14002214b  push    rdi
0x14002214c  push    r14
0x14002214e  push    r15
0x140022150  sub     rsp, 30h
0x140022154  movsxd  r15, ecx
0x140022157  xor     ebx, ebx
0x140022159  mov     r10, r15
0x14002215c  mov     [r9], bl
0x14002215f  and     r10d, 3Fh
0x140022163  lea     rcx, qword_14003E600
0x14002216a  mov     rax, r15
0x14002216d  mov     r14, r9
0x140022170  sar     rax, 6
0x140022174  mov     esi, r8d
0x140022177  mov     rbp, rdx
0x14002217a  lea     r10, [r10+r10*8]
0x14002217e  mov     rax, [rcx+rax*8]
0x140022182  cmp     [rax+r10*8+38h], bl
0x140022187  jge     loc_14002238C
0x14002218d  mov     edi, 74000h
0x140022192  test    edi, r8d
0x140022195  jnz     short loc_1400221B8
0x140022197  lea     rcx, [r11+8]; PMode
0x14002219b  mov     [rsp+48h+arg_0], ebx
0x14002219f  call    _get_fmode
0x1400221a4  test    eax, eax
0x1400221a6  jnz     loc_1400223A7
0x1400221ac  mov     eax, [rsp+48h+arg_0]
0x1400221b0  and     eax, edi
0x1400221b2  jnz     short loc_1400221F2
0x1400221b4  bts     esi, 0Eh
0x1400221b8  mov     ecx, esi
0x1400221ba  and     ecx, edi
0x1400221bc  mov     edi, 2
0x1400221c1  cmp     ecx, 4000h
0x1400221c7  jz      short loc_140022208
0x1400221c9  lea     eax, [rcx-10000h]
0x1400221cf  mov     edx, 0FFFFBFFFh
0x1400221d4  test    edx, eax
0x1400221d6  jz      short loc_1400221F6
0x1400221d8  lea     eax, [rcx-20000h]
0x1400221de  test    edx, eax
0x1400221e0  jz      short loc_140022203
0x1400221e2  lea     eax, [rcx-40000h]
0x1400221e8  test    edx, eax
0x1400221ea  jnz     short loc_14002220B
0x1400221ec  mov     byte ptr [r14], 1
0x1400221f0  jmp     short loc_14002220B
0x1400221f2  or      esi, eax
0x1400221f4  jmp     short loc_1400221B8
0x1400221f6  mov     ecx, 301h
0x1400221fb  mov     eax, esi
0x1400221fd  and     eax, ecx
0x1400221ff  cmp     eax, ecx
0x140022201  jnz     short loc_14002220B
0x140022203  mov     [r14], dil
0x140022206  jmp     short loc_14002220B
0x140022208  mov     [r14], bl
0x14002220b  test    esi, 70000h
0x140022211  jz      loc_14002238C
0x140022217  test    byte ptr [rbp+0], 40h
0x14002221b  jnz     loc_14002238C
0x140022221  mov     eax, [rbp+4]
0x140022224  mov     ecx, 0C0000000h
0x140022229  and     eax, ecx
0x14002222b  mov     esi, 80000000h
0x140022230  cmp     eax, 40000000h
0x140022235  jz      short loc_140022247
0x140022237  cmp     eax, esi
0x140022239  jz      loc_1400222C5
0x14002223f  cmp     eax, ecx
0x140022241  jnz     loc_14002238C
0x140022247  mov     ecx, [rbp+8]
0x14002224a  sub     ecx, 1
0x14002224d  jz      short loc_140022267
0x14002224f  sub     ecx, 1
0x140022252  jz      short loc_140022267
0x140022254  sub     ecx, 1
0x140022257  jz      short loc_14002228B
0x140022259  sub     ecx, 1
0x14002225c  jz      short loc_14002228B
0x14002225e  cmp     ecx, 1
0x140022261  jnz     loc_14002238C
0x140022267  movsx   ecx, byte ptr [r14]
0x14002226b  mov     [rsp+48h+arg_0], ebx
0x14002226f  sub     ecx, 1
0x140022272  jz      loc_140022356
0x140022278  cmp     ecx, 1
0x14002227b  jnz     loc_14002238C
0x140022281  mov     eax, 0FEFFh
0x140022286  jmp     loc_140022360
0x14002228b  mov     r8d, edi
0x14002228e  xor     edx, edx
0x140022290  mov     ecx, r15d
0x140022293  call    _lseeki64_nolock
0x140022298  test    rax, rax
0x14002229b  jz      short loc_140022267
0x14002229d  xor     r8d, r8d
0x1400222a0  xor     edx, edx
0x1400222a2  mov     ecx, r15d
0x1400222a5  call    _lseeki64_nolock
0x1400222aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400222ae  jnz     short loc_1400222BC
0x1400222b0  call    sub_140016EA0
0x1400222b5  mov     eax, [rax]
0x1400222b7  jmp     loc_14002238E
0x1400222bc  test    [rbp+4], esi
0x1400222bf  jz      loc_14002238C
0x1400222c5  mov     r8d, 3
0x1400222cb  mov     [rsp+48h+arg_0], ebx
0x1400222cf  lea     rdx, [rsp+48h+arg_0]
0x1400222d4  mov     ecx, r15d
0x1400222d7  call    sub_14002411C
0x1400222dc  cmp     eax, 0FFFFFFFFh
0x1400222df  jz      short loc_1400222B0
0x1400222e1  cmp     eax, edi
0x1400222e3  jz      short loc_1400222FE
0x1400222e5  cmp     eax, 3
0x1400222e8  jnz     short loc_14002233E
0x1400222ea  mov     eax, 0BFBBEFh
0x1400222ef  cmp     [rsp+48h+arg_0], eax
0x1400222f3  jnz     short loc_1400222FE
0x1400222f5  mov     byte ptr [r14], 1
0x1400222f9  jmp     loc_14002238C
0x1400222fe  movzx   ecx, word ptr [rsp+48h+arg_0]
0x140022303  cmp     ecx, 0FFFEh
0x140022309  jnz     short loc_140022318
0x14002230b  call    sub_140016EA0
0x140022310  mov     dword ptr [rax], 16h
0x140022316  jmp     short loc_1400222B0
0x140022318  mov     eax, 0FEFFh
0x14002231d  cmp     ecx, eax
0x14002231f  jnz     short loc_14002233E
0x140022321  xor     r8d, r8d
0x140022324  mov     rdx, rdi
0x140022327  mov     ecx, r15d
0x14002232a  call    _lseeki64_nolock
0x14002232f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140022333  jz      loc_1400222B0
0x140022339  mov     [r14], dil
0x14002233c  jmp     short loc_14002238C
0x14002233e  xor     r8d, r8d
0x140022341  xor     edx, edx
0x140022343  mov     ecx, r15d
0x140022346  call    _lseeki64_nolock
0x14002234b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002234f  jnz     short loc_14002238C
0x140022351  jmp     loc_1400222B0
0x140022356  mov     edi, 3
0x14002235b  mov     eax, 0BFBBEFh
0x140022360  mov     [rsp+48h+arg_0], eax
0x140022364  mov     r8d, edi
0x140022367  movsxd  rax, ebx
0x14002236a  lea     rdx, [rsp+48h+arg_0]
0x14002236f  sub     r8d, ebx; MaxCharCount
0x140022372  add     rdx, rax; Buf
0x140022375  mov     ecx, r15d; FileHandle
0x140022378  call    _write
0x14002237d  cmp     eax, 0FFFFFFFFh
0x140022380  jz      loc_1400222B0
0x140022386  add     ebx, eax
0x140022388  cmp     edi, ebx
0x14002238a  jg      short loc_140022364
0x14002238c  xor     eax, eax
0x14002238e  mov     rbx, [rsp+48h+arg_8]
0x140022393  mov     rbp, [rsp+48h+arg_10]
0x140022398  mov     rsi, [rsp+48h+arg_18]
0x14002239d  add     rsp, 30h
0x1400223a1  pop     r15
0x1400223a3  pop     r14
0x1400223a5  pop     rdi
0x1400223a6  retn
0x1400223a7  xor     r9d, r9d; LineNo
0x1400223aa  mov     [rsp+48h+Reserved], rbx; Reserved
0x1400223af  xor     r8d, r8d; FileName
0x1400223b2  xor     edx, edx; FunctionName
0x1400223b4  xor     ecx, ecx; Expression
0x1400223b6  call    _invoke_watson
```
