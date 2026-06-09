# AppxAllUserStore::Internal::ExpandEnvironmentInPath(AppxAllUserStore::BasicLogFile *,ushort const *,Common::StringBuffer &)

- ea: `0x1800421f4`
- end: `0x180042317`
- name: `?ExpandEnvironmentInPath@Internal@AppxAllUserStore@@YAJPEAVBasicLogFile@2@PEBGAEAVStringBuffer@Common@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *, Common::StringBuffer *, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180043b10`

## callees

- `0x1800092c0`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x180036498`
- `0x1800421f4`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180042246`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800422da`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180042246`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800422da`

## string_xrefs

- `0x180042257`: `Path %ws.`
- `0x180042219`: `In ExpandEnvironmentInPath %ws.`
- `0x1800422e9`: `Path %ws, len %u.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::ExpandEnvironmentInPath(
        AppxAllUserStore::Internal *this,
        const WCHAR *a2,
        LPWSTR *a3,
        struct Common::StringBuffer *a4)
{
  int v7; // eax
  DWORD v8; // eax
  DWORD v9; // edi
  int v11; // eax
  unsigned int v12; // ebp
  int v13; // eax
  int v14; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( this )
  {
    v7 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In ExpandEnvironmentInPath %ws.", a2, a4);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x416,
        (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
        (const char *)(unsigned int)v7);
  }
  v8 = ExpandEnvironmentStringsW(a2, 0, 0);
  v9 = v8;
  if ( !v8 )
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0x419,
             (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
             "Path %ws.",
             (const char *)a2);
  v11 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)a3, v8);
  v12 = v11;
  if ( v11 >= 0 )
  {
    if ( ExpandEnvironmentStringsW(a2, a3[1], v9) )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastErrorMsg(
               retaddr,
               (void *)0x41F,
               (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
               "Path %ws, len %u.",
               (const char *)a2,
               v9);
  }
  else
  {
    if ( this )
    {
      v13 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"SetCapacity %u failed, 0x%0x.", v9, (unsigned int)v11);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x41C,
          (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
          (const char *)(unsigned int)v13);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41C,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\getfolderstokeepforpbr.cpp",
      (const char *)v12,
      v14);
    return v12;
  }
}

```

## disassembly

```asm
0x1800421f4  push    rbx
0x1800421f6  push    rbp
0x1800421f7  push    rsi
0x1800421f8  push    rdi
0x1800421f9  push    r14
0x1800421fb  push    r15
0x1800421fd  sub     rsp, 38h
0x180042201  lea     r15, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\appxalluserst"...
0x180042208  mov     r14, r8
0x18004220b  mov     rbx, rdx
0x18004220e  mov     rsi, rcx
0x180042211  test    rcx, rcx
0x180042214  jz      short loc_18004223E
0x180042216  mov     r8, rdx
0x180042219  lea     rdx, aInExpandenviro; "In ExpandEnvironmentInPath %ws."
0x180042220  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180042225  test    eax, eax
0x180042227  jns     short loc_18004223E
0x180042229  mov     rcx, [rsp+68h]; this
0x18004222e  mov     r9d, eax; char *
0x180042231  mov     r8, r15; unsigned int
0x180042234  mov     edx, 416h; void *
0x180042239  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004223e  xor     r8d, r8d; nSize
0x180042241  xor     edx, edx; lpDst
0x180042243  mov     rcx, rbx; lpSrc
0x180042246  call    cs:__imp_ExpandEnvironmentStringsW
0x18004224c  mov     edi, eax
0x18004224e  test    eax, eax
0x180042250  jnz     short loc_180042275
0x180042252  mov     rcx, [rsp+68h]; this
0x180042257  lea     r9, aPathWs; "Path %ws."
0x18004225e  mov     r8, r15; unsigned int
0x180042261  mov     [rsp+68h+var_48], rbx; char *
0x180042266  mov     edx, 419h; void *
0x18004226b  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180042270  jmp     loc_18004230A
0x180042275  mov     edx, edi; unsigned int
0x180042277  mov     rcx, r14; this
0x18004227a  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x18004227f  mov     ebp, eax
0x180042281  test    eax, eax
0x180042283  jns     short loc_1800422D0
0x180042285  mov     ebx, 41Ch
0x18004228a  test    rsi, rsi
0x18004228d  jz      short loc_1800422BA
0x18004228f  mov     r9d, eax
0x180042292  lea     rdx, aSetcapacityUFa; "SetCapacity %u failed, 0x%0x."
0x180042299  mov     r8d, edi
0x18004229c  mov     rcx, rsi; this
0x18004229f  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800422a4  test    eax, eax
0x1800422a6  jns     short loc_1800422BA
0x1800422a8  mov     rcx, [rsp+68h]; this
0x1800422ad  mov     r9d, eax; char *
0x1800422b0  mov     r8, r15; unsigned int
0x1800422b3  mov     edx, ebx; void *
0x1800422b5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800422ba  mov     rcx, [rsp+68h]; this
0x1800422bf  mov     r9d, ebp; char *
0x1800422c2  mov     r8, r15; unsigned int
0x1800422c5  mov     edx, ebx; void *
0x1800422c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800422cc  mov     eax, ebp
0x1800422ce  jmp     short loc_18004230A
0x1800422d0  mov     rdx, [r14+8]; lpDst
0x1800422d4  mov     r8d, edi; nSize
0x1800422d7  mov     rcx, rbx; lpSrc
0x1800422da  call    cs:__imp_ExpandEnvironmentStringsW
0x1800422e0  test    eax, eax
0x1800422e2  jnz     short loc_180042308
0x1800422e4  mov     rcx, [rsp+68h]; this
0x1800422e9  lea     r9, aPathWsLenU; "Path %ws, len %u."
0x1800422f0  mov     [rsp+68h+var_40], edi
0x1800422f4  mov     r8, r15; unsigned int
0x1800422f7  mov     edx, 41Fh; void *
0x1800422fc  mov     [rsp+68h+var_48], rbx; char *
0x180042301  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180042306  jmp     short loc_18004230A
0x180042308  xor     eax, eax
0x18004230a  add     rsp, 38h
0x18004230e  pop     r15
0x180042310  pop     r14
0x180042312  pop     rdi
0x180042313  pop     rsi
0x180042314  pop     rbp
0x180042315  pop     rbx
0x180042316  retn
```
