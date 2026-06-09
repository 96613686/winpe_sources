# StateRepository::Localization::CreateMrtString(ushort const *,HSTRING__ * *)

- ea: `0x180009d80`
- end: `0x180009efb`
- name: `?CreateMrtString@Localization@StateRepository@@YAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(StateRepository::Localization *this, unsigned __int16 *, HSTRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009d58`
- `0x180009f2c`

## callees

- `0x180001d60`
- `0x180002154`
- `0x180002bdc`
- `0x180006224`
- `0x180009a20`
- `0x180009d80`
- `0x18000a158`

## import_xrefs

- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180009e09`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180009e4a`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180009e09`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x180009e4a`

## string_xrefs

- `0x180009db8`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x180009e5c`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x180009ea2`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Localization::CreateMrtString(
        StateRepository::Localization *this,
        unsigned __int16 *a2,
        HSTRING *a3)
{
  unsigned int v4; // ebx
  const unsigned __int16 *v6; // rax
  HSTRING *v7; // r8
  const WCHAR *v8; // rbp
  WCHAR *v9; // rsi
  WCHAR *v10; // rbx
  int HString; // edi
  const WCHAR *v12; // rcx
  int pszOutBuf[132]; // [rsp+20h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( !a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
      (const char *)0x80004003LL,
      pszOutBuf[0]);
    return v4;
  }
  v6 = FileUriToFilenameIfNecessary((const unsigned __int16 *)this);
  v8 = v6;
  v9 = 0;
  v10 = 0;
  if ( !v6 || !*v6 )
    goto LABEL_16;
  HString = SHLoadIndirectString(v6, (PWSTR)pszOutBuf, 0x104u, 0);
  if ( HString == -2147024774 )
  {
    v9 = (WCHAR *)operator new[](0x4000u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v9 )
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
        (const char *)0x8007000ELL,
        pszOutBuf[0]);
      operator delete(0);
      return v4;
    }
    operator delete(0);
    v10 = v9;
    HString = SHLoadIndirectString(v8, v9, 0x2000u, 0);
  }
  else
  {
    v9 = (WCHAR *)pszOutBuf;
  }
  if ( HString == -2147467259 || HString == -2147024893 )
  {
    v12 = v8;
LABEL_17:
    HString = StateRepository::Localization::CreateHString(v12, a2, v7);
    goto LABEL_18;
  }
  if ( HString >= 0 )
  {
LABEL_16:
    v12 = v9;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7B,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
    (const char *)(unsigned int)HString,
    pszOutBuf[0]);
LABEL_18:
  operator delete(v10);
  return (unsigned int)HString;
}

```

## disassembly

```asm
0x180009d80  mov     [rsp+arg_10], rbx
0x180009d85  push    rbp
0x180009d86  push    rsi
0x180009d87  push    rdi
0x180009d88  push    r14
0x180009d8a  push    r15
0x180009d8c  sub     rsp, 240h
0x180009d93  mov     rax, cs:__security_cookie
0x180009d9a  xor     rax, rsp
0x180009d9d  mov     [rsp+268h+var_38], rax
0x180009da5  xor     r15d, r15d
0x180009da8  mov     r14, rdx
0x180009dab  test    rdx, rdx
0x180009dae  jnz     short loc_180009DD7
0x180009db0  mov     rcx, [rsp+268h]; this
0x180009db8  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009dbf  mov     ebx, 80004003h
0x180009dc4  lea     edx, [r14+59h]; void *
0x180009dc8  mov     r9d, ebx; char *
0x180009dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dd0  mov     eax, ebx
0x180009dd2  jmp     loc_180009ED4
0x180009dd7  call    ?FileUriToFilenameIfNecessary@@YAPEBGPEBG@Z; FileUriToFilenameIfNecessary(ushort const *)
0x180009ddc  mov     rbp, rax
0x180009ddf  mov     rsi, r15
0x180009de2  mov     rbx, r15
0x180009de5  test    rax, rax
0x180009de8  jz      loc_180009EBD
0x180009dee  cmp     [rax], r15w
0x180009df2  jz      loc_180009EBD
0x180009df8  xor     r9d, r9d; ppvReserved
0x180009dfb  lea     rdx, [rsp+268h+pszOutBuf]; pszOutBuf
0x180009e00  mov     r8d, 104h; cchOutBuf
0x180009e06  mov     rcx, rax; pszSource
0x180009e09  call    cs:__imp_SHLoadIndirectString
0x180009e0f  mov     edi, eax
0x180009e11  cmp     eax, 8007007Ah
0x180009e16  jnz     short loc_180009E81
0x180009e18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e1f  mov     ecx, 4000h; unsigned __int64
0x180009e24  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009e29  mov     rsi, rax
0x180009e2c  test    rax, rax
0x180009e2f  jz      short loc_180009E54
0x180009e31  xor     ecx, ecx; Block
0x180009e33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009e38  xor     r9d, r9d; ppvReserved
0x180009e3b  mov     r8d, 2000h; cchOutBuf
0x180009e41  mov     rdx, rsi; pszOutBuf
0x180009e44  mov     rcx, rbp; pszSource
0x180009e47  mov     rbx, rsi
0x180009e4a  call    cs:__imp_SHLoadIndirectString
0x180009e50  mov     edi, eax
0x180009e52  jmp     short loc_180009E86
0x180009e54  mov     rcx, [rsp+268h]; this
0x180009e5c  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009e63  mov     ebx, 8007000Eh
0x180009e68  mov     edx, 6Eh ; 'n'; void *
0x180009e6d  mov     r9d, ebx; char *
0x180009e70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e75  xor     ecx, ecx; Block
0x180009e77  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009e7c  jmp     loc_180009DD0
0x180009e81  lea     rsi, [rsp+268h+pszOutBuf]
0x180009e86  cmp     edi, 80004005h
0x180009e8c  jz      short loc_180009EB8
0x180009e8e  cmp     edi, 80070003h
0x180009e94  jz      short loc_180009EB8
0x180009e96  test    edi, edi
0x180009e98  jns     short loc_180009EBD
0x180009e9a  mov     rcx, [rsp+268h]; this
0x180009ea2  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009ea9  mov     r9d, edi; char *
0x180009eac  mov     edx, 7Bh ; '{'; void *
0x180009eb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009eb6  jmp     short loc_180009ECA
0x180009eb8  mov     rcx, rbp
0x180009ebb  jmp     short loc_180009EC0
0x180009ebd  mov     rcx, rsi; sourceString
0x180009ec0  mov     rdx, r14; unsigned __int16 *
0x180009ec3  call    ?CreateHString@Localization@StateRepository@@YAJPEBGPEAPEAUHSTRING__@@@Z; StateRepository::Localization::CreateHString(ushort const *,HSTRING__ * *)
0x180009ec8  mov     edi, eax
0x180009eca  mov     rcx, rbx; Block
0x180009ecd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ed2  mov     eax, edi
0x180009ed4  mov     rcx, [rsp+268h+var_38]
0x180009edc  xor     rcx, rsp; StackCookie
0x180009edf  call    __security_check_cookie
0x180009ee4  mov     rbx, [rsp+268h+arg_10]
0x180009eec  add     rsp, 240h
0x180009ef3  pop     r15
0x180009ef5  pop     r14
0x180009ef7  pop     rdi
0x180009ef8  pop     rsi
0x180009ef9  pop     rbp
0x180009efa  retn
```
