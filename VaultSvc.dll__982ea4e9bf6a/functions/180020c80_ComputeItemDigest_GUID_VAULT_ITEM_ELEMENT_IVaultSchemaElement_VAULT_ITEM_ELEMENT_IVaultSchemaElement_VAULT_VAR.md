# ComputeItemDigest(_GUID *,_VAULT_ITEM_ELEMENT *,IVaultSchemaElement *,_VAULT_ITEM_ELEMENT *,IVaultSchemaElement *,_VAULT_VARIANT,ushort *)

- ea: `0x180020c80`
- end: `0x180021461`
- name: `?ComputeItemDigest@@YAKPEAU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@PEAUIVaultSchemaElement@@12U_VAULT_VARIANT@@PEAG@Z`
- size: `2017`
- prototype: `unsigned int __fastcall(_OWORD *, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800135d0`
- `0x180016250`
- `0x180022290`
- `0x1800358a0`

## callees

- `0x180003140`
- `0x180003fb0`
- `0x180012210`
- `0x18001cd60`
- `0x180020c80`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004b43c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180020e51`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180020ff5`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180020e51`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180020ff5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020d76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021135`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020d76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021135`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021090`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800213a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800213e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021410`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021090`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800213a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800213e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021410`
- `bcrypt!BCryptHashData` at `0x1800211e8`
- `bcrypt!BCryptHashData` at `0x1800211e8`
- `bcrypt!BCryptFinishHash` at `0x18002120b`
- `bcrypt!BCryptFinishHash` at `0x18002120b`
- `bcrypt!BCryptDestroyHash` at `0x180021221`
- `bcrypt!BCryptDestroyHash` at `0x180021221`
- `bcrypt!BCryptCreateHash` at `0x1800211c8`
- `bcrypt!BCryptCreateHash` at `0x1800211c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002106e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180021385`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800213b6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800213ef`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002106e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180021385`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800213b6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800213ef`

## pseudocode

