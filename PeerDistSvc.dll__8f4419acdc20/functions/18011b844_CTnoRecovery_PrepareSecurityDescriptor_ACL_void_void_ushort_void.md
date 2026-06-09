# CTnoRecovery::PrepareSecurityDescriptor(_ACL *,void *,void *,ushort,void *)

- ea: `0x18011b844`
- end: `0x18011bae2`
- name: `?PrepareSecurityDescriptor@CTnoRecovery@@CAJPEAU_ACL@@PEAX1G1@Z`
- size: `670`
- prototype: `__int64 __usercall@<rax>(PACL pDacl@<rcx>, PSID pOwner@<rdx>, PSID pGroup@<r8>, unsigned __int16@<r9w>, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18011ae54`

## callees

- `0x180004374`
- `0x180008290`
- `0x18002f328`
- `0x18011b844`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b89b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b89b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b9f9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18011ba3c`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18011ba3c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18011b9ef`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18011b9ef`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18011b995`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18011b995`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18011b93e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18011b93e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18011b8fa`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18011b8fa`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18011b891`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18011b891`

## pseudocode

```c
__int64 __fastcall CTnoRecovery::PrepareSecurityDescriptor(
        PACL pDacl,
        PSID pOwner,
        PSID pGroup,
        __int16 a4,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  DWORD LastError; // edi
  CHostedCacheMsgEncoding *v10; // rcx
  __int64 v11; // rdx

  if ( pDacl && pOwner && pGroup && pSecurityDescriptor )
  {
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 41;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v10 + 12), v11, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids, LastError);
        goto LABEL_11;
      }
      goto LABEL_11;
    }
    if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 42;
        goto LABEL_10;
      }
LABEL_11:
      if ( (int)LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return LastError;
    }
    if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, 0) )
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 43;
        goto LABEL_10;
      }
      goto LABEL_11;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 44;
        goto LABEL_10;
      }
      goto LABEL_11;
    }
    if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x1500u, a4 & 0x1500) )
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v11 = 45;
        goto LABEL_10;
      }
      goto LABEL_11;
    }
    if ( IsValidSecurityDescriptor(pSecurityDescriptor) )
    {
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 46, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids);
      }
      return 2147942413LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qqqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        40,
        WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
        pDacl,
        pOwner,
        pGroup,
        pSecurityDescriptor);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18011b844  push    rbp
