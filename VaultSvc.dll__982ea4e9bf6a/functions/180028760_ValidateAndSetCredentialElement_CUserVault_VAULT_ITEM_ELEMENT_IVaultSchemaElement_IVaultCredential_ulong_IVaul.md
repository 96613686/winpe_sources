# ValidateAndSetCredentialElement(CUserVault *,_VAULT_ITEM_ELEMENT *,IVaultSchemaElement *,IVaultCredential *,ulong (IVaultCredential::*)(IVaultSchemaElement *,_VAULT_VARIANT *),uchar,uchar *,_VAULT_CAUB *)

- ea: `0x180028760`
- end: `0x180028ccc`
- name: `?ValidateAndSetCredentialElement@@YAKPEAVCUserVault@@PEAU_VAULT_ITEM_ELEMENT@@PEAUIVaultSchemaElement@@PEAUIVaultCredential@@P84@EAAK2PEAU_VAULT_VARIANT@@@ZEPEAEPEAU_VAULT_CAUB@@@Z`
- size: `1388`
- prototype: `__int64 __fastcall(CUserVault *, int *, __int64, __int64, __int64 (__fastcall *)(__int64, __int64, unsigned int *), char, void *, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180016250`
- `0x180028600`

## callees

- `0x180003140`
- `0x18000aac0`
- `0x180028760`
- `0x18002a4a0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003be38`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028b60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028b60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c20`
- `bcrypt!BCryptHashData` at `0x180028a43`
- `bcrypt!BCryptHashData` at `0x180028a43`
- `bcrypt!BCryptFinishHash` at `0x180028a66`
- `bcrypt!BCryptFinishHash` at `0x180028a66`
- `bcrypt!BCryptDestroyHash` at `0x180028a7c`
- `bcrypt!BCryptDestroyHash` at `0x180028a7c`
- `bcrypt!BCryptCreateHash` at `0x180028a24`
- `bcrypt!BCryptCreateHash` at `0x180028a24`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180028b38`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180028bf7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180028b38`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180028bf7`

## pseudocode

