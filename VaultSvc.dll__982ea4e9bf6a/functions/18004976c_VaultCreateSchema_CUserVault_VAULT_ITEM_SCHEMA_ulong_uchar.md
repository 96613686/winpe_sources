# VaultCreateSchema(CUserVault *,_VAULT_ITEM_SCHEMA *,ulong,uchar)

- ea: `0x18004976c`
- end: `0x180049fef`
- name: `?VaultCreateSchema@@YAKPEAVCUserVault@@PEAU_VAULT_ITEM_SCHEMA@@KE@Z`
- size: `2179`
- prototype: `unsigned int __fastcall(struct CUserVault *this, struct _VAULT_ITEM_SCHEMA *, unsigned int, unsigned __int8)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800091d0`
- `0x180014900`
- `0x18002a9e0`
- `0x180046040`

## callees

- `0x180003140`
- `0x18000aac0`
- `0x180012210`
- `0x180027340`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004976c`
- `0x18004d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VaultCreateSchema(struct CUserVault *this, struct _VAULT_ITEM_SCHEMA *a2, int a3, char a4)
{
  char v4; // r13
  unsigned int VaultStore; // ebx
  HLOCAL v8; // rcx
  __int64 v9; // rax
  _BYTE *v10; // rdx
  _BYTE *v12; // rbx
  unsigned int v13; // r14d
  __int64 v14; // rax
  _BYTE *v15; // rcx
  unsigned int v16; // r14d
  __int64 v17; // rcx
  _BYTE *v18; // rax
  _BYTE *v19; // rcx
  bool v20; // r15
  _DWORD *v21; // r8
  __int64 v22; // rcx
  _BYTE *v23; // rax
  _BYTE *v24; // rcx
  __int64 v25; // rcx
  _BYTE *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  _BYTE *v29; // rax
  _DWORD *v30; // r8
  __int64 v31; // rcx
  _BYTE *v32; // rax
  __int64 v33; // rcx
  _BYTE *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rcx
  _BYTE *v38; // rax
  _DWORD *v39; // rax
  __int64 v40; // rcx
  _BYTE *v41; // rax
  _BYTE *v42; // rcx
  __int64 v43; // rcx
  _BYTE *v44; // rax
  __int64 v45; // rcx
  _BYTE *v46; // rax
  __int64 v47; // rcx
  _BYTE *v48; // rax
  _BYTE *v49; // rcx
  struct _GUID *v50; // rdx
  __int64 v51; // rcx
  _BYTE *v52; // rax
  unsigned int v53; // r14d
  __int64 v54; // r11
  __int64 v55; // r10
  __int64 v56; // r8
  unsigned int v57; // r13d
  __int64 v58; // rcx
  _BYTE *v59; // rax
  _BYTE *v60; // rcx
  __int64 v61; // rcx
  _BYTE *v62; // rax
  __int64 v63; // rcx
  _BYTE *v64; // rax
  _BYTE *v65; // rdx
  unsigned int v66; // esi
  __int64 v67; // rcx
  __int64 v68; // [rsp+30h] [rbp-48h] BYREF
  void (*v69)(void); // [rsp+38h] [rbp-40h]
  HLOCAL hMem; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v71; // [rsp+48h] [rbp-30h]
  __int64 (__fastcall *v72)(__int64); // [rsp+50h] [rbp-28h] BYREF
  __int64 v73; // [rsp+58h] [rbp-20h] BYREF
  int v74; // [rsp+60h] [rbp-18h]

  v4 = a4;
  v72 = AutoDereference<IVaultKeyManager>;
  v73 = 0;
  v74 = 0;
  v69 = (void (*)(void))AutoDereference<IVaultKeyManager>;
  hMem = 0;
  v71 = 0;
  v68 = 0;
  if ( (a3 & 0xFFFFFFFE) != 0 || !*((_QWORD *)a2 + 4) || !*((_QWORD *)a2 + 5) || !this )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v72);
    return 87;
  }
  VaultStore = CUserVault::GetVaultStore(this, (struct IVaultStore **)&hMem, 0);
  if ( VaultStore )
  {
    v8 = hMem;
    if ( hMem )
    {
      if ( v71 )
      {
        v9 = v71;
        v10 = hMem;
        do
        {
          *v10++ = 0;
          --v9;
        }
        while ( v9 );
      }
      if ( v69 )
        v69();
      else
        VaultFreeInternal(v8);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v72);
    return VaultStore;
  }
  v12 = hMem;
  v13 = dword_18005F624;
  if ( dword_18005F624 && (*(unsigned int (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 112LL))(hMem) + 1 > v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids,
        (unsigned int)dword_18005F624);
    if ( v12 )
    {
      v14 = v71;
      if ( v71 )
      {
        v15 = v12;
        do
        {
          *v15++ = 0;
          --v14;
        }
        while ( v14 );
      }
      if ( v69 )
        ((void (__fastcall *)(_BYTE *))v69)(v12);
      else
        VaultFreeInternal(v12);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v72);
    return 1381;
  }
  (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v12 + 72LL))(v12, &v68);
  v16 = (*(__int64 (__fastcall **)(__int64, struct _VAULT_ITEM_SCHEMA *, bool, _QWORD, __int64 *))(*(_QWORD *)v68 + 8LL))(
          v68,
          a2,
          *((_QWORD *)a2 + 3) == 0,
          *((_DWORD *)a2 + 12) + (unsigned int)(*((_QWORD *)a2 + 3) != 0) + 2,
          &v73);
  if ( v16 )
  {
    if ( !v12 )
    {
LABEL_35:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v72);
      return v16;
    }
    v17 = v71;
    if ( v71 )
    {
      v18 = v12;
      do
      {
        *v18++ = 0;
        --v17;
      }
      while ( v17 );
    }
    v19 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_35;
    }
