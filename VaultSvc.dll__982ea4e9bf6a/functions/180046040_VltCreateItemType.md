# VltCreateItemType

- ea: `0x180046040`
- end: `0x180046913`
- name: `VltCreateItemType`
- size: `2259`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation`

## callees

- `0x180003140`
- `0x180006610`
- `0x180012210`
- `0x180013390`
- `0x180015568`
- `0x18001eda0`
- `0x180020a24`
- `0x180021b70`
- `0x180027340`
- `0x180028ce0`
- `0x18002cc10`
- `0x18002e9c0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x180046040`
- `0x180048b80`
- `0x18004976c`
- `0x18004d010`

## string_xrefs

- `0x1800460bb`: `VltCreateItemType`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VltCreateItemType(
        __int64 a1,
        const struct _GUID *a2,
        struct _VAULT_ITEM_SCHEMA *a3,
        unsigned int a4)
{
  unsigned int v4; // r12d
  __int64 v7; // rdx
  int v8; // r8d
  unsigned int Schema; // ebx
  PVOID *v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned int v12; // r15d
  struct CUserVault *v13; // r14
  unsigned int VaultStore; // eax
  __int64 v15; // rdx
  int v16; // r8d
  HLOCAL v17; // rcx
  _BYTE *v18; // rax
  _BYTE *v19; // rbx
  unsigned int v20; // eax
  CVaultMgr *v21; // rcx
  unsigned int v22; // r12d
  __int64 v23; // rdx
  int v24; // r8d
  __int64 v25; // rax
  _BYTE *v26; // rcx
  __int64 v28; // rdx
  int v29; // r8d
  __int64 v30; // rax
  _BYTE *v31; // rcx
  __int64 v32; // rcx
  unsigned int UserVaultManager; // eax
  __int64 v34; // rcx
  _BYTE *v35; // rax
  unsigned int Vault; // eax
  unsigned int v37; // r14d
  __int64 v38; // rdx
  int v39; // r8d
  __int64 v40; // rcx
  _BYTE *v41; // rax
  __int64 v42; // rax
  _BYTE *v43; // rcx
  unsigned int v44; // eax
  __int64 v45; // rax
  __int64 v46; // rdx
  int v47; // r8d
  __int64 v48; // rax
  unsigned int v49; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v50; // [rsp+4Ch] [rbp-BCh] BYREF
  HANDLE v51[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 (__fastcall *v52)(__int64); // [rsp+60h] [rbp-A8h] BYREF
  struct CUserVault *v53; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+70h] [rbp-98h]
  __int64 (__fastcall *v55)(__int64); // [rsp+78h] [rbp-90h]
  HLOCAL hMem; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v57; // [rsp+88h] [rbp-80h]
  __int64 (__fastcall *v58)(__int64); // [rsp+90h] [rbp-78h] BYREF
  CUserVaultMgr *v59; // [rsp+98h] [rbp-70h] BYREF
  int v60; // [rsp+A0h] [rbp-68h]
  __int64 (__fastcall *v61)(__int64); // [rsp+A8h] [rbp-60h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-58h] BYREF
  int v63; // [rsp+B8h] [rbp-50h]
  _BYTE v64[80]; // [rsp+C8h] [rbp-40h] BYREF

  v4 = a4;
  v50 = a4;
  v49 = 0;
  v52 = AutoDereference<IVaultKeyManager>;
  v53 = 0;
  LODWORD(v54) = 0;
  v58 = AutoDereference<IVaultKeyManager>;
  v59 = 0;
  v60 = 0;
  LOBYTE(v51[0]) = 0;
  v51[1] = 0;
  FnTracer::FnTracer((FnTracer *)v64, "VltCreateItemType", &v49);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
LABEL_5:
    Schema = 87;
    v49 = 87;
    FnTracer::~FnTracer((FnTracer *)v64, v7, v8);
    CVaultRpcImpersonate::~CVaultRpcImpersonate(v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v58);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v52);
    return Schema;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF__guid__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v8, (_DWORD)a3, (__int64)a2);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
      WPP_SF_(v10[2], 33, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
  }
  DumpSchema(a3);
  v11 = *(_QWORD *)&a2->Data1;
  if ( !*(_QWORD *)&a2->Data1 )
    v11 = *(_QWORD *)a2->Data4 - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  v12 = 1168;
  if ( !v11 )
  {
    if ( (v4 & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
      goto LABEL_5;
    }
    goto LABEL_21;
  }
  if ( (v4 & 1) != 0 )
  {
LABEL_21:
    if ( Vault_CredmanVault_ID == *(_OWORD *)a2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
      Schema = 50;
      v49 = 50;
      FnTracer::~FnTracer((FnTracer *)v64, v7, v8);
      CVaultRpcImpersonate::~CVaultRpcImpersonate(v51);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v58);
      CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v52);
      return Schema;
    }
    v13 = (struct CUserVault *)VaultGlobals::g_GlobalSchemaMgr;
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v52);
    v53 = v13;
    (**(void (__fastcall ***)(struct CUserVault *))v13)(v13);
    goto LABEL_94;
  }
  v55 = AutoDereference<IVaultKeyManager>;
  hMem = 0;
  v57 = 0;
  v61 = AutoDereference<IVaultKeyManager>;
  v62 = 0;
  v63 = 0;
  VaultStore = CUserVault::GetVaultStore(VaultGlobals::g_GlobalSchemaMgr, (struct IVaultStore **)&hMem, 0);
  Schema = VaultStore;
  v49 = VaultStore;
  if ( VaultStore )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, VaultStore);
      Schema = v49;
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v61);
    v17 = hMem;
    if ( hMem )
    {
      if ( v57 )
      {
        v15 = v57;
        v18 = hMem;
        do
        {
          *v18++ = 0;
          --v15;
        }
        while ( v15 );
      }
      if ( v55 )
        ((void (__fastcall *)(HLOCAL, __int64))v55)(v17, v15);
      else
        VaultFreeInternal(v17);
    }
    goto LABEL_113;
  }
  v19 = hMem;
  v20 = (*(__int64 (__fastcall **)(HLOCAL, struct _VAULT_ITEM_SCHEMA *, __int64 *))(*(_QWORD *)hMem + 80LL))(
          hMem,
          a3,
          &v62);
  v22 = v20;
  v49 = v20;
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
    v49 = 183;
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v61);
    if ( v19 )
    {
      v25 = v57;
      if ( v57 )
      {
        v26 = v19;
        do
        {
          *v26++ = 0;
          --v25;
        }
        while ( v25 );
      }
      if ( v55 )
        v55((__int64)v19);
      else
        VaultFreeInternal(v19);
    }
    FnTracer::~FnTracer((FnTracer *)v64, v23, v24);
    CVaultRpcImpersonate::~CVaultRpcImpersonate(v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v58);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v52);
    return 183;
  }
  if ( v20 != 1168 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, v20);
      v22 = v49;
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v61);
    if ( !v19 )
      goto LABEL_62;
    v30 = v57;
    if ( v57 )
    {
      v31 = v19;
      do
      {
        *v31++ = 0;
        --v30;
      }
      while ( v30 );
    }
    v32 = (__int64)v19;
    if ( !v55 )
    {
      VaultFreeInternal(v19);
      goto LABEL_62;
    }
LABEL_60:
    v55(v32);
LABEL_62:
    FnTracer::~FnTracer((FnTracer *)v64, v28, v29);
    CVaultRpcImpersonate::~CVaultRpcImpersonate(v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v58);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v52);
    return v22;
  }
  UserVaultManager = CVaultMgr::GetUserVaultManager(v21, 1u, &v59, 0, 0);
  v22 = UserVaultManager;
  v49 = UserVaultManager;
  if ( UserVaultManager )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids,
        UserVaultManager);
      v22 = v49;
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v61);
    if ( !v19 )
      goto LABEL_62;
    if ( v57 )
    {
      v34 = v57;
      v35 = v19;
      do
      {
        *v35++ = 0;
        --v34;
      }
      while ( v34 );
    }
    v32 = (__int64)v19;
    if ( !v55 )
    {
      VaultFreeInternal(v19);
      goto LABEL_62;
    }
    goto LABEL_60;
  }
  Vault = CUserVaultMgr::GetVault(v59, a2, &v53);
  v37 = Vault;
  v49 = Vault;
  if ( Vault )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, Vault);
      v37 = v49;
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v61);
    if ( v19 )
    {
      if ( v57 )
      {
        v40 = v57;
        v41 = v19;
        do
        {
          *v41++ = 0;
          --v40;
        }
        while ( v40 );
      }
      if ( v55 )
        v55((__int64)v19);
      else
        VaultFreeInternal(v19);
    }
    FnTracer::~FnTracer((FnTracer *)v64, v38, v39);
    CVaultRpcImpersonate::~CVaultRpcImpersonate(v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v58);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v52);
    return v37;
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v61);
  if ( v19 )
  {
    v42 = v57;
    if ( v57 )
    {
      v43 = v19;
      do
      {
        *v43++ = 0;
        --v42;
      }
      while ( v42 );
    }
    if ( v55 )
      v55((__int64)v19);
    else
      VaultFreeInternal(v19);
  }
  v13 = v53;
  v4 = v50;
LABEL_94:
  v44 = CVaultRpcImpersonate::Impersonate((CVaultRpcImpersonate *)v51, 1);
  Schema = v44;
  v49 = v44;
  if ( v44 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, v44);
      Schema = v49;
    }
LABEL_113:
    FnTracer::~FnTracer((FnTracer *)v64, v15, v16);
    CVaultRpcImpersonate::~CVaultRpcImpersonate(v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v58);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v52);
    return Schema;
  }
  v50 = 0;
  v45 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v13 + 1) + 216LL))(*((_QWORD *)v13 + 1));
  if ( VaultAccessCheck(0, v45, &v50) )
  {
    v48 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v13 + 1) + 216LL))(*((_QWORD *)v13 + 1));
    if ( VaultAccessCheck(3, v48, &v50) )
    {
      Schema = VaultCreateSchema(v13, a3, v4, 0);
      v49 = Schema;
      if ( Schema && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
        Schema = v49;
      }
    }
    else
    {
      Schema = 5;
      v49 = 5;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, 5);
        Schema = v49;
      }
    }
    goto LABEL_113;
  }
  v49 = 1168;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, 1168);
    v12 = v49;
  }
  FnTracer::~FnTracer((FnTracer *)v64, v46, v47);
  CVaultRpcImpersonate::~CVaultRpcImpersonate(v51);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v58);
  CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v52);
  return v12;
}

```

