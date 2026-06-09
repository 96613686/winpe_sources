# UnionFs::StackEventTracer::GenerateFileNameForLogging(_UNICODE_STRING const *)

- ea: `0x140056450`
- end: `0x1400567ed`
- name: `?GenerateFileNameForLogging@StackEventTracer@UnionFs@@AEAAXPEBU_UNICODE_STRING@@@Z`
- size: `925`
- prototype: `void(UnionFs::StackEventTracer *__hidden this, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140056c0c`

## callees

- `0x140001008`
- `0x1400032b8`
- `0x140056450`
- `0x140079c48`
- `0x140079d0c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x140056587`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14005664d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140056587`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14005664d`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14005656a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14005656a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005653a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005653a`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140056617`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140056617`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005663e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14005663e`
- `FLTMGR!FltGetFileNameInformation` at `0x1400565bb`
- `FLTMGR!FltGetFileNameInformation` at `0x1400565bb`

## pseudocode

```c
void __fastcall UnionFs::StackEventTracer::GenerateFileNameForLogging(
        struct _UNICODE_STRING *this,
        const struct _UNICODE_STRING *a2)
{
  UnionFs::StackEventTracer *UniqueUnicodeString; // rax
  struct _UNICODE_STRING *v5; // rdx
  struct _UNICODE_STRING *v6; // rdi
  struct _UNICODE_STRING v7; // xmm6
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  __int16 MaximumLength; // dx
  const wchar_t *Buffer; // rax
  __int16 Length; // cx
  IRP *TopLevelIrp; // rsi
  struct _FLT_CALLBACK_DATA *v15; // rcx
  NTSTATUS FileNameInformation; // edi
  struct _FLT_FILE_NAME_INFORMATION *v17; // rcx
  struct _FLT_INSTANCE *v18; // rdx
  struct _FILE_OBJECT *v19; // rcx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rcx
  USHORT v24; // ax
  __int64 v25; // rdx
  __int64 v26; // rcx
  USHORT v27; // ax
  PWSTR v28; // rcx
  const char *v29; // [rsp+68h] [rbp-19h] BYREF
  __int64 v30; // [rsp+70h] [rbp-11h] BYREF
  const char *v31; // [rsp+78h] [rbp-9h] BYREF
  const char *v32; // [rsp+80h] [rbp-1h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp+7h] BYREF
  char v34; // [rsp+98h] [rbp+17h]
  int v35; // [rsp+F0h] [rbp+6Fh] BYREF
  const char *v36; // [rsp+F8h] [rbp+77h] BYREF
  const char *v37; // [rsp+100h] [rbp+7Fh] BYREF

  if ( a2 )
  {
    UniqueUnicodeString = (UnionFs::StackEventTracer *)FsFltWil::MakeUniqueUnicodeString(
                                                         &UnicodeString,
                                                         a2->MaximumLength,
                                                         1279685446);
    v6 = this + 41;
    if ( &this[41] != (struct _UNICODE_STRING *)UniqueUnicodeString )
    {
      v7 = *(struct _UNICODE_STRING *)UniqueUnicodeString;
      *(_OWORD *)UniqueUnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(this + 41, v5);
      *v6 = v7;
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v5);
    if ( this[41].Buffer )
    {
      RtlCopyUnicodeString(this + 41, a2);
      Buffer = this[41].Buffer;
      MaximumLength = this[41].MaximumLength;
      Length = v6->Length;
    }
    else
    {
      if ( (unsigned int)dword_14009E178 > 3 )
      {
        v35 = 635;
        v36 = "onecore\\base\\fs\\unionfs\\sys\\stackeventtracer.cpp";
        v37 = "UnionFs::StackEventTracer::GenerateFileNameForLogging";
        v29 = "Failed to allocate m_FileNameForLogging";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v8,
          (unsigned int)qword_140098A50,
          v9,
          v10,
          (__int64)&v29,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35);
      }
      MaximumLength = 48;
      Buffer = L"<File Name Unavailable>";
      Length = 46;
    }
    this[42].Length = Length;
    this[42].MaximumLength = MaximumLength;
    goto LABEL_35;
  }
  TopLevelIrp = IoGetTopLevelIrp();
  if ( TopLevelIrp == (IRP *)1379099506 )
  {
    *(_DWORD *)&this[42].Length = 3407922;
    Buffer = L"<Error in Recursive Call>";
    goto LABEL_35;
  }
  IoSetTopLevelIrp((PIRP)0x52336372);
  v15 = *(struct _FLT_CALLBACK_DATA **)&this[39].Length;
  if ( v15 )
  {
    UnicodeString.Buffer = 0;
    *(_QWORD *)&UnicodeString.Length = (char *)this + 648;
    v34 = 1;
    FileNameInformation = FltGetFileNameInformation(
                            v15,
                            0x1000402u,
                            (PFLT_FILE_NAME_INFORMATION *)&UnicodeString.Buffer);
    if ( !v34 )
      goto LABEL_20;
    v17 = **(struct _FLT_FILE_NAME_INFORMATION ***)&UnicodeString.Length;
    **(_QWORD **)&UnicodeString.Length = UnicodeString.Buffer;
  }
  else
  {
    v18 = (struct _FLT_INSTANCE *)this[39].Buffer;
    FileNameInformation = 0;
    if ( !v18 )
      goto LABEL_20;
    v19 = *(struct _FILE_OBJECT **)&this[40].Length;
    if ( !v19 )
      goto LABEL_20;
    UnicodeString.Buffer = 0;
    *(_QWORD *)&UnicodeString.Length = (char *)this + 648;
    v34 = 1;
    FileNameInformation = FltGetFileNameInformationUnsafe(
                            v19,
                            v18,
                            0x1000402u,
                            (PFLT_FILE_NAME_INFORMATION *)&UnicodeString.Buffer);
    if ( !v34 )
      goto LABEL_20;
    v17 = **(struct _FLT_FILE_NAME_INFORMATION ***)&UnicodeString.Length;
    **(_QWORD **)&UnicodeString.Length = UnicodeString.Buffer;
  }
  if ( v17 )
    FltReleaseFileNameInformation(v17);
LABEL_20:
  IoSetTopLevelIrp(TopLevelIrp);
  if ( FileNameInformation >= 0 )
  {
    v28 = this[40].Buffer;
    if ( !v28 )
      return;
    this[42].Length = v28[4];
    this[42].MaximumLength = v28[5];
    Buffer = (const wchar_t *)*((_QWORD *)v28 + 2);
  }
  else
  {
    if ( (unsigned int)dword_14009E178 > 3 )
    {
      v37 = *(const char **)&this[40].Length;
      v29 = (const char *)this[39].Buffer;
      v30 = *(_QWORD *)&this[39].Length;
      v31 = "onecore\\base\\fs\\unionfs\\sys\\stackeventtracer.cpp";
      v32 = "UnionFs::StackEventTracer::GenerateFileNameForLogging";
      *(_QWORD *)&UnicodeString.Length = "Querying file name";
      v35 = FileNameInformation;
      LODWORD(v36) = 710;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v20,
        (unsigned int)&word_1400989DE,
        v21,
        v22,
        (__int64)&UnicodeString,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v37);
    }
    v23 = *(_QWORD *)&this[40].Length;
    if ( v23 && (v24 = *(_WORD *)(v23 + 88)) != 0 )
    {
      this[42].Length = v24;
      this[42].MaximumLength = *(_WORD *)(v23 + 90);
    }
    else
    {
      v25 = *(_QWORD *)&this[39].Length;
      if ( !v25 || (v26 = *(_QWORD *)(*(_QWORD *)(v25 + 16) + 8LL)) == 0 || (v27 = *(_WORD *)(v26 + 88)) == 0 )
      {
        *(_DWORD *)&this[42].Length = 3145774;
        Buffer = L"<File Name Unavailable>";
        goto LABEL_35;
      }
      this[42].Length = v27;
      this[42].MaximumLength = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v25 + 16) + 8LL) + 90LL);
      v23 = *(_QWORD *)(*(_QWORD *)(v25 + 16) + 8LL);
    }
    Buffer = *(const wchar_t **)(v23 + 96);
  }
LABEL_35:
  this[42].Buffer = (PWSTR)Buffer;
}

```

