# ORSetValueInternal

- ea: `0x18002dee0`
- end: `0x18002e32d`
- name: `ORSetValueInternal`
- size: `1101`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x18002bf64`

## callees

- `0x180002b28`
- `0x180002b34`
- `0x180002bc4`
- `0x180002c48`
- `0x18002dac4`
- `0x18002dee0`
- `0x18002e334`
- `0x18002eb7c`
- `0x18002eef8`
- `0x1800361a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e073`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e073`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e02a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e02a`

## string_xrefs

- `0x18002e0c5`: `SymbolicLinkValue`

## pseudocode

```c
__int64 __fastcall ORSetValueInternal(__int64 a1, void *a2, int a3, const void *a4, unsigned int a5, int a6)
{
  const void *v6; // r12
  __int64 v9; // r15
  char *v10; // r13
  int v11; // edi
  unsigned int v12; // edi
  unsigned int v13; // ebx
  __int64 v14; // rdx
  unsigned __int64 v15; // r8
  size_t v16; // rbx
  char *v17; // rax
  __int64 v19; // rbx
  unsigned __int64 v20; // rbx
  _OWORD *v21; // rax
  _QWORD *v22; // rsi
  void *v23; // rax
  void *v24; // rax
  _WORD *v25; // r8
  int v26; // eax
  __int16 v27; // cx
  __int16 v28; // ax
  unsigned __int16 v29; // dx
  __int16 v30; // cx
  bool v31; // cf
  unsigned __int64 v32; // rax
  const void *v33; // rdx
  _DWORD *v34; // rdx
  int v35; // eax
  _QWORD *v36; // rdx
  size_t v37; // rdx
  __int64 v38; // rax
  int v39; // [rsp+20h] [rbp-40h]
  _OWORD *v40; // [rsp+30h] [rbp-30h] BYREF
  size_t v41; // [rsp+38h] [rbp-28h]
  unsigned __int64 v42; // [rsp+40h] [rbp-20h]
  void *v43[2]; // [rsp+48h] [rbp-18h] BYREF
  size_t Size; // [rsp+A0h] [rbp+40h] BYREF
  void *Src; // [rsp+A8h] [rbp+48h]
  int v46; // [rsp+B0h] [rbp+50h]

  v46 = a3;
  Src = a2;
  v6 = a4;
  v9 = 0;
  Size = 0;
  v10 = 0;
  v40 = 0;
  v11 = 0;
  a6 = 0;
  *(_OWORD *)v43 = 0;
  if ( *(_WORD *)(a1 + 28) == 29806 )
  {
    v9 = *(_QWORD *)(a1 + 16);
    if ( *(_DWORD *)v9 == -1092567328 )
    {
      v12 = a5;
      if ( !a4 && a5 )
      {
        v13 = 87;
LABEL_6:
        v11 = 0;
        goto LABEL_20;
      }
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 40) + 13LL) & 3) == 1 )
      {
        v13 = 5;
        goto LABEL_6;
      }
      if ( (a5 & 1) == 0 && ((unsigned int)(a3 - 1) <= 1 || a3 == 7) )
      {
        if ( a4 )
        {
          v14 = a5 >> 1;
          if ( a5 >> 1 )
          {
            v15 = (unsigned __int64)a4 + 2 * (unsigned int)(v14 - 1);
            if ( *(_WORD *)v15 )
            {
              v16 = 2 * v14;
              if ( ((v15 ^ ((unsigned __int64)a4 + 2 * v14)) & 0xFFFFFFFFFFFFF000uLL) == 0 && !*((_WORD *)a4 + v14) )
              {
                v17 = (char *)o__aligned_malloc_0(a5 + 2LL, 0x10u);
                v10 = v17;
                if ( !v17 )
                {
LABEL_18:
                  v13 = 8;
LABEL_19:
                  v11 = a6;
                  goto LABEL_20;
                }
                memcpy_0(v17, v6, v16);
                v6 = v10;
                *(_WORD *)&v10[v16] = 0;
                v12 += 2;
              }
            }
          }
        }
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 136));
      a6 = 1;
      if ( *(_WORD *)(a1 + 30) )
      {
        v13 = 1018;
        v11 = 1;
        goto LABEL_20;
      }
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 40) + 2LL) & 0x10) != 0
        && (v46 != 6 || (v12 & 1) != 0 || v12 > 0xFFFF || !a2 || wcsicmp(L"SymbolicLinkValue", (const wchar_t *)a2)) )
      {
LABEL_34:
        v13 = 87;
        goto LABEL_19;
      }
      v13 = ORFindValue(a2, a1, &Size);
      if ( !v13 )
      {
        v37 = Size;
        v39 = v46;
        *(_DWORD *)(*(_QWORD *)(Size + 24) + 12LL) = v46;
        v13 = ORUpdateValue(v9, v37, v6, v12, v39);
        if ( v13 )
          goto LABEL_19;
        v38 = *(_QWORD *)(a1 + 40);
        if ( *(_DWORD *)(v38 + 64) < v12 )
          *(_DWORD *)(v38 + 64) = v12;
        goto LABEL_64;
      }
      if ( v13 != 2 )
        goto LABEL_19;
      if ( a2 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *((_WORD *)a2 + v19) );
        v20 = 2 * v19;
        if ( v20 > 0xFFFF )
        {
          LOWORD(v43[0]) = -1;
          v13 = 534;
          goto LABEL_19;
        }
        LOWORD(v43[0]) = v20;
      }
      else
      {
        LOWORD(v20) = 0;
        LOWORD(v43[0]) = 0;
      }
      if ( (unsigned __int16)v20 > 0x7FFFu )
        goto LABEL_34;
      v21 = o__aligned_malloc_0(0x30u, 0x10u);
      v22 = v21;
      if ( !v21 )
        goto LABEL_18;
      v40 = v21;
      *v21 = 0;
      WORD1(v43[0]) = v20;
      v21[1] = 0;
      v21[2] = 0;
      Size = (unsigned __int16)v20;
      v23 = o__aligned_malloc_0((unsigned __int16)v20, 0x10u);
      v43[1] = v23;
      if ( !v23 )
        goto LABEL_18;
      memcpy_0(v23, Src, Size);
      LODWORD(Size) = (unsigned __int16)ORCompressCopyName(v43[1], Size, *(_QWORD *)(v9 + 16), v43);
      v41 = (unsigned int)(Size + 20);
      v24 = o__aligned_malloc_0((unsigned int)v41, 0x10u);
      v42 = (unsigned __int64)v24;
      if ( !v24 )
        goto LABEL_18;
      memset_0(v24, 0, v41);
      v25 = (_WORD *)v42;
      v26 = v46;
      v22[3] = v42;
      v27 = v25[8];
      *((_DWORD *)v25 + 3) = v26;
      v28 = v27 & 0xFFFE;
      *v25 = 27510;
      v29 = Size;
      v30 = v27 | 1;
      v31 = (unsigned __int16)Size < (unsigned __int16)v20;
      v25[1] = Size;
      if ( !v31 )
        v30 = v28;
      v32 = v29;
      v33 = v43[1];
      v25[8] = v30;
      v42 = v32;
      memcpy_0(v25 + 10, v33, (unsigned int)v32);
      v13 = ORUpdateValue(v9, v22, v6, v12, v46);
      if ( v13 )
        goto LABEL_19;
      v34 = *(_DWORD **)(a1 + 40);
      if ( v34[16] < v12 )
        v34[16] = v12;
      if ( (*(_BYTE *)(v22[3] + 16LL) & 1) != 0 )
      {
        if ( (unsigned int)v34[15] < 2 * v42 )
        {
          v35 = 2 * Size;
LABEL_57:
          v34[15] = v35;
        }
      }
      else
      {
        v35 = Size;
        if ( v34[15] < (unsigned int)Size )
          goto LABEL_57;
      }
      ++v34[9];
      v36 = *(_QWORD **)(a1 + 136);
      if ( *v36 != a1 + 128 )
        __fastfail(3u);
      *v22 = a1 + 128;
      v22[1] = v36;
      *v36 = v22;
      *(_QWORD *)(a1 + 136) = v22;
