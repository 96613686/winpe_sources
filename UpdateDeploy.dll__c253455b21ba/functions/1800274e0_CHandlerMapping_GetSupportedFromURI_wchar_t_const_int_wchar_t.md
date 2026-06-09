# CHandlerMapping::GetSupportedFromURI(wchar_t const *,int *,wchar_t * *)

- ea: `0x1800274e0`
- end: `0x180027942`
- name: `?GetSupportedFromURI@CHandlerMapping@@UEAAJPEB_WPEAHPEAPEA_W@Z`
- size: `1122`
- prototype: `__int64 __fastcall(CHandlerMapping *this, const wchar_t *, int *, wchar_t **)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003180`
- `0x180008b30`
- `0x18000dce4`
- `0x1800110fc`
- `0x18002686c`
- `0x180027080`
- `0x1800274e0`
- `0x180048ba0`
- `0x1800497f8`
- `0x180049ff8`
- `0x180061960`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180027644`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180027644`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800275ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027751`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002778a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800277b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800277e6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800275ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027751`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002778a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800277b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800277e6`

## string_xrefs

- `0x180027529`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\HandlerMapping.cpp`
- `0x1800275d9`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\HandlerMapping.cpp`
- `0x1800276cd`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\HandlerMapping.cpp`
- `0x18002790c`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\HandlerMapping.cpp`
- `0x180027760`: `wuuhdrv.dll`
- `0x18002771d`: `wuuhext.dll`
- `0x1800277c3`: `wuuhosdeployment.dll`
- `0x180027795`: `wuauengcore.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=79
__int64 __fastcall CHandlerMapping::GetSupportedFromURI(
        CHandlerMapping *this,
        const wchar_t *a2,
        int *a3,
        wchar_t **a4)
{
  __int64 v8; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rdi
  const WCHAR *v12; // r8
  __int64 v13; // rdx
  int FileBasePath; // edi
  unsigned __int64 v15; // r9
  void *v16; // rcx
  int v17; // r13d
  wchar_t *v18; // rsi
  int v19; // eax
  wchar_t *v20; // rbx
  __int64 v21; // rdx
  int v22; // edx
  wchar_t *v23; // rax
  wchar_t *UusHandlerSessionName; // rax
  int v25; // eax
  __int64 v26; // rdx
  unsigned int v27; // esi
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  wchar_t *v29; // [rsp+40h] [rbp-C0h] BYREF
  void *lpMem; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a3 )
  {
    v8 = 98;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\HandlerMapping.cpp",
      (const char *)0x80004003LL,
      (int)lpString2);
    return 2147500035LL;
  }
  if ( a2 && *a2 )
  {
    if ( !a4 )
    {
      v8 = 100;
      goto LABEL_3;
    }
    lpMem = 0;
    *a3 = 0;
    *a4 = 0;
    v10 = 0;
    if ( *((_DWORD *)this + 9) )
    {
      while ( 1 )
      {
        v11 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * v10);
        v12 = *(const WCHAR **)v11;
        if ( *(const wchar_t **)v11 == a2 || v12 && CompareStringW(0x7Fu, 1u, v12, -1, a2, -1) == 2 )
          break;
        if ( ++v10 >= *((_DWORD *)this + 9) )
          goto LABEL_13;
      }
      v17 = *(_DWORD *)(v11 + 8);
      v18 = *(wchar_t **)(v11 + 16);
      v19 = *(_DWORD *)(v11 + 32);
      if ( v19 == 2 )
      {
        v20 = 0;
        v29 = 0;
        memset(Filename, 0, 520);
        if ( GetModuleFileNameW(g_hInstance, Filename, 0x104u) >= 0x104 )
        {
          FileBasePath = -2147024774;
          v21 = 135;
          goto LABEL_31;
        }
        FileBasePath = DuplicateString<wchar_t *,wchar_t *>(Filename, &v29);
        v20 = v29;
        if ( FileBasePath < 0 )
        {
          v21 = 136;
          goto LABEL_31;
        }
        FileBasePath = GetFileBasePath(v29, v22);
        if ( FileBasePath < 0 )
        {
          v21 = 137;
          goto LABEL_31;
        }
        if ( lpMem )
        {
          SusFree(lpMem);
          lpMem = 0;
        }
        FileBasePath = CreateCombinedPath(v20, v18, (wchar_t **)&lpMem);
        if ( FileBasePath < 0 )
        {
          v21 = 140;
LABEL_31:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\HandlerMapping.cpp",
            (const char *)(unsigned int)FileBasePath,
            (int)lpString2);
          if ( v20 )
            SusFree(v20);
          goto LABEL_17;
        }
        if ( v20 )
          SusFree(v20);
LABEL_35:
        *a3 = v17;
        v23 = (wchar_t *)lpMem;
        v16 = 0;
        lpMem = 0;
        *a4 = v23;
        FileBasePath = 0;
LABEL_18:
        if ( v16 )
          SusFree(v16);
        return (unsigned int)FileBasePath;
      }
      if ( v19 != 1 )
        goto LABEL_35;
      if ( v18 != L"wuuhext.dll"
        && v18
        && CompareStringW(0x7Fu, 1u, v18, -1, L"wuuhext.dll", -1) != 2
        && v18 != L"wuuhdrv.dll"
        && CompareStringW(0x7Fu, 1u, v18, -1, L"wuuhdrv.dll", -1) != 2
        && v18 != L"wuauengcore.dll"
        && CompareStringW(0x7Fu, 1u, v18, -1, L"wuauengcore.dll", -1) != 2
        && v18 != L"wuuhosdeployment.dll" )
      {
        CompareStringW(0x7Fu, 1u, v18, -1, L"wuuhosdeployment.dll", -1);
      }
      if ( lpMem )
      {
        SusFree(lpMem);
        lpMem = 0;
      }
      UusHandlerSessionName = (wchar_t *)GetUusHandlerSessionName(v18);
      v25 = UndockedModuleLoader::Load_0(UusHandlerSessionName, v18, 0, 0, (__int64)&lpMem);
      FileBasePath = v25;
      if ( v25 < 0 )
      {
        v15 = (unsigned int)v25;
        v13 = 165;
        goto LABEL_16;
      }
      if ( !lpMem )
      {
        FileBasePath = -2147024809;
        v26 = 299;
        v27 = -2147024809;
LABEL_56:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
          (const char *)v27,
          (int)lpString2);
        v13 = 168;
        goto LABEL_15;
      }
      FileBasePath = CheckIfFileExists((const wchar_t *)lpMem);
      v27 = FileBasePath;
      if ( FileBasePath >= 0 )
        goto LABEL_35;
      if ( (unsigned __int16)FileBasePath != 2 && (unsigned __int16)FileBasePath != 3 )
      {
        LODWORD(lpString2) = FileBasePath;
        WUTrace(0, 0, 32, 5, lpString2, L"CheckIfFileExists for %ws");
        v26 = 317;
        goto LABEL_56;
      }
      v13 = 169;
    }
    else
    {
LABEL_13:
      v13 = 128;
    }
    FileBasePath = -2145091574;
