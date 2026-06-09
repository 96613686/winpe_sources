# ConvertAccessControlListToAcl(IADsAccessControlList *,_ACL * *,ushort const *)

- ea: `0x180011630`
- end: `0x1800118bb`
- name: `?ConvertAccessControlListToAcl@@YAJPEAUIADsAccessControlList@@PEAPEAU_ACL@@PEBG@Z`
- size: `651`
- prototype: `int(struct IADsAccessControlList *, struct _ACL **, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180011ca8`
- `0x180011f2c`

## callees

- `0x1800112e4`
- `0x180011630`
- `0x18001e010`

## import_xrefs

- `ADVAPI32!AddAce` at `0x180011827`
- `ADVAPI32!AddAce` at `0x180011827`
- `ADVAPI32!InitializeAcl` at `0x1800117e2`
- `ADVAPI32!InitializeAcl` at `0x1800117e2`
- `KERNEL32!GetLastError` at `0x1800117ec`
- `KERNEL32!GetLastError` at `0x180011831`
- `KERNEL32!GetLastError` at `0x1800117ec`
- `KERNEL32!GetLastError` at `0x180011831`
- `OLEAUT32!__imp_VariantInit` at `0x18001170b`
- `OLEAUT32!__imp_VariantInit` at `0x18001170b`
- `OLEAUT32!__imp_VariantClear` at `0x180011766`
- `OLEAUT32!__imp_VariantClear` at `0x180011766`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800116e2`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800117c2`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800116e2`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800117c2`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011861`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011870`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011861`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011870`

## pseudocode

