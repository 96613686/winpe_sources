# FormFinalPathNameByHandle

- ea: `0x1400220d0`
- end: `0x1400221f4`
- name: `FormFinalPathNameByHandle`
- size: `292`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1400221fc`
- `0x14002840c`

## callees

- `0x1400220d0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14002216d`
- `KERNEL32!HeapAlloc` at `0x14002216d`
- `KERNEL32!GetProcessHeap` at `0x140022156`
- `KERNEL32!GetProcessHeap` at `0x140022156`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14002213d`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14002218d`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14002213d`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x14002218d`
- `KERNEL32!GetLastError` at `0x14002219d`
- `KERNEL32!GetLastError` at `0x14002219d`
- `KERNEL32!SetLastError` at `0x1400221ad`
- `KERNEL32!SetLastError` at `0x1400221ca`
- `KERNEL32!SetLastError` at `0x1400221ad`
- `KERNEL32!SetLastError` at `0x1400221ca`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameByHandle(char *hFile, int a2)
{
  DWORD LastError; // edi
  WCHAR *v4; // rbx
  DWORD v5; // esi
  int v6; // edx
  int v7; // edx
  DWORD v8; // ecx
  DWORD FinalPathNameByHandleW; // ebp
  DWORD v10; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rax

  LastError = 0;
  v4 = 0;
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL || (a2 & 0xFFFFFFF8) != 0 )
  {
    v8 = 87;
    goto LABEL_17;
  }
  v5 = 0;
  if ( !a2 )
    goto LABEL_10;
  v6 = a2 - 1;
  if ( !v6 )
  {
    v5 = 1;
    goto LABEL_10;
  }
  v5 = 2;
  v7 = v6 - 1;
  if ( !v7 )
  {
LABEL_10:
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, 0, 0, v5);
    if ( !FinalPathNameByHandleW )
      goto LABEL_13;
    v10 = FinalPathNameByHandleW + 1;
    ProcessHeap = GetProcessHeap();
    v12 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * v10);
    v4 = v12;
    if ( !v12 )
    {
      LastError = 14;
      goto LABEL_14;
    }
    if ( !GetFinalPathNameByHandleW(hFile, v12, v10, v5) )
LABEL_13:
      LastError = GetLastError();
LABEL_14:
    SetLastError(LastError);
    return v4;
  }
  if ( v7 == 2 )
  {
    v5 = 4;
    goto LABEL_10;
  }
  v8 = 50;
LABEL_17:
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x1400220d0  mov     rax, rsp
0x1400220d3  mov     [rax+8], rbx
0x1400220d7  mov     [rax+10h], rbp
0x1400220db  mov     [rax+18h], rsi
0x1400220df  mov     [rax+20h], rdi
0x1400220e3  push    r14
0x1400220e5  sub     rsp, 20h
0x1400220e9  xor     edi, edi
0x1400220eb  lea     rax, [rcx-1]
0x1400220ef  mov     r14, rcx
0x1400220f2  mov     ebx, edi
0x1400220f4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400220f8  ja      loc_1400221C5
0x1400220fe  test    edx, 0FFFFFFF8h
0x140022104  jnz     loc_1400221C5
0x14002210a  mov     esi, edi
0x14002210c  test    edx, edx
0x14002210e  jz      short loc_140022135
0x140022110  sub     edx, 1
0x140022113  jz      short loc_140022130
0x140022115  lea     esi, [rdi+2]
0x140022118  sub     edx, 1
0x14002211b  jz      short loc_140022135
0x14002211d  cmp     edx, esi
0x14002211f  jz      short loc_140022129
0x140022121  lea     ecx, [rdi+32h]; hFile
0x140022124  jmp     loc_1400221CA
0x140022129  mov     esi, 4
0x14002212e  jmp     short loc_140022135
0x140022130  mov     esi, 1
0x140022135  mov     r9d, esi; dwFlags
0x140022138  xor     r8d, r8d; cchFilePath
0x14002213b  xor     edx, edx; lpszFilePath
0x14002213d  call    cs:__imp_GetFinalPathNameByHandleW
0x140022144  nop     dword ptr [rax+rax+00h]
0x140022149  mov     ebp, eax
0x14002214b  test    eax, eax
0x14002214d  jz      short loc_14002219D
0x14002214f  inc     ebp
0x140022151  mov     ebx, ebp
0x140022153  add     rbx, rbx
0x140022156  call    cs:__imp_GetProcessHeap
0x14002215d  nop     dword ptr [rax+rax+00h]
0x140022162  mov     r8, rbx; dwBytes
0x140022165  mov     edx, 8; dwFlags
0x14002216a  mov     rcx, rax; hHeap
0x14002216d  call    cs:__imp_HeapAlloc
0x140022174  nop     dword ptr [rax+rax+00h]
0x140022179  mov     rbx, rax
0x14002217c  test    rax, rax
0x14002217f  jz      short loc_1400221BE
0x140022181  mov     r9d, esi; dwFlags
0x140022184  mov     r8d, ebp; cchFilePath
0x140022187  mov     rdx, rax; lpszFilePath
0x14002218a  mov     rcx, r14; hFile
0x14002218d  call    cs:__imp_GetFinalPathNameByHandleW
0x140022194  nop     dword ptr [rax+rax+00h]
0x140022199  test    eax, eax
0x14002219b  jnz     short loc_1400221AB
0x14002219d  call    cs:__imp_GetLastError
0x1400221a4  nop     dword ptr [rax+rax+00h]
0x1400221a9  mov     edi, eax
0x1400221ab  mov     ecx, edi; dwErrCode
0x1400221ad  call    cs:__imp_SetLastError
0x1400221b4  nop     dword ptr [rax+rax+00h]
0x1400221b9  mov     rax, rbx
0x1400221bc  jmp     short loc_1400221D8
0x1400221be  mov     edi, 0Eh
0x1400221c3  jmp     short loc_1400221AB
0x1400221c5  mov     ecx, 57h ; 'W'; dwErrCode
0x1400221ca  call    cs:__imp_SetLastError
0x1400221d1  nop     dword ptr [rax+rax+00h]
0x1400221d6  xor     eax, eax
0x1400221d8  mov     rbx, [rsp+28h+arg_0]
0x1400221dd  mov     rbp, [rsp+28h+arg_8]
0x1400221e2  mov     rsi, [rsp+28h+arg_10]
0x1400221e7  mov     rdi, [rsp+28h+arg_18]
0x1400221ec  add     rsp, 20h
0x1400221f0  pop     r14
0x1400221f2  retn
```
