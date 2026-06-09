# CFileStream::HrGetPosition(_ULARGE_INTEGER *)

- ea: `0x1800a18a0`
- end: `0x1800a1983`
- name: `?HrGetPosition@CFileStream@@UEAAJPEAT_ULARGE_INTEGER@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800a18a0`
- `0x1800bb784`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1943`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a18ee`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a18ee`

## pseudocode

```c
__int64 __fastcall CFileStream::HrGetPosition(CFileStream *this, union _ULARGE_INTEGER *a2)
{
  char *v2; // rsi
  void *v5; // rcx
  DWORD v6; // ebp
  int v7; // eax
  LONG v8; // ecx
  signed int v9; // ebx
  bool v11; // zf
  signed int LastError; // eax
  LONG DistanceToMoveHigh; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 16;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 112LL))((char *)this + 16);
  DistanceToMoveHigh = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    goto LABEL_18;
  }
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 == (void *)-1LL )
  {
    v9 = -2003292404;
LABEL_18:
    v11 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_9;
  }
  v6 = SetFilePointer(v5, 0, &DistanceToMoveHigh, 1u);
  if ( v6 == -1 && (LastError = GetLastError(), (v9 = LastError) != 0) )
  {
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v7 = (int)g_doStackCaptures;
    if ( v9 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_7;
      goto LABEL_10;
    }
  }
  else
  {
    v7 = (int)g_doStackCaptures;
  }
  v8 = DistanceToMoveHigh;
  a2->LowPart = v6;
  if ( v8 >= 0 )
  {
    v9 = 0;
    a2->HighPart = v8;
    goto LABEL_7;
  }
  v9 = -2147024362;
  a2->HighPart = -1;
  v11 = v7 == 0;
LABEL_9:
  if ( !v11 )
LABEL_10:
    DoStackCapture(v9);
LABEL_7:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 120LL))(v2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a18a0  push    rbx
0x1800a18a2  push    rbp
0x1800a18a3  push    rsi
0x1800a18a4  push    rdi
0x1800a18a5  sub     rsp, 28h
0x1800a18a9  lea     rsi, [rcx+10h]
0x1800a18ad  mov     rbx, rcx
0x1800a18b0  mov     rax, [rsi]
0x1800a18b3  mov     rcx, rsi
0x1800a18b6  mov     rdi, rdx
0x1800a18b9  mov     rax, [rax+70h]
0x1800a18bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18c2  mov     [rsp+48h+DistanceToMoveHigh], 0
0x1800a18ca  test    rdi, rdi
0x1800a18cd  jz      loc_1800A197C
0x1800a18d3  mov     rcx, [rbx+78h]; hFile
0x1800a18d7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a18db  jz      loc_1800A196E
0x1800a18e1  mov     r9d, 1; dwMoveMethod
0x1800a18e7  lea     r8, [rsp+48h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800a18ec  xor     edx, edx; lDistanceToMove
0x1800a18ee  call    cs:__imp_SetFilePointer
0x1800a18f4  mov     ebp, eax
0x1800a18f6  cmp     eax, 0FFFFFFFFh
0x1800a18f9  jz      short loc_1800A1943
0x1800a18fb  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800a1901  mov     ecx, [rsp+48h+DistanceToMoveHigh]
0x1800a1905  mov     [rdi], ebp
0x1800a1907  test    ecx, ecx
0x1800a1909  js      short loc_1800A192A
0x1800a190b  xor     ebx, ebx
0x1800a190d  mov     [rdi+4], ecx
0x1800a1910  mov     rdx, [rsi]
0x1800a1913  mov     rcx, rsi
0x1800a1916  mov     rax, [rdx+78h]
0x1800a191a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a191f  mov     eax, ebx
0x1800a1921  add     rsp, 28h
0x1800a1925  pop     rdi
0x1800a1926  pop     rsi
0x1800a1927  pop     rbp
0x1800a1928  pop     rbx
0x1800a1929  retn
0x1800a192a  mov     ebx, 80070216h
0x1800a192f  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x1800a1936  test    eax, eax
0x1800a1938  jz      short loc_1800A1910
0x1800a193a  mov     ecx, ebx; int
0x1800a193c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a1941  jmp     short loc_1800A1910
0x1800a1943  call    cs:__imp_GetLastError
0x1800a1949  mov     ebx, eax
0x1800a194b  test    eax, eax
0x1800a194d  jz      short loc_1800A18FB
0x1800a194f  jle     short loc_1800A195A
0x1800a1951  movzx   ebx, ax
0x1800a1954  or      ebx, 80070000h
0x1800a195a  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800a1960  test    ebx, ebx
0x1800a1962  jns     short loc_1800A1901
0x1800a1964  test    eax, eax
0x1800a1966  jnz     short loc_1800A193A
0x1800a1968  test    ebx, ebx
0x1800a196a  jns     short loc_1800A1901
0x1800a196c  jmp     short loc_1800A1910
0x1800a196e  mov     ebx, 88982F0Ch
0x1800a1973  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800a197a  jmp     short loc_1800A1938
0x1800a197c  mov     ebx, 80070057h
0x1800a1981  jmp     short loc_1800A1973
```
