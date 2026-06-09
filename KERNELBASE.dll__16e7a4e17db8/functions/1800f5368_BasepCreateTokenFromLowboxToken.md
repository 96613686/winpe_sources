# BasepCreateTokenFromLowboxToken

- ea: `0x1800f5368`
- end: `0x1800f559a`
- name: `BasepCreateTokenFromLowboxToken`
- size: `562`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180066d28`

## callees

- `0x1800f5368`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800f53ee`
- `ntdll!RtlEqualSid` at `0x1800f54df`
- `ntdll!RtlEqualSid` at `0x1800f53ee`
- `ntdll!RtlEqualSid` at `0x1800f54df`
- `ntdll!NtQueryInformationToken` at `0x1800f53d8`
- `ntdll!NtQueryInformationToken` at `0x1800f543c`
- `ntdll!NtQueryInformationToken` at `0x1800f5495`
- `ntdll!NtQueryInformationToken` at `0x1800f53d8`
- `ntdll!NtQueryInformationToken` at `0x1800f543c`
- `ntdll!NtQueryInformationToken` at `0x1800f5495`
- `ntdll!RtlGetAppContainerSidType` at `0x1800f5404`
- `ntdll!RtlGetAppContainerSidType` at `0x1800f5404`
- `ntdll!RtlFreeHeap` at `0x1800f5546`
- `ntdll!RtlFreeHeap` at `0x1800f5592`
- `ntdll!RtlFreeHeap` at `0x1800f5546`
- `ntdll!RtlFreeHeap` at `0x1800f5592`
- `ntdll!NtDuplicateToken` at `0x1800f5527`
- `ntdll!NtDuplicateToken` at `0x1800f5527`
- `ntdll!RtlAllocateHeap` at `0x1800f53ad`
- `ntdll!RtlAllocateHeap` at `0x1800f5466`
- `ntdll!RtlAllocateHeap` at `0x1800f53ad`
- `ntdll!RtlAllocateHeap` at `0x1800f5466`

## pseudocode

```c
__int64 __fastcall BasepCreateTokenFromLowboxToken(HANDLE ExistingTokenHandle, _QWORD *a2, HANDLE *a3)
{
  PSID *Heap; // r14
  NTSTATUS AppContainerSidType; // ebx
  int *v7; // rdi
  int v8; // eax
  __int64 v9; // rcx
  int v10; // ebp
  unsigned int i; // ebx
  BOOLEAN v12; // al
  int v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]
  ULONG TokenInformationLength; // [rsp+98h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  v14 = 0;
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x4Cu);
  if ( !Heap )
    return (unsigned int)-1073741801;
  AppContainerSidType = NtQueryInformationToken(
                          ExistingTokenHandle,
                          TokenAppContainerSid,
                          Heap,
                          0x4Cu,
                          &TokenInformationLength);
  if ( AppContainerSidType >= 0 )
  {
    if ( !RtlEqualSid(*Heap, (PSID)*a2) )
    {
      AppContainerSidType = -1073741811;
      goto LABEL_18;
    }
    AppContainerSidType = RtlGetAppContainerSidType(*a2, &v14);
    if ( AppContainerSidType >= 0 )
    {
      v7 = 0;
      if ( v14 == 1 )
        goto LABEL_17;
      AppContainerSidType = NtQueryInformationToken(
                              ExistingTokenHandle,
                              TokenCapabilities,
                              0,
                              0,
                              &TokenInformationLength);
      if ( AppContainerSidType == -1073741789 )
      {
        v7 = (int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
        if ( !v7 )
        {
          AppContainerSidType = -1073741801;
          goto LABEL_18;
        }
        AppContainerSidType = NtQueryInformationToken(
                                ExistingTokenHandle,
                                TokenCapabilities,
                                v7,
                                TokenInformationLength,
                                &TokenInformationLength);
        if ( AppContainerSidType < 0 )
          goto LABEL_24;
        v8 = *v7;
        if ( *((_DWORD *)a2 + 4) != *v7 )
        {
LABEL_23:
          AppContainerSidType = -1073741811;
          goto LABEL_24;
        }
        v9 = a2[1];
        v10 = 0;
        v15 = v9;
        if ( v8 )
        {
LABEL_11:
          for ( i = 0; i < *((_DWORD *)a2 + 4); ++i )
          {
            v12 = RtlEqualSid(*(PSID *)&v7[4 * v10 + 2], *(PSID *)(v9 + 16LL * i));
            v9 = v15;
            if ( v12 && v7[4 * v10 + 4] == *(_DWORD *)(v15 + 16LL * i + 8) )
            {
              if ( ++v10 < (unsigned int)*v7 )
                goto LABEL_11;
              goto LABEL_17;
            }
          }
          goto LABEL_23;
        }
LABEL_17:
        AppContainerSidType = NtDuplicateToken(ExistingTokenHandle, 0xF01FFu, 0, 0, TokenPrimary, a3);
        if ( !v7 )
          goto LABEL_18;
LABEL_24:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      }
    }
  }
LABEL_18:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)AppContainerSidType;
}

```

