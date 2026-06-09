# CreateNewVaultInternal(CUserVaultMgr *,ushort const *,uchar,_GUID const *,_GUID const *,ushort const *,eVaultType,efVaultFlags,VaultPolicy *,IVaultCall *,CUserVault * *)

- ea: `0x180037f5c`
- end: `0x180038389`
- name: `?CreateNewVaultInternal@@YAKPEAVCUserVaultMgr@@PEBGEPEBU_GUID@@21W4eVaultType@@W4efVaultFlags@@PEAUVaultPolicy@@PEAUIVaultCall@@PEAPEAVCUserVault@@@Z`
- size: `1069`
- prototype: `__int64 __fastcall(__int64, wchar_t *, char, const struct _GUID *, __int64, __int64, int, unsigned int, __int64, __int64, CUserVault **)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180037eb8`
- `0x18003c62c`

## callees

- `0x180003140`
- `0x18000a6d0`
- `0x18000ab94`
- `0x18000acfc`
- `0x18000ad34`
- `0x18000af08`
- `0x18000b9f4`
- `0x18000bf3c`
- `0x18000cadc`
- `0x180012210`
- `0x180031b80`
- `0x180037f5c`
- `0x18003d084`
- `0x18003d960`
- `0x18004d010`

## pseudocode

```c
__int64 __fastcall CreateNewVaultInternal(
        __int64 a1,
        wchar_t *a2,
        char a3,
        const struct _GUID *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int a8,
        __int64 a9,
        __int64 a10,
        CUserVault **a11)
{
  unsigned __int8 *v15; // rdx
  unsigned int v16; // r8d
  unsigned int VaultKeyMaterial; // ebx
  struct CUserVault *v19; // rdx
  __int64 v20; // rdx
  HLOCAL v21; // rcx
  _BYTE *v22; // rax
  _BYTE *v23; // rbx
  CUserVault *v24; // rax
  CUserVault *v25; // rdi
  __int64 v26; // rax
  _BYTE *v27; // rcx
  __int64 v28; // rax
  _BYTE *v29; // rcx
  unsigned __int8 **v30; // [rsp+28h] [rbp-C1h]
  __int64 (__fastcall *v31)(__int64); // [rsp+50h] [rbp-99h] BYREF
  struct IVaultKeyManager *v32; // [rsp+58h] [rbp-91h] BYREF
  int v33; // [rsp+60h] [rbp-89h]
  __int64 v34; // [rsp+68h] [rbp-81h] BYREF
  unsigned __int8 *v35; // [rsp+70h] [rbp-79h] BYREF
  int v36; // [rsp+78h] [rbp-71h]
  __int64 (__fastcall *v37)(__int64); // [rsp+80h] [rbp-69h]
  HLOCAL hMem; // [rsp+88h] [rbp-61h] BYREF
  unsigned int v39; // [rsp+90h] [rbp-59h]
  unsigned __int8 *v40[2]; // [rsp+98h] [rbp-51h] BYREF
  unsigned int v41; // [rsp+A8h] [rbp-41h] BYREF
  CVaultCryptoProvider *v42; // [rsp+B0h] [rbp-39h]
  int v43; // [rsp+B8h] [rbp-31h]
  void *v44[2]; // [rsp+C0h] [rbp-29h] BYREF
  int v45; // [rsp+D0h] [rbp-19h]
  __int64 v46; // [rsp+D8h] [rbp-11h]
  int v47; // [rsp+E0h] [rbp-9h]

  v31 = AutoDereference<IVaultKeyManager>;
  v32 = 0;
  v33 = 0;
  v37 = AutoDereference<IVaultKeyManager>;
  hMem = 0;
  v39 = 0;
  v35 = 0;
  v36 = 0;
  v34 = 0;
  a8 = 0;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 1;
  CVaultKey::AssociateCryptoProviderWithAlg(v40, 1);
  *(_OWORD *)v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 2;
  CVaultKey::AssociateCryptoProviderWithAlg(v44, 2);
  a5 = 0;
  CVaultKey::Delete((CVaultKey *)v40);
  VaultKeyMaterial = CVaultCryptoProvider::GenerateKeyMaterial(v42, v15, v16, (void **)v40, &v40[1], &v41);
  if ( VaultKeyMaterial )
  {
    CVaultKey::Delete((CVaultKey *)v44);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
    CVaultKey::Delete((CVaultKey *)v40);
    if ( v42 )
      (*(void (__fastcall **)(CVaultCryptoProvider *))(*(_QWORD *)v42 + 8LL))(v42);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v31);
    return VaultKeyMaterial;
  }
  VaultKeyMaterial = CVaultKey::GenerateVaultKeyMaterial(v44);
  if ( VaultKeyMaterial )
  {
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&a5);
    CVaultKey::~CVaultKey((CVaultKey *)v44);
    CVaultKey::~CVaultKey((CVaultKey *)v40);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v31);
    return VaultKeyMaterial;
  }
  VaultKeyMaterial = CVaultFactory::CreateVaultKeyManager(
                       (CVaultFactory *)VaultGlobals::g_VaultFactory,
                       &Vault_Protection_Dpapi,
                       &v32);
  if ( VaultKeyMaterial
    || (VaultKeyMaterial = CVaultKeyStoreMgr::SerializeAndProtectKeyMaterial(
                             (CVaultKeyStoreMgr *)&a5,
                             v19,
                             v32,
                             (struct CVaultKey *)v44,
                             (struct CVaultKey *)v40,
                             &v35,
                             &a8)) != 0 )
  {
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&a5);
    CVaultKey::~CVaultKey((CVaultKey *)v44);
    CVaultKey::~CVaultKey((CVaultKey *)v40);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v31);
    return VaultKeyMaterial;
  }
  LOBYTE(v30) = a3;
  VaultKeyMaterial = CVaultFactory::CreateNewVault(
                       (__int64)VaultGlobals::g_VaultFactory,
                       a4,
                       (__int64)v35,
                       a8,
                       a2,
                       (__int64)v30,
                       a6,
                       a7,
                       a9,
                       &hMem);
  if ( VaultKeyMaterial )
  {
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&a5);
    CVaultKey::~CVaultKey((CVaultKey *)v44);
    CVaultKey::~CVaultKey((CVaultKey *)v40);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    v21 = hMem;
    if ( hMem )
    {
      if ( v39 )
      {
        v20 = v39;
        v22 = hMem;
        do
        {
          *v22++ = 0;
          --v20;
        }
        while ( v20 );
      }
      if ( v37 )
        ((void (__fastcall *)(HLOCAL, __int64))v37)(v21, v20);
      else
        VaultFreeInternal(v21);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v31);
    return VaultKeyMaterial;
  }
  v23 = hMem;
  v24 = (CUserVault *)CUserVault::InstantiateUserVaultObject(a1, hMem, 0);
  v25 = v24;
  if ( v24 )
  {
    CUserVault::InitVaultKey(v24, (struct CVaultKey *)v44, (struct CVaultKey *)v40, v32);
    *a11 = v25;
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&a5);
    CVaultKey::~CVaultKey((CVaultKey *)v44);
    CVaultKey::~CVaultKey((CVaultKey *)v40);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    if ( v23 )
    {
      v28 = v39;
      if ( v39 )
      {
        v29 = v23;
        do
        {
          *v29++ = 0;
          --v28;
        }
        while ( v28 );
      }
      if ( v37 )
        v37((__int64)v23);
      else
        VaultFreeInternal(v23);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v31);
    return 0;
  }
  else
  {
    CVaultKeyStoreMgr::~CVaultKeyStoreMgr((CVaultKeyStoreMgr *)&a5);
    CVaultKey::~CVaultKey((CVaultKey *)v44);
    CVaultKey::~CVaultKey((CVaultKey *)v40);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v34);
    if ( v23 )
    {
      v26 = v39;
      if ( v39 )
      {
        v27 = v23;
        do
        {
          *v27++ = 0;
          --v26;
        }
        while ( v26 );
      }
      if ( v37 )
        v37((__int64)v23);
      else
        VaultFreeInternal(v23);
    }
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v31);
    return 14;
  }
}

```

