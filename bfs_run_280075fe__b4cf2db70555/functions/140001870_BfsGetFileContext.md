# BfsGetFileContext

- ea: `0x140001870`
- end: `0x140001b1b`
- name: `BfsGetFileContext`
- size: `683`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140001fb0`
- `0x140003140`

## callees

- `0x140001008`
- `0x140001870`
- `0x140013730`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140001acb`
- `ntoskrnl!EtwWriteTransfer` at `0x140001acb`
- `FLTMGR!FltReleaseContext` at `0x1400019c2`
- `FLTMGR!FltReleaseContext` at `0x140001ae0`
- `FLTMGR!FltReleaseContext` at `0x1400019c2`
- `FLTMGR!FltReleaseContext` at `0x140001ae0`
- `FLTMGR!FltGetFileContext` at `0x1400018b2`
- `FLTMGR!FltGetFileContext` at `0x1400018b2`
- `FLTMGR!FltAllocateContext` at `0x1400018e9`
- `FLTMGR!FltAllocateContext` at `0x1400018e9`
- `FLTMGR!FltSetFileContext` at `0x1400019a9`
- `FLTMGR!FltSetFileContext` at `0x1400019a9`

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
0x140001870  mov     [rsp-8+arg_18], rbx
0x140001875  push    rbp
0x140001876  push    rsi
0x140001877  push    rdi
0x140001878  push    r14
0x14000187a  push    r15
0x14000187c  lea     rbp, [rsp-37h]
0x140001881  sub     rsp, 90h
0x140001888  mov     rax, cs:__security_cookie
0x14000188f  xor     rax, rsp
0x140001892  mov     [rbp+57h+var_28], rax
0x140001896  mov     rdi, r8
0x140001899  mov     rsi, rcx
0x14000189c  mov     rcx, [rcx+18h]; Instance
0x1400018a0  lea     r8, [rbp+57h+Context]; Context
0x1400018a4  xor     r15d, r15d
0x1400018a7  mov     r14, rdx
0x1400018aa  mov     [rbp+57h+Context], r15
0x1400018ae  mov     [rbp+57h+OldContext], r15
0x1400018b2  call    cs:__imp_FltGetFileContext
0x1400018b9  nop     dword ptr [rax+rax+00h]
0x1400018be  mov     ebx, eax
0x1400018c0  cmp     eax, 0C0000225h
0x1400018c5  jnz     loc_140001A20
0x1400018cb  mov     rcx, [rsi+8]; Filter
0x1400018cf  lea     rax, [rbp+57h+Context]
0x1400018d3  mov     edx, 4; ContextType
0x1400018d8  mov     [rsp+0B0h+ReturnedContext], rax; ReturnedContext
0x1400018dd  mov     r9d, 1; PoolType
0x1400018e3  mov     r8d, 10h; ContextSize
0x1400018e9  call    cs:__imp_FltAllocateContext
0x1400018f0  nop     dword ptr [rax+rax+00h]
0x1400018f5  mov     ebx, eax
0x1400018f7  test    eax, eax
0x1400018f9  jns     loc_140001985
0x1400018ff  mov     eax, cs:dword_140019000
0x140001905  cmp     eax, 3
0x140001908  jbe     loc_140001AD7
0x14000190e  lea     rax, [rbp+57h+var_7C]
0x140001912  mov     [rbp+57h+var_7C], ebx
0x140001915  mov     [rbp+57h+var_38], rax
0x140001919  mov     rax, cs:qword_140016D92
0x140001920  movzx   ecx, ax
0x140001923  mov     rax, cs:EventInformation
0x14000192a  mov     [rbp+57h+var_58.Ptr], rax
0x14000192e  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140001931  lea     rcx, _TraceLoggingMetadata
0x140001938  mov     [rbp+57h+var_30], 4
0x140001940  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140001947  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x14000194b  movzx   eax, word ptr [rax]
0x14000194e  mov     [rbp+57h+var_58.Size], eax
0x140001951  lea     rax, dword_140016D9C
0x140001958  mov     [rbp+57h+var_48], rax
0x14000195c  lea     rax, _TraceLoggingMetadataEnd
0x140001963  sub     eax, ecx
0x140001965  mov     dword ptr [rbp+57h+var_58.0Ch], 2
0x14000196c  mov     [rbp+57h+var_40], 1Eh
0x140001973  mov     [rbp+57h+var_3C], 1
0x14000197a  mov     [rbp+57h+var_80], eax
0x14000197d  mov     eax, [rbp+57h+var_80]
0x140001980  jmp     loc_140001AA9
0x140001985  mov     rax, [rbp+57h+Context]
0x140001989  xorps   xmm0, xmm0
0x14000198c  mov     r8d, 1; Operation
0x140001992  mov     rdx, r14; FileObject
0x140001995  movups  xmmword ptr [rax], xmm0
0x140001998  mov     r9, [rbp+57h+Context]; NewContext
0x14000199c  lea     rax, [rbp+57h+OldContext]
0x1400019a0  mov     rcx, [rsi+18h]; Instance
0x1400019a4  mov     [rsp+0B0h+ReturnedContext], rax; int
0x1400019a9  call    cs:__imp_FltSetFileContext
0x1400019b0  nop     dword ptr [rax+rax+00h]
0x1400019b5  mov     ebx, eax
0x1400019b7  cmp     eax, 0C01C0002h
0x1400019bc  jnz     short loc_1400019DC
0x1400019be  mov     rcx, [rbp+57h+Context]; Context
0x1400019c2  call    cs:__imp_FltReleaseContext
0x1400019c9  nop     dword ptr [rax+rax+00h]
0x1400019ce  mov     rax, [rbp+57h+OldContext]
0x1400019d2  mov     [rdi], rax
0x1400019d5  xor     eax, eax
0x1400019d7  jmp     loc_140001AF7
0x1400019dc  test    ebx, ebx
0x1400019de  jns     loc_140001AEE
0x1400019e4  mov     eax, cs:dword_140019000
0x1400019ea  cmp     eax, 3
0x1400019ed  jbe     loc_140001AD7
0x1400019f3  lea     rax, [rbp+57h+var_80]
0x1400019f7  mov     [rbp+57h+var_80], ebx
0x1400019fa  mov     [rbp+57h+var_38], rax
0x1400019fe  lea     rdx, byte_140016D91; int
0x140001a05  lea     rax, [rbp+57h+var_58]
0x140001a09  mov     [rbp+57h+var_30], 4
0x140001a11  mov     [rsp+0B0h+UserData], rax; PEVENT_DATA_DESCRIPTOR
0x140001a16  call    _tlgWriteTransfer_EtwWriteTransfer
0x140001a1b  jmp     loc_140001AD7
0x140001a20  test    ebx, ebx
0x140001a22  jns     loc_140001AEE
0x140001a28  mov     eax, cs:dword_140019000
0x140001a2e  cmp     eax, 3
0x140001a31  jbe     loc_140001AD7
0x140001a37  lea     rax, [rbp+57h+var_80]
0x140001a3b  mov     [rbp+57h+var_80], ebx
0x140001a3e  mov     [rbp+57h+var_38], rax
0x140001a42  mov     rax, cs:qword_140016D92
0x140001a49  movzx   ecx, ax
0x140001a4c  mov     rax, cs:EventInformation
0x140001a53  mov     [rbp+57h+var_58.Ptr], rax
0x140001a57  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140001a5a  lea     rcx, _TraceLoggingMetadata
0x140001a61  mov     [rbp+57h+var_30], 4
0x140001a69  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140001a70  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x140001a74  movzx   eax, word ptr [rax]
0x140001a77  mov     [rbp+57h+var_58.Size], eax
0x140001a7a  lea     rax, dword_140016D9C
0x140001a81  mov     [rbp+57h+var_48], rax
0x140001a85  lea     rax, _TraceLoggingMetadataEnd
0x140001a8c  sub     eax, ecx
0x140001a8e  mov     dword ptr [rbp+57h+var_58.0Ch], 2
0x140001a95  mov     [rbp+57h+var_40], 1Eh
0x140001a9c  mov     [rbp+57h+var_3C], 1
0x140001aa3  mov     [rbp+57h+var_7C], eax
0x140001aa6  mov     eax, [rbp+57h+var_7C]
0x140001aa9  mov     rcx, cs:RegHandle; RegHandle
0x140001ab0  lea     rax, [rbp+57h+var_58]
0x140001ab4  mov     [rsp+0B0h+UserData], rax; UserData
0x140001ab9  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140001abd  xor     r9d, r9d; RelatedActivityId
0x140001ac0  mov     dword ptr [rsp+0B0h+ReturnedContext], 3; UserDataCount
0x140001ac8  xor     r8d, r8d; ActivityId
0x140001acb  call    cs:__imp_EtwWriteTransfer
0x140001ad2  nop     dword ptr [rax+rax+00h]
0x140001ad7  mov     rcx, [rbp+57h+Context]; Context
0x140001adb  test    rcx, rcx
0x140001ade  jz      short loc_140001AF5
0x140001ae0  call    cs:__imp_FltReleaseContext
0x140001ae7  nop     dword ptr [rax+rax+00h]
0x140001aec  jmp     short loc_140001AF5
0x140001aee  mov     rax, [rbp+57h+Context]
0x140001af2  mov     [rdi], rax
0x140001af5  mov     eax, ebx
0x140001af7  mov     rcx, [rbp+57h+var_28]
0x140001afb  xor     rcx, rsp; StackCookie
0x140001afe  call    __security_check_cookie
0x140001b03  mov     rbx, [rsp+0B0h+arg_18]
0x140001b0b  add     rsp, 90h
0x140001b12  pop     r15
0x140001b14  pop     r14
0x140001b16  pop     rdi
0x140001b17  pop     rsi
0x140001b18  pop     rbp
0x140001b19  retn
```
