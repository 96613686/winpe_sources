# UiaManagerCrossMachineProxy::GetPropertyValue(HWND__ *,int,tagVARIANT *)

- ea: `0x1800591c0`
- end: `0x1800593c0`
- name: `?GetPropertyValue@UiaManagerCrossMachineProxy@@UEAAJPEAUHWND__@@HPEAUtagVARIANT@@@Z`
- size: `512`
- prototype: `int(UiaManagerCrossMachineProxy *__hidden this, HWND, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callees

- `0x1800078ec`
- `0x18000f968`
- `0x180012f28`
- `0x180016c4c`
- `0x180026094`
- `0x18002c1c0`
- `0x180031540`
- `0x180043680`
- `0x180057cb8`
- `0x180058e38`
- `0x1800591c0`
- `0x18007a20c`
- `0x18007a340`
- `0x18007a394`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800592e2`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800592e2`
- `OLEAUT32!__imp_VariantInit` at `0x1800591f8`
- `OLEAUT32!__imp_VariantInit` at `0x18005924f`
- `OLEAUT32!__imp_VariantInit` at `0x18005933b`
- `OLEAUT32!__imp_VariantInit` at `0x1800591f8`
- `OLEAUT32!__imp_VariantInit` at `0x18005924f`
- `OLEAUT32!__imp_VariantInit` at `0x18005933b`
- `OLEAUT32!__imp_VariantClear` at `0x180059264`
- `OLEAUT32!__imp_VariantClear` at `0x180059350`
- `OLEAUT32!__imp_VariantClear` at `0x180059264`
- `OLEAUT32!__imp_VariantClear` at `0x180059350`

## string_xrefs

- `0x180059287`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`
- `0x18005937e`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall UiaManagerCrossMachineProxy::GetPropertyValue(
        UiaManagerCrossMachineProxy *this,
        HWND a2,
        int a3,
        struct tagVARIANT *a4)
{
  int PropertyStatusCode; // eax
  VARIANTARG *v9; // rax
  __int128 v10; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  unsigned __int64 HwndPropertyIndex; // rdx
  int v14; // eax
  VARIANTARG *v15; // rax
  __int128 v16; // xmm6
  IRecordInfo *v17; // xmm7_8
  int v18; // [rsp+20h] [rbp-158h]
  VARIANTARG pvarg; // [rsp+28h] [rbp-150h] BYREF
  _BYTE v20[40]; // [rsp+40h] [rbp-138h] BYREF
  _BYTE v21[40]; // [rsp+68h] [rbp-110h] BYREF
  _BYTE v22[48]; // [rsp+90h] [rbp-E8h] BYREF
  __int64 v23; // [rsp+C0h] [rbp-B8h]
  __int64 v24; // [rsp+C8h] [rbp-B0h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  VariantInit(a4);
  UiaManagerTraceLoggingProvider::CrossMachineProxyGetPropertyValue(a2, a3);
  HwndInfoCache::GetPropertyValue((UiaManagerCrossMachineProxy *)((char *)this + 528));
  if ( v20[32] )
  {
    PropertyStatusCode = CachedCrossMachineHwndPropertyValue::GetPropertyStatusCode((CachedCrossMachineHwndPropertyValue *)v20);
    if ( PropertyStatusCode < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2F1,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
        (const char *)(unsigned int)PropertyStatusCode,
        v18);
    v9 = (VARIANTARG *)CachedCrossMachineHwndPropertyValue::DetachValue(v20, &pvarg);
    v10 = *(_OWORD *)&v9->vt;
    pRecInfo = v9->pRecInfo;
    VariantInit(v9);
    *(_OWORD *)&a4->vt = v10;
    a4->pRecInfo = pRecInfo;
    VariantClear(&pvarg);
    std::_Optional_destruct_base<CachedCrossMachineHwndPropertyValue,0>::~_Optional_destruct_base<CachedCrossMachineHwndPropertyValue,0>(v20);
    return 0;
  }
  else
  {
    std::_Optional_destruct_base<CachedCrossMachineHwndPropertyValue,0>::~_Optional_destruct_base<CachedCrossMachineHwndPropertyValue,0>(v20);
    UiaManagerCrossMachineProxy::ExecuteGetHwndInfoService((char *)this - 48, v22, a2);
    HwndPropertyIndex = BasicHwndUtils::GetHwndPropertyIndex(a3);
    if ( (v24 - v23) >> 5 <= HwndPropertyIndex )
      std::_Xout_of_range("invalid vector subscript");
    CachedCrossMachineHwndPropertyValue::CachedCrossMachineHwndPropertyValue(v21, v23 + 32 * HwndPropertyIndex);
    UiaManagerCrossMachineProxy::InsertHwndCacheEntry(
      (UiaManagerCrossMachineProxy *)((char *)this - 48),
      a2,
      (struct HwndInfoPayload *)v22);
    v14 = CachedCrossMachineHwndPropertyValue::GetPropertyStatusCode((CachedCrossMachineHwndPropertyValue *)v21);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30A,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxy.cpp",
        (const char *)(unsigned int)v14,
        v18);
    v15 = (VARIANTARG *)CachedCrossMachineHwndPropertyValue::DetachValue(v21, &pvarg);
    v16 = *(_OWORD *)&v15->vt;
    v17 = v15->pRecInfo;
    VariantInit(v15);
    *(_OWORD *)&a4->vt = v16;
    a4->pRecInfo = v17;
    VariantClear(&pvarg);
    std::_Variant_base<long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>>::_Destroy(v21);
    GetHwndInfoService::ResponsePayload::~ResponsePayload((GetHwndInfoService::ResponsePayload *)v22);
    return 0;
  }
}

