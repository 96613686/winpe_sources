# C449File::Load(void)

- ea: `0x180048848`
- end: `0x18004898e`
- name: `?Load@C449File@@QEAAJXZ`
- size: `326`
- prototype: `__int64 __fastcall(C449File *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800482a8`
- `0x180048648`
- `0x18004877c`

## callees

- `0x180013f04`
- `0x180023d6e`
- `0x180048848`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180048889`
- `KERNEL32!HeapFree` at `0x180048889`
- `KERNEL32!HeapAlloc` at `0x18004892c`
- `KERNEL32!HeapAlloc` at `0x18004892c`
- `KERNEL32!MapViewOfFile` at `0x18004890b`
- `KERNEL32!MapViewOfFile` at `0x18004890b`
- `KERNEL32!CreateFileMappingW` at `0x1800488eb`
- `KERNEL32!CreateFileMappingW` at `0x1800488eb`
- `KERNEL32!GetFileSize` at `0x1800488b7`
- `KERNEL32!GetFileSize` at `0x1800488b7`
- `KERNEL32!UnmapViewOfFile` at `0x180048957`
- `KERNEL32!UnmapViewOfFile` at `0x180048957`
- `KERNEL32!WaitForSingleObject` at `0x18004886c`
- `KERNEL32!WaitForSingleObject` at `0x18004886c`
- `KERNEL32!CloseHandle` at `0x180048960`
- `KERNEL32!CloseHandle` at `0x180048969`
- `KERNEL32!CloseHandle` at `0x180048960`
- `KERNEL32!CloseHandle` at `0x180048969`
- `KERNEL32!SetEvent` at `0x180048976`
- `KERNEL32!SetEvent` at `0x180048976`

## pseudocode

```c
__int64 __fastcall C449File::Load(C449File *this, __int64 a2, __int64 a3, struct _SECURITY_ATTRIBUTES *a4)
{
  int v4; // ebx
  void *v6; // r8
  const unsigned __int16 *v7; // rcx
  void *File; // rax
  void *v9; // rsi
  DWORD FileSize; // eax
  SIZE_T v11; // r15
  HANDLE FileMappingW; // rax
  void *v13; // rbp
  const void *v14; // r14
  void *v15; // rax
  void *v16; // rcx

  v4 = 0;
  if ( _InterlockedExchange((volatile __int32 *)this + 13, 0) )
  {
    v6 = (void *)*((_QWORD *)this + 8);
    if ( v6 )
      HeapFree(g_hDenaliHeap, 0, v6);
    v7 = (const unsigned __int16 *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 8) = 0;
    *((_DWORD *)this + 18) = 0;
    File = (void *)AspCreateFile(v7, a2, (__int64)v6, a4);
    v9 = File;
    if ( File == (void *)-1LL )
    {
      v4 = -2147467259;
    }
    else
    {
      FileSize = GetFileSize(File, 0);
      v11 = FileSize;
      if ( ((FileSize + 1) & 0xFFFFFFFE) != 0
        && (FileMappingW = CreateFileMappingW(v9, 0, 2u, 0, 0, 0), (v13 = FileMappingW) != 0) )
      {
        v14 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        if ( v14 )
        {
          v15 = HeapAlloc(g_hDenaliHeap, 0, v11);
          *((_QWORD *)this + 8) = v15;
          if ( v15 )
          {
            memcpy_0(v15, v14, v11);
            *((_DWORD *)this + 18) = v11;
          }
          else
          {
            v4 = -2147024882;
          }
          UnmapViewOfFile(v14);
        }
        else
        {
          v4 = -2147467259;
        }
        CloseHandle(v13);
      }
      else
      {
        v4 = -2147467259;
      }
      CloseHandle(v9);
    }
    v16 = (void *)*((_QWORD *)this + 11);
    *((_DWORD *)this + 24) = v4;
    SetEvent(v16);
  }
  else
  {
    WaitForSingleObject(*((HANDLE *)this + 11), 0xFFFFFFFF);
  }
  return *((unsigned int *)this + 24);
}

