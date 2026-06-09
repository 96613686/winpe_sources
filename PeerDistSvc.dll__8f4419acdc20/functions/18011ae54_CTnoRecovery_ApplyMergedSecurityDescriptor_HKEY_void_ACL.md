# CTnoRecovery::ApplyMergedSecurityDescriptor(HKEY__ *,void *,_ACL *)

- ea: `0x18011ae54`
- end: `0x18011b0ae`
- name: `?ApplyMergedSecurityDescriptor@CTnoRecovery@@CAJPEAUHKEY__@@PEAXPEAU_ACL@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(HKEY hKey, PSECURITY_DESCRIPTOR pSecurityDescriptor, PACL pDacl)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18011b0b4`

## callees

- `0x180008290`
- `0x180008310`
- `0x180028e84`
- `0x18011ae54`
- `0x18011b844`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011aed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011af40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011af8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011aed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011af40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011af8d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18011aecb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18011aecb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18011af7c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18011af7c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18011af36`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18011af36`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18011aff8`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18011aff8`

## pseudocode

```c
__int64 __fastcall CTnoRecovery::ApplyMergedSecurityDescriptor(
        HKEY hKey,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        PACL pDacl)
{
  DWORD LastError; // ebx
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  __int64 result; // rax
  DWORD v10; // eax
  LSTATUS v11; // eax
  DWORD dwRevision; // [rsp+30h] [rbp-40h] BYREF
  PSID pGroup; // [rsp+38h] [rbp-38h] BYREF
  PSID pOwner; // [rsp+40h] [rbp-30h] BYREF
  __int128 pSecurityDescriptora; // [rsp+48h] [rbp-28h] BYREF
  __int128 v16; // [rsp+58h] [rbp-18h]
  __int64 v17; // [rsp+68h] [rbp-8h]
  WORD pControl; // [rsp+90h] [rbp+20h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+A8h] [rbp+38h] BYREF

  dwRevision = 0;
  bOwnerDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  pControl = 0;
  v17 = 0;
  pSecurityDescriptora = 0;
  v16 = 0;
  if ( hKey && pSecurityDescriptor && pDacl )
  {
    if ( !GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted) )
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 34;
LABEL_9:
        WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids, LastError);
        goto LABEL_10;
      }
      goto LABEL_10;
    }
    if ( !GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bOwnerDefaulted) )
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 35;
        goto LABEL_9;
      }
LABEL_10:
      if ( (int)LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return LastError;
    }
    if ( !GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
    {
      v10 = GetLastError();
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 36, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids, v10);
      }
    }
    result = CTnoRecovery::PrepareSecurityDescriptor(pDacl, pOwner, pGroup, pControl, &pSecurityDescriptora);
    if ( (int)result >= 0 )
    {
      v11 = RegSetKeySecurity(hKey, 7u, &pSecurityDescriptora);
      LastError = v11;
      if ( !v11 )
        return 0;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids, hKey, v11);
      }
      goto LABEL_10;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        33,
        WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
        hKey,
        pSecurityDescriptor,
        pDacl,
        dwRevision,
        pGroup,
        pOwner,
        pSecurityDescriptora,
        *((_QWORD *)&pSecurityDescriptora + 1),
        v16,
        *((_QWORD *)&v16 + 1),
        v17);
    }
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18011ae54  mov     [rsp-18h+arg_8], rbx
0x18011ae59  mov     [rsp-18h+arg_10], rsi
0x18011ae5e  push    rbp
0x18011ae5f  push    rdi
0x18011ae60  push    r14
0x18011ae62  mov     rbp, rsp
0x18011ae65  sub     rsp, 70h
0x18011ae69  xor     eax, eax
0x18011ae6b  mov     [rbp+dwRevision], 0
0x18011ae72  mov     [rbp+bOwnerDefaulted], 0
0x18011ae79  xorps   xmm0, xmm0
0x18011ae7c  mov     [rbp+pOwner], 0
0x18011ae84  mov     r14, r8
0x18011ae87  mov     [rbp+pGroup], 0
0x18011ae8f  mov     rbx, rdx
0x18011ae92  mov     [rbp+pControl], ax
0x18011ae96  mov     rsi, rcx
0x18011ae99  mov     [rbp+var_8], rax
0x18011ae9d  movups  [rbp+pSecurityDescriptor], xmm0
0x18011aea1  movups  [rbp+var_18], xmm0
0x18011aea5  test    rcx, rcx
0x18011aea8  jz      loc_18011B050
0x18011aeae  test    rdx, rdx
0x18011aeb1  jz      loc_18011B050
0x18011aeb7  test    r8, r8
0x18011aeba  jz      loc_18011B050
0x18011aec0  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18011aec4  mov     rcx, rbx; pSecurityDescriptor
0x18011aec7  lea     rdx, [rbp+pOwner]; pOwner
0x18011aecb  call    cs:__imp_GetSecurityDescriptorOwner
0x18011aed1  test    eax, eax
0x18011aed3  jnz     short loc_18011AF2B
0x18011aed5  call    cs:__imp_GetLastError
0x18011aedb  mov     ebx, eax
0x18011aedd  mov     rcx, cs:WPP_GLOBAL_Control
0x18011aee4  lea     rdi, WPP_GLOBAL_Control
0x18011aeeb  cmp     rcx, rdi
0x18011aeee  jz      short loc_18011AF17
0x18011aef0  test    dword ptr [rcx+6Ch], 8000000h
0x18011aef7  jz      short loc_18011AF17
0x18011aef9  cmp     byte ptr [rcx+69h], 1
0x18011aefd  jb      short loc_18011AF17
0x18011aeff  mov     edx, 22h ; '"'
0x18011af04  mov     rcx, [rcx+60h]
0x18011af08  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011af0f  mov     r9d, ebx
0x18011af12  call    WPP_SF_d
0x18011af17  test    ebx, ebx
0x18011af19  jle     short loc_18011AF24
0x18011af1b  movzx   ebx, bx
0x18011af1e  or      ebx, 80070000h
0x18011af24  mov     eax, ebx
0x18011af26  jmp     loc_18011B099
0x18011af2b  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18011af2f  mov     rcx, rbx; pSecurityDescriptor
0x18011af32  lea     rdx, [rbp+pGroup]; pGroup
0x18011af36  call    cs:__imp_GetSecurityDescriptorGroup
0x18011af3c  test    eax, eax
0x18011af3e  jnz     short loc_18011AF71
0x18011af40  call    cs:__imp_GetLastError
0x18011af46  mov     ebx, eax
0x18011af48  mov     rcx, cs:WPP_GLOBAL_Control
0x18011af4f  lea     rdi, WPP_GLOBAL_Control
0x18011af56  cmp     rcx, rdi
0x18011af59  jz      short loc_18011AF17
0x18011af5b  test    dword ptr [rcx+6Ch], 8000000h
0x18011af62  jz      short loc_18011AF17
0x18011af64  cmp     byte ptr [rcx+69h], 1
0x18011af68  jb      short loc_18011AF17
0x18011af6a  mov     edx, 23h ; '#'
0x18011af6f  jmp     short loc_18011AF04
0x18011af71  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18011af75  mov     rcx, rbx; pSecurityDescriptor
0x18011af78  lea     rdx, [rbp+pControl]; pControl
0x18011af7c  call    cs:__imp_GetSecurityDescriptorControl
0x18011af82  lea     rdi, WPP_GLOBAL_Control
0x18011af89  test    eax, eax
0x18011af8b  jnz     short loc_18011AFC6
0x18011af8d  call    cs:__imp_GetLastError
0x18011af93  mov     rcx, cs:WPP_GLOBAL_Control
0x18011af9a  cmp     rcx, rdi
0x18011af9d  jz      short loc_18011AFC6
0x18011af9f  test    dword ptr [rcx+6Ch], 8000000h
0x18011afa6  jz      short loc_18011AFC6
0x18011afa8  cmp     byte ptr [rcx+69h], 1
0x18011afac  jb      short loc_18011AFC6
0x18011afae  mov     rcx, [rcx+60h]
0x18011afb2  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011afb9  mov     edx, 24h ; '$'
0x18011afbe  mov     r9d, eax
0x18011afc1  call    WPP_SF_d
0x18011afc6  movzx   r9d, [rbp+pControl]; unsigned __int16
0x18011afcb  lea     rax, [rbp+pSecurityDescriptor]
0x18011afcf  mov     r8, [rbp+pGroup]; pGroup
0x18011afd3  mov     rcx, r14; pDacl
0x18011afd6  mov     rdx, [rbp+pOwner]; pOwner
0x18011afda  mov     [rsp+70h+var_50], rax; void *
0x18011afdf  call    ?PrepareSecurityDescriptor@CTnoRecovery@@CAJPEAU_ACL@@PEAX1G1@Z; CTnoRecovery::PrepareSecurityDescriptor(_ACL *,void *,void *,ushort,void *)
0x18011afe4  test    eax, eax
0x18011afe6  js      loc_18011B099
0x18011afec  lea     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18011aff0  mov     edx, 7; SecurityInformation
0x18011aff5  mov     rcx, rsi; hKey
0x18011aff8  call    cs:__imp_RegSetKeySecurity
0x18011affe  mov     ebx, eax
0x18011b000  test    eax, eax
0x18011b002  jz      short loc_18011B04C
0x18011b004  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b00b  cmp     rcx, rdi
0x18011b00e  jz      loc_18011AF17
0x18011b014  test    dword ptr [rcx+6Ch], 8000000h
0x18011b01b  jz      loc_18011AF17
0x18011b021  cmp     byte ptr [rcx+69h], 1
0x18011b025  jb      loc_18011AF17
0x18011b02b  mov     rcx, [rcx+60h]
0x18011b02f  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b036  mov     edx, 25h ; '%'
0x18011b03b  mov     dword ptr [rsp+70h+var_50], eax
0x18011b03f  mov     r9, rsi
0x18011b042  call    WPP_SF_qD
0x18011b047  jmp     loc_18011AF17
0x18011b04c  xor     eax, eax
0x18011b04e  jmp     short loc_18011B099
0x18011b050  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b057  lea     rdi, WPP_GLOBAL_Control
0x18011b05e  cmp     rcx, rdi
0x18011b061  jz      short loc_18011B094
0x18011b063  test    dword ptr [rcx+6Ch], 8000000h
0x18011b06a  jz      short loc_18011B094
0x18011b06c  cmp     byte ptr [rcx+69h], 1
0x18011b070  jb      short loc_18011B094
0x18011b072  mov     rcx, [rcx+60h]
0x18011b076  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b07d  mov     edx, 21h ; '!'
0x18011b082  mov     [rsp+70h+var_48], r14
0x18011b087  mov     r9, rsi
0x18011b08a  mov     [rsp+70h+var_50], rbx
0x18011b08f  call    WPP_SF_qqq
0x18011b094  mov     eax, 80070057h
0x18011b099  lea     r11, [rsp+70h+var_s0]
0x18011b09e  mov     rbx, [r11+28h]
0x18011b0a2  mov     rsi, [r11+30h]
0x18011b0a6  mov     rsp, r11
0x18011b0a9  pop     r14
0x18011b0ab  pop     rdi
0x18011b0ac  pop     rbp
0x18011b0ad  retn
```
