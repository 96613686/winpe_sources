# VaultCreateVaultSecurable(EVaultSecurableType,_GUID const &,CVaultSid *,IVaultSecurable * *)

- ea: `0x18001a640`
- end: `0x18001a757`
- name: `?VaultCreateVaultSecurable@@YAKW4EVaultSecurableType@@AEBU_GUID@@PEAVCVaultSid@@PEAPEAVIVaultSecurable@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001a134`
- `0x18001b9c0`
- `0x18001bdb4`
- `0x180041524`
- `0x1800493d4`

## callees

- `0x180003810`
- `0x180006610`
- `0x18001a640`
- `0x180030320`
- `0x18003b7b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a67c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a67c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a6f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VaultCreateVaultSecurable(int a1, _OWORD *a2, struct CVaultSid *a3, _QWORD *a4)
{
  char *v8; // rax
  void *v9; // rbx
  unsigned int SecurityDescriptor; // edi
  void (__fastcall *v12)(HLOCAL); // [rsp+20h] [rbp-58h] BYREF
  char *v13; // [rsp+28h] [rbp-50h]
  int v14; // [rsp+30h] [rbp-48h]

  v12 = CVaultRoamingCredential::FreeRoamingCredential;
  v13 = 0;
  v14 = 0;
  v8 = (char *)LocalAlloc(0x40u, 0x50u);
  v9 = v8;
  if ( v8 )
  {
    *(_QWORD *)v8 = &CVaultSecurable::`vftable';
    *((_DWORD *)v8 + 2) = a1;
    *(_OWORD *)(v8 + 12) = *a2;
    *((_QWORD *)v8 + 5) = 0;
    *((_DWORD *)v8 + 12) = 0;
    *((_QWORD *)v8 + 4) = LocalFree;
    *((_QWORD *)v8 + 8) = 0;
    *((_DWORD *)v8 + 18) = 0;
    *((_QWORD *)v8 + 7) = AutoDereference<IVaultKeyManager>;
    v14 = 0;
    v13 = v8;
    SecurityDescriptor = CVaultSecurable::CreateSecurityDescriptor((PSECURITY_DESCRIPTOR *)v8, a3);
    if ( SecurityDescriptor )
    {
      CVaultRoamingCredential::FreeRoamingCredential(v9);
      return SecurityDescriptor;
    }
    else
    {
      *a4 = v9;
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete((__int64)&v12);
    return 14;
  }
}

```

## disassembly

```asm
0x18001a640  push    rbx
0x18001a642  push    rbp
0x18001a643  push    rsi
0x18001a644  push    rdi
0x18001a645  push    r14
0x18001a647  push    r15
0x18001a649  sub     rsp, 48h
0x18001a64d  mov     rsi, r9
0x18001a650  mov     rdi, r8
0x18001a653  mov     rbp, rdx
0x18001a656  mov     r14d, ecx
0x18001a659  lea     rax, ?FreeRoamingCredential@CVaultRoamingCredential@@SAXPEAV1@@Z; CVaultRoamingCredential::FreeRoamingCredential(CVaultRoamingCredential *)
0x18001a660  mov     [rsp+78h+var_58], rax
0x18001a665  xor     r15d, r15d
0x18001a668  mov     [rsp+78h+var_50], r15
0x18001a66d  mov     [rsp+78h+var_48], r15d
0x18001a672  mov     edx, 50h ; 'P'; uBytes
0x18001a677  mov     ecx, 40h ; '@'; uFlags
0x18001a67c  call    cs:__imp_LocalAlloc
0x18001a682  mov     rbx, rax
0x18001a685  test    rax, rax
0x18001a688  jnz     short loc_18001A6D6
0x18001a68a  lea     rax, WPP_GLOBAL_Control
0x18001a691  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a698  cmp     rcx, rax
0x18001a69b  jz      short loc_18001A6B9
0x18001a69d  test    byte ptr [rcx+1Ch], 2
0x18001a6a1  jz      short loc_18001A6B9
0x18001a6a3  mov     edx, 0Eh
0x18001a6a8  lea     r8, WPP_653e4a66d85f3580d6303a4ded660c7b_Traceguids
0x18001a6af  mov     rcx, [rcx+10h]
0x18001a6b3  call    WPP_SF_
0x18001a6b8  nop
0x18001a6b9  lea     rcx, [rsp+78h+var_58]
0x18001a6be  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x18001a6c3  nop
0x18001a6c4  mov     eax, 0Eh
0x18001a6c9  add     rsp, 48h
0x18001a6cd  pop     r15
0x18001a6cf  pop     r14
0x18001a6d1  pop     rdi
0x18001a6d2  pop     rsi
0x18001a6d3  pop     rbp
0x18001a6d4  pop     rbx
0x18001a6d5  retn
0x18001a6d6  lea     rax, ??_7CVaultSecurable@@6B@; const CVaultSecurable::`vftable'
0x18001a6dd  mov     [rbx], rax
0x18001a6e0  mov     [rbx+8], r14d
0x18001a6e4  movups  xmm0, xmmword ptr [rbp+0]
0x18001a6e8  movups  xmmword ptr [rbx+0Ch], xmm0
0x18001a6ec  mov     [rbx+28h], r15
0x18001a6f0  mov     [rbx+30h], r15d
0x18001a6f4  mov     rax, cs:__imp_LocalFree
0x18001a6fb  mov     [rbx+20h], rax
0x18001a6ff  mov     [rbx+40h], r15
0x18001a703  mov     [rbx+48h], r15d
0x18001a707  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18001a70e  mov     [rbx+38h], rax
0x18001a712  mov     [rsp+78h+var_48], r15d
0x18001a717  mov     [rsp+78h+var_50], rbx
0x18001a71c  mov     rdx, rdi; struct CVaultSid *
0x18001a71f  mov     rcx, rbx; this
0x18001a722  call    ?CreateSecurityDescriptor@CVaultSecurable@@QEAAKPEAVCVaultSid@@@Z; CVaultSecurable::CreateSecurityDescriptor(CVaultSid *)
0x18001a727  mov     edi, eax
0x18001a729  test    eax, eax
0x18001a72b  jz      short loc_18001A745
0x18001a72d  mov     rcx, rbx; hMem
0x18001a730  call    ?FreeRoamingCredential@CVaultRoamingCredential@@SAXPEAV1@@Z; CVaultRoamingCredential::FreeRoamingCredential(CVaultRoamingCredential *)
0x18001a735  nop
0x18001a736  mov     eax, edi
0x18001a738  add     rsp, 48h
0x18001a73c  pop     r15
0x18001a73e  pop     r14
0x18001a740  pop     rdi
0x18001a741  pop     rsi
0x18001a742  pop     rbp
0x18001a743  pop     rbx
0x18001a744  retn
0x18001a745  mov     [rsi], rbx
0x18001a748  xor     eax, eax
0x18001a74a  add     rsp, 48h
0x18001a74e  pop     r15
0x18001a750  pop     r14
0x18001a752  pop     rdi
0x18001a753  pop     rsi
0x18001a754  pop     rbp
0x18001a755  pop     rbx
0x18001a756  retn
```
