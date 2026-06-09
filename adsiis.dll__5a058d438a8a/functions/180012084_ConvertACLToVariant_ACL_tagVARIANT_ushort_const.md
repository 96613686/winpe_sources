# ConvertACLToVariant(_ACL *,tagVARIANT *,ushort const *)

- ea: `0x180012084`
- end: `0x18001222f`
- name: `?ConvertACLToVariant@@YAJPEAU_ACL@@PEAUtagVARIANT@@PEBG@Z`
- size: `427`
- prototype: `__int64 __fastcall(PACL pAcl, VARIANTARG *pvarg, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180012574`

## callees

- `0x180012084`
- `0x180012238`
- `0x18001d6c0`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180012138`
- `ole32!CoCreateInstance` at `0x180012138`
- `ADVAPI32!GetAce` at `0x18001215a`
- `ADVAPI32!GetAce` at `0x18001215a`
- `ADVAPI32!GetAclInformation` at `0x1800120ec`
- `ADVAPI32!GetAclInformation` at `0x180012105`
- `ADVAPI32!GetAclInformation` at `0x1800120ec`
- `ADVAPI32!GetAclInformation` at `0x180012105`
- `OLEAUT32!__imp_VariantInit` at `0x180012116`
- `OLEAUT32!__imp_VariantInit` at `0x180012116`
- `OLEAUT32!__imp_VariantClear` at `0x180012192`
- `OLEAUT32!__imp_VariantClear` at `0x180012192`

## pseudocode

```c
__int64 __fastcall ConvertACLToVariant(PACL pAcl, VARIANTARG *pvarg, const unsigned __int16 *a3)
{
  DWORD v6; // r14d
  unsigned int v7; // r13d
  HRESULT v8; // ebx
  unsigned int v9; // ebx
  DWORD i; // esi
  int v11; // eax
  unsigned int v12; // ecx
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v15; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-40h] BYREF
  LONGLONG v17; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG pvarga; // [rsp+50h] [rbp-30h] BYREF
  __int64 pAclInformation; // [rsp+68h] [rbp-18h] BYREF
  int v20; // [rsp+70h] [rbp-10h]

  ppv = 0;
  v17 = 0;
  pAce = 0;
  pAclInformation = 0;
  v20 = 0;
  v15 = 0;
  memset(&pvarga, 0, sizeof(pvarga));
  GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation);
  GetAclInformation(pAcl, &v15, 4u, AclRevisionInformation);
  v6 = pAclInformation;
  v7 = v15;
  VariantInit(pvarg);
  v8 = CoCreateInstance(&CLSID_AccessControlList, 0, 1u, &IID_IADsAccessControlList, &ppv);
  if ( v8 >= 0 )
  {
    v9 = 0;
    for ( i = 0; i < v6; ++i )
    {
      GetAce(pAcl, i, &pAce);
      ConvertAceToVariant((unsigned __int8 *)pAce, &pvarga, a3);
      v11 = (*(__int64 (__fastcall **)(LPVOID, LONGLONG))(*(_QWORD *)ppv + 88LL))(ppv, pvarga.llVal);
      v12 = v9 + 1;
      if ( v11 < 0 )
        v12 = v9;
      v9 = v12;
      VariantClear(&pvarga);
    }
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, v7);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 80LL))(ppv, v9);
    v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, LONGLONG *))ppv)(ppv, &IID_IDispatch, &v17);
    if ( v8 >= 0 )
    {
      pvarg->llVal = v17;
      pvarg->vt = 9;
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012084  mov     [rsp-38h+arg_18], rbx
0x180012089  push    rbp
0x18001208a  push    rsi
0x18001208b  push    rdi
0x18001208c  push    r12
0x18001208e  push    r13
0x180012090  push    r14
0x180012092  push    r15
0x180012094  mov     rbp, rsp
0x180012097  sub     rsp, 80h
0x18001209e  mov     rax, cs:__security_cookie
0x1800120a5  xor     rax, rsp
0x1800120a8  mov     [rbp+var_8], rax
0x1800120ac  xor     eax, eax
0x1800120ae  mov     [rbp+var_50], 0
0x1800120b6  mov     r12, r8
0x1800120b9  mov     [rbp+var_38], 0
0x1800120c1  mov     rdi, rdx
0x1800120c4  mov     qword ptr [rbp+pvarg+10h], rax
0x1800120c8  xorps   xmm0, xmm0
0x1800120cb  mov     [rbp+pAce], rax
0x1800120cf  lea     r9d, [rax+2]; dwAclInformationClass
0x1800120d3  mov     [rbp+pAclInformation], rax
0x1800120d7  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1800120db  mov     [rbp+var_10], eax
0x1800120de  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x1800120e2  mov     [rbp+var_48], eax
0x1800120e5  mov     r15, rcx
0x1800120e8  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800120ec  call    cs:__imp_GetAclInformation
0x1800120f2  mov     ebx, 1
0x1800120f7  lea     rdx, [rbp+var_48]; pAclInformation
0x1800120fb  mov     r9d, ebx; dwAclInformationClass
0x1800120fe  mov     rcx, r15; pAcl
0x180012101  lea     r8d, [rbx+3]; nAclInformationLength
0x180012105  call    cs:__imp_GetAclInformation
0x18001210b  mov     r14d, dword ptr [rbp+pAclInformation]
0x18001210f  mov     rcx, rdi; pvarg
0x180012112  mov     r13d, [rbp+var_48]
0x180012116  call    cs:__imp_VariantInit
0x18001211c  lea     rax, [rbp+var_50]
0x180012120  mov     r8d, ebx; dwClsContext
0x180012123  lea     r9, IID_IADsAccessControlList; riid
0x18001212a  mov     [rsp+80h+ppv], rax; ppv
0x18001212f  xor     edx, edx; pUnkOuter
0x180012131  lea     rcx, CLSID_AccessControlList; rclsid
0x180012138  call    cs:__imp_CoCreateInstance
0x18001213e  mov     ebx, eax
0x180012140  test    eax, eax
0x180012142  js      loc_1800121F1
0x180012148  xor     ebx, ebx
0x18001214a  xor     esi, esi
0x18001214c  test    r14d, r14d
0x18001214f  jz      short loc_18001219F
0x180012151  lea     r8, [rbp+pAce]; pAce
0x180012155  mov     edx, esi; dwAceIndex
0x180012157  mov     rcx, r15; pAcl
0x18001215a  call    cs:__imp_GetAce
0x180012160  mov     rcx, [rbp+pAce]; unsigned __int8 *
0x180012164  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x180012168  mov     r8, r12; unsigned __int16 *
0x18001216b  call    ?ConvertAceToVariant@@YAJPEAEPEAUtagVARIANT@@PEBG@Z; ConvertAceToVariant(uchar *,tagVARIANT *,ushort const *)
0x180012170  mov     rcx, [rbp+var_50]
0x180012174  mov     rdx, qword ptr [rbp+pvarg+8]
0x180012178  mov     rax, [rcx]
0x18001217b  mov     rax, [rax+58h]
0x18001217f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012184  lea     ecx, [rbx+1]
0x180012187  test    eax, eax
0x180012189  cmovs   ecx, ebx
0x18001218c  mov     ebx, ecx
0x18001218e  lea     rcx, [rbp+pvarg]; pvarg
0x180012192  call    cs:__imp_VariantClear
0x180012198  inc     esi
0x18001219a  cmp     esi, r14d
0x18001219d  jb      short loc_180012151
0x18001219f  mov     rcx, [rbp+var_50]
0x1800121a3  mov     edx, r13d
0x1800121a6  mov     rax, [rcx]
0x1800121a9  mov     rax, [rax+40h]
0x1800121ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121b2  mov     rcx, [rbp+var_50]
0x1800121b6  mov     edx, ebx
0x1800121b8  mov     rax, [rcx]
0x1800121bb  mov     rax, [rax+50h]
0x1800121bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121c4  mov     rcx, [rbp+var_50]
0x1800121c8  lea     r8, [rbp+var_38]
0x1800121cc  lea     rdx, IID_IDispatch
0x1800121d3  mov     rax, [rcx]
0x1800121d6  mov     rax, [rax]
0x1800121d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121de  mov     ebx, eax
0x1800121e0  test    eax, eax
0x1800121e2  js      short loc_1800121F1
0x1800121e4  mov     rax, [rbp+var_38]
0x1800121e8  mov     [rdi+8], rax
0x1800121ec  mov     word ptr [rdi], 9
0x1800121f1  mov     rcx, [rbp+var_50]
0x1800121f5  test    rcx, rcx
0x1800121f8  jz      short loc_180012206
0x1800121fa  mov     rax, [rcx]
0x1800121fd  mov     rax, [rax+10h]
0x180012201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012206  mov     eax, ebx
0x180012208  mov     rcx, [rbp+var_8]
0x18001220c  xor     rcx, rsp; StackCookie
0x18001220f  call    __security_check_cookie
0x180012214  mov     rbx, [rsp+80h+arg_18]
0x18001221c  add     rsp, 80h
0x180012223  pop     r15
0x180012225  pop     r14
0x180012227  pop     r13
0x180012229  pop     r12
0x18001222b  pop     rdi
0x18001222c  pop     rsi
0x18001222d  pop     rbp
0x18001222e  retn
```
