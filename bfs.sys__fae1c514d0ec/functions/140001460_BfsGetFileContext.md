# BfsGetFileContext

- ea: `0x140001460`
- end: `0x14000170b`
- name: `BfsGetFileContext`
- size: `683`
- prototype: `__int64 __fastcall(__int64, struct _FILE_OBJECT *, PFLT_CONTEXT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140001ba0`
- `0x140003270`

## callees

- `0x140001008`
- `0x140001460`
- `0x140013860`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400016bb`
- `ntoskrnl!EtwWriteTransfer` at `0x1400016bb`
- `FLTMGR!FltReleaseContext` at `0x1400015b2`
- `FLTMGR!FltReleaseContext` at `0x1400016d0`
- `FLTMGR!FltReleaseContext` at `0x1400015b2`
- `FLTMGR!FltReleaseContext` at `0x1400016d0`
- `FLTMGR!FltGetFileContext` at `0x1400014a2`
- `FLTMGR!FltGetFileContext` at `0x1400014a2`
- `FLTMGR!FltAllocateContext` at `0x1400014d9`
- `FLTMGR!FltAllocateContext` at `0x1400014d9`
- `FLTMGR!FltSetFileContext` at `0x140001599`
- `FLTMGR!FltSetFileContext` at `0x140001599`

## pseudocode

```c
__int64 __fastcall BfsGetFileContext(__int64 a1, struct _FILE_OBJECT *a2, PFLT_CONTEXT *a3)
{
  struct _FLT_INSTANCE *v5; // rcx
  NTSTATUS FileContext; // ebx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int ReturnedContext; // [rsp+20h] [rbp-39h]
  unsigned int v13; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-25h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-21h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-19h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+50h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-1h] BYREF
  int *v19; // [rsp+68h] [rbp+Fh]
  int v20; // [rsp+70h] [rbp+17h]
  int v21; // [rsp+74h] [rbp+1Bh]
  unsigned int *v22; // [rsp+78h] [rbp+1Fh]
  __int64 v23; // [rsp+80h] [rbp+27h]

  v5 = *(struct _FLT_INSTANCE **)(a1 + 24);
  Context = 0;
  OldContext = 0;
  FileContext = FltGetFileContext(v5, a2, &Context);
  if ( FileContext == -1073741275 )
  {
    FileContext = FltAllocateContext(*(PFLT_FILTER *)(a1 + 8), 4u, 0x10u, PagedPool, &Context);
    if ( FileContext < 0 )
    {
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_14;
      v14 = FileContext;
      v22 = &v14;
      UserData.Ptr = (ULONGLONG)EventInformation;
      *(_DWORD *)&EventDescriptor.Level = 3;
      v23 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)EventInformation;
      v19 = &dword_140016D9C;
      UserData.Reserved = 2;
      v20 = 30;
      v21 = 1;
      v13 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      goto LABEL_13;
    }
    *(_OWORD *)Context = 0;
    FileContext = FltSetFileContext(
                    *(PFLT_INSTANCE *)(a1 + 24),
                    a2,
                    FLT_SET_CONTEXT_KEEP_IF_EXISTS,
                    Context,
                    &OldContext);
    if ( FileContext == -1071906814 )
    {
      FltReleaseContext(Context);
      *a3 = OldContext;
      return 0;
    }
    if ( FileContext < 0 )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v13 = FileContext;
        v22 = &v13;
        v23 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v9, v10, ReturnedContext, &UserData);
      }
      goto LABEL_14;
    }
  }
  else if ( FileContext < 0 )
  {
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_14;
    v13 = FileContext;
    v22 = &v13;
    UserData.Ptr = (ULONGLONG)EventInformation;
    *(_DWORD *)&EventDescriptor.Level = 3;
    v23 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)EventInformation;
    v19 = &dword_140016D9C;
    UserData.Reserved = 2;
    v20 = 30;
    v21 = 1;
    v14 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_13:
    EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
LABEL_14:
    if ( Context )
      FltReleaseContext(Context);
    return (unsigned int)FileContext;
  }
  *a3 = Context;
  return (unsigned int)FileContext;
}