LABEL_33:
    ((void (__fastcall *)(_BYTE *, _QWORD))v69)(v19, 0);
    goto LABEL_35;
  }
  v20 = 0;
  v21 = (_DWORD *)*((_QWORD *)a2 + 3);
  if ( v21 )
  {
    if ( (v21[3] & 8) != 0 )
    {
      if ( !v12 )
        goto LABEL_171;
      if ( v71 )
      {
        v22 = v71;
        v23 = v12;
        do
        {
          *v23++ = 0;
          --v22;
        }
        while ( v22 );
      }
      v24 = v12;
      if ( !v69 )
      {
        VaultFreeInternal(v12);
        goto LABEL_171;
      }
      goto LABEL_43;
    }
    if ( *v21 > 1u )
    {
      if ( !v12 )
        goto LABEL_171;
      if ( v71 )
      {
        v25 = v71;
        v26 = v12;
        do
        {
          *v26++ = 0;
          --v25;
        }
        while ( v25 );
      }
      v24 = v12;
      if ( !v69 )
      {
        VaultFreeInternal(v12);
        goto LABEL_171;
      }
      goto LABEL_43;
    }
    v27 = (unsigned int)v21[1];
    v20 = (_DWORD)v27 == 11;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v73 + 48LL))(v73, v27, (unsigned int)v21[2]);
    if ( v16 )
    {
      if ( !v12 )
        goto LABEL_35;
      v28 = v71;
      if ( v71 )
      {
        v29 = v12;
        do
        {
          *v29++ = 0;
          --v28;
        }
        while ( v28 );
      }
      v19 = v12;
      if ( !v69 )
      {
        VaultFreeInternal(v12);
        goto LABEL_35;
      }
      goto LABEL_33;
    }
  }
  v30 = (_DWORD *)*((_QWORD *)a2 + 4);
  if ( (v30[3] & 8) != 0 )
  {
    if ( !v12 )
      goto LABEL_171;
    if ( v71 )
    {
      v31 = v71;
      v32 = v12;
      do
      {
        *v32++ = 0;
        --v31;
      }
      while ( v31 );
    }
    v24 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_171;
    }
    goto LABEL_43;
  }
  if ( (*v30 & 0xFFFFFFFD) != 0 )
  {
    if ( !v12 )
      goto LABEL_171;
    if ( v71 )
    {
      v33 = v71;
      v34 = v12;
      do
      {
        *v34++ = 0;
        --v33;
      }
      while ( v33 );
    }
    v24 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_171;
    }
