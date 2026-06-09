# CFileStream::HrSeek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x1800927c0`
- end: `0x1800928cc`
- name: `?HrSeek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `268`
- prototype: `int(CFileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800927c0`
- `0x1800bd9d4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092876`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180092820`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180092820`

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
0x1800927c0  mov     [rsp+arg_10], rbx
0x1800927c5  mov     [rsp+arg_18], rbp
0x1800927ca  mov     [rsp+arg_8], rdx
0x1800927cf  push    rsi
0x1800927d0  push    rdi
0x1800927d1  push    r14
0x1800927d3  sub     rsp, 20h
0x1800927d7  lea     r14, [rcx+10h]
0x1800927db  mov     rdi, rcx
0x1800927de  mov     rax, [r14]
0x1800927e1  mov     rcx, r14
0x1800927e4  mov     rsi, r9
0x1800927e7  mov     ebp, r8d
0x1800927ea  mov     rbx, rdx
0x1800927ed  mov     rax, [rax+70h]
0x1800927f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800927f6  mov     rcx, [rdi+78h]; hFile
0x1800927fa  mov     [rsp+38h+DistanceToMoveHigh], 0
0x180092802  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180092806  jz      loc_1800928B3
0x18009280c  mov     eax, dword ptr [rsp+38h+arg_8+4]
0x180092810  lea     r8, [rsp+38h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180092815  mov     r9d, ebp; dwMoveMethod
0x180092818  mov     [rsp+38h+DistanceToMoveHigh], eax
0x18009281c  mov     edx, ebx; lDistanceToMove
0x18009281e  xor     edi, edi
0x180092820  call    cs:__imp_SetFilePointer
0x180092827  nop     dword ptr [rax+rax+00h]
0x18009282c  or      ebp, 0FFFFFFFFh
0x18009282f  mov     ebx, eax
0x180092831  cmp     eax, ebp
0x180092833  jz      short loc_180092876
0x180092835  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18009283b  test    rsi, rsi
0x18009283e  jnz     short loc_180092865
0x180092840  mov     rdx, [r14]
0x180092843  mov     rcx, r14
0x180092846  mov     rax, [rdx+78h]
0x18009284a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009284f  mov     rbx, [rsp+38h+arg_10]
0x180092854  mov     eax, edi
0x180092856  mov     rbp, [rsp+38h+arg_18]
0x18009285b  add     rsp, 20h
0x18009285f  pop     r14
0x180092861  pop     rdi
0x180092862  pop     rsi
0x180092863  retn
0x180092865  mov     ecx, [rsp+38h+DistanceToMoveHigh]
0x180092869  mov     [rsi], ebx
0x18009286b  test    ecx, ecx
0x18009286d  js      short loc_18009289E
0x18009286f  xor     edi, edi
0x180092871  mov     [rsi+4], ecx
0x180092874  jmp     short loc_180092840
0x180092876  call    cs:__imp_GetLastError
0x18009287d  nop     dword ptr [rax+rax+00h]
0x180092882  test    eax, eax
0x180092884  jz      short loc_180092835
0x180092886  jg      short loc_1800928C1
0x180092888  mov     edi, eax
0x18009288a  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180092890  test    edi, edi
0x180092892  jns     short loc_18009283B
0x180092894  test    eax, eax
0x180092896  jnz     short loc_1800928AA
0x180092898  test    edi, edi
0x18009289a  js      short loc_180092840
0x18009289c  jmp     short loc_18009283B
0x18009289e  mov     edi, 80070216h
0x1800928a3  mov     [rsi+4], ebp
0x1800928a6  test    eax, eax
0x1800928a8  jz      short loc_180092840
0x1800928aa  mov     ecx, edi; int
0x1800928ac  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800928b1  jmp     short loc_180092840
0x1800928b3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800928ba  mov     edi, 88982F0Ch
0x1800928bf  jmp     short loc_1800928A8
0x1800928c1  movzx   edi, ax
0x1800928c4  or      edi, 80070000h
0x1800928ca  jmp     short loc_18009288A
```
