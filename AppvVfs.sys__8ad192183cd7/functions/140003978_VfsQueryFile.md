# VfsQueryFile

- ea: `0x140003978`
- end: `0x140003bf8`
- name: `VfsQueryFile`
- size: `640`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, void *, struct _UNICODE_STRING *, __int64, __int64, _QWORD *Context, bool *, _BYTE *, PBOOLEAN IsDirectory, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400031bc`
- `0x14000cd04`

## callees

- `0x140003978`
- `0x14000de04`
- `0x14000f984`
- `0x14001070c`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140003be5`
- `ntoskrnl!ObfDereferenceObject` at `0x14001485c`
- `ntoskrnl!ObfDereferenceObject` at `0x140003be5`
- `ntoskrnl!ObfDereferenceObject` at `0x14001485c`
- `FLTMGR!FltIsDirectory` at `0x140003ad0`
- `FLTMGR!FltIsDirectory` at `0x140003ad0`
- `FLTMGR!FltClose` at `0x140003bcf`
- `FLTMGR!FltClose` at `0x140014846`
- `FLTMGR!FltClose` at `0x140003bcf`
- `FLTMGR!FltClose` at `0x140014846`
- `FLTMGR!FltGetStreamContext` at `0x140003b30`
- `FLTMGR!FltGetStreamContext` at `0x140003b30`
- `FLTMGR!FltReleaseContext` at `0x140003bb8`
- `FLTMGR!FltReleaseContext` at `0x140003bb8`

## string_xrefs