LABEL_43:
    ((void (__fastcall *)(_BYTE *, _QWORD))v69)(v24, 0);
LABEL_171:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v72);
    return 87;
  }
  v35 = (unsigned int)v30[1];
  if ( (_DWORD)v35 == 11 )
    v20 = 1;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v73 + 40LL))(v73, v35, (unsigned int)v30[2]);
  if ( v16 )
  {
    if ( v12 )
    {
      v37 = v71;
      if ( v71 )
      {
        v38 = v12;
        do
        {
          *v38++ = 0;
          --v37;
        }
        while ( v37 );
      }
      if ( v69 )
        ((void (__fastcall *)(_BYTE *, __int64, _QWORD))v69)(v12, v36, 0);
      else
        VaultFreeInternal(v12);
    }
    goto LABEL_35;
  }
  v39 = (_DWORD *)*((_QWORD *)a2 + 5);
  if ( v39[3] )
  {
    if ( !v12 )
      goto LABEL_171;
    if ( v71 )
    {
      v40 = v71;
      v41 = v12;
      do
      {
        *v41++ = 0;
        --v40;
      }
      while ( v40 );
    }
    v42 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_171;
    }
    goto LABEL_116;
  }
  if ( *v39 != 3 && *v39 )
  {
    if ( !v12 )
      goto LABEL_171;
    if ( v71 )
    {
      v43 = v71;
      v44 = v12;
      do
      {
        *v44++ = 0;
        --v43;
      }
      while ( v43 );
    }
    v42 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_171;
    }
    goto LABEL_116;
  }
  v36 = (unsigned int)v39[1];
  if ( (_DWORD)v36 == 11 )
    v20 = 1;
  if ( v39[2] )
  {
    if ( !v12 )
      goto LABEL_171;
    if ( v71 )
    {
      v45 = v71;
      v46 = v12;
      do
      {
        *v46++ = 0;
        --v45;
      }
      while ( v45 );
    }
    v42 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_171;
    }
LABEL_116:
    ((void (__fastcall *)(_BYTE *, __int64, _QWORD))v69)(v42, v36, 0);
    goto LABEL_171;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v73 + 56LL))(v73, v36, 0);
  if ( v16 )
  {
    if ( !v12 )
      goto LABEL_35;
    v47 = v71;
    if ( v71 )
    {
      v48 = v12;
      do
      {
        *v48++ = 0;
        --v47;
      }
      while ( v47 );
    }
    v49 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_35;
    }
    goto LABEL_133;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 64LL))(v73, *((_QWORD *)a2 + 2));
  if ( v16 )
  {
    if ( !v12 )
      goto LABEL_35;
    v51 = v71;
    if ( v71 )
    {
      v52 = v12;
      do
      {
        *v52++ = 0;
        --v51;
      }
      while ( v51 );
    }
    v49 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_35;
    }
