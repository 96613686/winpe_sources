# DeletePathDirectoryCallback

- ea: `0x180066270`
- end: `0x180066555`
- name: `DeletePathDirectoryCallback`
- size: `741`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callees

- `0x180063538`
- `0x180063df0`
- `0x180064504`
- `0x180066270`
- `0x180066b38`
- `0x1800673e4`
- `0x180067480`
- `0x180067990`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800664aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800664aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800664be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800664be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800662ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800663ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800662ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800663ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066427`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066534`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066298`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800662e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006634e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066438`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066497`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066298`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800662e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006634e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066438`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066451`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180066497`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066412`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180066412`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800663cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800663cc`

## string_xrefs

- `0x180066470`: `DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]`

## pseudocode

```c
__int64 __fastcall DeletePathDirectoryCallback(__int64 a1, __int64 (__fastcall *a2)(DWORD *, __int64), __int64 a3)
{
  __int64 (__fastcall *v4)(DWORD *, __int64); // r13
  __int64 (__fastcall *v7)(_QWORD, _QWORD); // rax
  unsigned int v8; // r15d
  DWORD v9; // ecx
  __int64 v10; // rcx
  DWORD v11; // edi
  BOOL v12; // esi
  int v13; // eax
  int v14; // eax
  unsigned __int16 *v15; // rcx
  int v16; // edx
  BOOL v17; // eax
  const WCHAR *v18; // rcx
  int v19; // r13d
  DWORD LastError; // eax
  bool v21; // zf
  void *v22; // r13
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v24; // rcx
  int v25; // edx
  BOOL v26; // eax
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  const WCHAR *v28; // [rsp+48h] [rbp-18h]
  HANDLE hObject; // [rsp+50h] [rbp-10h]
  DWORD dwErrCode; // [rsp+B0h] [rbp+50h] BYREF
  int v32; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a2;
  if ( !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v7 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(a3 + 16);
  v8 = 1;
  if ( v7 )
  {
    v8 = v7(*(_QWORD *)(a1 + 40), *(_QWORD *)(a3 + 24));
    if ( !v8 )
    {
      if ( GetLastError() )
        goto LABEL_48;
      v9 = 1223;
      goto LABEL_7;
    }
  }
  v10 = *(_QWORD *)(a1 + 40);
  dwErrCode = 0;
  v11 = 1;
  v12 = 0;
  if ( (unsigned int)ReparsePointExists(v10, &dwErrCode) )
  {
    if ( dwErrCode )
    {
      v13 = *(_DWORD *)(a3 + 8);
      v11 = 0;
      dwErrCode = 0;
      if ( (v13 & 2) != 0
        || (v14 = ShouldEnumerateReparsePoint(*(_QWORD *)(a1 + 40), &dwErrCode), v11 = dwErrCode, !v14)
        || !dwErrCode )
      {
        v15 = *(unsigned __int16 **)(a1 + 40);
        if ( v15 )
        {
          v16 = *(_DWORD *)(a3 + 12) & 0x21;
          v17 = v16 ? DeleteFileEx2((__int64)v15, v16) : WdsRemoveDirectory(v15);
          v12 = v17;
        }
        else
        {
          SetLastError(0x57u);
          v12 = 0;
        }
        if ( !v11 )
          goto LABEL_47;
      }
    }
  }
  if ( (*(_DWORD *)(a3 + 12) & 0x20) != 0 )
  {
    v18 = *(const WCHAR **)(a1 + 40);
    v19 = 0;
    v32 = 0;
    lpMem = 0;
    v28 = v18;
    if ( v18 && *v18 )
    {
      hObject = CreateFileW(v18, 0, 7u, 0, 3u, 0x2200000u, 0);
      if ( hObject == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        dwErrCode = LastError;
      }
      else
      {
        dwErrCode = 0;
        if ( !(unsigned int)VerifyPathRedirectionByHandle(hObject, v28, &v32, &lpMem) )
          dwErrCode = GetLastError();
        CloseHandle(hObject);
        LastError = dwErrCode;
        v19 = v32;
      }
      SetLastError(LastError);
      if ( !dwErrCode )
        goto LABEL_32;
    }
    else
    {
      SetLastError(0x57u);
    }
    v19 = 1;
LABEL_32:
    v21 = v19 == 0;
    v22 = lpMem;
    if ( v21 )
    {
      LibLog(
        &g_WdsLibLog,
        50331648,
        L"DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]",
        *(_QWORD *)(a1 + 40),
        lpMem);
      v11 = 0;
      v8 = 0;
      SetLastError(0x2A9u);
      v12 = 0;
    }
    if ( v22 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v22);
    }
    v4 = a2;
  }
  if ( v11 )
  {
    if ( (unsigned int)EnumeratePathEx(
                         *(LPCWSTR *)(a1 + 40),
                         (__int64 (__fastcall *)(DWORD *, __int64 (__fastcall *)(_QWORD, _QWORD), __int64))DeletePathDirectoryCallback,
                         v4,
                         a3,
                         *(_DWORD *)(a3 + 8)) == 1 )
    {
      v24 = *(unsigned __int16 **)(a1 + 40);
      v8 = 1;
      if ( v24 )
      {
        v25 = *(_DWORD *)(a3 + 12) & 0x21;
        if ( v25 )
          v26 = DeleteFileEx2((__int64)v24, v25);
        else
          v26 = WdsRemoveDirectory(v24);
        if ( v26 )
          return v8;
        goto LABEL_48;
      }
      v9 = 87;
LABEL_7:
      SetLastError(v9);
      goto LABEL_48;
    }
    v8 = 0;
LABEL_48:
    ++*(_DWORD *)(a3 + 4);
    if ( !*(_DWORD *)a3 )
      *(_DWORD *)a3 = GetLastError();
    return v8;
  }
LABEL_47:
  if ( !v12 )
    goto LABEL_48;
  return v8;
}

```

