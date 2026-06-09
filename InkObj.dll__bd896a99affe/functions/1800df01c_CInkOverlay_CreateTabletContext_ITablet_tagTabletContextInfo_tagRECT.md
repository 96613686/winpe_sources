# CInkOverlay::_CreateTabletContext(ITablet *,tagTabletContextInfo *,tagRECT *)

- ea: `0x1800df01c`
- end: `0x1800df4d0`
- name: `?_CreateTabletContext@CInkOverlay@@AEAAJPEAUITablet@@PEAUtagTabletContextInfo@@PEAUtagRECT@@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(CInkOverlay *__hidden this, struct ITablet *, struct tagTabletContextInfo *, struct tagRECT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800ddbe0`
- `0x1800debc0`

## callees

- `0x180002740`
- `0x180010350`
- `0x180028a98`
- `0x1800df01c`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df08c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df0a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df0b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df3a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df49b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df08c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df0a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df0b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df3a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df450`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df49b`

## pseudocode

```c
__int64 __fastcall CInkOverlay::_CreateTabletContext(
        CInkOverlay *this,
        struct ITablet *a2,
        struct tagTabletContextInfo *a3,
        struct tagRECT *a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v7)(struct ITablet *, LPVOID *); // rax
  int updated; // ebx
  int v9; // r12d
  unsigned int v10; // edx
  _OWORD *v11; // r14
  _OWORD **v12; // r13
  __int64 v13; // rcx
  __int64 v14; // rax
  _OWORD *v15; // rax
  unsigned int v16; // esi
  unsigned int v17; // r12d
  __int64 v18; // rcx
  _OWORD *v19; // rdx
  int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // ecx
  int v23; // ecx
  unsigned int v24; // ecx
  _OWORD *v25; // rcx
  __int64 v26; // rax
  int v27; // edx
  __int64 v28; // r9
  __int64 v29; // rax
  __int64 v30; // rcx
  bool v31; // cf
  char *v32; // rax
  _QWORD *v33; // rcx
  _DWORD *v34; // rcx
  _OWORD *v35; // rsi
  _OWORD *v36; // rcx
  LPVOID pv; // [rsp+60h] [rbp-39h] BYREF
  LPVOID v39; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v40; // [rsp+70h] [rbp-29h]
  int v41; // [rsp+74h] [rbp-25h]
  __int64 v42; // [rsp+78h] [rbp-21h]
  struct ITablet *v43; // [rsp+80h] [rbp-19h]
  struct tagRECT *v44; // [rsp+88h] [rbp-11h]
  __int128 v45; // [rsp+90h] [rbp-9h] BYREF

  v4 = *(_QWORD *)a2;
  v43 = a2;
  v44 = a4;
  v7 = *(__int64 (__fastcall **)(struct ITablet *, LPVOID *))(v4 + 24);
  pv = 0;
  updated = v7(a2, &pv);
  if ( updated < 0 )
    return (unsigned int)updated;
  v9 = 1;
  v39 = 0;
  v41 = 1;
  CoTaskMemFree(*((LPVOID *)pv + 1));
  *((_QWORD *)pv + 1) = 0;
  CoTaskMemFree(*((LPVOID *)pv + 4));
  *((_QWORD *)pv + 4) = 0;
  CoTaskMemFree(*((LPVOID *)pv + 5));
  *((_QWORD *)pv + 5) = 0;
  v10 = *((_DWORD *)this + 117);
  if ( v10 < 2 )
  {
    v11 = 0;
    updated = -2147418113;
    goto LABEL_45;
  }
  if ( v10 <= 2 )
    goto LABEL_8;
  v12 = (_OWORD **)((char *)this + 472);
  v13 = *((_QWORD *)this + 59);
  v14 = 0x4CF7AFE76E0E07BFLL - *(_QWORD *)(v13 + 64);
  if ( *(_QWORD *)(v13 + 64) == 0x4CF7AFE76E0E07BFLL )
    v14 = 0x1884204664AFD187LL - *(_QWORD *)(v13 + 72);
  if ( v14 )
  {
LABEL_8:
    v9 = 0;
    v41 = 0;
    v12 = (_OWORD **)((char *)this + 472);
  }
  v40 = (*(_DWORD *)&g_CollectorProfileData != 0 ? 2 : 0) + v10 + (v9 ^ 1);
  v15 = WinMalloc(saturated_mul(v40, 0x10u));
  v11 = v15;
  if ( !v15 )
  {
    updated = -2147024882;
    goto LABEL_45;
  }
  v16 = 3;
  v17 = v9 + 2;
  *v15 = **v12;
  v15[1] = (*v12)[2];
  v15[2] = xmmword_180121350;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v17 >= *((_DWORD *)this + 117) )
      {
LABEL_18:
        v21 = v40;
        goto LABEL_19;
      }
      v42 = 32LL * v17;
      v18 = *(_QWORD *)v43;
      v19 = &(*v12)[(unsigned __int64)v42 / 0x10];
      v45 = 0;
      v20 = (*(__int64 (__fastcall **)(struct ITablet *, _OWORD *, __int128 *))(v18 + 64))(v43, v19, &v45);
      updated = v20;
      if ( v20 )
        break;
      if ( v16 < v40 )
      {
        v11[v16] = (*v12)[(unsigned __int64)v42 / 0x10];
        goto LABEL_32;
      }
      updated = -2147418113;
LABEL_17:
      ++v17;
      if ( updated < 0 )
        goto LABEL_18;
    }
    if ( v20 != -2147220965 )
      goto LABEL_17;
    v25 = *v12;
    updated = 0;
    v26 = 0x45D1FED3436510C5LL - *(_QWORD *)&(*v12)[(unsigned __int64)v42 / 0x10];
    if ( *(_QWORD *)&(*v12)[(unsigned __int64)v42 / 0x10] == 0x45D1FED3436510C5LL )
      v26 = 0x9D827AEAD371768BuLL - *((_QWORD *)&v25[(unsigned __int64)v42 / 0x10] + 1);
    if ( v26 )
      goto LABEL_17;
    v21 = v40;
    if ( v16 >= v40 )
      break;
    v11[v16] = v25[(unsigned __int64)v42 / 0x10];
LABEL_32:
    ++v16;
    ++v17;
  }
  updated = -2147418113;
LABEL_19:
  if ( *(_DWORD *)&g_CollectorProfileData )
  {
    v22 = v16 + 1;
    if ( v16 + 1 < v21 )
    {
      v11[v16] = GUID_PEN_TIMESTAMP1;
      v16 += 2;
      v11[v22] = GUID_PEN_TIMESTAMP2;
    }
  }
  *(_DWORD *)pv = v16;
  *((_QWORD *)pv + 1) = v11;
  if ( updated >= 0 )
  {
    v23 = *((_DWORD *)this + 79);
    if ( v23 == 0x80000000 )
    {
      v24 = 516;
      if ( *((_DWORD *)this + 80) != 0x80000000 )
        goto LABEL_35;
    }
    else
    {
      *((_DWORD *)pv + 12) = v23;
LABEL_35:
      v27 = *((_DWORD *)this + 80);
      v24 = 517;
      if ( v27 != 0x80000000 )
        *((_DWORD *)pv + 13) = v27;
    }
    v28 = v24 | 0x10;
    if ( *((_DWORD *)this + 78) != 1 )
      v28 = v24;
    if ( *(_DWORD *)&g_CollectorProfileData )
      LODWORD(v28) = v28 | 0x100;
    v29 = *((_QWORD *)this + 66);
    v30 = v29 + 64;
    v31 = v29 != 0;
    v32 = (char *)this + 768;
    if ( *((_DWORD *)this + 213) != 1 )
      v32 = (char *)this + 56;
    updated = (*(__int64 (__fastcall **)(struct ITablet *, _QWORD, struct tagRECT *, __int64, LPVOID, int, struct tagTabletContextInfo *, char *, LPVOID *, __int64))(*(_QWORD *)v43 + 32LL))(
                v43,
                *(_QWORD *)v32,
                v44,
                v28,
                pv,
                2,
                a3,
                (char *)a3 + 8,
                &v39,
                v30 & -(__int64)v31);
  }
  v9 = v41;
LABEL_45:
  CoTaskMemFree(*((LPVOID *)pv + 3));
  CoTaskMemFree(pv);
  if ( v11 )
    WinFree(v11);
  if ( updated >= 0 )
  {
    v33 = v39;
    *((_QWORD *)a3 + 2) = *((_QWORD *)v39 + 3);
    v33[3] = 0;
    *((_DWORD *)v39 + 4) = 0;
    v34 = v39;
    v35 = (_OWORD *)*((_QWORD *)v39 + 1);
    if ( !v9 )
    {
      v35[4] = v35[2];
      v35[5] = v35[3];
      v36 = (_OWORD *)*((_QWORD *)v39 + 1);
      v36[2] = *v36;
      v36[3] = v36[1];
      *((_QWORD *)v39 + 1) += 32LL;
      --*((_DWORD *)v39 + 1);
      v34 = v39;
    }
    *v34 = 4 * v34[1];
    updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID))(**((_QWORD **)this + 68) + 56LL))(
                *((_QWORD *)this + 68),
                *((unsigned int *)a3 + 2),
                v39);
    CoTaskMemFree(v35);
    CoTaskMemFree(v39);
    if ( updated < 0
      || (updated = CInkOverlay::_UpdateTabletToInkToDisplayMapping(this, *(struct ITabletContext **)a3, 0), updated < 0)
      || (updated = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)a3 + 56LL))(*(_QWORD *)a3, 1), updated < 0) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a3 + 16LL))(*(_QWORD *)a3);
      CoTaskMemFree(*((LPVOID *)a3 + 2));
      *(_OWORD *)a3 = 0;
      *((_QWORD *)a3 + 2) = 0;
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800df01c  push    rbp
0x1800df01e  push    rbx
0x1800df01f  push    rsi
0x1800df020  push    rdi
0x1800df021  push    r12
0x1800df023  push    r13
0x1800df025  push    r14
0x1800df027  push    r15
0x1800df029  lea     rbp, [rsp-1Fh]
0x1800df02e  sub     rsp, 0B8h
0x1800df035  mov     rax, cs:__security_cookie
0x1800df03c  xor     rax, rsp
0x1800df03f  mov     [rbp+57h+var_50], rax
0x1800df043  mov     rax, [rdx]
0x1800df046  mov     r15, r8
0x1800df049  mov     r8, rdx
0x1800df04c  mov     [rbp+57h+var_70], rdx
0x1800df050  mov     rdi, rcx
0x1800df053  mov     [rbp+57h+var_68], r9
0x1800df057  xor     r13d, r13d
0x1800df05a  lea     rdx, [rbp+57h+pv]
0x1800df05e  mov     rax, [rax+18h]
0x1800df062  mov     rcx, r8
0x1800df065  mov     [rbp+57h+pv], r13
0x1800df069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df06e  mov     ebx, eax
0x1800df070  test    eax, eax
0x1800df072  js      loc_1800DF4AE
0x1800df078  mov     rcx, [rbp+57h+pv]
0x1800df07c  lea     r12d, [r13+1]
0x1800df080  mov     [rbp+57h+var_88], r13
0x1800df084  mov     [rbp+57h+var_7C], r12d
0x1800df088  mov     rcx, [rcx+8]; pv
0x1800df08c  call    cs:__imp_CoTaskMemFree
0x1800df092  mov     rcx, [rbp+57h+pv]
0x1800df096  mov     [rcx+8], r13
0x1800df09a  mov     rcx, [rbp+57h+pv]
0x1800df09e  mov     rcx, [rcx+20h]; pv
0x1800df0a2  call    cs:__imp_CoTaskMemFree
0x1800df0a8  mov     rax, [rbp+57h+pv]
0x1800df0ac  mov     [rax+20h], r13
0x1800df0b0  mov     rcx, [rbp+57h+pv]
0x1800df0b4  mov     rcx, [rcx+28h]; pv
0x1800df0b8  call    cs:__imp_CoTaskMemFree
0x1800df0be  mov     rax, [rbp+57h+pv]
0x1800df0c2  mov     [rax+28h], r13
0x1800df0c6  mov     edx, [rdi+1D4h]
0x1800df0cc  cmp     edx, 2
0x1800df0cf  jnb     short loc_1800DF0DE
0x1800df0d1  mov     r14d, r13d
0x1800df0d4  mov     ebx, 8000FFFFh
0x1800df0d9  jmp     loc_1800DF391
0x1800df0de  jbe     short loc_1800DF10B
0x1800df0e0  mov     rax, qword ptr cs:xmmword_180121350
0x1800df0e7  lea     r13, [rdi+1D8h]
0x1800df0ee  mov     rcx, [r13+0]
0x1800df0f2  sub     rax, [rcx+40h]
0x1800df0f6  jnz     short loc_1800DF103
0x1800df0f8  mov     rax, qword ptr cs:xmmword_180121350+8
0x1800df0ff  sub     rax, [rcx+48h]
0x1800df103  test    rax, rax
0x1800df106  jz      short loc_1800DF119
0x1800df108  xor     r13d, r13d
0x1800df10b  mov     r12d, r13d
0x1800df10e  mov     [rbp+57h+var_7C], r13d
0x1800df112  lea     r13, [rdi+1D8h]
0x1800df119  mov     eax, cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A; CInkCollectorProfileData g_CollectorProfileData
0x1800df11f  neg     eax
0x1800df121  mov     eax, r12d
0x1800df124  sbb     ecx, ecx
0x1800df126  xor     eax, 1
0x1800df129  and     ecx, 2
0x1800df12c  add     eax, edx
0x1800df12e  add     eax, ecx
0x1800df130  mov     ecx, eax
0x1800df132  mov     [rbp+57h+var_80], eax
0x1800df135  mov     eax, 10h
0x1800df13a  mul     rcx
0x1800df13d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800df144  cmovb   rax, rcx
0x1800df148  mov     rcx, rax; unsigned __int64
0x1800df14b  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800df150  mov     r14, rax
0x1800df153  test    rax, rax
0x1800df156  jnz     short loc_1800DF165
0x1800df158  mov     ebx, 8007000Eh
0x1800df15d  xor     r13d, r13d
0x1800df160  jmp     loc_1800DF391
0x1800df165  mov     rax, [r13+0]
0x1800df169  mov     esi, 3
0x1800df16e  add     r12d, 2
0x1800df172  movups  xmm0, xmmword ptr [rax]
0x1800df175  movdqu  xmmword ptr [r14], xmm0
0x1800df17a  mov     rax, [r13+0]
0x1800df17e  movups  xmm1, xmmword ptr [rax+20h]
0x1800df182  movdqu  xmmword ptr [r14+10h], xmm1
0x1800df188  movaps  xmm0, cs:xmmword_180121350
0x1800df18f  movdqu  xmmword ptr [r14+20h], xmm0
0x1800df195  cmp     r12d, [rdi+1D4h]
0x1800df19c  jnb     short loc_1800DF202
0x1800df19e  mov     r9, [rbp+57h+var_70]
0x1800df1a2  lea     r8, [rbp+57h+var_60]
0x1800df1a6  xorps   xmm0, xmm0
0x1800df1a9  mov     edx, r12d
0x1800df1ac  shl     rdx, 5
0x1800df1b0  mov     [rbp+57h+var_78], rdx
0x1800df1b4  mov     rcx, [r9]
0x1800df1b7  add     rdx, [r13+0]
0x1800df1bb  movups  [rbp+57h+var_60], xmm0
0x1800df1bf  mov     rax, [rcx+40h]
0x1800df1c3  mov     rcx, r9
0x1800df1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df1cb  mov     ebx, eax
0x1800df1cd  test    eax, eax
0x1800df1cf  jnz     loc_1800DF27A
0x1800df1d5  cmp     esi, [rbp+57h+var_80]
0x1800df1d8  jnb     short loc_1800DF1F6
0x1800df1da  mov     rax, [r13+0]
0x1800df1de  mov     rdx, [rbp+57h+var_78]
0x1800df1e2  mov     ecx, esi
0x1800df1e4  add     rcx, rcx
0x1800df1e7  movups  xmm0, xmmword ptr [rdx+rax]
0x1800df1eb  movdqu  xmmword ptr [r14+rcx*8], xmm0
0x1800df1f1  jmp     loc_1800DF2C7
0x1800df1f6  mov     ebx, 8000FFFFh
0x1800df1fb  inc     r12d
0x1800df1fe  test    ebx, ebx
0x1800df200  jns     short loc_1800DF195
0x1800df202  mov     eax, [rbp+57h+var_80]
0x1800df205  xor     r13d, r13d
0x1800df208  cmp     cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A, r13d; CInkCollectorProfileData g_CollectorProfileData
0x1800df20f  jz      short loc_1800DF23F
0x1800df211  lea     ecx, [rsi+1]
0x1800df214  cmp     ecx, eax
0x1800df216  jnb     short loc_1800DF23F
0x1800df218  movups  xmm0, xmmword ptr cs:GUID_PEN_TIMESTAMP1.Data1
0x1800df21f  mov     eax, esi
0x1800df221  add     rax, rax
0x1800df224  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800df22a  mov     eax, ecx
0x1800df22c  movups  xmm0, xmmword ptr cs:GUID_PEN_TIMESTAMP2.Data1
0x1800df233  add     rax, rax
0x1800df236  add     esi, 2
0x1800df239  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800df23f  mov     rax, [rbp+57h+pv]
0x1800df243  mov     [rax], esi
0x1800df245  mov     rax, [rbp+57h+pv]
0x1800df249  mov     [rax+8], r14
0x1800df24d  test    ebx, ebx
0x1800df24f  js      loc_1800DF38D
0x1800df255  mov     ecx, [rdi+13Ch]
0x1800df25b  mov     r8d, 80000000h
0x1800df261  cmp     ecx, r8d
0x1800df264  jnz     short loc_1800DF2DB
0x1800df266  mov     ecx, 204h
0x1800df26b  cmp     [rdi+140h], r8d
0x1800df272  jz      loc_1800DF2F9
0x1800df278  jmp     short loc_1800DF2E2
0x1800df27a  cmp     eax, 8004021Bh
0x1800df27f  jnz     loc_1800DF1FB
0x1800df285  mov     rcx, [r13+0]
0x1800df289  xor     ebx, ebx
0x1800df28b  mov     rdx, [rbp+57h+var_78]
0x1800df28f  mov     rax, cs:qword_180121360
0x1800df296  sub     rax, [rdx+rcx]
0x1800df29a  jnz     short loc_1800DF2A8
0x1800df29c  mov     rax, cs:qword_180121368
0x1800df2a3  sub     rax, [rdx+rcx+8]
0x1800df2a8  test    rax, rax
0x1800df2ab  jnz     loc_1800DF1FB
0x1800df2b1  mov     eax, [rbp+57h+var_80]
0x1800df2b4  cmp     esi, eax
0x1800df2b6  jnb     short loc_1800DF2D1
0x1800df2b8  movups  xmm0, xmmword ptr [rdx+rcx]
0x1800df2bc  mov     eax, esi
0x1800df2be  add     rax, rax
0x1800df2c1  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800df2c7  inc     esi
0x1800df2c9  inc     r12d
0x1800df2cc  jmp     loc_1800DF195
0x1800df2d1  mov     ebx, 8000FFFFh
0x1800df2d6  jmp     loc_1800DF205
0x1800df2db  mov     rax, [rbp+57h+pv]
0x1800df2df  mov     [rax+30h], ecx
0x1800df2e2  mov     edx, [rdi+140h]
0x1800df2e8  mov     ecx, 205h
0x1800df2ed  cmp     edx, r8d
0x1800df2f0  jz      short loc_1800DF2F9
0x1800df2f2  mov     rax, [rbp+57h+pv]
0x1800df2f6  mov     [rax+34h], edx
0x1800df2f9  mov     r9d, ecx
0x1800df2fc  or      r9d, 10h
0x1800df300  cmp     dword ptr [rdi+138h], 1
0x1800df307  cmovnz  r9d, ecx
0x1800df30b  cmp     cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A, r13d; CInkCollectorProfileData g_CollectorProfileData
0x1800df312  jz      short loc_1800DF319
0x1800df314  bts     r9d, 8
0x1800df319  mov     r11, [rbp+57h+var_70]
0x1800df31d  mov     rax, [r11]
0x1800df320  mov     r10, [rax+20h]
0x1800df324  mov     rax, [rdi+210h]
0x1800df32b  lea     rcx, [rax+40h]
0x1800df32f  neg     rax
0x1800df332  lea     rax, [rdi+300h]
0x1800df339  sbb     rdx, rdx
0x1800df33c  and     rdx, rcx
0x1800df33f  lea     rcx, [r15+8]
0x1800df343  cmp     dword ptr [rdi+354h], 1
0x1800df34a  jz      short loc_1800DF350
0x1800df34c  lea     rax, [rdi+38h]
0x1800df350  mov     r8, [rbp+57h+var_68]
0x1800df354  mov     [rsp+0F0h+var_A8], rdx
0x1800df359  lea     rdx, [rbp+57h+var_88]
0x1800df35d  mov     [rsp+0F0h+var_B0], rdx
0x1800df362  mov     rdx, [rax]
0x1800df365  mov     rax, r10
0x1800df368  mov     [rsp+0F0h+var_B8], rcx
0x1800df36d  mov     rcx, [rbp+57h+pv]
0x1800df371  mov     [rsp+0F0h+var_C0], r15
0x1800df376  mov     [rsp+0F0h+var_C8], 2
0x1800df37e  mov     [rsp+0F0h+var_D0], rcx
0x1800df383  mov     rcx, r11
0x1800df386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df38b  mov     ebx, eax
0x1800df38d  mov     r12d, [rbp+57h+var_7C]
0x1800df391  mov     rcx, [rbp+57h+pv]
0x1800df395  mov     rcx, [rcx+18h]; pv
0x1800df399  call    cs:__imp_CoTaskMemFree
0x1800df39f  mov     rcx, [rbp+57h+pv]; pv
0x1800df3a3  call    cs:__imp_CoTaskMemFree
0x1800df3a9  test    r14, r14
0x1800df3ac  jz      short loc_1800DF3B6
0x1800df3ae  mov     rcx, r14; void *
0x1800df3b1  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800df3b6  test    ebx, ebx
0x1800df3b8  js      loc_1800DF4AE
0x1800df3be  mov     rcx, [rbp+57h+var_88]
0x1800df3c2  mov     rax, [rcx+18h]
0x1800df3c6  mov     [r15+10h], rax
0x1800df3ca  mov     [rcx+18h], r13
0x1800df3ce  mov     rax, [rbp+57h+var_88]
0x1800df3d2  mov     [rax+10h], r13d
0x1800df3d6  mov     rcx, [rbp+57h+var_88]
0x1800df3da  mov     rsi, [rcx+8]
0x1800df3de  test    r12d, r12d
0x1800df3e1  jnz     short loc_1800DF41E
0x1800df3e3  movups  xmm0, xmmword ptr [rsi+20h]
0x1800df3e7  movups  xmmword ptr [rsi+40h], xmm0
0x1800df3eb  movups  xmm1, xmmword ptr [rsi+30h]
0x1800df3ef  movups  xmmword ptr [rsi+50h], xmm1
0x1800df3f3  mov     rax, [rbp+57h+var_88]
0x1800df3f7  mov     rcx, [rax+8]
0x1800df3fb  movups  xmm0, xmmword ptr [rcx]
0x1800df3fe  movups  xmmword ptr [rcx+20h], xmm0
0x1800df402  movups  xmm1, xmmword ptr [rcx+10h]
0x1800df406  movups  xmmword ptr [rcx+30h], xmm1
0x1800df40a  mov     rax, [rbp+57h+var_88]
0x1800df40e  add     qword ptr [rax+8], 20h ; ' '
0x1800df413  mov     rax, [rbp+57h+var_88]
0x1800df417  dec     dword ptr [rax+4]
0x1800df41a  mov     rcx, [rbp+57h+var_88]
0x1800df41e  mov     eax, [rcx+4]
0x1800df421  shl     eax, 2
0x1800df424  mov     [rcx], eax
0x1800df426  mov     rcx, [rdi+220h]
0x1800df42d  mov     r8, [rbp+57h+var_88]
0x1800df431  mov     edx, [r15+8]
0x1800df435  mov     rax, [rcx]
0x1800df438  mov     rax, [rax+38h]
0x1800df43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df441  mov     rcx, rsi; pv
0x1800df444  mov     ebx, eax
0x1800df446  call    cs:__imp_CoTaskMemFree
0x1800df44c  mov     rcx, [rbp+57h+var_88]; pv
0x1800df450  call    cs:__imp_CoTaskMemFree
0x1800df456  test    ebx, ebx
0x1800df458  js      short loc_1800DF488
0x1800df45a  mov     rdx, [r15]; struct ITabletContext *
0x1800df45d  xor     r8d, r8d; int
0x1800df460  mov     rcx, rdi; this
0x1800df463  call    ?_UpdateTabletToInkToDisplayMapping@CInkOverlay@@AEAAJPEAUITabletContext@@H@Z; CInkOverlay::_UpdateTabletToInkToDisplayMapping(ITabletContext *,int)
0x1800df468  mov     ebx, eax
0x1800df46a  test    eax, eax
0x1800df46c  js      short loc_1800DF488
0x1800df46e  mov     rcx, [r15]
0x1800df471  mov     edx, 1
0x1800df476  mov     rax, [rcx]
0x1800df479  mov     rax, [rax+38h]
0x1800df47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df482  mov     ebx, eax
0x1800df484  test    eax, eax
0x1800df486  jns     short loc_1800DF4AE
0x1800df488  mov     rcx, [r15]
0x1800df48b  mov     rax, [rcx]
0x1800df48e  mov     rax, [rax+10h]
0x1800df492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df497  mov     rcx, [r15+10h]; pv
0x1800df49b  call    cs:__imp_CoTaskMemFree
0x1800df4a1  xorps   xmm0, xmm0
0x1800df4a4  xor     eax, eax
  ... truncated ...
```