LABEL_133:
    ((void (__fastcall *)(_BYTE *))v69)(v49);
    goto LABEL_35;
  }
  v53 = 0;
  if ( *((_DWORD *)a2 + 12) )
  {
    while ( 1 )
    {
      v54 = 16LL * v53;
      if ( !v4 && (unsigned int)(*(_DWORD *)(v54 + *((_QWORD *)a2 + 7)) - 100) > 0x26AC )
        break;
      v55 = *((_QWORD *)a2 + 7);
      v56 = *(unsigned int *)(v54 + v55 + 4);
      if ( (_DWORD)v56 == 11 )
        v20 = 1;
      v57 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD))(*(_QWORD *)v73 + 72LL))(
              v73,
              *(unsigned int *)(v54 + v55),
              v56,
              *(unsigned int *)(v54 + v55 + 8),
              *(_DWORD *)(v54 + v55 + 12));
      if ( v57 )
      {
        if ( v12 )
        {
          if ( v71 )
          {
            v61 = v71;
            v62 = v12;
            do
            {
              *v62++ = 0;
              --v61;
            }
            while ( v61 );
          }
          if ( v69 )
            ((void (__fastcall *)(_BYTE *))v69)(v12);
          else
            VaultFreeInternal(v12);
        }
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v72);
        return v57;
      }
      if ( ++v53 >= *((_DWORD *)a2 + 12) )
        goto LABEL_159;
      v4 = a4;
    }
    if ( !v12 )
      goto LABEL_171;
    if ( v71 )
    {
      v58 = v71;
      v59 = v12;
      do
      {
        *v59++ = 0;
        --v58;
      }
      while ( v58 );
    }
    v60 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_171;
    }
LABEL_169:
    ((void (__fastcall *)(_BYTE *))v69)(v60);
    goto LABEL_171;
  }
LABEL_159:
  if ( v20 && !CUserVault::IsCredmanVault(this, v50) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids);
    if ( !v12 )
      goto LABEL_171;
    if ( v71 )
    {
      v63 = v71;
      v64 = v12;
      do
      {
        *v64++ = 0;
        --v63;
      }
      while ( v63 );
    }
    v60 = v12;
    if ( !v69 )
    {
      VaultFreeInternal(v12);
      goto LABEL_171;
    }
    goto LABEL_169;
  }
  v66 = (*(__int64 (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v12 + 96LL))(v12, v73);
  if ( v12 )
  {
    v67 = v71;
    if ( v71 )
    {
      v65 = v12;
      do
      {
        *v65++ = 0;
        --v67;
      }
      while ( v67 );
    }
    if ( v69 )
      ((void (__fastcall *)(_BYTE *, _BYTE *))v69)(v12, v65);
    else
      VaultFreeInternal(v12);
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v72);
  return v66;
}

