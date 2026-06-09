# UnionFs::UfsPathTable::Traverse(_FLT_INSTANCE const &,wistd::function<long (UnionFs::UfsPathTierNode &,UnionFs::UfsPathTierNode *,UnionFs::UFS_TABLE_TRAVERSE_CTX &)> const &,UnionFs::StackEventTracer &,UnionFs::TraverseFlags)

- ea: `0x14004e914`
- end: `0x14004eabc`
- name: `?Traverse@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBV?$function@$$A6AJAEAVUfsPathTierNode@UnionFs@@PEAV12@AEAUUFS_TABLE_TRAVERSE_CTX@2@@Z@wistd@@AEAVStackEventTracer@2@W4TraverseFlags@2@@Z`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140048244`

## callees

- `0x1400439d8`
- `0x14004e914`
- `0x14004eac4`
- `0x140056c44`
- `0x140056c7c`
- `0x140075454`
- `0x140079f68`
- `0x14007a02c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004ea3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ea3e`
- `ntoskrnl!ExAllocatePool2` at `0x14004e9d4`
- `ntoskrnl!ExAllocatePool2` at `0x14004e9d4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004e96d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004e96d`

## string_xrefs

- `0x14004e9a9`: `UnionFs::UfsPathName::AllocAndInit`
- `0x14004ea6b`: `UnionFs::UfsPathName::AllocAndInit`
- `0x14004e94c`: `ORIGIN: Allocating path string`
- `0x14004ea4e`: `ORIGIN: Allocating UfsPathName`
- `0x14004ea83`: `PUSH: Allocating rootPath`
- `0x14004ea94`: `UnionFs::UfsPathTable::Traverse`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::Traverse(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  const char *v9; // rax
  __int64 v10; // r8
  unsigned int v11; // edi
  struct _UNICODE_STRING *v12; // rdx
  __int64 Pool2; // rax
  struct _UNICODE_STRING *v14; // rdx
  __int64 v15; // rdi
  struct _UNICODE_STRING *v16; // rdx
  unsigned int v17; // ebx
  const char *v19; // [rsp+28h] [rbp-28h]
  const char *v20; // [rsp+28h] [rbp-28h]
  unsigned __int16 v21; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF

  FsFltWil::MakeUniqueUnicodeString(&DestinationString, 52, 1634616917);
  if ( !DestinationString.Buffer )
  {
    v9 = "ORIGIN: Allocating path string";
    v10 = 0x5AC00130070LL;
LABEL_11:
    v11 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a4,
      (struct UnionFs::StackEventTracer *)v10,
      (unsigned __int64)"UnionFs::UfsPathName::AllocAndInit",
      v9,
      v19);
    goto LABEL_12;
  }
  RtlCopyUnicodeString(&DestinationString, &UnionFs::g_RootName);
  v21 = 0;
  v11 = UnionFs::Utils::PrependVolumeNameFromInstance(a2, &DestinationString, a4, &v21);
  if ( (v11 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v11,
      a4,
      (struct UnionFs::StackEventTracer *)0x5BE0013007ALL,
      (unsigned __int64)"UnionFs::UfsPathName::AllocAndInit",
      "PUSH: Prepending volume name",
      v19);
LABEL_12:
    FsFltWil::Details::FreeUnicodeString(&DestinationString, v12);
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v11,
      a4,
      (struct UnionFs::StackEventTracer *)0x45900140B08LL,
      (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
      "PUSH: Allocating rootPath",
      v20);
    return v11;
  }
  Pool2 = ExAllocatePool2(64, 256, 1634616917);
  if ( !Pool2 || (v15 = UnionFs::UfsPathName::UfsPathName(Pool2, &DestinationString, v21)) == 0 )
  {
    v9 = "ORIGIN: Allocating UfsPathName";
    v10 = 0x5CC00130084LL;
    goto LABEL_11;
  }
  FsFltWil::Details::FreeUnicodeString(&DestinationString, v14);
  v17 = UnionFs::UfsPathTable::Traverse(a1, a2, (const char *)v15, a5, a3, a4);
  if ( !*(_BYTE *)(v15 + 16) )
    *(_OWORD *)v15 = 0;
  FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v15, v16);
  ExFreePoolWithTag((PVOID)v15, 0);
  return v17;
}

```

## disassembly

