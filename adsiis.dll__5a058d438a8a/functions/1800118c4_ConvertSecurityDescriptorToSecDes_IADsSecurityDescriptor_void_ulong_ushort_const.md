# ConvertSecurityDescriptorToSecDes(IADsSecurityDescriptor *,void * *,ulong *,ushort const *)

- ea: `0x1800118c4`
- end: `0x180011b96`
- name: `?ConvertSecurityDescriptorToSecDes@@YAJPEAUIADsSecurityDescriptor@@PEAPEAXPEAKPEBG@Z`
- size: `722`
- prototype: `__int64 __fastcall(struct IADsSecurityDescriptor *, void **, unsigned int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001908c`

## callees

- `0x1800118c4`
- `0x180011ca8`
- `0x180011d98`
- `0x180011e64`
- `0x180011f2c`
- `0x18001201c`
- `0x18001e010`

## import_xrefs

- `ADVAPI32!MakeSelfRelativeSD` at `0x180011b5c`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180011b5c`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180011b2e`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x180011b2e`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180011b11`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180011b11`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180011abb`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180011abb`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180011a65`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180011a65`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180011a20`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180011a20`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x1800119db`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x1800119db`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180011935`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180011935`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180011b39`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180011b39`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001195f`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001196d`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001197b`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011989`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011b69`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011b7d`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001195f`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001196d`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18001197b`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011989`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011b69`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180011b7d`

## pseudocode

```c
__int64 __fastcall ConvertSecurityDescriptorToSecDes(
        struct IADsSecurityDescriptor *a1,
        void **a2,
        unsigned int *a3,
        const unsigned __int16 *a4)
{
  PSID v6; // r12
  PSID v7; // r15
  PACL v8; // r14
  PACL v9; // rsi
  int LastError; // ebx
  void *v11; // rdi
  int OwnerSecurityIdentifier; // eax
  int GroupSecurityIdentifier; // eax
  int Dacl; // eax
  BOOL v16; // edx
  int Sacl; // eax
  BOOL v18; // edx
  void *v19; // rax
  DWORD dwBufferLength; // [rsp+20h] [rbp-60h] BYREF
  int v21; // [rsp+24h] [rbp-5Ch] BYREF
  BOOL bOwnerDefaulted; // [rsp+28h] [rbp-58h] BYREF
  BOOL bGroupDefaulted; // [rsp+2Ch] [rbp-54h] BYREF
  BOOL bDaclDefaulted; // [rsp+30h] [rbp-50h] BYREF
  BOOL bSaclDefaulted; // [rsp+34h] [rbp-4Ch] BYREF
  PACL pSacl; // [rsp+38h] [rbp-48h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-40h] BYREF
  PSID pGroup; // [rsp+48h] [rbp-38h] BYREF
  PSID pOwner; // [rsp+50h] [rbp-30h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v31; // [rsp+78h] [rbp-8h]

  v31 = 0;
  bDaclDefaulted = 0;
  bSaclDefaulted = 0;
  bOwnerDefaulted = 0;
  bGroupDefaulted = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v6 = 0;
  pOwner = 0;
  v7 = 0;
  pGroup = 0;
  v8 = 0;
  pDacl = 0;
  v9 = 0;
  pSacl = 0;
  dwBufferLength = 0;
  v21 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastError = -2147467259;
LABEL_3:
    v11 = 0;
    *a3 = 0;
    goto LABEL_4;
  }
  LastError = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, int *))a1->lpVtbl->get_Control)(a1, &v21);
  if ( LastError < 0 )
    goto LABEL_3;
  if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x3F00u, v21 & 0x3F00) )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
      goto LABEL_3;
  }
  OwnerSecurityIdentifier = GetOwnerSecurityIdentifier(a1, &pOwner, &bOwnerDefaulted, a4);
  v6 = pOwner;
  LastError = OwnerSecurityIdentifier;
  if ( OwnerSecurityIdentifier < 0 )
    goto LABEL_3;
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, bOwnerDefaulted) )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
      goto LABEL_3;
  }
  GroupSecurityIdentifier = GetGroupSecurityIdentifier(a1, &pGroup, &bGroupDefaulted, a4);
  v7 = pGroup;
  LastError = GroupSecurityIdentifier;
  if ( GroupSecurityIdentifier < 0 )
    goto LABEL_3;
  if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, bGroupDefaulted) )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
      goto LABEL_3;
  }
  Dacl = GetDacl(a1, &pDacl, &bDaclDefaulted, a4);
  v8 = pDacl;
  LastError = Dacl;
  if ( Dacl < 0 )
    goto LABEL_3;
  if ( pDacl || (v16 = 0, bDaclDefaulted) )
    v16 = 1;
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, v16, pDacl, bDaclDefaulted) )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
      goto LABEL_3;
  }
  Sacl = GetSacl(a1, &pSacl, &bSaclDefaulted, a4);
  v9 = pSacl;
  LastError = Sacl;
  if ( Sacl < 0 )
    goto LABEL_3;
  if ( pSacl || (v18 = 0, bSaclDefaulted) )
    v18 = 1;
  if ( !SetSecurityDescriptorSacl(pSecurityDescriptor, v18, pSacl, bSaclDefaulted) )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
      goto LABEL_3;
  }
  dwBufferLength = GetSecurityDescriptorLength(pSecurityDescriptor);
  v19 = AllocADsMem(dwBufferLength);
  v11 = v19;
  if ( !v19 )
  {
    LastError = -2147024882;
    goto LABEL_3;
  }
  if ( !MakeSelfRelativeSD(pSecurityDescriptor, v19, &dwBufferLength) )
  {
    FreeADsMem(v11);
    LastError = HResultGetLastError();
    if ( LastError < 0 )
    {
      FreeADsMem(v11);
      goto LABEL_3;
    }
  }
  *a3 = dwBufferLength;