## disassembly

```asm
0x180066270  mov     [rsp-38h+arg_8], rdx
0x180066275  push    rbp
0x180066276  push    rbx
0x180066277  push    rsi
0x180066278  push    rdi
0x180066279  push    r13
0x18006627b  push    r14
0x18006627d  push    r15
0x18006627f  mov     rbp, rsp
0x180066282  sub     rsp, 60h
0x180066286  mov     rbx, r8
0x180066289  mov     r13, rdx
0x18006628c  mov     r14, rcx
0x18006628f  test    r8, r8
0x180066292  jnz     short loc_1800662AB
0x180066294  lea     ecx, [r8+57h]; dwErrCode
0x180066298  call    cs:__imp_SetLastError
0x18006629f  nop     dword ptr [rax+rax+00h]
0x1800662a4  xor     eax, eax
0x1800662a6  jmp     loc_180066545
0x1800662ab  mov     rax, [r8+10h]
0x1800662af  mov     r15d, 1
0x1800662b5  test    rax, rax
0x1800662b8  jz      short loc_1800662F8
0x1800662ba  mov     rdx, [r8+18h]
0x1800662be  mov     rcx, [rcx+28h]
0x1800662c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662c7  mov     r15d, eax
0x1800662ca  test    eax, eax
0x1800662cc  jnz     short loc_1800662F8
0x1800662ce  call    cs:__imp_GetLastError
0x1800662d5  nop     dword ptr [rax+rax+00h]
0x1800662da  test    eax, eax
0x1800662dc  jnz     loc_18006652C
0x1800662e2  mov     ecx, 4C7h; dwErrCode
0x1800662e7  call    cs:__imp_SetLastError
0x1800662ee  nop     dword ptr [rax+rax+00h]
0x1800662f3  jmp     loc_18006652C
0x1800662f8  mov     rcx, [r14+28h]
0x1800662fc  lea     rdx, [rbp+dwErrCode]
0x180066300  mov     [rbp+dwErrCode], 0
0x180066307  mov     edi, 1
0x18006630c  xor     esi, esi
0x18006630e  call    ReparsePointExists
0x180066313  test    eax, eax
0x180066315  jz      short loc_18006637C
0x180066317  cmp     [rbp+dwErrCode], esi
0x18006631a  jz      short loc_18006637C
0x18006631c  mov     eax, [rbx+8]
0x18006631f  xor     edi, edi
0x180066321  mov     [rbp+dwErrCode], edi
0x180066324  test    al, 2
0x180066326  jnz     short loc_180066340
0x180066328  mov     rcx, [r14+28h]
0x18006632c  lea     rdx, [rbp+dwErrCode]
0x180066330  call    ShouldEnumerateReparsePoint
0x180066335  mov     edi, [rbp+dwErrCode]
0x180066338  test    eax, eax
0x18006633a  jz      short loc_180066340
0x18006633c  test    edi, edi
0x18006633e  jnz     short loc_18006637C
0x180066340  mov     rcx, [r14+28h]
0x180066344  test    rcx, rcx
0x180066347  jnz     short loc_18006635E
0x180066349  mov     ecx, 57h ; 'W'; dwErrCode
0x18006634e  call    cs:__imp_SetLastError
0x180066355  nop     dword ptr [rax+rax+00h]
0x18006635a  xor     esi, esi
0x18006635c  jmp     short loc_180066374
0x18006635e  mov     edx, [rbx+0Ch]
0x180066361  and     edx, 21h
0x180066364  jnz     short loc_18006636D
0x180066366  call    WdsRemoveDirectory
0x18006636b  jmp     short loc_180066372
0x18006636d  call    DeleteFileEx2
0x180066372  mov     esi, eax
0x180066374  test    edi, edi
0x180066376  jz      loc_180066528
0x18006637c  mov     eax, [rbx+0Ch]
0x18006637f  test    al, 20h
0x180066381  jz      loc_1800664CE
0x180066387  mov     rcx, [r14+28h]; lpFileName
0x18006638b  xor     r13d, r13d
0x18006638e  mov     [rbp+arg_18], r13d
0x180066392  mov     [rbp+lpMem], r13
0x180066396  mov     [rbp+var_18], rcx
0x18006639a  test    rcx, rcx
0x18006639d  jz      loc_18006644C
0x1800663a3  xor     eax, eax
0x1800663a5  cmp     ax, [rcx]
0x1800663a8  jz      loc_18006644C
0x1800663ae  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x1800663b3  lea     r8d, [r13+7]; dwShareMode
0x1800663b7  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800663bf  xor     r9d, r9d; lpSecurityAttributes
0x1800663c2  xor     edx, edx; dwDesiredAccess
0x1800663c4  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x1800663cc  call    cs:__imp_CreateFileW
0x1800663d3  nop     dword ptr [rax+rax+00h]
0x1800663d8  mov     [rbp+hObject], rax
0x1800663dc  mov     rcx, rax
0x1800663df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800663e3  jz      short loc_180066427
0x1800663e5  mov     rdx, [rbp+var_18]
0x1800663e9  lea     r9, [rbp+lpMem]
0x1800663ed  xor     eax, eax
0x1800663ef  lea     r8, [rbp+arg_18]
0x1800663f3  mov     [rbp+dwErrCode], eax
0x1800663f6  call    VerifyPathRedirectionByHandle
0x1800663fb  test    eax, eax
0x1800663fd  jnz     short loc_18006640E
0x1800663ff  call    cs:__imp_GetLastError
0x180066406  nop     dword ptr [rax+rax+00h]
0x18006640b  mov     [rbp+dwErrCode], eax
0x18006640e  mov     rcx, [rbp+hObject]; hObject
0x180066412  call    cs:__imp_CloseHandle
0x180066419  nop     dword ptr [rax+rax+00h]
0x18006641e  mov     eax, [rbp+dwErrCode]
0x180066421  mov     r13d, [rbp+arg_18]
0x180066425  jmp     short loc_180066436
0x180066427  call    cs:__imp_GetLastError
0x18006642e  nop     dword ptr [rax+rax+00h]
0x180066433  mov     [rbp+dwErrCode], eax
0x180066436  mov     ecx, eax; dwErrCode
0x180066438  call    cs:__imp_SetLastError
0x18006643f  nop     dword ptr [rax+rax+00h]
0x180066444  cmp     [rbp+dwErrCode], 0
0x180066448  jz      short loc_180066463
0x18006644a  jmp     short loc_18006645D
0x18006644c  mov     ecx, 57h ; 'W'; dwErrCode
0x180066451  call    cs:__imp_SetLastError
0x180066458  nop     dword ptr [rax+rax+00h]
0x18006645d  mov     r13d, 1
0x180066463  test    r13d, r13d
0x180066466  mov     r13, [rbp+lpMem]
0x18006646a  jnz     short loc_1800664A5
0x18006646c  mov     r9, [r14+28h]
0x180066470  lea     r8, aDeletepathdire; "DeletePathDirectoryCallback: Spoofing d"...
0x180066477  mov     edx, 3000000h
0x18006647c  mov     qword ptr [rsp+60h+dwCreationDisposition], r13
0x180066481  lea     rcx, g_WdsLibLog
0x180066488  call    LibLog
0x18006648d  mov     ecx, 2A9h; dwErrCode
0x180066492  xor     edi, edi
0x180066494  xor     r15d, r15d
0x180066497  call    cs:__imp_SetLastError
0x18006649e  nop     dword ptr [rax+rax+00h]
0x1800664a3  xor     esi, esi
0x1800664a5  test    r13, r13
0x1800664a8  jz      short loc_1800664CA
0x1800664aa  call    cs:__imp_GetProcessHeap
0x1800664b1  nop     dword ptr [rax+rax+00h]
0x1800664b6  mov     r8, r13; lpMem
0x1800664b9  xor     edx, edx; dwFlags
0x1800664bb  mov     rcx, rax; hHeap
0x1800664be  call    cs:__imp_HeapFree
0x1800664c5  nop     dword ptr [rax+rax+00h]
0x1800664ca  mov     r13, [rbp+arg_8]
0x1800664ce  test    edi, edi
0x1800664d0  jz      short loc_180066528
0x1800664d2  mov     eax, [rbx+8]
0x1800664d5  lea     rdx, DeletePathDirectoryCallback
0x1800664dc  mov     rcx, [r14+28h]; lpFileName
0x1800664e0  mov     r9, rbx
0x1800664e3  mov     r8, r13
0x1800664e6  mov     [rsp+60h+dwCreationDisposition], eax; int
0x1800664ea  call    EnumeratePathEx
0x1800664ef  cmp     eax, 1
0x1800664f2  jnz     short loc_180066523
0x1800664f4  mov     rcx, [r14+28h]
0x1800664f8  mov     r15d, eax
0x1800664fb  test    rcx, rcx
0x1800664fe  jnz     short loc_180066508
0x180066500  lea     ecx, [rax+56h]
0x180066503  jmp     loc_1800662E7
0x180066508  mov     edx, [rbx+0Ch]
0x18006650b  and     edx, 21h
0x18006650e  jnz     short loc_180066517
0x180066510  call    WdsRemoveDirectory
0x180066515  jmp     short loc_18006651C
0x180066517  call    DeleteFileEx2
0x18006651c  cmp     eax, r15d
0x18006651f  jnz     short loc_18006652C
0x180066521  jmp     short loc_180066542
0x180066523  xor     r15d, r15d
0x180066526  jmp     short loc_18006652C
0x180066528  test    esi, esi
0x18006652a  jnz     short loc_180066542
0x18006652c  inc     dword ptr [rbx+4]
0x18006652f  cmp     dword ptr [rbx], 0
0x180066532  jnz     short loc_180066542
0x180066534  call    cs:__imp_GetLastError
0x18006653b  nop     dword ptr [rax+rax+00h]
0x180066540  mov     [rbx], eax
0x180066542  mov     eax, r15d
0x180066545  add     rsp, 60h
0x180066549  pop     r15
0x18006654b  pop     r14
0x18006654d  pop     r13
0x18006654f  pop     rdi
0x180066550  pop     rsi
0x180066551  pop     rbx
0x180066552  pop     rbp
0x180066553  retn
```
