# CNgscbToken::GetFullToken(CNgscbToken &)

- ea: `0x180022008`
- end: `0x18002210e`
- name: `?GetFullToken@CNgscbToken@@QEBAJAEAV1@@Z`
- size: `262`
- prototype: `__int64 __fastcall(CNgscbToken *__hidden this, struct CNgscbToken *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003b560`
- `0x18004a384`
- `0x180056bcc`
- `0x180078eec`

## callees

- `0x18001a508`
- `0x180022008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002205d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002205d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800220c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800220c8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022100`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180022100`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002204d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002209a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002204d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002209a`

## pseudocode

```c
__int64 __fastcall CNgscbToken::GetFullToken(HANDLE *this, struct CNgscbToken *a2)
{
  signed int LastError; // eax
  unsigned int v5; // edi
  HANDLE v6; // rcx
  BOOL v7; // eax
  HANDLE v8; // rbx
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp+38h] BYREF

  TokenInformation = 0;
  hObject = 0;
  ReturnLength = 0;
  if ( GetTokenInformation(*this, TokenElevationType, &TokenInformation, 4u, &ReturnLength)
    && ((v6 = *this, TokenInformation != 3)
      ? (v7 = DuplicateTokenEx(v6, 0, 0, SecurityImpersonation, TokenPrimary, &hObject))
      : (v7 = GetTokenInformation(v6, TokenLinkedToken, &hObject, 8u, &ReturnLength)),
        v7) )
  {
    v8 = hObject;
    v5 = 0;
    SH<void *,SH_HANDLE>::Reset(a2);
    *(_QWORD *)a2 = v8;
    hObject = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hObject )
    CloseHandle(hObject);
  return v5;
}

```

## disassembly

```asm
0x180022008  mov     [rsp-18h+arg_8], rbx
0x18002200d  push    rbp
0x18002200e  push    rsi
0x18002200f  push    rdi
0x180022010  mov     rbp, rsp
0x180022013  sub     rsp, 30h
0x180022017  mov     r9d, 4; TokenInformationLength
0x18002201d  mov     [rbp+TokenInformation], 0
0x180022024  mov     rsi, rdx
0x180022027  mov     [rbp+hObject], 0
0x18002202f  mov     rbx, rcx
0x180022032  mov     [rbp+arg_10], 0
0x180022039  mov     rcx, [rcx]; TokenHandle
0x18002203c  lea     rax, [rbp+arg_10]
0x180022040  lea     edx, [r9+0Eh]; TokenInformationClass
0x180022044  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180022049  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18002204d  call    cs:__imp_GetTokenInformation
0x180022054  nop     dword ptr [rax+rax+00h]
0x180022059  test    eax, eax
0x18002205b  jnz     short loc_18002207A
0x18002205d  call    cs:__imp_GetLastError
0x180022064  nop     dword ptr [rax+rax+00h]
0x180022069  mov     edi, eax
0x18002206b  test    eax, eax
0x18002206d  jle     short loc_1800220BF
0x18002206f  movzx   edi, ax
0x180022072  or      edi, 80070000h
0x180022078  jmp     short loc_1800220BF
0x18002207a  cmp     [rbp+TokenInformation], 3
0x18002207e  mov     rcx, [rbx]; hExistingToken
0x180022081  jnz     short loc_1800220E4
0x180022083  mov     r9d, 8; TokenInformationLength
0x180022089  lea     rax, [rbp+arg_10]
0x18002208d  lea     r8, [rbp+hObject]; TokenInformation
0x180022091  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180022096  lea     edx, [r9+0Bh]; TokenInformationClass
0x18002209a  call    cs:__imp_GetTokenInformation
0x1800220a1  nop     dword ptr [rax+rax+00h]
0x1800220a6  test    eax, eax
0x1800220a8  jz      short loc_18002205D
0x1800220aa  mov     rbx, [rbp+hObject]
0x1800220ae  xor     edi, edi
0x1800220b0  mov     rcx, rsi
0x1800220b3  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x1800220b8  mov     [rsi], rbx
0x1800220bb  mov     [rbp+hObject], rdi
0x1800220bf  mov     rcx, [rbp+hObject]; hObject
0x1800220c3  test    rcx, rcx
0x1800220c6  jz      short loc_1800220D4
0x1800220c8  call    cs:__imp_CloseHandle
0x1800220cf  nop     dword ptr [rax+rax+00h]
0x1800220d4  mov     rbx, [rsp+30h+arg_8]
0x1800220d9  mov     eax, edi
0x1800220db  add     rsp, 30h
0x1800220df  pop     rdi
0x1800220e0  pop     rsi
0x1800220e1  pop     rbp
0x1800220e2  retn
0x1800220e4  lea     rax, [rbp+hObject]
0x1800220e8  mov     r9d, 2; ImpersonationLevel
0x1800220ee  mov     [rsp+30h+phNewToken], rax; phNewToken
0x1800220f3  xor     r8d, r8d; lpTokenAttributes
0x1800220f6  xor     edx, edx; dwDesiredAccess
0x1800220f8  mov     dword ptr [rsp+30h+ReturnLength], 1; TokenType
0x180022100  call    cs:__imp_DuplicateTokenEx
0x180022107  nop     dword ptr [rax+rax+00h]
0x18002210c  jmp     short loc_1800220A6
```
