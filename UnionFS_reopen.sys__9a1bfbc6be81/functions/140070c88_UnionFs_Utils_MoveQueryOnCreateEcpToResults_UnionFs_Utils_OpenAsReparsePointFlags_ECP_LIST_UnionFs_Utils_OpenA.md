# UnionFs::Utils::MoveQueryOnCreateEcpToResults(UnionFs::Utils::OpenAsReparsePointFlags,_ECP_LIST &,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &)

- ea: `0x140070c88`
- end: `0x140070e1f`
- name: `?MoveQueryOnCreateEcpToResults@Utils@UnionFs@@YAJW4OpenAsReparsePointFlags@12@AEAU_ECP_LIST@@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@@Z`
- size: `407`
- prototype: `int __high(enum UnionFs::Utils::OpenAsReparsePointFlags, struct _ECP_LIST *, struct UnionFs::Utils::OpenAsReparsePointResults *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, installer_update`

## callers

- `0x140072c08`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140070c88`

## import_xrefs

- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140070cd9`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140070cd9`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070d0a`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070d54`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070dd7`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070e05`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070d0a`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070d54`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070dd7`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070e05`

## string_xrefs

- `0x140070d2b`: `UnionFs::Utils::MoveQueryOnCreateEcpToResults`
- `0x140070dab`: `UnionFs::Utils::MoveQueryOnCreateEcpToResults`
- `0x140070d1a`: `API: Removing QUERY_ON_CREATE ECP`
- `0x140070d9a`: `ORIGIN: QUERY_ON_CREATE error: FileEaInformation`
- `0x140070d79`: `ORIGIN: QUERY_ON_CREATE error: FileStatInformation`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::MoveQueryOnCreateEcpToResults(char a1, struct _ECP_LIST *a2, __int64 a3, int a4)
{
  NTSTATUS v7; // ebx
  PVOID v8; // rdx
  const char *v10; // rax
  __int64 v11; // r8
  void *v12; // rdx
  const char *v13; // [rsp+28h] [rbp-28h]
  PVOID v14; // [rsp+30h] [rbp-20h] BYREF
  PVOID *v15; // [rsp+38h] [rbp-18h]
  PVOID EcpContext; // [rsp+40h] [rbp-10h] BYREF
  char v17; // [rsp+48h] [rbp-8h]

  v14 = 0;
  v15 = &v14;
  EcpContext = 0;
  v17 = 1;
  v7 = FltRemoveExtraCreateParameter(
         *(PFLT_FILTER *)UnionFs::g_FilterState,
         a2,
         &GUID_ECP_QUERY_ON_CREATE,
         &EcpContext,
         0);
  if ( v17 )
  {
    v8 = *v15;
    *v15 = EcpContext;
    if ( v8 )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v8);
  }
  if ( v7 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v7,
      a4,
      (struct UnionFs::StackEventTracer *)0x366002120D5LL,
      (unsigned __int64)"UnionFs::Utils::MoveQueryOnCreateEcpToResults",
      "API: Removing QUERY_ON_CREATE ECP",
      v13);
    if ( v14 )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v14);
    return (unsigned int)v7;
  }
  if ( (a1 & 2) != 0 && (*((_DWORD *)v14 + 2) & 1) != 0 )
  {
    v10 = "ORIGIN: QUERY_ON_CREATE error: FileStatInformation";
    v11 = 0x367002120E7LL;
LABEL_14:
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000001LL,
      a4,
      (struct UnionFs::StackEventTracer *)v11,
      (unsigned __int64)"UnionFs::Utils::MoveQueryOnCreateEcpToResults",
      v10,
      v13);
    if ( v14 )
      FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v14);
    return 3221225473LL;
  }
  if ( (a1 & 4) != 0 && (*((_DWORD *)v14 + 2) & 4) != 0 )
  {
    v10 = "ORIGIN: QUERY_ON_CREATE error: FileEaInformation";
    v11 = 0x368002120F1LL;
    goto LABEL_14;
  }
  v12 = *(void **)(a3 + 16);
  *(_QWORD *)(a3 + 16) = v14;
  v14 = v12;
  if ( v12 )
    FltFreeExtraCreateParameter(*(PFLT_FILTER *)UnionFs::g_FilterState, v12);
  return 0;
}

```

## disassembly

