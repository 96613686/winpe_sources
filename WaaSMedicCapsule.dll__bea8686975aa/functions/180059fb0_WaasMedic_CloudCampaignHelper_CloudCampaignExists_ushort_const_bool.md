# WaasMedic::CloudCampaignHelper::CloudCampaignExists(ushort const *,bool *)

- ea: `0x180059fb0`
- end: `0x18005a17b`
- name: `?CloudCampaignExists@CloudCampaignHelper@WaasMedic@@SAJPEBGPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004f1c0`

## callees

- `0x180009a54`
- `0x18000b308`
- `0x180059fb0`
- `0x18005a264`
- `0x18005a490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005a0a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005a137`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005a0a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005a137`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a0b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a0c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a14d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a15b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a16e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a0b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a0c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a14d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a15b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a16e`

## pseudocode

```c
__int64 __fastcall WaasMedic::CloudCampaignHelper::CloudCampaignExists(const unsigned __int16 *a1, bool *a2)
{
  int CloudCampaigns; // esi
  const char *v5; // rax
  __int64 v6; // rdx
  int i; // r14d
  __int64 v8; // rcx
  int j; // r14d
  __int64 v10; // rcx
  int v11; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  const unsigned __int16 *v13; // [rsp+50h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+28h] BYREF

  v13 = a1;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cloudcampaignhelper.cpp",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
  *a2 = 0;
  LODWORD(v13) = 0;
  pv = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPluginBugFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CanvasPluginBugFixes>::GetImpl'::`2'::impl) )
  {
    CloudCampaigns = WaasMedic::CloudCampaignHelper::GetCloudCampaigns(
                       (struct tagCloudCampaignSpec **)&pv,
                       (unsigned int *)&v13);
    if ( CloudCampaigns < 0 )
    {
      v5 = "GetCloudCampaigns failed for campaign: %ws";
      v6 = 30;
LABEL_7:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cloudcampaignhelper.cpp",
        (const char *)(unsigned int)CloudCampaigns,
        (int)v5,
        L"CANVAS");
      return (unsigned int)CloudCampaigns;
    }
    if ( !pv )
    {
      if ( (_DWORD)v13 )
        return 2147500035LL;
      return 0;
    }
    for ( i = 0; i < (int)v13; ++i )
    {
      v8 = *((_QWORD *)pv + 2 * i + 1);
      if ( v8 )
      {
        if ( !(unsigned int)_o__wcsicmp(v8, L"CANVAS") )
          *a2 = 1;
      }
      CoTaskMemFree(*((LPVOID *)pv + 2 * i + 1));
      CoTaskMemFree(*((LPVOID *)pv + 2 * i));
    }
  }
  else
  {
    CloudCampaigns = WaasMedic::CloudCampaignHelper::GetCloudCampaigns(
                       (struct tagCloudCampaignSpec **)&pv,
                       (unsigned int *)&v13);
    if ( CloudCampaigns < 0 )
    {
      v5 = "GetCloudCampaigns failed for campaign: {}";
      v6 = 53;
      goto LABEL_7;
    }
    if ( !pv )
      return 2147500035LL;
    for ( j = 0; j < (int)v13; ++j )
    {
      v10 = *((_QWORD *)pv + 2 * j + 1);
      if ( v10 && !(unsigned int)_o__wcsicmp(v10, L"CANVAS") )
        *a2 = 1;
      CoTaskMemFree(*((LPVOID *)pv + 2 * j + 1));
      CoTaskMemFree(*((LPVOID *)pv + 2 * j));
    }
  }
  CoTaskMemFree(pv);
  return 0;
}

