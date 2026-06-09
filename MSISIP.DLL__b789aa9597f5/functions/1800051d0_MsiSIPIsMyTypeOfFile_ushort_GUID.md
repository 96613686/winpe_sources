# MsiSIPIsMyTypeOfFile(ushort *,_GUID *)

- ea: `0x1800051d0`
- end: `0x18000559d`
- name: `?MsiSIPIsMyTypeOfFile@@YAHPEAGPEAU_GUID@@@Z`
- size: `973`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x1800051d0`
- `0x18000d2b6`
- `0x18000d2ce`
- `0x18000d300`
- `0x18000e010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000521a`
- `msvcrt!wcsrchr` at `0x18000521a`
- `msvcrt!_wcsicmp` at `0x180005232`
- `msvcrt!_wcsicmp` at `0x180005246`
- `msvcrt!_wcsicmp` at `0x1800054ca`
- `msvcrt!_wcsicmp` at `0x1800054e2`
- `msvcrt!_wcsicmp` at `0x1800054fa`
- `msvcrt!_wcsicmp` at `0x180005512`
- `msvcrt!_wcsicmp` at `0x18000552a`
- `msvcrt!_wcsicmp` at `0x180005542`
- `msvcrt!_wcsicmp` at `0x18000555a`
- `msvcrt!_wcsicmp` at `0x180005572`
- `msvcrt!_wcsicmp` at `0x18000558a`
- `msvcrt!_wcsicmp` at `0x180005232`
- `msvcrt!_wcsicmp` at `0x180005246`
- `msvcrt!_wcsicmp` at `0x1800054ca`
- `msvcrt!_wcsicmp` at `0x1800054e2`
- `msvcrt!_wcsicmp` at `0x1800054fa`
- `msvcrt!_wcsicmp` at `0x180005512`
- `msvcrt!_wcsicmp` at `0x18000552a`
- `msvcrt!_wcsicmp` at `0x180005542`
- `msvcrt!_wcsicmp` at `0x18000555a`
- `msvcrt!_wcsicmp` at `0x180005572`
- `msvcrt!_wcsicmp` at `0x18000558a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800052a1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800052d9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005395`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800054a2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800052a1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800052d9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180005395`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800054a2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800053a8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800053ee`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800054b5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800053a8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800053ee`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800054b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053f6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180005289`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180005289`

## string_xrefs

- `0x180005282`: `ole32.dll`
- `0x1800052cf`: `StgOpenStorage`

## pseudocode

```c
__int64 __fastcall MsiSIPIsMyTypeOfFile(unsigned __int16 *a1, struct _GUID *a2)
{
  wchar_t *v4; // rax
  const wchar_t *v5; // rbx
  HMODULE LibraryW; // rax
  HMODULE v8; // rsi
  FARPROC ProcAddress; // rax
  int v10; // edi
  bool v11; // di
  FARPROC v12; // rax
  int (__fastcall *v13)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rbx
  unsigned int v14; // r15d
  void (*v15)(void); // rax
  DWORD LastError; // ebx
  __int64 v17; // rbx
  void (*v18)(void); // rax
  _QWORD v19[2]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v20[56]; // [rsp+50h] [rbp-88h] BYREF
  int v21; // [rsp+88h] [rbp-50h]
  _BYTE Buf1[20]; // [rsp+8Ch] [rbp-4Ch] BYREF

  v19[1] = -2;
  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  v4 = wcsrchr(a1, 0x2Eu);
  v5 = v4;
  if ( v4 )
  {
    if ( !_wcsicmp(L".jar", v4)
      || !_wcsicmp(L".hta", v5)
      || !_wcsicmp(L".cmd", v5)
      || !_wcsicmp(L".bat", v5)
      || !_wcsicmp(L".ps1", v5)
      || !_wcsicmp(L".wsh", v5)
      || !_wcsicmp(L".wsf", v5)
      || !_wcsicmp(L".js", v5)
      || !_wcsicmp(L".vbs", v5)
      || !_wcsicmp(L".vbe", v5)
      || !_wcsicmp(L".jse", v5) )
    {
      return 0;
    }
  }
  LibraryW = LoadLibraryW(L"ole32.dll");
  v8 = LibraryW;
  if ( !LibraryW )
    return 0;
  ProcAddress = GetProcAddress(LibraryW, "CoInitialize");
  if ( !ProcAddress )
  {
LABEL_25:
    LastError = GetLastError();
    FreeLibrary(v8);
    SetLastError(LastError);
    return 0;
  }
  v10 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147417850 )
  {
    SetLastError((unsigned __int16)v10);
    goto LABEL_25;
  }
  v11 = v10 >= 0;
  v12 = GetProcAddress(v8, "StgOpenStorage");
  v13 = (int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))v12;
  if ( !v12 )
  {
    if ( v11 )
    {
      v18 = (void (*)(void))GetProcAddress(v8, "CoUninitialize");
      if ( v18 )
        v18();
    }
    FreeLibrary(v8);
    return 0;
  }
  v14 = 0;
  v19[0] = 0;
  if ( ((int (__fastcall *)(unsigned __int16 *, _QWORD, __int64, _QWORD, _DWORD, _QWORD *))v12)(a1, 0, 32, 0, 0, v19) < 0 )
  {
    if ( v19[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
    v19[0] = 0;
    if ( v13(a1, 0, 65600, 0, 0, v19) < 0 )
      goto LABEL_15;
  }
  v17 = v19[0];
  if ( v19[0] )
  {
    memset_0(v20, 0, 0x50u);
    if ( (*(int (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v17 + 136LL))(v17, v20, 1) >= 0
      && (unsigned int)(v21 - 790656) <= 6
      && !memcmp_0(Buf1, &dword_18000F9AC, 0xCu) )
    {
      *a2 = gMSI;
      v14 = 1;
    }
LABEL_15:
    if ( v19[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
  }
  v19[0] = 0;
  if ( v11 )
  {
    v15 = (void (*)(void))GetProcAddress(v8, "CoUninitialize");
    if ( v15 )
      v15();
  }
  FreeLibrary(v8);
  if ( v19[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
  return v14;
}

```

