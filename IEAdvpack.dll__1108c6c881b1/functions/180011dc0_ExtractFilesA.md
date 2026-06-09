# ExtractFilesA

- ea: `0x180011dc0`
- end: `0x1800120fb`
- name: `ExtractFilesA`
- size: `827`
- prototype: `HRESULT __stdcall(LPCSTR pszCabName, LPCSTR pszExpandDir, DWORD dwFlags, LPCSTR pszFileList, LPVOID lpReserved, DWORD dwReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012110`

## callees

- `0x180011c90`
- `0x180011cb8`
- `0x180011d50`
- `0x180011dc0`
- `0x18001b980`
- `0x18001c010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001206f`
- `KERNEL32!LocalFree` at `0x1800120a8`
- `KERNEL32!LocalFree` at `0x18001206f`
- `KERNEL32!LocalFree` at `0x1800120a8`
- `KERNEL32!LocalAlloc` at `0x180011ecf`
- `KERNEL32!LocalAlloc` at `0x180011f28`
- `KERNEL32!LocalAlloc` at `0x180011ecf`
- `KERNEL32!LocalAlloc` at `0x180011f28`
- `KERNEL32!FreeLibrary` at `0x180011e7c`
- `KERNEL32!FreeLibrary` at `0x1800120c1`
- `KERNEL32!FreeLibrary` at `0x180011e7c`
- `KERNEL32!FreeLibrary` at `0x1800120c1`
- `KERNEL32!LoadLibraryExW` at `0x180011e27`
- `KERNEL32!LoadLibraryExW` at `0x180011e8e`
- `KERNEL32!LoadLibraryExW` at `0x180011e27`
- `KERNEL32!LoadLibraryExW` at `0x180011e8e`
- `KERNEL32!GetProcAddress` at `0x180011e44`
- `KERNEL32!GetProcAddress` at `0x180011e6b`
- `KERNEL32!GetProcAddress` at `0x180011eaf`
- `KERNEL32!GetProcAddress` at `0x180011e44`
- `KERNEL32!GetProcAddress` at `0x180011e6b`
- `KERNEL32!GetProcAddress` at `0x180011eaf`
- `KERNEL32!lstrcmpiA` at `0x180011fbf`
- `KERNEL32!lstrcmpiA` at `0x180011fbf`

## string_xrefs

- `0x180011e16`: `CABINET.DLL`
- `0x180011e3a`: `DllGetVersion`
- `0x180011e85`: `URLMON.DLL`

## pseudocode

