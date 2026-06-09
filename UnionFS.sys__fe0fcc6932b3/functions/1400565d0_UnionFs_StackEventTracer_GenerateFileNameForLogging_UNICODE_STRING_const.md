# UnionFs::StackEventTracer::GenerateFileNameForLogging(_UNICODE_STRING const *)

- ea: `0x1400565d0`
- end: `0x14005696d`
- name: `?GenerateFileNameForLogging@StackEventTracer@UnionFs@@AEAAXPEBU_UNICODE_STRING@@@Z`
- size: `925`
- prototype: `void(UnionFs::StackEventTracer *__hidden this, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140056d8c`

## callees

- `0x140001008`
- `0x1400032b8`
- `0x1400565d0`
- `0x140079f68`
- `0x14007a02c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x140056707`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400567cd`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140056707`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400567cd`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400566ea`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400566ea`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400566ba`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400566ba`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140056797`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140056797`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400567be`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400567be`
- `FLTMGR!FltGetFileNameInformation` at `0x14005673b`
- `FLTMGR!FltGetFileNameInformation` at `0x14005673b`

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
          (unsigned int)qword_140098AD0,
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
        (unsigned int)&dword_140098A14,
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
0x1400565d0  mov     rax, rsp
0x1400565d3  push    rbp
0x1400565d4  push    rbx
0x1400565d5  push    rsi
0x1400565d6  push    rdi
0x1400565d7  push    r14
0x1400565d9  lea     rbp, [rax-5Fh]
0x1400565dd  sub     rsp, 0B0h
0x1400565e4  xor     r14d, r14d
0x1400565e7  movaps  xmmword ptr [rax-38h], xmm6
0x1400565eb  mov     rsi, rdx
0x1400565ee  mov     rbx, rcx
0x1400565f1  test    rdx, rdx
0x1400565f4  jz      loc_1400566EA
0x1400565fa  movzx   edx, word ptr [rdx+2]
0x1400565fe  lea     rcx, [rbp+57h+UnicodeString]
0x140056602  mov     r8d, 4C467346h
0x140056608  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14005660d  lea     rdi, [rbx+290h]
0x140056614  cmp     rdi, rax
0x140056617  jz      short loc_14005662E
0x140056619  movups  xmm6, xmmword ptr [rax]
0x14005661c  mov     rcx, rdi; UnicodeString
0x14005661f  xorps   xmm0, xmm0
0x140056622  movups  xmmword ptr [rax], xmm0
0x140056625  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14005662a  movdqu  xmmword ptr [rdi], xmm6
0x14005662e  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x140056632  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140056637  cmp     [rbx+298h], r14
0x14005663e  jnz     short loc_1400566B4
0x140056640  mov     eax, cs:dword_14009E178
0x140056646  cmp     eax, 3
0x140056649  jbe     short loc_1400566A3
0x14005664b  lea     rax, aOnecoreBaseFsU_16; "onecore\\base\\fs\\unionfs\\sys\\stacke"...
0x140056652  mov     [rbp+57h+arg_8], 27Bh
0x140056659  mov     [rbp+57h+arg_10], rax
0x14005665d  lea     rdx, qword_140098AD0
0x140056664  lea     rax, aUnionfsStackev; "UnionFs::StackEventTracer::GenerateFile"...
0x14005666b  mov     [rbp+57h+arg_18], rax
0x14005666f  lea     rax, aFailedToAlloca; "Failed to allocate m_FileNameForLogging"
0x140056676  mov     [rbp+57h+var_70], rax
0x14005667a  lea     rax, [rbp+57h+arg_8]
0x14005667e  mov     [rsp+0D0h+var_98], rax
0x140056683  lea     rax, [rbp+57h+arg_10]
0x140056687  mov     [rsp+0D0h+var_A0], rax
0x14005668c  lea     rax, [rbp+57h+arg_18]
0x140056690  mov     [rsp+0D0h+var_A8], rax
0x140056695  lea     rax, [rbp+57h+var_70]
0x140056699  mov     [rsp+0D0h+var_B0], rax
0x14005669e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400566a3  mov     edx, 30h ; '0'
0x1400566a8  lea     rax, aFileNameUnavai; "<File Name Unavailable>"
0x1400566af  lea     ecx, [rdx-2]
0x1400566b2  jmp     short loc_1400566D7
0x1400566b4  mov     rdx, rsi; SourceString
0x1400566b7  mov     rcx, rdi; DestinationString
0x1400566ba  call    cs:__imp_RtlCopyUnicodeString
0x1400566c1  nop     dword ptr [rax+rax+00h]
0x1400566c6  mov     rax, [rbx+298h]
0x1400566cd  movzx   edx, word ptr [rbx+292h]
0x1400566d4  movzx   ecx, word ptr [rdi]
0x1400566d7  mov     [rbx+2A0h], cx
0x1400566de  mov     [rbx+2A2h], dx
0x1400566e5  jmp     loc_14005694F
0x1400566ea  call    cs:__imp_IoGetTopLevelIrp
0x1400566f1  nop     dword ptr [rax+rax+00h]
0x1400566f6  mov     ecx, 52336372h; Irp
0x1400566fb  mov     rsi, rax
0x1400566fe  cmp     rax, rcx
0x140056701  jz      loc_14005693E
0x140056707  call    cs:__imp_IoSetTopLevelIrp
0x14005670e  nop     dword ptr [rax+rax+00h]
0x140056713  mov     rcx, [rbx+270h]; CallbackData
0x14005671a  test    rcx, rcx
0x14005671d  jz      short loc_14005675F
0x14005671f  lea     rdx, [rbx+288h]
0x140056726  mov     [rbp+57h+UnicodeString.Buffer], r14
0x14005672a  mov     qword ptr [rbp+57h+UnicodeString.Length], rdx
0x14005672e  lea     r8, [rbp+57h+UnicodeString.Buffer]; FileNameInformation
0x140056732  mov     edx, 1000402h; NameOptions
0x140056737  mov     [rbp+57h+var_40], 1
0x14005673b  call    cs:__imp_FltGetFileNameInformation
0x140056742  nop     dword ptr [rax+rax+00h]
0x140056747  mov     edi, eax
0x140056749  cmp     [rbp+57h+var_40], r14b
0x14005674d  jz      short loc_1400567CA
0x14005674f  mov     r8, qword ptr [rbp+57h+UnicodeString.Length]
0x140056753  mov     rdx, [rbp+57h+UnicodeString.Buffer]
0x140056757  mov     rcx, [r8]
0x14005675a  mov     [r8], rdx
0x14005675d  jmp     short loc_1400567B9
0x14005675f  mov     rdx, [rbx+278h]; Instance
0x140056766  mov     edi, r14d
0x140056769  test    rdx, rdx
0x14005676c  jz      short loc_1400567CA
0x14005676e  mov     rcx, [rbx+280h]; FileObject
0x140056775  test    rcx, rcx
0x140056778  jz      short loc_1400567CA
0x14005677a  lea     rax, [rbx+288h]
0x140056781  mov     [rbp+57h+UnicodeString.Buffer], r14
0x140056785  lea     r9, [rbp+57h+UnicodeString.Buffer]; FileNameInformation
0x140056789  mov     qword ptr [rbp+57h+UnicodeString.Length], rax
0x14005678d  mov     r8d, 1000402h; NameOptions
0x140056793  mov     [rbp+57h+var_40], 1
0x140056797  call    cs:__imp_FltGetFileNameInformationUnsafe
0x14005679e  nop     dword ptr [rax+rax+00h]
0x1400567a3  mov     edi, eax
0x1400567a5  cmp     [rbp+57h+var_40], r14b
0x1400567a9  jz      short loc_1400567CA
0x1400567ab  mov     rdx, qword ptr [rbp+57h+UnicodeString.Length]
0x1400567af  mov     rax, [rbp+57h+UnicodeString.Buffer]
0x1400567b3  mov     rcx, [rdx]; FileNameInformation
0x1400567b6  mov     [rdx], rax
0x1400567b9  test    rcx, rcx
0x1400567bc  jz      short loc_1400567CA
0x1400567be  call    cs:__imp_FltReleaseFileNameInformation
0x1400567c5  nop     dword ptr [rax+rax+00h]
0x1400567ca  mov     rcx, rsi; Irp
0x1400567cd  call    cs:__imp_IoSetTopLevelIrp
0x1400567d4  nop     dword ptr [rax+rax+00h]
0x1400567d9  test    edi, edi
0x1400567db  jns     loc_140056916
0x1400567e1  mov     eax, cs:dword_14009E178
0x1400567e7  cmp     eax, 3
0x1400567ea  jbe     loc_140056890
0x1400567f0  mov     rax, [rbx+280h]
0x1400567f7  lea     rdx, dword_140098A14
0x1400567fe  mov     [rbp+57h+arg_18], rax
0x140056802  mov     rax, [rbx+278h]
0x140056809  mov     [rbp+57h+var_70], rax
0x14005680d  mov     rax, [rbx+270h]
0x140056814  mov     [rbp+57h+var_68], rax
0x140056818  lea     rax, aOnecoreBaseFsU_16; "onecore\\base\\fs\\unionfs\\sys\\stacke"...
0x14005681f  mov     [rbp+57h+var_60], rax
0x140056823  lea     rax, aUnionfsStackev; "UnionFs::StackEventTracer::GenerateFile"...
0x14005682a  mov     [rbp+57h+var_58], rax
0x14005682e  lea     rax, aQueryingFileNa; "Querying file name"
0x140056835  mov     qword ptr [rbp+57h+UnicodeString.Length], rax
0x140056839  lea     rax, [rbp+57h+arg_18]
0x14005683d  mov     [rsp+58h], rax
0x140056842  lea     rax, [rbp+57h+var_70]
0x140056846  mov     [rsp+0D0h+var_80], rax
0x14005684b  lea     rax, [rbp+57h+var_68]
0x14005684f  mov     [rsp+0D0h+var_88], rax
0x140056854  lea     rax, [rbp+57h+arg_8]
0x140056858  mov     [rsp+0D0h+var_90], rax
0x14005685d  lea     rax, [rbp+57h+arg_10]
0x140056861  mov     [rsp+0D0h+var_98], rax
0x140056866  lea     rax, [rbp+57h+var_60]
0x14005686a  mov     [rsp+0D0h+var_A0], rax
0x14005686f  lea     rax, [rbp+57h+var_58]
0x140056873  mov     [rsp+0D0h+var_A8], rax
0x140056878  lea     rax, [rbp+57h+UnicodeString]
0x14005687c  mov     [rsp+0D0h+var_B0], rax
0x140056881  mov     [rbp+57h+arg_8], edi
0x140056884  mov     dword ptr [rbp+57h+arg_10], 2C6h
0x14005688b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x140056890  mov     rcx, [rbx+280h]
0x140056897  test    rcx, rcx
0x14005689a  jz      short loc_1400568B9
0x14005689c  movzx   eax, word ptr [rcx+58h]
0x1400568a0  test    ax, ax
0x1400568a3  jz      short loc_1400568B9
0x1400568a5  mov     [rbx+2A0h], ax
0x1400568ac  movzx   eax, word ptr [rcx+5Ah]
0x1400568b0  mov     [rbx+2A2h], ax
0x1400568b7  jmp     short loc_1400568FD
0x1400568b9  mov     rdx, [rbx+270h]
0x1400568c0  test    rdx, rdx
0x1400568c3  jz      short loc_140056903
0x1400568c5  mov     rax, [rdx+10h]
0x1400568c9  mov     rcx, [rax+8]
0x1400568cd  test    rcx, rcx
0x1400568d0  jz      short loc_140056903
0x1400568d2  movzx   eax, word ptr [rcx+58h]
0x1400568d6  test    ax, ax
0x1400568d9  jz      short loc_140056903
0x1400568db  mov     [rbx+2A0h], ax
0x1400568e2  mov     rax, [rdx+10h]
0x1400568e6  mov     rcx, [rax+8]
0x1400568ea  movzx   eax, word ptr [rcx+5Ah]
0x1400568ee  mov     [rbx+2A2h], ax
0x1400568f5  mov     rax, [rdx+10h]
0x1400568f9  mov     rcx, [rax+8]
0x1400568fd  mov     rax, [rcx+60h]
0x140056901  jmp     short loc_14005694F
0x140056903  mov     dword ptr [rbx+2A0h], 30002Eh
0x14005690d  lea     rax, aFileNameUnavai; "<File Name Unavailable>"
0x140056914  jmp     short loc_14005694F
0x140056916  mov     rcx, [rbx+288h]
0x14005691d  test    rcx, rcx
0x140056920  jz      short loc_140056956
0x140056922  movzx   eax, word ptr [rcx+8]
0x140056926  mov     [rbx+2A0h], ax
0x14005692d  movzx   eax, word ptr [rcx+0Ah]
0x140056931  mov     [rbx+2A2h], ax
0x140056938  mov     rax, [rcx+10h]
0x14005693c  jmp     short loc_14005694F
0x14005693e  mov     dword ptr [rbx+2A0h], 340032h
0x140056948  lea     rax, aErrorInRecursi; "<Error in Recursive Call>"
0x14005694f  mov     [rbx+2A8h], rax
0x140056956  movaps  xmm6, [rsp+0D0h+var_38+8]
0x14005695e  add     rsp, 0B0h
0x140056965  pop     r14
0x140056967  pop     rdi
0x140056968  pop     rsi
0x140056969  pop     rbx
0x14005696a  pop     rbp
0x14005696b  retn
```
