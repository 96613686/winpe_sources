# GetResourceLibraryPathInternal

- ea: `0x180092bc0`
- end: `0x180092d5b`
- name: `GetResourceLibraryPathInternal`
- size: `411`
- prototype: `bool __fastcall(HMODULE, __int64, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180081e7c`

## callees

- `0x1800929fc`
- `0x180092a54`
- `0x180092b20`
- `0x180092bc0`
- `0x180092d80`
- `0x180092e04`
- `0x180093270`

## pseudocode

```c
bool __fastcall GetResourceLibraryPathInternal(HMODULE a1, __int64 a2, __int64 a3, const WCHAR *a4)
{
  unsigned __int16 v5; // di
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  __int64 v10; // rdx
  _WORD v12[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v13[264]; // [rsp+240h] [rbp+140h] BYREF

  v12[0] = 0;
  v5 = a2;
  if ( (_WORD)a2 == 3076 )
  {
    v5 = 1028;
  }
  else if ( (_WORD)a2 == 4100 )
  {
    v5 = 2052;
  }
  if ( !GetResourceDLLBasePathAndName(a1, a2, v13, (__int64)a4, v12)
    || !(unsigned __int8)GetResourceDLLPathLanguageSpecific((_DWORD)a4, v6, v5, (unsigned int)v13, (__int64)v12) )
  {
    return 0;
  }
  if ( PathFileExists(a4) )
    return 1;
  if ( !(unsigned __int8)GetResourceDLLPathLanguageSpecific((_DWORD)a4, v7, v5, (unsigned int)v13, (__int64)v12) )
    return 0;
  if ( PathFileExists(a4) )
    return 1;
  if ( v5 != 1033 )
  {
    if ( (unsigned __int8)GetResourceDLLPathLanguageSpecific((_DWORD)a4, v8, 1033, (unsigned int)v13, (__int64)v12) )
    {
      if ( PathFileExists(a4) )
        return 1;
      if ( (unsigned __int8)GetResourceDLLPathLanguageSpecific((_DWORD)a4, v9, 1033, (unsigned int)v13, (__int64)v12) )
      {
        if ( !PathFileExists(a4) )
          goto LABEL_15;
        return 1;
      }
    }
    return 0;
  }
LABEL_15:
  if ( (unsigned __int8)CopyString(a4, 261, v13) )
    PathAppend(a4, v10, v12);
  return PathFileExists(a4) != 0;
}

```

## disassembly

```asm
0x180092bc0  mov     [rsp-8+arg_10], rbx
0x180092bc5  push    rbp
0x180092bc6  push    rsi
0x180092bc7  push    rdi
0x180092bc8  lea     rbp, [rsp-360h]
0x180092bd0  sub     rsp, 460h
0x180092bd7  mov     rax, cs:__security_cookie
0x180092bde  xor     rax, rsp
0x180092be1  mov     [rbp+370h+var_20], rax
0x180092be8  xor     eax, eax
0x180092bea  mov     rbx, r9
0x180092bed  mov     [rsp+470h+var_440], ax
0x180092bf2  movzx   edi, dx
0x180092bf5  mov     eax, 0C04h
0x180092bfa  cmp     dx, ax
0x180092bfd  jz      short loc_180092C10
0x180092bff  mov     eax, 1004h
0x180092c04  cmp     dx, ax
0x180092c07  jnz     short loc_180092C15
0x180092c09  mov     edi, 804h
0x180092c0e  jmp     short loc_180092C15
0x180092c10  mov     edi, 404h
0x180092c15  lea     rax, [rsp+470h+var_440]
0x180092c1a  lea     r8, [rbp+370h+var_230]
0x180092c21  mov     [rsp+470h+var_450], rax
0x180092c26  call    GetResourceDLLBasePathAndName
0x180092c2b  test    al, al
0x180092c2d  jz      loc_180092D37
0x180092c33  lea     rax, [rsp+470h+var_440]
0x180092c38  movzx   r8d, di
0x180092c3c  lea     r9, [rbp+370h+var_230]
0x180092c43  mov     [rsp+470h+var_450], rax
0x180092c48  mov     rcx, rbx
0x180092c4b  call    GetResourceDLLPathLanguageSpecific
0x180092c50  test    al, al
0x180092c52  jz      loc_180092D37
0x180092c58  mov     rcx, rbx; lpFileName
0x180092c5b  call    PathFileExists
0x180092c60  test    al, al
0x180092c62  jnz     loc_180092D33
0x180092c68  lea     rax, [rsp+470h+var_440]
0x180092c6d  movzx   r8d, di
0x180092c71  lea     r9, [rbp+370h+var_230]
0x180092c78  mov     [rsp+470h+var_450], rax
0x180092c7d  mov     rcx, rbx
0x180092c80  call    GetResourceDLLPathLanguageSpecific
0x180092c85  test    al, al
0x180092c87  jz      loc_180092D37
0x180092c8d  mov     rcx, rbx; lpFileName
0x180092c90  call    PathFileExists
0x180092c95  test    al, al
0x180092c97  jnz     loc_180092D33
0x180092c9d  mov     esi, 409h
0x180092ca2  cmp     si, di
0x180092ca5  jz      short loc_180092CFF
0x180092ca7  lea     rax, [rsp+470h+var_440]
0x180092cac  mov     r8d, esi
0x180092caf  lea     r9, [rbp+370h+var_230]
0x180092cb6  mov     [rsp+470h+var_450], rax
0x180092cbb  mov     rcx, rbx
0x180092cbe  call    GetResourceDLLPathLanguageSpecific
0x180092cc3  test    al, al
0x180092cc5  jz      short loc_180092D37
0x180092cc7  mov     rcx, rbx; lpFileName
0x180092cca  call    PathFileExists
0x180092ccf  test    al, al
0x180092cd1  jnz     short loc_180092D33
0x180092cd3  lea     rax, [rsp+470h+var_440]
0x180092cd8  mov     r8d, esi
0x180092cdb  lea     r9, [rbp+370h+var_230]
0x180092ce2  mov     [rsp+470h+var_450], rax
0x180092ce7  mov     rcx, rbx
0x180092cea  call    GetResourceDLLPathLanguageSpecific
0x180092cef  test    al, al
0x180092cf1  jz      short loc_180092D37
0x180092cf3  mov     rcx, rbx; lpFileName
0x180092cf6  call    PathFileExists
0x180092cfb  test    al, al
0x180092cfd  jnz     short loc_180092D33
0x180092cff  lea     r8, [rbp+370h+var_230]
0x180092d06  mov     edx, 105h
0x180092d0b  mov     rcx, rbx
0x180092d0e  call    CopyString
0x180092d13  test    al, al
0x180092d15  jz      short loc_180092D24
0x180092d17  lea     r8, [rsp+470h+var_440]
0x180092d1c  mov     rcx, rbx
0x180092d1f  call    PathAppend
0x180092d24  mov     rcx, rbx; lpFileName
0x180092d27  call    PathFileExists
0x180092d2c  test    al, al
0x180092d2e  setnz   al
0x180092d31  jmp     short loc_180092D39
0x180092d33  mov     al, 1
0x180092d35  jmp     short loc_180092D39
0x180092d37  xor     al, al
0x180092d39  mov     rcx, [rbp+370h+var_20]
0x180092d40  xor     rcx, rsp; StackCookie
0x180092d43  call    __security_check_cookie
0x180092d48  mov     rbx, [rsp+470h+arg_10]
0x180092d50  add     rsp, 460h
0x180092d57  pop     rdi
0x180092d58  pop     rsi
0x180092d59  pop     rbp
0x180092d5a  retn
```
