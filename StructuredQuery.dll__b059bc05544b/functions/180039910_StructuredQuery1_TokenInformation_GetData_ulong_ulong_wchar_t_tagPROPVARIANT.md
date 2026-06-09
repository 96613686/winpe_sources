# StructuredQuery1::TokenInformation::GetData(ulong *,ulong *,wchar_t * *,tagPROPVARIANT *)

- ea: `0x180039910`
- end: `0x180039e56`
- name: `?GetData@TokenInformation@StructuredQuery1@@UEAAJPEAK0PEAPEA_WPEAUtagPROPVARIANT@@@Z`
- size: `1350`
- prototype: `__int64 __fastcall(StructuredQuery1::TokenInformation *__hidden this, unsigned int *, unsigned int *, wchar_t **, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001ee60`
- `0x1800236c0`
- `0x180039910`
- `0x18005e740`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18003998f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18003998f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039b86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039b86`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800399eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800399eb`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::TokenInformation::GetData(
        StructuredQuery1::TokenInformation *this,
        unsigned int *a2,
        unsigned int *a3,
        wchar_t **a4,
        struct tagPROPVARIANT *a5)
{
  wchar_t *v7; // rdi
  wchar_t **v8; // r12
  unsigned int v9; // r14d
  unsigned int *v10; // r15
  HRESULT v11; // esi
  __int64 v12; // r14
  __int64 v13; // rcx
  __int64 v14; // rsi
  int v15; // r15d
  unsigned int v16; // eax
  wchar_t *v17; // rcx
  __int64 v18; // r10
  __int64 result; // rax
  BYTE *v20; // xmm1_8
  __int64 v21; // r12
  unsigned __int64 v22; // rbp
  __int64 v23; // rbx
  int (__fastcall **v24)(__int64); // rax
  __int64 v25; // r14
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // eax
  unsigned __int64 v30; // rbx
  unsigned __int64 v31; // r14
  wchar_t *v32; // rax
  wchar_t *v33; // r15
  const size_t *v34; // rcx
  unsigned __int64 v35; // rdx
  wchar_t *v36; // r8
  __int64 v37; // r9
  __int64 v38; // r14
  bool v39; // cf
  unsigned int (__fastcall ***v40)(_QWORD); // rax
  __int64 v41; // rdx
  wchar_t v42; // ax
  wchar_t *v43; // rdx
  wchar_t v44; // cx
  wchar_t *v45; // r8
  wchar_t *v46; // rdx
  wchar_t v47; // r9
  bool v48; // zf
  int v49; // ecx
  unsigned int (__fastcall ***v50)(_QWORD); // rax
  __int64 v51; // rdx
  HRESULT v52; // eax
  int v53; // [rsp+20h] [rbp-88h]
  unsigned int v54; // [rsp+30h] [rbp-78h]
  wchar_t *v55; // [rsp+38h] [rbp-70h] BYREF
  PROPVARIANT pvar[5]; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v57; // [rsp+B0h] [rbp+8h]
  int v61; // [rsp+D0h] [rbp+28h]