```

## disassembly

```asm
0x1800591c0  mov     rax, rsp
0x1800591c3  push    rbx
0x1800591c4  push    rsi
0x1800591c5  push    rdi
0x1800591c6  push    r14
0x1800591c8  sub     rsp, 158h
0x1800591cf  movaps  xmmword ptr [rax-38h], xmm6
0x1800591d3  movaps  xmmword ptr [rax-48h], xmm7
0x1800591d7  mov     rax, cs:__security_cookie
0x1800591de  xor     rax, rsp
0x1800591e1  mov     [rsp+178h+var_58], rax
0x1800591e9  mov     r14, r9
0x1800591ec  mov     esi, r8d
0x1800591ef  mov     rbx, rdx
0x1800591f2  mov     rdi, rcx
0x1800591f5  mov     rcx, r9; pvarg
0x1800591f8  call    cs:__imp_VariantInit
0x1800591fe  mov     edx, esi; int
0x180059200  mov     rcx, rbx; HWND
0x180059203  call    ?CrossMachineProxyGetPropertyValue@UiaManagerTraceLoggingProvider@@SAXPEAUHWND__@@H@Z; UiaManagerTraceLoggingProvider::CrossMachineProxyGetPropertyValue(HWND__ *,int)
0x180059208  lea     rcx, [rdi+210h]
0x18005920f  mov     r9d, esi
0x180059212  mov     r8, rbx
0x180059215  lea     rdx, [rsp+178h+var_138]
0x18005921a  call    ?GetPropertyValue@HwndInfoCache@@QEBA?AV?$optional@VCachedCrossMachineHwndPropertyValue@@@std@@PEAUHWND__@@H@Z; HwndInfoCache::GetPropertyValue(HWND__ *,int)
0x18005921f  nop
0x180059220  cmp     [rsp+178h+var_118], 0
0x180059225  jz      short loc_180059299
0x180059227  lea     rcx, [rsp+178h+var_138]; this
0x18005922c  call    ?GetPropertyStatusCode@CachedCrossMachineHwndPropertyValue@@QEBAJXZ; CachedCrossMachineHwndPropertyValue::GetPropertyStatusCode(void)
0x180059231  test    eax, eax
0x180059233  js      short loc_18005927C
0x180059235  lea     rdx, [rsp+178h+pvarg]
0x18005923a  lea     rcx, [rsp+178h+var_138]
0x18005923f  call    ?DetachValue@CachedCrossMachineHwndPropertyValue@@QEAA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@XZ; CachedCrossMachineHwndPropertyValue::DetachValue(void)
0x180059244  movups  xmm6, xmmword ptr [rax]
0x180059247  movsd   xmm7, qword ptr [rax+10h]
0x18005924c  mov     rcx, rax; pvarg
0x18005924f  call    cs:__imp_VariantInit
0x180059255  movups  xmmword ptr [r14], xmm6
0x180059259  movsd   qword ptr [r14+10h], xmm7
0x18005925f  lea     rcx, [rsp+178h+pvarg]; pvarg
0x180059264  call    cs:__imp_VariantClear
0x18005926a  nop
0x18005926b  lea     rcx, [rsp+178h+var_138]
0x180059270  call    ??1?$_Optional_destruct_base@VCachedCrossMachineHwndPropertyValue@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<CachedCrossMachineHwndPropertyValue,0>::~_Optional_destruct_base<CachedCrossMachineHwndPropertyValue,0>(void)
0x180059275  xor     eax, eax
0x180059277  jmp     loc_180059394
0x18005927c  mov     rcx, [rsp+178h]; this
0x180059284  mov     r9d, eax; char *
0x180059287  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x18005928e  mov     edx, 2F1h; void *
0x180059293  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180059299  lea     rcx, [rsp+178h+var_138]
0x18005929e  call    ??1?$_Optional_destruct_base@VCachedCrossMachineHwndPropertyValue@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<CachedCrossMachineHwndPropertyValue,0>::~_Optional_destruct_base<CachedCrossMachineHwndPropertyValue,0>(void)
0x1800592a3  mov     r8, rbx
0x1800592a6  lea     rdx, [rsp+178h+var_E8]
0x1800592ae  lea     rcx, [rdi-30h]
0x1800592b2  call    ?ExecuteGetHwndInfoService@UiaManagerCrossMachineProxy@@AEAA?AUHwndInfoPayload@@PEAUHWND__@@@Z; UiaManagerCrossMachineProxy::ExecuteGetHwndInfoService(HWND__ *)
0x1800592b7  nop
0x1800592b8  mov     ecx, esi; int
0x1800592ba  call    ?GetHwndPropertyIndex@BasicHwndUtils@@SA_KH@Z; BasicHwndUtils::GetHwndPropertyIndex(int)
0x1800592bf  mov     rdx, rax
0x1800592c2  mov     rax, [rsp+178h+var_B0]
0x1800592ca  sub     rax, [rsp+178h+var_B8]
0x1800592d2  sar     rax, 5
0x1800592d6  cmp     rax, rdx
0x1800592d9  ja      short loc_1800592E8
0x1800592db  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x1800592e2  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800592e8  shl     rdx, 5
0x1800592ec  add     rdx, [rsp+178h+var_B8]
0x1800592f4  lea     rcx, [rsp+178h+var_110]
0x1800592f9  call    ??0CachedCrossMachineHwndPropertyValue@@QEAA@AEBV?$variant@JV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@@Z; CachedCrossMachineHwndPropertyValue::CachedCrossMachineHwndPropertyValue(std::variant<long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>> const &)
0x1800592fe  nop
0x1800592ff  lea     r8, [rsp+178h+var_E8]; struct HwndInfoPayload *
0x180059307  mov     rdx, rbx; HWND
0x18005930a  lea     rcx, [rdi-30h]; this
0x18005930e  call    ?InsertHwndCacheEntry@UiaManagerCrossMachineProxy@@AEAAXPEAUHWND__@@AEAUHwndInfoPayload@@@Z; UiaManagerCrossMachineProxy::InsertHwndCacheEntry(HWND__ *,HwndInfoPayload &)
0x180059313  lea     rcx, [rsp+178h+var_110]; this
0x180059318  call    ?GetPropertyStatusCode@CachedCrossMachineHwndPropertyValue@@QEBAJXZ; CachedCrossMachineHwndPropertyValue::GetPropertyStatusCode(void)
0x18005931d  test    eax, eax
0x18005931f  js      short loc_180059373
0x180059321  lea     rdx, [rsp+178h+pvarg]
0x180059326  lea     rcx, [rsp+178h+var_110]
0x18005932b  call    ?DetachValue@CachedCrossMachineHwndPropertyValue@@QEAA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@XZ; CachedCrossMachineHwndPropertyValue::DetachValue(void)
0x180059330  movups  xmm6, xmmword ptr [rax]
0x180059333  movsd   xmm7, qword ptr [rax+10h]
0x180059338  mov     rcx, rax; pvarg
0x18005933b  call    cs:__imp_VariantInit
0x180059341  movups  xmmword ptr [r14], xmm6
0x180059345  movsd   qword ptr [r14+10h], xmm7
0x18005934b  lea     rcx, [rsp+178h+pvarg]; pvarg
0x180059350  call    cs:__imp_VariantClear
0x180059356  nop
0x180059357  lea     rcx, [rsp+178h+var_110]
0x18005935c  call    ?_Destroy@?$_Variant_base@JV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@std@@QEAAXXZ; std::_Variant_base<long,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>>::_Destroy(void)
0x180059361  nop
0x180059362  lea     rcx, [rsp+178h+var_E8]; this
0x18005936a  call    ??1ResponsePayload@GetHwndInfoService@@QEAA@XZ; GetHwndInfoService::ResponsePayload::~ResponsePayload(void)
0x18005936f  xor     eax, eax
0x180059371  jmp     short loc_180059394
0x180059373  mov     rcx, [rsp+178h]; this
0x18005937b  mov     r9d, eax; char *
0x18005937e  lea     r8, aOnecoreWindows_16; "onecore\\windows\\accessibletech\\uiama"...
0x180059385  mov     edx, 30Ah; void *
0x18005938a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180059390  mov     eax, [rsp+178h+var_158]
0x180059394  mov     rcx, [rsp+178h+var_58]
0x18005939c  xor     rcx, rsp; StackCookie
0x18005939f  call    __security_check_cookie
0x1800593a4  lea     r11, [rsp+178h+var_20]
0x1800593ac  movaps  xmm6, xmmword ptr [r11-18h]
0x1800593b1  movaps  xmm7, xmmword ptr [r11-28h]
0x1800593b6  mov     rsp, r11
0x1800593b9  pop     r14
0x1800593bb  pop     rdi
0x1800593bc  pop     rsi
0x1800593bd  pop     rbx
0x1800593be  retn
```
