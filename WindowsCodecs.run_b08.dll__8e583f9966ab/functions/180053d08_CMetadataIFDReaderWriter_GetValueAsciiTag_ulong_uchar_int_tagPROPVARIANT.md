# CMetadataIFDReaderWriter::GetValueAsciiTag(ulong,uchar * *,int,tagPROPVARIANT *)

- ea: `0x180053d08`
- end: `0x1800540fe`
- name: `?GetValueAsciiTag@CMetadataIFDReaderWriter@@IEAAJKPEAPEAEHPEAUtagPROPVARIANT@@@Z`
- size: `1014`
- prototype: `int(CMetadataIFDReaderWriter *__hidden this, unsigned int, unsigned __int8 **, int, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054104`
- `0x180055030`

## callees

- `0x180052ac8`
- `0x180053d08`
- `0x1800bb784`
- `0x1800e3c04`
- `0x18017b528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180053e81`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180053e81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053ef9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053f88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053fdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053ef9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053f88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053fdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054054`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f79`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180053f79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800540f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800540f3`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetValueAsciiTag(
        CMetadataIFDReaderWriter *this,
        unsigned int a2,
        unsigned __int8 **a3,
        int a4,
        PROPVARIANT *pvar)
{
  unsigned __int8 *v5; // r12
  void *v7; // r15
  _BYTE *v8; // rdx
  unsigned int v9; // r14d
  __int64 v10; // rax
  unsigned int v11; // ecx
  unsigned __int8 *v12; // r9
  unsigned int v13; // edx
  int v14; // ebx
  int v15; // r13d
  unsigned int v16; // r8d
  unsigned int v17; // edx
  int v18; // r8d
  __int64 v19; // rcx
  int v20; // r14d
  LPVOID *v21; // rdi
  PROPVARIANT *v22; // rcx
  int v24; // eax
  __int64 v25; // rdx
  int v26; // ecx
  unsigned __int8 *v27; // rax
  unsigned __int8 *v28; // rbx
  unsigned __int64 v29; // rax
  bool v30; // zf
  unsigned int v31; // esi
  BYTE *v32; // rax
  int v33; // r13d
  BYTE *v34; // rdi
  PROPVARIANT *v35; // rax
  unsigned int v36; // edi
  unsigned int v37; // esi
  void *v38; // rax
  bool v39; // zf
  unsigned int v40; // eax
  size_t v41; // r8
  __int64 v42; // rbx
  unsigned int v43; // [rsp+30h] [rbp-40h]
  unsigned int v44; // [rsp+34h] [rbp-3Ch]
  int v45; // [rsp+38h] [rbp-38h] BYREF
  int *v46; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 *v47; // [rsp+48h] [rbp-28h]
  void *Block[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v49; // [rsp+60h] [rbp-10h]
  unsigned int v50; // [rsp+68h] [rbp-8h]
  char v51; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int8 **v52; // [rsp+C0h] [rbp+50h]
  int v53; // [rsp+C8h] [rbp+58h]

  v53 = a4;
  v52 = a3;
  v5 = *a3;
  v51 = 0;
  v49 = 0;
  v50 = 0;
  v7 = 0;
  v8 = (char *)this + 132;
  v9 = 0;
  *(_OWORD *)Block = 0;
  if ( !a2 )
  {
    if ( (*v8 & 2) != 0 )
      goto LABEL_55;
    a2 = 1;
    v53 = 0;
    v5 = (unsigned __int8 *)&v51;
  }
  if ( !v5[a2 - 1] )
    goto LABEL_3;
  if ( (*v8 & 2) != 0 )
  {
LABEL_55:
    v14 = -2003292317;
LABEL_56:
    v39 = (_DWORD)g_doStackCaptures == 0;
LABEL_57:
    if ( !v39 )
      DoStackCapture(v14);
    goto LABEL_46;
  }
  if ( a2 + 1 < a2 )
  {
    v30 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_43;
  }
  v7 = CoTaskMemAlloc(a2 + 1);
  if ( !v7 )
  {
LABEL_69:
    v14 = -2147024882;
    goto LABEL_56;
  }
  v40 = a2;
  v41 = a2++;
  v42 = v40;
  memcpy_0(v7, v5, v41);
  *((_BYTE *)v7 + v42) = 0;
  v5 = (unsigned __int8 *)v7;
LABEL_3:
  v10 = 0;
  v11 = 0;
  v44 = 0;
  v12 = v5;
  v47 = v5;
  v13 = 0;
  v14 = 0;
  while ( 1 )
  {
    v43 = v13;
    v15 = v14;
    if ( v13 >= a2 )
      break;
    if ( *v12 )
    {
      ++v13;
      goto LABEL_7;
    }
    v16 = v13;
    v17 = v9 + 1;
    v18 = v16 - v11 + 1;
    v45 = v18;
    if ( v9 + 1 < v9 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024362);
      v14 = -2147024362;
LABEL_39:
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v14);
LABEL_15:
      if ( v14 < 0 )
        goto LABEL_46;
      v12 = v47;
      goto LABEL_17;
    }
    if ( v17 > HIDWORD(v49) )
    {
      v46 = &v45;
      v24 = DynArrayImpl<0>::Grow(Block, 4u, 1, 0, (unsigned __int64 *)&v46);
      v14 = v24;
      if ( v24 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v24);
        v9 = v50;
      }
      else
      {
        v25 = 4 * v50;
        v9 = v50 + 1;
        v26 = *v46;
        ++v50;
        *(_DWORD *)((char *)Block[0] + v25) = v26;
      }
      if ( v14 < 0 )
        goto LABEL_39;
      goto LABEL_15;
    }
    v14 = 0;
    v19 = v9++;
    v50 = v17;
    *((_DWORD *)Block[0] + v19) = v18;
LABEL_17:
    v10 = v44 + 1;
    v11 = v43 + 1;
    ++v44;
    v13 = v43 + 1;
LABEL_7:
    v47 = ++v12;
  }
  if ( (_DWORD)v10 != 1 )
  {
    v29 = 8 * v10;
    if ( v29 > 0xFFFFFFFF )
    {
      v30 = (_DWORD)g_doStackCaptures == 0;
LABEL_43:
      if ( !v30 )
        DoStackCapture(-2147024362);
      v14 = -2147024362;
LABEL_46:
      v20 = v53;
LABEL_47:
      v21 = (LPVOID *)v52;
      PropVariantClear(pvar);
      goto LABEL_23;
    }
    v31 = v29;
    v32 = (BYTE *)CoTaskMemAlloc((unsigned int)v29);
    v33 = 0;
    v34 = v32;
    if ( v32 )
    {
      v14 = 0;
      memset_0(v32, 0, v31);
      v35 = pvar;
      pvar[2] = v34;
      v36 = 0;
      *(_WORD *)v35 = 4126;
      *((_DWORD *)v35 + 2) = v44;
      while ( 1 )
      {
        if ( v36 >= v44 )
        {
          v21 = (LPVOID *)v52;
          v20 = v53;
          goto LABEL_23;
        }
        v37 = *((_DWORD *)Block[0] + v36);
        v38 = CoTaskMemAlloc(v37);
        if ( !v38 )
          break;
        *((_QWORD *)pvar[2] + v36) = v38;
        memcpy_0(v38, &v5[v33], v37);
        v33 += v37;
        ++v36;
      }
      v39 = (_DWORD)g_doStackCaptures == 0;
      v14 = -2147024882;
      goto LABEL_57;
    }
    goto LABEL_69;
  }
  v20 = v53;
  if ( v7 )
  {
    v5 = (unsigned __int8 *)v7;
    v7 = 0;
    goto LABEL_35;
  }
  if ( v53 )
  {
    v21 = (LPVOID *)v52;
    *v52 = 0;
    goto LABEL_22;
  }
  v27 = (unsigned __int8 *)CoTaskMemAlloc(a2);
  v28 = v27;
  if ( !v27 )
  {
    v14 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
    goto LABEL_47;
  }
  memcpy_0(v27, v5, a2);
  v5 = v28;
LABEL_35:
  v21 = (LPVOID *)v52;
LABEL_22:
  v22 = pvar;
  *(_WORD *)pvar = 30;
  v22[1] = v5;
  v14 = v15;
LABEL_23:
  if ( v20 && *v21 )
  {
    CoTaskMemFree(*v21);
    *v21 = 0;
  }
  if ( v7 )
    CoTaskMemFree(v7);
  if ( Block[0] != Block[1] )
    free(Block[0]);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180053d08  mov     [rsp-38h+arg_0], rbx
0x180053d0d  mov     [rsp-38h+arg_18], r9d
0x180053d12  mov     [rsp-38h+arg_10], r8
0x180053d17  push    rbp
0x180053d18  push    rsi
0x180053d19  push    rdi
0x180053d1a  push    r12
0x180053d1c  push    r13
0x180053d1e  push    r14
0x180053d20  push    r15
0x180053d22  mov     rbp, rsp
0x180053d25  sub     rsp, 70h
0x180053d29  mov     r12, [r8]
0x180053d2c  xor     r13d, r13d
0x180053d2f  mov     esi, edx
0x180053d31  mov     [rbp+arg_8], r13b
0x180053d35  mov     [rbp+var_10], r13
0x180053d39  xorps   xmm0, xmm0
0x180053d3c  mov     [rbp+var_8], r13d
0x180053d40  mov     r15d, r13d
0x180053d43  lea     rdx, [rcx+84h]
0x180053d4a  mov     r14d, r13d
0x180053d4d  movdqu  xmmword ptr [rbp+Block], xmm0
0x180053d52  test    esi, esi
0x180053d54  jz      loc_1800540BF
0x180053d5a  lea     eax, [rsi-1]
0x180053d5d  cmp     [rax+r12], r13b
0x180053d61  jnz     loc_18005401D
0x180053d67  mov     eax, r13d
0x180053d6a  mov     ecx, r13d
0x180053d6d  mov     [rbp+var_3C], eax
0x180053d70  mov     r9, r12
0x180053d73  mov     [rbp+var_28], r12
0x180053d77  mov     edx, r13d
0x180053d7a  mov     ebx, r13d
0x180053d7d  mov     edi, 80070216h
0x180053d82  mov     [rbp+var_40], edx
0x180053d85  mov     r13d, ebx
0x180053d88  cmp     edx, esi
0x180053d8a  jnb     loc_180053E15
0x180053d90  xor     r13d, r13d
0x180053d93  cmp     [r9], r13b
0x180053d96  jz      short loc_180053DA3
0x180053d98  inc     edx
0x180053d9a  inc     r9
0x180053d9d  mov     [rbp+var_28], r9
0x180053da1  jmp     short loc_180053D82
0x180053da3  mov     r8d, edx
0x180053da6  lea     edx, [r14+1]
0x180053daa  sub     r8d, ecx
0x180053dad  inc     r8d
0x180053db0  mov     [rbp+var_38], r8d
0x180053db4  cmp     edx, r14d
0x180053db7  jb      loc_180053F25
0x180053dbd  cmp     edx, dword ptr [rbp+var_10+4]
0x180053dc0  ja      loc_180053EA1
0x180053dc6  mov     rax, [rbp+Block]
0x180053dca  mov     ebx, r13d
0x180053dcd  mov     ecx, r14d
0x180053dd0  mov     r14d, edx
0x180053dd3  mov     [rbp+var_8], edx
0x180053dd6  mov     [rax+rcx*4], r8d
0x180053dda  jmp     short loc_180053E04
0x180053ddc  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180053de3  jz      short loc_180053DEC
0x180053de5  mov     ecx, ebx; int
0x180053de7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180053dec  mov     r14d, [rbp+var_8]
0x180053df0  test    ebx, ebx
0x180053df2  js      loc_180053F37
0x180053df8  test    ebx, ebx
0x180053dfa  js      loc_180053F6D
0x180053e00  mov     r9, [rbp+var_28]
0x180053e04  mov     eax, [rbp+var_3C]
0x180053e07  mov     ecx, [rbp+var_40]
0x180053e0a  inc     eax
0x180053e0c  inc     ecx
0x180053e0e  mov     [rbp+var_3C], eax
0x180053e11  mov     edx, ecx
0x180053e13  jmp     short loc_180053D9A
0x180053e15  cmp     eax, 1
0x180053e18  jnz     loc_180053F50
0x180053e1e  mov     r14d, [rbp+arg_18]
0x180053e22  test    r15, r15
0x180053e25  jnz     loc_180054040
0x180053e2b  test    r14d, r14d
0x180053e2e  jz      loc_180053EF5
0x180053e34  mov     rdi, [rbp+arg_10]
0x180053e38  mov     [rdi], r15
0x180053e3b  mov     rcx, [rbp+pvar]
0x180053e3f  mov     word ptr [rcx], 1Eh
0x180053e44  mov     [rcx+8], r12
0x180053e48  mov     ebx, r13d
0x180053e4b  test    r13d, r13d
0x180053e4e  js      loc_180053F79
0x180053e54  test    r14d, r14d
0x180053e57  jz      short loc_180053E6E
0x180053e59  mov     rcx, [rdi]; pv
0x180053e5c  test    rcx, rcx
0x180053e5f  jz      short loc_180053E6E
0x180053e61  call    cs:__imp_CoTaskMemFree
0x180053e67  mov     qword ptr [rdi], 0
0x180053e6e  test    r15, r15
0x180053e71  jnz     loc_1800540F0
0x180053e77  mov     rcx, [rbp+Block]; Block
0x180053e7b  cmp     rcx, [rbp+Block+8]
0x180053e7f  jz      short loc_180053E87
0x180053e81  call    cs:__imp_free
0x180053e87  mov     eax, ebx
0x180053e89  mov     rbx, [rsp+70h+arg_0]
0x180053e91  add     rsp, 70h
0x180053e95  pop     r15
0x180053e97  pop     r14
0x180053e99  pop     r13
0x180053e9b  pop     r12
0x180053e9d  pop     rdi
0x180053e9e  pop     rsi
0x180053e9f  pop     rbp
0x180053ea0  retn
0x180053ea1  xor     r9d, r9d
0x180053ea4  lea     rax, [rbp+var_38]
0x180053ea8  mov     [rbp+var_30], rax
0x180053eac  lea     rcx, [rbp+Block]
0x180053eb0  lea     rax, [rbp+var_30]
0x180053eb4  mov     [rsp+70h+var_50], rax
0x180053eb9  lea     edx, [r9+4]
0x180053ebd  lea     r8d, [r9+1]
0x180053ec1  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x180053ec6  mov     ebx, eax
0x180053ec8  test    eax, eax
0x180053eca  js      loc_180053DDC
0x180053ed0  mov     r14d, [rbp+var_8]
0x180053ed4  mov     rax, [rbp+var_30]
0x180053ed8  lea     edx, ds:0[r14*4]
0x180053ee0  inc     r14d
0x180053ee3  mov     ecx, [rax]
0x180053ee5  mov     rax, [rbp+Block]
0x180053ee9  mov     [rbp+var_8], r14d
0x180053eed  mov     [rdx+rax], ecx
0x180053ef0  jmp     loc_180053DF0
0x180053ef5  mov     ecx, esi; cb
0x180053ef7  mov     edi, esi
0x180053ef9  call    cs:__imp_CoTaskMemAlloc
0x180053eff  mov     rbx, rax
0x180053f02  test    rax, rax
0x180053f05  jz      loc_1800540A1
0x180053f0b  mov     r8d, edi; Size
0x180053f0e  mov     rdx, r12; Src
0x180053f11  mov     rcx, rax; void *
0x180053f14  call    memcpy_0
0x180053f19  mov     r12, rbx
0x180053f1c  mov     rdi, [rbp+arg_10]
0x180053f20  jmp     loc_180053E3B
0x180053f25  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180053f2c  jz      short loc_180053F35
0x180053f2e  mov     ecx, edi; int
0x180053f30  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180053f35  mov     ebx, edi
0x180053f37  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180053f3e  jz      loc_180053DF8
0x180053f44  mov     ecx, ebx; int
0x180053f46  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180053f4b  jmp     loc_180053DF8
0x180053f50  shl     rax, 3
0x180053f54  mov     ecx, 0FFFFFFFFh
0x180053f59  cmp     rax, rcx
0x180053f5c  jbe     short loc_180053F84
0x180053f5e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180053f65  jnz     loc_1800540E4
0x180053f6b  mov     ebx, edi
0x180053f6d  mov     r14d, [rbp+arg_18]
0x180053f71  mov     rcx, [rbp+pvar]; pvar
0x180053f75  mov     rdi, [rbp+arg_10]
0x180053f79  call    cs:__imp_PropVariantClear
0x180053f7f  jmp     loc_180053E54
0x180053f84  mov     ecx, eax; cb
0x180053f86  mov     esi, eax
0x180053f88  call    cs:__imp_CoTaskMemAlloc
0x180053f8e  xor     r13d, r13d
0x180053f91  mov     rdi, rax
0x180053f94  test    rax, rax
0x180053f97  jz      loc_1800540DA
0x180053f9d  mov     r8d, esi; Size
0x180053fa0  xor     edx, edx; Val
0x180053fa2  mov     rcx, rax; void *
0x180053fa5  mov     ebx, r13d
0x180053fa8  call    memset_0
0x180053fad  mov     rax, [rbp+pvar]
0x180053fb1  mov     r14d, [rbp+var_3C]
0x180053fb5  mov     [rax+10h], rdi
0x180053fb9  mov     edi, r13d
0x180053fbc  mov     word ptr [rax], 101Eh
0x180053fc1  mov     [rax+8], r14d
0x180053fc5  mov     [rbp+var_3C], r13d
0x180053fc9  cmp     edi, r14d
0x180053fcc  jnb     short loc_180054010
0x180053fce  mov     rax, [rbp+Block]
0x180053fd2  mov     r13d, edi
0x180053fd5  mov     esi, [rax+r13*4]
0x180053fd9  mov     ecx, esi; cb
0x180053fdb  call    cs:__imp_CoTaskMemAlloc
0x180053fe1  test    rax, rax
0x180053fe4  jz      loc_180054093
0x180053fea  mov     rcx, [rbp+pvar]
0x180053fee  mov     r8d, esi; Size
0x180053ff1  mov     rcx, [rcx+10h]
0x180053ff5  mov     [rcx+r13*8], rax
0x180053ff9  mov     rcx, rax; void *
0x180053ffc  mov     r13d, [rbp+var_3C]
0x180054000  lea     rdx, [r12+r13]; Src
0x180054004  call    memcpy_0
0x180054009  add     r13d, esi
0x18005400c  inc     edi
0x18005400e  jmp     short loc_180053FC5
0x180054010  mov     rdi, [rbp+arg_10]
0x180054014  mov     r14d, [rbp+arg_18]
0x180054018  jmp     loc_180053E54
0x18005401d  test    byte ptr [rdx], 2
0x180054020  jz      short loc_18005404B
0x180054022  mov     ebx, 88982F63h
0x180054027  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18005402e  jz      loc_180053F6D
0x180054034  mov     ecx, ebx; int
0x180054036  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18005403b  jmp     loc_180053F6D
0x180054040  mov     r12, r15
0x180054043  xor     r15d, r15d
0x180054046  jmp     loc_180053F1C
0x18005404b  lea     ebx, [rsi+1]
0x18005404e  cmp     ebx, esi
0x180054050  jb      short loc_180054082
0x180054052  mov     ecx, ebx; cb
0x180054054  call    cs:__imp_CoTaskMemAlloc
0x18005405a  mov     r15, rax
0x18005405d  test    rax, rax
0x180054060  jz      short loc_1800540DA
0x180054062  mov     eax, esi
0x180054064  mov     rdx, r12; Src
0x180054067  mov     r8d, eax; Size
0x18005406a  mov     esi, ebx
0x18005406c  mov     rcx, r15; void *
0x18005406f  mov     ebx, eax
0x180054071  call    memcpy_0
0x180054076  mov     [rbx+r15], r13b
0x18005407a  mov     r12, r15
0x18005407d  jmp     loc_180053D67
0x180054082  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180054089  mov     edi, 80070216h
0x18005408e  jmp     loc_180053F65
0x180054093  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18005409a  mov     ebx, 8007000Eh
0x18005409f  jmp     short loc_18005402E
0x1800540a1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800540a8  mov     ebx, 8007000Eh
0x1800540ad  jz      loc_180053F71
0x1800540b3  mov     ecx, ebx; int
0x1800540b5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800540ba  jmp     loc_180053F71
0x1800540bf  test    byte ptr [rdx], 2
0x1800540c2  jnz     loc_180054022
0x1800540c8  mov     esi, 1
0x1800540cd  mov     [rbp+arg_18], r13d
0x1800540d1  lea     r12, [rbp+arg_8]
0x1800540d5  jmp     loc_180053D5A
0x1800540da  mov     ebx, 8007000Eh
0x1800540df  jmp     loc_180054027
0x1800540e4  mov     ecx, edi; int
0x1800540e6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800540eb  jmp     loc_180053F6B
0x1800540f0  mov     rcx, r15; pv
0x1800540f3  call    cs:__imp_CoTaskMemFree
0x1800540f9  jmp     loc_180053E77
```
