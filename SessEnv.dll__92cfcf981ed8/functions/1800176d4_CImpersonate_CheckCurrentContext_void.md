# CImpersonate::CheckCurrentContext(void *)

- ea: `0x1800176d4`
- end: `0x1800178d7`
- name: `?CheckCurrentContext@CImpersonate@@AEAAJPEAX@Z`
- size: `515`
- prototype: `__int64 __fastcall(CImpersonate *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017670`
- `0x18005a0ec`

## callees

- `0x180003f30`
- `0x1800176d4`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180017868`
- `ntdll!RtlEqualSid` at `0x180017868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017895`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017895`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017719`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017719`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017702`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017702`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017756`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800177cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800177ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017854`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017756`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800177cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800177ff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017854`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017790`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001782c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017790`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001782c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178b1`

## string_xrefs

- `0x18001776d`: `CheckCurrentContext: FAILED to get size infomration for input token, Error %x`
- `0x180017816`: `CheckCurrentContext: FAILED to get size infomration for current token, Error %x`
- `0x1800177dd`: `CheckCurrentContext: FAILED to get token infomration for input token, Error %x`
- `0x180017876`: `TERMSRV: CheckCurrentContext - Different user is being impersonated`

## pseudocode

```c
__int64 __fastcall CImpersonate::CheckCurrentContext(CImpersonate *this, void *a2)
{
  PSID *v3; // rsi
  PSID *v4; // rdi
  HANDLE CurrentThread; // rax
  __int64 v6; // rbx
  DWORD LastError; // eax
  DWORD v8; // ebx
  DWORD v9; // eax
  DWORD v10; // ebx
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  int v13; // [rsp+64h] [rbp+34h]
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  v13 = HIDWORD(this);
  TokenHandle = 0;
  TokenInformationLength = 0;
  v3 = 0;
  v4 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    LODWORD(v6) = GetLastError();
    goto LABEL_20;
  }
  LODWORD(v6) = 1375;
  if ( a2 )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      LODWORD(v6) = LastError;
      if ( LastError != 122 )
      {
        _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for input token, Error %x", LastError);
        goto LABEL_20;
      }
    }
    v8 = TokenInformationLength;
    v3 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v3 )
    {
LABEL_9:
      LODWORD(v6) = 8;
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to allocate memory");
      goto LABEL_20;
    }
    if ( !GetTokenInformation(a2, TokenUser, v3, v8, &TokenInformationLength) )
      goto LABEL_11;
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v9 = GetLastError();
      LODWORD(v6) = v9;
      if ( v9 != 122 )
      {
        _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get size infomration for current token, Error %x", v9);
        goto LABEL_20;
      }
    }
    v10 = TokenInformationLength;
    v4 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v4 )
      goto LABEL_9;
    if ( !GetTokenInformation(TokenHandle, TokenUser, v4, v10, &TokenInformationLength) )
    {
LABEL_11:
      v6 = GetLastError();
      _DbgPrintMessage(8, "CheckCurrentContext: FAILED to get token infomration for input token, Error %x", v6);
      goto LABEL_20;
    }
    if ( RtlEqualSid(*v3, *v4) )
    {
      LODWORD(v6) = 0;
    }
    else
    {
      _DbgPrintMessage(4, "TERMSRV: CheckCurrentContext - Different user is being impersonated");
      LODWORD(v6) = 1375;
    }
  }
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v3 )
    LocalFree(v3);
  if ( v4 )
    LocalFree(v4);
  if ( (int)v6 > 0 )
    LODWORD(v6) = (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800176d4  mov     [rsp-28h+arg_8], rbx
0x1800176d9  mov     qword ptr [rsp-28h+TokenInformationLength], rcx
0x1800176de  push    rbp
0x1800176df  push    rsi
0x1800176e0  push    rdi
0x1800176e1  push    r12
0x1800176e3  push    r14
0x1800176e5  mov     rbp, rsp
0x1800176e8  sub     rsp, 30h
0x1800176ec  mov     r14, rdx
0x1800176ef  mov     [rbp+TokenHandle], 0
0x1800176f7  mov     [rbp+TokenInformationLength], 0
0x1800176fe  xor     esi, esi
0x180017700  xor     edi, edi
0x180017702  call    cs:__imp_GetCurrentThread
0x180017708  lea     r12d, [rsi+1]
0x18001770c  mov     rcx, rax; ThreadHandle
0x18001770f  mov     r8d, r12d; OpenAsSelf
0x180017712  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180017716  lea     edx, [rsi+0Eh]; DesiredAccess
0x180017719  call    cs:__imp_OpenThreadToken
0x18001771f  test    eax, eax
0x180017721  jnz     short loc_180017730
0x180017723  call    cs:__imp_GetLastError
0x180017729  mov     ebx, eax
0x18001772b  jmp     loc_18001788C
0x180017730  mov     ebx, 55Fh
0x180017735  test    r14, r14
0x180017738  jz      loc_18001788C
0x18001773e  lea     rax, [rbp+TokenInformationLength]
0x180017742  mov     [rbp+TokenInformationLength], esi
0x180017745  xor     r9d, r9d; TokenInformationLength
0x180017748  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001774d  xor     r8d, r8d; TokenInformation
0x180017750  mov     edx, r12d; TokenInformationClass
0x180017753  mov     rcx, r14; TokenHandle
0x180017756  call    cs:__imp_GetTokenInformation
0x18001775c  test    eax, eax
0x18001775e  jnz     short loc_180017786
0x180017760  call    cs:__imp_GetLastError
0x180017766  mov     ebx, eax
0x180017768  cmp     eax, 7Ah ; 'z'
0x18001776b  jz      short loc_180017786
0x18001776d  lea     rdx, aCheckcurrentco_0; "CheckCurrentContext: FAILED to get size"...
0x180017774  mov     r8d, eax
0x180017777  mov     ecx, 8; int
0x18001777c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017781  jmp     loc_18001788C
0x180017786  mov     ebx, [rbp+TokenInformationLength]
0x180017789  mov     ecx, 40h ; '@'; uFlags
0x18001778e  mov     edx, ebx; uBytes
0x180017790  call    cs:__imp_LocalAlloc
0x180017796  mov     rsi, rax
0x180017799  test    rax, rax
0x18001779c  jnz     short loc_1800177B6
0x18001779e  mov     ebx, 8
0x1800177a3  lea     rdx, aCheckcurrentco_3; "CheckCurrentContext: FAILED to allocate"...
0x1800177aa  mov     ecx, ebx; int
0x1800177ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800177b1  jmp     loc_18001788C
0x1800177b6  lea     rax, [rbp+TokenInformationLength]
0x1800177ba  mov     r9d, ebx; TokenInformationLength
0x1800177bd  mov     r8, rsi; TokenInformation
0x1800177c0  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800177c5  mov     edx, r12d; TokenInformationClass
0x1800177c8  mov     rcx, r14; TokenHandle
0x1800177cb  call    cs:__imp_GetTokenInformation
0x1800177d1  test    eax, eax
0x1800177d3  jnz     short loc_1800177E6
0x1800177d5  call    cs:__imp_GetLastError
0x1800177db  mov     ebx, eax
0x1800177dd  lea     rdx, aCheckcurrentco; "CheckCurrentContext: FAILED to get toke"...
0x1800177e4  jmp     short loc_180017774
0x1800177e6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800177ea  lea     rax, [rbp+TokenInformationLength]
0x1800177ee  xor     r9d, r9d; TokenInformationLength
0x1800177f1  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800177f6  xor     r8d, r8d; TokenInformation
0x1800177f9  mov     [rbp+TokenInformationLength], edi
0x1800177fc  mov     edx, r12d; TokenInformationClass
0x1800177ff  call    cs:__imp_GetTokenInformation
0x180017805  test    eax, eax
0x180017807  jnz     short loc_180017822
0x180017809  call    cs:__imp_GetLastError
0x18001780f  mov     ebx, eax
0x180017811  cmp     eax, 7Ah ; 'z'
0x180017814  jz      short loc_180017822
0x180017816  lea     rdx, aCheckcurrentco_1; "CheckCurrentContext: FAILED to get size"...
0x18001781d  jmp     loc_180017774
0x180017822  mov     ebx, [rbp+TokenInformationLength]
0x180017825  mov     ecx, 40h ; '@'; uFlags
0x18001782a  mov     edx, ebx; uBytes
0x18001782c  call    cs:__imp_LocalAlloc
0x180017832  mov     rdi, rax
0x180017835  test    rax, rax
0x180017838  jz      loc_18001779E
0x18001783e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180017842  lea     rax, [rbp+TokenInformationLength]
0x180017846  mov     r9d, ebx; TokenInformationLength
0x180017849  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001784e  mov     r8, rdi; TokenInformation
0x180017851  mov     edx, r12d; TokenInformationClass
0x180017854  call    cs:__imp_GetTokenInformation
0x18001785a  test    eax, eax
0x18001785c  jz      loc_1800177D5
0x180017862  mov     rdx, [rdi]; Sid2
0x180017865  mov     rcx, [rsi]; Sid1
0x180017868  call    cs:__imp_RtlEqualSid
0x18001786e  test    al, al
0x180017870  jz      short loc_180017876
0x180017872  xor     ebx, ebx
0x180017874  jmp     short loc_18001788C
0x180017876  lea     rdx, aTermsrvCheckcu; "TERMSRV: CheckCurrentContext - Differen"...
0x18001787d  mov     ecx, 4; int
0x180017882  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017887  mov     ebx, 55Fh
0x18001788c  mov     rcx, [rbp+TokenHandle]; hObject
0x180017890  test    rcx, rcx
0x180017893  jz      short loc_18001789B
0x180017895  call    cs:__imp_CloseHandle
0x18001789b  test    rsi, rsi
0x18001789e  jz      short loc_1800178A9
0x1800178a0  mov     rcx, rsi; hMem
0x1800178a3  call    cs:__imp_LocalFree
0x1800178a9  test    rdi, rdi
0x1800178ac  jz      short loc_1800178B7
0x1800178ae  mov     rcx, rdi; hMem
0x1800178b1  call    cs:__imp_LocalFree
0x1800178b7  test    ebx, ebx
0x1800178b9  jle     short loc_1800178C4
0x1800178bb  movzx   ebx, bx
0x1800178be  or      ebx, 80070000h
0x1800178c4  mov     eax, ebx
0x1800178c6  mov     rbx, [rsp+30h+arg_8]
0x1800178cb  add     rsp, 30h
0x1800178cf  pop     r14
0x1800178d1  pop     r12
0x1800178d3  pop     rdi
0x1800178d4  pop     rsi
0x1800178d5  pop     rbp
0x1800178d6  retn
```