LABEL_15:
    v15 = (unsigned int)FileBasePath;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\HandlerMapping.cpp",
      (const char *)v15,
      (int)lpString2);
LABEL_17:
    v16 = lpMem;
    goto LABEL_18;
  }
  FileBasePath = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x63,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\HandlerMapping.cpp",
    (const char *)0x80070057LL,
    (int)lpString2);
  return (unsigned int)FileBasePath;
}

```

## disassembly

```asm
0x1800274e0  push    rbp
0x1800274e2  push    rbx
0x1800274e3  push    rsi
0x1800274e4  push    rdi
0x1800274e5  push    r12
0x1800274e7  push    r13
0x1800274e9  push    r14
0x1800274eb  push    r15
0x1800274ed  lea     rbp, [rsp-178h]
0x1800274f5  sub     rsp, 278h
0x1800274fc  mov     rax, cs:__security_cookie
0x180027503  xor     rax, rsp
0x180027506  mov     [rbp+1B0h+var_50], rax
0x18002750d  mov     r15, r9
0x180027510  mov     r12, r8
0x180027513  mov     rsi, rdx
0x180027516  mov     r14, rcx
0x180027519  xor     edx, edx
0x18002751b  test    r8, r8
0x18002751e  jnz     short loc_180027546
0x180027520  lea     edx, [r8+62h]; void *
0x180027524  mov     ebx, 80004003h
0x180027529  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180027530  mov     r9d, ebx; char *
0x180027533  mov     rcx, [rbp+1B8h]; this
0x18002753a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002753f  mov     eax, ebx
0x180027541  jmp     loc_18002791F
0x180027546  test    rsi, rsi
0x180027549  jz      loc_1800278FD
0x18002754f  cmp     [rsi], dx
0x180027552  jz      loc_1800278FD
0x180027558  test    r15, r15
0x18002755b  jnz     short loc_180027563
0x18002755d  lea     edx, [r15+64h]
0x180027561  jmp     short loc_180027524
0x180027563  mov     [rsp+2B0h+lpMem], rdx
0x180027568  mov     [r8], edx
0x18002756b  mov     [r9], rdx
0x18002756e  mov     ebx, edx
0x180027570  mov     eax, [rcx+24h]
0x180027573  test    eax, eax
0x180027575  jz      short loc_1800275C5
0x180027577  cmp     edx, eax
0x180027579  jnb     loc_1800278EE
0x18002757f  mov     ecx, ebx
0x180027581  mov     rax, [r14+18h]
0x180027585  mov     rdi, [rax+rcx*8]
0x180027589  mov     r8, [rdi]; lpString1
0x18002758c  cmp     r8, rsi
0x18002758f  jz      short loc_1800275FD
0x180027591  test    r8, r8
0x180027594  jz      short loc_1800275BB
0x180027596  mov     [rsp+2B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002759e  mov     [rsp+2B0h+lpString2], rsi; int
0x1800275a3  or      r9d, 0FFFFFFFFh; cchCount1
0x1800275a7  lea     edx, [r9+2]; dwCmpFlags
0x1800275ab  lea     ecx, [rdx+7Eh]; Locale
0x1800275ae  call    cs:__imp_CompareStringW
0x1800275b4  xor     edx, edx
0x1800275b6  cmp     eax, 2
0x1800275b9  jz      short loc_1800275FD
0x1800275bb  inc     ebx
0x1800275bd  mov     eax, [r14+24h]
0x1800275c1  cmp     ebx, eax
0x1800275c3  jb      short loc_18002757F
0x1800275c5  mov     edx, 80h; void *
0x1800275ca  mov     edi, 8024800Ah
0x1800275cf  mov     r9d, edi; char *
0x1800275d2  mov     rcx, [rbp+1B8h]; this
0x1800275d9  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800275e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800275e5  mov     rcx, [rsp+2B0h+lpMem]; lpMem
0x1800275ea  test    rcx, rcx
0x1800275ed  jz      loc_18002791D
0x1800275f3  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800275f8  jmp     loc_18002791D
0x1800275fd  mov     r13d, [rdi+8]
0x180027601  mov     rsi, [rdi+10h]
0x180027605  mov     eax, [rdi+20h]
0x180027608  cmp     eax, 2
0x18002760b  jnz     loc_180027716
0x180027611  mov     rbx, rdx
0x180027614  mov     [rsp+2B0h+var_270], rdx
0x180027619  mov     [rsp+2B0h+Filename], dx
0x18002761e  xor     edx, edx; Val
0x180027620  mov     r8d, 206h; Size
0x180027626  lea     rcx, [rsp+2B0h+var_25E]; void *
0x18002762b  call    memset
0x180027630  mov     edi, 104h
0x180027635  mov     r8d, edi; nSize
0x180027638  lea     rdx, [rsp+2B0h+Filename]; lpFilename
0x18002763d  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180027644  call    cs:__imp_GetModuleFileNameW
0x18002764a  cmp     eax, edi
0x18002764c  jb      short loc_18002765A
0x18002764e  mov     edi, 8007007Ah
0x180027653  mov     edx, 87h
0x180027658  jmp     short loc_1800276C3
0x18002765a  lea     rdx, [rsp+2B0h+var_270]
0x18002765f  lea     rcx, [rsp+2B0h+Filename]
0x180027664  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x180027669  mov     edi, eax
0x18002766b  mov     rbx, [rsp+2B0h+var_270]
0x180027670  test    eax, eax
0x180027672  jns     short loc_18002767B
0x180027674  mov     edx, 88h
0x180027679  jmp     short loc_1800276C3
0x18002767b  mov     rcx, rbx; wchar_t *
0x18002767e  call    ?GetFileBasePath@@YAJPEA_WH@Z; GetFileBasePath(wchar_t *,int)
0x180027683  mov     edi, eax
0x180027685  test    eax, eax
0x180027687  jns     short loc_180027690
0x180027689  mov     edx, 89h
0x18002768e  jmp     short loc_1800276C3
0x180027690  mov     rcx, [rsp+2B0h+lpMem]; lpMem
0x180027695  test    rcx, rcx
0x180027698  jz      short loc_1800276A8
0x18002769a  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002769f  mov     [rsp+2B0h+lpMem], 0
0x1800276a8  lea     r8, [rsp+2B0h+lpMem]; wchar_t **
0x1800276ad  mov     rdx, rsi; wchar_t *
0x1800276b0  mov     rcx, rbx; wchar_t *
0x1800276b3  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x1800276b8  mov     edi, eax
0x1800276ba  test    eax, eax
0x1800276bc  jns     short loc_1800276EF
0x1800276be  mov     edx, 8Ch; void *
0x1800276c3  mov     rcx, [rbp+1B8h]; this
0x1800276ca  mov     r9d, edi; char *
0x1800276cd  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800276d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276d9  test    rbx, rbx
0x1800276dc  jz      loc_1800275E5
0x1800276e2  mov     rcx, rbx; lpMem
0x1800276e5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800276ea  jmp     loc_1800275E5
0x1800276ef  test    rbx, rbx
0x1800276f2  jz      short loc_1800276FC
0x1800276f4  mov     rcx, rbx; lpMem
0x1800276f7  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800276fc  mov     [r12], r13d
0x180027700  mov     rax, [rsp+2B0h+lpMem]
0x180027705  xor     ecx, ecx
0x180027707  mov     [rsp+2B0h+lpMem], rcx
0x18002770c  mov     [r15], rax
0x18002770f  xor     edi, edi
0x180027711  jmp     loc_1800275EA
0x180027716  cmp     eax, 1
0x180027719  jnz     short loc_1800276FC
0x18002771b  mov     ebx, edx
0x18002771d  lea     rax, ?c_szWuuhextDll@@3QB_WB; "wuuhext.dll"
0x180027724  cmp     rsi, rax
0x180027727  jz      loc_1800277F1
0x18002772d  test    rsi, rsi
0x180027730  jz      loc_1800277F6
0x180027736  mov     [rsp+2B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002773e  mov     [rsp+2B0h+lpString2], rax; lpString2
0x180027743  or      r9d, 0FFFFFFFFh; cchCount1
0x180027747  mov     r8, rsi; lpString1
0x18002774a  lea     edx, [r9+2]; dwCmpFlags
0x18002774e  lea     ecx, [rdx+7Eh]; Locale
0x180027751  call    cs:__imp_CompareStringW
0x180027757  cmp     eax, 2
0x18002775a  jz      loc_1800277F1
0x180027760  lea     rax, ?c_szWuuhdrvDll@@3QB_WB; "wuuhdrv.dll"
0x180027767  cmp     rsi, rax
0x18002776a  jz      loc_1800277F1
0x180027770  or      r9d, 0FFFFFFFFh; cchCount1
0x180027774  mov     [rsp+2B0h+cchCount2], r9d; cchCount2
0x180027779  mov     [rsp+2B0h+lpString2], rax; lpString2
0x18002777e  mov     r8, rsi; lpString1
0x180027781  lea     edi, [r9+2]
0x180027785  mov     edx, edi; dwCmpFlags
0x180027787  lea     ecx, [rdi+7Eh]; Locale
0x18002778a  call    cs:__imp_CompareStringW
0x180027790  cmp     eax, 2
0x180027793  jz      short loc_1800277F1
0x180027795  lea     rcx, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x18002779c  cmp     rsi, rcx
0x18002779f  jz      short loc_1800277F1
0x1800277a1  or      eax, 0FFFFFFFFh
0x1800277a4  mov     [rsp+2B0h+cchCount2], eax; cchCount2
0x1800277a8  mov     [rsp+2B0h+lpString2], rcx; lpString2
0x1800277ad  mov     r9d, eax; cchCount1
0x1800277b0  mov     r8, rsi; lpString1
0x1800277b3  mov     edx, edi; dwCmpFlags
0x1800277b5  lea     ecx, [rdi+7Eh]; Locale
0x1800277b8  call    cs:__imp_CompareStringW
0x1800277be  cmp     eax, 2
0x1800277c1  jz      short loc_1800277F1
0x1800277c3  lea     rdx, ?c_szWuuhosdeploymentDll@@3QB_WB; "wuuhosdeployment.dll"
0x1800277ca  cmp     rsi, rdx
0x1800277cd  jz      short loc_1800277F1
0x1800277cf  or      eax, 0FFFFFFFFh
0x1800277d2  mov     [rsp+2B0h+cchCount2], eax; cchCount2
0x1800277d6  mov     [rsp+2B0h+lpString2], rdx; lpString2
0x1800277db  mov     r9d, eax; cchCount1
0x1800277de  mov     r8, rsi; lpString1
0x1800277e1  mov     edx, edi; dwCmpFlags
0x1800277e3  lea     ecx, [rdi+7Eh]; Locale
0x1800277e6  call    cs:__imp_CompareStringW
0x1800277ec  cmp     eax, 2
0x1800277ef  jnz     short loc_1800277F6
0x1800277f1  mov     ebx, 9
0x1800277f6  mov     rcx, [rsp+2B0h+lpMem]; lpMem
0x1800277fb  test    rcx, rcx
0x1800277fe  jz      short loc_18002780E
0x180027800  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180027805  mov     [rsp+2B0h+lpMem], 0
0x18002780e  mov     rcx, rsi; lpString1
0x180027811  call    ?GetUusHandlerSessionName@@YAPEB_WPEB_W@Z; GetUusHandlerSessionName(wchar_t const *)
0x180027816  lea     r9, [r14+28h]
0x18002781a  mov     [rsp+2B0h+var_278], 0
0x180027823  lea     rcx, [rsp+2B0h+lpMem]
0x180027828  mov     [rsp+2B0h+var_280], rcx; __int64
0x18002782d  mov     qword ptr [rsp+2B0h+cchCount2], 0; int
0x180027836  mov     [rsp+2B0h+lpString2], 0; int
0x18002783f  mov     r8d, ebx
0x180027842  mov     rdx, rsi; wchar_t *
0x180027845  mov     rcx, rax; wchar_t *
0x180027848  call    UndockedModuleLoader__Load_0
0x18002784d  mov     edi, eax
0x18002784f  test    eax, eax
0x180027851  jns     short loc_180027860
0x180027853  mov     r9d, eax
0x180027856  mov     edx, 0A5h
0x18002785b  jmp     loc_1800275D2
0x180027860  mov     rbx, [rsp+2B0h+lpMem]
0x180027865  test    rbx, rbx
0x180027868  jnz     short loc_180027878
0x18002786a  mov     edi, 80070057h
0x18002786f  mov     edx, 12Bh
0x180027874  mov     esi, edi
0x180027876  jmp     short loc_1800278C4
0x180027878  mov     rcx, rbx; wchar_t *
0x18002787b  call    ?CheckIfFileExists@@YAJPEB_W@Z; CheckIfFileExists(wchar_t const *)
0x180027880  mov     edi, eax
0x180027882  mov     esi, eax
0x180027884  test    eax, eax
0x180027886  jns     loc_1800276FC
0x18002788c  movzx   eax, di
0x18002788f  cmp     eax, 2
0x180027892  jz      short loc_1800278E4
0x180027894  cmp     eax, 3
0x180027897  jz      short loc_1800278E4
0x180027899  mov     [rsp+2B0h+var_280], rbx
0x18002789e  lea     rax, aCheckiffileexi; "CheckIfFileExists for %ws"
0x1800278a5  mov     qword ptr [rsp+2B0h+cchCount2], rax
0x1800278aa  mov     dword ptr [rsp+2B0h+lpString2], esi; int
0x1800278ae  xor     edx, edx
0x1800278b0  xor     ecx, ecx
0x1800278b2  lea     r9d, [rdx+5]
0x1800278b6  lea     r8d, [rdx+20h]
0x1800278ba  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800278bf  mov     edx, 13Dh; void *
0x1800278c4  lea     r8, aCW1SSrcClientL_29; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800278cb  mov     rcx, [rbp+1B8h]; this
0x1800278d2  mov     r9d, esi; char *
0x1800278d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800278da  mov     edx, 0A8h
0x1800278df  jmp     loc_1800275CF
0x1800278e4  mov     edx, 0A9h
0x1800278e9  jmp     loc_1800275CA
0x1800278ee  mov     edi, 80240007h
0x1800278f3  mov     edx, 72h ; 'r'
0x1800278f8  jmp     loc_1800275CF
0x1800278fd  mov     rcx, [rbp+1B8h]; this
0x180027904  mov     edi, 80070057h
0x180027909  mov     r9d, edi; char *
0x18002790c  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180027913  mov     edx, 63h ; 'c'; void *
0x180027918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002791d  mov     eax, edi
0x18002791f  mov     rcx, [rbp+1B0h+var_50]
0x180027926  xor     rcx, rsp; StackCookie
0x180027929  call    __security_check_cookie
0x18002792e  add     rsp, 278h
0x180027935  pop     r15
0x180027937  pop     r14
0x180027939  pop     r13
0x18002793b  pop     r12
0x18002793d  pop     rdi
0x18002793e  pop     rsi
0x18002793f  pop     rbx
0x180027940  pop     rbp
0x180027941  retn
```