```asm
0x140070c88  push    rbp
0x140070c8a  push    rbx
0x140070c8b  push    rsi
0x140070c8c  push    rdi
0x140070c8d  push    r14
0x140070c8f  mov     rbp, rsp
0x140070c92  sub     rsp, 50h
0x140070c96  mov     r14d, ecx
0x140070c99  mov     [rbp+var_20], 0
0x140070ca1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070ca8  lea     rax, [rbp+var_20]
0x140070cac  mov     rdi, r9
0x140070caf  mov     [rbp+var_18], rax
0x140070cb3  mov     rsi, r8
0x140070cb6  mov     [rbp+EcpContext], 0
0x140070cbe  lea     r9, [rbp+EcpContext]; EcpContext
0x140070cc2  mov     [rbp+var_8], 1
0x140070cc6  mov     rcx, [rcx]; Filter
0x140070cc9  lea     r8, GUID_ECP_QUERY_ON_CREATE; EcpType
0x140070cd0  mov     [rsp+50h+EcpContextSize], 0; EcpContextSize
0x140070cd9  call    cs:__imp_FltRemoveExtraCreateParameter
0x140070ce0  nop     dword ptr [rax+rax+00h]
0x140070ce5  cmp     [rbp+var_8], 0
0x140070ce9  mov     ebx, eax
0x140070ceb  jz      short loc_140070D16
0x140070ced  mov     r8, [rbp+var_18]
0x140070cf1  mov     rcx, [rbp+EcpContext]
0x140070cf5  mov     rdx, [r8]; EcpContext
0x140070cf8  mov     [r8], rcx
0x140070cfb  test    rdx, rdx
0x140070cfe  jz      short loc_140070D16
0x140070d00  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070d07  mov     rcx, [rcx]; Filter
0x140070d0a  call    cs:__imp_FltFreeExtraCreateParameter
0x140070d11  nop     dword ptr [rax+rax+00h]
0x140070d16  test    ebx, ebx
0x140070d18  jns     short loc_140070D67
0x140070d1a  lea     rax, aApiRemovingQue; "API: Removing QUERY_ON_CREATE ECP"
0x140070d21  mov     r8, 366002120D5h; struct UnionFs::StackEventTracer *
0x140070d2b  lea     r9, aUnionfsUtilsMo; "UnionFs::Utils::MoveQueryOnCreateEcpToR"...
0x140070d32  mov     [rsp+50h+EcpContextSize], rax; char *
0x140070d37  mov     rdx, rdi; int
0x140070d3a  mov     ecx, ebx; this
0x140070d3c  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070d41  mov     rdx, [rbp+var_20]; EcpContext
0x140070d45  test    rdx, rdx
0x140070d48  jz      short loc_140070D60
0x140070d4a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070d51  mov     rcx, [rcx]; Filter
0x140070d54  call    cs:__imp_FltFreeExtraCreateParameter
0x140070d5b  nop     dword ptr [rax+rax+00h]
0x140070d60  mov     eax, ebx
0x140070d62  jmp     loc_140070E13
0x140070d67  mov     rax, [rbp+var_20]
0x140070d6b  test    r14b, 2
0x140070d6f  jz      short loc_140070D8C
0x140070d71  mov     ecx, [rax+8]
0x140070d74  test    cl, 1
0x140070d77  jz      short loc_140070D8C
0x140070d79  lea     rax, aOriginQueryOnC; "ORIGIN: QUERY_ON_CREATE error: FileStat"...
0x140070d80  mov     r8, 367002120E7h
0x140070d8a  jmp     short loc_140070DAB
0x140070d8c  test    r14b, 4
0x140070d90  jz      short loc_140070DEA
0x140070d92  mov     ecx, [rax+8]
0x140070d95  test    cl, 4
0x140070d98  jz      short loc_140070DEA
0x140070d9a  lea     rax, aOriginQueryOnC_0; "ORIGIN: QUERY_ON_CREATE error: FileEaIn"...
0x140070da1  mov     r8, 368002120F1h; struct UnionFs::StackEventTracer *
0x140070dab  lea     r9, aUnionfsUtilsMo; "UnionFs::Utils::MoveQueryOnCreateEcpToR"...
0x140070db2  mov     [rsp+50h+EcpContextSize], rax; char *
0x140070db7  mov     rdx, rdi; int
0x140070dba  mov     ecx, 0C0000001h; this
0x140070dbf  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070dc4  mov     rdx, [rbp+var_20]; EcpContext
0x140070dc8  test    rdx, rdx
0x140070dcb  jz      short loc_140070DE3
0x140070dcd  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070dd4  mov     rcx, [rcx]; Filter
0x140070dd7  call    cs:__imp_FltFreeExtraCreateParameter
0x140070dde  nop     dword ptr [rax+rax+00h]
0x140070de3  mov     eax, 0C0000001h
0x140070de8  jmp     short loc_140070E13
0x140070dea  mov     rdx, [rsi+10h]; EcpContext
0x140070dee  mov     [rsi+10h], rax
0x140070df2  mov     [rbp+var_20], rdx
0x140070df6  test    rdx, rdx
0x140070df9  jz      short loc_140070E11
0x140070dfb  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070e02  mov     rcx, [rcx]; Filter
0x140070e05  call    cs:__imp_FltFreeExtraCreateParameter
0x140070e0c  nop     dword ptr [rax+rax+00h]
0x140070e11  xor     eax, eax
0x140070e13  add     rsp, 50h
0x140070e17  pop     r14
0x140070e19  pop     rdi
0x140070e1a  pop     rsi
0x140070e1b  pop     rbx
0x140070e1c  pop     rbp
0x140070e1d  retn
```
