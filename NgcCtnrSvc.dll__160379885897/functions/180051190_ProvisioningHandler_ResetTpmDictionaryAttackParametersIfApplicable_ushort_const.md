# ProvisioningHandler::ResetTpmDictionaryAttackParametersIfApplicable(ushort const *)

- ea: `0x180051190`
- end: `0x18005127d`
- name: `?ResetTpmDictionaryAttackParametersIfApplicable@ProvisioningHandler@@CAJPEBG@Z`
- size: `237`
- prototype: `__int64 __fastcall(NgcPolicy *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ec20`

## callees

- `0x180023278`
- `0x1800232a0`
- `0x180029b94`
- `0x18002c640`
- `0x18004e2a4`
- `0x18004e54c`
- `0x180051190`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x1800511ba`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800511ba`
- `TpmCoreProvisioning!TpmSetToLegacyDictionaryAttackParameters` at `0x180051225`
- `TpmCoreProvisioning!TpmSetToLegacyDictionaryAttackParameters` at `0x180051225`

## string_xrefs

- `0x1800511f1`: `onecore\ds\security\ngc\ctnrsvc\handlers\provisioning\provisioninghandler.cpp`
- `0x18005123f`: `onecore\ds\security\ngc\ctnrsvc\handlers\provisioning\provisioninghandler.cpp`
- `0x1800511d2`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProvisioningHandler::ResetTpmDictionaryAttackParametersIfApplicable(NgcPolicy *this)
{
  unsigned int DeviceInfo; // eax
  const unsigned __int16 *v3; // rdx
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // eax
  unsigned int v8; // [rsp+20h] [rbp-28h] BYREF
  __int128 v9; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v9 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, &v9);
  if ( DeviceInfo )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x99,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
           (const char *)DeviceInfo,
           v8);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E7,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\provisioning\\provisioninghandler.cpp",
        (const char *)(unsigned int)v4,
        v8);
      return v5;
    }
  }
  else if ( DWORD1(v9) == 2 && NgcPolicy::GetDefaultPinMinLength(this, v3) < 6 )
  {
    wil::ScopeExitIgnore__lambda_677d58d28eae9d7745d6c29609458d69___(&v8);
    v7 = TpmSetToLegacyDictionaryAttackParameters();
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7FB,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\provisioning\\provisioninghandler.cpp",
        (const char *)(unsigned int)v7,
        v8);
      wil::details::ScopeExitFnGuard__lambda_677d58d28eae9d7745d6c29609458d69___::_ScopeExitFnGuard__lambda_677d58d28eae9d7745d6c29609458d69___(&v8);
      return v5;
    }
    wil::details::ScopeExitFnGuard__lambda_677d58d28eae9d7745d6c29609458d69___::_ScopeExitFnGuard__lambda_677d58d28eae9d7745d6c29609458d69___(&v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180051190  push    rbx
0x180051192  sub     rsp, 40h
0x180051196  mov     rax, cs:__security_cookie
0x18005119d  xor     rax, rsp
0x1800511a0  mov     [rsp+48h+var_10], rax
0x1800511a5  mov     rbx, rcx
0x1800511a8  xorps   xmm0, xmm0
0x1800511ab  movups  [rsp+48h+var_20], xmm0
0x1800511b0  lea     rdx, [rsp+48h+var_20]
0x1800511b5  mov     ecx, 10h
0x1800511ba  call    cs:__imp_Tbsi_GetDeviceInfo
0x1800511c1  nop     dword ptr [rax+rax+00h]
0x1800511c6  test    eax, eax
0x1800511c8  jz      short loc_180051206
0x1800511ca  mov     rcx, [rsp+48h]; this
0x1800511cf  mov     r9d, eax; char *
0x1800511d2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800511d9  mov     edx, 99h; void *
0x1800511de  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800511e3  mov     ebx, eax
0x1800511e5  test    eax, eax
0x1800511e7  jns     short loc_180051267
0x1800511e9  mov     rcx, [rsp+48h]; this
0x1800511ee  mov     r9d, eax; char *
0x1800511f1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x1800511f8  mov     edx, 7E7h; void *
0x1800511fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051202  mov     eax, ebx
0x180051204  jmp     short loc_180051269
0x180051206  cmp     dword ptr [rsp+48h+var_20+4], 2
0x18005120b  jnz     short loc_180051267
0x18005120d  mov     rcx, rbx; this
0x180051210  call    ?GetDefaultPinMinLength@NgcPolicy@@YAKPEBG@Z; NgcPolicy::GetDefaultPinMinLength(ushort const *)
0x180051215  cmp     eax, 6
0x180051218  jnb     short loc_180051267
0x18005121a  lea     rcx, [rsp+48h+var_28]
0x18005121f  call    wil__ScopeExitIgnore__lambda_677d58d28eae9d7745d6c29609458d69___
0x180051224  nop
0x180051225  call    cs:__imp_?TpmSetToLegacyDictionaryAttackParameters@@YAJXZ; TpmSetToLegacyDictionaryAttackParameters(void)
0x18005122c  nop     dword ptr [rax+rax+00h]
0x180051231  mov     ebx, eax
0x180051233  test    eax, eax
0x180051235  jns     short loc_18005125D
0x180051237  mov     rcx, [rsp+48h]; this
0x18005123c  mov     r9d, eax; char *
0x18005123f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x180051246  mov     edx, 7FBh; void *
0x18005124b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051250  nop
0x180051251  lea     rcx, [rsp+48h+var_28]
0x180051256  call    wil__details__ScopeExitFnGuard__lambda_677d58d28eae9d7745d6c29609458d69______ScopeExitFnGuard__lambda_677d58d28eae9d7745d6c29609458d69___
0x18005125b  jmp     short loc_180051202
0x18005125d  lea     rcx, [rsp+48h+var_28]
0x180051262  call    wil__details__ScopeExitFnGuard__lambda_677d58d28eae9d7745d6c29609458d69______ScopeExitFnGuard__lambda_677d58d28eae9d7745d6c29609458d69___
0x180051267  xor     eax, eax
0x180051269  mov     rcx, [rsp+48h+var_10]
0x18005126e  xor     rcx, rsp; StackCookie
0x180051271  call    __security_check_cookie
0x180051276  add     rsp, 40h
0x18005127a  pop     rbx
0x18005127b  retn
```
