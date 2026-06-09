# BfspRestoreHyperVSetting

- ea: `0x14000efc8`
- end: `0x14000f29a`
- name: `BfspRestoreHyperVSetting`
- size: `722`
- prototype: `__int64 __fastcall(__int64, wchar_t *, _QWORD *, __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004080`

## callees

- `0x14000efc8`
- `0x140013b48`
- `0x140013ee8`
- `0x140018b54`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x14000f179`
- `msvcrt!wcscpy_s` at `0x14000f179`
- `msvcrt!wcsrchr` at `0x14000f188`
- `msvcrt!wcsrchr` at `0x14000f188`
- `KERNEL32!GetLastError` at `0x14000f04f`
- `KERNEL32!GetLastError` at `0x14000f04f`
- `KERNEL32!GetProcAddress` at `0x14000f07b`
- `KERNEL32!GetProcAddress` at `0x14000f09a`
- `KERNEL32!GetProcAddress` at `0x14000f0b2`
- `KERNEL32!GetProcAddress` at `0x14000f0cb`
- `KERNEL32!GetProcAddress` at `0x14000f0e4`
- `KERNEL32!GetProcAddress` at `0x14000f0fd`
- `KERNEL32!GetProcAddress` at `0x14000f07b`
- `KERNEL32!GetProcAddress` at `0x14000f09a`
- `KERNEL32!GetProcAddress` at `0x14000f0b2`
- `KERNEL32!GetProcAddress` at `0x14000f0cb`
- `KERNEL32!GetProcAddress` at `0x14000f0e4`
- `KERNEL32!GetProcAddress` at `0x14000f0fd`
- `KERNEL32!FreeLibrary` at `0x14000f113`
- `KERNEL32!FreeLibrary` at `0x14000f25b`
- `KERNEL32!FreeLibrary` at `0x14000f113`
- `KERNEL32!FreeLibrary` at `0x14000f25b`
- `KERNEL32!LoadLibraryExW` at `0x14000f041`
- `KERNEL32!LoadLibraryExW` at `0x14000f041`

## string_xrefs

- `0x14000f090`: `DismOpenSession`
- `0x14000f016`: `DISMAPI.DLL`
- `0x14000f0c1`: `DismDelete`

## pseudocode

```c
__int64 __fastcall BfspRestoreHyperVSetting(__int64 a1, wchar_t *a2, _QWORD *a3, __int16 a4)
{
  int LastError; // ebx
  void *v5; // rsi
  void (*v7)(void); // r12
  HMODULE Library; // rax
  HMODULE v9; // rdi
  FARPROC v10; // r14
  FARPROC ProcAddress; // r15
  bool v12; // sf
  int v13; // eax
  int v14; // ebx
  wchar_t *v15; // rcx
  int v16; // eax
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  void *v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *Source; // [rsp+50h] [rbp-B0h]
  _QWORD *v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  __int128 v25; // [rsp+68h] [rbp-98h]
  __int128 v26; // [rsp+78h] [rbp-88h]
  __int128 v27; // [rsp+88h] [rbp-78h]
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF

  LastError = 0;
  v23 = a3;
  Source = a2;
  v24 = a1;
  v21 = 0;
  v18 = 0;
  v25 = 0;
  v20 = 0;
  v5 = 0;
  v26 = 0;
  v19 = 0;
  v27 = 0;
  v7 = 0;
  Library = LoadLibraryExW(L"DISMAPI.DLL", 0, 0);
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DismInitialize");
    if ( ProcAddress )
    {
      v10 = GetProcAddress(v9, "DismOpenSession");
      if ( v10 )
      {
        *((_QWORD *)&v26 + 1) = GetProcAddress(v9, "DismGetFeatureInfo");
        if ( *((_QWORD *)&v26 + 1) )
        {
          *(_QWORD *)&v27 = GetProcAddress(v9, "DismDelete");
          if ( (_QWORD)v27 )
          {
            *((_QWORD *)&v27 + 1) = GetProcAddress(v9, "DismCloseSession");
            if ( *((_QWORD *)&v27 + 1) )
            {
              v7 = (void (*)(void))GetProcAddress(v9, "DismShutdown");
              if ( v7 )
                goto LABEL_14;
            }
          }
        }
      }
    }
    else
    {
      v10 = (FARPROC)v26;
    }
    LastError = 127;
    FreeLibrary(v9);
    v9 = 0;
    goto LABEL_12;
  }
  v10 = (FARPROC)v26;
  LastError = GetLastError();
  ProcAddress = (FARPROC)*((_QWORD *)&v25 + 1);
  if ( LastError )
  {
LABEL_12:
    v12 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_15;
    goto LABEL_13;
  }
  LOWORD(LastError) = 126;
