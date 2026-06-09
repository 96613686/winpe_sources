# CImpIColumnsUpdateInfo::GetColumnUpdateInfo(unsigned __int64 *,DBCOLUMNUPDATEINFO * *,ushort * *,uchar * *)

- ea: `0x180012d50`
- end: `0x180013580`
- name: `?GetColumnUpdateInfo@CImpIColumnsUpdateInfo@@UEAAJPEA_KPEAPEAUDBCOLUMNUPDATEINFO@@PEAPEAGPEAPEAE@Z`
- size: `2096`
- prototype: `__int64 __fastcall(CImpIColumnsUpdateInfo *__hidden this, unsigned __int64 *, struct DBCOLUMNUPDATEINFO **, unsigned __int16 **, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update`

## callees

- `0x18000266c`
- `0x180012d50`
- `0x180013588`
- `0x180015fb4`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e012`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180013538`
- `ole32!CoTaskMemFree` at `0x180013544`
- `ole32!CoTaskMemFree` at `0x180013550`
- `ole32!CoTaskMemFree` at `0x18001355a`
- `ole32!CoTaskMemFree` at `0x180013538`
- `ole32!CoTaskMemFree` at `0x180013544`
- `ole32!CoTaskMemFree` at `0x180013550`
- `ole32!CoTaskMemFree` at `0x18001355a`
- `ole32!CoTaskMemAlloc` at `0x180012e9e`
- `ole32!CoTaskMemAlloc` at `0x18001309d`
- `ole32!CoTaskMemAlloc` at `0x180012e9e`
- `ole32!CoTaskMemAlloc` at `0x18001309d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180012db6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180012db6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CImpIColumnsUpdateInfo::GetColumnUpdateInfo(
        CImpIColumnsUpdateInfo *this,
        unsigned __int64 *a2,
        struct DBCOLUMNUPDATEINFO **a3,
        unsigned __int16 **a4,
        unsigned __int8 **a5)
{
  unsigned __int16 **v5; // rdi
  unsigned __int8 *v9; // r12
  SIZE_T v10; // r14
  __int64 v11; // r15
  unsigned __int8 **v12; // rsi
  int v13; // eax
  int v14; // ebx
  struct DBCOLUMNUPDATEINFO *v15; // r13
  void *v16; // r11
  unsigned int v17; // r8d
  __int64 v18; // r9
  __int64 v19; // rdx
  _OWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int16 v23; // ax
  __int64 v24; // rax
  __int16 v25; // ax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rbx
  unsigned int v33; // eax
  __int64 v34; // r11
  __int64 v35; // rdi
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // r11
  int v39; // esi
  _QWORD *v40; // rsi
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // eax
  int v44; // r12d
  __int64 v45; // rax
  __int64 v46; // rax
  int v47; // eax
  int v48; // r12d
  __int64 v49; // rax
  __int64 v50; // rax
  int v51; // eax
  int v52; // r12d
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rdx
  int v56; // r8d
  void *v57; // rbx
  unsigned __int16 *v58; // rax
  void *v59; // rdi
  unsigned int v60; // esi
  unsigned int v62; // [rsp+30h] [rbp-88h]
  LPVOID pv; // [rsp+38h] [rbp-80h] BYREF
  int v64; // [rsp+40h] [rbp-78h]
  unsigned __int16 *v65; // [rsp+48h] [rbp-70h]
  struct DBCOLUMNUPDATEINFO *v66; // [rsp+50h] [rbp-68h]
  unsigned __int16 *v67; // [rsp+58h] [rbp-60h]
  LPVOID v68; // [rsp+60h] [rbp-58h] BYREF
  __int64 v69; // [rsp+68h] [rbp-50h] BYREF
  unsigned __int64 v70[9]; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v71; // [rsp+C0h] [rbp+8h]

  v5 = a4;
  v69 = 0;
  v66 = 0;
  v68 = 0;
  pv = 0;
  v9 = 0;
  v67 = 0;
  v10 = 0;
  v11 = *((_QWORD *)this + 3);
  v71 = *(_DWORD *)(v11 + 152);
  v70[0] = 0;
  v64 = 0;
  SetErrorInfo(0, 0);
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( v5 )
    *v5 = 0;
  v12 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a2 || !a3 || !v5 || !a5 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180048988[0] )
      bidTraceW(off_1800481D8[0], 70656, off_180048988[0], 2147942487LL, 69);
    ThrowHR(-2147024809);
  }
  (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(*((_QWORD *)this + 3), &IID_IColumnsInfo, &v69);
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v69 + 24LL))(
          v69,
          v70,
          &v68,
          &pv);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180048980[0] )
        bidTraceW(off_1800481D8[0], 76800, off_180048980[0], (unsigned int)v13, 75);
    }
    ThrowHR(v14);
  }
  v15 = (struct DBCOLUMNUPDATEINFO *)CoTaskMemAlloc(168LL * v71);
  v66 = v15;
  v16 = 0;
  if ( !v15 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180048978[0] )
      bidTraceW(off_1800481D8[0], 88064, off_180048978[0], 2147942414LL, 86);
    ThrowHR(-2147024882);
  }
  v17 = 0;
  if ( !v71 )
    goto LABEL_105;
  v18 = 0;
  do
  {
    v19 = 168 * v18;
    v20 = v68;
    *(_OWORD *)((char *)v15 + v19) = *((_OWORD *)v68 + 5 * v18);
    *(_OWORD *)((char *)v15 + v19 + 16) = v20[5 * v18 + 1];
    *(_OWORD *)((char *)v15 + v19 + 32) = v20[5 * v18 + 2];
    *(_OWORD *)((char *)v15 + v19 + 48) = v20[5 * v18 + 3];
    *(_OWORD *)((char *)v15 + v19 + 64) = v20[5 * v18 + 4];
    v21 = 9648 * v18;
    v22 = *(_QWORD *)(v11 + 336);
    if ( *(_DWORD *)(9648 * v18 + v22 + 9532) )
      v23 = 0;
    else
      v23 = *(_WORD *)(v21 + v22 + 9528);
    *(_WORD *)((char *)v15 + v19 + 114) = v23;
    v24 = *(_QWORD *)(v11 + 336);
    if ( *(_DWORD *)(v24 + v21 + 9584) )
      v25 = 0;
    else
      v25 = *(_WORD *)(v24 + v21 + 9580);
    *(_WORD *)((char *)v15 + v19 + 112) = v25;
    v26 = *(_QWORD *)(v11 + 336);
    if ( *(_DWORD *)(v21 + v26 + 9608) )
      v27 = 0;
    else
      v27 = *(_QWORD *)(v21 + v26 + 9616);
    *(_QWORD *)((char *)v15 + v19 + 120) = v27;
    v28 = *(_QWORD *)(v11 + 336);
    if ( *(_DWORD *)(v21 + v28 + 9632) )
      v29 = 0;
    else
      v29 = *(_QWORD *)(v21 + v28 + 9640);
    *(_QWORD *)((char *)v15 + v19 + 128) = v29;
    *(_QWORD *)((char *)v15 + v19 + 152) = 0;
    *(_DWORD *)((char *)v15 + v19 + 160) = 0;
    v30 = *(_QWORD *)(v11 + 336);
    if ( !*(_DWORD *)(v30 + v21 + 3216) )
      v10 += *(_QWORD *)(v30 + v21 + 3224) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 4260) )
      v10 += *(_QWORD *)(v30 + v21 + 4264) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 5300) )
      v10 += *(_QWORD *)(v30 + v21 + 5304) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 6340) )
      v10 += *(_QWORD *)(v30 + v21 + 6344) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 9608) )
      v10 += *(_QWORD *)(v30 + v21 + 9616) + 2LL;
    if ( !*(_DWORD *)(v30 + v21 + 9632) )
      v10 += *(_QWORD *)(v30 + v21 + 9640) + 2LL;
    ++v17;
    ++v18;
  }
  while ( v17 < v71 );
  if ( v10 )
  {
    v31 = (unsigned __int16 *)CoTaskMemAlloc(v10);
    v9 = (unsigned __int8 *)v31;
    v65 = v31;
    v67 = v31;
    v16 = 0;
    if ( !v31 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048970[0] )
        bidTraceW(off_1800481D8[0], 141312, off_180048970[0], 2147942414LL, 138);
      ThrowHR(-2147024882);
    }
    v32 = v31;
    v33 = 0;
    while ( 1 )
    {
      v62 = v33;
      if ( v33 >= v71 )
        break;
      v34 = v33;
      v35 = 9648LL * v33;
      v36 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v36 + 3216) )
      {
        v40 = (_QWORD *)((char *)v15 + 168 * v34);
        v16 = 0;
        v40[12] = 0;
      }
      else
      {
        v37 = StringCbCopyW(v32, (unsigned __int64)&v9[v10 - (_QWORD)v32], (const unsigned __int16 *)(v35 + v36 + 2188));
        v39 = v37;
        if ( v37 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048968[0] )
            bidTraceW(off_1800481D8[0], 152576, off_180048968[0], (unsigned int)v37, 149);
          ThrowHR(v39);
        }
        v40 = (_QWORD *)((char *)v15 + 168 * v38);
        v40[12] = v32;
        v41 = -1;
        v16 = 0;
        do
          ++v41;
        while ( *(_WORD *)(v35 + *(_QWORD *)(v11 + 336) + 2 * v41 + 2188) );
        v32 += v41 + 1;
      }
      v42 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v42 + 4260) )
      {
        v40[13] = 0;
      }
      else
      {
        v43 = StringCbCopyW(v32, (unsigned __int64)&v9[v10 - (_QWORD)v32], (const unsigned __int16 *)(v35 + v42 + 3232));
        v44 = v43;
        if ( v43 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048960[0] )
            bidTraceW(off_1800481D8[0], 163840, off_180048960[0], (unsigned int)v43, 160);
          ThrowHR(v44);
        }
        v40[13] = v32;
        v45 = -1;
        do
          ++v45;
        while ( *(_WORD *)(v35 + *(_QWORD *)(v11 + 336) + 2 * v45 + 3232) != (_WORD)v16 );
        v32 += v45 + 1;
        v9 = (unsigned __int8 *)v65;
      }
      v46 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v46 + 5300) == (_DWORD)v16 )
      {
        v47 = StringCbCopyW(v32, (unsigned __int64)&v9[v10 - (_QWORD)v32], (const unsigned __int16 *)(v35 + v46 + 4272));
        v48 = v47;
        if ( v47 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048958[0] )
            bidTraceW(off_1800481D8[0], 175104, off_180048958[0], (unsigned int)v47, 171);
          ThrowHR(v48);
        }
        v40[11] = v32;
        v49 = -1;
        do
          ++v49;
        while ( *(_WORD *)(v35 + *(_QWORD *)(v11 + 336) + 2 * v49 + 4272) != (_WORD)v16 );
        v32 += v49 + 1;
      }
      else
      {
        v40[11] = v16;
      }
      v50 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v50 + 6340) == (_DWORD)v16 )
      {
        v51 = StringCbCopyW(
                v32,
                (unsigned __int64)v65 + v10 - (_QWORD)v32,
                (const unsigned __int16 *)(v35 + v50 + 5312));
        v52 = v51;
        if ( v51 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048950[0] )
            bidTraceW(off_1800481D8[0], 186368, off_180048950[0], (unsigned int)v51, 182);
          ThrowHR(v52);
        }
        v40[10] = v32;
        v53 = -1;
        do
          ++v53;
        while ( *(_WORD *)(v35 + *(_QWORD *)(v11 + 336) + 2 * v53 + 5312) != (_WORD)v16 );
        v32 += v53 + 1;
      }
      else
      {
        v40[10] = v16;
      }
      v54 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v54 + 9608) == (_DWORD)v16 )
      {
        memcpy_0(v32, *(const void **)(v35 + v54 + 9600), *(_QWORD *)(v35 + v54 + 9616));
        v40[17] = v32;
        v32 = (unsigned __int16 *)((char *)v32 + *(_QWORD *)(v35 + *(_QWORD *)(v11 + 336) + 9616));
        v16 = 0;
      }
      else
      {
        v40[17] = v16;
      }
      v55 = *(_QWORD *)(v11 + 336);
      if ( *(_DWORD *)(v35 + v55 + 9632) == (_DWORD)v16 )
      {
        memcpy_0(v32, *(const void **)(v35 + v55 + 9624), *(_QWORD *)(v35 + v55 + 9640));
        v40[18] = v32;
        v32 = (unsigned __int16 *)((char *)v32 + *(_QWORD *)(v35 + *(_QWORD *)(v11 + 336) + 9640));
        v16 = 0;
      }
      else
      {
        v40[18] = v16;
      }
      v33 = v62 + 1;
      v9 = (unsigned __int8 *)v65;
    }
    v12 = a5;
    v5 = a4;
    v56 = v64;
  }
  else
  {
LABEL_105:
    v56 = 1;
  }
  v57 = v16;
  v66 = (struct DBCOLUMNUPDATEINFO *)v16;
  *a3 = v15;
  v58 = (unsigned __int16 *)pv;
  pv = v16;
  *v5 = v58;
  v59 = v16;
  v67 = (unsigned __int16 *)v16;
  *v12 = v9;
  *a2 = v70[0];
  v60 = Exit(v56, 0);
  CoTaskMemFree(v59);
  CoTaskMemFree(pv);
  CoTaskMemFree(v68);
  CoTaskMemFree(v57);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v69);
  return v60;
}

```

