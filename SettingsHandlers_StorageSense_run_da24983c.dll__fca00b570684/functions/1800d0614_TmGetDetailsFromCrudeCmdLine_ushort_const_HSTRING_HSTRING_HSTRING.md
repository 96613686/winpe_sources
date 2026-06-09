# TmGetDetailsFromCrudeCmdLine(ushort const *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)

- ea: `0x1800d0614`
- end: `0x1800d0837`
- name: `?TmGetDetailsFromCrudeCmdLine@@YAJPEBGPEAPEAUHSTRING__@@11@Z`
- size: `547`
- prototype: `int(const unsigned __int16 *, HSTRING *, HSTRING *, HSTRING *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800d5988`
- `0x1800d631c`
- `0x1800d9f98`

## callees

- `0x180006e50`
- `0x18000f07c`
- `0x1800d02bc`
- `0x1800d0614`
- `0x1800d0ccc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800d0790`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800d0790`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d07bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d07dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d07ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d07bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d07dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d07ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d07cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d07ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d080d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d07cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d07ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d080d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d0739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d075f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d07ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d0739`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d075f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d07ad`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800d0679`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800d0679`
- `ext-ms-win-shell-shell32-l1-2-2!SHEvaluateSystemCommandTemplate` at `0x1800d0695`
- `ext-ms-win-shell-shell32-l1-2-2!SHEvaluateSystemCommandTemplate` at `0x1800d0695`

## pseudocode

```c
__int64 __fastcall TmGetDetailsFromCrudeCmdLine(const unsigned __int16 *a1, HSTRING *a2, HSTRING *a3, HSTRING *a4)
{
  HRESULT String; // ebx
  __int64 v8; // rdi
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  wchar_t *v12; // rcx
  const WCHAR *v13; // rbx
  wchar_t *v14; // rax
  HANDLE ProcessHeap; // rax
  PWSTR v16; // rdi
  HANDLE v17; // rax
  PWSTR v18; // rdi
  HANDLE v19; // rax
  PWSTR ppszApplication; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR pszPath; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR ppszParameters; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Context; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR sourceString[1024]; // [rsp+50h] [rbp-B0h] BYREF

  Context = 0;
  ppszApplication = 0;
  pszPath = 0;
  ppszParameters = 0;
  String = TmExpandEnvironmentVariables(a1, (unsigned __int16 **)&pszPath);
  if ( String >= 0 )
  {
    if ( !PathIsNetworkPathW(pszPath)
      && (String = SHEvaluateSystemCommandTemplate(pszPath, &ppszApplication, 0, &ppszParameters), String >= 0)
      || (String = TmManualParseCmdLine((unsigned __int16 *)pszPath, &ppszApplication, &ppszParameters), String >= 0) )
    {
      v8 = -1;
      if ( !a2 )
        goto LABEL_14;
      v9 = ppszParameters && *ppszParameters
         ? StringCchPrintfW(sourceString, 0x400u, L"\"%s\" %s", ppszApplication, ppszParameters)
         : StringCchPrintfW(sourceString, 0x400u, L"\"%s\"", ppszApplication);
      String = v9;
      if ( v9 >= 0 )
      {
        v10 = -1;
        do
          ++v10;
        while ( sourceString[v10] );
        String = WindowsCreateString(sourceString, v10, a2);
        if ( String >= 0 )
        {
LABEL_14:
          if ( !a3 )
            goto LABEL_18;
          v11 = -1;
          do
            ++v11;
          while ( ppszApplication[v11] );
          String = WindowsCreateString(ppszApplication, v11, a3);
          if ( String >= 0 )
          {
LABEL_18:
            if ( a4 )
            {
              v12 = ppszApplication;
              v13 = 0;
              Context = 0;
              while ( 1 )
              {
                v14 = wcstok_s(v12, L"\\", &Context);
                if ( !v14 )
                  break;
                v13 = v14;
                v12 = 0;
              }
              do
                ++v8;
              while ( v13[v8] );
              String = WindowsCreateString(v13, v8, a4);
            }
          }
        }
      }
    }
  }
  if ( pszPath )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)pszPath);
  }
  v16 = ppszApplication;
  if ( ppszApplication )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
    ppszApplication = 0;
  }
  v18 = ppszParameters;
  if ( ppszParameters )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v18);
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800d0614  push    rbp
0x1800d0616  push    rbx
0x1800d0617  push    rdi
0x1800d0618  push    r12
0x1800d061a  push    r13
0x1800d061c  push    r14
0x1800d061e  push    r15
0x1800d0620  lea     rbp, [rsp-760h]
0x1800d0628  sub     rsp, 860h
0x1800d062f  mov     rax, cs:__security_cookie
0x1800d0636  xor     rax, rsp
0x1800d0639  mov     [rbp+790h+var_40], rax
0x1800d0640  xor     r13d, r13d
0x1800d0643  mov     r14, rdx
0x1800d0646  lea     rdx, [rsp+890h+pszPath]; unsigned __int16 **
0x1800d064b  mov     [rsp+890h+Context], r13
0x1800d0650  mov     [rsp+890h+ppszApplication], r13
0x1800d0655  mov     r12, r9
0x1800d0658  mov     [rsp+890h+pszPath], r13
0x1800d065d  mov     r15, r8
0x1800d0660  mov     [rsp+890h+ppszParameters], r13
0x1800d0665  call    ?TmExpandEnvironmentVariables@@YAJPEBGPEAPEAG@Z; TmExpandEnvironmentVariables(ushort const *,ushort * *)
0x1800d066a  mov     ebx, eax
0x1800d066c  test    eax, eax
0x1800d066e  js      loc_1800D07B5
0x1800d0674  mov     rcx, [rsp+890h+pszPath]; pszPath
0x1800d0679  call    cs:__imp_PathIsNetworkPathW
0x1800d067f  test    eax, eax
0x1800d0681  jnz     short loc_1800D06A1
0x1800d0683  mov     rcx, [rsp+890h+pszPath]; pszCmdTemplate
0x1800d0688  lea     r9, [rsp+890h+ppszParameters]; ppszParameters
0x1800d068d  xor     r8d, r8d; ppszCommandLine
0x1800d0690  lea     rdx, [rsp+890h+ppszApplication]; ppszApplication
0x1800d0695  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x1800d069b  mov     ebx, eax
0x1800d069d  test    eax, eax
0x1800d069f  jns     short loc_1800D06BF
0x1800d06a1  mov     rcx, [rsp+890h+pszPath]; unsigned __int16 *
0x1800d06a6  lea     r8, [rsp+890h+ppszParameters]; unsigned __int16 **
0x1800d06ab  lea     rdx, [rsp+890h+ppszApplication]; unsigned __int16 **
0x1800d06b0  call    ?TmManualParseCmdLine@@YAJPEAGPEAPEAG1@Z; TmManualParseCmdLine(ushort *,ushort * *,ushort * *)
0x1800d06b5  mov     ebx, eax
0x1800d06b7  test    eax, eax
0x1800d06b9  js      loc_1800D07B5
0x1800d06bf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800d06c3  test    r14, r14
0x1800d06c6  jz      short loc_1800D0745
0x1800d06c8  mov     rax, [rsp+890h+ppszParameters]
0x1800d06cd  test    rax, rax
0x1800d06d0  jz      short loc_1800D06FA
0x1800d06d2  cmp     [rax], r13w
0x1800d06d6  jz      short loc_1800D06FA
0x1800d06d8  mov     r9, [rsp+890h+ppszApplication]
0x1800d06dd  lea     r8, aSS_3; "\"%s\" %s"
0x1800d06e4  mov     edx, 400h; unsigned __int64
0x1800d06e9  mov     [rsp+890h+var_870], rax
0x1800d06ee  lea     rcx, [rsp+890h+sourceString]; unsigned __int16 *
0x1800d06f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d06f8  jmp     short loc_1800D0715
0x1800d06fa  mov     r9, [rsp+890h+ppszApplication]
0x1800d06ff  lea     r8, aS_0; "\"%s\""
0x1800d0706  mov     edx, 400h; unsigned __int64
0x1800d070b  lea     rcx, [rsp+890h+sourceString]; unsigned __int16 *
0x1800d0710  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d0715  mov     ebx, eax
0x1800d0717  test    eax, eax
0x1800d0719  js      loc_1800D07B5
0x1800d071f  lea     rax, [rsp+890h+sourceString]
0x1800d0724  mov     rdx, rdi
0x1800d0727  inc     rdx; length
0x1800d072a  cmp     [rax+rdx*2], r13w
0x1800d072f  jnz     short loc_1800D0727
0x1800d0731  mov     r8, r14; string
0x1800d0734  lea     rcx, [rsp+890h+sourceString]; sourceString
0x1800d0739  call    cs:__imp_WindowsCreateString
0x1800d073f  mov     ebx, eax
0x1800d0741  test    eax, eax
0x1800d0743  js      short loc_1800D07B5
0x1800d0745  test    r15, r15
0x1800d0748  jz      short loc_1800D076B
0x1800d074a  mov     rcx, [rsp+890h+ppszApplication]; sourceString
0x1800d074f  mov     rdx, rdi
0x1800d0752  inc     rdx; length
0x1800d0755  cmp     [rcx+rdx*2], r13w
0x1800d075a  jnz     short loc_1800D0752
0x1800d075c  mov     r8, r15; string
0x1800d075f  call    cs:__imp_WindowsCreateString
0x1800d0765  mov     ebx, eax
0x1800d0767  test    eax, eax
0x1800d0769  js      short loc_1800D07B5
0x1800d076b  test    r12, r12
0x1800d076e  jz      short loc_1800D07B5
0x1800d0770  mov     rcx, [rsp+890h+ppszApplication]
0x1800d0775  mov     rbx, r13
0x1800d0778  mov     [rsp+890h+Context], r13
0x1800d077d  jmp     short loc_1800D0784
0x1800d077f  mov     rbx, rax
0x1800d0782  xor     ecx, ecx; String
0x1800d0784  lea     r8, [rsp+890h+Context]; Context
0x1800d0789  lea     rdx, Delimiter; "\\"
0x1800d0790  call    cs:__imp_wcstok_s
0x1800d0796  test    rax, rax
0x1800d0799  jnz     short loc_1800D077F
0x1800d079b  inc     rdi
0x1800d079e  cmp     [rbx+rdi*2], r13w
0x1800d07a3  jnz     short loc_1800D079B
0x1800d07a5  mov     r8, r12; string
0x1800d07a8  mov     edx, edi; length
0x1800d07aa  mov     rcx, rbx; sourceString
0x1800d07ad  call    cs:__imp_WindowsCreateString
0x1800d07b3  mov     ebx, eax
0x1800d07b5  cmp     [rsp+890h+pszPath], r13
0x1800d07ba  jz      short loc_1800D07D2
0x1800d07bc  call    cs:__imp_GetProcessHeap
0x1800d07c2  mov     r8, [rsp+890h+pszPath]; lpMem
0x1800d07c7  xor     edx, edx; dwFlags
0x1800d07c9  mov     rcx, rax; hHeap
0x1800d07cc  call    cs:__imp_HeapFree
0x1800d07d2  mov     rdi, [rsp+890h+ppszApplication]
0x1800d07d7  test    rdi, rdi
0x1800d07da  jz      short loc_1800D07F5
0x1800d07dc  call    cs:__imp_GetProcessHeap
0x1800d07e2  mov     r8, rdi; lpMem
0x1800d07e5  xor     edx, edx; dwFlags
0x1800d07e7  mov     rcx, rax; hHeap
0x1800d07ea  call    cs:__imp_HeapFree
0x1800d07f0  mov     [rsp+890h+ppszApplication], r13
0x1800d07f5  mov     rdi, [rsp+890h+ppszParameters]
0x1800d07fa  test    rdi, rdi
0x1800d07fd  jz      short loc_1800D0813
0x1800d07ff  call    cs:__imp_GetProcessHeap
0x1800d0805  mov     r8, rdi; lpMem
0x1800d0808  xor     edx, edx; dwFlags
0x1800d080a  mov     rcx, rax; hHeap
0x1800d080d  call    cs:__imp_HeapFree
0x1800d0813  mov     eax, ebx
0x1800d0815  mov     rcx, [rbp+790h+var_40]
0x1800d081c  xor     rcx, rsp; StackCookie
0x1800d081f  call    __security_check_cookie
0x1800d0824  add     rsp, 860h
0x1800d082b  pop     r15
0x1800d082d  pop     r14
0x1800d082f  pop     r13
0x1800d0831  pop     r12
0x1800d0833  pop     rdi
0x1800d0834  pop     rbx
0x1800d0835  pop     rbp
0x1800d0836  retn
```