```c
__int64 __fastcall ConvertAccessControlListToAcl(
        struct IADsAccessControlList *a1,
        struct _ACL **a2,
        const unsigned __int16 *a3)
{
  struct IADsAccessControlListVtbl *lpVtbl; // rax
  signed int v7; // ebx
  _QWORD *v8; // r14
  __int64 v9; // rdi
  unsigned int i; // ebx
  int v11; // esi
  int v12; // r8d
  __int64 j; // rdx
  __int64 v14; // rcx
  DWORD v15; // ebx
  ACL *v16; // rax
  struct _ACL *v17; // r15
  signed int LastError; // eax
  __int64 k; // rsi
  signed int v20; // eax
  __int64 m; // rsi
  void *v22; // rcx
  struct IADsAccessControlEntry *v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  __int64 v26; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 *v27; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v29; // [rsp+A0h] [rbp+30h] BYREF
  int v30; // [rsp+B8h] [rbp+48h] BYREF

  v25 = 0;
  v29 = 0;
  v24 = 0;
  v27 = 0;
  lpVtbl = a1->lpVtbl;
  v26 = 0;
  v30 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v7 = ((__int64 (__fastcall *)(struct IADsAccessControlList *, unsigned int *))lpVtbl->get_AceCount)(a1, &v29);
  if ( v7 < 0 )
    goto LABEL_37;
  v7 = ((__int64 (__fastcall *)(struct IADsAccessControlList *, __int64 *))a1->lpVtbl->get__NewEnum)(a1, &v25);
  if ( v7 < 0 )
    goto LABEL_37;
  v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(v25, &IID_IEnumVARIANT, &v26);
  if ( v7 < 0 )
    goto LABEL_37;
  v8 = AllocADsMem(8 * v29);
  if ( !v8 )
  {
    v7 = -2147024882;
    goto LABEL_37;
  }
  v9 = 0;
  for ( i = 0; i < v29; ++i )
  {
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(__int64, __int64, VARIANTARG *, int *))(*(_QWORD *)v26 + 24LL))(v26, 1, &pvarg, &v30) >= 0
      && (**(int (__fastcall ***)(LONGLONG, GUID *, struct IADsAccessControlEntry **))pvarg.llVal)(
           pvarg.llVal,
           &IID_IADsAccessControlEntry,
           &v24) >= 0 )
    {
      v11 = ConvertAccessControlEntryToAce(v24, &v27, a3);
      VariantClear(&pvarg);
      if ( v24 )
      {
        ((void (__fastcall *)(struct IADsAccessControlEntry *))v24->lpVtbl->Release)(v24);
        v24 = 0;
      }
      if ( v11 >= 0 )
      {
        v8[v9] = v27;
        v9 = (unsigned int)(v9 + 1);
      }
    }
  }
  v12 = 0;
  for ( j = 0; (unsigned int)j < (unsigned int)v9; v12 += *(unsigned __int16 *)(v14 + 2) )
  {
    v14 = v8[j];
    j = (unsigned int)(j + 1);
  }
  v15 = v12 + 8;
  v16 = (ACL *)AllocADsMem(v12 + 8);
  v17 = v16;
  if ( v16 )
  {
    if ( InitializeAcl(v16, v15, 2u) )
    {
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 < 0 )
        goto LABEL_32;
    }
    for ( k = 0; (unsigned int)k < (unsigned int)v9; k = (unsigned int)(k + 1) )
    {
      if ( !AddAce(v17, 2u, k, (LPVOID)v8[k], *(unsigned __int16 *)(v8[k] + 2LL)) )
      {
        v20 = GetLastError();
        v7 = v20;
        if ( v20 > 0 )
          v7 = (unsigned __int16)v20 | 0x80070000;
        if ( v7 < 0 )
          goto LABEL_32;
      }
    }
    *a2 = v17;
    goto LABEL_32;
  }
  v7 = -2147024882;
LABEL_32:
  for ( m = 0; (unsigned int)m < (unsigned int)v9; m = (unsigned int)(m + 1) )
  {
    v22 = (void *)v8[m];
    if ( v22 )
      FreeADsMem(v22);
  }
  FreeADsMem(v8);
LABEL_37:
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180011630  mov     [rsp-28h+arg_8], rbx
0x180011635  mov     [rsp-28h+arg_10], rsi
0x18001163a  push    rbp
0x18001163b  push    rdi
0x18001163c  push    r12
0x18001163e  push    r14
0x180011640  push    r15
0x180011642  mov     rbp, rsp
0x180011645  sub     rsp, 70h
0x180011649  xor     eax, eax
0x18001164b  mov     [rbp+var_38], 0
0x180011653  mov     qword ptr [rbp+pvarg+10h], rax
0x180011657  mov     r12, rdx
0x18001165a  mov     [rbp+arg_0], eax
0x18001165d  lea     rdx, [rbp+arg_0]
0x180011661  mov     [rbp+var_40], rax
0x180011665  xorps   xmm0, xmm0
0x180011668  mov     [rbp+var_28], rax
0x18001166c  mov     r15, r8
0x18001166f  mov     rax, [rcx]
0x180011672  mov     rdi, rcx
0x180011675  mov     [rbp+var_30], 0
0x18001167d  mov     [rbp+arg_18], 0
0x180011684  movups  xmmword ptr [rbp+pvarg], xmm0
0x180011688  mov     rax, [rax+48h]
0x18001168c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011691  mov     ebx, eax
0x180011693  test    eax, eax
0x180011695  js      loc_180011876
0x18001169b  mov     rax, [rdi]
0x18001169e  lea     rdx, [rbp+var_38]
0x1800116a2  mov     rcx, rdi
0x1800116a5  mov     rax, [rax+70h]
0x1800116a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116ae  mov     ebx, eax
0x1800116b0  test    eax, eax
0x1800116b2  js      loc_180011876
0x1800116b8  mov     rcx, [rbp+var_38]
0x1800116bc  lea     r8, [rbp+var_30]
0x1800116c0  lea     rdx, IID_IEnumVARIANT
0x1800116c7  mov     rax, [rcx]
0x1800116ca  mov     rax, [rax]
0x1800116cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116d2  mov     ebx, eax
0x1800116d4  test    eax, eax
0x1800116d6  js      loc_180011876
0x1800116dc  mov     ecx, [rbp+arg_0]
0x1800116df  shl     ecx, 3; cb
0x1800116e2  call    cs:__imp_AllocADsMem
0x1800116e8  mov     r14, rax
0x1800116eb  test    rax, rax
0x1800116ee  jnz     short loc_1800116FA
0x1800116f0  mov     ebx, 8007000Eh
0x1800116f5  jmp     loc_180011876
0x1800116fa  xor     edi, edi
0x1800116fc  xor     ebx, ebx
0x1800116fe  cmp     [rbp+arg_0], ebx
0x180011701  jbe     loc_1800117A2
0x180011707  lea     rcx, [rbp+pvarg]; pvarg
0x18001170b  call    cs:__imp_VariantInit
0x180011711  mov     rcx, [rbp+var_30]
0x180011715  lea     r9, [rbp+arg_18]
0x180011719  lea     r8, [rbp+pvarg]
0x18001171d  mov     edx, 1
0x180011722  mov     rax, [rcx]
0x180011725  mov     rax, [rax+18h]
0x180011729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001172e  test    eax, eax
0x180011730  js      short loc_180011797
0x180011732  mov     rcx, qword ptr [rbp+pvarg+8]
0x180011736  lea     r8, [rbp+var_40]
0x18001173a  lea     rdx, IID_IADsAccessControlEntry
0x180011741  mov     rax, [rcx]
0x180011744  mov     rax, [rax]
0x180011747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001174c  test    eax, eax
0x18001174e  js      short loc_180011797
0x180011750  mov     rcx, [rbp+var_40]; struct IADsAccessControlEntry *
0x180011754  lea     rdx, [rbp+var_28]; unsigned __int8 **
0x180011758  mov     r8, r15; unsigned __int16 *
0x18001175b  call    ?ConvertAccessControlEntryToAce@@YAJPEAUIADsAccessControlEntry@@PEAPEAEPEBG@Z; ConvertAccessControlEntryToAce(IADsAccessControlEntry *,uchar * *,ushort const *)
0x180011760  lea     rcx, [rbp+pvarg]; pvarg
0x180011764  mov     esi, eax
0x180011766  call    cs:__imp_VariantClear
0x18001176c  mov     rcx, [rbp+var_40]
0x180011770  test    rcx, rcx
0x180011773  jz      short loc_180011789
0x180011775  mov     rdx, [rcx]
0x180011778  mov     rax, [rdx+10h]
0x18001177c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011781  mov     [rbp+var_40], 0
0x180011789  test    esi, esi
0x18001178b  js      short loc_180011797
0x18001178d  mov     rax, [rbp+var_28]
0x180011791  mov     [r14+rdi*8], rax
0x180011795  inc     edi
0x180011797  inc     ebx
0x180011799  cmp     ebx, [rbp+arg_0]
0x18001179c  jb      loc_180011707
0x1800117a2  xor     r8d, r8d
0x1800117a5  xor     edx, edx
0x1800117a7  test    edi, edi
0x1800117a9  jz      short loc_1800117BC
0x1800117ab  mov     rcx, [r14+rdx*8]
0x1800117af  inc     edx
0x1800117b1  movzx   eax, word ptr [rcx+2]
0x1800117b5  add     r8d, eax
0x1800117b8  cmp     edx, edi
0x1800117ba  jb      short loc_1800117AB
0x1800117bc  lea     ebx, [r8+8]
0x1800117c0  mov     ecx, ebx; cb
0x1800117c2  call    cs:__imp_AllocADsMem
0x1800117c8  mov     r15, rax
0x1800117cb  test    rax, rax
0x1800117ce  jnz     short loc_1800117D7
0x1800117d0  mov     ebx, 8007000Eh
0x1800117d5  jmp     short loc_180011852
0x1800117d7  mov     r8d, 2; dwAclRevision
0x1800117dd  mov     edx, ebx; nAclLength
0x1800117df  mov     rcx, r15; pAcl
0x1800117e2  call    cs:__imp_InitializeAcl
0x1800117e8  test    eax, eax
0x1800117ea  jnz     short loc_180011807
0x1800117ec  call    cs:__imp_GetLastError
0x1800117f2  mov     ebx, eax
0x1800117f4  test    eax, eax
0x1800117f6  jle     short loc_180011801
0x1800117f8  movzx   ebx, ax
0x1800117fb  or      ebx, 80070000h
0x180011801  test    ebx, ebx
0x180011803  js      short loc_180011852
0x180011805  jmp     short loc_180011809
0x180011807  xor     ebx, ebx
0x180011809  xor     esi, esi
0x18001180b  cmp     esi, edi
0x18001180d  jnb     short loc_18001184E
0x18001180f  mov     r9, [r14+rsi*8]; pAceList
0x180011813  mov     r8d, esi; dwStartingAceIndex
0x180011816  mov     edx, 2; dwAceRevision
0x18001181b  mov     rcx, r15; pAcl
0x18001181e  movzx   eax, word ptr [r9+2]
0x180011823  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x180011827  call    cs:__imp_AddAce
0x18001182d  test    eax, eax
0x18001182f  jnz     short loc_18001184A
0x180011831  call    cs:__imp_GetLastError
0x180011837  mov     ebx, eax
0x180011839  test    eax, eax
0x18001183b  jle     short loc_180011846
0x18001183d  movzx   ebx, ax
0x180011840  or      ebx, 80070000h
0x180011846  test    ebx, ebx
0x180011848  js      short loc_180011852
0x18001184a  inc     esi
0x18001184c  jmp     short loc_18001180B
0x18001184e  mov     [r12], r15
0x180011852  xor     esi, esi
0x180011854  test    edi, edi
0x180011856  jz      short loc_18001186D
0x180011858  mov     rcx, [r14+rsi*8]; pMem
0x18001185c  test    rcx, rcx
0x18001185f  jz      short loc_180011867
0x180011861  call    cs:__imp_FreeADsMem
0x180011867  inc     esi
0x180011869  cmp     esi, edi
0x18001186b  jb      short loc_180011858
0x18001186d  mov     rcx, r14; pMem
0x180011870  call    cs:__imp_FreeADsMem
0x180011876  mov     rcx, [rbp+var_38]
0x18001187a  test    rcx, rcx
0x18001187d  jz      short loc_18001188B
0x18001187f  mov     rax, [rcx]
0x180011882  mov     rax, [rax+10h]
0x180011886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001188b  mov     rcx, [rbp+var_30]
0x18001188f  test    rcx, rcx
0x180011892  jz      short loc_1800118A0
0x180011894  mov     rax, [rcx]
0x180011897  mov     rax, [rax+10h]
0x18001189b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118a0  lea     r11, [rsp+70h+var_s0]
0x1800118a5  mov     eax, ebx
0x1800118a7  mov     rbx, [r11+38h]
0x1800118ab  mov     rsi, [r11+40h]
0x1800118af  mov     rsp, r11
0x1800118b2  pop     r15
0x1800118b4  pop     r14
0x1800118b6  pop     r12
0x1800118b8  pop     rdi
0x1800118b9  pop     rbp
0x1800118ba  retn
```
