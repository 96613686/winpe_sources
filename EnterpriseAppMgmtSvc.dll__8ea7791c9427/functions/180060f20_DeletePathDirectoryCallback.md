# DeletePathDirectoryCallback

- ea: `0x180060f20`
- end: `0x1800611b0`
- name: `DeletePathDirectoryCallback`
- size: `656`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callees

- `0x18005e748`
- `0x18005eea8`
- `0x18005f56c`
- `0x180060f20`
- `0x1800616e8`
- `0x180061e8c`
- `0x180061f0c`
- `0x1800623f4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061118`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061118`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061126`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060f78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061091`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061196`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060f48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060f8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060fec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800610b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800610cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006110b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060f48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060f8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060fec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800610b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800610cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006110b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006109e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006109e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061064`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180061064`

## string_xrefs

- `0x1800610e4`: `DeletePathDirectoryCallback: Spoofing detected deleting [%s] -> [%s]`

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
0x180060f20  mov     [rsp-38h+arg_8], rdx
0x180060f25  push    rbp
0x180060f26  push    rbx
0x180060f27  push    rsi
0x180060f28  push    rdi
0x180060f29  push    r13
0x180060f2b  push    r14
0x180060f2d  push    r15
0x180060f2f  mov     rbp, rsp
0x180060f32  sub     rsp, 60h
0x180060f36  mov     rbx, r8
0x180060f39  mov     r13, rdx
0x180060f3c  mov     r14, rcx
0x180060f3f  test    r8, r8
0x180060f42  jnz     short loc_180060F55
0x180060f44  lea     ecx, [r8+57h]; dwErrCode
0x180060f48  call    cs:__imp_SetLastError
0x180060f4e  xor     eax, eax
0x180060f50  jmp     loc_1800611A1
0x180060f55  mov     rax, [r8+10h]
0x180060f59  mov     r15d, 1
0x180060f5f  test    rax, rax
0x180060f62  jz      short loc_180060F96
0x180060f64  mov     rdx, [r8+18h]
0x180060f68  mov     rcx, [rcx+28h]
0x180060f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f71  mov     r15d, eax
0x180060f74  test    eax, eax
0x180060f76  jnz     short loc_180060F96
0x180060f78  call    cs:__imp_GetLastError
0x180060f7e  test    eax, eax
0x180060f80  jnz     loc_18006118E
0x180060f86  mov     ecx, 4C7h; dwErrCode
0x180060f8b  call    cs:__imp_SetLastError
0x180060f91  jmp     loc_18006118E
0x180060f96  mov     rcx, [r14+28h]
0x180060f9a  lea     rdx, [rbp+dwErrCode]
0x180060f9e  mov     [rbp+dwErrCode], 0
0x180060fa5  mov     edi, 1
0x180060faa  xor     esi, esi
0x180060fac  call    ReparsePointExists
0x180060fb1  test    eax, eax
0x180060fb3  jz      short loc_180061014
0x180060fb5  cmp     [rbp+dwErrCode], esi
0x180060fb8  jz      short loc_180061014
0x180060fba  mov     eax, [rbx+8]
0x180060fbd  xor     edi, edi
0x180060fbf  mov     [rbp+dwErrCode], edi
0x180060fc2  test    al, 2
0x180060fc4  jnz     short loc_180060FDE
0x180060fc6  mov     rcx, [r14+28h]
0x180060fca  lea     rdx, [rbp+dwErrCode]
0x180060fce  call    ShouldEnumerateReparsePoint
0x180060fd3  mov     edi, [rbp+dwErrCode]
0x180060fd6  test    eax, eax
0x180060fd8  jz      short loc_180060FDE
0x180060fda  test    edi, edi
0x180060fdc  jnz     short loc_180061014
0x180060fde  mov     rcx, [r14+28h]
0x180060fe2  test    rcx, rcx
0x180060fe5  jnz     short loc_180060FF6
0x180060fe7  mov     ecx, 57h ; 'W'; dwErrCode
0x180060fec  call    cs:__imp_SetLastError
0x180060ff2  xor     esi, esi
0x180060ff4  jmp     short loc_18006100C
0x180060ff6  mov     edx, [rbx+0Ch]
0x180060ff9  and     edx, 21h
0x180060ffc  jnz     short loc_180061005
0x180060ffe  call    WdsRemoveDirectory
0x180061003  jmp     short loc_18006100A
0x180061005  call    DeleteFileEx2
0x18006100a  mov     esi, eax
0x18006100c  test    edi, edi
0x18006100e  jz      loc_18006118A
0x180061014  mov     eax, [rbx+0Ch]
0x180061017  test    al, 20h
0x180061019  jz      loc_180061130
0x18006101f  mov     rcx, [r14+28h]; lpFileName
0x180061023  xor     r13d, r13d
0x180061026  mov     [rbp+arg_18], r13d
0x18006102a  mov     [rbp+lpMem], r13
0x18006102e  mov     [rbp+var_18], rcx
0x180061032  test    rcx, rcx
0x180061035  jz      loc_1800610C6
0x18006103b  xor     eax, eax
0x18006103d  cmp     ax, [rcx]
0x180061040  jz      loc_1800610C6
0x180061046  mov     [rsp+60h+hTemplateFile], rax; hTemplateFile
0x18006104b  lea     r8d, [r13+7]; dwShareMode
0x18006104f  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180061057  xor     r9d, r9d; lpSecurityAttributes
0x18006105a  xor     edx, edx; dwDesiredAccess
0x18006105c  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x180061064  call    cs:__imp_CreateFileW
0x18006106a  mov     [rbp+hObject], rax
0x18006106e  mov     rcx, rax
0x180061071  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180061075  jz      short loc_1800610AD
0x180061077  mov     rdx, [rbp+var_18]
0x18006107b  lea     r9, [rbp+lpMem]
0x18006107f  xor     eax, eax
0x180061081  lea     r8, [rbp+arg_18]
0x180061085  mov     [rbp+dwErrCode], eax
0x180061088  call    VerifyPathRedirectionByHandle
0x18006108d  test    eax, eax
0x18006108f  jnz     short loc_18006109A
0x180061091  call    cs:__imp_GetLastError
0x180061097  mov     [rbp+dwErrCode], eax
0x18006109a  mov     rcx, [rbp+hObject]; hObject
0x18006109e  call    cs:__imp_CloseHandle
0x1800610a4  mov     eax, [rbp+dwErrCode]
0x1800610a7  mov     r13d, [rbp+arg_18]
0x1800610ab  jmp     short loc_1800610B6
0x1800610ad  call    cs:__imp_GetLastError
0x1800610b3  mov     [rbp+dwErrCode], eax
0x1800610b6  mov     ecx, eax; dwErrCode
0x1800610b8  call    cs:__imp_SetLastError
0x1800610be  cmp     [rbp+dwErrCode], 0
0x1800610c2  jz      short loc_1800610D7
0x1800610c4  jmp     short loc_1800610D1
0x1800610c6  mov     ecx, 57h ; 'W'; dwErrCode
0x1800610cb  call    cs:__imp_SetLastError
0x1800610d1  mov     r13d, 1
0x1800610d7  test    r13d, r13d
0x1800610da  mov     r13, [rbp+lpMem]
0x1800610de  jnz     short loc_180061113
0x1800610e0  mov     r9, [r14+28h]
0x1800610e4  lea     r8, aDeletepathdire; "DeletePathDirectoryCallback: Spoofing d"...
0x1800610eb  mov     edx, 3000000h
0x1800610f0  mov     qword ptr [rsp+60h+dwCreationDisposition], r13
0x1800610f5  lea     rcx, g_WdsLibLog
0x1800610fc  call    LibLog
0x180061101  mov     ecx, 2A9h; dwErrCode
0x180061106  xor     edi, edi
0x180061108  xor     r15d, r15d
0x18006110b  call    cs:__imp_SetLastError
0x180061111  xor     esi, esi
0x180061113  test    r13, r13
0x180061116  jz      short loc_18006112C
0x180061118  call    cs:__imp_GetProcessHeap
0x18006111e  mov     r8, r13; lpMem
0x180061121  xor     edx, edx; dwFlags
0x180061123  mov     rcx, rax; hHeap
0x180061126  call    cs:__imp_HeapFree
0x18006112c  mov     r13, [rbp+arg_8]
0x180061130  test    edi, edi
0x180061132  jz      short loc_18006118A
0x180061134  mov     eax, [rbx+8]
0x180061137  lea     rdx, DeletePathDirectoryCallback
0x18006113e  mov     rcx, [r14+28h]; lpFileName
0x180061142  mov     r9, rbx
0x180061145  mov     r8, r13
0x180061148  mov     [rsp+60h+dwCreationDisposition], eax; int
0x18006114c  call    EnumeratePathEx
0x180061151  cmp     eax, 1
0x180061154  jnz     short loc_180061185
0x180061156  mov     rcx, [r14+28h]
0x18006115a  mov     r15d, eax
0x18006115d  test    rcx, rcx
0x180061160  jnz     short loc_18006116A
0x180061162  lea     ecx, [rax+56h]
0x180061165  jmp     loc_180060F8B
0x18006116a  mov     edx, [rbx+0Ch]
0x18006116d  and     edx, 21h
0x180061170  jnz     short loc_180061179
0x180061172  call    WdsRemoveDirectory
0x180061177  jmp     short loc_18006117E
0x180061179  call    DeleteFileEx2
0x18006117e  cmp     eax, r15d
0x180061181  jnz     short loc_18006118E
0x180061183  jmp     short loc_18006119E
0x180061185  xor     r15d, r15d
0x180061188  jmp     short loc_18006118E
0x18006118a  test    esi, esi
0x18006118c  jnz     short loc_18006119E
0x18006118e  inc     dword ptr [rbx+4]
0x180061191  cmp     dword ptr [rbx], 0
0x180061194  jnz     short loc_18006119E
0x180061196  call    cs:__imp_GetLastError
0x18006119c  mov     [rbx], eax
0x18006119e  mov     eax, r15d
0x1800611a1  add     rsp, 60h
0x1800611a5  pop     r15
0x1800611a7  pop     r14
0x1800611a9  pop     r13
0x1800611ab  pop     rdi
0x1800611ac  pop     rsi
0x1800611ad  pop     rbx
0x1800611ae  pop     rbp
0x1800611af  retn
```
