# GetTaskService(void)

- ea: `0x180018350`
- end: `0x180018446`
- name: `?GetTaskService@@YA?AV?$ComPtr@UITaskService@@@WRL@Microsoft@@XZ`
- size: `246`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001b728`
- `0x18001b83c`

## callees

- `0x18000a7fc`
- `0x180018350`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018397`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018397`

## string_xrefs

- `0x18001841b`: `onecore\internal\shell\inc\taskutils.h`
- `0x180018434`: `onecore\internal\shell\inc\taskutils.h`

## pseudocode

```c
LPVOID *__fastcall GetTaskService(LPVOID *a1)
{
  HRESULT Instance; // eax
  LPVOID v3; // rcx
  int v4; // eax
  int ppv; // [rsp+20h] [rbp-49h]
  int v7[4]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v8; // [rsp+50h] [rbp-19h]
  __int128 v9; // [rsp+60h] [rbp-9h] BYREF
  __int64 v10; // [rsp+70h] [rbp+7h]
  __int128 v11; // [rsp+80h] [rbp+17h] BYREF
  __int64 v12; // [rsp+90h] [rbp+27h]
  __int128 v13; // [rsp+A0h] [rbp+37h] BYREF
  __int64 v14; // [rsp+B0h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a1 = 0;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, a1);
  if ( Instance < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\internal\\shell\\inc\\taskutils.h",
      (const char *)(unsigned int)Instance,
      ppv);
  v3 = *a1;
  *(_OWORD *)v7 = xmmword_18002D0F0;
  v8 = 0;
  v9 = xmmword_18002D0F0;
  v10 = 0;
  v11 = xmmword_18002D0F0;
  v12 = 0;
  v13 = xmmword_18002D0F0;
  v14 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v3 + 80LL))(
         v3,
         &v13,
         &v11,
         &v9);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\internal\\shell\\inc\\taskutils.h",
      (const char *)(unsigned int)v4,
      (int)v7);
  return a1;
}

```

## disassembly

```asm
0x180018350  mov     [rsp-8+arg_8], rbx
0x180018355  mov     [rsp-8+arg_0], rcx
0x18001835a  push    rbp
0x18001835b  lea     rbp, [rsp-57h]
0x180018360  sub     rsp, 0C0h
0x180018367  mov     rbx, rcx
0x18001836a  mov     [rbp+57h+var_90], 0
0x180018371  mov     qword ptr [rcx], 0
0x180018378  mov     r8d, 1; dwClsContext
0x18001837e  mov     [rbp+57h+var_90], r8d
0x180018382  mov     qword ptr [rsp+0C0h+ppv], rcx; int
0x180018387  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18001838e  xor     edx, edx; pUnkOuter
0x180018390  lea     rcx, CLSID_TaskScheduler; rclsid
0x180018397  call    cs:__imp_CoCreateInstance
0x18001839d  test    eax, eax
0x18001839f  js      loc_18001842D
0x1800183a5  mov     rcx, [rbx]
0x1800183a8  movups  xmm1, cs:xmmword_18002D0F0
0x1800183af  movsd   xmm0, cs:qword_18002D100
0x1800183b7  movaps  xmmword ptr [rbp+57h+var_80], xmm1
0x1800183bb  movsd   [rbp+57h+var_70], xmm0
0x1800183c0  movaps  [rbp+57h+var_60], xmm1
0x1800183c4  movsd   [rbp+57h+var_50], xmm0
0x1800183c9  movaps  [rbp+57h+var_40], xmm1
0x1800183cd  movsd   [rbp+57h+var_30], xmm0
0x1800183d2  movaps  [rbp+57h+var_20], xmm1
0x1800183d6  movsd   [rbp+57h+var_10], xmm0
0x1800183db  mov     rax, [rcx]
0x1800183de  lea     rdx, [rbp+57h+var_80]
0x1800183e2  mov     qword ptr [rsp+0C0h+ppv], rdx; int
0x1800183e7  lea     r9, [rbp+57h+var_60]
0x1800183eb  lea     r8, [rbp+57h+var_40]
0x1800183ef  lea     rdx, [rbp+57h+var_20]
0x1800183f3  mov     rax, [rax+50h]
0x1800183f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183fc  test    eax, eax
0x1800183fe  js      short loc_180018414
0x180018400  mov     rax, rbx
0x180018403  mov     rbx, [rsp+0C0h+arg_8]
0x18001840b  add     rsp, 0C0h
0x180018412  pop     rbp
0x180018413  retn
0x180018414  mov     rcx, [rbp+5Fh]; this
0x180018418  mov     r9d, eax; char *
0x18001841b  lea     r8, aOnecoreInterna_8; "onecore\\internal\\shell\\inc\\taskutil"...
0x180018422  mov     edx, 1Ch; void *
0x180018427  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001842d  mov     rcx, [rbp+5Fh]; this
0x180018431  mov     r9d, eax; char *
0x180018434  lea     r8, aOnecoreInterna_8; "onecore\\internal\\shell\\inc\\taskutil"...
0x18001843b  mov     edx, 1Bh; void *
0x180018440  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
