# CSingleSideReducer::BeginFigure(bool,MglPoint<double> const *,unsigned __int64 const *)

- ea: `0x1004378d0`
- end: `0x100437c03`
- name: `?BeginFigure@CSingleSideReducer@@UEAAJ_NPEBU?$MglPoint@N@@PEB_K@Z`
- size: `819`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x100426ab0`
- `0x1004378d0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100437a5e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100437a5e`

## pseudocode

```c
__int64 __fastcall CSingleSideReducer::BeginFigure(__int64 a1, char a2, _QWORD *a3, _QWORD *a4)
{
  __int64 result; // rax
  int v9; // eax
  int v10; // edi
  __int64 v11; // rsi
  int v12; // eax
  __int64 v13; // rdx
  void *v14; // rax
  int v15; // eax
  bool v16; // zf
  __int128 v17; // xmm1
  int v18; // ecx
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rdx
  __int128 v22; // xmm0
  __int64 v23; // xmm1_8
  int v24; // eax
  unsigned int v25; // r8d
  __int64 v26; // xmm0_8
  __int64 v27; // rdx
  __int64 v28; // r9
  int v29; // eax
  int v30; // ecx
  int v31; // eax
  _QWORD *v32; // rdx
  unsigned __int64 v33; // [rsp+30h] [rbp-58h] BYREF
  __int128 v34; // [rsp+38h] [rbp-50h]
  __int128 v35; // [rsp+48h] [rbp-40h]
  __int128 v36; // [rsp+58h] [rbp-30h]
  __int64 v37; // [rsp+68h] [rbp-20h]
  void *v38; // [rsp+90h] [rbp+8h] BYREF

  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 48) + 32LL))(a1 + 48);
  if ( (int)result >= 0 )
  {
    *(_BYTE *)(a1 + 104) = a2;
    if ( !a2 )
    {
      if ( !*(_BYTE *)(a1 + 106) )
      {
        _mm_lfence();
        return (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *, _QWORD *))(**(_QWORD **)(a1 + 40) + 32LL))(
                 *(_QWORD *)(a1 + 40),
                 0,
                 a3,
                 a4);
      }
      goto LABEL_34;
    }
    _mm_lfence();
    v9 = 0;
    v37 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    if ( *(_DWORD *)(a1 + 132) )
    {
      _mm_lfence();
      v9 = *(_DWORD *)(a1 + 132) - 1;
    }
    v10 = 0;
    v11 = *(_QWORD *)(*(_QWORD *)(a1 + 136)
                    + 8LL
                    * ((unsigned int)(v9 * *(_DWORD *)(a1 + 148) + *(_DWORD *)(a1 + 144) - 1)
                     / *(_DWORD *)(a1 + 148)))
        + 72LL * ((unsigned int)(v9 * *(_DWORD *)(a1 + 148) + *(_DWORD *)(a1 + 144) - 1) % *(_DWORD *)(a1 + 148));
    v12 = *(_DWORD *)(v11 + 32);
    if ( !v12 && !*(_DWORD *)(v11 + 20) || v12 == *(_DWORD *)(v11 + 36) )
    {
      if ( g_SOSHost )
      {
        if ( (*(int (__fastcall **)(_QWORD, unsigned __int64 *))(*g_SOSClerk + 80LL))(g_SOSClerk, &v33) < 0 )
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
        v13 = 1024;
        v10 = -2147024882;
        if ( v33 < 0x400 )
          v13 = v33;
        v14 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64))(*g_SOSMemObj + 120LL))(
                        g_SOSMemObj,
                        v13,
                        "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
                        98);
      }
      else
      {
        v14 = malloc(0x1000u);
        v10 = -2147024882;
      }
      v38 = v14;
      if ( v14 )
        v10 = 0;
      if ( v10 < 0
        || (v10 = CAutoArray<CGeodeticScannerConstruction::CSegment *,0,SOS_Or_CRT_Allocator<CGeodeticScannerConstruction::CSegment *>>::Add(
                    v11 + 16,
                    &v38),
            v10 < 0) )
      {
        _mm_lfence();
        return (unsigned int)v10;
      }
      *(_DWORD *)(v11 + 32) = 0;
    }
    ++*(_DWORD *)(v11 + 32);
    _mm_lfence();
    v15 = *(_DWORD *)(v11 + 20);
    v16 = v15 == 0;
    v17 = v35;
    v18 = v15 - 1;
    v19 = *(_DWORD *)(v11 + 32);
    if ( v16 )
      v18 = 0;
    v20 = 56LL * ((unsigned int)(*(_DWORD *)(v11 + 36) * v18 - 1 + v19) % *(_DWORD *)(v11 + 36));
    v21 = *(_QWORD *)(*(_QWORD *)(v11 + 24)
                    + 8LL * ((unsigned int)(*(_DWORD *)(v11 + 36) * v18 - 1 + v19) / *(_DWORD *)(v11 + 36)));
    *(_OWORD *)(v21 + v20) = v34;
    v22 = v36;
    *(_OWORD *)(v21 + v20 + 16) = v17;
    v23 = v37;
    *(_OWORD *)(v21 + v20 + 32) = v22;
    *(_QWORD *)(v21 + v20 + 48) = v23;
    _mm_lfence();
    ++*(_DWORD *)(a1 + 152);
    v24 = 0;
    if ( *(_DWORD *)(a1 + 132) )
    {
      _mm_lfence();
      v24 = *(_DWORD *)(a1 + 132) - 1;
    }
    v25 = *(_DWORD *)(a1 + 148);
    v26 = a3[1];
    v27 = (v24 * v25 + *(_DWORD *)(a1 + 144) - 1) % v25;
    v28 = *(_QWORD *)(*(_QWORD *)(a1 + 136) + 8LL * ((v24 * v25 + *(_DWORD *)(a1 + 144) - 1) / v25));
    v29 = *(_DWORD *)(v28 + 72LL * (unsigned int)v27 + 20);
    v30 = v29 - 1;
    if ( !v29 )
      v30 = 0;
    v31 = *(_DWORD *)(v28 + 72LL * (unsigned int)v27 + 32);
    v32 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)(v28 + 72 * v27 + 24)
                               + 8LL
                               * ((unsigned int)(*(_DWORD *)(v28 + 72 * v27 + 36) * v30 - 1 + v31)
                                / *(_DWORD *)(v28 + 72 * v27 + 36)))
                   + 56LL
                   * ((unsigned int)(*(_DWORD *)(v28 + 72 * v27 + 36) * v30 - 1 + v31) % *(_DWORD *)(v28 + 72 * v27 + 36)));
    v32[1] = *a3;
    v32[2] = v26;
    v32[4] = *(_QWORD *)(a1 + 168) + 16LL * *(unsigned int *)(a1 + 156);
    if ( *(_BYTE *)(a1 + 16) )
    {
      v32[3] = *a4;
      v32[5] = *(_QWORD *)(a1 + 184) + 8LL * *(unsigned int *)(a1 + 156);
    }
    return (unsigned int)v10;
  }
