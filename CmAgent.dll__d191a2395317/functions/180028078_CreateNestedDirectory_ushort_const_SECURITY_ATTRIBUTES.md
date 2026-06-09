# CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180028078`
- end: `0x1800282cb`
- name: `?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(const WCHAR *lpPathName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800282d4`

## callees

- `0x180002140`
- `0x1800091a0`
- `0x180028078`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002825c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002825c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002815b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028248`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002815b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180028248`

## pseudocode

```c
__int64 __fastcall CreateNestedDirectory(const WCHAR *lpPathName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  LPCWSTR v3; // rbx
  LPCWSTR v4; // rax
  __int64 v5; // rdx
  WCHAR v6; // cx
  __int64 v7; // rcx
  _WORD *v8; // rax
  signed int LastError; // eax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  WCHAR *v13; // rax
  WCHAR *v14; // rcx
  __int16 v15; // cx
  __int16 *v16; // rbx
  __int16 *v17; // rdi
  bool v18; // zf
  struct _SECURITY_ATTRIBUTES *v19; // rdx
  bool v20; // sf
  unsigned int v21; // ecx
  WCHAR PathName[3]; // [rsp+20h] [rbp-248h] BYREF
  __int16 v24; // [rsp+26h] [rbp-242h] BYREF

  v3 = lpPathName;
  if ( !lpPathName )
    return (unsigned int)-2147024735;
  v4 = lpPathName;
  v5 = 0x7FFFFFFF;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  if ( v5 )
  {
    if ( ((0x7FFFFFFF - v5) & (unsigned __int64)-(__int64)(v5 != 0)) >= 2 && lpPathName[1] == 58 )
    {
      v6 = *lpPathName;
      if ( (unsigned __int16)(*v3 - 97) <= 0x19u || (unsigned __int16)(v6 - 65) <= 0x19u )
        goto LABEL_58;
    }
  }
  v7 = 0x7FFFFFFF;
  v8 = v3;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  if ( v7
    && ((0x7FFFFFFF - v7) & ((unsigned __int128)-(__int128)(unsigned __int64)v7 >> 64)) >= 2
    && *v3 == 92
    && v3[1] == 92 )
  {
LABEL_58:
    if ( CreateDirectoryW(v3, lpSecurityAttributes) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      if ( LastError == -2147024893 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v3[v10] );
        v11 = 260;
        if ( v3[v10 - 1] == 92 )
        {
          v12 = 2147483646;
          v13 = PathName;
          do
          {
            if ( !v12 )
              break;
            if ( !*v3 )
              break;
            *v13++ = *v3++;
            --v12;
            --v11;
          }
          while ( v11 );
          v14 = v13 - 1;
          if ( v11 )
            v14 = v13;
          LastError = v11 == 0 ? 0x8007007A : 0;
          *v14 = 0;
        }
        else
        {
          LastError = StringCchPrintfW(PathName, 0x104u, L"%s\\", v3);
        }
        if ( LastError < 0 )
        {
          LastError = -2147024690;
        }
        else
        {
          v15 = v24;
          if ( v24 )
          {
            v16 = &v24;
            do
            {
              v17 = v16 + 1;
              if ( v15 == 92 )
              {
                v18 = *v17 == 0;
                v19 = lpSecurityAttributes;
                *v16 = 0;
                if ( !v18 )
                  v19 = 0;
                if ( CreateDirectoryW(PathName, v19) )
                {
                  LastError = 0;
                }
                else
                {
                  LastError = GetLastError();
                  v20 = LastError < 0;
                  if ( LastError > 0 )
                  {
                    LastError = (unsigned __int16)LastError | 0x80070000;
                    v20 = LastError < 0;
                  }
                  if ( !v20 )
                    LastError = -2147467259;
                }
                *v16 = 92;
              }
              ++v16;
              v15 = *v17;
            }
            while ( *v17 );
          }
        }
      }
    }
    v21 = 0;
    if ( LastError != -2147024713 )
      return (unsigned int)LastError;
  }
  else
  {
    return (unsigned int)-2147024735;
  }
  return v21;
}

```

