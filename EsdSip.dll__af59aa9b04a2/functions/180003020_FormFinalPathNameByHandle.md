# FormFinalPathNameByHandle

- ea: `0x180003020`
- end: `0x1800030c1`
- name: `FormFinalPathNameByHandle`
- size: `161`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180002060`

## callees

- `0x180003020`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800030a0`
- `KERNEL32!SetLastError` at `0x1800030b0`
- `KERNEL32!SetLastError` at `0x1800030a0`
- `KERNEL32!SetLastError` at `0x1800030b0`
- `KERNEL32!GetProcessHeap` at `0x180003053`
- `KERNEL32!GetProcessHeap` at `0x180003053`
- `KERNEL32!GetLastError` at `0x180003096`
- `KERNEL32!GetLastError` at `0x180003096`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180003041`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180003081`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180003041`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x180003081`
- `KERNEL32!HeapAlloc` at `0x180003064`
- `KERNEL32!HeapAlloc` at `0x180003064`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameByHandle(char *hFile)
{
  DWORD FinalPathNameByHandleW; // eax
  DWORD v3; // ebp
  SIZE_T v4; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  DWORD LastError; // ebx

  if ( (unsigned __int64)(hFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, 1u);
    if ( FinalPathNameByHandleW )
    {
      v3 = FinalPathNameByHandleW + 1;
      v4 = 2LL * (FinalPathNameByHandleW + 1);
      ProcessHeap = GetProcessHeap();
      v6 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v4);
      v7 = v6;
      if ( v6 )
      {
        LastError = 0;
        if ( !GetFinalPathNameByHandleW(hFile, v6, v3, 1u) )
          goto LABEL_8;
      }
      else
      {
        LastError = 14;
      }
LABEL_9:
      SetLastError(LastError);
      return v7;
    }
    v7 = 0;
LABEL_8:
    LastError = GetLastError();
    goto LABEL_9;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180003020  push    rbx
0x180003022  push    rbp
0x180003023  push    rsi
0x180003024  push    rdi
0x180003025  sub     rsp, 28h
0x180003029  lea     rax, [rcx-1]
0x18000302d  mov     rsi, rcx
0x180003030  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003034  ja      short loc_1800030AB
0x180003036  mov     r9d, 1; dwFlags
0x18000303c  xor     r8d, r8d; cchFilePath
0x18000303f  xor     edx, edx; lpszFilePath
0x180003041  call    cs:__imp_GetFinalPathNameByHandleW
0x180003047  test    eax, eax
0x180003049  jz      short loc_180003094
0x18000304b  lea     ebp, [rax+1]
0x18000304e  mov     ebx, ebp
0x180003050  add     rbx, rbx
0x180003053  call    cs:__imp_GetProcessHeap
0x180003059  mov     r8, rbx; dwBytes
0x18000305c  mov     edx, 8; dwFlags
0x180003061  mov     rcx, rax; hHeap
0x180003064  call    cs:__imp_HeapAlloc
0x18000306a  mov     rdi, rax
0x18000306d  test    rax, rax
0x180003070  jz      short loc_18000308D
0x180003072  xor     ebx, ebx
0x180003074  mov     r8d, ebp; cchFilePath
0x180003077  mov     rdx, rax; lpszFilePath
0x18000307a  mov     rcx, rsi; hFile
0x18000307d  lea     r9d, [rbx+1]; dwFlags
0x180003081  call    cs:__imp_GetFinalPathNameByHandleW
0x180003087  test    eax, eax
0x180003089  jnz     short loc_18000309E
0x18000308b  jmp     short loc_180003096
0x18000308d  mov     ebx, 0Eh
0x180003092  jmp     short loc_18000309E
0x180003094  xor     edi, edi
0x180003096  call    cs:__imp_GetLastError
0x18000309c  mov     ebx, eax
0x18000309e  mov     ecx, ebx; dwErrCode
0x1800030a0  call    cs:__imp_SetLastError
0x1800030a6  mov     rax, rdi
0x1800030a9  jmp     short loc_1800030B8
0x1800030ab  mov     ecx, 57h ; 'W'; dwErrCode
0x1800030b0  call    cs:__imp_SetLastError
0x1800030b6  xor     eax, eax
0x1800030b8  add     rsp, 28h
0x1800030bc  pop     rdi
0x1800030bd  pop     rsi
0x1800030be  pop     rbp
0x1800030bf  pop     rbx
0x1800030c0  retn
```
