# WriteFileHeader

- ea: `0x180033fa8`
- end: `0x180034094`
- name: `WriteFileHeader`
- size: `236`
- prototype: `__int64 __fastcall(void *, PUCHAR Buffer)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180031754`
- `0x18003218c`
- `0x180032794`
- `0x180032a8c`
- `0x180033258`

## callees

- `0x180023548`
- `0x180033fa8`
- `0x180034ba4`
- `0x180034fc0`
- `0x180034fe4`
- `0x180035278`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180034070`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180034070`

## pseudocode

```c
__int64 __fastcall WriteFileHeader(void *a1, _DWORD *Buffer, __int64 a3, char a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // r9d
  int v10; // r10d
  unsigned int v11; // eax
  int v12; // r10d
  unsigned int v13; // ebx
  _BYTE v15[8]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16; // [rsp+28h] [rbp-30h]
  _DWORD *v17; // [rsp+30h] [rbp-28h]
  unsigned int v18; // [rsp+40h] [rbp-18h]
  char v19; // [rsp+49h] [rbp-Fh]

  v16 = -1;
  v17 = Buffer;
  v18 = 128;
  v19 = 0;
  FileView::SetPointers((FileView *)v15);
  v10 = Buffer[30];
  v16 = 0;
  v11 = v10 & 0xFFFFFFFE;
  v12 = v10 | 1;
  if ( !(_BYTE)v8 )
    v12 = v11;
  Buffer[30] = v12;
  Buffer[31] = CalcGeneralHeaderCRC((PUCHAR)Buffer, v7, v8, v9);
  v13 = FileView::ActualWrite((FileView *)v15, a1, 0, v18);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v13);
    }
  }
  else
  {
    if ( a4 )
      FlushFileBuffers(a1);
    v13 = 0;
  }
  FileView::~FileView((FileView *)v15);
  return v13;
}

```

## disassembly

```asm
0x180033fa8  mov     rax, rsp
0x180033fab  mov     [rax+8], rbx
0x180033faf  mov     [rax+10h], rsi
0x180033fb3  push    rdi
0x180033fb4  sub     rsp, 50h
0x180033fb8  mov     sil, r9b
0x180033fbb  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFFh
0x180033fc3  mov     r9d, 80h
0x180033fc9  mov     [rax-28h], rdx
0x180033fcd  mov     rdi, rcx
0x180033fd0  mov     [rax-18h], r9d
0x180033fd4  lea     rcx, [rax-38h]; this
0x180033fd8  mov     byte ptr [rax-0Fh], 0
0x180033fdc  mov     rbx, rdx
0x180033fdf  call    ?SetPointers@FileView@@QEAAXXZ; FileView::SetPointers(void)
0x180033fe4  mov     r10d, [rbx+78h]
0x180033fe8  mov     rcx, rbx; Buffer
0x180033feb  mov     eax, r10d
0x180033fee  mov     [rsp+58h+var_30], 0
0x180033ff7  and     eax, 0FFFFFFFEh
0x180033ffa  or      r10d, 1
0x180033ffe  test    r8b, r8b
0x180034001  cmovz   r10d, eax
0x180034005  mov     [rbx+78h], r10d
0x180034009  call    ?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z; CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)
0x18003400e  mov     [rbx+7Ch], eax
0x180034011  lea     rcx, [rsp+58h+var_38]; this
0x180034016  mov     r9d, [rsp+58h+var_18]; unsigned int
0x18003401b  xor     r8d, r8d; unsigned int
0x18003401e  mov     rdx, rdi; void *
0x180034021  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180034026  mov     ebx, eax
0x180034028  test    eax, eax
0x18003402a  jz      short loc_180034068
0x18003402c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034033  lea     rax, WPP_GLOBAL_Control
0x18003403a  cmp     rcx, rax
0x18003403d  jz      short loc_180034078
0x18003403f  test    dword ptr [rcx+1Ch], 8000h
0x180034046  jz      short loc_180034078
0x180034048  cmp     byte ptr [rcx+19h], 2
0x18003404c  jb      short loc_180034078
0x18003404e  mov     rcx, [rcx+10h]
0x180034052  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180034059  mov     edx, 0Ah
0x18003405e  mov     r9d, ebx
0x180034061  call    WPP_SF_D
0x180034066  jmp     short loc_180034078
0x180034068  test    sil, sil
0x18003406b  jz      short loc_180034076
0x18003406d  mov     rcx, rdi; hFile
0x180034070  call    cs:__imp_FlushFileBuffers
0x180034076  xor     ebx, ebx
0x180034078  lea     rcx, [rsp+58h+var_38]; this
0x18003407d  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180034082  mov     rsi, [rsp+58h+arg_8]
0x180034087  mov     eax, ebx
0x180034089  mov     rbx, [rsp+58h+arg_0]
0x18003408e  add     rsp, 50h
0x180034092  pop     rdi
0x180034093  retn
```
