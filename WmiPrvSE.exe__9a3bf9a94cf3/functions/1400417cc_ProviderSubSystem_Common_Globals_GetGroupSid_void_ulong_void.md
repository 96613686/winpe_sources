# ProviderSubSystem_Common_Globals::GetGroupSid(void *,ulong *,void * &)

- ea: `0x1400417cc`
- end: `0x1400418d3`
- name: `?GetGroupSid@ProviderSubSystem_Common_Globals@@SAJPEAXPEAKAEAPEAX@Z`
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
- `0x1400417cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14004186f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14004186f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004181a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140041862`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14004181a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140041862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041828`

## pseudocode

```c
__int64 __fastcall ProviderSubSystem_Common_Globals::GetGroupSid(HANDLE TokenHandle, unsigned int *a2, void **a3)
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
      if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
      {
        v7 = (PSID *)operator new(TokenInformationLength);
        if ( v7 )
        {
          if ( GetTokenInformation(TokenHandle, TokenPrimaryGroup, v7, TokenInformationLength, &TokenInformationLength) )
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
0x1400417cc  mov     rax, rsp
0x1400417cf  mov     [rax+10h], rbx
0x1400417d3  mov     [rax+18h], rsi
0x1400417d7  push    rdi
0x1400417d8  push    r14
0x1400417da  push    r15
0x1400417dc  sub     rsp, 30h
0x1400417e0  mov     r15, r8
0x1400417e3  mov     r14, rdx
0x1400417e6  mov     rsi, rcx
0x1400417e9  test    rcx, rcx
0x1400417ec  jz      loc_1400418B8
0x1400417f2  test    rdx, rdx
0x1400417f5  jz      loc_1400418B1
0x1400417fb  xor     r9d, r9d; TokenInformationLength
0x1400417fe  mov     dword ptr [rax+8], 0
0x140041805  lea     rax, [rax+8]
0x140041809  xor     r8d, r8d; TokenInformation
0x14004180c  mov     ebx, 80041001h
0x140041811  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140041816  lea     edx, [r9+5]; TokenInformationClass
0x14004181a  call    cs:__imp_GetTokenInformation
0x140041820  test    eax, eax
0x140041822  jnz     loc_1400418BD
0x140041828  call    cs:__imp_GetLastError
0x14004182e  cmp     eax, 7Ah ; 'z'
0x140041831  jnz     loc_1400418BD
0x140041837  mov     ecx, [rsp+48h+TokenInformationLength]; dwBytes
0x14004183b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140041840  mov     rdi, rax
0x140041843  test    rax, rax
0x140041846  jz      short loc_1400418AA
0x140041848  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x14004184d  lea     rax, [rsp+48h+TokenInformationLength]
0x140041852  mov     r8, rdi; TokenInformation
0x140041855  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14004185a  mov     edx, 5; TokenInformationClass
0x14004185f  mov     rcx, rsi; TokenHandle
0x140041862  call    cs:__imp_GetTokenInformation
0x140041868  test    eax, eax
0x14004186a  jz      short loc_1400418A0
0x14004186c  mov     rcx, [rdi]; pSid
0x14004186f  call    cs:__imp_GetLengthSid
0x140041875  mov     ecx, eax; dwBytes
0x140041877  mov     [r14], eax
0x14004187a  mov     ebx, eax
0x14004187c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140041881  mov     [r15], rax
0x140041884  test    rax, rax
0x140041887  jz      short loc_14004189B
0x140041889  mov     rdx, [rdi]; Src
0x14004188c  mov     r8d, ebx; Size
0x14004188f  mov     rcx, rax; void *
0x140041892  call    memcpy_0
0x140041897  xor     ebx, ebx
0x140041899  jmp     short loc_1400418A0
0x14004189b  mov     ebx, 80041006h
0x1400418a0  mov     rcx, rdi; lpMem
0x1400418a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400418a8  jmp     short loc_1400418BD
0x1400418aa  mov     ebx, 80041006h
0x1400418af  jmp     short loc_1400418BD
0x1400418b1  mov     ebx, 80041008h
0x1400418b6  jmp     short loc_1400418BD
0x1400418b8  mov     ebx, 80070006h
0x1400418bd  mov     rsi, [rsp+48h+arg_10]
0x1400418c2  mov     eax, ebx
0x1400418c4  mov     rbx, [rsp+48h+arg_8]
0x1400418c9  add     rsp, 30h
0x1400418cd  pop     r15
0x1400418cf  pop     r14
0x1400418d1  pop     rdi
0x1400418d2  retn
```
