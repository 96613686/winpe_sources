# debugOpenLogFile

- ea: `0x1800165d0`
- end: `0x18001678c`
- name: `debugOpenLogFile`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000e7e4`

## callees

- `0x180006934`
- `0x180012ad4`
- `0x1800165d0`
- `0x180017bce`
- `0x180017c00`

## import_xrefs

- `msvcrt!wcschr` at `0x18001665a`
- `msvcrt!wcschr` at `0x18001665a`
- `KERNEL32!SetFilePointer` at `0x180016754`
- `KERNEL32!SetFilePointer` at `0x180016754`
- `KERNEL32!GetTempPath2W` at `0x180016671`
- `KERNEL32!GetTempPath2W` at `0x180016671`
- `KERNEL32!CloseHandle` at `0x180016766`
- `KERNEL32!CloseHandle` at `0x180016766`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016641`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180016641`

## pseudocode

```c
__int64 debugOpenLogFile()
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  WCHAR *v3; // rdx
  WCHAR *v4; // rax
  WCHAR *v5; // rdx
  void *File; // rax
  WCHAR Dst[264]; // [rsp+40h] [rbp-438h] BYREF
  _BYTE v8[528]; // [rsp+250h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  memset_0(v8, 0, 0x208u);
  if ( g_hLogFile != (HANDLE)-1LL )
  {
    _InterlockedIncrement(&g_iLogFileRefCount);
    return 1;
  }
  v1 = 260;
  if ( ExpandEnvironmentStringsW(L"FXSTIFFDebugLogFile.txt", Dst, 0x104u) - 1 <= 0x103 )
  {
    if ( wcschr(Dst, 0x5Cu) )
    {
      v2 = 2147483646;
      v3 = Dst;
      v4 = &g_szPathToFile;
      do
      {
        if ( !v2 )
          break;
        if ( !*v3 )
          break;
        *v4++ = *v3++;
        --v2;
        --v1;
      }
      while ( v1 );
      v5 = v4 - 1;
      if ( v1 )
        v5 = v4;
      *v5 = 0;
      if ( !v1 )
        return 0;
    }
    else if ( !(unsigned int)GetTempPath2W(260, v8)
           || (int)StringCchPrintfW(&g_szPathToFile, 0x104u, L"%s%s", v8, Dst) < 0 )
    {
      return 0;
    }
    File = (void *)InternalSafeCreateFile(&g_szPathToFile, 0x40000000u, 3u, 4u, 128);
    g_hLogFile = File;
    if ( File != (void *)-1LL )
    {
      if ( SetFilePointer(File, 0, 0, 2u) != -1 )
      {
        _InterlockedExchange(&g_iLogFileRefCount, 1);
        return 1;
      }
      CloseHandle(g_hLogFile);
      g_hLogFile = (HANDLE)-1LL;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800165d0  mov     [rsp+arg_0], rbx
0x1800165d5  push    rdi
0x1800165d6  sub     rsp, 470h
0x1800165dd  mov     rax, cs:__security_cookie
0x1800165e4  xor     rax, rsp
0x1800165e7  mov     [rsp+478h+var_18], rax
0x1800165ef  mov     ebx, 208h
0x1800165f4  lea     rcx, [rsp+478h+Dst]; void *
0x1800165f9  mov     r8d, ebx; Size
0x1800165fc  xor     edx, edx; Val
0x1800165fe  call    memset_0
0x180016603  mov     r8d, ebx; Size
0x180016606  lea     rcx, [rsp+478h+var_228]; void *
0x18001660e  xor     edx, edx; Val
0x180016610  call    memset_0
0x180016615  cmp     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x18001661d  jz      short loc_18001662D
0x18001661f  lock inc cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x180016626  mov     eax, 1
0x18001662b  jmp     short loc_1800166A8
0x18001662d  mov     ebx, 104h
0x180016632  lea     rdx, [rsp+478h+Dst]; lpDst
0x180016637  mov     r8d, ebx; nSize
0x18001663a  lea     rcx, Src; "FXSTIFFDebugLogFile.txt"
0x180016641  call    cs:__imp_ExpandEnvironmentStringsW
0x180016647  dec     eax
0x180016649  cmp     eax, 103h
0x18001664e  ja      short loc_1800166A6
0x180016650  mov     edx, 5Ch ; '\'; Ch
0x180016655  lea     rcx, [rsp+478h+Dst]; Str
0x18001665a  call    cs:__imp_wcschr
0x180016660  xor     edi, edi
0x180016662  test    rax, rax
0x180016665  jnz     short loc_1800166C9
0x180016667  lea     rdx, [rsp+478h+var_228]
0x18001666f  mov     ecx, ebx
0x180016671  call    cs:__imp_GetTempPath2W
0x180016677  test    eax, eax
0x180016679  jz      short loc_1800166A6
0x18001667b  lea     rax, [rsp+478h+Dst]
0x180016680  mov     edx, ebx; unsigned __int64
0x180016682  lea     r9, [rsp+478h+var_228]
0x18001668a  mov     qword ptr [rsp+478h+var_458], rax
0x18001668f  lea     r8, aSS; "%s%s"
0x180016696  lea     rcx, ?g_szPathToFile@@3PAGA; unsigned __int16 *
0x18001669d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800166a2  test    eax, eax
0x1800166a4  jns     short loc_18001670E
0x1800166a6  xor     eax, eax
0x1800166a8  mov     rcx, [rsp+478h+var_18]
0x1800166b0  xor     rcx, rsp; StackCookie
0x1800166b3  call    __security_check_cookie
0x1800166b8  mov     rbx, [rsp+478h+arg_0]
0x1800166c0  add     rsp, 470h
0x1800166c7  pop     rdi
0x1800166c8  retn
0x1800166c9  mov     ecx, 7FFFFFFEh
0x1800166ce  lea     rdx, [rsp+478h+Dst]
0x1800166d3  lea     rax, ?g_szPathToFile@@3PAGA; ushort near * g_szPathToFile
0x1800166da  test    rcx, rcx
0x1800166dd  jz      short loc_1800166FE
0x1800166df  movzx   r8d, word ptr [rdx]
0x1800166e3  test    r8w, r8w
0x1800166e7  jz      short loc_1800166FE
0x1800166e9  mov     [rax], r8w
0x1800166ed  add     rdx, 2
0x1800166f1  add     rax, 2
0x1800166f5  dec     rcx
0x1800166f8  sub     rbx, 1
0x1800166fc  jnz     short loc_1800166DA
0x1800166fe  test    rbx, rbx
0x180016701  lea     rdx, [rax-2]
0x180016705  cmovnz  rdx, rax
0x180016709  mov     [rdx], di
0x18001670c  jz      short loc_1800166A6
0x18001670e  mov     [rsp+478h+var_450], 80h; int
0x180016716  lea     rcx, ?g_szPathToFile@@3PAGA; lpFileName
0x18001671d  mov     edx, 40000000h; dwDesiredAccess
0x180016722  mov     [rsp+478h+var_458], 4; DWORD
0x18001672a  mov     r8d, 3; dwShareMode
0x180016730  call    InternalSafeCreateFile
0x180016735  mov     cs:?g_hLogFile@@3PEAXEA, rax; void * g_hLogFile
0x18001673c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016740  jz      loc_1800166A6
0x180016746  mov     r9d, 2; dwMoveMethod
0x18001674c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001674f  xor     edx, edx; lDistanceToMove
0x180016751  mov     rcx, rax; hFile
0x180016754  call    cs:__imp_SetFilePointer
0x18001675a  cmp     eax, 0FFFFFFFFh
0x18001675d  jnz     short loc_18001677C
0x18001675f  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x180016766  call    cs:__imp_CloseHandle
0x18001676c  mov     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x180016777  jmp     loc_1800166A6
0x18001677c  mov     eax, 1
0x180016781  xchg    eax, cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x180016787  jmp     loc_180016626
```
