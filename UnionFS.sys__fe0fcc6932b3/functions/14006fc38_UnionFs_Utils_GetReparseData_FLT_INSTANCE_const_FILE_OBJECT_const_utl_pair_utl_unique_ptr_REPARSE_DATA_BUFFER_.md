# UnionFs::Utils::GetReparseData(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::pair<utl::unique_ptr<_REPARSE_DATA_BUFFER,utl::default_delete<_REPARSE_DATA_BUFFER>>,ulong> &,UnionFs::StackEventTracer &,ulong)

- ea: `0x14006fc38`
- end: `0x14006fe6d`
- name: `?GetReparseData@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU?$pair@V?$unique_ptr@U_REPARSE_DATA_BUFFER@@U?$default_delete@U_REPARSE_DATA_BUFFER@@@utl@@@utl@@K@utl@@AEAVStackEventTracer@2@K@Z`
- size: `565`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, ULONG)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140040110`
- `0x14006c3ec`

## callees

- `0x140001008`
- `0x140056bd0`
- `0x140056c44`
- `0x140067ad8`
- `0x14006fc38`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006fc81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fc98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fd72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fe1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fc81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fc98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fd72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006fe1f`
- `FLTMGR!FltFsControlFile` at `0x14006fcd6`
- `FLTMGR!FltFsControlFile` at `0x14006fcd6`

## string_xrefs

- `0x14006fe2d`: `ORIGIN: Allocating reparse info buffer`
- `0x14006fd44`: `UnionFs::Utils::GetReparseData`
- `0x14006fd9d`: `UnionFs::Utils::GetReparseData`
- `0x14006fdd2`: `UnionFs::Utils::GetReparseData`
- `0x14006fe40`: `UnionFs::Utils::GetReparseData`
- `0x14006fd8c`: `API: Getting reparse point`
- `0x14006fdd9`: `File is not a reparse point`
- `0x14006fd31`: `ORIGIN: Corrupt reparse data`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::GetReparseData(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        int a4,
        ULONG LengthReturned)
{
  unsigned __int16 *v5; // rbx
  ULONG OutputBufferLength; // esi
  unsigned __int16 **v11; // rax
  unsigned __int16 *v12; // rdi
  unsigned int v13; // ebx
  int v14; // r8d
  ULONG v15; // ecx
  void *v16; // rax
  const char *OutputBuffer; // [rsp+28h] [rbp-40h]
  PVOID P; // [rsp+40h] [rbp-28h] BYREF
  const char *v20; // [rsp+48h] [rbp-20h] BYREF
  const char *v21; // [rsp+50h] [rbp-18h] BYREF
  const char *v22; // [rsp+58h] [rbp-10h] BYREF

  v5 = 0;
  LengthReturned = 0;
  for ( OutputBufferLength = 520; ; OutputBufferLength = v12[2] + 8 )
  {
    v11 = (unsigned __int16 **)utl::make_unique_pool<enum gsl::byte [0],256,1651656277,0>(&P, OutputBufferLength);
    v12 = *v11;
    *v11 = 0;
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( !v12 )
    {
      v13 = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a4,
        (struct UnionFs::StackEventTracer *)0x286002118E4LL,
        (unsigned __int64)"UnionFs::Utils::GetReparseData",
        "ORIGIN: Allocating reparse info buffer",
        OutputBuffer);
      return v13;
    }
    v13 = FltFsControlFile(Instance, FileObject, 0x900A8u, 0, 0, v12, OutputBufferLength, &LengthReturned);
    if ( v13 == 259 )
      MicrosoftTelemetryAssertTriggeredMsgKM("status != STATUS_PENDING");
    v15 = LengthReturned;
    if ( LengthReturned < 8 || v13 != -2147483643 )
      break;
    v5 = v12;
  }
  if ( v13 == -1073741195 )
  {
    if ( (unsigned int)dword_14009E178 > 4 )
    {
      LODWORD(P) = 6392;
      v20 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
      v21 = "UnionFs::Utils::GetReparseData";
      v22 = "File is not a reparse point";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        LengthReturned,
        (unsigned int)&byte_14009A38F,
        v14,
        (unsigned int)"UnionFs::Utils::GetReparseData",
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&P);
    }
    v13 = 0;
    goto LABEL_23;
  }
  if ( (v13 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)v13,
      a4,
      (struct UnionFs::StackEventTracer *)0x287002118FDLL,
      (unsigned __int64)"UnionFs::Utils::GetReparseData",
      "API: Getting reparse point",
      OutputBuffer);