## disassembly

```asm
0x1800051d0  mov     rax, rsp
0x1800051d3  push    rsi
0x1800051d4  push    rdi
0x1800051d5  push    r12
0x1800051d7  push    r14
0x1800051d9  push    r15
0x1800051db  sub     rsp, 0B0h
0x1800051e2  mov     [rsp+0D8h+var_90], 0FFFFFFFFFFFFFFFEh
0x1800051eb  mov     [rax+18h], rbx
0x1800051ef  mov     [rax+20h], rbp
0x1800051f3  mov     rax, cs:__security_cookie
0x1800051fa  xor     rax, rsp
0x1800051fd  mov     [rsp+0D8h+var_38], rax
0x180005205  mov     r14, rdx
0x180005208  mov     rbp, rcx
0x18000520b  test    rcx, rcx
0x18000520e  jz      short loc_180005254
0x180005210  test    rdx, rdx
0x180005213  jz      short loc_180005254
0x180005215  mov     edx, 2Eh ; '.'; Ch
0x18000521a  call    cs:__imp_wcsrchr
0x180005220  mov     rbx, rax
0x180005223  test    rax, rax
0x180005226  jz      short loc_180005282
0x180005228  mov     rdx, rax; String2
0x18000522b  lea     rcx, aJar; ".jar"
0x180005232  call    cs:__imp__wcsicmp
0x180005238  test    eax, eax
0x18000523a  jz      short loc_180005254
0x18000523c  mov     rdx, rbx; String2
0x18000523f  lea     rcx, aHta; ".hta"
0x180005246  call    cs:__imp__wcsicmp
0x18000524c  test    eax, eax
0x18000524e  jnz     loc_1800054C0
0x180005254  xor     eax, eax
0x180005256  mov     rcx, [rsp+0D8h+var_38]
0x18000525e  xor     rcx, rsp; StackCookie
0x180005261  call    __security_check_cookie
0x180005266  lea     r11, [rsp+0D8h+var_28]
0x18000526e  mov     rbx, [r11+40h]
0x180005272  mov     rbp, [r11+48h]
0x180005276  mov     rsp, r11
0x180005279  pop     r15
0x18000527b  pop     r14
0x18000527d  pop     r12
0x18000527f  pop     rdi
0x180005280  pop     rsi
0x180005281  retn
0x180005282  lea     rcx, LibFileName; "ole32.dll"
0x180005289  call    cs:__imp_LoadLibraryW
0x18000528f  mov     rsi, rax
0x180005292  test    rax, rax
0x180005295  jz      short loc_180005254
0x180005297  lea     rdx, aCoinitialize; "CoInitialize"
0x18000529e  mov     rcx, rax; hModule
0x1800052a1  call    cs:__imp_GetProcAddress
0x1800052a7  test    rax, rax
0x1800052aa  jz      loc_1800053E3
0x1800052b0  xor     ecx, ecx
0x1800052b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052b7  mov     edi, eax
0x1800052b9  mov     ecx, 80000000h
0x1800052be  add     eax, ecx
0x1800052c0  test    ecx, eax
0x1800052c2  jz      loc_1800053CE
0x1800052c8  shr     edi, 1Fh
0x1800052cb  xor     dil, 1
0x1800052cf  lea     rdx, aStgopenstorage; "StgOpenStorage"
0x1800052d6  mov     rcx, rsi; hModule
0x1800052d9  call    cs:__imp_GetProcAddress
0x1800052df  mov     rbx, rax
0x1800052e2  test    rax, rax
0x1800052e5  jz      loc_180005493
0x1800052eb  xor     r12d, r12d
0x1800052ee  mov     r15d, r12d
0x1800052f1  mov     [rsp+0D8h+var_98], r12
0x1800052f6  lea     rax, [rsp+0D8h+var_98]
0x1800052fb  mov     [rsp+0D8h+var_B0], rax
0x180005300  mov     [rsp+0D8h+var_B8], r12d
0x180005305  xor     r9d, r9d
0x180005308  xor     edx, edx
0x18000530a  mov     r8d, 20h ; ' '
0x180005310  mov     rcx, rbp
0x180005313  mov     rax, rbx
0x180005316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000531b  test    eax, eax
0x18000531d  jns     loc_180005401
0x180005323  mov     rcx, [rsp+0D8h+var_98]
0x180005328  test    rcx, rcx
0x18000532b  jz      short loc_180005339
0x18000532d  mov     rax, [rcx]
0x180005330  mov     rax, [rax+10h]
0x180005334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005339  mov     [rsp+0D8h+var_98], r12
0x18000533e  lea     rax, [rsp+0D8h+var_98]
0x180005343  mov     [rsp+0D8h+var_B0], rax
0x180005348  mov     [rsp+0D8h+var_B8], r12d
0x18000534d  xor     r9d, r9d
0x180005350  xor     edx, edx
0x180005352  mov     r8d, 10040h
0x180005358  mov     rcx, rbp
0x18000535b  mov     rax, rbx
0x18000535e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005363  test    eax, eax
0x180005365  jns     loc_180005401
0x18000536b  mov     rcx, [rsp+0D8h+var_98]
0x180005370  test    rcx, rcx
0x180005373  jz      short loc_180005381
0x180005375  mov     rax, [rcx]
0x180005378  mov     rax, [rax+10h]
0x18000537c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005381  mov     [rsp+0D8h+var_98], r12
0x180005386  test    dil, dil
0x180005389  jz      short loc_1800053A5
0x18000538b  lea     rdx, ProcName; "CoUninitialize"
0x180005392  mov     rcx, rsi; hModule
0x180005395  call    cs:__imp_GetProcAddress
0x18000539b  test    rax, rax
0x18000539e  jz      short loc_1800053A5
0x1800053a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053a5  mov     rcx, rsi; hLibModule
0x1800053a8  call    cs:__imp_FreeLibrary
0x1800053ae  nop
0x1800053af  mov     rcx, [rsp+0D8h+var_98]
0x1800053b4  test    rcx, rcx
0x1800053b7  jz      short loc_1800053C6
0x1800053b9  mov     rdx, [rcx]
0x1800053bc  mov     rax, [rdx+10h]
0x1800053c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053c5  nop
0x1800053c6  mov     eax, r15d
0x1800053c9  jmp     loc_180005256
0x1800053ce  cmp     edi, 80010106h
0x1800053d4  jz      loc_1800052C8
0x1800053da  movzx   ecx, di; dwErrCode
0x1800053dd  call    cs:__imp_SetLastError
0x1800053e3  call    cs:__imp_GetLastError
0x1800053e9  mov     ebx, eax
0x1800053eb  mov     rcx, rsi; hLibModule
0x1800053ee  call    cs:__imp_FreeLibrary
0x1800053f4  mov     ecx, ebx; dwErrCode
0x1800053f6  call    cs:__imp_SetLastError
0x1800053fc  jmp     loc_180005254
0x180005401  mov     rbx, [rsp+0D8h+var_98]
0x180005406  test    rbx, rbx
0x180005409  jz      loc_180005381
0x18000540f  xor     edx, edx; Val
0x180005411  mov     r8d, 50h ; 'P'; Size
0x180005417  lea     rcx, [rsp+0D8h+var_88]; void *
0x18000541c  call    memset_0
0x180005421  mov     rax, [rbx]
0x180005424  mov     r8d, 1
0x18000542a  lea     rdx, [rsp+0D8h+var_88]
0x18000542f  mov     rcx, rbx
0x180005432  mov     rax, [rax+88h]
0x180005439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000543e  test    eax, eax
0x180005440  js      loc_18000536B
0x180005446  mov     eax, [rsp+0D8h+var_50]
0x18000544d  add     eax, 0FFF3EF80h
0x180005452  cmp     eax, 6
0x180005455  ja      loc_18000536B
0x18000545b  mov     r8d, 0Ch; Size
0x180005461  lea     rdx, dword_18000F9AC; Buf2
0x180005468  lea     rcx, [rsp+0D8h+Buf1]; Buf1
0x180005470  call    memcmp_0
0x180005475  test    eax, eax
0x180005477  jnz     loc_18000536B
0x18000547d  movups  xmm0, xmmword ptr cs:?gMSI@@3U_GUID@@A.Data1; _GUID gMSI ...
0x180005484  movups  xmmword ptr [r14], xmm0
0x180005488  mov     r15d, 1
0x18000548e  jmp     loc_18000536B
0x180005493  test    dil, dil
0x180005496  jz      short loc_1800054B2
0x180005498  lea     rdx, ProcName; "CoUninitialize"
0x18000549f  mov     rcx, rsi; hModule
0x1800054a2  call    cs:__imp_GetProcAddress
0x1800054a8  test    rax, rax
0x1800054ab  jz      short loc_1800054B2
0x1800054ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b2  mov     rcx, rsi; hLibModule
0x1800054b5  call    cs:__imp_FreeLibrary
0x1800054bb  jmp     loc_180005254
0x1800054c0  mov     rdx, rbx; String2
0x1800054c3  lea     rcx, aCmd; ".cmd"
0x1800054ca  call    cs:__imp__wcsicmp
0x1800054d0  test    eax, eax
0x1800054d2  jz      loc_180005254
0x1800054d8  mov     rdx, rbx; String2
0x1800054db  lea     rcx, aBat; ".bat"
0x1800054e2  call    cs:__imp__wcsicmp
0x1800054e8  test    eax, eax
0x1800054ea  jz      loc_180005254
0x1800054f0  mov     rdx, rbx; String2
0x1800054f3  lea     rcx, aPs1; ".ps1"
0x1800054fa  call    cs:__imp__wcsicmp
0x180005500  test    eax, eax
0x180005502  jz      loc_180005254
0x180005508  mov     rdx, rbx; String2
0x18000550b  lea     rcx, aWsh; ".wsh"
0x180005512  call    cs:__imp__wcsicmp
0x180005518  test    eax, eax
0x18000551a  jz      loc_180005254
0x180005520  mov     rdx, rbx; String2
0x180005523  lea     rcx, aWsf; ".wsf"
0x18000552a  call    cs:__imp__wcsicmp
0x180005530  test    eax, eax
0x180005532  jz      loc_180005254
0x180005538  mov     rdx, rbx; String2
0x18000553b  lea     rcx, aJs; ".js"
0x180005542  call    cs:__imp__wcsicmp
0x180005548  test    eax, eax
0x18000554a  jz      loc_180005254
0x180005550  mov     rdx, rbx; String2
0x180005553  lea     rcx, aVbs; ".vbs"
0x18000555a  call    cs:__imp__wcsicmp
0x180005560  test    eax, eax
0x180005562  jz      loc_180005254
0x180005568  mov     rdx, rbx; String2
0x18000556b  lea     rcx, aVbe; ".vbe"
0x180005572  call    cs:__imp__wcsicmp
0x180005578  test    eax, eax
0x18000557a  jz      loc_180005254
0x180005580  mov     rdx, rbx; String2
0x180005583  lea     rcx, aJse; ".jse"
0x18000558a  call    cs:__imp__wcsicmp
0x180005590  test    eax, eax
0x180005592  jz      loc_180005254
0x180005598  jmp     loc_180005282
```
