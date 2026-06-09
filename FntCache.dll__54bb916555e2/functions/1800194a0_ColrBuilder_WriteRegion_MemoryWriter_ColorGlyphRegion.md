# ColrBuilder::WriteRegion(MemoryWriter<ColorGlyphRegion> &)

- ea: `0x1800194a0`
- end: `0x180019822`
- name: `?WriteRegion@ColrBuilder@@QEBAXAEAV?$MemoryWriter@VColorGlyphRegion@@@@@Z`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800165f8`

## callees

- `0x180016f0c`
- `0x18001872c`
- `0x1800194a0`
- `0x1800217ac`
- `0x18004d664`
- `0x18004d720`
- `0x18004de6c`
- `0x18004f1c8`
- `0x18004f93c`
- `0x18009f1ec`
- `0x1800a2180`
- `0x1800ab0aa`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800197eb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800197eb`

## pseudocode

```c
void __fastcall ColrBuilder::WriteRegion(__int64 a1, unsigned int *a2)
{
  const char *v4; // rdx
  __int64 v5; // r9
  int v6; // eax
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  int v9; // ebx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // r9
  struct FontCmapBuilder::Impl *Impl; // rax
  unsigned int v13; // eax
  __int64 v14; // r9
  unsigned int v15; // eax
  __int64 v16; // r9
  unsigned __int64 v17; // r14
  unsigned int v18; // eax
  unsigned __int64 v19; // rdx
  _OWORD *v20; // r10
  unsigned int *v21; // r11
  __int64 v22; // r9
  __int64 v23; // r14
  unsigned __int16 i; // r8
  unsigned __int16 v25; // cx
  unsigned __int16 j; // r9
  unsigned __int16 v27; // r8
  unsigned __int16 v28; // r10
  _OWORD *v29; // rcx
  unsigned int v30; // eax
  __int128 v31; // xmm1
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // [rsp+30h] [rbp-39h] BYREF
  int v36; // [rsp+38h] [rbp-31h]
  __int64 v37; // [rsp+40h] [rbp-29h] BYREF
  int v38; // [rsp+48h] [rbp-21h]
  unsigned int v39; // [rsp+50h] [rbp-19h]
  __int128 v40; // [rsp+58h] [rbp-11h]
  __int128 v41; // [rsp+68h] [rbp-1h]
  int v42; // [rsp+E0h] [rbp+77h] BYREF

  MemoryWriterImpl::WriteAligned((MemoryWriterImpl *)a2, 0, 0x24u, 4u);
  v4 = *(const char **)(a1 + 96);
  *(_QWORD *)&v40 = *(_QWORD *)(a1 + 80);
  WORD4(v40) = *(_WORD *)(a1 + 88);
  v5 = (unsigned __int16)((__int64)(*(_QWORD *)(a1 + 104) - (_QWORD)v4) >> 1);
  HIDWORD(v40) = *(unsigned __int16 *)(a1 + 90);
  WORD5(v40) = v5;
  v6 = MemoryWriterImpl::WriteAlignedCount((unsigned __int64)a2, v4, 2u, v5, 2u);
  v8 = *(unsigned int *)(a1 + 92);
  v9 = v6;
  v10 = *(_QWORD *)(a1 + 48);
  if ( v8 > v10 || (v11 = *(unsigned __int16 *)(a1 + 90), (v10 - v8) >> 2 < v11) )
    FailAsExceptionPolicy<FileFormatException>::OnOutOfRange(v8, v7);
  HIDWORD(v41) = MemoryWriterImpl::WriteAlignedCount(
                   (unsigned __int64)a2,
                   (const char *)(v8 + *(_QWORD *)(a1 + 40)),
                   4u,
                   v11,
                   1u);
  MemoryWriterImpl::BeginInnerRegionImpl(a2, &v35, 4);
  v37 = v35;
  v38 = v36;
  v39 = 0;
  Impl = FontCmapBuilder::GetImpl((FontCmapBuilder *)(a1 + 136));
  CmapRegionBuilder<CmapRegion>::WriteRegion(Impl, &v37);
  v13 = MemoryWriterImpl::EndInnerRegionImpl((MemoryWriterImpl *)a2, v39, 4u);
  v14 = *(unsigned __int16 *)(a1 + 84);
  LODWORD(v41) = v13;
  v15 = MemoryWriterImpl::WriteAlignedCount((unsigned __int64)a2, 0, 4u, v14, 2u);
  v16 = *(unsigned __int16 *)(a1 + 86);
  v17 = v15;
  DWORD1(v41) = v15;
  v18 = MemoryWriterImpl::WriteAlignedCount((unsigned __int64)a2, 0, 4u, v16, 2u);
  v20 = *(_OWORD **)a2;
  v21 = a2 + 2;
  DWORD2(v41) = v18;
  if ( v20 )
  {
    v19 = *v21;
    if ( v18 > v19 || ((unsigned int)v19 - (unsigned __int64)v18) >> 2 < *(unsigned __int16 *)(a1 + 86) )
    {
      FailAssert(0xD4u, (const char *)v19);
      JUMPOUT(0x180019821LL);
    }
    v22 = (__int64)v20 + v18;
    if ( (((_BYTE)v18 + (_BYTE)v20) & 1) != 0 )
    {
      FailAssert(0xD4u, (const char *)v19);
      __debugbreak();
    }
    if ( v17 > v19 || (v19 = (v19 - v17) >> 2, v19 < *(unsigned __int16 *)(a1 + 84)) )
    {
      FailAssert(0xD4u, (const char *)v19);
      __debugbreak();
    }
    v23 = (__int64)v20 + v17;
    if ( (v23 & 1) != 0 )
    {
      FailAssert(0xD4u, (const char *)v19);
      __debugbreak();
    }
    for ( i = 0; i < *(_WORD *)(a1 + 86); ++i )
    {
      v19 = i;
      *(_WORD *)(v22 + 4LL * i) = _byteswap_ushort(*(_WORD *)(*(_QWORD *)(a1 + 128) + 4LL * i));
      v25 = _byteswap_ushort(*(_WORD *)(*(_QWORD *)(a1 + 128) + 4LL * i + 2));
      *(_WORD *)(v22 + 4LL * i + 2) = v25;
      if ( v25 >= *(_WORD *)(a1 + 88) && v25 != 0xFFFF )
      {
        Exception::Exception((Exception *)&v42, -2003283968, 0);
        LogAndThrow<FileFormatException>(&v42, 0x6C6274726C6F63LL, 240);
      }
    }
    for ( j = 0; j < *(_WORD *)(a1 + 84); ++j )
    {
      v19 = j;
      v27 = _byteswap_ushort(*(_WORD *)(*(_QWORD *)(a1 + 120) + 6LL * j + 2));
      *(_WORD *)(v23 + 4LL * j) = v27;
      v28 = _byteswap_ushort(*(_WORD *)(*(_QWORD *)(a1 + 120) + 6LL * j + 4));
      *(_WORD *)(v23 + 4LL * j + 2) = v28;
      if ( !v28 || v27 + (unsigned int)v28 > *(unsigned __int16 *)(a1 + 86) )
      {
        Exception::Exception((Exception *)&v42, -2003283968, 0);
        LogAndThrow<FileFormatException>(&v42, 0x6C6274726C6F63LL, 252);
      }
    }
  }
  v29 = *(_OWORD **)a2;
  if ( *(_QWORD *)a2 )
  {
    v30 = a2[4];
    if ( v30 < 0x24 )
    {
      FailAssert(0x7Au, (const char *)v19);
      __debugbreak();
    }
    if ( *v21 < v30 )
    {
      FailAssert(0x7Bu, (const char *)v19);
      __debugbreak();
    }
    if ( *v21 < 0x24 )
    {
      memset_0(v29, 0, *v21);
      *(_DWORD *)_o__errno(v33, v32, v34) = 34;
      invalid_parameter_noinfo();
    }
    else
    {
      v31 = v41;
      *v29 = v40;
      v29[1] = v31;
      *((_DWORD *)v29 + 8) = v9;
    }
  }
}

```