```

## disassembly

```asm
0x180059fb0  mov     [rsp-18h+arg_10], rbx
0x180059fb5  mov     [rsp-18h+arg_18], rsi
0x180059fba  mov     [rsp-18h+arg_0], rcx
0x180059fbf  push    rbp
0x180059fc0  push    rdi
0x180059fc1  push    r14
0x180059fc3  mov     rbp, rsp
0x180059fc6  sub     rsp, 30h
0x180059fca  mov     rdi, rdx
0x180059fcd  test    rdx, rdx
0x180059fd0  jnz     short loc_18005A003
0x180059fd2  mov     rcx, [rbp+18h]; this
0x180059fd6  lea     r8, aOnecoreEnduser_42; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180059fdd  mov     r9d, 80004003h; char *
0x180059fe3  lea     edx, [rdi+18h]; void *
0x180059fe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059feb  mov     eax, 80004003h
0x180059ff0  mov     rbx, [rsp+30h+arg_10]
0x180059ff5  mov     rsi, [rsp+30h+arg_18]
0x180059ffa  add     rsp, 30h
0x180059ffe  pop     r14
0x18005a000  pop     rdi
0x18005a001  pop     rbp
0x18005a002  retn
0x18005a003  mov     byte ptr [rdx], 0
0x18005a006  mov     dword ptr [rbp+arg_0], 0
0x18005a00d  mov     [rbp+pv], 0
0x18005a015  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CanvasPluginBugFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CanvasPluginBugFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPluginBugFixes> `wil::Feature<__WilFeatureTraits_Feature_CanvasPluginBugFixes>::GetImpl(void)'::`2'::impl
0x18005a01c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CanvasPluginBugFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPluginBugFixes>::__private_IsEnabled(void)
0x18005a021  lea     rdx, [rbp+arg_0]; unsigned int *
0x18005a025  lea     rcx, [rbp+pv]; struct tagCloudCampaignSpec **
0x18005a029  test    al, al
0x18005a02b  jz      loc_18005A0E9
0x18005a031  call    ?GetCloudCampaigns@CloudCampaignHelper@WaasMedic@@SAJPEAPEAUtagCloudCampaignSpec@@PEAK@Z; WaasMedic::CloudCampaignHelper::GetCloudCampaigns(tagCloudCampaignSpec * *,ulong *)
0x18005a036  mov     esi, eax
0x18005a038  test    eax, eax
0x18005a03a  jns     short loc_18005A070
0x18005a03c  lea     rax, aGetcloudcampai; "GetCloudCampaigns failed for campaign: "...
0x18005a043  mov     edx, 1Eh; void *
0x18005a048  mov     rcx, [rbp+18h]; this
0x18005a04c  lea     rbx, aCanvas; "CANVAS"
0x18005a053  mov     [rsp+30h+var_8], rbx; char *
0x18005a058  lea     r8, aOnecoreEnduser_42; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a05f  mov     r9d, esi; char *
0x18005a062  mov     qword ptr [rsp+30h+var_10], rax; int
0x18005a067  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005a06c  mov     eax, esi
0x18005a06e  jmp     short loc_180059FF0
0x18005a070  cmp     [rbp+pv], 0
0x18005a075  jz      short loc_18005A0DA
0x18005a077  xor     r14d, r14d
0x18005a07a  cmp     dword ptr [rbp+arg_0], r14d
0x18005a07e  jle     loc_18005A16A
0x18005a084  lea     rbx, aCanvas; "CANVAS"
0x18005a08b  mov     rax, [rbp+pv]
0x18005a08f  movsxd  rsi, r14d
0x18005a092  add     rsi, rsi
0x18005a095  mov     rcx, [rax+rsi*8+8]
0x18005a09a  test    rcx, rcx
0x18005a09d  jz      short loc_18005A0AF
0x18005a09f  mov     rdx, rbx
0x18005a0a2  call    cs:__imp__o__wcsicmp
0x18005a0a8  test    eax, eax
0x18005a0aa  jnz     short loc_18005A0AF
0x18005a0ac  mov     byte ptr [rdi], 1
0x18005a0af  mov     rcx, [rbp+pv]
0x18005a0b3  mov     rcx, [rcx+rsi*8+8]; pv
0x18005a0b8  call    cs:__imp_CoTaskMemFree
0x18005a0be  mov     rcx, [rbp+pv]
0x18005a0c2  mov     rcx, [rcx+rsi*8]; pv
0x18005a0c6  call    cs:__imp_CoTaskMemFree
0x18005a0cc  inc     r14d
0x18005a0cf  cmp     r14d, dword ptr [rbp+arg_0]
0x18005a0d3  jl      short loc_18005A08B
0x18005a0d5  jmp     loc_18005A16A
0x18005a0da  cmp     dword ptr [rbp+arg_0], 0
0x18005a0de  jnz     loc_180059FEB
0x18005a0e4  jmp     loc_18005A174
0x18005a0e9  call    ?GetCloudCampaigns@CloudCampaignHelper@WaasMedic@@SAJPEAPEAUtagCloudCampaignSpec@@PEAK@Z; WaasMedic::CloudCampaignHelper::GetCloudCampaigns(tagCloudCampaignSpec * *,ulong *)
0x18005a0ee  mov     esi, eax
0x18005a0f0  test    eax, eax
0x18005a0f2  jns     short loc_18005A105
0x18005a0f4  lea     rax, aGetcloudcampai_0; "GetCloudCampaigns failed for campaign: "...
0x18005a0fb  mov     edx, 35h ; '5'
0x18005a100  jmp     loc_18005A048
0x18005a105  cmp     [rbp+pv], 0
0x18005a10a  jz      loc_180059FEB
0x18005a110  xor     r14d, r14d
0x18005a113  cmp     dword ptr [rbp+arg_0], r14d
0x18005a117  jle     short loc_18005A16A
0x18005a119  lea     rbx, aCanvas; "CANVAS"
0x18005a120  mov     rax, [rbp+pv]
0x18005a124  movsxd  rsi, r14d
0x18005a127  add     rsi, rsi
0x18005a12a  mov     rcx, [rax+rsi*8+8]
0x18005a12f  test    rcx, rcx
0x18005a132  jz      short loc_18005A144
0x18005a134  mov     rdx, rbx
0x18005a137  call    cs:__imp__o__wcsicmp
0x18005a13d  test    eax, eax
0x18005a13f  jnz     short loc_18005A144
0x18005a141  mov     byte ptr [rdi], 1
0x18005a144  mov     rcx, [rbp+pv]
0x18005a148  mov     rcx, [rcx+rsi*8+8]; pv
0x18005a14d  call    cs:__imp_CoTaskMemFree
0x18005a153  mov     rcx, [rbp+pv]
0x18005a157  mov     rcx, [rcx+rsi*8]; pv
0x18005a15b  call    cs:__imp_CoTaskMemFree
0x18005a161  inc     r14d
0x18005a164  cmp     r14d, dword ptr [rbp+arg_0]
0x18005a168  jl      short loc_18005A120
0x18005a16a  mov     rcx, [rbp+pv]; pv
0x18005a16e  call    cs:__imp_CoTaskMemFree
0x18005a174  xor     eax, eax
0x18005a176  jmp     loc_180059FF0
```