## disassembly

```asm
0x180028078  mov     [rsp+arg_10], rbx
0x18002807d  push    rbp
0x18002807e  push    rsi
0x18002807f  push    rdi
0x180028080  push    r12
0x180028082  push    r14
0x180028084  sub     rsp, 240h
0x18002808b  mov     rax, cs:__security_cookie
0x180028092  xor     rax, rsp
0x180028095  mov     [rsp+268h+var_38], rax
0x18002809d  xor     ebp, ebp
0x18002809f  mov     rsi, rdx
0x1800280a2  mov     rbx, rcx
0x1800280a5  test    rcx, rcx
0x1800280a8  jz      loc_18002829C
0x1800280ae  mov     r8d, 7FFFFFFFh
0x1800280b4  mov     rax, rcx
0x1800280b7  mov     edx, r8d
0x1800280ba  cmp     [rax], bp
0x1800280bd  jz      short loc_1800280C9
0x1800280bf  add     rax, 2
0x1800280c3  sub     rdx, 1
0x1800280c7  jnz     short loc_1800280BA
0x1800280c9  mov     rcx, r8
0x1800280cc  mov     rax, rdx
0x1800280cf  sub     rcx, rdx
0x1800280d2  mov     r14d, 5Ch ; '\'
0x1800280d8  neg     rax
0x1800280db  sbb     r9, r9
0x1800280de  and     r9, rcx
0x1800280e1  test    rdx, rdx
0x1800280e4  jz      short loc_180028109
0x1800280e6  cmp     r9, 2
0x1800280ea  jb      short loc_180028109
0x1800280ec  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800280f1  jnz     short loc_180028109
0x1800280f3  movzx   ecx, word ptr [rbx]
0x1800280f6  lea     eax, [rcx-61h]
0x1800280f9  cmp     ax, 19h
0x1800280fd  jbe     short loc_180028155
0x1800280ff  sub     cx, 41h ; 'A'
0x180028103  cmp     cx, 19h
0x180028107  jbe     short loc_180028155
0x180028109  mov     rcx, r8
0x18002810c  mov     rax, rbx
0x18002810f  cmp     [rax], bp
0x180028112  jz      short loc_18002811E
0x180028114  add     rax, 2
0x180028118  sub     rcx, 1
0x18002811c  jnz     short loc_18002810F
0x18002811e  sub     r8, rcx
0x180028121  mov     rax, rcx
0x180028124  neg     rax
0x180028127  sbb     rdx, rdx
0x18002812a  and     rdx, r8
0x18002812d  test    rcx, rcx
0x180028130  jz      loc_18002829C
0x180028136  cmp     rdx, 2
0x18002813a  jb      loc_18002829C
0x180028140  cmp     [rbx], r14w
0x180028144  jnz     loc_18002829C
0x18002814a  cmp     [rbx+2], r14w
0x18002814f  jnz     loc_18002829C
0x180028155  mov     rdx, rsi; lpSecurityAttributes
0x180028158  mov     rcx, rbx; lpPathName
0x18002815b  call    cs:__imp_CreateDirectoryW
0x180028162  nop     dword ptr [rax+rax+00h]
0x180028167  test    eax, eax
0x180028169  jz      short loc_180028172
0x18002816b  mov     eax, ebp
0x18002816d  jmp     loc_180028290
0x180028172  call    cs:__imp_GetLastError
0x180028179  nop     dword ptr [rax+rax+00h]
0x18002817e  test    eax, eax
0x180028180  jle     short loc_18002818A
0x180028182  movzx   eax, ax
0x180028185  or      eax, 80070000h
0x18002818a  test    eax, eax
0x18002818c  mov     r12d, 80004005h
0x180028192  cmovns  eax, r12d
0x180028196  cmp     eax, 80070003h
0x18002819b  jnz     loc_180028290
0x1800281a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800281a5  inc     rax
0x1800281a8  cmp     [rbx+rax*2], bp
0x1800281ac  jnz     short loc_1800281A5
0x1800281ae  mov     edx, 104h; unsigned __int64
0x1800281b3  cmp     [rbx+rax*2-2], r14w
0x1800281b9  jnz     short loc_180028205
0x1800281bb  mov     ecx, 7FFFFFFEh
0x1800281c0  lea     rax, [rsp+268h+PathName]
0x1800281c5  test    rcx, rcx
0x1800281c8  jz      short loc_1800281E9
0x1800281ca  movzx   r8d, word ptr [rbx]
0x1800281ce  test    r8w, r8w
0x1800281d2  jz      short loc_1800281E9
0x1800281d4  mov     [rax], r8w
0x1800281d8  add     rbx, 2
0x1800281dc  add     rax, 2
0x1800281e0  dec     rcx
0x1800281e3  sub     rdx, 1
0x1800281e7  jnz     short loc_1800281C5
0x1800281e9  lea     rcx, [rax-2]
0x1800281ed  test    rdx, rdx
0x1800281f0  cmovnz  rcx, rax
0x1800281f4  neg     rdx
0x1800281f7  sbb     eax, eax
0x1800281f9  not     eax
0x1800281fb  and     eax, 8007007Ah
0x180028200  mov     [rcx], bp
0x180028203  jmp     short loc_180028219
0x180028205  mov     r9, rbx
0x180028208  lea     r8, aS; "%s\\"
0x18002820f  lea     rcx, [rsp+268h+PathName]; unsigned __int16 *
0x180028214  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028219  test    eax, eax
0x18002821b  js      short loc_18002828B
0x18002821d  movzx   ecx, [rsp+268h+var_242]
0x180028222  test    cx, cx
0x180028225  jz      short loc_180028290
0x180028227  lea     rbx, [rsp+268h+var_242]
0x18002822c  lea     rdi, [rbx+2]
0x180028230  cmp     cx, r14w
0x180028234  jnz     short loc_18002827E
0x180028236  cmp     [rdi], bp
0x180028239  lea     rcx, [rsp+268h+PathName]; lpPathName
0x18002823e  mov     rdx, rsi
0x180028241  mov     [rbx], bp
0x180028244  cmovnz  rdx, rbp; lpSecurityAttributes
0x180028248  call    cs:__imp_CreateDirectoryW
0x18002824f  nop     dword ptr [rax+rax+00h]
0x180028254  test    eax, eax
0x180028256  jz      short loc_18002825C
0x180028258  mov     eax, ebp
0x18002825a  jmp     short loc_18002827A
0x18002825c  call    cs:__imp_GetLastError
0x180028263  nop     dword ptr [rax+rax+00h]
0x180028268  test    eax, eax
0x18002826a  jle     short loc_180028276
0x18002826c  movzx   eax, ax
0x18002826f  or      eax, 80070000h
0x180028274  test    eax, eax
0x180028276  cmovns  eax, r12d
0x18002827a  mov     [rbx], r14w
0x18002827e  mov     rbx, rdi
0x180028281  movzx   ecx, word ptr [rbx]
0x180028284  test    cx, cx
0x180028287  jnz     short loc_18002822C
0x180028289  jmp     short loc_180028290
0x18002828b  mov     eax, 800700CEh
0x180028290  cmp     eax, 800700B7h
0x180028295  mov     ecx, ebp
0x180028297  cmovnz  ecx, eax
0x18002829a  jmp     short loc_1800282A1
0x18002829c  mov     ecx, 800700A1h
0x1800282a1  mov     eax, ecx
0x1800282a3  mov     rcx, [rsp+268h+var_38]
0x1800282ab  xor     rcx, rsp; StackCookie
0x1800282ae  call    __security_check_cookie
0x1800282b3  mov     rbx, [rsp+268h+arg_10]
0x1800282bb  add     rsp, 240h
0x1800282c2  pop     r14
0x1800282c4  pop     r12
0x1800282c6  pop     rdi
0x1800282c7  pop     rsi
0x1800282c8  pop     rbp
0x1800282c9  retn
```
