# WriteFileMultiByte(void *,ushort *,ulong,ulong *,_OVERLAPPED *)

- ea: `0x140020e78`
- end: `0x140020fe0`
- name: `?WriteFileMultiByte@@YAJPEAXPEAGKPEAKPEAU_OVERLAPPED@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCWCH lpWideCharStr, unsigned int, unsigned int *, struct _OVERLAPPED *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140007dd4`
- `0x140016bb4`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140020e78`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140020ec8`
- `KERNEL32!WideCharToMultiByte` at `0x140020f30`
- `KERNEL32!WideCharToMultiByte` at `0x140020ec8`
- `KERNEL32!WideCharToMultiByte` at `0x140020f30`
- `KERNEL32!HeapFree` at `0x140020fb3`
- `KERNEL32!HeapFree` at `0x140020fb3`
- `KERNEL32!HeapAlloc` at `0x140020ef2`
- `KERNEL32!HeapAlloc` at `0x140020ef2`
- `KERNEL32!GetProcessHeap` at `0x140020ede`
- `KERNEL32!GetProcessHeap` at `0x140020f9f`
- `KERNEL32!GetProcessHeap` at `0x140020ede`
- `KERNEL32!GetProcessHeap` at `0x140020f9f`
- `KERNEL32!GetLastError` at `0x140020f68`
- `KERNEL32!GetLastError` at `0x140020f68`
- `KERNEL32!WriteFile` at `0x140020f58`
- `KERNEL32!WriteFile` at `0x140020f58`

## pseudocode

```c
__int64 __fastcall WriteFileMultiByte(HANDLE hFile, LPCWCH lpWideCharStr, unsigned int a3, unsigned int *a4)
{
  int v7; // ebp
  CHAR *v8; // rbx
  unsigned int v9; // edi
  unsigned int cbMultiByte; // esi
  HANDLE ProcessHeap; // rax
  CHAR *lpMultiByteStr; // rax
  CHAR *v13; // rdx
  signed int LastError; // eax
  HANDLE v15; // rax

  v7 = a3 >> 1;
  v8 = 0;
  v9 = 0;
  cbMultiByte = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, a3 >> 1, 0, 0, 0, 0);
  if ( !cbMultiByte )
    goto LABEL_8;
  ProcessHeap = GetProcessHeap();
  lpMultiByteStr = (CHAR *)HeapAlloc(ProcessHeap, 0, cbMultiByte);
  v8 = lpMultiByteStr;
  if ( !lpMultiByteStr )
  {
    v8 = 0;
    v9 = -2147024882;
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_13;
  }
  if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v7, lpMultiByteStr, cbMultiByte, 0, 0) != cbMultiByte )
    goto LABEL_8;
  v13 = 0;
  if ( v8 )
    v13 = v8;
  if ( !WriteFile(hFile, v13, cbMultiByte, a4, 0) )
  {
LABEL_8:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v9 = -2147467259;
    }
    goto LABEL_12;
  }
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v8 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v8);
  }
  return v9;
}

```

## disassembly