```

## disassembly

```asm
0x180048848  push    rbx
0x18004884a  push    rbp
0x18004884b  push    rsi
0x18004884c  push    rdi
0x18004884d  push    r12
0x18004884f  push    r14
0x180048851  push    r15
0x180048853  sub     rsp, 40h
0x180048857  xor     ebx, ebx
0x180048859  mov     rdi, rcx
0x18004885c  mov     eax, ebx
0x18004885e  xchg    eax, [rcx+34h]
0x180048861  test    eax, eax
0x180048863  jnz     short loc_180048877
0x180048865  mov     rcx, [rcx+58h]; hHandle
0x180048869  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18004886c  call    cs:__imp_WaitForSingleObject
0x180048872  jmp     loc_18004897C
0x180048877  mov     r8, [rcx+40h]; lpMem
0x18004887b  test    r8, r8
0x18004887e  jz      short loc_18004888F
0x180048880  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180048887  xor     edx, edx; dwFlags
0x180048889  call    cs:__imp_HeapFree
0x18004888f  mov     rcx, [rdi+38h]; unsigned __int16 *
0x180048893  mov     [rdi+40h], rbx
0x180048897  mov     [rdi+48h], ebx
0x18004889a  call    ?AspCreateFile@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; AspCreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18004889f  mov     rsi, rax
0x1800488a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800488a6  jnz     short loc_1800488B2
0x1800488a8  mov     ebx, 80004005h
0x1800488ad  jmp     loc_18004896F
0x1800488b2  xor     edx, edx; lpFileSizeHigh
0x1800488b4  mov     rcx, rsi; hFile
0x1800488b7  call    cs:__imp_GetFileSize
0x1800488bd  mov     r15d, eax
0x1800488c0  lea     ecx, [r15+1]
0x1800488c4  test    ecx, 0FFFFFFFEh
0x1800488ca  jnz     short loc_1800488D6
0x1800488cc  mov     ebx, 80004005h
0x1800488d1  jmp     loc_180048966
0x1800488d6  xor     r9d, r9d; dwMaximumSizeHigh
0x1800488d9  mov     [rsp+78h+lpName], rbx; lpName
0x1800488de  xor     edx, edx; lpFileMappingAttributes
0x1800488e0  mov     [rsp+78h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x1800488e4  mov     rcx, rsi; hFile
0x1800488e7  lea     r8d, [r9+2]; flProtect
0x1800488eb  call    cs:__imp_CreateFileMappingW
0x1800488f1  mov     rbp, rax
0x1800488f4  test    rax, rax
0x1800488f7  jz      short loc_1800488CC
0x1800488f9  xor     r9d, r9d; dwFileOffsetLow
0x1800488fc  mov     qword ptr [rsp+78h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x180048901  xor     r8d, r8d; dwFileOffsetHigh
0x180048904  mov     rcx, rax; hFileMappingObject
0x180048907  lea     edx, [r9+4]; dwDesiredAccess
0x18004890b  call    cs:__imp_MapViewOfFile
0x180048911  mov     r14, rax
0x180048914  test    rax, rax
0x180048917  jnz     short loc_180048920
0x180048919  mov     ebx, 80004005h
0x18004891e  jmp     short loc_18004895D
0x180048920  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180048927  mov     r8, r15; dwBytes
0x18004892a  xor     edx, edx; dwFlags
0x18004892c  call    cs:__imp_HeapAlloc
0x180048932  mov     [rdi+40h], rax
0x180048936  test    rax, rax
0x180048939  jz      short loc_18004894F
0x18004893b  mov     r8, r15; Size
0x18004893e  mov     rdx, r14; Src
0x180048941  mov     rcx, rax; void *
0x180048944  call    memcpy_0
0x180048949  mov     [rdi+48h], r15d
0x18004894d  jmp     short loc_180048954
0x18004894f  mov     ebx, 8007000Eh
0x180048954  mov     rcx, r14; lpBaseAddress
0x180048957  call    cs:__imp_UnmapViewOfFile
0x18004895d  mov     rcx, rbp; hObject
0x180048960  call    cs:__imp_CloseHandle
0x180048966  mov     rcx, rsi; hObject
0x180048969  call    cs:__imp_CloseHandle
0x18004896f  mov     rcx, [rdi+58h]; hEvent
0x180048973  mov     [rdi+60h], ebx
0x180048976  call    cs:__imp_SetEvent
0x18004897c  mov     eax, [rdi+60h]
0x18004897f  add     rsp, 40h
0x180048983  pop     r15
0x180048985  pop     r14
0x180048987  pop     r12
0x180048989  pop     rdi
0x18004898a  pop     rsi
0x18004898b  pop     rbp
0x18004898c  pop     rbx
0x18004898d  retn
```