## disassembly

```asm
0x180012d50  mov     rax, rsp
0x180012d53  mov     [rax+20h], r9
0x180012d57  mov     [rax+18h], r8
0x180012d5b  mov     [rax+10h], rdx
0x180012d5f  push    rbx
0x180012d60  push    rsi
0x180012d61  push    rdi
0x180012d62  push    r12
0x180012d64  push    r13
0x180012d66  push    r14
0x180012d68  push    r15
0x180012d6a  sub     rsp, 80h
0x180012d71  mov     rdi, r9
0x180012d74  mov     r13, r8
0x180012d77  mov     rsi, rdx
0x180012d7a  mov     rbx, rcx
0x180012d7d  xor     ecx, ecx; dwReserved
0x180012d7f  mov     [rax-50h], rcx
0x180012d83  mov     [rax-68h], rcx
0x180012d87  mov     [rax-58h], rcx
0x180012d8b  mov     [rax-80h], rcx
0x180012d8f  mov     r12d, ecx
0x180012d92  mov     [rax-60h], rcx
0x180012d96  mov     r14d, ecx
0x180012d99  mov     r15, [rbx+18h]
0x180012d9d  mov     eax, [r15+98h]
0x180012da4  mov     [rsp+0B8h+arg_0], eax
0x180012dab  mov     [rsp+0B8h+var_48], rcx
0x180012db0  mov     [rsp+0B8h+var_78], ecx
0x180012db4  xor     edx, edx; perrinfo
0x180012db6  call    cs:__imp_SetErrorInfo
0x180012dbc  xor     ecx, ecx
0x180012dbe  test    rsi, rsi
0x180012dc1  jz      short loc_180012DC6
0x180012dc3  mov     [rsi], rcx
0x180012dc6  test    r13, r13
0x180012dc9  jz      short loc_180012DCF
0x180012dcb  mov     [r13+0], rcx
0x180012dcf  test    rdi, rdi
0x180012dd2  jz      short loc_180012DD7
0x180012dd4  mov     [rdi], rcx
0x180012dd7  mov     rsi, [rsp+0B8h+arg_20]
0x180012ddf  test    rsi, rsi
0x180012de2  jz      short loc_180012DE7
0x180012de4  mov     [rsi], rcx
0x180012de7  cmp     [rsp+0B8h+arg_8], rcx
0x180012def  jz      loc_1800134D1
0x180012df5  test    r13, r13
0x180012df8  jz      loc_1800134D1
0x180012dfe  test    rdi, rdi
0x180012e01  jz      loc_1800134D1
0x180012e07  test    rsi, rsi
0x180012e0a  jz      loc_1800134D1
0x180012e10  mov     rcx, [rbx+18h]
0x180012e14  mov     rax, [rcx]
0x180012e17  lea     r8, [rsp+0B8h+var_50]
0x180012e1c  lea     rdx, IID_IColumnsInfo
0x180012e23  mov     rax, [rax]
0x180012e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e2b  mov     rcx, [rsp+0B8h+var_50]
0x180012e30  mov     rax, [rcx]
0x180012e33  lea     r9, [rsp+0B8h+pv]
0x180012e38  lea     r8, [rsp+0B8h+var_58]
0x180012e3d  lea     rdx, [rsp+0B8h+var_48]
0x180012e42  mov     rax, [rax+18h]
0x180012e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e4b  mov     ebx, eax
0x180012e4d  test    eax, eax
0x180012e4f  jns     short loc_180012E90
0x180012e51  test    byte ptr cs:_bidGblFlags, 2
0x180012e58  jz      short loc_180012E89
0x180012e5a  mov     rcx, cs:off_180048980; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180012e61  test    rcx, rcx
0x180012e64  jz      short loc_180012E89
0x180012e66  mov     [rsp+0B8h+var_98], 4Bh ; 'K'
0x180012e6e  mov     r9d, eax
0x180012e71  mov     r8, cs:off_180048980; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180012e78  mov     edx, 12C00h
0x180012e7d  mov     rcx, cs:off_1800481D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180012e84  call    _bidTraceW
0x180012e89  mov     ecx, ebx; int
0x180012e8b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180012e90  mov     ebx, [rsp+0B8h+arg_0]
0x180012e97  imul    rcx, rbx, 0A8h; cb
0x180012e9e  call    cs:__imp_CoTaskMemAlloc
0x180012ea4  mov     r13, rax
0x180012ea7  mov     [rsp+0B8h+var_68], rax
0x180012eac  xor     r11d, r11d
0x180012eaf  test    rax, rax
0x180012eb2  jnz     short loc_180012EF9
0x180012eb4  test    byte ptr cs:_bidGblFlags, 2
0x180012ebb  jz      short loc_180012EEF
0x180012ebd  mov     rax, cs:off_180048978; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180012ec4  test    rax, rax
0x180012ec7  jz      short loc_180012EEF
0x180012ec9  mov     [rsp+0B8h+var_98], 56h ; 'V'
0x180012ed1  mov     r9d, 8007000Eh
0x180012ed7  mov     r8, cs:off_180048978; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180012ede  mov     edx, 15800h
0x180012ee3  mov     rcx, cs:off_1800481D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180012eea  call    _bidTraceW
0x180012eef  mov     ecx, 8007000Eh; int
0x180012ef4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180012ef9  mov     r8d, r11d
0x180012efc  test    ebx, ebx
0x180012efe  jz      loc_180013477
0x180012f04  mov     r9, r11
0x180012f07  imul    rdx, r9, 0A8h
0x180012f0e  lea     rcx, [r9+r9*4]
0x180012f12  add     rcx, rcx
0x180012f15  mov     rax, [rsp+0B8h+var_58]
0x180012f1a  movups  xmm0, xmmword ptr [rax+rcx*8]
0x180012f1e  movups  xmmword ptr [rdx+r13], xmm0
0x180012f23  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x180012f28  movups  xmmword ptr [rdx+r13+10h], xmm1
0x180012f2e  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x180012f33  movups  xmmword ptr [rdx+r13+20h], xmm0
0x180012f39  movups  xmm1, xmmword ptr [rax+rcx*8+30h]
0x180012f3e  movups  xmmword ptr [rdx+r13+30h], xmm1
0x180012f44  movups  xmm0, xmmword ptr [rax+rcx*8+40h]
0x180012f49  movups  xmmword ptr [rdx+r13+40h], xmm0
0x180012f4f  imul    rcx, r9, 25B0h
0x180012f56  mov     rax, [r15+150h]
0x180012f5d  cmp     [rcx+rax+253Ch], r11d
0x180012f65  jnz     short loc_180012F71
0x180012f67  movzx   eax, word ptr [rcx+rax+2538h]
0x180012f6f  jmp     short loc_180012F74
0x180012f71  mov     eax, r11d
0x180012f74  mov     [rdx+r13+72h], ax
0x180012f7a  mov     rax, [r15+150h]
0x180012f81  cmp     [rax+rcx+2570h], r11d
0x180012f89  jnz     short loc_180012F95
0x180012f8b  movzx   eax, word ptr [rax+rcx+256Ch]
0x180012f93  jmp     short loc_180012F98
0x180012f95  mov     eax, r11d
0x180012f98  mov     [rdx+r13+70h], ax
0x180012f9e  mov     rax, [r15+150h]
0x180012fa5  cmp     [rcx+rax+2588h], r11d
0x180012fad  jnz     short loc_180012FB9
0x180012faf  mov     rax, [rcx+rax+2590h]
0x180012fb7  jmp     short loc_180012FBC
0x180012fb9  mov     rax, r11
0x180012fbc  mov     [rdx+r13+78h], rax
0x180012fc1  mov     rax, [r15+150h]
0x180012fc8  cmp     [rcx+rax+25A0h], r11d
0x180012fd0  jnz     short loc_180012FDC
0x180012fd2  mov     rax, [rcx+rax+25A8h]
0x180012fda  jmp     short loc_180012FDF
0x180012fdc  mov     rax, r11
0x180012fdf  mov     [rdx+r13+80h], rax
0x180012fe7  mov     [rdx+r13+98h], r11
0x180012fef  mov     [rdx+r13+0A0h], r11d
0x180012ff7  mov     rdx, [r15+150h]
0x180012ffe  cmp     [rdx+rcx+0C90h], r11d
0x180013006  jnz     short loc_180013014
0x180013008  add     r14, 2
0x18001300c  add     r14, [rdx+rcx+0C98h]
0x180013014  cmp     [rdx+rcx+10A4h], r11d
0x18001301c  jnz     short loc_18001302A
0x18001301e  add     r14, 2
0x180013022  add     r14, [rdx+rcx+10A8h]
0x18001302a  cmp     [rdx+rcx+14B4h], r11d
0x180013032  jnz     short loc_180013040
0x180013034  add     r14, 2
0x180013038  add     r14, [rdx+rcx+14B8h]
0x180013040  cmp     [rdx+rcx+18C4h], r11d
0x180013048  jnz     short loc_180013056
0x18001304a  add     r14, 2
0x18001304e  add     r14, [rdx+rcx+18C8h]
0x180013056  cmp     [rdx+rcx+2588h], r11d
0x18001305e  jnz     short loc_18001306C
0x180013060  add     r14, 2
0x180013064  add     r14, [rdx+rcx+2590h]
0x18001306c  cmp     [rdx+rcx+25A0h], r11d
0x180013074  jnz     short loc_180013082
0x180013076  add     r14, 2
0x18001307a  add     r14, [rdx+rcx+25A8h]
0x180013082  inc     r8d
0x180013085  inc     r9
0x180013088  cmp     r8d, ebx
0x18001308b  jb      loc_180012F07
0x180013091  test    r14, r14
0x180013094  jz      loc_180013477
0x18001309a  mov     rcx, r14; cb
0x18001309d  call    cs:__imp_CoTaskMemAlloc
0x1800130a3  mov     r12, rax
0x1800130a6  mov     [rsp+0B8h+var_70], rax
0x1800130ab  mov     [rsp+0B8h+var_60], rax
0x1800130b0  xor     r11d, r11d
0x1800130b3  test    rax, rax
0x1800130b6  jnz     short loc_1800130FD
0x1800130b8  test    byte ptr cs:_bidGblFlags, 2
0x1800130bf  jz      short loc_1800130F3
0x1800130c1  mov     rax, cs:off_180048970; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x1800130c8  test    rax, rax
0x1800130cb  jz      short loc_1800130F3
0x1800130cd  mov     [rsp+0B8h+var_98], 8Ah
0x1800130d5  mov     r9d, 8007000Eh
0x1800130db  mov     r8, cs:off_180048970; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x1800130e2  mov     edx, 22800h
0x1800130e7  mov     rcx, cs:off_1800481D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800130ee  call    _bidTraceW
0x1800130f3  mov     ecx, 8007000Eh; int
0x1800130f8  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800130fd  mov     rbx, rax
0x180013100  mov     eax, r11d
0x180013103  mov     [rsp+0B8h+var_88], eax
0x180013107  cmp     eax, [rsp+0B8h+arg_0]
0x18001310e  jnb     loc_18001347F
0x180013114  mov     r11d, eax
0x180013117  imul    rdi, r11, 25B0h
0x18001311e  mov     rax, [r15+150h]
0x180013125  cmp     dword ptr [rdi+rax+0C90h], 0
0x18001312d  jnz     loc_1800131CA
0x180013133  lea     r8, [rax+88Ch]
0x18001313a  add     r8, rdi; unsigned __int16 *
0x18001313d  mov     rdx, r14
0x180013140  sub     rdx, rbx
0x180013143  add     rdx, r12; unsigned __int64
0x180013146  mov     rcx, rbx; unsigned __int16 *
0x180013149  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001314e  mov     esi, eax
0x180013150  test    eax, eax
0x180013152  jns     short loc_180013193
0x180013154  test    byte ptr cs:_bidGblFlags, 2
0x18001315b  jz      short loc_18001318C
0x18001315d  mov     rcx, cs:off_180048968; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180013164  test    rcx, rcx
0x180013167  jz      short loc_18001318C
0x180013169  mov     [rsp+0B8h+var_98], 95h
0x180013171  mov     r9d, eax
0x180013174  mov     r8, cs:off_180048968; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x18001317b  mov     edx, 25400h
0x180013180  mov     rcx, cs:off_1800481D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180013187  call    _bidTraceW
0x18001318c  mov     ecx, esi; int
0x18001318e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180013193  imul    rsi, r11, 0A8h
0x18001319a  add     rsi, r13
0x18001319d  mov     [rsi+60h], rbx
0x1800131a1  mov     rcx, [r15+150h]
0x1800131a8  add     rcx, rdi
0x1800131ab  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800131af  xor     r11d, r11d
0x1800131b2  inc     rax
0x1800131b5  cmp     [rcx+rax*2+88Ch], r11w
0x1800131be  jnz     short loc_1800131B2
0x1800131c0  lea     rbx, [rbx+rax*2]
0x1800131c4  add     rbx, 2
0x1800131c8  jmp     short loc_1800131DB
0x1800131ca  imul    rsi, r11, 0A8h
0x1800131d1  add     rsi, r13
0x1800131d4  xor     r11d, r11d
0x1800131d7  mov     [rsi+60h], r11
0x1800131db  mov     rax, [r15+150h]
0x1800131e2  cmp     [rdi+rax+10A4h], r11d
0x1800131ea  jnz     loc_180013281
0x1800131f0  lea     r8, [rax+0CA0h]
0x1800131f7  add     r8, rdi; unsigned __int16 *
0x1800131fa  mov     rdx, r14
0x1800131fd  sub     rdx, rbx
0x180013200  add     rdx, r12; unsigned __int64
0x180013203  mov     rcx, rbx; unsigned __int16 *
0x180013206  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001320b  mov     r12d, eax
0x18001320e  test    eax, eax
0x180013210  jns     short loc_180013252
0x180013212  test    byte ptr cs:_bidGblFlags, 2
0x180013219  jz      short loc_18001324A
0x18001321b  mov     rcx, cs:off_180048960; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180013222  test    rcx, rcx
0x180013225  jz      short loc_18001324A
0x180013227  mov     [rsp+0B8h+var_98], 0A0h
0x18001322f  mov     r9d, eax
0x180013232  mov     r8, cs:off_180048960; "<CImpIColumnsUpdateInfo::GetColumnUpdat"...
0x180013239  mov     edx, 28000h
0x18001323e  mov     rcx, cs:off_1800481D8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180013245  call    _bidTraceW
0x18001324a  mov     ecx, r12d; int
0x18001324d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180013252  mov     [rsi+68h], rbx
0x180013256  mov     rcx, [r15+150h]
0x18001325d  add     rcx, rdi
0x180013260  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013264  inc     rax
0x180013267  cmp     [rcx+rax*2+0CA0h], r11w
0x180013270  jnz     short loc_180013264
0x180013272  lea     rbx, [rbx+rax*2]
0x180013276  add     rbx, 2
0x18001327a  mov     r12, [rsp+0B8h+var_70]
0x18001327f  jmp     short loc_180013285
0x180013281  mov     [rsi+68h], r11
0x180013285  mov     rax, [r15+150h]
0x18001328c  cmp     [rdi+rax+14B4h], r11d
0x180013294  jnz     loc_180013326
0x18001329a  lea     r8, [rax+10B0h]
0x1800132a1  add     r8, rdi; unsigned __int16 *
0x1800132a4  mov     rdx, r14
0x1800132a7  sub     rdx, rbx
0x1800132aa  add     rdx, r12; unsigned __int64
  ... truncated ...
```
