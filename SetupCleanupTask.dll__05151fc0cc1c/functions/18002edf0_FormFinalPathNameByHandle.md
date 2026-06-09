# FormFinalPathNameByHandle

- ea: `0x18002edf0`
- end: `0x18002eed0`
- name: `FormFinalPathNameByHandle`
- size: `224`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180030590`

## callees

- `0x18002edf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eead`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eebd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eead`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002eebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eea3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002ee4d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002ee8e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002ee4d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18002ee8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ee72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ee72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ee61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ee61`

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
0x18002edf0  push    rbx
0x18002edf2  push    rbp
0x18002edf3  push    rsi
0x18002edf4  push    rdi
0x18002edf5  push    r14
0x18002edf7  sub     rsp, 20h
0x18002edfb  lea     rax, [rcx-1]
0x18002edff  mov     rbp, rcx
0x18002ee02  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ee06  ja      loc_18002EEB8
0x18002ee0c  test    edx, 0FFFFFFF8h
0x18002ee12  jnz     loc_18002EEB8
0x18002ee18  xor     edi, edi
0x18002ee1a  test    edx, edx
0x18002ee1c  jz      short loc_18002EE45
0x18002ee1e  sub     edx, 1
0x18002ee21  jz      short loc_18002EE40
0x18002ee23  mov     edi, 2
0x18002ee28  sub     edx, 1
0x18002ee2b  jz      short loc_18002EE45
0x18002ee2d  cmp     edx, edi
0x18002ee2f  jz      short loc_18002EE39
0x18002ee31  lea     ecx, [rdi+30h]; hFile
0x18002ee34  jmp     loc_18002EEBD
0x18002ee39  mov     edi, 4
0x18002ee3e  jmp     short loc_18002EE45
0x18002ee40  mov     edi, 1
0x18002ee45  mov     r9d, edi; dwFlags
0x18002ee48  xor     r8d, r8d; cchFilePath
0x18002ee4b  xor     edx, edx; lpszFilePath
0x18002ee4d  call    cs:__imp_GetFinalPathNameByHandleW
0x18002ee53  test    eax, eax
0x18002ee55  jz      short loc_18002EEA1
0x18002ee57  lea     r14d, [rax+1]
0x18002ee5b  mov     ebx, r14d
0x18002ee5e  add     rbx, rbx
0x18002ee61  call    cs:__imp_GetProcessHeap
0x18002ee67  mov     r8, rbx; dwBytes
0x18002ee6a  mov     edx, 8; dwFlags
0x18002ee6f  mov     rcx, rax; hHeap
0x18002ee72  call    cs:__imp_HeapAlloc
0x18002ee78  mov     rsi, rax
0x18002ee7b  test    rax, rax
0x18002ee7e  jz      short loc_18002EE9A
0x18002ee80  mov     r9d, edi; dwFlags
0x18002ee83  mov     r8d, r14d; cchFilePath
0x18002ee86  mov     rdx, rax; lpszFilePath
0x18002ee89  mov     rcx, rbp; hFile
0x18002ee8c  xor     ebx, ebx
0x18002ee8e  call    cs:__imp_GetFinalPathNameByHandleW
0x18002ee94  test    eax, eax
0x18002ee96  jnz     short loc_18002EEAB
0x18002ee98  jmp     short loc_18002EEA3
0x18002ee9a  mov     ebx, 0Eh
0x18002ee9f  jmp     short loc_18002EEAB
0x18002eea1  xor     esi, esi
0x18002eea3  call    cs:__imp_GetLastError
0x18002eea9  mov     ebx, eax
0x18002eeab  mov     ecx, ebx; dwErrCode
0x18002eead  call    cs:__imp_SetLastError
0x18002eeb3  mov     rax, rsi
0x18002eeb6  jmp     short loc_18002EEC5
0x18002eeb8  mov     ecx, 57h ; 'W'; dwErrCode
0x18002eebd  call    cs:__imp_SetLastError
0x18002eec3  xor     eax, eax
0x18002eec5  add     rsp, 20h
0x18002eec9  pop     r14
0x18002eecb  pop     rdi
0x18002eecc  pop     rsi
0x18002eecd  pop     rbp
0x18002eece  pop     rbx
0x18002eecf  retn
```
