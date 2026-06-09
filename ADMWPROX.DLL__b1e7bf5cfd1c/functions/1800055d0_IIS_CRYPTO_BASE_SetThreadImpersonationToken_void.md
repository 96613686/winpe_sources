# IIS_CRYPTO_BASE::SetThreadImpersonationToken(void *)

- ea: `0x1800055d0`
- end: `0x180005604`
- name: `?SetThreadImpersonationToken@IIS_CRYPTO_BASE@@KAJPEAX@Z`
- size: `52`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000522c`
- `0x180005480`
- `0x180005528`
- `0x180005820`

## callees

- `0x1800055d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800055e7`
- `KERNEL32!GetLastError` at `0x1800055e7`
- `ADVAPI32!SetThreadToken` at `0x1800055dd`
- `ADVAPI32!SetThreadToken` at `0x1800055dd`

## pseudocode

```c
__int64 __fastcall IIS_CRYPTO_BASE::SetThreadImpersonationToken(HANDLE Token)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  v1 = 0;
  if ( !SetThreadToken(0, Token) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x1800055d0  push    rbx
0x1800055d2  sub     rsp, 20h
0x1800055d6  mov     rdx, rcx; Token
0x1800055d9  xor     ebx, ebx
0x1800055db  xor     ecx, ecx; Thread
0x1800055dd  call    cs:__imp_SetThreadToken
0x1800055e3  test    eax, eax
0x1800055e5  jnz     short loc_1800055FC
0x1800055e7  call    cs:__imp_GetLastError
0x1800055ed  mov     ebx, eax
0x1800055ef  test    eax, eax
0x1800055f1  jle     short loc_1800055FC
0x1800055f3  movzx   ebx, ax
0x1800055f6  or      ebx, 80070000h
0x1800055fc  mov     eax, ebx
0x1800055fe  add     rsp, 20h
0x180005602  pop     rbx
0x180005603  retn
```