LABEL_64:
      ++*(_QWORD *)(a1 + 168);
      v11 = 1;
      v13 = 0;
      *(_DWORD *)(v9 + 180) = 1;
      v40 = 0;
      goto LABEL_20;
    }
  }
  v13 = 6;
LABEL_20:
  ORFreeOrNop(v9, &v40);
  ORFreeOrNop(v9, &v43[1]);
  if ( v10 )
    aligned_free(v10);
  if ( v11 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 136));
  return v13;
}

```

## disassembly

```asm
0x18002dee0  mov     [rsp-38h+arg_18], rbx
0x18002dee5  mov     [rsp-38h+arg_10], r8d
0x18002deea  mov     [rsp-38h+Src], rdx
0x18002deef  push    rbp
0x18002def0  push    rsi
0x18002def1  push    rdi
0x18002def2  push    r12
0x18002def4  push    r13
0x18002def6  push    r14
0x18002def8  push    r15
0x18002defa  mov     rbp, rsp
0x18002defd  sub     rsp, 60h
0x18002df01  mov     r12, r9
0x18002df04  mov     eax, 746Eh
0x18002df09  xor     r9d, r9d
0x18002df0c  xorps   xmm0, xmm0
0x18002df0f  mov     rsi, rdx
0x18002df12  mov     r14, rcx
0x18002df15  mov     r15d, r9d
0x18002df18  mov     [rbp+Size], r9
0x18002df1c  mov     r13d, r9d
0x18002df1f  mov     [rbp+var_30], r9
0x18002df23  mov     edi, r9d
0x18002df26  mov     [rbp+arg_28], r9d
0x18002df2a  movups  xmmword ptr [rbp+var_18], xmm0
0x18002df2e  cmp     [rcx+1Ch], ax
0x18002df32  jnz     loc_18002E323
0x18002df38  mov     r15, [rcx+10h]
0x18002df3c  cmp     dword ptr [r15], 0BEE0BEE0h
0x18002df43  jnz     loc_18002E323
0x18002df49  mov     edi, [rbp+arg_20]
0x18002df4c  test    r12, r12
0x18002df4f  jnz     short loc_18002DF61
0x18002df51  test    edi, edi
0x18002df53  jz      short loc_18002DF61
0x18002df55  lea     ebx, [r9+57h]
0x18002df59  mov     edi, r9d
0x18002df5c  jmp     loc_18002DFFA
0x18002df61  mov     rax, [rcx+28h]
0x18002df65  mov     edx, 1
0x18002df6a  mov     cl, [rax+0Dh]
0x18002df6d  and     cl, 3
0x18002df70  cmp     cl, dl
0x18002df72  jnz     short loc_18002DF79
0x18002df74  lea     ebx, [rdx+4]
0x18002df77  jmp     short loc_18002DF59
0x18002df79  test    dl, dil
0x18002df7c  jnz     loc_18002E06C
0x18002df82  lea     eax, [r8-1]
0x18002df86  cmp     eax, edx
0x18002df88  jbe     short loc_18002DF94
0x18002df8a  cmp     r8d, 7
0x18002df8e  jnz     loc_18002E06C
0x18002df94  test    r12, r12
0x18002df97  jz      loc_18002E06C
0x18002df9d  mov     edx, edi
0x18002df9f  shr     edx, 1
0x18002dfa1  jz      loc_18002E06C
0x18002dfa7  lea     eax, [rdx-1]
0x18002dfaa  lea     r8, [r12+rax*2]
0x18002dfae  cmp     [r8], r9w
0x18002dfb2  jz      loc_18002E06C
0x18002dfb8  lea     rbx, [rdx+rdx]
0x18002dfbc  lea     rcx, [rbx+r12]
0x18002dfc0  mov     rax, rcx
0x18002dfc3  xor     rax, r8
0x18002dfc6  test    rax, 0FFFFFFFFFFFFF000h
0x18002dfcc  jnz     loc_18002E06C
0x18002dfd2  cmp     [rcx], r9w
0x18002dfd6  jnz     loc_18002E06C
0x18002dfdc  lea     rcx, [rdi+2]; Size
0x18002dfe0  mov     edx, 10h; Alignment
0x18002dfe5  call    _o__aligned_malloc_0
0x18002dfea  mov     r13, rax
0x18002dfed  test    rax, rax
0x18002dff0  jnz     short loc_18002E051
0x18002dff2  mov     ebx, 8
0x18002dff7  mov     edi, [rbp+arg_28]
0x18002dffa  lea     rdx, [rbp+var_30]
0x18002dffe  mov     rcx, r15
0x18002e001  call    ORFreeOrNop
0x18002e006  lea     rdx, [rbp+var_18+8]
0x18002e00a  mov     rcx, r15
0x18002e00d  call    ORFreeOrNop
0x18002e012  test    r13, r13
0x18002e015  jz      short loc_18002E01F
0x18002e017  mov     rcx, r13; Block
0x18002e01a  call    _aligned_free
0x18002e01f  test    edi, edi
0x18002e021  jz      short loc_18002E036
0x18002e023  lea     rcx, [r15+88h]; lpCriticalSection
0x18002e02a  call    cs:__imp_LeaveCriticalSection
0x18002e031  nop     dword ptr [rax+rax+00h]
0x18002e036  mov     eax, ebx
0x18002e038  mov     rbx, [rsp+60h+arg_18]
0x18002e040  add     rsp, 60h
0x18002e044  pop     r15
0x18002e046  pop     r14
0x18002e048  pop     r13
0x18002e04a  pop     r12
0x18002e04c  pop     rdi
0x18002e04d  pop     rsi
0x18002e04e  pop     rbp
0x18002e04f  retn
0x18002e051  mov     r8, rbx; Size
0x18002e054  mov     rdx, r12; Src
0x18002e057  mov     rcx, r13; void *
0x18002e05a  call    memcpy_0
0x18002e05f  xor     eax, eax
0x18002e061  mov     r12, r13
0x18002e064  mov     [rbx+r13], ax
0x18002e069  add     edi, 2
0x18002e06c  lea     rcx, [r15+88h]; lpCriticalSection
0x18002e073  call    cs:__imp_EnterCriticalSection
0x18002e07a  nop     dword ptr [rax+rax+00h]
0x18002e07f  xor     ecx, ecx
0x18002e081  mov     edx, 1
0x18002e086  mov     [rbp+arg_28], edx
0x18002e089  cmp     [r14+1Eh], cx
0x18002e08e  jz      short loc_18002E09C
0x18002e090  mov     ebx, 3FAh
0x18002e095  mov     edi, edx
0x18002e097  jmp     loc_18002DFFA
0x18002e09c  mov     rax, [r14+28h]
0x18002e0a0  test    byte ptr [rax+2], 10h
0x18002e0a4  jz      short loc_18002E0DF
0x18002e0a6  mov     ebx, 6
0x18002e0ab  cmp     [rbp+arg_10], ebx
0x18002e0ae  jnz     short loc_18002E0D5
0x18002e0b0  test    dl, dil
0x18002e0b3  jnz     short loc_18002E0D5
0x18002e0b5  cmp     edi, 0FFFFh
0x18002e0bb  ja      short loc_18002E0D5
0x18002e0bd  test    rsi, rsi
0x18002e0c0  jz      short loc_18002E0D5
0x18002e0c2  mov     rdx, rsi; String2
0x18002e0c5  lea     rcx, aSymboliclinkva; "SymbolicLinkValue"
0x18002e0cc  call    _wcsicmp
0x18002e0d1  test    eax, eax
0x18002e0d3  jz      short loc_18002E0DF
0x18002e0d5  mov     ebx, 57h ; 'W'
0x18002e0da  jmp     loc_18002DFF7
0x18002e0df  lea     r8, [rbp+Size]
0x18002e0e3  mov     rdx, r14
0x18002e0e6  mov     rcx, rsi
0x18002e0e9  call    ORFindValue
0x18002e0ee  mov     ebx, eax
0x18002e0f0  xor     eax, eax
0x18002e0f2  test    ebx, ebx
0x18002e0f4  jz      loc_18002E2CD
0x18002e0fa  cmp     ebx, 2
0x18002e0fd  jnz     loc_18002DFF7
0x18002e103  test    rsi, rsi
0x18002e106  jz      short loc_18002E136
0x18002e108  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e10c  inc     rbx
0x18002e10f  cmp     [rsi+rbx*2], ax
0x18002e113  jnz     short loc_18002E10C
0x18002e115  add     rbx, rbx
0x18002e118  mov     eax, 0FFFFh
0x18002e11d  cmp     rbx, rax
0x18002e120  ja      short loc_18002E128
0x18002e122  mov     word ptr [rbp+var_18], bx
0x18002e126  jmp     short loc_18002E13D
0x18002e128  mov     word ptr [rbp+var_18], ax
0x18002e12c  mov     ebx, 216h
0x18002e131  jmp     loc_18002DFF7
0x18002e136  movzx   ebx, ax
0x18002e139  mov     word ptr [rbp+var_18], ax
0x18002e13d  mov     eax, 7FFFh
0x18002e142  cmp     bx, ax
0x18002e145  ja      short loc_18002E0D5
0x18002e147  mov     edx, 10h; Alignment
0x18002e14c  lea     ecx, [rdx+20h]; Size
0x18002e14f  call    _o__aligned_malloc_0
0x18002e154  mov     rsi, rax
0x18002e157  test    rax, rax
0x18002e15a  jz      loc_18002DFF2
0x18002e160  xorps   xmm0, xmm0
0x18002e163  mov     [rbp+var_30], rax
0x18002e167  movups  xmmword ptr [rax], xmm0
0x18002e16a  mov     edx, 10h; Alignment
0x18002e16f  mov     word ptr [rbp+var_18+2], bx
0x18002e173  movups  xmmword ptr [rax+10h], xmm0
0x18002e177  movups  xmmword ptr [rax+20h], xmm0
0x18002e17b  movzx   eax, bx
0x18002e17e  mov     ecx, eax; Size
0x18002e180  mov     [rbp+Size], rax
0x18002e184  call    _o__aligned_malloc_0
0x18002e189  mov     [rbp+var_18+8], rax
0x18002e18d  test    rax, rax
0x18002e190  jz      loc_18002DFF2
0x18002e196  mov     r8, [rbp+Size]; Size
0x18002e19a  mov     rcx, rax; void *
0x18002e19d  mov     rdx, [rbp+Src]; Src
0x18002e1a1  call    memcpy_0
0x18002e1a6  mov     r8, [r15+10h]
0x18002e1aa  lea     r9, [rbp+var_18]
0x18002e1ae  mov     rdx, [rbp+Size]
0x18002e1b2  mov     rcx, [rbp+var_18+8]
0x18002e1b6  call    ORCompressCopyName
0x18002e1bb  movzx   eax, ax
0x18002e1be  mov     edx, 10h; Alignment
0x18002e1c3  mov     dword ptr [rbp+Size], eax
0x18002e1c6  add     eax, 14h
0x18002e1c9  mov     ecx, eax; Size
0x18002e1cb  mov     [rbp+var_28], rax
0x18002e1cf  call    _o__aligned_malloc_0
0x18002e1d4  mov     [rbp+var_20], rax
0x18002e1d8  test    rax, rax
0x18002e1db  jz      loc_18002DFF2
0x18002e1e1  mov     r8, [rbp+var_28]; Size
0x18002e1e5  xor     edx, edx; Val
0x18002e1e7  mov     rcx, rax; void *
0x18002e1ea  call    memset_0
0x18002e1ef  mov     r8, [rbp+var_20]
0x18002e1f3  mov     edx, 0FFFEh
0x18002e1f8  mov     eax, [rbp+arg_10]
0x18002e1fb  mov     [rsi+18h], r8
0x18002e1ff  movzx   ecx, word ptr [r8+10h]
0x18002e204  mov     [r8+0Ch], eax
0x18002e208  movzx   eax, cx
0x18002e20b  and     ax, dx
0x18002e20e  mov     word ptr [r8], 6B76h
0x18002e214  mov     edx, dword ptr [rbp+Size]
0x18002e217  or      cx, 1
0x18002e21b  cmp     dx, bx
0x18002e21e  mov     [r8+2], dx
0x18002e223  cmovnb  cx, ax
0x18002e227  movzx   eax, dx
0x18002e22a  mov     rdx, [rbp+var_18+8]; Src
0x18002e22e  mov     [r8+10h], cx
0x18002e233  lea     rcx, [r8+14h]; void *
0x18002e237  mov     r8d, eax; Size
0x18002e23a  mov     [rbp+var_20], rax
0x18002e23e  call    memcpy_0
0x18002e243  mov     eax, [rbp+arg_10]
0x18002e246  mov     r9d, edi
0x18002e249  mov     r8, r12
0x18002e24c  mov     [rsp+60h+var_40], eax
0x18002e250  mov     rdx, rsi
0x18002e253  mov     rcx, r15
0x18002e256  call    ORUpdateValue
0x18002e25b  mov     ebx, eax
0x18002e25d  test    eax, eax
0x18002e25f  jnz     loc_18002DFF7
0x18002e265  mov     rdx, [r14+28h]
0x18002e269  cmp     [rdx+40h], edi
0x18002e26c  jnb     short loc_18002E271
0x18002e26e  mov     [rdx+40h], edi
0x18002e271  mov     rax, [rsi+18h]
0x18002e275  mov     r8d, 1
0x18002e27b  test    [rax+10h], r8b
0x18002e27f  jz      short loc_18002E297
0x18002e281  mov     rcx, [rbp+var_20]
0x18002e285  mov     eax, [rdx+3Ch]
0x18002e288  add     rcx, rcx
0x18002e28b  cmp     rax, rcx
0x18002e28e  jnb     short loc_18002E2A2
0x18002e290  mov     eax, dword ptr [rbp+Size]
0x18002e293  add     eax, eax
0x18002e295  jmp     short loc_18002E29F
0x18002e297  mov     eax, dword ptr [rbp+Size]
0x18002e29a  cmp     [rdx+3Ch], eax
0x18002e29d  jnb     short loc_18002E2A2
0x18002e29f  mov     [rdx+3Ch], eax
0x18002e2a2  add     [rdx+24h], r8d
0x18002e2a6  lea     rax, [r14+80h]
0x18002e2ad  mov     rdx, [rax+8]
0x18002e2b1  cmp     [rdx], rax
0x18002e2b4  jz      short loc_18002E2BD
0x18002e2b6  mov     ecx, 3
0x18002e2bb  int     29h; Win8: RtlFailFast(ecx)
0x18002e2bd  mov     [rsi], rax
0x18002e2c0  mov     [rsi+8], rdx
0x18002e2c4  mov     [rdx], rsi
0x18002e2c7  mov     [rax+8], rsi
0x18002e2cb  jmp     short loc_18002E303
0x18002e2cd  mov     ecx, [rbp+arg_10]
0x18002e2d0  mov     r9d, edi
0x18002e2d3  mov     rdx, [rbp+Size]
0x18002e2d7  mov     r8, r12
0x18002e2da  mov     [rsp+60h+var_40], ecx
0x18002e2de  mov     rax, [rdx+18h]
0x18002e2e2  mov     [rax+0Ch], ecx
0x18002e2e5  mov     rcx, r15
0x18002e2e8  call    ORUpdateValue
0x18002e2ed  mov     ebx, eax
0x18002e2ef  test    eax, eax
0x18002e2f1  jnz     loc_18002DFF7
0x18002e2f7  mov     rax, [r14+28h]
0x18002e2fb  cmp     [rax+40h], edi
0x18002e2fe  jnb     short loc_18002E303
0x18002e300  mov     [rax+40h], edi
0x18002e303  mov     eax, 1
0x18002e308  add     [r14+0A8h], rax
0x18002e30f  mov     edi, eax
0x18002e311  xor     ebx, ebx
0x18002e313  mov     [r15+0B4h], eax
0x18002e31a  mov     [rbp+var_30], rbx
  ... truncated ...
```