LABEL_13:
  LastError = (unsigned __int16)LastError | 0xC0070000;
LABEL_14:
  v12 = LastError < 0;
LABEL_15:
  if ( !v12 )
  {
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(0, 0, 0);
    if ( v13 < 0
      || ((a4 & 0x8000) == 0
        ? (wcscpy_s(Destination, 0x104u, Source), *wcsrchr(Destination, 0x5Cu) = 0, v15 = Destination)
        : (v15 = L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}"),
          (v13 = ((__int64 (__fastcall *)(wchar_t *, _QWORD, _QWORD, unsigned int *))v10)(v15, 0, 0, &v18), v13 < 0)
       || (v13 = (*((__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, _QWORD, __int64 *))&v26 + 1))(
                   v18,
                   L"Microsoft-Hyper-V-Hypervisor",
                   0,
                   0,
                   &v20),
           v13 < 0)) )
    {
      v14 = (unsigned __int16)v13;
      if ( !(_WORD)v13 )
        v14 = 31;
      LastError = v14 | 0xC0070000;
    }
    else if ( *(_DWORD *)(v20 + 8) == 4 )
    {
      v16 = BcdOpenObject(v24, v23, &v19);
      v5 = v19;
      LastError = v16;
      if ( v16 >= 0 )
      {
        v21 = 1;
        LastError = BcdSetElementDataWithFlags((__int64)v19, 620757232, 0, (__int64)&v21, 8u);
      }
    }
    if ( v20 )
      ((void (*)(void))v27)();
    (*((void (__fastcall **)(_QWORD))&v27 + 1))(v18);
    v7();
    if ( v9 )
      FreeLibrary(v9);
    if ( v5 )
      BcdCloseObject(v5);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14000efc8  mov     [rsp-8+arg_18], rbx
