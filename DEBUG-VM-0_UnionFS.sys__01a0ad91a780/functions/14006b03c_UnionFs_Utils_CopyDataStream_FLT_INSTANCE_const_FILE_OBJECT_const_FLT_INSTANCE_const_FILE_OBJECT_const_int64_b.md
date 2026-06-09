# UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,__int64,bool,UnionFs::StackEventTracer &)

- ea: `0x14006b03c`
- end: `0x14006b26c`
- name: `?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@01_J_NAEAVStackEventTracer@2@@Z`
- size: `560`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE InitiatingInstance@<rcx>, PFILE_OBJECT FileObject@<rdx>, PFLT_INSTANCE Instance@<r8>, const struct _FLT_INSTANCE *@<r9>, ULONG BytesWritten, ULONG, bool, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x14006b274`
- `0x14006c058`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x14006b03c`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14006b1cd`
- `ntoskrnl!KeDelayExecutionThread` at `0x14006b1cd`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14006b208`
- `FLTMGR!FltFreePoolAlignedWithTag` at `0x14006b208`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14006b091`
- `FLTMGR!FltAllocatePoolAlignedWithTag` at `0x14006b091`
- `FLTMGR!FltWriteFile` at `0x14006b1a8`
- `FLTMGR!FltWriteFile` at `0x14006b1a8`
- `FLTMGR!FltReadFile` at `0x14006b120`
- `FLTMGR!FltReadFile` at `0x14006b120`

## string_xrefs

- `0x14006b0bc`: `UnionFs::Utils::CopyDataStream`
- `0x14006b244`: `UnionFs::Utils::CopyDataStream`
- `0x14006b0a9`: `ORIGIN: Allocating stream copy buffer`
- `0x14006b259`: `API: Reading source stream`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CopyDataStream(
        PFLT_INSTANCE InitiatingInstance,
        PFILE_OBJECT FileObject,
        PFLT_INSTANCE Instance,
        struct _FILE_OBJECT *a4,
        __int64 BytesWritten,
        ULONG BytesRead,
        int a7)
{
  __int64 v7; // rdi
  ULONG v8; // esi
  struct _FILE_OBJECT *v10; // r12
  char *Buffer; // r14
  NTSTATUS v13; // ebx
  ULONG v14; // r9d
  const char *v16; // rax
  __int64 v17; // r8
  const char *Flags; // [rsp+28h] [rbp-38h]
  const char *Flagsa; // [rsp+28h] [rbp-38h]
  union _LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-10h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+58h] [rbp-8h] BYREF

  v7 = BytesWritten;
  v8 = 0x1000000;
  v10 = FileObject;
  if ( BytesWritten < 0x1000000 )
    v8 = (BytesWritten + 4095) & 0xFFFFF000;
  Buffer = (char *)FltAllocatePoolAlignedWithTag(Instance, (POOL_TYPE)512, v8, 0x6E674655u);
  if ( Buffer )
  {
    for ( ByteOffset.QuadPart = 0; ; ByteOffset.QuadPart += BytesRead )
    {
      if ( v7 <= 0 )
      {
        v13 = 0;
        goto LABEL_15;
      }
      BytesRead = 0;
      v13 = FltReadFile(InitiatingInstance, v10, &ByteOffset, v8, Buffer, 5u, &BytesRead, 0, 0);
      if ( v13 < 0 )
        break;
      v14 = BytesRead;
      if ( (BytesRead & 0xFFF) != 0 )
      {
        memset(&Buffer[BytesRead], 0, 4096 - (BytesRead & 0xFFF));
        v14 = BytesRead;
      }
      while ( 1 )
      {
        LODWORD(BytesWritten) = 0;
        v13 = FltWriteFile(
                Instance,
                a4,
                &ByteOffset,
                (v14 + 4095) & 0xFFFFF000,
                Buffer,
                0xFu,
                (PULONG)&BytesWritten,
                0,
                0);
        if ( v13 != -1073741740 )
          break;
        Interval.QuadPart = -100000;
        KeDelayExecutionThread(0, 1u, &Interval);
        v14 = BytesRead;
      }
      v10 = FileObject;
      if ( v13 < 0 )
      {
        v16 = "API: Writing target stream";
        v17 = 0x27D002119CFLL;
        goto LABEL_18;
      }
      v7 -= BytesRead;
    }
    v16 = "API: Reading source stream";
    v17 = 0x27C002119A5LL;
LABEL_18:
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v13,
      a7,
      (struct UnionFs::StackEventTracer *)v17,
      (unsigned __int64)"UnionFs::Utils::CopyDataStream",
      v16,
      Flagsa);
LABEL_15:
    FltFreePoolAlignedWithTag(Instance, Buffer, 0x6E674655u);
  }
  else
  {
    v13 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a7,
      (struct UnionFs::StackEventTracer *)0x27B00211987LL,
      (unsigned __int64)"UnionFs::Utils::CopyDataStream",
      "ORIGIN: Allocating stream copy buffer",
      Flags);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14006b03c  mov     [rsp-38h+arg_0], rbx
0x14006b041  mov     [rsp-38h+FileObject], r9
0x14006b046  mov     [rsp-38h+arg_8], rdx
0x14006b04b  push    rbp
0x14006b04c  push    rsi
0x14006b04d  push    rdi
0x14006b04e  push    r12
0x14006b050  push    r13
0x14006b052  push    r14
0x14006b054  push    r15
0x14006b056  mov     rbp, rsp
0x14006b059  sub     rsp, 60h
0x14006b05d  mov     rdi, [rbp+BytesWritten]
0x14006b061  mov     esi, 1000000h
0x14006b066  mov     r15, r8
0x14006b069  mov     r12, rdx
0x14006b06c  mov     r13, rcx
0x14006b06f  cmp     rdi, rsi
0x14006b072  jge     short loc_14006B080
0x14006b074  lea     esi, [rdi+0FFFh]
0x14006b07a  and     esi, 0FFFFF000h
0x14006b080  mov     r8d, esi; NumberOfBytes
0x14006b083  mov     edx, 200h; PoolType
0x14006b088  mov     r9d, 6E674655h; Tag
0x14006b08e  mov     rcx, r15; Instance
0x14006b091  call    cs:__imp_FltAllocatePoolAlignedWithTag
0x14006b098  nop     dword ptr [rax+rax+00h]
0x14006b09d  mov     r14, rax
0x14006b0a0  test    rax, rax
0x14006b0a3  jnz     short loc_14006B0D7
0x14006b0a5  mov     rdx, qword ptr [rbp+arg_30]; int
0x14006b0a9  lea     rax, aOriginAllocati_91; "ORIGIN: Allocating stream copy buffer"
0x14006b0b0  mov     ebx, 0C000009Ah
0x14006b0b5  mov     [rsp+60h+Buffer], rax; char *
0x14006b0ba  mov     ecx, ebx; this
0x14006b0bc  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b0c3  mov     r8, 27B00211987h; struct UnionFs::StackEventTracer *
0x14006b0cd  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b0d2  jmp     loc_14006B214
0x14006b0d7  mov     qword ptr [rbp+ByteOffset], 0
0x14006b0df  jmp     loc_14006B1F1
0x14006b0e4  mov     [rsp+60h+CallbackContext], 0; CallbackContext
0x14006b0ed  lea     rax, [rbp+arg_28]
0x14006b0f1  mov     [rsp+60h+CallbackRoutine], 0; CallbackRoutine
0x14006b0fa  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14006b0fe  mov     [rsp+60h+BytesRead], rax; BytesRead
0x14006b103  mov     r9d, esi; Length
0x14006b106  mov     dword ptr [rsp+60h+Flags], 5; Flags
0x14006b10e  mov     rdx, r12; FileObject
0x14006b111  mov     rcx, r13; InitiatingInstance
0x14006b114  mov     [rsp+60h+Buffer], r14; Buffer
0x14006b119  mov     [rbp+arg_28], 0
0x14006b120  call    cs:__imp_FltReadFile
0x14006b127  nop     dword ptr [rax+rax+00h]
0x14006b12c  mov     ebx, eax
0x14006b12e  test    eax, eax
0x14006b130  js      loc_14006B259
0x14006b136  mov     r9d, [rbp+arg_28]
0x14006b13a  mov     ecx, r9d
0x14006b13d  and     ecx, 0FFFh
0x14006b143  jz      short loc_14006B15D
0x14006b145  mov     r8d, 1000h
0x14006b14b  xor     edx, edx; Val
0x14006b14d  sub     r8d, ecx; Size
0x14006b150  lea     rcx, [r14+r9]; void *
0x14006b154  call    memset
0x14006b159  mov     r9d, [rbp+arg_28]
0x14006b15d  mov     r12, [rbp+FileObject]
0x14006b161  mov     [rsp+60h+CallbackContext], 0; CallbackContext
0x14006b16a  lea     rax, [rbp+BytesWritten]
0x14006b16e  mov     [rsp+60h+CallbackRoutine], 0; CallbackRoutine
0x14006b177  lea     r8, [rbp+ByteOffset]; ByteOffset
0x14006b17b  mov     [rsp+60h+BytesRead], rax; BytesWritten
0x14006b180  add     r9d, 0FFFh
0x14006b187  mov     dword ptr [rsp+60h+Flags], 0Fh; char *
0x14006b18f  and     r9d, 0FFFFF000h; Length
0x14006b196  mov     rdx, r12; FileObject
0x14006b199  mov     [rsp+60h+Buffer], r14; Buffer
0x14006b19e  mov     rcx, r15; InitiatingInstance
0x14006b1a1  mov     dword ptr [rbp+BytesWritten], 0
0x14006b1a8  call    cs:__imp_FltWriteFile
0x14006b1af  nop     dword ptr [rax+rax+00h]
0x14006b1b4  mov     ebx, eax
0x14006b1b6  cmp     eax, 0C0000054h
0x14006b1bb  jnz     short loc_14006B1DF
0x14006b1bd  lea     r8, [rbp+Interval]; Interval
0x14006b1c1  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFE7960h
0x14006b1c9  mov     dl, 1; Alertable
0x14006b1cb  xor     ecx, ecx; WaitMode
0x14006b1cd  call    cs:__imp_KeDelayExecutionThread
0x14006b1d4  nop     dword ptr [rax+rax+00h]
0x14006b1d9  mov     r9d, [rbp+arg_28]
0x14006b1dd  jmp     short loc_14006B161
0x14006b1df  mov     r12, [rbp+arg_8]
0x14006b1e3  test    ebx, ebx
0x14006b1e5  js      short loc_14006B22F
0x14006b1e7  mov     eax, [rbp+arg_28]
0x14006b1ea  sub     rdi, rax
0x14006b1ed  add     qword ptr [rbp+ByteOffset], rax
0x14006b1f1  test    rdi, rdi
0x14006b1f4  jg      loc_14006B0E4
0x14006b1fa  xor     ebx, ebx
0x14006b1fc  mov     r8d, 6E674655h; Tag
0x14006b202  mov     rdx, r14; Buffer
0x14006b205  mov     rcx, r15; Instance
0x14006b208  call    cs:__imp_FltFreePoolAlignedWithTag
0x14006b20f  nop     dword ptr [rax+rax+00h]
0x14006b214  mov     eax, ebx
0x14006b216  mov     rbx, [rsp+60h+arg_0]
0x14006b21e  add     rsp, 60h
0x14006b222  pop     r15
0x14006b224  pop     r14
0x14006b226  pop     r13
0x14006b228  pop     r12
0x14006b22a  pop     rdi
0x14006b22b  pop     rsi
0x14006b22c  pop     rbp
0x14006b22d  retn
0x14006b22f  lea     rax, aApiWritingTarg; "API: Writing target stream"
0x14006b236  mov     r8, 27D002119CFh; struct UnionFs::StackEventTracer *
0x14006b240  mov     rdx, qword ptr [rbp+arg_30]; int
0x14006b244  lea     r9, aUnionfsUtilsCo_4; "UnionFs::Utils::CopyDataStream"
0x14006b24b  mov     ecx, ebx; this
0x14006b24d  mov     [rsp+60h+Buffer], rax; char *
0x14006b252  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b257  jmp     short loc_14006B1FC
0x14006b259  lea     rax, aApiReadingSour; "API: Reading source stream"
0x14006b260  mov     r8, 27C002119A5h
0x14006b26a  jmp     short loc_14006B240
```