- `0x140003a6e`: `VfsQueryFile() - Failed to open file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsQueryFile(
        PFLT_INSTANCE Instance,
        void *a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        __int64 a5,
        _QWORD *Context,
        bool *a7,
        _BYTE *a8,
        PBOOLEAN IsDirectory,
        bool *a10)
{
  _BYTE *v11; // r12
  bool *v12; // r15
  _BYTE *v13; // rdi
  unsigned __int8 *v14; // rsi
  bool *v15; // r14
  NTSTATUS v16; // ebx
  NTSTATUS StreamContext; // eax
  PFLT_CONTEXT v19; // rcx
  __int64 Scb; // rax
  ULONG v21[2]; // [rsp+20h] [rbp-68h]
  PFILE_OBJECT FileObject; // [rsp+48h] [rbp-40h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-38h] BYREF

  FileHandle = 0;
  FileObject = 0;
  v11 = Context;
  *(_BYTE *)Context = 0;
  v12 = a7;
  if ( a7 )
  {
    if ( !a4 || !a5 )
      return 3221225485LL;
    *a7 = 0;
  }
  v13 = a8;
  if ( a8 )
    *a8 = 0;
  v14 = IsDirectory;
  if ( IsDirectory )
    *IsDirectory = 0;
  v15 = a10;
  if ( a10 )
    *a10 = 0;
  v16 = VfsOpenFile(Instance, a2, a3, 0x100008u, 1u, 0x4020u, &FileHandle, &FileObject);
  if ( v16 >= 0 )
  {
    *v11 = 1;
    if ( v13 )
      *v13 = 1;
    if ( v14 )
    {
      v16 = FltIsDirectory(FileObject, Instance, v14);
      if ( v16 < 0 )
        goto LABEL_37;
    }
    if ( v15 && *v11 )
      *v15 = (int)VfsQueryTombstone(Instance, FileObject) >= 0;
    if ( !v12 )
      goto LABEL_37;
    Context = 0;
    StreamContext = FltGetStreamContext(Instance, FileObject, (PFLT_CONTEXT *)&Context);
    v16 = StreamContext;
    if ( StreamContext != -1073741275 )
    {
      if ( StreamContext >= 0 )
      {
        v19 = Context;
        if ( (*((_DWORD *)Context + 1) & 1) != 0 )
        {
          Scb = VfsScbTableGetScb(Context, a4, a5, 0, 0);
          v19 = Context;
        }
        else
        {
          Scb = Context[2];
        }
        *v12 = Scb != 0;
        FltReleaseContext(v19);
      }
      else
      {
        v21[0] = StreamContext;
        LogWrite(
          1,
          0,
          L"VfsQueryFile() - Failed to get stream context for fileobject: %p\n Status: 0x%08X",
          FileObject,
          *(_QWORD *)v21);
      }
      goto LABEL_37;
    }
  }
  else
  {
    if ( v16 != -1073741772 && v16 != -1073741766 )
    {
      if ( v16 != -1073741773 )
      {
        v21[0] = v16;
        LogWrite(1, 0, L"VfsQueryFile() - Failed to open file: %wZ\n Status: 0x%08X", a3, *(_QWORD *)v21);
      }
      goto LABEL_37;
    }
    if ( v13 && v16 == -1073741772 )
      *v13 = 1;
  }
  v16 = 0;
LABEL_37:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140003978  mov     r11, rsp
0x14000397b  mov     [r11+8], rbx
0x14000397f  mov     [r11+10h], rsi
0x140003983  mov     [r11+20h], r9
0x140003987  mov     [r11+18h], r8
0x14000398b  push    rdi
0x14000398c  push    r12
0x14000398e  push    r13
0x140003990  push    r14
0x140003992  push    r15
0x140003994  sub     rsp, 60h
0x140003998  mov     rax, r8
0x14000399b  mov     r13, rcx
0x14000399e  xor     ecx, ecx
0x1400039a0  mov     [r11-38h], rcx
0x1400039a4  mov     [r11-40h], rcx
0x1400039a8  mov     r12, [rsp+88h+Context]
0x1400039b0  mov     [r12], cl
0x1400039b4  mov     r15, [rsp+88h+arg_30]
0x1400039bc  test    r15, r15
0x1400039bf  jz      short loc_1400039DB
0x1400039c1  test    r9, r9
0x1400039c4  jz      loc_140003A7A
0x1400039ca  cmp     [rsp+88h+arg_20], rcx
0x1400039d2  jz      loc_140003A7A
0x1400039d8  mov     [r15], cl
0x1400039db  mov     rdi, [rsp+88h+arg_38]
0x1400039e3  test    rdi, rdi
0x1400039e6  jz      short loc_1400039EA
0x1400039e8  mov     [rdi], cl
0x1400039ea  mov     rsi, [rsp+88h+IsDirectory]
0x1400039f2  test    rsi, rsi
0x1400039f5  jz      short loc_1400039F9
0x1400039f7  mov     [rsi], cl
0x1400039f9  mov     r14, [rsp+88h+arg_48]
0x140003a01  test    r14, r14
0x140003a04  jz      short loc_140003A09
0x140003a06  mov     [r14], cl
0x140003a09  lea     rcx, [rsp+88h+FileObject]
0x140003a0e  mov     [rsp+88h+var_50], rcx; FileObject
0x140003a13  lea     rcx, [rsp+88h+FileHandle]
0x140003a18  mov     [rsp+88h+var_58], rcx; FileHandle
0x140003a1d  mov     [rsp+88h+var_60], 4020h; ULONG
0x140003a25  mov     [rsp+88h+var_68], 1; ULONG
0x140003a2d  mov     r9d, 100008h
0x140003a33  mov     rcx, r13; Instance
0x140003a36  call    VfsOpenFile
0x140003a3b  mov     ebx, eax
0x140003a3d  mov     [rsp+88h+var_48], eax
0x140003a41  test    eax, eax
0x140003a43  jns     short loc_140003AB3
0x140003a45  mov     eax, 0C0000034h
0x140003a4a  cmp     ebx, eax
0x140003a4c  jz      short loc_140003A9A
0x140003a4e  cmp     ebx, 0C000003Ah
0x140003a54  jz      short loc_140003A9A
0x140003a56  cmp     ebx, 0C0000033h
0x140003a5c  jz      loc_140003BC5
0x140003a62  mov     [rsp+88h+var_68], ebx
0x140003a66  mov     r9, [rsp+88h+arg_10]
0x140003a6e  lea     r8, aVfsqueryfileFa; "VfsQueryFile() - Failed to open file: %"...
0x140003a75  jmp     loc_140003B65
0x140003a7a  mov     eax, 0C000000Dh
0x140003a7f  lea     r11, [rsp+88h+var_28]
0x140003a84  mov     rbx, [r11+30h]
0x140003a88  mov     rsi, [r11+38h]
0x140003a8c  mov     rsp, r11
0x140003a8f  pop     r15
0x140003a91  pop     r14
0x140003a93  pop     r13
0x140003a95  pop     r12
0x140003a97  pop     rdi
0x140003a98  retn
0x140003a9a  test    rdi, rdi
0x140003a9d  jz      loc_140003B49
0x140003aa3  cmp     ebx, eax
0x140003aa5  jnz     loc_140003B49
0x140003aab  mov     byte ptr [rdi], 1
0x140003aae  jmp     loc_140003B49
0x140003ab3  mov     byte ptr [r12], 1
0x140003ab8  test    rdi, rdi
0x140003abb  jz      short loc_140003AC0
0x140003abd  mov     byte ptr [rdi], 1
0x140003ac0  test    rsi, rsi
0x140003ac3  jz      short loc_140003AEA
0x140003ac5  mov     r8, rsi; IsDirectory
0x140003ac8  mov     rdx, r13; Instance
0x140003acb  mov     rcx, [rsp+88h+FileObject]; FileObject
0x140003ad0  call    cs:__imp_FltIsDirectory
0x140003ad7  nop     dword ptr [rax+rax+00h]
0x140003adc  mov     ebx, eax
0x140003ade  mov     [rsp+88h+var_48], eax
0x140003ae2  test    eax, eax
0x140003ae4  js      loc_140003BC5
0x140003aea  test    r14, r14
0x140003aed  jz      short loc_140003B0B
0x140003aef  cmp     byte ptr [r12], 0
0x140003af4  jz      short loc_140003B0B
0x140003af6  mov     rdx, [rsp+88h+FileObject]; FileObject
0x140003afb  mov     rcx, r13; Instance
0x140003afe  call    VfsQueryTombstone
0x140003b03  shr     eax, 1Fh
0x140003b06  xor     al, 1
0x140003b08  mov     [r14], al
0x140003b0b  test    r15, r15
0x140003b0e  jz      loc_140003BC5
0x140003b14  mov     [rsp+88h+Context], 0
0x140003b20  lea     r8, [rsp+88h+Context]; Context
0x140003b28  mov     rdx, [rsp+88h+FileObject]; FileObject
0x140003b2d  mov     rcx, r13; Instance
0x140003b30  call    cs:__imp_FltGetStreamContext
0x140003b37  nop     dword ptr [rax+rax+00h]
0x140003b3c  mov     ebx, eax
0x140003b3e  mov     [rsp+88h+var_48], eax
0x140003b42  cmp     eax, 0C0000225h
0x140003b47  jnz     short loc_140003B51
0x140003b49  xor     ebx, ebx
0x140003b4b  mov     [rsp+88h+var_48], ebx
0x140003b4f  jmp     short loc_140003BC5
0x140003b51  test    eax, eax
0x140003b53  jns     short loc_140003B71
0x140003b55  mov     [rsp+88h+var_68], eax
0x140003b59  mov     r9, [rsp+88h+FileObject]
0x140003b5e  lea     r8, aVfsqueryfileFa_0; "VfsQueryFile() - Failed to get stream c"...
0x140003b65  xor     edx, edx
0x140003b67  lea     ecx, [rdx+1]
0x140003b6a  call    LogWrite
0x140003b6f  jmp     short loc_140003BC5
0x140003b71  mov     rcx, [rsp+88h+Context]; Context
0x140003b79  mov     eax, [rcx+4]
0x140003b7c  test    al, 1
0x140003b7e  jz      short loc_140003BAB
0x140003b80  mov     qword ptr [rsp+88h+var_68], 0
0x140003b89  xor     r9d, r9d
0x140003b8c  mov     r8, [rsp+88h+arg_20]
0x140003b94  mov     rdx, [rsp+88h+arg_18]
0x140003b9c  call    VfsScbTableGetScb
0x140003ba1  mov     rcx, [rsp+88h+Context]
0x140003ba9  jmp     short loc_140003BAF
0x140003bab  mov     rax, [rcx+10h]
0x140003baf  test    rax, rax
0x140003bb2  setnz   al
0x140003bb5  mov     [r15], al
0x140003bb8  call    cs:__imp_FltReleaseContext
0x140003bbf  nop     dword ptr [rax+rax+00h]
0x140003bc4  nop
0x140003bc5  mov     rcx, [rsp+88h+FileHandle]; FileHandle
0x140003bca  test    rcx, rcx
0x140003bcd  jz      short loc_140003BDB
0x140003bcf  call    cs:__imp_FltClose
0x140003bd6  nop     dword ptr [rax+rax+00h]
0x140003bdb  mov     rcx, [rsp+88h+FileObject]; Object
0x140003be0  test    rcx, rcx
0x140003be3  jz      short loc_140003BF1
0x140003be5  call    cs:__imp_ObfDereferenceObject
0x140003bec  nop     dword ptr [rax+rax+00h]
0x140003bf1  mov     eax, ebx
0x140003bf3  jmp     loc_140003A7F
0x140014834  push    rbp
0x140014836  sub     rsp, 40h
0x14001483a  mov     rbp, rdx
0x14001483d  mov     rcx, [rbp+50h]; FileHandle
0x140014841  test    rcx, rcx
0x140014844  jz      short loc_140014853
0x140014846  call    cs:__imp_FltClose
0x14001484d  nop     dword ptr [rax+rax+00h]
0x140014852  nop
0x140014853  mov     rcx, [rbp+48h]; Object
0x140014857  test    rcx, rcx
0x14001485a  jz      short loc_140014869
0x14001485c  call    cs:__imp_ObfDereferenceObject
0x140014863  nop     dword ptr [rax+rax+00h]
0x140014868  nop
0x140014869  add     rsp, 40h
0x14001486d  pop     rbp
0x14001486e  retn
```
