# VfsOpenScb

- ea: `0x1400037ac`
- end: `0x140003972`
- name: `VfsOpenScb`
- size: `454`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, void *, struct _UNICODE_STRING *, char, __int64, __int64, __int64 *, HANDLE *, PFILE_OBJECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140002b4c`
- `0x14000b2dc`

## callees

- `0x1400037ac`
- `0x14000de04`
- `0x14000e0a0`
- `0x14001070c`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140003933`
- `ntoskrnl!ObfDereferenceObject` at `0x140014804`
- `ntoskrnl!ObfDereferenceObject` at `0x140003933`
- `ntoskrnl!ObfDereferenceObject` at `0x140014804`
- `FLTMGR!FltClose` at `0x140003949`
- `FLTMGR!FltClose` at `0x14001481a`
- `FLTMGR!FltClose` at `0x140003949`
- `FLTMGR!FltClose` at `0x14001481a`
- `FLTMGR!FltGetStreamContext` at `0x14000386a`
- `FLTMGR!FltGetStreamContext` at `0x14000386a`
- `FLTMGR!FltReleaseContext` at `0x14000391d`
- `FLTMGR!FltReleaseContext` at `0x1400147ee`
- `FLTMGR!FltReleaseContext` at `0x14000391d`
- `FLTMGR!FltReleaseContext` at `0x1400147ee`

## string_xrefs

