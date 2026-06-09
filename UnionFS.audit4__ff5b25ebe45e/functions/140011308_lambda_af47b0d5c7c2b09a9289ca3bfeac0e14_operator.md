# _lambda_af47b0d5c7c2b09a9289ca3bfeac0e14_::operator()

- ea: `0x140011308`
- end: `0x140011491`
- name: `_lambda_af47b0d5c7c2b09a9289ca3bfeac0e14_::operator()`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140011a60`

## callees

- `0x140001220`
- `0x140002158`
- `0x140011308`

## import_xrefs

- `FLTMGR!FltCancelFileOpen` at `0x1400113c7`
- `FLTMGR!FltCancelFileOpen` at `0x1400113c7`
- `FLTMGR!FltSetInformationFile` at `0x140011401`
- `FLTMGR!FltSetInformationFile` at `0x140011401`

## string_xrefs

- `0x140011354`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x140011426`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x14001135f`: `UnionFs::UnionFsFilter::PostCreate::<lambda_af47b0d5c7c2b09a9289ca3bfeac0e14>::operator ()`
- `0x140011434`: `UnionFs::UnionFsFilter::PostCreate::<lambda_af47b0d5c7c2b09a9289ca3bfeac0e14>::operator ()`
- `0x14001136a`: `PostCreate failure after create with side effect`
- `0x14001143f`: `Could not set delete disposition in PostCreate of FILE_CREATED after failure.`

## pseudocode

```c
void __fastcall lambda_af47b0d5c7c2b09a9289ca3bfeac0e14_::operator()(_QWORD *a1, int a2, __int64 a3, int a4)
{
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // [rsp+50h] [rbp-20h] BYREF
  const char *v14; // [rsp+58h] [rbp-18h] BYREF
  const char *v15; // [rsp+60h] [rbp-10h] BYREF
  const char *v16; // [rsp+68h] [rbp-8h] BYREF
  int FileInformation; // [rsp+90h] [rbp+20h] BYREF
  int v18; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+38h] BYREF

  v6 = *(_QWORD *)(*a1 + 32LL);
  if ( !v6 )
  {
LABEL_4:
    if ( (unsigned int)dword_14009E178 > 3 )
    {
      v7 = *a1;
      FileInformation = a2;
      v8 = *(_QWORD *)(v7 + 32);
      v16 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
      v15 = "UnionFs::UnionFsFilter::PostCreate::<lambda_af47b0d5c7c2b09a9289ca3bfeac0e14>::operator ()";
      v14 = "PostCreate failure after create with side effect";
      v19 = v8;
      v18 = 635;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)word_1400963CA,
        v6,
        a4,
        (__int64)&v14,
        (__int64)&v15,
        (__int64)&v16,
        (__int64)&v18,
        (__int64)&v19,
        (__int64)&FileInformation);
    }
    goto LABEL_6;
  }
  v6 -= 2;
  if ( v6 )
  {
    if ( v6 != 1 )
      goto LABEL_6;
    goto LABEL_4;
  }
  v9 = a1[1];
  FileInformation = 3;
  v10 = FltSetInformationFile(
          *(PFLT_INSTANCE *)(v9 + 24),
          *(PFILE_OBJECT *)(v9 + 32),
          &FileInformation,
          4u,
          (FILE_INFORMATION_CLASS)64);
  if ( v10 < 0 && (unsigned int)dword_14009E178 > 3 )
  {
    LODWORD(v19) = v10;
    v18 = a2;
    v14 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
    v15 = "UnionFs::UnionFsFilter::PostCreate::<lambda_af47b0d5c7c2b09a9289ca3bfeac0e14>::operator ()";
    v16 = "Could not set delete disposition in PostCreate of FILE_CREATED after failure.";
    v13 = 654;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      dword_14009E178,
      (unsigned int)word_1400961EA,
      v11,
      v12,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v19,
      (__int64)&v18);
  }
LABEL_6:
  FltCancelFileOpen(*(PFLT_INSTANCE *)(a1[1] + 24LL), *(PFILE_OBJECT *)(a1[1] + 32LL));
}

