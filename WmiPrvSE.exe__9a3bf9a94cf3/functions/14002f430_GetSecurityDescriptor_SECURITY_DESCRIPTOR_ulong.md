# GetSecurityDescriptor(_SECURITY_DESCRIPTOR &,ulong)

- ea: `0x14002f430`
- end: `0x14002f94f`
- name: `?GetSecurityDescriptor@@YAJAEAU_SECURITY_DESCRIPTOR@@K@Z`
- size: `1311`
- prototype: `__int64 __fastcall(struct _SECURITY_DESCRIPTOR *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140029a60`

## callees

- `0x14000a0f0`
- `0x14000a530`
- `0x1400234b8`
- `0x14002f430`
- `0x140046430`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002f4c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002f56a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002f65f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002f717`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002f4c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002f56a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002f65f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002f717`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002f86d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002f86d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14002f462`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14002f462`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002f4b5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002f55c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002f64b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002f705`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002f4b5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002f55c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002f64b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14002f705`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002f4fc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002f597`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002f68e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002f744`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002f4fc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002f597`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002f68e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14002f744`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002f7af`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002f7af`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002f7da`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002f806`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002f830`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002f859`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002f7da`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002f806`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002f830`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002f859`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002f8a7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002f8b6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002f8c5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002f8d4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002f8a7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002f8b6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002f8c5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14002f8d4`
- `wbemcomn!GetMemLogObject` at `0x14002f8e5`
- `wbemcomn!GetMemLogObject` at `0x14002f8e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002f8f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002f8f0`

## pseudocode

```c
__int64 __fastcall GetSecurityDescriptor(struct _SECURITY_DESCRIPTOR *a1)
{
  _WORD *v1; // r15
  DWORD LengthSid; // edi
  DWORD v3; // r12d
  char *v4; // rax
  _DWORD *v5; // r14
  int v6; // ebx
  _DWORD *v7; // r13
  DWORD v8; // edi
  char *v9; // rax
  _WORD *v10; // rdi
  char *v11; // rax
  char *v12; // rax
  unsigned __int16 v13; // ax
  struct _ACL *v14; // rax
  struct _ACL *v15; // r12
  DWORD v16; // esi
  CMemoryLog *MemLogObject; // rax
  DWORD nDestinationSidLength; // [rsp+60h] [rbp-59h]
  DWORD nDestinationSidLengtha; // [rsp+60h] [rbp-59h]
  unsigned int nDestinationSidLengthb; // [rsp+60h] [rbp-59h]
  PSID v22; // [rsp+68h] [rbp-51h] BYREF
  PSID v23; // [rsp+70h] [rbp-49h] BYREF
  PSID pSid; // [rsp+78h] [rbp-41h] BYREF
  SIZE_T v25; // [rsp+80h] [rbp-39h]
  SIZE_T v26; // [rsp+88h] [rbp-31h]
  PSID pSourceSid; // [rsp+90h] [rbp-29h] BYREF
  DWORD nAceListLength; // [rsp+98h] [rbp-21h]
  DWORD v29; // [rsp+9Ch] [rbp-1Dh]
  SIZE_T v30; // [rsp+A0h] [rbp-19h]
  SIZE_T v31; // [rsp+A8h] [rbp-11h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+B0h] [rbp-9h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v34; // [rsp+C0h] [rbp+7h] BYREF

  pSecurityDescriptor = a1;
  v1 = 0;
  if ( !InitializeSecurityDescriptor(a1, 1u) )
  {
    v6 = -2147217398;
LABEL_62:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
    goto LABEL_63;
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSourceSid = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSourceSid) )
  {
    v6 = -2147217402;
    pSid = 0;
    v23 = 0;
    v22 = 0;
    goto LABEL_51;
  }
  LengthSid = GetLengthSid(pSourceSid);
  v3 = (unsigned __int16)(LengthSid + 8);
  v31 = (unsigned __int16)(LengthSid + 8);
  v4 = (char *)operator new(v31);
  v5 = v4;
  if ( v4 )
  {
    v6 = 0;
    CopySid(LengthSid, v4 + 8, pSourceSid);
    v5[1] = 983071;
    *(_WORD *)v5 = 768;
    *((_WORD *)v5 + 1) = v3;
  }
  else
  {
    v6 = -2147217402;
  }
  pSid = 0;
  v7 = 0;
  if ( v6 < 0 )
  {
    LOWORD(v26) = 0;
    v31 = (unsigned __int16)(LengthSid + 8);
  }
  else
  {
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      v23 = 0;
      goto LABEL_13;
    }
    v8 = GetLengthSid(pSid);
    v26 = (unsigned __int16)(v8 + 8);
    v9 = (char *)operator new(v26);
    v7 = v9;
    if ( v9 )
    {
      CopySid(v8, v9 + 8, pSid);
      v7[1] = 1245215;
      *(_WORD *)v7 = 768;
      *((_WORD *)v7 + 1) = v8 + 8;
    }
    else
    {
      v6 = -2147217402;
    }
    v1 = 0;
  }
  v23 = 0;
  if ( v6 < 0 )
  {
    LOWORD(v25) = 0;
    goto LABEL_30;
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &v23) )
  {
    nDestinationSidLength = GetLengthSid(v23);
    v25 = (unsigned __int16)(nDestinationSidLength + 8);
    v11 = (char *)operator new(v25);
    v1 = v11;
    if ( v11 )
    {
      CopySid(nDestinationSidLength, v11 + 8, v23);
      v1[1] = nDestinationSidLength + 8;
      *((_DWORD *)v1 + 1) = 1245215;
      v10 = 0;
      *v1 = 768;
      v22 = 0;
      *(_DWORD *)v34.Value = 0;
      *(_WORD *)&v34.Value[4] = 256;
      if ( AllocateAndInitializeSid(&v34, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v22) )
      {
        nDestinationSidLengtha = GetLengthSid(v22);
        v30 = (unsigned __int16)(nDestinationSidLengtha + 8);
        v12 = (char *)operator new(v30);
        v10 = v12;
        if ( v12 )
        {
          CopySid(nDestinationSidLengtha, v12 + 8, v22);
          v13 = v30;
          v10[1] = v30;
          *((_DWORD *)v10 + 1) = 131093;
          *v10 = 768;
        }
        else
        {
          v13 = v30;
          v6 = -2147217402;
        }
        if ( v6 < 0 )
          goto LABEL_15;
        v29 = v13;
        nAceListLength = v3;
        nDestinationSidLengthb = v3 + 8 + (unsigned __int16)v26 + (unsigned __int16)v25 + v13;
        v14 = (struct _ACL *)operator new(nDestinationSidLengthb);
        v15 = v14;
        if ( v14 )
        {
          if ( InitializeAcl(v14, nDestinationSidLengthb, 2u) )
          {
            v16 = 0;
            if ( (_WORD)v31 )
              v16 = AddAce(v15, 2u, 0, v5, nAceListLength);
            if ( (_WORD)v25 && AddAce(v15, 2u, v16, v1, (unsigned __int16)v25) )
              ++v16;
            if ( (_WORD)v26 && AddAce(v15, 2u, v16, v7, (unsigned __int16)v26) )
              ++v16;
            if ( (_WORD)v30 )
              AddAce(v15, 2u, v16, v10, v29);
            if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v15, 0) )
            {
              operator delete(v15);
              v6 = -2147217398;
            }
          }
          goto LABEL_15;
        }
      }
      goto LABEL_14;
    }
    v6 = -2147217402;
