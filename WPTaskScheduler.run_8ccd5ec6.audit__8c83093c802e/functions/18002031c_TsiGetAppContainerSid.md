# TsiGetAppContainerSid

- ea: `0x18002031c`
- end: `0x180020415`
- name: `TsiGetAppContainerSid`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004db0`

## callees

- `0x180010208`
- `0x18002031c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180020404`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180020404`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002036b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002036b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800203b9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800203b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002035d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800203ac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002035d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800203ac`
- `ntdll!RtlCopySid` at `0x1800203df`
- `ntdll!RtlCopySid` at `0x1800203df`

## pseudocode

```c
__int64 __fastcall TsiGetAppContainerSid(_QWORD *a1, void *a2)
{
  PSID *v2; // rdi
  unsigned int v5; // ebx
  ULONG LengthSid; // ebp
  void *v7; // rax
  void *v8; // rbx
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  TokenInformationLength = 0;
  if ( !a1 )
  {
    v5 = -2147467261;
    goto LABEL_12;
  }
  if ( !GetTokenInformation(a2, TokenAppContainerSid, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
  {
    v2 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v2 )
    {
LABEL_6:
      v5 = -2147024882;
      goto LABEL_12;
    }
    if ( GetTokenInformation(a2, TokenAppContainerSid, v2, TokenInformationLength, &TokenInformationLength) )
    {
      LengthSid = GetLengthSid(*v2);
      v7 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
      v8 = v7;
      if ( v7 )
      {
        RtlCopySid(LengthSid, v7, *v2);
        *a1 = v8;
        v5 = 0;
        goto LABEL_12;
      }
      goto LABEL_6;
    }
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  operator delete[](v2);
  return v5;
}

```

## disassembly

```asm
0x18002031c  push    rbx
0x18002031e  push    rbp
0x18002031f  push    rsi
0x180020320  push    rdi
0x180020321  sub     rsp, 38h
0x180020325  xor     edi, edi
0x180020327  mov     [rsp+58h+TokenInformationLength], 0
0x18002032f  mov     rbx, rdx
0x180020332  mov     rsi, rcx
0x180020335  test    rcx, rcx
0x180020338  jnz     short loc_180020344
0x18002033a  mov     ebx, 80004003h
0x18002033f  jmp     loc_180020401
0x180020344  xor     r9d, r9d; TokenInformationLength
0x180020347  lea     rax, [rsp+58h+TokenInformationLength]
0x18002034c  xor     r8d, r8d; TokenInformation
0x18002034f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180020354  mov     rcx, rbx; TokenHandle
0x180020357  lea     ebp, [r9+1Fh]
0x18002035b  mov     edx, ebp; TokenInformationClass
0x18002035d  call    cs:__imp_GetTokenInformation
0x180020363  test    eax, eax
0x180020365  jnz     loc_1800203EC
0x18002036b  call    cs:__imp_GetLastError
0x180020371  cmp     eax, 7Ah ; 'z'
0x180020374  jnz     short loc_1800203EC
0x180020376  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18002037a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020381  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020386  mov     rdi, rax
0x180020389  test    rax, rax
0x18002038c  jnz     short loc_180020395
0x18002038e  mov     ebx, 8007000Eh
0x180020393  jmp     short loc_180020401
0x180020395  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18002039a  lea     rax, [rsp+58h+TokenInformationLength]
0x18002039f  mov     r8, rdi; TokenInformation
0x1800203a2  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800203a7  mov     edx, ebp; TokenInformationClass
0x1800203a9  mov     rcx, rbx; TokenHandle
0x1800203ac  call    cs:__imp_GetTokenInformation
0x1800203b2  test    eax, eax
0x1800203b4  jz      short loc_1800203EC
0x1800203b6  mov     rcx, [rdi]; pSid
0x1800203b9  call    cs:__imp_GetLengthSid
0x1800203bf  mov     ecx, eax; unsigned __int64
0x1800203c1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800203c8  mov     ebp, eax
0x1800203ca  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800203cf  mov     rbx, rax
0x1800203d2  test    rax, rax
0x1800203d5  jz      short loc_18002038E
0x1800203d7  mov     r8, [rdi]; SourceSid
0x1800203da  mov     rdx, rax; DestinationSid
0x1800203dd  mov     ecx, ebp; DestinationSidLength
0x1800203df  call    cs:__imp_RtlCopySid
0x1800203e5  mov     [rsi], rbx
0x1800203e8  xor     ebx, ebx
0x1800203ea  jmp     short loc_180020401
0x1800203ec  call    cs:__imp_GetLastError
0x1800203f2  mov     ebx, eax
0x1800203f4  test    eax, eax
0x1800203f6  jle     short loc_180020401
0x1800203f8  movzx   ebx, ax
0x1800203fb  or      ebx, 80070000h
0x180020401  mov     rcx, rdi
0x180020404  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002040a  mov     eax, ebx
0x18002040c  add     rsp, 38h
0x180020410  pop     rdi
0x180020411  pop     rsi
0x180020412  pop     rbp
0x180020413  pop     rbx
0x180020414  retn
```
