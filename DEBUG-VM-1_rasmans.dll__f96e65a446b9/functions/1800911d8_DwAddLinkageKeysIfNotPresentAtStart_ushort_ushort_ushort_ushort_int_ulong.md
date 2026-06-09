# DwAddLinkageKeysIfNotPresentAtStart(ushort *,ushort *,ushort *,ushort *,int *,ulong)

- ea: `0x1800911d8`
- end: `0x1800914c5`
- name: `?DwAddLinkageKeysIfNotPresentAtStart@@YAKPEAG000PEAHK@Z`
- size: `749`
- prototype: `unsigned int __fastcall(STRSAFE_LPCWSTR pszSrc, LPCWSTR lpSubKey, LPCWSTR lpValueName, STRSAFE_LPCWSTR, int *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800916c8`
- `0x180091b5c`

## callees

- `0x18000e4f0`
- `0x180053974`
- `0x1800911d8`
- `0x180092ed8`
- `0x180093380`
- `0x1800ad750`
- `0x1800e71ee`
- `0x1800e7206`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009141b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009141b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091269`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091269`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091433`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091433`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180091408`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180091408`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180091344`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180091344`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091413`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091441`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091413`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180091441`

## string_xrefs

- `0x180091468`: `DwAddLinkageKeysAtStart: Function failed with error %d`
- `0x18009144e`: `DwAddLinkageKeysAtStart: Function failed with error %d`

## pseudocode