```

## disassembly

```asm
0x18004976c  mov     [rsp-40h+arg_18], r9b
0x180049771  push    rbp
0x180049772  push    rbx
0x180049773  push    rsi
0x180049774  push    rdi
0x180049775  push    r12
0x180049777  push    r13
0x180049779  push    r14
0x18004977b  push    r15
0x18004977d  mov     rbp, rsp
0x180049780  sub     rsp, 78h
0x180049784  mov     r13b, r9b
0x180049787  mov     rsi, rdx
0x18004978a  mov     r12, rcx
0x18004978d  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180049794  mov     [rbp+var_28], rax
0x180049798  xor     r15d, r15d
0x18004979b  mov     [rbp+var_20], r15
0x18004979f  mov     [rbp+var_18], r15d
0x1800497a3  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800497aa  mov     [rbp+var_40], rax
0x1800497ae  mov     [rbp+hMem], r15
0x1800497b2  mov     [rbp+var_30], r15d
0x1800497b6  mov     [rbp+var_48], r15
0x1800497ba  test    r8d, 0FFFFFFFEh
0x1800497c1  jz      short loc_1800497D2
0x1800497c3  lea     rcx, [rbp+var_28]
0x1800497c7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800497cc  nop
0x1800497cd  jmp     loc_180049FD9
0x1800497d2  cmp     [rdx+20h], r15
0x1800497d6  jz      loc_180049FCF
0x1800497dc  cmp     [rdx+28h], r15
0x1800497e0  jz      loc_180049FCF
0x1800497e6  test    r12, r12
0x1800497e9  jnz     short loc_1800497FA
0x1800497eb  lea     rcx, [rbp+var_28]
0x1800497ef  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800497f4  nop
0x1800497f5  jmp     loc_180049FD9
0x1800497fa  xor     r8d, r8d; unsigned __int8
0x1800497fd  lea     rdx, [rbp+hMem]; struct IVaultStore **
0x180049801  call    ?GetVaultStore@CUserVault@@QEAAKPEAPEAUIVaultStore@@E@Z; CUserVault::GetVaultStore(IVaultStore * *,uchar)
0x180049806  mov     ebx, eax
0x180049808  test    eax, eax
0x18004980a  jz      short loc_180049861
0x18004980c  mov     rcx, [rbp+hMem]; hMem
0x180049810  test    rcx, rcx
0x180049813  jz      short loc_180049850
0x180049815  mov     edx, [rbp+var_30]
0x180049818  test    edx, edx
0x18004981a  jz      short loc_18004983A
0x18004981c  test    rcx, rcx
0x18004981f  jz      short loc_18004983A
0x180049821  mov     eax, edx
0x180049823  test    edx, edx
0x180049825  jz      short loc_18004983A
0x180049827  mov     rdx, rcx
0x18004982a  mov     edi, 1
0x18004982f  mov     [rdx], r15b
0x180049832  add     rdx, rdi
0x180049835  sub     rax, rdi
0x180049838  jnz     short loc_18004982F
0x18004983a  mov     rax, [rbp+var_40]
0x18004983e  test    rax, rax
0x180049841  jz      short loc_18004984A
0x180049843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049848  jmp     short loc_180049850
0x18004984a  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18004984f  nop
0x180049850  lea     rcx, [rbp+var_28]
0x180049854  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049859  nop
0x18004985a  mov     eax, ebx
0x18004985c  jmp     loc_180049FDE
0x180049861  mov     edi, 1
0x180049866  mov     rbx, [rbp+hMem]
0x18004986a  mov     r14d, cs:dword_18005F624
0x180049871  test    r14d, r14d
0x180049874  jz      loc_18004990C
0x18004987a  mov     rax, [rbx]
0x18004987d  mov     rcx, rbx
0x180049880  mov     rax, [rax+70h]
0x180049884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049889  add     eax, edi
0x18004988b  cmp     eax, r14d
0x18004988e  jbe     short loc_18004990C
0x180049890  lea     rax, WPP_GLOBAL_Control
0x180049897  mov     rcx, cs:WPP_GLOBAL_Control
0x18004989e  cmp     rcx, rax
0x1800498a1  jz      short loc_1800498C4
0x1800498a3  test    byte ptr [rcx+1Ch], 2
0x1800498a7  jz      short loc_1800498C4
0x1800498a9  lea     edx, [rdi+45h]
0x1800498ac  mov     r9d, cs:dword_18005F624
0x1800498b3  lea     r8, WPP_8d9ace457ef737f541b71792ab2942e9_Traceguids
0x1800498ba  mov     rcx, [rcx+10h]
0x1800498be  call    WPP_SF_d
0x1800498c3  nop
0x1800498c4  test    rbx, rbx
0x1800498c7  jz      short loc_1800498F8
0x1800498c9  mov     eax, [rbp+var_30]
0x1800498cc  cmp     rax, rdi
0x1800498cf  jb      short loc_1800498DF
0x1800498d1  mov     rcx, rbx
0x1800498d4  mov     [rcx], r15b
0x1800498d7  add     rcx, rdi
0x1800498da  sub     rax, rdi
0x1800498dd  jnz     short loc_1800498D4
0x1800498df  mov     rax, [rbp+var_40]
0x1800498e3  mov     rcx, rbx; hMem
0x1800498e6  test    rax, rax
0x1800498e9  jz      short loc_1800498F2
0x1800498eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498f0  jmp     short loc_1800498F8
0x1800498f2  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x1800498f7  nop
0x1800498f8  lea     rcx, [rbp+var_28]
0x1800498fc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049901  nop
0x180049902  mov     eax, 565h
0x180049907  jmp     loc_180049FDE
0x18004990c  mov     rax, [rbx]
0x18004990f  lea     rdx, [rbp+var_48]
0x180049913  mov     rcx, rbx
0x180049916  mov     rax, [rax+48h]
0x18004991a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004991f  mov     rcx, [rbp+var_48]
0x180049923  mov     r10, [rcx]
0x180049926  mov     rax, [rsi+18h]
0x18004992a  neg     rax
0x18004992d  sbb     r9d, r9d
0x180049930  neg     r9d
0x180049933  add     r9d, 2
0x180049937  add     r9d, [rsi+30h]
0x18004993b  mov     r8d, r15d
0x18004993e  cmp     [rsi+18h], r15
0x180049942  setz    r8b
0x180049946  lea     rax, [rbp+var_20]
0x18004994a  mov     [rsp+78h+var_58], rax
0x18004994f  mov     rdx, rsi
0x180049952  mov     rax, [r10+8]
0x180049956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004995b  mov     r14d, eax
0x18004995e  xor     edx, edx
0x180049960  test    eax, eax
0x180049962  jz      short loc_1800499A9
0x180049964  test    rbx, rbx
0x180049967  jz      short loc_180049997
0x180049969  mov     ecx, [rbp+var_30]
0x18004996c  cmp     rcx, rdi
0x18004996f  jb      short loc_18004997E
0x180049971  mov     rax, rbx
0x180049974  mov     [rax], dl
0x180049976  add     rax, rdi
0x180049979  sub     rcx, rdi
0x18004997c  jnz     short loc_180049974
0x18004997e  mov     rax, [rbp+var_40]
0x180049982  mov     rcx, rbx; hMem
0x180049985  test    rax, rax
0x180049988  jz      short loc_180049991
0x18004998a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004998f  jmp     short loc_180049997
0x180049991  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180049996  nop
0x180049997  lea     rcx, [rbp+var_28]
0x18004999b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800499a0  nop
0x1800499a1  mov     eax, r14d
0x1800499a4  jmp     loc_180049FDE
0x1800499a9  mov     r15b, dl
0x1800499ac  mov     r8, [rsi+18h]
0x1800499b0  test    r8, r8
0x1800499b3  jz      loc_180049AD3
0x1800499b9  mov     r9d, [r8+0Ch]
0x1800499bd  test    r9b, 8
0x1800499c1  jz      short loc_180049A0F
0x1800499c3  test    rbx, rbx
0x1800499c6  jz      short loc_180049A00
0x1800499c8  mov     eax, [rbp+var_30]
0x1800499cb  test    eax, eax
0x1800499cd  jz      short loc_1800499E7
0x1800499cf  test    rbx, rbx
0x1800499d2  jz      short loc_1800499E7
0x1800499d4  mov     ecx, eax
0x1800499d6  test    eax, eax
0x1800499d8  jz      short loc_1800499E7
0x1800499da  mov     rax, rbx
0x1800499dd  mov     [rax], dl
0x1800499df  add     rax, rdi
0x1800499e2  sub     rcx, rdi
0x1800499e5  jnz     short loc_1800499DD
0x1800499e7  mov     rax, [rbp+var_40]
0x1800499eb  mov     rcx, rbx; hMem
0x1800499ee  test    rax, rax
0x1800499f1  jz      short loc_1800499FA
0x1800499f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499f8  jmp     short loc_180049A00
0x1800499fa  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x1800499ff  nop
0x180049a00  lea     rcx, [rbp+var_28]
0x180049a04  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049a09  nop
0x180049a0a  jmp     loc_180049FD9
0x180049a0f  cmp     [r8], edi
0x180049a12  jbe     short loc_180049A60
0x180049a14  test    rbx, rbx
0x180049a17  jz      short loc_180049A51
0x180049a19  mov     eax, [rbp+var_30]
0x180049a1c  test    eax, eax
0x180049a1e  jz      short loc_180049A38
0x180049a20  test    rbx, rbx
0x180049a23  jz      short loc_180049A38
0x180049a25  mov     ecx, eax
0x180049a27  test    eax, eax
0x180049a29  jz      short loc_180049A38
0x180049a2b  mov     rax, rbx
0x180049a2e  mov     [rax], dl
0x180049a30  add     rax, rdi
0x180049a33  sub     rcx, rdi
0x180049a36  jnz     short loc_180049A2E
0x180049a38  mov     rax, [rbp+var_40]
0x180049a3c  mov     rcx, rbx; hMem
0x180049a3f  test    rax, rax
0x180049a42  jz      short loc_180049A4B
0x180049a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a49  jmp     short loc_180049A51
0x180049a4b  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180049a50  nop
0x180049a51  lea     rcx, [rbp+var_28]
0x180049a55  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049a5a  nop
0x180049a5b  jmp     loc_180049FD9
0x180049a60  mov     edx, [r8+4]
0x180049a64  cmp     edx, 0Bh
0x180049a67  setz    r15b
0x180049a6b  mov     rcx, [rbp+var_20]
0x180049a6f  mov     rax, [rcx]
0x180049a72  mov     r8d, [r8+8]
0x180049a76  mov     rax, [rax+30h]
0x180049a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a7f  mov     r14d, eax
0x180049a82  xor     edx, edx
0x180049a84  test    eax, eax
0x180049a86  jz      short loc_180049AD3
0x180049a88  test    rbx, rbx
0x180049a8b  jz      short loc_180049AC4
0x180049a8d  mov     ecx, [rbp+var_30]
0x180049a90  test    ecx, ecx
0x180049a92  jz      short loc_180049AAB
0x180049a94  test    rbx, rbx
0x180049a97  jz      short loc_180049AAB
0x180049a99  test    rcx, rcx
0x180049a9c  jz      short loc_180049AAB
0x180049a9e  mov     rax, rbx
0x180049aa1  mov     [rax], dl
0x180049aa3  add     rax, rdi
0x180049aa6  sub     rcx, rdi
0x180049aa9  jnz     short loc_180049AA1
0x180049aab  mov     rax, [rbp+var_40]
0x180049aaf  mov     rcx, rbx; hMem
0x180049ab2  test    rax, rax
0x180049ab5  jz      short loc_180049ABE
0x180049ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049abc  jmp     short loc_180049AC4
0x180049abe  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180049ac3  nop
0x180049ac4  lea     rcx, [rbp+var_28]
0x180049ac8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180049acd  nop
0x180049ace  jmp     loc_1800499A1
0x180049ad3  mov     r8, [rsi+20h]
0x180049ad7  mov     r9d, [r8+0Ch]
0x180049adb  test    r9b, 8
0x180049adf  jz      short loc_180049B2D
0x180049ae1  test    rbx, rbx
0x180049ae4  jz      short loc_180049B1E
0x180049ae6  mov     eax, [rbp+var_30]
0x180049ae9  test    eax, eax
0x180049aeb  jz      short loc_180049B05
0x180049aed  test    rbx, rbx
0x180049af0  jz      short loc_180049B05
0x180049af2  mov     ecx, eax
0x180049af4  test    eax, eax
0x180049af6  jz      short loc_180049B05
0x180049af8  mov     rax, rbx
0x180049afb  mov     [rax], dl
0x180049afd  add     rax, rdi
0x180049b00  sub     rcx, rdi
0x180049b03  jnz     short loc_180049AFB
0x180049b05  mov     rax, [rbp+var_40]
0x180049b09  mov     rcx, rbx; hMem
0x180049b0c  test    rax, rax
0x180049b0f  jz      short loc_180049B18
0x180049b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b16  jmp     short loc_180049B1E
0x180049b18  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180049b1d  nop
0x180049b1e  lea     rcx, [rbp+var_28]
0x180049b22  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
  ... truncated ...
```
