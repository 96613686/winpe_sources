# CTnoRecovery::GetDaclsFromSecurityDescriptors(void *,void *,_ACL * *,_ACL * *)

- ea: `0x18011b424`
- end: `0x18011b631`
- name: `?GetDaclsFromSecurityDescriptors@CTnoRecovery@@CAJPEAX0PEAPEAU_ACL@@1@Z`
- size: `525`
- prototype: `static int(void *, void *, struct _ACL **, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18011b0b4`

## callees

- `0x180008290`
- `0x18002f328`
- `0x18011b424`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011b541`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011b48a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011b537`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011b48a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011b537`

## pseudocode

```c
__int64 __fastcall CTnoRecovery::GetDaclsFromSecurityDescriptors(
        void *a1,
        void *a2,
        struct _ACL **a3,
        struct _ACL **a4)
{
  DWORD LastError; // ebx
  CHostedCacheMsgEncoding *v8; // rcx
  __int64 v9; // rdx
  CHostedCacheMsgEncoding *v11; // rcx
  __int64 v12; // rdx
  WINBOOL bDaclDefaulted; // [rsp+40h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-20h] BYREF
  PACL v15; // [rsp+50h] [rbp-18h] BYREF
  WINBOOL bDaclPresent; // [rsp+90h] [rbp+28h] BYREF

  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  v15 = 0;
  if ( a1 && a2 && a3 && a4 )
  {
    if ( !GetSecurityDescriptorDacl(a1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v9 = 29;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v8 + 12), v9, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids, LastError);
        goto LABEL_11;
      }
      goto LABEL_11;
    }
    if ( bDaclPresent )
    {
      if ( !GetSecurityDescriptorDacl(a2, &bDaclPresent, &v15, &bDaclDefaulted) )
      {
        LastError = GetLastError();
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v9 = 31;
          goto LABEL_10;
        }
LABEL_11:
        if ( (int)LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return LastError;
      }
      if ( bDaclPresent )
      {
        *a3 = pDacl;
        *a4 = v15;
        return 0;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return 2147943568LL;
      }
      v12 = 32;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return 2147943568LL;
      }
      v12 = 30;
    }
    WPP_SF_d(*((_QWORD *)v11 + 12), v12, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids, 0);
    return 2147943568LL;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_qqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      28,
      WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids,
      a1,
      a2,
      a3,
      a4);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18011b424  push    rbp
