# GetTokenInformationWithLocalAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x140007e64`
- end: `0x14000808a`
- name: `?GetTokenInformationWithLocalAlloc@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `550`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140007158`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140007e64`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140007e98`
- `ADVAPI32!GetTokenInformation` at `0x140008025`
- `ADVAPI32!GetTokenInformation` at `0x140007e98`
- `ADVAPI32!GetTokenInformation` at `0x140008025`
- `KERNEL32!LocalAlloc` at `0x140007f85`
- `KERNEL32!LocalAlloc` at `0x140007f85`
- `KERNEL32!LocalFree` at `0x14000806b`
- `KERNEL32!LocalFree` at `0x14000806b`
- `KERNEL32!IsDebuggerPresent` at `0x140007ee7`
- `KERNEL32!IsDebuggerPresent` at `0x140007fd2`
- `KERNEL32!IsDebuggerPresent` at `0x140007ee7`
- `KERNEL32!IsDebuggerPresent` at `0x140007fd2`
- `KERNEL32!GetLastError` at `0x140007f48`
- `KERNEL32!GetLastError` at `0x14000802f`
- `KERNEL32!GetLastError` at `0x140007f48`
- `KERNEL32!GetLastError` at `0x14000802f`

## string_xrefs

- `0x140007ecf`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007faf`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007ec3`: `GetTokenInformationWithLocalAlloc`
- `0x140007f9f`: `GetTokenInformationWithLocalAlloc`
- `0x140007fb6`: `pTokenInformation`

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
0x140007e64  mov     r11, rsp
0x140007e67  mov     [r11+8], rbx
0x140007e6b  mov     [r11+10h], rbp
0x140007e6f  push    rsi
0x140007e70  push    rdi
0x140007e71  push    r12
0x140007e73  push    r14
0x140007e75  push    r15
0x140007e77  sub     rsp, 40h
0x140007e7b  mov     r15, r8
0x140007e7e  lea     rax, [r11+20h]
0x140007e82  xor     r14d, r14d
0x140007e85  mov     [r11-48h], rax
0x140007e89  xor     r8d, r8d; TokenInformation
0x140007e8c  mov     [r11+20h], r14d
0x140007e90  xor     r9d, r9d; TokenInformationLength
0x140007e93  mov     edi, edx
0x140007e95  mov     rsi, rcx
0x140007e98  call    cs:__imp_GetTokenInformation
0x140007e9e  test    eax, eax
0x140007ea0  jz      loc_140007F48
0x140007ea6  mov     ebx, 8000FFFFh
0x140007eab  lea     r12, aFsuccess_0; "!fSuccess"
0x140007eb2  mov     r15d, 0D5Dh
0x140007eb8  lea     rbp, aCbraex; "CBRAEx"
0x140007ebf  mov     [rsp+68h+var_40], ebx; int
0x140007ec3  lea     rsi, aGettokeninform; "GetTokenInformationWithLocalAlloc"
0x140007eca  mov     [rsp+68h+ReturnLength], r12; unsigned __int16 *
0x140007ecf  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007ed6  mov     r9, rbp; unsigned __int16 *
0x140007ed9  mov     r8, rsi; unsigned __int16 *
0x140007edc  mov     rcx, rdi; unsigned __int16 *
0x140007edf  mov     edx, r15d; unsigned int
0x140007ee2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007ee7  call    cs:__imp_IsDebuggerPresent
0x140007eed  test    eax, eax
0x140007eef  jz      short loc_140007F20
0x140007ef1  mov     [rsp+68h+var_30], ebx
0x140007ef5  mov     r9d, r15d
0x140007ef8  mov     [rsp+68h+var_38], r12
0x140007efd  mov     qword ptr [rsp+68h+var_40], rbp
0x140007f02  mov     r8, rdi
0x140007f05  mov     [rsp+68h+ReturnLength], rsi
0x140007f0a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007f11  mov     ecx, 2; unsigned __int8
0x140007f16  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007f1b  jmp     loc_140008068
0x140007f20  mov     dword ptr [rsp+68h+var_38], ebx
0x140007f24  mov     r8d, r15d
0x140007f27  mov     qword ptr [rsp+68h+var_40], r12
0x140007f2c  mov     [rsp+68h+ReturnLength], rbp
0x140007f31  mov     r9, rsi
0x140007f34  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007f3b  mov     rdx, rdi
0x140007f3e  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140007f43  jmp     loc_140008068
0x140007f48  call    cs:__imp_GetLastError
0x140007f4e  mov     ebx, eax
0x140007f50  cmp     eax, 18h
0x140007f53  jz      short loc_140007F79
0x140007f55  cmp     eax, 7Ah ; 'z'
0x140007f58  jz      short loc_140007F79
0x140007f5a  test    eax, eax
0x140007f5c  jle     short loc_140007F67
0x140007f5e  movzx   ebx, ax
0x140007f61  or      ebx, 80070000h
0x140007f67  lea     r12, aErr24lErr122l; "(err == 24L) || (err == 122L)"
0x140007f6e  mov     r15d, 0D60h
0x140007f74  jmp     loc_140007EB8
0x140007f79  mov     edx, dword ptr [rsp+68h+uBytes]; uBytes
0x140007f80  mov     ecx, 40h ; '@'; uFlags
0x140007f85  call    cs:__imp_LocalAlloc
0x140007f8b  mov     r14, rax
0x140007f8e  test    rax, rax
0x140007f91  jnz     short loc_140008008
0x140007f93  mov     ebx, 8007000Eh
0x140007f98  lea     r12, aCpr; "CPR"
0x140007f9f  lea     rsi, aGettokeninform; "GetTokenInformationWithLocalAlloc"
0x140007fa6  mov     [rsp+68h+var_40], ebx; int
0x140007faa  mov     ebp, 0D63h
0x140007faf  lea     rdi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007fb6  lea     r15, aPtokeninformat; "pTokenInformation"
0x140007fbd  mov     r9, r12; unsigned __int16 *
0x140007fc0  mov     r8, rsi; unsigned __int16 *
0x140007fc3  mov     [rsp+68h+ReturnLength], r15; unsigned __int16 *
0x140007fc8  mov     edx, ebp; unsigned int
0x140007fca  mov     rcx, rdi; unsigned __int16 *
0x140007fcd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007fd2  call    cs:__imp_IsDebuggerPresent
0x140007fd8  test    eax, eax
0x140007fda  jz      short loc_140007FF2
0x140007fdc  mov     [rsp+68h+var_30], ebx
0x140007fe0  mov     r9d, ebp
0x140007fe3  mov     [rsp+68h+var_38], r15
0x140007fe8  mov     qword ptr [rsp+68h+var_40], r12
0x140007fed  jmp     loc_140007F02
0x140007ff2  mov     dword ptr [rsp+68h+var_38], ebx
0x140007ff6  mov     r8d, ebp
0x140007ff9  mov     qword ptr [rsp+68h+var_40], r15
0x140007ffe  mov     [rsp+68h+ReturnLength], r12
0x140008003  jmp     loc_140007F31
0x140008008  mov     r9d, dword ptr [rsp+68h+uBytes]; TokenInformationLength
0x140008010  lea     rax, [rsp+68h+uBytes]
0x140008018  mov     r8, r14; TokenInformation
0x14000801b  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140008020  mov     edx, edi; TokenInformationClass
0x140008022  mov     rcx, rsi; TokenHandle
0x140008025  call    cs:__imp_GetTokenInformation
0x14000802b  test    eax, eax
0x14000802d  jnz     short loc_140008060
0x14000802f  call    cs:__imp_GetLastError
0x140008035  mov     ebx, eax
0x140008037  test    eax, eax
0x140008039  jle     short loc_140008044
0x14000803b  movzx   ebx, ax
0x14000803e  or      ebx, 80070000h
0x140008044  test    ebx, ebx
0x140008046  lea     r12, aFsuccess; "fSuccess"
0x14000804d  mov     eax, 80004005h
0x140008052  mov     r15d, 0D66h
0x140008058  cmovns  ebx, eax
0x14000805b  jmp     loc_140007EB8
0x140008060  xor     ebx, ebx
0x140008062  mov     [r15], r14
0x140008065  xor     r14d, r14d
0x140008068  mov     rcx, r14; hMem
0x14000806b  call    cs:__imp_LocalFree
0x140008071  mov     rbp, [rsp+68h+arg_8]
0x140008076  mov     eax, ebx
0x140008078  mov     rbx, [rsp+68h+arg_0]
0x14000807d  add     rsp, 40h
0x140008081  pop     r15
0x140008083  pop     r14
0x140008085  pop     r12
0x140008087  pop     rdi
0x140008088  pop     rsi
0x140008089  retn
```