LABEL_4:
  *a2 = v11;
  if ( v8 )
    FreeADsMem(v8);
  if ( v9 )
    FreeADsMem(v9);
  if ( v6 )
    FreeADsMem(v6);
  if ( v7 )
    FreeADsMem(v7);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800118c4  mov     [rsp-38h+arg_0], rbx
0x1800118c9  mov     [rsp-38h+arg_10], r8
0x1800118ce  mov     [rsp-38h+arg_8], rdx
0x1800118d3  push    rbp
0x1800118d4  push    rsi
0x1800118d5  push    rdi
0x1800118d6  push    r12
0x1800118d8  push    r13
0x1800118da  push    r14
0x1800118dc  push    r15
0x1800118de  mov     rbp, rsp
0x1800118e1  sub     rsp, 80h
0x1800118e8  xor     ebx, ebx
0x1800118ea  xor     eax, eax
0x1800118ec  xorps   xmm0, xmm0
0x1800118ef  mov     [rbp+var_8], rax
0x1800118f3  mov     rdi, rcx
0x1800118f6  mov     [rbp+bDaclDefaulted], ebx
0x1800118f9  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800118fd  mov     [rbp+bSaclDefaulted], ebx
0x180011900  lea     edx, [rax+1]; dwRevision
0x180011903  mov     [rbp+bOwnerDefaulted], ebx
0x180011906  mov     r13, r9
0x180011909  mov     [rbp+bGroupDefaulted], ebx
0x18001190c  movups  [rbp+pSecurityDescriptor], xmm0
0x180011910  mov     r12d, ebx
0x180011913  mov     [rbp+pOwner], rbx
0x180011917  movups  [rbp+var_18], xmm0
0x18001191b  mov     r15d, ebx
0x18001191e  mov     [rbp+pGroup], rbx
0x180011922  mov     r14d, ebx
0x180011925  mov     [rbp+pDacl], rbx
0x180011929  mov     esi, ebx
0x18001192b  mov     [rbp+pSacl], rbx
0x18001192f  mov     [rbp+dwBufferLength], ebx
0x180011932  mov     [rbp+var_5C], ebx
0x180011935  call    cs:__imp_InitializeSecurityDescriptor
0x18001193b  test    eax, eax
0x18001193d  jnz     short loc_1800119AC
0x18001193f  mov     ebx, 80004005h
0x180011944  mov     rcx, [rbp+arg_10]
0x180011948  xor     edi, edi
0x18001194a  mov     dword ptr [rcx], 0
0x180011950  mov     rax, [rbp+arg_8]
0x180011954  mov     [rax], rdi
0x180011957  test    r14, r14
0x18001195a  jz      short loc_180011965
0x18001195c  mov     rcx, r14; pMem
0x18001195f  call    cs:__imp_FreeADsMem
0x180011965  test    rsi, rsi
0x180011968  jz      short loc_180011973
0x18001196a  mov     rcx, rsi; pMem
0x18001196d  call    cs:__imp_FreeADsMem
0x180011973  test    r12, r12
0x180011976  jz      short loc_180011981
0x180011978  mov     rcx, r12; pMem
0x18001197b  call    cs:__imp_FreeADsMem
0x180011981  test    r15, r15
0x180011984  jz      short loc_18001198F
0x180011986  mov     rcx, r15; pMem
0x180011989  call    cs:__imp_FreeADsMem
0x18001198f  mov     eax, ebx
0x180011991  mov     rbx, [rsp+80h+arg_0]
0x180011999  add     rsp, 80h
0x1800119a0  pop     r15
0x1800119a2  pop     r14
0x1800119a4  pop     r13
0x1800119a6  pop     r12
0x1800119a8  pop     rdi
0x1800119a9  pop     rsi
0x1800119aa  pop     rbp
0x1800119ab  retn
0x1800119ac  mov     rax, [rdi]
0x1800119af  lea     rdx, [rbp+var_5C]
0x1800119b3  mov     rcx, rdi
0x1800119b6  mov     rax, [rax+48h]
0x1800119ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119bf  mov     ebx, eax
0x1800119c1  test    eax, eax
0x1800119c3  js      loc_180011944
0x1800119c9  movzx   r8d, word ptr [rbp+var_5C]
0x1800119ce  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800119d2  mov     edx, 3F00h; ControlBitsOfInterest
0x1800119d7  and     r8w, dx; ControlBitsToSet
0x1800119db  call    cs:__imp_SetSecurityDescriptorControl
0x1800119e1  test    eax, eax
0x1800119e3  jnz     short loc_1800119F4
0x1800119e5  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x1800119ea  mov     ebx, eax
0x1800119ec  test    eax, eax
0x1800119ee  js      loc_180011944
0x1800119f4  mov     r9, r13; unsigned __int16 *
0x1800119f7  lea     r8, [rbp+bOwnerDefaulted]; int *
0x1800119fb  lea     rdx, [rbp+pOwner]; void **
0x1800119ff  mov     rcx, rdi; struct IADsSecurityDescriptor *
0x180011a02  call    ?GetOwnerSecurityIdentifier@@YAJPEAUIADsSecurityDescriptor@@PEAPEAXPEAHPEBG@Z; GetOwnerSecurityIdentifier(IADsSecurityDescriptor *,void * *,int *,ushort const *)
0x180011a07  mov     r12, [rbp+pOwner]
0x180011a0b  mov     ebx, eax
0x180011a0d  test    eax, eax
0x180011a0f  js      loc_180011944
0x180011a15  mov     r8d, [rbp+bOwnerDefaulted]; bOwnerDefaulted
0x180011a19  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180011a1d  mov     rdx, r12; pOwner
0x180011a20  call    cs:__imp_SetSecurityDescriptorOwner
0x180011a26  test    eax, eax
0x180011a28  jnz     short loc_180011A39
0x180011a2a  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x180011a2f  mov     ebx, eax
0x180011a31  test    eax, eax
0x180011a33  js      loc_180011944
0x180011a39  mov     r9, r13; unsigned __int16 *
0x180011a3c  lea     r8, [rbp+bGroupDefaulted]; int *
0x180011a40  lea     rdx, [rbp+pGroup]; void **
0x180011a44  mov     rcx, rdi; struct IADsSecurityDescriptor *
0x180011a47  call    ?GetGroupSecurityIdentifier@@YAJPEAUIADsSecurityDescriptor@@PEAPEAXPEAHPEBG@Z; GetGroupSecurityIdentifier(IADsSecurityDescriptor *,void * *,int *,ushort const *)
0x180011a4c  mov     r15, [rbp+pGroup]
0x180011a50  mov     ebx, eax
0x180011a52  test    eax, eax
0x180011a54  js      loc_180011944
0x180011a5a  mov     r8d, [rbp+bGroupDefaulted]; bGroupDefaulted
0x180011a5e  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180011a62  mov     rdx, r15; pGroup
0x180011a65  call    cs:__imp_SetSecurityDescriptorGroup
0x180011a6b  test    eax, eax
0x180011a6d  jnz     short loc_180011A7E
0x180011a6f  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x180011a74  mov     ebx, eax
0x180011a76  test    eax, eax
0x180011a78  js      loc_180011944
0x180011a7e  mov     r9, r13; unsigned __int16 *
0x180011a81  lea     r8, [rbp+bDaclDefaulted]; int *
0x180011a85  lea     rdx, [rbp+pDacl]; struct _ACL **
0x180011a89  mov     rcx, rdi; struct IADsSecurityDescriptor *
0x180011a8c  call    ?GetDacl@@YAJPEAUIADsSecurityDescriptor@@PEAPEAU_ACL@@PEAHPEBG@Z; GetDacl(IADsSecurityDescriptor *,_ACL * *,int *,ushort const *)
0x180011a91  mov     r14, [rbp+pDacl]
0x180011a95  mov     ebx, eax
0x180011a97  test    eax, eax
0x180011a99  js      loc_180011944
0x180011a9f  mov     r9d, [rbp+bDaclDefaulted]; bDaclDefaulted
0x180011aa3  test    r14, r14
0x180011aa6  jnz     short loc_180011AAF
0x180011aa8  xor     edx, edx
0x180011aaa  test    r9d, r9d
0x180011aad  jz      short loc_180011AB4
0x180011aaf  mov     edx, 1; bDaclPresent
0x180011ab4  mov     r8, r14; pDacl
0x180011ab7  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180011abb  call    cs:__imp_SetSecurityDescriptorDacl
0x180011ac1  test    eax, eax
0x180011ac3  jnz     short loc_180011AD4
0x180011ac5  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x180011aca  mov     ebx, eax
0x180011acc  test    eax, eax
0x180011ace  js      loc_180011944
0x180011ad4  mov     r9, r13; unsigned __int16 *
0x180011ad7  lea     r8, [rbp+bSaclDefaulted]; int *
0x180011adb  lea     rdx, [rbp+pSacl]; struct _ACL **
0x180011adf  mov     rcx, rdi; struct IADsSecurityDescriptor *
0x180011ae2  call    ?GetSacl@@YAJPEAUIADsSecurityDescriptor@@PEAPEAU_ACL@@PEAHPEBG@Z; GetSacl(IADsSecurityDescriptor *,_ACL * *,int *,ushort const *)
0x180011ae7  mov     rsi, [rbp+pSacl]
0x180011aeb  mov     ebx, eax
0x180011aed  test    eax, eax
0x180011aef  js      loc_180011944
0x180011af5  mov     r9d, [rbp+bSaclDefaulted]; bSaclDefaulted
0x180011af9  test    rsi, rsi
0x180011afc  jnz     short loc_180011B05
0x180011afe  xor     edx, edx
0x180011b00  test    r9d, r9d
0x180011b03  jz      short loc_180011B0A
0x180011b05  mov     edx, 1; bSaclPresent
0x180011b0a  mov     r8, rsi; pSacl
0x180011b0d  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180011b11  call    cs:__imp_SetSecurityDescriptorSacl
0x180011b17  test    eax, eax
0x180011b19  jnz     short loc_180011B2A
0x180011b1b  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x180011b20  mov     ebx, eax
0x180011b22  test    eax, eax
0x180011b24  js      loc_180011944
0x180011b2a  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180011b2e  call    cs:__imp_GetSecurityDescriptorLength
0x180011b34  mov     ecx, eax; cb
0x180011b36  mov     [rbp+dwBufferLength], eax
0x180011b39  call    cs:__imp_AllocADsMem
0x180011b3f  mov     rdi, rax
0x180011b42  test    rax, rax
0x180011b45  jnz     short loc_180011B51
0x180011b47  mov     ebx, 8007000Eh
0x180011b4c  jmp     loc_180011944
0x180011b51  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x180011b55  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x180011b58  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x180011b5c  call    cs:__imp_MakeSelfRelativeSD
0x180011b62  test    eax, eax
0x180011b64  jnz     short loc_180011B88
0x180011b66  mov     rcx, rdi; pMem
0x180011b69  call    cs:__imp_FreeADsMem
0x180011b6f  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x180011b74  mov     ebx, eax
0x180011b76  test    eax, eax
0x180011b78  jns     short loc_180011B88
0x180011b7a  mov     rcx, rdi; pMem
0x180011b7d  call    cs:__imp_FreeADsMem
0x180011b83  jmp     loc_180011944
0x180011b88  mov     rcx, [rbp+arg_10]
0x180011b8c  mov     eax, [rbp+dwBufferLength]
0x180011b8f  mov     [rcx], eax
0x180011b91  jmp     loc_180011950
```
