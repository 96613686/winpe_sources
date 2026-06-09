# ept_map_auth

- ea: `0x180003810`
- end: `0x180003a14`
- name: `ept_map_auth`
- size: `516`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, __int64, __int64 *, __int64 *, PSID pSid, _QWORD *, int, _DWORD *, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003750`
- `0x1800037b0`

## callees

- `0x180003810`
- `0x180003a1c`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180003883`
- `RPCRT4!RpcRaiseException` at `0x1800039ea`
- `RPCRT4!RpcRaiseException` at `0x180003883`
- `RPCRT4!RpcRaiseException` at `0x1800039ea`
- `RPCRT4!I_RpcFree` at `0x1800039bd`
- `RPCRT4!I_RpcFree` at `0x180003a09`
- `RPCRT4!I_RpcFree` at `0x18000aa51`
- `RPCRT4!I_RpcFree` at `0x1800039bd`
- `RPCRT4!I_RpcFree` at `0x180003a09`
- `RPCRT4!I_RpcFree` at `0x18000aa51`
- `RPCRT4!I_RpcAllocate` at `0x1800038bd`
- `RPCRT4!I_RpcAllocate` at `0x1800038bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003857`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003857`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa64`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800038fa`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800038fa`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180003944`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180003944`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800038a3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800038a3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180003916`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180003916`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800038db`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800038db`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000392d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000392d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800038b0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800038b0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003839`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003874`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003839`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180003874`

## pseudocode

```c
void __fastcall ept_map_auth(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        __int64 *a3,
        __int64 *a4,
        PSID pSid,
        _QWORD *a6,
        int a7,
        _DWORD *a8,
        __int64 a9,
        _DWORD *a10)
{
  _QWORD *pSecurityDescriptor; // rbx
  unsigned int v14; // r14d
  struct _ACL *v15; // rax
  struct _ACL *v16; // rsi
  int v17; // edi
  void *v18; // rcx

  if ( !pSid )
  {
    pSecurityDescriptor = 0;
    goto LABEL_16;
  }
  if ( !IsValidSid(pSid) )
    goto LABEL_5;
  pSecurityDescriptor = HeapAlloc(hEpMapperHeap, 0, 0x28u);
  if ( !pSecurityDescriptor )
    RpcRaiseException(14);
  if ( !IsValidSid(pSid) || !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
LABEL_5:
    RpcRaiseException(1752);
  v14 = GetLengthSid(pSid) + 88;
  v15 = (struct _ACL *)I_RpcAllocate(v14);
  v16 = v15;
  if ( v15 )
  {
    if ( InitializeAcl(v15, v14, 2u)
      && AddAccessAllowedAce(v16, 2u, 0x20000u, pSid)
      && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v16, 0)
      && SetSecurityDescriptorGroup(pSecurityDescriptor, pSid, 0)
      && SetSecurityDescriptorOwner(pSecurityDescriptor, pSid, 0) )
    {
      v17 = 0;
      goto LABEL_15;
    }
    v17 = 382312653;
  }
  else
  {
    v17 = 14;
  }
  if ( v16 )
    I_RpcFree(v16);
LABEL_15:
  if ( v17 )
    goto LABEL_5;
LABEL_16:
  ept_map_auth_sd(pAsync, a2, a3, a4, pSecurityDescriptor, a6, a7, a8, a9, a10);
  if ( pSecurityDescriptor )
  {
    v18 = (void *)pSecurityDescriptor[4];
    if ( v18 )
      I_RpcFree(v18);
    HeapFree(hEpMapperHeap, 0, pSecurityDescriptor);
  }
}

```

## disassembly