```asm
0x140020e78  mov     rax, rsp
0x140020e7b  mov     [rax+8], rbx
0x140020e7f  mov     [rax+10h], rbp
0x140020e83  mov     [rax+18h], rsi
0x140020e87  push    rdi
0x140020e88  push    r12
0x140020e8a  push    r13
0x140020e8c  push    r14
0x140020e8e  push    r15
0x140020e90  sub     rsp, 40h
0x140020e94  xor     r13d, r13d
0x140020e97  mov     ebp, r8d
0x140020e9a  mov     [rax-30h], r13
0x140020e9e  mov     r15, r9
0x140020ea1  mov     [rax-38h], r13
0x140020ea5  mov     r14, rdx
0x140020ea8  mov     r12, rcx
0x140020eab  mov     [rax-40h], r13d
0x140020eaf  mov     r8, rdx; lpWideCharStr
0x140020eb2  shr     ebp, 1
0x140020eb4  mov     r9d, ebp; cchWideChar
0x140020eb7  mov     [rax-48h], r13
0x140020ebb  xor     edx, edx; dwFlags
0x140020ebd  mov     ecx, 0FDE9h; CodePage
0x140020ec2  mov     ebx, r13d
0x140020ec5  mov     edi, r13d
0x140020ec8  call    cs:__imp_WideCharToMultiByte
0x140020ecf  nop     dword ptr [rax+rax+00h]
0x140020ed4  mov     esi, eax
0x140020ed6  test    eax, eax
0x140020ed8  jz      loc_140020F68
0x140020ede  call    cs:__imp_GetProcessHeap
0x140020ee5  nop     dword ptr [rax+rax+00h]
0x140020eea  mov     r8d, esi; dwBytes
0x140020eed  xor     edx, edx; dwFlags
0x140020eef  mov     rcx, rax; hHeap
0x140020ef2  call    cs:__imp_HeapAlloc
0x140020ef9  nop     dword ptr [rax+rax+00h]
0x140020efe  mov     rbx, rax
0x140020f01  test    rax, rax
0x140020f04  jnz     short loc_140020F10
0x140020f06  mov     ebx, r13d
0x140020f09  mov     edi, 8007000Eh
0x140020f0e  jmp     short loc_140020F8C
0x140020f10  mov     [rsp+68h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x140020f15  mov     r9d, ebp; cchWideChar
0x140020f18  mov     [rsp+68h+lpDefaultChar], r13; lpDefaultChar
0x140020f1d  mov     r8, r14; lpWideCharStr
0x140020f20  mov     [rsp+68h+cbMultiByte], esi; cbMultiByte
0x140020f24  xor     edx, edx; dwFlags
0x140020f26  mov     ecx, 0FDE9h; CodePage
0x140020f2b  mov     [rsp+68h+lpMultiByteStr], rbx; lpMultiByteStr
0x140020f30  call    cs:__imp_WideCharToMultiByte
0x140020f37  nop     dword ptr [rax+rax+00h]
0x140020f3c  cmp     eax, esi
0x140020f3e  jnz     short loc_140020F68
0x140020f40  test    rbx, rbx
0x140020f43  mov     [rsp+68h+lpMultiByteStr], r13; lpOverlapped
0x140020f48  mov     rdx, r13
0x140020f4b  mov     r9, r15; lpNumberOfBytesWritten
0x140020f4e  cmovnz  rdx, rbx; lpBuffer
0x140020f52  mov     r8d, esi; nNumberOfBytesToWrite
0x140020f55  mov     rcx, r12; hFile
0x140020f58  call    cs:__imp_WriteFile
0x140020f5f  nop     dword ptr [rax+rax+00h]
0x140020f64  test    eax, eax
0x140020f66  jnz     short loc_140020F93
0x140020f68  call    cs:__imp_GetLastError
0x140020f6f  nop     dword ptr [rax+rax+00h]
0x140020f74  mov     edi, eax
0x140020f76  test    eax, eax
0x140020f78  jnz     short loc_140020F81
0x140020f7a  mov     edi, 80004005h
0x140020f7f  jmp     short loc_140020F8C
0x140020f81  jle     short loc_140020F8C
0x140020f83  movzx   edi, ax
0x140020f86  or      edi, 80070000h
0x140020f8c  mov     ecx, edi
0x140020f8e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140020f93  mov     ecx, edi
0x140020f95  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140020f9a  test    rbx, rbx
0x140020f9d  jz      short loc_140020FBF
0x140020f9f  call    cs:__imp_GetProcessHeap
0x140020fa6  nop     dword ptr [rax+rax+00h]
0x140020fab  mov     r8, rbx; lpMem
0x140020fae  xor     edx, edx; dwFlags
0x140020fb0  mov     rcx, rax; hHeap
0x140020fb3  call    cs:__imp_HeapFree
0x140020fba  nop     dword ptr [rax+rax+00h]
0x140020fbf  lea     r11, [rsp+68h+var_28]
0x140020fc4  mov     eax, edi
0x140020fc6  mov     rbx, [r11+30h]
0x140020fca  mov     rbp, [r11+38h]
0x140020fce  mov     rsi, [r11+40h]
0x140020fd2  mov     rsp, r11
0x140020fd5  pop     r15
0x140020fd7  pop     r14
0x140020fd9  pop     r13
0x140020fdb  pop     r12
0x140020fdd  pop     rdi
0x140020fde  retn
```
