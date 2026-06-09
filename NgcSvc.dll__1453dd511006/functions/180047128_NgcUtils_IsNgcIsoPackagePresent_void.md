# NgcUtils::IsNgcIsoPackagePresent(void)

- ea: `0x180047128`
- end: `0x1800471ec`
- name: `?IsNgcIsoPackagePresent@NgcUtils@@YA_NXZ`
- size: `196`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004a01c`

## callees

- `0x18003601c`
- `0x180047128`
- `0x1800471f4`
- `0x180047228`
- `0x1800481b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047181`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180047181`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800471c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800471df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800471c4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800471df`

## string_xrefs

- `0x180047147`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x1800471a2`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

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
0x180047128  sub     rsp, 38h
0x18004712c  mov     [rsp+38h+arg_0], 0
0x180047131  lea     rcx, [rsp+38h+arg_0]; this
0x180047136  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18004713b  mov     rcx, [rsp+38h]; this
0x180047140  test    eax, eax
0x180047142  jns     short loc_18004715A
0x180047144  mov     r9d, eax; char *
0x180047147  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18004714e  mov     edx, 0A0h; void *
0x180047153  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047158  jmp     short loc_1800471BD
0x18004715a  mov     [rsp+38h+arg_8], 0
0x180047163  lea     rax, [rsp+38h+arg_8]
0x180047168  mov     [rsp+38h+ppv], rax; ppv
0x18004716d  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x180047174  xor     edx, edx; pUnkOuter
0x180047176  lea     r8d, [rdx+1]; dwClsContext
0x18004717a  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x180047181  call    cs:__imp_CoCreateInstance
0x180047187  test    eax, eax
0x180047189  jns     short loc_1800471CE
0x18004718b  mov     rcx, [rsp+38h]; this
0x180047190  lea     rax, aNgcisoctnrCoul; "NgcIsoCtnr could not be instantiated."
0x180047197  mov     [rsp+38h+ppv], rax; int
0x18004719c  mov     r9d, 80090029h; char *
0x1800471a2  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800471a9  mov     edx, 0A9h; void *
0x1800471ae  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800471b3  lea     rcx, [rsp+38h+arg_8]
0x1800471b8  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x1800471bd  cmp     [rsp+38h+arg_0], 0
0x1800471c2  jz      short loc_1800471CA
0x1800471c4  call    cs:__imp_CoUninitialize
0x1800471ca  xor     al, al
0x1800471cc  jmp     short loc_1800471E7
0x1800471ce  lea     rcx, [rsp+38h+arg_8]
0x1800471d3  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x1800471d8  cmp     [rsp+38h+arg_0], 0
0x1800471dd  jz      short loc_1800471E5
0x1800471df  call    cs:__imp_CoUninitialize
0x1800471e5  mov     al, 1
0x1800471e7  add     rsp, 38h
0x1800471eb  retn
```
