# GPDebugPrintX(ulong,char *,...)

- ea: `0x180002fa0`
- end: `0x18000313c`
- name: `?GPDebugPrintX@@YAXKPEADZZ`
- size: `412`
- prototype: `void(int, char *, ...)`
- caller_count: `19`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001210`
- `0x180002c70`
- `0x1800069d0`
- `0x18000704c`
- `0x180008128`
- `0x180008b44`
- `0x180008fb4`
- `0x18000eda4`
- `0x18000f390`
- `0x18000fac4`
- `0x18000fb7c`
- `0x18000fd14`
- `0x18000ff88`
- `0x1800100c8`
- `0x1800101cc`
- `0x180010464`
- `0x1800106e0`
- `0x180010bc0`
- `0x180010e24`

## callees

- `0x180002fa0`
- `0x180003a30`
- `0x1800088e4`
- `0x180008af0`
- `0x1800097d0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800030af`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800030af`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180002ffc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180002ffc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003114`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003114`

## pseudocode

```c
void GPDebugPrintX(int a1, char *a2, ...)
{
  size_t *v2; // r8
  __int64 v3; // rbx
  __int64 v4; // rax
  size_t v5; // rdx
  CHAR *v6; // rcx
  unsigned __int64 v7; // rdx
  const char *v8; // r8
  __int64 v9; // rax
  __int64 v10; // rax
  void *v11; // r11
  _QWORD SystemTime[3]; // [rsp+58h] [rbp-B0h] BYREF
  CHAR OutputString[528]; // [rsp+78h] [rbp-90h] BYREF
  __int64 argList; // [rsp+2D8h] [rbp+1D0h] BYREF
  va_list va; // [rsp+2D8h] [rbp+1D0h]
  va_list va1; // [rsp+2E0h] [rbp+1D8h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  argList = va_arg(va1, _QWORD);
  if ( a1 )
  {
    memset(SystemTime, 0, sizeof(SystemTime));
    GetSystemTime((LPSYSTEMTIME)&SystemTime[1]);
    StringCchPrintfA(
      OutputString,
      0x200u,
      "%02d/%02d/%4d %2d:%2d:%2d.%08d:",
      WORD1(SystemTime[1]),
      HIWORD(SystemTime[1]),
      LOWORD(SystemTime[1]),
      LOWORD(SystemTime[2]),
      WORD1(SystemTime[2]),
      WORD2(SystemTime[2]),
      HIWORD(SystemTime[2]));
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( OutputString[v4] );
    v5 = (unsigned int)(512 - v4);
    if ( (_DWORD)v4 != 512 )
    {
      v6 = &OutputString[(unsigned int)v4];
      if ( (unsigned int)v5 > 0x7FFFFFFF )
        *v6 = 0;
      else
        StringVPrintfWorkerA(v6, v5, v2, a2, va);
    }
    OutputDebugStringA(OutputString);
    if ( GPLogFileHandle )
    {
      v9 = -1;
      do
        ++v9;
      while ( OutputString[v9] );
      v10 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v10 < 0x200 )
      {
        OutputString[v10] = 13;
        StringCchCatA(OutputString, v7, v8);
        do
          ++v3;
        while ( OutputString[v3] );
        WriteFile(v11, OutputString, v3, (LPDWORD)SystemTime, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x180002fa0  test    ecx, ecx
0x180002fa2  jz      locret_18000313B
0x180002fa8  mov     r11, rsp
0x180002fab  mov     [r11+10h], rdx
0x180002faf  mov     [r11+18h], r8
0x180002fb3  mov     [r11+20h], r9
0x180002fb7  push    rbp
0x180002fb8  push    rsi
0x180002fb9  push    rdi
0x180002fba  lea     rbp, [r11-1B8h]
0x180002fc1  sub     rsp, 2A0h
0x180002fc8  mov     rax, cs:__security_cookie
0x180002fcf  xor     rax, rsp
0x180002fd2  mov     [rbp+1B0h+var_30], rax
0x180002fd9  xor     esi, esi
0x180002fdb  mov     [r11-20h], rbx
0x180002fdf  xorps   xmm0, xmm0
0x180002fe2  mov     qword ptr [rsp+2B0h+SystemTime], rsi
0x180002fe7  lea     rcx, [rsp+2B0h+SystemTime+8]; lpSystemTime
0x180002fec  mov     dword ptr [rsp+2B0h+SystemTime], esi
0x180002ff0  movups  xmmword ptr [rsp+2B0h+SystemTime+8], xmm0
0x180002ff5  lea     rdi, [rbp+1B0h+arg_10]
0x180002ffc  call    cs:__imp_GetSystemTime
0x180003002  movzx   ecx, word ptr [rsp+2B0h+SystemTime+14h]
0x180003007  movzx   edx, word ptr [rsp+2B0h+SystemTime+12h]
0x18000300c  movzx   r8d, word ptr [rsp+2B0h+SystemTime+10h]
0x180003012  movzx   eax, word ptr [rsp+2B0h+SystemTime+16h]
0x180003017  movzx   r10d, word ptr [rsp+2B0h+SystemTime+8]
0x18000301d  movzx   r11d, word ptr [rsp+2B0h+SystemTime+0Eh]
0x180003023  movzx   r9d, word ptr [rsp+2B0h+SystemTime+0Ah]
0x180003029  mov     dword ptr [rsp+2B0h+var_268], eax
0x18000302d  mov     [rsp+2B0h+var_270], ecx
0x180003031  lea     rcx, [rsp+2B0h+OutputString]; char *
0x180003036  mov     [rsp+2B0h+var_278], edx
0x18000303a  mov     edx, 200h; unsigned __int64
0x18000303f  mov     [rsp+2B0h+var_280], r8d
0x180003044  lea     r8, a02d02d4d2d2d2d; "%02d/%02d/%4d %2d:%2d:%2d.%08d:"
0x18000304b  mov     [rsp+2B0h+var_288], r10d
0x180003050  mov     dword ptr [rsp+2B0h+argList], r11d
0x180003055  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000305a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180003061  lea     rcx, [rsp+2B0h+OutputString]
0x180003066  mov     rax, rbx
0x180003069  nop     dword ptr [rax+00000000h]
0x180003070  inc     rax
0x180003073  cmp     [rcx+rax], sil
0x180003077  jnz     short loc_180003070
0x180003079  mov     edx, 200h
0x18000307e  sub     edx, eax; cchDest
0x180003080  jz      short loc_1800030AA
0x180003082  mov     eax, eax
0x180003084  lea     rcx, [rsp+2B0h+OutputString]
0x180003089  add     rcx, rax; pszDest
0x18000308c  cmp     edx, 7FFFFFFFh
0x180003092  ja      short loc_1800030A7
0x180003094  mov     r9, [rbp+1B0h+pszFormat]; pszFormat
0x18000309b  mov     [rsp+2B0h+argList], rdi; argList
0x1800030a0  call    StringVPrintfWorkerA
0x1800030a5  jmp     short loc_1800030AA
0x1800030a7  mov     [rcx], sil
0x1800030aa  lea     rcx, [rsp+2B0h+OutputString]; lpOutputString
0x1800030af  call    cs:__imp_OutputDebugStringA
0x1800030b5  mov     r11, cs:?GPLogFileHandle@@3PEAXEA; void * GPLogFileHandle
0x1800030bc  test    r11, r11
0x1800030bf  jz      short loc_18000311A
0x1800030c1  lea     rcx, [rsp+2B0h+OutputString]
0x1800030c6  mov     rax, rbx
0x1800030c9  nop     dword ptr [rax+00000000h]
0x1800030d0  inc     rax
0x1800030d3  cmp     [rcx+rax], sil
0x1800030d7  jnz     short loc_1800030D0
0x1800030d9  inc     eax
0x1800030db  cmp     eax, 200h
0x1800030e0  jnb     short loc_18000311A
0x1800030e2  lea     rcx, [rsp+2B0h+OutputString]; char *
0x1800030e7  mov     [rsp+rax+2B0h+OutputString], 0Dh
0x1800030ec  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800030f1  lea     rax, [rsp+2B0h+OutputString]
0x1800030f6  inc     rbx
0x1800030f9  cmp     [rax+rbx], sil
0x1800030fd  jnz     short loc_1800030F6
0x1800030ff  mov     r8d, ebx; nNumberOfBytesToWrite
0x180003102  mov     [rsp+2B0h+argList], rsi; lpOverlapped
0x180003107  lea     r9, [rsp+2B0h+SystemTime]; lpNumberOfBytesWritten
0x18000310c  mov     rcx, r11; hFile
0x18000310f  lea     rdx, [rsp+2B0h+OutputString]; lpBuffer
0x180003114  call    cs:__imp_WriteFile
0x18000311a  mov     rbx, [rsp+298h]
0x180003122  mov     rcx, [rbp+1B0h+var_30]
0x180003129  xor     rcx, rsp; StackCookie
0x18000312c  call    __security_check_cookie
0x180003131  add     rsp, 2A0h
0x180003138  pop     rdi
0x180003139  pop     rsi
0x18000313a  pop     rbp
0x18000313b  retn
```
