# CFileStream::HrSeek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180092120`
- end: `0x18009221f`
- name: `?HrSeek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `255`
- prototype: `int(CFileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180092120`
- `0x1800bb784`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800921cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800921cf`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180092180`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180092180`

## pseudocode

```c
__int64 __fastcall CFileStream::HrSeek(CFileStream *this, union _LARGE_INTEGER a2, DWORD a3, union _ULARGE_INTEGER *a4)
{
  char *v4; // r14
  LONG LowPart; // ebx
  void *v9; // rcx
  unsigned int v10; // edi
  DWORD v11; // ebx
  int v12; // eax
  LONG v14; // ecx
  signed int LastError; // eax
  bool v16; // zf
  LONG DistanceToMoveHigh; // [rsp+40h] [rbp+8h] BYREF
  union _LARGE_INTEGER v18; // [rsp+48h] [rbp+10h]

  v18 = a2;
  v4 = (char *)this + 16;
  LowPart = a2.LowPart;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 112LL))((char *)this + 16);
  v9 = (void *)*((_QWORD *)this + 15);
  DistanceToMoveHigh = 0;
  if ( v9 == (void *)-1LL )
  {
    v16 = (_DWORD)g_doStackCaptures == 0;
    v10 = -2003292404;
LABEL_13:
    if ( v16 )
      goto LABEL_4;
LABEL_14:
    DoStackCapture(v10);
    goto LABEL_4;
  }
  DistanceToMoveHigh = v18.HighPart;
  v10 = 0;
  v11 = SetFilePointer(v9, LowPart, &DistanceToMoveHigh, a3);
  if ( v11 != -1 || (LastError = GetLastError()) == 0 )
  {
    v12 = (int)g_doStackCaptures;
    if ( !a4 )
      goto LABEL_4;
    v14 = DistanceToMoveHigh;
    a4->LowPart = v11;
    if ( v14 >= 0 )
    {
      v10 = 0;
      a4->HighPart = v14;
      goto LABEL_4;
    }
    v10 = -2147024362;
    a4->HighPart = -1;
    v16 = v12 == 0;
    goto LABEL_13;
  }
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  else
    v10 = LastError;
  if ( (_DWORD)g_doStackCaptures )
    goto LABEL_14;
LABEL_4:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 120LL))(v4);
  return v10;
}

```

## disassembly

```asm
0x180092120  mov     [rsp+arg_10], rbx
0x180092125  mov     [rsp+arg_18], rbp
0x18009212a  mov     [rsp+arg_8], rdx
0x18009212f  push    rsi
0x180092130  push    rdi
0x180092131  push    r14
0x180092133  sub     rsp, 20h
0x180092137  lea     r14, [rcx+10h]
0x18009213b  mov     rdi, rcx
0x18009213e  mov     rax, [r14]
0x180092141  mov     rcx, r14
0x180092144  mov     rsi, r9
0x180092147  mov     ebp, r8d
0x18009214a  mov     rbx, rdx
0x18009214d  mov     rax, [rax+70h]
0x180092151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092156  mov     rcx, [rdi+78h]; hFile
0x18009215a  mov     [rsp+38h+DistanceToMoveHigh], 0
0x180092162  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180092166  jz      loc_180092206
0x18009216c  mov     eax, dword ptr [rsp+38h+arg_8+4]
0x180092170  lea     r8, [rsp+38h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180092175  mov     r9d, ebp; dwMoveMethod
0x180092178  mov     [rsp+38h+DistanceToMoveHigh], eax
0x18009217c  mov     edx, ebx; lDistanceToMove
0x18009217e  xor     edi, edi
0x180092180  call    cs:__imp_SetFilePointer
0x180092186  or      ebp, 0FFFFFFFFh
0x180092189  mov     ebx, eax
0x18009218b  cmp     eax, ebp
0x18009218d  jz      short loc_1800921CF
0x18009218f  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180092195  test    rsi, rsi
0x180092198  jnz     short loc_1800921BE
0x18009219a  mov     rdx, [r14]
0x18009219d  mov     rcx, r14
0x1800921a0  mov     rax, [rdx+78h]
0x1800921a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800921a9  mov     rbx, [rsp+38h+arg_10]
0x1800921ae  mov     eax, edi
0x1800921b0  mov     rbp, [rsp+38h+arg_18]
0x1800921b5  add     rsp, 20h
0x1800921b9  pop     r14
0x1800921bb  pop     rdi
0x1800921bc  pop     rsi
0x1800921bd  retn
0x1800921be  mov     ecx, [rsp+38h+DistanceToMoveHigh]
0x1800921c2  mov     [rsi], ebx
0x1800921c4  test    ecx, ecx
0x1800921c6  js      short loc_1800921F1
0x1800921c8  xor     edi, edi
0x1800921ca  mov     [rsi+4], ecx
0x1800921cd  jmp     short loc_18009219A
0x1800921cf  call    cs:__imp_GetLastError
0x1800921d5  test    eax, eax
0x1800921d7  jz      short loc_18009218F
0x1800921d9  jg      short loc_180092214
0x1800921db  mov     edi, eax
0x1800921dd  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800921e3  test    edi, edi
0x1800921e5  jns     short loc_180092195
0x1800921e7  test    eax, eax
0x1800921e9  jnz     short loc_1800921FD
0x1800921eb  test    edi, edi
0x1800921ed  js      short loc_18009219A
0x1800921ef  jmp     short loc_180092195
0x1800921f1  mov     edi, 80070216h
0x1800921f6  mov     [rsi+4], ebp
0x1800921f9  test    eax, eax
0x1800921fb  jz      short loc_18009219A
0x1800921fd  mov     ecx, edi; int
0x1800921ff  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180092204  jmp     short loc_18009219A
0x180092206  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18009220d  mov     edi, 88982F0Ch
0x180092212  jmp     short loc_1800921FB
0x180092214  movzx   edi, ax
0x180092217  or      edi, 80070000h
0x18009221d  jmp     short loc_1800921DD
```
