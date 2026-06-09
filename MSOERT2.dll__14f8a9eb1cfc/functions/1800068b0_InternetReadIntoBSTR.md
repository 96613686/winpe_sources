# InternetReadIntoBSTR

- ea: `0x1800068b0`
- end: `0x180006aad`
- name: `InternetReadIntoBSTR`
- size: `509`
- prototype: `__int64 __fastcall(HINTERNET hFile)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001c80`
- `0x1800068b0`
- `0x180011968`
- `0x180014010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180006a0a`
- `KERNEL32!MultiByteToWideChar` at `0x180006a3c`
- `KERNEL32!MultiByteToWideChar` at `0x180006a0a`
- `KERNEL32!MultiByteToWideChar` at `0x180006a3c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006a1a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006a1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006a57`
- `OLEAUT32!__imp_SysFreeString` at `0x180006a57`
- `WININET!HttpQueryInfoA` at `0x18000690a`
- `WININET!HttpQueryInfoA` at `0x18000690a`
- `WININET!InternetReadFile` at `0x180006954`
- `WININET!InternetReadFile` at `0x180006954`

## pseudocode

```c
__int64 __fastcall InternetReadIntoBSTR(HINTERNET hFile, OLECHAR **a2)
{
  int LastError; // ebx
  int v5; // r12d
  unsigned int v6; // esi
  const CHAR *v7; // rdi
  __int64 v8; // rbp
  unsigned int v9; // r14d
  DWORD v10; // ecx
  __int64 v11; // rax
  UINT v12; // eax
  int cchWideChar; // ebx
  WCHAR *lpWideCharStr; // rax
  OLECHAR *v15; // rsi
  DWORD dwNumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  int v18; // [rsp+80h] [rbp+18h] BYREF
  DWORD v19; // [rsp+88h] [rbp+20h] BYREF

  LastError = 0;
  if ( !hFile || !a2 )
    return 2147942487LL;
  *a2 = 0;
  dwNumberOfBytesRead = 0;
  v18 = 0;
  v5 = 1;
  v19 = 4;
  v6 = 0x8000;
  if ( HttpQueryInfoA(hFile, 0x20000005u, &v18, &v19, 0) && v18 )
  {
    v6 = v18 + 1;
    v5 = 0;
  }
  v7 = (const CHAR *)ZeroAllocate(v6);
  if ( v7 )
  {
    LODWORD(v8) = 0;
    v9 = v6;
    while ( 1 )
    {
      dwNumberOfBytesRead = 0;
      if ( !InternetReadFile(hFile, (LPVOID)&v7[(unsigned int)v8], v9 - v8, &dwNumberOfBytesRead) )
        LastError = HrGetLastError();
      if ( LastError < 0 )
        break;
      v10 = dwNumberOfBytesRead;
      LastError = 0;
      v8 = dwNumberOfBytesRead + (unsigned int)v8;
      if ( v5 )
      {
        if ( !dwNumberOfBytesRead )
          goto LABEL_22;
        if ( v9 - (unsigned int)v8 <= 0x2000 )
        {
          if ( v9 > 0x8000 && v6 < 0x100000 )
            v6 *= 2;
          v9 += v6;
          v11 = ((__int64 (__fastcall *)(LPMALLOC, const CHAR *, _QWORD))g_pMalloc->lpVtbl->Realloc)(g_pMalloc, v7, v9);
          if ( !v11 && v9 )
            goto LABEL_29;
          v10 = dwNumberOfBytesRead;
          v7 = (const CHAR *)v11;
        }
      }
      if ( !v10 || !v5 )
      {
LABEL_22:
        if ( !(_DWORD)v8 )
        {
          LastError = -2147013892;
          break;
        }
        v7[v8] = 0;
        v12 = MultiByteToWideChar(0xFDE9u, 0, v7, -1, 0, 0);
        cchWideChar = v12;
        if ( v12 )
        {
          lpWideCharStr = SysAllocStringLen(0, v12);
          v15 = lpWideCharStr;
          if ( !lpWideCharStr )
          {
LABEL_29:
            LastError = -2147024882;
            break;
          }
          if ( MultiByteToWideChar(0xFDE9u, 0, v7, -1, lpWideCharStr, cchWideChar) )
          {
            *a2 = v15;
            LastError = 0;
          }
          else
          {
            LastError = HrGetLastError();
            SysFreeString(v15);
          }
        }
        else
        {
          LastError = HrGetLastError();
        }
        break;
      }
    }
    if ( v7 )
      ((void (__fastcall *)(LPMALLOC, const CHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v7);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800068b0  mov     rax, rsp
0x1800068b3  mov     [rax+10h], rbx
0x1800068b7  push    rbp
0x1800068b8  push    rsi
0x1800068b9  push    rdi
0x1800068ba  push    r12
0x1800068bc  push    r13
0x1800068be  push    r14
0x1800068c0  push    r15
0x1800068c2  sub     rsp, 30h
0x1800068c6  xor     ebx, ebx
0x1800068c8  mov     r15, rdx
0x1800068cb  mov     r13, rcx
0x1800068ce  test    rcx, rcx
0x1800068d1  jz      loc_180006A93
0x1800068d7  test    rdx, rdx
0x1800068da  jz      loc_180006A93
0x1800068e0  mov     [rdx], rbx
0x1800068e3  lea     r9, [rax+20h]; lpdwBufferLength
0x1800068e7  mov     edx, 20000005h; dwInfoLevel
0x1800068ec  mov     [rax+8], ebx
0x1800068ef  lea     r8, [rax+18h]; lpBuffer
0x1800068f3  mov     [rax+18h], ebx
0x1800068f6  lea     r12d, [rbx+1]
0x1800068fa  mov     dword ptr [rax+20h], 4
0x180006901  mov     esi, 8000h
0x180006906  mov     [rax-48h], rbx
0x18000690a  call    cs:__imp_HttpQueryInfoA
0x180006910  test    eax, eax
0x180006912  jz      short loc_180006925
0x180006914  mov     eax, [rsp+68h+arg_10]
0x18000691b  test    eax, eax
0x18000691d  jz      short loc_180006925
0x18000691f  lea     esi, [rax+1]
0x180006922  mov     r12d, ebx
0x180006925  mov     ecx, esi; Size
0x180006927  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x18000692c  mov     rdi, rax
0x18000692f  test    rax, rax
0x180006932  jz      loc_180006A8A
0x180006938  mov     ebp, ebx
0x18000693a  mov     r14d, esi
0x18000693d  mov     r8d, r14d
0x180006940  mov     edx, ebp
0x180006942  sub     r8d, ebp; dwNumberOfBytesToRead
0x180006945  mov     [rsp+68h+dwNumberOfBytesRead], ebx
0x180006949  add     rdx, rdi; lpBuffer
0x18000694c  lea     r9, [rsp+68h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180006951  mov     rcx, r13; hFile
0x180006954  call    cs:__imp_InternetReadFile
0x18000695a  test    eax, eax
0x18000695c  jnz     short loc_180006965
0x18000695e  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180006963  mov     ebx, eax
0x180006965  test    ebx, ebx
0x180006967  js      loc_180006A6D
0x18000696d  mov     ecx, [rsp+68h+dwNumberOfBytesRead]
0x180006971  xor     ebx, ebx
0x180006973  add     ebp, ecx
0x180006975  test    r12d, r12d
0x180006978  jz      short loc_1800069CE
0x18000697a  test    ecx, ecx
0x18000697c  jz      short loc_1800069DB
0x18000697e  mov     eax, r14d
0x180006981  sub     eax, ebp
0x180006983  cmp     eax, 2000h
0x180006988  ja      short loc_1800069CE
0x18000698a  cmp     r14d, 8000h
0x180006991  jbe     short loc_18000699D
0x180006993  cmp     esi, 100000h
0x180006999  jnb     short loc_18000699D
0x18000699b  add     esi, esi
0x18000699d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800069a4  add     r14d, esi
0x1800069a7  mov     r8d, r14d
0x1800069aa  mov     rdx, rdi
0x1800069ad  mov     rax, [rcx]
0x1800069b0  mov     rax, [rax+20h]
0x1800069b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b9  test    rax, rax
0x1800069bc  jnz     short loc_1800069C7
0x1800069be  test    r14d, r14d
0x1800069c1  jnz     loc_180006A5F
0x1800069c7  mov     ecx, [rsp+68h+dwNumberOfBytesRead]
0x1800069cb  mov     rdi, rax
0x1800069ce  test    ecx, ecx
0x1800069d0  jz      short loc_1800069DB
0x1800069d2  test    r12d, r12d
0x1800069d5  jnz     loc_18000693D
0x1800069db  test    ebp, ebp
0x1800069dd  jnz     short loc_1800069E9
0x1800069df  mov     ebx, 80072AFCh
0x1800069e4  jmp     loc_180006A6D
0x1800069e9  mov     [rbp+rdi+0], bl
0x1800069ed  mov     r14d, 0FDE9h
0x1800069f3  or      ebp, 0FFFFFFFFh
0x1800069f6  mov     [rsp+68h+cchWideChar], ebx; cchWideChar
0x1800069fa  mov     r9d, ebp; cbMultiByte
0x1800069fd  mov     [rsp+68h+lpWideCharStr], rbx; lpWideCharStr
0x180006a02  mov     r8, rdi; lpMultiByteStr
0x180006a05  xor     edx, edx; dwFlags
0x180006a07  mov     ecx, r14d; CodePage
0x180006a0a  call    cs:__imp_MultiByteToWideChar
0x180006a10  mov     ebx, eax
0x180006a12  test    eax, eax
0x180006a14  jz      short loc_180006A66
0x180006a16  mov     edx, eax; ui
0x180006a18  xor     ecx, ecx; strIn
0x180006a1a  call    cs:__imp_SysAllocStringLen
0x180006a20  mov     rsi, rax
0x180006a23  test    rax, rax
0x180006a26  jz      short loc_180006A5F
0x180006a28  mov     [rsp+68h+cchWideChar], ebx; cchWideChar
0x180006a2c  mov     r9d, ebp; cbMultiByte
0x180006a2f  mov     r8, rdi; lpMultiByteStr
0x180006a32  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x180006a37  xor     edx, edx; dwFlags
0x180006a39  mov     ecx, r14d; CodePage
0x180006a3c  call    cs:__imp_MultiByteToWideChar
0x180006a42  test    eax, eax
0x180006a44  jz      short loc_180006A4D
0x180006a46  mov     [r15], rsi
0x180006a49  xor     ebx, ebx
0x180006a4b  jmp     short loc_180006A6D
0x180006a4d  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180006a52  mov     rcx, rsi; bstrString
0x180006a55  mov     ebx, eax
0x180006a57  call    cs:__imp_SysFreeString
0x180006a5d  jmp     short loc_180006A6D
0x180006a5f  mov     ebx, 8007000Eh
0x180006a64  jmp     short loc_180006A6D
0x180006a66  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180006a6b  mov     ebx, eax
0x180006a6d  test    rdi, rdi
0x180006a70  jz      short loc_180006A8F
0x180006a72  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180006a79  mov     rdx, rdi
0x180006a7c  mov     rax, [rcx]
0x180006a7f  mov     rax, [rax+28h]
0x180006a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a88  jmp     short loc_180006A8F
0x180006a8a  mov     ebx, 8007000Eh
0x180006a8f  mov     eax, ebx
0x180006a91  jmp     short loc_180006A98
0x180006a93  mov     eax, 80070057h
0x180006a98  mov     rbx, [rsp+68h+arg_8]
0x180006a9d  add     rsp, 30h
0x180006aa1  pop     r15
0x180006aa3  pop     r14
0x180006aa5  pop     r13
0x180006aa7  pop     r12
0x180006aa9  pop     rdi
0x180006aaa  pop     rsi
0x180006aab  pop     rbp
0x180006aac  retn
```