## disassembly

```asm
0x1800f5368  mov     rax, rsp
0x1800f536b  mov     [rax+8], rbx
0x1800f536f  mov     [rax+18h], r8
0x1800f5373  push    rbp
0x1800f5374  push    rsi
0x1800f5375  push    rdi
0x1800f5376  push    r12
0x1800f5378  push    r13
0x1800f537a  push    r14
0x1800f537c  push    r15
0x1800f537e  sub     rsp, 40h
0x1800f5382  mov     r13, rcx
0x1800f5385  mov     dword ptr [rax+20h], 0
0x1800f538c  mov     dword ptr [rax-48h], 0
0x1800f5393  mov     rsi, rdx
0x1800f5396  mov     rcx, gs:60h
0x1800f539f  mov     ebx, 4Ch ; 'L'
0x1800f53a4  mov     r8d, ebx; Size
0x1800f53a7  xor     edx, edx; Flags
0x1800f53a9  mov     rcx, [rcx+30h]; HeapHandle
0x1800f53ad  call    cs:__imp_RtlAllocateHeap
0x1800f53b3  mov     r14, rax
0x1800f53b6  test    rax, rax
0x1800f53b9  jz      loc_1800F5566
0x1800f53bf  lea     rax, [rsp+78h+TokenInformationLength]
0x1800f53c7  mov     r9d, ebx; TokenInformationLength
0x1800f53ca  mov     r8, r14; TokenInformation
0x1800f53cd  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800f53d2  lea     edx, [rbx-2Dh]; TokenInformationClass
0x1800f53d5  mov     rcx, r13; TokenHandle
0x1800f53d8  call    cs:__imp_NtQueryInformationToken
0x1800f53de  mov     ebx, eax
0x1800f53e0  test    eax, eax
0x1800f53e2  js      loc_1800F5534
0x1800f53e8  mov     rdx, [rsi]; Sid2
0x1800f53eb  mov     rcx, [r14]; Sid1
0x1800f53ee  call    cs:__imp_RtlEqualSid
0x1800f53f4  test    al, al
0x1800f53f6  jz      loc_1800F556D
0x1800f53fc  mov     rcx, [rsi]
0x1800f53ff  lea     rdx, [rsp+78h+var_48]
0x1800f5404  call    cs:__imp_RtlGetAppContainerSidType
0x1800f540a  mov     ebx, eax
0x1800f540c  test    eax, eax
0x1800f540e  js      loc_1800F5534
0x1800f5414  xor     edi, edi
0x1800f5416  cmp     [rsp+78h+var_48], 1
0x1800f541b  jz      loc_1800F5504
0x1800f5421  lea     rax, [rsp+78h+TokenInformationLength]
0x1800f5429  xor     r9d, r9d; TokenInformationLength
0x1800f542c  lea     ebp, [rdi+1Eh]
0x1800f542f  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800f5434  mov     edx, ebp; TokenInformationClass
0x1800f5436  xor     r8d, r8d; TokenInformation
0x1800f5439  mov     rcx, r13; TokenHandle
0x1800f543c  call    cs:__imp_NtQueryInformationToken
0x1800f5442  mov     ebx, eax
0x1800f5444  cmp     eax, 0C0000023h
0x1800f5449  jnz     loc_1800F5534
0x1800f544f  mov     rcx, gs:60h
0x1800f5458  xor     edx, edx; Flags
0x1800f545a  mov     r8d, [rsp+78h+TokenInformationLength]; Size
0x1800f5462  mov     rcx, [rcx+30h]; HeapHandle
0x1800f5466  call    cs:__imp_RtlAllocateHeap
0x1800f546c  mov     rdi, rax
0x1800f546f  test    rax, rax
0x1800f5472  jz      loc_1800F5574
0x1800f5478  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x1800f5480  lea     rax, [rsp+78h+TokenInformationLength]
0x1800f5488  mov     r8, rdi; TokenInformation
0x1800f548b  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800f5490  mov     edx, ebp; TokenInformationClass
0x1800f5492  mov     rcx, r13; TokenHandle
0x1800f5495  call    cs:__imp_NtQueryInformationToken
0x1800f549b  mov     ebx, eax
0x1800f549d  test    eax, eax
0x1800f549f  js      loc_1800F5580
0x1800f54a5  mov     eax, [rdi]
0x1800f54a7  cmp     [rsi+10h], eax
0x1800f54aa  jnz     loc_1800F557B
0x1800f54b0  mov     rcx, [rsi+8]
0x1800f54b4  xor     ebp, ebp
0x1800f54b6  mov     [rsp+78h+var_40], rcx
0x1800f54bb  test    eax, eax
0x1800f54bd  jz      short loc_1800F5504
0x1800f54bf  xor     ebx, ebx
0x1800f54c1  cmp     ebx, [rsi+10h]
0x1800f54c4  jnb     loc_1800F557B
0x1800f54ca  mov     r15d, ebx
0x1800f54cd  mov     r12d, ebp
0x1800f54d0  add     r15, r15
0x1800f54d3  add     r12, r12
0x1800f54d6  mov     rdx, [rcx+r15*8]; Sid2
0x1800f54da  mov     rcx, [rdi+r12*8+8]; Sid1
0x1800f54df  call    cs:__imp_RtlEqualSid
0x1800f54e5  mov     rcx, [rsp+78h+var_40]
0x1800f54ea  test    al, al
0x1800f54ec  jnz     short loc_1800F54F2
0x1800f54ee  inc     ebx
0x1800f54f0  jmp     short loc_1800F54C1
0x1800f54f2  mov     eax, [rcx+r15*8+8]
0x1800f54f7  cmp     [rdi+r12*8+10h], eax
0x1800f54fc  jnz     short loc_1800F54EE
0x1800f54fe  inc     ebp
0x1800f5500  cmp     ebp, [rdi]
0x1800f5502  jb      short loc_1800F54BF
0x1800f5504  mov     rax, [rsp+78h+arg_10]
0x1800f550c  xor     r9d, r9d; EffectiveOnly
0x1800f550f  mov     [rsp+78h+NewTokenHandle], rax; NewTokenHandle
0x1800f5514  xor     r8d, r8d; ObjectAttributes
0x1800f5517  mov     edx, 0F01FFh; DesiredAccess
0x1800f551c  mov     dword ptr [rsp+78h+ReturnLength], 1; TokenType
0x1800f5524  mov     rcx, r13; ExistingTokenHandle
0x1800f5527  call    cs:__imp_NtDuplicateToken
0x1800f552d  mov     ebx, eax
0x1800f552f  test    rdi, rdi
0x1800f5532  jnz     short loc_1800F5580
0x1800f5534  mov     rcx, gs:60h
0x1800f553d  mov     r8, r14; P
0x1800f5540  xor     edx, edx; Flags
0x1800f5542  mov     rcx, [rcx+30h]; HeapHandle
0x1800f5546  call    cs:__imp_RtlFreeHeap
0x1800f554c  mov     eax, ebx
0x1800f554e  mov     rbx, [rsp+78h+arg_0]
0x1800f5556  add     rsp, 40h
0x1800f555a  pop     r15
0x1800f555c  pop     r14
0x1800f555e  pop     r13
0x1800f5560  pop     r12
0x1800f5562  pop     rdi
0x1800f5563  pop     rsi
0x1800f5564  pop     rbp
0x1800f5565  retn
0x1800f5566  mov     ebx, 0C0000017h
0x1800f556b  jmp     short loc_1800F554C
0x1800f556d  mov     ebx, 0C000000Dh
0x1800f5572  jmp     short loc_1800F5534
0x1800f5574  mov     ebx, 0C0000017h
0x1800f5579  jmp     short loc_1800F5534
0x1800f557b  mov     ebx, 0C000000Dh
0x1800f5580  mov     rcx, gs:60h
0x1800f5589  mov     r8, rdi; P
0x1800f558c  xor     edx, edx; Flags
0x1800f558e  mov     rcx, [rcx+30h]; HeapHandle
0x1800f5592  call    cs:__imp_RtlFreeHeap
0x1800f5598  jmp     short loc_1800F5534
```
