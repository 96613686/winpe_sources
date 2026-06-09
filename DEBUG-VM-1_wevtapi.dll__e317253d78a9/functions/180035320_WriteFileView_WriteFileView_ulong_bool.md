# WriteFileView::WriteFileView(ulong,bool)

- ea: `0x180035320`
- end: `0x180035462`
- name: `??0WriteFileView@@QEAA@K_N@Z`
- size: `322`
- prototype: `WriteFileView *__fastcall(WriteFileView *__hidden this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180030e88`
- `0x180031754`
- `0x180033b9c`

## callees

- `0x180023548`
- `0x1800254b4`
- `0x180034f8c`
- `0x180035320`
- `0x1800357e0`
- `0x180038fb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WriteFileView *__fastcall WriteFileView::WriteFileView(WriteFileView *this, unsigned int a2, bool a3)
{
  unsigned int v5; // ebx
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v8; // [rsp+38h] [rbp-20h]
  __int64 v9; // [rsp+3Ch] [rbp-1Ch]
  char v10; // [rsp+44h] [rbp-14h]

  *(_QWORD *)this = &BufferStream::`vftable';
  FileView::FileView((WriteFileView *)((char *)this + 8), a2, a3);
  *(_QWORD *)this = &WriteFileView::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = &WriterStringTable::`vftable';
  *((_QWORD *)this + 9) = 0;
  memset_0((char *)this + 80, 0, 0x100u);
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = &WriterTemplateTable::`vftable';
  *((_QWORD *)this + 44) = 0;
  memset_0((char *)this + 360, 0, 0x80u);
  *((_QWORD *)this + 61) = 0;
  if ( a3 )
  {
    v5 = WriteFileView::TryAllocIfNecessary(this);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e8d0195a3cc637ab3689c79b5b31cbb7_Traceguids, v5);
      }
      pExceptionObject[0] = &word_18004024A;
      pExceptionObject[1] = 0;
      pExceptionObject[2] = 0;
      v8 = v5;
      v9 = -1;
      v10 = 0;
      throw (EvtException *)pExceptionObject;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180035320  mov     [rsp+arg_8], rbx
0x180035325  mov     [rsp+arg_0], rcx
0x18003532a  push    rdi
0x18003532b  sub     rsp, 50h
0x18003532f  mov     bl, r8b
0x180035332  mov     rdi, rcx
0x180035335  lea     rax, ??_7BufferStream@@6B@; const BufferStream::`vftable'
0x18003533c  mov     [rcx], rax
0x18003533f  add     rcx, 8; this
0x180035343  call    ??0FileView@@QEAA@K_N@Z; FileView::FileView(ulong,bool)
0x180035348  nop
0x180035349  lea     rax, ??_7WriteFileView@@6B@; const WriteFileView::`vftable'
0x180035350  mov     [rdi], rax
0x180035353  mov     qword ptr [rdi+38h], 0
0x18003535b  lea     rax, ??_7WriterStringTable@@6B@; const WriterStringTable::`vftable'
0x180035362  mov     [rdi+40h], rax
0x180035366  mov     qword ptr [rdi+48h], 0
0x18003536e  lea     rcx, [rdi+50h]; void *
0x180035372  xor     edx, edx; Val
0x180035374  mov     r8d, 100h; Size
0x18003537a  call    memset_0
0x18003537f  mov     qword ptr [rdi+150h], 0
0x18003538a  lea     rax, ??_7WriterTemplateTable@@6B@; const WriterTemplateTable::`vftable'
0x180035391  mov     [rdi+158h], rax
0x180035398  mov     qword ptr [rdi+160h], 0
0x1800353a3  lea     rcx, [rdi+168h]; void *
0x1800353aa  xor     edx, edx; Val
0x1800353ac  mov     r8d, 80h; Size
0x1800353b2  call    memset_0
0x1800353b7  mov     qword ptr [rdi+1E8h], 0
0x1800353c2  test    bl, bl
0x1800353c4  jz      loc_180035454
0x1800353ca  mov     rcx, rdi; this
0x1800353cd  call    ?TryAllocIfNecessary@WriteFileView@@QEAAKXZ; WriteFileView::TryAllocIfNecessary(void)
0x1800353d2  mov     ebx, eax
0x1800353d4  test    eax, eax
0x1800353d6  jz      short loc_180035454
0x1800353d8  lea     rax, WPP_GLOBAL_Control
0x1800353df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353e6  cmp     rcx, rax
0x1800353e9  jz      short loc_180035412
0x1800353eb  test    dword ptr [rcx+1Ch], 200h
0x1800353f2  jz      short loc_180035412
0x1800353f4  cmp     byte ptr [rcx+19h], 2
0x1800353f8  jb      short loc_180035412
0x1800353fa  mov     edx, 0Ah
0x1800353ff  mov     r9d, ebx
0x180035402  lea     r8, WPP_e8d0195a3cc637ab3689c79b5b31cbb7_Traceguids
0x180035409  mov     rcx, [rcx+10h]
0x18003540d  call    WPP_SF_D
0x180035412  lea     rax, word_18004024A
0x180035419  mov     [rsp+58h+pExceptionObject], rax
0x18003541e  mov     [rsp+58h+var_30], 0
0x180035427  mov     [rsp+58h+var_28], 0
0x180035430  mov     [rsp+58h+var_20], ebx
0x180035434  mov     [rsp+58h+var_1C], 0FFFFFFFFFFFFFFFFh
0x18003543d  mov     [rsp+58h+var_14], 0
0x180035442  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180035449  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18003544e  call    _CxxThrowException_0
0x180035454  mov     rax, rdi
0x180035457  mov     rbx, [rsp+58h+arg_8]
0x18003545c  add     rsp, 50h
0x180035460  pop     rdi
0x180035461  retn
```
