# CInkCollector::_CreateTabletContext(ITablet *,tagTabletContextInfo *,tagRECT *)

- ea: `0x1800b08b0`
- end: `0x1800b0d4e`
- name: `?_CreateTabletContext@CInkCollector@@AEAAJPEAUITablet@@PEAUtagTabletContextInfo@@PEAUtagRECT@@@Z`
- size: `1182`
- prototype: `__int64 __fastcall(CInkCollector *__hidden this, struct ITablet *, struct tagTabletContextInfo *, struct tagRECT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800af4f0`
- `0x1800b028c`

## callees

- `0x180002740`
- `0x180010350`
- `0x1800b08b0`
- `0x1800b358c`
- `0x180104f30`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b094c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0cc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0cce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0d19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0920`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0936`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b094c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0c21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0cc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0cce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b0d19`

## pseudocode

```c
__int64 __fastcall CInkCollector::_CreateTabletContext(
        CInkCollector *this,
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
  v10 = *((_DWORD *)this + 117);
  if ( v10 < 2 )
  {
    v11 = 0;
    updated = -2147418113;
    goto LABEL_43;
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
    v37 = 0;
    v12 = (_OWORD **)((char *)this + 472);
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
      if ( v17 >= *((_DWORD *)this + 117) )
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
    updated = (*(__int64 (__fastcall **)(struct ITablet *, _QWORD, struct tagRECT *, __int64, LPVOID, int, struct tagTabletContextInfo *, char *, LPVOID *, __int64))(*(_QWORD *)v39 + 32LL))(
                v39,
                *((_QWORD *)this + 7),
                v40,
                v28,
                pv,
                2,
                a3,
                (char *)a3 + 8,
                &v35,
                (*((_QWORD *)this + 66) + 64LL) & -(__int64)(*((_QWORD *)this + 66) != 0));
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
    updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID))(**((_QWORD **)this + 68) + 56LL))(
                *((_QWORD *)this + 68),
                *((unsigned int *)a3 + 2),
                v35);
    CoTaskMemFree(v31);
    CoTaskMemFree(v35);
    if ( updated < 0
      || (updated = CInkCollector::_UpdateTabletToInkToDisplayMapping(this, *(struct ITabletContext **)a3, 0),
          updated < 0)
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
0x1800b08b0  push    rbp
0x1800b08b2  push    rbx
0x1800b08b3  push    rsi
0x1800b08b4  push    rdi
0x1800b08b5  push    r12
0x1800b08b7  push    r13
0x1800b08b9  push    r14
0x1800b08bb  push    r15
0x1800b08bd  lea     rbp, [rsp-1Fh]
0x1800b08c2  sub     rsp, 0B8h
0x1800b08c9  mov     rax, cs:__security_cookie
0x1800b08d0  xor     rax, rsp
0x1800b08d3  mov     [rbp+57h+var_50], rax
0x1800b08d7  mov     rax, [rdx]
0x1800b08da  mov     r15, r8
0x1800b08dd  mov     r8, rdx
0x1800b08e0  mov     [rbp+57h+var_70], rdx
0x1800b08e4  mov     rsi, rcx
0x1800b08e7  mov     [rbp+57h+var_68], r9
0x1800b08eb  xor     r13d, r13d
0x1800b08ee  lea     rdx, [rbp+57h+pv]
0x1800b08f2  mov     rax, [rax+18h]
0x1800b08f6  mov     rcx, r8
0x1800b08f9  mov     [rbp+57h+pv], r13
0x1800b08fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0902  mov     ebx, eax
0x1800b0904  test    eax, eax
0x1800b0906  js      loc_1800B0D2C
0x1800b090c  mov     rcx, [rbp+57h+pv]
0x1800b0910  lea     r12d, [r13+1]
0x1800b0914  mov     [rbp+57h+var_88], r13
0x1800b0918  mov     [rbp+57h+var_7C], r12d
0x1800b091c  mov     rcx, [rcx+8]; pv
0x1800b0920  call    cs:__imp_CoTaskMemFree
0x1800b0926  mov     rcx, [rbp+57h+pv]
0x1800b092a  mov     [rcx+8], r13
0x1800b092e  mov     rcx, [rbp+57h+pv]
0x1800b0932  mov     rcx, [rcx+20h]; pv
0x1800b0936  call    cs:__imp_CoTaskMemFree
0x1800b093c  mov     rax, [rbp+57h+pv]
0x1800b0940  mov     [rax+20h], r13
0x1800b0944  mov     rcx, [rbp+57h+pv]
0x1800b0948  mov     rcx, [rcx+28h]; pv
0x1800b094c  call    cs:__imp_CoTaskMemFree
0x1800b0952  mov     rax, [rbp+57h+pv]
0x1800b0956  mov     [rax+28h], r13
0x1800b095a  mov     edx, [rsi+1D4h]
0x1800b0960  cmp     edx, 2
0x1800b0963  jnb     short loc_1800B0972
0x1800b0965  mov     r14d, r13d
0x1800b0968  mov     ebx, 8000FFFFh
0x1800b096d  jmp     loc_1800B0C0F
0x1800b0972  jbe     short loc_1800B099F
0x1800b0974  mov     rax, qword ptr cs:xmmword_180121350
0x1800b097b  lea     r13, [rsi+1D8h]
0x1800b0982  mov     rcx, [r13+0]
0x1800b0986  sub     rax, [rcx+40h]
0x1800b098a  jnz     short loc_1800B0997
0x1800b098c  mov     rax, qword ptr cs:xmmword_180121350+8
0x1800b0993  sub     rax, [rcx+48h]
0x1800b0997  test    rax, rax
0x1800b099a  jz      short loc_1800B09AD
0x1800b099c  xor     r13d, r13d
0x1800b099f  mov     r12d, r13d
0x1800b09a2  mov     [rbp+57h+var_7C], r13d
0x1800b09a6  lea     r13, [rsi+1D8h]
0x1800b09ad  mov     eax, cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A; CInkCollectorProfileData g_CollectorProfileData
0x1800b09b3  neg     eax
0x1800b09b5  mov     eax, r12d
0x1800b09b8  sbb     ecx, ecx
0x1800b09ba  xor     eax, 1
0x1800b09bd  and     ecx, 2
0x1800b09c0  add     eax, edx
0x1800b09c2  add     eax, ecx
0x1800b09c4  mov     ecx, eax
0x1800b09c6  mov     [rbp+57h+var_80], eax
0x1800b09c9  mov     eax, 10h
0x1800b09ce  mul     rcx
0x1800b09d1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b09d8  cmovb   rax, rcx
0x1800b09dc  mov     rcx, rax; unsigned __int64
0x1800b09df  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800b09e4  mov     r14, rax
0x1800b09e7  test    rax, rax
0x1800b09ea  jnz     short loc_1800B09F9
0x1800b09ec  mov     ebx, 8007000Eh
0x1800b09f1  xor     r13d, r13d
0x1800b09f4  jmp     loc_1800B0C0F
0x1800b09f9  mov     rax, [r13+0]
0x1800b09fd  mov     edi, 3
0x1800b0a02  add     r12d, 2
0x1800b0a06  movups  xmm0, xmmword ptr [rax]
0x1800b0a09  movdqu  xmmword ptr [r14], xmm0
0x1800b0a0e  mov     rax, [r13+0]
0x1800b0a12  movups  xmm1, xmmword ptr [rax+20h]
0x1800b0a16  movdqu  xmmword ptr [r14+10h], xmm1
0x1800b0a1c  movaps  xmm0, cs:xmmword_180121350
0x1800b0a23  movdqu  xmmword ptr [r14+20h], xmm0
0x1800b0a29  cmp     r12d, [rsi+1D4h]
0x1800b0a30  jnb     short loc_1800B0A96
0x1800b0a32  mov     r9, [rbp+57h+var_70]
0x1800b0a36  lea     r8, [rbp+57h+var_60]
0x1800b0a3a  xorps   xmm0, xmm0
0x1800b0a3d  mov     edx, r12d
0x1800b0a40  shl     rdx, 5
0x1800b0a44  mov     [rbp+57h+var_78], rdx
0x1800b0a48  mov     rcx, [r9]
0x1800b0a4b  add     rdx, [r13+0]
0x1800b0a4f  movups  [rbp+57h+var_60], xmm0
0x1800b0a53  mov     rax, [rcx+40h]
0x1800b0a57  mov     rcx, r9
0x1800b0a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a5f  mov     ebx, eax
0x1800b0a61  test    eax, eax
0x1800b0a63  jnz     loc_1800B0B0E
0x1800b0a69  cmp     edi, [rbp+57h+var_80]
0x1800b0a6c  jnb     short loc_1800B0A8A
0x1800b0a6e  mov     rax, [r13+0]
0x1800b0a72  mov     rdx, [rbp+57h+var_78]
0x1800b0a76  mov     ecx, edi
0x1800b0a78  add     rcx, rcx
0x1800b0a7b  movups  xmm0, xmmword ptr [rdx+rax]
0x1800b0a7f  movdqu  xmmword ptr [r14+rcx*8], xmm0
0x1800b0a85  jmp     loc_1800B0B5B
0x1800b0a8a  mov     ebx, 8000FFFFh
0x1800b0a8f  inc     r12d
0x1800b0a92  test    ebx, ebx
0x1800b0a94  jns     short loc_1800B0A29
0x1800b0a96  mov     eax, [rbp+57h+var_80]
0x1800b0a99  xor     r13d, r13d
0x1800b0a9c  cmp     cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A, r13d; CInkCollectorProfileData g_CollectorProfileData
0x1800b0aa3  jz      short loc_1800B0AD3
0x1800b0aa5  lea     ecx, [rdi+1]
0x1800b0aa8  cmp     ecx, eax
0x1800b0aaa  jnb     short loc_1800B0AD3
0x1800b0aac  movups  xmm0, xmmword ptr cs:GUID_PEN_TIMESTAMP1.Data1
0x1800b0ab3  mov     eax, edi
0x1800b0ab5  add     rax, rax
0x1800b0ab8  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800b0abe  mov     eax, ecx
0x1800b0ac0  movups  xmm0, xmmword ptr cs:GUID_PEN_TIMESTAMP2.Data1
0x1800b0ac7  add     rax, rax
0x1800b0aca  add     edi, 2
0x1800b0acd  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800b0ad3  mov     rax, [rbp+57h+pv]
0x1800b0ad7  mov     [rax], edi
0x1800b0ad9  mov     rax, [rbp+57h+pv]
0x1800b0add  mov     [rax+8], r14
0x1800b0ae1  test    ebx, ebx
0x1800b0ae3  js      loc_1800B0C0B
0x1800b0ae9  mov     ecx, [rsi+13Ch]
0x1800b0aef  mov     r8d, 80000000h
0x1800b0af5  cmp     ecx, r8d
0x1800b0af8  jnz     short loc_1800B0B6F
0x1800b0afa  mov     ecx, 204h
0x1800b0aff  cmp     [rsi+140h], r8d
0x1800b0b06  jz      loc_1800B0B8D
0x1800b0b0c  jmp     short loc_1800B0B76
0x1800b0b0e  cmp     eax, 8004021Bh
0x1800b0b13  jnz     loc_1800B0A8F
0x1800b0b19  mov     rcx, [r13+0]
0x1800b0b1d  xor     ebx, ebx
0x1800b0b1f  mov     rdx, [rbp+57h+var_78]
0x1800b0b23  mov     rax, cs:qword_180121360
0x1800b0b2a  sub     rax, [rdx+rcx]
0x1800b0b2e  jnz     short loc_1800B0B3C
0x1800b0b30  mov     rax, cs:qword_180121368
0x1800b0b37  sub     rax, [rdx+rcx+8]
0x1800b0b3c  test    rax, rax
0x1800b0b3f  jnz     loc_1800B0A8F
0x1800b0b45  mov     eax, [rbp+57h+var_80]
0x1800b0b48  cmp     edi, eax
0x1800b0b4a  jnb     short loc_1800B0B65
0x1800b0b4c  movups  xmm0, xmmword ptr [rdx+rcx]
0x1800b0b50  mov     eax, edi
0x1800b0b52  add     rax, rax
0x1800b0b55  movdqu  xmmword ptr [r14+rax*8], xmm0
0x1800b0b5b  inc     edi
0x1800b0b5d  inc     r12d
0x1800b0b60  jmp     loc_1800B0A29
0x1800b0b65  mov     ebx, 8000FFFFh
0x1800b0b6a  jmp     loc_1800B0A99
0x1800b0b6f  mov     rax, [rbp+57h+pv]
0x1800b0b73  mov     [rax+30h], ecx
0x1800b0b76  mov     edx, [rsi+140h]
0x1800b0b7c  mov     ecx, 205h
0x1800b0b81  cmp     edx, r8d
0x1800b0b84  jz      short loc_1800B0B8D
0x1800b0b86  mov     rax, [rbp+57h+pv]
0x1800b0b8a  mov     [rax+34h], edx
0x1800b0b8d  mov     r9d, ecx
0x1800b0b90  or      r9d, 10h
0x1800b0b94  cmp     dword ptr [rsi+138h], 1
0x1800b0b9b  cmovnz  r9d, ecx
0x1800b0b9f  cmp     cs:?g_CollectorProfileData@@3VCInkCollectorProfileData@@A, r13d; CInkCollectorProfileData g_CollectorProfileData
0x1800b0ba6  jz      short loc_1800B0BAD
0x1800b0ba8  bts     r9d, 8
0x1800b0bad  mov     rcx, [rsi+210h]
0x1800b0bb4  mov     r11, [rbp+57h+var_70]
0x1800b0bb8  mov     r8, [rbp+57h+var_68]
0x1800b0bbc  lea     rax, [rcx+40h]
0x1800b0bc0  neg     rcx
0x1800b0bc3  mov     r10, [r11]
0x1800b0bc6  lea     rcx, [r15+8]
0x1800b0bca  sbb     rdx, rdx
0x1800b0bcd  and     rdx, rax
0x1800b0bd0  lea     rax, [rbp+57h+var_88]
0x1800b0bd4  mov     [rsp+0F0h+var_A8], rdx
0x1800b0bd9  mov     rdx, [rsi+38h]
0x1800b0bdd  mov     [rsp+0F0h+var_B0], rax
0x1800b0be2  mov     rax, [r10+20h]
0x1800b0be6  mov     [rsp+0F0h+var_B8], rcx
0x1800b0beb  mov     rcx, [rbp+57h+pv]
0x1800b0bef  mov     [rsp+0F0h+var_C0], r15
0x1800b0bf4  mov     [rsp+0F0h+var_C8], 2
0x1800b0bfc  mov     [rsp+0F0h+var_D0], rcx
0x1800b0c01  mov     rcx, r11
0x1800b0c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0c09  mov     ebx, eax
0x1800b0c0b  mov     r12d, [rbp+57h+var_7C]
0x1800b0c0f  mov     rcx, [rbp+57h+pv]
0x1800b0c13  mov     rcx, [rcx+18h]; pv
0x1800b0c17  call    cs:__imp_CoTaskMemFree
0x1800b0c1d  mov     rcx, [rbp+57h+pv]; pv
0x1800b0c21  call    cs:__imp_CoTaskMemFree
0x1800b0c27  test    r14, r14
0x1800b0c2a  jz      short loc_1800B0C34
0x1800b0c2c  mov     rcx, r14; void *
0x1800b0c2f  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x1800b0c34  test    ebx, ebx
0x1800b0c36  js      loc_1800B0D2C
0x1800b0c3c  mov     rcx, [rbp+57h+var_88]
0x1800b0c40  mov     rax, [rcx+18h]
0x1800b0c44  mov     [r15+10h], rax
0x1800b0c48  mov     [rcx+18h], r13
0x1800b0c4c  mov     rax, [rbp+57h+var_88]
0x1800b0c50  mov     [rax+10h], r13d
0x1800b0c54  mov     rcx, [rbp+57h+var_88]
0x1800b0c58  mov     rdi, [rcx+8]
0x1800b0c5c  test    r12d, r12d
0x1800b0c5f  jnz     short loc_1800B0C9C
0x1800b0c61  movups  xmm0, xmmword ptr [rdi+20h]
0x1800b0c65  movups  xmmword ptr [rdi+40h], xmm0
0x1800b0c69  movups  xmm1, xmmword ptr [rdi+30h]
0x1800b0c6d  movups  xmmword ptr [rdi+50h], xmm1
0x1800b0c71  mov     rax, [rbp+57h+var_88]
0x1800b0c75  mov     rcx, [rax+8]
0x1800b0c79  movups  xmm0, xmmword ptr [rcx]
0x1800b0c7c  movups  xmmword ptr [rcx+20h], xmm0
0x1800b0c80  movups  xmm1, xmmword ptr [rcx+10h]
0x1800b0c84  movups  xmmword ptr [rcx+30h], xmm1
0x1800b0c88  mov     rax, [rbp+57h+var_88]
0x1800b0c8c  add     qword ptr [rax+8], 20h ; ' '
0x1800b0c91  mov     rax, [rbp+57h+var_88]
0x1800b0c95  dec     dword ptr [rax+4]
0x1800b0c98  mov     rcx, [rbp+57h+var_88]
0x1800b0c9c  mov     eax, [rcx+4]
0x1800b0c9f  shl     eax, 2
0x1800b0ca2  mov     [rcx], eax
0x1800b0ca4  mov     rcx, [rsi+220h]
0x1800b0cab  mov     r8, [rbp+57h+var_88]
0x1800b0caf  mov     edx, [r15+8]
0x1800b0cb3  mov     rax, [rcx]
0x1800b0cb6  mov     rax, [rax+38h]
0x1800b0cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0cbf  mov     rcx, rdi; pv
0x1800b0cc2  mov     ebx, eax
0x1800b0cc4  call    cs:__imp_CoTaskMemFree
0x1800b0cca  mov     rcx, [rbp+57h+var_88]; pv
0x1800b0cce  call    cs:__imp_CoTaskMemFree
0x1800b0cd4  test    ebx, ebx
0x1800b0cd6  js      short loc_1800B0D06
0x1800b0cd8  mov     rdx, [r15]; struct ITabletContext *
0x1800b0cdb  xor     r8d, r8d; int
0x1800b0cde  mov     rcx, rsi; this
0x1800b0ce1  call    ?_UpdateTabletToInkToDisplayMapping@CInkCollector@@AEAAJPEAUITabletContext@@H@Z; CInkCollector::_UpdateTabletToInkToDisplayMapping(ITabletContext *,int)
0x1800b0ce6  mov     ebx, eax
0x1800b0ce8  test    eax, eax
0x1800b0cea  js      short loc_1800B0D06
0x1800b0cec  mov     rcx, [r15]
0x1800b0cef  mov     edx, 1
0x1800b0cf4  mov     rax, [rcx]
0x1800b0cf7  mov     rax, [rax+38h]
0x1800b0cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0d00  mov     ebx, eax
0x1800b0d02  test    eax, eax
0x1800b0d04  jns     short loc_1800B0D2C
0x1800b0d06  mov     rcx, [r15]
0x1800b0d09  mov     rax, [rcx]
0x1800b0d0c  mov     rax, [rax+10h]
0x1800b0d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0d15  mov     rcx, [r15+10h]; pv
0x1800b0d19  call    cs:__imp_CoTaskMemFree
0x1800b0d1f  xorps   xmm0, xmm0
0x1800b0d22  xor     eax, eax
0x1800b0d24  movups  xmmword ptr [r15], xmm0
0x1800b0d28  mov     [r15+10h], rax
0x1800b0d2c  mov     eax, ebx
0x1800b0d2e  mov     rcx, [rbp+57h+var_50]
0x1800b0d32  xor     rcx, rsp; StackCookie
  ... truncated ...
```
