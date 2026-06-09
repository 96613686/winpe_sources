# CHttpPolicyExtensionEntry::Initialize(void)

- ea: `0x1800b9138`
- end: `0x1800b9562`
- name: `?Initialize@CHttpPolicyExtensionEntry@@QEAAHXZ`
- size: `1066`
- prototype: `__int64 __fastcall(CHttpPolicyExtensionEntry *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b8e8c`
- `0x1800b90d0`

## callees

- `0x1800b9138`
- `0x1800f73c8`
- `0x180106074`
- `0x18012c5f4`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801b100c`
- `0x1801b1048`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e21a0`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e41b0`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b92f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b92f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9523`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b93f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b9430`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b93f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b9430`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b93b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b93b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b92d9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b92d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b933b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b933b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b93a5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b93a5`

## string_xrefs

- `0x1800b93ed`: `HttpPolicyExtensionInit`
- `0x1800b9425`: `HttpPolicyExtensionShutdown`

## pseudocode

```c
__int64 __fastcall CHttpPolicyExtensionEntry::Initialize(CHttpPolicyExtensionEntry *this)
{
  unsigned int v2; // edi
  signed int v3; // r14d
  __int64 FileW; // rbx
  size_t v5; // rdx
  HRESULT v6; // eax
  __int64 v7; // rcx
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  int v12; // eax
  HMODULE LibraryW; // rax
  HMODULE v14; // rcx
  unsigned int v15; // [rsp+4Ch] [rbp-29Ch]
  HMODULE v16; // [rsp+58h] [rbp-290h]
  FARPROC ProcAddress; // [rsp+58h] [rbp-290h]
  LPCWSTR *v18; // [rsp+68h] [rbp-280h]
  FARPROC v19; // [rsp+80h] [rbp-268h]
  int v20; // [rsp+88h] [rbp-260h] BYREF
  wchar_t pszDest[37]; // [rsp+90h] [rbp-258h] BYREF
  _BYTE v22[454]; // [rsp+DAh] [rbp-20Eh] BYREF

  v2 = 0;
  v3 = 0;
  FileW = -1;
  wcscpy(pszDest, L"SOFTWARE\\Policies\\Microsofindows\\");
  memset_0(v22, 0, 0x1BEu);
  v20 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_(1038, 11, &WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids);
  if ( **((_DWORD **)this + 3) )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
      WPP_SF_S(1038, 12, &WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, *((_QWORD *)this + 4));
    v2 = 1;
    goto LABEL_20;
  }
  v6 = StringCchCatW(pszDest, v5, *((STRSAFE_LPCWSTR *)this + 6));
  v3 = v6;
  if ( v6 > 0 )
    v3 = (unsigned __int16)v6 | 0x80070000;
  if ( v3 < 0 )
    goto LABEL_20;
  if ( (int)WxRegValuesExist(v7, pszDest, &v20) >= 0 && v20 )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
      WPP_SF_S(1038, 14, &WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, *((_QWORD *)this + 4));
    v18 = (LPCWSTR *)((char *)this + 32);
    FileW = (__int64)CreateFileW(*((LPCWSTR *)this + 4), 0x80000000, 1u, 0, 3u, 0, 0);
    if ( FileW == -1 )
    {
      if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
      {
        LastError = GetLastError();
        v9 = 15;
LABEL_17:
        v10 = LastError;
LABEL_18:
        WPP_SF_d(1038, v9, &WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, v10);
      }
    }
    else
    {
      v12 = WxVerifyMicrosoftSignedEx(*v18, *((unsigned int *)this + 4));
      v3 = v12;
      if ( v12 > 0 )
        v3 = (unsigned __int16)v12 | 0x80070000;
      if ( v3 < 0 )
        goto LABEL_19;
      LibraryW = LoadLibraryW(*v18);
      v16 = LibraryW;
      v14 = (HMODULE)*((_QWORD *)this + 8);
      if ( v14 )
      {
        FreeLibrary(v14);
        LibraryW = v16;
      }
      *((_QWORD *)this + 8) = LibraryW;
      if ( !LibraryW )
      {
        if ( (BYTE1(xmmword_180266B60) & 0x40) == 0 )
          goto LABEL_19;
        LastError = GetLastError();
        v9 = 16;
        goto LABEL_17;
      }
      if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
        WPP_SF_q(1038, 17, &WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, LibraryW);
      ProcAddress = GetProcAddress(*((HMODULE *)this + 8), "HttpPolicyExtensionInit");
      if ( !ProcAddress )
      {
        if ( (BYTE1(xmmword_180266B60) & 0x40) == 0 )
          goto LABEL_19;
        LastError = GetLastError();
        v9 = 18;
        goto LABEL_17;
      }
      v19 = GetProcAddress(*((HMODULE *)this + 8), "HttpPolicyExtensionShutdown");
      if ( !v19 )
      {
        if ( (BYTE1(xmmword_180266B60) & 0x40) == 0 )
          goto LABEL_19;
        LastError = GetLastError();
        v9 = 19;
        goto LABEL_17;
      }
      v15 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))ProcAddress)(1, *((unsigned int *)this + 5), 0, 0);
      v10 = v15;
      if ( !v15 )
      {
        *((_QWORD *)this + 9) = ProcAddress;
        *((_QWORD *)this + 10) = v19;
        if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
          WPP_SF_S(1038, 21, &WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, *v18);
        goto LABEL_19;
      }
      if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
      {
        v9 = 20;
        goto LABEL_18;
      }
    }
