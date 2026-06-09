# DeletePathDirectoryCallback

- ea: `0x1800654d0`
- end: `0x18006573f`
- name: `DeletePathDirectoryCallback`
- size: `623`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callees

- `0x1800654d0`
- `0x180065c98`
- `0x18006631c`
- `0x1800663ac`
- `0x18006642c`
- `0x180066d8c`
- `0x180068ae8`
- `0x18006f010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18006563b`
- `KERNEL32!CloseHandle` at `0x18006563b`
- `KERNEL32!SetLastError` at `0x1800654fe`
- `KERNEL32!SetLastError` at `0x180065541`
- `KERNEL32!SetLastError` at `0x180065659`
- `KERNEL32!SetLastError` at `0x18006566c`
- `KERNEL32!SetLastError` at `0x1800656a8`
- `KERNEL32!SetLastError` at `0x1800654fe`
- `KERNEL32!SetLastError` at `0x180065541`
- `KERNEL32!SetLastError` at `0x180065659`
- `KERNEL32!SetLastError` at `0x18006566c`
- `KERNEL32!SetLastError` at `0x1800656a8`
- `KERNEL32!GetLastError` at `0x18006552e`
- `KERNEL32!GetLastError` at `0x18006562e`
- `KERNEL32!GetLastError` at `0x18006564e`
- `KERNEL32!GetLastError` at `0x18006571c`
- `KERNEL32!GetLastError` at `0x18006552e`
- `KERNEL32!GetLastError` at `0x18006562e`
- `KERNEL32!GetLastError` at `0x18006564e`
- `KERNEL32!GetLastError` at `0x18006571c`
- `KERNEL32!HeapFree` at `0x1800656c4`
- `KERNEL32!HeapFree` at `0x1800656c4`
- `KERNEL32!GetProcessHeap` at `0x1800656b6`
- `KERNEL32!GetProcessHeap` at `0x1800656b6`
- `KERNEL32!CreateFileW` at `0x180065601`
- `KERNEL32!CreateFileW` at `0x180065601`

## string_xrefs

- `0x180065681`: `DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DeletePathDirectoryCallback(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // rax
  unsigned int v7; // r14d
  __int64 v8; // rcx
  DWORD v9; // edi
  int v10; // r15d
  int v11; // eax
  int v12; // eax
  const WCHAR *v13; // rcx
  int v14; // r13d
  DWORD LastError; // eax
  const WCHAR *lpFileName; // [rsp+48h] [rbp-18h]
  HANDLE hObject; // [rsp+50h] [rbp-10h]
  DWORD dwErrCode; // [rsp+B0h] [rbp+50h] BYREF
  int v19; // [rsp+B8h] [rbp+58h]

  if ( !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v6 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(a3 + 16);
  v7 = 1;
  if ( v6 )
  {
    v7 = v6(*(_QWORD *)(a1 + 40), *(_QWORD *)(a3 + 24));
    if ( !v7 )
    {
      if ( !GetLastError() )
        SetLastError(0x4C7u);
      goto LABEL_33;
    }
  }
  v8 = *(_QWORD *)(a1 + 40);
  dwErrCode = 0;
  v9 = 1;
  v10 = 0;
  if ( (unsigned int)ReparsePointExists(v8, &dwErrCode) )
  {
    if ( dwErrCode )
    {
      v11 = *(_DWORD *)(a3 + 8);
      v9 = 0;
      dwErrCode = 0;
      if ( (v11 & 2) != 0
        || (v12 = ShouldEnumerateReparsePoint(*(_QWORD *)(a1 + 40), &dwErrCode), v9 = dwErrCode, !v12)
        || !dwErrCode )
      {
        v10 = WdsRemoveDirectoryWithFlags(*(_QWORD *)(a1 + 40), *(unsigned int *)(a3 + 12));
        if ( !v9 )
          goto LABEL_32;
      }
    }
  }
  if ( (*(_DWORD *)(a3 + 12) & 0x20) != 0 )
  {
    v13 = *(const WCHAR **)(a1 + 40);
    v14 = 0;
    v19 = 0;
    lpFileName = v13;
    if ( v13 && *v13 )
    {
      hObject = CreateFileW(v13, 0, 7u, 0, 3u, 0x2200000u, 0);
      if ( hObject == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        dwErrCode = LastError;
      }
      else
      {
        dwErrCode = 0;
        if ( !(unsigned int)VerifyPathRedirectionByHandle(hObject, lpFileName) )
          dwErrCode = GetLastError();
        CloseHandle(hObject);
        LastError = dwErrCode;
        v14 = v19;
      }
      SetLastError(LastError);
      if ( !dwErrCode )
        goto LABEL_25;
    }
    else
    {
      SetLastError(0x57u);
    }
    v14 = 1;
LABEL_25:
    if ( !v14 )
    {
      LibLog(
        &g_WdsLibLog,
        50331648,
        L"DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]",
        *(_QWORD *)(a1 + 40),
        0);
      v9 = 0;
      v7 = 0;
      SetLastError(0x2A9u);
      v10 = 0;
    }
  }
  if ( v9 )
  {
    if ( (unsigned int)EnumeratePathEx(*(LPCWSTR *)(a1 + 40), *(_DWORD *)(a3 + 8)) == 1 )
    {
      v7 = 1;
      if ( (unsigned int)WdsRemoveDirectoryWithFlags(*(_QWORD *)(a1 + 40), *(unsigned int *)(a3 + 12)) == 1 )
        return v7;
    }
    else
    {
      v7 = 0;
    }
LABEL_33:
    ++*(_DWORD *)(a3 + 4);
    if ( !*(_DWORD *)a3 )
      *(_DWORD *)a3 = GetLastError();
    return v7;
  }
LABEL_32:
  if ( !v10 )
    goto LABEL_33;
  return v7;
}

```

