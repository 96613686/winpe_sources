# LSP::LexEntryData::ComputeLemmaFrom(ushort const *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x18004ff88`
- end: `0x180050308`
- name: `?ComputeLemmaFrom@LexEntryData@LSP@@QEBAPEBGPEBG_KPEAG1@Z`
- size: `896`
- prototype: `const unsigned __int16 *(LSP::LexEntryData *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180035f30`
- `0x18003ce34`

## callees

- `0x180009710`
- `0x18000a630`
- `0x18002be20`
- `0x18003c078`
- `0x18004e638`
- `0x18004ff88`
- `0x180051928`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800502e7`
- `msvcrt!memcpy_s` at `0x1800502e7`

## pseudocode

```c
unsigned __int16 *__fastcall LSP::LexEntryData::ComputeLemmaFrom(
        LSP::LexEntryData *this,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned __int16 *a4,
        unsigned __int64 a5)
{
  unsigned int v6; // r9d
  unsigned __int64 v8; // rsi
  int v9; // ebx
  int v10; // ebp
  __int64 v11; // r12
  unsigned __int16 v12; // r10
  unsigned __int16 v13; // r13
  __int64 v14; // r14
  int v15; // r15d
  int v16; // r8d
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  __int16 v30; // ax
  int v31; // eax
  unsigned __int16 *v32; // rcx
  unsigned __int64 v33; // rdx
  int v34; // eax
  __int16 v35; // r10
  unsigned __int16 v36; // ax
  unsigned int v37; // eax
  unsigned __int16 v38; // ax
  __int64 v39; // r9
  unsigned int v40; // eax
  __int64 v41; // r8
  int v42; // r14d
  int j; // esi
  __int64 v44; // rcx
  __int64 v45; // rax
  int i; // edx
  __int64 v47; // rcx
  __int64 v48; // rax
  int v50; // [rsp+20h] [rbp-78h]
  int v51; // [rsp+24h] [rbp-74h]
  int v52; // [rsp+28h] [rbp-70h]
  wchar_t *Source; // [rsp+30h] [rbp-68h]
  unsigned __int16 v54; // [rsp+A0h] [rbp+8h]

  v6 = *((_DWORD *)this + 2);
  v8 = a3;
  v9 = -1;
  v54 = 0;
  v10 = 0;
  LODWORD(v11) = 0;
  v12 = 0;
  Source = 0;
  v13 = 0;
  LODWORD(v14) = 0;
  v15 = -1;
  v50 = -1;
  v51 = -1;
  v52 = -1;
  while ( v6 )
  {
    v16 = v6 & 0xF;
    v17 = (unsigned __int8)v6 >> 4;
    if ( v17 > 9 )
    {
      if ( v17 == 10 || v17 == 11 || v17 == 12 || v17 == 13 || v17 == 14 )
      {
        v26 = v17 - 10;
        if ( v26 )
        {
          v27 = v26 - 1;
          if ( v27 )
          {
            v28 = v27 - 1;
            if ( v28 )
            {
              v29 = v28 - 1;
              if ( v29 )
              {
                if ( v29 == 1 )
                  v30 = 126;
                else
                  v30 = 0;
              }
              else
              {
                v30 = 94;
              }
            }
            else
            {
              v30 = 168;
            }
          }
          else
          {
            v30 = 96;
          }
        }
        else
        {
          v30 = 180;
        }
        v13 = v30;
        v9 = v6 & 0xF;
      }
      else
      {
        if ( v17 != 15 )
        {
LABEL_42:
          v31 = StringCchCopyNW(a4, a5, a2, a3);
          ThrowIfFailed(v31);
          return a4;
        }
        v23 = 3;
        v24 = 3;
        if ( (unsigned int)(2 * v16) < 3 )
          v24 = (unsigned int)(2 * v16);
        v25 = 2 * v16 + 1;
        if ( v25 < 3 )
          v23 = v25;
        v6 >>= 8;
        v14 = qword_1800C0538[v24];
        v15 = (unsigned __int8)v6;
        Source = (&off_1800B7CD8)[v23];
        v11 = qword_1800C0538[(unsigned int)v23];
      }
    }
    else if ( v17 == 9 )
    {
      v50 = v6 & 0xF;
    }
    else
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 2;
          if ( v20 )
          {
            v21 = v20 - 2;
            if ( v21 )
            {
              v22 = v21 - 1;
              if ( v22 )
              {
                if ( v22 != 1 )
                  goto LABEL_42;
                v52 = v6 & 0xF;
              }
              else
              {
                v51 = v6 & 0xF;
              }
            }
            else
            {
              v6 >>= 8;
              v12 = ((_WORD)v16 << 8) | (unsigned __int8)v6;
            }
          }
          else
          {
            v6 >>= 8;
            v54 = ((_WORD)v16 << 8) | (unsigned __int8)v6;
          }
        }
        else
        {
          v10 = v6 & 0xF;
        }
      }
      else
      {
        v8 -= v6 & 0xF;
      }
    }
    v6 >>= 8;
  }
  if ( v12 )
  {
    *a4 = v12;
    v32 = a4 + 1;
    v33 = a5 - 1;
  }
  else
  {
    v32 = a4;
    v33 = a5;
  }
  v34 = StringCchCopyNW(v32, v33, &a2[v10], v8);
  ThrowIfFailed(v34);
  v35 = 0;
  if ( v54 )
  {
    v36 = v54;
    a4[v8 + 1] = 0;
  }
  else
  {
    v36 = 0;
  }
  a4[v8] = v36;
  if ( v13 )
  {
    v37 = LSP::LexEntryData::ExpandAccent(a4[v9]);
    v38 = LSP::LexEntryData::AddAccentTo(HIWORD(v37), v13);
    a4[v39] = v38;
  }
  if ( v50 >= 0 )
  {
    v40 = LSP::LexEntryData::ExpandAccent(a4[v50]);
    a4[v41] = HIWORD(v40);
  }
  if ( v51 >= 0 )
  {
    a4[v51] = CMN_CharUpperW(a4[v51]);
    v35 = 0;
  }
  if ( v52 >= 0 )
  {
    a4[v52] = CMN_CharLowerW(a4[v52]);
    v35 = 0;
  }
  if ( v15 >= 0 )
  {
    v42 = v14 - v11;
    if ( v42 >= 0 )
    {
      if ( v42 > 0 )
      {
        for ( i = v11 + v15; a4[i] != v35; ++i )
        {
          v47 = i;
          v48 = i + v42;
          a4[v47] = a4[v48];
        }
      }
    }
    else
    {
      for ( j = v8 - v42; j >= (int)v11 + v15; --j )
      {
        v44 = j;
        v45 = j + v42;
        a4[v44] = a4[v45];
      }
    }
    memcpy_s(&a4[v15], 2 * (a5 - v15), Source, 2LL * (int)v11);
  }
  return a4;
}

