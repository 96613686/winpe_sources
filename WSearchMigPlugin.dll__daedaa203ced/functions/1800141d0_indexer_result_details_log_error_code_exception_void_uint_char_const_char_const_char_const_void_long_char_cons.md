# indexer::result::details::log_error_code_exception(void *,uint,char const *,char const *,char const *,void *,long,char const *,char const *)

- ea: `0x1800141d0`
- end: `0x1800142dd`
- name: `?log_error_code_exception@details@result@indexer@@YAXPEAXIPEBD110J11@Z`
- size: `269`
- prototype: `void __fastcall(indexer::result::details *this, void *, __int64, const char *, const char *, const char *, wil::details *, __int64, const char *)`
- caller_count: `17`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180017048`
- `0x1800170af`
- `0x180017116`
- `0x18001717d`
- `0x1800171e4`
- `0x18001724b`
- `0x1800172b5`
- `0x18001731f`
- `0x180017389`
- `0x1800173e9`
- `0x180017495`
- `0x1800174ff`
- `0x180017569`
- `0x1800175d3`
- `0x18001763d`
- `0x1800176cc`
- `0x180017736`

## callees

- `0x1800026f0`
- `0x1800038bc`
- `0x180006870`
- `0x1800091e4`
- `0x180013cd4`
- `0x1800141d0`
- `0x180016d70`

## string_xrefs

- `0x18001427e`: `onecoreuap\base\appmodel\search\migplugin\wsmigpluginclass.cpp`

## pseudocode

```c
void __fastcall indexer::result::details::log_error_code_exception(
        indexer::result::details *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5,
        const char *a6,
        wil::details *a7,
        __int64 a8,
        const char *a9)
{
  wchar_t v10[2048]; // [rsp+60h] [rbp-A0h] BYREF

  wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_44936384>::GetImpl'::`2'::impl) )
    StringCchPrintfW(v10, 0x100u, L"%hs: %hs", a8, a9);
  else
    StringCchPrintfW(v10, 0x800u, L"%hs: %hs", a8, a9);
  wil::details::ReportFailure_Base<1,0>(this, 78, "onecoreuap\\base\\appmodel\\search\\migplugin\\wsmigpluginclass.cpp");
}

```

## disassembly

```asm
0x1800141d0  mov     [rsp-8+arg_8], rbx
0x1800141d5  mov     [rsp-8+arg_10], rsi
0x1800141da  push    rbp
0x1800141db  push    rdi
0x1800141dc  push    r12
0x1800141de  push    r14
0x1800141e0  push    r15
0x1800141e2  lea     rbp, [rsp-0F70h]
0x1800141ea  mov     eax, 1070h
0x1800141ef  call    _alloca_probe
0x1800141f4  sub     rsp, rax
0x1800141f7  mov     rax, cs:__security_cookie
0x1800141fe  xor     rax, rsp
0x180014201  mov     [rbp+0F90h+var_30], rax
0x180014208  mov     rsi, [rbp+0F90h+arg_28]
0x18001420f  mov     rdi, rcx
0x180014212  mov     r14, [rbp+0F90h+arg_38]
0x180014219  mov     r15, [rbp+0F90h+arg_40]
0x180014220  mov     ebx, dword ptr [rbp+0F90h+arg_30]
0x180014226  mov     ecx, ebx; this
0x180014228  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001422d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_44936384@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384> `wil::Feature<__WilFeatureTraits_Feature_BugFix_44936384>::GetImpl(void)'::`2'::impl
0x180014234  mov     r12d, eax
0x180014237  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_44936384@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_44936384>::__private_IsEnabled(void)
0x18001423c  mov     [rsp+1090h+var_1070], r15
0x180014241  mov     r9, r14
0x180014244  lea     r8, aHsHs; "%hs: %hs"
0x18001424b  test    al, al
0x18001424d  jz      short loc_180014265
0x18001424f  mov     edx, 100h; unsigned __int64
0x180014254  lea     rcx, [rsp+1090h+var_1030]; wchar_t *
0x180014259  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001425e  lea     rax, [rsp+1090h+var_1030]
0x180014263  jmp     short loc_180014279
0x180014265  mov     edx, 800h; unsigned __int64
0x18001426a  lea     rcx, [rsp+1090h+var_1030]; wchar_t *
0x18001426f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180014274  lea     rax, [rsp+1090h+var_1030]
0x180014279  mov     [rsp+1090h+var_1058], rax
0x18001427e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\mig"...
0x180014285  lea     rax, [rsp+1090h+var_1040]
0x18001428a  mov     [rsp+1090h+var_1040], ebx
0x18001428e  mov     [rsp+1090h+var_1060], rax
0x180014293  mov     edx, 4Eh ; 'N'
0x180014298  mov     rcx, rdi
0x18001429b  mov     [rsp+1090h+var_1068], rsi
0x1800142a0  mov     [rsp+1090h+var_103C], r12d
0x1800142a5  mov     [rsp+1090h+var_1038], 0
0x1800142ad  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800142b2  mov     rcx, [rbp+0F90h+var_30]
0x1800142b9  xor     rcx, rsp; StackCookie
0x1800142bc  call    __security_check_cookie
0x1800142c1  lea     r11, [rsp+1090h+var_20]
0x1800142c9  mov     rbx, [r11+38h]
0x1800142cd  mov     rsi, [r11+40h]
0x1800142d1  mov     rsp, r11
0x1800142d4  pop     r15
0x1800142d6  pop     r14
0x1800142d8  pop     r12
0x1800142da  pop     rdi
0x1800142db  pop     rbp
0x1800142dc  retn
```
