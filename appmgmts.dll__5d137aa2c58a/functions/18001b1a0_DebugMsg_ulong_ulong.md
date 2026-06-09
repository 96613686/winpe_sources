# _DebugMsg(ulong,ulong,...)

- ea: `0x18001b1a0`
- end: `0x18001b4ac`
- name: `?_DebugMsg@@YAXKKZZ`
- size: `780`
- prototype: `void(char, unsigned int, ...)`
- caller_count: `78`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000239c`
- `0x180002b90`
- `0x1800030c0`
- `0x180003370`
- `0x1800047d0`
- `0x1800049d0`
- `0x180004e30`
- `0x180004ef0`
- `0x180005294`
- `0x180005a48`
- `0x180005cec`
- `0x180005f2c`
- `0x1800061f8`
- `0x180006c54`
- `0x180007110`
- `0x1800071e4`
- `0x180007410`
- `0x1800079b0`
- `0x180007b58`
- `0x180007c24`
- `0x180007ea4`
- `0x1800084d4`
- `0x180008724`
- `0x180008d6c`
- `0x180008fe4`
- `0x1800093ac`
- `0x18000949c`
- `0x180009584`
- `0x18000a148`
- `0x18000a6e4`
- `0x18000a7c0`
- `0x18000ac90`
- `0x18000b16c`
- `0x18000b3bc`
- `0x18000b7e8`
- `0x18000bbd0`
- `0x18000bdf0`
- `0x18000c1d0`
- `0x18000c2cc`
- `0x18000c790`
- `0x18000c8c0`
- `0x18000ca60`
- `0x18000cb98`
- `0x18000da3c`
- `0x18000dd00`
- `0x18000df00`
- `0x18000eeac`
- `0x18000f024`
- `0x18000f634`
- `0x18000f8bc`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x180012d70`
- `0x18001309c`
- `0x18001acb8`
- `0x18001acf0`
- `0x18001af40`
- `0x18001b0d4`
- `0x18001b1a0`
- `0x18001b4e0`
- `0x18002ad30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b2fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b2fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b304`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b43e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b43e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b485`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b485`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b38f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b38f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b40e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b435`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b40e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b435`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001b3d1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18001b3d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001b2f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001b2f6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b35c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b367`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b374`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b35c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b367`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001b374`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b2d8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b2d8`

## pseudocode

```c
void _DebugMsg(char a1, unsigned int a2, ...)
{
  int (*v3)(HINSTANCE, unsigned int, unsigned __int16 *, int); // rbx
  DWORD v4; // edi
  HINSTANCE v5; // rax
  DWORD v6; // r8d
  _BYTE *v7; // rdx
  DWORD v8; // ecx
  HINSTANCE HandleForCallingDll; // rax
  int v10; // r14d
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  BYTE v13; // al
  WCHAR *v14; // rax
  int v15; // edx
  WCHAR *v16; // rdi
  void *v17; // rax
  __int64 v18; // rbx
  void *v19; // rsi
  DWORD v20; // eax
  DWORD v21; // eax
  LPWSTR lpBuffer; // [rsp+28h] [rbp-E0h]
  DWORD nSize[2]; // [rsp+30h] [rbp-D8h]
  va_list *Arguments; // [rsp+38h] [rbp-D0h]
  WCHAR Buffer[4]; // [rsp+58h] [rbp-B0h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+60h] [rbp-A8h] BYREF
  va_list v27[4]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR OutputString[64]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v29[4096]; // [rsp+108h] [rbp+0h] BYREF
  va_list va; // [rsp+1168h] [rbp+1060h] BYREF

  va_start(va, a2);
  *(_QWORD *)Buffer = 0;
  memset(v27, 0, 24);
  if ( gDebugEnabled == 1 && !gDebugInitialized )
  {
    ApplyDebugSettings();
    if ( gDebugEnabled != 1 || gDebugInitialized != 1 )
      return;
  }
  if ( (gDebugLevel & 2) == 0 && ((gDebugLevel & 1) == 0 || (a1 & 4) != 0) || !(unsigned int)LoadLoadString() )
    return;
  va_copy((va_list)v27, va);
  if ( a2 < 0x3E8 )
  {
    HandleForCallingDll = AppmgmtGetHandleForCallingDll();
    v6 = a2;
    v7 = HandleForCallingDll;
    v8 = 2304;
  }
  else
  {
    v3 = pfnLoadStringW;
    v4 = 0;
    v5 = AppmgmtGetHandleForCallingDll();
    if ( !((unsigned int (__fastcall *)(HINSTANCE, _QWORD, _BYTE *, __int64))v3)(v5, a2, v29, 2048) )
      goto LABEL_14;
    v6 = 0;
    v7 = v29;
    v8 = 1280;
  }
  v4 = FormatMessageW(v8, v7, v6, 0, Buffer, 0, v27);
LABEL_14:
  v27[0] = 0;
  if ( v4 )
  {
    v10 = a1 & 8;
    GetLocalTime((LPSYSTEMTIME)&v27[1]);
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    LODWORD(Arguments) = WORD1(v27[2]);
    nSize[0] = LOWORD(v27[2]);
    LODWORD(lpBuffer) = CurrentThreadId;
    StringCchPrintfW(
      OutputString,
      0x40u,
      L"APPMGMT (%x.%x) %02d:%02d:%02d:%03d ",
      CurrentProcessId,
      lpBuffer,
      *(_QWORD *)nSize,
      Arguments,
      WORD2(v27[2]),
      HIWORD(v27[2]));
    v13 = gDebugLevel;
    if ( (gDebugLevel & 0x40) == 0 )
    {
      OutputDebugStringW(OutputString);
      OutputDebugStringW(*(LPCWSTR *)Buffer);
      OutputDebugStringW(L"\r\n");
      v13 = gDebugLevel;
    }
    if ( (v13 & 8) != 0 )
    {
      v14 = (WCHAR *)LocalAlloc(0, 0x208u);
      v16 = v14;
      if ( v14 && (unsigned int)GetDebugLogFileName(v14, v15) )
      {
        v17 = OpenUnicodeLogFile(v16);
        v18 = -1;
        v19 = v17;
        if ( v17 != (void *)-1LL && SetFilePointer(v17, 0, 0, 2u) != -1 )
        {
          NumberOfBytesWritten[0] = 0;
          do
            ++v18;
          while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v18) );
          v20 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(2 * v18);
          WriteFile(v19, *(LPCVOID *)Buffer, v20, NumberOfBytesWritten, 0);
          v21 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(4);
          WriteFile(v19, L"\r\n", v21, NumberOfBytesWritten, 0);
        }
        CloseHandle(v19);
      }
      LocalFree(v16);
      v13 = gDebugLevel;
    }
    if ( !v10 && (v13 & 4) != 0 )
    {
      *(_QWORD *)NumberOfBytesWritten = 0;
      CEventsBase::Report((CEventsBase *)NumberOfBytesWritten, 0x191u, 0, 1u, *(_QWORD *)Buffer);
    }
    LocalFree(*(HLOCAL *)Buffer);
  }
}

