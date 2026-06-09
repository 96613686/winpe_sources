# IIS_CRYPTO_BASE::GetThreadImpersonationToken(void * *)

- ea: `0x18000534c`
- end: `0x1800053b6`
- name: `?GetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAPEAX@Z`
- size: `106`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000522c`
- `0x180005480`
- `0x180005528`
- `0x180005820`

## callees

- `0x18000534c`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000535b`
- `KERNEL32!GetCurrentThread` at `0x18000535b`
- `KERNEL32!GetLastError` at `0x18000537a`
- `KERNEL32!GetLastError` at `0x18000537a`
- `ADVAPI32!OpenThreadToken` at `0x180005370`
- `ADVAPI32!OpenThreadToken` at `0x180005370`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_BASE::GetThreadImpersonationToken(PHANDLE TokenHandle)
{
  unsigned int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax

  v2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 && LastError != 120 && LastError != 50 )
    {
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      else
        v2 = LastError;
    }
    *TokenHandle = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18000534c  mov     [rsp+arg_0], rbx
0x180005351  push    rdi
0x180005352  sub     rsp, 20h
0x180005356  mov     rdi, rcx
0x180005359  xor     ebx, ebx
0x18000535b  call    cs:__imp_GetCurrentThread
0x180005361  mov     r9, rdi; TokenHandle
0x180005364  lea     r8d, [rbx+1]; OpenAsSelf
0x180005368  mov     rcx, rax; ThreadHandle
0x18000536b  mov     edx, 0F01FFh; DesiredAccess
0x180005370  call    cs:__imp_OpenThreadToken
0x180005376  test    eax, eax
0x180005378  jnz     short loc_1800053A9
0x18000537a  call    cs:__imp_GetLastError
0x180005380  cmp     eax, 3F0h
0x180005385  jz      short loc_1800053A2
0x180005387  cmp     eax, 78h ; 'x'
0x18000538a  jz      short loc_1800053A2
0x18000538c  cmp     eax, 32h ; '2'
0x18000538f  jz      short loc_1800053A2
0x180005391  test    eax, eax
0x180005393  jg      short loc_180005399
0x180005395  mov     ebx, eax
0x180005397  jmp     short loc_1800053A2
0x180005399  movzx   ebx, ax
0x18000539c  or      ebx, 80070000h
0x1800053a2  mov     qword ptr [rdi], 0
0x1800053a9  mov     eax, ebx
0x1800053ab  mov     rbx, [rsp+28h+arg_0]
0x1800053b0  add     rsp, 20h
0x1800053b4  pop     rdi
0x1800053b5  retn
```