```

## disassembly

```asm
0x140001460  mov     [rsp-8+arg_18], rbx
0x140001465  push    rbp
0x140001466  push    rsi
0x140001467  push    rdi
0x140001468  push    r14
0x14000146a  push    r15
0x14000146c  lea     rbp, [rsp-37h]
0x140001471  sub     rsp, 90h
0x140001478  mov     rax, cs:__security_cookie
0x14000147f  xor     rax, rsp
0x140001482  mov     [rbp+57h+var_28], rax
0x140001486  mov     rdi, r8
0x140001489  mov     rsi, rcx
0x14000148c  mov     rcx, [rcx+18h]; Instance
0x140001490  lea     r8, [rbp+57h+Context]; Context
0x140001494  xor     r15d, r15d
0x140001497  mov     r14, rdx
0x14000149a  mov     [rbp+57h+Context], r15
0x14000149e  mov     [rbp+57h+OldContext], r15
0x1400014a2  call    cs:__imp_FltGetFileContext
0x1400014a9  nop     dword ptr [rax+rax+00h]
0x1400014ae  mov     ebx, eax
0x1400014b0  cmp     eax, 0C0000225h
0x1400014b5  jnz     loc_140001610
0x1400014bb  mov     rcx, [rsi+8]; Filter
0x1400014bf  lea     rax, [rbp+57h+Context]
0x1400014c3  mov     edx, 4; ContextType
0x1400014c8  mov     [rsp+0B0h+ReturnedContext], rax; ReturnedContext
0x1400014cd  mov     r9d, 1; PoolType
0x1400014d3  mov     r8d, 10h; ContextSize
0x1400014d9  call    cs:__imp_FltAllocateContext
0x1400014e0  nop     dword ptr [rax+rax+00h]
0x1400014e5  mov     ebx, eax
0x1400014e7  test    eax, eax
0x1400014e9  jns     loc_140001575
0x1400014ef  mov     eax, cs:dword_140019000
0x1400014f5  cmp     eax, 3
0x1400014f8  jbe     loc_1400016C7
0x1400014fe  lea     rax, [rbp+57h+var_7C]
0x140001502  mov     [rbp+57h+var_7C], ebx
0x140001505  mov     [rbp+57h+var_38], rax
0x140001509  mov     rax, cs:qword_140016D92
0x140001510  movzx   ecx, ax
0x140001513  mov     rax, cs:EventInformation
0x14000151a  mov     [rbp+57h+var_58.Ptr], rax
0x14000151e  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140001521  lea     rcx, _TraceLoggingMetadata
0x140001528  mov     [rbp+57h+var_30], 4
0x140001530  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140001537  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x14000153b  movzx   eax, word ptr [rax]
0x14000153e  mov     [rbp+57h+var_58.Size], eax
0x140001541  lea     rax, dword_140016D9C
0x140001548  mov     [rbp+57h+var_48], rax
0x14000154c  lea     rax, _TraceLoggingMetadataEnd
0x140001553  sub     eax, ecx
0x140001555  mov     dword ptr [rbp+57h+var_58.0Ch], 2
0x14000155c  mov     [rbp+57h+var_40], 1Eh
0x140001563  mov     [rbp+57h+var_3C], 1
0x14000156a  mov     [rbp+57h+var_80], eax
0x14000156d  mov     eax, [rbp+57h+var_80]
0x140001570  jmp     loc_140001699
0x140001575  mov     rax, [rbp+57h+Context]
0x140001579  xorps   xmm0, xmm0
0x14000157c  mov     r8d, 1; Operation
0x140001582  mov     rdx, r14; FileObject
0x140001585  movups  xmmword ptr [rax], xmm0
0x140001588  mov     r9, [rbp+57h+Context]; NewContext
0x14000158c  lea     rax, [rbp+57h+OldContext]
0x140001590  mov     rcx, [rsi+18h]; Instance
0x140001594  mov     [rsp+0B0h+ReturnedContext], rax; int
0x140001599  call    cs:__imp_FltSetFileContext
0x1400015a0  nop     dword ptr [rax+rax+00h]
0x1400015a5  mov     ebx, eax
0x1400015a7  cmp     eax, 0C01C0002h
0x1400015ac  jnz     short loc_1400015CC
0x1400015ae  mov     rcx, [rbp+57h+Context]; Context
0x1400015b2  call    cs:__imp_FltReleaseContext
0x1400015b9  nop     dword ptr [rax+rax+00h]
0x1400015be  mov     rax, [rbp+57h+OldContext]
0x1400015c2  mov     [rdi], rax
0x1400015c5  xor     eax, eax
0x1400015c7  jmp     loc_1400016E7
0x1400015cc  test    ebx, ebx
0x1400015ce  jns     loc_1400016DE
0x1400015d4  mov     eax, cs:dword_140019000
0x1400015da  cmp     eax, 3
0x1400015dd  jbe     loc_1400016C7
0x1400015e3  lea     rax, [rbp+57h+var_80]
0x1400015e7  mov     [rbp+57h+var_80], ebx
0x1400015ea  mov     [rbp+57h+var_38], rax
0x1400015ee  lea     rdx, byte_140016D91; int
0x1400015f5  lea     rax, [rbp+57h+var_58]
0x1400015f9  mov     [rbp+57h+var_30], 4
0x140001601  mov     [rsp+0B0h+UserData], rax; PEVENT_DATA_DESCRIPTOR
0x140001606  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000160b  jmp     loc_1400016C7
0x140001610  test    ebx, ebx
0x140001612  jns     loc_1400016DE
0x140001618  mov     eax, cs:dword_140019000
0x14000161e  cmp     eax, 3
0x140001621  jbe     loc_1400016C7
0x140001627  lea     rax, [rbp+57h+var_80]
0x14000162b  mov     [rbp+57h+var_80], ebx
0x14000162e  mov     [rbp+57h+var_38], rax
0x140001632  mov     rax, cs:qword_140016D92
0x140001639  movzx   ecx, ax
0x14000163c  mov     rax, cs:EventInformation
0x140001643  mov     [rbp+57h+var_58.Ptr], rax
0x140001647  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x14000164a  lea     rcx, _TraceLoggingMetadata
0x140001651  mov     [rbp+57h+var_30], 4
0x140001659  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140001660  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x140001664  movzx   eax, word ptr [rax]
0x140001667  mov     [rbp+57h+var_58.Size], eax
0x14000166a  lea     rax, dword_140016D9C
0x140001671  mov     [rbp+57h+var_48], rax
0x140001675  lea     rax, _TraceLoggingMetadataEnd
0x14000167c  sub     eax, ecx
0x14000167e  mov     dword ptr [rbp+57h+var_58.0Ch], 2
0x140001685  mov     [rbp+57h+var_40], 1Eh
0x14000168c  mov     [rbp+57h+var_3C], 1
0x140001693  mov     [rbp+57h+var_7C], eax
0x140001696  mov     eax, [rbp+57h+var_7C]
0x140001699  mov     rcx, cs:RegHandle; RegHandle
0x1400016a0  lea     rax, [rbp+57h+var_58]
0x1400016a4  mov     [rsp+0B0h+UserData], rax; UserData
0x1400016a9  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1400016ad  xor     r9d, r9d; RelatedActivityId
0x1400016b0  mov     dword ptr [rsp+0B0h+ReturnedContext], 3; UserDataCount
0x1400016b8  xor     r8d, r8d; ActivityId
0x1400016bb  call    cs:__imp_EtwWriteTransfer
0x1400016c2  nop     dword ptr [rax+rax+00h]
0x1400016c7  mov     rcx, [rbp+57h+Context]; Context
0x1400016cb  test    rcx, rcx
0x1400016ce  jz      short loc_1400016E5
0x1400016d0  call    cs:__imp_FltReleaseContext
0x1400016d7  nop     dword ptr [rax+rax+00h]
0x1400016dc  jmp     short loc_1400016E5
0x1400016de  mov     rax, [rbp+57h+Context]
0x1400016e2  mov     [rdi], rax
0x1400016e5  mov     eax, ebx
0x1400016e7  mov     rcx, [rbp+57h+var_28]
0x1400016eb  xor     rcx, rsp; StackCookie
0x1400016ee  call    __security_check_cookie
0x1400016f3  mov     rbx, [rsp+0B0h+arg_18]
0x1400016fb  add     rsp, 90h
0x140001702  pop     r15
0x140001704  pop     r14
0x140001706  pop     rdi
0x140001707  pop     rsi
0x140001708  pop     rbp
0x140001709  retn
```