```

## disassembly

```asm
0x18001b1a0  mov     rax, rsp
0x18001b1a3  mov     [rax+10h], edx
0x18001b1a6  mov     [rax+18h], r8
0x18001b1aa  mov     [rax+20h], r9
0x18001b1ae  push    rbp
0x18001b1af  push    rbx
0x18001b1b0  push    rsi
0x18001b1b1  push    rdi
0x18001b1b2  push    r12
0x18001b1b4  push    r14
0x18001b1b6  push    r15
0x18001b1b8  lea     rbp, [rax-1048h]
0x18001b1bf  mov     eax, 1110h
0x18001b1c4  call    _alloca_probe
0x18001b1c9  sub     rsp, rax
0x18001b1cc  mov     rax, cs:__security_cookie
0x18001b1d3  xor     rax, rsp
0x18001b1d6  mov     [rbp+1040h+var_40], rax
0x18001b1dd  xor     r15d, r15d
0x18001b1e0  xorps   xmm0, xmm0
0x18001b1e3  mov     r14d, ecx
0x18001b1e6  mov     qword ptr [rsp+1140h+Buffer], r15
0x18001b1eb  mov     qword ptr [rsp+1140h+var_10E0], r15
0x18001b1f0  movups  xmmword ptr [rsp+1140h+var_10E0+8], xmm0
0x18001b1f5  lea     r12d, [r15+1]
0x18001b1f9  cmp     cs:?gDebugEnabled@@3KA, r12d; ulong gDebugEnabled
0x18001b200  jnz     short loc_18001B22A
0x18001b202  cmp     cs:?gDebugInitialized@@3KA, r15d; ulong gDebugInitialized
0x18001b209  jnz     short loc_18001B22A
0x18001b20b  call    ?ApplyDebugSettings@@YAXXZ; ApplyDebugSettings(void)
0x18001b210  cmp     cs:?gDebugEnabled@@3KA, r12d; ulong gDebugEnabled
0x18001b217  jnz     loc_18001B48B
0x18001b21d  cmp     cs:?gDebugInitialized@@3KA, r12d; ulong gDebugInitialized
0x18001b224  jnz     loc_18001B48B
0x18001b22a  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18001b230  test    al, 2
0x18001b232  jnz     short loc_18001B247
0x18001b234  test    r12b, al
0x18001b237  jz      loc_18001B48B
0x18001b23d  test    r14b, 4
0x18001b241  jnz     loc_18001B48B
0x18001b247  call    ?LoadLoadString@@YAHXZ; LoadLoadString(void)
0x18001b24c  test    eax, eax
0x18001b24e  jz      loc_18001B48B
0x18001b254  cmp     [rbp+1040h+dwMessageId], 3E8h
0x18001b25e  lea     rax, [rbp+1040h+arg_10]
0x18001b265  mov     qword ptr [rsp+1140h+var_10E0], rax
0x18001b26a  jb      short loc_18001B2A8
0x18001b26c  mov     rbx, cs:?pfnLoadStringW@@3P6AHPEAUHINSTANCE__@@IPEAGH@ZEA; int (*pfnLoadStringW)(HINSTANCE__ *,uint,ushort *,int)
0x18001b273  mov     edi, r15d
0x18001b276  call    ?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; AppmgmtGetHandleForCallingDll(void)
0x18001b27b  mov     edx, [rbp+1040h+dwMessageId]
0x18001b281  lea     r8, [rbp+1040h+var_1040]
0x18001b285  mov     rcx, rax
0x18001b288  mov     r9d, 800h
0x18001b28e  mov     rax, rbx
0x18001b291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b296  test    eax, eax
0x18001b298  jz      short loc_18001B2E0
0x18001b29a  xor     r8d, r8d
0x18001b29d  lea     rdx, [rbp+1040h+var_1040]
0x18001b2a1  mov     ecx, 500h
0x18001b2a6  jmp     short loc_18001B2BC
0x18001b2a8  call    ?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; AppmgmtGetHandleForCallingDll(void)
0x18001b2ad  mov     r8d, [rbp+1040h+dwMessageId]; dwMessageId
0x18001b2b4  mov     rdx, rax; lpSource
0x18001b2b7  mov     ecx, 900h; dwFlags
0x18001b2bc  lea     rax, [rsp+1140h+var_10E0]
0x18001b2c1  xor     r9d, r9d; dwLanguageId
0x18001b2c4  mov     [rsp+1140h+Arguments], rax; Arguments
0x18001b2c9  lea     rax, [rsp+1140h+Buffer]
0x18001b2ce  mov     [rsp+1140h+nSize], r15d; nSize
0x18001b2d3  mov     [rsp+1140h+lpBuffer], rax; lpBuffer
0x18001b2d8  call    cs:__imp_FormatMessageW
0x18001b2de  mov     edi, eax
0x18001b2e0  mov     qword ptr [rsp+1140h+var_10E0], r15
0x18001b2e5  test    edi, edi
0x18001b2e7  jz      loc_18001B48B
0x18001b2ed  lea     rcx, [rsp+1140h+var_10E0+8]; lpSystemTime
0x18001b2f2  and     r14d, 8
0x18001b2f6  call    cs:__imp_GetLocalTime
0x18001b2fc  call    cs:__imp_GetCurrentThreadId
0x18001b302  mov     ebx, eax
0x18001b304  call    cs:__imp_GetCurrentProcessId
0x18001b30a  movzx   ecx, word ptr [rsp+1140h+var_10E0+16h]
0x18001b30f  movzx   edx, word ptr [rsp+1140h+var_10E0+14h]
0x18001b314  movzx   r8d, word ptr [rsp+1140h+var_10E0+12h]
0x18001b31a  movzx   r9d, word ptr [rsp+1140h+var_10E0+10h]
0x18001b320  mov     [rsp+40h], ecx
0x18001b324  lea     rcx, [rbp+1040h+OutputString]; unsigned __int16 *
0x18001b328  mov     [rsp+1140h+var_1108], edx
0x18001b32c  mov     edx, 40h ; '@'; unsigned __int64
0x18001b331  mov     dword ptr [rsp+1140h+Arguments], r8d
0x18001b336  lea     r8, aAppmgmtXX02d02; "APPMGMT (%x.%x) %02d:%02d:%02d:%03d "
0x18001b33d  mov     [rsp+1140h+nSize], r9d
0x18001b342  mov     r9d, eax
0x18001b345  mov     dword ptr [rsp+1140h+lpBuffer], ebx
0x18001b349  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b34e  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18001b354  test    al, 40h
0x18001b356  jnz     short loc_18001B380
0x18001b358  lea     rcx, [rbp+1040h+OutputString]; lpOutputString
0x18001b35c  call    cs:__imp_OutputDebugStringW
0x18001b362  mov     rcx, qword ptr [rsp+1140h+Buffer]; lpOutputString
0x18001b367  call    cs:__imp_OutputDebugStringW
0x18001b36d  lea     rcx, Buffer; "\r\n"
0x18001b374  call    cs:__imp_OutputDebugStringW
0x18001b37a  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18001b380  test    al, 8
0x18001b382  jz      loc_18001B453
0x18001b388  mov     edx, 208h; uBytes
0x18001b38d  xor     ecx, ecx; uFlags
0x18001b38f  call    cs:__imp_LocalAlloc
0x18001b395  mov     rdi, rax
0x18001b398  test    rax, rax
0x18001b39b  jz      loc_18001B444
0x18001b3a1  mov     rcx, rax; lpDst
0x18001b3a4  call    ?GetDebugLogFileName@@YAHPEAGJ@Z; GetDebugLogFileName(ushort *,long)
0x18001b3a9  test    eax, eax
0x18001b3ab  jz      loc_18001B444
0x18001b3b1  mov     rcx, rdi; lpFileName
0x18001b3b4  call    ?OpenUnicodeLogFile@@YAPEAXPEBG@Z; OpenUnicodeLogFile(ushort const *)
0x18001b3b9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b3bd  mov     rsi, rax
0x18001b3c0  cmp     rax, rbx
0x18001b3c3  jz      short loc_18001B43B
0x18001b3c5  lea     r9d, [rbx+3]; dwMoveMethod
0x18001b3c9  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001b3cc  xor     edx, edx; lDistanceToMove
0x18001b3ce  mov     rcx, rax; hFile
0x18001b3d1  call    cs:__imp_SetFilePointer
0x18001b3d7  cmp     eax, 0FFFFFFFFh
0x18001b3da  jz      short loc_18001B43B
0x18001b3dc  mov     rax, qword ptr [rsp+1140h+Buffer]
0x18001b3e1  mov     [rsp+1140h+NumberOfBytesWritten], r15d
0x18001b3e6  inc     rbx
0x18001b3e9  cmp     [rax+rbx*2], r15w
0x18001b3ee  jnz     short loc_18001B3E6
0x18001b3f0  lea     rcx, [rbx+rbx]
0x18001b3f4  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001b3f9  mov     rdx, qword ptr [rsp+1140h+Buffer]; lpBuffer
0x18001b3fe  lea     r9, [rsp+1140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b403  mov     r8d, eax; nNumberOfBytesToWrite
0x18001b406  mov     [rsp+1140h+lpBuffer], r15; lpOverlapped
0x18001b40b  mov     rcx, rsi; hFile
0x18001b40e  call    cs:__imp_WriteFile
0x18001b414  mov     ecx, 4
0x18001b419  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001b41e  mov     r8d, eax; nNumberOfBytesToWrite
0x18001b421  mov     [rsp+1140h+lpBuffer], r15; lpOverlapped
0x18001b426  lea     r9, [rsp+1140h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b42b  mov     rcx, rsi; hFile
0x18001b42e  lea     rdx, Buffer; "\r\n"
0x18001b435  call    cs:__imp_WriteFile
0x18001b43b  mov     rcx, rsi; hObject
0x18001b43e  call    cs:__imp_CloseHandle
0x18001b444  mov     rcx, rdi; hMem
0x18001b447  call    cs:__imp_LocalFree
0x18001b44d  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18001b453  test    r14d, r14d
0x18001b456  jnz     short loc_18001B480
0x18001b458  test    al, 4
0x18001b45a  jz      short loc_18001B480
0x18001b45c  mov     rax, qword ptr [rsp+1140h+Buffer]
0x18001b461  lea     rcx, [rsp+1140h+NumberOfBytesWritten]; this
0x18001b466  mov     r9d, r12d; unsigned __int16
0x18001b469  mov     [rsp+1140h+lpBuffer], rax
0x18001b46e  xor     r8d, r8d; int
0x18001b471  mov     qword ptr [rsp+1140h+NumberOfBytesWritten], r15
0x18001b476  mov     edx, 191h; unsigned int
0x18001b47b  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x18001b480  mov     rcx, qword ptr [rsp+1140h+Buffer]; hMem
0x18001b485  call    cs:__imp_LocalFree
0x18001b48b  mov     rcx, [rbp+1040h+var_40]
0x18001b492  xor     rcx, rsp; StackCookie
0x18001b495  call    __security_check_cookie
0x18001b49a  add     rsp, 1110h
0x18001b4a1  pop     r15
0x18001b4a3  pop     r14
0x18001b4a5  pop     r12
0x18001b4a7  pop     rdi
0x18001b4a8  pop     rsi
0x18001b4a9  pop     rbx
0x18001b4aa  pop     rbp
0x18001b4ab  retn
```
