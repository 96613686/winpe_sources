# wil::init_once_nothrow<_lambda_c01e51b825b5be6aac6ea6e913b52d50_>(_RTL_RUN_ONCE &,_lambda_c01e51b825b5be6aac6ea6e913b52d50_,bool *)

- ea: `0x180083274`
- end: `0x180083370`
- name: `??$init_once_nothrow@V_lambda_c01e51b825b5be6aac6ea6e913b52d50_@@@wil@@YAJAEAT_RTL_RUN_ONCE@@V_lambda_c01e51b825b5be6aac6ea6e913b52d50_@@PEA_N@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18008323c`

## callees

- `0x18000a9cc`
- `0x180010a90`
- `0x180083274`
- `0x180083378`
- `0x180095600`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180083299`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180083299`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008334a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180083363`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18008334a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180083363`

## string_xrefs

- `0x1800832e8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 __fastcall wil::init_once_nothrow<_lambda_c01e51b825b5be6aac6ea6e913b52d50_>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const char *v3; // r9
  int v5; // eax
  __int64 v6; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v9 = 0;
  if ( !InitOnceBeginInitialize(&stru_180190128, 0, &v9, 0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( v9 )
  {
    v10 = 0;
    v5 = Microsoft::WRL::Details::MakeAndInitialize<CRootProxyAudioObjectActivator,CRootProxyAudioObjectActivator,>(&v10);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
        (const char *)(unsigned int)v5,
        v7);
      qword_18018FCA8 = 0;
LABEL_9:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)0x8000FFFFLL, v7);
      InitOnceComplete(&stru_180190128, 4u, 0);
      return 2147549183LL;
    }
    v6 = v10;
    if ( v10 )
      v6 = v10 + 8;
    qword_18018FCA8 = v6;
    if ( !v6 )
      goto LABEL_9;
    InitOnceComplete(&stru_180190128, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180083274  mov     rax, rsp
0x180083277  mov     [rax+18h], r8
0x18008327b  mov     [rax+10h], dl
0x18008327e  sub     rsp, 28h
0x180083282  mov     dword ptr [rax+10h], 0
0x180083289  xor     r9d, r9d; lpContext
0x18008328c  lea     r8, [rax+10h]; fPending
0x180083290  xor     edx, edx; dwFlags
0x180083292  lea     rcx, stru_180190128; lpInitOnce
0x180083299  call    cs:__imp_InitOnceBeginInitialize
0x18008329f  test    eax, eax
0x1800832a1  jnz     short loc_1800832BE
0x1800832a3  mov     rcx, [rsp+28h]; this
0x1800832a8  lea     r8, aWil; "wil"
0x1800832af  mov     edx, 37Ah; void *
0x1800832b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800832b9  jmp     loc_18008336B
0x1800832be  cmp     [rsp+28h+arg_8], 0
0x1800832c3  jz      loc_180083369
0x1800832c9  mov     [rsp+28h+arg_10], 0
0x1800832d2  lea     rcx, [rsp+28h+arg_10]
0x1800832d7  call    ??$MakeAndInitialize@VCRootProxyAudioObjectActivator@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCRootProxyAudioObjectActivator@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CRootProxyAudioObjectActivator,CRootProxyAudioObjectActivator,>(CRootProxyAudioObjectActivator * *)
0x1800832dc  test    eax, eax
0x1800832de  jns     short loc_180083306
0x1800832e0  mov     rcx, [rsp+28h]; this
0x1800832e5  mov     r9d, eax; char *
0x1800832e8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800832ef  mov     edx, 146h; void *
0x1800832f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800832f9  mov     cs:qword_18018FCA8, 0
0x180083304  jmp     short loc_180083320
0x180083306  mov     rax, [rsp+28h+arg_10]
0x18008330b  test    rax, rax
0x18008330e  jz      short loc_180083314
0x180083310  add     rax, 8
0x180083314  mov     cs:qword_18018FCA8, rax
0x18008331b  test    rax, rax
0x18008331e  jnz     short loc_180083357
0x180083320  mov     rcx, [rsp+28h]; this
0x180083325  mov     r9d, 8000FFFFh; char *
0x18008332b  lea     r8, aWil; "wil"
0x180083332  mov     edx, 37Fh; void *
0x180083337  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008333c  xor     r8d, r8d; lpContext
0x18008333f  lea     edx, [r8+4]; dwFlags
0x180083343  lea     rcx, stru_180190128; lpInitOnce
0x18008334a  call    cs:__imp_InitOnceComplete
0x180083350  mov     eax, 8000FFFFh
0x180083355  jmp     short loc_18008336B
0x180083357  xor     r8d, r8d; lpContext
0x18008335a  xor     edx, edx; dwFlags
0x18008335c  lea     rcx, stru_180190128; lpInitOnce
0x180083363  call    cs:__imp_InitOnceComplete
0x180083369  xor     eax, eax
0x18008336b  add     rsp, 28h
0x18008336f  retn
```
