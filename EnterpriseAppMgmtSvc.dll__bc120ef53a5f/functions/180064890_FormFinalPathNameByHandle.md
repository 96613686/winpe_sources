# FormFinalPathNameByHandle

- ea: `0x180064890`
- end: `0x18006499b`
- name: `FormFinalPathNameByHandle`
- size: `267`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1800649a4`
- `0x180067990`

## callees

- `0x180064890`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006491e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006491e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064907`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180064907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006495b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006495b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006496b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064981`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006496b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064981`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800648ed`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180064940`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800648ed`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180064940`

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
0x180064890  push    rbx
0x180064892  push    rbp
0x180064893  push    rsi
0x180064894  push    rdi
0x180064895  push    r14
0x180064897  sub     rsp, 20h
0x18006489b  lea     rax, [rcx-1]
0x18006489f  mov     rbp, rcx
0x1800648a2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800648a6  ja      loc_18006497C
0x1800648ac  test    edx, 0FFFFFFF8h
0x1800648b2  jnz     loc_18006497C
0x1800648b8  xor     edi, edi
0x1800648ba  test    edx, edx
0x1800648bc  jz      short loc_1800648E5
0x1800648be  sub     edx, 1
0x1800648c1  jz      short loc_1800648E0
0x1800648c3  mov     edi, 2
0x1800648c8  sub     edx, 1
0x1800648cb  jz      short loc_1800648E5
0x1800648cd  cmp     edx, edi
0x1800648cf  jz      short loc_1800648D9
0x1800648d1  lea     ecx, [rdi+30h]; hFile
0x1800648d4  jmp     loc_180064981
0x1800648d9  mov     edi, 4
0x1800648de  jmp     short loc_1800648E5
0x1800648e0  mov     edi, 1
0x1800648e5  mov     r9d, edi; dwFlags
0x1800648e8  xor     r8d, r8d; cchFilePath
0x1800648eb  xor     edx, edx; lpszFilePath
0x1800648ed  call    cs:__imp_GetFinalPathNameByHandleW
0x1800648f4  nop     dword ptr [rax+rax+00h]
0x1800648f9  test    eax, eax
0x1800648fb  jz      short loc_180064959
0x1800648fd  lea     r14d, [rax+1]
0x180064901  mov     ebx, r14d
0x180064904  add     rbx, rbx
0x180064907  call    cs:__imp_GetProcessHeap
0x18006490e  nop     dword ptr [rax+rax+00h]
0x180064913  mov     r8, rbx; dwBytes
0x180064916  mov     edx, 8; dwFlags
0x18006491b  mov     rcx, rax; hHeap
0x18006491e  call    cs:__imp_HeapAlloc
0x180064925  nop     dword ptr [rax+rax+00h]
0x18006492a  mov     rsi, rax
0x18006492d  test    rax, rax
0x180064930  jz      short loc_180064952
0x180064932  mov     r9d, edi; dwFlags
0x180064935  mov     r8d, r14d; cchFilePath
0x180064938  mov     rdx, rax; lpszFilePath
0x18006493b  mov     rcx, rbp; hFile
0x18006493e  xor     ebx, ebx
0x180064940  call    cs:__imp_GetFinalPathNameByHandleW
0x180064947  nop     dword ptr [rax+rax+00h]
0x18006494c  test    eax, eax
0x18006494e  jnz     short loc_180064969
0x180064950  jmp     short loc_18006495B
0x180064952  mov     ebx, 0Eh
0x180064957  jmp     short loc_180064969
0x180064959  xor     esi, esi
0x18006495b  call    cs:__imp_GetLastError
0x180064962  nop     dword ptr [rax+rax+00h]
0x180064967  mov     ebx, eax
0x180064969  mov     ecx, ebx; dwErrCode
0x18006496b  call    cs:__imp_SetLastError
0x180064972  nop     dword ptr [rax+rax+00h]
0x180064977  mov     rax, rsi
0x18006497a  jmp     short loc_18006498F
0x18006497c  mov     ecx, 57h ; 'W'; dwErrCode
0x180064981  call    cs:__imp_SetLastError
0x180064988  nop     dword ptr [rax+rax+00h]
0x18006498d  xor     eax, eax
0x18006498f  add     rsp, 20h
0x180064993  pop     r14
0x180064995  pop     rdi
0x180064996  pop     rsi
0x180064997  pop     rbp
0x180064998  pop     rbx
0x180064999  retn
```
