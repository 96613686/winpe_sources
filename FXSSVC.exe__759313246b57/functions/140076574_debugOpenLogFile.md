# debugOpenLogFile

- ea: `0x140076574`
- end: `0x140076752`
- name: `debugOpenLogFile`
- size: `478`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400246b0`
- `0x1400289cc`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x14006e124`
- `0x140076574`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x140076624`
- `KERNEL32!GetTempPath2W` at `0x140076624`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400765e8`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400765e8`
- `KERNEL32!CloseHandle` at `0x140076726`
- `KERNEL32!CloseHandle` at `0x140076726`
- `KERNEL32!SetFilePointer` at `0x14007670e`
- `KERNEL32!SetFilePointer` at `0x14007670e`
- `msvcrt!wcschr` at `0x140076607`
- `msvcrt!wcschr` at `0x140076607`

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
  if ( ExpandEnvironmentStringsW(L"FXSSVCDebugLogFile.txt", Dst, 0x104u) - 1 <= 0x103 )
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
0x140076574  mov     [rsp+arg_0], rbx
0x140076579  push    rdi
0x14007657a  sub     rsp, 470h
0x140076581  mov     rax, cs:__security_cookie
0x140076588  xor     rax, rsp
0x14007658b  mov     [rsp+478h+var_18], rax
0x140076593  mov     ebx, 208h
0x140076598  lea     rcx, [rsp+478h+Dst]; void *
0x14007659d  mov     r8d, ebx; Size
0x1400765a0  xor     edx, edx; Val
0x1400765a2  call    memset_0
0x1400765a7  mov     r8d, ebx; Size
0x1400765aa  lea     rcx, [rsp+478h+var_228]; void *
0x1400765b2  xor     edx, edx; Val
0x1400765b4  call    memset_0
0x1400765b9  cmp     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x1400765c1  jz      short loc_1400765D4
0x1400765c3  lock inc cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x1400765ca  mov     eax, 1
0x1400765cf  jmp     loc_140076661
0x1400765d4  mov     ebx, 104h
0x1400765d9  lea     rdx, [rsp+478h+Dst]; lpDst
0x1400765de  mov     r8d, ebx; nSize
0x1400765e1  lea     rcx, Src; "FXSSVCDebugLogFile.txt"
0x1400765e8  call    cs:__imp_ExpandEnvironmentStringsW
0x1400765ef  nop     dword ptr [rax+rax+00h]
0x1400765f4  dec     eax
0x1400765f6  cmp     eax, 103h
0x1400765fb  ja      short loc_14007665F
0x1400765fd  mov     edx, 5Ch ; '\'; Ch
0x140076602  lea     rcx, [rsp+478h+Dst]; Str
0x140076607  call    cs:__imp_wcschr
0x14007660e  nop     dword ptr [rax+rax+00h]
0x140076613  xor     edi, edi
0x140076615  test    rax, rax
0x140076618  jnz     short loc_140076683
0x14007661a  lea     rdx, [rsp+478h+var_228]
0x140076622  mov     ecx, ebx
0x140076624  call    cs:__imp_GetTempPath2W
0x14007662b  nop     dword ptr [rax+rax+00h]
0x140076630  test    eax, eax
0x140076632  jz      short loc_14007665F
0x140076634  lea     rax, [rsp+478h+Dst]
0x140076639  mov     edx, ebx; unsigned __int64
0x14007663b  lea     r9, [rsp+478h+var_228]
0x140076643  mov     qword ptr [rsp+478h+var_458], rax
0x140076648  lea     r8, aSS_1; "%s%s"
0x14007664f  lea     rcx, ?g_szPathToFile@@3PAGA; unsigned __int16 *
0x140076656  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007665b  test    eax, eax
0x14007665d  jns     short loc_1400766C8
0x14007665f  xor     eax, eax
0x140076661  mov     rcx, [rsp+478h+var_18]
0x140076669  xor     rcx, rsp; StackCookie
0x14007666c  call    __security_check_cookie
0x140076671  mov     rbx, [rsp+478h+arg_0]
0x140076679  add     rsp, 470h
0x140076680  pop     rdi
0x140076681  retn
0x140076683  mov     ecx, 7FFFFFFEh
0x140076688  lea     rdx, [rsp+478h+Dst]
0x14007668d  lea     rax, ?g_szPathToFile@@3PAGA; ushort near * g_szPathToFile
0x140076694  test    rcx, rcx
0x140076697  jz      short loc_1400766B8
0x140076699  movzx   r8d, word ptr [rdx]
0x14007669d  test    r8w, r8w
0x1400766a1  jz      short loc_1400766B8
0x1400766a3  mov     [rax], r8w
0x1400766a7  add     rdx, 2
0x1400766ab  add     rax, 2
0x1400766af  dec     rcx
0x1400766b2  sub     rbx, 1
0x1400766b6  jnz     short loc_140076694
0x1400766b8  test    rbx, rbx
0x1400766bb  lea     rdx, [rax-2]
0x1400766bf  cmovnz  rdx, rax
0x1400766c3  mov     [rdx], di
0x1400766c6  jz      short loc_14007665F
0x1400766c8  mov     [rsp+478h+var_450], 80h; int
0x1400766d0  lea     rcx, ?g_szPathToFile@@3PAGA; lpFileName
0x1400766d7  mov     edx, 40000000h; dwDesiredAccess
0x1400766dc  mov     [rsp+478h+var_458], 4; DWORD
0x1400766e4  mov     r8d, 3; dwShareMode
0x1400766ea  call    InternalSafeCreateFile
0x1400766ef  mov     cs:?g_hLogFile@@3PEAXEA, rax; void * g_hLogFile
0x1400766f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400766fa  jz      loc_14007665F
0x140076700  mov     r9d, 2; dwMoveMethod
0x140076706  xor     r8d, r8d; lpDistanceToMoveHigh
0x140076709  xor     edx, edx; lDistanceToMove
0x14007670b  mov     rcx, rax; hFile
0x14007670e  call    cs:__imp_SetFilePointer
0x140076715  nop     dword ptr [rax+rax+00h]
0x14007671a  cmp     eax, 0FFFFFFFFh
0x14007671d  jnz     short loc_140076742
0x14007671f  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x140076726  call    cs:__imp_CloseHandle
0x14007672d  nop     dword ptr [rax+rax+00h]
0x140076732  mov     cs:?g_hLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hLogFile
0x14007673d  jmp     loc_14007665F
0x140076742  mov     eax, 1
0x140076747  xchg    eax, cs:?g_iLogFileRefCount@@3JA; long g_iLogFileRefCount
0x14007674d  jmp     loc_1400765CA
```
