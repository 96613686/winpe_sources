# CompletionCallback::Invoke(IDownloadJob *,IDownloadProgressChangedCallbackArgs *)

- ea: `0x180045800`
- end: `0x180045acb`
- name: `?Invoke@CompletionCallback@@UEAAJPEAUIDownloadJob@@PEAUIDownloadProgressChangedCallbackArgs@@@Z`
- size: `715`
- prototype: `__int64 __fastcall(CompletionCallback *__hidden this, struct IDownloadJob *, struct IDownloadProgressChangedCallbackArgs *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180045800`
- `0x180049a5c`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180045869`
- `msvcp_win!_Mtx_unlock` at `0x180045869`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004583c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004585a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004583c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004585a`
- `msvcp_win!_Mtx_lock` at `0x18004582d`
- `msvcp_win!_Mtx_lock` at `0x18004582d`

## string_xrefs

- `0x1800458a1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180045900`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004595a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800459c9`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180045a26`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CompletionCallback::Invoke(
        CompletionCallback *this,
        struct IDownloadJob *a2,
        struct IDownloadProgressChangedCallbackArgs *a3)
{
  __int64 v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // edi
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-50h]
  __int64 v21; // [rsp+30h] [rbp-40h] BYREF
  int v22; // [rsp+38h] [rbp-38h] BYREF
  int v23; // [rsp+3Ch] [rbp-34h] BYREF
  __int128 v24; // [rsp+40h] [rbp-30h] BYREF
  __int128 v25; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( _Mtx_lock((CompletionCallback *)((char *)this + 24)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)this + 25) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 25) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v5 = *((_QWORD *)this + 13);
  _Mtx_unlock((CompletionCallback *)((char *)this + 24));
  if ( v5 )
  {
    v21 = 0;
    v6 = ((__int64 (__fastcall *)(struct IDownloadProgressChangedCallbackArgs *, __int64 *))a3->lpVtbl->get_Progress)(
           a3,
           &v21);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v6,
        v20);
      v8 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      return v7;
    }
    v23 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 80LL))(v21, &v23);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v10,
        v20);
      v11 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      return v7;
    }
    v22 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 112LL))(v21, &v22);
    v7 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v12,
        v20);
      v13 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return v7;
    }
    v14 = 2;
    if ( v22 == 1 )
      v14 = 1;
    v25 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v21 + 88LL))(v21, &v25);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v15,
        v20);
      v16 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      return v7;
    }
    v24 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v21 + 96LL))(v21, &v24);
    v7 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v17,
        v20);
      v18 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      return v7;
    }
    CompletionCallback::_NotifyProgressChanged(
      (char *)this - 24,
      (unsigned int)(60 * v23 / 100),
      v14,
      *((_QWORD *)&v25 + 1),
      *((_QWORD *)&v24 + 1));
    v19 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180045800  mov     [rsp-18h+arg_8], rbx