  v7 = 0;
  v8 = a4;
  v9 = *((_DWORD *)this + 3);
  v57 = *((_DWORD *)this + 2);
  v10 = a2;
  memset(pvar, 0, 24);
  v54 = v9;
  v55 = 0;
  if ( a5 )
  {
    v11 = PropVariantCopy(pvar, (const PROPVARIANT *)this + 2);
    if ( v11 < 0 )
    {
LABEL_9:
      PropVariantClear(pvar);
      v10 = a2;
      v16 = 0;
      v9 = 0;
      goto LABEL_19;
    }
  }
  else
  {
    v11 = 0;
  }
  if ( v8 )
  {
    v12 = *((_QWORD *)this + 5);
    v13 = *(_QWORD *)(v12 + 24);
    if ( !v13 )
    {
      v52 = _AllocStringWorker<CTCoAllocPolicy>(0, (__int64)a2, 0, 0, v53, &v55);
      v7 = v55;
      v11 = v52;
      goto LABEL_16;
    }
    LOBYTE(v61) = 0;
    if ( *((_WORD *)this + 8) == 3 )
      v61 = *((_DWORD *)this + 6);
    v14 = *((int *)this + 2);
    v15 = v14 + *((_DWORD *)this + 3);
    if ( v15 < (unsigned int)v14 )
    {
      v11 = -2147024362;
      goto LABEL_9;
    }
    v21 = *(_QWORD *)(v13 + 48);
    v22 = 0;
    v23 = 0;
    if ( (int)v14 >= 0 )
    {
      v24 = *(int (__fastcall ***)(__int64))(v12 + 56);
      v25 = v12 + 56;
      if ( (int)v14 < (*v24)(v25) )
      {
        if ( (v61 & 1) != 0
          && (int)v14 > 0
          && (v50 = (unsigned int (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(
                                                             v25,
                                                             v14 - 1),
              (**v50)(v50) == 11) )
        {
          v51 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, v14 - 1);
          v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 24LL))(v51);
        }
        else
        {
          v26 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, v14);
          v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
        }
        v22 = v27;
        if ( (int)v14 >= v15 )
        {
          v23 = v27;
        }
        else
        {
          if ( (v61 & 1) != 0
            && v15 < (**(int (__fastcall ***)(__int64))v25)(v25)
            && (v40 = (unsigned int (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 8LL))(
                                                               v25,
                                                               v15),
                (**v40)(v40) == 11) )
          {
            v41 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 8LL))(v25, v15);
            v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 8LL))(v41);
          }
          else
          {
            v28 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, v15 - 1LL);
            v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 24LL))(v28);
          }
          v23 = v29;
          if ( v29 < v22 )
            goto LABEL_52;
        }
      }
    }
    v30 = v23 - v22;
    v31 = v30 + 1;
    if ( v30 + 1 >= v30 && is_mul_ok(v31, 2u) )
    {
      v32 = (wchar_t *)CoTaskMemAlloc(2 * v31);
      v11 = -2147024882;
      v33 = v32;
      if ( v32 )
        v11 = 0;
      if ( v11 >= 0 )
      {
        if ( (v32 || v30 == -1) && v31 <= 0x7FFFFFFF )
        {
          if ( v30 >= 0x7FFFFFFF )
          {
            if ( v30 != -1 )
              *v32 = 0;
          }
          else
          {
            v34 = (const size_t *)(v21 + 2 * v22);
            if ( !v34 )
            {
              v34 = &cchOriginalDestLength;
              v30 = 0;
            }
            if ( v31 )
            {
              v35 = v31;
              v36 = v32;
              v37 = 0;
              do
              {
                if ( !v30 )
                  break;
                if ( !*(_WORD *)v34 )
                  break;
                *v36 = *(_WORD *)v34;
                v34 = (const size_t *)((char *)v34 + 2);
                ++v36;
                --v30;
                ++v37;
                --v35;
              }
              while ( v35 );
              v17 = v36 - 1;
              v18 = v37 - 1;
              if ( v35 )
              {
                v17 = v36;
                v18 = v37;
              }
              *v17 = 0;
              if ( v35 )
              {
                v39 = v31 == v18;
                v38 = v31 - v18;
                if ( !v39 && v38 != 1 && (unsigned __int64)(2 * v38) > 2 )
                  memset_0(&v32[v18 + 1], 0, 2 * v38 - 2);
              }
            }
          }
        }
        else
        {
          *v32 = 0;
        }
        if ( (v61 & 1) != 0 )
        {
          v42 = *v33;
          v43 = v33;
          if ( *v33 )
          {
            while ( v42 != 65282 )
            {
              if ( v42 <= 0x201Eu )
              {
                if ( v42 == 8222 || v42 == 34 || v42 == 171 || v42 == 187 )
                  break;
                v49 = v42 - 8220;
                v48 = v42 == 8220;
              }
              else
              {
                if ( v42 == 8223 || v42 == 12317 )
                  break;
                v49 = v42 - 12318;
                v48 = v42 == 12318;
              }
              if ( !v48 && v49 != 1 )
              {
                v42 = v43[1];
                ++v43;
                if ( v42 )
                  continue;
              }
              break;
            }
          }
          v44 = *v43;
          if ( *v43 )
          {
            v45 = v43;
            do
            {
              *v45 = v44;
              if ( SemanticsUM::Syntax::IsDoubleQuote(v44) && SemanticsUM::Syntax::IsDoubleQuote(v47) )
                ++v46;
              v44 = *v46;
            }
            while ( *v46 );
            *v45 = 0;
          }
        }
        v7 = v33;
      }
      goto LABEL_15;
    }