- `0x140003846`: `VfsOpenScb() - Failed to open file: %wZ\n Status: 0x%08X`
- `0x140003894`: `VfsOpenScb() - Failed to get stream context for fileobject: %p\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsOpenScb(
        PFLT_INSTANCE Instance,
        void *a2,
        struct _UNICODE_STRING *a3,
        char a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7,
        HANDLE *a8,
        PFILE_OBJECT *a9)
{
  NTSTATUS StreamContext; // eax
  int v13; // ebx
  PFILE_OBJECT v14; // r9
  const WCHAR *v15; // r8
  __int64 v16; // r9
  __int64 Scb; // rax
  ULONG v19[2]; // [rsp+20h] [rbp-68h]
  PFILE_OBJECT FileObject; // [rsp+48h] [rbp-40h] BYREF
  HANDLE FileHandle; // [rsp+50h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+58h] [rbp-30h] BYREF

  FileHandle = 0;
  FileObject = 0;
  Context = 0;
  *a7 = 0;
  *a8 = 0;
  if ( a9 )
    *a9 = 0;
  StreamContext = VfsOpenFile(Instance, a2, a3, 0x100000u, 1u, 0x4020u, &FileHandle, &FileObject);
  v13 = StreamContext;
  if ( StreamContext < 0 )
  {
    v14 = (PFILE_OBJECT)a3;
    v15 = L"VfsOpenScb() - Failed to open file: %wZ\n Status: 0x%08X";
LABEL_5:
    v19[0] = StreamContext;
    LogWrite(1, 0, v15, v14, *(_QWORD *)v19);
    goto LABEL_15;
  }
  StreamContext = FltGetStreamContext(Instance, FileObject, &Context);
  v13 = StreamContext;
  if ( StreamContext >= 0 )
  {
    if ( a5 && a6 )
    {
      LOBYTE(v16) = 1;
      Scb = VfsScbTableGetScb(Context, a5, a6, v16, 0);
    }
    else
    {
      Scb = VfsScbUnitOpenScb(Context);
    }
    *a7 = Scb;
  }
  else
  {
    if ( StreamContext != -1073741275 )
    {
      v14 = FileObject;
      v15 = L"VfsOpenScb() - Failed to get stream context for fileobject: %p\n Status: 0x%08X";
      goto LABEL_5;
    }
    v13 = 0;
  }
LABEL_15:
  if ( v13 >= 0 && (*a7 || a4) )
  {
    *a8 = FileHandle;
    FileHandle = 0;
    if ( a9 )
    {
      *a9 = FileObject;
      FileObject = 0;
    }
  }
  if ( Context )
    FltReleaseContext(Context);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400037ac  mov     r11, rsp
0x1400037af  mov     [r11+8], rbx
0x1400037b3  mov     [r11+10h], rsi
0x1400037b7  mov     [r11+20h], r9b
0x1400037bb  push    rdi
0x1400037bc  push    r12
0x1400037be  push    r13
0x1400037c0  push    r14
0x1400037c2  push    r15
0x1400037c4  sub     rsp, 60h
0x1400037c8  mov     r12b, r9b
0x1400037cb  mov     r14, r8
0x1400037ce  mov     r15, rcx
0x1400037d1  xor     eax, eax
0x1400037d3  mov     [rsp+88h+var_48], eax
0x1400037d7  mov     [r11-38h], rax
0x1400037db  mov     [r11-40h], rax
0x1400037df  mov     [r11-30h], rax
0x1400037e3  mov     rsi, [rsp+88h+arg_30]
0x1400037eb  mov     [rsi], rax
0x1400037ee  mov     r13, [rsp+88h+arg_38]
0x1400037f6  mov     [r13+0], rax
0x1400037fa  mov     rdi, [rsp+88h+arg_40]
0x140003802  test    rdi, rdi
0x140003805  jz      short loc_14000380A
0x140003807  mov     [rdi], rax
0x14000380a  lea     rax, [rsp+88h+FileObject]
0x14000380f  mov     [rsp+88h+var_50], rax; FileObject
0x140003814  lea     rax, [rsp+88h+FileHandle]
0x140003819  mov     [rsp+88h+var_58], rax; FileHandle
0x14000381e  mov     [rsp+88h+var_60], 4020h; ULONG
0x140003826  mov     [rsp+88h+var_68], 1; ULONG
0x14000382e  mov     r9d, 100000h
0x140003834  call    VfsOpenFile
0x140003839  mov     ebx, eax
0x14000383b  mov     [rsp+88h+var_48], eax
0x14000383f  test    eax, eax
0x140003841  jns     short loc_14000385D
0x140003843  mov     r9, r14
0x140003846  lea     r8, aVfsopenscbFail; "VfsOpenScb() - Failed to open file: %wZ"...
0x14000384d  mov     [rsp+88h+var_68], eax
0x140003851  xor     edx, edx
0x140003853  lea     ecx, [rdx+1]
0x140003856  call    LogWrite
0x14000385b  jmp     short loc_1400038DC
0x14000385d  lea     r8, [rsp+88h+Context]; Context
0x140003862  mov     rdx, [rsp+88h+FileObject]; FileObject
0x140003867  mov     rcx, r15; Instance
0x14000386a  call    cs:__imp_FltGetStreamContext
0x140003871  nop     dword ptr [rax+rax+00h]
0x140003876  mov     ebx, eax
0x140003878  mov     [rsp+88h+var_48], eax
0x14000387c  test    eax, eax
0x14000387e  jns     short loc_14000389D
0x140003880  cmp     eax, 0C0000225h
0x140003885  jnz     short loc_14000388F
0x140003887  xor     ebx, ebx
0x140003889  mov     [rsp+88h+var_48], ebx
0x14000388d  jmp     short loc_1400038DC
0x14000388f  mov     r9, [rsp+88h+FileObject]
0x140003894  lea     r8, aVfsopenscbFail_0; "VfsOpenScb() - Failed to get stream con"...
0x14000389b  jmp     short loc_14000384D
0x14000389d  mov     rdx, [rsp+88h+arg_20]
0x1400038a5  test    rdx, rdx
0x1400038a8  jz      short loc_1400038CF
0x1400038aa  mov     r8, [rsp+88h+arg_28]
0x1400038b2  test    r8, r8
0x1400038b5  jz      short loc_1400038CF
0x1400038b7  mov     qword ptr [rsp+88h+var_68], 0
0x1400038c0  mov     r9b, 1
0x1400038c3  mov     rcx, [rsp+88h+Context]
0x1400038c8  call    VfsScbTableGetScb
0x1400038cd  jmp     short loc_1400038D9
0x1400038cf  mov     rcx, [rsp+88h+Context]
0x1400038d4  call    VfsScbUnitOpenScb
0x1400038d9  mov     [rsi], rax
0x1400038dc  test    ebx, ebx
0x1400038de  js      short loc_140003913
0x1400038e0  cmp     qword ptr [rsi], 0
0x1400038e4  jnz     short loc_1400038EB
0x1400038e6  test    r12b, r12b
0x1400038e9  jz      short loc_140003913
0x1400038eb  mov     rax, [rsp+88h+FileHandle]
0x1400038f0  mov     [r13+0], rax
0x1400038f4  mov     [rsp+88h+FileHandle], 0
0x1400038fd  test    rdi, rdi
0x140003900  jz      short loc_140003913
0x140003902  mov     rax, [rsp+88h+FileObject]
0x140003907  mov     [rdi], rax
0x14000390a  mov     [rsp+88h+FileObject], 0
0x140003913  mov     rcx, [rsp+88h+Context]; Context
0x140003918  test    rcx, rcx
0x14000391b  jz      short loc_140003929
0x14000391d  call    cs:__imp_FltReleaseContext
0x140003924  nop     dword ptr [rax+rax+00h]
0x140003929  mov     rcx, [rsp+88h+FileObject]; Object
0x14000392e  test    rcx, rcx
0x140003931  jz      short loc_14000393F
0x140003933  call    cs:__imp_ObfDereferenceObject
0x14000393a  nop     dword ptr [rax+rax+00h]
0x14000393f  mov     rcx, [rsp+88h+FileHandle]; FileHandle
0x140003944  test    rcx, rcx
0x140003947  jz      short loc_140003955
0x140003949  call    cs:__imp_FltClose
0x140003950  nop     dword ptr [rax+rax+00h]
0x140003955  mov     eax, ebx
0x140003957  lea     r11, [rsp+88h+var_28]
0x14000395c  mov     rbx, [r11+30h]
0x140003960  mov     rsi, [r11+38h]
0x140003964  mov     rsp, r11
0x140003967  pop     r15
0x140003969  pop     r14
0x14000396b  pop     r13
0x14000396d  pop     r12
0x14000396f  pop     rdi
0x140003970  retn
0x14001478f  push    rbp
0x140014791  sub     rsp, 40h
0x140014795  mov     rbp, rdx
0x140014798  cmp     dword ptr [rbp+40h], 0
0x14001479c  jl      short loc_1400147E5
0x14001479e  mov     rax, [rbp+0C0h]
0x1400147a5  cmp     qword ptr [rax], 0
0x1400147a9  jnz     short loc_1400147B4
0x1400147ab  cmp     byte ptr [rbp+0A8h], 0
0x1400147b2  jz      short loc_1400147E5
0x1400147b4  mov     rcx, [rbp+50h]
0x1400147b8  mov     rax, [rbp+0C8h]
0x1400147bf  mov     [rax], rcx
0x1400147c2  mov     qword ptr [rbp+50h], 0
0x1400147ca  mov     rcx, [rbp+0D0h]
0x1400147d1  test    rcx, rcx
0x1400147d4  jz      short loc_1400147E5
0x1400147d6  mov     rax, [rbp+48h]
0x1400147da  mov     [rcx], rax
0x1400147dd  mov     qword ptr [rbp+48h], 0
0x1400147e5  mov     rcx, [rbp+58h]; Context
0x1400147e9  test    rcx, rcx
0x1400147ec  jz      short loc_1400147FB
0x1400147ee  call    cs:__imp_FltReleaseContext
0x1400147f5  nop     dword ptr [rax+rax+00h]
0x1400147fa  nop
0x1400147fb  mov     rcx, [rbp+48h]; Object
0x1400147ff  test    rcx, rcx
0x140014802  jz      short loc_140014811
0x140014804  call    cs:__imp_ObfDereferenceObject
0x14001480b  nop     dword ptr [rax+rax+00h]
0x140014810  nop
0x140014811  mov     rcx, [rbp+50h]; FileHandle
0x140014815  test    rcx, rcx
0x140014818  jz      short loc_140014827
0x14001481a  call    cs:__imp_FltClose
0x140014821  nop     dword ptr [rax+rax+00h]
0x140014826  nop
0x140014827  add     rsp, 40h
0x14001482b  pop     rbp
0x14001482c  retn
```
