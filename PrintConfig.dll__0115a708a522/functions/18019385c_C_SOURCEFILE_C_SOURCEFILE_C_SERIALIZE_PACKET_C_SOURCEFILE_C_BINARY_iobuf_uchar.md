# C_SOURCEFILE::C_SOURCEFILE(C_SERIALIZE_PACKET *,C_SOURCEFILE *,C_BINARY *,_iobuf *,uchar *)

- ea: `0x18019385c`
- end: `0x180193b9d`
- name: `??0C_SOURCEFILE@@QEAA@PEAVC_SERIALIZE_PACKET@@PEAV0@PEAVC_BINARY@@PEAU_iobuf@@PEAE@Z`
- size: `833`
- prototype: `C_SOURCEFILE *__fastcall(C_SOURCEFILE *this, struct C_SERIALIZE_PACKET *, struct C_SOURCEFILE *, struct C_BINARY *, struct _iobuf *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18017fee4`
- `0x180181400`
- `0x1801821e8`
- `0x180182508`

## callees

- `0x180003c20`
- `0x180150854`
- `0x180183614`
- `0x180183adc`
- `0x180183c50`
- `0x180183cd8`
- `0x1801842d8`
- `0x180184d50`
- `0x1801850b8`
- `0x180185134`
- `0x18019385c`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x180193998`
- `KERNEL32!CreateFileMappingW` at `0x180193998`
- `KERNEL32!MapViewOfFile` at `0x1801939c5`
- `KERNEL32!MapViewOfFile` at `0x1801939c5`
- `KERNEL32!GetFileSize` at `0x180193964`
- `KERNEL32!GetFileSize` at `0x180193964`
- `KERNEL32!CreateFileW` at `0x180193943`
- `KERNEL32!CreateFileW` at `0x180193943`
- `KERNEL32!CloseHandle` at `0x1801939d7`
- `KERNEL32!CloseHandle` at `0x180193ad4`
- `KERNEL32!CloseHandle` at `0x1801939d7`
- `KERNEL32!CloseHandle` at `0x180193ad4`

## string_xrefs

- `0x180193b2f`: `C_SOURCEFILE::C_SOURCEFILE:   failed to open File:  `

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
  const void *v28; // rcx
  void (__fastcall ***v29)(_QWORD, __int64, __int64, C_BUFFER *); // rcx
  const void *v30; // rcx
  void *v32[2]; // [rsp+40h] [rbp-78h] BYREF
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
                    if ( !(_DWORD)v17 || (unsigned int)C_BUFFER::InsertData(v14, a6, v17) )
                    {
LABEL_44:
                      if ( (unsigned int)C_BUFFER::AddData(*((C_BUFFER **)this + 5), v21, FileSize, 0)
                        && !*(_DWORD *)(*((_QWORD *)this + 5) + 20LL) )
                      {
                        v28 = (const void *)*((_QWORD *)this + 3);
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
              v30 = (const void *)*((_QWORD *)this + 3);
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
              C_BINARY::~C_BINARY(v32);
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
0x18019385c  push    rbx
0x18019385e  push    rbp
0x18019385f  push    rsi
0x180193860  push    rdi
0x180193861  push    r12
0x180193863  push    r13
0x180193865  push    r14
0x180193867  push    r15
0x180193869  sub     rsp, 78h
0x18019386d  mov     rbp, [rsp+0B8h+arg_20]
0x180193875  mov     rbx, r8
0x180193878  mov     r8, rbp; struct _iobuf *
0x18019387b  mov     rsi, r9
0x18019387e  mov     r15, rdx
0x180193881  mov     rdi, rcx
0x180193884  call    ??0C_SERIALIZE@@QEAA@PEAVC_SERIALIZE_PACKET@@PEAU_iobuf@@@Z; C_SERIALIZE::C_SERIALIZE(C_SERIALIZE_PACKET *,_iobuf *)
0x180193889  cmp     dword ptr [rdi+14h], 0
0x18019388d  lea     rax, ??_7C_SOURCEFILE@@6B@; const C_SOURCEFILE::`vftable'
0x180193894  mov     r13d, 2
0x18019389a  mov     [rdi], rax
0x18019389d  mov     qword ptr [rdi+18h], 0
0x1801938a5  mov     qword ptr [rdi+28h], 0
0x1801938ad  mov     [rdi+30h], rsi
0x1801938b1  mov     [rdi+38h], rbx
0x1801938b5  mov     [rdi+40h], r13d
0x1801938b9  jnz     loc_180193B88
0x1801938bf  test    rsi, rsi
0x1801938c2  jz      loc_180193B81
0x1801938c8  cmp     dword ptr [rsi+14h], 0
0x1801938cc  jnz     loc_180193B81
0x1801938d2  mov     r8, [rsi+20h]; unsigned __int16 *
0x1801938d6  test    r8, r8
0x1801938d9  jz      loc_180193B81
0x1801938df  mov     r9d, [rsi+18h]
0x1801938e3  shr     r9d, 1; unsigned int
0x1801938e6  jz      loc_180193B81
0x1801938ec  mov     rdx, r15; struct C_SERIALIZE_PACKET *
0x1801938ef  mov     qword ptr [rsp+0B8h+dwCreationDisposition], rbp; struct _iobuf *
0x1801938f4  lea     rcx, [rsp+0B8h+var_78]; this
0x1801938f9  call    ??0C_WSTRINGZ@@QEAA@PEAVC_SERIALIZE_PACKET@@PEBGKPEAU_iobuf@@@Z; C_WSTRINGZ::C_WSTRINGZ(C_SERIALIZE_PACKET *,ushort const *,ulong,_iobuf *)
0x1801938fe  cmp     [rsp+0B8h+var_64], 0
0x180193903  jnz     loc_180193B69
0x180193909  lea     r14, [rdi+20h]
0x18019390d  lea     ebx, [r13-1]
0x180193911  test    r14, r14
0x180193914  jz      loc_180193AE3
0x18019391a  mov     rcx, [rsp+0B8h+lpFileName]; lpFileName
0x18019391f  xor     r9d, r9d; lpSecurityAttributes
0x180193922  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x18019392b  mov     r8d, ebx; dwShareMode
0x18019392e  mov     [rsp+0B8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180193936  mov     edx, 80000000h; dwDesiredAccess
0x18019393b  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180193943  call    cs:__imp_CreateFileW
0x18019394a  nop     dword ptr [rax+rax+00h]
0x18019394f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180193953  mov     [r14], rax
0x180193956  cmp     rax, rsi
0x180193959  jz      loc_180193ACC
0x18019395f  xor     edx, edx; lpFileSizeHigh
0x180193961  mov     rcx, rax; hFile
0x180193964  call    cs:__imp_GetFileSize
0x18019396b  nop     dword ptr [rax+rax+00h]
0x180193970  mov     r12d, eax
0x180193973  cmp     eax, 0FFFFFFFFh
0x180193976  jz      loc_180193ACC
0x18019397c  mov     rcx, [r14]; hFile
0x18019397f  xor     r9d, r9d; dwMaximumSizeHigh
0x180193982  mov     qword ptr [rsp+0B8h+dwFlagsAndAttributes], 0; lpName
0x18019398b  mov     r8d, r13d; flProtect
0x18019398e  xor     edx, edx; lpFileMappingAttributes
0x180193990  mov     [rsp+0B8h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180193998  call    cs:__imp_CreateFileMappingW
0x18019399f  nop     dword ptr [rax+rax+00h]
0x1801939a4  mov     rbp, rax
0x1801939a7  test    rax, rax
0x1801939aa  jz      loc_180193ACC
0x1801939b0  xor     r9d, r9d; dwFileOffsetLow
0x1801939b3  mov     qword ptr [rsp+0B8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1801939bc  xor     r8d, r8d; dwFileOffsetHigh
0x1801939bf  lea     edx, [rbx+3]; dwDesiredAccess
0x1801939c2  mov     rcx, rax; hFileMappingObject
0x1801939c5  call    cs:__imp_MapViewOfFile
0x1801939cc  nop     dword ptr [rax+rax+00h]
0x1801939d1  mov     rcx, rbp; hObject
0x1801939d4  mov     r13, rax
0x1801939d7  call    cs:__imp_CloseHandle
0x1801939de  nop     dword ptr [rax+rax+00h]
0x1801939e3  test    r13, r13
0x1801939e6  jz      loc_180193ACC
0x1801939ec  mov     [rdi+18h], r13
0x1801939f0  test    r12d, r12d
0x1801939f3  jz      loc_180193AEB
0x1801939f9  lea     ecx, [rbx+4Fh]; Size
0x1801939fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180193a01  mov     rbp, [rsp+0B8h+arg_20]
0x180193a09  mov     rdx, r15; struct C_SERIALIZE_PACKET *
0x180193a0c  mov     rcx, rax; this
0x180193a0f  mov     qword ptr [rsp+0B8h+dwCreationDisposition], rbp; struct _iobuf *
0x180193a14  call    ??0C_BUFFER@@QEAA@PEAVC_SERIALIZE_PACKET@@KKPEAU_iobuf@@@Z; C_BUFFER::C_BUFFER(C_SERIALIZE_PACKET *,ulong,ulong,_iobuf *)
0x180193a19  mov     [rdi+28h], rax
0x180193a1d  mov     r9, rax
0x180193a20  test    rax, rax
0x180193a23  jz      short loc_180193A80
0x180193a25  mov     eax, [rax+14h]
0x180193a28  cmp     eax, 2
0x180193a2b  jnz     short loc_180193A47
0x180193a2d  mov     rcx, [r9]
0x180193a30  mov     rax, [rcx]
0x180193a33  mov     rcx, r9
0x180193a36  mov     edx, ebx
0x180193a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193a3d  mov     qword ptr [rdi+28h], 0
0x180193a45  jmp     short loc_180193A80
0x180193a47  cmp     eax, ebx
0x180193a49  jz      short loc_180193A3D
0x180193a4b  test    eax, eax
0x180193a4d  jz      short loc_180193A57
0x180193a4f  mov     rax, [r9]
0x180193a52  mov     rax, [rax]
0x180193a55  jmp     short loc_180193A33
0x180193a57  mov     rdx, [rsp+0B8h+arg_28]; unsigned __int8 *
0x180193a5f  test    rdx, rdx
0x180193a62  jz      short loc_180193A8B
0x180193a64  inc     rsi
0x180193a67  cmp     byte ptr [rdx+rsi], 0
0x180193a6b  jnz     short loc_180193A64
0x180193a6d  test    esi, esi
0x180193a6f  jz      short loc_180193A8B
0x180193a71  mov     r8d, esi; unsigned int
0x180193a74  mov     rcx, r9; this
0x180193a77  call    ?InsertData@C_BUFFER@@QEAAHPEAEK@Z; C_BUFFER::InsertData(uchar *,ulong)
0x180193a7c  test    eax, eax
0x180193a7e  jnz     short loc_180193A8B
0x180193a80  cmp     dword ptr [rdi+14h], 2
0x180193a84  jz      short loc_180193AF3
0x180193a86  mov     [rdi+14h], ebx
0x180193a89  jmp     short loc_180193AF3
0x180193a8b  mov     rcx, [rdi+28h]; this
0x180193a8f  xor     r9d, r9d; int
0x180193a92  mov     r8d, r12d; unsigned int
0x180193a95  mov     rdx, r13; unsigned __int8 *
0x180193a98  call    ?AddData@C_BUFFER@@QEAAHPEAEKH@Z; C_BUFFER::AddData(uchar *,ulong,int)
0x180193a9d  test    eax, eax
0x180193a9f  jz      short loc_180193A80
0x180193aa1  mov     rax, [rdi+28h]
0x180193aa5  cmp     dword ptr [rax+14h], 0
0x180193aa9  jnz     short loc_180193A80
0x180193aab  mov     rcx, [rdi+18h]
0x180193aaf  test    rcx, rcx
0x180193ab2  jz      short loc_180193AC4
0x180193ab4  mov     rdx, [r14]
0x180193ab7  call    UnmapFileFromMemory
0x180193abc  mov     qword ptr [rdi+18h], 0
0x180193ac4  mov     [rdi+40h], ebx
0x180193ac7  jmp     loc_180193B69
0x180193acc  cmp     [r14], rsi
0x180193acf  jz      short loc_180193AE3
0x180193ad1  mov     rcx, [r14]; hObject
0x180193ad4  call    cs:__imp_CloseHandle
0x180193adb  nop     dword ptr [rax+rax+00h]
0x180193ae0  mov     [r14], rsi
0x180193ae3  mov     qword ptr [rdi+18h], 0
0x180193aeb  mov     rbp, [rsp+0B8h+arg_20]
0x180193af3  mov     rcx, [rdi+28h]
0x180193af7  test    rcx, rcx
0x180193afa  jz      short loc_180193B11
0x180193afc  mov     rax, [rcx]
0x180193aff  mov     edx, ebx
0x180193b01  mov     rax, [rax]
0x180193b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193b09  mov     qword ptr [rdi+28h], 0
0x180193b11  mov     rcx, [rdi+18h]
0x180193b15  test    rcx, rcx
0x180193b18  jz      short loc_180193B2A
0x180193b1a  mov     rdx, [r14]
0x180193b1d  call    UnmapFileFromMemory
0x180193b22  mov     qword ptr [rdi+18h], 0
0x180193b2a  mov     ebx, 3
0x180193b2f  lea     rdx, aCSourcefileCSo; "C_SOURCEFILE::C_SOURCEFILE:   failed to"...
0x180193b36  mov     r8d, ebx; unsigned int
0x180193b39  mov     rcx, rbp; struct _iobuf *
0x180193b3c  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x180193b41  mov     rdx, [rdi+30h]; struct C_BINARY *
0x180193b45  mov     r8d, ebx; unsigned int
0x180193b48  mov     rcx, rbp; struct _iobuf *
0x180193b4b  call    ?EmitWstr@@YAXPEAU_iobuf@@PEAVC_BINARY@@K@Z; EmitWstr(_iobuf *,C_BINARY *,ulong)
0x180193b50  mov     r8d, ebx; unsigned int
0x180193b53  lea     rdx, asc_18021FE40; "\n"
0x180193b5a  mov     rcx, rbp; struct _iobuf *
0x180193b5d  call    ?ErrorMessage@@YAXPEAU_iobuf@@PEADK@Z; ErrorMessage(_iobuf *,char *,ulong)
0x180193b62  mov     dword ptr [rdi+40h], 2
0x180193b69  lea     rax, ??_7C_WSTRINGZ@@6B@; const C_WSTRINGZ::`vftable'
0x180193b70  lea     rcx, [rsp+0B8h+var_78]; this
0x180193b75  mov     [rsp+0B8h+var_78], rax
0x180193b7a  call    ??1C_BINARY@@UEAA@XZ; C_BINARY::~C_BINARY(void)
0x180193b7f  jmp     short loc_180193B88
0x180193b81  mov     dword ptr [rdi+14h], 1
0x180193b88  mov     rax, rdi
0x180193b8b  add     rsp, 78h
0x180193b8f  pop     r15
0x180193b91  pop     r14
0x180193b93  pop     r13
0x180193b95  pop     r12
0x180193b97  pop     rdi
0x180193b98  pop     rsi
0x180193b99  pop     rbp
0x180193b9a  pop     rbx
0x180193b9b  retn
```
