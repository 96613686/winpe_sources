# ProviderSubSystem_Common_Globals::GetUserSid(void *,ulong *,void * &)

- ea: `0x1400418dc`
- end: `0x1400419e3`
- name: `?GetUserSid@ProviderSubSystem_Common_Globals@@SAJPEAXPEAKAEAPEAX@Z`
- size: `263`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140041c60`

## callees

- `0x14000a0f0`
- `0x14000a530`
- `0x14002b716`
- `0x1400418dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14004197f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14004197f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004192a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140041972`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004192a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140041972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041938`

## pseudocode

```c
__int64 __fastcall ProviderSubSystem_Common_Globals::GetUserSid(HANDLE TokenHandle, unsigned int *a2, void **a3)
{
  unsigned int v6; // ebx
  PSID *v7; // rdi
  DWORD LengthSid; // eax
  DWORD v9; // ebx
  void *v10; // rax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF

  if ( TokenHandle )
  {
    if ( a2 )
    {
      TokenInformationLength = 0;
      v6 = -2147217407;
      if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
      {
        v7 = (PSID *)operator new(TokenInformationLength);
        if ( v7 )
        {
          if ( GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
          {
            LengthSid = GetLengthSid(*v7);
            *a2 = LengthSid;
            v9 = LengthSid;
            v10 = operator new(LengthSid);
            *a3 = v10;
            if ( v10 )
            {
              memcpy_0(v10, *v7, v9);
              v6 = 0;
            }
            else
            {
              v6 = -2147217402;
            }
          }
          operator delete(v7);
        }
        else
        {
          return (unsigned int)-2147217402;
        }
      }
    }
    else
    {
      return (unsigned int)-2147217400;
    }
  }
  else
  {
    return (unsigned int)-2147024890;
  }
  return v6;
}

```

## disassembly

```asm
0x1400418dc  mov     rax, rsp
0x1400418df  mov     [rax+10h], rbx
0x1400418e3  mov     [rax+18h], rsi
0x1400418e7  push    rdi
0x1400418e8  push    r14
0x1400418ea  push    r15
0x1400418ec  sub     rsp, 30h
0x1400418f0  mov     r15, r8
0x1400418f3  mov     r14, rdx
0x1400418f6  mov     rsi, rcx
0x1400418f9  test    rcx, rcx
0x1400418fc  jz      loc_1400419C8
0x140041902  test    rdx, rdx
0x140041905  jz      loc_1400419C1
0x14004190b  xor     r9d, r9d; TokenInformationLength
0x14004190e  mov     dword ptr [rax+8], 0
0x140041915  lea     rax, [rax+8]
0x140041919  xor     r8d, r8d; TokenInformation
0x14004191c  mov     ebx, 80041001h
0x140041921  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140041926  lea     edx, [r9+1]; TokenInformationClass
0x14004192a  call    cs:__imp_GetTokenInformation
0x140041930  test    eax, eax
0x140041932  jnz     loc_1400419CD
0x140041938  call    cs:__imp_GetLastError
0x14004193e  cmp     eax, 7Ah ; 'z'
0x140041941  jnz     loc_1400419CD
0x140041947  mov     ecx, [rsp+48h+TokenInformationLength]; dwBytes
0x14004194b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140041950  mov     rdi, rax
0x140041953  test    rax, rax
0x140041956  jz      short loc_1400419BA
0x140041958  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x14004195d  lea     rax, [rsp+48h+TokenInformationLength]
0x140041962  mov     r8, rdi; TokenInformation
0x140041965  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14004196a  mov     edx, 1; TokenInformationClass
0x14004196f  mov     rcx, rsi; TokenHandle
0x140041972  call    cs:__imp_GetTokenInformation
0x140041978  test    eax, eax
0x14004197a  jz      short loc_1400419B0
0x14004197c  mov     rcx, [rdi]; pSid
0x14004197f  call    cs:__imp_GetLengthSid
0x140041985  mov     ecx, eax; dwBytes
0x140041987  mov     [r14], eax
0x14004198a  mov     ebx, eax
0x14004198c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140041991  mov     [r15], rax
0x140041994  test    rax, rax
0x140041997  jz      short loc_1400419AB
0x140041999  mov     rdx, [rdi]; Src
0x14004199c  mov     r8d, ebx; Size
0x14004199f  mov     rcx, rax; void *
0x1400419a2  call    memcpy_0
0x1400419a7  xor     ebx, ebx
0x1400419a9  jmp     short loc_1400419B0
0x1400419ab  mov     ebx, 80041006h
0x1400419b0  mov     rcx, rdi; lpMem
0x1400419b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400419b8  jmp     short loc_1400419CD
0x1400419ba  mov     ebx, 80041006h
0x1400419bf  jmp     short loc_1400419CD
0x1400419c1  mov     ebx, 80041008h
0x1400419c6  jmp     short loc_1400419CD
0x1400419c8  mov     ebx, 80070006h
0x1400419cd  mov     rsi, [rsp+48h+arg_10]
0x1400419d2  mov     eax, ebx
0x1400419d4  mov     rbx, [rsp+48h+arg_8]
0x1400419d9  add     rsp, 30h
0x1400419dd  pop     r15
0x1400419df  pop     r14
0x1400419e1  pop     rdi
0x1400419e2  retn
```
