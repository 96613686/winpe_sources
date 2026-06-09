# PopulateCallerAccountInfo(void *,IVaultCredential *,ushort *,ulong)

- ea: `0x18002d724`
- end: `0x18002dd06`
- name: `?PopulateCallerAccountInfo@@YAKPEAXPEAUIVaultCredential@@PEAGK@Z`
- size: `1506`
- prototype: `__int64 __fastcall(HANDLE token, struct IVaultCredential *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016250`
- `0x1800358a0`

## callees

- `0x180003140`
- `0x18000eb30`
- `0x180011110`
- `0x18002d724`
- `0x18002dd0c`
- `0x18003a580`
- `0x18004d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002d9d5`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002d9d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d7ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002da59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dae4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002db33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d7ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002da59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002dae4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002db33`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002d7ac`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002d7ea`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002d7ac`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18002d7ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PopulateCallerAccountInfo(HANDLE token, struct IVaultCredential *a2, unsigned __int16 *a3)
{
  ULONG PackageFamilyNameFromToken; // ebx
  WCHAR *v7; // rax
  Appx *v8; // rsi
  ULONG PackageAcquisitionInfoByFamilyName; // eax
  const unsigned __int16 *v11; // r14
  unsigned __int64 *v12; // r15
  unsigned __int64 *v13; // rax
  unsigned __int64 *v14; // r12
  ULONG v15; // eax
  struct _GUID *ThreadInformation; // [rsp+40h] [rbp-79h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+48h] [rbp-71h] BYREF
  __int64 v18; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 *v19; // [rsp+58h] [rbp-61h]
  int v20; // [rsp+60h] [rbp-59h]
  __int64 v21; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int64 *v22; // [rsp+70h] [rbp-49h]
  int v23; // [rsp+78h] [rbp-41h]
  __int64 v24; // [rsp+80h] [rbp-39h] BYREF
  const unsigned __int16 *v25; // [rsp+88h] [rbp-31h]
  int v26; // [rsp+90h] [rbp-29h]
  __int64 v27; // [rsp+98h] [rbp-21h] BYREF
  WCHAR *v28; // [rsp+A0h] [rbp-19h]
  int v29; // [rsp+A8h] [rbp-11h]
  unsigned __int16 v30[4]; // [rsp+B0h] [rbp-9h] BYREF
  unsigned __int16 v31[4]; // [rsp+B8h] [rbp-1h] BYREF
  unsigned __int16 v32[4]; // [rsp+C0h] [rbp+7h] BYREF
  unsigned __int64 v33[2]; // [rsp+C8h] [rbp+Fh] BYREF

  packageFamilyNameLength = 0;
  *(_QWORD *)v32 = 0;
  *(_QWORD *)v31 = 0;
  *(_QWORD *)v30 = 0;
  v28 = 0;
  v29 = 0;
  v27 = 0;
  v25 = 0;
  v26 = 0;
  v24 = 0;
  v22 = 0;
  v23 = 0;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v18 = 0;
  ThreadInformation = 0;
  *(_OWORD *)v33 = 0;
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(token, &packageFamilyNameLength, 0);
  if ( PackageFamilyNameFromToken != 122 )
  {
    if ( !PackageFamilyNameFromToken )
      PackageFamilyNameFromToken = 1359;
    goto LABEL_12;
  }
  v7 = (WCHAR *)LocalAlloc(0x40u, 2LL * packageFamilyNameLength);
  v8 = (Appx *)v7;
  v28 = v7;
  if ( !v7 )
  {
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    return 122;
  }
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(token, &packageFamilyNameLength, v7);
  if ( PackageFamilyNameFromToken )
    goto LABEL_12;
  if ( a3 )
    _o_wcsncpy_s(a3, 256, v8, -1);
  if ( !a2 )
  {
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    return 0;
  }
  PackageFamilyNameFromToken = CVaultIntegrityLevel::Elevate((CVaultIntegrityLevel *)&ThreadInformation);
  if ( PackageFamilyNameFromToken )
  {
LABEL_12:
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    return PackageFamilyNameFromToken;
  }
  PackageAcquisitionInfoByFamilyName = Appx::GetPackageAcquisitionInfoByFamilyName(
                                         v8,
                                         0,
                                         v32,
                                         0,
                                         v31,
                                         0,
                                         v30,
                                         v33,
                                         ThreadInformation);
  PackageFamilyNameFromToken = PackageAcquisitionInfoByFamilyName;
  if ( PackageAcquisitionInfoByFamilyName )
  {
    if ( PackageAcquisitionInfoByFamilyName != -2147024774 )
    {
      if ( (PackageAcquisitionInfoByFamilyName & 0x1FFF0000) == 0x70000 )
        PackageFamilyNameFromToken = (unsigned __int16)PackageAcquisitionInfoByFamilyName;
      goto LABEL_12;
    }
    v11 = (const unsigned __int16 *)LocalAlloc(0x40u, 2LL * *(unsigned int *)v32);
    v25 = v11;
    if ( v11 )
    {
      v12 = (unsigned __int64 *)LocalAlloc(0x40u, 2LL * *(unsigned int *)v31);
      v22 = v12;
      if ( v12 )
      {
        v13 = (unsigned __int64 *)LocalAlloc(0x40u, 2LL * *(unsigned int *)v30);
        v14 = v13;
        v19 = v13;
        if ( v13 )
        {
          v15 = Appx::GetPackageAcquisitionInfoByFamilyName(v8, v11, v32, v12, v31, v13, v30, v33, ThreadInformation);
          PackageFamilyNameFromToken = v15;
          if ( v15 )
          {
            if ( (v15 & 0x1FFF0000) == 0x70000 )
              PackageFamilyNameFromToken = (unsigned __int16)v15;
          }
          else
          {
            PackageFamilyNameFromToken = (*(__int64 (__fastcall **)(struct IVaultCredential *, const unsigned __int16 *))(*(_QWORD *)a2 + 288LL))(
                                           a2,
                                           v11);
            if ( !PackageFamilyNameFromToken )
            {
              PackageFamilyNameFromToken = (*(__int64 (__fastcall **)(struct IVaultCredential *, unsigned __int64 *))(*(_QWORD *)a2 + 296LL))(
                                             a2,
                                             v12);
              if ( !PackageFamilyNameFromToken )
              {
                PackageFamilyNameFromToken = (*(__int64 (__fastcall **)(struct IVaultCredential *, unsigned __int64 *))(*(_QWORD *)a2 + 304LL))(
                                               a2,
                                               v14);
                if ( !PackageFamilyNameFromToken )
                  PackageFamilyNameFromToken = (*(__int64 (__fastcall **)(struct IVaultCredential *, unsigned __int64 *))(*(_QWORD *)a2 + 312LL))(
                                                 a2,
                                                 v33);
              }
            }
          }
          goto LABEL_12;
        }
      }
    }
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    return 14;
  }
  else
  {
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v21);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v27);
    return 1359;
  }
}