0x18011b426  push    rbx
0x18011b427  push    rsi
0x18011b428  push    rdi
0x18011b429  mov     rbp, rsp
0x18011b42c  sub     rsp, 68h
0x18011b430  mov     [rbp+bDaclPresent], 0
0x18011b437  mov     rbx, r9
0x18011b43a  mov     [rbp+bDaclDefaulted], 0
0x18011b441  mov     rdi, r8
0x18011b444  mov     [rbp+pDacl], 0
0x18011b44c  mov     rsi, rdx
0x18011b44f  mov     [rbp+var_18], 0
0x18011b457  mov     r10, rcx
0x18011b45a  test    rcx, rcx
0x18011b45d  jz      loc_18011B5DA
0x18011b463  test    rdx, rdx
0x18011b466  jz      loc_18011B5DA
0x18011b46c  test    r8, r8
0x18011b46f  jz      loc_18011B5DA
0x18011b475  test    rbx, rbx
0x18011b478  jz      loc_18011B5DA
0x18011b47e  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18011b482  lea     r8, [rbp+pDacl]; pDacl
0x18011b486  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18011b48a  call    cs:__imp_GetSecurityDescriptorDacl
0x18011b490  test    eax, eax
0x18011b492  jnz     short loc_18011B4EA
0x18011b494  call    cs:__imp_GetLastError
0x18011b49a  mov     ebx, eax
0x18011b49c  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b4a3  lea     rax, WPP_GLOBAL_Control
0x18011b4aa  cmp     rcx, rax
0x18011b4ad  jz      short loc_18011B4D6
0x18011b4af  test    dword ptr [rcx+6Ch], 8000000h
0x18011b4b6  jz      short loc_18011B4D6
0x18011b4b8  cmp     byte ptr [rcx+69h], 1
0x18011b4bc  jb      short loc_18011B4D6
0x18011b4be  mov     edx, 1Dh
0x18011b4c3  mov     rcx, [rcx+60h]
0x18011b4c7  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b4ce  mov     r9d, ebx
0x18011b4d1  call    WPP_SF_d
0x18011b4d6  test    ebx, ebx
0x18011b4d8  jle     short loc_18011B4E3
0x18011b4da  movzx   ebx, bx
0x18011b4dd  or      ebx, 80070000h
0x18011b4e3  mov     eax, ebx
0x18011b4e5  jmp     loc_18011B628
0x18011b4ea  cmp     [rbp+bDaclPresent], 0
0x18011b4ee  jnz     short loc_18011B528
0x18011b4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b4f7  lea     rax, WPP_GLOBAL_Control
0x18011b4fe  cmp     rcx, rax
0x18011b501  jz      loc_18011B5C1
0x18011b507  test    dword ptr [rcx+6Ch], 8000000h
0x18011b50e  jz      loc_18011B5C1
0x18011b514  cmp     byte ptr [rcx+69h], 1
0x18011b518  jb      loc_18011B5C1
0x18011b51e  mov     edx, 1Eh
0x18011b523  jmp     loc_18011B5AE
0x18011b528  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18011b52c  mov     rcx, rsi; pSecurityDescriptor
0x18011b52f  lea     r8, [rbp+var_18]; pDacl
0x18011b533  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18011b537  call    cs:__imp_GetSecurityDescriptorDacl
0x18011b53d  test    eax, eax
0x18011b53f  jnz     short loc_18011B581
0x18011b541  call    cs:__imp_GetLastError
0x18011b547  mov     ebx, eax
0x18011b549  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b550  lea     rax, WPP_GLOBAL_Control
0x18011b557  cmp     rcx, rax
0x18011b55a  jz      loc_18011B4D6
0x18011b560  test    dword ptr [rcx+6Ch], 8000000h
0x18011b567  jz      loc_18011B4D6
0x18011b56d  cmp     byte ptr [rcx+69h], 1
0x18011b571  jb      loc_18011B4D6
0x18011b577  mov     edx, 1Fh
0x18011b57c  jmp     loc_18011B4C3
0x18011b581  cmp     [rbp+bDaclPresent], 0
0x18011b585  jnz     short loc_18011B5C8
0x18011b587  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b58e  lea     rax, WPP_GLOBAL_Control
0x18011b595  cmp     rcx, rax
0x18011b598  jz      short loc_18011B5C1
0x18011b59a  test    dword ptr [rcx+6Ch], 8000000h
0x18011b5a1  jz      short loc_18011B5C1
0x18011b5a3  cmp     byte ptr [rcx+69h], 1
0x18011b5a7  jb      short loc_18011B5C1
0x18011b5a9  mov     edx, 20h ; ' '
0x18011b5ae  mov     rcx, [rcx+60h]
0x18011b5b2  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b5b9  xor     r9d, r9d
0x18011b5bc  call    WPP_SF_d
0x18011b5c1  mov     eax, 80070490h
0x18011b5c6  jmp     short loc_18011B628
0x18011b5c8  mov     rax, [rbp+pDacl]
0x18011b5cc  mov     [rdi], rax
0x18011b5cf  mov     rax, [rbp+var_18]
0x18011b5d3  mov     [rbx], rax
0x18011b5d6  xor     eax, eax
0x18011b5d8  jmp     short loc_18011B628
0x18011b5da  mov     rcx, cs:WPP_GLOBAL_Control
0x18011b5e1  lea     rax, WPP_GLOBAL_Control
0x18011b5e8  cmp     rcx, rax
0x18011b5eb  jz      short loc_18011B623
0x18011b5ed  test    dword ptr [rcx+6Ch], 8000000h
0x18011b5f4  jz      short loc_18011B623
0x18011b5f6  cmp     byte ptr [rcx+69h], 1
0x18011b5fa  jb      short loc_18011B623
0x18011b5fc  mov     rcx, [rcx+60h]
0x18011b600  lea     r8, WPP_88ceccd027793c6cfd811b6c21a04040_Traceguids
0x18011b607  mov     [rsp+68h+var_38], rbx
0x18011b60c  mov     edx, 1Ch
0x18011b611  mov     [rsp+68h+var_40], rdi
0x18011b616  mov     r9, r10
0x18011b619  mov     [rsp+68h+var_48], rsi
0x18011b61e  call    WPP_SF_qqqq
0x18011b623  mov     eax, 80070057h
0x18011b628  add     rsp, 68h
0x18011b62c  pop     rdi
0x18011b62d  pop     rsi
0x18011b62e  pop     rbx
0x18011b62f  pop     rbp
0x18011b630  retn
```
