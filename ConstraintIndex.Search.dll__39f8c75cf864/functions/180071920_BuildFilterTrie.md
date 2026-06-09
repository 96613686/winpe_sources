# BuildFilterTrie

- ea: `0x180071920`
- end: `0x180071a4f`
- name: `BuildFilterTrie`
- size: `303`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18001ae50`
- `0x18001b4d4`
- `0x18001c2a0`
- `0x18001cb54`
- `0x18006cec0`
- `0x180071920`
- `0x180075b44`
- `0x180075e84`
- `0x180076bb8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800719ad`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800719ad`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800719bd`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800719bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall BuildFilterTrie(wchar_t *a1, wchar_t *a2, __int64 a3)
{
  unsigned __int64 v5; // rdx
  const char *v6; // rax
  std::exception *v8; // [rsp+38h] [rbp-440h] BYREF
  int v9[4]; // [rsp+40h] [rbp-438h] BYREF
  __int128 v10; // [rsp+50h] [rbp-428h]
  __int64 v11; // [rsp+60h] [rbp-418h]
  _BYTE v12[208]; // [rsp+70h] [rbp-408h] BYREF
  _BYTE v13[272]; // [rsp+140h] [rbp-338h] BYREF
  WCHAR pszPath[264]; // [rsp+250h] [rbp-228h] BYREF

  memset_0(v12, 0, sizeof(v12));
  try
  {
    Microsoft::ISRC::ConstraintIndex::ConstraintIndex((Microsoft::ISRC::ConstraintIndex *)v12, a1);
    *(_OWORD *)v9 = 0;
    v10 = 0;
    v11 = 0;
    Microsoft::ISRC::FilterTrieBuilder::FilterTrieBuilder(
      (Microsoft::ISRC::FilterTrieBuilder *)v9,
      (const struct Microsoft::ISRC::ConstraintIndex *)v12);
    StringCchCopyW(pszPath, v5, a2);
    PathCchRemoveFileSpec(pszPath, 0x104u);
    PathCchAddBackslash(pszPath, 0x104u);
    memset_0(v13, 0, 0x108u);
    std::ofstream::ofstream(v13, a2, 32);
    Microsoft::ISRC::FilterTrieBuilder::Build((int)v9);
    std::ofstream::`vbase destructor'(v13);
    Microsoft::ISRC::FilterTrieBuilder::~FilterTrieBuilder((Microsoft::ISRC::FilterTrieBuilder *)v9);
    Microsoft::ISRC::ConstraintIndex::~ConstraintIndex((Microsoft::ISRC::ConstraintIndex *)v12);
  }
  catch ( std::exception *v8 )
  {
    *(_BYTE *)a3 = 1;
    v6 = (const char *)(*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v8 + 8LL))(v8);
    *(_QWORD *)(a3 + 8) = AllocateReturnString(v6);
  }
}

```

## disassembly

```asm
0x180071920  mov     [rsp+arg_18], rbx
0x180071925  push    rdi
0x180071926  sub     rsp, 470h
0x18007192d  mov     rax, cs:__security_cookie
0x180071934  xor     rax, rsp
0x180071937  mov     [rsp+478h+var_18], rax
0x18007193f  mov     rdi, rdx
0x180071942  mov     rbx, rcx
0x180071945  mov     [rsp+478h+var_448], r8
0x18007194a  xor     edx, edx; Val
0x18007194c  mov     r8d, 0D0h; Size
0x180071952  lea     rcx, [rsp+478h+var_408]; void *
0x180071957  call    memset_0
0x18007195c  mov     rdx, rbx; wchar_t *
0x18007195f  lea     rcx, [rsp+478h+var_408]; this
0x180071964  call    ??0ConstraintIndex@ISRC@Microsoft@@QEAA@PEB_W@Z; Microsoft::ISRC::ConstraintIndex::ConstraintIndex(wchar_t const *)
0x180071969  nop
0x18007196a  xorps   xmm0, xmm0
0x18007196d  xor     eax, eax
0x18007196f  movups  xmmword ptr [rsp+478h+var_438], xmm0
0x180071974  movups  [rsp+478h+var_428], xmm0
0x180071979  mov     [rsp+478h+var_418], rax
0x18007197e  lea     rdx, [rsp+478h+var_408]; struct Microsoft::ISRC::ConstraintIndex *
0x180071983  lea     rcx, [rsp+478h+var_438]; this
0x180071988  call    ??0FilterTrieBuilder@ISRC@Microsoft@@QEAA@PEBVConstraintIndex@12@@Z; Microsoft::ISRC::FilterTrieBuilder::FilterTrieBuilder(Microsoft::ISRC::ConstraintIndex const *)
0x18007198d  nop
0x18007198e  mov     r8, rdi; wchar_t *
0x180071991  lea     rcx, [rsp+478h+pszPath]; wchar_t *
0x180071999  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18007199e  mov     ebx, 104h
0x1800719a3  mov     edx, ebx; cchPath
0x1800719a5  lea     rcx, [rsp+478h+pszPath]; pszPath
0x1800719ad  call    cs:__imp_PathCchRemoveFileSpec
0x1800719b3  mov     edx, ebx; cchPath
0x1800719b5  lea     rcx, [rsp+478h+pszPath]; pszPath
0x1800719bd  call    cs:__imp_PathCchAddBackslash
0x1800719c3  xor     edx, edx; Val
0x1800719c5  lea     r8d, [rbx+4]; Size
0x1800719c9  lea     rcx, [rsp+478h+var_338]; void *
0x1800719d1  call    memset_0
0x1800719d6  mov     r8d, 20h ; ' '
0x1800719dc  mov     rdx, rdi
0x1800719df  lea     rcx, [rsp+478h+var_338]
0x1800719e7  call    ??0?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAA@PEB_WHH@Z; std::ofstream::ofstream(wchar_t const *,int,int)
0x1800719ec  nop
0x1800719ed  lea     r8, [rsp+478h+pszPath]
0x1800719f5  lea     rdx, [rsp+478h+var_338]
0x1800719fd  lea     rcx, [rsp+478h+var_438]; int
0x180071a02  call    ?Build@FilterTrieBuilder@ISRC@Microsoft@@QEAAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@PEB_W@Z; Microsoft::ISRC::FilterTrieBuilder::Build(std::ostream &,wchar_t const *)
0x180071a07  nop
0x180071a08  lea     rcx, [rsp+478h+var_338]
0x180071a10  call    ??_D?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ofstream::`vbase destructor'(void)
0x180071a15  nop
0x180071a16  lea     rcx, [rsp+478h+var_438]; this
0x180071a1b  call    ??1FilterTrieBuilder@ISRC@Microsoft@@QEAA@XZ; Microsoft::ISRC::FilterTrieBuilder::~FilterTrieBuilder(void)
0x180071a20  nop
0x180071a21  lea     rcx, [rsp+478h+var_408]; this
0x180071a26  call    ??1ConstraintIndex@ISRC@Microsoft@@QEAA@XZ; Microsoft::ISRC::ConstraintIndex::~ConstraintIndex(void)
0x180071a2b  nop
0x180071a2c  jmp     short $+2
0x180071a2e  mov     rcx, [rsp+478h+var_18]
0x180071a36  xor     rcx, rsp; StackCookie
0x180071a39  call    __security_check_cookie
0x180071a3e  mov     rbx, [rsp+478h+arg_18]
0x180071a46  add     rsp, 470h
0x180071a4d  pop     rdi
0x180071a4e  retn
```
