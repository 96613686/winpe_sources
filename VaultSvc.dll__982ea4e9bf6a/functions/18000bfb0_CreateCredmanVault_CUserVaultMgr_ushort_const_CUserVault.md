# CreateCredmanVault(CUserVaultMgr *,ushort const *,CUserVault * *)

- ea: `0x18000bfb0`
- end: `0x18000c341`
- name: `?CreateCredmanVault@@YAKPEAVCUserVaultMgr@@PEBGPEAPEAVCUserVault@@@Z`
- size: `913`
- prototype: `__int64 __fastcall(struct CUserVaultMgr *, const unsigned __int16 *, struct CUserVault **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18000cd28`

## callees

- `0x180003140`
- `0x180004cfc`
- `0x18000a6d0`
- `0x18000ab94`
- `0x18000acfc`
- `0x18000ad34`
- `0x18000af08`
- `0x18000bfb0`
- `0x18000cadc`
- `0x180012210`
- `0x180031b80`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall CreateCredmanVault(struct CUserVaultMgr *a1, const unsigned __int16 *a2, struct CUserVault **a3)
{
  unsigned __int8 *v6; // rdx
  unsigned int v7; // r8d
  unsigned int VaultKeyMaterial; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  HLOCAL v12; // rcx
  _BYTE *v13; // rax
  _BYTE *v14; // rbx
  CUserVault *v15; // rax
  struct CUserVault *v16; // rdi
  __int64 v17; // rax
  _BYTE *v18; // rcx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  HLOCAL hMem; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v22; // [rsp+40h] [rbp-29h]
  __int64 (__fastcall *v23)(__int64); // [rsp+48h] [rbp-21h] BYREF
  struct IVaultKeyManager *v24; // [rsp+50h] [rbp-19h] BYREF
  int v25; // [rsp+58h] [rbp-11h]
  unsigned __int8 *v26[2]; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v27; // [rsp+70h] [rbp+7h] BYREF
  void *v28; // [rsp+78h] [rbp+Fh]
  int v29; // [rsp+80h] [rbp+17h]
  void *v30[2]; // [rsp+88h] [rbp+1Fh] BYREF
  int v31; // [rsp+98h] [rbp+2Fh]
  void *v32; // [rsp+A0h] [rbp+37h]
  int v33; // [rsp+A8h] [rbp+3Fh]
  __int64 v34; // [rsp+E8h] [rbp+7Fh] BYREF

  hMem = 0;
  v22 = 0;
  v23 = AutoDereference<IVaultKeyManager>;
  v24 = 0;
  v25 = 0;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  v29 = 1;
  v28 = &VaultCryptoGlobals::g_VaultAes256Provider;
  ((void (__fastcall *)(void *))*VaultCryptoGlobals::g_VaultAes256Provider)(&VaultCryptoGlobals::g_VaultAes256Provider);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  v33 = 2;
  v32 = &VaultCryptoGlobals::g_VaultAes128Provider;
  ((void (*)(void))*VaultCryptoGlobals::g_VaultAes128Provider)();
  v34 = 0;
  VaultKeyMaterial = CVaultCryptoProvider::GenerateKeyMaterial(
                       (CVaultCryptoProvider *)&VaultCryptoGlobals::g_VaultAes256Provider,
                       v6,
                       v7,
                       (void **)v26,
                       &v26[1],
                       &v27);
  if ( VaultKeyMaterial || (VaultKeyMaterial = CVaultKey::GenerateVaultKeyMaterial(v30)) != 0 )
  {
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&v34);
    CVaultKey::~CVaultKey((CVaultKey *)v30);
    CVaultKey::~CVaultKey((CVaultKey *)v26);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    return VaultKeyMaterial;
  }
  VaultKeyMaterial = CVaultFactory::CreateVaultKeyManager(
                       (CVaultFactory *)VaultGlobals::g_VaultFactory,
                       &Vault_Protection_Dpapi,
                       &v24);
  if ( VaultKeyMaterial )
  {
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&v34);
    CVaultKey::~CVaultKey((CVaultKey *)v30);
    CVaultKey::~CVaultKey((CVaultKey *)v26);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    return VaultKeyMaterial;
  }
  v10 = CVaultCredmanStore::ConstructCredmanStore(a2, (struct IVaultStore **)&hMem);
  VaultKeyMaterial = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids, v10);
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&v34);
    CVaultKey::~CVaultKey((CVaultKey *)v30);
    CVaultKey::~CVaultKey((CVaultKey *)v26);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    v12 = hMem;
    if ( hMem )
    {
      if ( v22 )
      {
        v11 = v22;
        v13 = hMem;
        do
        {
          *v13++ = 0;
          --v11;
        }
        while ( v11 );
      }
      if ( AutoDereference<IVaultKeyManager> )
        ((void (__fastcall *)(HLOCAL, __int64))AutoDereference<IVaultKeyManager>)(v12, v11);
      else
        VaultFreeInternal(v12);
    }
    return VaultKeyMaterial;
  }
  v14 = hMem;
  v15 = (CUserVault *)CUserVault::InstantiateUserVaultObject(a1, hMem, 2);
  v16 = v15;
  if ( v15 )
  {
    CUserVault::InitVaultKey(v15, (struct CVaultKey *)v30, (struct CVaultKey *)v26, v24);
    *a3 = v16;
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&v34);
    CVaultKey::~CVaultKey((CVaultKey *)v30);
    CVaultKey::~CVaultKey((CVaultKey *)v26);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    if ( v14 )
    {
      v19 = v22;
      if ( v22 )
      {
        v20 = v14;
        do
        {
          *v20++ = 0;
          --v19;
        }
        while ( v19 );
      }
      if ( AutoDereference<IVaultKeyManager> )
        AutoDereference<IVaultKeyManager>((__int64)v14);
      else
        VaultFreeInternal(v14);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids);
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&v34);
    CVaultKey::~CVaultKey((CVaultKey *)v30);
    CVaultKey::~CVaultKey((CVaultKey *)v26);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    if ( v14 )
    {
      v17 = v22;
      if ( v22 )
      {
        v18 = v14;
        do
        {
          *v18++ = 0;
          --v17;
        }
        while ( v17 );
      }
      if ( AutoDereference<IVaultKeyManager> )
        AutoDereference<IVaultKeyManager>((__int64)v14);
      else
        VaultFreeInternal(v14);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x18000bfb0  mov     [rsp-8+arg_0], rbx
0x18000bfb5  mov     [rsp-8+arg_8], rsi
0x18000bfba  push    rbp
0x18000bfbb  push    rdi
0x18000bfbc  push    r14
0x18000bfbe  lea     rbp, [rsp-47h]
0x18000bfc3  sub     rsp, 0B0h
0x18000bfca  mov     r14, r8
0x18000bfcd  mov     rdi, rdx
0x18000bfd0  mov     rsi, rcx
0x18000bfd3  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18000bfda  mov     [rbp+57h+var_90], rax
0x18000bfde  mov     [rbp+57h+hMem], 0
0x18000bfe6  mov     [rbp+57h+var_80], 0
0x18000bfed  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18000bff4  mov     [rbp+57h+var_78], rax
0x18000bff8  mov     [rbp+57h+var_70], 0
0x18000c000  mov     [rbp+57h+var_68], 0
0x18000c007  xorps   xmm0, xmm0
0x18000c00a  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18000c00f  mov     [rbp+57h+var_50], 0
0x18000c016  mov     [rbp+57h+var_40], 1
0x18000c01d  lea     rbx, ?g_VaultAes256Provider@VaultCryptoGlobals@@3VCVaultCryptoProvider@@A; CVaultCryptoProvider VaultCryptoGlobals::g_VaultAes256Provider
0x18000c024  mov     [rbp+57h+var_48], rbx
0x18000c028  mov     rax, cs:?g_VaultAes256Provider@VaultCryptoGlobals@@3VCVaultCryptoProvider@@A; CVaultCryptoProvider VaultCryptoGlobals::g_VaultAes256Provider
0x18000c02f  mov     rcx, rbx
0x18000c032  mov     rax, [rax]
0x18000c035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c03a  nop
0x18000c03b  xorps   xmm0, xmm0
0x18000c03e  movdqu  xmmword ptr [rbp+57h+var_38], xmm0
0x18000c043  mov     [rbp+57h+var_28], 0
0x18000c04a  mov     [rbp+57h+var_18], 2
0x18000c051  lea     rcx, ?g_VaultAes128Provider@VaultCryptoGlobals@@3VCVaultCryptoProvider@@A; CVaultCryptoProvider VaultCryptoGlobals::g_VaultAes128Provider
0x18000c058  mov     [rbp+57h+var_20], rcx
0x18000c05c  mov     rax, cs:?g_VaultAes128Provider@VaultCryptoGlobals@@3VCVaultCryptoProvider@@A; CVaultCryptoProvider VaultCryptoGlobals::g_VaultAes128Provider
0x18000c063  mov     rax, [rax]
0x18000c066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c06b  nop
0x18000c06c  mov     [rbp+57h+arg_18], 0
0x18000c074  lea     rax, [rbp+57h+var_50]
0x18000c078  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x18000c07d  lea     rax, [rbp+57h+var_60+8]
0x18000c081  mov     [rsp+0C0h+var_A0], rax; unsigned __int8 **
0x18000c086  lea     r9, [rbp+57h+var_60]; void **
0x18000c08a  mov     rcx, rbx; this
0x18000c08d  call    ?GenerateKeyMaterial@CVaultCryptoProvider@@QEAAKPEAEKPEAPEAXPEAPEAEPEAK@Z; CVaultCryptoProvider::GenerateKeyMaterial(uchar *,ulong,void * *,uchar * *,ulong *)
0x18000c092  mov     ebx, eax
0x18000c094  test    eax, eax
0x18000c096  jz      short loc_18000C0C7
0x18000c098  lea     rcx, [rbp+57h+arg_18]; this
0x18000c09c  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x18000c0a1  nop
0x18000c0a2  lea     rcx, [rbp+57h+var_38]; this
0x18000c0a6  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c0ab  nop
0x18000c0ac  lea     rcx, [rbp+57h+var_60]; this
0x18000c0b0  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c0b5  nop
0x18000c0b6  lea     rcx, [rbp+57h+var_78]
0x18000c0ba  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c0bf  nop
0x18000c0c0  mov     eax, ebx
0x18000c0c2  jmp     loc_18000C329
0x18000c0c7  lea     rcx, [rbp+57h+var_38]; this
0x18000c0cb  call    ?GenerateVaultKeyMaterial@CVaultKey@@QEAAKXZ; CVaultKey::GenerateVaultKeyMaterial(void)
0x18000c0d0  mov     ebx, eax
0x18000c0d2  test    eax, eax
0x18000c0d4  jz      short loc_18000C100
0x18000c0d6  lea     rcx, [rbp+57h+arg_18]; this
0x18000c0da  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x18000c0df  nop
0x18000c0e0  lea     rcx, [rbp+57h+var_38]; this
0x18000c0e4  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c0e9  nop
0x18000c0ea  lea     rcx, [rbp+57h+var_60]; this
0x18000c0ee  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c0f3  nop
0x18000c0f4  lea     rcx, [rbp+57h+var_78]
0x18000c0f8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c0fd  nop
0x18000c0fe  jmp     short loc_18000C0C0
0x18000c100  lea     r8, [rbp+57h+var_70]; struct IVaultKeyManager **
0x18000c104  lea     rdx, Vault_Protection_Dpapi; struct _GUID *
0x18000c10b  lea     rcx, ?g_VaultFactory@VaultGlobals@@3VCVaultFactory@@A; this
0x18000c112  call    ?CreateVaultKeyManager@CVaultFactory@@UEAAKPEBU_GUID@@PEAPEAUIVaultKeyManager@@@Z; CVaultFactory::CreateVaultKeyManager(_GUID const *,IVaultKeyManager * *)
0x18000c117  mov     ebx, eax
0x18000c119  test    eax, eax
0x18000c11b  jz      short loc_18000C14A
0x18000c11d  lea     rcx, [rbp+57h+arg_18]; this
0x18000c121  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x18000c126  nop
0x18000c127  lea     rcx, [rbp+57h+var_38]; this
0x18000c12b  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c130  nop
0x18000c131  lea     rcx, [rbp+57h+var_60]; this
0x18000c135  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c13a  nop
0x18000c13b  lea     rcx, [rbp+57h+var_78]
0x18000c13f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c144  nop
0x18000c145  jmp     loc_18000C0C0
0x18000c14a  lea     rdx, [rbp+57h+hMem]; struct IVaultStore **
0x18000c14e  mov     rcx, rdi; unsigned __int16 *
0x18000c151  call    ?ConstructCredmanStore@CVaultCredmanStore@@SAKPEBGPEAPEAUIVaultStore@@@Z; CVaultCredmanStore::ConstructCredmanStore(ushort const *,IVaultStore * *)
0x18000c156  mov     ebx, eax
0x18000c158  test    eax, eax
0x18000c15a  jz      loc_18000C1FF
0x18000c160  lea     rdx, WPP_GLOBAL_Control
0x18000c167  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c16e  cmp     rcx, rdx
0x18000c171  jz      short loc_18000C192
0x18000c173  test    byte ptr [rcx+1Ch], 2
0x18000c177  jz      short loc_18000C192
0x18000c179  mov     edx, 0Eh
0x18000c17e  mov     r9d, eax
0x18000c181  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x18000c188  mov     rcx, [rcx+10h]
0x18000c18c  call    WPP_SF_d
0x18000c191  nop
0x18000c192  lea     rcx, [rbp+57h+arg_18]; this
0x18000c196  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x18000c19b  nop
0x18000c19c  lea     rcx, [rbp+57h+var_38]; this
0x18000c1a0  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c1a5  nop
0x18000c1a6  lea     rcx, [rbp+57h+var_60]; this
0x18000c1aa  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c1af  nop
0x18000c1b0  lea     rcx, [rbp+57h+var_78]
0x18000c1b4  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c1b9  nop
0x18000c1ba  mov     rcx, [rbp+57h+hMem]; hMem
0x18000c1be  test    rcx, rcx
0x18000c1c1  jz      short loc_18000C1FA
0x18000c1c3  mov     eax, [rbp+57h+var_80]
0x18000c1c6  test    eax, eax
0x18000c1c8  jz      short loc_18000C1E4
0x18000c1ca  test    rcx, rcx
0x18000c1cd  jz      short loc_18000C1E4
0x18000c1cf  mov     edx, eax
0x18000c1d1  test    eax, eax
0x18000c1d3  jz      short loc_18000C1E4
0x18000c1d5  mov     rax, rcx
0x18000c1d8  mov     byte ptr [rax], 0
0x18000c1db  inc     rax
0x18000c1de  sub     rdx, 1
0x18000c1e2  jnz     short loc_18000C1D8
0x18000c1e4  mov     rax, [rbp+57h+var_90]
0x18000c1e8  test    rax, rax
0x18000c1eb  jz      short loc_18000C1F4
0x18000c1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1f2  jmp     short loc_18000C1FA
0x18000c1f4  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18000c1f9  nop
0x18000c1fa  jmp     loc_18000C0C0
0x18000c1ff  mov     rbx, [rbp+57h+hMem]
0x18000c203  mov     r8d, 2
0x18000c209  mov     rdx, rbx
0x18000c20c  mov     rcx, rsi
0x18000c20f  call    ?InstantiateUserVaultObject@CUserVault@@SAPEAV1@PEAVCUserVaultMgr@@PEAUIVaultStore@@W4efVaultFlags@@@Z; CUserVault::InstantiateUserVaultObject(CUserVaultMgr *,IVaultStore *,efVaultFlags)
0x18000c214  mov     rdi, rax
0x18000c217  test    rax, rax
0x18000c21a  jnz     loc_18000C2B2
0x18000c220  lea     rdx, WPP_GLOBAL_Control
0x18000c227  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c22e  cmp     rcx, rdx
0x18000c231  jz      short loc_18000C24D
0x18000c233  test    byte ptr [rcx+1Ch], 2
0x18000c237  jz      short loc_18000C24D
0x18000c239  lea     edx, [rax+0Fh]
0x18000c23c  lea     r8, WPP_6081ca3d18673b5dea6fba056fc5e84e_Traceguids
0x18000c243  mov     rcx, [rcx+10h]
0x18000c247  call    WPP_SF_
0x18000c24c  nop
0x18000c24d  lea     rcx, [rbp+57h+arg_18]; this
0x18000c251  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x18000c256  nop
0x18000c257  lea     rcx, [rbp+57h+var_38]; this
0x18000c25b  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c260  nop
0x18000c261  lea     rcx, [rbp+57h+var_60]; this
0x18000c265  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c26a  nop
0x18000c26b  lea     rcx, [rbp+57h+var_78]
0x18000c26f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c274  nop
0x18000c275  test    rbx, rbx
0x18000c278  jz      short loc_18000C2AB
0x18000c27a  mov     eax, [rbp+57h+var_80]
0x18000c27d  cmp     rax, 1
0x18000c281  jb      short loc_18000C292
0x18000c283  mov     rcx, rbx
0x18000c286  mov     byte ptr [rcx], 0
0x18000c289  inc     rcx
0x18000c28c  sub     rax, 1
0x18000c290  jnz     short loc_18000C286
0x18000c292  mov     rax, [rbp+57h+var_90]
0x18000c296  mov     rcx, rbx; hMem
0x18000c299  test    rax, rax
0x18000c29c  jz      short loc_18000C2A5
0x18000c29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a3  jmp     short loc_18000C2AB
0x18000c2a5  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18000c2aa  nop
0x18000c2ab  mov     eax, 0Eh
0x18000c2b0  jmp     short loc_18000C329
0x18000c2b2  mov     r9, [rbp+57h+var_70]; struct IVaultKeyManager *
0x18000c2b6  lea     r8, [rbp+57h+var_60]; struct CVaultKey *
0x18000c2ba  lea     rdx, [rbp+57h+var_38]; struct CVaultKey *
0x18000c2be  mov     rcx, rdi; this
0x18000c2c1  call    ?InitVaultKey@CUserVault@@QEAAKPEAVCVaultKey@@0PEAUIVaultKeyManager@@@Z; CUserVault::InitVaultKey(CVaultKey *,CVaultKey *,IVaultKeyManager *)
0x18000c2c6  mov     [r14], rdi
0x18000c2c9  lea     rcx, [rbp+57h+arg_18]; this
0x18000c2cd  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x18000c2d2  nop
0x18000c2d3  lea     rcx, [rbp+57h+var_38]; this
0x18000c2d7  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c2dc  nop
0x18000c2dd  lea     rcx, [rbp+57h+var_60]; this
0x18000c2e1  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18000c2e6  nop
0x18000c2e7  lea     rcx, [rbp+57h+var_78]
0x18000c2eb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c2f0  nop
0x18000c2f1  test    rbx, rbx
0x18000c2f4  jz      short loc_18000C327
0x18000c2f6  mov     eax, [rbp+57h+var_80]
0x18000c2f9  cmp     rax, 1
0x18000c2fd  jb      short loc_18000C30E
0x18000c2ff  mov     rcx, rbx
0x18000c302  mov     byte ptr [rcx], 0
0x18000c305  inc     rcx
0x18000c308  sub     rax, 1
0x18000c30c  jnz     short loc_18000C302
0x18000c30e  mov     rax, [rbp+57h+var_90]
0x18000c312  mov     rcx, rbx; hMem
0x18000c315  test    rax, rax
0x18000c318  jz      short loc_18000C321
0x18000c31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c31f  jmp     short loc_18000C327
0x18000c321  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18000c326  nop
0x18000c327  xor     eax, eax
0x18000c329  lea     r11, [rsp+0C0h+var_10]
0x18000c331  mov     rbx, [r11+20h]
0x18000c335  mov     rsi, [r11+28h]
0x18000c339  mov     rsp, r11
0x18000c33c  pop     r14
0x18000c33e  pop     rdi
0x18000c33f  pop     rbp
0x18000c340  retn
```