LABEL_30:
    v22 = 0;
    v10 = 0;
    goto LABEL_15;
  }
LABEL_13:
  v22 = 0;
  v10 = 0;
LABEL_14:
  v6 = -2147217402;
LABEL_15:
  if ( v5 )
    operator delete(v5);
  if ( v1 )
    operator delete(v1);
  if ( v7 )
    operator delete(v7);
  if ( v10 )
    operator delete(v10);
LABEL_51:
  if ( pSourceSid )
    FreeSid(pSourceSid);
  if ( v23 )
    FreeSid(v23);
  if ( pSid )
    FreeSid(pSid);
  if ( v22 )
    FreeSid(v22);
  if ( v6 < 0 )
    goto LABEL_62;
LABEL_63:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002f430  push    rbp
0x14002f432  push    rbx
0x14002f433  push    rsi
0x14002f434  push    rdi
0x14002f435  push    r12
0x14002f437  push    r13
0x14002f439  push    r14
0x14002f43b  push    r15
0x14002f43d  lea     rbp, [rsp-1Fh]
0x14002f442  sub     rsp, 0D8h
0x14002f449  mov     rax, cs:__security_cookie
0x14002f450  xor     rax, rsp
0x14002f453  mov     [rbp+57h+var_48], rax
0x14002f457  mov     ebx, 1
0x14002f45c  mov     [rbp+57h+pSecurityDescriptor], rcx
0x14002f460  mov     edx, ebx; dwRevision
0x14002f462  call    cs:__imp_InitializeSecurityDescriptor
0x14002f468  xor     r15d, r15d
0x14002f46b  test    eax, eax
0x14002f46d  jz      loc_14002F8E0
0x14002f473  lea     rax, [rbp+57h+pSourceSid]
0x14002f477  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x14002f47b  mov     [rsp+110h+pSid], rax; pSid
0x14002f480  lea     r8d, [rbx+11h]; nSubAuthority0
0x14002f484  mov     [rsp+110h+nSubAuthority7], r15d; nSubAuthority7
0x14002f489  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14002f48d  mov     [rsp+110h+nSubAuthority6], r15d; nSubAuthority6
0x14002f492  xor     r9d, r9d; nSubAuthority1
0x14002f495  mov     [rsp+110h+nSubAuthority5], r15d; nSubAuthority5
0x14002f49a  mov     dl, bl; nSubAuthorityCount
0x14002f49c  mov     [rsp+110h+nSubAuthority4], r15d; nSubAuthority4
0x14002f4a1  mov     [rsp+110h+nSubAuthority3], r15d; nSubAuthority3
0x14002f4a6  mov     [rsp+110h+nSubAuthority2], r15d; nSubAuthority2
0x14002f4ab  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14002f4b1  mov     [rbp+57h+pSourceSid], r15
0x14002f4b5  call    cs:__imp_AllocateAndInitializeSid
0x14002f4bb  test    eax, eax
0x14002f4bd  jz      loc_14002F88D
0x14002f4c3  mov     rcx, [rbp+57h+pSourceSid]; pSid
0x14002f4c7  call    cs:__imp_GetLengthSid
0x14002f4cd  mov     edi, eax
0x14002f4cf  lea     ecx, [rax+8]
0x14002f4d2  movzx   r12d, cx
0x14002f4d6  mov     ecx, r12d; dwBytes
0x14002f4d9  mov     [rbp+57h+var_68], r12
0x14002f4dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002f4e2  mov     r14, rax
0x14002f4e5  mov     esi, 80041006h
0x14002f4ea  test    rax, rax
0x14002f4ed  jz      short loc_14002F517
0x14002f4ef  mov     r8, [rbp+57h+pSourceSid]; pSourceSid
0x14002f4f3  lea     rdx, [rax+8]; pDestinationSid
0x14002f4f7  mov     ecx, edi; nDestinationSidLength
0x14002f4f9  mov     ebx, r15d
0x14002f4fc  call    cs:__imp_CopySid
0x14002f502  mov     dword ptr [r14+4], 0F001Fh
0x14002f50a  mov     word ptr [r14], 300h
0x14002f510  mov     [r14+2], r12w
0x14002f515  jmp     short loc_14002F519
0x14002f517  mov     ebx, esi
0x14002f519  mov     [rbp+57h+var_98], r15
0x14002f51d  mov     r13, r15
0x14002f520  test    ebx, ebx
0x14002f522  js      loc_14002F606
0x14002f528  lea     rax, [rbp+57h+var_98]
0x14002f52c  xor     r9d, r9d; nSubAuthority1
0x14002f52f  mov     [rsp+110h+pSid], rax; pSid
0x14002f534  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14002f538  mov     [rsp+110h+nSubAuthority7], r15d; nSubAuthority7
0x14002f53d  mov     dl, 1; nSubAuthorityCount
0x14002f53f  mov     [rsp+110h+nSubAuthority6], r15d; nSubAuthority6
0x14002f544  mov     [rsp+110h+nSubAuthority5], r15d; nSubAuthority5
0x14002f549  lea     r8d, [r9+13h]; nSubAuthority0
0x14002f54d  mov     [rsp+110h+nSubAuthority4], r15d; nSubAuthority4
0x14002f552  mov     [rsp+110h+nSubAuthority3], r15d; nSubAuthority3
0x14002f557  mov     [rsp+110h+nSubAuthority2], r15d; nSubAuthority2
0x14002f55c  call    cs:__imp_AllocateAndInitializeSid
0x14002f562  test    eax, eax
0x14002f564  jz      short loc_14002F5BA
0x14002f566  mov     rcx, [rbp+57h+var_98]; pSid
0x14002f56a  call    cs:__imp_GetLengthSid
0x14002f570  mov     edi, eax
0x14002f572  lea     ecx, [rax+8]
0x14002f575  movzx   r15d, cx
0x14002f579  mov     ecx, r15d; dwBytes
0x14002f57c  mov     [rbp+57h+var_88], r15
0x14002f580  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002f585  mov     r13, rax
0x14002f588  test    rax, rax
0x14002f58b  jz      short loc_14002F5B3
0x14002f58d  mov     r8, [rbp+57h+var_98]; pSourceSid
0x14002f591  lea     rdx, [rax+8]; pDestinationSid
0x14002f595  mov     ecx, edi; nDestinationSidLength
0x14002f597  call    cs:__imp_CopySid
0x14002f59d  mov     dword ptr [r13+4], 13001Fh
0x14002f5a5  mov     word ptr [r13+0], 300h
0x14002f5ac  mov     [r13+2], r15w
0x14002f5b1  jmp     short loc_14002F5B5
0x14002f5b3  mov     ebx, esi
0x14002f5b5  xor     r15d, r15d
0x14002f5b8  jmp     short loc_14002F60F
0x14002f5ba  mov     [rbp+57h+var_A0], r15
0x14002f5be  xor     ecx, ecx
0x14002f5c0  mov     [rbp+57h+var_A8], rcx
0x14002f5c4  mov     rdi, rcx
0x14002f5c7  mov     ebx, esi
0x14002f5c9  test    r14, r14
0x14002f5cc  jz      short loc_14002F5D6
0x14002f5ce  mov     rcx, r14; lpMem
0x14002f5d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002f5d6  test    r15, r15
0x14002f5d9  jz      short loc_14002F5E3
0x14002f5db  mov     rcx, r15; lpMem
0x14002f5de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002f5e3  test    r13, r13
0x14002f5e6  jz      short loc_14002F5F0
0x14002f5e8  mov     rcx, r13; lpMem
0x14002f5eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002f5f0  test    rdi, rdi
0x14002f5f3  jz      loc_14002F89E
0x14002f5f9  mov     rcx, rdi; lpMem
0x14002f5fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002f601  jmp     loc_14002F89E
0x14002f606  mov     word ptr [rbp+57h+var_88], r15w
0x14002f60b  mov     [rbp+57h+var_68], r12
0x14002f60f  xor     ecx, ecx
0x14002f611  mov     [rbp+57h+var_A0], r15
0x14002f615  test    ebx, ebx
0x14002f617  js      loc_14002F6B5
0x14002f61d  lea     rax, [rbp+57h+var_A0]
0x14002f621  xor     r9d, r9d; nSubAuthority1
0x14002f624  mov     [rsp+110h+pSid], rax; pSid
0x14002f629  lea     r8d, [rcx+14h]; nSubAuthority0
0x14002f62d  mov     [rsp+110h+nSubAuthority7], ecx; nSubAuthority7
0x14002f631  mov     dl, 1; nSubAuthorityCount
0x14002f633  mov     [rsp+110h+nSubAuthority6], ecx; nSubAuthority6
0x14002f637  mov     [rsp+110h+nSubAuthority5], ecx; nSubAuthority5
0x14002f63b  mov     [rsp+110h+nSubAuthority4], ecx; nSubAuthority4
0x14002f63f  mov     [rsp+110h+nSubAuthority3], ecx; nSubAuthority3
0x14002f643  mov     [rsp+110h+nSubAuthority2], ecx; nSubAuthority2
0x14002f647  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14002f64b  call    cs:__imp_AllocateAndInitializeSid
0x14002f651  xor     ecx, ecx
0x14002f653  test    eax, eax
0x14002f655  jz      loc_14002F5C0
0x14002f65b  mov     rcx, [rbp+57h+var_A0]; pSid
0x14002f65f  call    cs:__imp_GetLengthSid
0x14002f665  mov     [rbp+57h+nDestinationSidLength], eax
0x14002f668  lea     ecx, [rax+8]
0x14002f66b  movzx   edi, cx
0x14002f66e  mov     ecx, edi; dwBytes
0x14002f670  mov     [rbp+57h+var_90], rdi
0x14002f674  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002f679  xor     ecx, ecx
0x14002f67b  mov     r15, rax
0x14002f67e  test    rax, rax
0x14002f681  jz      short loc_14002F6B1
0x14002f683  mov     r8, [rbp+57h+var_A0]; pSourceSid
0x14002f687  lea     rdx, [rax+8]; pDestinationSid
0x14002f68b  mov     ecx, [rbp+57h+nDestinationSidLength]; nDestinationSidLength
0x14002f68e  call    cs:__imp_CopySid
0x14002f694  xor     ecx, ecx
0x14002f696  mov     [r15+2], di
0x14002f69b  mov     dword ptr [r15+4], 13001Fh
0x14002f6a3  mov     edi, ecx
0x14002f6a5  mov     word ptr [r15], 300h
0x14002f6ab  mov     [rbp+57h+var_A8], rcx
0x14002f6af  jmp     short loc_14002F6C8
0x14002f6b1  mov     ebx, esi
0x14002f6b3  jmp     short loc_14002F6B9
0x14002f6b5  mov     word ptr [rbp+57h+var_90], cx
0x14002f6b9  mov     [rbp+57h+var_A8], rcx
0x14002f6bd  mov     rdi, rcx
0x14002f6c0  test    ebx, ebx
0x14002f6c2  js      loc_14002F5C9
0x14002f6c8  lea     rax, [rbp+57h+var_A8]
0x14002f6cc  mov     dword ptr [rbp+57h+var_50.Value], 0
0x14002f6d3  mov     [rsp+110h+pSid], rax; pSid
0x14002f6d8  mov     edx, 1; nSubAuthorityCount
0x14002f6dd  mov     [rsp+110h+nSubAuthority7], ecx; nSubAuthority7
0x14002f6e1  xor     r9d, r9d; nSubAuthority1
0x14002f6e4  mov     [rsp+110h+nSubAuthority6], ecx; nSubAuthority6
0x14002f6e8  xor     r8d, r8d; nSubAuthority0
0x14002f6eb  mov     [rsp+110h+nSubAuthority5], ecx; nSubAuthority5
0x14002f6ef  mov     [rsp+110h+nSubAuthority4], ecx; nSubAuthority4
0x14002f6f3  mov     [rsp+110h+nSubAuthority3], ecx; nSubAuthority3
0x14002f6f7  mov     [rsp+110h+nSubAuthority2], ecx; nSubAuthority2
0x14002f6fb  lea     rcx, [rbp+57h+var_50]; pIdentifierAuthority
0x14002f6ff  mov     word ptr [rbp+57h+var_50.Value+4], 100h
0x14002f705  call    cs:__imp_AllocateAndInitializeSid
0x14002f70b  test    eax, eax
0x14002f70d  jz      loc_14002F5C7
0x14002f713  mov     rcx, [rbp+57h+var_A8]; pSid
0x14002f717  call    cs:__imp_GetLengthSid
0x14002f71d  mov     [rbp+57h+nDestinationSidLength], eax
0x14002f720  lea     ecx, [rax+8]
0x14002f723  movzx   eax, cx
0x14002f726  mov     ecx, eax; dwBytes
0x14002f728  mov     [rbp+57h+var_70], rax
0x14002f72c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002f731  mov     rdi, rax
0x14002f734  test    rax, rax
0x14002f737  jz      short loc_14002F760
0x14002f739  mov     r8, [rbp+57h+var_A8]; pSourceSid
0x14002f73d  lea     rdx, [rax+8]; pDestinationSid
0x14002f741  mov     ecx, [rbp+57h+nDestinationSidLength]; nDestinationSidLength
0x14002f744  call    cs:__imp_CopySid
0x14002f74a  mov     rax, [rbp+57h+var_70]
0x14002f74e  mov     [rdi+2], ax
0x14002f752  mov     dword ptr [rdi+4], 20015h
0x14002f759  mov     word ptr [rdi], 300h
0x14002f75e  jmp     short loc_14002F766
0x14002f760  mov     rax, [rbp+57h+var_70]
0x14002f764  mov     ebx, esi
0x14002f766  test    ebx, ebx
0x14002f768  js      loc_14002F5C9
0x14002f76e  movzx   edx, word ptr [rbp+57h+var_90]
0x14002f772  mov     ecx, r12d
0x14002f775  movzx   r8d, word ptr [rbp+57h+var_88]
0x14002f77a  movzx   eax, ax
0x14002f77d  mov     [rbp+57h+var_74], eax
0x14002f780  add     eax, edx
0x14002f782  mov     [rbp+57h+nAceListLength], ecx
0x14002f785  add     eax, r8d
0x14002f788  add     ecx, 8
0x14002f78b  add     eax, ecx
0x14002f78d  mov     ecx, eax; dwBytes
0x14002f78f  mov     [rbp+57h+nDestinationSidLength], eax
0x14002f792  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002f797  mov     r12, rax
0x14002f79a  test    rax, rax
0x14002f79d  jz      loc_14002F5C7
0x14002f7a3  mov     edx, [rbp+57h+nDestinationSidLength]; nAclLength
0x14002f7a6  mov     r8d, 2; dwAclRevision
0x14002f7ac  mov     rcx, rax; pAcl
0x14002f7af  call    cs:__imp_InitializeAcl
0x14002f7b5  xor     ecx, ecx
0x14002f7b7  test    eax, eax
0x14002f7b9  jz      loc_14002F5C9
0x14002f7bf  mov     esi, ecx
0x14002f7c1  cmp     word ptr [rbp+57h+var_68], cx
0x14002f7c5  jz      short loc_14002F7EA
0x14002f7c7  mov     eax, [rbp+57h+nAceListLength]
0x14002f7ca  lea     edx, [rcx+2]; dwAceRevision
0x14002f7cd  mov     rcx, r12; pAcl
0x14002f7d0  mov     [rsp+110h+nSubAuthority2], eax; nAceListLength
0x14002f7d4  mov     r9, r14; pAceList
0x14002f7d7  xor     r8d, r8d; dwStartingAceIndex
0x14002f7da  call    cs:__imp_AddAce
0x14002f7e0  xor     ecx, ecx
0x14002f7e2  test    eax, eax
0x14002f7e4  lea     eax, [rcx+1]
0x14002f7e7  cmovnz  esi, eax
0x14002f7ea  cmp     word ptr [rbp+57h+var_90], cx
0x14002f7ee  jz      short loc_14002F814
0x14002f7f0  movzx   eax, word ptr [rbp+57h+var_90]
0x14002f7f4  mov     r9, r15; pAceList
0x14002f7f7  mov     r8d, esi; dwStartingAceIndex
0x14002f7fa  mov     [rsp+110h+nSubAuthority2], eax; nAceListLength
0x14002f7fe  mov     edx, 2; dwAceRevision
0x14002f803  mov     rcx, r12; pAcl
0x14002f806  call    cs:__imp_AddAce
0x14002f80c  xor     ecx, ecx
0x14002f80e  test    eax, eax
0x14002f810  jz      short loc_14002F814
0x14002f812  inc     esi
0x14002f814  cmp     word ptr [rbp+57h+var_88], cx
0x14002f818  jz      short loc_14002F83E
0x14002f81a  movzx   eax, word ptr [rbp+57h+var_88]
0x14002f81e  mov     r9, r13; pAceList
0x14002f821  mov     r8d, esi; dwStartingAceIndex
0x14002f824  mov     [rsp+110h+nSubAuthority2], eax; nAceListLength
0x14002f828  mov     edx, 2; dwAceRevision
0x14002f82d  mov     rcx, r12; pAcl
0x14002f830  call    cs:__imp_AddAce
0x14002f836  xor     ecx, ecx
0x14002f838  test    eax, eax
0x14002f83a  jz      short loc_14002F83E
0x14002f83c  inc     esi
0x14002f83e  cmp     word ptr [rbp+57h+var_70], cx
0x14002f842  jz      short loc_14002F85F
0x14002f844  mov     eax, [rbp+57h+var_74]
0x14002f847  mov     r9, rdi; pAceList
0x14002f84a  mov     r8d, esi; dwStartingAceIndex
0x14002f84d  mov     [rsp+110h+nSubAuthority2], eax; nAceListLength
0x14002f851  mov     edx, 2; dwAceRevision
0x14002f856  mov     rcx, r12; pAcl
0x14002f859  call    cs:__imp_AddAce
0x14002f85f  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14002f863  xor     r9d, r9d; bDaclDefaulted
0x14002f866  mov     r8, r12; pDacl
0x14002f869  lea     edx, [r9+1]; bDaclPresent
0x14002f86d  call    cs:__imp_SetSecurityDescriptorDacl
0x14002f873  test    eax, eax
0x14002f875  jnz     loc_14002F5C9
0x14002f87b  mov     rcx, r12; lpMem
0x14002f87e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002f883  mov     ebx, 8004100Ah
0x14002f888  jmp     loc_14002F5C9
0x14002f88d  mov     ebx, 80041006h
  ... truncated ...
```
