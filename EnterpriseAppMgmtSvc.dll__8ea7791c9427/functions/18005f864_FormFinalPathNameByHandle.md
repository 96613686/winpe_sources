# FormFinalPathNameByHandle

- ea: `0x18005f864`
- end: `0x18005f944`
- name: `FormFinalPathNameByHandle`
- size: `224`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x18005f94c`
- `0x1800623f4`

## callees

- `0x18005f864`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f8e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005f8e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f8d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005f8d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f917`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f921`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f931`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f921`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f931`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005f8c1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005f902`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005f8c1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005f902`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameByHandle(char *hFile, int a2)
{
  DWORD v3; // edi
  int v4; // edx
  int v5; // edx
  DWORD v6; // ecx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v8; // r14d
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rsi
  DWORD LastError; // ebx

  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL || (a2 & 0xFFFFFFF8) != 0 )
  {
    v6 = 87;
    goto LABEL_19;
  }
  v3 = 0;
  if ( !a2 )
  {
LABEL_10:
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, v3);
    if ( FinalPathNameByHandleW )
    {
      v8 = FinalPathNameByHandleW + 1;
      v9 = 2LL * (FinalPathNameByHandleW + 1);
      ProcessHeap = GetProcessHeap();
      v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v9);
      v12 = v11;
      if ( v11 )
      {
        LastError = 0;
        if ( !GetFinalPathNameByHandleW(hFile, v11, v8, v3) )
          goto LABEL_16;
      }
      else
      {
        LastError = 14;
      }
LABEL_17:
      SetLastError(LastError);
      return v12;
    }
    v12 = 0;
LABEL_16:
    LastError = GetLastError();
    goto LABEL_17;
  }
  v4 = a2 - 1;
  if ( !v4 )
  {
    v3 = 1;
    goto LABEL_10;
  }
  v3 = 2;
  v5 = v4 - 1;
  if ( !v5 )
    goto LABEL_10;
  if ( v5 == 2 )
  {
    v3 = 4;
    goto LABEL_10;
  }
  v6 = 50;
LABEL_19:
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18005f864  push    rbx
0x18005f866  push    rbp
0x18005f867  push    rsi
0x18005f868  push    rdi
0x18005f869  push    r14
0x18005f86b  sub     rsp, 20h
0x18005f86f  lea     rax, [rcx-1]
0x18005f873  mov     rbp, rcx
0x18005f876  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005f87a  ja      loc_18005F92C
0x18005f880  test    edx, 0FFFFFFF8h
0x18005f886  jnz     loc_18005F92C
0x18005f88c  xor     edi, edi
0x18005f88e  test    edx, edx
0x18005f890  jz      short loc_18005F8B9
0x18005f892  sub     edx, 1
0x18005f895  jz      short loc_18005F8B4
0x18005f897  mov     edi, 2
0x18005f89c  sub     edx, 1
0x18005f89f  jz      short loc_18005F8B9
0x18005f8a1  cmp     edx, edi
0x18005f8a3  jz      short loc_18005F8AD
0x18005f8a5  lea     ecx, [rdi+30h]; hFile
0x18005f8a8  jmp     loc_18005F931
0x18005f8ad  mov     edi, 4
0x18005f8b2  jmp     short loc_18005F8B9
0x18005f8b4  mov     edi, 1
0x18005f8b9  mov     r9d, edi; dwFlags
0x18005f8bc  xor     r8d, r8d; cchFilePath
0x18005f8bf  xor     edx, edx; lpszFilePath
0x18005f8c1  call    cs:__imp_GetFinalPathNameByHandleW
0x18005f8c7  test    eax, eax
0x18005f8c9  jz      short loc_18005F915
0x18005f8cb  lea     r14d, [rax+1]
0x18005f8cf  mov     ebx, r14d
0x18005f8d2  add     rbx, rbx
0x18005f8d5  call    cs:__imp_GetProcessHeap
0x18005f8db  mov     r8, rbx; dwBytes
0x18005f8de  mov     edx, 8; dwFlags
0x18005f8e3  mov     rcx, rax; hHeap
0x18005f8e6  call    cs:__imp_HeapAlloc
0x18005f8ec  mov     rsi, rax
0x18005f8ef  test    rax, rax
0x18005f8f2  jz      short loc_18005F90E
0x18005f8f4  mov     r9d, edi; dwFlags
0x18005f8f7  mov     r8d, r14d; cchFilePath
0x18005f8fa  mov     rdx, rax; lpszFilePath
0x18005f8fd  mov     rcx, rbp; hFile
0x18005f900  xor     ebx, ebx
0x18005f902  call    cs:__imp_GetFinalPathNameByHandleW
0x18005f908  test    eax, eax
0x18005f90a  jnz     short loc_18005F91F
0x18005f90c  jmp     short loc_18005F917
0x18005f90e  mov     ebx, 0Eh
0x18005f913  jmp     short loc_18005F91F
0x18005f915  xor     esi, esi
0x18005f917  call    cs:__imp_GetLastError
0x18005f91d  mov     ebx, eax
0x18005f91f  mov     ecx, ebx; dwErrCode
0x18005f921  call    cs:__imp_SetLastError
0x18005f927  mov     rax, rsi
0x18005f92a  jmp     short loc_18005F939
0x18005f92c  mov     ecx, 57h ; 'W'; dwErrCode
0x18005f931  call    cs:__imp_SetLastError
0x18005f937  xor     eax, eax
0x18005f939  add     rsp, 20h
0x18005f93d  pop     r14
0x18005f93f  pop     rdi
0x18005f940  pop     rsi
0x18005f941  pop     rbp
0x18005f942  pop     rbx
0x18005f943  retn
```
