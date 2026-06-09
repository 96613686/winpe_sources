# CUpdateDeploymentJob::get_RequiresRestorePoint(int *)

- ea: `0x18002c37c`
- end: `0x18002c59f`
- name: `?get_RequiresRestorePoint@CUpdateDeploymentJob@@AEAAJPEAH@Z`
- size: `547`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002c300`

## callees

- `0x180003180`
- `0x18002c37c`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c535`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c535`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c54a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c54a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c56e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c48e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c4b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c48e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c4b6`

## string_xrefs

- `0x18002c3bc`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002c44a`: `http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/SingleStageAppX`
- `0x18002c3fe`: `http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/AppXPackage`
- `0x18002c526`: `kernel32.dll`
- `0x18002c540`: `OOBEComplete`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::get_RequiresRestorePoint(CUpdateDeploymentJob *this, int *a2)
{
  int *v2; // r13
  CUpdateDeploymentJob *v3; // rsi
  int v5; // edi
  __int64 v6; // r14
  char v7; // r12
  char v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r15
  __int64 v12; // rax
  __int64 v13; // rbp
  __int64 v14; // rdx
  const WCHAR *v15; // rbx
  bool v16; // al
  int v17; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  int lpString2; // [rsp+20h] [rbp-68h]
  char v21; // [rsp+30h] [rbp-58h]
  CUpdateDeploymentJob *v23; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v2 = a2;
  v23 = this;
  v3 = this;
  if ( a2 )
  {
    v5 = 1;
    v6 = 0;
    v7 = 1;
    v8 = 1;
    if ( !*((_DWORD *)this + 172) )
      goto LABEL_21;
    v9 = *(_QWORD *)GUID_e0789628_ce08_4437_be74_2495b842f43b.Data4;
    v10 = *(_QWORD *)&GUID_e0789628_ce08_4437_be74_2495b842f43b.Data1;
    do
    {
      v11 = *(_QWORD *)(*((_QWORD *)v3 + 87) + 8 * v6);
      v12 = v10 - *(_QWORD *)(v11 + 504);
      if ( v10 == *(_QWORD *)(v11 + 504) )
        v12 = v9 - *(_QWORD *)(v11 + 512);
      v13 = 0;
      v8 &= v12 == 0;
      v21 = v8;
      if ( *(_DWORD *)(v11 + 544) )
      {
        do
        {
          v14 = *(_QWORD *)(*(_QWORD *)(v11 + 552) + 8 * v13);
          v15 = *(const WCHAR **)(v14 + 80);
          v16 = *(_DWORD *)(v14 + 344)
             || v15 == L"http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/AppXPackage"
             || v15
             && (CompareStringW(
                   0x7Fu,
                   1u,
                   v15,
                   -1,
                   L"http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/AppXPackage",
                   -1) == 2
              || v15 == L"http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/SingleStageAppX"
              || CompareStringW(
                   0x7Fu,
                   1u,
                   v15,
                   -1,
                   L"http://schemas.microsoft.com/msus/2002/12/UpdateHandlers/SingleStageAppX",
                   -1) == 2);
          v7 &= v16;
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (unsigned int)v13 < *(_DWORD *)(v11 + 544) );
        v9 = *(_QWORD *)GUID_e0789628_ce08_4437_be74_2495b842f43b.Data4;
        v10 = *(_QWORD *)&GUID_e0789628_ce08_4437_be74_2495b842f43b.Data1;
        v3 = v23;
        v8 = v21;
      }
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < *((_DWORD *)v3 + 172) );
    v2 = a2;
    if ( v7 || v8 )
LABEL_21:
      v5 = 0;
    v17 = 0;
    if ( (*((_BYTE *)v3 + 792) & 4) == 0 )
      v17 = v5;
    if ( v17 )
    {
      LODWORD(v23) = 0;
      ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
      if ( ModuleHandleW
        && (ProcAddress = GetProcAddress(ModuleHandleW, "OOBEComplete")) != 0
        && ((unsigned int (__fastcall *)(CUpdateDeploymentJob **))ProcAddress)(&v23) )
      {
        if ( !(_DWORD)v23 )
          v17 = 0;
      }
      else
      {
        GetLastError();
      }
    }
    *v2 = v17;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x876,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80004003LL,
      lpString2);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18002c37c  mov     [rsp+arg_10], rbx
0x18002c381  push    rbp
0x18002c382  push    rsi
0x18002c383  push    rdi
0x18002c384  push    r12
0x18002c386  push    r13
0x18002c388  push    r14
0x18002c38a  push    r15
0x18002c38c  sub     rsp, 50h
0x18002c390  mov     rax, cs:__security_cookie
0x18002c397  xor     rax, rsp
0x18002c39a  mov     [rsp+88h+var_40], rax
0x18002c39f  mov     [rsp+88h+var_50], rdx
0x18002c3a4  mov     r13, rdx
0x18002c3a7  mov     [rsp+88h+var_48], rcx
0x18002c3ac  mov     rsi, rcx
0x18002c3af  test    rdx, rdx
0x18002c3b2  jnz     short loc_18002C3DC
0x18002c3b4  mov     rcx, [rsp+88h]; this
0x18002c3bc  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002c3c3  mov     ebx, 80004003h
0x18002c3c8  mov     edx, 876h; void *
0x18002c3cd  mov     r9d, ebx; char *
0x18002c3d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3d5  mov     eax, ebx
0x18002c3d7  jmp     loc_18002C57A
0x18002c3dc  mov     edi, 1
0x18002c3e1  xor     r14d, r14d
0x18002c3e4  mov     r12b, dil
0x18002c3e7  mov     r9b, dil
0x18002c3ea  cmp     [rcx+2B0h], r14d
0x18002c3f1  jbe     loc_18002C511
0x18002c3f7  mov     rdx, qword ptr cs:_GUID_e0789628_ce08_4437_be74_2495b842f43b.Data4
0x18002c3fe  lea     r13, aHttpSchemasMic_1; "http://schemas.microsoft.com/msus/2002/"...
0x18002c405  mov     r8, qword ptr cs:_GUID_e0789628_ce08_4437_be74_2495b842f43b.Data1
0x18002c40c  mov     rax, [rsi+2B8h]
0x18002c413  mov     r15, [rax+r14*8]
0x18002c417  mov     rax, r8
0x18002c41a  sub     rax, [r15+1F8h]
0x18002c421  jnz     short loc_18002C42D
0x18002c423  mov     rax, rdx
0x18002c426  sub     rax, [r15+200h]
0x18002c42d  test    rax, rax
0x18002c430  setz    al
0x18002c433  xor     ebp, ebp
0x18002c435  and     r9b, al
0x18002c438  mov     [rsp+88h+var_58], r9b
0x18002c43d  cmp     [r15+220h], ebp
0x18002c444  jbe     loc_18002C4F2
0x18002c44a  lea     rsi, aHttpSchemasMic_0; "http://schemas.microsoft.com/msus/2002/"...
0x18002c451  mov     rax, [r15+228h]
0x18002c458  mov     rdx, [rax+rbp*8]
0x18002c45c  cmp     dword ptr [rdx+158h], 0
0x18002c463  mov     rbx, [rdx+50h]
0x18002c467  jnz     short loc_18002C4C5
0x18002c469  cmp     rbx, r13
0x18002c46c  jz      short loc_18002C4C5
0x18002c46e  test    rbx, rbx
0x18002c471  jz      short loc_18002C4C1
0x18002c473  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002c47b  or      r9d, 0FFFFFFFFh; cchCount1
0x18002c47f  mov     r8, rbx; lpString1
0x18002c482  mov     [rsp+88h+lpString2], r13; lpString2
0x18002c487  mov     edx, edi; dwCmpFlags
0x18002c489  mov     ecx, 7Fh; Locale
0x18002c48e  call    cs:__imp_CompareStringW
0x18002c494  cmp     eax, 2
0x18002c497  jz      short loc_18002C4C5
0x18002c499  cmp     rbx, rsi
0x18002c49c  jz      short loc_18002C4C5
0x18002c49e  or      r9d, 0FFFFFFFFh; cchCount1
0x18002c4a2  mov     r8, rbx; lpString1
0x18002c4a5  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x18002c4aa  mov     edx, edi; dwCmpFlags
0x18002c4ac  mov     ecx, 7Fh; Locale
0x18002c4b1  mov     [rsp+88h+lpString2], rsi; lpString2
0x18002c4b6  call    cs:__imp_CompareStringW
0x18002c4bc  cmp     eax, 2
0x18002c4bf  jz      short loc_18002C4C5
0x18002c4c1  xor     al, al
0x18002c4c3  jmp     short loc_18002C4C8
0x18002c4c5  mov     al, dil
0x18002c4c8  and     r12b, al
0x18002c4cb  add     ebp, edi
0x18002c4cd  cmp     ebp, [r15+220h]
0x18002c4d4  jb      loc_18002C451
0x18002c4da  mov     rdx, qword ptr cs:_GUID_e0789628_ce08_4437_be74_2495b842f43b.Data4
0x18002c4e1  mov     r8, qword ptr cs:_GUID_e0789628_ce08_4437_be74_2495b842f43b.Data1
0x18002c4e8  mov     rsi, [rsp+88h+var_48]
0x18002c4ed  mov     r9b, [rsp+88h+var_58]
0x18002c4f2  add     r14d, edi
0x18002c4f5  cmp     r14d, [rsi+2B0h]
0x18002c4fc  jb      loc_18002C40C
0x18002c502  mov     r13, [rsp+88h+var_50]
0x18002c507  test    r12b, r12b
0x18002c50a  jnz     short loc_18002C511
0x18002c50c  test    r9b, r9b
0x18002c50f  jz      short loc_18002C513
0x18002c511  xor     edi, edi
0x18002c513  test    byte ptr [rsi+318h], 4
0x18002c51a  mov     ebx, 0
0x18002c51f  cmovz   ebx, edi
0x18002c522  test    ebx, ebx
0x18002c524  jz      short loc_18002C574
0x18002c526  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18002c52d  mov     dword ptr [rsp+88h+var_48], 0
0x18002c535  call    cs:__imp_GetModuleHandleW
0x18002c53b  test    rax, rax
0x18002c53e  jz      short loc_18002C56E
0x18002c540  lea     rdx, aOobecomplete; "OOBEComplete"
0x18002c547  mov     rcx, rax; hModule
0x18002c54a  call    cs:__imp_GetProcAddress
0x18002c550  test    rax, rax
0x18002c553  jz      short loc_18002C56E
0x18002c555  lea     rcx, [rsp+88h+var_48]
0x18002c55a  call    _guard_dispatch_icall
0x18002c55f  test    eax, eax
0x18002c561  jz      short loc_18002C56E
0x18002c563  cmp     dword ptr [rsp+88h+var_48], 0
0x18002c568  jnz     short loc_18002C574
0x18002c56a  xor     ebx, ebx
0x18002c56c  jmp     short loc_18002C574
0x18002c56e  call    cs:__imp_GetLastError
0x18002c574  mov     [r13+0], ebx
0x18002c578  xor     eax, eax
0x18002c57a  mov     rcx, [rsp+88h+var_40]
0x18002c57f  xor     rcx, rsp; StackCookie
0x18002c582  call    __security_check_cookie
0x18002c587  mov     rbx, [rsp+88h+arg_10]
0x18002c58f  add     rsp, 50h
0x18002c593  pop     r15
0x18002c595  pop     r14
0x18002c597  pop     r13
0x18002c599  pop     r12
0x18002c59b  pop     rdi
0x18002c59c  pop     rsi
0x18002c59d  pop     rbp
0x18002c59e  retn
```
