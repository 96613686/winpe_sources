# AccessCheck_Internal(EnrollmentEnrollType,ushort const *)

- ea: `0x18004abc0`
- end: `0x18004adbf`
- name: `?AccessCheck_Internal@@YAJW4EnrollmentEnrollType@@PEBG@Z`
- size: `511`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004aa4c`
- `0x18004aab4`

## callees

- `0x180014af0`
- `0x180017284`
- `0x180018f88`
- `0x1800199f8`
- `0x180019d68`
- `0x180045e04`
- `0x18004abc0`
- `0x18004bbc4`
- `0x180058f88`
- `0x1800a8f18`
- `0x1800b3344`

## import_xrefs

- `DMCmnUtils!DmIsSystemOrUserIsAdmin` at `0x18004acea`
- `DMCmnUtils!DmIsSystemOrUserIsAdmin` at `0x18004ad4c`
- `DMCmnUtils!DmIsSystemOrUserIsAdmin` at `0x18004acea`
- `DMCmnUtils!DmIsSystemOrUserIsAdmin` at `0x18004ad4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ac35`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ac2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ac2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ac15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ac15`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18004abe9`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18004abe9`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004ad7f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18004ad7f`
- `ntdll!RtlIsMultiSessionSku` at `0x18004ac78`
- `ntdll!RtlIsMultiSessionSku` at `0x18004ac78`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AccessCheck_Internal(unsigned int a1, __int64 a2)
{
  signed int v4; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v7; // eax
  int v9; // [rsp+20h] [rbp-30h] BYREF
  int v10; // [rsp+24h] [rbp-2Ch] BYREF
  unsigned int Pid; // [rsp+28h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-18h] BYREF
  wchar_t *String2; // [rsp+80h] [rbp+30h] BYREF
  int v15; // [rsp+88h] [rbp+38h] BYREF

  v13[0] = 0;
  v13[2] = 0;
  Pid = 0;
  if ( I_RpcBindingInqLocalClientPID(0, &Pid) == 1725 )
    goto LABEL_20;
  v4 = AutoImpersonate::ImpersonateClient((AutoImpersonate *)v13);
  if ( v4 >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_6;
    }
    v15 = 0;
    v4 = CheckThreadAdmin(TokenHandle, &v15);
    if ( v4 < 0 || v15 != 1 )
    {
      if ( (unsigned __int8)RtlIsMultiSessionSku() )
      {
        String2 = 0;
        if ( (int)GetAppSid(TokenHandle, &String2) >= 0 )
        {
          if ( !wcscmp_0(
                  L"S-1-15-2-1910091885-1573563583-1104941280-2418270861-3411158377-2822700936-2990310272",
                  String2) )
          {
            if ( a1 <= 0x18 )
            {
              v7 = 20971552;
              if ( _bittest(&v7, a1) )
                goto LABEL_18;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
              && (unsigned int)LUAIsShadowAdminEnabled() )
            {
              goto LABEL_26;
            }
            v9 = 0;
            if ( (int)DmIsSystemOrUserIsAdmin(&v9) >= 0 && v9 == 1 )
            {
LABEL_18:
              CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&String2);
LABEL_19:
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_20:
              v4 = 0;
              goto LABEL_30;
            }
          }
          if ( !wcscmp_0(
                  L"S-1-15-2-2434737943-167758768-3180539153-984336765-1107280622-3591121930-2677285773",
                  String2)
            && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl)
             || !(unsigned int)LUAIsShadowAdminEnabled()) )
          {
            v10 = 0;
            if ( (int)DmIsSystemOrUserIsAdmin(&v10) >= 0 && v10 == 1 )
              goto LABEL_18;
          }
        }
LABEL_26:
        CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&String2);
        goto LABEL_29;
      }
      AutoImpersonate::RevertToSelf((AutoImpersonate *)v13);
      LOBYTE(String2) = 0;
      v4 = CapabilityCheck(TokenHandle, a2, &String2);
      if ( v4 >= 0 )
      {
        if ( (_BYTE)String2 == 1 )
          goto LABEL_19;
LABEL_29:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        v4 = -2147024891;
        goto LABEL_30;
      }
    }
LABEL_6:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
LABEL_30:
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004abc0  mov     [rsp-18h+arg_0], rbx
0x18004abc5  push    rbp
0x18004abc6  push    rsi
0x18004abc7  push    rdi
0x18004abc8  mov     rbp, rsp
0x18004abcb  sub     rsp, 50h
0x18004abcf  mov     rsi, rdx
0x18004abd2  mov     edi, ecx
0x18004abd4  mov     [rbp+var_18], 0
0x18004abd8  mov     [rbp+var_16], 0
0x18004abdc  mov     [rbp+Pid], 0
0x18004abe3  lea     rdx, [rbp+Pid]; Pid
0x18004abe7  xor     ecx, ecx; Binding
0x18004abe9  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18004abef  cmp     eax, 6BDh
0x18004abf4  jz      loc_18004AD0D
0x18004abfa  lea     rcx, [rbp+var_18]; this
0x18004abfe  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18004ac03  mov     ebx, eax
0x18004ac05  test    eax, eax
0x18004ac07  js      loc_18004ADA7
0x18004ac0d  mov     [rbp+TokenHandle], 0
0x18004ac15  call    cs:__imp_GetCurrentThread
0x18004ac1b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004ac1f  mov     edx, 8; DesiredAccess
0x18004ac24  lea     r8d, [rdx-7]; OpenAsSelf
0x18004ac28  mov     rcx, rax; ThreadHandle
0x18004ac2b  call    cs:__imp_OpenThreadToken
0x18004ac31  test    eax, eax
0x18004ac33  jnz     short loc_18004AC58
0x18004ac35  call    cs:__imp_GetLastError
0x18004ac3b  mov     ebx, eax
0x18004ac3d  test    eax, eax
0x18004ac3f  jle     short loc_18004AC4A
0x18004ac41  movzx   ebx, ax
0x18004ac44  or      ebx, 80070000h
0x18004ac4a  lea     rcx, [rbp+TokenHandle]
0x18004ac4e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ac53  jmp     loc_18004ADA7
0x18004ac58  mov     [rbp+arg_18], 0
0x18004ac5f  lea     rdx, [rbp+arg_18]
0x18004ac63  mov     rcx, [rbp+TokenHandle]
0x18004ac67  call    CheckThreadAdmin
0x18004ac6c  mov     ebx, eax
0x18004ac6e  test    eax, eax
0x18004ac70  js      short loc_18004AC78
0x18004ac72  cmp     [rbp+arg_18], 1
0x18004ac76  jz      short loc_18004AC4A
0x18004ac78  call    cs:__imp_RtlIsMultiSessionSku
0x18004ac7e  test    al, al
0x18004ac80  jz      loc_18004AD67
0x18004ac86  mov     [rbp+String2], 0
0x18004ac8e  lea     rdx, [rbp+String2]
0x18004ac92  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004ac96  call    GetAppSid
0x18004ac9b  test    eax, eax
0x18004ac9d  js      loc_18004AD5C
0x18004aca3  mov     rdx, [rbp+String2]; String2
0x18004aca7  lea     rcx, aS1152191009188; "S-1-15-2-1910091885-1573563583-11049412"...
0x18004acae  call    wcscmp_0
0x18004acb3  test    eax, eax
0x18004acb5  jnz     short loc_18004AD14
0x18004acb7  cmp     edi, 18h
0x18004acba  ja      short loc_18004ACC6
0x18004acbc  mov     eax, 1400020h
0x18004acc1  bt      eax, edi
0x18004acc4  jb      short loc_18004ACFA
0x18004acc6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18004accd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18004acd2  test    al, al
0x18004acd4  jz      short loc_18004ACDF
0x18004acd6  call    LUAIsShadowAdminEnabled
0x18004acdb  test    eax, eax
0x18004acdd  jnz     short loc_18004AD5C
0x18004acdf  mov     [rbp+var_30], 0
0x18004ace6  lea     rcx, [rbp+var_30]
0x18004acea  call    cs:__imp_?DmIsSystemOrUserIsAdmin@@YAJPEAH@Z; DmIsSystemOrUserIsAdmin(int *)
0x18004acf0  test    eax, eax
0x18004acf2  js      short loc_18004AD14
0x18004acf4  cmp     [rbp+var_30], 1
0x18004acf8  jnz     short loc_18004AD14
0x18004acfa  lea     rcx, [rbp+String2]
0x18004acfe  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18004ad03  nop
0x18004ad04  lea     rcx, [rbp+TokenHandle]
0x18004ad08  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ad0d  xor     ebx, ebx
0x18004ad0f  jmp     loc_18004ADA7
0x18004ad14  mov     rdx, [rbp+String2]; String2
0x18004ad18  lea     rcx, aS1152243473794; "S-1-15-2-2434737943-167758768-318053915"...
0x18004ad1f  call    wcscmp_0
0x18004ad24  test    eax, eax
0x18004ad26  jnz     short loc_18004AD5C
0x18004ad28  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18004ad2f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18004ad34  test    al, al
0x18004ad36  jz      short loc_18004AD41
0x18004ad38  call    LUAIsShadowAdminEnabled
0x18004ad3d  test    eax, eax
0x18004ad3f  jnz     short loc_18004AD5C
0x18004ad41  mov     [rbp+var_2C], 0
0x18004ad48  lea     rcx, [rbp+var_2C]
0x18004ad4c  call    cs:__imp_?DmIsSystemOrUserIsAdmin@@YAJPEAH@Z; DmIsSystemOrUserIsAdmin(int *)
0x18004ad52  test    eax, eax
0x18004ad54  js      short loc_18004AD5C
0x18004ad56  cmp     [rbp+var_2C], 1
0x18004ad5a  jz      short loc_18004ACFA
0x18004ad5c  lea     rcx, [rbp+String2]
0x18004ad60  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18004ad65  jmp     short loc_18004AD99
0x18004ad67  lea     rcx, [rbp+var_18]; this
0x18004ad6b  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18004ad70  mov     byte ptr [rbp+String2], 0
0x18004ad74  lea     r8, [rbp+String2]
0x18004ad78  mov     rdx, rsi
0x18004ad7b  mov     rcx, [rbp+TokenHandle]
0x18004ad7f  call    cs:__imp_CapabilityCheck
0x18004ad85  mov     ebx, eax
0x18004ad87  test    eax, eax
0x18004ad89  js      loc_18004AC4A
0x18004ad8f  cmp     byte ptr [rbp+String2], 1
0x18004ad93  jz      loc_18004AD04
0x18004ad99  lea     rcx, [rbp+TokenHandle]
0x18004ad9d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ada2  mov     ebx, 80070005h
0x18004ada7  lea     rcx, [rbp+var_18]; this
0x18004adab  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18004adb0  mov     eax, ebx
0x18004adb2  mov     rbx, [rsp+50h+arg_0]
0x18004adb7  add     rsp, 50h
0x18004adbb  pop     rdi
0x18004adbc  pop     rsi
0x18004adbd  pop     rbp
0x18004adbe  retn
```
