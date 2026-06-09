# FormFinalPathNameByHandle

- ea: `0x18003cc94`
- end: `0x18003cd74`
- name: `FormFinalPathNameByHandle`
- size: `224`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x18003cd7c`
- `0x18003e3e0`

## callees

- `0x18003cc94`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003ccf1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003cd32`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003ccf1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18003cd32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cd05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003cd05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cd16`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003cd16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cd51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cd61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cd51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003cd61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cd47`

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
0x18003cc94  push    rbx
0x18003cc96  push    rbp
0x18003cc97  push    rsi
0x18003cc98  push    rdi
0x18003cc99  push    r14
0x18003cc9b  sub     rsp, 20h
0x18003cc9f  lea     rax, [rcx-1]
0x18003cca3  mov     rbp, rcx
0x18003cca6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003ccaa  ja      loc_18003CD5C
0x18003ccb0  test    edx, 0FFFFFFF8h
0x18003ccb6  jnz     loc_18003CD5C
0x18003ccbc  xor     edi, edi
0x18003ccbe  test    edx, edx
0x18003ccc0  jz      short loc_18003CCE9
0x18003ccc2  sub     edx, 1
0x18003ccc5  jz      short loc_18003CCE4
0x18003ccc7  mov     edi, 2
0x18003cccc  sub     edx, 1
0x18003cccf  jz      short loc_18003CCE9
0x18003ccd1  cmp     edx, edi
0x18003ccd3  jz      short loc_18003CCDD
0x18003ccd5  lea     ecx, [rdi+30h]; hFile
0x18003ccd8  jmp     loc_18003CD61
0x18003ccdd  mov     edi, 4
0x18003cce2  jmp     short loc_18003CCE9
0x18003cce4  mov     edi, 1
0x18003cce9  mov     r9d, edi; dwFlags
0x18003ccec  xor     r8d, r8d; cchFilePath
0x18003ccef  xor     edx, edx; lpszFilePath
0x18003ccf1  call    cs:__imp_GetFinalPathNameByHandleW
0x18003ccf7  test    eax, eax
0x18003ccf9  jz      short loc_18003CD45
0x18003ccfb  lea     r14d, [rax+1]
0x18003ccff  mov     ebx, r14d
0x18003cd02  add     rbx, rbx
0x18003cd05  call    cs:__imp_GetProcessHeap
0x18003cd0b  mov     r8, rbx; dwBytes
0x18003cd0e  mov     edx, 8; dwFlags
0x18003cd13  mov     rcx, rax; hHeap
0x18003cd16  call    cs:__imp_HeapAlloc
0x18003cd1c  mov     rsi, rax
0x18003cd1f  test    rax, rax
0x18003cd22  jz      short loc_18003CD3E
0x18003cd24  mov     r9d, edi; dwFlags
0x18003cd27  mov     r8d, r14d; cchFilePath
0x18003cd2a  mov     rdx, rax; lpszFilePath
0x18003cd2d  mov     rcx, rbp; hFile
0x18003cd30  xor     ebx, ebx
0x18003cd32  call    cs:__imp_GetFinalPathNameByHandleW
0x18003cd38  test    eax, eax
0x18003cd3a  jnz     short loc_18003CD4F
0x18003cd3c  jmp     short loc_18003CD47
0x18003cd3e  mov     ebx, 0Eh
0x18003cd43  jmp     short loc_18003CD4F
0x18003cd45  xor     esi, esi
0x18003cd47  call    cs:__imp_GetLastError
0x18003cd4d  mov     ebx, eax
0x18003cd4f  mov     ecx, ebx; dwErrCode
0x18003cd51  call    cs:__imp_SetLastError
0x18003cd57  mov     rax, rsi
0x18003cd5a  jmp     short loc_18003CD69
0x18003cd5c  mov     ecx, 57h ; 'W'; dwErrCode
0x18003cd61  call    cs:__imp_SetLastError
0x18003cd67  xor     eax, eax
0x18003cd69  add     rsp, 20h
0x18003cd6d  pop     r14
0x18003cd6f  pop     rdi
0x18003cd70  pop     rsi
0x18003cd71  pop     rbp
0x18003cd72  pop     rbx
0x18003cd73  retn
```