```c
__int64 __fastcall ValidateAndSetCredentialElement(
        CUserVault *a1,
        int *a2,
        __int64 a3,
        __int64 a4,
        __int64 (__fastcall *a5)(__int64, __int64, unsigned int *),
        char a6,
        void *a7,
        __int64 a8)
{
  _BYTE *v10; // rsi
  unsigned int v11; // r12d
  void (__fastcall *v12)(HLOCAL); // r13
  int v13; // ebx
  int v14; // eax
  unsigned int *v15; // rbx
  int v16; // ecx
  int v17; // eax
  _QWORD *v18; // r8
  __int64 v19; // rax
  int v20; // edx
  __int64 v21; // rax
  __int64 v22; // rax
  struct _GUID *v23; // rdx
  ULONG v24; // ebx
  UCHAR *v25; // rdi
  unsigned int v26; // edi
  HLOCAL v27; // rbx
  __int64 v28; // rcx
  _BYTE *v29; // rax
  SIZE_T v30; // rdx
  _BYTE *v31; // rax
  __int64 v33; // rdx
  unsigned int v34; // ebx
  _BYTE *v35; // rcx
  SIZE_T v36; // rax
  _BYTE *v37; // rdx
  int v38; // eax
  int pbSecret; // [rsp+20h] [rbp-A1h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-81h] BYREF
  int v41; // [rsp+48h] [rbp-79h] BYREF
  void (__fastcall *v42)(HLOCAL); // [rsp+50h] [rbp-71h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-69h] BYREF
  unsigned int v44; // [rsp+60h] [rbp-61h]
  CUserVault *v45; // [rsp+68h] [rbp-59h]
  __int128 v46; // [rsp+70h] [rbp-51h] BYREF
  HLOCAL v47; // [rsp+80h] [rbp-41h]
  unsigned int *v48; // [rsp+88h] [rbp-39h]
  __int64 v49; // [rsp+90h] [rbp-31h]
  __int64 (__fastcall *v50)(__int64, __int64, unsigned int *); // [rsp+98h] [rbp-29h]
  UCHAR pbOutput[24]; // [rsp+A0h] [rbp-21h] BYREF

  v49 = a4;
  v45 = a1;
  v50 = a5;
  phHash = a7;
  v10 = 0;
  hMem = 0;
  v11 = 0;
  v44 = 0;
  v12 = 0;
  v42 = 0;
  v41 = 0;
  v46 = 0;
  v47 = 0;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
LABEL_5:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v42);
    return 87;
  }
  if ( !a6 )
  {
    v13 = *a2;
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3) != v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
      goto LABEL_5;
    }
  }
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3);
  v15 = (unsigned int *)(a2 + 2);
  v16 = a2[2];
  if ( v16 != v14 )
  {
LABEL_73:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 24LL))(a3);
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, *v15, v38);
    }
    return 87;
  }
  if ( v16 == 7 )
  {
    v21 = *((_QWORD *)a2 + 2);
    if ( v21 )
    {
      *(_QWORD *)(a8 + 8) = v21;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(*((_QWORD *)a2 + 2) + 2 * v22) );
      v17 = 2 * v22 + 2;
    }
    else
    {
LABEL_33:
      *(_QWORD *)(a8 + 8) = 0;
      v17 = 0;
    }
  }
  else
  {
    switch ( v16 )
    {
      case 0:
        *(_QWORD *)(a8 + 8) = a2 + 4;
        v17 = 1;
        break;
      case 1:
      case 2:
        *(_QWORD *)(a8 + 8) = a2 + 4;
        v17 = 2;
        break;
      case 3:
      case 4:
        *(_QWORD *)(a8 + 8) = a2 + 4;
        v17 = 4;
        break;
      case 5:
        *(_QWORD *)(a8 + 8) = a2 + 4;
        v17 = 8;
        break;
      case 6:
        *(_QWORD *)(a8 + 8) = a2 + 4;
        v17 = 16;
        break;
      case 8:
      case 10:
        if ( !a2[4] )
          goto LABEL_33;
        *(_QWORD *)(a8 + 8) = *((_QWORD *)a2 + 3);
        v17 = a2[4];
        break;
      case 11:
        v18 = (_QWORD *)*((_QWORD *)a2 + 2);
        if ( !v18 )
          goto LABEL_33;
        if ( *v18 )
        {
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)(*v18 + 2 * v19) );
          v20 = 2 * v19 + 2;
        }
        else
        {
          v20 = 0;
        }
        *(_QWORD *)(a8 + 8) = v18;
        v17 = v20 + *(_DWORD *)(*((_QWORD *)a2 + 2) + 16LL) + 32;
        break;
      default:
        goto LABEL_73;
    }
  }
  *(_DWORD *)a8 = v17;
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a3 + 16LL))(a3) == 2 || CUserVault::IsCredmanVault(v45, v23) )
  {
    *(_BYTE *)phHash = 0;
  }
  else
  {
    LODWORD(v46) = 10;
    *(_BYTE *)phHash = 1;
    v15 = (unsigned int *)&v46;
    v48 = (unsigned int *)&v46;
    if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 32LL))(a3) & 4) != 0 )
    {
      v24 = *(_DWORD *)a8;
      v25 = *(UCHAR **)(a8 + 8);
      phHash = 0;
      if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
        __fastfail(7u);
      if ( BCryptHashData(phHash, v25, v24, 0) < 0 )
        __fastfail(7u);
      if ( BCryptFinishHash(phHash, pbOutput, 0x14u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash);
      phHash = 0;
      LOBYTE(pbSecret) = 0;
      v26 = CUserVault::EncryptData(v45, 0, pbOutput, 20, pbSecret, &hMem, &v41);
      if ( v26 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids, v26);
        v27 = hMem;
        if ( hMem )
        {
          if ( v44 )
          {
            v28 = v44;
            v29 = hMem;
            do
            {
              *v29++ = 0;
              --v28;
            }
            while ( v28 );
          }
          if ( v42 )
          {
            v42(v27);
          }
          else if ( v27 )
          {
            v30 = LocalSize(v27);
            if ( v30 )
            {
              v31 = v27;
              do
              {
                *v31++ = 0;
                --v30;
              }
              while ( v30 );
            }
            LocalFree(v27);
          }
        }
        return v26;
      }
      DWORD2(v46) = v41;
      v10 = hMem;
      v47 = hMem;
      v11 = v44;
      v12 = v42;
      v15 = v48;
    }
    else
    {
      DWORD2(v46) = 0;
    }
  }
  v34 = v50(v49, a3, v15);
  if ( v10 )
  {
    if ( v11 )
    {
      v33 = v11;
      v35 = v10;
      do
      {
        *v35++ = 0;
        --v33;
      }
      while ( v33 );
    }
    if ( v12 )
    {
      ((void (__fastcall *)(_BYTE *, __int64))v12)(v10, v33);
    }
    else
    {
      v36 = LocalSize(v10);
      if ( v36 )
      {
        v37 = v10;
        do
        {
          *v37++ = 0;
          --v36;
        }
        while ( v36 );
      }
      LocalFree(v10);
    }
  }
  return v34;
}

```

