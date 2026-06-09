# GetApplicationIcon(ushort const *,int,ushort const *,ushort const *)

- ea: `0x1801acbdc`
- end: `0x1801aceeb`
- name: `?GetApplicationIcon@@YAJPEBGH00@Z`
- size: `783`
- prototype: `int(const unsigned __int16 *, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ee574`
- `0x1800eeb40`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180009e6c`
- `0x180009e84`
- `0x1801ac668`
- `0x1801ac698`
- `0x1801acbdc`
- `0x1801ad01c`
- `0x1801ad098`
- `0x1801ad6e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801acd9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801acdd7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801acdeb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801acdff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801ace13`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801acd9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801acdd7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801acdeb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801acdff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801ace13`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801acd7d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1801acd7d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801acd4a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801acd4a`
- `KERNEL32!GetLastError` at `0x1801acca5`
- `KERNEL32!GetLastError` at `0x1801acca5`
- `SHLWAPI!PathFindExtensionW` at `0x1801acd5a`
- `SHLWAPI!PathFindExtensionW` at `0x1801acdb5`
- `SHLWAPI!PathFindExtensionW` at `0x1801acd5a`
- `SHLWAPI!PathFindExtensionW` at `0x1801acdb5`
- `SHLWAPI!PathRemoveBlanksW` at `0x1801acd38`
- `SHLWAPI!PathRemoveBlanksW` at `0x1801acd38`
- `SHLWAPI!PathUnquoteSpacesW` at `0x1801acd2b`
- `SHLWAPI!PathUnquoteSpacesW` at `0x1801acd2b`
- `USER32!DestroyIcon` at `0x1801aceaa`
- `USER32!DestroyIcon` at `0x1801aceaa`
- `SHELL32!SHGetFileInfoW` at `0x1801ace86`
- `SHELL32!SHGetFileInfoW` at `0x1801ace86`

## string_xrefs

- `0x1801acd06`: `onecore\base\appcompat\shared\unmanaged\appdeviceicon\lib\appicon.cpp`
- `0x1801acd91`: `msiexec.exe`

## pseudocode

```c
__int64 __fastcall GetApplicationIcon(
        const unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v7; // rdx
  unsigned int IconFromBinary; // esi
  DWORD v9; // r12d
  __int64 v10; // rax
  WCHAR *v11; // r8
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rdx
  WCHAR *v14; // rcx
  DWORD LastError; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  wchar_t *v18; // rdi
  LPWSTR ExtensionW; // rax
  LPWSTR v20; // rax
  LPWSTR v21; // rbx
  int v22; // r8d
  __int64 v23; // rdx
  SHFILEINFOW psfi; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR sz[264]; // [rsp+320h] [rbp+220h] BYREF

  memset_0(sz, 0, 0x208u);
  if ( __PAIR128__((unsigned __int64)a3, (unsigned __int64)a1) == 0 )
    return (unsigned int)-2147024809;
  v9 = 0;
  if ( a1 )
  {
    v10 = 2147483646;
    v11 = sz;
    v12 = a1;
    v13 = 260;
    do
    {
      if ( !v10 )
        break;
      if ( !*v12 )
        break;
      *v11++ = *v12++;
      --v10;
      --v13;
    }
    while ( v13 );
    v14 = v11 - 1;
    IconFromBinary = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
      v14 = v11;
    *v14 = 0;
    if ( !v13 )
    {
      LastError = GetLastError();
      v16 = CurrentIP_0();
      v17 = ConstructPartialMsgW(0x2000000u, "[%hs] [0x%x] Failed at %d", "GetApplicationIcon", IconFromBinary, 834);
      WdsSetupLogMessageW_0(
        v17,
        0,
        L"D",
        0,
        834,
        L"onecore\\base\\appcompat\\shared\\unmanaged\\appdeviceicon\\lib\\appicon.cpp",
        L"GetApplicationIcon",
        v16,
        LastError,
        0,
        0);
      return IconFromBinary;
    }
    PathUnquoteSpacesW(sz);
    PathRemoveBlanksW(sz);
    v18 = wcsrchr(sz, 0x2Cu);
    ExtensionW = PathFindExtensionW(sz);
    if ( v18 )
    {
      if ( ExtensionW )
      {
        if ( ExtensionW < v18 )
        {
          *v18 = 0;
          if ( v18[1] )
            v9 = _o__wtoi(v18 + 1);
        }
      }
    }
  }
  else if ( a3 )
  {
    return (unsigned int)GetIconFromProduct(a3, v7, a4);
  }
  if ( !(unsigned int)_o__wcsicmp(a1, L"msiexec.exe") && a3 )
    return (unsigned int)GetIconFromProduct(a3, v7, a4);
  v20 = PathFindExtensionW(sz);
  v21 = v20;
  if ( !v20 )
    return (unsigned int)-2147467259;
  if ( !(unsigned int)_o__wcsicmp(v20, L".exe")
    || !(unsigned int)_o__wcsicmp(v21, L".ico")
    || !(unsigned int)_o__wcsicmp(v21, L".dll") )
  {
    IconFromBinary = GetIconFromBinary(sz, v9, v22, a4);
LABEL_29:
    if ( (IconFromBinary & 0x80000000) == 0 )
      return IconFromBinary;
    goto LABEL_30;
  }
  if ( !(unsigned int)_o__wcsicmp(v21, L".msi") )
  {
    IconFromBinary = GetIconFromMsi(sz, v23, 0, a4);
    if ( (IconFromBinary & 0x80000000) != 0 )
      return IconFromBinary;
    goto LABEL_29;
  }
LABEL_30:
  IconFromBinary = -2147467259;
  memset_0(&psfi, 0, sizeof(psfi));
  if ( SHGetFileInfoW(sz, v9, &psfi, 0x2B8u, 0x100u) )
    IconFromBinary = CreatePngGraphic(psfi.hIcon, a4);
  if ( psfi.hIcon )
    DestroyIcon(psfi.hIcon);
  return IconFromBinary;
}

