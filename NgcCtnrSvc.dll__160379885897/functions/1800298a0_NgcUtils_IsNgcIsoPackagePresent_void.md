# NgcUtils::IsNgcIsoPackagePresent(void)

- ea: `0x1800298a0`
- end: `0x180029977`
- name: `?IsNgcIsoPackagePresent@NgcUtils@@YA_NXZ`
- size: `215`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059e8c`

## callees

- `0x18000c688`
- `0x1800134a0`
- `0x1800298a0`
- `0x180029980`
- `0x1800299b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029942`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029963`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029942`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029963`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800298f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800298f9`

## string_xrefs

- `0x1800298bf`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x180029920`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall NgcUtils::IsNgcIsoPackagePresent(NgcUtils *this, unsigned int a2)
{
  int v2; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v7; // [rsp+40h] [rbp+8h] BYREF
  LPVOID v8; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  v2 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)&v7, a2);
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)(unsigned int)v2,
      ppv);
LABEL_5:
    if ( v7 )
      CoUninitialize();
    return 0;
  }
  v8 = 0;
  if ( CoCreateInstance(
         &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
         0,
         1u,
         &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
         &v8) < 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)0x80090029LL,
      (int)"NgcIsoCtnr could not be instantiated.",
      v5);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v8);
    goto LABEL_5;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v8);
  if ( v7 )
    CoUninitialize();
  return 1;
}

```

## disassembly

```asm
0x1800298a0  sub     rsp, 38h
0x1800298a4  mov     [rsp+38h+arg_0], 0
0x1800298a9  lea     rcx, [rsp+38h+arg_0]; this
0x1800298ae  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x1800298b3  mov     rcx, [rsp+38h]; this
0x1800298b8  test    eax, eax
0x1800298ba  jns     short loc_1800298D2
0x1800298bc  mov     r9d, eax; char *
0x1800298bf  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800298c6  mov     edx, 0A0h; void *
0x1800298cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800298d0  jmp     short loc_18002993B
0x1800298d2  mov     [rsp+38h+arg_8], 0
0x1800298db  lea     rax, [rsp+38h+arg_8]
0x1800298e0  mov     [rsp+38h+ppv], rax; ppv
0x1800298e5  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x1800298ec  xor     edx, edx; pUnkOuter
0x1800298ee  lea     r8d, [rdx+1]; dwClsContext
0x1800298f2  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x1800298f9  call    cs:__imp_CoCreateInstance
0x180029900  nop     dword ptr [rax+rax+00h]
0x180029905  test    eax, eax
0x180029907  jns     short loc_180029952
0x180029909  mov     rcx, [rsp+38h]; this
0x18002990e  lea     rax, aNgcisoctnrCoul; "NgcIsoCtnr could not be instantiated."
0x180029915  mov     [rsp+38h+ppv], rax; int
0x18002991a  mov     r9d, 80090029h; char *
0x180029920  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180029927  mov     edx, 0A9h; void *
0x18002992c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180029931  lea     rcx, [rsp+38h+arg_8]
0x180029936  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18002993b  cmp     [rsp+38h+arg_0], 0
0x180029940  jz      short loc_18002994E
0x180029942  call    cs:__imp_CoUninitialize
0x180029949  nop     dword ptr [rax+rax+00h]
0x18002994e  xor     al, al
0x180029950  jmp     short loc_180029971
0x180029952  lea     rcx, [rsp+38h+arg_8]
0x180029957  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18002995c  cmp     [rsp+38h+arg_0], 0
0x180029961  jz      short loc_18002996F
0x180029963  call    cs:__imp_CoUninitialize
0x18002996a  nop     dword ptr [rax+rax+00h]
0x18002996f  mov     al, 1
0x180029971  add     rsp, 38h
0x180029975  retn
```
