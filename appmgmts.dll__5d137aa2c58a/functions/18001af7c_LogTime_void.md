# LogTime(void)

- ea: `0x18001af7c`
- end: `0x18001b0cc`
- name: `?LogTime@@YAXXZ`
- size: `336`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000219c`
- `0x180002b90`
- `0x180003370`
- `0x18000bbd0`
- `0x18000bdf0`
- `0x18000dc40`
- `0x18000dd00`
- `0x180012580`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001acb8`
- `0x18001af40`
- `0x18001af7c`
- `0x18001b0d4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b0ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b0ab`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b07b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b0a2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b07b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b0a2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001b040`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001b040`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001afce`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001afce`

## pseudocode

```c
void __fastcall LogTime(__int64 a1, int a2)
{
  void *v2; // rax
  __int64 v3; // rbx
  void *v4; // rdi
  DWORD v5; // eax
  DWORD v6; // eax
  int lpOverlapped; // [rsp+20h] [rbp-E0h]
  int wHour; // [rsp+28h] [rbp-D8h]
  int wMinute; // [rsp+30h] [rbp-D0h]
  int wSecond; // [rsp+38h] [rbp-C8h]
  int wMilliseconds; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 Buffer[64]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+F0h] [rbp-10h] BYREF

  if ( (gDebugLevel & 8) != 0 )
  {
    SystemTime = 0;
    if ( (unsigned int)GetDebugLogFileName(Dst, a2) )
    {
      GetLocalTime(&SystemTime);
      wMilliseconds = SystemTime.wMilliseconds;
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      lpOverlapped = SystemTime.wDay;
      StringCchPrintfW(
        Buffer,
        0x40u,
        L"%02d-%02d %02d:%02d:%02d:%03d ",
        SystemTime.wMonth,
        lpOverlapped,
        wHour,
        wMinute,
        wSecond,
        wMilliseconds);
      v2 = OpenUnicodeLogFile(Dst);
      v3 = -1;
      v4 = v2;
      if ( v2 != (void *)-1LL )
      {
        if ( SetFilePointer(v2, 0, 0, 2u) != -1 )
        {
          NumberOfBytesWritten = 0;
          do
            ++v3;
          while ( Buffer[v3] );
          v5 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(2 * v3);
          WriteFile(v4, Buffer, v5, &NumberOfBytesWritten, 0);
          v6 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(4);
          WriteFile(v4, L"\r\n", v6, &NumberOfBytesWritten, 0);
        }
        CloseHandle(v4);
      }
    }
  }
}

```

## disassembly

```asm
0x18001af7c  push    rbp
0x18001af7e  push    rbx
0x18001af7f  push    rsi
0x18001af80  push    rdi
0x18001af81  lea     rbp, [rsp-218h]
0x18001af89  sub     rsp, 318h
0x18001af90  mov     rax, cs:__security_cookie
0x18001af97  xor     rax, rsp
0x18001af9a  mov     [rbp+230h+var_30], rax
0x18001afa1  test    byte ptr cs:?gDebugLevel@@3KA, 8; ulong gDebugLevel
0x18001afa8  jz      loc_18001B0B1
0x18001afae  xorps   xmm0, xmm0
0x18001afb1  lea     rcx, [rbp+230h+Dst]; lpDst
0x18001afb5  movups  xmmword ptr [rsp+330h+SystemTime.wYear], xmm0
0x18001afba  call    ?GetDebugLogFileName@@YAHPEAGJ@Z; GetDebugLogFileName(ushort *,long)
0x18001afbf  xor     esi, esi
0x18001afc1  test    eax, eax
0x18001afc3  jz      loc_18001B0B1
0x18001afc9  lea     rcx, [rsp+330h+SystemTime]; lpSystemTime
0x18001afce  call    cs:__imp_GetLocalTime
0x18001afd4  movzx   ecx, [rsp+330h+SystemTime.wSecond]
0x18001afd9  movzx   edx, [rsp+330h+SystemTime.wMinute]
0x18001afde  movzx   r8d, [rsp+330h+SystemTime.wHour]
0x18001afe4  movzx   eax, [rsp+330h+SystemTime.wMilliseconds]
0x18001afe9  movzx   r10d, [rsp+330h+SystemTime.wDay]
0x18001afef  movzx   r9d, [rsp+330h+SystemTime.wMonth]
0x18001aff5  mov     [rsp+330h+var_2F0], eax
0x18001aff9  mov     [rsp+330h+var_2F8], ecx
0x18001affd  lea     rcx, [rsp+330h+Buffer]; unsigned __int16 *
0x18001b002  mov     [rsp+330h+var_300], edx
0x18001b006  lea     edx, [rsi+40h]; unsigned __int64
0x18001b009  mov     [rsp+330h+var_308], r8d
0x18001b00e  lea     r8, a02d02d02d02d02_0; "%02d-%02d %02d:%02d:%02d:%03d "
0x18001b015  mov     dword ptr [rsp+330h+lpOverlapped], r10d
0x18001b01a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b01f  lea     rcx, [rbp+230h+Dst]; lpFileName
0x18001b023  call    ?OpenUnicodeLogFile@@YAPEAXPEBG@Z; OpenUnicodeLogFile(ushort const *)
0x18001b028  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b02c  mov     rdi, rax
0x18001b02f  cmp     rax, rbx
0x18001b032  jz      short loc_18001B0B1
0x18001b034  lea     r9d, [rsi+2]; dwMoveMethod
0x18001b038  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001b03b  xor     edx, edx; lDistanceToMove
0x18001b03d  mov     rcx, rax; hFile
0x18001b040  call    cs:__imp_SetFilePointer
0x18001b046  cmp     eax, 0FFFFFFFFh
0x18001b049  jz      short loc_18001B0A8
0x18001b04b  mov     [rsp+330h+NumberOfBytesWritten], esi
0x18001b04f  lea     rax, [rsp+330h+Buffer]
0x18001b054  inc     rbx
0x18001b057  cmp     [rax+rbx*2], si
0x18001b05b  jnz     short loc_18001B054
0x18001b05d  lea     rcx, [rbx+rbx]
0x18001b061  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001b066  mov     r8d, eax; nNumberOfBytesToWrite
0x18001b069  mov     [rsp+330h+lpOverlapped], rsi; lpOverlapped
0x18001b06e  lea     r9, [rsp+330h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b073  mov     rcx, rdi; hFile
0x18001b076  lea     rdx, [rsp+330h+Buffer]; lpBuffer
0x18001b07b  call    cs:__imp_WriteFile
0x18001b081  mov     ecx, 4
0x18001b086  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001b08b  mov     r8d, eax; nNumberOfBytesToWrite
0x18001b08e  mov     [rsp+330h+lpOverlapped], rsi; lpOverlapped
0x18001b093  lea     r9, [rsp+330h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b098  mov     rcx, rdi; hFile
0x18001b09b  lea     rdx, Buffer; "\r\n"
0x18001b0a2  call    cs:__imp_WriteFile
0x18001b0a8  mov     rcx, rdi; hObject
0x18001b0ab  call    cs:__imp_CloseHandle
0x18001b0b1  mov     rcx, [rbp+230h+var_30]
0x18001b0b8  xor     rcx, rsp; StackCookie
0x18001b0bb  call    __security_check_cookie
0x18001b0c0  add     rsp, 318h
0x18001b0c7  pop     rdi
0x18001b0c8  pop     rsi
0x18001b0c9  pop     rbx
0x18001b0ca  pop     rbp
0x18001b0cb  retn
```
