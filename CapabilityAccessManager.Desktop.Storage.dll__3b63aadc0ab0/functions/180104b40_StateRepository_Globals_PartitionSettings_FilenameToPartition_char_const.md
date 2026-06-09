# StateRepository::Globals::PartitionSettings::FilenameToPartition(char const *)

- ea: `0x180104b40`
- end: `0x180104c5b`
- name: `?FilenameToPartition@PartitionSettings@Globals@StateRepository@@SA?AW4Partition@3@PEBD@Z`
- size: `283`
- prototype: `__int64 __fastcall(const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180103cd8`

## callees

- `0x180003060`
- `0x1800038f0`
- `0x180003a40`
- `0x1800f7630`
- `0x180103d80`
- `0x180104b40`
- `0x180104c64`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180104bff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180104bff`

## string_xrefs

- `0x180104b9b`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::PartitionSettings::FilenameToPartition(const char *a1)
{
  int v2; // eax
  void *v3; // rcx
  const WCHAR *v5; // rsi
  int *v6; // rbx
  unsigned int v7; // edi
  LPCWCH *v8; // rax
  void *v9; // rcx
  void *Block[2]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v11[528]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *(_OWORD *)Block = 0;
  memset_0(v11, 0, 0x208u);
  v2 = StateRepository::Utf16String::Set((StateRepository::Utf16String *)Block, a1);
  if ( v2 >= 0 )
  {
    v5 = (const WCHAR *)Block[0];
    v6 = (int *)&qword_180128050;
    while ( 1 )
    {
      v7 = *v6;
      v8 = (LPCWCH *)StateRepository::Globals::PartitionSettings::Get((unsigned int)*v6);
      if ( v8 )
      {
        if ( *v8 && CompareStringOrdinal(v5, -1, *v8, -1, 1) == 2 )
          break;
      }
      if ( ++v6 == &dword_18012805C )
      {
        v7 = 0;
        break;
      }
    }
    v9 = Block[1];
    Block[1] = 0;
    if ( v9 )
      operator delete(v9);
    return v7;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x186,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v2);
    v3 = Block[1];
    Block[1] = 0;
    if ( v3 )
      operator delete(v3);
    return 0;
  }
}

```

## disassembly

```asm
0x180104b40  mov     [rsp+arg_8], rbx
0x180104b45  mov     [rsp+arg_10], rsi
0x180104b4a  push    rdi
0x180104b4b  sub     rsp, 260h
0x180104b52  mov     rax, cs:__security_cookie
0x180104b59  xor     rax, rsp
0x180104b5c  mov     [rsp+268h+var_18], rax
0x180104b64  mov     rbx, rcx
0x180104b67  xorps   xmm0, xmm0
0x180104b6a  lea     rcx, [rsp+268h+var_228]; void *
0x180104b6f  movdqa  xmmword ptr [rsp+268h+Block], xmm0
0x180104b75  xor     edx, edx; Val
0x180104b77  mov     r8d, 208h; Size
0x180104b7d  call    memset_0
0x180104b82  mov     rdx, rbx; char *
0x180104b85  lea     rcx, [rsp+268h+Block]; this
0x180104b8a  call    ?Set@Utf16String@StateRepository@@QEAAJPEBD@Z; StateRepository::Utf16String::Set(char const *)
0x180104b8f  test    eax, eax
0x180104b91  jns     short loc_180104BCB
0x180104b93  mov     rcx, [rsp+268h]; this
0x180104b9b  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180104ba2  mov     r9d, eax; char *
0x180104ba5  mov     edx, 186h; void *
0x180104baa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180104baf  mov     rcx, [rsp+268h+Block+8]; Block
0x180104bb4  mov     [rsp+268h+Block+8], 0
0x180104bbd  test    rcx, rcx
0x180104bc0  jz      short loc_180104BC7
0x180104bc2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104bc7  xor     eax, eax
0x180104bc9  jmp     short loc_180104C36
0x180104bcb  mov     rsi, [rsp+268h+Block]
0x180104bd0  lea     rbx, qword_180128050
0x180104bd7  mov     edi, [rbx]
0x180104bd9  mov     ecx, edi
0x180104bdb  call    ?Get@PartitionSettings@Globals@StateRepository@@SAPEBU123@W4Partition@3@@Z; StateRepository::Globals::PartitionSettings::Get(StateRepository::Partition)
0x180104be0  test    rax, rax
0x180104be3  jz      short loc_180104C0A
0x180104be5  mov     r8, [rax]; lpString2
0x180104be8  test    r8, r8
0x180104beb  jz      short loc_180104C0A
0x180104bed  or      r9d, 0FFFFFFFFh; cchCount2
0x180104bf1  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x180104bf9  or      edx, r9d; cchCount1
0x180104bfc  mov     rcx, rsi; lpString1
0x180104bff  call    cs:__imp_CompareStringOrdinal
0x180104c05  cmp     eax, 2
0x180104c08  jz      short loc_180104C1C
0x180104c0a  add     rbx, 4
0x180104c0e  lea     rax, dword_18012805C
0x180104c15  cmp     rbx, rax
0x180104c18  jnz     short loc_180104BD7
0x180104c1a  xor     edi, edi
0x180104c1c  mov     rcx, [rsp+268h+Block+8]; Block
0x180104c21  mov     [rsp+268h+Block+8], 0
0x180104c2a  test    rcx, rcx
0x180104c2d  jz      short loc_180104C34
0x180104c2f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180104c34  mov     eax, edi
0x180104c36  mov     rcx, [rsp+268h+var_18]
0x180104c3e  xor     rcx, rsp; StackCookie
0x180104c41  call    __security_check_cookie
0x180104c46  lea     r11, [rsp+268h+var_8]
0x180104c4e  mov     rbx, [r11+18h]
0x180104c52  mov     rsi, [r11+20h]
0x180104c56  mov     rsp, r11
0x180104c59  pop     rdi
0x180104c5a  retn
```
