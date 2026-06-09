# header_pax_extension

- ea: `0x1800e05a4`
- end: `0x1800e0b21`
- name: `header_pax_extension`
- size: `1405`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800075f4`

## callees

- `0x180005914`
- `0x180005c7c`
- `0x180006c00`
- `0x18000a2d0`
- `0x18000c0ec`
- `0x18000ce38`
- `0x18000e764`
- `0x1800144b0`
- `0x180014a74`
- `0x1800b1730`
- `0x1800e05a4`
- `0x1800e0eec`
- `0x1800ece24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e0833`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800e0833`

## string_xrefs

- `0x1800e09d5`: `Pathname`
- `0x1800e0601`: `pax extension header has invalid size: %lld`
- `0x1800e066a`: `Ignoring oversized pax extensions: %lld > %lld`
- `0x1800e0950`: `Truncated tar archive detected while reading pax attribute name`
- `0x1800e08c6`: `Truncated tar archive detected while completing pax attribute`
- `0x1800e0ad9`: `Linkpath`

## pseudocode

```c
__int64 __fastcall header_pax_extension(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v10; // r12
  int v11; // r13d
  unsigned int v12; // r15d
  size_t v13; // rdx
  _BYTE *filter_ahead; // rax
  _BYTE *v15; // r8
  signed __int64 v16; // r9
  __int64 v17; // rdx
  char *v18; // rcx
  char *v19; // r8
  char *v20; // r9
  char *v21; // rdx
  bool v22; // zf
  __int64 v23; // rdi
  __int64 v24; // rax
  int v25; // eax
  _BYTE *v26; // rax
  __int64 v27; // rbx
  _QWORD *v28; // rdi
  __int64 v29; // r12
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // r8
  int v33; // eax
  int v34; // ecx
  signed __int64 v35; // [rsp+40h] [rbp-30h] BYREF
  _BYTE *v36; // [rsp+48h] [rbp-28h]
  __int64 v37; // [rsp+50h] [rbp-20h]
  void *Block[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v39; // [rsp+68h] [rbp-8h]
  _BYTE *v41; // [rsp+C8h] [rbp+58h]
  int v42; // [rsp+C8h] [rbp+58h]

  v35 = 0;
  v39 = 0;
  *(_OWORD *)Block = 0;
  v7 = tar_atol(a4 + 124, 12);
  v8 = v7;
  if ( v7 > 0xFFFFFFFFFFFFFFFLL )
    return 4294967266LL;
  if ( v7 < 0 )
  {
    archive_set_error(a1, 22, "pax extension header has invalid size: %lld", v7);
    return 4294967266LL;
  }
  v10 = -(int)v7 & 0x1FF;
  if ( v7 > 0x40000000 )
  {
    if ( v10 + v7 == _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v10 + v7) )
    {
      archive_set_error(a1, 22, "Ignoring oversized pax extensions: %lld > %lld", v8, 0x40000000);
      return 4294967276LL;
    }
    return 4294967266LL;
  }
  if ( (unsigned int)tar_flush_unconsumed(a1, a5) )
    return 4294967266LL;
  v11 = 0;
  v12 = -20;
  Block[0] = 0;
  Block[1] = 0;
  v39 = 0;
  while ( 1 )
  {
    if ( v8 <= 0 )
    {
      *a5 += v10 + v8;
      if ( *(_DWORD *)(a2 + 144) )
      {
        v27 = archive_string_conversion_from_charset(a1, "UTF-8", 1);
        if ( !v27 )
          return 4294967266LL;
      }
      else
      {
        v27 = *(_QWORD *)(a2 + 296);
      }
      if ( *(_QWORD *)(a2 + 32) )
      {
        v28 = (_QWORD *)(a2 + 24);
      }
      else
      {
        if ( !*(_QWORD *)(a2 + 8) )
        {
          v29 = a3;
          goto LABEL_67;
        }
        v28 = (_QWORD *)a2;
      }
      v29 = a3;
      if ( v28 && (unsigned int)archive_mstring_copy_mbs_len_l(a3 + 488, *v28, v28[1], v27) )
      {
        v11 = set_conversion_failed_error(a1, v27, "Pathname");
        if ( v11 == -30 )
          return 4294967266LL;
        archive_mstring_copy_mbs(a3 + 488, *v28);
      }
LABEL_67:
      v30 = *(_QWORD *)(a2 + 56);
      if ( v30 && (unsigned int)archive_mstring_copy_mbs_len_l(v29 + 592, *(_QWORD *)(a2 + 48), v30, v27) )
      {
        v11 = set_conversion_failed_error(a1, v27, "Uname");
        if ( v11 == -30 )
          return 4294967266LL;
        archive_mstring_copy_mbs(v29 + 592, *(_QWORD *)(a2 + 48));
      }
      v31 = *(_QWORD *)(a2 + 80);
      if ( v31 && (unsigned int)archive_mstring_copy_mbs_len_l(v29 + 280, *(_QWORD *)(a2 + 72), v31, v27) )
      {
        v11 = set_conversion_failed_error(a1, v27, "Gname");
        if ( v11 == -30 )
          return 4294967266LL;
        archive_mstring_copy_mbs(v29 + 280, *(_QWORD *)(a2 + 72));
      }
      v32 = *(_QWORD *)(a2 + 104);
      if ( v32 )
      {
        v33 = archive_mstring_copy_mbs_len_l(v29 + 384, *(_QWORD *)(a2 + 96), v32, v27);
        v34 = *(_DWORD *)(v29 + 160);
        if ( (v34 & 2) == 0 )
          *(_DWORD *)(v29 + 160) = v34 | 1;
        if ( v33 )
        {
          v11 = set_conversion_failed_error(a1, v27, "Linkpath");
          if ( v11 == -30 )
            return 4294967266LL;
          archive_entry_copy_link(v29, *(_QWORD *)(a2 + 96));
        }
      }
      *(_QWORD *)(a2 + 168) = -*(_DWORD *)(a2 + 152) & 0x1FF;
      return (unsigned int)v11;
    }
    v13 = 512;
    if ( v8 < 512 )
      v13 = v8;
    filter_ahead = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), v13, (size_t *)&v35);
    v15 = filter_ahead;
    if ( !filter_ahead )
    {
      archive_set_error(a1, 22, "Truncated tar archive detected while reading pax attribute name");
      return 4294967266LL;
    }
    v16 = v35;
    v41 = filter_ahead;
    if ( v35 > v8 )
      v16 = v8;
    v17 = 0;
    v37 = 0;
    v35 = v16;
LABEL_17:
    v18 = &filter_ahead[v16];
    if ( v15 >= &filter_ahead[v16] )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "Ignoring malformed pax attributes: overlarge attribute size field");
      goto LABEL_52;
    }
    if ( *v15 != 32 )
      break;
    if ( v17 > v8 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "Ignoring malformed pax attribute:  %lld > %lld", v17, v8);
      goto LABEL_52;
    }
    v19 = v15 + 1;
    if ( v19 >= v18 || (v20 = &filter_ahead[v17], v19 >= &filter_ahead[v17]) || *v19 == 61 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "Ignoring malformed pax attributes: empty name found");
      goto LABEL_52;
    }
    v21 = v19;
    while ( 1 )
    {
      if ( v19 >= v18 || v19 >= v20 )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Ignoring malformed pax attributes: overlarge attribute name");
        goto LABEL_52;
      }
      v22 = *v19 == 61;
      v36 = v19 + 1;
      if ( v22 )
        break;
      ++v19;
    }
    Block[1] = 0;
    archive_strncat(Block, v21, v19 - v21);
    *a5 += v36 - v41;
    if ( (unsigned int)tar_flush_unconsumed(a1, a5) )
      return 4294967266LL;
    v23 = v41 - v36 + v8;
    v22 = v41 - v36 + v37 == 0;
    v24 = v41 - v36 + v37;
    v37 = v24;
    if ( v22 )
      goto LABEL_46;
    v25 = pax_attribute(a1, a2, a3, (char *)Block[0], (unsigned __int64)Block[1], v24 - 1, a5);
    v37 = v23 - v37;
    v23 = v37 + 1;
    v42 = v25;
    Block[1] = 0;
    v39 = 0;
    free(Block[0]);
    Block[0] = 0;
    if ( v42 < -20 )
    {
      v12 = v42;
LABEL_47:
      *a5 += v10 + v23;
      return v12;
    }
    if ( v11 >= v42 )
      v11 = v42;
    if ( (unsigned int)tar_flush_unconsumed(a1, a5) )
      return 4294967266LL;
    v26 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 1u, (size_t *)&v35);
    if ( !v26 )
    {
      archive_set_error(a1, 22, "Truncated tar archive detected while completing pax attribute");
      return 4294967266LL;
    }
    if ( *v26 != 10 )
    {
LABEL_46:
      archive_set_error(a1, 22, "Malformed pax attributes");
      goto LABEL_47;
    }
    ++*a5;
    if ( (unsigned int)tar_flush_unconsumed(a1, a5) )
      return 4294967266LL;
    v8 = v37;
  }
  if ( (unsigned __int8)(*v15 - 48) > 9u )
  {
    archive_set_error(a1, 0xFFFFFFFFLL, "Ignoring malformed pax attributes: malformed attribute size field");
    goto LABEL_52;
  }
  v17 = (char)*v15 - 48 + 10 * v17;
  v37 = v17;
  if ( (unsigned __int64)v17 <= 0x5F5E0FF )
  {
    filter_ahead = v41;
    ++v15;
    goto LABEL_17;
  }
  archive_set_error(a1, 0xFFFFFFFFLL, "Ignoring malformed pax attribute: size > %lld", 99999999);
LABEL_52:
  *a5 += v10 + v8;
  return v12;
}

```

