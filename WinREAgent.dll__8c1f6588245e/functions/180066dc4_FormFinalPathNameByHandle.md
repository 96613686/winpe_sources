# FormFinalPathNameByHandle

- ea: `0x180066dc4`
- end: `0x180066ea4`
- name: `FormFinalPathNameByHandle`
- size: `224`
- prototype: `WCHAR *__fastcall(char *hFile, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180066eac`
- `0x180068ae8`

## callees

- `0x180066dc4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180066e81`
- `KERNEL32!SetLastError` at `0x180066e91`
- `KERNEL32!SetLastError` at `0x180066e81`
- `KERNEL32!SetLastError` at `0x180066e91`
- `KERNEL32!GetLastError` at `0x180066e77`
- `KERNEL32!GetLastError` at `0x180066e77`
- `KERNEL32!HeapAlloc` at `0x180066e46`
- `KERNEL32!HeapAlloc` at `0x180066e46`
- `KERNEL32!GetProcessHeap` at `0x180066e35`
- `KERNEL32!GetProcessHeap` at `0x180066e35`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180066e21`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180066e62`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180066e21`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180066e62`

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
0x180066dc4  push    rbx
0x180066dc6  push    rbp
0x180066dc7  push    rsi
0x180066dc8  push    rdi
0x180066dc9  push    r14
0x180066dcb  sub     rsp, 20h
0x180066dcf  lea     rax, [rcx-1]
0x180066dd3  mov     rbp, rcx
0x180066dd6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180066dda  ja      loc_180066E8C
0x180066de0  test    edx, 0FFFFFFF8h
0x180066de6  jnz     loc_180066E8C
0x180066dec  xor     edi, edi
0x180066dee  test    edx, edx
0x180066df0  jz      short loc_180066E19
0x180066df2  sub     edx, 1
0x180066df5  jz      short loc_180066E14
0x180066df7  mov     edi, 2
0x180066dfc  sub     edx, 1
0x180066dff  jz      short loc_180066E19
0x180066e01  cmp     edx, edi
0x180066e03  jz      short loc_180066E0D
0x180066e05  lea     ecx, [rdi+30h]; hFile
0x180066e08  jmp     loc_180066E91
0x180066e0d  mov     edi, 4
0x180066e12  jmp     short loc_180066E19
0x180066e14  mov     edi, 1
0x180066e19  mov     r9d, edi; dwFlags
0x180066e1c  xor     r8d, r8d; cchFilePath
0x180066e1f  xor     edx, edx; lpszFilePath
0x180066e21  call    cs:__imp_GetFinalPathNameByHandleW
0x180066e27  test    eax, eax
0x180066e29  jz      short loc_180066E75
0x180066e2b  lea     r14d, [rax+1]
0x180066e2f  mov     ebx, r14d
0x180066e32  add     rbx, rbx
0x180066e35  call    cs:__imp_GetProcessHeap
0x180066e3b  mov     r8, rbx; dwBytes
0x180066e3e  mov     edx, 8; dwFlags
0x180066e43  mov     rcx, rax; hHeap
0x180066e46  call    cs:__imp_HeapAlloc
0x180066e4c  mov     rsi, rax
0x180066e4f  test    rax, rax
0x180066e52  jz      short loc_180066E6E
0x180066e54  mov     r9d, edi; dwFlags
0x180066e57  mov     r8d, r14d; cchFilePath
0x180066e5a  mov     rdx, rax; lpszFilePath
0x180066e5d  mov     rcx, rbp; hFile
0x180066e60  xor     ebx, ebx
0x180066e62  call    cs:__imp_GetFinalPathNameByHandleW
0x180066e68  test    eax, eax
0x180066e6a  jnz     short loc_180066E7F
0x180066e6c  jmp     short loc_180066E77
0x180066e6e  mov     ebx, 0Eh
0x180066e73  jmp     short loc_180066E7F
0x180066e75  xor     esi, esi
0x180066e77  call    cs:__imp_GetLastError
0x180066e7d  mov     ebx, eax
0x180066e7f  mov     ecx, ebx; dwErrCode
0x180066e81  call    cs:__imp_SetLastError
0x180066e87  mov     rax, rsi
0x180066e8a  jmp     short loc_180066E99
0x180066e8c  mov     ecx, 57h ; 'W'; dwErrCode
0x180066e91  call    cs:__imp_SetLastError
0x180066e97  xor     eax, eax
0x180066e99  add     rsp, 20h
0x180066e9d  pop     r14
0x180066e9f  pop     rdi
0x180066ea0  pop     rsi
0x180066ea1  pop     rbp
0x180066ea2  pop     rbx
0x180066ea3  retn
```
