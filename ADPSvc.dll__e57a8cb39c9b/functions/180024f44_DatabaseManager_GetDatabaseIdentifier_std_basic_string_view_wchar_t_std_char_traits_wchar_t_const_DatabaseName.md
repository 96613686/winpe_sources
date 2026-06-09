# DatabaseManager::GetDatabaseIdentifier(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,DatabaseName)

- ea: `0x180024f44`
- end: `0x1800250e4`
- name: `?GetDatabaseIdentifier@DatabaseManager@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@3@W4DatabaseName@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800250ec`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x180007234`
- `0x18000c13c`
- `0x180018950`
- `0x180024d34`
- `0x180024f44`

## string_xrefs

- `0x180025074`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasemanager.cpp`
- `0x180025091`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasemanager.cpp`
- `0x1800250ae`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasemanager.cpp`
- `0x1800250d2`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\databasemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DatabaseManager::GetDatabaseIdentifier(__int64 a1, _QWORD *a2, int a3)
{
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // r8
  const char *v12; // [rsp+20h] [rbp-248h]
  int v13[2]; // [rsp+20h] [rbp-248h]
  int v14[2]; // [rsp+20h] [rbp-248h]
  int v15[2]; // [rsp+20h] [rbp-248h]
  wchar_t v16[256]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  memset_0(v16, 0, sizeof(v16));
  if ( a3 )
  {
    v6 = a3 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasemanager.cpp",
          "Invalid database name",
          v12);
      *(_QWORD *)v13 = *a2;
      v7 = StringCchPrintfW(v16, 0x100u, L"%i_%s", 2);
      if ( v7 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasemanager.cpp",
          (const char *)(unsigned int)v7,
          v13[0]);
    }
    else
    {
      *(_QWORD *)v14 = *a2;
      v8 = StringCchPrintfW(v16, 0x100u, L"%i_%s", 1);
      if ( v8 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasemanager.cpp",
          (const char *)(unsigned int)v8,
          v14[0]);
    }
  }
  else
  {
    *(_QWORD *)v15 = *a2;
    v9 = StringCchPrintfW(v16, 0x100u, L"%i_%s", 0);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\databasemanager.cpp",
        (const char *)(unsigned int)v9,
        v15[0]);
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v10 = -1;
  *(_QWORD *)(a1 + 24) = 0;
  do
    ++v10;
  while ( v16[v10] );
  std::wstring::_Construct<1,wchar_t const *>(a1, v16);
  return a1;
}

```

## disassembly

```asm
0x180024f44  mov     [rsp+arg_10], rbx
0x180024f49  push    rbp
0x180024f4a  push    rsi
0x180024f4b  push    rdi
0x180024f4c  sub     rsp, 250h
0x180024f53  mov     rax, cs:__security_cookie
0x180024f5a  xor     rax, rsp
0x180024f5d  mov     [rsp+268h+var_28], rax
0x180024f65  mov     ebx, r8d
0x180024f68  mov     [rsp+268h+var_230], rcx
0x180024f6d  mov     rsi, rdx
0x180024f70  mov     rdi, rcx
0x180024f73  xor     edx, edx; Val
0x180024f75  lea     rcx, [rsp+268h+var_228]; void *
0x180024f7a  mov     r8d, 200h; Size
0x180024f80  xor     ebp, ebp
0x180024f82  call    memset_0
0x180024f87  test    ebx, ebx
0x180024f89  jz      short loc_180024FF3
0x180024f8b  sub     ebx, 1
0x180024f8e  jz      short loc_180024FC5
0x180024f90  cmp     ebx, 1
0x180024f93  jnz     loc_1800250C3
0x180024f99  mov     rax, [rsi]
0x180024f9c  lea     r9d, [rbp+2]
0x180024fa0  lea     r8, aIS; "%i_%s"
0x180024fa7  mov     qword ptr [rsp+268h+var_248], rax; int
0x180024fac  mov     edx, 100h; unsigned __int64
0x180024fb1  lea     rcx, [rsp+268h+var_228]; wchar_t *
0x180024fb6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180024fbb  test    eax, eax
0x180024fbd  js      loc_180025089
0x180024fc3  jmp     short loc_180025018
0x180024fc5  mov     rax, [rsi]
0x180024fc8  lea     r8, aIS; "%i_%s"
0x180024fcf  mov     r9d, 1
0x180024fd5  mov     qword ptr [rsp+268h+var_248], rax; int
0x180024fda  mov     edx, 100h; unsigned __int64
0x180024fdf  lea     rcx, [rsp+268h+var_228]; wchar_t *
0x180024fe4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180024fe9  test    eax, eax
0x180024feb  js      loc_1800250A6
0x180024ff1  jmp     short loc_180025018
0x180024ff3  mov     rax, [rsi]
0x180024ff6  lea     r8, aIS; "%i_%s"
0x180024ffd  xor     r9d, r9d
0x180025000  mov     qword ptr [rsp+268h+var_248], rax; int
0x180025005  mov     edx, 100h; unsigned __int64
0x18002500a  lea     rcx, [rsp+268h+var_228]; wchar_t *
0x18002500f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180025014  test    eax, eax
0x180025016  js      short loc_18002506C
0x180025018  xorps   xmm0, xmm0
0x18002501b  lea     rax, [rsp+268h+var_228]
0x180025020  movups  xmmword ptr [rdi], xmm0
0x180025023  mov     [rdi+10h], rbp
0x180025027  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002502b  mov     [rdi+18h], rbp
0x18002502f  inc     r8
0x180025032  cmp     [rax+r8*2], bp
0x180025037  jnz     short loc_18002502F
0x180025039  lea     rdx, [rsp+268h+var_228]
0x18002503e  mov     rcx, rdi
0x180025041  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180025046  mov     rax, rdi
0x180025049  mov     rcx, [rsp+268h+var_28]
0x180025051  xor     rcx, rsp; StackCookie
0x180025054  call    __security_check_cookie
0x180025059  mov     rbx, [rsp+268h+arg_10]
0x180025061  add     rsp, 250h
0x180025068  pop     rdi
0x180025069  pop     rsi
0x18002506a  pop     rbp
0x18002506b  retn
0x18002506c  mov     rcx, [rsp+268h]; this
0x180025074  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18002507b  mov     r9d, eax; char *
0x18002507e  mov     edx, 59h ; 'Y'; void *
0x180025083  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180025089  mov     rcx, [rsp+268h]; this
0x180025091  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180025098  mov     r9d, eax; char *
0x18002509b  mov     edx, 6Dh ; 'm'; void *
0x1800250a0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800250a6  mov     rcx, [rsp+268h]; this
0x1800250ae  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x1800250b5  mov     r9d, eax; char *
0x1800250b8  mov     edx, 63h ; 'c'; void *
0x1800250bd  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800250c3  mov     rcx, [rsp+268h]; this
0x1800250cb  lea     r9, aInvalidDatabas_0; "Invalid database name"
0x1800250d2  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x1800250d9  mov     edx, 72h ; 'r'; void *
0x1800250de  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```
