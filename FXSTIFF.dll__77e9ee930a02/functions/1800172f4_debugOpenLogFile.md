# debugOpenLogFile

- ea: `0x1800172f4`
- end: `0x1800174d2`
- name: `debugOpenLogFile`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000ee54`

## callees

- `0x180006b18`
- `0x1800131b4`
- `0x1800172f4`
- `0x18001899e`
- `0x1800189d0`

## import_xrefs

- `msvcrt!wcschr` at `0x180017387`
- `msvcrt!wcschr` at `0x180017387`
- `KERNEL32!SetFilePointer` at `0x18001748e`
- `KERNEL32!SetFilePointer` at `0x18001748e`
- `KERNEL32!GetTempPath2W` at `0x1800173a4`
- `KERNEL32!GetTempPath2W` at `0x1800173a4`
- `KERNEL32!CloseHandle` at `0x1800174a6`
- `KERNEL32!CloseHandle` at `0x1800174a6`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180017368`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180017368`

## pseudocode

```c
__int64 debugOpenLogFile()
{
  __int64 v1; // rbx
  __int64 v2; // r9
  __int64 v3; // rcx
  WCHAR *v4; // rdx
  WCHAR *v5; // rax
  WCHAR *v6; // rdx
  void *File; // rax
  WCHAR Dst[264]; // [rsp+40h] [rbp-438h] BYREF
  _BYTE v9[528]; // [rsp+250h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  memset_0(v9, 0, 0x208u);
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
      v3 = 2147483646;
      v4 = Dst;
      v5 = &g_szPathToFile;
      do
      {
        if ( !v3 )
          break;
        if ( !*v4 )
          break;
        *v5++ = *v4++;
        --v3;
        --v1;
      }
      while ( v1 );
      v6 = v5 - 1;
      if ( v1 )
        v6 = v5;
      *v6 = 0;
      if ( !v1 )
        return 0;
    }
    else if ( !(unsigned int)GetTempPath2W(260, v9)
           || (int)StringCchPrintfW(&g_szPathToFile, 0x104u, L"%s%s", v9, Dst) < 0 )
    {
      return 0;
    }
    File = (void *)InternalSafeCreateFile(&g_szPathToFile, 0x40000000u, 3u, v2, 4u, 128);
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
0x1800172f4  mov     [rsp+arg_0], rbx
0x1800172f9  push    rdi
0x1800172fa  sub     rsp, 470h
0x180017301  mov     rax, cs:__security_cookie
0x180017308  xor     rax, rsp
0x18001730b  mov     [rsp+478h+var_18], rax
0x180017313  mov     ebx, 208h
0x180017318  lea     rcx, [rsp+478h+Dst]; void *
0x18001731d  mov     r8d, ebx; Size
0x180017320  xor     edx, edx; Val
0x180017322  call    memset_0
0x180017327  mov     r8d, ebx; Size
0x18001732a  lea     rcx, [rsp+478h+var_228]; void *
0x180017332  xor     edx, edx; Val
0x180017334  call    memset_0
0x180017339  cmp     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x180017341  jz      short loc_180017354
0x180017343  lock inc cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x18001734a  mov     eax, 1
0x18001734f  jmp     loc_1800173E1
0x180017354  mov     ebx, 104h
0x180017359  lea     rdx, [rsp+478h+Dst]; lpDst
0x18001735e  mov     r8d, ebx; nSize
0x180017361  lea     rcx, Src; "FXSTIFFDebugLogFile.txt"
0x180017368  call    cs:__imp_ExpandEnvironmentStringsW
0x18001736f  nop     dword ptr [rax+rax+00h]
0x180017374  dec     eax
0x180017376  cmp     eax, 103h
0x18001737b  ja      short loc_1800173DF
0x18001737d  mov     edx, 5Ch ; '\'; Ch
0x180017382  lea     rcx, [rsp+478h+Dst]; Str
0x180017387  call    cs:__imp_wcschr
0x18001738e  nop     dword ptr [rax+rax+00h]
0x180017393  xor     edi, edi
0x180017395  test    rax, rax
0x180017398  jnz     short loc_180017403
0x18001739a  lea     rdx, [rsp+478h+var_228]
0x1800173a2  mov     ecx, ebx
0x1800173a4  call    cs:__imp_GetTempPath2W
0x1800173ab  nop     dword ptr [rax+rax+00h]
0x1800173b0  test    eax, eax
0x1800173b2  jz      short loc_1800173DF
0x1800173b4  lea     rax, [rsp+478h+Dst]
0x1800173b9  mov     edx, ebx; unsigned __int64
0x1800173bb  lea     r9, [rsp+478h+var_228]
0x1800173c3  mov     qword ptr [rsp+478h+var_458], rax
0x1800173c8  lea     r8, aSS; "%s%s"
0x1800173cf  lea     rcx, ?g_szPathToFile@@3PAGA; unsigned __int16 *
0x1800173d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800173db  test    eax, eax
0x1800173dd  jns     short loc_180017448
0x1800173df  xor     eax, eax
0x1800173e1  mov     rcx, [rsp+478h+var_18]
0x1800173e9  xor     rcx, rsp; StackCookie
0x1800173ec  call    __security_check_cookie
0x1800173f1  mov     rbx, [rsp+478h+arg_0]
0x1800173f9  add     rsp, 470h
0x180017400  pop     rdi
0x180017401  retn
0x180017403  mov     ecx, 7FFFFFFEh
0x180017408  lea     rdx, [rsp+478h+Dst]
0x18001740d  lea     rax, ?g_szPathToFile@@3PAGA; ushort near * g_szPathToFile
0x180017414  test    rcx, rcx
0x180017417  jz      short loc_180017438
0x180017419  movzx   r8d, word ptr [rdx]
0x18001741d  test    r8w, r8w
0x180017421  jz      short loc_180017438
0x180017423  mov     [rax], r8w
0x180017427  add     rdx, 2
0x18001742b  add     rax, 2
0x18001742f  dec     rcx
0x180017432  sub     rbx, 1
0x180017436  jnz     short loc_180017414
0x180017438  test    rbx, rbx
0x18001743b  lea     rdx, [rax-2]
0x18001743f  cmovnz  rdx, rax
0x180017443  mov     [rdx], di
0x180017446  jz      short loc_1800173DF
0x180017448  mov     [rsp+478h+var_450], 80h; int
0x180017450  lea     rcx, ?g_szPathToFile@@3PAGA; lpFileName
0x180017457  mov     edx, 40000000h; dwDesiredAccess
0x18001745c  mov     [rsp+478h+var_458], 4; DWORD
0x180017464  mov     r8d, 3; dwShareMode
0x18001746a  call    InternalSafeCreateFile
0x18001746f  mov     cs:?g_hLogFile@@3PEAXEA, rax; void * g_hLogFile
0x180017476  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001747a  jz      loc_1800173DF
0x180017480  mov     r9d, 2; dwMoveMethod
0x180017486  xor     r8d, r8d; lpDistanceToMoveHigh
0x180017489  xor     edx, edx; lDistanceToMove
0x18001748b  mov     rcx, rax; hFile
0x18001748e  call    cs:__imp_SetFilePointer
0x180017495  nop     dword ptr [rax+rax+00h]
0x18001749a  cmp     eax, 0FFFFFFFFh
0x18001749d  jnz     short loc_1800174C2
0x18001749f  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x1800174a6  call    cs:__imp_CloseHandle
0x1800174ad  nop     dword ptr [rax+rax+00h]
0x1800174b2  mov     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x1800174bd  jmp     loc_1800173DF
0x1800174c2  mov     eax, 1
0x1800174c7  xchg    eax, cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x1800174cd  jmp     loc_18001734A
```
