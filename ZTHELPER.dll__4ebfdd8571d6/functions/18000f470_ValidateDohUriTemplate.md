# ValidateDohUriTemplate

- ea: `0x18000f470`
- end: `0x18000f669`
- name: `ValidateDohUriTemplate`
- size: `505`
- prototype: `__int64 __fastcall(_DWORD *, const WCHAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006bcc`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x18000eb7c`
- `0x18000f470`
- `0x180015008`
- `0x180015178`
- `0x180015ad8`
- `0x180015fd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f54d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f54d`
- `WINHTTP!WinHttpCrackUrl` at `0x18000f543`
- `WINHTTP!WinHttpCrackUrl` at `0x18000f543`

## pseudocode

```c
__int64 __fastcall ValidateDohUriTemplate(_DWORD *a1, const WCHAR *a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  DWORD LastError; // ebx
  DWORD v8; // eax
  int v9; // ecx
  __int64 v10; // rdx
  bool v11; // zf
  __int64 v12; // rax
  __int64 v13; // r9
  int v15; // [rsp+40h] [rbp-69h] BYREF
  _OWORD v16[2]; // [rsp+48h] [rbp-61h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+70h] [rbp-39h] BYREF

  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  memset(v16, 0, 28);
  v15 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qS(v5, 32, (unsigned int)WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, (_DWORD)a1, (__int64)a2);
  if ( !a1 || !a2 )
  {
    LastError = 87;
    goto LABEL_32;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_DDDDS(v5, v4, v6, a1[2], a1[3], a1[4], a1[5], (__int64)a2);
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwHostNameLength = -1;
  UrlComponents.dwUrlPathLength = -1;
  if ( !WinHttpCrackUrl(a2, 0, 0, &UrlComponents) )
  {
    LastError = GetLastError();
    goto LABEL_32;
  }
  if ( UrlComponents.dwHostNameLength && UrlComponents.dwUrlPathLength )
  {
    v8 = CheckHostnameIpLiteral(&UrlComponents, &v15, v16);
    LastError = v8;
    if ( v8 )
    {
      if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
        return LastError;
      v10 = 35;
      v13 = v8;
      goto LABEL_31;
    }
    if ( !v15 )
      goto LABEL_32;
    v9 = *(unsigned __int16 *)a1;
    if ( (_WORD)v9 == LOWORD(v16[0]) )
    {
      if ( v9 == 2 )
      {
        v11 = DWORD1(v16[0]) == a1[2];
      }
      else
      {
        v12 = *((_QWORD *)&v16[0] + 1) - *((_QWORD *)a1 + 1);
        if ( *((_QWORD *)&v16[0] + 1) == *((_QWORD *)a1 + 1) )
          v12 = *(_QWORD *)&v16[1] - *((_QWORD *)a1 + 2);
        v11 = v12 == 0;
      }
      if ( v11 )
      {
        LastError = 0;
        goto LABEL_32;
      }
    }
    else if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    {
      WPP_SF_dd(1035, 31, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, *(unsigned __int16 *)a1, LOWORD(v16[0]));
    }
    LastError = 87;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      return LastError;
    v10 = 36;
  }
  else
  {
    LastError = 87;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      return LastError;
    v10 = 34;
  }
  v13 = 87;
LABEL_31:
  WPP_SF_d(1035, v10, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, v13);
LABEL_32:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 37, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000f470  mov     [rsp-8+arg_10], rbx
0x18000f475  mov     [rsp-8+arg_18], rdi
0x18000f47a  push    rbp
0x18000f47b  push    r12
0x18000f47d  push    r15
0x18000f47f  lea     rbp, [rsp-47h]
0x18000f484  sub     rsp, 0F0h
0x18000f48b  mov     rax, cs:__security_cookie
0x18000f492  xor     rax, rsp
0x18000f495  mov     [rbp+57h+var_20], rax
0x18000f499  mov     rbx, rdx
0x18000f49c  mov     rdi, rcx
0x18000f49f  xor     edx, edx; Val
0x18000f4a1  lea     rcx, [rbp+57h+UrlComponents]; void *
0x18000f4a5  lea     r8d, [rdx+68h]; Size
0x18000f4a9  call    memset_0
0x18000f4ae  xorps   xmm0, xmm0
0x18000f4b1  xor     eax, eax
0x18000f4b3  movups  [rbp+57h+var_B8], xmm0
0x18000f4b7  mov     [rbp+57h+var_C0], eax
0x18000f4ba  movups  [rbp+57h+var_B8+0Ch], xmm0
0x18000f4be  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f4c5  lea     r15, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids
0x18000f4cc  jz      short loc_18000F4E1
0x18000f4ce  lea     edx, [rax+20h]
0x18000f4d1  mov     [rsp+100h+var_E0], rbx
0x18000f4d6  mov     r9, rdi
0x18000f4d9  mov     r8, r15
0x18000f4dc  call    WPP_SF_qS
0x18000f4e1  mov     r12d, 40Bh
0x18000f4e7  test    rdi, rdi
0x18000f4ea  jnz     short loc_18000F4F6
0x18000f4ec  mov     ebx, 57h ; 'W'
0x18000f4f1  jmp     loc_18000F626
0x18000f4f6  test    rbx, rbx
0x18000f4f9  jz      short loc_18000F4EC
0x18000f4fb  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f502  jz      short loc_18000F527
0x18000f504  mov     eax, [rdi+14h]
0x18000f507  mov     r9d, [rdi+8]
0x18000f50b  mov     [rsp+100h+var_C8], rbx
0x18000f510  mov     [rsp+100h+var_D0], eax
0x18000f514  mov     eax, [rdi+10h]
0x18000f517  mov     [rsp+100h+var_D8], eax
0x18000f51b  mov     eax, [rdi+0Ch]
0x18000f51e  mov     dword ptr [rsp+100h+var_E0], eax
0x18000f522  call    WPP_SF_DDDDS
0x18000f527  or      eax, 0FFFFFFFFh
0x18000f52a  mov     [rbp+57h+UrlComponents.dwStructSize], 68h ; 'h'
0x18000f531  lea     r9, [rbp+57h+UrlComponents]; lpUrlComponents
0x18000f535  mov     [rbp+57h+UrlComponents.dwHostNameLength], eax
0x18000f538  xor     r8d, r8d; dwFlags
0x18000f53b  mov     [rbp+57h+UrlComponents.dwUrlPathLength], eax
0x18000f53e  xor     edx, edx; dwUrlLength
0x18000f540  mov     rcx, rbx; pwszUrl
0x18000f543  call    cs:__imp_WinHttpCrackUrl
0x18000f549  test    eax, eax
0x18000f54b  jnz     short loc_18000F55A
0x18000f54d  call    cs:__imp_GetLastError
0x18000f553  mov     ebx, eax
0x18000f555  jmp     loc_18000F626
0x18000f55a  cmp     [rbp+57h+UrlComponents.dwHostNameLength], 0
0x18000f55e  jbe     loc_18000F607
0x18000f564  cmp     [rbp+57h+UrlComponents.dwUrlPathLength], 0
0x18000f568  jbe     loc_18000F607
0x18000f56e  lea     r8, [rbp+57h+var_B8]
0x18000f572  lea     rdx, [rbp+57h+var_C0]
0x18000f576  lea     rcx, [rbp+57h+UrlComponents]
0x18000f57a  call    CheckHostnameIpLiteral
0x18000f57f  mov     ebx, eax
0x18000f581  test    eax, eax
0x18000f583  jnz     short loc_18000F5F4
0x18000f585  cmp     [rbp+57h+var_C0], eax
0x18000f588  jz      loc_18000F626
0x18000f58e  movzx   ecx, word ptr [rdi]
0x18000f591  cmp     cx, word ptr [rbp+57h+var_B8]
0x18000f595  jz      short loc_18000F5CC
0x18000f597  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f59e  jz      short loc_18000F5B9
0x18000f5a0  movzx   eax, word ptr [rbp+57h+var_B8]
0x18000f5a4  lea     edx, [rbx+1Fh]
0x18000f5a7  mov     r9d, ecx
0x18000f5aa  mov     dword ptr [rsp+100h+var_E0], eax
0x18000f5ae  mov     ecx, r12d
0x18000f5b1  mov     r8, r15
0x18000f5b4  call    WPP_SF_dd
0x18000f5b9  mov     ebx, 57h ; 'W'
0x18000f5be  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f5c5  jz      short loc_18000F642
0x18000f5c7  lea     edx, [rbx-33h]
0x18000f5ca  jmp     short loc_18000F618
0x18000f5cc  cmp     ecx, 2
0x18000f5cf  jnz     short loc_18000F5D9
0x18000f5d1  mov     eax, dword ptr [rbp+57h+var_B8+4]
0x18000f5d4  cmp     eax, [rdi+8]
0x18000f5d7  jmp     short loc_18000F5EE
0x18000f5d9  mov     rax, qword ptr [rbp+57h+var_B8+8]
0x18000f5dd  sub     rax, [rdi+8]
0x18000f5e1  jnz     short loc_18000F5EB
0x18000f5e3  mov     rax, [rbp+57h+var_A8]
0x18000f5e7  sub     rax, [rdi+10h]
0x18000f5eb  test    rax, rax
0x18000f5ee  jnz     short loc_18000F5B9
0x18000f5f0  xor     ebx, ebx
0x18000f5f2  jmp     short loc_18000F626
0x18000f5f4  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f5fb  jz      short loc_18000F642
0x18000f5fd  mov     edx, 23h ; '#'
0x18000f602  mov     r9d, eax
0x18000f605  jmp     short loc_18000F61B
0x18000f607  mov     ebx, 57h ; 'W'
0x18000f60c  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f613  jz      short loc_18000F642
0x18000f615  lea     edx, [rbx-35h]
0x18000f618  mov     r9d, ebx
0x18000f61b  mov     r8, r15
0x18000f61e  mov     ecx, r12d
0x18000f621  call    WPP_SF_d
0x18000f626  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f62d  jz      short loc_18000F642
0x18000f62f  mov     edx, 25h ; '%'
0x18000f634  mov     ecx, r12d
0x18000f637  mov     r9d, ebx
0x18000f63a  mov     r8, r15
0x18000f63d  call    WPP_SF_d
0x18000f642  mov     eax, ebx
0x18000f644  mov     rcx, [rbp+57h+var_20]
0x18000f648  xor     rcx, rsp; StackCookie
0x18000f64b  call    __security_check_cookie
0x18000f650  lea     r11, [rsp+100h+var_10]
0x18000f658  mov     rbx, [r11+30h]
0x18000f65c  mov     rdi, [r11+38h]
0x18000f660  mov     rsp, r11
0x18000f663  pop     r15
0x18000f665  pop     r12
0x18000f667  pop     rbp
0x18000f668  retn
```
