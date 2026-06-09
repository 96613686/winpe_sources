# AppxAllUserStore::BasicLogFile::WriteLine(ushort const *)

- ea: `0x180036740`
- end: `0x1800367f2`
- name: `?WriteLine@BasicLogFile@AppxAllUserStore@@AEAAJPEBG@Z`
- size: `178`
- prototype: `int(AppxAllUserStore::BasicLogFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017cd0`

## callees

- `0x180033768`
- `0x180036498`
- `0x180036740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180036779`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180036779`

## string_xrefs

- `0x180036784`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::BasicLogFile::WriteLine(AppxAllUserStore::BasicLogFile *this, const char *a2)
{
  __int64 v2; // rax
  void *v4; // rcx
  int v5; // edi
  int lpOverlapped; // [rsp+20h] [rbp-38h]
  int v8; // [rsp+28h] [rbp-30h]
  int v9; // [rsp+38h] [rbp-20h]
  DWORD v10; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)&a2[2 * v2] );
  v4 = (void *)*((_QWORD *)this + 3);
  v5 = 2 * v2;
  NumberOfBytesWritten = 0;
  if ( WriteFile(v4, a2, 2 * v2, &NumberOfBytesWritten, 0) )
  {
    v10 = NumberOfBytesWritten;
    v9 = v5;
    LOBYTE(lpOverlapped) = NumberOfBytesWritten == 0;
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)0x8000FFFFLL,
      lpOverlapped,
      (bool)"LogLine %ws of len %u written %u.",
      a2,
      v9,
      v10);
    return 0;
  }
  else
  {
    v8 = v5;
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0x50,
             (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
             "LogLine %ws of len %u.",
             a2,
             v8);
  }
}

```

## disassembly

```asm
0x180036740  mov     [rsp+arg_8], rbx
0x180036745  mov     [rsp+arg_10], rsi
0x18003674a  push    rdi
0x18003674b  sub     rsp, 50h
0x18003674f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036753  mov     rbx, rdx
0x180036756  xor     esi, esi
0x180036758  inc     rax
0x18003675b  cmp     [rdx+rax*2], si
0x18003675f  jnz     short loc_180036758
0x180036761  mov     rcx, [rcx+18h]; hFile
0x180036765  lea     edi, [rax+rax]
0x180036768  mov     r8d, edi; nNumberOfBytesToWrite
0x18003676b  mov     [rsp+58h+NumberOfBytesWritten], esi
0x18003676f  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180036774  mov     [rsp+58h+lpOverlapped], rsi; lpOverlapped
0x180036779  call    cs:__imp_WriteFile
0x18003677f  mov     rcx, [rsp+58h]; this
0x180036784  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003678b  test    eax, eax
0x18003678d  jnz     short loc_1800367A9
0x18003678f  mov     dword ptr [rsp+58h+var_30], edi
0x180036793  lea     r9, aLoglineWsOfLen; "LogLine %ws of len %u."
0x18003679a  lea     edx, [rax+50h]; void *
0x18003679d  mov     [rsp+58h+lpOverlapped], rbx; char *
0x1800367a2  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800367a7  jmp     short loc_1800367E2
0x1800367a9  mov     eax, [rsp+58h+NumberOfBytesWritten]
0x1800367ad  mov     r9d, 8000FFFFh; char *
0x1800367b3  mov     [rsp+58h+var_18], eax
0x1800367b7  cmp     eax, 1
0x1800367ba  mov     [rsp+58h+var_20], edi
0x1800367be  lea     rax, aLoglineWsOfLen_0; "LogLine %ws of len %u written %u."
0x1800367c5  setb    dl
0x1800367c8  mov     [rsp+58h+var_28], rbx; char *
0x1800367cd  mov     qword ptr [rsp+58h+var_30], rax; bool
0x1800367d2  mov     byte ptr [rsp+58h+lpOverlapped], dl; int
0x1800367d6  mov     edx, 52h ; 'R'; void *
0x1800367db  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800367e0  xor     eax, eax
0x1800367e2  mov     rbx, [rsp+58h+arg_8]
0x1800367e7  mov     rsi, [rsp+58h+arg_10]
0x1800367ec  add     rsp, 50h
0x1800367f0  pop     rdi
0x1800367f1  retn
```
