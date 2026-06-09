# C_SOURCEFILE::C_SOURCEFILE(C_SERIALIZE_PACKET *,C_SOURCEFILE *,C_BINARY *,_iobuf *,uchar *)

- ea: `0x18018bd28`
- end: `0x18018c044`
- name: `??0C_SOURCEFILE@@QEAA@PEAVC_SERIALIZE_PACKET@@PEAV0@PEAVC_BINARY@@PEAU_iobuf@@PEAE@Z`
- size: `796`
- prototype: `C_SOURCEFILE *__fastcall(C_SOURCEFILE *this, struct C_SERIALIZE_PACKET *, struct C_SOURCEFILE *, struct C_BINARY *, struct _iobuf *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18017835c`
- `0x180179878`
- `0x18017a654`
- `0x18017a974`

## callees

- `0x180003b00`
- `0x180149ae8`
- `0x18017ba78`
- `0x18017bf34`
- `0x18017c0a4`
- `0x18017c12c`
- `0x18017c724`
- `0x18017d118`
- `0x18017d480`
- `0x18017d4fc`
- `0x18018bd28`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18018be58`
- `KERNEL32!CreateFileMappingW` at `0x18018be58`
- `KERNEL32!MapViewOfFile` at `0x18018be7f`
- `KERNEL32!MapViewOfFile` at `0x18018be7f`
- `KERNEL32!GetFileSize` at `0x18018be2a`
- `KERNEL32!GetFileSize` at `0x18018be2a`
- `KERNEL32!CreateFileW` at `0x18018be0f`
- `KERNEL32!CreateFileW` at `0x18018be0f`
- `KERNEL32!CloseHandle` at `0x18018be8b`
- `KERNEL32!CloseHandle` at `0x18018bf82`
- `KERNEL32!CloseHandle` at `0x18018be8b`
- `KERNEL32!CloseHandle` at `0x18018bf82`

## string_xrefs

- `0x18018bfd7`: `C_SOURCEFILE::C_SOURCEFILE:   failed to open File:  `

## pseudocode

```c
C_SOURCEFILE *__fastcall C_SOURCEFILE::C_SOURCEFILE(
        C_SOURCEFILE *this,
        struct C_SERIALIZE_PACKET *a2,
        struct C_SOURCEFILE *a3,
        struct C_BINARY *a4,
        struct _iobuf *a5,
        unsigned __int8 *a6)
{
  bool v10; // zf
  const unsigned __int16 *v11; // r8
  unsigned int v12; // r9d
  __int64 v13; // r8
  C_BUFFER *v14; // r9
  HANDLE *v15; // r14
  HANDLE FileW; // rax
  __int64 v17; // rsi
  DWORD FileSize; // r12d
  HANDLE FileMappingW; // rax
  void *v20; // rbp
  unsigned __int8 *v21; // r13
  C_BUFFER *v22; // rax
  struct _iobuf *v23; // rbp
  __int64 v24; // r8
  __int64 v25; // r9
  C_BUFFER *v26; // rax
  int v27; // eax
  __int64 v28; // rcx
  void (__fastcall ***v29)(_QWORD, __int64, __int64, C_BUFFER *); // rcx
  __int64 v30; // rcx
  _QWORD v32[2]; // [rsp+40h] [rbp-78h] BYREF
  int v33; // [rsp+54h] [rbp-64h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-58h]

  C_SERIALIZE::C_SERIALIZE(this, a2, a5);
  v10 = *((_DWORD *)this + 5) == 0;
  *(_QWORD *)this = &C_SOURCEFILE::`vftable';
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = a4;
  *((_QWORD *)this + 7) = a3;
  *((_DWORD *)this + 16) = 2;
  if ( v10 )
  {
    if ( !a4
      || *((_DWORD *)a4 + 5)
      || (v11 = (const unsigned __int16 *)*((_QWORD *)a4 + 4)) == 0
      || (v12 = *((_DWORD *)a4 + 6) >> 1) == 0 )
    {
      *((_DWORD *)this + 5) = 1;
      return this;
    }
    C_WSTRINGZ::C_WSTRINGZ((C_WSTRINGZ *)v32, a2, v11, v12, a5);
    if ( v33 )
      goto LABEL_39;
    v15 = (HANDLE *)((char *)this + 32);
    if ( this != (C_SOURCEFILE *)-32LL )
    {
      FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v17 = -1;
      *v15 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        FileSize = GetFileSize(FileW, 0);
        if ( FileSize != -1 )
        {
          FileMappingW = CreateFileMappingW(*v15, 0, 2u, 0, 0, 0);
          v20 = FileMappingW;
          if ( FileMappingW )
          {
            v21 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
            CloseHandle(v20);
            if ( v21 )
            {
              *((_QWORD *)this + 3) = v21;
              if ( FileSize )
              {
                v22 = (C_BUFFER *)operator new(0x50u);
                v23 = a5;
                v26 = C_BUFFER::C_BUFFER(v22, a2, v24, v25, a5);
                *((_QWORD *)this + 5) = v26;
                v14 = v26;
                if ( !v26 )
                  goto LABEL_23;
                v27 = *((_DWORD *)v26 + 5);
                if ( v27 != 2 )
                {
                  if ( v27 == 1 )
                    goto LABEL_16;
                  if ( !v27 )
                  {
                    if ( !a6 )
                      goto LABEL_44;
                    do
                      ++v17;
                    while ( a6[v17] );
                    if ( !(_DWORD)v17 || C_BUFFER::InsertData(v14, a6, v17) )
                    {
LABEL_44:
                      if ( C_BUFFER::AddData(*((C_BUFFER **)this + 5), v21, FileSize, 0)
                        && !*(_DWORD *)(*((_QWORD *)this + 5) + 20LL) )
                      {
                        v28 = *((_QWORD *)this + 3);
                        if ( v28 )
                        {
                          UnmapFileFromMemory(v28, *v15);
                          *((_QWORD *)this + 3) = 0;
                        }
                        *((_DWORD *)this + 16) = 1;
                        goto LABEL_39;
                      }
                    }
                    goto LABEL_23;
                  }
                }
                (**(void (__fastcall ***)(C_BUFFER *, __int64))v14)(v14, 1);
LABEL_16:
                *((_QWORD *)this + 5) = 0;
LABEL_23:
                if ( *((_DWORD *)this + 5) != 2 )
                  *((_DWORD *)this + 5) = 1;
                goto LABEL_34;
              }
LABEL_33:
              v23 = a5;
LABEL_34:
              v29 = (void (__fastcall ***)(_QWORD, __int64, __int64, C_BUFFER *))*((_QWORD *)this + 5);
              if ( v29 )
              {
                (**v29)(v29, 1, v13, v14);
                *((_QWORD *)this + 5) = 0;
              }
              v30 = *((_QWORD *)this + 3);
              if ( v30 )
              {
                UnmapFileFromMemory(v30, *v15);
                *((_QWORD *)this + 3) = 0;
              }
              ErrorMessage(v23, "C_SOURCEFILE::C_SOURCEFILE:   failed to open File:  ", 3u);
              EmitWstr(v23, *((struct C_BINARY **)this + 6), 3u);
              ErrorMessage(v23, "\n", 3u);
              *((_DWORD *)this + 16) = 2;
LABEL_39:
              v32[0] = &C_WSTRINGZ::`vftable';
              C_BINARY::~C_BINARY((C_BINARY *)v32);
              return this;
            }
          }
        }
      }
      if ( *v15 != (HANDLE)-1LL )
      {
        CloseHandle(*v15);
        *v15 = (HANDLE)-1LL;
      }
    }
    *((_QWORD *)this + 3) = 0;
    goto LABEL_33;
  }
  return this;
}

