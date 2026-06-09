# CSingleSideReducer::SetAttribute(uint,unsigned __int64)

- ea: `0x1004373d0`
- end: `0x1004376f7`
- name: `?SetAttribute@CSingleSideReducer@@UEAAJI_K@Z`
- size: `807`
- prototype: `__int64 __fastcall(CSingleSideReducer *__hidden this, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x100426ab0`
- `0x1004373d0`
- `0x100439420`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004375cd`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1004375cd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437685`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004376bc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437685`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004376bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSingleSideReducer::SetAttribute(CSingleSideReducer *this, unsigned int a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v7; // rsi
  int v8; // eax
  char *v9; // rdi
  int v10; // ebx
  int v11; // eax
  __int128 *v12; // rax
  int v13; // eax
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  _QWORD v18[2]; // [rsp+38h] [rbp-19h] BYREF
  __int128 v19; // [rsp+48h] [rbp-9h]
  __int128 v20; // [rsp+58h] [rbp+7h] BYREF
  __int128 v21; // [rsp+68h] [rbp+17h]
  void *v22[2]; // [rsp+78h] [rbp+27h]
  void *Block; // [rsp+88h] [rbp+37h]
  __int128 *v24; // [rsp+B8h] [rbp+67h] BYREF
  unsigned __int64 v25; // [rsp+D0h] [rbp+7Fh] BYREF

  v18[1] = -2;
  result = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 8LL))((char *)this + 48);
  if ( (int)result < 0 )
  {
    _mm_lfence();
    return result;
  }
  if ( a2 == 3 )
    return 2147500037LL;
  if ( a2 != 4 )
  {
    _mm_lfence();
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 5) + 8LL))(
             *((_QWORD *)this + 5),
             a2,
             a3);
  }
  v19 = 0;
  v21 = 0;
  *(_OWORD *)v22 = 0;
  Block = 0;
  LOBYTE(v19) = 0;
  *(_QWORD *)((char *)&v19 + 4) = 0;
  v24 = &v20;
  v20 = 0u;
  v7 = 1024;
  if ( g_SOSHost )
  {
    if ( (*(int (__fastcall **)(_QWORD, unsigned __int64 *))(*g_SOSClerk + 80LL))(g_SOSClerk, &v25) < 0 )
    {
      if ( g_SOSHost )
        MEMORY[0] = 0;
      else
        (*(void (__fastcall **)(_QWORD, __int64, const char *, const char *, int, _QWORD))(MEMORY[0] + 528LL))(
          0,
          1,
          "SUCCEEDED(hr)",
          "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
          77,
          0);
    }
    v8 = 1024;
    if ( v25 < 0x400 )
      v8 = v25;
  }
  else
  {
    v8 = 4096;
  }
  DWORD1(v21) = v8 / 0x38uLL;
  LODWORD(v21) = 0;
  v22[0] = 0;
  *((_QWORD *)&v21 + 1) = 0;
  Block = 0;
  v22[1] = 0;
  v9 = (char *)this + 128;
  v10 = 0;
  v11 = *((_DWORD *)v9 + 4);
  if ( !v11 && !*((_DWORD *)v9 + 1) || v11 == *((_DWORD *)v9 + 5) )
  {
    if ( g_SOSHost )
    {
      if ( (*(int (__fastcall **)(_QWORD, _QWORD *))(*g_SOSClerk + 80LL))(g_SOSClerk, v18) < 0 )
      {
        if ( g_SOSHost )
          MEMORY[0] = 0;
        else
          (*(void (__fastcall **)(_QWORD, __int64, const char *, const char *, int, _QWORD))(MEMORY[0] + 528LL))(
            0,
            1,
            "SUCCEEDED(hr)",
            "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
            77,
            0);
      }
      if ( v18[0] < 0x400u )
        v7 = v18[0];
      v10 = -2147024882;
      v12 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                          g_SOSMemObj,
                          v7,
                          "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
                          98);
    }
    else
    {
      v12 = (__int128 *)malloc(0x1000u);
      v10 = -2147024882;
    }
    if ( v12 )
      v10 = 0;
    v24 = v12;
    if ( v10 < 0 )
      goto LABEL_34;
    _mm_lfence();
    v10 = CAutoArray<CGeodeticScannerConstruction::CSegment *,0,SOS_Or_CRT_Allocator<CGeodeticScannerConstruction::CSegment *>>::Add(
            v9,
            &v24);
    if ( v10 < 0 )
      goto LABEL_34;
    *((_DWORD *)v9 + 4) = 0;
  }
  ++*((_DWORD *)v9 + 4);
  _mm_lfence();
  v13 = *((_DWORD *)v9 + 1);
  v14 = v13 - 1;
  if ( !v13 )
    v14 = 0;
  v15 = (unsigned int)(*((_DWORD *)v9 + 5) * v14 + *((_DWORD *)v9 + 4) - 1) / *((_DWORD *)v9 + 5);
  v16 = 9LL * ((unsigned int)(*((_DWORD *)v9 + 5) * v14 + *((_DWORD *)v9 + 4) - 1) % *((_DWORD *)v9 + 5));
  v17 = *(_QWORD *)(*((_QWORD *)v9 + 1) + 8 * v15);
  *(_OWORD *)(v17 + 8 * v16) = v19;
  *(_OWORD *)(v17 + 8 * v16 + 16) = v20;
  *(_OWORD *)(v17 + 8 * v16 + 32) = v21;
  *(_OWORD *)(v17 + 8 * v16 + 48) = *(_OWORD *)v22;
  *(_QWORD *)(v17 + 8 * v16 + 64) = Block;
LABEL_34:
  if ( g_SOSHost )
  {
    if ( Block )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(Block);
  }
  Block = 0;
  v22[1] = 0;
  if ( g_SOSHost )
  {
    if ( v22[0] )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v22[0]);
  }
  v22[0] = 0;
  *((_QWORD *)&v21 + 1) = 0;
  ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(&v20);
  _mm_lfence();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1004373d0  mov     rax, rsp
0x1004373d3  push    rbp
0x1004373d4  push    rdi
0x1004373d5  push    r14
0x1004373d7  lea     rbp, [rax-5Fh]
0x1004373db  sub     rsp, 90h
0x1004373e2  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x1004373ea  mov     [rax+10h], rbx
0x1004373ee  mov     [rax+18h], rsi
0x1004373f2  mov     rsi, r8
0x1004373f5  mov     ebx, edx
0x1004373f7  mov     rdi, rcx
0x1004373fa  add     rcx, 30h ; '0'
0x1004373fe  mov     rax, [rcx]
0x100437401  call    qword ptr [rax+8]
0x100437404  test    eax, eax
0x100437406  jns     short loc_100437410
0x100437408  lfence
0x10043740b  jmp     loc_1004376DF
0x100437410  mov     eax, ebx
0x100437412  sub     eax, 3
0x100437415  jz      loc_1004376DA
0x10043741b  cmp     eax, 1
0x10043741e  jz      short loc_100437437
0x100437420  lfence
0x100437423  mov     rcx, [rdi+28h]
0x100437427  mov     rax, [rcx]
0x10043742a  mov     r8, rsi
0x10043742d  mov     edx, ebx
0x10043742f  call    qword ptr [rax+8]
0x100437432  jmp     loc_1004376DF
0x100437437  xorps   xmm0, xmm0
0x10043743a  xor     eax, eax
0x10043743c  movups  [rbp+57h+var_60], xmm0
0x100437440  movups  [rbp+57h+var_50], xmm0
0x100437444  movups  [rbp+57h+var_40], xmm0
0x100437448  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x10043744c  mov     [rbp+57h+Block], rax
0x100437450  mov     byte ptr [rbp+57h+var_60], al
0x100437453  xor     r14d, r14d
0x100437456  mov     qword ptr [rbp+57h+var_60+4], r14
0x10043745a  lea     rax, [rbp+57h+var_50]
0x10043745e  mov     [rbp+57h+arg_0], rax
0x100437462  mov     qword ptr [rbp+57h+var_50+8], r14
0x100437466  mov     qword ptr [rbp+57h+var_50], r14
0x10043746a  mov     esi, 400h
0x10043746f  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r14; SOS_AutoHost g_SOSHost
0x100437476  jz      short loc_1004374E1
0x100437478  mov     rcx, cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A; SOS_AutoMemClerk g_SOSClerk
0x10043747f  mov     rax, [rcx]
0x100437482  lea     rdx, [rbp+57h+arg_18]
0x100437486  call    qword ptr [rax+50h]
0x100437489  test    eax, eax
0x10043748b  jns     short loc_1004374D0
0x10043748d  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r14; SOS_AutoHost g_SOSHost
0x100437494  jz      short loc_1004374A0
0x100437496  mov     ds:0, r14d
0x10043749e  jmp     short loc_1004374D0
0x1004374a0  mov     rax, ds:0
0x1004374a8  mov     [rsp+0A0h+var_78], r14
0x1004374ad  mov     dword ptr [rsp+0A0h+var_80], 4Dh ; 'M'
0x1004374b5  lea     r9, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x1004374bc  lea     r8, aSucceededHr; "SUCCEEDED(hr)"
0x1004374c3  mov     edx, 1
0x1004374c8  xor     ecx, ecx
0x1004374ca  call    qword ptr [rax+210h]
0x1004374d0  mov     rax, rsi
0x1004374d3  mov     rcx, [rbp+57h+arg_18]
0x1004374d7  cmp     rcx, rsi
0x1004374da  jnb     short loc_1004374E6
0x1004374dc  mov     rax, rcx
0x1004374df  jmp     short loc_1004374E6
0x1004374e1  mov     eax, 1000h
0x1004374e6  movsxd  rcx, eax
0x1004374e9  mov     rax, 2492492492492493h
0x1004374f3  mul     rcx
0x1004374f6  sub     rcx, rdx
0x1004374f9  shr     rcx, 1
0x1004374fc  add     rcx, rdx
0x1004374ff  shr     rcx, 5
0x100437503  mov     dword ptr [rbp+57h+var_40+4], ecx
0x100437506  mov     dword ptr [rbp+57h+var_40], r14d
0x10043750a  mov     [rbp+57h+var_30], r14
0x10043750e  mov     qword ptr [rbp+57h+var_40+8], r14
0x100437512  mov     [rbp+57h+Block], r14
0x100437516  mov     [rbp+57h+var_30+8], r14
0x10043751a  sub     rdi, 0FFFFFFFFFFFFFF80h
0x10043751e  mov     ebx, r14d
0x100437521  mov     eax, [rdi+10h]
0x100437524  test    eax, eax
0x100437526  jnz     short loc_10043752D
0x100437528  cmp     [rdi+4], ebx
0x10043752b  jz      short loc_100437536
0x10043752d  cmp     eax, [rdi+14h]
0x100437530  jnz     loc_100437600
0x100437536  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rbx; SOS_AutoHost g_SOSHost
0x10043753d  jz      loc_1004375C8
0x100437543  mov     rcx, cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A; SOS_AutoMemClerk g_SOSClerk
0x10043754a  mov     rax, [rcx]
0x10043754d  lea     rdx, [rbp+57h+var_70]
0x100437551  call    qword ptr [rax+50h]
0x100437554  test    eax, eax
0x100437556  jns     short loc_10043759B
0x100437558  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rbx; SOS_AutoHost g_SOSHost
0x10043755f  jz      short loc_10043756B
0x100437561  mov     ds:0, r14d
0x100437569  jmp     short loc_10043759B
0x10043756b  mov     rax, ds:0
0x100437573  mov     [rsp+0A0h+var_78], r14
0x100437578  mov     dword ptr [rsp+0A0h+var_80], 4Dh ; 'M'
0x100437580  lea     r9, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100437587  lea     r8, aSucceededHr; "SUCCEEDED(hr)"
0x10043758e  mov     edx, 1
0x100437593  xor     ecx, ecx
0x100437595  call    qword ptr [rax+210h]
0x10043759b  cmp     [rbp+57h+var_70], rsi
0x10043759f  cmovb   rsi, [rbp+57h+var_70]
0x1004375a4  mov     ebx, 8007000Eh
0x1004375a9  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004375b0  mov     rax, [rcx]
0x1004375b3  mov     r9d, 62h ; 'b'
0x1004375b9  lea     r8, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x1004375c0  mov     rdx, rsi
0x1004375c3  call    qword ptr [rax+78h]
0x1004375c6  jmp     short loc_1004375D8
0x1004375c8  mov     ecx, 1000h; Size
0x1004375cd  call    cs:__imp_malloc
0x1004375d3  mov     ebx, 8007000Eh
0x1004375d8  test    rax, rax
0x1004375db  cmovnz  ebx, r14d
0x1004375df  mov     [rbp+57h+arg_0], rax
0x1004375e3  test    ebx, ebx
0x1004375e5  js      short loc_10043765C
0x1004375e7  lfence
0x1004375ea  lea     rdx, [rbp+57h+arg_0]
0x1004375ee  mov     rcx, rdi
0x1004375f1  call    ?Add@?$CAutoArray@PEAVCSegment@CGeodeticScannerConstruction@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCSegment@CGeodeticScannerConstruction@@@@@@QEAAJAEBQEAVCSegment@CGeodeticScannerConstruction@@@Z; CAutoArray<CGeodeticScannerConstruction::CSegment *,0,SOS_Or_CRT_Allocator<CGeodeticScannerConstruction::CSegment *>>::Add(CGeodeticScannerConstruction::CSegment * const &)
0x1004375f6  mov     ebx, eax
0x1004375f8  test    eax, eax
0x1004375fa  js      short loc_10043765C
0x1004375fc  mov     [rdi+10h], r14d
0x100437600  inc     dword ptr [rdi+10h]
0x100437603  lfence
0x100437606  mov     eax, [rdi+4]
0x100437609  lea     ecx, [rax-1]
0x10043760c  test    eax, eax
0x10043760e  cmovz   ecx, r14d
0x100437612  imul    ecx, [rdi+14h]
0x100437616  mov     eax, [rdi+10h]
0x100437619  dec     eax
0x10043761b  add     eax, ecx
0x10043761d  xor     edx, edx
0x10043761f  div     dword ptr [rdi+14h]
0x100437622  mov     r8, [rdi+8]
0x100437626  lea     rcx, [rdx+rdx*8]
0x10043762a  mov     rax, [r8+rax*8]
0x10043762e  movups  xmm0, [rbp+57h+var_60]
0x100437632  movups  xmmword ptr [rax+rcx*8], xmm0
0x100437636  movups  xmm1, [rbp+57h+var_50]
0x10043763a  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x10043763f  movups  xmm0, [rbp+57h+var_40]
0x100437643  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x100437648  movups  xmm1, xmmword ptr [rbp+57h+var_30]
0x10043764c  movups  xmmword ptr [rax+rcx*8+30h], xmm1
0x100437651  movsd   xmm0, [rbp+57h+Block]
0x100437656  movsd   qword ptr [rax+rcx*8+40h], xmm0
0x10043765c  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x100437664  jz      short loc_100437681
0x100437666  mov     rdx, [rbp+57h+Block]
0x10043766a  test    rdx, rdx
0x10043766d  jz      short loc_10043768B
0x10043766f  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100437676  mov     rax, [rcx]
0x100437679  call    qword ptr [rax+80h]
0x10043767f  jmp     short loc_10043768B
0x100437681  mov     rcx, [rbp+57h+Block]; Block
0x100437685  call    cs:__imp_free
0x10043768b  mov     [rbp+57h+Block], r14
0x10043768f  mov     [rbp+57h+var_30+8], r14
0x100437693  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10043769b  jz      short loc_1004376B8
0x10043769d  mov     rdx, [rbp+57h+var_30]
0x1004376a1  test    rdx, rdx
0x1004376a4  jz      short loc_1004376C2
0x1004376a6  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004376ad  mov     rax, [rcx]
0x1004376b0  call    qword ptr [rax+80h]
0x1004376b6  jmp     short loc_1004376C2
0x1004376b8  mov     rcx, [rbp+57h+var_30]; Block
0x1004376bc  call    cs:__imp_free
0x1004376c2  mov     [rbp+57h+var_30], r14
0x1004376c6  mov     qword ptr [rbp+57h+var_40+8], r14
0x1004376ca  lea     rcx, [rbp+57h+var_50]
0x1004376ce  call    ??1?$ArrayOverPages@UShapeData@CSingleSideReducer@@V?$Default_Allocator@UShapeData@CSingleSideReducer@@@@@@QEAA@XZ; ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(void)
0x1004376d3  lfence
0x1004376d6  mov     eax, ebx
0x1004376d8  jmp     short loc_1004376DF
0x1004376da  mov     eax, 80004005h
0x1004376df  lea     r11, [rsp+0A0h+var_10]
0x1004376e7  mov     rbx, [r11+28h]
0x1004376eb  mov     rsi, [r11+30h]
0x1004376ef  mov     rsp, r11
0x1004376f2  pop     r14
0x1004376f4  pop     rdi
0x1004376f5  pop     rbp
0x1004376f6  retn
```
