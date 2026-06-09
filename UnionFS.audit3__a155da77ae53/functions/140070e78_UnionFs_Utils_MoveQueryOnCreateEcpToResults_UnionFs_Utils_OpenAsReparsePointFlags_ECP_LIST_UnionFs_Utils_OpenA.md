# UnionFs::Utils::MoveQueryOnCreateEcpToResults(UnionFs::Utils::OpenAsReparsePointFlags,_ECP_LIST &,UnionFs::Utils::OpenAsReparsePointResults &,UnionFs::StackEventTracer &)

- ea: `0x140070e78`
- end: `0x14007100f`
- name: `?MoveQueryOnCreateEcpToResults@Utils@UnionFs@@YAJW4OpenAsReparsePointFlags@12@AEAU_ECP_LIST@@AEAUOpenAsReparsePointResults@12@AEAVStackEventTracer@2@@Z`
- size: `407`
- prototype: `int __high(enum UnionFs::Utils::OpenAsReparsePointFlags, struct _ECP_LIST *, struct UnionFs::Utils::OpenAsReparsePointResults *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting, installer_update`

## callers

- `0x140072df8`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140070e78`

## import_xrefs

- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140070ec9`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140070ec9`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070efa`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070f44`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070fc7`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070ff5`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070efa`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070f44`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070fc7`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x140070ff5`

## string_xrefs

- `0x140070f1b`: `UnionFs::Utils::MoveQueryOnCreateEcpToResults`
- `0x140070f9b`: `UnionFs::Utils::MoveQueryOnCreateEcpToResults`
- `0x140070f0a`: `API: Removing QUERY_ON_CREATE ECP`
- `0x140070f8a`: `ORIGIN: QUERY_ON_CREATE error: FileEaInformation`
- `0x140070f69`: `ORIGIN: QUERY_ON_CREATE error: FileStatInformation`

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
      (struct UnionFs::StackEventTracer *)0x3660021210BLL,
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
    v11 = 0x3670021211DLL;
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
    v11 = 0x36800212127LL;
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
0x140070e78  push    rbp
0x140070e7a  push    rbx
0x140070e7b  push    rsi
0x140070e7c  push    rdi
0x140070e7d  push    r14
0x140070e7f  mov     rbp, rsp
0x140070e82  sub     rsp, 50h
0x140070e86  mov     r14d, ecx
0x140070e89  mov     [rbp+var_20], 0
0x140070e91  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070e98  lea     rax, [rbp+var_20]
0x140070e9c  mov     rdi, r9
0x140070e9f  mov     [rbp+var_18], rax
0x140070ea3  mov     rsi, r8
0x140070ea6  mov     [rbp+EcpContext], 0
0x140070eae  lea     r9, [rbp+EcpContext]; EcpContext
0x140070eb2  mov     [rbp+var_8], 1
0x140070eb6  mov     rcx, [rcx]; Filter
0x140070eb9  lea     r8, GUID_ECP_QUERY_ON_CREATE; EcpType
0x140070ec0  mov     [rsp+50h+EcpContextSize], 0; EcpContextSize
0x140070ec9  call    cs:__imp_FltRemoveExtraCreateParameter
0x140070ed0  nop     dword ptr [rax+rax+00h]
0x140070ed5  cmp     [rbp+var_8], 0
0x140070ed9  mov     ebx, eax
0x140070edb  jz      short loc_140070F06
0x140070edd  mov     r8, [rbp+var_18]
0x140070ee1  mov     rcx, [rbp+EcpContext]
0x140070ee5  mov     rdx, [r8]; EcpContext
0x140070ee8  mov     [r8], rcx
0x140070eeb  test    rdx, rdx
0x140070eee  jz      short loc_140070F06
0x140070ef0  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070ef7  mov     rcx, [rcx]; Filter
0x140070efa  call    cs:__imp_FltFreeExtraCreateParameter
0x140070f01  nop     dword ptr [rax+rax+00h]
0x140070f06  test    ebx, ebx
0x140070f08  jns     short loc_140070F57
0x140070f0a  lea     rax, aApiRemovingQue; "API: Removing QUERY_ON_CREATE ECP"
0x140070f11  mov     r8, 3660021210Bh; struct UnionFs::StackEventTracer *
0x140070f1b  lea     r9, aUnionfsUtilsMo; "UnionFs::Utils::MoveQueryOnCreateEcpToR"...
0x140070f22  mov     [rsp+50h+EcpContextSize], rax; char *
0x140070f27  mov     rdx, rdi; int
0x140070f2a  mov     ecx, ebx; this
0x140070f2c  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070f31  mov     rdx, [rbp+var_20]; EcpContext
0x140070f35  test    rdx, rdx
0x140070f38  jz      short loc_140070F50
0x140070f3a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070f41  mov     rcx, [rcx]; Filter
0x140070f44  call    cs:__imp_FltFreeExtraCreateParameter
0x140070f4b  nop     dword ptr [rax+rax+00h]
0x140070f50  mov     eax, ebx
0x140070f52  jmp     loc_140071003
0x140070f57  mov     rax, [rbp+var_20]
0x140070f5b  test    r14b, 2
0x140070f5f  jz      short loc_140070F7C
0x140070f61  mov     ecx, [rax+8]
0x140070f64  test    cl, 1
0x140070f67  jz      short loc_140070F7C
0x140070f69  lea     rax, aOriginQueryOnC; "ORIGIN: QUERY_ON_CREATE error: FileStat"...
0x140070f70  mov     r8, 3670021211Dh
0x140070f7a  jmp     short loc_140070F9B
0x140070f7c  test    r14b, 4
0x140070f80  jz      short loc_140070FDA
0x140070f82  mov     ecx, [rax+8]
0x140070f85  test    cl, 4
0x140070f88  jz      short loc_140070FDA
0x140070f8a  lea     rax, aOriginQueryOnC_0; "ORIGIN: QUERY_ON_CREATE error: FileEaIn"...
0x140070f91  mov     r8, 36800212127h; struct UnionFs::StackEventTracer *
0x140070f9b  lea     r9, aUnionfsUtilsMo; "UnionFs::Utils::MoveQueryOnCreateEcpToR"...
0x140070fa2  mov     [rsp+50h+EcpContextSize], rax; char *
0x140070fa7  mov     rdx, rdi; int
0x140070faa  mov     ecx, 0C0000001h; this
0x140070faf  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070fb4  mov     rdx, [rbp+var_20]; EcpContext
0x140070fb8  test    rdx, rdx
0x140070fbb  jz      short loc_140070FD3
0x140070fbd  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070fc4  mov     rcx, [rcx]; Filter
0x140070fc7  call    cs:__imp_FltFreeExtraCreateParameter
0x140070fce  nop     dword ptr [rax+rax+00h]
0x140070fd3  mov     eax, 0C0000001h
0x140070fd8  jmp     short loc_140071003
0x140070fda  mov     rdx, [rsi+10h]; EcpContext
0x140070fde  mov     [rsi+10h], rax
0x140070fe2  mov     [rbp+var_20], rdx
0x140070fe6  test    rdx, rdx
0x140070fe9  jz      short loc_140071001
0x140070feb  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140070ff2  mov     rcx, [rcx]; Filter
0x140070ff5  call    cs:__imp_FltFreeExtraCreateParameter
0x140070ffc  nop     dword ptr [rax+rax+00h]
0x140071001  xor     eax, eax
0x140071003  add     rsp, 50h
0x140071007  pop     r14
0x140071009  pop     rdi
0x14007100a  pop     rsi
0x14007100b  pop     rbx
0x14007100c  pop     rbp
0x14007100d  retn
```