LABEL_34:
  _mm_lfence();
  return result;
}

```

## disassembly

```asm
0x1004378d0  mov     [rsp+arg_18], rbx
0x1004378d5  push    rdi
0x1004378d6  push    r14
0x1004378d8  push    r15
0x1004378da  sub     rsp, 70h
0x1004378de  mov     rax, [rcx+30h]
0x1004378e2  mov     rbx, rcx
0x1004378e5  add     rcx, 30h ; '0'
0x1004378e9  mov     r14, r9
0x1004378ec  mov     r15, r8
0x1004378ef  movzx   edi, dl
0x1004378f2  call    qword ptr [rax+20h]
0x1004378f5  test    eax, eax
0x1004378f7  js      loc_100437BEE
0x1004378fd  mov     [rbx+68h], dil
0x100437901  test    dil, dil
0x100437904  jnz     short loc_100437937
0x100437906  cmp     [rbx+6Ah], dil
0x10043790a  jnz     loc_100437BEE
0x100437910  lfence
0x100437913  mov     rcx, [rbx+28h]
0x100437917  mov     r9, r14
0x10043791a  mov     r8, r15
0x10043791d  xor     edx, edx
0x10043791f  mov     rax, [rcx]
0x100437922  mov     rbx, [rsp+88h+arg_18]
0x10043792a  add     rsp, 70h
0x10043792e  pop     r15
0x100437930  pop     r14
0x100437932  pop     rdi
0x100437933  jmp     qword ptr [rax+20h]
0x100437937  mov     [rsp+88h+arg_8], rbp
0x10043793f  mov     [rsp+88h+arg_10], rsi
0x100437947  lfence
0x10043794a  xorps   xmm0, xmm0
0x10043794d  xor     eax, eax
0x10043794f  xor     ebp, ebp
0x100437951  mov     [rsp+88h+var_20], rax
0x100437956  movups  [rsp+88h+var_50], xmm0
0x10043795b  movups  [rsp+88h+var_40], xmm0
0x100437960  movups  [rsp+88h+var_30], xmm0
0x100437965  cmp     [rbx+84h], eax
0x10043796b  jbe     short loc_100437978
0x10043796d  lfence
0x100437970  mov     eax, [rbx+84h]
0x100437976  dec     eax
0x100437978  mov     r8d, [rbx+94h]
0x10043797f  xor     edx, edx
0x100437981  mov     ecx, r8d
0x100437984  mov     edi, ebp
0x100437986  imul    ecx, eax
0x100437989  mov     eax, [rbx+90h]
0x10043798f  dec     eax
0x100437991  add     eax, ecx
0x100437993  div     r8d
0x100437996  mov     ecx, edx
0x100437998  mov     edx, eax
0x10043799a  mov     rax, [rbx+88h]
0x1004379a1  lea     rcx, [rcx+rcx*8]
0x1004379a5  mov     rax, [rax+rdx*8]
0x1004379a9  lea     rsi, [rax+rcx*8]
0x1004379ad  mov     eax, [rax+rcx*8+20h]
0x1004379b1  test    eax, eax
0x1004379b3  jnz     short loc_1004379BA
0x1004379b5  cmp     [rsi+14h], ebp
0x1004379b8  jz      short loc_1004379C3
0x1004379ba  cmp     eax, [rsi+24h]
0x1004379bd  jnz     loc_100437A9D
0x1004379c3  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rdi; SOS_AutoHost g_SOSHost
0x1004379ca  jz      loc_100437A59
0x1004379d0  mov     rcx, cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A; SOS_AutoMemClerk g_SOSClerk
0x1004379d7  lea     rdx, [rsp+88h+var_58]
0x1004379dc  mov     rax, [rcx]
0x1004379df  call    qword ptr [rax+50h]
0x1004379e2  test    eax, eax
0x1004379e4  jns     short loc_100437A28
0x1004379e6  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rdi; SOS_AutoHost g_SOSHost
0x1004379ed  jz      short loc_1004379F8
0x1004379ef  mov     ds:0, ebp
0x1004379f6  jmp     short loc_100437A28
0x1004379f8  mov     rax, ds:0
0x100437a00  lea     r9, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100437a07  mov     [rsp+88h+var_60], rbp
0x100437a0c  lea     r8, aSucceededHr; "SUCCEEDED(hr)"
0x100437a13  mov     edx, 1
0x100437a18  mov     [rsp+88h+var_68], 4Dh ; 'M'
0x100437a20  xor     ecx, ecx
0x100437a22  call    qword ptr [rax+210h]
0x100437a28  mov     edx, 400h
0x100437a2d  mov     edi, 8007000Eh
0x100437a32  cmp     [rsp+88h+var_58], rdx
0x100437a37  cmovb   rdx, [rsp+88h+var_58]
0x100437a3d  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100437a44  lea     r8, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x100437a4b  mov     r9d, 62h ; 'b'
0x100437a51  mov     rax, [rcx]
0x100437a54  call    qword ptr [rax+78h]
0x100437a57  jmp     short loc_100437A69
0x100437a59  mov     ecx, 1000h; Size
0x100437a5e  call    cs:__imp_malloc
0x100437a64  mov     edi, 8007000Eh
0x100437a69  test    rax, rax
0x100437a6c  mov     [rsp+88h+arg_0], rax
0x100437a74  cmovnz  edi, ebp
0x100437a77  test    edi, edi
0x100437a79  js      loc_100437BE9
0x100437a7f  lea     rdx, [rsp+88h+arg_0]
0x100437a87  lea     rcx, [rsi+10h]
0x100437a8b  call    ?Add@?$CAutoArray@PEAVCSegment@CGeodeticScannerConstruction@@$0A@V?$SOS_Or_CRT_Allocator@PEAVCSegment@CGeodeticScannerConstruction@@@@@@QEAAJAEBQEAVCSegment@CGeodeticScannerConstruction@@@Z; CAutoArray<CGeodeticScannerConstruction::CSegment *,0,SOS_Or_CRT_Allocator<CGeodeticScannerConstruction::CSegment *>>::Add(CGeodeticScannerConstruction::CSegment * const &)
0x100437a90  mov     edi, eax
0x100437a92  test    eax, eax
0x100437a94  js      loc_100437BE9
0x100437a9a  mov     [rsi+20h], ebp
0x100437a9d  inc     dword ptr [rsi+20h]
0x100437aa0  lfence
0x100437aa3  mov     eax, [rsi+14h]
0x100437aa6  test    eax, eax
0x100437aa8  movups  xmm0, [rsp+88h+var_50]
0x100437aad  movups  xmm1, [rsp+88h+var_40]
0x100437ab2  lea     ecx, [rax-1]
0x100437ab5  mov     eax, [rsi+20h]
0x100437ab8  cmovz   ecx, ebp
0x100437abb  xor     edx, edx
0x100437abd  imul    ecx, [rsi+24h]
0x100437ac1  dec     ecx
0x100437ac3  add     eax, ecx
0x100437ac5  div     dword ptr [rsi+24h]
0x100437ac8  mov     r8d, edx
0x100437acb  imul    r9, r8, 38h ; '8'
0x100437acf  mov     ecx, eax
0x100437ad1  mov     rax, [rsi+18h]
0x100437ad5  mov     rdx, [rax+rcx*8]
0x100437ad9  movups  xmmword ptr [rdx+r9], xmm0
0x100437ade  movups  xmm0, [rsp+88h+var_30]
0x100437ae3  movups  xmmword ptr [rdx+r9+10h], xmm1
0x100437ae9  movsd   xmm1, [rsp+88h+var_20]
0x100437aef  movups  xmmword ptr [rdx+r9+20h], xmm0
0x100437af5  movsd   qword ptr [rdx+r9+30h], xmm1
0x100437afc  lfence
0x100437aff  inc     dword ptr [rbx+98h]
0x100437b05  mov     eax, ebp
0x100437b07  cmp     [rbx+84h], eax
0x100437b0d  jbe     short loc_100437B1A
0x100437b0f  lfence
0x100437b12  mov     eax, [rbx+84h]
0x100437b18  dec     eax
0x100437b1a  mov     r8d, [rbx+94h]
0x100437b21  xor     edx, edx
0x100437b23  movsd   xmm0, qword ptr [r15+8]
0x100437b29  mov     ecx, r8d
0x100437b2c  imul    ecx, eax
0x100437b2f  mov     eax, [rbx+90h]
0x100437b35  dec     eax
0x100437b37  add     eax, ecx
0x100437b39  div     r8d
0x100437b3c  mov     ecx, eax
0x100437b3e  mov     rax, [rbx+88h]
0x100437b45  lea     r10, [rdx+rdx*8]
0x100437b49  mov     r9, [rax+rcx*8]
0x100437b4d  mov     eax, [r9+r10*8+14h]
0x100437b52  test    eax, eax
0x100437b54  lea     ecx, [rax-1]
0x100437b57  mov     eax, [r9+r10*8+20h]
0x100437b5c  cmovz   ecx, ebp
0x100437b5f  xor     edx, edx
0x100437b61  imul    ecx, [r9+r10*8+24h]
0x100437b67  dec     ecx
0x100437b69  add     eax, ecx
0x100437b6b  div     dword ptr [r9+r10*8+24h]
0x100437b70  mov     ecx, eax
0x100437b72  mov     rax, [r9+r10*8+18h]
0x100437b77  mov     r8d, edx
0x100437b7a  imul    rdx, r8, 38h ; '8'
0x100437b7e  add     rdx, [rax+rcx*8]
0x100437b82  mov     rax, [r15]
0x100437b85  mov     [rdx+8], rax
0x100437b89  movsd   qword ptr [rdx+10h], xmm0
0x100437b8e  mov     eax, [rbx+9Ch]
0x100437b94  shl     rax, 4
0x100437b98  add     rax, [rbx+0A8h]
0x100437b9f  mov     [rdx+20h], rax
0x100437ba3  cmp     [rbx+10h], bpl
0x100437ba7  jz      short loc_100437BC5
0x100437ba9  mov     rax, [r14]
0x100437bac  mov     [rdx+18h], rax
0x100437bb0  mov     ecx, [rbx+9Ch]
0x100437bb6  mov     rax, [rbx+0B8h]
0x100437bbd  lea     rcx, [rax+rcx*8]
0x100437bc1  mov     [rdx+28h], rcx
0x100437bc5  mov     rbp, [rsp+88h+arg_8]
0x100437bcd  mov     eax, edi
0x100437bcf  mov     rsi, [rsp+88h+arg_10]
0x100437bd7  mov     rbx, [rsp+88h+arg_18]
0x100437bdf  add     rsp, 70h
0x100437be3  pop     r15
0x100437be5  pop     r14
0x100437be7  pop     rdi
0x100437be8  retn
0x100437be9  lfence
0x100437bec  jmp     short loc_100437BC5
0x100437bee  lfence
0x100437bf1  mov     rbx, [rsp+88h+arg_18]
0x100437bf9  add     rsp, 70h
0x100437bfd  pop     r15
0x100437bff  pop     r14
0x100437c01  pop     rdi
0x100437c02  retn
```
