# CSpSecurityAttribute::CSpSecurityAttribute(ulong,ulong)

- ea: `0x140007680`
- end: `0x14000780f`
- name: `??0CSpSecurityAttribute@@QEAA@KK@Z`
- size: `399`
- prototype: `CSpSecurityAttribute *__fastcall(CSpSecurityAttribute *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000ede4`

## callees

- `0x140002d54`
- `0x140002ff4`
- `0x140007680`
- `0x14000ffdc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400076f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007731`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400076f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140007731`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400076d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400076d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400076be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400076be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400077c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400077c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140007746`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140007746`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400077f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400077f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400077e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400077e8`

## pseudocode

```c
CSpSecurityAttribute *__fastcall CSpSecurityAttribute::CSpSecurityAttribute(CSpSecurityAttribute *this)
{
  PSID *v2; // rsi
  WCHAR *v3; // rdi
  HANDLE CurrentProcess; // rax
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // kr00_8
  unsigned __int16 *v9; // rax
  LPWSTR StringSid; // [rsp+70h] [rbp+40h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp+50h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+58h] BYREF

  TokenInformationLength = 0;
  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  TokenHandle = (void *)-1LL;
  v2 = 0;
  StringSid = 0;
  v3 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( TokenInformationLength )
    {
      v2 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v2, &StringSid) )
        {
          v5 = -1;
          do
            ++v5;
          while ( StringSid[v5] );
          v6 = v5 + 43;
          v8 = v5 + 43;
          v7 = 2 * (v5 + 43);
          if ( !is_mul_ok(v8, 2u) )
            v7 = -1;
          v9 = (unsigned __int16 *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
          v3 = v9;
          if ( v9 )
          {
            StringCchPrintfW(v9, v6, L"D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;;%s)(A;CIOI;GR;;;AC)");
            if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v3, 1u, (PSECURITY_DESCRIPTOR *)this + 1, 0) )
            {
              *(_DWORD *)this = 24;
              *((_DWORD *)this + 4) = 0;
            }
          }
        }
      }
    }
  }
  operator delete(v3);
  operator delete(v2);
  LocalFree(StringSid);
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return this;
}

```

## disassembly

```asm
0x140007680  mov     [rsp-38h+TokenInformationLength], r8d
0x140007685  push    rbp
0x140007686  push    rbx
0x140007687  push    rsi
0x140007688  push    rdi
0x140007689  push    r12
0x14000768b  push    r14
0x14000768d  push    r15
0x14000768f  mov     rbp, rsp
0x140007692  sub     rsp, 30h
0x140007696  xor     r15d, r15d
0x140007699  xorps   xmm0, xmm0
0x14000769c  xor     eax, eax
0x14000769e  mov     [rbp+TokenInformationLength], r15d
0x1400076a2  movups  xmmword ptr [rcx], xmm0
0x1400076a5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400076a9  mov     [rcx+10h], rax
0x1400076ad  mov     rbx, rcx
0x1400076b0  mov     [rbp+TokenHandle], r12
0x1400076b4  mov     esi, r15d
0x1400076b7  mov     [rbp+StringSid], r15
0x1400076bb  mov     edi, r15d
0x1400076be  call    cs:__imp_GetCurrentProcess
0x1400076c4  mov     rcx, rax; ProcessHandle
0x1400076c7  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400076cb  lea     edx, [r12+9]; DesiredAccess
0x1400076d0  call    cs:__imp_OpenProcessToken
0x1400076d6  test    eax, eax
0x1400076d8  jz      loc_1400077D4
0x1400076de  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400076e2  lea     rax, [rbp+TokenInformationLength]
0x1400076e6  xor     r9d, r9d; TokenInformationLength
0x1400076e9  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1400076ee  xor     r8d, r8d; TokenInformation
0x1400076f1  lea     edx, [r12+2]; TokenInformationClass
0x1400076f6  call    cs:__imp_GetTokenInformation
0x1400076fc  mov     eax, [rbp+TokenInformationLength]
0x1400076ff  test    eax, eax
0x140007701  jz      loc_1400077D4
0x140007707  mov     ecx, eax; unsigned __int64
0x140007709  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140007710  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140007715  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140007719  lea     edx, [r12+2]; TokenInformationClass
0x14000771e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140007722  mov     rsi, rax
0x140007725  lea     rax, [rbp+TokenInformationLength]
0x140007729  mov     r8, rsi; TokenInformation
0x14000772c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140007731  call    cs:__imp_GetTokenInformation
0x140007737  test    eax, eax
0x140007739  jz      loc_1400077D4
0x14000773f  mov     rcx, [rsi]; Sid
0x140007742  lea     rdx, [rbp+StringSid]; StringSid
0x140007746  call    cs:__imp_ConvertSidToStringSidW
0x14000774c  test    eax, eax
0x14000774e  jz      loc_1400077D4
0x140007754  mov     rcx, [rbp+StringSid]
0x140007758  mov     rax, r12
0x14000775b  inc     rax
0x14000775e  cmp     [rcx+rax*2], r15w
0x140007763  jnz     short loc_14000775B
0x140007765  lea     r14, [rax+2Bh]
0x140007769  mov     eax, 2
0x14000776e  mul     r14
0x140007771  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140007778  cmovb   rax, r12
0x14000777c  mov     rcx, rax; unsigned __int64
0x14000777f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140007784  mov     rdi, rax
0x140007787  test    rax, rax
0x14000778a  jz      short loc_1400077D4
0x14000778c  mov     rcx, [rbp+StringSid]
0x140007790  lea     r8, aDPACioi0x08xAu; "D:P(A;CIOI;0x%08X;;;AU)(A;CIOI;0x%08X;;"...
0x140007797  mov     [rsp+30h+var_8], rcx
0x14000779c  mov     r9d, 100001h
0x1400077a2  mov     rcx, rax; unsigned __int16 *
0x1400077a5  mov     dword ptr [rsp+30h+ReturnLength], r9d
0x1400077aa  mov     rdx, r14; unsigned __int64
0x1400077ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400077b2  xor     r9d, r9d; SecurityDescriptorSize
0x1400077b5  lea     r8, [rbx+8]; SecurityDescriptor
0x1400077b9  mov     rcx, rdi; StringSecurityDescriptor
0x1400077bc  lea     edx, [r9+1]; StringSDRevision
0x1400077c0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400077c6  test    eax, eax
0x1400077c8  jz      short loc_1400077D4
0x1400077ca  mov     dword ptr [rbx], 18h
0x1400077d0  mov     [rbx+10h], r15d
0x1400077d4  mov     rcx, rdi; Block
0x1400077d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400077dc  mov     rcx, rsi; Block
0x1400077df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400077e4  mov     rcx, [rbp+StringSid]; hMem
0x1400077e8  call    cs:__imp_LocalFree
0x1400077ee  mov     rcx, [rbp+TokenHandle]; hObject
0x1400077f2  cmp     rcx, r12
0x1400077f5  jz      short loc_1400077FD
0x1400077f7  call    cs:__imp_CloseHandle
0x1400077fd  mov     rax, rbx
0x140007800  add     rsp, 30h
0x140007804  pop     r15
0x140007806  pop     r14
0x140007808  pop     r12
0x14000780a  pop     rdi
0x14000780b  pop     rsi
0x14000780c  pop     rbx
0x14000780d  pop     rbp
0x14000780e  retn
```