```c
unsigned int __fastcall ComputeItemDigest(
        _OWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  wchar_t *v9; // r14
  __int64 v10; // r15
  wchar_t *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  wchar_t *v15; // rax
  wchar_t *v16; // rdx
  unsigned int RawData; // ebx
  int v18; // edi
  __int64 v19; // rcx
  wchar_t v20; // dx
  wchar_t *v21; // rcx
  __int64 v22; // rbx
  unsigned int v23; // ebx
  size_t v24; // rdi
  unsigned int result; // eax
  unsigned int v26; // r13d
  SIZE_T v27; // rax
  wchar_t *v28; // rcx
  unsigned int v29; // eax
  size_t v30; // r15
  UCHAR *v31; // rax
  UCHAR *v32; // r12
  int v33; // ebx
  unsigned int v34; // r9d
  UCHAR v35; // dl
  __int64 v36; // r10
  __int64 v37; // rax
  UCHAR v38; // r8
  __int64 v39; // rcx
  UCHAR v40; // r8
  UCHAR v41; // r8
  UCHAR v42; // r8
  SIZE_T v43; // rax
  UCHAR *v44; // rcx
  _BYTE *v45; // rbx
  SIZE_T v46; // rax
  _BYTE *v47; // rdx
  SIZE_T v48; // rax
  wchar_t *v49; // rdx
  wchar_t *String; // [rsp+40h] [rbp-C0h] BYREF
  int v51; // [rsp+48h] [rbp-B8h]
  __int128 v52; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v53; // [rsp+60h] [rbp-A0h]
  wchar_t v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  wchar_t *v56[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h]
  HLOCAL hMem; // [rsp+98h] [rbp-68h]
  __int64 v59; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+B0h] [rbp-50h]
  __int64 v62; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v63; // [rsp+C0h] [rbp-40h]
  int v64; // [rsp+C8h] [rbp-38h]
  unsigned __int8 *v65[2]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD *v66; // [rsp+E0h] [rbp-20h]
  UCHAR pbOutput[24]; // [rsp+E8h] [rbp-18h] BYREF

  v55 = a3;
  v66 = a1;
  v57 = a6;
  *(_OWORD *)v65 = 0;
  *(_OWORD *)v56 = 0;
  v9 = 0;
  v63 = 0;
  v64 = 0;
  v62 = 0;
  hMem = 0;
  v60 = 0;
  v61 = 0;
  v59 = 0;
  LODWORD(v53) = 0;
  v52 = 0u;
  v10 = -1;
  if ( !a4 || !a5 )
  {
LABEL_42:
    String = (wchar_t *)v65[1];
    v24 = LODWORD(v65[0]);
    goto LABEL_43;
  }
  if ( *(_DWORD *)(a4 + 8) != 7
    || !*(_QWORD *)(a4 + 16)
    || ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 32LL))(a5) & 0x10) != 0 )
  {
    if ( *(_DWORD *)(a4 + 8) == 7
      && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 32LL))(a5) & 0x10) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids);
    }
    result = VaultVariantGetRawData((struct _VAULT_VARIANT *)(a4 + 8), &v65[1], (unsigned int *)v65);
    if ( result )
      return result;
    goto LABEL_42;
  }
  v11 = *(wchar_t **)(a4 + 16);
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  v13 = (unsigned int)(v12 + 1);
  if ( (unsigned int)v13 < (unsigned int)v12 )
  {
    RawData = 534;
LABEL_32:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids, RawData);
    goto LABEL_110;
  }
  v14 = (unsigned int)v13;
  v15 = (wchar_t *)LocalAlloc(0x40u, 2 * v13);
  v16 = v15;
  String = v15;
  if ( !v15 )
  {
    RawData = 14;
    goto LABEL_32;
  }
  if ( !v14 )
  {
    v18 = -2147024809;
    goto LABEL_25;
  }
  if ( v14 > 0x7FFFFFFF )
  {
    v18 = -2147024809;
    *v15 = 0;
    goto LABEL_25;
  }
  v19 = 2147483646;
  do
  {
    if ( !v19 )
      break;
    v20 = *v11;
    if ( !*v11 )
      break;
    ++v11;
    *v15++ = v20;
    --v19;
    --v14;
  }
  while ( v14 );
  v21 = v15 - 1;
  if ( v14 )
    v21 = v15;
  *v21 = 0;
  v18 = -2147024774;
  if ( v14 )
    v18 = 0;
  v16 = String;
  if ( !v14 )
  {
LABEL_25:
    VaultFreeInternal(v16);
    v16 = 0;
    String = 0;
    RawData = (unsigned __int16)v18;
    if ( (v18 & 0x1FFF0000) != 0x70000 )
      RawData = v18;
    if ( RawData )
      goto LABEL_32;
  }
  v9 = v16;
  v64 = 0;
  v63 = v16;
  v22 = -1;
  do
    ++v22;
  while ( *(_WORD *)(*(_QWORD *)(a4 + 16) + 2 * v22) );
  v23 = v22 + 1;
  _wcslwr_s(v16, v23);
  v24 = 2 * v23;
LABEL_43:
  v51 = v24;
  if ( *(_DWORD *)(a2 + 8) == 7 )
  {
    if ( *(_QWORD *)(a2 + 16) && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 32LL))(v55) & 0x10) == 0 )
    {
      RawData = DuplicateString(*(const unsigned __int16 **)(a2 + 16), &v56[1]);
      if ( RawData )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids, RawData);
        goto LABEL_110;
      }
      hMem = v56[1];
      v61 = 0;
      v60 = v56[1];
      do
        ++v10;
      while ( *(_WORD *)(*(_QWORD *)(a2 + 16) + 2 * v10) );
      _wcslwr_s(v56[1], (unsigned int)(v10 + 1));
      v26 = 2 * (v10 + 1);
      goto LABEL_67;
    }
    if ( *(_DWORD *)(a2 + 8) == 7
      && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v55 + 32LL))(v55) & 0x10) != 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids);
    }
  }
  RawData = VaultVariantGetRawData((struct _VAULT_VARIANT *)(a2 + 8), (unsigned __int8 **)&v56[1], (unsigned int *)v56);
  if ( RawData )
  {
    if ( v9 )
    {
      v27 = LocalSize(v9);
      if ( v27 )
      {
        v28 = v9;
        do
        {
          *(_BYTE *)v28 = 0;
          v28 = (wchar_t *)((char *)v28 + 1);
          --v27;
        }
        while ( v27 );
      }
      LocalFree(v9);
    }
    return RawData;
  }
  v26 = (unsigned int)v56[0];
LABEL_67:
  if ( *(_DWORD *)v57 != 8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v52);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v59);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v62);
    return 87;
  }
  if ( (unsigned int)v24 + v26 < (unsigned int)v24
    || (v29 = v24 + v26 + 16, v29 < 0x10)
    || (v30 = *(unsigned int *)(v57 + 8), (_DWORD)v30) && (v29 += v30, v29 < (unsigned int)v30) )
  {
    RawData = 534;
    goto LABEL_110;
  }
  v31 = (UCHAR *)LocalAlloc(0x40u, v29);
  v32 = v31;
  if ( !v31 )
  {
    RawData = 14;
LABEL_110:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v52);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v59);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v62);
    return RawData;
  }
  memcpy_0(v31, String, v24);
  memcpy_0(&v32[v24], v56[1], v26);
  *(_OWORD *)&v32[v26 + v24] = *v66;
  if ( (_DWORD)v30 )
    memcpy_0(&v32[v26 + 16 + v24], *(const void **)(v57 + 16), v30);
  v33 = v51 + v30 + v26;
  String = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, (BCRYPT_HASH_HANDLE *)&String, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(String, v32, v33 + 16, 0) < 0 )
    __fastfail(7u);
  if ( BCryptFinishHash(String, pbOutput, 0x14u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(String);
  String = 0;
  v52 = *(_OWORD *)L"0123456789ABCDEF";
  v53 = *(_OWORD *)L"89ABCDEF";
  v54 = a0123456789abcd[16];
  v34 = 0;
  while ( 1 )
  {
    v35 = pbOutput[v34];
    v36 = 2 * v34;
    *(_WORD *)(a7 + 2 * v36) = *((_WORD *)&v52 + ((unsigned __int64)v35 >> 4));
    *(_WORD *)(a7 + 2LL * (unsigned int)(v36 + 1)) = *((_WORD *)&v52 + (v35 & 0xF));
    v37 = v34 + 1;
    if ( (unsigned int)v37 >= 0x14 )
      break;
    v38 = pbOutput[v37];
    *(_WORD *)(a7 + 2LL * (unsigned int)(v36 + 2)) = *((_WORD *)&v52 + ((unsigned __int64)v38 >> 4));
    *(_WORD *)(a7 + 2LL * (unsigned int)(v36 + 3)) = *((_WORD *)&v52 + (v38 & 0xF));
    v39 = v34 + 2;
    if ( (unsigned int)v39 >= 0x14 )
      goto LABEL_93;
    v40 = pbOutput[v39];
    *(_WORD *)(a7 + 2LL * (unsigned int)(2 * v39)) = *((_WORD *)&v52 + ((unsigned __int64)v40 >> 4));
    *(_WORD *)(a7 + 2LL * (unsigned int)(v36 + 5)) = *((_WORD *)&v52 + (v40 & 0xF));
    v39 = v34 + 3;
    if ( (unsigned int)v39 >= 0x14
      || (v41 = pbOutput[v39],
          *(_WORD *)(a7 + 2LL * (unsigned int)(2 * v39)) = *((_WORD *)&v52 + ((unsigned __int64)v41 >> 4)),
          *(_WORD *)(a7 + 2LL * (unsigned int)(v36 + 7)) = *((_WORD *)&v52 + (v41 & 0xF)),
          v39 = v34 + 4,
          (unsigned int)v39 >= 0x14) )
    {
LABEL_93:
      v34 = v39;
      goto LABEL_95;
    }
    v42 = pbOutput[v39];
    *(_WORD *)(a7 + 2LL * (unsigned int)(2 * v39)) = *((_WORD *)&v52 + ((unsigned __int64)v42 >> 4));
    *(_WORD *)(a7 + 2LL * (unsigned int)(v36 + 9)) = *((_WORD *)&v52 + (v42 & 0xF));
    v34 += 5;
    if ( v34 >= 0x14 )
      goto LABEL_95;
  }
  ++v34;
LABEL_95:
  *(_WORD *)(a7 + 4LL * v34) = 0;
  v43 = LocalSize(v32);
  if ( v43 )
  {
    v44 = v32;
    do
    {
      *v44++ = 0;
      --v43;
    }
    while ( v43 );
  }
  LocalFree(v32);
  v45 = hMem;
  if ( hMem )
  {
    v46 = LocalSize(hMem);
    if ( v46 )
    {
      v47 = v45;
      do
      {
        *v47++ = 0;
        --v46;
      }
      while ( v46 );
    }
    LocalFree(v45);
  }
  if ( v9 )
  {
    v48 = LocalSize(v9);
    if ( v48 )
    {
      v49 = v9;
      do
      {
        *(_BYTE *)v49 = 0;
        v49 = (wchar_t *)((char *)v49 + 1);
        --v48;
      }
      while ( v48 );
    }
    LocalFree(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180020c80  push    rbp
0x180020c82  push    rbx
0x180020c83  push    rsi
0x180020c84  push    rdi
0x180020c85  push    r12
0x180020c87  push    r13
0x180020c89  push    r14
0x180020c8b  push    r15
0x180020c8d  lea     rbp, [rsp-18h]
0x180020c92  sub     rsp, 118h
0x180020c99  mov     rax, cs:__security_cookie
0x180020ca0  xor     rax, rsp
0x180020ca3  mov     [rbp+50h+var_50], rax
0x180020ca7  mov     r13, r9
0x180020caa  mov     [rsp+150h+var_D8], r8
0x180020caf  mov     r12, rdx
0x180020cb2  mov     [rbp+50h+var_70], rcx
0x180020cb6  mov     rax, [rbp+50h+arg_28]
0x180020cbd  mov     [rbp+50h+var_C0], rax
0x180020cc1  mov     rbx, [rbp+50h+arg_20]
0x180020cc8  mov     rsi, [rbp+50h+arg_30]
0x180020ccf  xorps   xmm0, xmm0
0x180020cd2  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x180020cd6  xorps   xmm1, xmm1
0x180020cd9  movups  xmmword ptr [rbp+50h+var_D0], xmm1
0x180020cdd  xor     ecx, ecx
0x180020cdf  mov     r14d, ecx
0x180020ce2  mov     [rbp+50h+var_90], rcx
0x180020ce6  mov     [rbp+50h+var_88], ecx
0x180020ce9  mov     [rbp+50h+var_98], rcx
0x180020ced  mov     [rbp+50h+hMem], rcx
0x180020cf1  mov     [rbp+50h+var_A8], rcx
0x180020cf5  mov     [rbp+50h+var_A0], ecx
0x180020cf8  mov     [rbp+50h+var_B0], rcx
0x180020cfc  mov     qword ptr [rsp+150h+var_100+8], rcx
0x180020d01  mov     dword ptr [rsp+150h+var_F0], ecx
0x180020d05  mov     qword ptr [rsp+150h+var_100], rcx
0x180020d0a  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180020d11  test    r9, r9
0x180020d14  jz      loc_180020F1C
0x180020d1a  test    rbx, rbx
0x180020d1d  jz      loc_180020F1C
0x180020d23  cmp     dword ptr [r9+8], 7
0x180020d28  jnz     loc_180020EBA
0x180020d2e  cmp     [r9+10h], rcx
0x180020d32  jz      loc_180020EBA
0x180020d38  mov     rax, [rbx]
0x180020d3b  mov     rcx, rbx
0x180020d3e  mov     rax, [rax+20h]
0x180020d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d47  test    al, 10h
0x180020d49  jnz     loc_180020EBA
0x180020d4f  mov     rdi, [r13+10h]
0x180020d53  mov     rax, r15
0x180020d56  inc     rax
0x180020d59  cmp     word ptr [rdi+rax*2], 0
0x180020d5e  jnz     short loc_180020D56
0x180020d60  lea     ecx, [rax+1]
0x180020d63  cmp     ecx, eax
0x180020d65  jb      loc_180020E5F
0x180020d6b  mov     ebx, ecx
0x180020d6d  lea     rdx, [rcx+rcx]; uBytes
0x180020d71  mov     ecx, 40h ; '@'; uFlags
0x180020d76  call    cs:__imp_LocalAlloc
0x180020d7c  mov     rdx, rax
0x180020d7f  mov     [rsp+150h+String], rax
0x180020d84  test    rax, rax
0x180020d87  jnz     short loc_180020D93
0x180020d89  mov     ebx, 0Eh
0x180020d8e  jmp     loc_180020E64
0x180020d93  test    rbx, rbx
0x180020d96  jz      short loc_180020DF5
0x180020d98  cmp     rbx, 7FFFFFFFh
0x180020d9f  jbe     short loc_180020DA8
0x180020da1  mov     edi, 80070057h
0x180020da6  jmp     short loc_180020DFF
0x180020da8  mov     ecx, 7FFFFFFEh
0x180020dad  nop     dword ptr [rax]
0x180020db0  test    rcx, rcx
0x180020db3  jz      short loc_180020DD1
0x180020db5  movzx   edx, word ptr [rdi]
0x180020db8  test    dx, dx
0x180020dbb  jz      short loc_180020DD1
0x180020dbd  add     rdi, 2
0x180020dc1  mov     [rax], dx
0x180020dc4  add     rax, 2
0x180020dc8  dec     rcx
0x180020dcb  sub     rbx, 1
0x180020dcf  jnz     short loc_180020DB0
0x180020dd1  lea     rcx, [rax-2]
0x180020dd5  test    rbx, rbx
0x180020dd8  cmovnz  rcx, rax
0x180020ddc  xor     eax, eax
0x180020dde  mov     [rcx], ax
0x180020de1  mov     edi, 8007007Ah
0x180020de6  test    rbx, rbx
0x180020de9  cmovnz  edi, eax
0x180020dec  mov     rdx, [rsp+150h+String]
0x180020df1  jz      short loc_180020E04
0x180020df3  jmp     short loc_180020E29
0x180020df5  mov     edi, 80070057h
0x180020dfa  test    rbx, rbx
0x180020dfd  jz      short loc_180020E04
0x180020dff  xor     eax, eax
0x180020e01  mov     [rdx], ax
0x180020e04  mov     rcx, rdx; hMem
0x180020e07  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180020e0c  xor     edx, edx
0x180020e0e  mov     [rsp+150h+String], rdx
0x180020e13  mov     eax, edi
0x180020e15  and     eax, 1FFF0000h
0x180020e1a  movzx   ebx, di
0x180020e1d  cmp     eax, 70000h
0x180020e22  cmovnz  ebx, edi
0x180020e25  test    ebx, ebx
0x180020e27  jnz     short loc_180020E64
0x180020e29  mov     r14, rdx
0x180020e2c  mov     [rbp+50h+var_88], 0
0x180020e33  mov     [rbp+50h+var_90], rdx
0x180020e37  mov     rax, [r13+10h]
0x180020e3b  mov     rbx, r15
0x180020e3e  xchg    ax, ax
0x180020e40  inc     rbx
0x180020e43  cmp     word ptr [rax+rbx*2], 0
0x180020e48  jnz     short loc_180020E40
0x180020e4a  inc     ebx
0x180020e4c  mov     edx, ebx; SizeInWords
0x180020e4e  mov     rcx, r14; String
0x180020e51  call    cs:__imp__wcslwr_s
0x180020e57  lea     edi, [rbx+rbx]
0x180020e5a  jmp     loc_180020F28
0x180020e5f  mov     ebx, 216h
0x180020e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e6b  lea     rax, WPP_GLOBAL_Control
0x180020e72  cmp     rcx, rax
0x180020e75  jz      short loc_180020E96
0x180020e77  test    byte ptr [rcx+1Ch], 2
0x180020e7b  jz      short loc_180020E96
0x180020e7d  mov     edx, 10h
0x180020e82  mov     r9d, ebx
0x180020e85  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x180020e8c  mov     rcx, [rcx+10h]
0x180020e90  call    WPP_SF_d
0x180020e95  nop
0x180020e96  lea     rcx, [rsp+150h+var_100]
0x180020e9b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020ea0  nop
0x180020ea1  lea     rcx, [rbp+50h+var_B0]
0x180020ea5  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020eaa  nop
0x180020eab  lea     rcx, [rbp+50h+var_98]
0x180020eaf  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020eb4  nop
0x180020eb5  jmp     loc_18002143F
0x180020eba  cmp     dword ptr [r13+8], 7
0x180020ebf  jnz     short loc_180020F02
0x180020ec1  mov     rax, [rbx]
0x180020ec4  mov     rcx, rbx
0x180020ec7  mov     rax, [rax+20h]
0x180020ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ed0  test    al, 10h
0x180020ed2  jz      short loc_180020F02
0x180020ed4  mov     rcx, cs:WPP_GLOBAL_Control
0x180020edb  lea     rax, WPP_GLOBAL_Control
0x180020ee2  cmp     rcx, rax
0x180020ee5  jz      short loc_180020F02
0x180020ee7  test    byte ptr [rcx+1Ch], 8
0x180020eeb  jz      short loc_180020F02
0x180020eed  mov     edx, 11h
0x180020ef2  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x180020ef9  mov     rcx, [rcx+10h]
0x180020efd  call    WPP_SF_
0x180020f02  lea     r8, [rbp+50h+var_80]; unsigned int *
0x180020f06  lea     rdx, [rbp+50h+var_80+8]; unsigned __int8 **
0x180020f0a  lea     rcx, [r13+8]; struct _VAULT_VARIANT *
0x180020f0e  call    ?VaultVariantGetRawData@@YAKPEAU_VAULT_VARIANT@@PEAPEAEPEAK@Z; VaultVariantGetRawData(_VAULT_VARIANT *,uchar * *,ulong *)
0x180020f13  test    eax, eax
0x180020f15  jz      short loc_180020F1C
0x180020f17  jmp     loc_180021441
0x180020f1c  mov     rax, [rbp+50h+var_80+8]
0x180020f20  mov     [rsp+150h+String], rax
0x180020f25  mov     edi, dword ptr [rbp+50h+var_80]
0x180020f28  mov     [rsp+150h+var_108], edi
0x180020f2c  mov     r13, [rsp+150h+var_D8]
0x180020f31  cmp     dword ptr [r12+8], 7
0x180020f37  jnz     loc_18002104E
0x180020f3d  cmp     qword ptr [r12+10h], 0
0x180020f43  jz      loc_180021004
0x180020f49  mov     rax, [r13+0]
0x180020f4d  mov     rcx, r13
0x180020f50  mov     rax, [rax+20h]
0x180020f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f59  test    al, 10h
0x180020f5b  jnz     loc_180021004
0x180020f61  lea     rdx, [rbp+50h+var_D0+8]; unsigned __int16 **
0x180020f65  mov     rcx, [r12+10h]; unsigned __int16 *
0x180020f6a  call    ?DuplicateString@@YAKPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180020f6f  mov     ebx, eax
0x180020f71  test    eax, eax
0x180020f73  jz      short loc_180020FCB
0x180020f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f7c  lea     rax, WPP_GLOBAL_Control
0x180020f83  cmp     rcx, rax
0x180020f86  jz      short loc_180020FA7
0x180020f88  test    byte ptr [rcx+1Ch], 2
0x180020f8c  jz      short loc_180020FA7
0x180020f8e  mov     edx, 12h
0x180020f93  mov     r9d, ebx
0x180020f96  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x180020f9d  mov     rcx, [rcx+10h]
0x180020fa1  call    WPP_SF_d
0x180020fa6  nop
0x180020fa7  lea     rcx, [rsp+150h+var_100]
0x180020fac  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020fb1  nop
0x180020fb2  lea     rcx, [rbp+50h+var_B0]
0x180020fb6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020fbb  nop
0x180020fbc  lea     rcx, [rbp+50h+var_98]
0x180020fc0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180020fc5  nop
0x180020fc6  jmp     loc_18002143F
0x180020fcb  mov     rcx, [rbp+50h+var_D0+8]; String
0x180020fcf  mov     [rbp+50h+hMem], rcx
0x180020fd3  mov     [rbp+50h+var_A0], 0
0x180020fda  mov     [rbp+50h+var_A8], rcx
0x180020fde  mov     rax, [r12+10h]
0x180020fe3  lea     r15, [r15+1]
0x180020fe7  cmp     word ptr [rax+r15*2], 0
0x180020fed  jnz     short loc_180020FE3
0x180020fef  lea     ebx, [r15+1]
0x180020ff3  mov     edx, ebx; SizeInWords
0x180020ff5  call    cs:__imp__wcslwr_s
0x180020ffb  lea     r13d, [rbx+rbx]
0x180020fff  jmp     loc_1800210A0
0x180021004  cmp     dword ptr [r12+8], 7
0x18002100a  jnz     short loc_18002104E
0x18002100c  mov     rax, [r13+0]
0x180021010  mov     rcx, r13
0x180021013  mov     rax, [rax+20h]
0x180021017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002101c  test    al, 10h
0x18002101e  jz      short loc_18002104E
0x180021020  mov     rcx, cs:WPP_GLOBAL_Control
0x180021027  lea     rax, WPP_GLOBAL_Control
0x18002102e  cmp     rcx, rax
0x180021031  jz      short loc_18002104E
0x180021033  test    byte ptr [rcx+1Ch], 8
0x180021037  jz      short loc_18002104E
0x180021039  mov     edx, 13h
0x18002103e  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x180021045  mov     rcx, [rcx+10h]
0x180021049  call    WPP_SF_
0x18002104e  lea     r8, [rbp+50h+var_D0]; unsigned int *
0x180021052  lea     rdx, [rbp+50h+var_D0+8]; unsigned __int8 **
0x180021056  lea     rcx, [r12+8]; struct _VAULT_VARIANT *
0x18002105b  call    ?VaultVariantGetRawData@@YAKPEAU_VAULT_VARIANT@@PEAPEAEPEAK@Z; VaultVariantGetRawData(_VAULT_VARIANT *,uchar * *,ulong *)
0x180021060  mov     ebx, eax
0x180021062  test    eax, eax
0x180021064  jz      short loc_18002109C
0x180021066  test    r14, r14
0x180021069  jz      short loc_180021097
0x18002106b  mov     rcx, r14; hMem
0x18002106e  call    cs:__imp_LocalSize
0x180021074  test    rax, rax
0x180021077  jz      short loc_18002108D
0x180021079  mov     rcx, r14
0x18002107c  nop     dword ptr [rax+00h]
0x180021080  mov     byte ptr [rcx], 0
0x180021083  lea     rcx, [rcx+1]
0x180021087  sub     rax, 1
0x18002108b  jnz     short loc_180021080
0x18002108d  mov     rcx, r14; hMem
0x180021090  call    cs:__imp_LocalFree
0x180021096  nop
0x180021097  jmp     loc_18002143F
0x18002109c  mov     r13d, dword ptr [rbp+50h+var_D0]
0x1800210a0  mov     rcx, [rbp+50h+var_C0]
0x1800210a4  cmp     dword ptr [rcx], 8
0x1800210a7  jz      short loc_180021101
0x1800210a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800210b0  lea     rax, WPP_GLOBAL_Control
0x1800210b7  cmp     rcx, rax
0x1800210ba  jz      short loc_1800210D8
0x1800210bc  test    byte ptr [rcx+1Ch], 8
0x1800210c0  jz      short loc_1800210D8
0x1800210c2  mov     edx, 14h
0x1800210c7  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x1800210ce  mov     rcx, [rcx+10h]
0x1800210d2  call    WPP_SF_
0x1800210d7  nop
0x1800210d8  lea     rcx, [rsp+150h+var_100]
0x1800210dd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800210e2  nop
0x1800210e3  lea     rcx, [rbp+50h+var_B0]
0x1800210e7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800210ec  nop
0x1800210ed  lea     rcx, [rbp+50h+var_98]
0x1800210f1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800210f6  nop
  ... truncated ...
```