0x18011b846  push    rsi
0x18011b847  push    rdi
0x18011b848  push    r14
0x18011b84a  push    r15
0x18011b84c  sub     rsp, 40h
0x18011b850  mov     rdi, [rsp+68h+pSecurityDescriptor]
0x18011b858  movzx   r15d, r9w
0x18011b85c  mov     rbp, r8
0x18011b85f  mov     rsi, rdx
0x18011b862  mov     r14, rcx
0x18011b865  test    rcx, rcx
0x18011b868  jz      loc_18011BA88
0x18011b86e  test    rdx, rdx
0x18011b871  jz      loc_18011BA88
0x18011b877  test    r8, r8
0x18011b87a  jz      loc_18011BA88
0x18011b880  test    rdi, rdi
0x18011b883  jz      loc_18011BA88
0x18011b889  mov     edx, 1; dwRevision
0x18011b88e  mov     rcx, rdi; pSecurityDescriptor
0x18011b891  call    cs:__imp_InitializeSecurityDescriptor
0x18011b897  test    eax, eax
0x18011b899  jnz     short loc_18011B8F1
0x18011b89b  call    cs:__imp_GetLastError
0x18011b8a1  mov     edi, eax
0x18011b8a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b8aa  lea     rax, WPP_GLOBAL_Control
0x18011b8b1  cmp     rcx, rax
0x18011b8b4  jz      short loc_18011B8DD
0x18011b8b6  test    dword ptr [rcx+6Ch], 8000000h
0x18011b8bd  jz      short loc_18011B8DD
0x18011b8bf  cmp     byte ptr [rcx+69h], 1
0x18011b8c3  jb      short loc_18011B8DD
0x18011b8c5  mov     edx, 29h ; ')'
0x18011b8ca  mov     rcx, [rcx+60h]
0x18011b8ce  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b8d5  mov     r9d, edi
0x18011b8d8  call    WPP_SF_d
0x18011b8dd  test    edi, edi
0x18011b8df  jle     short loc_18011B8EA
0x18011b8e1  movzx   edi, di
0x18011b8e4  or      edi, 80070000h
0x18011b8ea  mov     eax, edi
0x18011b8ec  jmp     loc_18011BAD6
0x18011b8f1  xor     r8d, r8d; bOwnerDefaulted
0x18011b8f4  mov     rdx, rsi; pOwner
0x18011b8f7  mov     rcx, rdi; pSecurityDescriptor
0x18011b8fa  call    cs:__imp_SetSecurityDescriptorOwner
0x18011b900  test    eax, eax
0x18011b902  jnz     short loc_18011B935
0x18011b904  call    cs:__imp_GetLastError
0x18011b90a  mov     edi, eax
0x18011b90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b913  lea     rax, WPP_GLOBAL_Control
0x18011b91a  cmp     rcx, rax
0x18011b91d  jz      short loc_18011B8DD
0x18011b91f  test    dword ptr [rcx+6Ch], 8000000h
0x18011b926  jz      short loc_18011B8DD
0x18011b928  cmp     byte ptr [rcx+69h], 1
0x18011b92c  jb      short loc_18011B8DD
0x18011b92e  mov     edx, 2Ah ; '*'
0x18011b933  jmp     short loc_18011B8CA
0x18011b935  xor     r8d, r8d; bGroupDefaulted
0x18011b938  mov     rdx, rbp; pGroup
0x18011b93b  mov     rcx, rdi; pSecurityDescriptor
0x18011b93e  call    cs:__imp_SetSecurityDescriptorGroup
0x18011b944  test    eax, eax
0x18011b946  jnz     short loc_18011B988
0x18011b948  call    cs:__imp_GetLastError
0x18011b94e  mov     edi, eax
0x18011b950  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b957  lea     rax, WPP_GLOBAL_Control
0x18011b95e  cmp     rcx, rax
0x18011b961  jz      loc_18011B8DD
0x18011b967  test    dword ptr [rcx+6Ch], 8000000h
0x18011b96e  jz      loc_18011B8DD
0x18011b974  cmp     byte ptr [rcx+69h], 1
0x18011b978  jb      loc_18011B8DD
0x18011b97e  mov     edx, 2Bh ; '+'
0x18011b983  jmp     loc_18011B8CA
0x18011b988  xor     r9d, r9d; bDaclDefaulted
0x18011b98b  mov     r8, r14; pDacl
0x18011b98e  mov     rcx, rdi; pSecurityDescriptor
0x18011b991  lea     edx, [r9+1]; bDaclPresent
0x18011b995  call    cs:__imp_SetSecurityDescriptorDacl
0x18011b99b  test    eax, eax
0x18011b99d  jnz     short loc_18011B9DF
0x18011b99f  call    cs:__imp_GetLastError
0x18011b9a5  mov     edi, eax
0x18011b9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b9ae  lea     rax, WPP_GLOBAL_Control
0x18011b9b5  cmp     rcx, rax
0x18011b9b8  jz      loc_18011B8DD
0x18011b9be  test    dword ptr [rcx+6Ch], 8000000h
0x18011b9c5  jz      loc_18011B8DD
0x18011b9cb  cmp     byte ptr [rcx+69h], 1
0x18011b9cf  jb      loc_18011B8DD
0x18011b9d5  mov     edx, 2Ch ; ','
0x18011b9da  jmp     loc_18011B8CA
0x18011b9df  mov     edx, 1500h; ControlBitsOfInterest
0x18011b9e4  mov     rcx, rdi; pSecurityDescriptor
0x18011b9e7  and     r15w, dx
0x18011b9eb  movzx   r8d, r15w; ControlBitsToSet
0x18011b9ef  call    cs:__imp_SetSecurityDescriptorControl
0x18011b9f5  test    eax, eax
0x18011b9f7  jnz     short loc_18011BA39
0x18011b9f9  call    cs:__imp_GetLastError
0x18011b9ff  mov     edi, eax
0x18011ba01  mov     rcx, cs:WPP_GLOBAL_Control
0x18011ba08  lea     rax, WPP_GLOBAL_Control
0x18011ba0f  cmp     rcx, rax
0x18011ba12  jz      loc_18011B8DD
0x18011ba18  test    dword ptr [rcx+6Ch], 8000000h
0x18011ba1f  jz      loc_18011B8DD
0x18011ba25  cmp     byte ptr [rcx+69h], 1
0x18011ba29  jb      loc_18011B8DD
0x18011ba2f  mov     edx, 2Dh ; '-'
0x18011ba34  jmp     loc_18011B8CA
0x18011ba39  mov     rcx, rdi; pSecurityDescriptor
0x18011ba3c  call    cs:__imp_IsValidSecurityDescriptor
0x18011ba42  test    eax, eax
0x18011ba44  jnz     short loc_18011BA84
0x18011ba46  mov     rcx, cs:WPP_GLOBAL_Control
0x18011ba4d  lea     rax, WPP_GLOBAL_Control
0x18011ba54  cmp     rcx, rax
0x18011ba57  jz      short loc_18011BA7D
0x18011ba59  test    dword ptr [rcx+6Ch], 8000000h
0x18011ba60  jz      short loc_18011BA7D
0x18011ba62  cmp     byte ptr [rcx+69h], 1
0x18011ba66  jb      short loc_18011BA7D
0x18011ba68  mov     rcx, [rcx+60h]
0x18011ba6c  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011ba73  mov     edx, 2Eh ; '.'
0x18011ba78  call    WPP_SF_
0x18011ba7d  mov     eax, 8007000Dh
0x18011ba82  jmp     short loc_18011BAD6
0x18011ba84  xor     eax, eax
0x18011ba86  jmp     short loc_18011BAD6
0x18011ba88  mov     rcx, cs:WPP_GLOBAL_Control
0x18011ba8f  lea     rax, WPP_GLOBAL_Control
0x18011ba96  cmp     rcx, rax
0x18011ba99  jz      short loc_18011BAD1
0x18011ba9b  test    dword ptr [rcx+6Ch], 8000000h
0x18011baa2  jz      short loc_18011BAD1
0x18011baa4  cmp     byte ptr [rcx+69h], 1
0x18011baa8  jb      short loc_18011BAD1
0x18011baaa  mov     rcx, [rcx+60h]
0x18011baae  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011bab5  mov     [rsp+68h+var_38], rdi
0x18011baba  mov     edx, 28h ; '('
0x18011babf  mov     [rsp+68h+var_40], rbp
0x18011bac4  mov     r9, r14
0x18011bac7  mov     [rsp+68h+var_48], rsi
0x18011bacc  call    WPP_SF_qqqq
0x18011bad1  mov     eax, 80070057h
0x18011bad6  add     rsp, 40h
0x18011bada  pop     r15
0x18011badc  pop     r14
0x18011bade  pop     rdi
0x18011badf  pop     rsi
0x18011bae0  pop     rbp
0x18011bae1  retn
```
