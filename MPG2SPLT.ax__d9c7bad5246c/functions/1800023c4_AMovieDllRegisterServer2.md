# AMovieDllRegisterServer2

- ea: `0x1800023c4`
- end: `0x1800025eb`
- name: `AMovieDllRegisterServer2`
- size: `551`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001f80`
- `0x180001f90`

## callees

- `0x180001460`
- `0x1800023c4`
- `0x1800025f4`
- `0x1800026b8`
- `0x1800029c8`
- `0x1800065c4`
- `0x180034010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180002474`
- `KERNEL32!MultiByteToWideChar` at `0x180002474`
- `KERNEL32!GetLastError` at `0x18000240b`
- `KERNEL32!GetLastError` at `0x18000240b`
- `KERNEL32!GetModuleFileNameA` at `0x180002401`
- `KERNEL32!GetModuleFileNameA` at `0x180002401`
- `ole32!CoCreateInstance` at `0x180002501`
- `ole32!CoCreateInstance` at `0x18000252b`
- `ole32!CoCreateInstance` at `0x180002501`
- `ole32!CoCreateInstance` at `0x18000252b`
- `ole32!CoUninitialize` at `0x180002593`
- `ole32!CoUninitialize` at `0x180002593`
- `ole32!CoFreeUnusedLibraries` at `0x18000258d`
- `ole32!CoFreeUnusedLibraries` at `0x18000258d`
- `ole32!CoInitializeEx` at `0x1800024cb`
- `ole32!CoInitializeEx` at `0x1800024cb`

## pseudocode

```c
__int64 __fastcall AMovieDllRegisterServer2(unsigned int a1)
{
  __int64 result; // rax
  __int64 v3; // r8
  CHAR *v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rdx
  int Instance; // ebx
  __int64 v8; // rdi
  __int64 v9; // rcx
  int v10; // eax
  LPVOID v11; // rcx
  __int64 v12; // rdi
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR Filename[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[264]; // [rsp+160h] [rbp+60h] BYREF

  if ( !GetModuleFileNameA(g_hInst, Filename, 0x104u) )
    return GetLastError() | 0x80070000;
  v3 = 260;
  v4 = Filename;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0x80070057 : 0;
  if ( v3 )
  {
    MultiByteToWideChar(0, 0, Filename, v3 != 0 ? 260 - v3 + 1 : 1, WideCharStr, 260);
    if ( a1 )
    {
      v5 = 0;
      while ( 1 )
      {
        v6 = (__int64)*(&g_Templates + 5 * v5);
        *(_OWORD *)v14 = *(_OWORD *)*(&g_Templates + 5 * v5 + 1);
        Instance = AMovieSetupRegisterServer((const GUID *)v14, v6, (__int64)WideCharStr);
        if ( Instance < 0 )
          break;
        v5 = (unsigned int)(v5 + 1);
        if ( (int)v5 >= 5 )
          goto LABEL_11;
      }
    }
    else
    {
LABEL_11:
      CoInitializeEx(0, 2u);
      ppv = 0;
      v14[0] = 0;
      Instance = CoCreateInstance(&CLSID_FilterMapper2, 0, 1u, &IID_IFilterMapper2, &ppv);
      if ( Instance >= 0
        || (Instance = CoCreateInstance(&CLSID_FilterMapper, 0, 1u, &IID_IFilterMapper, v14), Instance >= 0) )
      {
        v8 = 0;
        do
        {
          v9 = (__int64)*(&g_Templates + 5 * v8 + 4);
          if ( v9 )
          {
            if ( ppv )
              v10 = AMovieSetupRegisterFilter2(v9, ppv, a1);
            else
              v10 = AMovieSetupRegisterFilter(v9, v14[0], a1);
            Instance = v10;
          }
          if ( Instance < 0 )
            break;
          v8 = (unsigned int)(v8 + 1);
        }
        while ( (int)v8 < 5 );
        v11 = ppv;
        if ( !ppv )
          v11 = v14[0];
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
      }
      CoFreeUnusedLibraries();
      CoUninitialize();
      if ( Instance >= 0 && !a1 )
      {
        v12 = 0;
        do
        {
          *(_OWORD *)v14 = *(_OWORD *)*(&g_Templates + 5 * v12 + 1);
          Instance = AMovieSetupUnregisterServer(v14);
          if ( Instance < 0 )
            break;
          v12 = (unsigned int)(v12 + 1);
        }
        while ( (int)v12 < 5 );
      }
    }
    return (unsigned int)Instance;
  }
  return result;
}

```

## disassembly

```asm
0x1800023c4  push    rbp
0x1800023c6  push    rbx
0x1800023c7  push    rsi
0x1800023c8  push    rdi
0x1800023c9  push    r12
0x1800023cb  lea     rbp, [rsp-280h]
0x1800023d3  sub     rsp, 380h
0x1800023da  mov     rax, cs:__security_cookie
0x1800023e1  xor     rax, rsp
0x1800023e4  mov     [rbp+2A0h+var_30], rax
0x1800023eb  mov     esi, ecx
0x1800023ed  lea     rdx, [rsp+3A0h+Filename]; lpFilename
0x1800023f2  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x1800023f9  mov     ebx, 104h
0x1800023fe  mov     r8d, ebx; nSize
0x180002401  call    cs:__imp_GetModuleFileNameA
0x180002407  test    eax, eax
0x180002409  jnz     short loc_18000241B
0x18000240b  call    cs:__imp_GetLastError
0x180002411  or      eax, 80070000h
0x180002416  jmp     loc_1800025CE
0x18000241b  mov     r8, rbx
0x18000241e  lea     rax, [rsp+3A0h+Filename]
0x180002423  cmp     byte ptr [rax], 0
0x180002426  jz      short loc_180002431
0x180002428  inc     rax
0x18000242b  sub     r8, 1
0x18000242f  jnz     short loc_180002423
0x180002431  mov     rax, r8
0x180002434  mov     rdx, rbx
0x180002437  neg     rax
0x18000243a  mov     rcx, r8
0x18000243d  sbb     eax, eax
0x18000243f  sub     rdx, r8
0x180002442  not     eax
0x180002444  and     eax, 80070057h
0x180002449  neg     rcx
0x18000244c  sbb     r9, r9
0x18000244f  and     r9, rdx
0x180002452  test    r8, r8
0x180002455  jz      loc_1800025CE
0x18000245b  lea     rax, [rbp+2A0h+WideCharStr]
0x18000245f  mov     [rsp+3A0h+cchWideChar], ebx; cchWideChar
0x180002463  inc     r9d; cbMultiByte
0x180002466  mov     [rsp+3A0h+lpWideCharStr], rax; lpWideCharStr
0x18000246b  lea     r8, [rsp+3A0h+Filename]; lpMultiByteStr
0x180002470  xor     edx, edx; dwFlags
0x180002472  xor     ecx, ecx; CodePage
0x180002474  call    cs:__imp_MultiByteToWideChar
0x18000247a  lea     r12, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x180002481  test    esi, esi
0x180002483  jz      short loc_1800024C4
0x180002485  xor     edi, edi
0x180002487  lea     rdx, [rdi+rdi*4]
0x18000248b  mov     rax, [r12+rdx*8+8]
0x180002490  lea     r8, [rbp+2A0h+WideCharStr]
0x180002494  mov     rdx, [r12+rdx*8]
0x180002498  lea     rcx, [rsp+3A0h+var_360]
0x18000249d  movups  xmm0, xmmword ptr [rax]
0x1800024a0  movdqu  xmmword ptr [rsp+3A0h+var_360], xmm0
0x1800024a6  call    AMovieSetupRegisterServer
0x1800024ab  mov     ebx, eax
0x1800024ad  test    eax, eax
0x1800024af  js      loc_1800025CC
0x1800024b5  inc     edi
0x1800024b7  cmp     edi, 5
0x1800024ba  jl      short loc_180002487
0x1800024bc  test    eax, eax
0x1800024be  js      loc_1800025CC
0x1800024c4  mov     edx, 2; dwCoInit
0x1800024c9  xor     ecx, ecx; pvReserved
0x1800024cb  call    cs:__imp_CoInitializeEx
0x1800024d1  xor     edx, edx; pUnkOuter
0x1800024d3  mov     [rsp+3A0h+ppv], 0
0x1800024dc  lea     rax, [rsp+3A0h+ppv]
0x1800024e1  mov     [rsp+3A0h+var_360], 0
0x1800024ea  lea     r9, IID_IFilterMapper2; riid
0x1800024f1  mov     [rsp+3A0h+lpWideCharStr], rax; ppv
0x1800024f6  lea     rcx, CLSID_FilterMapper2; rclsid
0x1800024fd  lea     r8d, [rdx+1]; dwClsContext
0x180002501  call    cs:__imp_CoCreateInstance
0x180002507  mov     ebx, eax
0x180002509  test    eax, eax
0x18000250b  jns     short loc_180002537
0x18000250d  xor     edx, edx; pUnkOuter
0x18000250f  lea     rax, [rsp+3A0h+var_360]
0x180002514  lea     r9, IID_IFilterMapper; riid
0x18000251b  mov     [rsp+3A0h+lpWideCharStr], rax; ppv
0x180002520  lea     rcx, CLSID_FilterMapper; rclsid
0x180002527  lea     r8d, [rdx+1]; dwClsContext
0x18000252b  call    cs:__imp_CoCreateInstance
0x180002531  mov     ebx, eax
0x180002533  test    eax, eax
0x180002535  js      short loc_18000258D
0x180002537  xor     edi, edi
0x180002539  lea     rcx, [rdi+rdi*4]
0x18000253d  mov     rcx, [r12+rcx*8+20h]
0x180002542  test    rcx, rcx
0x180002545  jz      short loc_180002567
0x180002547  mov     rdx, [rsp+3A0h+ppv]
0x18000254c  mov     r8d, esi
0x18000254f  test    rdx, rdx
0x180002552  jz      short loc_18000255B
0x180002554  call    AMovieSetupRegisterFilter2
0x180002559  jmp     short loc_180002565
0x18000255b  mov     rdx, [rsp+3A0h+var_360]
0x180002560  call    AMovieSetupRegisterFilter
0x180002565  mov     ebx, eax
0x180002567  test    ebx, ebx
0x180002569  js      short loc_180002572
0x18000256b  inc     edi
0x18000256d  cmp     edi, 5
0x180002570  jl      short loc_180002539
0x180002572  mov     rcx, [rsp+3A0h+ppv]
0x180002577  test    rcx, rcx
0x18000257a  jnz     short loc_180002581
0x18000257c  mov     rcx, [rsp+3A0h+var_360]
0x180002581  mov     rax, [rcx]
0x180002584  mov     rax, [rax+10h]
0x180002588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000258d  call    cs:__imp_CoFreeUnusedLibraries
0x180002593  call    cs:__imp_CoUninitialize
0x180002599  test    ebx, ebx
0x18000259b  js      short loc_1800025CC
0x18000259d  test    esi, esi
0x18000259f  jnz     short loc_1800025CC
0x1800025a1  xor     edi, edi
0x1800025a3  lea     rax, [rdi+rdi*4]
0x1800025a7  mov     rax, [r12+rax*8+8]
0x1800025ac  lea     rcx, [rsp+3A0h+var_360]
0x1800025b1  movups  xmm0, xmmword ptr [rax]
0x1800025b4  movdqu  xmmword ptr [rsp+3A0h+var_360], xmm0
0x1800025ba  call    AMovieSetupUnregisterServer
0x1800025bf  mov     ebx, eax
0x1800025c1  test    eax, eax
0x1800025c3  js      short loc_1800025CC
0x1800025c5  inc     edi
0x1800025c7  cmp     edi, 5
0x1800025ca  jl      short loc_1800025A3
0x1800025cc  mov     eax, ebx
0x1800025ce  mov     rcx, [rbp+2A0h+var_30]
0x1800025d5  xor     rcx, rsp; StackCookie
0x1800025d8  call    __security_check_cookie
0x1800025dd  add     rsp, 380h
0x1800025e4  pop     r12
0x1800025e6  pop     rdi
0x1800025e7  pop     rsi
0x1800025e8  pop     rbx
0x1800025e9  pop     rbp
0x1800025ea  retn
```
