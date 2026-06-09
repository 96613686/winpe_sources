# UfhpUtilityAllocGetSecurityDescAllowAccessToWorld(void * *,_ACL * *)

- ea: `0x180040fa8`
- end: `0x18004118e`
- name: `?UfhpUtilityAllocGetSecurityDescAllowAccessToWorld@@YAKPEAPEAXPEAPEAU_ACL@@@Z`
- size: `486`
- prototype: `unsigned int __fastcall(void **, struct _ACL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f0fe0`

## callees

- `0x180040fa8`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004112a`
- `ntdll!RtlFreeHeap` at `0x180041147`
- `ntdll!RtlFreeHeap` at `0x18004112a`
- `ntdll!RtlFreeHeap` at `0x180041147`
- `ntdll!RtlAllocateHeap` at `0x180041052`
- `ntdll!RtlAllocateHeap` at `0x1800410a9`
- `ntdll!RtlAllocateHeap` at `0x180041052`
- `ntdll!RtlAllocateHeap` at `0x1800410a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041107`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004101b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004101b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004115f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004115f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004106e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18004106e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800410fd`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800410fd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180041031`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180041031`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004108c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18004108c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800410e8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800410e8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800410d6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800410d6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800410c1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800410c1`

## pseudocode

```c
__int64 __fastcall UfhpUtilityAllocGetSecurityDescAllowAccessToWorld(void **a1, struct _ACL **a2)
{
  void *v4; // rdi
  struct _ACL *v5; // rsi
  DWORD LastError; // ebx
  DWORD v7; // r14d
  struct _ACL *Heap; // rax
  PVOID v9; // rax
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  pSid = 0;
  v4 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = 8;
    v7 = GetLengthSid(pSid) + 20;
    Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v7);
    v5 = Heap;
    if ( !Heap )
      goto LABEL_17;
    if ( InitializeAcl(Heap, v7, 2u) && AddAccessAllowedAce(v5, 2u, 0x401FFFFFu, pSid) )
    {
      v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x28u);
      v4 = v9;
      if ( !v9 )
      {
LABEL_15:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
        goto LABEL_17;
      }
      if ( InitializeSecurityDescriptor(v9, 1u) )
      {
        if ( SetSecurityDescriptorDacl(v4, 1, v5, 0) )
        {
          if ( SetSecurityDescriptorOwner(v4, 0, 0) )
          {
            LastError = 0;
            if ( SetSecurityDescriptorGroup(v4, 0, 0) )
              goto LABEL_16;
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  LastError = GetLastError();
  if ( !LastError )
  {
LABEL_16:
    *a1 = v4;
    *a2 = v5;
    goto LABEL_17;
  }
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v5 )
    goto LABEL_15;
LABEL_17:
  if ( pSid )
    FreeSid(pSid);
  return LastError;
}

```

## disassembly

```asm
0x180040fa8  mov     r11, rsp
0x180040fab  mov     [r11+18h], rbx
0x180040faf  push    rbp
0x180040fb0  push    rsi
0x180040fb1  push    rdi
0x180040fb2  push    r12
0x180040fb4  push    r13
0x180040fb6  push    r14
0x180040fb8  push    r15
0x180040fba  mov     rbp, rsp
0x180040fbd  sub     rsp, 80h
0x180040fc4  mov     rax, cs:__security_cookie
0x180040fcb  xor     rax, rsp
0x180040fce  mov     [rbp+var_10], rax
0x180040fd2  xor     r13d, r13d
0x180040fd5  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 100h
0x180040fdb  lea     rax, [rbp+pSid]
0x180040fdf  mov     [rbp+pSid], r13
0x180040fe3  mov     [r11-68h], rax
0x180040fe7  mov     r12, rdx
0x180040fea  mov     [r11-70h], r13d
0x180040fee  mov     r15, rcx
0x180040ff1  mov     [r11-78h], r13d
0x180040ff5  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180040ff9  mov     [r11-80h], r13d
0x180040ffd  xor     r9d, r9d; nSubAuthority1
0x180041000  mov     [rsp+80h+nSubAuthority4], r13d; nSubAuthority4
0x180041005  xor     r8d, r8d; nSubAuthority0
0x180041008  mov     [rsp+80h+nSubAuthority3], r13d; nSubAuthority3
0x18004100d  mov     dl, 1; nSubAuthorityCount
0x18004100f  mov     [rsp+80h+nSubAuthority2], r13d; nSubAuthority2
0x180041014  mov     edi, r13d
0x180041017  mov     dword ptr [rbp+pIdentifierAuthority.Value], r13d
0x18004101b  call    cs:__imp_AllocateAndInitializeSid
0x180041021  test    eax, eax
0x180041023  jnz     short loc_18004102D
0x180041025  mov     esi, r13d
0x180041028  jmp     loc_180041107
0x18004102d  mov     rcx, [rbp+pSid]; pSid
0x180041031  call    cs:__imp_GetLengthSid
0x180041037  mov     rcx, gs:60h
0x180041040  mov     ebx, 8
0x180041045  mov     edx, ebx; Flags
0x180041047  lea     r14d, [rax+14h]
0x18004104b  mov     rcx, [rcx+30h]; HeapHandle
0x18004104f  mov     r8d, r14d; Size
0x180041052  call    cs:__imp_RtlAllocateHeap
0x180041058  mov     rsi, rax
0x18004105b  test    rax, rax
0x18004105e  jz      loc_180041156
0x180041064  lea     r8d, [rbx-6]; dwAclRevision
0x180041068  mov     edx, r14d; nAclLength
0x18004106b  mov     rcx, rax; pAcl
0x18004106e  call    cs:__imp_InitializeAcl
0x180041074  test    eax, eax
0x180041076  jz      loc_180041107
0x18004107c  mov     r9, [rbp+pSid]; pSid
0x180041080  lea     edx, [rbx-6]; dwAceRevision
0x180041083  mov     r8d, 401FFFFFh; AccessMask
0x180041089  mov     rcx, rsi; pAcl
0x18004108c  call    cs:__imp_AddAccessAllowedAce
0x180041092  test    eax, eax
0x180041094  jz      short loc_180041107
0x180041096  mov     rcx, gs:60h
0x18004109f  lea     r8d, [rbx+20h]; Size
0x1800410a3  mov     edx, ebx; Flags
0x1800410a5  mov     rcx, [rcx+30h]; HeapHandle
0x1800410a9  call    cs:__imp_RtlAllocateHeap
0x1800410af  mov     rdi, rax
0x1800410b2  test    rax, rax
0x1800410b5  jz      short loc_180041135
0x1800410b7  mov     ebx, 1
0x1800410bc  mov     rcx, rax; pSecurityDescriptor
0x1800410bf  mov     edx, ebx; dwRevision
0x1800410c1  call    cs:__imp_InitializeSecurityDescriptor
0x1800410c7  test    eax, eax
0x1800410c9  jz      short loc_180041107
0x1800410cb  xor     r9d, r9d; bDaclDefaulted
0x1800410ce  mov     r8, rsi; pDacl
0x1800410d1  mov     edx, ebx; bDaclPresent
0x1800410d3  mov     rcx, rdi; pSecurityDescriptor
0x1800410d6  call    cs:__imp_SetSecurityDescriptorDacl
0x1800410dc  test    eax, eax
0x1800410de  jz      short loc_180041107
0x1800410e0  xor     r8d, r8d; bOwnerDefaulted
0x1800410e3  xor     edx, edx; pOwner
0x1800410e5  mov     rcx, rdi; pSecurityDescriptor
0x1800410e8  call    cs:__imp_SetSecurityDescriptorOwner
0x1800410ee  test    eax, eax
0x1800410f0  jz      short loc_180041107
0x1800410f2  xor     r8d, r8d; bGroupDefaulted
0x1800410f5  xor     edx, edx; pGroup
0x1800410f7  mov     rcx, rdi; pSecurityDescriptor
0x1800410fa  mov     ebx, r13d
0x1800410fd  call    cs:__imp_SetSecurityDescriptorGroup
0x180041103  test    eax, eax
0x180041105  jnz     short loc_18004114F
0x180041107  call    cs:__imp_GetLastError
0x18004110d  mov     ebx, eax
0x18004110f  test    eax, eax
0x180041111  jz      short loc_18004114F
0x180041113  test    rdi, rdi
0x180041116  jz      short loc_180041130
0x180041118  mov     rcx, gs:60h
0x180041121  mov     r8, rdi; P
0x180041124  xor     edx, edx; Flags
0x180041126  mov     rcx, [rcx+30h]; HeapHandle
0x18004112a  call    cs:__imp_RtlFreeHeap
0x180041130  test    rsi, rsi
0x180041133  jz      short loc_180041156
0x180041135  mov     rcx, gs:60h
0x18004113e  mov     r8, rsi; P
0x180041141  xor     edx, edx; Flags
0x180041143  mov     rcx, [rcx+30h]; HeapHandle
0x180041147  call    cs:__imp_RtlFreeHeap
0x18004114d  jmp     short loc_180041156
0x18004114f  mov     [r15], rdi
0x180041152  mov     [r12], rsi
0x180041156  mov     rcx, [rbp+pSid]; pSid
0x18004115a  test    rcx, rcx
0x18004115d  jz      short loc_180041165
0x18004115f  call    cs:__imp_FreeSid
0x180041165  mov     eax, ebx
0x180041167  mov     rcx, [rbp+var_10]
0x18004116b  xor     rcx, rsp; StackCookie
0x18004116e  call    __security_check_cookie
0x180041173  mov     rbx, [rsp+80h+arg_10]
0x18004117b  add     rsp, 80h
0x180041182  pop     r15
0x180041184  pop     r14
0x180041186  pop     r13
0x180041188  pop     r12
0x18004118a  pop     rdi
0x18004118b  pop     rsi
0x18004118c  pop     rbp
0x18004118d  retn
```