```

## disassembly

```asm
0x18018bd28  push    rbx
0x18018bd2a  push    rbp
0x18018bd2b  push    rsi
0x18018bd2c  push    rdi
0x18018bd2d  push    r12
0x18018bd2f  push    r13
0x18018bd31  push    r14
0x18018bd33  push    r15
0x18018bd35  sub     rsp, 78h
0x18018bd39  mov     rbp, [rsp+0B8h+arg_20]
0x18018bd41  mov     rbx, r8
0x18018bd44  mov     r8, rbp; struct _iobuf *
0x18018bd47  mov     rsi, r9
0x18018bd4a  mov     r15, rdx
0x18018bd4d  mov     rdi, rcx
0x18018bd50  call    ??0C_SERIALIZE@@QEAA@PEAVC_SERIALIZE_PACKET@@PEAU_iobuf@@@Z; C_SERIALIZE::C_SERIALIZE(C_SERIALIZE_PACKET *,_iobuf *)
0x18018bd55  cmp     dword ptr [rdi+14h], 0
0x18018bd59  lea     rax, ??_7C_SOURCEFILE@@6B@; const C_SOURCEFILE::`vftable'
0x18018bd60  mov     r13d, 2
0x18018bd66  mov     [rdi], rax
0x18018bd69  mov     qword ptr [rdi+18h], 0
0x18018bd71  mov     qword ptr [rdi+28h], 0
0x18018bd79  mov     [rdi+30h], rsi
0x18018bd7d  mov     [rdi+38h], rbx
0x18018bd81  mov     [rdi+40h], r13d
0x18018bd85  jnz     loc_18018C030
0x18018bd8b  test    rsi, rsi
0x18018bd8e  jz      loc_18018C029
0x18018bd94  cmp     dword ptr [rsi+14h], 0
0x18018bd98  jnz     loc_18018C029
0x18018bd9e  mov     r8, [rsi+20h]; unsigned __int16 *
0x18018bda2  test    r8, r8
0x18018bda5  jz      loc_18018C029
0x18018bdab  mov     r9d, [rsi+18h]
0x18018bdaf  shr     r9d, 1; unsigned int
0x18018bdb2  jz      loc_18018C029
0x18018bdb8  mov     rdx, r15; struct C_SERIALIZE_PACKET *
0x18018bdbb  mov     qword ptr [rsp+0B8h+dwCreationDisposition], rbp; struct _iobuf *
0x18018bdc0  lea     rcx, [rsp+0B8h+var_78]; this
0x18018bdc5  call    ??0C_WSTRINGZ@@QEAA@PEAVC_SERIALIZE_PACKET@@PEBGKPEAU_iobuf@@@Z; C_WSTRINGZ::C_WSTRINGZ(C_SERIALIZE_PACKET *,ushort const *,ulong,_iobuf *)
0x18018bdca  cmp     [rsp+0B8h+var_64], 0
0x18018bdcf  jnz     loc_18018C011
0x18018bdd5  lea     r14, [rdi+20h]
0x18018bdd9  lea     ebx, [r13-1]
0x18018bddd  test    r14, r14
0x18018bde0  jz      loc_18018BF8B
0x18018bde6  mov     rcx, [rsp+0B8h+lpFileName]; lpFileName
0x18018bdeb  xor     r9d, r9d; lpSecurityAttributes
0x18018bdee  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x18018bdf7  mov     r8d, ebx; dwShareMode
0x18018bdfa  mov     [rsp+0B8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18018be02  mov     edx, 80000000h; dwDesiredAccess
0x18018be07  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x18018be0f  call    cs:__imp_CreateFileW
0x18018be15  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18018be19  mov     [r14], rax
0x18018be1c  cmp     rax, rsi
0x18018be1f  jz      loc_18018BF7A
0x18018be25  xor     edx, edx; lpFileSizeHigh
0x18018be27  mov     rcx, rax; hFile
0x18018be2a  call    cs:__imp_GetFileSize
0x18018be30  mov     r12d, eax
0x18018be33  cmp     eax, 0FFFFFFFFh
0x18018be36  jz      loc_18018BF7A
0x18018be3c  mov     rcx, [r14]; hFile
0x18018be3f  xor     r9d, r9d; dwMaximumSizeHigh
0x18018be42  mov     qword ptr [rsp+0B8h+dwFlagsAndAttributes], 0; lpName
0x18018be4b  mov     r8d, r13d; flProtect
0x18018be4e  xor     edx, edx; lpFileMappingAttributes
0x18018be50  mov     [rsp+0B8h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18018be58  call    cs:__imp_CreateFileMappingW
0x18018be5e  mov     rbp, rax
0x18018be61  test    rax, rax
0x18018be64  jz      loc_18018BF7A
0x18018be6a  xor     r9d, r9d; dwFileOffsetLow
0x18018be6d  mov     qword ptr [rsp+0B8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18018be76  xor     r8d, r8d; dwFileOffsetHigh
0x18018be79  lea     edx, [rbx+3]; dwDesiredAccess
0x18018be7c  mov     rcx, rax; hFileMappingObject
0x18018be7f  call    cs:__imp_MapViewOfFile
0x18018be85  mov     rcx, rbp; hObject
0x18018be88  mov     r13, rax
0x18018be8b  call    cs:__imp_CloseHandle
0x18018be91  test    r13, r13
0x18018be94  jz      loc_18018BF7A
0x18018be9a  mov     [rdi+18h], r13
0x18018be9e  test    r12d, r12d
0x18018bea1  jz      loc_18018BF93
0x18018bea7  lea     ecx, [rbx+4Fh]; Size
0x18018beaa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018beaf  mov     rbp, [rsp+0B8h+arg_20]
0x18018beb7  mov     rdx, r15; struct C_SERIALIZE_PACKET *
0x18018beba  mov     rcx, rax; this
0x18018bebd  mov     qword ptr [rsp+0B8h+dwCreationDisposition], rbp; struct _iobuf *
0x18018bec2  call    ??0C_BUFFER@@QEAA@PEAVC_SERIALIZE_PACKET@@KKPEAU_iobuf@@@Z; C_BUFFER::C_BUFFER(C_SERIALIZE_PACKET *,ulong,ulong,_iobuf *)
0x18018bec7  mov     [rdi+28h], rax
0x18018becb  mov     r9, rax
0x18018bece  test    rax, rax
0x18018bed1  jz      short loc_18018BF2E
0x18018bed3  mov     eax, [rax+14h]
0x18018bed6  cmp     eax, 2
0x18018bed9  jnz     short loc_18018BEF5
0x18018bedb  mov     rcx, [r9]
0x18018bede  mov     rax, [rcx]
0x18018bee1  mov     rcx, r9
0x18018bee4  mov     edx, ebx
0x18018bee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018beeb  mov     qword ptr [rdi+28h], 0
0x18018bef3  jmp     short loc_18018BF2E
0x18018bef5  cmp     eax, ebx
0x18018bef7  jz      short loc_18018BEEB
0x18018bef9  test    eax, eax
0x18018befb  jz      short loc_18018BF05
0x18018befd  mov     rax, [r9]
0x18018bf00  mov     rax, [rax]
0x18018bf03  jmp     short loc_18018BEE1
0x18018bf05  mov     rdx, [rsp+0B8h+arg_28]; unsigned __int8 *
0x18018bf0d  test    rdx, rdx
0x18018bf10  jz      short loc_18018BF39
0x18018bf12  inc     rsi
0x18018bf15  cmp     byte ptr [rdx+rsi], 0
0x18018bf19  jnz     short loc_18018BF12
0x18018bf1b  test    esi, esi
0x18018bf1d  jz      short loc_18018BF39
0x18018bf1f  mov     r8d, esi; unsigned int
0x18018bf22  mov     rcx, r9; this
0x18018bf25  call    ?InsertData@C_BUFFER@@QEAAHPEAEK@Z; C_BUFFER::InsertData(uchar *,ulong)
0x18018bf2a  test    eax, eax
0x18018bf2c  jnz     short loc_18018BF39
0x18018bf2e  cmp     dword ptr [rdi+14h], 2
0x18018bf32  jz      short loc_18018BF9B
0x18018bf34  mov     [rdi+14h], ebx
0x18018bf37  jmp     short loc_18018BF9B
0x18018bf39  mov     rcx, [rdi+28h]; this
0x18018bf3d  xor     r9d, r9d; int
0x18018bf40  mov     r8d, r12d; unsigned int
0x18018bf43  mov     rdx, r13; unsigned __int8 *
0x18018bf46  call    ?AddData@C_BUFFER@@QEAAHPEAEKH@Z; C_BUFFER::AddData(uchar *,ulong,int)
0x18018bf4b  test    eax, eax
0x18018bf4d  jz      short loc_18018BF2E
0x18018bf4f  mov     rax, [rdi+28h]
0x18018bf53  cmp     dword ptr [rax+14h], 0
0x18018bf57  jnz     short loc_18018BF2E
0x18018bf59  mov     rcx, [rdi+18h]
0x18018bf5d  test    rcx, rcx
0x18018bf60  jz      short loc_18018BF72
0x18018bf62  mov     rdx, [r14]
0x18018bf65  call    UnmapFileFromMemory
0x18018bf6a  mov     qword ptr [rdi+18h], 0
0x18018bf72  mov     [rdi+40h], ebx
0x18018bf75  jmp     loc_18018C011
0x18018bf7a  cmp     [r14], rsi
0x18018bf7d  jz      short loc_18018BF8B
0x18018bf7f  mov     rcx, [r14]; hObject
0x18018bf82  call    cs:__imp_CloseHandle
0x18018bf88  mov     [r14], rsi
0x18018bf8b  mov     qword ptr [rdi+18h], 0
0x18018bf93  mov     rbp, [rsp+0B8h+arg_20]
0x18018bf9b  mov     rcx, [rdi+28h]
0x18018bf9f  test    rcx, rcx
0x18018bfa2  jz      short loc_18018BFB9
0x18018bfa4  mov     rax, [rcx]
0x18018bfa7  mov     edx, ebx
0x18018bfa9  mov     rax, [rax]
0x18018bfac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018bfb1  mov     qword ptr [rdi+28h], 0
0x18018bfb9  mov     rcx, [rdi+18h]
0x18018bfbd  test    rcx, rcx
0x18018bfc0  jz      short loc_18018BFD2
0x18018bfc2  mov     rdx, [r14]
0x18018bfc5  call    UnmapFileFromMemory
0x18018bfca  mov     qword ptr [rdi+18h], 0
0x18018bfd2  mov     ebx, 3
0x18018bfd7  lea     rdx, aCSourcefileCSo; "C_SOURCEFILE::C_SOURCEFILE:   failed to"...
0x18018bfde  mov     r8d, ebx; unsigned int
0x18018bfe1  mov     rcx, rbp; struct _iobuf *
0x18018bfe4  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x18018bfe9  mov     rdx, [rdi+30h]; struct C_BINARY *
0x18018bfed  mov     r8d, ebx; unsigned int
0x18018bff0  mov     rcx, rbp; struct _iobuf *
0x18018bff3  call    ?EmitWstr@@YAXPEAU_iobuf@@PEAVC_BINARY@@K@Z; EmitWstr(_iobuf *,C_BINARY *,ulong)
0x18018bff8  mov     r8d, ebx; unsigned int
0x18018bffb  lea     rdx, asc_180218178; "\n"
0x18018c002  mov     rcx, rbp; struct _iobuf *
0x18018c005  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x18018c00a  mov     dword ptr [rdi+40h], 2
0x18018c011  lea     rax, ??_7C_WSTRINGZ@@6B@; const C_WSTRINGZ::`vftable'
0x18018c018  lea     rcx, [rsp+0B8h+var_78]; this
0x18018c01d  mov     [rsp+0B8h+var_78], rax
0x18018c022  call    ??1C_BINARY@@UEAA@XZ; C_BINARY::~C_BINARY(void)
0x18018c027  jmp     short loc_18018C030
0x18018c029  mov     dword ptr [rdi+14h], 1
0x18018c030  mov     rax, rdi
0x18018c033  add     rsp, 78h
0x18018c037  pop     r15
0x18018c039  pop     r14
0x18018c03b  pop     r13
0x18018c03d  pop     r12
0x18018c03f  pop     rdi
0x18018c040  pop     rsi
0x18018c041  pop     rbp
0x18018c042  pop     rbx
0x18018c043  retn
```