```

## disassembly

```asm
0x140011308  push    rbp
0x14001130a  push    rbx
0x14001130b  push    rdi
0x14001130c  mov     rbp, rsp
0x14001130f  sub     rsp, 70h
0x140011313  mov     rax, [rcx]
0x140011316  mov     edi, edx
0x140011318  mov     rbx, rcx
0x14001131b  mov     r8, [rax+20h]
0x14001131f  test    r8, r8
0x140011322  jz      short loc_140011338
0x140011324  sub     r8, 2
0x140011328  jz      loc_1400113DC
0x14001132e  cmp     r8, 1
0x140011332  jnz     loc_1400113BB
0x140011338  mov     eax, cs:dword_14009E178
0x14001133e  cmp     eax, 3
0x140011341  jbe     short loc_1400113BB
0x140011343  mov     rax, [rcx]
0x140011346  lea     rdx, word_1400963CA
0x14001134d  mov     [rbp+FileInformation], edi
0x140011350  mov     rcx, [rax+20h]
0x140011354  lea     rax, aOnecoreBaseFsU_14; "onecore\\base\\fs\\unionfs\\sys\\create"...
0x14001135b  mov     [rbp+var_8], rax
0x14001135f  lea     rax, aUnionfsUnionfs_53; "UnionFs::UnionFsFilter::PostCreate::<la"...
0x140011366  mov     [rbp+var_10], rax
0x14001136a  lea     rax, aPostcreateFail; "PostCreate failure after create with si"...
0x140011371  mov     [rbp+var_18], rax
0x140011375  lea     rax, [rbp+FileInformation]
0x140011379  mov     [rsp+70h+var_28], rax
0x14001137e  lea     rax, [rbp+arg_18]
0x140011382  mov     [rsp+70h+var_30], rax
0x140011387  lea     rax, [rbp+arg_10]
0x14001138b  mov     [rsp+70h+var_38], rax
0x140011390  lea     rax, [rbp+var_8]
0x140011394  mov     [rsp+70h+var_40], rax
0x140011399  lea     rax, [rbp+var_10]
0x14001139d  mov     [rsp+70h+var_48], rax
0x1400113a2  lea     rax, [rbp+var_18]
0x1400113a6  mov     qword ptr [rsp+70h+FileInformationClass], rax
0x1400113ab  mov     [rbp+arg_18], rcx
0x1400113af  mov     [rbp+arg_10], 27Bh
0x1400113b6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400113bb  mov     rcx, [rbx+8]
0x1400113bf  mov     rdx, [rcx+20h]; FileObject
0x1400113c3  mov     rcx, [rcx+18h]; Instance
0x1400113c7  call    cs:__imp_FltCancelFileOpen
0x1400113ce  nop     dword ptr [rax+rax+00h]
0x1400113d3  add     rsp, 70h
0x1400113d7  pop     rdi
0x1400113d8  pop     rbx
0x1400113d9  pop     rbp
0x1400113da  retn
0x1400113dc  mov     rcx, [rcx+8]
0x1400113e0  lea     r8, [rbp+FileInformation]; FileInformation
0x1400113e4  mov     [rbp+FileInformation], 3
0x1400113eb  mov     r9d, 4; Length
0x1400113f1  mov     [rsp+70h+FileInformationClass], 40h ; '@'; FileInformationClass
0x1400113f9  mov     rdx, [rcx+20h]; FileObject
0x1400113fd  mov     rcx, [rcx+18h]; Instance
0x140011401  call    cs:__imp_FltSetInformationFile
0x140011408  nop     dword ptr [rax+rax+00h]
0x14001140d  test    eax, eax
0x14001140f  jns     short loc_1400113BB
0x140011411  mov     ecx, cs:dword_14009E178
0x140011417  cmp     ecx, 3
0x14001141a  jbe     short loc_1400113BB
0x14001141c  mov     dword ptr [rbp+arg_18], eax
0x14001141f  lea     rdx, word_1400961EA
0x140011426  lea     rax, aOnecoreBaseFsU_14; "onecore\\base\\fs\\unionfs\\sys\\create"...
0x14001142d  mov     [rbp+arg_10], edi
0x140011430  mov     [rbp+var_18], rax
0x140011434  lea     rax, aUnionfsUnionfs_53; "UnionFs::UnionFsFilter::PostCreate::<la"...
0x14001143b  mov     [rbp+var_10], rax
0x14001143f  lea     rax, aCouldNotSetDel; "Could not set delete disposition in Pos"...
0x140011446  mov     [rbp+var_8], rax
0x14001144a  lea     rax, [rbp+arg_10]
0x14001144e  mov     [rsp+70h+var_28], rax
0x140011453  lea     rax, [rbp+arg_18]
0x140011457  mov     [rsp+70h+var_30], rax
0x14001145c  lea     rax, [rbp+var_20]
0x140011460  mov     [rsp+70h+var_38], rax
0x140011465  lea     rax, [rbp+var_18]
0x140011469  mov     [rsp+70h+var_40], rax
0x14001146e  lea     rax, [rbp+var_10]
0x140011472  mov     [rsp+70h+var_48], rax
0x140011477  lea     rax, [rbp+var_8]
0x14001147b  mov     qword ptr [rsp+70h+FileInformationClass], rax
0x140011480  mov     [rbp+var_20], 28Eh
0x140011487  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001148c  jmp     loc_1400113BB
```