## disassembly

```asm
0x180037f5c  push    rbp
0x180037f5e  push    rbx
0x180037f5f  push    rsi
0x180037f60  push    rdi
0x180037f61  push    r12
0x180037f63  push    r14
0x180037f65  push    r15
0x180037f67  lea     rbp, [rsp-7]
0x180037f6c  sub     rsp, 0F0h
0x180037f73  mov     rsi, r9
0x180037f76  mov     r14b, r8b
0x180037f79  mov     r15, rdx
0x180037f7c  mov     rdi, rcx
0x180037f7f  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180037f86  mov     [rsp+120h+var_D0], rax
0x180037f8b  xor     r12d, r12d
0x180037f8e  mov     [rsp+120h+var_C8], r12
0x180037f93  mov     [rsp+120h+var_C0], r12d
0x180037f98  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180037f9f  mov     [rbp+37h+var_A0], rax
0x180037fa3  mov     [rbp+37h+hMem], r12
0x180037fa7  mov     [rbp+37h+var_90], r12d
0x180037fab  mov     [rbp+37h+var_B0], r12
0x180037faf  mov     [rbp+37h+var_A8], r12d
0x180037fb3  mov     [rsp+120h+var_B8], r12
0x180037fb8  mov     [rbp+37h+arg_38], r12d
0x180037fbc  xorps   xmm0, xmm0
0x180037fbf  movdqu  xmmword ptr [rbp+37h+var_88], xmm0
0x180037fc4  mov     [rbp+37h+var_78], r12d
0x180037fc8  mov     [rbp+37h+var_70], r12
0x180037fcc  mov     [rbp+37h+var_68], 1
0x180037fd3  lea     edx, [r12+1]
0x180037fd8  lea     rcx, [rbp+37h+var_88]
0x180037fdc  call    ?AssociateCryptoProviderWithAlg@CVaultKey@@AEAAKW4eVaultProtectionAlg@@@Z; CVaultKey::AssociateCryptoProviderWithAlg(eVaultProtectionAlg)
0x180037fe1  nop
0x180037fe2  xorps   xmm0, xmm0
0x180037fe5  movdqu  xmmword ptr [rbp+37h+var_60], xmm0
0x180037fea  mov     [rbp+37h+var_50], r12d
0x180037fee  mov     [rbp+37h+var_48], r12
0x180037ff2  lea     edx, [r12+2]
0x180037ff7  mov     [rbp+37h+var_40], edx
0x180037ffa  lea     rcx, [rbp+37h+var_60]
0x180037ffe  call    ?AssociateCryptoProviderWithAlg@CVaultKey@@AEAAKW4eVaultProtectionAlg@@@Z; CVaultKey::AssociateCryptoProviderWithAlg(eVaultProtectionAlg)
0x180038003  nop
0x180038004  mov     [rbp+37h+arg_20], r12
0x180038008  lea     rcx, [rbp+37h+var_88]; this
0x18003800c  call    ?Delete@CVaultKey@@QEAAXXZ; CVaultKey::Delete(void)
0x180038011  lea     rax, [rbp+37h+var_78]
0x180038015  mov     [rsp+120h+var_F8], rax; unsigned int *
0x18003801a  lea     rax, [rbp+37h+var_88+8]
0x18003801e  mov     [rsp+120h+var_100], rax; unsigned __int8 **
0x180038023  lea     r9, [rbp+37h+var_88]; void **
0x180038027  mov     rcx, [rbp+37h+var_70]; this
0x18003802b  call    ?GenerateKeyMaterial@CVaultCryptoProvider@@QEAAKPEAEKPEAPEAXPEAPEAEPEAK@Z; CVaultCryptoProvider::GenerateKeyMaterial(uchar *,ulong,void * *,uchar * *,ulong *)
0x180038030  mov     ebx, eax
0x180038032  test    eax, eax
0x180038034  jz      short loc_180038091
0x180038036  lea     rcx, [rbp+37h+var_60]; this
0x18003803a  call    ?Delete@CVaultKey@@QEAAXXZ; CVaultKey::Delete(void)
0x18003803f  mov     rcx, [rbp+37h+var_48]
0x180038043  test    rcx, rcx
0x180038046  jz      short loc_180038055
0x180038048  mov     rax, [rcx]
0x18003804b  mov     rax, [rax+8]
0x18003804f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038054  nop
0x180038055  lea     rcx, [rbp+37h+var_88]; this
0x180038059  call    ?Delete@CVaultKey@@QEAAXXZ; CVaultKey::Delete(void)
0x18003805e  mov     rcx, [rbp+37h+var_70]
0x180038062  test    rcx, rcx
0x180038065  jz      short loc_180038074
0x180038067  mov     rax, [rcx]
0x18003806a  mov     rax, [rax+8]
0x18003806e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038073  nop
0x180038074  lea     rcx, [rsp+120h+var_B8]
0x180038079  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003807e  nop
0x18003807f  lea     rcx, [rsp+120h+var_D0]
0x180038084  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180038089  nop
0x18003808a  mov     eax, ebx
0x18003808c  jmp     loc_180038377
0x180038091  lea     rcx, [rbp+37h+var_60]; this
0x180038095  call    ?GenerateVaultKeyMaterial@CVaultKey@@QEAAKXZ; CVaultKey::GenerateVaultKeyMaterial(void)
0x18003809a  mov     ebx, eax
0x18003809c  test    eax, eax
0x18003809e  jz      short loc_1800380D6
0x1800380a0  lea     rcx, [rbp+37h+arg_20]; this
0x1800380a4  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x1800380a9  nop
0x1800380aa  lea     rcx, [rbp+37h+var_60]; this
0x1800380ae  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x1800380b3  nop
0x1800380b4  lea     rcx, [rbp+37h+var_88]; this
0x1800380b8  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x1800380bd  nop
0x1800380be  lea     rcx, [rsp+120h+var_B8]
0x1800380c3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800380c8  nop
0x1800380c9  lea     rcx, [rsp+120h+var_D0]
0x1800380ce  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800380d3  nop
0x1800380d4  jmp     short loc_18003808A
0x1800380d6  lea     r8, [rsp+120h+var_C8]; struct IVaultKeyManager **
0x1800380db  lea     rdx, Vault_Protection_Dpapi; struct _GUID *
0x1800380e2  lea     rcx, ?g_VaultFactory@VaultGlobals@@3VCVaultFactory@@A; this
0x1800380e9  call    ?CreateVaultKeyManager@CVaultFactory@@UEAAKPEBU_GUID@@PEAPEAUIVaultKeyManager@@@Z; CVaultFactory::CreateVaultKeyManager(_GUID const *,IVaultKeyManager * *)
0x1800380ee  mov     ebx, eax
0x1800380f0  test    eax, eax
0x1800380f2  jz      short loc_18003812D
0x1800380f4  lea     rcx, [rbp+37h+arg_20]; this
0x1800380f8  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x1800380fd  nop
0x1800380fe  lea     rcx, [rbp+37h+var_60]; this
0x180038102  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x180038107  nop
0x180038108  lea     rcx, [rbp+37h+var_88]; this
0x18003810c  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x180038111  nop
0x180038112  lea     rcx, [rsp+120h+var_B8]
0x180038117  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003811c  nop
0x18003811d  lea     rcx, [rsp+120h+var_D0]
0x180038122  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180038127  nop
0x180038128  jmp     loc_18003808A
0x18003812d  lea     rax, [rbp+37h+arg_38]
0x180038131  mov     [rsp+120h+var_F0], rax; unsigned int *
0x180038136  lea     rax, [rbp+37h+var_B0]
0x18003813a  mov     [rsp+120h+var_F8], rax; unsigned __int8 **
0x18003813f  lea     rax, [rbp+37h+var_88]
0x180038143  mov     [rsp+120h+var_100], rax; struct CVaultKey *
0x180038148  lea     r9, [rbp+37h+var_60]; struct CVaultKey *
0x18003814c  mov     r8, [rsp+120h+var_C8]; struct IVaultKeyManager *
0x180038151  lea     rcx, [rbp+37h+arg_20]; this
0x180038155  call    ?SerializeAndProtectKeyMaterial@CVaultKeyStoreMgr@@QEAAKPEAVCUserVault@@PEAUIVaultKeyManager@@PEAVCVaultKey@@2PEAPEAEPEAK@Z; CVaultKeyStoreMgr::SerializeAndProtectKeyMaterial(CUserVault *,IVaultKeyManager *,CVaultKey *,CVaultKey *,uchar * *,ulong *)
0x18003815a  mov     ebx, eax
0x18003815c  test    eax, eax
0x18003815e  jz      short loc_180038199
0x180038160  lea     rcx, [rbp+37h+arg_20]; this
0x180038164  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x180038169  nop
0x18003816a  lea     rcx, [rbp+37h+var_60]; this
0x18003816e  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x180038173  nop
0x180038174  lea     rcx, [rbp+37h+var_88]; this
0x180038178  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18003817d  nop
0x18003817e  lea     rcx, [rsp+120h+var_B8]
0x180038183  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180038188  nop
0x180038189  lea     rcx, [rsp+120h+var_D0]
0x18003818e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180038193  nop
0x180038194  jmp     loc_18003808A
0x180038199  lea     rax, [rbp+37h+hMem]
0x18003819d  mov     [rsp+120h+var_D8], rax
0x1800381a2  mov     rax, [rbp+37h+arg_40]
0x1800381a9  mov     [rsp+120h+var_E0], rax
0x1800381ae  mov     eax, [rbp+37h+arg_30]
0x1800381b1  mov     [rsp+120h+var_E8], eax
0x1800381b5  mov     rax, [rbp+37h+arg_28]
0x1800381b9  mov     [rsp+120h+var_F0], rax
0x1800381be  mov     byte ptr [rsp+120h+var_F8], r14b
0x1800381c3  mov     [rsp+120h+var_100], r15
0x1800381c8  mov     r9d, [rbp+37h+arg_38]
0x1800381cc  mov     r8, [rbp+37h+var_B0]
0x1800381d0  mov     rdx, rsi
0x1800381d3  lea     rcx, ?g_VaultFactory@VaultGlobals@@3VCVaultFactory@@A; CVaultFactory VaultGlobals::g_VaultFactory
0x1800381da  call    ?CreateNewVault@CVaultFactory@@UEAAKPEBU_GUID@@PEAEKPEBGE2W4eVaultType@@PEAUVaultPolicy@@PEAPEAUIVaultStore@@@Z; CVaultFactory::CreateNewVault(_GUID const *,uchar *,ulong,ushort const *,uchar,ushort const *,eVaultType,VaultPolicy *,IVaultStore * *)
0x1800381df  mov     ebx, eax
0x1800381e1  test    eax, eax
0x1800381e3  jz      short loc_18003825E
0x1800381e5  lea     rcx, [rbp+37h+arg_20]; this
0x1800381e9  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x1800381ee  nop
0x1800381ef  lea     rcx, [rbp+37h+var_60]; this
0x1800381f3  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x1800381f8  nop
0x1800381f9  lea     rcx, [rbp+37h+var_88]; this
0x1800381fd  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x180038202  nop
0x180038203  lea     rcx, [rsp+120h+var_B8]
0x180038208  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003820d  nop
0x18003820e  mov     rcx, [rbp+37h+hMem]; hMem
0x180038212  test    rcx, rcx
0x180038215  jz      short loc_18003824E
0x180038217  mov     eax, [rbp+37h+var_90]
0x18003821a  test    eax, eax
0x18003821c  jz      short loc_180038238
0x18003821e  test    rcx, rcx
0x180038221  jz      short loc_180038238
0x180038223  mov     edx, eax
0x180038225  test    eax, eax
0x180038227  jz      short loc_180038238
0x180038229  mov     rax, rcx
0x18003822c  mov     [rax], r12b
0x18003822f  inc     rax
0x180038232  sub     rdx, 1
0x180038236  jnz     short loc_18003822C
0x180038238  mov     rax, [rbp+37h+var_A0]
0x18003823c  test    rax, rax
0x18003823f  jz      short loc_180038248
0x180038241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038246  jmp     short loc_18003824E
0x180038248  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18003824d  nop
0x18003824e  lea     rcx, [rsp+120h+var_D0]
0x180038253  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180038258  nop
0x180038259  jmp     loc_18003808A
0x18003825e  mov     rbx, [rbp+37h+hMem]
0x180038262  xor     r8d, r8d
0x180038265  mov     rdx, rbx
0x180038268  mov     rcx, rdi
0x18003826b  call    ?InstantiateUserVaultObject@CUserVault@@SAPEAV1@PEAVCUserVaultMgr@@PEAUIVaultStore@@W4efVaultFlags@@@Z; CUserVault::InstantiateUserVaultObject(CUserVaultMgr *,IVaultStore *,efVaultFlags)
0x180038270  mov     rdi, rax
0x180038273  test    rax, rax
0x180038276  jnz     short loc_1800382EC
0x180038278  lea     rcx, [rbp+37h+arg_20]; this
0x18003827c  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x180038281  nop
0x180038282  lea     rcx, [rbp+37h+var_60]; this
0x180038286  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18003828b  nop
0x18003828c  lea     rcx, [rbp+37h+var_88]; this
0x180038290  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x180038295  nop
0x180038296  lea     rcx, [rsp+120h+var_B8]
0x18003829b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800382a0  nop
0x1800382a1  test    rbx, rbx
0x1800382a4  jz      short loc_1800382D7
0x1800382a6  mov     eax, [rbp+37h+var_90]
0x1800382a9  cmp     rax, 1
0x1800382ad  jb      short loc_1800382BE
0x1800382af  mov     rcx, rbx
0x1800382b2  mov     [rcx], r12b
0x1800382b5  inc     rcx
0x1800382b8  sub     rax, 1
0x1800382bc  jnz     short loc_1800382B2
0x1800382be  mov     rax, [rbp+37h+var_A0]
0x1800382c2  mov     rcx, rbx; hMem
0x1800382c5  test    rax, rax
0x1800382c8  jz      short loc_1800382D1
0x1800382ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382cf  jmp     short loc_1800382D7
0x1800382d1  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x1800382d6  nop
0x1800382d7  lea     rcx, [rsp+120h+var_D0]
0x1800382dc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800382e1  nop
0x1800382e2  mov     eax, 0Eh
0x1800382e7  jmp     loc_180038377
0x1800382ec  mov     r9, [rsp+120h+var_C8]; struct IVaultKeyManager *
0x1800382f1  lea     r8, [rbp+37h+var_88]; struct CVaultKey *
0x1800382f5  lea     rdx, [rbp+37h+var_60]; struct CVaultKey *
0x1800382f9  mov     rcx, rdi; this
0x1800382fc  call    ?InitVaultKey@CUserVault@@QEAAKPEAVCVaultKey@@0PEAUIVaultKeyManager@@@Z; CUserVault::InitVaultKey(CVaultKey *,CVaultKey *,IVaultKeyManager *)
0x180038301  mov     rax, [rbp+37h+arg_50]
0x180038308  mov     [rax], rdi
0x18003830b  lea     rcx, [rbp+37h+arg_20]; this
0x18003830f  call    ??1CVaultKeyStoreMgr@@QEAA@XZ; CVaultKeyStoreMgr::~CVaultKeyStoreMgr(void)
0x180038314  nop
0x180038315  lea     rcx, [rbp+37h+var_60]; this
0x180038319  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x18003831e  nop
0x18003831f  lea     rcx, [rbp+37h+var_88]; this
0x180038323  call    ??1CVaultKey@@QEAA@XZ; CVaultKey::~CVaultKey(void)
0x180038328  nop
0x180038329  lea     rcx, [rsp+120h+var_B8]
0x18003832e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180038333  nop
0x180038334  test    rbx, rbx
0x180038337  jz      short loc_18003836A
0x180038339  mov     eax, [rbp+37h+var_90]
0x18003833c  cmp     rax, 1
0x180038340  jb      short loc_180038351
0x180038342  mov     rcx, rbx
0x180038345  mov     [rcx], r12b
0x180038348  inc     rcx
0x18003834b  sub     rax, 1
0x18003834f  jnz     short loc_180038345
0x180038351  mov     rax, [rbp+37h+var_A0]
0x180038355  mov     rcx, rbx; hMem
0x180038358  test    rax, rax
0x18003835b  jz      short loc_180038364
0x18003835d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038362  jmp     short loc_18003836A
0x180038364  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180038369  nop
0x18003836a  lea     rcx, [rsp+120h+var_D0]
0x18003836f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180038374  nop
0x180038375  xor     eax, eax
0x180038377  add     rsp, 0F0h
0x18003837e  pop     r15
0x180038380  pop     r14
  ... truncated ...
```
