# CreatePath

- ea: `0x140021f6c`
- end: `0x1400220ca`
- name: `CreatePath`
- size: `350`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140025770`
- `0x1400258e4`
- `0x140055684`

## callees

- `0x140001d28`
- `0x140021f6c`
- `0x140022960`
- `0x140022c14`
- `0x140024510`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14002206f`
- `KERNEL32!HeapFree` at `0x14002206f`
- `KERNEL32!GetProcessHeap` at `0x14002205b`
- `KERNEL32!GetProcessHeap` at `0x14002205b`
- `KERNEL32!CreateDirectoryW` at `0x140021ff1`
- `KERNEL32!CreateDirectoryW` at `0x140022016`
- `KERNEL32!CreateDirectoryW` at `0x140021ff1`
- `KERNEL32!CreateDirectoryW` at `0x140022016`
- `KERNEL32!GetLastError` at `0x140022027`
- `KERNEL32!GetLastError` at `0x14002207d`
- `KERNEL32!GetLastError` at `0x140022027`
- `KERNEL32!GetLastError` at `0x14002207d`
- `KERNEL32!SetLastError` at `0x14002208d`
- `KERNEL32!SetLastError` at `0x1400220a2`
- `KERNEL32!SetLastError` at `0x14002208d`
- `KERNEL32!SetLastError` at `0x1400220a2`

## string_xrefs

- `0x140022036`: `CreatePath: Unable to create [%s]; GLE = 0x%x`

## pseudocode

```c
__int64 __fastcall CreatePath(unsigned __int16 *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // ebp
  WCHAR *v4; // rdi
  const wchar_t *i; // rcx
  wchar_t *v6; // rax
  wchar_t *v7; // r14
  HANDLE ProcessHeap; // rax

  v1 = 0;
  LastError = 0;
  if ( a1 && *a1 )
  {
    v4 = (WCHAR *)PrepareUnicodePathEx(a1);
    if ( v4 )
    {
      for ( i = v4; ; i = v7 + 1 )
      {
        v6 = wcschr_0(i, 0x5Cu);
        v7 = v6;
        if ( !v6 )
          break;
        *v6 = 0;
        if ( !(unsigned int)DirectoryExists(v4) )
          CreateDirectoryW(v4, 0);
        *v7 = 92;
      }
      if ( (unsigned int)DirectoryExists(v4) == 1 || CreateDirectoryW(v4, 0) )
      {
        v1 = 1;
      }
      else
      {
        LastError = GetLastError();
        LibLog(&g_WdsLibLog, 50331648, L"CreatePath: Unable to create [%s]; GLE = 0x%x", a1, LastError);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    else
    {
      LastError = GetLastError();
    }
    SetLastError(LastError);
    return v1;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x140021f6c  mov     rax, rsp
0x140021f6f  mov     [rax+10h], rbx
0x140021f73  mov     [rax+18h], rbp
0x140021f77  mov     [rax+20h], rsi
0x140021f7b  push    rdi
0x140021f7c  push    r14
0x140021f7e  push    r15
0x140021f80  sub     rsp, 30h
0x140021f84  xor     ebx, ebx
0x140021f86  mov     rsi, rcx
0x140021f89  mov     [rax+8], rbx
0x140021f8d  mov     ebp, ebx
0x140021f8f  test    rcx, rcx
0x140021f92  jz      loc_14002209D
0x140021f98  cmp     bx, [rcx]
0x140021f9b  jz      loc_14002209D
0x140021fa1  lea     rdx, [rax+8]
0x140021fa5  call    PrepareUnicodePathEx
0x140021faa  mov     rdi, rax
0x140021fad  test    rax, rax
0x140021fb0  jz      loc_14002207D
0x140021fb6  mov     rax, [rsp+48h+arg_0]
0x140021fbb  lea     rcx, [rax+2]
0x140021fbf  test    rax, rax
0x140021fc2  jnz     short loc_140021FC7
0x140021fc4  mov     rcx, rdi; Str
0x140021fc7  mov     r15d, 5Ch ; '\'
0x140021fcd  mov     edx, r15d; Ch
0x140021fd0  call    wcschr_0
0x140021fd5  mov     r14, rax
0x140021fd8  mov     rcx, rdi
0x140021fdb  test    rax, rax
0x140021fde  jz      short loc_140022007
0x140021fe0  mov     [rax], bx
0x140021fe3  call    DirectoryExists
0x140021fe8  test    eax, eax
0x140021fea  jnz     short loc_140021FFD
0x140021fec  xor     edx, edx; lpSecurityAttributes
0x140021fee  mov     rcx, rdi; lpPathName
0x140021ff1  call    cs:__imp_CreateDirectoryW
0x140021ff8  nop     dword ptr [rax+rax+00h]
0x140021ffd  mov     [r14], r15w
0x140022001  lea     rcx, [r14+2]
0x140022005  jmp     short loc_140021FCD
0x140022007  call    DirectoryExists
0x14002200c  cmp     eax, 1
0x14002200f  jz      short loc_140022056
0x140022011  xor     edx, edx; lpSecurityAttributes
0x140022013  mov     rcx, rdi; lpPathName
0x140022016  call    cs:__imp_CreateDirectoryW
0x14002201d  nop     dword ptr [rax+rax+00h]
0x140022022  cmp     eax, 1
0x140022025  jz      short loc_140022056
0x140022027  call    cs:__imp_GetLastError
0x14002202e  nop     dword ptr [rax+rax+00h]
0x140022033  mov     r9, rsi
0x140022036  lea     r8, aCreatepathUnab; "CreatePath: Unable to create [%s]; GLE "...
0x14002203d  lea     rcx, g_WdsLibLog
0x140022044  mov     [rsp+48h+var_28], eax
0x140022048  mov     edx, 3000000h
0x14002204d  mov     ebp, eax
0x14002204f  call    LibLog
0x140022054  jmp     short loc_14002205B
0x140022056  mov     ebx, 1
0x14002205b  call    cs:__imp_GetProcessHeap
0x140022062  nop     dword ptr [rax+rax+00h]
0x140022067  mov     r8, rdi; lpMem
0x14002206a  xor     edx, edx; dwFlags
0x14002206c  mov     rcx, rax; hHeap
0x14002206f  call    cs:__imp_HeapFree
0x140022076  nop     dword ptr [rax+rax+00h]
0x14002207b  jmp     short loc_14002208B
0x14002207d  call    cs:__imp_GetLastError
0x140022084  nop     dword ptr [rax+rax+00h]
0x140022089  mov     ebp, eax
0x14002208b  mov     ecx, ebp; dwErrCode
0x14002208d  call    cs:__imp_SetLastError
0x140022094  nop     dword ptr [rax+rax+00h]
0x140022099  mov     eax, ebx
0x14002209b  jmp     short loc_1400220B0
0x14002209d  mov     ecx, 57h ; 'W'; dwErrCode
0x1400220a2  call    cs:__imp_SetLastError
0x1400220a9  nop     dword ptr [rax+rax+00h]
0x1400220ae  xor     eax, eax
0x1400220b0  mov     rbx, [rsp+48h+arg_8]
0x1400220b5  mov     rbp, [rsp+48h+arg_10]
0x1400220ba  mov     rsi, [rsp+48h+arg_18]
0x1400220bf  add     rsp, 30h
0x1400220c3  pop     r15
0x1400220c5  pop     r14
0x1400220c7  pop     rdi
0x1400220c8  retn
```
