# CVaultCredmanStore::DeleteCredential(_GUID const *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *,_VAULT_ITEM_ELEMENT *)

- ea: `0x18003f0c0`
- end: `0x18003f44d`
- name: `?DeleteCredential@CVaultCredmanStore@@UEAAKPEBU_GUID@@PEAU_VAULT_ITEM_ELEMENT@@11@Z`
- size: `909`
- prototype: `__int64 __fastcall(CVaultCredmanStore *this, const struct _GUID *, struct _VAULT_ITEM_ELEMENT *, struct _VAULT_ITEM_ELEMENT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003140`
- `0x180013300`
- `0x18002e2e0`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003f0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f355`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f276`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f276`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18003f347`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18003f347`
- `ntdll!RtlReleaseResource` at `0x18003f10b`
- `ntdll!RtlReleaseResource` at `0x18003f130`
- `ntdll!RtlReleaseResource` at `0x18003f156`
- `ntdll!RtlReleaseResource` at `0x18003f1fa`
- `ntdll!RtlReleaseResource` at `0x18003f234`
- `ntdll!RtlReleaseResource` at `0x18003f258`
- `ntdll!RtlReleaseResource` at `0x18003f292`
- `ntdll!RtlReleaseResource` at `0x18003f324`
- `ntdll!RtlReleaseResource` at `0x18003f3a1`
- `ntdll!RtlReleaseResource` at `0x18003f3ec`
- `ntdll!RtlReleaseResource` at `0x18003f40b`
- `ntdll!RtlReleaseResource` at `0x18003f42a`
- `ntdll!RtlReleaseResource` at `0x18003f10b`
- `ntdll!RtlReleaseResource` at `0x18003f130`
- `ntdll!RtlReleaseResource` at `0x18003f156`
- `ntdll!RtlReleaseResource` at `0x18003f1fa`
- `ntdll!RtlReleaseResource` at `0x18003f234`
- `ntdll!RtlReleaseResource` at `0x18003f258`
- `ntdll!RtlReleaseResource` at `0x18003f292`
- `ntdll!RtlReleaseResource` at `0x18003f324`
- `ntdll!RtlReleaseResource` at `0x18003f3a1`
- `ntdll!RtlReleaseResource` at `0x18003f3ec`
- `ntdll!RtlReleaseResource` at `0x18003f40b`
- `ntdll!RtlReleaseResource` at `0x18003f42a`

## pseudocode

```c
__int64 __fastcall CVaultCredmanStore::DeleteCredential(
        CVaultCredmanStore *this,
        const struct _GUID *a2,
        struct _VAULT_ITEM_ELEMENT *a3,
        struct _VAULT_ITEM_ELEMENT *a4)
{
  unsigned __int16 *v7; // rdi
  __int64 v8; // rax
  DWORD v9; // edx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // edx
  unsigned int v16; // eax
  __int64 v17; // rcx
  unsigned __int64 v18; // rbx
  DWORD v19; // eax
  DWORD LastError; // ebx
  PRTL_RESOURCE Resource; // [rsp+30h] [rbp-38h] BYREF
  char v22; // [rsp+38h] [rbp-30h]
  __int64 v23; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-20h]
  int v25; // [rsp+50h] [rbp-18h]

  v24 = 0;
  v25 = 0;
  v23 = 0;
  CVaultRtlLock::CVaultRtlLock(&Resource, (char *)this + 192, 1);
  if ( !a4 )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
LABEL_72:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    return 87;
  }
  if ( *(_DWORD *)a4 != 1 )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
    goto LABEL_72;
  }
  if ( *((_DWORD *)a4 + 2) != 7 )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
    goto LABEL_72;
  }
  v7 = (unsigned __int16 *)*((_QWORD *)a4 + 2);
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&Vault_Schema_DomainPassword.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&Vault_Schema_DomainPassword.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)Vault_Schema_DomainPassword.Data4;
  if ( !v8 )
  {
    v9 = 2;
    goto LABEL_53;
  }
  v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&Vault_Schema_DomainCertificate.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&Vault_Schema_DomainCertificate.Data1 )
    v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)Vault_Schema_DomainCertificate.Data4;
  if ( !v10 )
  {
    v9 = 3;
    goto LABEL_53;
  }
  v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&Vault_Schema_DomainExtended.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&Vault_Schema_DomainExtended.Data1 )
    v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)Vault_Schema_DomainExtended.Data4;
  if ( v11 )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
    goto LABEL_72;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( v7[v13] );
  v14 = v13 + 1;
  if ( (int)v13 + 1 < (unsigned int)v13 )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
