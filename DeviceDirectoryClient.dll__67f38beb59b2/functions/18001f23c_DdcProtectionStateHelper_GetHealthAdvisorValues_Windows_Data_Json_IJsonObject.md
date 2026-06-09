# DdcProtectionStateHelper::GetHealthAdvisorValues(Windows::Data::Json::IJsonObject *)

- ea: `0x18001f23c`
- end: `0x18001f2da`
- name: `?GetHealthAdvisorValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020068`

## callees

- `0x180004060`
- `0x1800050b8`
- `0x18001d150`
- `0x18001dcfc`
- `0x18001f23c`

## string_xrefs

- `0x18001f2ae`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcProtectionStateHelper::GetHealthAdvisorValues(struct Windows::Data::Json::IJsonObject *a1)
{
  int AssessmentValues; // edi
  int v3; // edx
  int v4; // ecx
  __int64 i; // rbx
  int v6; // edx
  int v7; // ecx
  _DWORD v9[2]; // [rsp+48h] [rbp+10h]
  IUnknown *v10; // [rsp+50h] [rbp+18h] BYREF

  AssessmentValues = 0;
  v10 = 0;
  v9[0] = 256;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  CreateInstanceWithCloak<IHealthAdvisorShield>(v4, v3, &v10);
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    AssessmentValues = DdcProtectionStateHelper::GetAssessmentValues(v9[i], (__int64)v10, (__int64)a1);
    if ( AssessmentValues < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          AssessmentValues,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
          206,
          "CHR(GetAssessmentValues(eAssessments[i], pHealthAdvisorShield.Get(), pProtectionState))");
      break;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  return (unsigned int)AssessmentValues;
}

```

## disassembly

```asm
0x18001f23c  mov     rax, rsp
0x18001f23f  mov     [rax+8], rbx
0x18001f243  mov     [rax+20h], rsi
0x18001f247  push    rdi
0x18001f248  sub     rsp, 30h
0x18001f24c  mov     rsi, rcx
0x18001f24f  xor     edi, edi
0x18001f251  mov     [rax+18h], rdi
0x18001f255  mov     dword ptr [rax+10h], 100h
0x18001f25c  lea     rcx, [rax+18h]
0x18001f260  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f265  lea     r8, [rsp+38h+arg_10]
0x18001f26a  call    ??$CreateInstanceWithCloak@UIHealthAdvisorShield@@@@YAJAEBU_GUID@@0PEAPEAUIHealthAdvisorShield@@@Z; CreateInstanceWithCloak<IHealthAdvisorShield>(_GUID const &,_GUID const &,IHealthAdvisorShield * *)
0x18001f26f  xor     ebx, ebx
0x18001f271  cmp     ebx, 1
0x18001f274  jnb     short loc_18001F2BE
0x18001f276  mov     r8, rsi
0x18001f279  mov     rdx, [rsp+38h+arg_10]
0x18001f27e  mov     ecx, [rsp+rbx*4+38h+arg_8]
0x18001f282  call    ?GetAssessmentValues@DdcProtectionStateHelper@@CAJW4_tagHealthAdvisorAssessment@@PEAUIHealthAdvisorShield@@PEAUIJsonObject@Json@Data@Windows@@@Z; DdcProtectionStateHelper::GetAssessmentValues(_tagHealthAdvisorAssessment,IHealthAdvisorShield *,Windows::Data::Json::IJsonObject *)
0x18001f287  mov     edi, eax
0x18001f289  test    eax, eax
0x18001f28b  js      short loc_18001F291
0x18001f28d  inc     ebx
0x18001f28f  jmp     short loc_18001F271
0x18001f291  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001f298  jz      short loc_18001F2BE
0x18001f29a  lea     rax, aChrGetassessme_0; "CHR(GetAssessmentValues(eAssessments[i]"...
0x18001f2a1  mov     [rsp+38h+var_10], rax
0x18001f2a6  mov     [rsp+38h+var_18], 4CEh
0x18001f2ae  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001f2b5  mov     r8d, edi
0x18001f2b8  call    McTemplateU0dsqs_EventWriteTransfer
0x18001f2bd  nop
0x18001f2be  lea     rcx, [rsp+38h+arg_10]
0x18001f2c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f2c8  mov     eax, edi
0x18001f2ca  mov     rbx, [rsp+38h+arg_0]
0x18001f2cf  mov     rsi, [rsp+38h+arg_18]
0x18001f2d4  add     rsp, 30h
0x18001f2d8  pop     rdi
0x18001f2d9  retn
```
