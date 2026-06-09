# SdbpVerifySignature

- ea: `0x18004bde0`
- end: `0x18004c0fe`
- name: `SdbpVerifySignature`
- size: `798`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800212c4`

## callees

- `0x18004bde0`
- `0x180059235`
- `0x180059241`
- `0x180059270`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004be66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004be7b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004be66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004be7b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c0c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c0d6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c0c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004c0d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bea0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004beb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bec6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bed9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bea0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004beb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bec6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004bed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf8d`

## string_xrefs

- `0x18004be6f`: `Crypt32.dll`
- `0x18004be5a`: `WinTrust.dll`

## pseudocode

```c
__int64 __fastcall SdbpVerifySignature(__int64 a1)
{
  HMODULE Library; // r12
  HMODULE v3; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // r13
  FARPROC v6; // rdi
  FARPROC v7; // r14
  FARPROC v8; // rax
  unsigned int (__fastcall *v9)(_QWORD, _QWORD, _QWORD, _QWORD); // r15
  int v10; // ebx
  int v11; // ebx
  __int64 v12; // rax
  signed int LastError; // eax
  __int64 v14; // rax
  __int64 v15; // rbx
  signed int v16; // edi
  __int128 v18; // [rsp+30h] [rbp-A9h] BYREF
  __int128 v19; // [rsp+40h] [rbp-99h] BYREF
  __int64 v20; // [rsp+50h] [rbp-89h]
  __m256i v21; // [rsp+58h] [rbp-81h] BYREF
  _DWORD v22[10]; // [rsp+80h] [rbp-59h] BYREF
  __m256i *v23; // [rsp+A8h] [rbp-31h]
  int v24; // [rsp+B0h] [rbp-29h]
  __int64 v25; // [rsp+B8h] [rbp-21h]
  int v26; // [rsp+C8h] [rbp-11h]
  _DWORD v27[4]; // [rsp+D0h] [rbp-9h] BYREF

  v27[0] = 11191659;
  v27[1] = 298896708;
  v27[2] = -1073692020;
  v27[3] = -292175281;
  memset(&v21, 0, 28);
  v20 = 0;
  v18 = 0;
  v19 = 0;
  memset_0(v22, 0, 0x50u);
  Library = LoadLibraryExW(L"WinTrust.dll", 0, 0x800u);
  v3 = LoadLibraryExW(L"Crypt32.dll", 0, 0x800u);
  v4 = v3;
  if ( !Library || !v3 )
  {
    ProcAddress = 0;
LABEL_30:
    v11 = -2147467259;
    goto LABEL_31;
  }
  ProcAddress = GetProcAddress(Library, "WinVerifyTrust");
  v6 = GetProcAddress(Library, "WTHelperProvDataFromStateData");
  v7 = GetProcAddress(Library, "WTHelperGetProvSignerFromChain");
  v8 = GetProcAddress(v4, "CertVerifyCertificateChainPolicy");
  v9 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v8;
  if ( !ProcAddress || !v6 || !v7 || !v8 )
    goto LABEL_30;
  memset_0(v22, 0, 0x50u);
  v22[0] = 80;
  v22[8] = 1;
  v24 = 1;
  v22[6] = 2;
  v23 = &v21;
  v26 = 4160;
  v21.m256i_i64[0] = 32;
  *(_OWORD *)&v21.m256i_u64[2] = 0;
  v21.m256i_i64[1] = a1;
  v10 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, _DWORD *))ProcAddress)(0, v27, v22);
  if ( v10 )
  {
    v11 = v10 | 0x10000000;
    if ( v11 < 0 )
      goto LABEL_31;
    goto LABEL_30;
  }
  v12 = ((__int64 (__fastcall *)(__int64))v6)(v25);
  if ( v12 )
  {
    v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))v7)(v12, 0, 0, 0);
    v15 = v14;
    if ( v14 )
    {
      if ( !strcmp_0(
              "1.2.840.113549.1.1.5",
              *(const char **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 16) + 8LL) + 24LL) + 24LL)) )
      {
        v11 = -2146889726;
        goto LABEL_31;
      }
      v18 = 0x2000000000010uLL;
      v20 = 0;
      v19 = 0;
      LODWORD(v19) = 24;
      if ( v9(7, *(_QWORD *)(v15 + 56), &v18, &v19) )
      {
        v16 = DWORD1(v19);
        if ( !DWORD1(v19) )
          goto LABEL_28;
        if ( SDWORD1(v19) > 0 )
          v16 = WORD2(v19) | 0x80070000;
        DWORD1(v18) = 0x10000;
        if ( v9(7, *(_QWORD *)(v15 + 56), &v18, &v19) )
        {
          if ( DWORD1(v19) )
          {
            if ( v16 >= 0 )
              v16 = -2147467259;
            v11 = v16;
            goto LABEL_31;
          }
LABEL_28:
          v11 = 0;
          goto LABEL_31;
        }
      }
    }
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    LastError = -2147467259;
  v11 = LastError;
LABEL_31:
  v24 = 2;
  ((void (__fastcall *)(_QWORD, _DWORD *, _DWORD *))ProcAddress)(0, v27, v22);
  if ( Library )
    FreeLibrary(Library);
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004bde0  push    rbp
0x18004bde2  push    rbx
0x18004bde3  push    rsi
0x18004bde4  push    rdi
0x18004bde5  push    r12
0x18004bde7  push    r13
0x18004bde9  push    r14
0x18004bdeb  push    r15
0x18004bded  lea     rbp, [rsp-1Fh]
0x18004bdf2  sub     rsp, 0F8h
0x18004bdf9  mov     rax, cs:__security_cookie
0x18004be00  xor     rax, rsp
0x18004be03  mov     [rbp+57h+var_50], rax
0x18004be07  xorps   xmm0, xmm0
0x18004be0a  mov     [rbp+57h+var_60], 0AAC56Bh
0x18004be11  xor     eax, eax
0x18004be13  mov     [rbp+57h+var_5C], 11D0CD44h
0x18004be1a  mov     rbx, rcx
0x18004be1d  mov     [rbp+57h+var_58], 0C000C28Ch
0x18004be24  xorps   xmm1, xmm1
0x18004be27  mov     [rbp+57h+var_54], 0EE95C24Fh
0x18004be2e  movups  [rsp+130h+var_D8], xmm0
0x18004be33  lea     r8d, [rax+50h]; Size
0x18004be37  mov     [rsp+130h+var_E0], rax
0x18004be3c  xor     edx, edx; Val
0x18004be3e  lea     rcx, [rbp+57h+var_B0]; void *
0x18004be42  movups  [rbp+57h+var_D8+0Ch], xmm0
0x18004be46  movups  [rsp+130h+var_100], xmm0
0x18004be4b  movups  [rsp+130h+var_F0], xmm1
0x18004be50  call    memset_0
0x18004be55  mov     edi, 800h
0x18004be5a  lea     rcx, aWintrustDll; "WinTrust.dll"
0x18004be61  mov     r8d, edi; dwFlags
0x18004be64  xor     edx, edx; hFile
0x18004be66  call    cs:__imp_LoadLibraryExW
0x18004be6c  mov     r8d, edi; dwFlags
0x18004be6f  lea     rcx, aCrypt32Dll; "Crypt32.dll"
0x18004be76  xor     edx, edx; hFile
0x18004be78  mov     r12, rax
0x18004be7b  call    cs:__imp_LoadLibraryExW
0x18004be81  mov     rsi, rax
0x18004be84  test    r12, r12
0x18004be87  jz      loc_18004C09F
0x18004be8d  test    rax, rax
0x18004be90  jz      loc_18004C09F
0x18004be96  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x18004be9d  mov     rcx, r12; hModule
0x18004bea0  call    cs:__imp_GetProcAddress
0x18004bea6  lea     rdx, aWthelperprovda; "WTHelperProvDataFromStateData"
0x18004bead  mov     rcx, r12; hModule
0x18004beb0  mov     r13, rax
0x18004beb3  call    cs:__imp_GetProcAddress
0x18004beb9  lea     rdx, aWthelpergetpro; "WTHelperGetProvSignerFromChain"
0x18004bec0  mov     rcx, r12; hModule
0x18004bec3  mov     rdi, rax
0x18004bec6  call    cs:__imp_GetProcAddress
0x18004becc  lea     rdx, aCertverifycert; "CertVerifyCertificateChainPolicy"
0x18004bed3  mov     rcx, rsi; hModule
0x18004bed6  mov     r14, rax
0x18004bed9  call    cs:__imp_GetProcAddress
0x18004bedf  mov     r15, rax
0x18004bee2  test    r13, r13
0x18004bee5  jz      loc_18004C0A2
0x18004beeb  test    rdi, rdi
0x18004beee  jz      loc_18004C0A2
0x18004bef4  test    r14, r14
0x18004bef7  jz      loc_18004C0A2
0x18004befd  test    rax, rax
0x18004bf00  jz      loc_18004C0A2
0x18004bf06  xor     edx, edx; Val
0x18004bf08  lea     rcx, [rbp+57h+var_B0]; void *
0x18004bf0c  lea     r8d, [rdx+50h]; Size
0x18004bf10  call    memset_0
0x18004bf15  mov     eax, 1
0x18004bf1a  mov     [rbp+57h+var_B0], 50h ; 'P'
0x18004bf21  mov     [rbp+57h+var_90], eax
0x18004bf24  lea     r8, [rbp+57h+var_B0]
0x18004bf28  mov     [rbp+57h+var_80], eax
0x18004bf2b  lea     rdx, [rbp+57h+var_60]
0x18004bf2f  lea     rax, [rsp+130h+var_D8]
0x18004bf34  mov     [rbp+57h+var_98], 2
0x18004bf3b  mov     [rbp+57h+var_88], rax
0x18004bf3f  xorps   xmm0, xmm0
0x18004bf42  mov     rax, r13
0x18004bf45  mov     [rbp+57h+var_68], 1040h
0x18004bf4c  xor     ecx, ecx
0x18004bf4e  mov     qword ptr [rsp+130h+var_D8], 20h ; ' '
0x18004bf57  movdqu  [rbp+57h+var_C8], xmm0
0x18004bf5c  mov     qword ptr [rbp+57h+var_D8+8], rbx
0x18004bf60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf65  mov     ebx, eax
0x18004bf67  test    eax, eax
0x18004bf69  jz      short loc_18004BF7C
0x18004bf6b  or      ebx, 10000000h
0x18004bf71  jl      loc_18004C0A7
0x18004bf77  jmp     loc_18004C0A2
0x18004bf7c  mov     rcx, [rbp+57h+var_78]
0x18004bf80  mov     rax, rdi
0x18004bf83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf88  test    rax, rax
0x18004bf8b  jnz     short loc_18004BFB0
0x18004bf8d  call    cs:__imp_GetLastError
0x18004bf93  test    eax, eax
0x18004bf95  jle     short loc_18004BF9F
0x18004bf97  movzx   eax, ax
0x18004bf9a  or      eax, 80070000h
0x18004bf9f  mov     ebx, 80004005h
0x18004bfa4  test    eax, eax
0x18004bfa6  cmovns  eax, ebx
0x18004bfa9  mov     ebx, eax
0x18004bfab  jmp     loc_18004C0A7
0x18004bfb0  mov     rcx, rax
0x18004bfb3  xor     r9d, r9d
0x18004bfb6  mov     rax, r14
0x18004bfb9  xor     r8d, r8d
0x18004bfbc  xor     edx, edx
0x18004bfbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfc3  mov     rbx, rax
0x18004bfc6  test    rax, rax
0x18004bfc9  jz      short loc_18004BF8D
0x18004bfcb  mov     rax, [rax+10h]
0x18004bfcf  mov     rcx, [rax+8]
0x18004bfd3  mov     rdx, [rcx+18h]
0x18004bfd7  lea     rcx, a12840113549115; "1.2.840.113549.1.1.5"
0x18004bfde  mov     rdx, [rdx+18h]; Str2
0x18004bfe2  call    strcmp_0
0x18004bfe7  test    eax, eax
0x18004bfe9  jnz     short loc_18004BFF5
0x18004bfeb  mov     ebx, 80091002h
0x18004bff0  jmp     loc_18004C0A7
0x18004bff5  xor     eax, eax
0x18004bff7  mov     dword ptr [rsp+130h+var_100], 10h
0x18004bfff  mov     [rsp+130h+var_E0], rax
0x18004c004  lea     r9, [rsp+130h+var_F0]
0x18004c009  xorps   xmm0, xmm0
0x18004c00c  mov     qword ptr [rsp+130h+var_100+8], 0
0x18004c015  movups  [rsp+130h+var_F0], xmm0
0x18004c01a  lea     r14d, [rax+7]
0x18004c01e  mov     dword ptr [rsp+130h+var_F0], 18h
0x18004c026  mov     dword ptr [rsp+130h+var_100+4], 20000h
0x18004c02e  lea     r8, [rsp+130h+var_100]
0x18004c033  mov     rdx, [rbx+38h]
0x18004c037  mov     ecx, r14d
0x18004c03a  mov     rax, r15
0x18004c03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c042  test    eax, eax
0x18004c044  jz      loc_18004BF8D
0x18004c04a  mov     edi, dword ptr [rsp+130h+var_F0+4]
0x18004c04e  test    edi, edi
0x18004c050  jz      short loc_18004C09B
0x18004c052  jle     short loc_18004C05D
0x18004c054  movzx   edi, di
0x18004c057  or      edi, 80070000h
0x18004c05d  mov     dword ptr [rsp+130h+var_100+4], 10000h
0x18004c065  lea     r9, [rsp+130h+var_F0]
0x18004c06a  mov     rdx, [rbx+38h]
0x18004c06e  lea     r8, [rsp+130h+var_100]
0x18004c073  mov     rcx, r14
0x18004c076  mov     rax, r15
0x18004c079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c07e  test    eax, eax
0x18004c080  jz      loc_18004BF8D
0x18004c086  cmp     dword ptr [rsp+130h+var_F0+4], 0
0x18004c08b  jz      short loc_18004C09B
0x18004c08d  mov     ebx, 80004005h
0x18004c092  test    edi, edi
0x18004c094  cmovns  edi, ebx
0x18004c097  mov     ebx, edi
0x18004c099  jmp     short loc_18004C0A7
0x18004c09b  xor     ebx, ebx
0x18004c09d  jmp     short loc_18004C0A7
0x18004c09f  xor     r13d, r13d
0x18004c0a2  mov     ebx, 80004005h
0x18004c0a7  lea     r8, [rbp+57h+var_B0]
0x18004c0ab  mov     [rbp+57h+var_80], 2
0x18004c0b2  lea     rdx, [rbp+57h+var_60]
0x18004c0b6  xor     ecx, ecx
0x18004c0b8  mov     rax, r13
0x18004c0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0c0  test    r12, r12
0x18004c0c3  jz      short loc_18004C0CE
0x18004c0c5  mov     rcx, r12; hLibModule
0x18004c0c8  call    cs:__imp_FreeLibrary
0x18004c0ce  test    rsi, rsi
0x18004c0d1  jz      short loc_18004C0DC
0x18004c0d3  mov     rcx, rsi; hLibModule
0x18004c0d6  call    cs:__imp_FreeLibrary
0x18004c0dc  mov     eax, ebx
0x18004c0de  mov     rcx, [rbp+57h+var_50]
0x18004c0e2  xor     rcx, rsp; StackCookie
0x18004c0e5  call    __security_check_cookie
0x18004c0ea  add     rsp, 0F8h
0x18004c0f1  pop     r15
0x18004c0f3  pop     r14
0x18004c0f5  pop     r13
0x18004c0f7  pop     r12
0x18004c0f9  pop     rdi
0x18004c0fa  pop     rsi
0x18004c0fb  pop     rbx
0x18004c0fc  pop     rbp
0x18004c0fd  retn
```
