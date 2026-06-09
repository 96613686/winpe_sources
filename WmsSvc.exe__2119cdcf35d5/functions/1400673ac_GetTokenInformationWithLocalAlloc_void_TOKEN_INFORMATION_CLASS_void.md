# GetTokenInformationWithLocalAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x1400673ac`
- end: `0x1400675d2`
- name: `?GetTokenInformationWithLocalAlloc@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `550`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140066310`
- `0x140073168`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400673ac`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x1400673e0`
- `ADVAPI32!GetTokenInformation` at `0x14006756d`
- `ADVAPI32!GetTokenInformation` at `0x1400673e0`
- `ADVAPI32!GetTokenInformation` at `0x14006756d`
- `KERNEL32!LocalFree` at `0x1400675b3`
- `KERNEL32!LocalFree` at `0x1400675b3`
- `KERNEL32!LocalAlloc` at `0x1400674cd`
- `KERNEL32!LocalAlloc` at `0x1400674cd`
- `KERNEL32!GetLastError` at `0x140067490`
- `KERNEL32!GetLastError` at `0x140067577`
- `KERNEL32!GetLastError` at `0x140067490`
- `KERNEL32!GetLastError` at `0x140067577`
- `KERNEL32!IsDebuggerPresent` at `0x14006742f`
- `KERNEL32!IsDebuggerPresent` at `0x14006751a`
- `KERNEL32!IsDebuggerPresent` at `0x14006742f`
- `KERNEL32!IsDebuggerPresent` at `0x14006751a`

## string_xrefs

- `0x140067417`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x1400674f7`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006740b`: `GetTokenInformationWithLocalAlloc`
- `0x1400674e7`: `GetTokenInformationWithLocalAlloc`
- `0x1400674fe`: `pTokenInformation`

## pseudocode

