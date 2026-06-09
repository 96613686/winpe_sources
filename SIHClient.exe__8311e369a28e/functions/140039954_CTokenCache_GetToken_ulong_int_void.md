# CTokenCache::GetToken(ulong,int,void * *)

- ea: `0x140039954`
- end: `0x1400399ff`
- name: `?GetToken@CTokenCache@@QEBAJKHPEAPEAX@Z`
- size: `171`
- prototype: `int(CTokenCache *__hidden this, unsigned int, int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140038d20`

## callees

- `0x140008de4`
- `0x140008e08`
- `0x140039954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400399ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400399ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003996d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003996d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400399bf`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1400399bf`

## string_xrefs

- `0x14003997d`: `C:\__w\1\s\src\Client\Engine\lib\susenginelib\tokencache.cpp`
- `0x1400399ce`: `C:\__w\1\s\src\Client\Engine\lib\susenginelib\tokencache.cpp`

## pseudocode

```c
__int64 __fastcall CTokenCache::GetToken(CTokenCache *this, __int64 a2, __int64 a3, void **a4)
{
  unsigned int LastError; // ebx
  void *v7; // rcx
  const char *v8; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( this )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( a4 )
  {
    *a4 = 0;
    v7 = (void *)*((_QWORD *)this + 6);
    if ( !v7 || DuplicateTokenEx(v7, 0xEu, 0, SecurityImpersonation, TokenImpersonation, a4) )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x33,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\tokencache.cpp",
                    v8);
  }
  else
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\tokencache.cpp",
      (const char *)0x80004003LL,
      TokenType);
  }
  if ( this )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return LastError;
}

```

## disassembly

```asm
0x140039954  mov     [rsp+arg_8], rbx
0x140039959  push    rdi
0x14003995a  sub     rsp, 30h
0x14003995e  mov     rbx, r9
0x140039961  mov     rdi, rcx
0x140039964  test    rcx, rcx
0x140039967  jz      short loc_140039973
0x140039969  add     rcx, 8; lpCriticalSection
0x14003996d  call    cs:__imp_EnterCriticalSection
0x140039973  test    rbx, rbx
0x140039976  jnz     short loc_140039998
0x140039978  mov     rcx, [rsp+38h]; this
0x14003997d  lea     r8, aCW1SSrcClientE_2; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140039984  mov     ebx, 80004003h
0x140039989  mov     edx, 27h ; '''; void *
0x14003998e  mov     r9d, ebx; char *
0x140039991  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140039996  jmp     short loc_1400399E3
0x140039998  mov     qword ptr [rbx], 0
0x14003999f  mov     rcx, [rdi+30h]; hExistingToken
0x1400399a3  test    rcx, rcx
0x1400399a6  jz      short loc_1400399E1
0x1400399a8  mov     r9d, 2; ImpersonationLevel
0x1400399ae  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1400399b3  xor     r8d, r8d; lpTokenAttributes
0x1400399b6  mov     [rsp+38h+TokenType], r9d; TokenType
0x1400399bb  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1400399bf  call    cs:__imp_DuplicateTokenEx
0x1400399c5  test    eax, eax
0x1400399c7  jnz     short loc_1400399E1
0x1400399c9  mov     rcx, [rsp+38h]; this
0x1400399ce  lea     r8, aCW1SSrcClientE_2; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1400399d5  lea     edx, [rax+33h]; void *
0x1400399d8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400399dd  mov     ebx, eax
0x1400399df  jmp     short loc_1400399E3
0x1400399e1  xor     ebx, ebx
0x1400399e3  test    rdi, rdi
0x1400399e6  jz      short loc_1400399F2
0x1400399e8  lea     rcx, [rdi+8]; lpCriticalSection
0x1400399ec  call    cs:__imp_LeaveCriticalSection
0x1400399f2  mov     eax, ebx
0x1400399f4  mov     rbx, [rsp+38h+arg_8]
0x1400399f9  add     rsp, 30h
0x1400399fd  pop     rdi
0x1400399fe  retn
```