## disassembly

```asm
0x180028760  push    rbp
0x180028762  push    rbx
0x180028763  push    rsi
0x180028764  push    rdi
0x180028765  push    r12
0x180028767  push    r13
0x180028769  push    r14
0x18002876b  push    r15
0x18002876d  lea     rbp, [rsp-7]
0x180028772  sub     rsp, 0C8h
0x180028779  mov     rax, cs:__security_cookie
0x180028780  xor     rax, rsp
0x180028783  mov     [rbp+3Fh+var_48], rax
0x180028787  mov     [rbp+3Fh+var_70], r9
0x18002878b  mov     r15, r8
0x18002878e  mov     rdi, rdx
0x180028791  mov     [rbp+3Fh+var_98], rcx
0x180028795  mov     r14, [rbp+3Fh+arg_38]
0x18002879c  mov     rax, [rbp+3Fh+arg_20]
0x1800287a0  mov     [rbp+3Fh+var_68], rax
0x1800287a4  mov     rax, [rbp+3Fh+arg_30]
0x1800287a8  mov     [rsp+100h+phHash], rax
0x1800287ad  xor     esi, esi
0x1800287af  mov     [rbp+3Fh+hMem], rsi
0x1800287b3  xor     r12d, r12d
0x1800287b6  mov     [rbp+3Fh+var_A0], r12d
0x1800287ba  xor     r13d, r13d
0x1800287bd  mov     [rbp+3Fh+var_B0], r13
0x1800287c1  mov     [rbp+3Fh+var_B8], r13d
0x1800287c5  xorps   xmm0, xmm0
0x1800287c8  xor     eax, eax
0x1800287ca  movups  [rbp+3Fh+var_90], xmm0
0x1800287ce  mov     [rbp+3Fh+var_80], rax
0x1800287d2  test    r8, r8
0x1800287d5  jnz     short loc_180028815
0x1800287d7  lea     rax, WPP_GLOBAL_Control
0x1800287de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287e5  cmp     rcx, rax
0x1800287e8  jz      short loc_180028806
0x1800287ea  test    byte ptr [rcx+1Ch], 2
0x1800287ee  jz      short loc_180028806
0x1800287f0  mov     edx, 12h
0x1800287f5  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x1800287fc  mov     rcx, [rcx+10h]
0x180028800  call    WPP_SF_
0x180028805  nop
0x180028806  lea     rcx, [rbp+3Fh+var_B0]
0x18002880a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002880f  nop
0x180028810  jmp     loc_180028C77
0x180028815  cmp     [rbp+3Fh+arg_28], al
0x180028818  jnz     short loc_18002886D
0x18002881a  mov     ebx, [rdx]
0x18002881c  mov     rax, [r8]
0x18002881f  mov     rcx, r15
0x180028822  mov     rax, [rax+8]
0x180028826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002882b  cmp     eax, ebx
0x18002882d  jz      short loc_18002886D
0x18002882f  lea     rax, WPP_GLOBAL_Control
0x180028836  mov     rcx, cs:WPP_GLOBAL_Control
0x18002883d  cmp     rcx, rax
0x180028840  jz      short loc_18002885E
0x180028842  test    byte ptr [rcx+1Ch], 2
0x180028846  jz      short loc_18002885E
0x180028848  mov     edx, 13h
0x18002884d  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x180028854  mov     rcx, [rcx+10h]
0x180028858  call    WPP_SF_
0x18002885d  nop
0x18002885e  lea     rcx, [rbp+3Fh+var_B0]
0x180028862  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180028867  nop
0x180028868  jmp     loc_180028C77
0x18002886d  mov     rax, [r15]
0x180028870  mov     rcx, r15
0x180028873  mov     rax, [rax+18h]
0x180028877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002887c  lea     rbx, [rdi+8]
0x180028880  movsxd  rcx, dword ptr [rbx]
0x180028883  cmp     ecx, eax
0x180028885  jnz     def_1800288AE; jumptable 00000001800288AE default case, cases 7,9
0x18002888b  cmp     ecx, 7
0x18002888e  jz      loc_180028969
0x180028894  cmp     ecx, 0Bh; switch 12 cases
0x180028897  ja      def_1800288AE; jumptable 00000001800288AE default case, cases 7,9
0x18002889d  lea     rdx, __ImageBase
0x1800288a4  mov     ecx, ds:(jpt_1800288AE - 180000000h)[rdx+rcx*4]
0x1800288ab  add     rcx, rdx
0x1800288ae  jmp     rcx; switch jump
0x1800288b0  lea     rax, [rdi+10h]; jumptable 00000001800288AE case 0
0x1800288b4  mov     [r14+8], rax
0x1800288b8  mov     eax, 1
0x1800288bd  jmp     loc_18002899F
0x1800288c2  lea     rax, [rdi+10h]; jumptable 00000001800288AE cases 1,2
0x1800288c6  mov     [r14+8], rax
0x1800288ca  mov     eax, 2
0x1800288cf  jmp     loc_18002899F
0x1800288d4  lea     rax, [rdi+10h]; jumptable 00000001800288AE cases 3,4
0x1800288d8  mov     [r14+8], rax
0x1800288dc  mov     eax, 4
0x1800288e1  jmp     loc_18002899F
0x1800288e6  lea     rax, [rdi+10h]; jumptable 00000001800288AE case 5
0x1800288ea  mov     [r14+8], rax
0x1800288ee  mov     eax, 8
0x1800288f3  jmp     loc_18002899F
0x1800288f8  lea     rax, [rdi+10h]; jumptable 00000001800288AE case 6
0x1800288fc  mov     [r14+8], rax
0x180028900  mov     eax, 10h
0x180028905  jmp     loc_18002899F
0x18002890a  cmp     dword ptr [rdi+10h], 0; jumptable 00000001800288AE cases 8,10
0x18002890e  jz      loc_180028995
0x180028914  mov     rax, [rdi+18h]
0x180028918  mov     [r14+8], rax
0x18002891c  mov     eax, [rdi+10h]
0x18002891f  jmp     loc_18002899F
0x180028924  mov     r8, [rdi+10h]; jumptable 00000001800288AE case 11
0x180028928  test    r8, r8
0x18002892b  jz      short loc_180028995
0x18002892d  mov     rcx, [r8]
0x180028930  test    rcx, rcx
0x180028933  jz      short loc_180028955
0x180028935  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002893c  nop     dword ptr [rax+00h]
0x180028940  lea     rax, [rax+1]
0x180028944  cmp     word ptr [rcx+rax*2], 0
0x180028949  jnz     short loc_180028940
0x18002894b  lea     rdx, ds:2[rax*2]
0x180028953  jmp     short loc_180028957
0x180028955  xor     edx, edx
0x180028957  mov     [r14+8], r8
0x18002895b  mov     rax, [rdi+10h]
0x18002895f  mov     eax, [rax+10h]
0x180028962  add     eax, 20h ; ' '
0x180028965  add     eax, edx
0x180028967  jmp     short loc_18002899F
0x180028969  mov     rax, [rdi+10h]
0x18002896d  test    rax, rax
0x180028970  jz      short loc_180028995
0x180028972  mov     [r14+8], rax
0x180028976  mov     rcx, [rdi+10h]
0x18002897a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028981  lea     rax, [rax+1]
0x180028985  cmp     word ptr [rcx+rax*2], 0
0x18002898a  jnz     short loc_180028981
0x18002898c  lea     eax, ds:2[rax*2]
0x180028993  jmp     short loc_18002899F
0x180028995  mov     qword ptr [r14+8], 0
0x18002899d  xor     eax, eax
0x18002899f  mov     [r14], eax
0x1800289a2  mov     rax, [r15]
0x1800289a5  mov     rcx, r15
0x1800289a8  mov     rax, [rax+10h]
0x1800289ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289b1  cmp     eax, 2
0x1800289b4  jz      loc_180028B93
0x1800289ba  mov     rcx, [rbp+3Fh+var_98]; this
0x1800289be  call    ?IsCredmanVault@CUserVault@@QEAAEPEAU_GUID@@@Z; CUserVault::IsCredmanVault(_GUID *)
0x1800289c3  test    al, al
0x1800289c5  jnz     loc_180028B93
0x1800289cb  mov     dword ptr [rbp+3Fh+var_90], 0Ah
0x1800289d2  mov     rax, [rsp+100h+phHash]
0x1800289d7  mov     byte ptr [rax], 1
0x1800289da  lea     rbx, [rbp+3Fh+var_90]
0x1800289de  mov     [rbp+3Fh+var_78], rbx
0x1800289e2  mov     rax, [r15]
0x1800289e5  mov     rcx, r15
0x1800289e8  mov     rax, [rax+20h]
0x1800289ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f1  test    al, 4
0x1800289f3  jz      loc_180028B8A
0x1800289f9  mov     ebx, [r14]
0x1800289fc  mov     rdi, [r14+8]
0x180028a00  xor     esi, esi
0x180028a02  mov     [rsp+100h+phHash], rsi
0x180028a07  mov     [rsp+100h+dwFlags], esi; dwFlags
0x180028a0b  mov     [rsp+100h+cbSecret], esi; cbSecret
0x180028a0f  mov     [rsp+100h+pbSecret], rsi; pbSecret
0x180028a14  xor     r9d, r9d; cbHashObject
0x180028a17  xor     r8d, r8d; pbHashObject
0x180028a1a  lea     rdx, [rsp+100h+phHash]; phHash
0x180028a1f  mov     ecx, 31h ; '1'; hAlgorithm
0x180028a24  call    cs:__imp_BCryptCreateHash
0x180028a2a  test    eax, eax
0x180028a2c  jns     short loc_180028A35
0x180028a2e  mov     ecx, 7
0x180028a33  int     29h; Win8: RtlFailFast(ecx)
0x180028a35  xor     r9d, r9d; dwFlags
0x180028a38  mov     r8d, ebx; cbInput
0x180028a3b  mov     rdx, rdi; pbInput
0x180028a3e  mov     rcx, [rsp+100h+phHash]; hHash
0x180028a43  call    cs:__imp_BCryptHashData
0x180028a49  test    eax, eax
0x180028a4b  jns     short loc_180028A54
0x180028a4d  mov     ecx, 7
0x180028a52  int     29h; Win8: RtlFailFast(ecx)
0x180028a54  xor     r9d, r9d; dwFlags
0x180028a57  mov     r8d, 14h; cbOutput
0x180028a5d  lea     rdx, [rbp+3Fh+pbOutput]; pbOutput
0x180028a61  mov     rcx, [rsp+100h+phHash]; hHash
0x180028a66  call    cs:__imp_BCryptFinishHash
0x180028a6c  test    eax, eax
0x180028a6e  jns     short loc_180028A77
0x180028a70  mov     ecx, 7
0x180028a75  int     29h; Win8: RtlFailFast(ecx)
0x180028a77  mov     rcx, [rsp+100h+phHash]; hHash
0x180028a7c  call    cs:__imp_BCryptDestroyHash
0x180028a82  mov     [rsp+100h+phHash], rsi
0x180028a87  lea     rax, [rbp+3Fh+var_B8]
0x180028a8b  mov     qword ptr [rsp+100h+dwFlags], rax
0x180028a90  lea     rax, [rbp+3Fh+hMem]
0x180028a94  mov     qword ptr [rsp+100h+cbSecret], rax
0x180028a99  mov     byte ptr [rsp+100h+pbSecret], sil
0x180028a9e  mov     r9d, 14h
0x180028aa4  lea     r8, [rbp+3Fh+pbOutput]
0x180028aa8  xor     edx, edx
0x180028aaa  mov     rcx, [rbp+3Fh+var_98]
0x180028aae  call    ?EncryptData@CUserVault@@QEAAKW4eVaultEncrypt@@PEAEKEPEAPEAEPEAK@Z; CUserVault::EncryptData(eVaultEncrypt,uchar *,ulong,uchar,uchar * *,ulong *)
0x180028ab3  mov     edi, eax
0x180028ab5  test    eax, eax
0x180028ab7  jz      loc_180028B6E
0x180028abd  lea     rax, WPP_GLOBAL_Control
0x180028ac4  mov     rcx, cs:WPP_GLOBAL_Control
0x180028acb  cmp     rcx, rax
0x180028ace  jz      short loc_180028AEF
0x180028ad0  test    byte ptr [rcx+1Ch], 2
0x180028ad4  jz      short loc_180028AEF
0x180028ad6  mov     edx, 15h
0x180028adb  mov     r9d, edi
0x180028ade  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x180028ae5  mov     rcx, [rcx+10h]
0x180028ae9  call    WPP_SF_d
0x180028aee  nop
0x180028aef  mov     rbx, [rbp+3Fh+hMem]
0x180028af3  test    rbx, rbx
0x180028af6  jz      short loc_180028B67
0x180028af8  mov     eax, [rbp+3Fh+var_A0]
0x180028afb  test    eax, eax
0x180028afd  jz      short loc_180028B1D
0x180028aff  test    rbx, rbx
0x180028b02  jz      short loc_180028B1D
0x180028b04  mov     ecx, eax
0x180028b06  test    eax, eax
0x180028b08  jz      short loc_180028B1D
0x180028b0a  mov     rax, rbx
0x180028b0d  nop     dword ptr [rax]
0x180028b10  mov     byte ptr [rax], 0
0x180028b13  lea     rax, [rax+1]
0x180028b17  sub     rcx, 1
0x180028b1b  jnz     short loc_180028B10
0x180028b1d  mov     rax, [rbp+3Fh+var_B0]
0x180028b21  test    rax, rax
0x180028b24  jz      short loc_180028B30
0x180028b26  mov     rcx, rbx
0x180028b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b2e  jmp     short loc_180028B67
0x180028b30  test    rbx, rbx
0x180028b33  jz      short loc_180028B67
0x180028b35  mov     rcx, rbx; hMem
0x180028b38  call    cs:__imp_LocalSize
0x180028b3e  mov     rdx, rax
0x180028b41  test    rax, rax
0x180028b44  jz      short loc_180028B5D
0x180028b46  mov     rax, rbx
0x180028b49  nop     dword ptr [rax+00000000h]
0x180028b50  mov     byte ptr [rax], 0
0x180028b53  lea     rax, [rax+1]
0x180028b57  sub     rdx, 1
0x180028b5b  jnz     short loc_180028B50
0x180028b5d  mov     rcx, rbx; hMem
0x180028b60  call    cs:__imp_LocalFree
0x180028b66  nop
0x180028b67  mov     eax, edi
0x180028b69  jmp     loc_180028C7C
0x180028b6e  mov     eax, [rbp+3Fh+var_B8]
0x180028b71  mov     dword ptr [rbp+3Fh+var_90+8], eax
0x180028b74  mov     rsi, [rbp+3Fh+hMem]
0x180028b78  mov     [rbp+3Fh+var_80], rsi
0x180028b7c  mov     r12d, [rbp+3Fh+var_A0]
0x180028b80  mov     r13, [rbp+3Fh+var_B0]
0x180028b84  mov     rbx, [rbp+3Fh+var_78]
0x180028b88  jmp     short loc_180028B9B
0x180028b8a  mov     dword ptr [rbp+3Fh+var_90+8], 0
0x180028b91  jmp     short loc_180028B9B
0x180028b93  mov     rax, [rsp+100h+phHash]
0x180028b98  mov     byte ptr [rax], 0
0x180028b9b  mov     r8, rbx
0x180028b9e  mov     rdx, r15
0x180028ba1  mov     rcx, [rbp+3Fh+var_70]
0x180028ba5  mov     rax, [rbp+3Fh+var_68]
0x180028ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028bae  mov     ebx, eax
0x180028bb0  test    rsi, rsi
0x180028bb3  jz      short loc_180028C27
0x180028bb5  test    r12d, r12d
0x180028bb8  jz      short loc_180028BDD
0x180028bba  test    rsi, rsi
0x180028bbd  jz      short loc_180028BDD
0x180028bbf  mov     edx, r12d
0x180028bc2  test    r12d, r12d
  ... truncated ...
```