```

## disassembly

```asm
0x18002d724  mov     [rsp-8+arg_18], rbx
0x18002d729  push    rbp
0x18002d72a  push    rsi
0x18002d72b  push    rdi
0x18002d72c  push    r12
0x18002d72e  push    r13
0x18002d730  push    r14
0x18002d732  push    r15
0x18002d734  lea     rbp, [rsp-27h]
0x18002d739  sub     rsp, 0E0h
0x18002d740  mov     rax, cs:__security_cookie
0x18002d747  xor     rax, rsp
0x18002d74a  mov     [rbp+57h+var_38], rax
0x18002d74e  mov     r14, r8
0x18002d751  mov     rdi, rdx
0x18002d754  mov     r15, rcx
0x18002d757  xor     r13d, r13d
0x18002d75a  mov     [rbp+57h+packageFamilyNameLength], r13d
0x18002d75e  mov     qword ptr [rbp+57h+var_50], r13
0x18002d762  mov     qword ptr [rbp+57h+var_58], r13
0x18002d766  mov     qword ptr [rbp+57h+var_60], r13
0x18002d76a  mov     [rbp+57h+var_70], r13
0x18002d76e  mov     [rbp+57h+var_68], r13d
0x18002d772  mov     [rbp+57h+var_78], r13
0x18002d776  mov     [rbp+57h+var_88], r13
0x18002d77a  mov     [rbp+57h+var_80], r13d
0x18002d77e  mov     [rbp+57h+var_90], r13
0x18002d782  mov     [rbp+57h+var_A0], r13
0x18002d786  mov     [rbp+57h+var_98], r13d
0x18002d78a  mov     [rbp+57h+var_A8], r13
0x18002d78e  mov     [rbp+57h+var_B8], r13
0x18002d792  mov     [rbp+57h+var_B0], r13d
0x18002d796  mov     [rbp+57h+var_C0], r13
0x18002d79a  mov     [rbp+57h+ThreadInformation], r13
0x18002d79e  xorps   xmm0, xmm0
0x18002d7a1  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18002d7a5  xor     r8d, r8d; packageFamilyName
0x18002d7a8  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18002d7ac  call    cs:__imp_GetPackageFamilyNameFromToken
0x18002d7b2  mov     ebx, eax
0x18002d7b4  cmp     eax, 7Ah ; 'z'
0x18002d7b7  jnz     loc_18002D8CF
0x18002d7bd  mov     edx, [rbp+57h+packageFamilyNameLength]
0x18002d7c0  add     rdx, rdx; uBytes
0x18002d7c3  lea     r12d, [r13+40h]
0x18002d7c7  mov     ecx, r12d; uFlags
0x18002d7ca  call    cs:__imp_LocalAlloc
0x18002d7d0  mov     rsi, rax
0x18002d7d3  mov     [rbp+57h+var_70], rax
0x18002d7d7  test    rax, rax
0x18002d7da  jz      loc_18002D953
0x18002d7e0  mov     r8, rax; packageFamilyName
0x18002d7e3  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18002d7e7  mov     rcx, r15; token
0x18002d7ea  call    cs:__imp_GetPackageFamilyNameFromToken
0x18002d7f0  mov     ebx, eax
0x18002d7f2  test    eax, eax
0x18002d7f4  jnz     loc_18002D98F
0x18002d7fa  test    r14, r14
0x18002d7fd  jnz     loc_18002D9C6
0x18002d803  test    rdi, rdi
0x18002d806  jz      loc_18002D9E0
0x18002d80c  lea     rcx, [rbp+57h+ThreadInformation]; this
0x18002d810  call    ?Elevate@CVaultIntegrityLevel@@QEAAKXZ; CVaultIntegrityLevel::Elevate(void)
0x18002d815  mov     ebx, eax
0x18002d817  test    eax, eax
0x18002d819  jnz     loc_18002DA19
0x18002d81f  lea     rax, [rbp+57h+var_48]
0x18002d823  mov     [rsp+110h+var_D8], rax; unsigned __int64 *
0x18002d828  lea     rax, [rbp+57h+var_60]
0x18002d82c  mov     [rsp+110h+var_E0], rax; unsigned __int16 *
0x18002d831  mov     [rsp+110h+var_E8], r13; unsigned __int64 *
0x18002d836  lea     rax, [rbp+57h+var_58]
0x18002d83a  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x18002d83f  xor     r9d, r9d; unsigned __int64 *
0x18002d842  lea     r8, [rbp+57h+var_50]; unsigned __int16 *
0x18002d846  xor     edx, edx; unsigned __int16 *
0x18002d848  mov     rcx, rsi; this
0x18002d84b  call    ?GetPackageAcquisitionInfoByFamilyName@Appx@@YAJPEBGPEAGPEA_K1212PEAU_GUID@@@Z; Appx::GetPackageAcquisitionInfoByFamilyName(ushort const *,ushort *,unsigned __int64 *,ushort *,unsigned __int64 *,ushort *,unsigned __int64 *,_GUID *)
0x18002d850  mov     ebx, eax
0x18002d852  test    eax, eax
0x18002d854  jz      loc_18002DCCA
0x18002d85a  cmp     eax, 8007007Ah
0x18002d85f  jz      loc_18002DA50
0x18002d865  and     eax, 1FFF0000h
0x18002d86a  cmp     eax, 70000h
0x18002d86f  jnz     short loc_18002D874
0x18002d871  movzx   ebx, bx
0x18002d874  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002d878  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002d87d  nop
0x18002d87e  lea     rcx, [rbp+57h+var_C0]
0x18002d882  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d887  nop
0x18002d888  lea     rcx, [rbp+57h+var_A8]
0x18002d88c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d891  nop
0x18002d892  lea     rcx, [rbp+57h+var_90]
0x18002d896  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d89b  nop
0x18002d89c  lea     rcx, [rbp+57h+var_78]
0x18002d8a0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d8a5  nop
0x18002d8a6  mov     eax, ebx
0x18002d8a8  mov     rcx, [rbp+57h+var_38]
0x18002d8ac  xor     rcx, rsp; StackCookie
0x18002d8af  call    __security_check_cookie
0x18002d8b4  mov     rbx, [rsp+110h+arg_18]
0x18002d8bc  add     rsp, 0E0h
0x18002d8c3  pop     r15
0x18002d8c5  pop     r14
0x18002d8c7  pop     r13
0x18002d8c9  pop     r12
0x18002d8cb  pop     rdi
0x18002d8cc  pop     rsi
0x18002d8cd  pop     rbp
0x18002d8ce  retn
0x18002d8cf  mov     eax, 54Fh
0x18002d8d4  test    ebx, ebx
0x18002d8d6  cmovz   ebx, eax
0x18002d8d9  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002d8dd  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002d8e2  nop
0x18002d8e3  lea     rcx, [rbp+57h+var_C0]
0x18002d8e7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d8ec  nop
0x18002d8ed  lea     rcx, [rbp+57h+var_A8]
0x18002d8f1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d8f6  nop
0x18002d8f7  lea     rcx, [rbp+57h+var_90]
0x18002d8fb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d900  nop
0x18002d901  lea     rcx, [rbp+57h+var_78]
0x18002d905  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d90a  nop
0x18002d90b  jmp     short loc_18002D8A6
0x18002d90d  and     eax, 1FFF0000h
0x18002d912  cmp     eax, 70000h
0x18002d917  jnz     short loc_18002D91C
0x18002d919  movzx   ebx, bx
0x18002d91c  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002d920  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002d925  nop
0x18002d926  lea     rcx, [rbp+57h+var_C0]
0x18002d92a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d92f  nop
0x18002d930  lea     rcx, [rbp+57h+var_A8]
0x18002d934  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d939  nop
0x18002d93a  lea     rcx, [rbp+57h+var_90]
0x18002d93e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d943  nop
0x18002d944  lea     rcx, [rbp+57h+var_78]
0x18002d948  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d94d  nop
0x18002d94e  jmp     loc_18002D8A6
0x18002d953  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002d957  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002d95c  nop
0x18002d95d  lea     rcx, [rbp+57h+var_C0]
0x18002d961  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d966  nop
0x18002d967  lea     rcx, [rbp+57h+var_A8]
0x18002d96b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d970  nop
0x18002d971  lea     rcx, [rbp+57h+var_90]
0x18002d975  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d97a  nop
0x18002d97b  lea     rcx, [rbp+57h+var_78]
0x18002d97f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d984  nop
0x18002d985  mov     eax, 7Ah ; 'z'
0x18002d98a  jmp     loc_18002D8A8
0x18002d98f  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002d993  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002d998  nop
0x18002d999  lea     rcx, [rbp+57h+var_C0]
0x18002d99d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d9a2  nop
0x18002d9a3  lea     rcx, [rbp+57h+var_A8]
0x18002d9a7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d9ac  nop
0x18002d9ad  lea     rcx, [rbp+57h+var_90]
0x18002d9b1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d9b6  nop
0x18002d9b7  lea     rcx, [rbp+57h+var_78]
0x18002d9bb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d9c0  nop
0x18002d9c1  jmp     loc_18002D8A6
0x18002d9c6  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002d9ca  mov     r8, rsi
0x18002d9cd  mov     edx, 100h
0x18002d9d2  mov     rcx, r14
0x18002d9d5  call    cs:__imp__o_wcsncpy_s
0x18002d9db  jmp     loc_18002D803
0x18002d9e0  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002d9e4  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002d9e9  nop
0x18002d9ea  lea     rcx, [rbp+57h+var_C0]
0x18002d9ee  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d9f3  nop
0x18002d9f4  lea     rcx, [rbp+57h+var_A8]
0x18002d9f8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002d9fd  nop
0x18002d9fe  lea     rcx, [rbp+57h+var_90]
0x18002da02  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da07  nop
0x18002da08  lea     rcx, [rbp+57h+var_78]
0x18002da0c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da11  nop
0x18002da12  xor     eax, eax
0x18002da14  jmp     loc_18002D8A8
0x18002da19  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002da1d  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002da22  nop
0x18002da23  lea     rcx, [rbp+57h+var_C0]
0x18002da27  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da2c  nop
0x18002da2d  lea     rcx, [rbp+57h+var_A8]
0x18002da31  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da36  nop
0x18002da37  lea     rcx, [rbp+57h+var_90]
0x18002da3b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da40  nop
0x18002da41  lea     rcx, [rbp+57h+var_78]
0x18002da45  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da4a  nop
0x18002da4b  jmp     loc_18002D8A6
0x18002da50  mov     edx, dword ptr [rbp+57h+var_50]
0x18002da53  add     rdx, rdx; uBytes
0x18002da56  mov     ecx, r12d; uFlags
0x18002da59  call    cs:__imp_LocalAlloc
0x18002da5f  mov     r14, rax
0x18002da62  mov     [rbp+57h+var_88], rax
0x18002da66  test    rax, rax
0x18002da69  jnz     short loc_18002DADB
0x18002da6b  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002da6f  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002da74  nop
0x18002da75  lea     rcx, [rbp+57h+var_C0]
0x18002da79  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da7e  nop
0x18002da7f  lea     rcx, [rbp+57h+var_A8]
0x18002da83  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da88  nop
0x18002da89  lea     rcx, [rbp+57h+var_90]
0x18002da8d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da92  nop
0x18002da93  lea     rcx, [rbp+57h+var_78]
0x18002da97  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002da9c  nop
0x18002da9d  jmp     short loc_18002DAD1
0x18002da9f  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002daa3  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002daa8  nop
0x18002daa9  lea     rcx, [rbp+57h+var_C0]
0x18002daad  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002dab2  nop
0x18002dab3  lea     rcx, [rbp+57h+var_A8]
0x18002dab7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002dabc  nop
0x18002dabd  lea     rcx, [rbp+57h+var_90]
0x18002dac1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002dac6  nop
0x18002dac7  lea     rcx, [rbp+57h+var_78]
0x18002dacb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002dad0  nop
0x18002dad1  mov     eax, 0Eh
0x18002dad6  jmp     loc_18002D8A8
0x18002dadb  mov     edx, dword ptr [rbp+57h+var_58]
0x18002dade  add     rdx, rdx; uBytes
0x18002dae1  mov     ecx, r12d; uFlags
0x18002dae4  call    cs:__imp_LocalAlloc
0x18002daea  mov     r15, rax
0x18002daed  mov     [rbp+57h+var_A0], rax
0x18002daf1  test    rax, rax
0x18002daf4  jnz     short loc_18002DB2A
0x18002daf6  lea     rcx, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002dafa  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x18002daff  nop
0x18002db00  lea     rcx, [rbp+57h+var_C0]
0x18002db04  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002db09  nop
0x18002db0a  lea     rcx, [rbp+57h+var_A8]
0x18002db0e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002db13  nop
0x18002db14  lea     rcx, [rbp+57h+var_90]
0x18002db18  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002db1d  nop
0x18002db1e  lea     rcx, [rbp+57h+var_78]
0x18002db22  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18002db27  nop
0x18002db28  jmp     short loc_18002DAD1
0x18002db2a  mov     edx, dword ptr [rbp+57h+var_60]
0x18002db2d  add     rdx, rdx; uBytes
0x18002db30  mov     ecx, r12d; uFlags
0x18002db33  call    cs:__imp_LocalAlloc
0x18002db39  mov     r12, rax
0x18002db3c  mov     [rbp+57h+var_B8], rax
0x18002db40  test    rax, rax
  ... truncated ...
```
