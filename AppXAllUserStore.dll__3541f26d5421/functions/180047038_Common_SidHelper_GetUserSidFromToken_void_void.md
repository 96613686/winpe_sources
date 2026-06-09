# Common::SidHelper::GetUserSidFromToken(void *,void * *)

- ea: `0x180047038`
- end: `0x1800471f1`
- name: `?GetUserSidFromToken@SidHelper@Common@@SAJPEAXPEAPEAX@Z`
- size: `441`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800203e0`

## callees

- `0x180007a10`
- `0x18000d710`
- `0x180018248`
- `0x18001a324`
- `0x180047038`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470b6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800471a6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800471a6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180047157`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180047157`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800470a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047130`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800470a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180047130`

## string_xrefs

- `0x180047064`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x1800470c5`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x1800470fc`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x18004713e`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x180047180`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x1800471b4`: `onecore\base\appmodel\common\sidhelper.cpp`

## pseudocode

```c
__int64 __fastcall Common::SidHelper::GetUserSidFromToken(HANDLE TokenHandle, void **a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  const char *v7; // r9
  PSID *v8; // rbx
  const char *v9; // r9
  unsigned int LastError; // esi
  DWORD LengthSid; // eax
  DWORD v12; // r14d
  void *v13; // rdi
  const char *v14; // r9
  int ReturnLength; // [rsp+20h] [rbp-10h]
  int ReturnLengtha; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF

  if ( !TokenHandle )
  {
    v4 = 71;
LABEL_3:
    v5 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
      (const char *)v5,
      ReturnLength);
    return v5;
  }
  if ( !a2 )
  {
    v4 = 72;
    goto LABEL_3;
  }
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v5 = -2147418113;
    v4 = 75;
    goto LABEL_4;
  }
  if ( GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4C,
             (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
             v7);
  TokenInformation = 0;
  Common::GlobalHeap::Alloc(TokenInformationLength, &TokenInformation);
  v8 = (PSID *)TokenInformation;
  if ( TokenInformation )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    {
      LengthSid = GetLengthSid(*v8);
      TokenInformation = 0;
      v12 = LengthSid;
      Common::GlobalHeap::Alloc(LengthSid, &TokenInformation);
      v13 = TokenInformation;
      if ( TokenInformation )
      {
        if ( CopySid(v12, TokenInformation, *v8) )
        {
          *a2 = v13;
          LastError = 0;
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x56,
                        (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
                        v14);
          Common::GlobalHeap::Free(v13);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
          (const char *)0x8007000ELL,
          ReturnLengtha);
        LastError = -2147024882;
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x50,
                    (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
                    v9);
    }
    Common::GlobalHeap::Free(v8);
    return LastError;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180047038  mov     [rsp-18h+arg_8], rbx
0x18004703d  mov     [rsp-18h+arg_18], rsi
0x180047042  push    rbp
0x180047043  push    rdi
0x180047044  push    r14
0x180047046  mov     rbp, rsp
0x180047049  sub     rsp, 30h
0x18004704d  mov     rsi, rdx
0x180047050  mov     rdi, rcx
0x180047053  test    rcx, rcx
0x180047056  jnz     short loc_18004707A
0x180047058  lea     edx, [rcx+47h]; void *
0x18004705b  mov     ebx, 80070057h
0x180047060  mov     rcx, [rbp+18h]; this
0x180047064  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\common\\sidhel"...
0x18004706b  mov     r9d, ebx; char *
0x18004706e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047073  mov     eax, ebx
0x180047075  jmp     loc_1800471DE
0x18004707a  test    rsi, rsi
0x18004707d  jnz     short loc_180047084
0x18004707f  lea     edx, [rsi+48h]
0x180047082  jmp     short loc_18004705B
0x180047084  xor     r9d, r9d; TokenInformationLength
0x180047087  mov     [rbp+TokenInformationLength], 0
0x18004708e  lea     rax, [rbp+TokenInformationLength]
0x180047092  xor     r8d, r8d; TokenInformation
0x180047095  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x18004709a  lea     r14d, [r9+1]
0x18004709e  mov     edx, r14d; TokenInformationClass
0x1800470a1  call    cs:__imp_GetTokenInformation
0x1800470a7  test    eax, eax
0x1800470a9  jz      short loc_1800470B6
0x1800470ab  mov     ebx, 8000FFFFh
0x1800470b0  lea     edx, [r14+4Ah]
0x1800470b4  jmp     short loc_180047060
0x1800470b6  call    cs:__imp_GetLastError
0x1800470bc  cmp     eax, 7Ah ; 'z'
0x1800470bf  jz      short loc_1800470DB
0x1800470c1  mov     rcx, [rbp+18h]; this
0x1800470c5  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\common\\sidhel"...
0x1800470cc  mov     edx, 4Ch ; 'L'; void *
0x1800470d1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800470d6  jmp     loc_1800471DE
0x1800470db  mov     ecx, [rbp+TokenInformationLength]; Size
0x1800470de  lea     rdx, [rbp+TokenInformation]; void **
0x1800470e2  mov     [rbp+TokenInformation], 0
0x1800470ea  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800470ef  mov     rbx, [rbp+TokenInformation]
0x1800470f3  test    rbx, rbx
0x1800470f6  jnz     short loc_18004711A
0x1800470f8  mov     rcx, [rbp+18h]; this
0x1800470fc  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\common\\sidhel"...
0x180047103  mov     edi, 8007000Eh
0x180047108  lea     edx, [rbx+4Fh]; void *
0x18004710b  mov     r9d, edi; char *
0x18004710e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047113  mov     eax, edi
0x180047115  jmp     loc_1800471DE
0x18004711a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004711e  lea     rax, [rbp+TokenInformationLength]
0x180047122  mov     r8, rbx; TokenInformation
0x180047125  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x18004712a  mov     edx, r14d; TokenInformationClass
0x18004712d  mov     rcx, rdi; TokenHandle
0x180047130  call    cs:__imp_GetTokenInformation
0x180047136  test    eax, eax
0x180047138  jnz     short loc_180047154
0x18004713a  mov     rcx, [rbp+18h]; this
0x18004713e  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\common\\sidhel"...
0x180047145  lea     edx, [rax+50h]; void *
0x180047148  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004714d  mov     esi, eax
0x18004714f  jmp     loc_1800471D4
0x180047154  mov     rcx, [rbx]; pSid
0x180047157  call    cs:__imp_GetLengthSid
0x18004715d  lea     rdx, [rbp+TokenInformation]; void **
0x180047161  mov     [rbp+TokenInformation], 0
0x180047169  mov     ecx, eax; Size
0x18004716b  mov     r14d, eax
0x18004716e  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x180047173  mov     rdi, [rbp+TokenInformation]
0x180047177  test    rdi, rdi
0x18004717a  jnz     short loc_18004719D
0x18004717c  mov     rcx, [rbp+18h]; this
0x180047180  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\common\\sidhel"...
0x180047187  mov     edi, 8007000Eh
0x18004718c  mov     edx, 55h ; 'U'; void *
0x180047191  mov     r9d, edi; char *
0x180047194  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047199  mov     esi, edi
0x18004719b  jmp     short loc_1800471D4
0x18004719d  mov     r8, [rbx]; pSourceSid
0x1800471a0  mov     rdx, rdi; pDestinationSid
0x1800471a3  mov     ecx, r14d; nDestinationSidLength
0x1800471a6  call    cs:__imp_CopySid
0x1800471ac  test    eax, eax
0x1800471ae  jnz     short loc_1800471CF
0x1800471b0  mov     rcx, [rbp+18h]; this
0x1800471b4  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\common\\sidhel"...
0x1800471bb  lea     edx, [rax+56h]; void *
0x1800471be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800471c3  mov     rcx, rdi; void *
0x1800471c6  mov     esi, eax
0x1800471c8  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800471cd  jmp     short loc_1800471D4
0x1800471cf  mov     [rsi], rdi
0x1800471d2  xor     esi, esi
0x1800471d4  mov     rcx, rbx; void *
0x1800471d7  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800471dc  mov     eax, esi
0x1800471de  mov     rbx, [rsp+30h+arg_8]
0x1800471e3  mov     rsi, [rsp+30h+arg_18]
0x1800471e8  add     rsp, 30h
0x1800471ec  pop     r14
0x1800471ee  pop     rdi
0x1800471ef  pop     rbp
0x1800471f0  retn
```
