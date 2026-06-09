# WaasMedic::CloudCampaignHelper::GetCloudCampaigns(tagCloudCampaignSpec * *,ulong *)

- ea: `0x18005a264`
- end: `0x18005a340`
- name: `?GetCloudCampaigns@CloudCampaignHelper@WaasMedic@@SAJPEAPEAUtagCloudCampaignSpec@@PEAK@Z`
- size: `220`
- prototype: `__int64 __fastcall(struct tagCloudCampaignSpec **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180059fb0`

## callees

- `0x18002c238`
- `0x18005a264`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a29e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005a29e`

## string_xrefs

- `0x18005a2ab`: `Failed to CoCreateInstance of WaaSAssessorInternal`
- `0x18005a2ed`: `COM call to WaaSAssessmentClient GetCloudCampaigns failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CloudCampaignHelper::GetCloudCampaigns(
        struct tagCloudCampaignSpec **a1,
        unsigned int *a2)
{
  unsigned __int64 v4; // rbx
  LPVOID v5; // rcx
  const char *v7; // [rsp+28h] [rbp-10h]
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = 0;
  v4 = (unsigned int)CoCreateInstance(
                       &GUID_098ef871_fa9f_46af_8958_c083515d7c9c,
                       0,
                       1u,
                       &GUID_28f36eb8_3990_460a_bda9_3f06f8514de9,
                       &v10);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x53,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cloudcampaignhelper.cpp",
    (const char *)v4,
    (int)"Failed to CoCreateInstance of WaaSAssessorInternal",
    v7);
  if ( (v4 & 0x80000000) == 0LL )
  {
    v4 = (*(unsigned int (__fastcall **)(LPVOID, struct tagCloudCampaignSpec **, unsigned int *))(*(_QWORD *)v10 + 112LL))(
           v10,
           a1,
           a2);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cloudcampaignhelper.cpp",
      (const char *)v4,
      (int)"COM call to WaaSAssessmentClient GetCloudCampaigns failed",
      v8);
  }
  v5 = v10;
  if ( v10 )
  {
    v10 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005a264  mov     r11, rsp
0x18005a267  mov     [r11+8], rbx
0x18005a26b  mov     [r11+10h], rsi
0x18005a26f  push    rdi
0x18005a270  sub     rsp, 30h
0x18005a274  mov     rdi, rdx
0x18005a277  mov     rsi, rcx
0x18005a27a  mov     qword ptr [r11+18h], 0
0x18005a282  lea     rax, [r11+18h]
0x18005a286  mov     [r11-18h], rax
0x18005a28a  lea     r9, _GUID_28f36eb8_3990_460a_bda9_3f06f8514de9; riid
0x18005a291  xor     edx, edx; pUnkOuter
0x18005a293  lea     r8d, [rdx+1]; dwClsContext
0x18005a297  lea     rcx, _GUID_098ef871_fa9f_46af_8958_c083515d7c9c; rclsid
0x18005a29e  call    cs:__imp_CoCreateInstance
0x18005a2a4  mov     ebx, eax
0x18005a2a6  mov     rcx, [rsp+38h]; this
0x18005a2ab  lea     rax, aFailedToCocrea; "Failed to CoCreateInstance of WaaSAsses"...
0x18005a2b2  mov     qword ptr [rsp+38h+var_18], rax; int
0x18005a2b7  mov     r9d, ebx; char *
0x18005a2ba  lea     r8, aOnecoreEnduser_42; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a2c1  mov     edx, 53h ; 'S'; void *
0x18005a2c6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005a2cb  test    ebx, ebx
0x18005a2cd  js      short loc_18005A30E
0x18005a2cf  mov     rcx, [rsp+38h+arg_10]
0x18005a2d4  mov     rax, [rcx]
0x18005a2d7  mov     r8, rdi
0x18005a2da  mov     rdx, rsi
0x18005a2dd  mov     rax, [rax+70h]
0x18005a2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2e6  mov     ebx, eax
0x18005a2e8  mov     rcx, [rsp+38h]; this
0x18005a2ed  lea     rax, aComCallToWaasa; "COM call to WaaSAssessmentClient GetClo"...
0x18005a2f4  mov     qword ptr [rsp+38h+var_18], rax; int
0x18005a2f9  mov     r9d, ebx; char *
0x18005a2fc  lea     r8, aOnecoreEnduser_42; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a303  mov     edx, 58h ; 'X'; void *
0x18005a308  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005a30d  nop
0x18005a30e  mov     rcx, [rsp+38h+arg_10]
0x18005a313  test    rcx, rcx
0x18005a316  jz      short loc_18005A32E
0x18005a318  mov     [rsp+38h+arg_10], 0
0x18005a321  mov     rax, [rcx]
0x18005a324  mov     rax, [rax+10h]
0x18005a328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a32d  nop
0x18005a32e  mov     eax, ebx
0x18005a330  mov     rbx, [rsp+38h+arg_0]
0x18005a335  mov     rsi, [rsp+38h+arg_8]
0x18005a33a  add     rsp, 30h
0x18005a33e  pop     rdi
0x18005a33f  retn
```