## disassembly

```asm
0x140056450  mov     rax, rsp
0x140056453  push    rbp
0x140056454  push    rbx
0x140056455  push    rsi
0x140056456  push    rdi
0x140056457  push    r14
0x140056459  lea     rbp, [rax-5Fh]
0x14005645d  sub     rsp, 0B0h
0x140056464  xor     r14d, r14d
0x140056467  movaps  xmmword ptr [rax-38h], xmm6
0x14005646b  mov     rsi, rdx
0x14005646e  mov     rbx, rcx
0x140056471  test    rdx, rdx
0x140056474  jz      loc_14005656A
0x14005647a  movzx   edx, word ptr [rdx+2]
0x14005647e  lea     rcx, [rbp+57h+UnicodeString]
0x140056482  mov     r8d, 4C467346h
0x140056488  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14005648d  lea     rdi, [rbx+290h]
0x140056494  cmp     rdi, rax
0x140056497  jz      short loc_1400564AE
0x140056499  movups  xmm6, xmmword ptr [rax]
0x14005649c  mov     rcx, rdi; UnicodeString
0x14005649f  xorps   xmm0, xmm0
0x1400564a2  movups  xmmword ptr [rax], xmm0
0x1400564a5  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400564aa  movdqu  xmmword ptr [rdi], xmm6
0x1400564ae  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1400564b2  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400564b7  cmp     [rbx+298h], r14
0x1400564be  jnz     short loc_140056534
0x1400564c0  mov     eax, cs:dword_14009E178
0x1400564c6  cmp     eax, 3
0x1400564c9  jbe     short loc_140056523
0x1400564cb  lea     rax, aOnecoreBaseFsU_16; "onecore\\base\\fs\\unionfs\\sys\\stacke"...
0x1400564d2  mov     [rbp+57h+arg_8], 27Bh
0x1400564d9  mov     [rbp+57h+arg_10], rax
0x1400564dd  lea     rdx, qword_140098A50
0x1400564e4  lea     rax, aUnionfsStackev; "UnionFs::StackEventTracer::GenerateFile"...
0x1400564eb  mov     [rbp+57h+arg_18], rax
0x1400564ef  lea     rax, aFailedToAlloca; "Failed to allocate m_FileNameForLogging"
0x1400564f6  mov     [rbp+57h+var_70], rax
0x1400564fa  lea     rax, [rbp+57h+arg_8]
0x1400564fe  mov     [rsp+0D0h+var_98], rax
0x140056503  lea     rax, [rbp+57h+arg_10]
0x140056507  mov     [rsp+0D0h+var_A0], rax
0x14005650c  lea     rax, [rbp+57h+arg_18]
0x140056510  mov     [rsp+0D0h+var_A8], rax
0x140056515  lea     rax, [rbp+57h+var_70]
0x140056519  mov     [rsp+0D0h+var_B0], rax
0x14005651e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140056523  mov     edx, 30h ; '0'
0x140056528  lea     rax, aFileNameUnavai; "<File Name Unavailable>"
0x14005652f  lea     ecx, [rdx-2]
0x140056532  jmp     short loc_140056557
0x140056534  mov     rdx, rsi; SourceString
0x140056537  mov     rcx, rdi; DestinationString
0x14005653a  call    cs:__imp_RtlCopyUnicodeString
0x140056541  nop     dword ptr [rax+rax+00h]
0x140056546  mov     rax, [rbx+298h]
0x14005654d  movzx   edx, word ptr [rbx+292h]
0x140056554  movzx   ecx, word ptr [rdi]
0x140056557  mov     [rbx+2A0h], cx
0x14005655e  mov     [rbx+2A2h], dx
0x140056565  jmp     loc_1400567CF
0x14005656a  call    cs:__imp_IoGetTopLevelIrp
0x140056571  nop     dword ptr [rax+rax+00h]
0x140056576  mov     ecx, 52336372h; Irp
0x14005657b  mov     rsi, rax
0x14005657e  cmp     rax, rcx
0x140056581  jz      loc_1400567BE
0x140056587  call    cs:__imp_IoSetTopLevelIrp
0x14005658e  nop     dword ptr [rax+rax+00h]
0x140056593  mov     rcx, [rbx+270h]; CallbackData
0x14005659a  test    rcx, rcx
0x14005659d  jz      short loc_1400565DF
0x14005659f  lea     rdx, [rbx+288h]
0x1400565a6  mov     [rbp+57h+UnicodeString.Buffer], r14
0x1400565aa  mov     qword ptr [rbp+57h+UnicodeString.Length], rdx
0x1400565ae  lea     r8, [rbp+57h+UnicodeString.Buffer]; FileNameInformation
0x1400565b2  mov     edx, 1000402h; NameOptions
0x1400565b7  mov     [rbp+57h+var_40], 1
0x1400565bb  call    cs:__imp_FltGetFileNameInformation
0x1400565c2  nop     dword ptr [rax+rax+00h]
0x1400565c7  mov     edi, eax
0x1400565c9  cmp     [rbp+57h+var_40], r14b
0x1400565cd  jz      short loc_14005664A
0x1400565cf  mov     r8, qword ptr [rbp+57h+UnicodeString.Length]
0x1400565d3  mov     rdx, [rbp+57h+UnicodeString.Buffer]
0x1400565d7  mov     rcx, [r8]
0x1400565da  mov     [r8], rdx
0x1400565dd  jmp     short loc_140056639
0x1400565df  mov     rdx, [rbx+278h]; Instance
0x1400565e6  mov     edi, r14d
0x1400565e9  test    rdx, rdx
0x1400565ec  jz      short loc_14005664A
0x1400565ee  mov     rcx, [rbx+280h]; FileObject
0x1400565f5  test    rcx, rcx
0x1400565f8  jz      short loc_14005664A
0x1400565fa  lea     rax, [rbx+288h]
0x140056601  mov     [rbp+57h+UnicodeString.Buffer], r14
0x140056605  lea     r9, [rbp+57h+UnicodeString.Buffer]; FileNameInformation
0x140056609  mov     qword ptr [rbp+57h+UnicodeString.Length], rax
0x14005660d  mov     r8d, 1000402h; NameOptions
0x140056613  mov     [rbp+57h+var_40], 1
0x140056617  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14005661e  nop     dword ptr [rax+rax+00h]
0x140056623  mov     edi, eax
0x140056625  cmp     [rbp+57h+var_40], r14b
0x140056629  jz      short loc_14005664A
0x14005662b  mov     rdx, qword ptr [rbp+57h+UnicodeString.Length]
0x14005662f  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x140056633  mov     rcx, [rdx]; FileNameInformation
0x140056636  mov     [rdx], rax
0x140056639  test    rcx, rcx
0x14005663c  jz      short loc_14005664A
0x14005663e  call    cs:__imp_FltReleaseFileNameInformation
0x140056645  nop     dword ptr [rax+rax+00h]
0x14005664a  mov     rcx, rsi; Irp
0x14005664d  call    cs:__imp_IoSetTopLevelIrp
0x140056654  nop     dword ptr [rax+rax+00h]
0x140056659  test    edi, edi
0x14005665b  jns     loc_140056796
0x140056661  mov     eax, cs:dword_14009E178
0x140056667  cmp     eax, 3
0x14005666a  jbe     loc_140056710
0x140056670  mov     rax, [rbx+280h]
0x140056677  lea     rdx, word_1400989DE
0x14005667e  mov     [rbp+57h+arg_18], rax
0x140056682  mov     rax, [rbx+278h]
0x140056689  mov     [rbp+57h+var_70], rax
0x14005668d  mov     rax, [rbx+270h]
0x140056694  mov     [rbp+57h+var_68], rax
0x140056698  lea     rax, aOnecoreBaseFsU_16; "onecore\\base\\fs\\unionfs\\sys\\stacke"...
0x14005669f  mov     [rbp+57h+var_60], rax
0x1400566a3  lea     rax, aUnionfsStackev; "UnionFs::StackEventTracer::GenerateFile"...
0x1400566aa  mov     [rbp+57h+var_58], rax
0x1400566ae  lea     rax, aQueryingFileNa; "Querying file name"
0x1400566b5  mov     qword ptr [rbp+57h+UnicodeString.Length], rax
0x1400566b9  lea     rax, [rbp+57h+arg_18]
0x1400566bd  mov     [rsp+58h], rax
0x1400566c2  lea     rax, [rbp+57h+var_70]
0x1400566c6  mov     [rsp+0D0h+var_80], rax
0x1400566cb  lea     rax, [rbp+57h+var_68]
0x1400566cf  mov     [rsp+0D0h+var_88], rax
0x1400566d4  lea     rax, [rbp+57h+arg_8]
0x1400566d8  mov     [rsp+0D0h+var_90], rax
0x1400566dd  lea     rax, [rbp+57h+arg_10]
0x1400566e1  mov     [rsp+0D0h+var_98], rax
0x1400566e6  lea     rax, [rbp+57h+var_60]
0x1400566ea  mov     [rsp+0D0h+var_A0], rax
0x1400566ef  lea     rax, [rbp+57h+var_58]
0x1400566f3  mov     [rsp+0D0h+var_A8], rax
0x1400566f8  lea     rax, [rbp+57h+UnicodeString]
0x1400566fc  mov     [rsp+0D0h+var_B0], rax
0x140056701  mov     [rbp+57h+arg_8], edi
0x140056704  mov     dword ptr [rbp+57h+arg_10], 2C6h
0x14005670b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x140056710  mov     rcx, [rbx+280h]
0x140056717  test    rcx, rcx
0x14005671a  jz      short loc_140056739
0x14005671c  movzx   eax, word ptr [rcx+58h]
0x140056720  test    ax, ax
0x140056723  jz      short loc_140056739
0x140056725  mov     [rbx+2A0h], ax
0x14005672c  movzx   eax, word ptr [rcx+5Ah]
0x140056730  mov     [rbx+2A2h], ax
0x140056737  jmp     short loc_14005677D
0x140056739  mov     rdx, [rbx+270h]
0x140056740  test    rdx, rdx
0x140056743  jz      short loc_140056783
0x140056745  mov     rax, [rdx+10h]
0x140056749  mov     rcx, [rax+8]
0x14005674d  test    rcx, rcx
0x140056750  jz      short loc_140056783
0x140056752  movzx   eax, word ptr [rcx+58h]
0x140056756  test    ax, ax
0x140056759  jz      short loc_140056783
0x14005675b  mov     [rbx+2A0h], ax
0x140056762  mov     rax, [rdx+10h]
0x140056766  mov     rcx, [rax+8]
0x14005676a  movzx   eax, word ptr [rcx+5Ah]
0x14005676e  mov     [rbx+2A2h], ax
0x140056775  mov     rax, [rdx+10h]
0x140056779  mov     rcx, [rax+8]
0x14005677d  mov     rax, [rcx+60h]
0x140056781  jmp     short loc_1400567CF
0x140056783  mov     dword ptr [rbx+2A0h], 30002Eh
0x14005678d  lea     rax, aFileNameUnavai; "<File Name Unavailable>"
0x140056794  jmp     short loc_1400567CF
0x140056796  mov     rcx, [rbx+288h]
0x14005679d  test    rcx, rcx
0x1400567a0  jz      short loc_1400567D6
0x1400567a2  movzx   eax, word ptr [rcx+8]
0x1400567a6  mov     [rbx+2A0h], ax
0x1400567ad  movzx   eax, word ptr [rcx+0Ah]
0x1400567b1  mov     [rbx+2A2h], ax
0x1400567b8  mov     rax, [rcx+10h]
0x1400567bc  jmp     short loc_1400567CF
0x1400567be  mov     dword ptr [rbx+2A0h], 340032h
0x1400567c8  lea     rax, aErrorInRecursi; "<Error in Recursive Call>"
0x1400567cf  mov     [rbx+2A8h], rax
0x1400567d6  movaps  xmm6, [rsp+0D0h+var_38+8]
0x1400567de  add     rsp, 0B0h
0x1400567e5  pop     r14
0x1400567e7  pop     rdi
0x1400567e8  pop     rsi
0x1400567e9  pop     rbx
0x1400567ea  pop     rbp
0x1400567eb  retn
```
