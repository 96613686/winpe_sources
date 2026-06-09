# VaultCreateVaultSecurableFromPackageId(EVaultSecurableType,_GUID const &,_VAULT_VARIANT &,IVaultSecurable * *)

- ea: `0x180003ca4`
- end: `0x180003e54`
- name: `?VaultCreateVaultSecurableFromPackageId@@YAKW4EVaultSecurableType@@AEBU_GUID@@AEAU_VAULT_VARIANT@@PEAPEAVIVaultSecurable@@@Z`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003e60`

## callees

- `0x180003140`
- `0x180003810`
- `0x180003ca4`
- `0x180006610`
- `0x18002b3d0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003d69`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003d69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003dde`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall VaultCreateVaultSecurableFromPackageId(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        PSECURITY_DESCRIPTOR **a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  char *v8; // rax
  PSECURITY_DESCRIPTOR *v9; // rbx
  unsigned int SecurityDescriptor; // edi
  __int64 (__fastcall *v11)(__int64); // [rsp+20h] [rbp-50h] BYREF
  struct CVaultSid *v12; // [rsp+28h] [rbp-48h] BYREF
  int v13; // [rsp+30h] [rbp-40h]
  _BYTE pIdentifierAuthority[39]; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v15; // [rsp+60h] [rbp-10h]

  if ( *(_DWORD *)a3 != 8 )
    return 87;
  v12 = 0;
  v13 = 0;
  v11 = AutoDereference<IVaultKeyManager>;
  memset(pIdentifierAuthority, 0, sizeof(pIdentifierAuthority));
  v6 = 39;
  if ( *(_DWORD *)(a3 + 8) < 0x27u )
    v6 = *(_DWORD *)(a3 + 8);
  v15 = v6;
  memcpy_0(pIdentifierAuthority, *(const void **)(a3 + 16), v6);
  v7 = CVaultPackageId::ComposeSid((PSID_IDENTIFIER_AUTHORITY)pIdentifierAuthority, &v12);
  if ( v7 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v11);
    return v7;
  }
  *(_QWORD *)pIdentifierAuthority = CVaultRoamingCredential::FreeRoamingCredential;
  *(_QWORD *)&pIdentifierAuthority[8] = 0;
  *(_DWORD *)&pIdentifierAuthority[16] = 0;
  v8 = (char *)LocalAlloc(0x40u, 0x50u);
  v9 = (PSECURITY_DESCRIPTOR *)v8;
  if ( v8 )
  {
    *(_QWORD *)v8 = &CVaultSecurable::`vftable';
    *((_DWORD *)v8 + 2) = 3;
    *(_OWORD *)(v8 + 12) = xmmword_1800515B8;
    *((_QWORD *)v8 + 5) = 0;
    *((_DWORD *)v8 + 12) = 0;
    *((_QWORD *)v8 + 4) = LocalFree;
    *((_QWORD *)v8 + 8) = 0;
    *((_DWORD *)v8 + 18) = 0;
    *((_QWORD *)v8 + 7) = AutoDereference<IVaultKeyManager>;
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)pIdentifierAuthority);
    *(_QWORD *)&pIdentifierAuthority[8] = v9;
    SecurityDescriptor = CVaultSecurable::CreateSecurityDescriptor(v9, v12);
    if ( !SecurityDescriptor )
    {
      *a4 = v9;
      SecurityDescriptor = 0;
      goto LABEL_15;
    }
  }
  else
  {
    SecurityDescriptor = 14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
  }
  CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)pIdentifierAuthority);
LABEL_15:
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete((__int64)&v11);
  return SecurityDescriptor;
}

```

## disassembly

```asm
0x180003ca4  mov     [rsp-18h+arg_0], rbx
0x180003ca9  push    rbp
0x180003caa  push    rsi
0x180003cab  push    rdi
0x180003cac  mov     rbp, rsp
0x180003caf  sub     rsp, 70h
0x180003cb3  mov     rax, cs:__security_cookie
0x180003cba  xor     rax, rsp
0x180003cbd  mov     [rbp+var_8], rax
0x180003cc1  mov     rsi, r9
0x180003cc4  mov     r10, r8
0x180003cc7  cmp     dword ptr [r8], 8
0x180003ccb  jz      short loc_180003CD7
0x180003ccd  mov     eax, 57h ; 'W'
0x180003cd2  jmp     loc_180003E38
0x180003cd7  mov     [rbp+var_48], 0
0x180003cdf  mov     [rbp+var_40], 0
0x180003ce6  lea     rdi, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180003ced  mov     [rbp+var_50], rdi
0x180003cf1  xorps   xmm0, xmm0
0x180003cf4  xor     eax, eax
0x180003cf6  movups  [rbp+pIdentifierAuthority], xmm0
0x180003cfa  movups  xmmword ptr [rbp+var_28], xmm0
0x180003cfe  mov     qword ptr [rbp+var_28+0Fh], rax
0x180003d02  mov     eax, 27h ; '''
0x180003d07  cmp     [r8+8], eax
0x180003d0b  cmovb   eax, [r8+8]
0x180003d10  mov     [rbp+var_10], eax
0x180003d13  mov     r8d, eax; Size
0x180003d16  mov     rdx, [r10+10h]; Src
0x180003d1a  lea     rcx, [rbp+pIdentifierAuthority]; void *
0x180003d1e  call    memcpy_0
0x180003d23  lea     rdx, [rbp+var_48]; struct CVaultSid **
0x180003d27  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180003d2b  call    ?ComposeSid@CVaultPackageId@@QEAAKPEAPEAVCVaultSid@@@Z; CVaultPackageId::ComposeSid(CVaultSid * *)
0x180003d30  mov     ebx, eax
0x180003d32  test    eax, eax
0x180003d34  jz      short loc_180003D47
0x180003d36  lea     rcx, [rbp+var_50]
0x180003d3a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003d3f  nop
0x180003d40  mov     eax, ebx
0x180003d42  jmp     loc_180003E38
0x180003d47  lea     rax, ?FreeRoamingCredential@CVaultRoamingCredential@@SAXPEAV1@@Z; CVaultRoamingCredential::FreeRoamingCredential(CVaultRoamingCredential *)
0x180003d4e  mov     qword ptr [rbp+pIdentifierAuthority], rax
0x180003d52  mov     qword ptr [rbp+pIdentifierAuthority+8], 0
0x180003d5a  mov     dword ptr [rbp+var_28], 0
0x180003d61  mov     edx, 50h ; 'P'; uBytes
0x180003d66  lea     ecx, [rdx-10h]; uFlags
0x180003d69  call    cs:__imp_LocalAlloc
0x180003d6f  mov     rbx, rax
0x180003d72  test    rax, rax
0x180003d75  jnz     short loc_180003DB2
0x180003d77  lea     rax, WPP_GLOBAL_Control
0x180003d7e  lea     edi, [rbx+0Eh]
0x180003d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d88  cmp     rcx, rax
0x180003d8b  jz      short loc_180003DA6
0x180003d8d  test    byte ptr [rcx+1Ch], 2
0x180003d91  jz      short loc_180003DA6
0x180003d93  mov     edx, edi
0x180003d95  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x180003d9c  mov     rcx, [rcx+10h]
0x180003da0  call    WPP_SF_
0x180003da5  nop
0x180003da6  lea     rcx, [rbp+pIdentifierAuthority]
0x180003daa  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180003daf  nop
0x180003db0  jmp     short loc_180003E2C
0x180003db2  lea     rax, ??_7CVaultSecurable@@6B@; const CVaultSecurable::`vftable'
0x180003db9  mov     [rbx], rax
0x180003dbc  mov     dword ptr [rbx+8], 3
0x180003dc3  movups  xmm0, cs:xmmword_1800515B8
0x180003dca  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x180003dcf  mov     qword ptr [rbx+28h], 0
0x180003dd7  mov     dword ptr [rbx+30h], 0
0x180003dde  mov     rax, cs:__imp_LocalFree
0x180003de5  mov     [rbx+20h], rax
0x180003de9  mov     qword ptr [rbx+40h], 0
0x180003df1  mov     dword ptr [rbx+48h], 0
0x180003df8  mov     [rbx+38h], rdi
0x180003dfc  lea     rcx, [rbp+pIdentifierAuthority]
0x180003e00  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180003e05  mov     qword ptr [rbp+pIdentifierAuthority+8], rbx
0x180003e09  mov     rdx, [rbp+var_48]; struct CVaultSid *
0x180003e0d  mov     rcx, rbx; this
0x180003e10  call    ?CreateSecurityDescriptor@CVaultSecurable@@QEAAKPEAVCVaultSid@@@Z; CVaultSecurable::CreateSecurityDescriptor(CVaultSid *)
0x180003e15  mov     edi, eax
0x180003e17  test    eax, eax
0x180003e19  jz      short loc_180003E27
0x180003e1b  lea     rcx, [rbp+pIdentifierAuthority]
0x180003e1f  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180003e24  nop
0x180003e25  jmp     short loc_180003E2C
0x180003e27  mov     [rsi], rbx
0x180003e2a  xor     edi, edi
0x180003e2c  lea     rcx, [rbp+var_50]
0x180003e30  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180003e35  nop
0x180003e36  mov     eax, edi
0x180003e38  mov     rcx, [rbp+var_8]
0x180003e3c  xor     rcx, rsp; StackCookie
0x180003e3f  call    __security_check_cookie
0x180003e44  mov     rbx, [rsp+70h+arg_0]
0x180003e4c  add     rsp, 70h
0x180003e50  pop     rdi
0x180003e51  pop     rsi
0x180003e52  pop     rbp
0x180003e53  retn
```