```c
__int64 __fastcall DwAddLinkageKeysIfNotPresentAtStart(
        STRSAFE_LPCWSTR pszSrc,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        STRSAFE_LPCWSTR a4,
        int *a5,
        unsigned int a6)
{
  void *v9; // r14
  unsigned int v11; // edi
  DWORD LastError; // ebx
  unsigned int v13; // r8d
  unsigned int ValueWithAllocW; // eax
  __int64 v15; // rdi
  int v16; // r15d
  _WORD *v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // r10
  char *v21; // rdx
  STRSAFE_LPCWSTR v22; // rcx
  signed __int64 v23; // rdx
  int v24; // r8d
  int v25; // r9d
  wchar_t *v26; // rax
  wchar_t *v27; // rsi
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  wchar_t *v32; // rax
  bool v33; // zf
  _WORD *v34; // rcx
  SIZE_T uBytes; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  void *Src; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpValueNamea; // [rsp+58h] [rbp-A8h]
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v41[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  lpValueNamea = lpValueName;
  Src = 0;
  hKey = 0;
  uBytes = 0;
  v40 = 0;
  v9 = 0;
  memset_0(v41, 0, sizeof(v41));
  *a5 = 0;
  v11 = a6;
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Bu, &hKey);
  if ( !LastError )
  {
    ValueWithAllocW = RegQueryValueWithAllocW(
                        hKey,
                        lpValueName,
                        v13,
                        (unsigned __int8 **)&Src,
                        (unsigned int *)&uBytes,
                        (unsigned int *)&uBytes + 1,
                        a6);
    v9 = Src;
    LastError = ValueWithAllocW;
    if ( !ValueWithAllocW )
    {
      v15 = -1;
      v16 = 2;
      v17 = Src;
      if ( *(_WORD *)Src )
      {
        while ( 1 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v17[v18] );
          v19 = -1;
          do
            ++v19;
          while ( a4[v19] );
          v20 = (unsigned int)v18;
          if ( (unsigned int)v18 >= v19 )
          {
            v21 = (char *)&v17[v19];
            if ( *(_WORD *)v21 == 123 )
            {
              v22 = pszSrc;
              v23 = v21 - (char *)pszSrc;
              do
              {
                v24 = *(STRSAFE_LPCWSTR)((char *)v22 + v23);
                v25 = *v22 - v24;
                if ( v25 )
                  break;
                ++v22;
              }
              while ( v24 );
              if ( !v25 )
                break;
            }
          }
          v17 += v20 + 1;
          if ( !*v17 )
            goto LABEL_17;
        }
        *a5 = 1;
      }
LABEL_17:
      if ( !*a5 )
      {
        v26 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)uBytes);
        v27 = v26;
        if ( v26 )
        {
          v28 = -1;
          do
            ++v28;
          while ( a4[v28] );
          StringCchCopyW(v26, v28 + 1, a4);
          v29 = -1;
          do
            ++v29;
          while ( pszSrc[v29] );
          v30 = -1;
          do
            ++v30;
          while ( a4[v30] );
          StringCchCatW(v27, v30 + v29 + 1, pszSrc);
          v31 = -1;
          do
            ++v31;
          while ( pszSrc[v31] );
          do
            ++v15;
          while ( a4[v15] );
          memcpy_0(&v27[v15 + 1 + v31], v9, HIDWORD(uBytes));
          v32 = v27;
          while ( 1 )
          {
            v33 = *v32 == 0;
            v34 = ++v32;
            if ( v33 && !*v34 )
              break;
            ++v16;
          }
          LastError = RegSetValueExW(hKey, lpValueNamea, 0, 7u, (const BYTE *)v27, 2 * v16);
          LocalFree(v27);
        }
        else
        {
          LastError = GetLastError();
        }
      }
      v11 = a6;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    LocalFree(v9);
  if ( LastError )
  {
    TraceIt(v11, "DwAddLinkageKeysAtStart: Function failed with error %d", LastError);
    if ( qword_18010ED20 )
    {
      LOWORD(v40) = 0;
      FormatRRASErrorString(&v40, L"DwAddLinkageKeysAtStart: Function failed with error %d", LastError);
      ((void (__fastcall *)(__int64, __int64, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, qword_18010ED20, &v40);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800911d8  push    rbp
0x1800911da  push    rbx
0x1800911db  push    rsi
0x1800911dc  push    rdi
0x1800911dd  push    r12
0x1800911df  push    r13
0x1800911e1  push    r14
0x1800911e3  push    r15
0x1800911e5  lea     rbp, [rsp-778h]
0x1800911ed  sub     rsp, 878h
0x1800911f4  mov     rax, cs:__security_cookie
0x1800911fb  xor     rax, rsp
0x1800911fe  mov     [rbp+7B0h+var_50], rax
0x180091205  mov     rsi, [rbp+7B0h+arg_20]
0x18009120c  xor     edi, edi
0x18009120e  mov     r15, r8
0x180091211  mov     [rsp+8B0h+lpValueName], r8
0x180091216  mov     rbx, rdx
0x180091219  mov     [rsp+8B0h+Src], rdi
0x18009121e  mov     r13, rcx
0x180091221  mov     [rsp+8B0h+hKey], rdi
0x180091226  xor     edx, edx; Val
0x180091228  mov     dword ptr [rsp+8B0h+uBytes+4], edi
0x18009122c  mov     r8d, 7FCh; Size
0x180091232  mov     dword ptr [rsp+8B0h+uBytes], edi
0x180091236  lea     rcx, [rsp+8B0h+var_84C]; void *
0x18009123b  mov     [rsp+8B0h+var_850], edi
0x18009123f  mov     r14d, edi
0x180091242  mov     r12, r9
0x180091245  call    memset_0
0x18009124a  lea     rax, [rsp+8B0h+hKey]
0x18009124f  mov     [rsi], edi
0x180091251  mov     r9d, 2001Bh; samDesired
0x180091257  mov     [rsp+8B0h+phkResult], rax; phkResult
0x18009125c  xor     r8d, r8d; ulOptions
0x18009125f  mov     rdx, rbx; lpSubKey
0x180091262  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180091269  call    cs:__imp_RegOpenKeyExW
0x18009126f  mov     edi, [rbp+7B0h+arg_28]
0x180091275  mov     ebx, eax
0x180091277  test    eax, eax
0x180091279  jnz     loc_180091429
0x18009127f  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180091284  lea     rax, [rsp+8B0h+uBytes+4]
0x180091289  mov     [rsp+8B0h+var_880], edi; unsigned int
0x18009128d  lea     r9, [rsp+8B0h+Src]; unsigned __int8 **
0x180091292  mov     qword ptr [rsp+8B0h+cbData], rax; unsigned int *
0x180091297  mov     rdx, r15; lpValueName
0x18009129a  lea     rax, [rsp+8B0h+uBytes]
0x18009129f  mov     [rsp+8B0h+phkResult], rax; unsigned int *
0x1800912a4  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x1800912a9  mov     r14, [rsp+8B0h+Src]
0x1800912ae  xor     r11d, r11d
0x1800912b1  mov     ebx, eax
0x1800912b3  test    eax, eax
0x1800912b5  jnz     loc_180091429
0x1800912bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800912bf  lea     r15d, [rbx+2]
0x1800912c3  mov     rax, r14
0x1800912c6  cmp     [r14], r11w
0x1800912ca  jz      short loc_180091332
0x1800912cc  mov     rdx, rdi
0x1800912cf  inc     rdx
0x1800912d2  cmp     [rax+rdx*2], r11w
0x1800912d7  jnz     short loc_1800912CF
0x1800912d9  mov     rcx, rdi
0x1800912dc  inc     rcx
0x1800912df  cmp     [r12+rcx*2], r11w
0x1800912e4  jnz     short loc_1800912DC
0x1800912e6  mov     r10d, edx
0x1800912e9  cmp     r10, rcx
0x1800912ec  jb      short loc_18009131D
0x1800912ee  lea     rdx, [rax+rcx*2]
0x1800912f2  mov     ecx, 7Bh ; '{'
0x1800912f7  cmp     cx, [rdx]
0x1800912fa  jnz     short loc_18009131D
0x1800912fc  mov     rcx, r13
0x1800912ff  sub     rdx, r13
0x180091302  movzx   r9d, word ptr [rcx]
0x180091306  movzx   r8d, word ptr [rcx+rdx]
0x18009130b  sub     r9d, r8d
0x18009130e  jnz     short loc_180091318
0x180091310  add     rcx, r15
0x180091313  test    r8d, r8d
0x180091316  jnz     short loc_180091302
0x180091318  test    r9d, r9d
0x18009131b  jz      short loc_18009132C
0x18009131d  lea     rax, [rax+r10*2]
0x180091321  add     rax, r15
0x180091324  cmp     [rax], r11w
0x180091328  jnz     short loc_1800912CC
0x18009132a  jmp     short loc_180091332
0x18009132c  mov     dword ptr [rsi], 1
0x180091332  cmp     [rsi], r11d
0x180091335  jnz     loc_180091423
0x18009133b  mov     edx, dword ptr [rsp+8B0h+uBytes]; uBytes
0x18009133f  mov     ecx, 40h ; '@'; uFlags
0x180091344  call    cs:__imp_LocalAlloc
0x18009134a  xor     ebx, ebx
0x18009134c  mov     rsi, rax
0x18009134f  test    rax, rax
0x180091352  jz      loc_18009141B
0x180091358  mov     rdx, rdi
0x18009135b  inc     rdx
0x18009135e  cmp     [r12+rdx*2], bx
0x180091363  jnz     short loc_18009135B
0x180091365  inc     rdx; cchDest
0x180091368  mov     r8, r12; pszSrc
0x18009136b  mov     rcx, rsi; pszDest
0x18009136e  call    StringCchCopyW
0x180091373  mov     rcx, rdi
0x180091376  inc     rcx
0x180091379  cmp     [r13+rcx*2+0], bx
0x18009137f  jnz     short loc_180091376
0x180091381  mov     rax, rdi
0x180091384  inc     rax
0x180091387  cmp     [r12+rax*2], bx
0x18009138c  jnz     short loc_180091384
0x18009138e  lea     rdx, [rcx+1]
0x180091392  mov     r8, r13; pszSrc
0x180091395  add     rdx, rax; cchDest
0x180091398  mov     rcx, rsi; pszDest
0x18009139b  call    StringCchCatW
0x1800913a0  mov     rax, rdi
0x1800913a3  inc     rax
0x1800913a6  cmp     [r13+rax*2+0], bx
0x1800913ac  jnz     short loc_1800913A3
0x1800913ae  inc     rdi
0x1800913b1  cmp     [r12+rdi*2], bx
0x1800913b6  jnz     short loc_1800913AE
0x1800913b8  mov     r8d, dword ptr [rsp+8B0h+uBytes+4]; Size
0x1800913bd  inc     rax
0x1800913c0  add     rax, rdi
0x1800913c3  mov     rdx, r14; Src
0x1800913c6  lea     rcx, [rsi+rax*2]; void *
0x1800913ca  call    memcpy_0
0x1800913cf  mov     rax, rsi
0x1800913d2  cmp     [rax], bx
0x1800913d5  lea     rcx, [rax+2]
0x1800913d9  mov     rax, rcx
0x1800913dc  jnz     short loc_1800913E3
0x1800913de  cmp     [rcx], bx
0x1800913e1  jz      short loc_1800913E8
0x1800913e3  inc     r15d
0x1800913e6  jmp     short loc_1800913D2
0x1800913e8  mov     rdx, [rsp+8B0h+lpValueName]; lpValueName
0x1800913ed  lea     eax, [r15+r15]
0x1800913f1  mov     rcx, [rsp+8B0h+hKey]; hKey
0x1800913f6  mov     r9d, 7; dwType
0x1800913fc  mov     [rsp+8B0h+cbData], eax; cbData
0x180091400  xor     r8d, r8d; Reserved
0x180091403  mov     [rsp+8B0h+phkResult], rsi; lpData
0x180091408  call    cs:__imp_RegSetValueExW
0x18009140e  mov     rcx, rsi; hMem
0x180091411  mov     ebx, eax
0x180091413  call    cs:__imp_LocalFree
0x180091419  jmp     short loc_180091423
0x18009141b  call    cs:__imp_GetLastError
0x180091421  mov     ebx, eax
0x180091423  mov     edi, [rbp+7B0h+arg_28]
0x180091429  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18009142e  test    rcx, rcx
0x180091431  jz      short loc_180091439
0x180091433  call    cs:__imp_RegCloseKey
0x180091439  test    r14, r14
0x18009143c  jz      short loc_180091447
0x18009143e  mov     rcx, r14; hMem
0x180091441  call    cs:__imp_LocalFree
0x180091447  test    ebx, ebx
0x180091449  jz      short loc_1800914A0
0x18009144b  mov     r8d, ebx
0x18009144e  lea     rdx, aDwaddlinkageke; "DwAddLinkageKeysAtStart: Function faile"...
0x180091455  mov     ecx, edi; unsigned int
0x180091457  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18009145c  cmp     cs:qword_18010ED20, 0
0x180091464  jz      short loc_1800914A0
0x180091466  xor     eax, eax
0x180091468  lea     rdx, aDwaddlinkageke_0; "DwAddLinkageKeysAtStart: Function faile"...
0x18009146f  mov     r8d, ebx
0x180091472  mov     word ptr [rsp+8B0h+var_850], ax
0x180091477  lea     rcx, [rsp+8B0h+var_850]
0x18009147c  call    FormatRRASErrorString
0x180091481  mov     rdx, cs:qword_18010ED20
0x180091488  lea     r8, [rsp+8B0h+var_850]
0x18009148d  mov     rcx, cs:gRegHelpEtwContext
0x180091494  mov     rax, cs:gRegHelpTemplateFunc
0x18009149b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800914a0  mov     eax, ebx
0x1800914a2  mov     rcx, [rbp+7B0h+var_50]
0x1800914a9  xor     rcx, rsp; StackCookie
0x1800914ac  call    __security_check_cookie
0x1800914b1  add     rsp, 878h
0x1800914b8  pop     r15
0x1800914ba  pop     r14
0x1800914bc  pop     r13
0x1800914be  pop     r12
0x1800914c0  pop     rdi
0x1800914c1  pop     rsi
0x1800914c2  pop     rbx
0x1800914c3  pop     rbp
0x1800914c4  retn
```