```

## disassembly

```asm
0x18004ff88  mov     rax, rsp
0x18004ff8b  mov     [rax+10h], rbx
0x18004ff8f  mov     [rax+18h], r8
0x18004ff93  push    rbp
0x18004ff94  push    rsi
0x18004ff95  push    rdi
0x18004ff96  push    r12
0x18004ff98  push    r13
0x18004ff9a  push    r14
0x18004ff9c  push    r15
0x18004ff9e  sub     rsp, 60h
0x18004ffa2  xorps   xmm0, xmm0
0x18004ffa5  mov     rdi, r9
0x18004ffa8  mov     r9d, [rcx+8]
0x18004ffac  mov     r11, rdx
0x18004ffaf  xor     edx, edx
0x18004ffb1  mov     rsi, r8
0x18004ffb4  or      ebx, 0FFFFFFFFh
0x18004ffb7  mov     [rsp+98h+arg_0], edx
0x18004ffbe  movups  xmmword ptr [rax-50h], xmm0
0x18004ffc2  mov     rcx, [rax-50h]
0x18004ffc6  mov     ebp, edx
0x18004ffc8  mov     r12, [rax-48h]
0x18004ffcc  mov     r10d, edx
0x18004ffcf  movups  xmmword ptr [rax-60h], xmm0
0x18004ffd3  mov     [rax-68h], rcx
0x18004ffd7  mov     r13d, edx
0x18004ffda  mov     r14, [rax-58h]
0x18004ffde  mov     r15d, ebx
0x18004ffe1  mov     [rsp+98h+var_78], ebx
0x18004ffe5  mov     [rsp+98h+var_74], ebx
0x18004ffe9  mov     [rsp+98h+var_70], ebx
0x18004ffed  test    r9d, r9d
0x18004fff0  jz      loc_18005019E
0x18004fff6  mov     ecx, r9d
0x18004fff9  mov     r8d, r9d
0x18004fffc  shr     ecx, 4
0x18004ffff  and     r8d, 0Fh
0x180050003  and     ecx, 0Fh
0x180050006  cmp     ecx, 9
0x180050009  ja      loc_1800500AD
0x18005000f  jz      loc_1800500A3
0x180050015  sub     ecx, 1
0x180050018  jz      short loc_180050098
0x18005001a  sub     ecx, 1
0x18005001d  jz      short loc_180050090
0x18005001f  sub     ecx, 2
0x180050022  jz      short loc_18005006A
0x180050024  sub     ecx, 2
0x180050027  jz      short loc_18005004B
0x180050029  sub     ecx, 1
0x18005002c  jz      short loc_180050041
0x18005002e  cmp     ecx, 1
0x180050031  jnz     loc_180050177
0x180050037  mov     [rsp+98h+var_70], r8d
0x18005003c  jmp     loc_18005016E
0x180050041  mov     [rsp+98h+var_74], r8d
0x180050046  jmp     loc_18005016E
0x18005004b  shr     r9d, 8
0x18005004f  mov     ecx, 0FFh
0x180050054  movzx   r10d, r9w
0x180050058  shl     r8w, 8
0x18005005d  and     r10w, cx
0x180050061  or      r10w, r8w
0x180050065  jmp     loc_18005016E
0x18005006a  shr     r9d, 8
0x18005006e  mov     ecx, 0FFh
0x180050073  movzx   eax, r9w
0x180050077  shl     r8w, 8
0x18005007c  and     ax, cx
0x18005007f  or      ax, r8w
0x180050083  mov     word ptr [rsp+98h+arg_0], ax
0x18005008b  jmp     loc_18005016E
0x180050090  mov     ebp, r8d
0x180050093  jmp     loc_18005016E
0x180050098  mov     eax, r8d
0x18005009b  sub     rsi, rax
0x18005009e  jmp     loc_18005016E
0x1800500a3  mov     [rsp+98h+var_78], r8d
0x1800500a8  jmp     loc_18005016E
0x1800500ad  mov     edx, ecx
0x1800500af  sub     edx, 0Ah
0x1800500b2  jz      short loc_180050125
0x1800500b4  sub     edx, 1
0x1800500b7  jz      short loc_180050125
0x1800500b9  sub     edx, 1
0x1800500bc  jz      short loc_180050125
0x1800500be  sub     edx, 1
0x1800500c1  jz      short loc_180050125
0x1800500c3  sub     edx, 1
0x1800500c6  jz      short loc_180050125
0x1800500c8  cmp     edx, 1
0x1800500cb  jnz     loc_180050177
0x1800500d1  lea     r14d, [rdx+2]
0x1800500d5  lea     eax, [r8+r8]
0x1800500d9  mov     ecx, r14d
0x1800500dc  cmp     eax, r14d
0x1800500df  mov     edx, r14d
0x1800500e2  cmovb   edx, eax
0x1800500e5  lea     eax, ds:1[r8*2]
0x1800500ed  cmp     eax, r14d
0x1800500f0  lea     r8, cs:180000000h
0x1800500f7  cmovb   ecx, eax
0x1800500fa  shr     r9d, 8
0x1800500fe  mov     r14, ds:rva qword_1800C0538[r8+rdx*8]
0x180050106  xor     edx, edx
0x180050108  mov     eax, ecx
0x18005010a  movzx   r15d, r9b
0x18005010e  mov     rcx, ds:rva off_1800B7CD8[r8+rcx*8]; "ss" ...
0x180050116  mov     [rsp+98h+Source], rcx
0x18005011b  mov     r12, ds:rva qword_1800C0538[r8+rax*8]
0x180050123  jmp     short loc_18005016E
0x180050125  sub     ecx, 0Ah
0x180050128  jz      short loc_180050160
0x18005012a  sub     ecx, 1
0x18005012d  jz      short loc_180050159
0x18005012f  sub     ecx, 1
0x180050132  jz      short loc_180050152
0x180050134  sub     ecx, 1
0x180050137  jz      short loc_18005014B
0x180050139  xor     edx, edx
0x18005013b  cmp     ecx, 1
0x18005013e  jz      short loc_180050144
0x180050140  mov     eax, edx
0x180050142  jmp     short loc_180050167
0x180050144  mov     eax, 7Eh ; '~'
0x180050149  jmp     short loc_180050167
0x18005014b  mov     eax, 5Eh ; '^'
0x180050150  jmp     short loc_180050165
0x180050152  mov     eax, 0A8h
0x180050157  jmp     short loc_180050165
0x180050159  mov     eax, 60h ; '`'
0x18005015e  jmp     short loc_180050165
0x180050160  mov     eax, 0B4h
0x180050165  xor     edx, edx
0x180050167  movzx   r13d, ax
0x18005016b  mov     ebx, r8d
0x18005016e  shr     r9d, 8
0x180050172  jmp     loc_18004FFED
0x180050177  mov     r9, [rsp+98h+arg_10]; unsigned __int64
0x18005017f  mov     r8, r11; unsigned __int16 *
0x180050182  mov     rdx, [rsp+98h+arg_20]; unsigned __int64
0x18005018a  mov     rcx, rdi; unsigned __int16 *
0x18005018d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180050192  mov     ecx, eax; int
0x180050194  call    ?ThrowIfFailed@@YAXJ@Z; ThrowIfFailed(long)
0x180050199  jmp     loc_1800502ED
0x18005019e  movsxd  rax, ebp
0x1800501a1  mov     rbp, [rsp+98h+arg_20]
0x1800501a9  lea     r8, [r11+rax*2]; unsigned __int16 *
0x1800501ad  test    r10w, r10w
0x1800501b1  jz      short loc_1800501C1
0x1800501b3  mov     [rdi], r10w
0x1800501b7  lea     rcx, [rdi+2]
0x1800501bb  lea     rdx, [rbp-1]
0x1800501bf  jmp     short loc_1800501C7
0x1800501c1  mov     rcx, rdi; unsigned __int16 *
0x1800501c4  mov     rdx, rbp; unsigned __int64
0x1800501c7  mov     r9, rsi; unsigned __int64
0x1800501ca  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800501cf  mov     ecx, eax; int
0x1800501d1  call    ?ThrowIfFailed@@YAXJ@Z; ThrowIfFailed(long)
0x1800501d6  xor     r10d, r10d
0x1800501d9  cmp     word ptr [rsp+98h+arg_0], r10w
0x1800501e2  jz      short loc_1800501F3
0x1800501e4  mov     eax, [rsp+98h+arg_0]
0x1800501eb  mov     [rdi+rsi*2+2], r10w
0x1800501f1  jmp     short loc_1800501F6
0x1800501f3  mov     eax, r10d
0x1800501f6  mov     [rdi+rsi*2], ax
0x1800501fa  test    r13w, r13w
0x1800501fe  jz      short loc_180050221
0x180050200  movsxd  r9, ebx
0x180050203  movzx   ecx, word ptr [rdi+r9*2]; unsigned __int16
0x180050208  call    ?ExpandAccent@LexEntryData@LSP@@SAKG@Z; LSP::LexEntryData::ExpandAccent(ushort)
0x18005020d  shr     eax, 10h
0x180050210  movzx   edx, r13w; unsigned __int16
0x180050214  movzx   ecx, ax; unsigned __int16
0x180050217  call    ?AddAccentTo@LexEntryData@LSP@@SAGGG@Z; LSP::LexEntryData::AddAccentTo(ushort,ushort)
0x18005021c  mov     [rdi+r9*2], ax
0x180050221  movsxd  rax, [rsp+98h+var_78]
0x180050226  test    eax, eax
0x180050228  js      short loc_18005023E
0x18005022a  movzx   ecx, word ptr [rdi+rax*2]; unsigned __int16
0x18005022e  mov     r8, rax
0x180050231  call    ?ExpandAccent@LexEntryData@LSP@@SAKG@Z; LSP::LexEntryData::ExpandAccent(ushort)
0x180050236  shr     eax, 10h
0x180050239  mov     [rdi+r8*2], ax
0x18005023e  movsxd  rax, [rsp+98h+var_74]
0x180050243  test    eax, eax
0x180050245  js      short loc_18005025A
0x180050247  movzx   ecx, word ptr [rdi+rax*2]
0x18005024b  mov     rbx, rax
0x18005024e  call    CMN_CharUpperW
0x180050253  mov     [rdi+rbx*2], ax
0x180050257  xor     r10d, r10d
0x18005025a  movsxd  rax, [rsp+98h+var_70]
0x18005025f  test    eax, eax
0x180050261  js      short loc_180050276
0x180050263  movzx   ecx, word ptr [rdi+rax*2]
0x180050267  mov     rbx, rax
0x18005026a  call    CMN_CharLowerW
0x18005026f  mov     [rdi+rbx*2], ax
0x180050273  xor     r10d, r10d
0x180050276  test    r15d, r15d
0x180050279  js      short loc_1800502ED
0x18005027b  sub     r14d, r12d
0x18005027e  jns     short loc_1800502A2
0x180050280  lea     edx, [r12+r15]
0x180050284  sub     esi, r14d
0x180050287  jmp     short loc_18005029C
0x180050289  lea     eax, [rsi+r14]
0x18005028d  movsxd  rcx, esi
0x180050290  cdqe
0x180050292  dec     esi
0x180050294  movzx   eax, word ptr [rdi+rax*2]
0x180050298  mov     [rdi+rcx*2], ax
0x18005029c  cmp     esi, edx
0x18005029e  jge     short loc_180050289
0x1800502a0  jmp     short loc_1800502CA
0x1800502a2  test    r14d, r14d
0x1800502a5  jle     short loc_1800502CA
0x1800502a7  lea     edx, [r12+r15]
0x1800502ab  jmp     short loc_1800502C0
0x1800502ad  lea     eax, [rdx+r14]
0x1800502b1  movsxd  rcx, edx
0x1800502b4  cdqe
0x1800502b6  inc     edx
0x1800502b8  movzx   eax, word ptr [rdi+rax*2]
0x1800502bc  mov     [rdi+rcx*2], ax
0x1800502c0  movsxd  rax, edx
0x1800502c3  cmp     [rdi+rax*2], r10w
0x1800502c8  jnz     short loc_1800502AD
0x1800502ca  mov     r8, [rsp+98h+Source]; Source
0x1800502cf  movsxd  rax, r15d
0x1800502d2  sub     rbp, rax
0x1800502d5  movsxd  r9, r12d
0x1800502d8  add     r9, r9; SourceSize
0x1800502db  lea     rcx, [rdi+rax*2]; Destination
0x1800502df  lea     rdx, ds:0[rbp*2]; DestinationSize
0x1800502e7  call    cs:__imp_memcpy_s
0x1800502ed  mov     rbx, [rsp+98h+arg_8]
0x1800502f5  mov     rax, rdi
0x1800502f8  add     rsp, 60h
0x1800502fc  pop     r15
0x1800502fe  pop     r14
0x180050300  pop     r13
0x180050302  pop     r12
0x180050304  pop     rdi
0x180050305  pop     rsi
0x180050306  pop     rbp
0x180050307  retn
```