## disassembly

```asm
0x180046040  mov     rax, rsp
0x180046043  mov     [rax+8], rbx
0x180046047  push    rbp
0x180046048  push    rsi
0x180046049  push    rdi
0x18004604a  push    r12
0x18004604c  push    r13
0x18004604e  push    r14
0x180046050  push    r15
0x180046052  lea     rbp, [rax-68h]
0x180046056  sub     rsp, 130h
0x18004605d  movaps  xmmword ptr [rax-48h], xmm6
0x180046061  mov     rax, cs:__security_cookie
0x180046068  xor     rax, rsp
0x18004606b  mov     [rbp+60h+var_50], rax
0x18004606f  mov     r12d, r9d
0x180046072  mov     [rsp+160h+var_11C], r9d
0x180046077  mov     r13, r8
0x18004607a  mov     r14, rdx
0x18004607d  xor     ebx, ebx
0x18004607f  mov     [rsp+160h+var_120], ebx
0x180046083  xorps   xmm6, xmm6
0x180046086  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18004608d  mov     [rsp+160h+var_108], rax
0x180046092  mov     [rsp+160h+var_100], rbx
0x180046097  mov     dword ptr [rsp+160h+var_F8], ebx
0x18004609b  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800460a2  mov     [rbp+60h+var_D8], rax
0x1800460a6  mov     [rbp+60h+var_D0], rbx
0x1800460aa  mov     [rbp+60h+var_C8], ebx
0x1800460ad  mov     byte ptr [rsp+160h+var_118], bl
0x1800460b1  mov     [rsp+160h+var_110], rbx
0x1800460b6  lea     r8, [rsp+160h+var_120]; unsigned int *
0x1800460bb  lea     rdx, aVltcreateitemt; "VltCreateItemType"
0x1800460c2  lea     rcx, [rbp+60h+var_A0]; this
0x1800460c6  call    ??0FnTracer@@QEAA@PEADPEAK@Z; FnTracer::FnTracer(char *,ulong *)
0x1800460cb  test    r14, r14
0x1800460ce  jnz     short loc_180046133
0x1800460d0  lea     rdi, WPP_GLOBAL_Control
0x1800460d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800460de  cmp     rcx, rdi
0x1800460e1  jz      short loc_1800460FC
0x1800460e3  test    byte ptr [rcx+1Ch], 2
0x1800460e7  jz      short loc_1800460FC
0x1800460e9  lea     edx, [rbx+1Fh]
0x1800460ec  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x1800460f3  mov     rcx, [rcx+10h]
0x1800460f7  call    WPP_SF_
0x1800460fc  mov     ebx, 57h ; 'W'
0x180046101  mov     [rsp+160h+var_120], ebx
0x180046105  lea     rcx, [rbp+60h+var_A0]; this
0x180046109  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x18004610e  lea     rcx, [rsp+160h+var_118]; this
0x180046113  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046118  nop
0x180046119  lea     rcx, [rbp+60h+var_D8]
0x18004611d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046122  nop
0x180046123  lea     rcx, [rsp+160h+var_108]
0x180046128  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18004612d  nop
0x18004612e  jmp     loc_1800468E5
0x180046133  lea     rdi, WPP_GLOBAL_Control
0x18004613a  lea     rsi, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180046141  mov     rcx, cs:WPP_GLOBAL_Control
0x180046148  cmp     rcx, rdi
0x18004614b  jz      short loc_180046191
0x18004614d  test    byte ptr [rcx+1Ch], 8
0x180046151  jz      short loc_180046175
0x180046153  mov     edx, 20h ; ' '
0x180046158  mov     dword ptr [rsp+160h+var_138], r12d; unsigned int *
0x18004615d  mov     [rsp+160h+var_140], r14
0x180046162  mov     r9, r13
0x180046165  mov     rcx, [rcx+10h]
0x180046169  call    WPP_SF__guid__guid_D
0x18004616e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046175  cmp     rcx, rdi
0x180046178  jz      short loc_180046191
0x18004617a  test    byte ptr [rcx+1Ch], 8
0x18004617e  jz      short loc_180046191
0x180046180  mov     edx, 21h ; '!'
0x180046185  mov     r8, rsi
0x180046188  mov     rcx, [rcx+10h]
0x18004618c  call    WPP_SF_
0x180046191  mov     rcx, r13; struct _VAULT_ITEM_SCHEMA *
0x180046194  call    ?DumpSchema@@YAXPEAU_VAULT_ITEM_SCHEMA@@@Z; DumpSchema(_VAULT_ITEM_SCHEMA *)
0x180046199  mov     rcx, [r14]
0x18004619c  movq    rax, xmm6
0x1800461a1  sub     rcx, rax
0x1800461a4  jnz     short loc_1800461B7
0x1800461a6  mov     rcx, [r14+8]
0x1800461aa  psrldq  xmm6, 8
0x1800461af  movq    rax, xmm6
0x1800461b4  sub     rcx, rax
0x1800461b7  mov     eax, r12d
0x1800461ba  and     eax, 1
0x1800461bd  mov     r15d, 490h
0x1800461c3  test    rcx, rcx
0x1800461c6  jnz     short loc_180046224
0x1800461c8  test    eax, eax
0x1800461ca  jnz     short loc_18004622C
0x1800461cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800461d3  cmp     rcx, rdi
0x1800461d6  jz      short loc_1800461ED
0x1800461d8  test    byte ptr [rcx+1Ch], 2
0x1800461dc  jz      short loc_1800461ED
0x1800461de  lea     edx, [rax+22h]
0x1800461e1  mov     r8, rsi
0x1800461e4  mov     rcx, [rcx+10h]
0x1800461e8  call    WPP_SF_
0x1800461ed  mov     ebx, 57h ; 'W'
0x1800461f2  mov     [rsp+160h+var_120], ebx
0x1800461f6  lea     rcx, [rbp+60h+var_A0]; this
0x1800461fa  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x1800461ff  lea     rcx, [rsp+160h+var_118]; this
0x180046204  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046209  nop
0x18004620a  lea     rcx, [rbp+60h+var_D8]
0x18004620e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046213  nop
0x180046214  lea     rcx, [rsp+160h+var_108]
0x180046219  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18004621e  nop
0x18004621f  jmp     loc_1800468E5
0x180046224  test    eax, eax
0x180046226  jz      loc_1800462C8
0x18004622c  mov     rax, qword ptr cs:Vault_CredmanVault_ID
0x180046233  cmp     rax, [r14]
0x180046236  jnz     short loc_18004629F
0x180046238  mov     rax, qword ptr cs:Vault_CredmanVault_ID+8
0x18004623f  cmp     rax, [r14+8]
0x180046243  jnz     short loc_18004629F
0x180046245  mov     rcx, cs:WPP_GLOBAL_Control
0x18004624c  cmp     rcx, rdi
0x18004624f  jz      short loc_180046268
0x180046251  test    byte ptr [rcx+1Ch], 2
0x180046255  jz      short loc_180046268
0x180046257  mov     edx, 23h ; '#'
0x18004625c  mov     r8, rsi
0x18004625f  mov     rcx, [rcx+10h]
0x180046263  call    WPP_SF_
0x180046268  mov     ebx, 32h ; '2'
0x18004626d  mov     [rsp+160h+var_120], ebx
0x180046271  lea     rcx, [rbp+60h+var_A0]; this
0x180046275  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x18004627a  lea     rcx, [rsp+160h+var_118]; this
0x18004627f  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046284  nop
0x180046285  lea     rcx, [rbp+60h+var_D8]
0x180046289  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18004628e  nop
0x18004628f  lea     rcx, [rsp+160h+var_108]
0x180046294  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046299  nop
0x18004629a  jmp     loc_1800468E5
0x18004629f  mov     r14, cs:?g_GlobalSchemaMgr@VaultGlobals@@3VCVaultGlobalSchemaMgr@@A; CVaultGlobalSchemaMgr VaultGlobals::g_GlobalSchemaMgr
0x1800462a6  lea     rcx, [rsp+160h+var_108]
0x1800462ab  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x1800462b0  mov     [rsp+160h+var_100], r14
0x1800462b5  mov     rax, [r14]
0x1800462b8  mov     rcx, r14
0x1800462bb  mov     rax, [rax]
0x1800462be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800462c3  jmp     loc_1800466F9
0x1800462c8  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800462cf  mov     [rsp+160h+var_F0], rax
0x1800462d4  mov     [rsp+160h+hMem], rbx
0x1800462d9  mov     [rbp+60h+var_E0], ebx
0x1800462dc  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800462e3  mov     [rbp+60h+var_C0], rax
0x1800462e7  mov     [rbp+60h+var_B8], rbx
0x1800462eb  mov     [rbp+60h+var_B0], ebx
0x1800462ee  xor     r8d, r8d; unsigned __int8
0x1800462f1  lea     rdx, [rsp+160h+hMem]; struct IVaultStore **
0x1800462f6  mov     rcx, cs:?g_GlobalSchemaMgr@VaultGlobals@@3VCVaultGlobalSchemaMgr@@A; this
0x1800462fd  call    ?GetVaultStore@CUserVault@@QEAAKPEAPEAUIVaultStore@@E@Z; CUserVault::GetVaultStore(IVaultStore * *,uchar)
0x180046302  mov     ebx, eax
0x180046304  mov     [rsp+160h+var_120], eax
0x180046308  test    eax, eax
0x18004630a  jz      loc_1800463B4
0x180046310  mov     rcx, cs:WPP_GLOBAL_Control
0x180046317  cmp     rcx, rdi
0x18004631a  jz      short loc_18004633A
0x18004631c  test    byte ptr [rcx+1Ch], 2
0x180046320  jz      short loc_18004633A
0x180046322  mov     edx, 24h ; '$'
0x180046327  mov     r9d, eax
0x18004632a  mov     r8, rsi
0x18004632d  mov     rcx, [rcx+10h]
0x180046331  call    WPP_SF_d
0x180046336  mov     ebx, [rsp+160h+var_120]
0x18004633a  lea     rcx, [rbp+60h+var_C0]
0x18004633e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046343  nop
0x180046344  mov     rcx, [rsp+160h+hMem]; hMem
0x180046349  test    rcx, rcx
0x18004634c  jz      short loc_180046386
0x18004634e  mov     eax, [rbp+60h+var_E0]
0x180046351  test    eax, eax
0x180046353  jz      short loc_18004636F
0x180046355  test    rcx, rcx
0x180046358  jz      short loc_18004636F
0x18004635a  mov     edx, eax
0x18004635c  test    eax, eax
0x18004635e  jz      short loc_18004636F
0x180046360  mov     rax, rcx
0x180046363  mov     byte ptr [rax], 0
0x180046366  inc     rax
0x180046369  sub     rdx, 1
0x18004636d  jnz     short loc_180046363
0x18004636f  mov     rax, [rsp+160h+var_F0]
0x180046374  test    rax, rax
0x180046377  jz      short loc_180046380
0x180046379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004637e  jmp     short loc_180046386
0x180046380  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180046385  nop
0x180046386  lea     rcx, [rbp+60h+var_A0]; this
0x18004638a  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x18004638f  lea     rcx, [rsp+160h+var_118]; this
0x180046394  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046399  nop
0x18004639a  lea     rcx, [rbp+60h+var_D8]
0x18004639e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800463a3  nop
0x1800463a4  lea     rcx, [rsp+160h+var_108]
0x1800463a9  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x1800463ae  nop
0x1800463af  jmp     loc_1800468E5
0x1800463b4  mov     rbx, [rsp+160h+hMem]
0x1800463b9  mov     rax, [rbx]
0x1800463bc  lea     r8, [rbp+60h+var_B8]
0x1800463c0  mov     rdx, r13
0x1800463c3  mov     rcx, rbx
0x1800463c6  mov     rax, [rax+50h]
0x1800463ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463cf  mov     r12d, eax
0x1800463d2  mov     [rsp+160h+var_120], eax
0x1800463d6  test    eax, eax
0x1800463d8  jnz     loc_180046479
0x1800463de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463e5  cmp     rcx, rdi
0x1800463e8  jz      short loc_1800463FF
0x1800463ea  test    byte ptr [rcx+1Ch], 2
0x1800463ee  jz      short loc_1800463FF
0x1800463f0  lea     edx, [rax+25h]
0x1800463f3  mov     r8, rsi
0x1800463f6  mov     rcx, [rcx+10h]
0x1800463fa  call    WPP_SF_
0x1800463ff  mov     edi, 0B7h
0x180046404  mov     [rsp+160h+var_120], edi
0x180046408  lea     rcx, [rbp+60h+var_C0]
0x18004640c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046411  nop
0x180046412  test    rbx, rbx
0x180046415  jz      short loc_180046449
0x180046417  mov     eax, [rbp+60h+var_E0]
0x18004641a  cmp     rax, 1
0x18004641e  jb      short loc_18004642F
0x180046420  mov     rcx, rbx
0x180046423  mov     byte ptr [rcx], 0
0x180046426  inc     rcx
0x180046429  sub     rax, 1
0x18004642d  jnz     short loc_180046423
0x18004642f  mov     rax, [rsp+160h+var_F0]
0x180046434  mov     rcx, rbx; hMem
0x180046437  test    rax, rax
0x18004643a  jz      short loc_180046443
0x18004643c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046441  jmp     short loc_180046449
0x180046443  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180046448  nop
0x180046449  lea     rcx, [rbp+60h+var_A0]; this
0x18004644d  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x180046452  lea     rcx, [rsp+160h+var_118]; this
0x180046457  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x18004645c  nop
0x18004645d  lea     rcx, [rbp+60h+var_D8]
0x180046461  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046466  nop
0x180046467  lea     rcx, [rsp+160h+var_108]
0x18004646c  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046471  nop
0x180046472  mov     eax, edi
0x180046474  jmp     loc_1800468E7
0x180046479  cmp     eax, r15d
0x18004647c  jz      loc_18004651F
0x180046482  mov     rcx, cs:WPP_GLOBAL_Control
0x180046489  cmp     rcx, rdi
0x18004648c  jz      short loc_1800464AD
0x18004648e  test    byte ptr [rcx+1Ch], 2
0x180046492  jz      short loc_1800464AD
0x180046494  mov     edx, 26h ; '&'
0x180046499  mov     r9d, eax
0x18004649c  mov     r8, rsi
0x18004649f  mov     rcx, [rcx+10h]
0x1800464a3  call    WPP_SF_d
0x1800464a8  mov     r12d, [rsp+160h+var_120]
0x1800464ad  lea     rcx, [rbp+60h+var_C0]
0x1800464b1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
  ... truncated ...
```
