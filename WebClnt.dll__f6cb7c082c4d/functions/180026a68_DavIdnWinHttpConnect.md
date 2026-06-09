# DavIdnWinHttpConnect

- ea: `0x180026a68`
- end: `0x180026b42`
- name: `DavIdnWinHttpConnect`
- size: `218`
- prototype: `HINTERNET __fastcall(HINTERNET hSession, WCHAR *lpUnicodeCharStr, INTERNET_PORT)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049bc`
- `0x180007e10`
- `0x1800099d0`
- `0x18001ca70`
- `0x180021f00`

## callees

- `0x180026a68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026aab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026ada`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026ada`
- `KERNEL32!LocalFree` at `0x180026b01`
- `KERNEL32!LocalFree` at `0x180026b2a`
- `KERNEL32!LocalFree` at `0x180026b01`
- `KERNEL32!LocalFree` at `0x180026b2a`
- `KERNEL32!LocalAlloc` at `0x180026ac7`
- `KERNEL32!LocalAlloc` at `0x180026ac7`
- `KERNEL32!IdnToAscii` at `0x180026aa1`
- `KERNEL32!IdnToAscii` at `0x180026af4`
- `KERNEL32!IdnToAscii` at `0x180026aa1`
- `KERNEL32!IdnToAscii` at `0x180026af4`
- `WINHTTP!WinHttpConnect` at `0x180026b19`
- `WINHTTP!WinHttpConnect` at `0x180026b19`

## pseudocode

```c
HINTERNET __fastcall DavIdnWinHttpConnect(HINTERNET hSession, WCHAR *lpUnicodeCharStr, INTERNET_PORT a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int cchASCIIChar; // ebp
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  HINTERNET v12; // rdi

  v3 = -1;
  do
    ++v3;
  while ( lpUnicodeCharStr[v3] );
  v7 = IdnToAscii(2u, lpUnicodeCharStr, v3, 0, 0);
  if ( !v7 )
    goto LABEL_4;
  if ( v7 == (_DWORD)v3 )
  {
    v11 = lpUnicodeCharStr;
  }
  else
  {
    cchASCIIChar = v7 + 1;
    v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * (v7 + 1));
    v11 = v10;
    if ( !v10 )
    {
      SetLastError(0x5AAu);
      return 0;
    }
    if ( !IdnToAscii(2u, lpUnicodeCharStr, v3, v10, cchASCIIChar) )
    {
      LocalFree(v11);
LABEL_4:
      GetLastError();
      return 0;
    }
  }
  v12 = WinHttpConnect(hSession, v11, a3, 0);
  if ( v11 != lpUnicodeCharStr )
    LocalFree(v11);
  return v12;
}

```

## disassembly

```asm
0x180026a68  push    rbx
0x180026a6a  push    rbp
0x180026a6b  push    rsi
0x180026a6c  push    rdi
0x180026a6d  push    r12
0x180026a6f  push    r14
0x180026a71  push    r15
0x180026a73  sub     rsp, 30h
0x180026a77  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180026a7b  movzx   r14d, r8w
0x180026a7f  xor     r12d, r12d
0x180026a82  mov     rsi, rdx
0x180026a85  mov     r15, rcx
0x180026a88  inc     rdi
0x180026a8b  cmp     [rdx+rdi*2], r12w
0x180026a90  jnz     short loc_180026A88
0x180026a92  xor     r9d, r9d; lpASCIICharStr
0x180026a95  mov     [rsp+68h+cchASCIIChar], r12d; cchASCIIChar
0x180026a9a  mov     r8d, edi; cchUnicodeChar
0x180026a9d  lea     ecx, [r9+2]; dwFlags
0x180026aa1  call    cs:__imp_IdnToAscii
0x180026aa7  test    eax, eax
0x180026aa9  jnz     short loc_180026AB5
0x180026aab  call    cs:__imp_GetLastError
0x180026ab1  xor     eax, eax
0x180026ab3  jmp     short loc_180026B33
0x180026ab5  cmp     eax, edi
0x180026ab7  jz      short loc_180026B09
0x180026ab9  lea     ebp, [rax+1]
0x180026abc  mov     ecx, 40h ; '@'; uFlags
0x180026ac1  movsxd  rdx, ebp
0x180026ac4  add     rdx, rdx; uBytes
0x180026ac7  call    cs:__imp_LocalAlloc
0x180026acd  mov     rbx, rax
0x180026ad0  test    rax, rax
0x180026ad3  jnz     short loc_180026AE2
0x180026ad5  mov     ecx, 5AAh; dwErrCode
0x180026ada  call    cs:__imp_SetLastError
0x180026ae0  jmp     short loc_180026AB1
0x180026ae2  mov     r9, rbx; lpASCIICharStr
0x180026ae5  mov     [rsp+68h+cchASCIIChar], ebp; cchASCIIChar
0x180026ae9  mov     r8d, edi; cchUnicodeChar
0x180026aec  mov     rdx, rsi; lpUnicodeCharStr
0x180026aef  mov     ecx, 2; dwFlags
0x180026af4  call    cs:__imp_IdnToAscii
0x180026afa  test    eax, eax
0x180026afc  jnz     short loc_180026B0C
0x180026afe  mov     rcx, rbx; hMem
0x180026b01  call    cs:__imp_LocalFree
0x180026b07  jmp     short loc_180026AAB
0x180026b09  mov     rbx, rsi
0x180026b0c  xor     r9d, r9d; dwReserved
0x180026b0f  movzx   r8d, r14w; nServerPort
0x180026b13  mov     rdx, rbx; pswzServerName
0x180026b16  mov     rcx, r15; hSession
0x180026b19  call    cs:__imp_WinHttpConnect
0x180026b1f  mov     rdi, rax
0x180026b22  cmp     rbx, rsi
0x180026b25  jz      short loc_180026B30
0x180026b27  mov     rcx, rbx; hMem
0x180026b2a  call    cs:__imp_LocalFree
0x180026b30  mov     rax, rdi
0x180026b33  add     rsp, 30h
0x180026b37  pop     r15
0x180026b39  pop     r14
0x180026b3b  pop     r12
0x180026b3d  pop     rdi
0x180026b3e  pop     rsi
0x180026b3f  pop     rbp
0x180026b40  pop     rbx
0x180026b41  retn
```
