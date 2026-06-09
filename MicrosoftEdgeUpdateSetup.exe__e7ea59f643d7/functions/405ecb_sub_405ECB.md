# sub_405ECB

- ea: `0x405ecb`
- end: `0x405fef`
- name: `sub_405ECB`
- size: `292`
- prototype: `void __thiscall(PSECURITY_DESCRIPTOR *this, _BYTE *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4062cf`

## callees

- `0x4010bf`
- `0x405383`
- `0x40539c`
- `0x40541a`
- `0x4056bc`
- `0x405810`
- `0x405ecb`
- `0x405ff0`
- `0x4061ae`
- `0x408c05`
- `0x40c28b`
- `0x40c2a6`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x405fab`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x405fab`
- `ADVAPI32!GetAclInformation` at `0x405f58`
- `ADVAPI32!GetAclInformation` at `0x405f58`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x405f0a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x405f0a`

## pseudocode

```c
void __thiscall sub_405ECB(PSECURITY_DESCRIPTOR *this, _BYTE *a2, int a3)
{
  _BYTE *v4; // esi
  ACL *v5; // eax
  ACL *v6; // edi
  void *v7; // eax
  BOOL v8; // eax
  signed int v9; // esi
  size_t v10; // [esp-4h] [ebp-30h]
  PACL pDacl; // [esp+10h] [ebp-1Ch] BYREF
  BOOL bDaclPresent; // [esp+14h] [ebp-18h] BYREF
  BOOL bDaclDefaulted; // [esp+18h] [ebp-14h] BYREF
  _BYTE pAclInformation[4]; // [esp+1Ch] [ebp-10h] BYREF
  size_t Size; // [esp+20h] [ebp-Ch]

  v4 = a2;
  if ( this[1] )
    sub_405FF0();
  pDacl = 0;
  if ( this[1] )
  {
    if ( !GetSecurityDescriptorDacl(this[1], &bDaclPresent, &pDacl, &bDaclDefaulted) )
      goto LABEL_22;
  }
  else
  {
    sub_4061AE(this);
  }
  if ( a2[8] || (v4 = a2, !(*(int (__thiscall **)(_BYTE *))(*(_DWORD *)a2 + 4))(a2)) )
  {
    v6 = 0;
    goto LABEL_15;
  }
  v5 = (ACL *)sub_4056BC(a2);
  if ( !v5 )
    sub_4010BF(-2147467259);
  if ( !GetAclInformation(v5, pAclInformation, 0xCu, AclSizeInformation) )
LABEL_22:
    sub_405383();
  v6 = (ACL *)malloc(Size);
  if ( !v6 )
    sub_4010BF(-2147024882);
  v10 = Size;
  v7 = (void *)sub_4056BC(a2);
  sub_40539C(v6, Size, v7, v10);
LABEL_15:
  v8 = v4[8] || v6;
  if ( !SetSecurityDescriptorDacl(this[1], v8, v6, 0) )
  {
    v9 = sub_40541A();
    free(v6);
    sub_4010BF(v9);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x405ecb  push    ebp
0x405ecc  mov     ebp, esp
0x405ece  sub     esp, 20h
0x405ed1  mov     eax, ___security_cookie
0x405ed6  xor     eax, ebp
0x405ed8  mov     [ebp+var_4], eax
0x405edb  push    ebx
0x405edc  mov     ebx, ecx
0x405ede  push    esi
0x405edf  mov     esi, [ebp+arg_0]
0x405ee2  push    edi
0x405ee3  cmp     dword ptr [ebx+4], 0
0x405ee7  mov     [ebp+var_20], esi
0x405eea  jz      short loc_405EF1
0x405eec  call    sub_405FF0
0x405ef1  and     [ebp+pDacl], 0
0x405ef5  cmp     dword ptr [ebx+4], 0
0x405ef9  jz      short loc_405F1A
0x405efb  lea     eax, [ebp+bDaclDefaulted]
0x405efe  push    eax; lpbDaclDefaulted
0x405eff  lea     eax, [ebp+pDacl]
0x405f02  push    eax; pDacl
0x405f03  lea     eax, [ebp+bDaclPresent]
0x405f06  push    eax; lpbDaclPresent
0x405f07  push    dword ptr [ebx+4]; pSecurityDescriptor
0x405f0a  call    ds:GetSecurityDescriptorDacl
0x405f10  test    eax, eax
0x405f12  jz      loc_405FE0
0x405f18  jmp     short loc_405F21
0x405f1a  mov     ecx, ebx
0x405f1c  call    sub_4061AE
0x405f21  cmp     byte ptr [esi+8], 0
0x405f25  jnz     short loc_405F91
0x405f27  mov     eax, [esi]
0x405f29  mov     esi, [eax+4]
0x405f2c  mov     ecx, esi
0x405f2e  call    ds:___guard_check_icall_fptr
0x405f34  mov     ecx, [ebp+var_20]
0x405f37  call    esi
0x405f39  mov     esi, [ebp+var_20]
0x405f3c  test    eax, eax
0x405f3e  jz      short loc_405F91
0x405f40  mov     ecx, esi
0x405f42  call    sub_4056BC
0x405f47  test    eax, eax
0x405f49  jz      loc_405FE5
0x405f4f  push    2; dwAclInformationClass
0x405f51  push    0Ch; nAclInformationLength
0x405f53  lea     ecx, [ebp+pAclInformation]
0x405f56  push    ecx; pAclInformation
0x405f57  push    eax; pAcl
0x405f58  call    ds:GetAclInformation
0x405f5e  test    eax, eax
0x405f60  jz      short loc_405FE0
0x405f62  push    [ebp+Size]; Size
0x405f65  call    _malloc
0x405f6a  mov     edi, eax
0x405f6c  pop     ecx
0x405f6d  test    edi, edi
0x405f6f  jnz     short loc_405F78
0x405f71  push    8007000Eh
0x405f76  jmp     short loc_405FEA
0x405f78  push    [ebp+Size]; size_t
0x405f7b  mov     ecx, esi
0x405f7d  call    sub_4056BC
0x405f82  mov     edx, [ebp+Size]; Size
0x405f85  mov     ecx, edi; void *
0x405f87  push    eax; Src
0x405f88  call    sub_40539C
0x405f8d  pop     ecx
0x405f8e  pop     ecx
0x405f8f  jmp     short loc_405F93
0x405f91  xor     edi, edi
0x405f93  cmp     byte ptr [esi+8], 0
0x405f97  jnz     short loc_405FA1
0x405f99  test    edi, edi
0x405f9b  jnz     short loc_405FA1
0x405f9d  xor     eax, eax
0x405f9f  jmp     short loc_405FA4
0x405fa1  xor     eax, eax
0x405fa3  inc     eax
0x405fa4  push    0; bDaclDefaulted
0x405fa6  push    edi; pDacl
0x405fa7  push    eax; bDaclPresent
0x405fa8  push    dword ptr [ebx+4]; pSecurityDescriptor
0x405fab  call    ds:SetSecurityDescriptorDacl
0x405fb1  test    eax, eax
0x405fb3  jnz     short loc_405FC6
0x405fb5  call    sub_40541A
0x405fba  push    edi; Block
0x405fbb  mov     esi, eax
0x405fbd  call    _free
0x405fc2  pop     ecx
0x405fc3  push    esi
0x405fc4  jmp     short loc_405FEA
0x405fc6  push    [ebp+pDacl]; Block
0x405fc9  call    _free
0x405fce  pop     ecx
0x405fcf  mov     ecx, [ebp+var_4]
0x405fd2  pop     edi
0x405fd3  pop     esi
0x405fd4  xor     ecx, ebp; StackCookie
0x405fd6  pop     ebx
0x405fd7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x405fdc  leave
0x405fdd  retn    8
0x405fe0  call    sub_405383
0x405fe5  push    80004005h
0x405fea  call    sub_4010BF
```