```asm
0x14004e914  push    rbp
0x14004e916  push    rbx
0x14004e917  push    rsi
0x14004e918  push    rdi
0x14004e919  push    r12
0x14004e91b  push    r14
0x14004e91d  push    r15
0x14004e91f  mov     rbp, rsp
0x14004e922  sub     rsp, 50h
0x14004e926  mov     r15, r8
0x14004e929  mov     r14, rdx
0x14004e92c  mov     r12, rcx
0x14004e92f  xor     ebx, ebx
0x14004e931  mov     r8d, 616E4655h
0x14004e937  lea     rcx, [rbp+DestinationString]
0x14004e93b  mov     rsi, r9
0x14004e93e  lea     edx, [rbx+34h]
0x14004e941  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14004e946  cmp     [rbp+DestinationString.Buffer], rbx
0x14004e94a  jnz     short loc_14004E962
0x14004e94c  lea     rax, aOriginAllocati_51; "ORIGIN: Allocating path string"
0x14004e953  mov     r8, 5AC00130070h
0x14004e95d  jmp     loc_14004EA5F
0x14004e962  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; SourceString
0x14004e969  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004e96d  call    cs:__imp_RtlCopyUnicodeString
0x14004e974  nop     dword ptr [rax+rax+00h]
0x14004e979  xor     eax, eax
0x14004e97b  lea     r9, [rbp+var_20]
0x14004e97f  mov     r8, rsi
0x14004e982  mov     [rbp+var_20], ax
0x14004e986  lea     rdx, [rbp+DestinationString]
0x14004e98a  mov     rcx, r14
0x14004e98d  call    ?PrependVolumeNameFromInstance@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEAG@Z; UnionFs::Utils::PrependVolumeNameFromInstance(_FLT_INSTANCE const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort *)
0x14004e992  mov     edi, eax
0x14004e994  test    eax, eax
0x14004e996  jns     short loc_14004E9C4
0x14004e998  lea     rax, aPushPrepending_0; "PUSH: Prepending volume name"
0x14004e99f  mov     r8, 5BE0013007Ah; struct UnionFs::StackEventTracer *
0x14004e9a9  lea     r9, aUnionfsUfspath_42; "UnionFs::UfsPathName::AllocAndInit"
0x14004e9b0  mov     [rsp+50h+var_30], rax; char *
0x14004e9b5  mov     rdx, rsi; int
0x14004e9b8  mov     ecx, edi; this
0x14004e9ba  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004e9bf  jmp     loc_14004EA7A
0x14004e9c4  mov     edx, 100h
0x14004e9c9  mov     ecx, 40h ; '@'
0x14004e9ce  mov     r8d, 616E4655h
0x14004e9d4  call    cs:__imp_ExAllocatePool2
0x14004e9db  nop     dword ptr [rax+rax+00h]
0x14004e9e0  test    rax, rax
0x14004e9e3  jz      short loc_14004EA4E
0x14004e9e5  movzx   r8d, [rbp+var_20]
0x14004e9ea  lea     rdx, [rbp+DestinationString]
0x14004e9ee  mov     rcx, rax
0x14004e9f1  call    ??0UfsPathName@UnionFs@@AEAA@$$QEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@G@Z; UnionFs::UfsPathName::UfsPathName(wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &&,ushort)
0x14004e9f6  mov     rdi, rax
0x14004e9f9  test    rax, rax
0x14004e9fc  jz      short loc_14004EA4E
0x14004e9fe  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14004ea02  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004ea07  mov     r9d, [rbp+arg_20]
0x14004ea0b  mov     r8, rdi
0x14004ea0e  mov     rdx, r14
0x14004ea11  mov     [rsp+50h+var_28], rsi
0x14004ea16  mov     rcx, r12
0x14004ea19  mov     [rsp+50h+var_30], r15
0x14004ea1e  call    ?Traverse@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4TraverseFlags@2@AEBV?$function@$$A6AJAEAVUfsPathTierNode@UnionFs@@PEAV12@AEAUUFS_TABLE_TRAVERSE_CTX@2@@Z@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathTable::Traverse(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::TraverseFlags,wistd::function<long (UnionFs::UfsPathTierNode &,UnionFs::UfsPathTierNode *,UnionFs::UFS_TABLE_TRAVERSE_CTX &)> const &,UnionFs::StackEventTracer &)
0x14004ea23  cmp     byte ptr [rdi+10h], 0
0x14004ea27  mov     ebx, eax
0x14004ea29  jnz     short loc_14004EA31
0x14004ea2b  xorps   xmm0, xmm0
0x14004ea2e  movups  xmmword ptr [rdi], xmm0
0x14004ea31  mov     rcx, rdi; UnicodeString
0x14004ea34  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004ea39  xor     edx, edx; Tag
0x14004ea3b  mov     rcx, rdi; P
0x14004ea3e  call    cs:__imp_ExFreePoolWithTag
0x14004ea45  nop     dword ptr [rax+rax+00h]
0x14004ea4a  mov     eax, ebx
0x14004ea4c  jmp     short loc_14004EAAC
0x14004ea4e  lea     rax, aOriginAllocati_45; "ORIGIN: Allocating UfsPathName"
0x14004ea55  mov     r8, 5CC00130084h; struct UnionFs::StackEventTracer *
0x14004ea5f  mov     edi, 0C000009Ah
0x14004ea64  mov     [rsp+50h+var_30], rax; char *
0x14004ea69  mov     ecx, edi; this
0x14004ea6b  lea     r9, aUnionfsUfspath_42; "UnionFs::UfsPathName::AllocAndInit"
0x14004ea72  mov     rdx, rsi; int
0x14004ea75  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004ea7a  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14004ea7e  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004ea83  lea     rax, aPushAllocating_1; "PUSH: Allocating rootPath"
0x14004ea8a  mov     r8, 45900140B08h; struct UnionFs::StackEventTracer *
0x14004ea94  lea     r9, aUnionfsUfspath_63; "UnionFs::UfsPathTable::Traverse"
0x14004ea9b  mov     [rsp+50h+var_30], rax; char *
0x14004eaa0  mov     rdx, rsi; int
0x14004eaa3  mov     ecx, edi; this
0x14004eaa5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004eaaa  mov     eax, edi
0x14004eaac  add     rsp, 50h
0x14004eab0  pop     r15
0x14004eab2  pop     r14
0x14004eab4  pop     r12
0x14004eab6  pop     rdi
0x14004eab7  pop     rsi
0x14004eab8  pop     rbx
0x14004eab9  pop     rbp
0x14004eaba  retn
```
