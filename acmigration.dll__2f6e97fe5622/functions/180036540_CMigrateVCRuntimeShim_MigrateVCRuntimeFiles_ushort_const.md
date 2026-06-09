# CMigrateVCRuntimeShim::MigrateVCRuntimeFiles(ushort const *)

- ea: `0x180036540`
- end: `0x180036869`
- name: `?MigrateVCRuntimeFiles@CMigrateVCRuntimeShim@@QEAAKPEBG@Z`
- size: `809`
- prototype: `unsigned int __fastcall(CMigrateVCRuntimeShim *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180035f00`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a51c`
- `0x180036384`
- `0x180036540`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800365d7`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800365d7`
- `KERNEL32!GetLastError` at `0x1800365e3`
- `KERNEL32!GetLastError` at `0x18003665c`
- `KERNEL32!GetLastError` at `0x1800366ad`
- `KERNEL32!GetLastError` at `0x1800366dc`
- `KERNEL32!GetLastError` at `0x18003670e`
- `KERNEL32!GetLastError` at `0x18003673e`
- `KERNEL32!GetLastError` at `0x180036770`
- `KERNEL32!GetLastError` at `0x1800367a0`
- `KERNEL32!GetLastError` at `0x1800367d2`
- `KERNEL32!GetLastError` at `0x180036801`
- `KERNEL32!GetLastError` at `0x180036830`
- `KERNEL32!GetLastError` at `0x1800365e3`
- `KERNEL32!GetLastError` at `0x18003665c`
- `KERNEL32!GetLastError` at `0x1800366ad`
- `KERNEL32!GetLastError` at `0x1800366dc`
- `KERNEL32!GetLastError` at `0x18003670e`
- `KERNEL32!GetLastError` at `0x18003673e`
- `KERNEL32!GetLastError` at `0x180036770`
- `KERNEL32!GetLastError` at `0x1800367a0`
- `KERNEL32!GetLastError` at `0x1800367d2`
- `KERNEL32!GetLastError` at `0x180036801`
- `KERNEL32!GetLastError` at `0x180036830`

## string_xrefs

- `0x1800366c2`: `\System32`
- `0x180036756`: `\System32`
- `0x180036662`: `[MigrateVCRuntimeShim] Creating System32 backup string failed. [%d]`
- `0x1800366e2`: `[MigrateVCRuntimeShim] Concatenating System32 backup path failed. [%d]`
- `0x180036714`: `[MigrateVCRuntimeShim] Concatenating Syswow64 backup path failed. [%d]`
- `0x180036744`: `[MigrateVCRuntimeShim] Concatenating System32 online path failed. [%d]`
- `0x180036776`: `[MigrateVCRuntimeShim] Concatenating System32 online path failed. [%d]`
- `0x1800367a6`: `[MigrateVCRuntimeShim] Concatenating Syswow64 online path failed. [%d]`
- `0x1800367d8`: `[MigrateVCRuntimeShim] Concatenating Syswow64 online path failed. [%d]`

## pseudocode

```c
__int64 __fastcall CMigrateVCRuntimeShim::MigrateVCRuntimeFiles(
        CMigrateVCRuntimeShim *this,
        const unsigned __int16 *a2)
{
  DWORD LastError; // eax
  const char *v4; // r9
  __int64 v5; // r8
  DWORD v6; // ebx
  __int64 v7; // r8
  wchar_t *v8; // rax
  __int64 v9; // rcx
  const unsigned __int16 *v10; // r9
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  wchar_t *v14; // rax
  wchar_t *v15; // rcx
  CMigrateVCRuntimeShim *v16; // rcx
  CMigrateVCRuntimeShim *v17; // rcx
  DWORD v19; // [rsp+20h] [rbp-E0h]
  WCHAR Dst[264]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v21[264]; // [rsp+240h] [rbp+140h] BYREF
  wchar_t pszDest[264]; // [rsp+450h] [rbp+350h] BYREF
  wchar_t v23[264]; // [rsp+660h] [rbp+560h] BYREF
  wchar_t v24[264]; // [rsp+870h] [rbp+770h] BYREF

  memset_0(Dst, 0, 0x208u);
  memset_0(pszDest, 0, 0x208u);
  memset_0(v24, 0, 0x208u);
  memset_0(v21, 0, 0x208u);
  memset_0(v23, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%", Dst, 0x104u) )
  {
    v7 = 2147483646;
    v8 = pszDest;
    v9 = 2147483646;
    v10 = a2;
    v11 = 260;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v8++ = *v10++;
      --v9;
      --v11;
    }
    while ( v11 );
    v12 = v8 - 1;
    if ( v11 )
      v12 = v8;
    *v12 = 0;
    if ( v11 )
    {
      v13 = 260;
      v14 = v24;
      do
      {
        if ( !v7 )
          break;
        if ( !*a2 )
          break;
        *v14++ = *a2++;
        --v7;
        --v13;
      }
      while ( v13 );
      v15 = v14 - 1;
      if ( v13 )
        v15 = v14;
      *v15 = 0;
      if ( v13 )
      {
        if ( StringCchCatW(pszDest, 0x104u, L"\\System32") )
        {
          LastError = GetLastError();
          v4 = "[MigrateVCRuntimeShim] Concatenating System32 backup path failed. [%d]";
          v5 = 535;
        }
        else if ( StringCchCatW(v24, 0x104u, L"\\SysWOW64") )
        {
          LastError = GetLastError();
          v4 = "[MigrateVCRuntimeShim] Concatenating Syswow64 backup path failed. [%d]";
          v5 = 541;
        }
        else if ( StringCchCatW(v21, 0x104u, Dst) )
        {
          LastError = GetLastError();
          v4 = "[MigrateVCRuntimeShim] Concatenating System32 online path failed. [%d]";
          v5 = 548;
        }
        else if ( StringCchCatW(v21, 0x104u, L"\\System32") )
        {
          LastError = GetLastError();
          v4 = "[MigrateVCRuntimeShim] Concatenating System32 online path failed. [%d]";
          v5 = 554;
        }
        else if ( StringCchCatW(v23, 0x104u, Dst) )
        {
          LastError = GetLastError();
          v4 = "[MigrateVCRuntimeShim] Concatenating Syswow64 online path failed. [%d]";
          v5 = 560;
        }
        else if ( StringCchCatW(v23, 0x104u, L"\\SysWOW64") )
        {
          LastError = GetLastError();
          v4 = "[MigrateVCRuntimeShim] Concatenating Syswow64 online path failed. [%d]";
          v5 = 566;
        }
        else if ( CMigrateVCRuntimeShim::CopyVCRuntimeFiles(v16, pszDest, v21) )
        {
          if ( CMigrateVCRuntimeShim::CopyVCRuntimeFiles(v17, v24, v23) )
            return 0;
          LastError = GetLastError();
          v4 = "[MigrateVCRuntimeShim] migrate files failed. [%d]";
          v5 = 582;
        }
        else
        {
          LastError = GetLastError();
          v4 = "[MigrateVCRuntimeShim] migrate files failed. [%d]";
          v5 = 574;
        }
      }
      else
      {
        LastError = GetLastError();
        v4 = "[MigrateVCRuntimeShim] Creating Syswow64 backup string failed. [%d]";
        v5 = 528;
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = "[MigrateVCRuntimeShim] Creating System32 backup string failed. [%d]";
      v5 = 522;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = "[MigrateVCRuntimeShim] Error expanding SystemRoot. [%d]";
    v5 = 514;
  }
  v19 = LastError;
  v6 = LastError;
  AslLogCallPrintf(1, "CMigrateVCRuntimeShim::MigrateVCRuntimeFiles", v5, v4, v19);
  return v6;
}

```

## disassembly

```asm
0x180036540  push    rbp
0x180036542  push    rbx
0x180036543  push    rsi
0x180036544  push    rdi
0x180036545  push    r14
0x180036547  lea     rbp, [rsp-990h]
0x18003654f  sub     rsp, 0A90h
0x180036556  mov     rax, cs:__security_cookie
0x18003655d  xor     rax, rsp
0x180036560  mov     [rbp+9B0h+var_30], rax
0x180036567  mov     rbx, rdx
0x18003656a  lea     rcx, [rsp+0AB0h+Dst]; void *
0x18003656f  mov     edi, 208h
0x180036574  xor     edx, edx; Val
0x180036576  mov     r8d, edi; Size
0x180036579  call    memset_0
0x18003657e  mov     r8d, edi; Size
0x180036581  lea     rcx, [rbp+9B0h+pszDest]; void *
0x180036588  xor     edx, edx; Val
0x18003658a  call    memset_0
0x18003658f  mov     r8d, edi; Size
0x180036592  lea     rcx, [rbp+9B0h+var_240]; void *
0x180036599  xor     edx, edx; Val
0x18003659b  call    memset_0
0x1800365a0  mov     r8d, edi; Size
0x1800365a3  lea     rcx, [rbp+9B0h+var_870]; void *
0x1800365aa  xor     edx, edx; Val
0x1800365ac  call    memset_0
0x1800365b1  mov     r8d, edi; Size
0x1800365b4  lea     rcx, [rbp+9B0h+var_450]; void *
0x1800365bb  xor     edx, edx; Val
0x1800365bd  call    memset_0
0x1800365c2  mov     r14d, 104h
0x1800365c8  lea     rdx, [rsp+0AB0h+Dst]; lpDst
0x1800365cd  mov     r8d, r14d; nSize
0x1800365d0  lea     rcx, aSystemroot_1; "%SystemRoot%"
0x1800365d7  call    cs:__imp_ExpandEnvironmentStringsW
0x1800365dd  xor     esi, esi
0x1800365df  test    eax, eax
0x1800365e1  jnz     short loc_18003660E
0x1800365e3  call    cs:__imp_GetLastError
0x1800365e9  lea     r9, aMigratevcrunti_10; "[MigrateVCRuntimeShim] Error expanding "...
0x1800365f0  lea     r8d, [rdi-6]
0x1800365f4  lea     ecx, [rsi+1]
0x1800365f7  lea     rdx, aCmigratevcrunt; "CMigrateVCRuntimeShim::MigrateVCRuntime"...
0x1800365fe  mov     [rsp+0AB0h+var_A90], eax
0x180036602  mov     ebx, eax
0x180036604  call    AslLogCallPrintf
0x180036609  jmp     loc_18003684A
0x18003660e  mov     r8d, 7FFFFFFEh
0x180036614  lea     rax, [rbp+9B0h+pszDest]
0x18003661b  mov     ecx, r8d
0x18003661e  mov     r9, rbx
0x180036621  mov     rdx, r14
0x180036624  mov     edi, 1
0x180036629  test    rcx, rcx
0x18003662c  jz      short loc_18003664C
0x18003662e  movzx   r10d, word ptr [r9]
0x180036632  test    r10w, r10w
0x180036636  jz      short loc_18003664C
0x180036638  mov     [rax], r10w
0x18003663c  add     r9, 2
0x180036640  add     rax, 2
0x180036644  sub     rcx, rdi
0x180036647  sub     rdx, rdi
0x18003664a  jnz     short loc_180036629
0x18003664c  test    rdx, rdx
0x18003664f  lea     rcx, [rax-2]
0x180036653  cmovnz  rcx, rax
0x180036657  mov     [rcx], si
0x18003665a  jnz     short loc_180036673
0x18003665c  call    cs:__imp_GetLastError
0x180036662  lea     r9, aMigratevcrunti_6; "[MigrateVCRuntimeShim] Creating System3"...
0x180036669  mov     r8d, 20Ah
0x18003666f  mov     ecx, edi
0x180036671  jmp     short loc_1800365F7
0x180036673  mov     rdx, r14
0x180036676  lea     rax, [rbp+9B0h+var_240]
0x18003667d  test    r8, r8
0x180036680  jz      short loc_18003669D
0x180036682  movzx   ecx, word ptr [rbx]
0x180036685  test    cx, cx
0x180036688  jz      short loc_18003669D
0x18003668a  mov     [rax], cx
0x18003668d  add     rbx, 2
0x180036691  add     rax, 2
0x180036695  sub     r8, rdi
0x180036698  sub     rdx, rdi
0x18003669b  jnz     short loc_18003667D
0x18003669d  test    rdx, rdx
0x1800366a0  lea     rcx, [rax-2]
0x1800366a4  cmovnz  rcx, rax
0x1800366a8  mov     [rcx], si
0x1800366ab  jnz     short loc_1800366C2
0x1800366ad  call    cs:__imp_GetLastError
0x1800366b3  lea     r9, aMigratevcrunti_12; "[MigrateVCRuntimeShim] Creating Syswow6"...
0x1800366ba  mov     r8d, 210h
0x1800366c0  jmp     short loc_18003666F
0x1800366c2  lea     r8, aSystem32_1; "\\System32"
0x1800366c9  mov     rdx, r14; cchDest
0x1800366cc  lea     rcx, [rbp+9B0h+pszDest]; pszDest
0x1800366d3  call    StringCchCatW
0x1800366d8  test    eax, eax
0x1800366da  jz      short loc_1800366F4
0x1800366dc  call    cs:__imp_GetLastError
0x1800366e2  lea     r9, aMigratevcrunti; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x1800366e9  mov     r8d, 217h
0x1800366ef  jmp     loc_18003666F
0x1800366f4  lea     r8, aSyswow64; "\\SysWOW64"
0x1800366fb  mov     rdx, r14; cchDest
0x1800366fe  lea     rcx, [rbp+9B0h+var_240]; pszDest
0x180036705  call    StringCchCatW
0x18003670a  test    eax, eax
0x18003670c  jz      short loc_180036726
0x18003670e  call    cs:__imp_GetLastError
0x180036714  lea     r9, aMigratevcrunti_4; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x18003671b  mov     r8d, 21Dh
0x180036721  jmp     loc_18003666F
0x180036726  lea     r8, [rsp+0AB0h+Dst]; pszSrc
0x18003672b  mov     rdx, r14; cchDest
0x18003672e  lea     rcx, [rbp+9B0h+var_870]; pszDest
0x180036735  call    StringCchCatW
0x18003673a  test    eax, eax
0x18003673c  jz      short loc_180036756
0x18003673e  call    cs:__imp_GetLastError
0x180036744  lea     r9, aMigratevcrunti_11; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x18003674b  mov     r8d, 224h
0x180036751  jmp     loc_18003666F
0x180036756  lea     r8, aSystem32_1; "\\System32"
0x18003675d  mov     rdx, r14; cchDest
0x180036760  lea     rcx, [rbp+9B0h+var_870]; pszDest
0x180036767  call    StringCchCatW
0x18003676c  test    eax, eax
0x18003676e  jz      short loc_180036788
0x180036770  call    cs:__imp_GetLastError
0x180036776  lea     r9, aMigratevcrunti_11; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x18003677d  mov     r8d, 22Ah
0x180036783  jmp     loc_18003666F
0x180036788  lea     r8, [rsp+0AB0h+Dst]; pszSrc
0x18003678d  mov     rdx, r14; cchDest
0x180036790  lea     rcx, [rbp+9B0h+var_450]; pszDest
0x180036797  call    StringCchCatW
0x18003679c  test    eax, eax
0x18003679e  jz      short loc_1800367B8
0x1800367a0  call    cs:__imp_GetLastError
0x1800367a6  lea     r9, aMigratevcrunti_2; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x1800367ad  mov     r8d, 230h
0x1800367b3  jmp     loc_18003666F
0x1800367b8  lea     r8, aSyswow64; "\\SysWOW64"
0x1800367bf  mov     rdx, r14; cchDest
0x1800367c2  lea     rcx, [rbp+9B0h+var_450]; pszDest
0x1800367c9  call    StringCchCatW
0x1800367ce  test    eax, eax
0x1800367d0  jz      short loc_1800367EA
0x1800367d2  call    cs:__imp_GetLastError
0x1800367d8  lea     r9, aMigratevcrunti_2; "[MigrateVCRuntimeShim] Concatenating Sy"...
0x1800367df  mov     r8d, 236h
0x1800367e5  jmp     loc_18003666F
0x1800367ea  lea     r8, [rbp+9B0h+var_870]; unsigned __int16 *
0x1800367f1  lea     rdx, [rbp+9B0h+pszDest]; unsigned __int16 *
0x1800367f8  call    ?CopyVCRuntimeFiles@CMigrateVCRuntimeShim@@AEAAHPEBG0@Z; CMigrateVCRuntimeShim::CopyVCRuntimeFiles(ushort const *,ushort const *)
0x1800367fd  test    eax, eax
0x1800367ff  jnz     short loc_180036819
0x180036801  call    cs:__imp_GetLastError
0x180036807  lea     r9, aMigratevcrunti_14; "[MigrateVCRuntimeShim] migrate files fa"...
0x18003680e  mov     r8d, 23Eh
0x180036814  jmp     loc_18003666F
0x180036819  lea     r8, [rbp+9B0h+var_450]; unsigned __int16 *
0x180036820  lea     rdx, [rbp+9B0h+var_240]; unsigned __int16 *
0x180036827  call    ?CopyVCRuntimeFiles@CMigrateVCRuntimeShim@@AEAAHPEBG0@Z; CMigrateVCRuntimeShim::CopyVCRuntimeFiles(ushort const *,ushort const *)
0x18003682c  test    eax, eax
0x18003682e  jnz     short loc_180036848
0x180036830  call    cs:__imp_GetLastError
0x180036836  lea     r9, aMigratevcrunti_14; "[MigrateVCRuntimeShim] migrate files fa"...
0x18003683d  mov     r8d, 246h
0x180036843  jmp     loc_18003666F
0x180036848  mov     ebx, esi
0x18003684a  mov     eax, ebx
0x18003684c  mov     rcx, [rbp+9B0h+var_30]
0x180036853  xor     rcx, rsp; StackCookie
0x180036856  call    __security_check_cookie
0x18003685b  add     rsp, 0A90h
0x180036862  pop     r14
0x180036864  pop     rdi
0x180036865  pop     rsi
0x180036866  pop     rbx
0x180036867  pop     rbp
0x180036868  retn
```