```asm
0x180003810  push    rbx
0x180003812  push    rsi
0x180003813  push    rdi
0x180003814  push    r12
0x180003816  push    r13
0x180003818  push    r14
0x18000381a  push    r15
0x18000381c  sub     rsp, 50h
0x180003820  mov     r15, r9
0x180003823  mov     r12, r8
0x180003826  mov     r13, rcx
0x180003829  mov     rdi, [rsp+88h+pSid]
0x180003831  test    rdi, rdi
0x180003834  jz      short loc_18000388A
0x180003836  mov     rcx, rdi; pSid
0x180003839  call    cs:__imp_IsValidSid
0x18000383f  test    eax, eax
0x180003841  jz      short loc_18000387E
0x180003843  test    rdi, rdi
0x180003846  jz      short loc_18000388A
0x180003848  xor     edx, edx; dwFlags
0x18000384a  mov     r8d, 28h ; '('; dwBytes
0x180003850  mov     rcx, cs:hEpMapperHeap; hHeap
0x180003857  call    cs:__imp_HeapAlloc
0x18000385d  mov     rbx, rax
0x180003860  mov     [rsp+88h+pSid], rax
0x180003868  test    rax, rax
0x18000386b  jz      loc_1800039E5
0x180003871  mov     rcx, rdi; pSid
0x180003874  call    cs:__imp_IsValidSid
0x18000387a  test    eax, eax
0x18000387c  jnz     short loc_18000389B
0x18000387e  mov     ecx, 6D8h; exception
0x180003883  call    cs:__imp_RpcRaiseException
0x180003889  int     3; Trap to Debugger
0x18000388a  xor     edi, edi
0x18000388c  mov     ebx, edi
0x18000388e  mov     [rsp+88h+pSid], rbx
0x180003896  jmp     loc_18000395C
0x18000389b  mov     edx, 1; dwRevision
0x1800038a0  mov     rcx, rbx; pSecurityDescriptor
0x1800038a3  call    cs:__imp_InitializeSecurityDescriptor
0x1800038a9  test    eax, eax
0x1800038ab  jz      short loc_18000387E
0x1800038ad  mov     rcx, rdi; pSid
0x1800038b0  call    cs:__imp_GetLengthSid
0x1800038b6  lea     r14d, [rax+58h]
0x1800038ba  mov     ecx, r14d; Size
0x1800038bd  call    cs:__imp_I_RpcAllocate
0x1800038c3  mov     rsi, rax
0x1800038c6  test    rax, rax
0x1800038c9  jz      loc_1800039F1
0x1800038cf  mov     r8d, 2; dwAclRevision
0x1800038d5  mov     edx, r14d; nAclLength
0x1800038d8  mov     rcx, rax; pAcl
0x1800038db  call    cs:__imp_InitializeAcl
0x1800038e1  test    eax, eax
0x1800038e3  jz      loc_1800039F8
0x1800038e9  mov     r9, rdi; pSid
0x1800038ec  mov     edx, 2; dwAceRevision
0x1800038f1  mov     r8d, 20000h; AccessMask
0x1800038f7  mov     rcx, rsi; pAcl
0x1800038fa  call    cs:__imp_AddAccessAllowedAce
0x180003900  test    eax, eax
0x180003902  jz      loc_1800039F8
0x180003908  xor     r9d, r9d; bDaclDefaulted
0x18000390b  mov     r8, rsi; pDacl
0x18000390e  mov     edx, 1; bDaclPresent
0x180003913  mov     rcx, rbx; pSecurityDescriptor
0x180003916  call    cs:__imp_SetSecurityDescriptorDacl
0x18000391c  test    eax, eax
0x18000391e  jz      loc_1800039F8
0x180003924  xor     r8d, r8d; bGroupDefaulted
0x180003927  mov     rdx, rdi; pGroup
0x18000392a  mov     rcx, rbx; pSecurityDescriptor
0x18000392d  call    cs:__imp_SetSecurityDescriptorGroup
0x180003933  test    eax, eax
0x180003935  jz      loc_1800039F8
0x18000393b  xor     r8d, r8d; bOwnerDefaulted
0x18000393e  mov     rdx, rdi; pOwner
0x180003941  mov     rcx, rbx; pSecurityDescriptor
0x180003944  call    cs:__imp_SetSecurityDescriptorOwner
0x18000394a  test    eax, eax
0x18000394c  jz      loc_1800039F8
0x180003952  xor     edi, edi
0x180003954  test    edi, edi
0x180003956  jnz     loc_18000387E
0x18000395c  mov     rax, [rsp+88h+arg_48]
0x180003964  mov     [rsp+88h+var_40], rax; __int64
0x180003969  mov     rax, [rsp+88h+arg_40]
0x180003971  mov     [rsp+88h+var_48], rax; __int64
0x180003976  mov     rax, [rsp+88h+arg_38]
0x18000397e  mov     [rsp+88h+var_50], rax; __int64
0x180003983  mov     eax, [rsp+88h+arg_30]
0x18000398a  mov     [rsp+88h+var_58], eax; int
0x18000398e  mov     rax, [rsp+88h+arg_28]
0x180003996  mov     [rsp+88h+var_60], rax; __int64
0x18000399b  mov     [rsp+88h+pSecurityDescriptor], rbx; pSecurityDescriptor
0x1800039a0  mov     r9, r15
0x1800039a3  mov     r8, r12
0x1800039a6  mov     rcx, r13; pAsync
0x1800039a9  call    ept_map_auth_sd
0x1800039ae  nop
0x1800039af  test    rbx, rbx
0x1800039b2  jz      short loc_1800039D5
0x1800039b4  mov     rcx, [rbx+20h]; Object
0x1800039b8  test    rcx, rcx
0x1800039bb  jz      short loc_1800039C3
0x1800039bd  call    cs:__imp_I_RpcFree
0x1800039c3  mov     r8, rbx; lpMem
0x1800039c6  xor     edx, edx; dwFlags
0x1800039c8  mov     rcx, cs:hEpMapperHeap; hHeap
0x1800039cf  call    cs:__imp_HeapFree
0x1800039d5  add     rsp, 50h
0x1800039d9  pop     r15
0x1800039db  pop     r14
0x1800039dd  pop     r13
0x1800039df  pop     r12
0x1800039e1  pop     rdi
0x1800039e2  pop     rsi
0x1800039e3  pop     rbx
0x1800039e4  retn
0x1800039e5  mov     ecx, 0Eh; exception
0x1800039ea  call    cs:__imp_RpcRaiseException
0x1800039f0  int     3; Trap to Debugger
0x1800039f1  mov     edi, 0Eh
0x1800039f6  jmp     short loc_1800039FD
0x1800039f8  mov     edi, 16C9A0CDh
0x1800039fd  test    rsi, rsi
0x180003a00  jz      loc_180003954
0x180003a06  mov     rcx, rsi; Object
0x180003a09  call    cs:__imp_I_RpcFree
0x180003a0f  jmp     loc_180003954
0x18000aa30  push    rbx
0x18000aa32  push    rbp
0x18000aa33  sub     rsp, 58h
0x18000aa37  mov     rbp, rdx
0x18000aa3a  mov     rbx, [rbp+0B0h]
0x18000aa41  test    rbx, rbx
0x18000aa44  jz      short loc_18000AA6B
0x18000aa46  cmp     qword ptr [rbx+20h], 0
0x18000aa4b  jz      short loc_18000AA58
0x18000aa4d  mov     rcx, [rbx+20h]; Object
0x18000aa51  call    cs:__imp_I_RpcFree
0x18000aa57  nop
0x18000aa58  mov     r8, rbx; lpMem
0x18000aa5b  xor     edx, edx; dwFlags
0x18000aa5d  mov     rcx, cs:hEpMapperHeap; hHeap
0x18000aa64  call    cs:__imp_HeapFree
0x18000aa6a  nop
0x18000aa6b  add     rsp, 58h
0x18000aa6f  pop     rbp
0x18000aa70  pop     rbx
0x18000aa71  retn
```