LABEL_19:
    v2 = 1;
    goto LABEL_20;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x40) == 0 )
    goto LABEL_22;
  WPP_SF_SS(
    1038,
    13,
    (unsigned int)&WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids,
    *((_QWORD *)this + 6),
    *((_QWORD *)this + 4));
LABEL_20:
  if ( (BYTE1(xmmword_180266B60) & 0x40) != 0 )
    WPP_SF_dd(1038, 22, &WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids, v2, v3);
LABEL_22:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return v2;
}

```

## disassembly

```asm
0x1800b9138  push    rbx
0x1800b913a  push    rsi
0x1800b913b  push    rdi
0x1800b913c  push    r12
0x1800b913e  push    r14
0x1800b9140  push    r15
0x1800b9142  sub     rsp, 2B8h
0x1800b9149  mov     rax, cs:__security_cookie
0x1800b9150  xor     rax, rsp
0x1800b9153  mov     [rsp+2E8h+var_48], rax
0x1800b915b  mov     rsi, rcx
0x1800b915e  mov     [rsp+2E8h+var_270], rcx
0x1800b9163  xor     edi, edi
0x1800b9165  mov     r14d, edi
0x1800b9168  mov     [rsp+2E8h+var_294], edi
0x1800b916c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9170  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_3; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800b9177  movaps  xmmword ptr [rsp+2E8h+pszDest], xmm0
0x1800b917f  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_3+10h; "\\Policies\\Microsoft\\Windows\\"
0x1800b9186  movaps  [rsp+2E8h+var_248], xmm1
0x1800b918e  movaps  xmm0, xmmword ptr cs:aSoftwarePolici_3+20h; "s\\Microsoft\\Windows\\"
0x1800b9195  movaps  [rsp+2E8h+var_238], xmm0
0x1800b919d  movaps  xmm1, xmmword ptr cs:aSoftwarePolici_3+30h; "oft\\Windows\\"
0x1800b91a4  movaps  [rsp+2E8h+var_228], xmm1
0x1800b91ac  movups  xmm0, xmmword ptr cs:aSoftwarePolici_3+3Ah; "indows\\"
0x1800b91b3  movups  [rsp+2E8h+var_228+0Ah], xmm0
0x1800b91bb  xor     edx, edx; Val
0x1800b91bd  mov     r8d, 1BEh; Size
0x1800b91c3  lea     rcx, [rsp+2E8h+var_20E]; void *
0x1800b91cb  call    memset_0
0x1800b91d0  mov     [rsp+2E8h+var_260], edi
0x1800b91d7  mov     r15d, 40Eh
0x1800b91dd  lea     r12, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids
0x1800b91e4  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b91eb  jz      short loc_1800B91FB
0x1800b91ed  lea     edx, [rdi+0Bh]
0x1800b91f0  mov     ecx, r15d
0x1800b91f3  mov     r8, r12
0x1800b91f6  call    WPP_SF_
0x1800b91fb  mov     rax, [rsi+18h]
0x1800b91ff  cmp     [rax], edi
0x1800b9201  jz      short loc_1800B922A
0x1800b9203  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b920a  jz      short loc_1800B9220
0x1800b920c  mov     edx, 0Ch
0x1800b9211  mov     ecx, r15d
0x1800b9214  mov     r9, [rsi+20h]
0x1800b9218  mov     r8, r12
0x1800b921b  call    WPP_SF_S
0x1800b9220  mov     edi, 1
0x1800b9225  jmp     loc_1800B9311
0x1800b922a  mov     r8, [rsi+30h]; pszSrc
0x1800b922e  lea     rcx, [rsp+2E8h+pszDest]; pszDest
0x1800b9236  call    StringCchCatW
0x1800b923b  mov     r14d, eax
0x1800b923e  test    eax, eax
0x1800b9240  jle     short loc_1800B924D
0x1800b9242  movzx   r14d, ax
0x1800b9246  or      r14d, 80070000h
0x1800b924d  test    r14d, r14d
0x1800b9250  jns     short loc_1800B925F
0x1800b9252  mov     [rsp+2E8h+var_294], 63h ; 'c'
0x1800b925a  jmp     loc_1800B9311
0x1800b925f  lea     r8, [rsp+2E8h+var_260]
0x1800b9267  lea     rdx, [rsp+2E8h+pszDest]
0x1800b926f  call    WxRegValuesExist
0x1800b9274  test    eax, eax
0x1800b9276  js      loc_1800B9533
0x1800b927c  cmp     [rsp+2E8h+var_260], edi
0x1800b9283  jz      loc_1800B9533
0x1800b9289  mov     ebx, 1
0x1800b928e  mov     [rsp+2E8h+var_2A8], ebx
0x1800b9292  mov     [rsp+2E8h+var_288], ebx
0x1800b9296  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b929d  jz      short loc_1800B92B1
0x1800b929f  lea     edx, [rbx+0Dh]
0x1800b92a2  mov     ecx, r15d
0x1800b92a5  mov     r9, [rsi+20h]
0x1800b92a9  mov     r8, r12
0x1800b92ac  call    WPP_SF_S
0x1800b92b1  lea     rax, [rsi+20h]
0x1800b92b5  mov     [rsp+2E8h+var_280], rax
0x1800b92ba  mov     [rsp+2E8h+hTemplateFile], rdi; hTemplateFile
0x1800b92bf  mov     [rsp+2E8h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800b92c3  mov     [rsp+2E8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800b92cb  xor     r9d, r9d; lpSecurityAttributes
0x1800b92ce  mov     r8d, ebx; dwShareMode
0x1800b92d1  mov     edx, 80000000h; dwDesiredAccess
0x1800b92d6  mov     rcx, [rax]; lpFileName
0x1800b92d9  call    cs:__imp_CreateFileW
0x1800b92df  mov     rbx, rax
0x1800b92e2  mov     [rsp+2E8h+var_278], rax
0x1800b92e7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b92eb  jnz     short loc_1800B9364
0x1800b92ed  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b92f4  jz      short loc_1800B930D
0x1800b92f6  call    cs:__imp_GetLastError
0x1800b92fc  lea     edx, [rbx+10h]
0x1800b92ff  mov     r9d, eax
0x1800b9302  mov     ecx, r15d
0x1800b9305  mov     r8, r12
0x1800b9308  call    WPP_SF_d
0x1800b930d  mov     edi, [rsp+2E8h+var_2A8]
0x1800b9311  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b9318  jz      short loc_1800B9332
0x1800b931a  mov     edx, 16h
0x1800b931f  mov     ecx, r15d
0x1800b9322  mov     [rsp+2E8h+dwCreationDisposition], r14d
0x1800b9327  mov     r9d, edi
0x1800b932a  mov     r8, r12
0x1800b932d  call    WPP_SF_dd
0x1800b9332  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9336  jz      short loc_1800B9341
0x1800b9338  mov     rcx, rbx; hObject
0x1800b933b  call    cs:__imp_CloseHandle
0x1800b9341  mov     eax, edi
0x1800b9343  mov     rcx, [rsp+2E8h+var_48]
0x1800b934b  xor     rcx, rsp; StackCookie
0x1800b934e  call    __security_check_cookie
0x1800b9353  add     rsp, 2B8h
0x1800b935a  pop     r15
0x1800b935c  pop     r14
0x1800b935e  pop     r12
0x1800b9360  pop     rdi
0x1800b9361  pop     rsi
0x1800b9362  pop     rbx
0x1800b9363  retn
0x1800b9364  mov     edx, [rsi+10h]
0x1800b9367  mov     rcx, [rsp+2E8h+var_280]
0x1800b936c  mov     rcx, [rcx]
0x1800b936f  call    WxVerifyMicrosoftSignedEx
0x1800b9374  mov     r14d, eax
0x1800b9377  test    eax, eax
0x1800b9379  jle     short loc_1800B9386
0x1800b937b  movzx   r14d, ax
0x1800b937f  or      r14d, 80070000h
0x1800b9386  mov     [rsp+2E8h+var_298], r14d
0x1800b938b  test    r14d, r14d
0x1800b938e  jns     short loc_1800B939D
0x1800b9390  mov     [rsp+2E8h+var_294], 91h
0x1800b9398  jmp     loc_1800B930D
0x1800b939d  mov     rax, [rsp+2E8h+var_280]
0x1800b93a2  mov     rcx, [rax]; lpLibFileName
0x1800b93a5  call    cs:__imp_LoadLibraryW
0x1800b93ab  mov     [rsp+2E8h+var_290], rax
0x1800b93b0  mov     rcx, [rsi+40h]; hLibModule
0x1800b93b4  test    rcx, rcx
0x1800b93b7  jz      short loc_1800B93C4
0x1800b93b9  call    cs:__imp_FreeLibrary
0x1800b93bf  mov     rax, [rsp+2E8h+var_290]
0x1800b93c4  mov     [rsi+40h], rax
0x1800b93c8  test    rax, rax
0x1800b93cb  jz      loc_1800B9516
0x1800b93d1  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b93d8  jz      short loc_1800B93ED
0x1800b93da  mov     edx, 11h
0x1800b93df  mov     ecx, r15d
0x1800b93e2  mov     r9, rax
0x1800b93e5  mov     r8, r12
0x1800b93e8  call    WPP_SF_q
0x1800b93ed  lea     rdx, aHttppolicyexte; "HttpPolicyExtensionInit"
0x1800b93f4  mov     rcx, [rsi+40h]; hModule
0x1800b93f8  call    cs:__imp_GetProcAddress
0x1800b93fe  mov     [rsp+2E8h+var_290], rax
0x1800b9403  test    rax, rax
0x1800b9406  jnz     short loc_1800B9425
0x1800b9408  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b940f  jz      loc_1800B930D
0x1800b9415  call    cs:__imp_GetLastError
0x1800b941b  mov     edx, 12h
0x1800b9420  jmp     loc_1800B92FF
0x1800b9425  lea     rdx, aHttppolicyexte_0; "HttpPolicyExtensionShutdown"
0x1800b942c  mov     rcx, [rsi+40h]; hModule
0x1800b9430  call    cs:__imp_GetProcAddress
0x1800b9436  mov     [rsp+2E8h+var_268], rax
0x1800b943e  test    rax, rax
0x1800b9441  jnz     short loc_1800B9460
0x1800b9443  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b944a  jz      loc_1800B930D
0x1800b9450  call    cs:__imp_GetLastError
0x1800b9456  mov     edx, 13h
0x1800b945b  jmp     loc_1800B92FF
0x1800b9460  mov     [rsp+2E8h+var_29C], edi
0x1800b9464  mov     ecx, [rsp+2E8h+var_2A8]
0x1800b9468  mov     [rsp+2E8h+var_2A4], ecx
0x1800b946c  xor     r9d, r9d
0x1800b946f  xor     r8d, r8d
0x1800b9472  mov     edx, [rsi+14h]
0x1800b9475  mov     rax, [rsp+2E8h+var_290]
0x1800b947a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b947f  mov     [rsp+2E8h+var_29C], eax
0x1800b9483  jmp     short loc_1800B94AB
0x1800b9485  xor     edi, edi
0x1800b9487  mov     r15d, 40Eh
0x1800b948d  lea     r12, WPP_70a6ea6fbc8b32957ec072c0c9e35dfc_Traceguids
0x1800b9494  mov     r14d, [rsp+2E8h+var_298]
0x1800b9499  mov     rbx, [rsp+2E8h+var_278]
0x1800b949e  mov     ecx, [rsp+2E8h+var_288]
0x1800b94a2  mov     [rsp+2E8h+var_2A8], ecx
0x1800b94a6  mov     rsi, [rsp+2E8h+var_270]
0x1800b94ab  cmp     [rsp+2E8h+var_2A4], edi
0x1800b94af  jnz     short loc_1800B94B6
0x1800b94b1  call    WxReportSwallowedFatalException
0x1800b94b6  mov     r9d, [rsp+2E8h+var_29C]
0x1800b94bb  test    r9d, r9d
0x1800b94be  jz      short loc_1800B94D7
0x1800b94c0  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b94c7  jz      loc_1800B930D
0x1800b94cd  mov     edx, 14h
0x1800b94d2  jmp     loc_1800B9302
0x1800b94d7  mov     rax, [rsp+2E8h+var_290]
0x1800b94dc  mov     [rsi+48h], rax
0x1800b94e0  mov     rax, [rsp+2E8h+var_268]
0x1800b94e8  mov     [rsi+50h], rax
0x1800b94ec  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b94f3  jz      loc_1800B930D
0x1800b94f9  mov     edx, 15h
0x1800b94fe  mov     ecx, r15d
0x1800b9501  mov     rax, [rsp+2E8h+var_280]
0x1800b9506  mov     r9, [rax]
0x1800b9509  mov     r8, r12
0x1800b950c  call    WPP_SF_S
0x1800b9511  jmp     loc_1800B930D
0x1800b9516  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b951d  jz      loc_1800B930D
0x1800b9523  call    cs:__imp_GetLastError
0x1800b9529  mov     edx, 10h
0x1800b952e  jmp     loc_1800B92FF
0x1800b9533  test    byte ptr cs:xmmword_180266B60+1, 40h
0x1800b953a  jz      loc_1800B9332
0x1800b9540  mov     edx, 0Dh
0x1800b9545  mov     ecx, r15d
0x1800b9548  mov     rax, [rsi+20h]
0x1800b954c  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax
0x1800b9551  mov     r9, [rsi+30h]
0x1800b9555  mov     r8, r12
0x1800b9558  call    WPP_SF_SS
0x1800b955d  jmp     loc_1800B9311
0x1801ca327  push    rbp
0x1801ca329  sub     rsp, 40h
0x1801ca32d  mov     rbp, rdx
0x1801ca330  call    WxSaveExceptionFilter
0x1801ca335  mov     [rbp+44h], eax
0x1801ca338  mov     eax, [rbp+44h]
0x1801ca33b  add     rsp, 40h
0x1801ca33f  pop     rbp
0x1801ca340  retn
0x1801ca342  push    rbp
0x1801ca344  sub     rsp, 40h
0x1801ca348  mov     rbp, rdx
0x1801ca34b  cmp     dword ptr [rbp+44h], 0
0x1801ca34f  jnz     short loc_1801CA357
0x1801ca351  call    WxReportSwallowedFatalException
0x1801ca357  add     rsp, 40h
0x1801ca35b  pop     rbp
0x1801ca35c  retn
```