LABEL_23:
    ExFreePoolWithTag(v12, 0);
    return v13;
  }
  if ( LengthReturned < (unsigned int)v12[2] + 8 )
  {
    v13 = -1073741566;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000102LL,
      a4,
      (struct UnionFs::StackEventTracer *)0x28800211905LL,
      (unsigned __int64)"UnionFs::Utils::GetReparseData",
      "ORIGIN: Corrupt reparse data",
      OutputBuffer);
    goto LABEL_23;
  }
  v16 = *(void **)a3;
  *(_QWORD *)a3 = v12;
  if ( v16 )
  {
    ExFreePoolWithTag(v16, 0);
    v15 = LengthReturned;
  }
  *(_DWORD *)(a3 + 8) = v15;
  return 0;
}

```

## disassembly

```asm
0x14006fc38  push    rbp
0x14006fc3a  push    rbx
0x14006fc3b  push    rsi
0x14006fc3c  push    rdi
0x14006fc3d  push    r12
0x14006fc3f  push    r13
0x14006fc41  push    r14
0x14006fc43  push    r15
0x14006fc45  mov     rbp, rsp
0x14006fc48  sub     rsp, 68h
0x14006fc4c  xor     ebx, ebx
0x14006fc4e  mov     r15, r9
0x14006fc51  mov     [rbp+arg_20], ebx
0x14006fc54  mov     r14, r8
0x14006fc57  mov     r12, rdx
0x14006fc5a  mov     r13, rcx
0x14006fc5d  mov     esi, 208h
0x14006fc62  mov     edx, esi
0x14006fc64  lea     rcx, [rbp+P]
0x14006fc68  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GCHCEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1651656277,0>(unsigned __int64)
0x14006fc6d  mov     rdi, [rax]
0x14006fc70  mov     qword ptr [rax], 0
0x14006fc77  test    rbx, rbx
0x14006fc7a  jz      short loc_14006FC8D
0x14006fc7c  xor     edx, edx; Tag
0x14006fc7e  mov     rcx, rbx; P
0x14006fc81  call    cs:__imp_ExFreePoolWithTag
0x14006fc88  nop     dword ptr [rax+rax+00h]
0x14006fc8d  mov     rcx, [rbp+P]; P
0x14006fc91  test    rcx, rcx
0x14006fc94  jz      short loc_14006FCA4
0x14006fc96  xor     edx, edx; Tag
0x14006fc98  call    cs:__imp_ExFreePoolWithTag
0x14006fc9f  nop     dword ptr [rax+rax+00h]
0x14006fca4  test    rdi, rdi
0x14006fca7  jz      loc_14006FE2D
0x14006fcad  lea     rax, [rbp+arg_20]
0x14006fcb1  xor     r9d, r9d; InputBuffer
0x14006fcb4  mov     [rsp+68h+LengthReturned], rax; LengthReturned
0x14006fcb9  mov     r8d, 900A8h; FsControlCode
0x14006fcbf  mov     [rsp+68h+OutputBufferLength], esi; OutputBufferLength
0x14006fcc3  mov     rdx, r12; FileObject
0x14006fcc6  mov     [rsp+68h+OutputBuffer], rdi; char *
0x14006fccb  mov     rcx, r13; Instance
0x14006fcce  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x14006fcd6  call    cs:__imp_FltFsControlFile
0x14006fcdd  nop     dword ptr [rax+rax+00h]
0x14006fce2  mov     ebx, eax
0x14006fce4  cmp     eax, 103h
0x14006fce9  jnz     short loc_14006FCF7
0x14006fceb  lea     rcx, aStatusStatusPe; "status != STATUS_PENDING"
0x14006fcf2  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006fcf7  mov     ecx, [rbp+arg_20]
0x14006fcfa  cmp     ecx, 8
0x14006fcfd  jb      short loc_14006FD16
0x14006fcff  cmp     ebx, 80000005h
0x14006fd05  jnz     short loc_14006FD16
0x14006fd07  movzx   esi, word ptr [rdi+4]
0x14006fd0b  mov     rbx, rdi
0x14006fd0e  add     esi, 8
0x14006fd11  jmp     loc_14006FC62
0x14006fd16  cmp     ebx, 0C0000275h
0x14006fd1c  jz      loc_14006FDB5
0x14006fd22  test    ebx, ebx
0x14006fd24  js      short loc_14006FD8C
0x14006fd26  movzx   eax, word ptr [rdi+4]
0x14006fd2a  add     eax, 8
0x14006fd2d  cmp     ecx, eax
0x14006fd2f  jnb     short loc_14006FD62
0x14006fd31  lea     rax, aOriginCorruptR; "ORIGIN: Corrupt reparse data"
0x14006fd38  mov     ebx, 0C0000102h
0x14006fd3d  mov     ecx, ebx; this
0x14006fd3f  mov     qword ptr [rsp+68h+InputBufferLength], rax; char *
0x14006fd44  lea     r9, aUnionfsUtilsGe_6; "UnionFs::Utils::GetReparseData"
0x14006fd4b  mov     r8, 28800211905h; struct UnionFs::StackEventTracer *
0x14006fd55  mov     rdx, r15; int
0x14006fd58  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006fd5d  jmp     loc_14006FE1A
0x14006fd62  mov     rax, [r14]
0x14006fd65  mov     [r14], rdi
0x14006fd68  test    rax, rax
0x14006fd6b  jz      short loc_14006FD81
0x14006fd6d  xor     edx, edx; Tag
0x14006fd6f  mov     rcx, rax; P
0x14006fd72  call    cs:__imp_ExFreePoolWithTag
0x14006fd79  nop     dword ptr [rax+rax+00h]
0x14006fd7e  mov     ecx, [rbp+arg_20]
0x14006fd81  mov     [r14+8], ecx
0x14006fd85  xor     eax, eax
0x14006fd87  jmp     loc_14006FE5B
0x14006fd8c  lea     rax, aApiGettingRepa; "API: Getting reparse point"
0x14006fd93  mov     r8, 287002118FDh; struct UnionFs::StackEventTracer *
0x14006fd9d  lea     r9, aUnionfsUtilsGe_6; "UnionFs::Utils::GetReparseData"
0x14006fda4  mov     qword ptr [rsp+68h+InputBufferLength], rax; char *
0x14006fda9  mov     rdx, r15; int
0x14006fdac  mov     ecx, ebx; this
0x14006fdae  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006fdb3  jmp     short loc_14006FE1A
0x14006fdb5  mov     eax, cs:dword_14009E178
0x14006fdbb  cmp     eax, 4
0x14006fdbe  jbe     short loc_14006FE18
0x14006fdc0  lea     rax, aOnecoreBaseFsU_3; "onecore\\base\\fs\\unionfs\\sys\\unionf"...
0x14006fdc7  mov     dword ptr [rbp+P], 18F8h
0x14006fdce  mov     [rbp+var_20], rax
0x14006fdd2  lea     r9, aUnionfsUtilsGe_6; "UnionFs::Utils::GetReparseData"
0x14006fdd9  lea     rax, aFileIsNotARepa; "File is not a reparse point"
0x14006fde0  mov     [rbp+var_18], r9
0x14006fde4  mov     [rbp+var_10], rax
0x14006fde8  lea     rdx, byte_14009A38F
0x14006fdef  lea     rax, [rbp+P]
0x14006fdf3  mov     [rsp+68h+LengthReturned], rax
0x14006fdf8  lea     rax, [rbp+var_20]
0x14006fdfc  mov     qword ptr [rsp+68h+OutputBufferLength], rax
0x14006fe01  lea     rax, [rbp+var_18]
0x14006fe05  mov     [rsp+68h+OutputBuffer], rax
0x14006fe0a  lea     rax, [rbp+var_10]
0x14006fe0e  mov     qword ptr [rsp+68h+InputBufferLength], rax
0x14006fe13  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14006fe18  xor     ebx, ebx
0x14006fe1a  xor     edx, edx; Tag
0x14006fe1c  mov     rcx, rdi; P
0x14006fe1f  call    cs:__imp_ExFreePoolWithTag
0x14006fe26  nop     dword ptr [rax+rax+00h]
0x14006fe2b  jmp     short loc_14006FE59
0x14006fe2d  lea     rax, aOriginAllocati_41; "ORIGIN: Allocating reparse info buffer"
0x14006fe34  mov     ebx, 0C000009Ah
0x14006fe39  mov     ecx, ebx; this
0x14006fe3b  mov     qword ptr [rsp+68h+InputBufferLength], rax; char *
0x14006fe40  lea     r9, aUnionfsUtilsGe_6; "UnionFs::Utils::GetReparseData"
0x14006fe47  mov     r8, 286002118E4h; struct UnionFs::StackEventTracer *
0x14006fe51  mov     rdx, r15; int
0x14006fe54  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006fe59  mov     eax, ebx
0x14006fe5b  add     rsp, 68h
0x14006fe5f  pop     r15
0x14006fe61  pop     r14
0x14006fe63  pop     r13
0x14006fe65  pop     r12
0x14006fe67  pop     rdi
0x14006fe68  pop     rsi
0x14006fe69  pop     rbx
0x14006fe6a  pop     rbp
0x14006fe6b  retn
```
