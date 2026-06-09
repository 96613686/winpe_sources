# AppxAllUserStore::Internal::MoveDeletedAllUserPackages(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)

- ea: `0x180033908`
- end: `0x180033bae`
- name: `?MoveDeletedAllUserPackages@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z`
- size: `678`
- prototype: `__int64 __fastcall(AppxAllUserStore::BasicLogFile *this, const unsigned __int16 *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180033dcc`

## callees

- `0x180004920`
- `0x18000ed34`
- `0x180017cd0`
- `0x180017f50`
- `0x18001a6a0`
- `0x180033908`
- `0x18004682c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a1a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180033a04`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180033a04`

## string_xrefs

- `0x18003393d`: `In MoveDeletedAllUserPackages %ls %ls %u.`
- `0x180033a30`: `MoveFileEx %ls to %ls`
- `0x180033ace`: `Moved %u packages, 1st error: 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::MoveDeletedAllUserPackages(
        AppxAllUserStore::BasicLogFile *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  const unsigned __int16 *v5; // r14
  int v7; // eax
  unsigned __int64 v8; // rax
  int v9; // r15d
  __int64 v10; // r12
  unsigned __int64 i; // rbx
  __int64 v12; // rsi
  const unsigned __int16 *v13; // rdx
  int v14; // r14d
  const unsigned __int16 *v15; // rdx
  BOOL v16; // eax
  LPCWSTR v17; // rsi
  const char *v18; // r14
  signed int LastError; // eax
  int v20; // esi
  int v21; // eax
  int v22; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // [rsp+20h] [rbp-50h]
  int v27; // [rsp+20h] [rbp-50h]
  char *v28; // [rsp+28h] [rbp-48h]
  LPCWSTR lpNewFileName[2]; // [rsp+40h] [rbp-30h] BYREF
  int v30; // [rsp+50h] [rbp-20h]
  LPCWSTR lpExistingFileName[2]; // [rsp+58h] [rbp-18h] BYREF
  int v32; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v26 = *(_DWORD *)(a4 + 16);
  v5 = a2;
  v7 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In MoveDeletedAllUserPackages %ls %ls %u.", a2, a3);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x850,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v7,
      v26);
  v8 = *(_QWORD *)(a4 + 16);
  if ( !v8 )
    return 0;
  v9 = 0;
  v10 = 0;
  for ( i = 0; i < v8; ++i )
  {
    v12 = 8 * i;
    v32 = 0;
    *(_OWORD *)lpExistingFileName = 0;
    if ( i < v8 )
      v13 = *(const unsigned __int16 **)(v12 + *(_QWORD *)a4);
    else
      v13 = 0;
    v14 = Common::PathHelpers::CombinePaths(v5, v13, (struct Common::StringBuffer *)lpExistingFileName);
    if ( v14 < 0 )
    {
      if ( i < *(_QWORD *)(a4 + 16) )
        v25 = *(_QWORD *)(v12 + *(_QWORD *)a4);
      else
        v25 = 0;
      LODWORD(v28) = i;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x85C,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v14,
        (int)"The %u is %ls.",
        v28,
        v25);
      goto LABEL_33;
    }
    *(_OWORD *)lpNewFileName = 0;
    v30 = 0;
    if ( i < *(_QWORD *)(a4 + 16) )
      v15 = *(const unsigned __int16 **)(v12 + *(_QWORD *)a4);
    else
      v15 = 0;
    v14 = Common::PathHelpers::CombinePaths(a3, v15, (struct Common::StringBuffer *)lpNewFileName);
    if ( v14 < 0 )
    {
      if ( i < *(_QWORD *)(a4 + 16) )
        v24 = *(_QWORD *)(v12 + *(_QWORD *)a4);
      else
        v24 = 0;
      LODWORD(v28) = i;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x861,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v14,
        (int)"The %u is %ls.",
        v28,
        v24);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpNewFileName);
LABEL_33:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
      return (unsigned int)v14;
    }
    v16 = MoveFileExW(lpExistingFileName[1], lpNewFileName[1], 0xAu);
    v17 = lpNewFileName[1];
    v18 = (const char *)lpExistingFileName[1];
    if ( v16 )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v20 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x86B,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)LastError,
            (__int64)"MoveFileEx %ls to %ls",
            v18,
            v17);
    v27 = v20;
    v21 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"Moving %ls to %ls yielded 0x%0x.",
            lpExistingFileName[1],
            lpNewFileName[1]);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x86E,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v21,
        v20);
    if ( v9 >= 0 )
      v9 = v20;
    v10 += (unsigned __int64)(unsigned int)~v20 >> 31;
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpNewFileName);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
    v8 = *(_QWORD *)(a4 + 16);
    v5 = a2;
  }
  v22 = AppxAllUserStore::BasicLogFile::WriteMsg(
          this,
          L"Moved %u packages, 1st error: 0x%0x.",
          (unsigned int)v10,
          (unsigned int)v9);
  if ( v22 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x875,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v22,
      v27);
  return 0;
}

