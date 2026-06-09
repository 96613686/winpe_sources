# StateRepository::Globals::PartitionSettings::FilenameToPartition(char const *)

- ea: `0x180023560`
- end: `0x18002367d`
- name: `?FilenameToPartition@PartitionSettings@Globals@StateRepository@@SA?AW4Partition@3@PEBD@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180028200`

## callees

- `0x180003980`
- `0x1800041cc`
- `0x1800042f4`
- `0x18000c3bc`
- `0x180023560`
- `0x180023684`
- `0x180024c54`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002362b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002362b`

## string_xrefs

- `0x1800235bb`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::PartitionSettings::FilenameToPartition(const char *a1)
{
  int v2; // eax
  void *v3; // rcx
  const WCHAR *v5; // rsi
  int *i; // rbx
  unsigned int v7; // edi
  LPCWCH *v8; // rax
  void *v9; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-248h]
  void *Block[2]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v12[528]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *(_OWORD *)Block = 0;
  memset_0(v12, 0, 0x208u);
  v2 = StateRepository::Utf16String::Set((StateRepository::Utf16String *)Block, a1);
  if ( v2 >= 0 )
  {
    v5 = (const WCHAR *)Block[0];
    for ( i = (int *)&qword_180042218; i != &dword_180042224; ++i )
    {
      v7 = *i;
      v8 = (LPCWCH *)StateRepository::Globals::PartitionSettings::Get((unsigned int)*i);
      if ( v8 && *v8 && CompareStringOrdinal(v5, -1, *v8, -1, 1) == 2 )
        goto LABEL_12;
    }
    v7 = 0;
LABEL_12:
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v2,
      bIgnoreCase);
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
0x180023560  mov     [rsp+arg_8], rbx
0x180023565  mov     [rsp+arg_10], rsi
0x18002356a  push    rdi
0x18002356b  sub     rsp, 260h
0x180023572  mov     rax, cs:__security_cookie
0x180023579  xor     rax, rsp
0x18002357c  mov     [rsp+268h+var_18], rax
0x180023584  mov     rbx, rcx
0x180023587  xorps   xmm0, xmm0
0x18002358a  lea     rcx, [rsp+268h+var_228]; void *
0x18002358f  movdqa  xmmword ptr [rsp+268h+Block], xmm0
0x180023595  xor     edx, edx; Val
0x180023597  mov     r8d, 208h; Size
0x18002359d  call    memset_0
0x1800235a2  mov     rdx, rbx; char *
0x1800235a5  lea     rcx, [rsp+268h+Block]; this
0x1800235aa  call    ?Set@Utf16String@StateRepository@@QEAAJPEBD@Z; StateRepository::Utf16String::Set(char const *)
0x1800235af  test    eax, eax
0x1800235b1  jns     short loc_1800235EB
0x1800235b3  mov     rcx, [rsp+268h]; this
0x1800235bb  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x1800235c2  mov     r9d, eax; char *
0x1800235c5  mov     edx, 186h; void *
0x1800235ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800235cf  mov     rcx, [rsp+268h+Block+8]; Block
0x1800235d4  mov     [rsp+268h+Block+8], 0
0x1800235dd  test    rcx, rcx
0x1800235e0  jz      short loc_1800235E7
0x1800235e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800235e7  xor     eax, eax
0x1800235e9  jmp     short loc_180023658
0x1800235eb  mov     rsi, [rsp+268h+Block]
0x1800235f0  lea     rbx, qword_180042218
0x1800235f7  lea     rax, dword_180042224
0x1800235fe  cmp     rbx, rax
0x180023601  jz      short loc_18002363C
0x180023603  mov     edi, [rbx]
0x180023605  mov     ecx, edi
0x180023607  call    ?Get@PartitionSettings@Globals@StateRepository@@SAPEBU123@W4Partition@3@@Z; StateRepository::Globals::PartitionSettings::Get(StateRepository::Partition)
0x18002360c  test    rax, rax
0x18002360f  jz      short loc_180023636
0x180023611  mov     r8, [rax]; lpString2
0x180023614  test    r8, r8
0x180023617  jz      short loc_180023636
0x180023619  or      r9d, 0FFFFFFFFh; cchCount2
0x18002361d  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x180023625  or      edx, r9d; cchCount1
0x180023628  mov     rcx, rsi; lpString1
0x18002362b  call    cs:__imp_CompareStringOrdinal
0x180023631  cmp     eax, 2
0x180023634  jz      short loc_18002363E
0x180023636  add     rbx, 4
0x18002363a  jmp     short loc_1800235F7
0x18002363c  xor     edi, edi
0x18002363e  mov     rcx, [rsp+268h+Block+8]; Block
0x180023643  mov     [rsp+268h+Block+8], 0
0x18002364c  test    rcx, rcx
0x18002364f  jz      short loc_180023656
0x180023651  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023656  mov     eax, edi
0x180023658  mov     rcx, [rsp+268h+var_18]
0x180023660  xor     rcx, rsp; StackCookie
0x180023663  call    __security_check_cookie
0x180023668  lea     r11, [rsp+268h+var_8]
0x180023670  mov     rbx, [r11+18h]
0x180023674  mov     rsi, [r11+20h]
0x180023678  mov     rsp, r11
0x18002367b  pop     rdi
0x18002367c  retn
```