## disassembly

```asm
0x1800194a0  push    rbp
0x1800194a2  push    rbx
0x1800194a3  push    rsi
0x1800194a4  push    rdi
0x1800194a5  push    r12
0x1800194a7  push    r13
0x1800194a9  push    r14
0x1800194ab  push    r15
0x1800194ad  lea     rbp, [rsp-1Fh]
0x1800194b2  sub     rsp, 88h
0x1800194b9  mov     rsi, rdx
0x1800194bc  mov     r13d, 4
0x1800194c2  mov     rdi, rcx
0x1800194c5  mov     r9d, r13d; unsigned __int64
0x1800194c8  xor     edx, edx; void *
0x1800194ca  mov     rcx, rsi; this
0x1800194cd  lea     r8d, [r13+20h]; unsigned __int64
0x1800194d1  call    ?WriteAligned@MemoryWriterImpl@@IEAAIPEBX_K1@Z; MemoryWriterImpl::WriteAligned(void const *,unsigned __int64,unsigned __int64)
0x1800194d6  mov     eax, [rdi+50h]
0x1800194d9  lea     r12d, [r13-2]
0x1800194dd  mov     rdx, [rdi+60h]; void *
0x1800194e1  mov     r8d, r12d; unsigned __int64
0x1800194e4  mov     dword ptr [rbp+57h+var_68], eax
0x1800194e7  mov     rcx, rsi; this
0x1800194ea  movzx   eax, word ptr [rdi+54h]
0x1800194ee  mov     word ptr [rbp+57h+var_68+4], ax
0x1800194f2  movzx   eax, word ptr [rdi+56h]
0x1800194f6  mov     word ptr [rbp+57h+var_68+6], ax
0x1800194fa  movzx   eax, word ptr [rdi+58h]
0x1800194fe  mov     word ptr [rbp+57h+var_68+8], ax
0x180019502  mov     rax, [rdi+68h]
0x180019506  sub     rax, rdx
0x180019509  mov     [rsp+0C0h+var_A0], r12; unsigned __int64
0x18001950e  sar     rax, 1
0x180019511  movzx   r9d, ax; unsigned __int64
0x180019515  movzx   eax, word ptr [rdi+5Ah]
0x180019519  mov     dword ptr [rbp+57h+var_68+0Ch], eax
0x18001951c  mov     word ptr [rbp+57h+var_68+0Ah], r9w
0x180019521  call    ?WriteAlignedCount@MemoryWriterImpl@@IEAAIPEBX_K11@Z; MemoryWriterImpl::WriteAlignedCount(void const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180019526  mov     ecx, [rdi+5Ch]
0x180019529  mov     ebx, eax
0x18001952b  mov     rax, [rdi+30h]
0x18001952f  cmp     rcx, rax
0x180019532  ja      loc_18001978F
0x180019538  movzx   r9d, word ptr [rdi+5Ah]; unsigned __int64
0x18001953d  sub     rax, rcx
0x180019540  shr     rax, 2
0x180019544  cmp     rax, r9
0x180019547  jb      loc_18001978F
0x18001954d  mov     rdx, [rdi+28h]
0x180019551  lea     r15d, [r13-3]
0x180019555  add     rdx, rcx; void *
0x180019558  mov     [rsp+0C0h+var_A0], r15; unsigned __int64
0x18001955d  mov     rcx, rsi; this
0x180019560  mov     r8d, r13d; unsigned __int64
0x180019563  call    ?WriteAlignedCount@MemoryWriterImpl@@IEAAIPEBX_K11@Z; MemoryWriterImpl::WriteAlignedCount(void const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180019568  mov     r8d, r13d
0x18001956b  mov     dword ptr [rbp+57h+var_58+0Ch], eax
0x18001956e  lea     rdx, [rbp+57h+var_90]
0x180019572  mov     rcx, rsi
0x180019575  call    ?BeginInnerRegionImpl@MemoryWriterImpl@@IEAA?AVWriteableMemoryRegion@@I@Z; MemoryWriterImpl::BeginInnerRegionImpl(uint)
0x18001957a  mov     rax, [rbp+57h+var_90]
0x18001957e  lea     rcx, [rdi+88h]; this
0x180019585  mov     [rbp+57h+var_80], rax
0x180019589  mov     eax, [rbp+57h+var_88]
0x18001958c  mov     [rbp+57h+var_78], eax
0x18001958f  mov     [rbp+57h+var_70], 0
0x180019596  call    ?GetImpl@FontCmapBuilder@@AEBAAEAVImpl@1@XZ; FontCmapBuilder::GetImpl(void)
0x18001959b  lea     rdx, [rbp+57h+var_80]
0x18001959f  mov     rcx, rax
0x1800195a2  call    ?WriteRegion@?$CmapRegionBuilder@VCmapRegion@@@@QEBAXAEAV?$MemoryWriter@VCmapRegion@@@@@Z; CmapRegionBuilder<CmapRegion>::WriteRegion(MemoryWriter<CmapRegion> &)
0x1800195a7  mov     edx, [rbp+57h+var_70]; unsigned int
0x1800195aa  mov     r8d, r13d; unsigned int
0x1800195ad  mov     rcx, rsi; this
0x1800195b0  call    ?EndInnerRegionImpl@MemoryWriterImpl@@IEAAIII@Z; MemoryWriterImpl::EndInnerRegionImpl(uint,uint)
0x1800195b5  movzx   r9d, word ptr [rdi+54h]; unsigned __int64
0x1800195ba  mov     r8d, r13d; unsigned __int64
0x1800195bd  xor     edx, edx; void *
0x1800195bf  mov     dword ptr [rbp+57h+var_58], eax
0x1800195c2  mov     rcx, rsi; this
0x1800195c5  mov     [rsp+0C0h+var_A0], r12; unsigned __int64
0x1800195ca  call    ?WriteAlignedCount@MemoryWriterImpl@@IEAAIPEBX_K11@Z; MemoryWriterImpl::WriteAlignedCount(void const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x1800195cf  movzx   r9d, word ptr [rdi+56h]; unsigned __int64
0x1800195d4  mov     r8d, r13d; unsigned __int64
0x1800195d7  mov     r14d, eax
0x1800195da  xor     edx, edx; void *
0x1800195dc  mov     rcx, rsi; this
0x1800195df  mov     dword ptr [rbp+57h+var_58+4], r14d
0x1800195e3  mov     [rsp+0C0h+var_A0], r12; unsigned __int64
0x1800195e8  call    ?WriteAlignedCount@MemoryWriterImpl@@IEAAIPEBX_K11@Z; MemoryWriterImpl::WriteAlignedCount(void const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x1800195ed  mov     r10, [rsi]
0x1800195f0  lea     r11, [rsi+8]
0x1800195f4  mov     dword ptr [rbp+57h+var_58+8], eax
0x1800195f7  test    r10, r10
0x1800195fa  jz      loc_18001974A
0x180019600  mov     edx, [r11]; char *
0x180019603  mov     r8d, eax
0x180019606  cmp     r8, rdx
0x180019609  ja      loc_180019817
0x18001960f  movzx   eax, word ptr [rdi+56h]
0x180019613  mov     ecx, edx
0x180019615  sub     rcx, r8
0x180019618  shr     rcx, 2
0x18001961c  cmp     rcx, rax
0x18001961f  jb      loc_180019817
0x180019625  lea     r9, [r8+r10]
0x180019629  test    r15b, r9b
0x18001962c  jnz     loc_180019795
0x180019632  cmp     r14, rdx
0x180019635  ja      loc_18001980C
0x18001963b  movzx   eax, word ptr [rdi+54h]
0x18001963f  sub     rdx, r14
0x180019642  shr     rdx, 2; char *
0x180019646  cmp     rdx, rax
0x180019649  jb      loc_18001980C
0x18001964f  add     r14, r10
0x180019652  test    r15b, r14b
0x180019655  jnz     loc_1800197A0
0x18001965b  xor     r8d, r8d
0x18001965e  cmp     r8w, [rdi+56h]
0x180019663  jnb     short loc_1800196E4
0x180019665  mov     rax, [rdi+80h]
0x18001966c  movzx   edx, r8w
0x180019670  movzx   ecx, byte ptr [rax+rdx*4+1]
0x180019675  movzx   eax, byte ptr [rax+rdx*4]
0x180019679  shl     ax, 8
0x18001967d  or      cx, ax
0x180019680  mov     [r9+rdx*4], cx
0x180019685  mov     rax, [rdi+80h]
0x18001968c  movzx   ecx, byte ptr [rax+rdx*4+3]
0x180019691  movzx   eax, byte ptr [rax+rdx*4+2]
0x180019696  shl     ax, 8
0x18001969a  or      cx, ax
0x18001969d  mov     [r9+rdx*4+2], cx
0x1800196a3  cmp     cx, [rdi+58h]
0x1800196a7  jnb     short loc_1800196AF
0x1800196a9  add     r8w, r15w
0x1800196ad  jmp     short loc_18001965E
0x1800196af  mov     eax, 0FFFFh
0x1800196b4  cmp     cx, ax
0x1800196b7  jz      short loc_1800196A9
0x1800196b9  xor     r8d, r8d; unsigned int
0x1800196bc  lea     rcx, [rbp+57h+arg_10]; this
0x1800196c0  mov     edx, 88985000h; int
0x1800196c5  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800196ca  mov     rdx, 6C6274726C6F63h
0x1800196d4  lea     rcx, [rbp+57h+arg_10]
0x1800196d8  mov     r8d, 0F0h
0x1800196de  call    ??$LogAndThrow@VFileFormatException@@@@YAXAEBVFileFormatException@@VEventTag@@I@Z; LogAndThrow<FileFormatException>(FileFormatException const &,EventTag,uint)
0x1800196e4  xor     r9d, r9d
0x1800196e7  cmp     r9w, [rdi+54h]
0x1800196ec  jnb     short loc_18001974A
0x1800196ee  mov     rax, [rdi+78h]
0x1800196f2  movzx   edx, r9w
0x1800196f6  lea     rcx, [rdx+rdx*2]
0x1800196fa  movzx   r8d, byte ptr [rax+rcx*2+2]
0x180019700  movzx   eax, byte ptr [rax+rcx*2+3]
0x180019705  shl     r8w, 8
0x18001970a  or      r8w, ax
0x18001970e  mov     [r14+rdx*4], r8w
0x180019713  mov     rax, [rdi+78h]
0x180019717  movzx   r10d, byte ptr [rax+rcx*2+5]
0x18001971d  movzx   eax, byte ptr [rax+rcx*2+4]
0x180019722  shl     ax, 8
0x180019726  or      r10w, ax
0x18001972a  mov     [r14+rdx*4+2], r10w
0x180019730  jz      short loc_1800197AB
0x180019732  movzx   eax, r8w
0x180019736  movzx   ecx, r10w
0x18001973a  add     ecx, eax
0x18001973c  movzx   eax, word ptr [rdi+56h]
0x180019740  cmp     ecx, eax
0x180019742  ja      short loc_1800197AB
0x180019744  add     r9w, r15w
0x180019748  jmp     short loc_1800196E7
0x18001974a  mov     rcx, [rsi]; void *
0x18001974d  test    rcx, rcx
0x180019750  jz      short loc_18001977B
0x180019752  mov     eax, [rsi+10h]
0x180019755  cmp     eax, 24h ; '$'
0x180019758  jb      loc_180019801
0x18001975e  cmp     [r11], eax
0x180019761  jb      short loc_1800197D6
0x180019763  cmp     dword ptr [r11], 24h ; '$'
0x180019767  jb      short loc_1800197E1
0x180019769  movups  xmm0, [rbp+57h+var_68]
0x18001976d  movups  xmm1, [rbp+57h+var_58]
0x180019771  movups  xmmword ptr [rcx], xmm0
0x180019774  movups  xmmword ptr [rcx+10h], xmm1
0x180019778  mov     [rcx+20h], ebx
0x18001977b  add     rsp, 88h
0x180019782  pop     r15
0x180019784  pop     r14
0x180019786  pop     r13
0x180019788  pop     r12
0x18001978a  pop     rdi
0x18001978b  pop     rsi
0x18001978c  pop     rbx
0x18001978d  pop     rbp
0x18001978e  retn
0x18001978f  call    ?OnOutOfRange@?$FailAsExceptionPolicy@VFileFormatException@@@@SAXPEBX@Z; FailAsExceptionPolicy<FileFormatException>::OnOutOfRange(void const *)
0x180019795  mov     ecx, 0D4h; unsigned int
0x18001979a  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x18001979f  int     3; Trap to Debugger
0x1800197a0  mov     ecx, 0D4h; unsigned int
0x1800197a5  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x1800197aa  int     3; Trap to Debugger
0x1800197ab  xor     r8d, r8d; unsigned int
0x1800197ae  lea     rcx, [rbp+57h+arg_10]; this
0x1800197b2  mov     edx, 88985000h; int
0x1800197b7  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800197bc  mov     rdx, 6C6274726C6F63h
0x1800197c6  lea     rcx, [rbp+57h+arg_10]
0x1800197ca  mov     r8d, 0FCh
0x1800197d0  call    ??$LogAndThrow@VFileFormatException@@@@YAXAEBVFileFormatException@@VEventTag@@I@Z; LogAndThrow<FileFormatException>(FileFormatException const &,EventTag,uint)
0x1800197d6  mov     ecx, 7Bh ; '{'; unsigned int
0x1800197db  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x1800197e0  int     3; Trap to Debugger
0x1800197e1  mov     r8d, [r11]; Size
0x1800197e4  xor     edx, edx; Val
0x1800197e6  call    memset_0
0x1800197eb  call    cs:__imp__o__errno
0x1800197f1  mov     dword ptr [rax], 22h ; '"'
0x1800197f7  call    _invalid_parameter_noinfo
0x1800197fc  jmp     loc_18001977B
0x180019801  mov     ecx, 7Ah ; 'z'; unsigned int
0x180019806  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x18001980b  int     3; Trap to Debugger
0x18001980c  mov     ecx, 0D4h; unsigned int
0x180019811  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x180019816  int     3; Trap to Debugger
0x180019817  mov     ecx, 0D4h; unsigned int
0x18001981c  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
```
