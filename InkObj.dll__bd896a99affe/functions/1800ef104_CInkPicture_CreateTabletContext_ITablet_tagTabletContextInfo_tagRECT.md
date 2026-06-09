# CInkPicture::_CreateTabletContext(ITablet *,tagTabletContextInfo *,tagRECT *)

- ea: `0x1800ef104`
- end: `0x1800ef5a5`
- name: `?_CreateTabletContext@CInkPicture@@AEAAJPEAUITablet@@PEAUtagTabletContextInfo@@PEAUtagRECT@@@Z`
- size: `1185`
- prototype: `__int64 __fastcall(CInkPicture *__hidden this, struct ITablet *, struct tagTabletContextInfo *, struct tagRECT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800edc00`
- `0x1800eeadc`

## callees

- `0x180002740`
- `0x180010350`
- `0x1800ef104`
- `0x1800f3a28`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef174`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef18a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef1a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef46e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef570`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef174`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef18a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef1a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef46e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ef570`

## pseudocode

```c
__int64 __fastcall CInkPicture::_CreateTabletContext(
        CInkPicture *this,
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
  unsigned int v16; // edi
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
  _QWORD *v29; // rcx
  _DWORD *v30; // rcx
  _OWORD *v31; // rdi
  _OWORD *v32; // rcx
  LPVOID pv; // [rsp+60h] [rbp-39h] BYREF
  LPVOID v35; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v36; // [rsp+70h] [rbp-29h]
  int v37; // [rsp+74h] [rbp-25h]
  __int64 v38; // [rsp+78h] [rbp-21h]
  struct ITablet *v39; // [rsp+80h] [rbp-19h]
  struct tagRECT *v40; // [rsp+88h] [rbp-11h]
  __int128 v41; // [rsp+90h] [rbp-9h] BYREF

  v4 = *(_QWORD *)a2;
  v39 = a2;
  v40 = a4;
  v7 = *(__int64 (__fastcall **)(struct ITablet *, LPVOID *))(v4 + 24);
  pv = 0;
  updated = v7(a2, &pv);
  if ( updated < 0 )
    return (unsigned int)updated;
  v9 = 1;
  v35 = 0;
  v37 = 1;
  CoTaskMemFree(*((LPVOID *)pv + 1));
  *((_QWORD *)pv + 1) = 0;
  CoTaskMemFree(*((LPVOID *)pv + 4));
  *((_QWORD *)pv + 4) = 0;
  CoTaskMemFree(*((LPVOID *)pv + 5));
  *((_QWORD *)pv + 5) = 0;
  v10 = *((_DWORD *)this + 173);
  if ( v10 < 2 )
  {
    v11 = 0;
    updated = -2147418113;
    goto LABEL_43;
  }
  if ( v10 <= 2 )
    goto LABEL_8;
  v12 = (_OWORD **)((char *)this + 696);
  v13 = *((_QWORD *)this + 87);
  v14 = 0x4CF7AFE76E0E07BFLL - *(_QWORD *)(v13 + 64);
  if ( *(_QWORD *)(v13 + 64) == 0x4CF7AFE76E0E07BFLL )
    v14 = 0x1884204664AFD187LL - *(_QWORD *)(v13 + 72);
  if ( v14 )
  {
LABEL_8:
    v9 = 0;
    v37 = 0;
    v12 = (_OWORD **)((char *)this + 696);
  }
  v36 = (*(_DWORD *)&g_CollectorProfileData != 0 ? 2 : 0) + v10 + (v9 ^ 1);
  v15 = WinMalloc(saturated_mul(v36, 0x10u));
  v11 = v15;
  if ( !v15 )
  {
    updated = -2147024882;
    goto LABEL_43;
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
      if ( v17 >= *((_DWORD *)this + 173) )
      {
LABEL_18:
        v21 = v36;
        goto LABEL_19;
      }
      v38 = 32LL * v17;
      v18 = *(_QWORD *)v39;
      v19 = &(*v12)[(unsigned __int64)v38 / 0x10];
      v41 = 0;
      v20 = (*(__int64 (__fastcall **)(struct ITablet *, _OWORD *, __int128 *))(v18 + 64))(v39, v19, &v41);
      updated = v20;
      if ( v20 )
        break;
      if ( v16 < v36 )
      {
        v11[v16] = (*v12)[(unsigned __int64)v38 / 0x10];
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
    v26 = 0x45D1FED3436510C5LL - *(_QWORD *)&(*v12)[(unsigned __int64)v38 / 0x10];
    if ( *(_QWORD *)&(*v12)[(unsigned __int64)v38 / 0x10] == 0x45D1FED3436510C5LL )
      v26 = 0x9D827AEAD371768BuLL - *((_QWORD *)&v25[(unsigned __int64)v38 / 0x10] + 1);
    if ( v26 )
      goto LABEL_17;
    v21 = v36;
    if ( v16 >= v36 )
      break;
    v11[v16] = v25[(unsigned __int64)v38 / 0x10];
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
    v23 = *((_DWORD *)this + 135);
    if ( v23 == 0x80000000 )
    {
      v24 = 516;
      if ( *((_DWORD *)this + 136) != 0x80000000 )
        goto LABEL_35;
    }
    else
    {
      *((_DWORD *)pv + 12) = v23;
LABEL_35:
      v27 = *((_DWORD *)this + 136);
      v24 = 517;
      if ( v27 != 0x80000000 )
        *((_DWORD *)pv + 13) = v27;
    }
    v28 = v24 | 0x10;
    if ( *((_DWORD *)this + 134) != 1 )
      v28 = v24;
    if ( *(_DWORD *)&g_CollectorProfileData )
      LODWORD(v28) = v28 | 0x100;
    updated = (*(__int64 (__fastcall **)(struct ITablet *, _QWORD, struct tagRECT *, __int64, LPVOID, int, struct tagTabletContextInfo *, char *, LPVOID *, __int64))(*(_QWORD *)v39 + 32LL))(
                v39,
                *((_QWORD *)this + 21),
                v40,
                v28,
                pv,
                2,
                a3,
                (char *)a3 + 8,
                &v35,
                (*((_QWORD *)this + 94) + 64LL) & -(__int64)(*((_QWORD *)this + 94) != 0));
  }
  v9 = v37;
LABEL_43:
  CoTaskMemFree(*((LPVOID *)pv + 3));
  CoTaskMemFree(pv);
  if ( v11 )
    WinFree(v11);
  if ( updated >= 0 )
  {
    v29 = v35;
    *((_QWORD *)a3 + 2) = *((_QWORD *)v35 + 3);
    v29[3] = 0;
    *((_DWORD *)v35 + 4) = 0;
    v30 = v35;
    v31 = (_OWORD *)*((_QWORD *)v35 + 1);
    if ( !v9 )
    {
      v31[4] = v31[2];
      v31[5] = v31[3];
      v32 = (_OWORD *)*((_QWORD *)v35 + 1);
      v32[2] = *v32;
      v32[3] = v32[1];
      *((_QWORD *)v35 + 1) += 32LL;
      --*((_DWORD *)v35 + 1);
      v30 = v35;
    }
    *v30 = 4 * v30[1];
    updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID))(**((_QWORD **)this + 96) + 56LL))(
                *((_QWORD *)this + 96),
                *((unsigned int *)a3 + 2),
                v35);
    CoTaskMemFree(v31);
    CoTaskMemFree(v35);
    if ( updated < 0
      || (updated = CInkPicture::_UpdateTabletToInkToDisplayMapping(this, *(struct ITabletContext **)a3, 0), updated < 0)
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
0x1800ef104  push    rbp
0x1800ef106  push    rbx
0x1800ef107  push    rsi
0x1800ef108  push    rdi
0x1800ef109  push    r12
0x1800ef10b  push    r13
0x1800ef10d  push    r14
0x1800ef10f  push    r15
0x1800ef111  lea     rbp, [rsp-1Fh]
0x1800ef116  sub     rsp, 0B8h
0x1800ef11d  mov     rax, cs:__security_cookie
0x1800ef124  xor     rax, rsp
0x1800ef127  mov     [rbp+57h+var_50], rax
0x1800ef12b  mov     rax, [rdx]
0x1800ef12e  mov     r15, r8
0x1800ef131  mov     r8, rdx
0x1800ef134  mov     [rbp+57h+var_70], rdx
0x1800ef138  mov     rsi, rcx
0x1800ef13b  mov     [rbp+57h+var_68], r9
0x1800ef13f  xor     r13d, r13d
0x1800ef142  lea     rdx, [rbp+57h+pv]
0x1800ef146  mov     rax, [rax+18h]
0x1800ef14a  mov     rcx, r8
0x1800ef14d  mov     [rbp+57h+pv], r13
0x1800ef151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef156  mov     ebx, eax
0x1800ef158  test    eax, eax
0x1800ef15a  js      loc_1800EF583
0x1800ef160  mov     rcx, [rbp+57h+pv]
0x1800ef164  lea     r12d, [r13+1]
0x1800ef168  mov     [rbp+57h+var_88], r13
0x1800ef16c  mov     [rbp+57h+var_7C], r12d
0x1800ef170  mov     rcx, [rcx+8]; pv
0x1800ef174  call    cs:__imp_CoTaskMemFree
0x1800ef17a  mov     rcx, [rbp+57h+pv]
0x1800ef17e  mov     [rcx+8], r13
0x1800ef182  mov     rcx, [rbp+57h+pv]
0x1800ef186  mov     rcx, [rcx+20h]; pv
0x1800ef18a  call    cs:__imp_CoTaskMemFree
0x1800ef190  mov     rax, [rbp+57h+pv]
0x1800ef194  mov     [rax+20h], r13
0x1800ef198  mov     rcx, [rbp+57h+pv]
0x1800ef19c  mov     rcx, [rcx+28h]; pv
0x1800ef1a0  call    cs:__imp_CoTaskMemFree
0x1800ef1a6  mov     rax, [rbp+57h+pv]
0x1800ef1aa  mov     [rax+28h], r13
0x1800ef1ae  mov     edx, [rsi+2B4h]
0x1800ef1b4  cmp     edx, 2
0x1800ef1b7  jnb     short loc_1800EF1C6
0x1800ef1b9  mov     r14d, r13d
0x1800ef1bc  mov     ebx, 8000FFFFh
0x1800ef1c1  jmp     loc_1800EF466
0x1800ef1c6  jbe     short loc_1800EF1F3
0x1800ef1c8  mov     rax, qword ptr cs:xmmword_180121350
0x1800ef1cf  lea     r13, [rsi+2B8h]
0x1800ef1d6  mov     rcx, [r13+0]
0x1800ef1da  sub     rax, [rcx+40h]
0x1800ef1de  jnz     short loc_1800EF1EB
0x1800ef1e0  mov     rax, qword ptr cs:xmmword_180121350+8
0x1800ef1e7  sub     rax, [rcx+48h]
0x1800ef1eb  test    rax, rax
0x1800ef1ee  jz      short loc_1800EF201
0x1800ef1f0  xor     r13d, r13d
0x1800ef1f3  mov     r12d, r13d
0x1800ef1f6  mov     [rbp+57h+var_7C], r13d
0x1800ef1fa  lea     r13, [rsi+2B8h]
0x1800ef201  mov     eax, cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A; CInkCollectorProfileData g_CollectorProfileData
0x1800ef207  neg     eax
0x1800ef209  mov     eax, r12d
0x1800ef20c  sbb     ecx, ecx
0x1800ef20e  xor     eax, 1
0x1800ef211  and     ecx, 2
0x1800ef214  add     eax, edx
0x1800ef216  add     eax, ecx
0x1800ef218  mov     ecx, eax
0x1800ef21a  mov     [rbp+57h+var_80], eax
0x1800ef21d  mov     eax, 10h
0x1800ef222  mul     rcx
0x1800ef225  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ef22c  cmovb   rax, rcx
0x1800ef230  mov     rcx, rax; unsigned __int64
0x1800ef233  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800ef238  mov     r14, rax
0x1800ef23b  test    rax, rax
0x1800ef23e  jnz     short loc_1800EF24D
0x1800ef240  mov     ebx, 8007000Eh
0x1800ef245  xor     r13d, r13d
0x1800ef248  jmp     loc_1800EF466
0x1800ef24d  mov     rax, [r13+0]
0x1800ef251  mov     edi, 3
0x1800ef256  add     r12d, 2
0x1800ef25a  movups  xmm0, xmmword ptr [rax]
0x1800ef25d  movdqu  xmmword ptr [r14], xmm0
0x1800ef262  mov     rax, [r13+0]
0x1800ef266  movups  xmm1, xmmword ptr [rax+20h]
0x1800ef26a  movdqu  xmmword ptr [r14+10h], xmm1
0x1800ef270  movaps  xmm0, cs:xmmword_180121350
0x1800ef277  movdqu  xmmword ptr [r14+20h], xmm0
0x1800ef27d  cmp     r12d, [rsi+2B4h]
0x1800ef284  jnb     short loc_1800EF2EA
0x1800ef286  mov     r9, [rbp+57h+var_70]
0x1800ef28a  lea     r8, [rbp+57h+var_60]
0x1800ef28e  xorps   xmm0, xmm0
0x1800ef291  mov     edx, r12d
0x1800ef294  shl     rdx, 5
0x1800ef298  mov     [rbp+57h+var_78], rdx
0x1800ef29c  mov     rcx, [r9]
0x1800ef29f  add     rdx, [r13+0]
0x1800ef2a3  movups  [rbp+57h+var_60], xmm0
0x1800ef2a7  mov     rax, [rcx+40h]
0x1800ef2ab  mov     rcx, r9
0x1800ef2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef2b3  mov     ebx, eax
0x1800ef2b5  test    eax, eax
0x1800ef2b7  jnz     loc_1800EF362
0x1800ef2bd  cmp     edi, [rbp+57h+var_80]
0x1800ef2c0  jnb     short loc_1800EF2DE
0x1800ef2c2  mov     rax, [r13+0]
0x1800ef2c6  mov     rdx, [rbp+57h+var_78]
0x1800ef2ca  mov     ecx, edi
0x1800ef2cc  add     rcx, rcx
0x1800ef2cf  movups  xmm0, xmmword ptr [rdx+rax]
0x1800ef2d3  movdqu  xmmword ptr [r14+rcx*8], xmm0
0x1800ef2d9  jmp     loc_1800EF3AF
0x1800ef2de  mov     ebx, 8000FFFFh
0x1800ef2e3  inc     r12d
0x1800ef2e6  test    ebx, ebx
0x1800ef2e8  jns     short loc_1800EF27D
0x1800ef2ea  mov     eax, [rbp+57h+var_80]
0x1800ef2ed  xor     r13d, r13d
0x1800ef2f0  cmp     cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A, r13d; CInkCollectorProfileData g_CollectorProfileData
0x1800ef2f7  jz      short loc_1800EF327
0x1800ef2f9  lea     ecx, [rdi+1]
0x1800ef2fc  cmp     ecx, eax
0x1800ef2fe  jnb     short loc_1800EF327
0x1800ef300  movups  xmm0, xmmword ptr cs:GUID_PEN_TIMESTAMP1.Data1
0x1800ef307  mov     eax, edi
0x1800ef309  add     rax, rax
0x1800ef30c  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800ef312  mov     eax, ecx
0x1800ef314  movups  xmm0, xmmword ptr cs:GUID_PEN_TIMESTAMP2.Data1
0x1800ef31b  add     rax, rax
0x1800ef31e  add     edi, 2
0x1800ef321  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800ef327  mov     rax, [rbp+57h+pv]
0x1800ef32b  mov     [rax], edi
0x1800ef32d  mov     rax, [rbp+57h+pv]
0x1800ef331  mov     [rax+8], r14
0x1800ef335  test    ebx, ebx
0x1800ef337  js      loc_1800EF462
0x1800ef33d  mov     ecx, [rsi+21Ch]
0x1800ef343  mov     r8d, 80000000h
0x1800ef349  cmp     ecx, r8d
0x1800ef34c  jnz     short loc_1800EF3C3
0x1800ef34e  mov     ecx, 204h
0x1800ef353  cmp     [rsi+220h], r8d
0x1800ef35a  jz      loc_1800EF3E1
0x1800ef360  jmp     short loc_1800EF3CA
0x1800ef362  cmp     eax, 8004021Bh
0x1800ef367  jnz     loc_1800EF2E3
0x1800ef36d  mov     rcx, [r13+0]
0x1800ef371  xor     ebx, ebx
0x1800ef373  mov     rdx, [rbp+57h+var_78]
0x1800ef377  mov     rax, cs:qword_180121360
0x1800ef37e  sub     rax, [rdx+rcx]
0x1800ef382  jnz     short loc_1800EF390
0x1800ef384  mov     rax, cs:qword_180121368
0x1800ef38b  sub     rax, [rdx+rcx+8]
0x1800ef390  test    rax, rax
0x1800ef393  jnz     loc_1800EF2E3
0x1800ef399  mov     eax, [rbp+57h+var_80]
0x1800ef39c  cmp     edi, eax
0x1800ef39e  jnb     short loc_1800EF3B9
0x1800ef3a0  movups  xmm0, xmmword ptr [rdx+rcx]
0x1800ef3a4  mov     eax, edi
0x1800ef3a6  add     rax, rax
0x1800ef3a9  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800ef3af  inc     edi
0x1800ef3b1  inc     r12d
0x1800ef3b4  jmp     loc_1800EF27D
0x1800ef3b9  mov     ebx, 8000FFFFh
0x1800ef3be  jmp     loc_1800EF2ED
0x1800ef3c3  mov     rax, [rbp+57h+pv]
0x1800ef3c7  mov     [rax+30h], ecx
0x1800ef3ca  mov     edx, [rsi+220h]
0x1800ef3d0  mov     ecx, 205h
0x1800ef3d5  cmp     edx, r8d
0x1800ef3d8  jz      short loc_1800EF3E1
0x1800ef3da  mov     rax, [rbp+57h+pv]
0x1800ef3de  mov     [rax+34h], edx
0x1800ef3e1  mov     r9d, ecx
0x1800ef3e4  or      r9d, 10h
0x1800ef3e8  cmp     dword ptr [rsi+218h], 1
0x1800ef3ef  cmovnz  r9d, ecx
0x1800ef3f3  cmp     cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A, r13d; CInkCollectorProfileData g_CollectorProfileData
0x1800ef3fa  jz      short loc_1800EF401
0x1800ef3fc  bts     r9d, 8
0x1800ef401  mov     rcx, [rsi+2F0h]
0x1800ef408  mov     r11, [rbp+57h+var_70]
0x1800ef40c  mov     r8, [rbp+57h+var_68]
0x1800ef410  lea     rax, [rcx+40h]
0x1800ef414  neg     rcx
0x1800ef417  mov     r10, [r11]
0x1800ef41a  lea     rcx, [r15+8]
0x1800ef41e  sbb     rdx, rdx
0x1800ef421  and     rdx, rax
0x1800ef424  lea     rax, [rbp+57h+var_88]
0x1800ef428  mov     [rsp+0F0h+var_A8], rdx
0x1800ef42d  mov     rdx, [rsi+0A8h]
0x1800ef434  mov     [rsp+0F0h+var_B0], rax
0x1800ef439  mov     rax, [r10+20h]
0x1800ef43d  mov     [rsp+0F0h+var_B8], rcx
0x1800ef442  mov     rcx, [rbp+57h+pv]
0x1800ef446  mov     [rsp+0F0h+var_C0], r15
0x1800ef44b  mov     [rsp+0F0h+var_C8], 2
0x1800ef453  mov     [rsp+0F0h+var_D0], rcx
0x1800ef458  mov     rcx, r11
0x1800ef45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef460  mov     ebx, eax
0x1800ef462  mov     r12d, [rbp+57h+var_7C]
0x1800ef466  mov     rcx, [rbp+57h+pv]
0x1800ef46a  mov     rcx, [rcx+18h]; pv
0x1800ef46e  call    cs:__imp_CoTaskMemFree
0x1800ef474  mov     rcx, [rbp+57h+pv]; pv
0x1800ef478  call    cs:__imp_CoTaskMemFree
0x1800ef47e  test    r14, r14
0x1800ef481  jz      short loc_1800EF48B
0x1800ef483  mov     rcx, r14; void *
0x1800ef486  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800ef48b  test    ebx, ebx
0x1800ef48d  js      loc_1800EF583
0x1800ef493  mov     rcx, [rbp+57h+var_88]
0x1800ef497  mov     rax, [rcx+18h]
0x1800ef49b  mov     [r15+10h], rax
0x1800ef49f  mov     [rcx+18h], r13
0x1800ef4a3  mov     rax, [rbp+57h+var_88]
0x1800ef4a7  mov     [rax+10h], r13d
0x1800ef4ab  mov     rcx, [rbp+57h+var_88]
0x1800ef4af  mov     rdi, [rcx+8]
0x1800ef4b3  test    r12d, r12d
0x1800ef4b6  jnz     short loc_1800EF4F3
0x1800ef4b8  movups  xmm0, xmmword ptr [rdi+20h]
0x1800ef4bc  movups  xmmword ptr [rdi+40h], xmm0
0x1800ef4c0  movups  xmm1, xmmword ptr [rdi+30h]
0x1800ef4c4  movups  xmmword ptr [rdi+50h], xmm1
0x1800ef4c8  mov     rax, [rbp+57h+var_88]
0x1800ef4cc  mov     rcx, [rax+8]
0x1800ef4d0  movups  xmm0, xmmword ptr [rcx]
0x1800ef4d3  movups  xmmword ptr [rcx+20h], xmm0
0x1800ef4d7  movups  xmm1, xmmword ptr [rcx+10h]
0x1800ef4db  movups  xmmword ptr [rcx+30h], xmm1
0x1800ef4df  mov     rax, [rbp+57h+var_88]
0x1800ef4e3  add     qword ptr [rax+8], 20h ; ' '
0x1800ef4e8  mov     rax, [rbp+57h+var_88]
0x1800ef4ec  dec     dword ptr [rax+4]
0x1800ef4ef  mov     rcx, [rbp+57h+var_88]
0x1800ef4f3  mov     eax, [rcx+4]
0x1800ef4f6  shl     eax, 2
0x1800ef4f9  mov     [rcx], eax
0x1800ef4fb  mov     rcx, [rsi+300h]
0x1800ef502  mov     r8, [rbp+57h+var_88]
0x1800ef506  mov     edx, [r15+8]
0x1800ef50a  mov     rax, [rcx]
0x1800ef50d  mov     rax, [rax+38h]
0x1800ef511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef516  mov     rcx, rdi; pv
0x1800ef519  mov     ebx, eax
0x1800ef51b  call    cs:__imp_CoTaskMemFree
0x1800ef521  mov     rcx, [rbp+57h+var_88]; pv
0x1800ef525  call    cs:__imp_CoTaskMemFree
0x1800ef52b  test    ebx, ebx
0x1800ef52d  js      short loc_1800EF55D
0x1800ef52f  mov     rdx, [r15]; struct ITabletContext *
0x1800ef532  xor     r8d, r8d; int
0x1800ef535  mov     rcx, rsi; this
0x1800ef538  call    ?_UpdateTabletToInkToDisplayMapping@CInkPicture@@AEAAJPEAUITabletContext@@H@Z; CInkPicture::_UpdateTabletToInkToDisplayMapping(ITabletContext *,int)
0x1800ef53d  mov     ebx, eax
0x1800ef53f  test    eax, eax
0x1800ef541  js      short loc_1800EF55D
0x1800ef543  mov     rcx, [r15]
0x1800ef546  mov     edx, 1
0x1800ef54b  mov     rax, [rcx]
0x1800ef54e  mov     rax, [rax+38h]
0x1800ef552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef557  mov     ebx, eax
0x1800ef559  test    eax, eax
0x1800ef55b  jns     short loc_1800EF583
0x1800ef55d  mov     rcx, [r15]
0x1800ef560  mov     rax, [rcx]
0x1800ef563  mov     rax, [rax+10h]
0x1800ef567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef56c  mov     rcx, [r15+10h]; pv
0x1800ef570  call    cs:__imp_CoTaskMemFree
0x1800ef576  xorps   xmm0, xmm0
0x1800ef579  xor     eax, eax
0x1800ef57b  movups  xmmword ptr [r15], xmm0
0x1800ef57f  mov     [r15+10h], rax
0x1800ef583  mov     eax, ebx
0x1800ef585  mov     rcx, [rbp+57h+var_50]
0x1800ef589  xor     rcx, rsp; StackCookie
  ... truncated ...
```