0x180045805  mov     [rsp-18h+arg_18], rsi
0x18004580a  push    rbp
0x18004580b  push    rdi
0x18004580c  push    r14
0x18004580e  mov     rbp, rsp
0x180045811  sub     rsp, 70h
0x180045815  mov     rax, cs:__security_cookie
0x18004581c  xor     rax, rsp
0x18004581f  mov     [rbp+var_10], rax
0x180045823  mov     rsi, r8
0x180045826  mov     r14, rcx
0x180045829  add     rcx, 18h; _Mtx_t
0x18004582d  call    cs:__imp__Mtx_lock
0x180045833  test    eax, eax
0x180045835  jz      short loc_180045843
0x180045837  mov     ecx, 5
0x18004583c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180045842  int     3; Trap to Debugger
0x180045843  cmp     dword ptr [r14+64h], 7FFFFFFFh
0x18004584b  jnz     short loc_180045861
0x18004584d  mov     dword ptr [r14+64h], 7FFFFFFEh
0x180045855  mov     ecx, 6
0x18004585a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180045860  int     3; Trap to Debugger
0x180045861  mov     rbx, [r14+68h]
0x180045865  lea     rcx, [r14+18h]; _Mtx_t
0x180045869  call    cs:__imp__Mtx_unlock
0x18004586f  nop
0x180045870  test    rbx, rbx
0x180045873  jz      loc_180045AA8
0x180045879  mov     [rbp+var_40], 0
0x180045881  mov     rax, [rsi]
0x180045884  lea     rdx, [rbp+var_40]
0x180045888  mov     rcx, rsi
0x18004588b  mov     rax, [rax+38h]
0x18004588f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045894  mov     ebx, eax
0x180045896  test    eax, eax
0x180045898  jns     short loc_1800458D8
0x18004589a  mov     rcx, [rbp+18h]; this
0x18004589e  mov     r9d, eax; char *
0x1800458a1  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800458a8  mov     edx, 0EDh; void *
0x1800458ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800458b2  nop
0x1800458b3  mov     rcx, [rbp+var_40]
0x1800458b7  test    rcx, rcx
0x1800458ba  jz      short loc_1800458D1
0x1800458bc  mov     [rbp+var_40], 0
0x1800458c4  mov     rax, [rcx]
0x1800458c7  mov     rax, [rax+10h]
0x1800458cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458d0  nop
0x1800458d1  mov     eax, ebx
0x1800458d3  jmp     loc_180045AAA
0x1800458d8  mov     [rbp+var_34], 0
0x1800458df  mov     rcx, [rbp+var_40]
0x1800458e3  mov     rax, [rcx]
0x1800458e6  lea     rdx, [rbp+var_34]
0x1800458ea  mov     rax, [rax+50h]
0x1800458ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458f3  mov     ebx, eax
0x1800458f5  test    eax, eax
0x1800458f7  jns     short loc_180045932
0x1800458f9  mov     rcx, [rbp+18h]; this
0x1800458fd  mov     r9d, eax; char *
0x180045900  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180045907  mov     edx, 0F0h; void *
0x18004590c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045911  nop
0x180045912  mov     rcx, [rbp+var_40]
0x180045916  test    rcx, rcx
0x180045919  jz      short loc_180045930
0x18004591b  mov     [rbp+var_40], 0
0x180045923  mov     rax, [rcx]
0x180045926  mov     rax, [rax+10h]
0x18004592a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004592f  nop
0x180045930  jmp     short loc_1800458D1
0x180045932  mov     [rbp+var_38], 0
0x180045939  mov     rcx, [rbp+var_40]
0x18004593d  mov     rax, [rcx]
0x180045940  lea     rdx, [rbp+var_38]
0x180045944  mov     rax, [rax+70h]
0x180045948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004594d  mov     ebx, eax
0x18004594f  test    eax, eax
0x180045951  jns     short loc_18004598F
0x180045953  mov     rcx, [rbp+18h]; this
0x180045957  mov     r9d, eax; char *
0x18004595a  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180045961  mov     edx, 0F3h; void *
0x180045966  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004596b  nop
0x18004596c  mov     rcx, [rbp+var_40]
0x180045970  test    rcx, rcx
0x180045973  jz      short loc_18004598A
0x180045975  mov     [rbp+var_40], 0
0x18004597d  mov     rax, [rcx]
0x180045980  mov     rax, [rax+10h]
0x180045984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045989  nop
0x18004598a  jmp     loc_1800458D1
0x18004598f  mov     ecx, [rbp+var_38]
0x180045992  sub     ecx, 1
0x180045995  mov     edi, 2
0x18004599a  jnz     short loc_1800459A1
0x18004599c  mov     edi, 1
0x1800459a1  xorps   xmm0, xmm0
0x1800459a4  movups  [rbp+var_20], xmm0
0x1800459a8  mov     rcx, [rbp+var_40]
0x1800459ac  mov     rax, [rcx]
0x1800459af  lea     rdx, [rbp+var_20]
0x1800459b3  mov     rax, [rax+58h]
0x1800459b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459bc  mov     ebx, eax
0x1800459be  test    eax, eax
0x1800459c0  jns     short loc_1800459FE
0x1800459c2  mov     rcx, [rbp+18h]; this
0x1800459c6  mov     r9d, eax; char *
0x1800459c9  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800459d0  mov     edx, 0F7h; void *
0x1800459d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800459da  nop
0x1800459db  mov     rcx, [rbp+var_40]
0x1800459df  test    rcx, rcx
0x1800459e2  jz      short loc_1800459F9
0x1800459e4  mov     [rbp+var_40], 0
0x1800459ec  mov     rax, [rcx]
0x1800459ef  mov     rax, [rax+10h]
0x1800459f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459f8  nop
0x1800459f9  jmp     loc_1800458D1
0x1800459fe  xorps   xmm0, xmm0
0x180045a01  movups  [rbp+var_30], xmm0
0x180045a05  mov     rcx, [rbp+var_40]
0x180045a09  mov     rax, [rcx]
0x180045a0c  lea     rdx, [rbp+var_30]
0x180045a10  mov     rax, [rax+60h]
0x180045a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a19  mov     ebx, eax
0x180045a1b  test    eax, eax
0x180045a1d  jns     short loc_180045A5B
0x180045a1f  mov     rcx, [rbp+18h]; this
0x180045a23  mov     r9d, eax; char *
0x180045a26  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180045a2d  mov     edx, 0FAh; void *
0x180045a32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045a37  nop
0x180045a38  mov     rcx, [rbp+var_40]
0x180045a3c  test    rcx, rcx
0x180045a3f  jz      short loc_180045A56
0x180045a41  mov     [rbp+var_40], 0
0x180045a49  mov     rax, [rcx]
0x180045a4c  mov     rax, [rax+10h]
0x180045a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a55  nop
0x180045a56  jmp     loc_1800458D1
0x180045a5b  imul    ecx, [rbp+var_34], 3Ch ; '<'
0x180045a5f  mov     eax, 51EB851Fh
0x180045a64  imul    ecx
0x180045a66  sar     edx, 5
0x180045a69  mov     eax, edx
0x180045a6b  shr     eax, 1Fh
0x180045a6e  add     edx, eax
0x180045a70  lea     rcx, [r14-18h]
0x180045a74  mov     rax, qword ptr [rbp+var_30+8]
0x180045a78  mov     qword ptr [rsp+70h+var_50], rax
0x180045a7d  mov     r9, qword ptr [rbp+var_20+8]
0x180045a81  mov     r8d, edi
0x180045a84  call    ?_NotifyProgressChanged@CompletionCallback@@AEAAXIW4LanguagePackInstallProgressState@@_K1@Z; CompletionCallback::_NotifyProgressChanged(uint,LanguagePackInstallProgressState,unsigned __int64,unsigned __int64)
0x180045a89  nop
0x180045a8a  mov     rcx, [rbp+var_40]
0x180045a8e  test    rcx, rcx
0x180045a91  jz      short loc_180045AA8
0x180045a93  mov     [rbp+var_40], 0
0x180045a9b  mov     rax, [rcx]
0x180045a9e  mov     rax, [rax+10h]
0x180045aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045aa7  nop
0x180045aa8  xor     eax, eax
0x180045aaa  mov     rcx, [rbp+var_10]
0x180045aae  xor     rcx, rsp; StackCookie
0x180045ab1  call    __security_check_cookie
0x180045ab6  lea     r11, [rsp+70h+var_s0]
0x180045abb  mov     rbx, [r11+28h]
0x180045abf  mov     rsi, [r11+38h]
0x180045ac3  mov     rsp, r11
0x180045ac6  pop     r14
0x180045ac8  pop     rdi
0x180045ac9  pop     rbp
0x180045aca  retn
```
