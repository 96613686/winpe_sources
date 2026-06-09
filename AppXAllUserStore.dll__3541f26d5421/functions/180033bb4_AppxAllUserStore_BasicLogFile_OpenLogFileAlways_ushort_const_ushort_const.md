# AppxAllUserStore::BasicLogFile::OpenLogFileAlways(ushort const *,ushort const *)

- ea: `0x180033bb4`
- end: `0x180033dc6`
- name: `?OpenLogFileAlways@BasicLogFile@AppxAllUserStore@@QEAAJPEBG0@Z`
- size: `530`
- prototype: `__int64 __fastcall(AppxAllUserStore::BasicLogFile *__hidden this, char *, char *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180034de8`
- `0x18004252c`

## callees

- `0x180016118`
- `0x180017cd0`
- `0x180018248`
- `0x18001a324`
- `0x18001a6a0`
- `0x1800262c8`
- `0x180033768`
- `0x180033bb4`
- `0x18004682c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033d20`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033d20`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033c72`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033c72`

## string_xrefs

- `0x180033bd8`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180033c24`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180033ccf`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180033d2b`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180033d99`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180033c18`: `Directory %ws log file %ws.`
- `0x180033cc3`: `Directory %ws log file %ws.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::BasicLogFile::OpenLogFileAlways(
        AppxAllUserStore::BasicLogFile *this,
        char *a2,
        char *a3)
{
  __int64 v6; // rdx
  unsigned int HResultFromLastError; // ebx
  int v9; // esi
  void *v10; // rdx
  Common *v11; // rcx
  HANDLE FileW; // rsi
  const char *v13; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-38h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-38h]
  const char *hTemplateFile; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int16 Buffer; // [rsp+68h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp+20h] BYREF

  if ( !a2 )
  {
    v6 = 235;
LABEL_3:
    HResultFromLastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return HResultFromLastError;
  }
  if ( !a3 )
  {
    v6 = 236;
    goto LABEL_3;
  }
  v9 = Common::PathHelpers::CombinePaths((const unsigned __int16 *)a2, (const unsigned __int16 *)a3, this);
  if ( v9 >= 0 )
  {
    FileW = CreateFileW(*((LPCWSTR *)this + 1), 0xC0000000, 3u, 0, 2u, 0x80u, 0);
    if ( *((HANDLE *)this + 3) == FileW )
    {
      FileW = (HANDLE)*((_QWORD *)this + 3);
    }
    else
    {
      Common::CloseHandleHelper(*((Common **)this + 3), v10);
      *((_QWORD *)this + 3) = FileW;
    }
    if ( FileW == (HANDLE)-1LL )
    {
      *((_QWORD *)this + 1) = 0;
      *(_DWORD *)this = 0;
      *((_DWORD *)this + 4) = 0;
      HResultFromLastError = Common::GetHResultFromLastError(v11);
      if ( (HResultFromLastError & 0x80000000) != 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
          (const char *)HResultFromLastError,
          (int)"Directory %ws log file %ws.",
          a2,
          a3);
      return HResultFromLastError;
    }
    NumberOfBytesWritten = 0;
    Buffer = -257;
    if ( WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      LODWORD(hTemplateFile) = NumberOfBytesWritten;
      LOBYTE(dwCreationDispositiona) = NumberOfBytesWritten == 0;
      wil::details::in1diag3::Log_HrIfMsg(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
        (const char *)0x8000FFFFLL,
        dwCreationDispositiona,
        (bool)"Written %u.",
        hTemplateFile);
      HResultFromLastError = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Begin %ws.", a3);
      if ( (HResultFromLastError & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
          (const char *)HResultFromLastError,
          (int)"%ws.",
          a3);
        return HResultFromLastError;
      }
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x105,
               (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
               v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)(unsigned int)v9,
      (int)"Directory %ws log file %ws.",
      a2,
      a3);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180033bb4  mov     [rsp+arg_0], rbx
0x180033bb9  push    rbp
0x180033bba  push    rsi
0x180033bbb  push    rdi
0x180033bbc  sub     rsp, 40h
0x180033bc0  mov     rdi, r8
0x180033bc3  mov     rbp, rdx
0x180033bc6  mov     rbx, rcx
0x180033bc9  test    rdx, rdx
0x180033bcc  jnz     short loc_180033BF3
0x180033bce  mov     edx, 0EBh; void *
0x180033bd3  mov     rcx, [rsp+58h]; this
0x180033bd8  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033bdf  mov     ebx, 80070057h
0x180033be4  mov     r9d, ebx; char *
0x180033be7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033bec  mov     eax, ebx
0x180033bee  jmp     loc_180033DB9
0x180033bf3  test    rdi, rdi
0x180033bf6  jnz     short loc_180033BFF
0x180033bf8  mov     edx, 0ECh
0x180033bfd  jmp     short loc_180033BD3
0x180033bff  mov     r8, rbx; this
0x180033c02  mov     rdx, rdi; unsigned __int16 *
0x180033c05  mov     rcx, rbp; Src
0x180033c08  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x180033c0d  mov     esi, eax
0x180033c0f  test    eax, eax
0x180033c11  jns     short loc_180033C49
0x180033c13  mov     rcx, [rsp+58h]; this
0x180033c18  lea     rax, aDirectoryWsLog; "Directory %ws log file %ws."
0x180033c1f  mov     [rsp+58h+hTemplateFile], rdi
0x180033c24  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033c2b  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rbp; char *
0x180033c30  mov     r9d, esi; char *
0x180033c33  mov     edx, 0EEh; void *
0x180033c38  mov     qword ptr [rsp+58h+dwCreationDisposition], rax; int
0x180033c3d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033c42  mov     eax, esi
0x180033c44  jmp     loc_180033DB9
0x180033c49  mov     rcx, [rbx+8]; lpFileName
0x180033c4d  xor     r9d, r9d; lpSecurityAttributes
0x180033c50  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180033c59  mov     edx, 0C0000000h; dwDesiredAccess
0x180033c5e  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180033c66  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x180033c6e  lea     r8d, [r9+3]; dwShareMode
0x180033c72  call    cs:__imp_CreateFileW
0x180033c78  mov     rsi, rax
0x180033c7b  cmp     [rbx+18h], rax
0x180033c7f  jz      short loc_180033C90
0x180033c81  mov     rcx, [rbx+18h]; this
0x180033c85  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x180033c8a  mov     [rbx+18h], rsi
0x180033c8e  jmp     short loc_180033C94
0x180033c90  mov     rsi, [rbx+18h]
0x180033c94  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180033c98  jnz     short loc_180033CF2
0x180033c9a  mov     qword ptr [rbx+8], 0
0x180033ca2  mov     dword ptr [rbx], 0
0x180033ca8  mov     dword ptr [rbx+10h], 0
0x180033caf  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x180033cb4  mov     ebx, eax
0x180033cb6  test    eax, eax
0x180033cb8  jns     loc_180033BEC
0x180033cbe  mov     rcx, [rsp+58h]; this
0x180033cc3  lea     rax, aDirectoryWsLog; "Directory %ws log file %ws."
0x180033cca  mov     [rsp+58h+hTemplateFile], rdi
0x180033ccf  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033cd6  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rbp; char *
0x180033cdb  mov     r9d, ebx; char *
0x180033cde  mov     edx, 0FBh; void *
0x180033ce3  mov     qword ptr [rsp+58h+dwCreationDisposition], rax; int
0x180033ce8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033ced  jmp     loc_180033BEC
0x180033cf2  mov     eax, 0FEFFh
0x180033cf7  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180033cff  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180033d04  mov     [rsp+58h+Buffer], ax
0x180033d09  mov     r8d, 2; nNumberOfBytesToWrite
0x180033d0f  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x180033d18  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x180033d1d  mov     rcx, rsi; hFile
0x180033d20  call    cs:__imp_WriteFile
0x180033d26  mov     rcx, [rsp+58h]; this
0x180033d2b  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033d32  test    eax, eax
0x180033d34  jnz     short loc_180033D42
0x180033d36  mov     edx, 105h; void *
0x180033d3b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033d40  jmp     short loc_180033DB9
0x180033d42  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x180033d46  mov     r9d, 8000FFFFh; char *
0x180033d4c  mov     dword ptr [rsp+58h+hTemplateFile], eax; char *
0x180033d50  cmp     eax, 1
0x180033d53  lea     rax, aWrittenU; "Written %u."
0x180033d5a  setb    dl
0x180033d5d  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rax; bool
0x180033d62  mov     byte ptr [rsp+58h+dwCreationDisposition], dl; int
0x180033d66  mov     edx, 106h; void *
0x180033d6b  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180033d70  mov     r8, rdi
0x180033d73  lea     rdx, aBeginWs; "Begin %ws."
0x180033d7a  mov     rcx, rbx; this
0x180033d7d  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180033d82  mov     ebx, eax
0x180033d84  test    eax, eax
0x180033d86  jns     short loc_180033DB7
0x180033d88  mov     rcx, [rsp+58h]; this
0x180033d8d  lea     rax, aWs; "%ws."
0x180033d94  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], rdi; char *
0x180033d99  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033da0  mov     r9d, ebx; char *
0x180033da3  mov     qword ptr [rsp+58h+dwCreationDisposition], rax; int
0x180033da8  mov     edx, 107h; void *
0x180033dad  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033db2  jmp     loc_180033BEC
0x180033db7  xor     eax, eax
0x180033db9  mov     rbx, [rsp+58h+arg_0]
0x180033dbe  add     rsp, 40h
0x180033dc2  pop     rdi
0x180033dc3  pop     rsi
0x180033dc4  pop     rbp
0x180033dc5  retn
```