## disassembly

```asm
0x1800654d0  mov     [rsp-38h+arg_0], rbx
0x1800654d5  mov     [rsp-38h+arg_8], rdx
0x1800654da  push    rbp
0x1800654db  push    rsi
0x1800654dc  push    rdi
0x1800654dd  push    r12
0x1800654df  push    r13
0x1800654e1  push    r14
0x1800654e3  push    r15
0x1800654e5  mov     rbp, rsp
0x1800654e8  sub     rsp, 60h
0x1800654ec  mov     rbx, r8
0x1800654ef  mov     r12, rdx
0x1800654f2  mov     rsi, rcx
0x1800654f5  test    r8, r8
0x1800654f8  jnz     short loc_18006550B
0x1800654fa  lea     ecx, [r8+57h]; dwErrCode
0x1800654fe  call    cs:__imp_SetLastError
0x180065504  xor     eax, eax
0x180065506  jmp     loc_180065727
0x18006550b  mov     rax, [r8+10h]
0x18006550f  mov     r14d, 1
0x180065515  test    rax, rax
0x180065518  jz      short loc_18006554C
0x18006551a  mov     rdx, [r8+18h]
0x18006551e  mov     rcx, [rcx+28h]
0x180065522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065527  mov     r14d, eax
0x18006552a  test    eax, eax
0x18006552c  jnz     short loc_18006554C
0x18006552e  call    cs:__imp_GetLastError
0x180065534  test    eax, eax
0x180065536  jnz     loc_180065714
0x18006553c  mov     ecx, 4C7h; dwErrCode
0x180065541  call    cs:__imp_SetLastError
0x180065547  jmp     loc_180065714
0x18006554c  mov     rcx, [rsi+28h]
0x180065550  lea     rdx, [rbp+dwErrCode]
0x180065554  mov     [rbp+dwErrCode], 0
0x18006555b  mov     edi, 1
0x180065560  xor     r15d, r15d
0x180065563  call    ReparsePointExists
0x180065568  test    eax, eax
0x18006556a  jz      short loc_1800655AD
0x18006556c  cmp     [rbp+dwErrCode], r15d
0x180065570  jz      short loc_1800655AD
0x180065572  mov     eax, [rbx+8]
0x180065575  xor     edi, edi
0x180065577  mov     [rbp+dwErrCode], edi
0x18006557a  test    al, 2
0x18006557c  jnz     short loc_180065596
0x18006557e  mov     rcx, [rsi+28h]
0x180065582  lea     rdx, [rbp+dwErrCode]
0x180065586  call    ShouldEnumerateReparsePoint
0x18006558b  mov     edi, [rbp+dwErrCode]
0x18006558e  test    eax, eax
0x180065590  jz      short loc_180065596
0x180065592  test    edi, edi
0x180065594  jnz     short loc_1800655AD
0x180065596  mov     edx, [rbx+0Ch]
0x180065599  mov     rcx, [rsi+28h]
0x18006559d  call    WdsRemoveDirectoryWithFlags
0x1800655a2  mov     r15d, eax
0x1800655a5  test    edi, edi
0x1800655a7  jz      loc_18006570F
0x1800655ad  mov     ecx, [rbx+0Ch]
0x1800655b0  test    cl, 20h
0x1800655b3  jz      loc_1800656CE
0x1800655b9  mov     rcx, [rsi+28h]; lpFileName
0x1800655bd  xor     r13d, r13d
0x1800655c0  xor     r12d, r12d
0x1800655c3  mov     [rbp+arg_18], r13d
0x1800655c7  mov     [rbp+lpMem], r12
0x1800655cb  mov     [rbp+lpFileName], rcx
0x1800655cf  test    rcx, rcx
0x1800655d2  jz      loc_180065667
0x1800655d8  xor     eax, eax
0x1800655da  cmp     ax, [rcx]
0x1800655dd  jz      loc_180065667
0x1800655e3  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x1800655e8  lea     r8d, [r13+7]; dwShareMode
0x1800655ec  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800655f4  xor     r9d, r9d; lpSecurityAttributes
0x1800655f7  xor     edx, edx; dwDesiredAccess
0x1800655f9  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x180065601  call    cs:__imp_CreateFileW
0x180065607  mov     [rbp+hObject], rax
0x18006560b  mov     rcx, rax; hFile
0x18006560e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180065612  jz      short loc_18006564E
0x180065614  mov     rdx, [rbp+lpFileName]; lpFileName
0x180065618  lea     r9, [rbp+lpMem]
0x18006561c  xor     eax, eax
0x18006561e  lea     r8, [rbp+arg_18]
0x180065622  mov     [rbp+dwErrCode], eax
0x180065625  call    VerifyPathRedirectionByHandle
0x18006562a  test    eax, eax
0x18006562c  jnz     short loc_180065637
0x18006562e  call    cs:__imp_GetLastError
0x180065634  mov     [rbp+dwErrCode], eax
0x180065637  mov     rcx, [rbp+hObject]; hObject
0x18006563b  call    cs:__imp_CloseHandle
0x180065641  mov     eax, [rbp+dwErrCode]
0x180065644  mov     r13d, [rbp+arg_18]
0x180065648  mov     r12, [rbp+lpMem]
0x18006564c  jmp     short loc_180065657
0x18006564e  call    cs:__imp_GetLastError
0x180065654  mov     [rbp+dwErrCode], eax
0x180065657  mov     ecx, eax; dwErrCode
0x180065659  call    cs:__imp_SetLastError
0x18006565f  cmp     [rbp+dwErrCode], 0
0x180065663  jz      short loc_180065678
0x180065665  jmp     short loc_180065672
0x180065667  mov     ecx, 57h ; 'W'; dwErrCode
0x18006566c  call    cs:__imp_SetLastError
0x180065672  mov     r13d, 1
0x180065678  test    r13d, r13d
0x18006567b  jnz     short loc_1800656B1
0x18006567d  mov     r9, [rsi+28h]
0x180065681  lea     r8, aDeletepathdire; "DeletePathDirectoryCallback: Spoofing d"...
0x180065688  mov     edx, 3000000h
0x18006568d  mov     qword ptr [rsp+60h+dwCreationDisposition], r12
0x180065692  lea     rcx, g_WdsLibLog
0x180065699  call    LibLog
0x18006569e  mov     ecx, 2A9h; dwErrCode
0x1800656a3  xor     edi, edi
0x1800656a5  xor     r14d, r14d
0x1800656a8  call    cs:__imp_SetLastError
0x1800656ae  xor     r15d, r15d
0x1800656b1  test    r12, r12
0x1800656b4  jz      short loc_1800656CA
0x1800656b6  call    cs:__imp_GetProcessHeap
0x1800656bc  mov     r8, r12; lpMem
0x1800656bf  xor     edx, edx; dwFlags
0x1800656c1  mov     rcx, rax; hHeap
0x1800656c4  call    cs:__imp_HeapFree
0x1800656ca  mov     r12, [rbp+arg_8]
0x1800656ce  test    edi, edi
0x1800656d0  jz      short loc_18006570F
0x1800656d2  mov     eax, [rbx+8]
0x1800656d5  lea     rdx, DeletePathDirectoryCallback
0x1800656dc  mov     rcx, [rsi+28h]; lpFileName
0x1800656e0  mov     r9, rbx
0x1800656e3  mov     r8, r12
0x1800656e6  mov     [rsp+60h+dwCreationDisposition], eax; int
0x1800656ea  call    EnumeratePathEx
0x1800656ef  cmp     eax, 1
0x1800656f2  jnz     short loc_18006570A
0x1800656f4  mov     edx, [rbx+0Ch]
0x1800656f7  mov     r14d, eax
0x1800656fa  mov     rcx, [rsi+28h]
0x1800656fe  call    WdsRemoveDirectoryWithFlags
0x180065703  cmp     eax, r14d
0x180065706  jnz     short loc_180065714
0x180065708  jmp     short loc_180065724
0x18006570a  xor     r14d, r14d
0x18006570d  jmp     short loc_180065714
0x18006570f  test    r15d, r15d
0x180065712  jnz     short loc_180065724
0x180065714  inc     dword ptr [rbx+4]
0x180065717  cmp     dword ptr [rbx], 0
0x18006571a  jnz     short loc_180065724
0x18006571c  call    cs:__imp_GetLastError
0x180065722  mov     [rbx], eax
0x180065724  mov     eax, r14d
0x180065727  mov     rbx, [rsp+60h+arg_0]
0x18006572f  add     rsp, 60h
0x180065733  pop     r15
0x180065735  pop     r14
0x180065737  pop     r13
0x180065739  pop     r12
0x18006573b  pop     rdi
0x18006573c  pop     rsi
0x18006573d  pop     rbp
0x18006573e  retn
```