```c
HRESULT __stdcall ExtractFilesA(
        LPCSTR pszCabName,
        LPCSTR pszExpandDir,
        DWORD dwFlags,
        LPCSTR pszFileList,
        LPVOID lpReserved,
        DWORD dwReserved)
{
  HRESULT v9; // ebx
  HMODULE Library; // rax
  HMODULE v11; // r14
  FARPROC ProcAddress; // rax
  FARPROC v13; // r12
  HMODULE v14; // rax
  char *v15; // rax
  char *v16; // rdi
  __int64 v17; // rax
  unsigned int v18; // esi
  char *v19; // rax
  int v20; // eax
  int v21; // r13d
  __int64 v22; // rbx
  __int64 v23; // r15
  const CHAR *v24; // rdx
  __int64 v25; // rbp
  int v26; // ecx
  const CHAR *v27; // rsi
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rsi
  LPVOID *v33; // rcx
  HMODULE v35; // [rsp+20h] [rbp-78h]
  CHAR *lpString1; // [rsp+28h] [rbp-70h]
  const CHAR *v37; // [rsp+30h] [rbp-68h]
  __int128 v39; // [rsp+40h] [rbp-58h] BYREF
  int v40; // [rsp+50h] [rbp-48h]

  v40 = 0;
  v39 = 0;
  if ( pszCabName && pszExpandDir )
  {
    v9 = -2147467259;
    Library = LoadLibraryExW(L"CABINET.DLL", 0, 0x800u);
    v35 = Library;
    v11 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "DllGetVersion");
      if ( ProcAddress )
      {
        LODWORD(v39) = 20;
        ((void (__fastcall *)(__int128 *))ProcAddress)(&v39);
        v13 = GetProcAddress(v11, "Extract");
        if ( v13 )
        {
LABEL_9:
          v15 = (char *)LocalAlloc(0x40u, 0x338u);
          v16 = v15;
          if ( v15 )
          {
            StringCchCopyA(v15 + 32, 0x104u, (char *)pszExpandDir);
            if ( !pszFileList )
            {
              *((_DWORD *)v16 + 7) = 3;
              v9 = ((__int64 (__fastcall *)(char *, LPCSTR))v13)(v16, pszCabName);
              goto LABEL_45;
            }
            v17 = -1;
            do
              ++v17;
            while ( pszFileList[v17] );
            v18 = v17 + 2;
            v19 = (char *)LocalAlloc(0x40u, (unsigned int)(v17 + 2));
            lpString1 = v19;
            if ( v19 )
            {
              v20 = PrepareFileList(v19, v18, pszFileList);
              *((_DWORD *)v16 + 7) = 1;
              v21 = v20;
              if ( v20 > 0 )
              {
                v9 = ((__int64 (__fastcall *)(char *, LPCSTR))v13)(v16, pszCabName);
                if ( v9 >= 0 )
                {
                  v22 = *((_QWORD *)v16 + 2);
                  v23 = 0;
                  if ( v22 )
                  {
                    do
                    {
                      v24 = *(const CHAR **)v22;
                      v25 = -1;
                      v37 = *(const CHAR **)v22;
                      do
                        ++v25;
                      while ( v24[v25] );
                      v26 = 0;
                      v27 = lpString1;
                      if ( *lpString1 )
                      {
                        while ( 1 )
                        {
                          if ( v26 )
                            goto LABEL_32;
                          v28 = -1;
                          do
                            ++v28;
                          while ( v27[v28] );
                          if ( (_DWORD)v28 != (_DWORD)v25 )
                            goto LABEL_28;
                          if ( lstrcmpiA(v27, v24) )
                            break;
                          v26 = 1;
LABEL_31:
                          v24 = v37;
                          if ( !*v27 )
                            goto LABEL_32;
                        }
                        v26 = 0;
LABEL_28:
                        v29 = -1;
                        do
                          ++v29;
                        while ( v27[v29] );
                        v27 += v29 + 1;
                        goto LABEL_31;
                      }
LABEL_32:
                      v30 = *(_QWORD *)(v22 + 8);
                      if ( v26 )
                      {
                        v23 = v22;
                        --v21;
                        v22 = *(_QWORD *)(v22 + 8);
                      }
                      else if ( v23 )
                      {
                        *(_QWORD *)(v23 + 8) = v30;
                        FreeFileNode((LPVOID *)v22);
                        v22 = *(_QWORD *)(v23 + 8);
                      }
                      else
                      {
                        *((_QWORD *)v16 + 2) = v30;
                        FreeFileNode((LPVOID *)v22);
                        v22 = *((_QWORD *)v16 + 2);
                      }
                    }
                    while ( v22 );
                    v11 = v35;
                  }
                  v31 = *((_QWORD *)v16 + 2);
                  if ( !v31 || v21 )
                  {
                    v9 = -2147467259;
                  }
                  else
                  {
                    *((_DWORD *)v16 + 7) &= ~1u;
                    *((_QWORD *)v16 + 102) = v31;
                    *((_DWORD *)v16 + 3) = 0;
                    *((_DWORD *)v16 + 1) = 0;
                    v9 = ((__int64 (__fastcall *)(char *, LPCSTR))v13)(v16, pszCabName);
                  }
                }
              }
              LocalFree(lpString1);
            }
            else
            {
              v9 = -2147024882;
            }
LABEL_45:
            v32 = *((_QWORD *)v16 + 2);
            while ( v32 )
            {
              v33 = (LPVOID *)v32;
              v32 = *(_QWORD *)(v32 + 8);
              FreeFileNode(v33);
            }
            *((_QWORD *)v16 + 2) = 0;
            LocalFree(v16);
            goto LABEL_50;
          }
          v9 = -2147024882;
LABEL_50:
          FreeLibrary(v11);
          if ( v9 == 1 )
            return -2147467259;
          return v9;
        }
      }
      FreeLibrary(v11);
    }
    v14 = LoadLibraryExW(L"URLMON.DLL", 0, 0x800u);
    v35 = v14;
    v11 = v14;
    if ( !v14 )
      return v9;
    v13 = GetProcAddress(v14, "Extract");
    if ( !v13 )
      goto LABEL_50;
    goto LABEL_9;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180011dc0  mov     [rsp+arg_10], rbx; ExtractFiles
0x180011dc5  push    rbp
0x180011dc6  push    rsi
0x180011dc7  push    rdi
0x180011dc8  push    r12
0x180011dca  push    r13
0x180011dcc  push    r14
0x180011dce  push    r15
0x180011dd0  sub     rsp, 60h
0x180011dd4  mov     rax, cs:__security_cookie
0x180011ddb  xor     rax, rsp
0x180011dde  mov     [rsp+98h+var_40], rax
0x180011de3  xor     eax, eax
0x180011de5  mov     [rsp+98h+var_60], rcx
0x180011dea  mov     [rsp+98h+var_48], eax
0x180011dee  xorps   xmm0, xmm0
0x180011df1  mov     rbp, r9
0x180011df4  mov     rsi, rdx
0x180011df7  mov     r15, rcx
0x180011dfa  movups  [rsp+98h+var_58], xmm0
0x180011dff  test    rcx, rcx
0x180011e02  jz      loc_1800120D1
0x180011e08  test    rdx, rdx
0x180011e0b  jz      loc_1800120D1
0x180011e11  mov     edi, 800h
0x180011e16  lea     rcx, aCabinetDll; "CABINET.DLL"
0x180011e1d  mov     r8d, edi; dwFlags
0x180011e20  xor     edx, edx; hFile
0x180011e22  mov     ebx, 80004005h
0x180011e27  call    cs:__imp_LoadLibraryExW
0x180011e2d  mov     [rsp+98h+var_78], rax
0x180011e32  mov     r14, rax
0x180011e35  test    rax, rax
0x180011e38  jz      short loc_180011E82
0x180011e3a  lea     rdx, aDllgetversion; "DllGetVersion"
0x180011e41  mov     rcx, rax; hModule
0x180011e44  call    cs:__imp_GetProcAddress
0x180011e4a  test    rax, rax
0x180011e4d  jz      short loc_180011E79
0x180011e4f  lea     rcx, [rsp+98h+var_58]
0x180011e54  mov     dword ptr [rsp+98h+var_58], 14h
0x180011e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e61  lea     rdx, aExtract; "Extract"
0x180011e68  mov     rcx, r14; hModule
0x180011e6b  call    cs:__imp_GetProcAddress
0x180011e71  mov     r12, rax
0x180011e74  test    rax, rax
0x180011e77  jnz     short loc_180011EC1
0x180011e79  mov     rcx, r14; hLibModule
0x180011e7c  call    cs:__imp_FreeLibrary
0x180011e82  mov     r8d, edi; dwFlags
0x180011e85  lea     rcx, aUrlmonDll; "URLMON.DLL"
0x180011e8c  xor     edx, edx; hFile
0x180011e8e  call    cs:__imp_LoadLibraryExW
0x180011e94  mov     [rsp+98h+var_78], rax
0x180011e99  mov     r14, rax
0x180011e9c  test    rax, rax
0x180011e9f  jz      loc_1800120CD
0x180011ea5  lea     rdx, aExtract; "Extract"
0x180011eac  mov     rcx, rax; hModule
0x180011eaf  call    cs:__imp_GetProcAddress
0x180011eb5  mov     r12, rax
0x180011eb8  test    rax, rax
0x180011ebb  jz      loc_1800120BC
0x180011ec1  mov     r13d, 40h ; '@'
0x180011ec7  mov     edx, 338h; uBytes
0x180011ecc  mov     ecx, r13d; uFlags
0x180011ecf  call    cs:__imp_LocalAlloc
0x180011ed5  mov     rdi, rax
0x180011ed8  test    rax, rax
0x180011edb  jz      loc_1800120B0
0x180011ee1  lea     rcx, [rax+20h]; char *
0x180011ee5  mov     r8, rsi; char *
0x180011ee8  mov     edx, 104h; unsigned __int64
0x180011eed  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180011ef2  test    rbp, rbp
0x180011ef5  jnz     short loc_180011F13
0x180011ef7  mov     rdx, r15
0x180011efa  mov     dword ptr [rdi+1Ch], 3
0x180011f01  mov     rcx, rdi
0x180011f04  mov     rax, r12
0x180011f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f0c  mov     ebx, eax
0x180011f0e  jmp     loc_180012085
0x180011f13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011f17  inc     rax
0x180011f1a  cmp     byte ptr [rax+rbp], 0
0x180011f1e  jnz     short loc_180011F17
0x180011f20  lea     esi, [rax+2]
0x180011f23  mov     ecx, r13d; uFlags
0x180011f26  mov     edx, esi; uBytes
0x180011f28  call    cs:__imp_LocalAlloc
0x180011f2e  mov     [rsp+98h+lpString1], rax
0x180011f33  test    rax, rax
0x180011f36  jz      loc_180012080
0x180011f3c  mov     r8, rbp; char *
0x180011f3f  mov     edx, esi; unsigned int
0x180011f41  mov     rcx, rax; char *
0x180011f44  call    ?PrepareFileList@@YAHPEADKPEBD@Z; PrepareFileList(char *,ulong,char const *)
0x180011f49  mov     dword ptr [rdi+1Ch], 1
0x180011f50  mov     r13d, eax
0x180011f53  test    eax, eax
0x180011f55  jle     loc_180012065
0x180011f5b  mov     rdx, r15
0x180011f5e  mov     rcx, rdi
0x180011f61  mov     rax, r12
0x180011f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f69  mov     ebx, eax
0x180011f6b  test    eax, eax
0x180011f6d  js      loc_180012065
0x180011f73  mov     rbx, [rdi+10h]
0x180011f77  xor     r15d, r15d
0x180011f7a  test    rbx, rbx
0x180011f7d  jz      loc_180012032
0x180011f83  mov     r14, [rsp+98h+lpString1]
0x180011f88  mov     rdx, [rbx]; lpString2
0x180011f8b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180011f8f  mov     [rsp+98h+var_68], rdx
0x180011f94  inc     rbp
0x180011f97  cmp     byte ptr [rdx+rbp], 0
0x180011f9b  jnz     short loc_180011F94
0x180011f9d  xor     ecx, ecx
0x180011f9f  mov     rsi, r14
0x180011fa2  cmp     [r14], cl
0x180011fa5  jz      short loc_180011FED
0x180011fa7  test    ecx, ecx
0x180011fa9  jnz     short loc_180011FED
0x180011fab  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011faf  inc     rax
0x180011fb2  cmp     byte ptr [rsi+rax], 0
0x180011fb6  jnz     short loc_180011FAF
0x180011fb8  cmp     eax, ebp
0x180011fba  jnz     short loc_180011FD0
0x180011fbc  mov     rcx, rsi; lpString1
0x180011fbf  call    cs:__imp_lstrcmpiA
0x180011fc5  test    eax, eax
0x180011fc7  jnz     short loc_180011FCE
0x180011fc9  lea     ecx, [rax+1]
0x180011fcc  jmp     short loc_180011FE3
0x180011fce  xor     ecx, ecx
0x180011fd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011fd4  inc     rax
0x180011fd7  cmp     byte ptr [rsi+rax], 0
0x180011fdb  jnz     short loc_180011FD4
0x180011fdd  inc     rsi
0x180011fe0  add     rsi, rax
0x180011fe3  cmp     byte ptr [rsi], 0
0x180011fe6  mov     rdx, [rsp+98h+var_68]
0x180011feb  jnz     short loc_180011FA7
0x180011fed  mov     rax, [rbx+8]
0x180011ff1  test    ecx, ecx
0x180011ff3  jnz     short loc_18001201B
0x180011ff5  mov     rcx, rbx; struct sFNAME *
0x180011ff8  test    r15, r15
0x180011ffb  jnz     short loc_18001200C
0x180011ffd  mov     [rdi+10h], rax
0x180012001  call    ?FreeFileNode@@YAXPEAUsFNAME@@@Z; FreeFileNode(sFNAME *)
0x180012006  mov     rbx, [rdi+10h]
0x18001200a  jmp     short loc_180012024
0x18001200c  mov     [r15+8], rax
0x180012010  call    ?FreeFileNode@@YAXPEAUsFNAME@@@Z; FreeFileNode(sFNAME *)
0x180012015  mov     rbx, [r15+8]
0x180012019  jmp     short loc_180012024
0x18001201b  mov     r15, rbx
0x18001201e  dec     r13d
0x180012021  mov     rbx, rax
0x180012024  test    rbx, rbx
0x180012027  jnz     loc_180011F88
0x18001202d  mov     r14, [rsp+98h+var_78]
0x180012032  mov     rax, [rdi+10h]
0x180012036  test    rax, rax
0x180012039  jz      short loc_180012077
0x18001203b  test    r13d, r13d
0x18001203e  jnz     short loc_180012077
0x180012040  and     dword ptr [rdi+1Ch], 0FFFFFFFEh
0x180012044  mov     rcx, rdi
0x180012047  mov     rdx, [rsp+98h+var_60]
0x18001204c  mov     [rdi+330h], rax
0x180012053  mov     rax, r12
0x180012056  mov     [rdi+0Ch], r13d
0x18001205a  mov     [rdi+4], r13d
0x18001205e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012063  mov     ebx, eax
0x180012065  mov     ebp, 80004005h
0x18001206a  mov     rcx, [rsp+98h+lpString1]; hMem
0x18001206f  call    cs:__imp_LocalFree
0x180012075  jmp     short loc_18001208A
0x180012077  mov     ebp, 80004005h
0x18001207c  mov     ebx, ebp
0x18001207e  jmp     short loc_18001206A
0x180012080  mov     ebx, 8007000Eh
0x180012085  mov     ebp, 80004005h
0x18001208a  mov     rsi, [rdi+10h]
0x18001208e  jmp     short loc_18001209C
0x180012090  mov     rcx, rsi; struct sFNAME *
0x180012093  mov     rsi, [rsi+8]
0x180012097  call    ?FreeFileNode@@YAXPEAUsFNAME@@@Z; FreeFileNode(sFNAME *)
0x18001209c  test    rsi, rsi
0x18001209f  jnz     short loc_180012090
0x1800120a1  mov     rcx, rdi; hMem
0x1800120a4  mov     [rdi+10h], rsi
0x1800120a8  call    cs:__imp_LocalFree
0x1800120ae  jmp     short loc_1800120BE
0x1800120b0  mov     ebx, 8007000Eh
0x1800120b5  mov     ebp, 80004005h
0x1800120ba  jmp     short loc_1800120BE
0x1800120bc  mov     ebp, ebx
0x1800120be  mov     rcx, r14; hLibModule
0x1800120c1  call    cs:__imp_FreeLibrary
0x1800120c7  cmp     ebx, 1
0x1800120ca  cmovz   ebx, ebp
0x1800120cd  mov     eax, ebx
0x1800120cf  jmp     short loc_1800120D6
0x1800120d1  mov     eax, 80070057h
0x1800120d6  mov     rcx, [rsp+98h+var_40]
0x1800120db  xor     rcx, rsp; StackCookie
0x1800120de  call    __security_check_cookie
0x1800120e3  mov     rbx, [rsp+98h+arg_10]
0x1800120eb  add     rsp, 60h
0x1800120ef  pop     r15
0x1800120f1  pop     r14
0x1800120f3  pop     r13
0x1800120f5  pop     r12
0x1800120f7  pop     rdi
0x1800120f8  pop     rsi
0x1800120f9  pop     rbp
0x1800120fa  retn
```