LABEL_29:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    return 534;
  }
  do
    ++v12;
  while ( *(_WORD *)(*((_QWORD *)a3 + 2) + 2 * v12) );
  v16 = v14 + v12;
  if ( v14 + (unsigned int)v12 < v14 )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
    goto LABEL_29;
  }
  v17 = v16 + 1;
  if ( (unsigned int)v17 < v16 )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
    goto LABEL_29;
  }
  v18 = (unsigned int)v17;
  v7 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v17);
  v24 = v7;
  if ( !v7 )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    return 14;
  }
  v19 = StringCchPrintfW(v7, v18, L"%ws%c%s", *((_QWORD *)a4 + 2), 124, *((_QWORD *)a3 + 2));
  LastError = v19;
  if ( v19 )
  {
    if ( (v19 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v19;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, LastError);
    if ( v22 )
      RtlReleaseResource(Resource);
    goto LABEL_51;
  }
  v9 = 6;
LABEL_53:
  if ( CredDeleteW(v7, v9, 0) )
  {
    if ( v22 )
      RtlReleaseResource(Resource);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1168 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids, LastError);
      if ( v22 )
        RtlReleaseResource(Resource);
LABEL_51:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
      return LastError;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids);
    if ( v22 )
      RtlReleaseResource(Resource);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v23);
    return 1168;
  }
}