```

## disassembly

```asm
0x1801acbdc  mov     [rsp-8+arg_8], rbx
0x1801acbe1  push    rbp
0x1801acbe2  push    rsi
0x1801acbe3  push    rdi
0x1801acbe4  push    r12
0x1801acbe6  push    r13
0x1801acbe8  push    r14
0x1801acbea  push    r15
0x1801acbec  lea     rbp, [rsp-440h]
0x1801acbf4  sub     rsp, 540h
0x1801acbfb  mov     rax, cs:__security_cookie
0x1801acc02  xor     rax, rsp
0x1801acc05  mov     [rbp+470h+var_40], rax
0x1801acc0c  mov     rbx, r8
0x1801acc0f  mov     r14, rcx
0x1801acc12  mov     r8d, 208h; Size
0x1801acc18  lea     rcx, [rbp+470h+sz]; void *
0x1801acc1f  xor     edx, edx; Val
0x1801acc21  mov     r15, r9
0x1801acc24  call    memset_0
0x1801acc29  xor     r13d, r13d
0x1801acc2c  test    r14, r14
0x1801acc2f  jnz     short loc_1801ACC40
0x1801acc31  test    rbx, rbx
0x1801acc34  jnz     short loc_1801ACC40
0x1801acc36  mov     esi, 80070057h
0x1801acc3b  jmp     loc_1801ACEBF
0x1801acc40  mov     r12d, r13d
0x1801acc43  test    r14, r14
0x1801acc46  jz      loc_1801ACD88
0x1801acc4c  mov     eax, 7FFFFFFEh
0x1801acc51  lea     r8, [rbp+470h+sz]
0x1801acc58  mov     rcx, r14
0x1801acc5b  mov     edx, 104h
0x1801acc60  test    rax, rax
0x1801acc63  jz      short loc_1801ACC84
0x1801acc65  movzx   r9d, word ptr [rcx]
0x1801acc69  test    r9w, r9w
0x1801acc6d  jz      short loc_1801ACC84
0x1801acc6f  mov     [r8], r9w
0x1801acc73  add     rcx, 2
0x1801acc77  add     r8, 2
0x1801acc7b  dec     rax
0x1801acc7e  sub     rdx, 1
0x1801acc82  jnz     short loc_1801ACC60
0x1801acc84  mov     rax, rdx
0x1801acc87  lea     rcx, [r8-2]
0x1801acc8b  neg     rax
0x1801acc8e  sbb     esi, esi
0x1801acc90  not     esi
0x1801acc92  and     esi, 8007007Ah
0x1801acc98  test    rdx, rdx
0x1801acc9b  cmovnz  rcx, r8
0x1801acc9f  mov     [rcx], r13w
0x1801acca3  jnz     short loc_1801ACD24
0x1801acca5  call    cs:__imp_GetLastError
0x1801accab  mov     edi, eax
0x1801accad  call    CurrentIP_0
0x1801accb2  mov     r14d, 342h
0x1801accb8  lea     r8, aGetapplication; "GetApplicationIcon"
0x1801accbf  mov     r9d, esi
0x1801accc2  mov     [rsp+570h+uFlags], r14d
0x1801accc7  lea     rdx, aHs0xXFailedAtD; "[%hs] [0x%x] Failed at %d"
0x1801accce  mov     ecx, 2000000h; unsigned int
0x1801accd3  mov     rbx, rax
0x1801accd6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801accdb  mov     [rsp+570h+var_520], r13d
0x1801acce0  lea     rcx, aGetapplication_0; "GetApplicationIcon"
0x1801acce7  mov     [rsp+570h+var_528], r13
0x1801accec  lea     r8, aD_2; "D"
0x1801accf3  mov     [rsp+570h+var_530], edi
0x1801accf7  xor     r9d, r9d
0x1801accfa  mov     [rsp+570h+var_538], rbx
0x1801accff  xor     edx, edx
0x1801acd01  mov     [rsp+570h+var_540], rcx
0x1801acd06  lea     rcx, aOnecoreBaseApp_94; "onecore\\base\\appcompat\\shared\\unman"...
0x1801acd0d  mov     [rsp+570h+var_548], rcx
0x1801acd12  mov     rcx, rax
0x1801acd15  mov     [rsp+570h+uFlags], r14d
0x1801acd1a  call    WdsSetupLogMessageW_0
0x1801acd1f  jmp     loc_1801ACEBF
0x1801acd24  lea     rcx, [rbp+470h+sz]; lpsz
0x1801acd2b  call    cs:__imp_PathUnquoteSpacesW
0x1801acd31  lea     rcx, [rbp+470h+sz]; pszPath
0x1801acd38  call    cs:__imp_PathRemoveBlanksW
0x1801acd3e  mov     edx, 2Ch ; ','; Ch
0x1801acd43  lea     rcx, [rbp+470h+sz]; Str
0x1801acd4a  call    cs:__imp_wcsrchr
0x1801acd50  lea     rcx, [rbp+470h+sz]; pszPath
0x1801acd57  mov     rdi, rax
0x1801acd5a  call    cs:__imp_PathFindExtensionW
0x1801acd60  test    rdi, rdi
0x1801acd63  jz      short loc_1801ACD91
0x1801acd65  test    rax, rax
0x1801acd68  jz      short loc_1801ACD91
0x1801acd6a  cmp     rax, rdi
0x1801acd6d  jnb     short loc_1801ACD91
0x1801acd6f  lea     rcx, [rdi+2]
0x1801acd73  mov     [rdi], r13w
0x1801acd77  cmp     [rcx], r13w
0x1801acd7b  jz      short loc_1801ACD91
0x1801acd7d  call    cs:__imp__o__wtoi
0x1801acd83  mov     r12d, eax
0x1801acd86  jmp     short loc_1801ACD91
0x1801acd88  test    rbx, rbx
0x1801acd8b  jnz     loc_1801ACEB2
0x1801acd91  lea     rdx, aMsiexecExe; "msiexec.exe"
0x1801acd98  mov     rcx, r14
0x1801acd9b  call    cs:__imp__o__wcsicmp
0x1801acda1  test    eax, eax
0x1801acda3  jnz     short loc_1801ACDAE
0x1801acda5  test    rbx, rbx
0x1801acda8  jnz     loc_1801ACEB2
0x1801acdae  lea     rcx, [rbp+470h+sz]; pszPath
0x1801acdb5  call    cs:__imp_PathFindExtensionW
0x1801acdbb  mov     rbx, rax
0x1801acdbe  test    rax, rax
0x1801acdc1  jnz     short loc_1801ACDCD
0x1801acdc3  mov     esi, 80004005h
0x1801acdc8  jmp     loc_1801ACEBF
0x1801acdcd  lea     rdx, aExe; ".exe"
0x1801acdd4  mov     rcx, rbx
0x1801acdd7  call    cs:__imp__o__wcsicmp
0x1801acddd  test    eax, eax
0x1801acddf  jz      short loc_1801ACE3B
0x1801acde1  lea     rdx, aIco; ".ico"
0x1801acde8  mov     rcx, rbx
0x1801acdeb  call    cs:__imp__o__wcsicmp
0x1801acdf1  test    eax, eax
0x1801acdf3  jz      short loc_1801ACE3B
0x1801acdf5  lea     rdx, aDll; ".dll"
0x1801acdfc  mov     rcx, rbx
0x1801acdff  call    cs:__imp__o__wcsicmp
0x1801ace05  test    eax, eax
0x1801ace07  jz      short loc_1801ACE3B
0x1801ace09  lea     rdx, aMsi; ".msi"
0x1801ace10  mov     rcx, rbx
0x1801ace13  call    cs:__imp__o__wcsicmp
0x1801ace19  test    eax, eax
0x1801ace1b  jnz     short loc_1801ACE53
0x1801ace1d  mov     r9, r15; unsigned __int16 *
0x1801ace20  lea     rcx, [rbp+470h+sz]; szDatabasePath
0x1801ace27  xor     r8d, r8d; unsigned __int16 *
0x1801ace2a  call    ?GetIconFromMsi@@YAJPEBGHPEAG0@Z; GetIconFromMsi(ushort const *,int,ushort *,ushort const *)
0x1801ace2f  mov     esi, eax
0x1801ace31  test    eax, eax
0x1801ace33  js      loc_1801ACEBF
0x1801ace39  jmp     short loc_1801ACE4F
0x1801ace3b  mov     r9, r15; unsigned __int16 *
0x1801ace3e  lea     rcx, [rbp+470h+sz]; unsigned __int16 *
0x1801ace45  mov     edx, r12d; int
0x1801ace48  call    ?GetIconFromBinary@@YAJPEBGHH0@Z; GetIconFromBinary(ushort const *,int,int,ushort const *)
0x1801ace4d  mov     esi, eax
0x1801ace4f  test    esi, esi
0x1801ace51  jns     short loc_1801ACEBF
0x1801ace53  mov     ebx, 2B8h
0x1801ace58  lea     rcx, [rsp+570h+psfi]; void *
0x1801ace5d  mov     r8d, ebx; Size
0x1801ace60  xor     edx, edx; Val
0x1801ace62  mov     esi, 80004005h
0x1801ace67  call    memset_0
0x1801ace6c  mov     r9d, ebx; cbFileInfo
0x1801ace6f  mov     [rsp+570h+uFlags], 100h; uFlags
0x1801ace77  lea     r8, [rsp+570h+psfi]; psfi
0x1801ace7c  mov     edx, r12d; dwFileAttributes
0x1801ace7f  lea     rcx, [rbp+470h+sz]; pszPath
0x1801ace86  call    cs:__imp_SHGetFileInfoW
0x1801ace8c  test    rax, rax
0x1801ace8f  jz      short loc_1801ACEA0
0x1801ace91  mov     rcx, [rsp+570h+psfi.hIcon]; HICON
0x1801ace96  mov     rdx, r15; unsigned __int16 *
0x1801ace99  call    ?CreatePngGraphic@@YAJPEAUHICON__@@PEBG@Z; CreatePngGraphic(HICON__ *,ushort const *)
0x1801ace9e  mov     esi, eax
0x1801acea0  mov     rcx, [rsp+570h+psfi.hIcon]; hIcon
0x1801acea5  test    rcx, rcx
0x1801acea8  jz      short loc_1801ACEBF
0x1801aceaa  call    cs:__imp_DestroyIcon
0x1801aceb0  jmp     short loc_1801ACEBF
0x1801aceb2  mov     r8, r15; unsigned __int16 *
0x1801aceb5  mov     rcx, rbx; szProduct
0x1801aceb8  call    ?GetIconFromProduct@@YAJPEBGH0@Z; GetIconFromProduct(ushort const *,int,ushort const *)
0x1801acebd  mov     esi, eax
0x1801acebf  mov     eax, esi
0x1801acec1  mov     rcx, [rbp+470h+var_40]
0x1801acec8  xor     rcx, rsp; StackCookie
0x1801acecb  call    __security_check_cookie
0x1801aced0  mov     rbx, [rsp+570h+arg_8]
0x1801aced8  add     rsp, 540h
0x1801acedf  pop     r15
0x1801acee1  pop     r14
0x1801acee3  pop     r13
0x1801acee5  pop     r12
0x1801acee7  pop     rdi
0x1801acee8  pop     rsi
0x1801acee9  pop     rbp
0x1801aceea  retn
```