LABEL_52:
    v11 = -2147024362;
LABEL_15:
    v8 = a4;
    v10 = a2;
LABEL_16:
    if ( v11 < 0 )
      goto LABEL_9;
    v9 = v54;
  }
  v16 = v57;
LABEL_19:
  if ( v10 )
    *v10 = v16;
  if ( a3 )
    *a3 = v9;
  if ( v8 )
    *v8 = v7;
  result = (unsigned int)v11;
  if ( a5 )
  {
    v20 = (BYTE *)pvar[2];
    *(_OWORD *)&a5->vt = *(_OWORD *)pvar;
    a5->bstrblobVal.pData = v20;
  }
  return result;
}

```

## disassembly

```asm
0x180039910  mov     r11, rsp
0x180039913  mov     [r11+20h], r9
0x180039917  mov     [r11+18h], r8
0x18003991b  mov     [r11+10h], rdx
0x18003991f  push    rsi
0x180039920  push    r13
0x180039922  sub     rsp, 98h
0x180039929  mov     eax, [rcx+8]
0x18003992c  xorps   xmm0, xmm0
0x18003992f  mov     r13, [rsp+0A8h+arg_20]
0x180039937  mov     [r11-18h], rbx
0x18003993b  mov     rbx, rcx
0x18003993e  mov     [r11-20h], rbp
0x180039942  mov     [r11-28h], rdi
0x180039946  xor     edi, edi
0x180039948  mov     [r11-30h], r12
0x18003994c  mov     r12, r9
0x18003994f  mov     [r11-38h], r14
0x180039953  mov     r14d, [rcx+0Ch]
0x180039957  mov     [rsp+0A8h+arg_0], eax
0x18003995e  xor     eax, eax
0x180039960  mov     [r11-40h], r15
0x180039964  mov     r15, rdx
0x180039967  mov     word ptr [rsp+0A8h+pvar], ax
0x18003996c  mov     [rsp+0A8h+var_78], r14d
0x180039971  mov     [r11-70h], rdi
0x180039975  movups  xmmword ptr [rsp+0A8h+pvar+2], xmm0
0x18003997a  mov     [r11-58h], rax
0x18003997e  test    r13, r13
0x180039981  jz      loc_180039DE3
0x180039987  lea     rdx, [rcx+10h]; pvarSrc
0x18003998b  lea     rcx, [r11-68h]; pvarDest
0x18003998f  call    cs:__imp_PropVariantCopy
0x180039995  mov     esi, eax
0x180039997  test    eax, eax
0x180039999  js      short loc_1800399E6
0x18003999b  test    r12, r12
0x18003999e  jz      loc_180039A4B
0x1800399a4  mov     r14, [rbx+28h]
0x1800399a8  mov     rcx, [r14+18h]
0x1800399ac  test    rcx, rcx
0x1800399af  jz      loc_180039DF8
0x1800399b5  cmp     word ptr [rbx+10h], 3
0x1800399ba  mov     dword ptr [rsp+0A8h+arg_20], edi
0x1800399c1  jnz     short loc_1800399CD
0x1800399c3  mov     eax, [rbx+18h]
0x1800399c6  mov     dword ptr [rsp+0A8h+arg_20], eax
0x1800399cd  movsxd  rsi, dword ptr [rbx+8]
0x1800399d1  mov     r15d, [rbx+0Ch]
0x1800399d5  add     r15d, esi
0x1800399d8  cmp     r15d, esi
0x1800399db  jnb     loc_180039AC2
0x1800399e1  mov     esi, 80070216h
0x1800399e6  lea     rcx, [rsp+0A8h+pvar]; pvar
0x1800399eb  call    cs:__imp_PropVariantClear
0x1800399f1  mov     r15, [rsp+0A8h+arg_8]
0x1800399f9  xor     eax, eax
0x1800399fb  xor     r14d, r14d
0x1800399fe  jmp     short loc_180039A52
0x180039a00  test    rdx, rdx
0x180039a03  lea     rcx, [r8-2]
0x180039a07  lea     r10, [r9-1]
0x180039a0b  cmovnz  rcx, r8
0x180039a0f  cmovnz  r10, r9
0x180039a13  xor     eax, eax
0x180039a15  mov     [rcx], ax
0x180039a18  test    rdx, rdx
0x180039a1b  jnz     loc_180039C2C
0x180039a21  test    byte ptr [rsp+0A8h+arg_20], 1
0x180039a29  jnz     loc_180039CC2
0x180039a2f  mov     rdi, r15
0x180039a32  mov     r12, [rsp+0A8h+arg_18]
0x180039a3a  mov     r15, [rsp+0A8h+arg_8]
0x180039a42  test    esi, esi
0x180039a44  js      short loc_1800399E6
0x180039a46  mov     r14d, [rsp+0A8h+var_78]
0x180039a4b  mov     eax, [rsp+0A8h+arg_0]
0x180039a52  mov     rbp, [rsp+0A8h+var_20]
0x180039a5a  mov     rbx, [rsp+0A8h+var_18]
0x180039a62  test    r15, r15
0x180039a65  jz      short loc_180039A6A
0x180039a67  mov     [r15], eax
0x180039a6a  mov     rax, [rsp+0A8h+arg_10]
0x180039a72  mov     r15, [rsp+0A8h+var_40]
0x180039a77  test    rax, rax
0x180039a7a  jz      short loc_180039A7F
0x180039a7c  mov     [rax], r14d
0x180039a7f  mov     r14, [rsp+0A8h+var_38]
0x180039a84  test    r12, r12
0x180039a87  jz      short loc_180039A8D
0x180039a89  mov     [r12], rdi
0x180039a8d  mov     r12, [rsp+0A8h+var_30]
0x180039a92  mov     eax, esi
0x180039a94  mov     rdi, [rsp+0A8h+var_28]
0x180039a9c  test    r13, r13
0x180039a9f  jz      short loc_180039AB7
0x180039aa1  movups  xmm0, xmmword ptr [rsp+0A8h+pvar]
0x180039aa6  movsd   xmm1, [rsp+0A8h+var_58]
0x180039aac  movups  xmmword ptr [r13+0], xmm0
0x180039ab1  movsd   qword ptr [r13+10h], xmm1
0x180039ab7  add     rsp, 98h
0x180039abe  pop     r13
0x180039ac0  pop     rsi
0x180039ac1  retn
0x180039ac2  mov     r12, [rcx+30h]
0x180039ac6  xor     ebp, ebp
0x180039ac8  xor     ebx, ebx
0x180039aca  test    esi, esi
0x180039acc  js      loc_180039B62
0x180039ad2  mov     rax, [r14+38h]
0x180039ad6  add     r14, 38h ; '8'
0x180039ada  mov     rcx, r14
0x180039add  mov     rax, [rax]
0x180039ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ae5  cmp     esi, eax
0x180039ae7  jge     short loc_180039B62
0x180039ae9  mov     ebx, dword ptr [rsp+0A8h+arg_20]
0x180039af0  and     ebx, 1
0x180039af3  jnz     loc_180039D8C
0x180039af9  mov     rax, [r14]
0x180039afc  mov     rdx, rsi
0x180039aff  mov     rcx, r14
0x180039b02  mov     rax, [rax+8]
0x180039b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b0b  mov     rdx, rax
0x180039b0e  mov     rcx, [rax]
0x180039b11  mov     rax, [rcx+8]
0x180039b15  mov     rcx, rdx
0x180039b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b1d  mov     ebp, eax
0x180039b1f  cmp     esi, r15d
0x180039b22  jge     loc_180039E19
0x180039b28  test    ebx, ebx
0x180039b2a  jnz     loc_180039C5E
0x180039b30  mov     rax, [r14]
0x180039b33  mov     rcx, r14
0x180039b36  movsxd  rdx, r15d
0x180039b39  dec     rdx
0x180039b3c  mov     rax, [rax+8]
0x180039b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b45  mov     rdx, rax
0x180039b48  mov     rcx, [rax]
0x180039b4b  mov     rax, [rcx+18h]
0x180039b4f  mov     rcx, rdx
0x180039b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b57  mov     ebx, eax
0x180039b59  cmp     rbx, rbp
0x180039b5c  jb      loc_180039C22
0x180039b62  sub     rbx, rbp
0x180039b65  lea     r14, [rbx+1]
0x180039b69  cmp     r14, rbx
0x180039b6c  jb      loc_180039C22
0x180039b72  mov     eax, 2
0x180039b77  mul     r14
0x180039b7a  test    rdx, rdx
0x180039b7d  jnz     loc_180039C22
0x180039b83  mov     rcx, rax; cb
0x180039b86  call    cs:__imp_CoTaskMemAlloc
0x180039b8c  xor     ecx, ecx
0x180039b8e  mov     esi, 8007000Eh
0x180039b93  test    rax, rax
0x180039b96  mov     r15, rax
0x180039b99  cmovnz  esi, ecx
0x180039b9c  mov     ecx, esi
0x180039b9e  test    esi, esi
0x180039ba0  js      loc_180039E21
0x180039ba6  test    rax, rax
0x180039ba9  jz      loc_180039E2E
0x180039baf  cmp     r14, 7FFFFFFFh
0x180039bb6  ja      loc_180039E37
0x180039bbc  cmp     rbx, 7FFFFFFFh
0x180039bc3  jnb     loc_180039E42
0x180039bc9  lea     rcx, [r12+rbp*2]
0x180039bcd  test    rcx, rcx
0x180039bd0  jz      loc_180039DEA
0x180039bd6  test    r14, r14
0x180039bd9  jz      loc_180039A21
0x180039bdf  mov     rdx, r14
0x180039be2  mov     r8, r15
0x180039be5  xor     r9d, r9d
0x180039be8  nop     dword ptr [rax+rax+00000000h]
0x180039bf0  test    rbx, rbx
0x180039bf3  jz      loc_180039A00
0x180039bf9  movzx   eax, word ptr [rcx]
0x180039bfc  test    ax, ax
0x180039bff  jz      loc_180039A00
0x180039c05  mov     [r8], ax
0x180039c09  add     rcx, 2
0x180039c0d  add     r8, 2
0x180039c11  dec     rbx
0x180039c14  inc     r9
0x180039c17  sub     rdx, 1
0x180039c1b  jnz     short loc_180039BF0
0x180039c1d  jmp     loc_180039A00
0x180039c22  mov     esi, 80070216h
0x180039c27  jmp     loc_180039A32
0x180039c2c  sub     r14, r10
0x180039c2f  cmp     r14, 1
0x180039c33  jbe     loc_180039A21
0x180039c39  lea     r8, [r14+r14]
0x180039c3d  cmp     r8, 2
0x180039c41  jbe     loc_180039A21
0x180039c47  inc     r10
0x180039c4a  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180039c4e  xor     edx, edx; Val
0x180039c50  lea     rcx, [r15+r10*2]; void *
0x180039c54  call    memset_0
0x180039c59  jmp     loc_180039A21
0x180039c5e  mov     rax, [r14]
0x180039c61  mov     rcx, r14
0x180039c64  mov     rax, [rax]
0x180039c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c6c  cmp     r15d, eax
0x180039c6f  jge     loc_180039B30
0x180039c75  mov     rax, [r14]
0x180039c78  mov     rcx, r14
0x180039c7b  movsxd  rbx, r15d
0x180039c7e  mov     rdx, rbx
0x180039c81  mov     rax, [rax+8]
0x180039c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c8a  mov     rcx, rax
0x180039c8d  mov     r8, [rax]
0x180039c90  mov     rax, [r8]
0x180039c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c98  cmp     eax, 0Bh
0x180039c9b  jnz     loc_180039B30
0x180039ca1  mov     rax, [r14]
0x180039ca4  mov     rdx, rbx
0x180039ca7  mov     rcx, r14
0x180039caa  mov     rax, [rax+8]
0x180039cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cb3  mov     rdx, rax
0x180039cb6  mov     rcx, [rax]
0x180039cb9  mov     rax, [rcx+8]
0x180039cbd  jmp     loc_180039B4F
0x180039cc2  movzx   eax, word ptr [r15]
0x180039cc6  mov     rdx, r15
0x180039cc9  test    ax, ax
0x180039ccc  jz      short loc_180039CDB
0x180039cce  xchg    ax, ax
0x180039cd0  movzx   ecx, ax
0x180039cd3  cmp     ecx, 0FF02h
0x180039cd9  jnz     short loc_180039D28
0x180039cdb  movzx   ecx, word ptr [rdx]; wchar_t
0x180039cde  test    cx, cx
0x180039ce1  jz      loc_180039A2F
0x180039ce7  mov     r8, rdx
0x180039cea  movzx   r9d, word ptr [rdx+2]
0x180039cef  add     rdx, 2
0x180039cf3  mov     [r8], cx
0x180039cf7  lea     r8, [r8+2]
0x180039cfb  call    ?IsDoubleQuote@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsDoubleQuote(wchar_t)
0x180039d00  test    al, al
0x180039d02  jz      short loc_180039D15
0x180039d04  movzx   ecx, r9w; wchar_t
0x180039d08  call    ?IsDoubleQuote@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsDoubleQuote(wchar_t)
0x180039d0d  test    al, al
0x180039d0f  jz      short loc_180039D15
0x180039d11  add     rdx, 2
0x180039d15  movzx   ecx, word ptr [rdx]
0x180039d18  test    cx, cx
0x180039d1b  jnz     short loc_180039CEA
0x180039d1d  xor     eax, eax
0x180039d1f  mov     [r8], ax
0x180039d23  jmp     loc_180039A2F
0x180039d28  cmp     ecx, 201Eh
0x180039d2e  jbe     short loc_180039D60
0x180039d30  sub     ecx, 201Fh
0x180039d36  jz      short loc_180039CDB
0x180039d38  sub     ecx, 0FFEh
0x180039d3e  jz      short loc_180039CDB
0x180039d40  sub     ecx, 1
0x180039d43  jz      short loc_180039CDB
0x180039d45  cmp     ecx, 1
0x180039d48  jz      short loc_180039CDB
0x180039d4a  movzx   eax, word ptr [rdx+2]
0x180039d4e  add     rdx, 2
0x180039d52  test    ax, ax
0x180039d55  jnz     loc_180039CD0
0x180039d5b  jmp     loc_180039CDB
0x180039d60  jz      loc_180039CDB
0x180039d66  sub     ecx, 22h ; '"'
0x180039d69  jz      loc_180039CDB
0x180039d6f  sub     ecx, 89h
0x180039d75  jz      loc_180039CDB
0x180039d7b  sub     ecx, 10h
0x180039d7e  jz      loc_180039CDB
0x180039d84  sub     ecx, 1F61h
0x180039d8a  jmp     short loc_180039D43
0x180039d8c  test    esi, esi
0x180039d8e  jle     loc_180039AF9
0x180039d94  mov     rax, [r14]
0x180039d97  lea     rdx, [rsi-1]
0x180039d9b  mov     rcx, r14
0x180039d9e  mov     rax, [rax+8]
0x180039da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039da7  mov     r8, rax
0x180039daa  mov     rcx, [rax]
0x180039dad  mov     rax, [rcx]
0x180039db0  mov     rcx, r8
  ... truncated ...
```
