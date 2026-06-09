# UnionFs::UfsPathTable::Traverse(_FLT_INSTANCE const &,wistd::function<long (UnionFs::UfsPathTierNode &,UnionFs::UfsPathTierNode *,UnionFs::UFS_TABLE_TRAVERSE_CTX &)> const &,UnionFs::StackEventTracer &,UnionFs::TraverseFlags)

- ea: `0x14004e794`
- end: `0x14004e93c`
- name: `?Traverse@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBV?$function@$$A6AJAEAVUfsPathTierNode@UnionFs@@PEAV12@AEAUUFS_TABLE_TRAVERSE_CTX@2@@Z@wistd@@AEAVStackEventTracer@2@W4TraverseFlags@2@@Z`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1400480c4`

## callees

- `0x140043858`
- `0x14004e794`
- `0x14004e944`
- `0x140056ac4`
- `0x140056afc`
- `0x140075254`
- `0x140079c48`
- `0x140079d0c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004e8be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e8be`
- `ntoskrnl!ExAllocatePool2` at `0x14004e854`
- `ntoskrnl!ExAllocatePool2` at `0x14004e854`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004e7ed`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14004e7ed`

## string_xrefs

- `0x14004e829`: `UnionFs::UfsPathName::AllocAndInit`
- `0x14004e8eb`: `UnionFs::UfsPathName::AllocAndInit`
- `0x14004e7cc`: `ORIGIN: Allocating path string`
- `0x14004e8ce`: `ORIGIN: Allocating UfsPathName`
- `0x14004e903`: `PUSH: Allocating rootPath`
- `0x14004e914`: `UnionFs::UfsPathTable::Traverse`

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
0x14004e794  push    rbp
0x14004e796  push    rbx
0x14004e797  push    rsi
0x14004e798  push    rdi
0x14004e799  push    r12
0x14004e79b  push    r14
0x14004e79d  push    r15
0x14004e79f  mov     rbp, rsp
0x14004e7a2  sub     rsp, 50h
0x14004e7a6  mov     r15, r8
0x14004e7a9  mov     r14, rdx
0x14004e7ac  mov     r12, rcx
0x14004e7af  xor     ebx, ebx
0x14004e7b1  mov     r8d, 616E4655h
0x14004e7b7  lea     rcx, [rbp+DestinationString]
0x14004e7bb  mov     rsi, r9
0x14004e7be  lea     edx, [rbx+34h]
0x14004e7c1  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14004e7c6  cmp     [rbp+DestinationString.Buffer], rbx
0x14004e7ca  jnz     short loc_14004E7E2
0x14004e7cc  lea     rax, aOriginAllocati_50; "ORIGIN: Allocating path string"
0x14004e7d3  mov     r8, 5AC00130070h
0x14004e7dd  jmp     loc_14004E8DF
0x14004e7e2  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; SourceString
0x14004e7e9  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004e7ed  call    cs:__imp_RtlCopyUnicodeString
0x14004e7f4  nop     dword ptr [rax+rax+00h]
0x14004e7f9  xor     eax, eax
0x14004e7fb  lea     r9, [rbp+var_20]
0x14004e7ff  mov     r8, rsi
0x14004e802  mov     [rbp+var_20], ax
0x14004e806  lea     rdx, [rbp+DestinationString]
0x14004e80a  mov     rcx, r14
0x14004e80d  call    ?PrependVolumeNameFromInstance@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@PEAG@Z; UnionFs::Utils::PrependVolumeNameFromInstance(_FLT_INSTANCE const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,ushort *)
0x14004e812  mov     edi, eax
0x14004e814  test    eax, eax
0x14004e816  jns     short loc_14004E844
0x14004e818  lea     rax, aPushPrepending_0; "PUSH: Prepending volume name"
0x14004e81f  mov     r8, 5BE0013007Ah; struct UnionFs::StackEventTracer *
0x14004e829  lea     r9, aUnionfsUfspath_43; "UnionFs::UfsPathName::AllocAndInit"
0x14004e830  mov     [rsp+50h+var_30], rax; char *
0x14004e835  mov     rdx, rsi; int
0x14004e838  mov     ecx, edi; this
0x14004e83a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004e83f  jmp     loc_14004E8FA
0x14004e844  mov     edx, 100h
0x14004e849  mov     ecx, 40h ; '@'
0x14004e84e  mov     r8d, 616E4655h
0x14004e854  call    cs:__imp_ExAllocatePool2
0x14004e85b  nop     dword ptr [rax+rax+00h]
0x14004e860  test    rax, rax
0x14004e863  jz      short loc_14004E8CE
0x14004e865  movzx   r8d, [rbp+var_20]
0x14004e86a  lea     rdx, [rbp+DestinationString]
0x14004e86e  mov     rcx, rax
0x14004e871  call    ??0UfsPathName@UnionFs@@AEAA@$$QEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@G@Z; UnionFs::UfsPathName::UfsPathName(wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &&,ushort)
0x14004e876  mov     rdi, rax
0x14004e879  test    rax, rax
0x14004e87c  jz      short loc_14004E8CE
0x14004e87e  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14004e882  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004e887  mov     r9d, [rbp+arg_20]
0x14004e88b  mov     r8, rdi
0x14004e88e  mov     rdx, r14
0x14004e891  mov     [rsp+50h+var_28], rsi
0x14004e896  mov     rcx, r12
0x14004e899  mov     [rsp+50h+var_30], r15
0x14004e89e  call    ?Traverse@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4TraverseFlags@2@AEBV?$function@$$A6AJAEAVUfsPathTierNode@UnionFs@@PEAV12@AEAUUFS_TABLE_TRAVERSE_CTX@2@@Z@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathTable::Traverse(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::TraverseFlags,wistd::function<long (UnionFs::UfsPathTierNode &,UnionFs::UfsPathTierNode *,UnionFs::UFS_TABLE_TRAVERSE_CTX &)> const &,UnionFs::StackEventTracer &)
0x14004e8a3  cmp     byte ptr [rdi+10h], 0
0x14004e8a7  mov     ebx, eax
0x14004e8a9  jnz     short loc_14004E8B1
0x14004e8ab  xorps   xmm0, xmm0
0x14004e8ae  movups  xmmword ptr [rdi], xmm0
0x14004e8b1  mov     rcx, rdi; UnicodeString
0x14004e8b4  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004e8b9  xor     edx, edx; Tag
0x14004e8bb  mov     rcx, rdi; P
0x14004e8be  call    cs:__imp_ExFreePoolWithTag
0x14004e8c5  nop     dword ptr [rax+rax+00h]
0x14004e8ca  mov     eax, ebx
0x14004e8cc  jmp     short loc_14004E92C
0x14004e8ce  lea     rax, aOriginAllocati_44; "ORIGIN: Allocating UfsPathName"
0x14004e8d5  mov     r8, 5CC00130084h; struct UnionFs::StackEventTracer *
0x14004e8df  mov     edi, 0C000009Ah
0x14004e8e4  mov     [rsp+50h+var_30], rax; char *
0x14004e8e9  mov     ecx, edi; this
0x14004e8eb  lea     r9, aUnionfsUfspath_43; "UnionFs::UfsPathName::AllocAndInit"
0x14004e8f2  mov     rdx, rsi; int
0x14004e8f5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004e8fa  lea     rcx, [rbp+DestinationString]; UnicodeString
0x14004e8fe  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004e903  lea     rax, aPushAllocating_1; "PUSH: Allocating rootPath"
0x14004e90a  mov     r8, 45900140B08h; struct UnionFs::StackEventTracer *
0x14004e914  lea     r9, aUnionfsUfspath_63; "UnionFs::UfsPathTable::Traverse"
0x14004e91b  mov     [rsp+50h+var_30], rax; char *
0x14004e920  mov     rdx, rsi; int
0x14004e923  mov     ecx, edi; this
0x14004e925  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004e92a  mov     eax, edi
0x14004e92c  add     rsp, 50h
0x14004e930  pop     r15
0x14004e932  pop     r14
0x14004e934  pop     r12
0x14004e936  pop     rdi
0x14004e937  pop     rsi
0x14004e938  pop     rbx
0x14004e939  pop     rbp
0x14004e93a  retn
```