```

## disassembly

```asm
0x18003f0c0  push    rbp
0x18003f0c2  push    rbx
0x18003f0c3  push    rsi
0x18003f0c4  push    rdi
0x18003f0c5  push    r14
0x18003f0c7  push    r15
0x18003f0c9  mov     rbp, rsp
0x18003f0cc  sub     rsp, 68h
0x18003f0d0  mov     rsi, r9
0x18003f0d3  mov     r14, r8
0x18003f0d6  mov     rbx, rdx
0x18003f0d9  xor     r15d, r15d
0x18003f0dc  mov     [rbp+var_20], r15
0x18003f0e0  mov     [rbp+var_18], r15d
0x18003f0e4  mov     [rbp+var_28], r15
0x18003f0e8  lea     rdx, [rcx+0C0h]
0x18003f0ef  lea     r8d, [r15+1]
0x18003f0f3  lea     rcx, [rbp+Resource]
0x18003f0f7  call    ??0CVaultRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eVaultLock@@@Z; CVaultRtlLock::CVaultRtlLock(_RTL_RESOURCE *,eVaultLock)
0x18003f0fc  test    rsi, rsi
0x18003f0ff  jnz     short loc_18003F121
0x18003f101  cmp     [rbp+var_30], r15b
0x18003f105  jz      short loc_18003F112
0x18003f107  mov     rcx, [rbp+Resource]; Resource
0x18003f10b  call    cs:__imp_RtlReleaseResource
0x18003f111  nop
0x18003f112  lea     rcx, [rbp+var_28]
0x18003f116  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f11b  nop
0x18003f11c  jmp     loc_18003F43B
0x18003f121  cmp     dword ptr [rsi], 1
0x18003f124  jz      short loc_18003F146
0x18003f126  cmp     [rbp+var_30], r15b
0x18003f12a  jz      short loc_18003F137
0x18003f12c  mov     rcx, [rbp+Resource]; Resource
0x18003f130  call    cs:__imp_RtlReleaseResource
0x18003f136  nop
0x18003f137  lea     rcx, [rbp+var_28]
0x18003f13b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f140  nop
0x18003f141  jmp     loc_18003F43B
0x18003f146  cmp     dword ptr [rsi+8], 7
0x18003f14a  jz      short loc_18003F16C
0x18003f14c  cmp     [rbp+var_30], r15b
0x18003f150  jz      short loc_18003F15D
0x18003f152  mov     rcx, [rbp+Resource]; Resource
0x18003f156  call    cs:__imp_RtlReleaseResource
0x18003f15c  nop
0x18003f15d  lea     rcx, [rbp+var_28]
0x18003f161  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f166  nop
0x18003f167  jmp     loc_18003F43B
0x18003f16c  mov     rdi, [rsi+10h]
0x18003f170  mov     rax, [rbx]
0x18003f173  sub     rax, qword ptr cs:Vault_Schema_DomainPassword.Data1
0x18003f17a  jnz     short loc_18003F187
0x18003f17c  mov     rax, [rbx+8]
0x18003f180  sub     rax, qword ptr cs:Vault_Schema_DomainPassword.Data4
0x18003f187  test    rax, rax
0x18003f18a  jnz     short loc_18003F194
0x18003f18c  lea     edx, [rax+2]
0x18003f18f  jmp     loc_18003F341
0x18003f194  mov     rax, [rbx]
0x18003f197  sub     rax, qword ptr cs:Vault_Schema_DomainCertificate.Data1
0x18003f19e  jnz     short loc_18003F1AB
0x18003f1a0  mov     rax, [rbx+8]
0x18003f1a4  sub     rax, qword ptr cs:Vault_Schema_DomainCertificate.Data4
0x18003f1ab  test    rax, rax
0x18003f1ae  jnz     short loc_18003F1B8
0x18003f1b0  lea     edx, [rax+3]
0x18003f1b3  jmp     loc_18003F341
0x18003f1b8  mov     rax, [rbx]
0x18003f1bb  sub     rax, qword ptr cs:Vault_Schema_DomainExtended.Data1
0x18003f1c2  jnz     short loc_18003F1CF
0x18003f1c4  mov     rax, [rbx+8]
0x18003f1c8  sub     rax, qword ptr cs:Vault_Schema_DomainExtended.Data4
0x18003f1cf  test    rax, rax
0x18003f1d2  jnz     loc_18003F420
0x18003f1d8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003f1dc  mov     rax, rcx
0x18003f1df  inc     rax
0x18003f1e2  cmp     [rdi+rax*2], r15w
0x18003f1e7  jnz     short loc_18003F1DF
0x18003f1e9  lea     edx, [rax+1]
0x18003f1ec  cmp     edx, eax
0x18003f1ee  jnb     short loc_18003F215
0x18003f1f0  cmp     [rbp+var_30], r15b
0x18003f1f4  jz      short loc_18003F201
0x18003f1f6  mov     rcx, [rbp+Resource]; Resource
0x18003f1fa  call    cs:__imp_RtlReleaseResource
0x18003f200  nop
0x18003f201  lea     rcx, [rbp+var_28]
0x18003f205  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f20a  nop
0x18003f20b  mov     eax, 216h
0x18003f210  jmp     loc_18003F440
0x18003f215  mov     rax, [r14+10h]
0x18003f219  inc     rcx
0x18003f21c  cmp     [rax+rcx*2], r15w
0x18003f221  jnz     short loc_18003F219
0x18003f223  lea     eax, [rdx+rcx]
0x18003f226  cmp     eax, edx
0x18003f228  jnb     short loc_18003F247
0x18003f22a  cmp     [rbp+var_30], r15b
0x18003f22e  jz      short loc_18003F23B
0x18003f230  mov     rcx, [rbp+Resource]; Resource
0x18003f234  call    cs:__imp_RtlReleaseResource
0x18003f23a  nop
0x18003f23b  lea     rcx, [rbp+var_28]
0x18003f23f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f244  nop
0x18003f245  jmp     short loc_18003F20B
0x18003f247  lea     ecx, [rax+1]
0x18003f24a  cmp     ecx, eax
0x18003f24c  jnb     short loc_18003F26B
0x18003f24e  cmp     [rbp+var_30], r15b
0x18003f252  jz      short loc_18003F25F
0x18003f254  mov     rcx, [rbp+Resource]; Resource
0x18003f258  call    cs:__imp_RtlReleaseResource
0x18003f25e  nop
0x18003f25f  lea     rcx, [rbp+var_28]
0x18003f263  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f268  nop
0x18003f269  jmp     short loc_18003F20B
0x18003f26b  mov     ebx, ecx
0x18003f26d  lea     rdx, [rcx+rcx]; uBytes
0x18003f271  mov     ecx, 40h ; '@'; uFlags
0x18003f276  call    cs:__imp_LocalAlloc
0x18003f27c  mov     rdi, rax
0x18003f27f  mov     [rbp+var_20], rax
0x18003f283  test    rax, rax
0x18003f286  jnz     short loc_18003F2AD
0x18003f288  cmp     [rbp+var_30], r15b
0x18003f28c  jz      short loc_18003F299
0x18003f28e  mov     rcx, [rbp+Resource]; Resource
0x18003f292  call    cs:__imp_RtlReleaseResource
0x18003f298  nop
0x18003f299  lea     rcx, [rbp+var_28]
0x18003f29d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f2a2  nop
0x18003f2a3  mov     eax, 0Eh
0x18003f2a8  jmp     loc_18003F440
0x18003f2ad  mov     rax, [r14+10h]
0x18003f2b1  mov     [rsp+68h+var_40], rax
0x18003f2b6  mov     [rsp+68h+var_48], 7Ch ; '|'
0x18003f2be  mov     r9, [rsi+10h]
0x18003f2c2  lea     r8, aWsCS; "%ws%c%s"
0x18003f2c9  mov     rdx, rbx; unsigned __int64
0x18003f2cc  mov     rcx, rdi; unsigned __int16 *
0x18003f2cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003f2d4  mov     ebx, eax
0x18003f2d6  test    eax, eax
0x18003f2d8  jz      short loc_18003F33C
0x18003f2da  and     eax, 1FFF0000h
0x18003f2df  cmp     eax, 70000h
0x18003f2e4  jnz     short loc_18003F2E9
0x18003f2e6  movzx   ebx, bx
0x18003f2e9  lea     rax, WPP_GLOBAL_Control
0x18003f2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f2f7  cmp     rcx, rax
0x18003f2fa  jz      short loc_18003F31A
0x18003f2fc  test    byte ptr [rcx+1Ch], 2
0x18003f300  jz      short loc_18003F31A
0x18003f302  mov     edx, 22h ; '"'
0x18003f307  mov     r9d, ebx
0x18003f30a  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x18003f311  mov     rcx, [rcx+10h]
0x18003f315  call    WPP_SF_d
0x18003f31a  cmp     [rbp+var_30], r15b
0x18003f31e  jz      short loc_18003F32B
0x18003f320  mov     rcx, [rbp+Resource]; Resource
0x18003f324  call    cs:__imp_RtlReleaseResource
0x18003f32a  nop
0x18003f32b  lea     rcx, [rbp+var_28]
0x18003f32f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f334  nop
0x18003f335  mov     eax, ebx
0x18003f337  jmp     loc_18003F440
0x18003f33c  mov     edx, 6; Type
0x18003f341  xor     r8d, r8d; Flags
0x18003f344  mov     rcx, rdi; TargetName
0x18003f347  call    cs:__imp_CredDeleteW
0x18003f34d  test    eax, eax
0x18003f34f  jnz     loc_18003F401
0x18003f355  call    cs:__imp_GetLastError
0x18003f35b  mov     ebx, eax
0x18003f35d  mov     edi, 490h
0x18003f362  cmp     eax, edi
0x18003f364  jz      short loc_18003F3B4
0x18003f366  lea     rax, WPP_GLOBAL_Control
0x18003f36d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f374  cmp     rcx, rax
0x18003f377  jz      short loc_18003F397
0x18003f379  test    byte ptr [rcx+1Ch], 2
0x18003f37d  jz      short loc_18003F397
0x18003f37f  mov     edx, 23h ; '#'
0x18003f384  mov     r9d, ebx
0x18003f387  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x18003f38e  mov     rcx, [rcx+10h]
0x18003f392  call    WPP_SF_d
0x18003f397  cmp     [rbp+var_30], r15b
0x18003f39b  jz      short loc_18003F3A8
0x18003f39d  mov     rcx, [rbp+Resource]; Resource
0x18003f3a1  call    cs:__imp_RtlReleaseResource
0x18003f3a7  nop
0x18003f3a8  lea     rcx, [rbp+var_28]
0x18003f3ac  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f3b1  nop
0x18003f3b2  jmp     short loc_18003F335
0x18003f3b4  lea     rax, WPP_GLOBAL_Control
0x18003f3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3c2  cmp     rcx, rax
0x18003f3c5  jz      short loc_18003F3E2
0x18003f3c7  test    byte ptr [rcx+1Ch], 4
0x18003f3cb  jz      short loc_18003F3E2
0x18003f3cd  mov     edx, 24h ; '$'
0x18003f3d2  lea     r8, WPP_a1941115094638e056392bf8f8c33bbf_Traceguids
0x18003f3d9  mov     rcx, [rcx+10h]
0x18003f3dd  call    WPP_SF_
0x18003f3e2  cmp     [rbp+var_30], r15b
0x18003f3e6  jz      short loc_18003F3F3
0x18003f3e8  mov     rcx, [rbp+Resource]; Resource
0x18003f3ec  call    cs:__imp_RtlReleaseResource
0x18003f3f2  nop
0x18003f3f3  lea     rcx, [rbp+var_28]
0x18003f3f7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f3fc  nop
0x18003f3fd  mov     eax, edi
0x18003f3ff  jmp     short loc_18003F440
0x18003f401  cmp     [rbp+var_30], r15b
0x18003f405  jz      short loc_18003F412
0x18003f407  mov     rcx, [rbp+Resource]; Resource
0x18003f40b  call    cs:__imp_RtlReleaseResource
0x18003f411  nop
0x18003f412  lea     rcx, [rbp+var_28]
0x18003f416  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f41b  nop
0x18003f41c  xor     eax, eax
0x18003f41e  jmp     short loc_18003F440
0x18003f420  cmp     [rbp+var_30], r15b
0x18003f424  jz      short loc_18003F431
0x18003f426  mov     rcx, [rbp+Resource]; Resource
0x18003f42a  call    cs:__imp_RtlReleaseResource
0x18003f430  nop
0x18003f431  lea     rcx, [rbp+var_28]
0x18003f435  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003f43a  nop
0x18003f43b  mov     eax, 57h ; 'W'
0x18003f440  add     rsp, 68h
0x18003f444  pop     r15
0x18003f446  pop     r14
0x18003f448  pop     rdi
0x18003f449  pop     rsi
0x18003f44a  pop     rbx
0x18003f44b  pop     rbp
0x18003f44c  retn
```