```

## disassembly

```asm
0x180033908  mov     [rsp-38h+arg_0], rbx
0x18003390d  mov     [rsp-38h+Src], r8
0x180033912  mov     [rsp-38h+arg_8], rdx
0x180033917  push    rbp
0x180033918  push    rsi
0x180033919  push    rdi
0x18003391a  push    r12
0x18003391c  push    r13
0x18003391e  push    r14
0x180033920  push    r15
0x180033922  mov     rbp, rsp
0x180033925  sub     rsp, 70h
0x180033929  mov     eax, [r9+10h]
0x18003392d  mov     rdi, r9
0x180033930  mov     r9, r8
0x180033933  mov     dword ptr [rsp+70h+var_50], eax; int
0x180033937  mov     r8, rdx
0x18003393a  mov     r14, rdx
0x18003393d  lea     rdx, aInMovedeleteda; "In MoveDeletedAllUserPackages %ls %ls %"...
0x180033944  mov     r13, rcx
0x180033947  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18003394c  test    eax, eax
0x18003394e  jns     short loc_180033968
0x180033950  mov     rcx, [rbp+38h]; this
0x180033954  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003395b  mov     r9d, eax; char *
0x18003395e  mov     edx, 850h; void *
0x180033963  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033968  mov     rax, [rdi+10h]
0x18003396c  test    rax, rax
0x18003396f  jz      loc_180033AFC
0x180033975  xor     r15d, r15d
0x180033978  xor     r12d, r12d
0x18003397b  test    rax, rax
0x18003397e  jz      loc_180033ACB
0x180033984  xor     ebx, ebx
0x180033986  xor     ecx, ecx
0x180033988  lea     rsi, ds:0[rbx*8]
0x180033990  mov     [rbp+var_8], ecx
0x180033993  xorps   xmm0, xmm0
0x180033996  movups  xmmword ptr [rbp+lpExistingFileName], xmm0
0x18003399a  cmp     rbx, rax
0x18003399d  jb      short loc_1800339A3
0x18003399f  xor     edx, edx
0x1800339a1  jmp     short loc_1800339AA
0x1800339a3  mov     rax, [rdi]
0x1800339a6  mov     rdx, [rsi+rax]; unsigned __int16 *
0x1800339aa  lea     r8, [rbp+lpExistingFileName]; this
0x1800339ae  mov     rcx, r14; Src
0x1800339b1  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x1800339b6  mov     r14d, eax
0x1800339b9  test    eax, eax
0x1800339bb  js      loc_180033B5F
0x1800339c1  xor     eax, eax
0x1800339c3  xorps   xmm0, xmm0
0x1800339c6  movups  xmmword ptr [rbp+lpNewFileName], xmm0
0x1800339ca  mov     [rbp+var_20], eax
0x1800339cd  cmp     rbx, [rdi+10h]
0x1800339d1  jb      short loc_1800339D7
0x1800339d3  xor     edx, edx
0x1800339d5  jmp     short loc_1800339DE
0x1800339d7  mov     rax, [rdi]
0x1800339da  mov     rdx, [rsi+rax]; unsigned __int16 *
0x1800339de  mov     rcx, [rbp+Src]; Src
0x1800339e2  lea     r8, [rbp+lpNewFileName]; this
0x1800339e6  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x1800339eb  mov     r14d, eax
0x1800339ee  test    eax, eax
0x1800339f0  js      loc_180033B16
0x1800339f6  mov     rdx, [rbp+lpNewFileName+8]; lpNewFileName
0x1800339fa  mov     r8d, 0Ah; dwFlags
0x180033a00  mov     rcx, [rbp+lpExistingFileName+8]; lpExistingFileName
0x180033a04  call    cs:__imp_MoveFileExW
0x180033a0a  mov     rsi, [rbp+lpNewFileName+8]
0x180033a0e  mov     r14, [rbp+lpExistingFileName+8]
0x180033a12  test    eax, eax
0x180033a14  jz      short loc_180033A1A
0x180033a16  xor     eax, eax
0x180033a18  jmp     short loc_180033A2C
0x180033a1a  call    cs:__imp_GetLastError
0x180033a20  test    eax, eax
0x180033a22  jle     short loc_180033A2C
0x180033a24  movzx   eax, ax
0x180033a27  or      eax, 80070000h
0x180033a2c  mov     rcx, [rbp+38h]; this
0x180033a30  lea     rdx, aMovefileexLsTo; "MoveFileEx %ls to %ls"
0x180033a37  mov     [rsp+70h+var_40], rsi
0x180033a3c  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033a43  mov     [rsp+70h+var_48], r14; char *
0x180033a48  mov     r9d, eax; char *
0x180033a4b  mov     [rsp+70h+var_50], rdx; __int64
0x180033a50  mov     edx, 86Bh; void *
0x180033a55  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033a5a  mov     r9, [rbp+lpNewFileName+8]
0x180033a5e  lea     rdx, aMovingLsToLsYi; "Moving %ls to %ls yielded 0x%0x."
0x180033a65  mov     r8, [rbp+lpExistingFileName+8]
0x180033a69  mov     rcx, r13; this
0x180033a6c  mov     esi, eax
0x180033a6e  mov     dword ptr [rsp+70h+var_50], eax; int
0x180033a72  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180033a77  test    eax, eax
0x180033a79  jns     short loc_180033A93
0x180033a7b  mov     rcx, [rbp+38h]; this
0x180033a7f  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033a86  mov     r9d, eax; char *
0x180033a89  mov     edx, 86Eh; void *
0x180033a8e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033a93  test    r15d, r15d
0x180033a96  lea     rcx, [rbp+lpNewFileName]; this
0x180033a9a  cmovns  r15d, esi
0x180033a9e  not     esi
0x180033aa0  mov     eax, esi
0x180033aa2  shr     rax, 1Fh
0x180033aa6  add     r12, rax
0x180033aa9  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180033aae  lea     rcx, [rbp+lpExistingFileName]; this
0x180033ab2  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180033ab7  mov     rax, [rdi+10h]
0x180033abb  inc     rbx
0x180033abe  mov     r14, [rbp+arg_8]
0x180033ac2  cmp     rbx, rax
0x180033ac5  jb      loc_180033986
0x180033acb  mov     r8d, r12d
0x180033ace  lea     rdx, aMovedUPackages; "Moved %u packages, 1st error: 0x%0x."
0x180033ad5  mov     r9d, r15d
0x180033ad8  mov     rcx, r13; this
0x180033adb  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180033ae0  test    eax, eax
0x180033ae2  jns     short loc_180033AFC
0x180033ae4  mov     rcx, [rbp+38h]; this
0x180033ae8  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033aef  mov     r9d, eax; char *
0x180033af2  mov     edx, 875h; void *
0x180033af7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033afc  xor     eax, eax
0x180033afe  mov     rbx, [rsp+70h+arg_0]
0x180033b06  add     rsp, 70h
0x180033b0a  pop     r15
0x180033b0c  pop     r14
0x180033b0e  pop     r13
0x180033b10  pop     r12
0x180033b12  pop     rdi
0x180033b13  pop     rsi
0x180033b14  pop     rbp
0x180033b15  retn
0x180033b16  cmp     rbx, [rdi+10h]
0x180033b1a  jb      short loc_180033B20
0x180033b1c  xor     eax, eax
0x180033b1e  jmp     short loc_180033B27
0x180033b20  mov     rax, [rdi]
0x180033b23  mov     rax, [rsi+rax]
0x180033b27  mov     rcx, [rbp+38h]; this
0x180033b2b  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033b32  mov     [rsp+70h+var_40], rax
0x180033b37  mov     r9d, r14d; char *
0x180033b3a  lea     rax, aTheUIsLs; "The %u is %ls."
0x180033b41  mov     dword ptr [rsp+70h+var_48], ebx; char *
0x180033b45  mov     edx, 861h; void *
0x180033b4a  mov     [rsp+70h+var_50], rax; int
0x180033b4f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033b54  lea     rcx, [rbp+lpNewFileName]; this
0x180033b58  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180033b5d  jmp     short loc_180033B9D
0x180033b5f  cmp     rbx, [rdi+10h]
0x180033b63  jb      short loc_180033B69
0x180033b65  xor     eax, eax
0x180033b67  jmp     short loc_180033B70
0x180033b69  mov     rax, [rdi]
0x180033b6c  mov     rax, [rsi+rax]
0x180033b70  mov     rcx, [rbp+38h]; this
0x180033b74  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033b7b  mov     [rsp+70h+var_40], rax
0x180033b80  mov     r9d, r14d; char *
0x180033b83  lea     rax, aTheUIsLs; "The %u is %ls."
0x180033b8a  mov     dword ptr [rsp+70h+var_48], ebx; char *
0x180033b8e  mov     edx, 85Ch; void *
0x180033b93  mov     [rsp+70h+var_50], rax; int
0x180033b98  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033b9d  lea     rcx, [rbp+lpExistingFileName]; this
0x180033ba1  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180033ba6  mov     eax, r14d
0x180033ba9  jmp     loc_180033AFE
```