```c
__int64 __fastcall GetTokenInformationWithLocalAlloc(
        HANDLE TokenHandle,
        TOKEN_INFORMATION_CLASS TokenInformationClass,
        void **a3)
{
  HLOCAL v4; // r14
  signed int v7; // ebx
  const unsigned __int16 *v8; // r12
  unsigned int v9; // r15d
  signed int LastError; // eax
  signed int v11; // eax
  SIZE_T uBytes; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  LODWORD(uBytes) = 0;
  if ( GetTokenInformation(TokenHandle, TokenInformationClass, 0, 0, (PDWORD)&uBytes) )
  {
    v7 = -2147418113;
    v8 = L"!fSuccess";
    v9 = 3421;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v9,
      L"GetTokenInformationWithLocalAlloc",
      L"CBRAEx",
      v8,
      v7);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v9,
        L"GetTokenInformationWithLocalAlloc",
        L"CBRAEx",
        v8,
        v7);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v9,
        L"GetTokenInformationWithLocalAlloc",
        L"CBRAEx",
        v8,
        v7);
    goto LABEL_24;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError != 24 && LastError != 122 )
  {
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = L"(err == 24L) || (err == 122L)";
    v9 = 3424;
    goto LABEL_3;
  }
  v4 = LocalAlloc(0x40u, (unsigned int)uBytes);
  if ( v4 )
  {
    if ( GetTokenInformation(TokenHandle, TokenInformationClass, v4, uBytes, (PDWORD)&uBytes) )
    {
      v7 = 0;
      *a3 = v4;
      v4 = 0;
      goto LABEL_24;
    }
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    v8 = L"fSuccess";
    v9 = 3430;
    if ( v7 >= 0 )
      v7 = -2147467259;
    goto LABEL_3;
  }
  v7 = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
    0xD63u,
    L"GetTokenInformationWithLocalAlloc",
    L"CPR",
    L"pTokenInformation",
    -2147024882);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      3427,
      L"GetTokenInformationWithLocalAlloc",
      L"CPR",
      L"pTokenInformation",
      -2147024882);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      3427,
      L"GetTokenInformationWithLocalAlloc",
      L"CPR",
      L"pTokenInformation",
      -2147024882);
LABEL_24:
  LocalFree(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400673ac  mov     r11, rsp
0x1400673af  mov     [r11+8], rbx
0x1400673b3  mov     [r11+10h], rbp
0x1400673b7  push    rsi
0x1400673b8  push    rdi
0x1400673b9  push    r12
0x1400673bb  push    r14
0x1400673bd  push    r15
0x1400673bf  sub     rsp, 40h
0x1400673c3  mov     r15, r8
0x1400673c6  lea     rax, [r11+20h]
0x1400673ca  xor     r14d, r14d
0x1400673cd  mov     [r11-48h], rax
0x1400673d1  xor     r8d, r8d; TokenInformation
0x1400673d4  mov     [r11+20h], r14d
0x1400673d8  xor     r9d, r9d; TokenInformationLength
0x1400673db  mov     edi, edx
0x1400673dd  mov     rsi, rcx
0x1400673e0  call    cs:__imp_GetTokenInformation
0x1400673e6  test    eax, eax
0x1400673e8  jz      loc_140067490
0x1400673ee  mov     ebx, 8000FFFFh
0x1400673f3  lea     r12, aFsuccess_0; "!fSuccess"
0x1400673fa  mov     r15d, 0D5Dh
0x140067400  lea     rbp, aCbraex; "CBRAEx"
0x140067407  mov     [rsp+68h+var_40], ebx; int
0x14006740b  lea     rsi, aGettokeninform; "GetTokenInformationWithLocalAlloc"
0x140067412  mov     [rsp+68h+ReturnLength], r12; unsigned __int16 *
0x140067417  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006741e  mov     r9, rbp; unsigned __int16 *
0x140067421  mov     r8, rsi; unsigned __int16 *
0x140067424  mov     rcx, rdi; unsigned __int16 *
0x140067427  mov     edx, r15d; unsigned int
0x14006742a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006742f  call    cs:__imp_IsDebuggerPresent
0x140067435  test    eax, eax
0x140067437  jz      short loc_140067468
0x140067439  mov     [rsp+68h+var_30], ebx
0x14006743d  mov     r9d, r15d
0x140067440  mov     [rsp+68h+var_38], r12
0x140067445  mov     qword ptr [rsp+68h+var_40], rbp
0x14006744a  mov     r8, rdi
0x14006744d  mov     [rsp+68h+ReturnLength], rsi
0x140067452  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140067459  mov     ecx, 2; unsigned __int8
0x14006745e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140067463  jmp     loc_1400675B0
0x140067468  mov     dword ptr [rsp+68h+var_38], ebx
0x14006746c  mov     r8d, r15d
0x14006746f  mov     qword ptr [rsp+68h+var_40], r12
0x140067474  mov     [rsp+68h+ReturnLength], rbp
0x140067479  mov     r9, rsi
0x14006747c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140067483  mov     rdx, rdi
0x140067486  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006748b  jmp     loc_1400675B0
0x140067490  call    cs:__imp_GetLastError
0x140067496  mov     ebx, eax
0x140067498  cmp     eax, 18h
0x14006749b  jz      short loc_1400674C1
0x14006749d  cmp     eax, 7Ah ; 'z'
0x1400674a0  jz      short loc_1400674C1
0x1400674a2  test    eax, eax
0x1400674a4  jle     short loc_1400674AF
0x1400674a6  movzx   ebx, ax
0x1400674a9  or      ebx, 80070000h
0x1400674af  lea     r12, aErr24lErr122l; "(err == 24L) || (err == 122L)"
0x1400674b6  mov     r15d, 0D60h
0x1400674bc  jmp     loc_140067400
0x1400674c1  mov     edx, dword ptr [rsp+68h+uBytes]; uBytes
0x1400674c8  mov     ecx, 40h ; '@'; uFlags
0x1400674cd  call    cs:__imp_LocalAlloc
0x1400674d3  mov     r14, rax
0x1400674d6  test    rax, rax
0x1400674d9  jnz     short loc_140067550
0x1400674db  mov     ebx, 8007000Eh
0x1400674e0  lea     r12, aCpr; "CPR"
0x1400674e7  lea     rsi, aGettokeninform; "GetTokenInformationWithLocalAlloc"
0x1400674ee  mov     [rsp+68h+var_40], ebx; int
0x1400674f2  mov     ebp, 0D63h
0x1400674f7  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x1400674fe  lea     r15, aPtokeninformat; "pTokenInformation"
0x140067505  mov     r9, r12; unsigned __int16 *
0x140067508  mov     r8, rsi; unsigned __int16 *
0x14006750b  mov     [rsp+68h+ReturnLength], r15; unsigned __int16 *
0x140067510  mov     edx, ebp; unsigned int
0x140067512  mov     rcx, rdi; unsigned __int16 *
0x140067515  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006751a  call    cs:__imp_IsDebuggerPresent
0x140067520  test    eax, eax
0x140067522  jz      short loc_14006753A
0x140067524  mov     [rsp+68h+var_30], ebx
0x140067528  mov     r9d, ebp
0x14006752b  mov     [rsp+68h+var_38], r15
0x140067530  mov     qword ptr [rsp+68h+var_40], r12
0x140067535  jmp     loc_14006744A
0x14006753a  mov     dword ptr [rsp+68h+var_38], ebx
0x14006753e  mov     r8d, ebp
0x140067541  mov     qword ptr [rsp+68h+var_40], r15
0x140067546  mov     [rsp+68h+ReturnLength], r12
0x14006754b  jmp     loc_140067479
0x140067550  mov     r9d, dword ptr [rsp+68h+uBytes]; TokenInformationLength
0x140067558  lea     rax, [rsp+68h+uBytes]
0x140067560  mov     r8, r14; TokenInformation
0x140067563  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140067568  mov     edx, edi; TokenInformationClass
0x14006756a  mov     rcx, rsi; TokenHandle
0x14006756d  call    cs:__imp_GetTokenInformation
0x140067573  test    eax, eax
0x140067575  jnz     short loc_1400675A8
0x140067577  call    cs:__imp_GetLastError
0x14006757d  mov     ebx, eax
0x14006757f  test    eax, eax
0x140067581  jle     short loc_14006758C
0x140067583  movzx   ebx, ax
0x140067586  or      ebx, 80070000h
0x14006758c  test    ebx, ebx
0x14006758e  lea     r12, aFsuccess; "fSuccess"
0x140067595  mov     eax, 80004005h
0x14006759a  mov     r15d, 0D66h
0x1400675a0  cmovns  ebx, eax
0x1400675a3  jmp     loc_140067400
0x1400675a8  xor     ebx, ebx
0x1400675aa  mov     [r15], r14
0x1400675ad  xor     r14d, r14d
0x1400675b0  mov     rcx, r14; hMem
0x1400675b3  call    cs:__imp_LocalFree
0x1400675b9  mov     rbp, [rsp+68h+arg_8]
0x1400675be  mov     eax, ebx
0x1400675c0  mov     rbx, [rsp+68h+arg_0]
0x1400675c5  add     rsp, 40h
0x1400675c9  pop     r15
0x1400675cb  pop     r14
0x1400675cd  pop     r12
0x1400675cf  pop     rdi
0x1400675d0  pop     rsi
0x1400675d1  retn
```
