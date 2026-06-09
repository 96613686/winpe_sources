# WaitHelper::WaitForMultipleObjects(ulong,void * const *,int,ulong,ulong &)

- ea: `0x18306a490`
- end: `0x18306aa2e`
- name: `?WaitForMultipleObjects@WaitHelper@@SAKKPEBQEAXHKAEAK@Z`
- size: `1438`
- prototype: `unsigned int __fastcall(unsigned int, void *const *, int, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x183069b90`
- `0x18306a070`

## callees

- `0x1815bbb70`
- `0x183066770`
- `0x183069ca0`
- `0x18306a490`
- `0x18306aa60`
- `0x18306aaf0`
- `0x1832c3a30`
- `0x1832ce3b0`

## import_xrefs

- `KERNEL32!CreateThread` at `0x18306a77e`
- `KERNEL32!CreateThread` at `0x18306a77e`
- `KERNEL32!WaitForMultipleObjects` at `0x18306a4db`
- `KERNEL32!WaitForMultipleObjects` at `0x18306a8fb`
- `KERNEL32!WaitForMultipleObjects` at `0x18306a4db`
- `KERNEL32!WaitForMultipleObjects` at `0x18306a8fb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9b8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9d0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9e0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9fd`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9b8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9d0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9e0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18306a9fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
DWORD __fastcall WaitHelper::WaitForMultipleObjects(DWORD a1, void *const *a2, BOOL a3, DWORD a4, unsigned int *a5)
{
  unsigned int *v7; // r14
  int v8; // edi
  DWORD result; // eax
  DWORD v10; // eax
  int v11; // ecx
  int v12; // r10d
  DWORD v13; // r15d
  __int64 v14; // r9
  DWORD v15; // eax
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rcx
  DWORD v18; // r14d
  int v19; // ebx
  void *const *v20; // rsi
  unsigned __int64 v21; // rbx
  __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // r9
  unsigned __int64 v25; // r8
  __int64 v26; // rbx
  __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r9
  unsigned __int64 v30; // r8
  unsigned int v31; // esi
  HANDLE Thread; // rbx
  const HANDLE *v33; // r10
  HANDLE *v34; // rax
  signed __int64 v35; // rbx
  signed __int64 v36; // rax
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // r8
  signed __int64 v40; // rax
  unsigned __int64 v41; // rdx
  unsigned __int64 v42; // r9
  unsigned __int64 v43; // r8
  HANDLE *v44; // rax
  int v45; // r9d
  unsigned int v46; // edx
  unsigned __int64 v47; // r8
  unsigned __int64 v48; // rax
  unsigned int v49; // ecx
  void *v50; // rcx
  unsigned __int64 v51; // rax
  unsigned __int64 v52; // rax
  void *const *v53; // [rsp+30h] [rbp-71h]
  int v54; // [rsp+40h] [rbp-61h] BYREF
  void *const *v55; // [rsp+48h] [rbp-59h]
  BOOL v56; // [rsp+50h] [rbp-51h]
  DWORD v57; // [rsp+54h] [rbp-4Dh]
  int v58; // [rsp+58h] [rbp-49h]
  __int64 v59; // [rsp+60h] [rbp-41h]
  HANDLE v60; // [rsp+68h] [rbp-39h] BYREF
  __int128 v61; // [rsp+70h] [rbp-31h] BYREF
  __int64 v62; // [rsp+80h] [rbp-21h]
  HANDLE *lpHandles[2]; // [rsp+88h] [rbp-19h] BYREF
  HANDLE *v64; // [rsp+98h] [rbp-9h]

  v59 = -2;
  v53 = a2;
  v7 = a5;
  v8 = 0;
  *a5 = 0;
  if ( a1 > 0x40 )
  {
    v10 = a1 >> 6;
    v11 = a1 & 0x3F;
    v12 = v11;
    if ( !v11 )
      v12 = 64;
    LODWORD(v60) = v12;
    v13 = v10 + 1;
    if ( !v11 )
      v13 = v10;
    v61 = 0;
    v14 = 0;
    v62 = 0;
    v15 = 0;
    v16 = 0;
    if ( v13 )
    {
      v17 = *((_QWORD *)&v61 + 1);
      while ( 1 )
      {
        v18 = v15 + 1;
        v19 = 64;
        if ( v15 + 1 == v13 )
          v19 = v12;
        v54 = v19;
        v20 = &a2[64 * v15];
        v55 = v20;
        v56 = a3;
        v57 = a4;
        v58 = 0;
        if ( (unsigned __int64)&v54 >= v17 || v16 > (unsigned __int64)&v54 )
        {
          if ( v17 == v14 && !((__int64)(v14 - v17) >> 5) )
          {
            v27 = (__int64)(v17 - v16) >> 5;
            if ( v27 == 0x7FFFFFFFFFFFFFFLL )
              std::vector<VarBase>::_Xlen(&v61);
            v28 = v27 + 1;
            v29 = (__int64)(v14 - v16) >> 5;
            v30 = 0;
            if ( 0x7FFFFFFFFFFFFFFLL - (v29 >> 1) >= v29 )
              v30 = v29 + (v29 >> 1);
            if ( v30 >= v28 )
              v28 = v30;
            std::vector<WaitHelper::WaitWorkerContext>::_Reallocate(&v61, v28);
            v14 = v62;
            v17 = *((_QWORD *)&v61 + 1);
            v16 = v61;
            a2 = v53;
            v12 = (int)v60;
          }
          if ( !v17 )
            goto LABEL_38;
          *(_DWORD *)v17 = v19;
          *(_QWORD *)(v17 + 8) = v20;
          *(_DWORD *)(v17 + 16) = a3;
          *(_DWORD *)(v17 + 20) = a4;
          *(_DWORD *)(v17 + 24) = 0;
        }
        else
        {
          v21 = (unsigned __int64)&v54 - v16;
          if ( v17 == v14 && !((__int64)(v14 - v17) >> 5) )
          {
            v22 = (__int64)(v17 - v16) >> 5;
            if ( v22 == 0x7FFFFFFFFFFFFFFLL )
              std::vector<VarBase>::_Xlen(&v61);
            v23 = v22 + 1;
            v24 = (__int64)(v14 - v16) >> 5;
            v25 = 0;
            if ( 0x7FFFFFFFFFFFFFFLL - (v24 >> 1) >= v24 )
              v25 = v24 + (v24 >> 1);
            if ( v25 >= v23 )
              v23 = v25;
            std::vector<WaitHelper::WaitWorkerContext>::_Reallocate(&v61, v23);
            v14 = v62;
            v17 = *((_QWORD *)&v61 + 1);
            v16 = v61;
            a2 = v53;
            v12 = (int)v60;
          }
          v26 = v16 + (v21 & 0xFFFFFFFFFFFFFFE0uLL);
          if ( !v17 )
            goto LABEL_38;
          *(_DWORD *)v17 = *(_DWORD *)v26;
          *(_QWORD *)(v17 + 8) = *(_QWORD *)(v26 + 8);
          *(_DWORD *)(v17 + 16) = *(_DWORD *)(v26 + 16);
          *(_DWORD *)(v17 + 20) = *(_DWORD *)(v26 + 20);
          *(_DWORD *)(v17 + 24) = *(_DWORD *)(v26 + 24);
        }
        v14 = v62;
        v17 = *((_QWORD *)&v61 + 1);
        v16 = v61;
LABEL_38:
        v17 += 32LL;
        *((_QWORD *)&v61 + 1) = v17;
        v15 = v18;
        if ( v18 >= v13 )
        {
          v7 = a5;
          break;
        }
      }
    }
    *(_OWORD *)lpHandles = 0;
    v64 = 0;
    v31 = 0;
    if ( !v13 )
    {
      v44 = lpHandles[1];
      v33 = lpHandles[0];
LABEL_72:
      if ( WaitForMultipleObjects(v44 - v33, v33, 1, 0xFFFFFFFF) )
      {
        v8 = -1;
      }
      else
      {
        v45 = 0;
        v46 = 0;
        v47 = (__int64)(*((_QWORD *)&v61 + 1) - v61) >> 5;
        if ( v47 )
        {
          v48 = 0;
          while ( 1 )
          {
            if ( v47 <= v48 )
              std::vector<CxDescriptiveStats>::_Xran(&v61);
            v49 = *(_DWORD *)(32 * v48 + v61 + 24);
            if ( v49 == -1 || v49 == 258 )
              break;
            if ( v49 >= 0x80 )
            {
              v45 = (v46 << 6) + v49 - 128;
              v8 = 128;
              goto LABEL_86;
            }
            if ( !a3 )
            {
              v45 = v49 + (v46 << 6);
              goto LABEL_86;
            }
            v48 = ++v46;
            if ( v46 >= v47 )
              goto LABEL_86;
          }
          v8 = *(_DWORD *)(32 * v48 + v61 + 24);
        }
LABEL_86:
        *v7 = v45;
      }
      WaitHelper::ThreadHandleArray::~ThreadHandleArray((WaitHelper::ThreadHandleArray *)lpHandles);
      v50 = (void *)v61;
      if ( (_QWORD)v61 )
      {
        v51 = (v62 - (__int64)v61) >> 5;
        if ( v51 > 0x7FFFFFFFFFFFFFFLL )
          _invalid_parameter_noinfo_noreturn();
        if ( 32 * v51 >= 0x1000 )
        {
          if ( (v61 & 0x1F) != 0 )
            _invalid_parameter_noinfo_noreturn();
          v52 = *(_QWORD *)(v61 - 8);
          if ( v52 >= (unsigned __int64)v61 )
            _invalid_parameter_noinfo_noreturn();
          if ( (unsigned __int64)v61 - v52 < 8 )
            _invalid_parameter_noinfo_noreturn();
          if ( (unsigned __int64)v61 - v52 > 0x27 )
            _invalid_parameter_noinfo_noreturn();
          v50 = *(void **)(v61 - 8);
        }
        operator delete(v50);
      }
      return v8;
    }
    while ( 1 )
    {
      Thread = CreateThread(0, 0, WaitHelper::WaitWorker, (LPVOID)(v16 + 32LL * v31), 0, 0);
      v60 = Thread;
      v33 = lpHandles[0];
      v34 = lpHandles[1];
      if ( &v60 >= lpHandles[1] || lpHandles[0] > &v60 )
      {
        if ( lpHandles[1] == v64 && !(v64 - lpHandles[1]) )
        {
          v40 = lpHandles[1] - lpHandles[0];
          if ( v40 == 0x1FFFFFFFFFFFFFFFLL )
            std::vector<VarBase>::_Xlen(lpHandles);
          v41 = v40 + 1;
          v42 = v64 - lpHandles[0];
          v43 = 0;
          if ( 0x1FFFFFFFFFFFFFFFLL - (v42 >> 1) >= v42 )
            v43 = v42 + (v42 >> 1);
          if ( v43 >= v41 )
            v41 = v43;
          std::vector<void *>::_Reallocate(lpHandles, v41);
          v34 = lpHandles[1];
          v33 = lpHandles[0];
        }
        if ( v34 )
        {
          *v34 = Thread;
          goto LABEL_66;
        }
      }
      else
      {
        v35 = &v60 - lpHandles[0];
        if ( lpHandles[1] == v64 && !(v64 - lpHandles[1]) )
        {
          v36 = lpHandles[1] - lpHandles[0];
          if ( v36 == 0x1FFFFFFFFFFFFFFFLL )
            std::vector<VarBase>::_Xlen(lpHandles);
          v37 = v36 + 1;
          v38 = v64 - lpHandles[0];
          v39 = 0;
          if ( 0x1FFFFFFFFFFFFFFFLL - (v38 >> 1) >= v38 )
            v39 = v38 + (v38 >> 1);
          if ( v39 >= v37 )
            v37 = v39;
          std::vector<void *>::_Reallocate(lpHandles, v37);
          v34 = lpHandles[1];
          v33 = lpHandles[0];
        }
        if ( v34 )
        {
          *v34 = v33[v35];
LABEL_66:
          v34 = lpHandles[1];
          v33 = lpHandles[0];
        }
      }
      v44 = v34 + 1;
      lpHandles[1] = v44;
      if ( ++v31 >= v13 )
        goto LABEL_72;
      v16 = v61;
    }
  }
  result = WaitForMultipleObjects(a1, a2, a3, a4);
  if ( result != -1 && result != 258 )
  {
    if ( result >= 0x80 )
    {
      *a5 = result - 128;
      return 128;
    }
    *a5 = result;
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18306a490  push    rbp
0x18306a492  push    rbx
0x18306a493  push    rsi
0x18306a494  push    rdi
0x18306a495  push    r12
0x18306a497  push    r13
0x18306a499  push    r14
0x18306a49b  push    r15
0x18306a49d  lea     rbp, [rsp-17h]
0x18306a4a2  sub     rsp, 0B8h
0x18306a4a9  mov     [rbp+4Fh+var_90], 0FFFFFFFFFFFFFFFEh
0x18306a4b1  mov     rax, cs:__security_cookie
0x18306a4b8  xor     rax, rsp
0x18306a4bb  mov     [rbp+4Fh+var_50], rax
0x18306a4bf  mov     r12d, r9d
0x18306a4c2  mov     r13d, r8d
0x18306a4c5  mov     [rbp+4Fh+var_C0], rdx
0x18306a4c9  mov     r14, [rbp+4Fh+arg_20]
0x18306a4cd  mov     [rbp+4Fh+var_B8], r14
0x18306a4d1  xor     edi, edi
0x18306a4d3  mov     [r14], edi
0x18306a4d6  cmp     ecx, 40h ; '@'
0x18306a4d9  ja      short loc_18306A514
0x18306a4db  call    cs:__imp_WaitForMultipleObjects
0x18306a4e1  cmp     eax, 0FFFFFFFFh
0x18306a4e4  jz      loc_18306AA0E
0x18306a4ea  cmp     eax, 102h
0x18306a4ef  jz      loc_18306AA0E
0x18306a4f5  cmp     eax, 80h
0x18306a4fa  jb      short loc_18306A50C
0x18306a4fc  add     eax, 0FFFFFF80h
0x18306a4ff  mov     [r14], eax
0x18306a502  mov     eax, 80h
0x18306a507  jmp     loc_18306AA0E
0x18306a50c  mov     [r14], eax
0x18306a50f  jmp     loc_18306AA0C
0x18306a514  mov     eax, ecx
0x18306a516  shr     eax, 6
0x18306a519  and     ecx, 3Fh
0x18306a51c  mov     r10d, ecx
0x18306a51f  mov     r11d, 40h ; '@'
0x18306a525  cmovbe  r10d, r11d
0x18306a529  mov     dword ptr [rbp+4Fh+var_88], r10d
0x18306a52d  lea     r15d, [rax+1]
0x18306a531  test    ecx, ecx
0x18306a533  cmovz   r15d, eax
0x18306a537  xorps   xmm0, xmm0
0x18306a53a  movdqu  [rbp+4Fh+var_80], xmm0
0x18306a53f  mov     r9, rdi
0x18306a542  mov     [rbp+4Fh+var_70], rdi
0x18306a546  mov     eax, edi
0x18306a548  mov     r8, qword ptr [rbp+4Fh+var_80]
0x18306a54c  test    r15d, r15d
0x18306a54f  jz      loc_18306A732
0x18306a555  mov     rcx, qword ptr [rbp+4Fh+var_80+8]
0x18306a559  nop     dword ptr [rax+00000000h]
0x18306a560  lea     r14d, [rax+1]
0x18306a564  mov     ebx, r11d
0x18306a567  cmp     r14d, r15d
0x18306a56a  cmovz   ebx, r10d
0x18306a56e  mov     [rbp+4Fh+var_B0], ebx
0x18306a571  shl     eax, 6
0x18306a574  lea     rsi, [rdx+rax*8]
0x18306a578  mov     [rbp+4Fh+var_A8], rsi
0x18306a57c  mov     [rbp+4Fh+var_A0], r13d
0x18306a580  mov     [rbp+4Fh+var_9C], r12d
0x18306a584  mov     [rbp+4Fh+var_98], edi
0x18306a587  lea     rax, [rbp+4Fh+var_B0]
0x18306a58b  cmp     rax, rcx
0x18306a58e  jnb     loc_18306A65F
0x18306a594  lea     rax, [rbp+4Fh+var_B0]
0x18306a598  cmp     r8, rax
0x18306a59b  ja      loc_18306A65F
0x18306a5a1  lea     rbx, [rbp+4Fh+var_B0]
0x18306a5a5  sub     rbx, r8
0x18306a5a8  cmp     rcx, r9
0x18306a5ab  jnz     short loc_18306A62C
0x18306a5ad  mov     rax, r9
0x18306a5b0  sub     rax, rcx
0x18306a5b3  sar     rax, 5
0x18306a5b7  cmp     rax, 1
0x18306a5bb  jnb     short loc_18306A62C
0x18306a5bd  sub     rcx, r8
0x18306a5c0  sar     rcx, 5
0x18306a5c4  mov     r10, 7FFFFFFFFFFFFFFh
0x18306a5ce  mov     rax, r10
0x18306a5d1  sub     rax, rcx
0x18306a5d4  cmp     rax, 1
0x18306a5d8  jb      loc_18306A71A
0x18306a5de  lea     rdx, [rcx+1]
0x18306a5e2  sub     r9, r8
0x18306a5e5  sar     r9, 5
0x18306a5e9  mov     rax, r9
0x18306a5ec  shr     rax, 1
0x18306a5ef  mov     rcx, r10
0x18306a5f2  sub     rcx, rax
0x18306a5f5  add     rax, r9
0x18306a5f8  mov     r8, rdi
0x18306a5fb  cmp     rcx, r9
0x18306a5fe  cmovnb  r8, rax
0x18306a602  cmp     r8, rdx
0x18306a605  cmovnb  rdx, r8
0x18306a609  lea     rcx, [rbp+4Fh+var_80]
0x18306a60d  call    ?_Reallocate@?$vector@UWaitWorkerContext@WaitHelper@@V?$allocator@UWaitWorkerContext@WaitHelper@@@std@@@std@@IEAAX_K@Z
0x18306a612  mov     r9, [rbp+4Fh+var_70]
0x18306a616  mov     rcx, qword ptr [rbp+4Fh+var_80+8]
0x18306a61a  mov     r8, qword ptr [rbp+4Fh+var_80]
0x18306a61e  mov     rdx, [rbp+4Fh+var_C0]
0x18306a622  mov     r10d, dword ptr [rbp+4Fh+var_88]
0x18306a626  mov     r11d, 40h ; '@'
0x18306a62c  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18306a630  add     rbx, r8
0x18306a633  test    rcx, rcx
0x18306a636  jz      loc_18306A705
0x18306a63c  mov     eax, [rbx]
0x18306a63e  mov     [rcx], eax
0x18306a640  mov     rax, [rbx+8]
0x18306a644  mov     [rcx+8], rax
0x18306a648  mov     eax, [rbx+10h]
0x18306a64b  mov     [rcx+10h], eax
0x18306a64e  mov     eax, [rbx+14h]
0x18306a651  mov     [rcx+14h], eax
0x18306a654  mov     eax, [rbx+18h]
0x18306a657  mov     [rcx+18h], eax
0x18306a65a  jmp     loc_18306A6F9
0x18306a65f  cmp     rcx, r9
0x18306a662  jnz     short loc_18306A6E3
0x18306a664  mov     rax, r9
0x18306a667  sub     rax, rcx
0x18306a66a  sar     rax, 5
0x18306a66e  cmp     rax, 1
0x18306a672  jnb     short loc_18306A6E3
0x18306a674  sub     rcx, r8
0x18306a677  sar     rcx, 5
0x18306a67b  mov     r10, 7FFFFFFFFFFFFFFh
0x18306a685  mov     rax, r10
0x18306a688  sub     rax, rcx
0x18306a68b  cmp     rax, 1
0x18306a68f  jb      loc_18306A724
0x18306a695  lea     rdx, [rcx+1]
0x18306a699  sub     r9, r8
0x18306a69c  sar     r9, 5
0x18306a6a0  mov     rax, r9
0x18306a6a3  shr     rax, 1
0x18306a6a6  mov     rcx, r10
0x18306a6a9  sub     rcx, rax
0x18306a6ac  add     rax, r9
0x18306a6af  mov     r8, rdi
0x18306a6b2  cmp     rcx, r9
0x18306a6b5  cmovnb  r8, rax
0x18306a6b9  cmp     r8, rdx
0x18306a6bc  cmovnb  rdx, r8
0x18306a6c0  lea     rcx, [rbp+4Fh+var_80]
0x18306a6c4  call    ?_Reallocate@?$vector@UWaitWorkerContext@WaitHelper@@V?$allocator@UWaitWorkerContext@WaitHelper@@@std@@@std@@IEAAX_K@Z
0x18306a6c9  mov     r9, [rbp+4Fh+var_70]
0x18306a6cd  mov     rcx, qword ptr [rbp+4Fh+var_80+8]
0x18306a6d1  mov     r8, qword ptr [rbp+4Fh+var_80]
0x18306a6d5  mov     rdx, [rbp+4Fh+var_C0]
0x18306a6d9  mov     r10d, dword ptr [rbp+4Fh+var_88]
0x18306a6dd  mov     r11d, 40h ; '@'
0x18306a6e3  test    rcx, rcx
0x18306a6e6  jz      short loc_18306A705
0x18306a6e8  mov     [rcx], ebx
0x18306a6ea  mov     [rcx+8], rsi
0x18306a6ee  mov     [rcx+10h], r13d
0x18306a6f2  mov     [rcx+14h], r12d
0x18306a6f6  mov     [rcx+18h], edi
0x18306a6f9  mov     r9, [rbp+4Fh+var_70]
0x18306a6fd  mov     r8, qword ptr [rbp+4Fh+var_80]
0x18306a701  mov     rcx, qword ptr [rbp+4Fh+var_80+8]
0x18306a705  add     rcx, 20h ; ' '
0x18306a709  mov     qword ptr [rbp+4Fh+var_80+8], rcx
0x18306a70d  mov     eax, r14d
0x18306a710  cmp     r14d, r15d
0x18306a713  jnb     short loc_18306A72E
0x18306a715  jmp     loc_18306A560
0x18306a71a  lea     rcx, [rbp+4Fh+var_80]
0x18306a71e  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ
0x18306a724  lea     rcx, [rbp+4Fh+var_80]
0x18306a728  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ
0x18306a72e  mov     r14, [rbp+4Fh+var_B8]
0x18306a732  xorps   xmm0, xmm0
0x18306a735  movdqu  xmmword ptr [rbp+4Fh+lpHandles], xmm0
0x18306a73a  mov     [rbp+4Fh+var_58], rdi
0x18306a73e  mov     esi, edi
0x18306a740  test    r15d, r15d
0x18306a743  jz      loc_18306A8DD
0x18306a749  mov     r12, 1FFFFFFFFFFFFFFFh
0x18306a753  nop     dword ptr [rax+00h]
0x18306a757  nop     word ptr [rax+rax+00000000h]
0x18306a760  mov     r9d, esi
0x18306a763  shl     r9, 5
0x18306a767  add     r9, r8; lpParameter
0x18306a76a  mov     [rsp+0F0h+lpThreadId], rdi; lpThreadId
0x18306a76f  mov     [rsp+0F0h+dwCreationFlags], edi; dwCreationFlags
0x18306a773  lea     r8, ?WaitWorker@WaitHelper@@CAKPEAX@Z; lpStartAddress
0x18306a77a  xor     edx, edx; dwStackSize
0x18306a77c  xor     ecx, ecx; lpThreadAttributes
0x18306a77e  call    cs:__imp_CreateThread
0x18306a784  mov     rbx, rax
0x18306a787  mov     [rbp+4Fh+var_88], rax
0x18306a78b  lea     rcx, [rbp+4Fh+var_88]
0x18306a78f  mov     r10, [rbp+4Fh+lpHandles]
0x18306a793  mov     rax, [rbp+4Fh+lpHandles+8]
0x18306a797  cmp     rcx, rax
0x18306a79a  jnb     loc_18306A839
0x18306a7a0  lea     rcx, [rbp+4Fh+var_88]
0x18306a7a4  cmp     r10, rcx
0x18306a7a7  ja      loc_18306A839
0x18306a7ad  lea     rbx, [rbp+4Fh+var_88]
0x18306a7b1  sub     rbx, r10
0x18306a7b4  sar     rbx, 3
0x18306a7b8  mov     r9, [rbp+4Fh+var_58]
0x18306a7bc  cmp     rax, r9
0x18306a7bf  jnz     short loc_18306A824
0x18306a7c1  mov     rcx, r9
0x18306a7c4  sub     rcx, rax
0x18306a7c7  sar     rcx, 3
0x18306a7cb  cmp     rcx, 1
0x18306a7cf  jnb     short loc_18306A824
0x18306a7d1  sub     rax, r10
0x18306a7d4  sar     rax, 3
0x18306a7d8  mov     rcx, r12
0x18306a7db  sub     rcx, rax
0x18306a7de  cmp     rcx, 1
0x18306a7e2  jb      loc_18306A8C9
0x18306a7e8  lea     rdx, [rax+1]
0x18306a7ec  sub     r9, r10
0x18306a7ef  sar     r9, 3
0x18306a7f3  mov     rax, r9
0x18306a7f6  shr     rax, 1
0x18306a7f9  mov     rcx, r12
0x18306a7fc  sub     rcx, rax
0x18306a7ff  add     rax, r9
0x18306a802  mov     r8, rdi
0x18306a805  cmp     rcx, r9
0x18306a808  cmovnb  r8, rax
0x18306a80c  cmp     r8, rdx
0x18306a80f  cmovnb  rdx, r8
0x18306a813  lea     rcx, [rbp+4Fh+lpHandles]
0x18306a817  call    ?_Reallocate@?$vector@PEAXV?$allocator@PEAX@std@@@std@@IEAAX_K@Z
0x18306a81c  mov     rax, [rbp+4Fh+lpHandles+8]
0x18306a820  mov     r10, [rbp+4Fh+lpHandles]
0x18306a824  lea     rcx, [r10+rbx*8]
0x18306a828  test    rax, rax
0x18306a82b  jz      loc_18306A8B1
0x18306a831  mov     rcx, [rcx]
0x18306a834  mov     [rax], rcx
0x18306a837  jmp     short loc_18306A8A9
0x18306a839  mov     r9, [rbp+4Fh+var_58]
0x18306a83d  cmp     rax, r9
0x18306a840  jnz     short loc_18306A8A1
0x18306a842  mov     rcx, r9
0x18306a845  sub     rcx, rax
0x18306a848  sar     rcx, 3
0x18306a84c  cmp     rcx, 1
0x18306a850  jnb     short loc_18306A8A1
0x18306a852  sub     rax, r10
0x18306a855  sar     rax, 3
0x18306a859  mov     rcx, r12
0x18306a85c  sub     rcx, rax
0x18306a85f  cmp     rcx, 1
0x18306a863  jb      short loc_18306A8D3
0x18306a865  lea     rdx, [rax+1]
0x18306a869  sub     r9, r10
0x18306a86c  sar     r9, 3
0x18306a870  mov     rax, r9
0x18306a873  shr     rax, 1
0x18306a876  mov     rcx, r12
0x18306a879  sub     rcx, rax
0x18306a87c  add     rax, r9
0x18306a87f  mov     r8, rdi
0x18306a882  cmp     rcx, r9
0x18306a885  cmovnb  r8, rax
0x18306a889  cmp     r8, rdx
0x18306a88c  cmovnb  rdx, r8
0x18306a890  lea     rcx, [rbp+4Fh+lpHandles]
0x18306a894  call    ?_Reallocate@?$vector@PEAXV?$allocator@PEAX@std@@@std@@IEAAX_K@Z
0x18306a899  mov     rax, [rbp+4Fh+lpHandles+8]
0x18306a89d  mov     r10, [rbp+4Fh+lpHandles]
0x18306a8a1  test    rax, rax
0x18306a8a4  jz      short loc_18306A8B1
0x18306a8a6  mov     [rax], rbx
0x18306a8a9  mov     rax, [rbp+4Fh+lpHandles+8]
0x18306a8ad  mov     r10, [rbp+4Fh+lpHandles]
0x18306a8b1  add     rax, 8
0x18306a8b5  mov     [rbp+4Fh+lpHandles+8], rax
0x18306a8b9  inc     esi
0x18306a8bb  cmp     esi, r15d
0x18306a8be  jnb     short loc_18306A8E5
0x18306a8c0  mov     r8, qword ptr [rbp+4Fh+var_80]
0x18306a8c4  jmp     loc_18306A760
0x18306a8c9  lea     rcx, [rbp+4Fh+lpHandles]
0x18306a8cd  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ
0x18306a8d3  lea     rcx, [rbp+4Fh+lpHandles]
0x18306a8d7  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ
0x18306a8dd  mov     rax, [rbp+4Fh+lpHandles+8]
0x18306a8e1  mov     r10, [rbp+4Fh+lpHandles]
0x18306a8e5  sub     rax, r10
0x18306a8e8  sar     rax, 3
  ... truncated ...
```
