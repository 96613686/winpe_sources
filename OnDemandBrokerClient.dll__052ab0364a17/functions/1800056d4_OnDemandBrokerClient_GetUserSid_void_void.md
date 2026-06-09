# OnDemandBrokerClient::GetUserSid(void *,void * *)

- ea: `0x1800056d4`
- end: `0x180005811`
- name: `?GetUserSid@OnDemandBrokerClient@@AEAAJPEAXPEAPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this, void *, void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005230`
- `0x180005b70`
- `0x180005f60`
- `0x180006210`

## callees

- `0x180004d44`
- `0x180004d78`
- `0x1800056d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000572b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000572b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005794`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005721`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000578a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005721`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000578a`
- `ntdll!RtlCopySid` at `0x1800057db`
- `ntdll!RtlCopySid` at `0x1800057db`
- `ntdll!RtlLengthSid` at `0x1800057ae`
- `ntdll!RtlLengthSid` at `0x1800057ae`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::GetUserSid(OnDemandBrokerClient *this, void *a2, void **a3)
{
  unsigned int v5; // ebx
  signed int v6; // eax
  PSID *v7; // rsi
  signed int LastError; // eax
  ULONG v9; // ebx
  void *v10; // rax
  NTSTATUS v11; // ebx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+64h] [rbp+Ch]

  v14 = HIDWORD(this);
  TokenInformationLength = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) || (v6 = GetLastError(), v5 = v6, v6 == 122) )
    {
      v7 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( v7 )
      {
        if ( GetTokenInformation(a2, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
        {
          v9 = RtlLengthSid(*v7);
          v10 = operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
          *a3 = v10;
          if ( v10 )
          {
            v11 = RtlCopySid(v9, v10, *v7);
            if ( v11 < 0 )
            {
              operator delete[](*a3);
              v5 = v11 | 0x10000000;
              *a3 = 0;
            }
            else
            {
              v5 = 0;
            }
          }
          else
          {
            v5 = -2147024882;
          }
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
        operator delete[](v7);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else if ( v6 > 0 )
    {
      return (unsigned __int16)v6 | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x1800056d4  mov     qword ptr [rsp+TokenInformationLength], rcx
0x1800056d9  push    rbx
0x1800056da  push    rbp
0x1800056db  push    rsi
0x1800056dc  push    rdi
0x1800056dd  sub     rsp, 38h
0x1800056e1  mov     [rsp+58h+TokenInformationLength], 0
0x1800056e9  mov     rdi, r8
0x1800056ec  mov     rbp, rdx
0x1800056ef  test    rdx, rdx
0x1800056f2  jnz     short loc_1800056FE
0x1800056f4  mov     ebx, 80070057h
0x1800056f9  jmp     loc_180005806
0x1800056fe  test    rdi, rdi
0x180005701  jz      short loc_1800056F4
0x180005703  xor     r9d, r9d; TokenInformationLength
0x180005706  mov     qword ptr [r8], 0
0x18000570d  lea     rax, [rsp+58h+TokenInformationLength]
0x180005712  xor     r8d, r8d; TokenInformation
0x180005715  mov     rcx, rbp; TokenHandle
0x180005718  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000571d  lea     edx, [r9+1]; TokenInformationClass
0x180005721  call    cs:__imp_GetTokenInformation
0x180005727  test    eax, eax
0x180005729  jnz     short loc_18000574E
0x18000572b  call    cs:__imp_GetLastError
0x180005731  mov     ebx, eax
0x180005733  cmp     eax, 7Ah ; 'z'
0x180005736  jz      short loc_18000574E
0x180005738  test    eax, eax
0x18000573a  jle     loc_180005806
0x180005740  movzx   ebx, ax
0x180005743  or      ebx, 80070000h
0x180005749  jmp     loc_180005806
0x18000574e  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x180005752  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005759  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000575e  mov     rsi, rax
0x180005761  test    rax, rax
0x180005764  jnz     short loc_180005770
0x180005766  mov     ebx, 8007000Eh
0x18000576b  jmp     loc_180005806
0x180005770  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180005775  lea     rax, [rsp+58h+TokenInformationLength]
0x18000577a  mov     r8, rsi; TokenInformation
0x18000577d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180005782  mov     edx, 1; TokenInformationClass
0x180005787  mov     rcx, rbp; TokenHandle
0x18000578a  call    cs:__imp_GetTokenInformation
0x180005790  test    eax, eax
0x180005792  jnz     short loc_1800057AB
0x180005794  call    cs:__imp_GetLastError
0x18000579a  mov     ebx, eax
0x18000579c  test    eax, eax
0x18000579e  jle     short loc_1800057FE
0x1800057a0  movzx   ebx, ax
0x1800057a3  or      ebx, 80070000h
0x1800057a9  jmp     short loc_1800057FE
0x1800057ab  mov     rcx, [rsi]; Sid
0x1800057ae  call    cs:__imp_RtlLengthSid
0x1800057b4  mov     ecx, eax; unsigned __int64
0x1800057b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800057bd  mov     ebx, eax
0x1800057bf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800057c4  mov     [rdi], rax
0x1800057c7  test    rax, rax
0x1800057ca  jnz     short loc_1800057D3
0x1800057cc  mov     ebx, 8007000Eh
0x1800057d1  jmp     short loc_1800057FE
0x1800057d3  mov     r8, [rsi]; SourceSid
0x1800057d6  mov     rdx, rax; DestinationSid
0x1800057d9  mov     ecx, ebx; DestinationSidLength
0x1800057db  call    cs:__imp_RtlCopySid
0x1800057e1  mov     ebx, eax
0x1800057e3  test    eax, eax
0x1800057e5  js      short loc_1800057EB
0x1800057e7  xor     ebx, ebx
0x1800057e9  jmp     short loc_1800057FE
0x1800057eb  mov     rcx, [rdi]; Block
0x1800057ee  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800057f3  bts     ebx, 1Ch
0x1800057f7  mov     qword ptr [rdi], 0
0x1800057fe  mov     rcx, rsi; Block
0x180005801  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005806  mov     eax, ebx
0x180005808  add     rsp, 38h
0x18000580c  pop     rdi
0x18000580d  pop     rsi
0x18000580e  pop     rbp
0x18000580f  pop     rbx
0x180005810  retn
```
