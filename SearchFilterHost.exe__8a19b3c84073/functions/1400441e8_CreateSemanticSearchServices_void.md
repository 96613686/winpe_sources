# CreateSemanticSearchServices(void)

- ea: `0x1400441e8`
- end: `0x140044336`
- name: `?CreateSemanticSearchServices@@YA?AV?$com_ptr_t@UIIndexerSemanticSearchServices@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400459e0`
- `0x140046770`
- `0x140046bc0`

## callees

- `0x1400198c4`
- `0x14001b858`
- `0x140033fb0`
- `0x1400441e8`
- `0x14004616c`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140044267`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140044267`

## string_xrefs

- `0x140044323`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x140044308`: `onecoreuap\base\appmodel\Search\common\include\SemanticVectorHelper.h`
- `0x1400442fc`: `Total duration to cocreate wsaifabricsvc %u\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall CreateSemanticSearchServices(_QWORD *a1)
{
  _QWORD *v1; // rsi
  unsigned int v2; // ebx
  unsigned int v3; // r14d
  int v4; // ebx
  HRESULT v5; // eax
  LPVOID v6; // rax
  __int64 v7; // rcx
  _QWORD *result; // rax
  int v9; // ebx
  int ppv; // [rsp+20h] [rbp-38h]
  unsigned int v11; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _QWORD *v13; // [rsp+60h] [rbp+8h] BYREF
  int v14; // [rsp+68h] [rbp+10h]
  LPVOID v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v13 = a1;
  v1 = a1;
  v11 = 0;
  std::chrono::steady_clock::now(&v16);
  *v1 = 0;
  v2 = 1;
  v3 = 1;
  v14 = 1;
  while ( 2 )
  {
    try
    {
      while ( !*v1 && v3 <= 3 )
      {
        v4 = v2 | 4;
        v15 = 0;
        v5 = CoCreateInstance(
               &GUID_879d4670_5a0c_4467_bbc4_30c943755bf8,
               0,
               4u,
               &GUID_e621e0fa_3b69_48e6_bc9f_d65ad301cb14,
               &v15);
        if ( v5 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v5,
            ppv);
        v2 = v4 & 0xFFFFFFF9 | 2;
        v11 = v2;
        v6 = v15;
        v15 = 0;
        v7 = *v1;
        *v1 = v6;
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        wil::com_ptr_t<IFilter,wil::err_exception_policy>::~com_ptr_t<IFilter,wil::err_exception_policy>((__int64 *)&v15);
      }
      std::chrono::steady_clock::now(&v13);
      SearchIndexerDebug::Verbose(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\SemanticVectorHelper.h",
        (const wchar_t *)0x62,
        (unsigned int)L"Total duration to cocreate wsaifabricsvc %u\n",
        (const wchar_t *)(((__int64)v13 - v16) / 1000));
      result = v1;
    }
    catch ( ... )
    {
      v9 = v14;
      if ( v14 == 3 )
        throw;
      Sleep(10 * v14);
      v14 = v9 + 1;
      v1 = v13;
      v3 = v9 + 1;
      v2 = v11;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1400441e8  mov     rax, rsp
0x1400441eb  mov     [rax+8], rcx
0x1400441ef  push    rbx
0x1400441f0  push    rsi
0x1400441f1  push    r14
0x1400441f3  sub     rsp, 40h
0x1400441f7  mov     qword ptr [rax-20h], 0FFFFFFFFFFFFFFFEh
0x1400441ff  mov     rsi, rcx
0x140044202  mov     dword ptr [rax-28h], 0
0x140044209  lea     rcx, [rax+20h]
0x14004420d  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x140044212  mov     qword ptr [rsi], 0
0x140044219  mov     ebx, 1
0x14004421e  mov     r14d, ebx
0x140044221  mov     [rsp+58h+arg_8], ebx
0x140044225  cmp     qword ptr [rsi], 0
0x140044229  jnz     loc_1400442CD
0x14004422f  cmp     r14d, 3
0x140044233  ja      loc_1400442CD
0x140044239  or      ebx, 4
0x14004423c  mov     [rsp+58h+var_28], ebx
0x140044240  mov     [rsp+58h+arg_10], 0
0x140044249  lea     rax, [rsp+58h+arg_10]
0x14004424e  mov     qword ptr [rsp+58h+ppv], rax; int
0x140044253  lea     r9, _GUID_e621e0fa_3b69_48e6_bc9f_d65ad301cb14; riid
0x14004425a  xor     edx, edx; pUnkOuter
0x14004425c  lea     r8d, [rdx+4]; dwClsContext
0x140044260  lea     rcx, _GUID_879d4670_5a0c_4467_bbc4_30c943755bf8; rclsid
0x140044267  call    cs:__imp_CoCreateInstance
0x14004426d  mov     rcx, [rsp+58h]; this
0x140044272  test    eax, eax
0x140044274  js      loc_140044320
0x14004427a  and     ebx, 0FFFFFFFBh
0x14004427d  or      ebx, 2
0x140044280  mov     [rsp+58h+var_28], ebx
0x140044284  mov     rax, [rsp+58h+arg_10]
0x140044289  mov     [rsp+58h+arg_10], 0
0x140044292  mov     rcx, [rsi]
0x140044295  mov     [rsi], rax
0x140044298  test    rcx, rcx
0x14004429b  jz      short loc_1400442AA
0x14004429d  mov     rax, [rcx]
0x1400442a0  mov     rax, [rax+10h]
0x1400442a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400442a9  nop
0x1400442aa  lea     rcx, [rsp+58h+arg_10]
0x1400442af  call    ??1?$com_ptr_t@UIFilter@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFilter,wil::err_exception_policy>::~com_ptr_t<IFilter,wil::err_exception_policy>(void)
0x1400442b4  nop
0x1400442b5  jmp     loc_140044225
0x1400442ba  mov     rsi, [rsp+58h+arg_0]
0x1400442bf  mov     r14d, [rsp+58h+arg_8]
0x1400442c4  mov     ebx, [rsp+58h+var_28]
0x1400442c8  jmp     loc_140044225
0x1400442cd  lea     rcx, [rsp+58h+arg_0]
0x1400442d2  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1400442d7  mov     rcx, [rsp+58h+arg_0]
0x1400442dc  sub     rcx, [rsp+58h+arg_18]
0x1400442e1  mov     rax, 20C49BA5E353F7CFh
0x1400442eb  imul    rcx
0x1400442ee  sar     rdx, 7
0x1400442f2  mov     r9, rdx
0x1400442f5  shr     r9, 3Fh
0x1400442f9  add     r9, rdx; wchar_t *
0x1400442fc  lea     r8, aTotalDurationT; "Total duration to cocreate wsaifabricsv"...
0x140044303  mov     edx, 62h ; 'b'; wchar_t *
0x140044308  lea     rcx, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14004430f  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x140044314  mov     rax, rsi
0x140044317  add     rsp, 40h
0x14004431b  pop     r14
0x14004431d  pop     rsi
0x14004431e  pop     rbx
0x14004431f  retn
0x140044320  mov     r9d, eax; char *
0x140044323  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14004432a  mov     edx, 1CBEh; void *
0x14004432f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
