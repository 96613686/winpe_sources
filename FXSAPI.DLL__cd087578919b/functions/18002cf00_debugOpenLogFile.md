# debugOpenLogFile

- ea: `0x18002cf00`
- end: `0x18002d0de`
- name: `debugOpenLogFile`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800289a8`

## callees

- `0x1800084ac`
- `0x18002cf00`
- `0x1800308e0`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `msvcrt!wcschr` at `0x18002cf93`
- `msvcrt!wcschr` at `0x18002cf93`
- `KERNEL32!GetTempPath2W` at `0x18002cfb0`
- `KERNEL32!GetTempPath2W` at `0x18002cfb0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002cf74`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002cf74`
- `KERNEL32!SetFilePointer` at `0x18002d09a`
- `KERNEL32!SetFilePointer` at `0x18002d09a`
- `KERNEL32!CloseHandle` at `0x18002d0b2`
- `KERNEL32!CloseHandle` at `0x18002d0b2`

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
  if ( ExpandEnvironmentStringsW(L"FXSAPIDebugLogFile.txt", Dst, 0x104u) - 1 <= 0x103 )
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
0x18002cf00  mov     [rsp+arg_0], rbx
0x18002cf05  push    rdi
0x18002cf06  sub     rsp, 470h
0x18002cf0d  mov     rax, cs:__security_cookie
0x18002cf14  xor     rax, rsp
0x18002cf17  mov     [rsp+478h+var_18], rax
0x18002cf1f  mov     ebx, 208h
0x18002cf24  lea     rcx, [rsp+478h+Dst]; void *
0x18002cf29  mov     r8d, ebx; Size
0x18002cf2c  xor     edx, edx; Val
0x18002cf2e  call    memset_0
0x18002cf33  mov     r8d, ebx; Size
0x18002cf36  lea     rcx, [rsp+478h+var_228]; void *
0x18002cf3e  xor     edx, edx; Val
0x18002cf40  call    memset_0
0x18002cf45  cmp     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x18002cf4d  jz      short loc_18002CF60
0x18002cf4f  lock inc cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x18002cf56  mov     eax, 1
0x18002cf5b  jmp     loc_18002CFED
0x18002cf60  mov     ebx, 104h
0x18002cf65  lea     rdx, [rsp+478h+Dst]; lpDst
0x18002cf6a  mov     r8d, ebx; nSize
0x18002cf6d  lea     rcx, Src; "FXSAPIDebugLogFile.txt"
0x18002cf74  call    cs:__imp_ExpandEnvironmentStringsW
0x18002cf7b  nop     dword ptr [rax+rax+00h]
0x18002cf80  dec     eax
0x18002cf82  cmp     eax, 103h
0x18002cf87  ja      short loc_18002CFEB
0x18002cf89  mov     edx, 5Ch ; '\'; Ch
0x18002cf8e  lea     rcx, [rsp+478h+Dst]; Str
0x18002cf93  call    cs:__imp_wcschr
0x18002cf9a  nop     dword ptr [rax+rax+00h]
0x18002cf9f  xor     edi, edi
0x18002cfa1  test    rax, rax
0x18002cfa4  jnz     short loc_18002D00F
0x18002cfa6  lea     rdx, [rsp+478h+var_228]
0x18002cfae  mov     ecx, ebx
0x18002cfb0  call    cs:__imp_GetTempPath2W
0x18002cfb7  nop     dword ptr [rax+rax+00h]
0x18002cfbc  test    eax, eax
0x18002cfbe  jz      short loc_18002CFEB
0x18002cfc0  lea     rax, [rsp+478h+Dst]
0x18002cfc5  mov     edx, ebx; unsigned __int64
0x18002cfc7  lea     r9, [rsp+478h+var_228]
0x18002cfcf  mov     qword ptr [rsp+478h+var_458], rax
0x18002cfd4  lea     r8, aSS_0; "%s%s"
0x18002cfdb  lea     rcx, ?g_szPathToFile@@3PAGA; unsigned __int16 *
0x18002cfe2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002cfe7  test    eax, eax
0x18002cfe9  jns     short loc_18002D054
0x18002cfeb  xor     eax, eax
0x18002cfed  mov     rcx, [rsp+478h+var_18]
0x18002cff5  xor     rcx, rsp; StackCookie
0x18002cff8  call    __security_check_cookie
0x18002cffd  mov     rbx, [rsp+478h+arg_0]
0x18002d005  add     rsp, 470h
0x18002d00c  pop     rdi
0x18002d00d  retn
0x18002d00f  mov     ecx, 7FFFFFFEh
0x18002d014  lea     rdx, [rsp+478h+Dst]
0x18002d019  lea     rax, ?g_szPathToFile@@3PAGA; ushort near * g_szPathToFile
0x18002d020  test    rcx, rcx
0x18002d023  jz      short loc_18002D044
0x18002d025  movzx   r8d, word ptr [rdx]
0x18002d029  test    r8w, r8w
0x18002d02d  jz      short loc_18002D044
0x18002d02f  mov     [rax], r8w
0x18002d033  add     rdx, 2
0x18002d037  add     rax, 2
0x18002d03b  dec     rcx
0x18002d03e  sub     rbx, 1
0x18002d042  jnz     short loc_18002D020
0x18002d044  test    rbx, rbx
0x18002d047  lea     rdx, [rax-2]
0x18002d04b  cmovnz  rdx, rax
0x18002d04f  mov     [rdx], di
0x18002d052  jz      short loc_18002CFEB
0x18002d054  mov     [rsp+478h+var_450], 80h; int
0x18002d05c  lea     rcx, ?g_szPathToFile@@3PAGA; lpFileName
0x18002d063  mov     edx, 40000000h; dwDesiredAccess
0x18002d068  mov     [rsp+478h+var_458], 4; DWORD
0x18002d070  mov     r8d, 3; dwShareMode
0x18002d076  call    InternalSafeCreateFile
0x18002d07b  mov     cs:?g_hLogFile@@3PEAXEA, rax; void * g_hLogFile
0x18002d082  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d086  jz      loc_18002CFEB
0x18002d08c  mov     r9d, 2; dwMoveMethod
0x18002d092  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002d095  xor     edx, edx; lDistanceToMove
0x18002d097  mov     rcx, rax; hFile
0x18002d09a  call    cs:__imp_SetFilePointer
0x18002d0a1  nop     dword ptr [rax+rax+00h]
0x18002d0a6  cmp     eax, 0FFFFFFFFh
0x18002d0a9  jnz     short loc_18002D0CE
0x18002d0ab  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x18002d0b2  call    cs:__imp_CloseHandle
0x18002d0b9  nop     dword ptr [rax+rax+00h]
0x18002d0be  mov     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x18002d0c9  jmp     loc_18002CFEB
0x18002d0ce  mov     eax, 1
0x18002d0d3  xchg    eax, cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x18002d0d9  jmp     loc_18002CF56
```
