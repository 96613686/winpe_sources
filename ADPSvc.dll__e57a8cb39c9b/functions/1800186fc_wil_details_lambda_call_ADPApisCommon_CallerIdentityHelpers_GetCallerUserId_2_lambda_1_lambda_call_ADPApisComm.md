# wil::details::lambda_call__ADPApisCommon::CallerIdentityHelpers::GetCallerUserId_::_2_::_lambda_1___::_lambda_call__ADPApisCommon::CallerIdentityHelpers::GetCallerUserId_::_2_::_lambda_1___

- ea: `0x1800186fc`
- end: `0x180018733`
- name: `wil::details::lambda_call__ADPApisCommon::CallerIdentityHelpers::GetCallerUserId_::_2_::_lambda_1___::_lambda_call__ADPApisCommon::CallerIdentityHelpers::GetCallerUserId_::_2_::_lambda_1___`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800c85e2`

## callees

- `0x1800186fc`
- `0x180018950`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001870a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001870a`

## string_xrefs

- `0x18001871e`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\calleridentityhelpers.cpp`

## pseudocode

```c
void __fastcall wil::details::lambda_call__ADPApisCommon::CallerIdentityHelpers::GetCallerUserId_::_2_::_lambda_1___::_lambda_call__ADPApisCommon::CallerIdentityHelpers::GetCallerUserId_::_2_::_lambda_1___(
        __int64 a1)
{
  HRESULT v1; // eax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 1) )
  {
    *(_BYTE *)(a1 + 1) = 0;
    v1 = CoRevertToSelf();
    if ( v1 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\c"
                      "alleridentityhelpers.cpp",
        (const char *)(unsigned int)v1,
        v2);
  }
}

```

## disassembly

```asm
0x1800186fc  sub     rsp, 28h
0x180018700  cmp     byte ptr [rcx+1], 0
0x180018704  jz      short loc_180018714
0x180018706  mov     byte ptr [rcx+1], 0
0x18001870a  call    cs:__imp_CoRevertToSelf
0x180018710  test    eax, eax
0x180018712  js      short loc_180018719
0x180018714  add     rsp, 28h
0x180018718  retn
0x180018719  mov     rcx, [rsp+28h]; this
0x18001871e  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180018725  mov     r9d, eax; char *
0x180018728  mov     edx, 0Ch; void *
0x18001872d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
