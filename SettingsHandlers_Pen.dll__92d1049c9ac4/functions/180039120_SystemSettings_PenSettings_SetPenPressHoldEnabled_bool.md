# SystemSettings::PenSettings::SetPenPressHoldEnabled(bool)

- ea: `0x180039120`
- end: `0x1800391a6`
- name: `?SetPenPressHoldEnabled@PenSettings@SystemSettings@@YAX_N@Z`
- size: `134`
- prototype: `void __fastcall(SystemSettings::PenSettings *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003a2b0`

## callees

- `0x1800030e0`
- `0x180039120`
- `0x18003a8f0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039153`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003918d`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180039153`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003918d`

## pseudocode

```c
void __fastcall SystemSettings::PenSettings::SetPenPressHoldEnabled(SystemSettings::PenSettings *this)
{
  char v1; // bl
  UINT v2; // r9d
  _DWORD pvParam[8]; // [rsp+20h] [rbp-38h] BYREF

  v1 = (char)this;
  memset(pvParam, 0, 28);
  SystemParametersInfoW(0x96u, 0x1Cu, pvParam, 0);
  pvParam[1] = v1 != 0 ? 1 : 3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixPenPressAndHoldToggle>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixPenPressAndHoldToggle>::GetImpl'::`2'::impl) )
    v2 = 3;
  else
    v2 = 0;
  SystemParametersInfoW(0x97u, 0x1Cu, pvParam, v2);
}

```

## disassembly

```asm
0x180039120  push    rbx
0x180039122  sub     rsp, 50h
0x180039126  mov     rax, cs:__security_cookie
0x18003912d  xor     rax, rsp
0x180039130  mov     [rsp+58h+var_18], rax
0x180039135  xorps   xmm0, xmm0
0x180039138  lea     r8, [rsp+58h+pvParam]; pvParam
0x18003913d  xor     r9d, r9d; fWinIni
0x180039140  mov     bl, cl
0x180039142  movups  xmmword ptr [rsp+58h+pvParam], xmm0
0x180039147  movups  xmmword ptr [rsp+58h+pvParam+0Ch], xmm0
0x18003914c  lea     edx, [r9+1Ch]; uiParam
0x180039150  lea     ecx, [rdx+7Ah]; uiAction
0x180039153  call    cs:__imp_SystemParametersInfoW
0x180039159  neg     bl
0x18003915b  sbb     eax, eax
0x18003915d  and     eax, 0FFFFFFFEh
0x180039160  add     eax, 3
0x180039163  mov     [rsp+58h+pvParam+4], eax
0x180039167  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixPenPressAndHoldToggle@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixPenPressAndHoldToggle@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixPenPressAndHoldToggle> `wil::Feature<__WilFeatureTraits_Feature_FixPenPressAndHoldToggle>::GetImpl(void)'::`2'::impl
0x18003916e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixPenPressAndHoldToggle@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixPenPressAndHoldToggle>::__private_IsEnabled(void)
0x180039173  lea     r8, [rsp+58h+pvParam]; pvParam
0x180039178  mov     edx, 1Ch; uiParam
0x18003917d  lea     ecx, [rdx+7Bh]; uiAction
0x180039180  test    al, al
0x180039182  jz      short loc_18003918A
0x180039184  lea     r9d, [rdx-19h]
0x180039188  jmp     short loc_18003918D
0x18003918a  xor     r9d, r9d; fWinIni
0x18003918d  call    cs:__imp_SystemParametersInfoW
0x180039193  mov     rcx, [rsp+58h+var_18]
0x180039198  xor     rcx, rsp; StackCookie
0x18003919b  call    __security_check_cookie
0x1800391a0  add     rsp, 50h
0x1800391a4  pop     rbx
0x1800391a5  retn
```
