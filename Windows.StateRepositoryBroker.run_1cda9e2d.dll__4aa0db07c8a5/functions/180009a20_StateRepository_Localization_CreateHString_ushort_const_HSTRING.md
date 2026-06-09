# StateRepository::Localization::CreateHString(ushort const *,HSTRING__ * *)

- ea: `0x180009a20`
- end: `0x180009af0`
- name: `?CreateHString@Localization@StateRepository@@YAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(PCNZWCH sourceString, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009d80`

## callees

- `0x180006224`
- `0x180006f34`
- `0x180009a20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009a91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009a91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009aa4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009aa4`

## string_xrefs

- `0x180009a41`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x180009ac0`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Localization::CreateHString(
        PCNZWCH sourceString,
        unsigned __int16 *a2,
        HSTRING *a3)
{
  unsigned int v5; // ebx
  const WCHAR *v6; // rcx
  unsigned __int64 v7; // rdx
  HSTRING v8; // rbx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF
  __int64 v13; // [rsp+40h] [rbp+18h] BYREF

  if ( a2 )
  {
    v13 = 0;
    v6 = (const WCHAR *)&unk_18000E6E4;
    string = 0;
    if ( sourceString )
      v6 = sourceString;
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    if ( v7 > 0xFFFFFFFF )
    {
      v5 = -2147024362;
    }
    else
    {
      v5 = WindowsCreateString(v6, v7, &string);
      if ( (v5 & 0x80000000) == 0 )
      {
        v8 = string;
        WindowsDeleteString(0);
        *(_QWORD *)a2 = v8;
        v5 = 0;
        v13 = 0;
LABEL_12:
        Windows::Internal::String::~String((Windows::Internal::String *)&v13);
        return v5;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
      (const char *)v5,
      v10);
    goto LABEL_12;
  }
  v5 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
    (const char *)0x80004003LL,
    v10);
  return v5;
}

```

## disassembly

```asm
0x180009a20  mov     [rsp+arg_0], rbx
0x180009a25  mov     [rsp+arg_18], rsi
0x180009a2a  push    rdi; int
0x180009a2b  sub     rsp, 20h
0x180009a2f  xor     esi, esi
0x180009a31  mov     rdi, rdx
0x180009a34  mov     rax, rcx
0x180009a37  test    rdx, rdx
0x180009a3a  jnz     short loc_180009A5D
0x180009a3c  mov     rcx, [rsp+28h]; this
0x180009a41  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009a48  mov     ebx, 80004003h
0x180009a4d  lea     edx, [rdi+2Eh]; void *
0x180009a50  mov     r9d, ebx; char *
0x180009a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a58  jmp     loc_180009ADE
0x180009a5d  test    rax, rax
0x180009a60  mov     [rsp+28h+arg_10], rsi
0x180009a65  lea     rcx, unk_18000E6E4
0x180009a6c  mov     [rsp+28h+string], rsi
0x180009a71  cmovnz  rcx, rax; sourceString
0x180009a75  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009a79  inc     rdx; length
0x180009a7c  cmp     [rcx+rdx*2], si
0x180009a80  jnz     short loc_180009A79
0x180009a82  mov     eax, 0FFFFFFFFh
0x180009a87  cmp     rdx, rax
0x180009a8a  ja      short loc_180009AB6
0x180009a8c  lea     r8, [rsp+28h+string]; string
0x180009a91  call    cs:__imp_WindowsCreateString
0x180009a97  mov     ebx, eax
0x180009a99  test    eax, eax
0x180009a9b  js      short loc_180009ABB
0x180009a9d  mov     rbx, [rsp+28h+string]
0x180009aa2  xor     ecx, ecx; string
0x180009aa4  call    cs:__imp_WindowsDeleteString
0x180009aaa  mov     [rdi], rbx
0x180009aad  mov     ebx, esi
0x180009aaf  mov     [rsp+28h+arg_10], rsi
0x180009ab4  jmp     short loc_180009AD4
0x180009ab6  mov     ebx, 80070216h
0x180009abb  mov     rcx, [rsp+28h]; this
0x180009ac0  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009ac7  mov     r9d, ebx; char *
0x180009aca  mov     edx, 31h ; '1'; void *
0x180009acf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ad4  lea     rcx, [rsp+28h+arg_10]; this
0x180009ad9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180009ade  mov     rsi, [rsp+28h+arg_18]
0x180009ae3  mov     eax, ebx
0x180009ae5  mov     rbx, [rsp+28h+arg_0]
0x180009aea  add     rsp, 20h
0x180009aee  pop     rdi
0x180009aef  retn
```