## disassembly

```asm
0x1800e05a4  mov     [rsp-38h+arg_0], rbx
0x1800e05a9  mov     [rsp-38h+arg_10], r8
0x1800e05ae  push    rbp
0x1800e05af  push    rsi
0x1800e05b0  push    rdi
0x1800e05b1  push    r12
0x1800e05b3  push    r13
0x1800e05b5  push    r14
0x1800e05b7  push    r15
0x1800e05b9  mov     rbp, rsp
0x1800e05bc  sub     rsp, 70h
0x1800e05c0  xor     eax, eax
0x1800e05c2  mov     [rbp+var_30], 0
0x1800e05ca  mov     r14, rdx
0x1800e05cd  mov     [rbp+var_8], rax
0x1800e05d1  mov     rsi, rcx
0x1800e05d4  xorps   xmm0, xmm0
0x1800e05d7  lea     rcx, [r9+7Ch]
0x1800e05db  lea     edx, [rax+0Ch]
0x1800e05de  movups  xmmword ptr [rbp+Block], xmm0
0x1800e05e2  call    tar_atol
0x1800e05e7  mov     rcx, 0FFFFFFFFFFFFFFFh
0x1800e05f1  mov     rdi, rax
0x1800e05f4  cmp     rax, rcx
0x1800e05f7  jg      short loc_1800E0615
0x1800e05f9  test    rax, rax
0x1800e05fc  jns     short loc_1800E0632
0x1800e05fe  mov     r9, rax
0x1800e0601  lea     r8, aPaxExtensionHe; "pax extension header has invalid size: "...
0x1800e0608  mov     edx, 16h
0x1800e060d  mov     rcx, rsi
0x1800e0610  call    archive_set_error
0x1800e0615  mov     eax, 0FFFFFFE2h
0x1800e061a  mov     rbx, [rsp+70h+arg_0]
0x1800e0622  add     rsp, 70h
0x1800e0626  pop     r15
0x1800e0628  pop     r14
0x1800e062a  pop     r13
0x1800e062c  pop     r12
0x1800e062e  pop     rdi
0x1800e062f  pop     rsi
0x1800e0630  pop     rbp
0x1800e0631  retn
0x1800e0632  mov     r12, rdi
0x1800e0635  mov     r15d, 40000000h
0x1800e063b  neg     r12
0x1800e063e  and     r12d, 1FFh
0x1800e0645  cmp     rdi, r15
0x1800e0648  jle     short loc_1800E0685
0x1800e064a  mov     rcx, [rsi+278h]
0x1800e0651  lea     rbx, [r12+rax]
0x1800e0655  mov     rdx, rbx
0x1800e0658  call    __archive_read_filter_consume
0x1800e065d  cmp     rbx, rax
0x1800e0660  jnz     short loc_1800E0615
0x1800e0662  mov     r9, rdi
0x1800e0665  mov     [rsp+70h+var_50], r15
0x1800e066a  lea     r8, aIgnoringOversi; "Ignoring oversized pax extensions: %lld"...
0x1800e0671  mov     edx, 16h
0x1800e0676  mov     rcx, rsi
0x1800e0679  call    archive_set_error
0x1800e067e  mov     eax, 0FFFFFFECh
0x1800e0683  jmp     short loc_1800E061A
0x1800e0685  mov     rbx, [rbp+arg_20]
0x1800e0689  mov     rcx, rsi
0x1800e068c  mov     rdx, rbx
0x1800e068f  call    tar_flush_unconsumed
0x1800e0694  test    eax, eax
0x1800e0696  jnz     loc_1800E0615
0x1800e069c  xor     r13d, r13d
0x1800e069f  lea     r15d, [rax-14h]
0x1800e06a3  mov     [rbp+Block], r13
0x1800e06a7  mov     [rbp+Block+8], r13
0x1800e06ab  mov     [rbp+var_8], r13
0x1800e06af  test    rdi, rdi
0x1800e06b2  jle     loc_1800E095C
0x1800e06b8  mov     rcx, [rsi+278h]
0x1800e06bf  lea     r8, [rbp+var_30]
0x1800e06c3  mov     edx, 200h
0x1800e06c8  cmp     rdi, rdx
0x1800e06cb  cmovl   rdx, rdi
0x1800e06cf  call    __archive_read_filter_ahead
0x1800e06d4  mov     r8, rax
0x1800e06d7  test    rax, rax
0x1800e06da  jz      loc_1800E0950
0x1800e06e0  mov     r9, [rbp+var_30]
0x1800e06e4  cmp     r9, rdi
0x1800e06e7  mov     [rbp+arg_18], rax
0x1800e06eb  cmovg   r9, rdi
0x1800e06ef  xor     edx, edx
0x1800e06f1  mov     [rbp+var_20], rdx
0x1800e06f5  mov     [rbp+var_30], r9
0x1800e06f9  lea     rcx, [rax+r9]
0x1800e06fd  cmp     r8, rcx
0x1800e0700  jnb     loc_1800E092F
0x1800e0706  cmp     byte ptr [r8], 20h ; ' '
0x1800e070a  jz      short loc_1800E0746
0x1800e070c  mov     al, [r8]
0x1800e070f  sub     al, 30h ; '0'
0x1800e0711  cmp     al, 9
0x1800e0713  ja      loc_1800E08BD
0x1800e0719  movsx   eax, byte ptr [r8]
0x1800e071d  sub     eax, 30h ; '0'
0x1800e0720  movsxd  rcx, eax
0x1800e0723  lea     rax, [rdx+rdx*4]
0x1800e0727  lea     rdx, [rcx+rax*2]
0x1800e072b  mov     eax, 5F5E0FFh
0x1800e0730  mov     [rbp+var_20], rdx
0x1800e0734  cmp     rdx, rax
0x1800e0737  ja      loc_1800E08A3
0x1800e073d  mov     rax, [rbp+arg_18]
0x1800e0741  inc     r8
0x1800e0744  jmp     short loc_1800E06F9
0x1800e0746  cmp     rdx, rdi
0x1800e0749  jg      loc_1800E0913
0x1800e074f  inc     r8
0x1800e0752  cmp     r8, rcx
0x1800e0755  jnb     loc_1800E090A
0x1800e075b  lea     r9, [rax+rdx]
0x1800e075f  cmp     r8, r9
0x1800e0762  jnb     loc_1800E090A
0x1800e0768  cmp     byte ptr [r8], 3Dh ; '='
0x1800e076c  jz      loc_1800E090A
0x1800e0772  mov     rdx, r8
0x1800e0775  cmp     r8, rcx
0x1800e0778  jnb     loc_1800E0901
0x1800e077e  cmp     r8, r9
0x1800e0781  jnb     loc_1800E0901
0x1800e0787  cmp     byte ptr [r8], 3Dh ; '='
0x1800e078b  lea     rax, [r8+1]
0x1800e078f  mov     [rbp+var_28], rax
0x1800e0793  jz      short loc_1800E079A
0x1800e0795  mov     r8, rax
0x1800e0798  jmp     short loc_1800E0775
0x1800e079a  sub     r8, rdx
0x1800e079d  mov     [rbp+Block+8], 0
0x1800e07a5  lea     rcx, [rbp+Block]
0x1800e07a9  call    archive_strncat
0x1800e07ae  mov     rax, [rbp+var_28]
0x1800e07b2  mov     rdx, rbx
0x1800e07b5  sub     rax, [rbp+arg_18]
0x1800e07b9  mov     rcx, rsi
0x1800e07bc  add     [rbx], rax
0x1800e07bf  call    tar_flush_unconsumed
0x1800e07c4  test    eax, eax
0x1800e07c6  jnz     loc_1800E0615
0x1800e07cc  mov     rax, [rbp+var_20]
0x1800e07d0  mov     rcx, [rbp+arg_18]
0x1800e07d4  sub     rcx, [rbp+var_28]
0x1800e07d8  add     rdi, rcx
0x1800e07db  add     rax, rcx
0x1800e07de  mov     [rbp+var_20], rax
0x1800e07e2  jz      loc_1800E08E4
0x1800e07e8  mov     r9, [rbp+Block]
0x1800e07ec  dec     rax
0x1800e07ef  mov     r8, [rbp+arg_10]
0x1800e07f3  mov     rdx, r14
0x1800e07f6  mov     [rsp+70h+var_40], rbx
0x1800e07fb  mov     rcx, rsi
0x1800e07fe  mov     [rsp+70h+var_48], rax
0x1800e0803  mov     rax, [rbp+Block+8]
0x1800e0807  mov     [rsp+70h+var_50], rax
0x1800e080c  call    pax_attribute
0x1800e0811  sub     rdi, [rbp+var_20]
0x1800e0815  mov     rcx, [rbp+Block]; Block
0x1800e0819  mov     [rbp+var_20], rdi
0x1800e081d  inc     rdi
0x1800e0820  mov     dword ptr [rbp+arg_18], eax
0x1800e0823  mov     [rbp+Block+8], 0
0x1800e082b  mov     [rbp+var_8], 0
0x1800e0833  call    cs:__imp_free
0x1800e0839  mov     eax, dword ptr [rbp+arg_18]
0x1800e083c  mov     [rbp+Block], 0
0x1800e0844  cmp     eax, r15d
0x1800e0847  jl      loc_1800E08DF
0x1800e084d  cmp     r13d, eax
0x1800e0850  mov     rdx, rbx
0x1800e0853  mov     rcx, rsi
0x1800e0856  cmovge  r13d, eax
0x1800e085a  call    tar_flush_unconsumed
0x1800e085f  test    eax, eax
0x1800e0861  jnz     loc_1800E0615
0x1800e0867  mov     rcx, [rsi+278h]
0x1800e086e  lea     r8, [rbp+var_30]
0x1800e0872  lea     edx, [rax+1]
0x1800e0875  call    __archive_read_filter_ahead
0x1800e087a  test    rax, rax
0x1800e087d  jz      short loc_1800E08C6
0x1800e087f  cmp     byte ptr [rax], 0Ah
0x1800e0882  jnz     short loc_1800E08E4
0x1800e0884  inc     qword ptr [rbx]
0x1800e0887  mov     rdx, rbx
0x1800e088a  mov     rcx, rsi
0x1800e088d  call    tar_flush_unconsumed
0x1800e0892  test    eax, eax
0x1800e0894  jnz     loc_1800E0615
0x1800e089a  mov     rdi, [rbp+var_20]
0x1800e089e  jmp     loc_1800E06AF
0x1800e08a3  mov     r9, rax
0x1800e08a6  lea     r8, aIgnoringMalfor_0; "Ignoring malformed pax attribute: size "...
0x1800e08ad  or      edx, 0FFFFFFFFh
0x1800e08b0  mov     rcx, rsi
0x1800e08b3  call    archive_set_error
0x1800e08b8  jmp     loc_1800E0941
0x1800e08bd  lea     r8, aIgnoringMalfor_2; "Ignoring malformed pax attributes: malf"...
0x1800e08c4  jmp     short loc_1800E0936
0x1800e08c6  lea     r8, aTruncatedTarAr_1; "Truncated tar archive detected while co"...
0x1800e08cd  mov     edx, 16h
0x1800e08d2  mov     rcx, rsi
0x1800e08d5  call    archive_set_error
0x1800e08da  jmp     loc_1800E0615
0x1800e08df  mov     r15d, eax
0x1800e08e2  jmp     short loc_1800E08F8
0x1800e08e4  lea     r8, aMalformedPaxAt; "Malformed pax attributes"
0x1800e08eb  mov     edx, 16h
0x1800e08f0  mov     rcx, rsi
0x1800e08f3  call    archive_set_error
0x1800e08f8  lea     rcx, [r12+rdi]
0x1800e08fc  add     [rbx], rcx
0x1800e08ff  jmp     short loc_1800E0948
0x1800e0901  lea     r8, aIgnoringMalfor_1; "Ignoring malformed pax attributes: over"...
0x1800e0908  jmp     short loc_1800E0936
0x1800e090a  lea     r8, aIgnoringMalfor_4; "Ignoring malformed pax attributes: empt"...
0x1800e0911  jmp     short loc_1800E0936
0x1800e0913  mov     r9, rdx
0x1800e0916  mov     [rsp+70h+var_50], rdi
0x1800e091b  or      edx, 0FFFFFFFFh
0x1800e091e  lea     r8, aIgnoringMalfor; "Ignoring malformed pax attribute:  %lld"...
0x1800e0925  mov     rcx, rsi
0x1800e0928  call    archive_set_error
0x1800e092d  jmp     short loc_1800E0941
0x1800e092f  lea     r8, aIgnoringMalfor_3; "Ignoring malformed pax attributes: over"...
0x1800e0936  or      edx, 0FFFFFFFFh
0x1800e0939  mov     rcx, rsi
0x1800e093c  call    archive_set_error
0x1800e0941  lea     rax, [r12+rdi]
0x1800e0945  add     [rbx], rax
0x1800e0948  mov     eax, r15d
0x1800e094b  jmp     loc_1800E061A
0x1800e0950  lea     r8, aTruncatedTarAr; "Truncated tar archive detected while re"...
0x1800e0957  jmp     loc_1800E08CD
0x1800e095c  lea     rax, [r12+rdi]
0x1800e0960  add     [rbx], rax
0x1800e0963  cmp     dword ptr [r14+90h], 0
0x1800e096b  jnz     short loc_1800E0976
0x1800e096d  mov     rbx, [r14+128h]
0x1800e0974  jmp     short loc_1800E0997
0x1800e0976  mov     r8d, 1
0x1800e097c  lea     rdx, Str2; "UTF-8"
0x1800e0983  mov     rcx, rsi
0x1800e0986  call    archive_string_conversion_from_charset
0x1800e098b  mov     rbx, rax
0x1800e098e  test    rax, rax
0x1800e0991  jz      loc_1800E0615
0x1800e0997  cmp     qword ptr [r14+20h], 0
0x1800e099c  jbe     short loc_1800E09A4
0x1800e099e  lea     rdi, [r14+18h]
0x1800e09a2  jmp     short loc_1800E09AE
0x1800e09a4  cmp     qword ptr [r14+8], 0
0x1800e09a9  jbe     short loc_1800E0A00
0x1800e09ab  mov     rdi, r14
0x1800e09ae  mov     r12, [rbp+arg_10]
0x1800e09b2  test    rdi, rdi
0x1800e09b5  jz      short loc_1800E0A04
0x1800e09b7  mov     r8, [rdi+8]
0x1800e09bb  lea     r15, [r12+1E8h]
0x1800e09c3  mov     rdx, [rdi]
0x1800e09c6  mov     rcx, r15
0x1800e09c9  mov     r9, rbx
0x1800e09cc  call    archive_mstring_copy_mbs_len_l
0x1800e09d1  test    eax, eax
0x1800e09d3  jz      short loc_1800E0A04
0x1800e09d5  lea     r8, aPathname; "Pathname"
0x1800e09dc  mov     rdx, rbx
0x1800e09df  mov     rcx, rsi
0x1800e09e2  call    set_conversion_failed_error
0x1800e09e7  mov     r13d, eax
0x1800e09ea  cmp     eax, 0FFFFFFE2h
0x1800e09ed  jz      loc_1800E0615
0x1800e09f3  mov     rdx, [rdi]
0x1800e09f6  mov     rcx, r15
0x1800e09f9  call    archive_mstring_copy_mbs
0x1800e09fe  jmp     short loc_1800E0A04
0x1800e0a00  mov     r12, [rbp+arg_10]
0x1800e0a04  mov     r8, [r14+38h]
0x1800e0a08  test    r8, r8
0x1800e0a0b  jz      short loc_1800E0A52
0x1800e0a0d  mov     rdx, [r14+30h]
0x1800e0a11  lea     rdi, [r12+250h]
0x1800e0a19  mov     rcx, rdi
0x1800e0a1c  mov     r9, rbx
0x1800e0a1f  call    archive_mstring_copy_mbs_len_l
0x1800e0a24  test    eax, eax
0x1800e0a26  jz      short loc_1800E0A52
0x1800e0a28  lea     r8, aUname_0; "Uname"
0x1800e0a2f  mov     rdx, rbx
0x1800e0a32  mov     rcx, rsi
0x1800e0a35  call    set_conversion_failed_error
0x1800e0a3a  mov     r13d, eax
0x1800e0a3d  cmp     eax, 0FFFFFFE2h
  ... truncated ...
```