0x14000efcd  push    rbp
0x14000efce  push    rsi
0x14000efcf  push    rdi
0x14000efd0  push    r12
0x14000efd2  push    r13
0x14000efd4  push    r14
0x14000efd6  push    r15
0x14000efd8  lea     rbp, [rsp-1C0h]
0x14000efe0  sub     rsp, 2C0h
0x14000efe7  mov     rax, cs:__security_cookie
0x14000efee  xor     rax, rsp
0x14000eff1  mov     [rbp+1F0h+var_40], rax
0x14000eff8  xor     ebx, ebx
0x14000effa  mov     [rsp+2F0h+var_298], r8
0x14000efff  xorps   xmm0, xmm0
0x14000f002  mov     [rsp+2F0h+Source], rdx
0x14000f007  mov     [rsp+2F0h+var_290], rcx
0x14000f00c  xor     r8d, r8d; dwFlags
0x14000f00f  xor     edx, edx; hFile
0x14000f011  mov     [rsp+2F0h+var_2A8], rbx
0x14000f016  lea     rcx, aDismapiDll; "DISMAPI.DLL"
0x14000f01d  mov     [rsp+2F0h+var_2C0], ebx
0x14000f021  movups  [rsp+2F0h+var_288], xmm0
0x14000f026  mov     [rsp+2F0h+var_2B0], rbx
0x14000f02b  mov     esi, ebx
0x14000f02d  movups  [rsp+2F0h+var_278], xmm0
0x14000f032  mov     [rsp+2F0h+var_2B8], rbx
0x14000f037  mov     r13d, r9d
0x14000f03a  movups  [rbp+1F0h+var_268], xmm0
0x14000f03e  xor     r12d, r12d
0x14000f041  call    cs:__imp_LoadLibraryExW
0x14000f047  mov     rdi, rax
0x14000f04a  test    rax, rax
0x14000f04d  jnz     short loc_14000F071
0x14000f04f  call    cs:__imp_GetLastError
0x14000f055  mov     r14, qword ptr [rsp+2F0h+var_278]
0x14000f05a  mov     ebx, eax
0x14000f05c  mov     r15, qword ptr [rsp+2F0h+var_288+8]
0x14000f061  test    eax, eax
0x14000f063  jnz     loc_14000F11B
0x14000f069  lea     ebx, [rsi+7Eh]
0x14000f06c  jmp     loc_14000F11F
0x14000f071  lea     rdx, aDisminitialize; "DismInitialize"
0x14000f078  mov     rcx, rdi; hModule
0x14000f07b  call    cs:__imp_GetProcAddress
0x14000f081  mov     r15, rax
0x14000f084  test    rax, rax
0x14000f087  jnz     short loc_14000F090
0x14000f089  mov     r14, qword ptr [rsp+2F0h+var_278]
0x14000f08e  jmp     short loc_14000F10B
0x14000f090  lea     rdx, aDismopensessio; "DismOpenSession"
0x14000f097  mov     rcx, rdi; hModule
0x14000f09a  call    cs:__imp_GetProcAddress
0x14000f0a0  mov     r14, rax
0x14000f0a3  test    rax, rax
0x14000f0a6  jz      short loc_14000F10B
0x14000f0a8  lea     rdx, aDismgetfeature; "DismGetFeatureInfo"
0x14000f0af  mov     rcx, rdi; hModule
0x14000f0b2  call    cs:__imp_GetProcAddress
0x14000f0b8  mov     qword ptr [rbp+1F0h+var_278+8], rax
0x14000f0bc  test    rax, rax
0x14000f0bf  jz      short loc_14000F10B
0x14000f0c1  lea     rdx, aDismdelete; "DismDelete"
0x14000f0c8  mov     rcx, rdi; hModule
0x14000f0cb  call    cs:__imp_GetProcAddress
0x14000f0d1  mov     qword ptr [rbp+1F0h+var_268], rax
0x14000f0d5  test    rax, rax
0x14000f0d8  jz      short loc_14000F10B
0x14000f0da  lea     rdx, aDismclosesessi; "DismCloseSession"
0x14000f0e1  mov     rcx, rdi; hModule
0x14000f0e4  call    cs:__imp_GetProcAddress
0x14000f0ea  mov     qword ptr [rbp+1F0h+var_268+8], rax
0x14000f0ee  test    rax, rax
0x14000f0f1  jz      short loc_14000F10B
0x14000f0f3  lea     rdx, aDismshutdown; "DismShutdown"
0x14000f0fa  mov     rcx, rdi; hModule
0x14000f0fd  call    cs:__imp_GetProcAddress
0x14000f103  mov     r12, rax
0x14000f106  test    rax, rax
0x14000f109  jnz     short loc_14000F128
0x14000f10b  mov     ebx, 7Fh
0x14000f110  mov     rcx, rdi; hLibModule
0x14000f113  call    cs:__imp_FreeLibrary
0x14000f119  xor     edi, edi
0x14000f11b  test    ebx, ebx
0x14000f11d  jle     short loc_14000F12A
0x14000f11f  movzx   ebx, bx
0x14000f122  or      ebx, 0C0070000h
0x14000f128  test    ebx, ebx
0x14000f12a  js      loc_14000F26E
0x14000f130  xor     r8d, r8d
0x14000f133  xor     edx, edx
0x14000f135  xor     ecx, ecx
0x14000f137  mov     rax, r15
0x14000f13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f13f  test    eax, eax
0x14000f141  jns     short loc_14000F15B
0x14000f143  movzx   ebx, ax
0x14000f146  mov     eax, 1Fh
0x14000f14b  test    ebx, ebx
0x14000f14d  cmovz   ebx, eax
0x14000f150  or      ebx, 0C0070000h
0x14000f156  jmp     loc_14000F22B
0x14000f15b  bt      r13d, 0Fh
0x14000f160  jnb     short loc_14000F16B
0x14000f162  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x14000f169  jmp     short loc_14000F197
0x14000f16b  mov     r8, [rsp+2F0h+Source]; Source
0x14000f170  lea     rcx, [rbp+1F0h+Destination]; Destination
0x14000f174  mov     edx, 104h; SizeInWords
0x14000f179  call    cs:__imp_wcscpy_s
0x14000f17f  mov     edx, 5Ch ; '\'; Ch
0x14000f184  lea     rcx, [rbp+1F0h+Destination]; Str
0x14000f188  call    cs:__imp_wcsrchr
0x14000f18e  xor     ecx, ecx
0x14000f190  mov     [rax], cx
0x14000f193  lea     rcx, [rbp+1F0h+Destination]
0x14000f197  lea     r9, [rsp+2F0h+var_2C0]
0x14000f19c  xor     r8d, r8d
0x14000f19f  xor     edx, edx
0x14000f1a1  mov     rax, r14
0x14000f1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1a9  test    eax, eax
0x14000f1ab  js      short loc_14000F143
0x14000f1ad  mov     ecx, [rsp+2F0h+var_2C0]
0x14000f1b1  lea     rax, [rsp+2F0h+var_2B0]
0x14000f1b6  mov     [rsp+2F0h+var_2D0], rax
0x14000f1bb  lea     rdx, aMicrosoftHyper; "Microsoft-Hyper-V-Hypervisor"
0x14000f1c2  mov     rax, qword ptr [rbp+1F0h+var_278+8]
0x14000f1c6  xor     r9d, r9d
0x14000f1c9  xor     r8d, r8d
0x14000f1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1d1  test    eax, eax
0x14000f1d3  js      loc_14000F143
0x14000f1d9  mov     rax, [rsp+2F0h+var_2B0]
0x14000f1de  cmp     dword ptr [rax+8], 4
0x14000f1e2  jnz     short loc_14000F22B
0x14000f1e4  mov     rdx, [rsp+2F0h+var_298]
0x14000f1e9  lea     r8, [rsp+2F0h+var_2B8]
0x14000f1ee  mov     rcx, [rsp+2F0h+var_290]
0x14000f1f3  call    BcdOpenObject
0x14000f1f8  mov     rsi, [rsp+2F0h+var_2B8]
0x14000f1fd  mov     ebx, eax
0x14000f1ff  test    eax, eax
0x14000f201  js      short loc_14000F22B
0x14000f203  lea     r9, [rsp+2F0h+var_2A8]
0x14000f208  mov     [rsp+2F0h+var_2A8], 1
0x14000f211  xor     r8d, r8d
0x14000f214  mov     dword ptr [rsp+2F0h+var_2D0], 8
0x14000f21c  mov     edx, 250000F0h
0x14000f221  mov     rcx, rsi
0x14000f224  call    BcdSetElementDataWithFlags
0x14000f229  mov     ebx, eax
0x14000f22b  mov     rcx, [rsp+2F0h+var_2B0]
0x14000f230  test    rcx, rcx
0x14000f233  jz      short loc_14000F23E
0x14000f235  mov     rax, qword ptr [rbp+1F0h+var_268]
0x14000f239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f23e  mov     ecx, [rsp+2F0h+var_2C0]
0x14000f242  mov     rax, qword ptr [rbp+1F0h+var_268+8]
0x14000f246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f24b  mov     rax, r12
0x14000f24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f253  test    rdi, rdi
0x14000f256  jz      short loc_14000F261
0x14000f258  mov     rcx, rdi; hLibModule
0x14000f25b  call    cs:__imp_FreeLibrary
0x14000f261  test    rsi, rsi
0x14000f264  jz      short loc_14000F26E
0x14000f266  mov     rcx, rsi; Handle
0x14000f269  call    BcdCloseObject
0x14000f26e  mov     eax, ebx
0x14000f270  mov     rcx, [rbp+1F0h+var_40]
0x14000f277  xor     rcx, rsp; StackCookie
0x14000f27a  call    __security_check_cookie
0x14000f27f  mov     rbx, [rsp+2F0h+arg_18]
0x14000f287  add     rsp, 2C0h
0x14000f28e  pop     r15
0x14000f290  pop     r14
0x14000f292  pop     r13
0x14000f294  pop     r12
0x14000f296  pop     rdi
0x14000f297  pop     rsi
0x14000f298  pop     rbp
0x14000f299  retn
```
