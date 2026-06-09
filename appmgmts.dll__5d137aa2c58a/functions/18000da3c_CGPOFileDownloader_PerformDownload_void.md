# CGPOFileDownloader::PerformDownload(void)

- ea: `0x18000da3c`
- end: `0x18000db62`
- name: `?PerformDownload@CGPOFileDownloader@@AEAAKXZ`
- size: `294`
- prototype: `__int64 __fastcall(CGPOFileDownloader *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d864`

## callees

- `0x18000da3c`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db00`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000db2a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000db2a`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x18000da9f`
- `api-ms-win-core-file-l1-1-0!ReadFileEx` at `0x18000da9f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000da64`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000da64`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000dace`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000dace`

## pseudocode

```c
__int64 __fastcall CGPOFileDownloader::PerformDownload(CGPOFileDownloader *this)
{
  void *v2; // rcx
  void *v3; // rdx
  void *v4; // rcx
  DWORD v5; // eax
  struct _OVERLAPPED *LastError; // rbx
  DWORD v7; // r8d
  const void *v8; // rdx
  void *v9; // rcx
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  do
  {
    v2 = (void *)*((_QWORD *)this + 5);
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = this;
    if ( ResetEvent(v2)
      && (v3 = *(void **)this,
          v4 = (void *)*((_QWORD *)this + 3),
          Overlapped.Pointer = (PVOID)*((unsigned int *)this + 12),
          ReadFileEx(v4, v3, 0xF000u, &Overlapped, CGPOFileDownloader::ReadCompletionRoutine)) )
    {
      while ( 1 )
      {
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xCBBu);
        v5 = WaitForSingleObjectEx(*((HANDLE *)this + 5), 0xFFFFFFFF, 1);
        LastError = (struct _OVERLAPPED *)v5;
        if ( !v5 )
          break;
        if ( v5 != 192 )
          goto LABEL_9;
      }
      LastError = (struct _OVERLAPPED *)*((unsigned int *)this + 13);
LABEL_9:
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4, 0xCBCu);
    }
    else
    {
      LastError = (struct _OVERLAPPED *)GetLastError();
    }
    if ( (_DWORD)LastError )
    {
      if ( (_DWORD)LastError == 38 )
      {
        *((_DWORD *)this + 14) = 1;
        LODWORD(LastError) = 0;
      }
      continue;
    }
    v7 = *((_DWORD *)this + 2);
    if ( v7 )
    {
      v8 = *(const void **)this;
      v9 = (void *)*((_QWORD *)this + 4);
      NumberOfBytesWritten = 0;
      LODWORD(LastError) = WriteFile(v9, v8, v7, &NumberOfBytesWritten, LastError);
    }
    if ( (_DWORD)LastError == 38 )
      break;
  }
  while ( !*((_DWORD *)this + 14) );
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000da3c  mov     [rsp+arg_8], rbx
0x18000da41  push    rdi
0x18000da42  sub     rsp, 50h
0x18000da46  mov     rdi, rcx
0x18000da49  mov     rcx, [rdi+28h]; hEvent
0x18000da4d  xorps   xmm0, xmm0
0x18000da50  movdqu  xmmword ptr [rsp+58h+Overlapped.InternalHigh], xmm0
0x18000da56  mov     [rsp+58h+Overlapped.Internal], 0
0x18000da5f  mov     [rsp+58h+Overlapped.hEvent], rdi
0x18000da64  call    cs:__imp_ResetEvent
0x18000da6a  test    eax, eax
0x18000da6c  jz      loc_18000DB00
0x18000da72  mov     eax, [rdi+30h]
0x18000da75  lea     r9, [rsp+58h+Overlapped]; lpOverlapped
0x18000da7a  mov     rdx, [rdi]; lpBuffer
0x18000da7d  mov     r8d, 0F000h; nNumberOfBytesToRead
0x18000da83  mov     rcx, [rdi+18h]; hFile
0x18000da87  mov     dword ptr [rsp+58h+Overlapped.10h], eax
0x18000da8b  lea     rax, ?ReadCompletionRoutine@CGPOFileDownloader@@CAXKKPEAU_OVERLAPPED@@@Z; CGPOFileDownloader::ReadCompletionRoutine(ulong,ulong,_OVERLAPPED *)
0x18000da92  mov     [rsp+58h+lpCompletionRoutine], rax; lpCompletionRoutine
0x18000da97  mov     dword ptr [rsp+58h+Overlapped.10h+4], 0
0x18000da9f  call    cs:__imp_ReadFileEx
0x18000daa5  test    eax, eax
0x18000daa7  jz      short loc_18000DB00
0x18000daa9  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000dab0  jz      short loc_18000DAC1
0x18000dab2  mov     edx, 0CBBh; unsigned int
0x18000dab7  mov     ecx, 4; unsigned int
0x18000dabc  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000dac1  mov     rcx, [rdi+28h]; hHandle
0x18000dac5  mov     r8d, 1; bAlertable
0x18000dacb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000dace  call    cs:__imp_WaitForSingleObjectEx
0x18000dad4  mov     ebx, eax
0x18000dad6  test    eax, eax
0x18000dad8  jz      short loc_18000DAE3
0x18000dada  cmp     eax, 0C0h
0x18000dadf  jz      short loc_18000DAA9
0x18000dae1  jmp     short loc_18000DAE6
0x18000dae3  mov     ebx, [rdi+34h]
0x18000dae6  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000daed  jz      short loc_18000DB08
0x18000daef  mov     edx, 0CBCh; unsigned int
0x18000daf4  mov     ecx, 4; unsigned int
0x18000daf9  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000dafe  jmp     short loc_18000DB08
0x18000db00  call    cs:__imp_GetLastError
0x18000db06  mov     ebx, eax
0x18000db08  test    ebx, ebx
0x18000db0a  jnz     short loc_18000DB52
0x18000db0c  mov     r8d, [rdi+8]; nNumberOfBytesToWrite
0x18000db10  test    r8d, r8d
0x18000db13  jz      short loc_18000DB32
0x18000db15  mov     rdx, [rdi]; lpBuffer
0x18000db18  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000db1d  mov     rcx, [rdi+20h]; hFile
0x18000db21  mov     [rsp+58h+NumberOfBytesWritten], ebx
0x18000db25  mov     [rsp+58h+lpCompletionRoutine], rbx; lpOverlapped
0x18000db2a  call    cs:__imp_WriteFile
0x18000db30  mov     ebx, eax
0x18000db32  test    ebx, ebx
0x18000db34  jz      short loc_18000DB3B
0x18000db36  cmp     ebx, 26h ; '&'
0x18000db39  jz      short loc_18000DB45
0x18000db3b  cmp     dword ptr [rdi+38h], 0
0x18000db3f  jz      loc_18000DA49
0x18000db45  mov     eax, ebx
0x18000db47  mov     rbx, [rsp+58h+arg_8]
0x18000db4c  add     rsp, 50h
0x18000db50  pop     rdi
0x18000db51  retn
0x18000db52  cmp     ebx, 26h ; '&'
0x18000db55  jnz     short loc_18000DB3B
0x18000db57  mov     dword ptr [rdi+38h], 1
0x18000db5e  xor     ebx, ebx
0x18000db60  jmp     short loc_18000DB3B
```
