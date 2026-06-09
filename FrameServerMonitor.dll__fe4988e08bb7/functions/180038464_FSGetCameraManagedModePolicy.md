# FSGetCameraManagedModePolicy

- ea: `0x180038464`
- end: `0x18003855e`
- name: `FSGetCameraManagedModePolicy`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180036b70`

## callees

- `0x1800019f0`
- `0x180034e10`
- `0x180038464`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180038502`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180038502`

## string_xrefs

- `0x1800384b2`: `ConfigureCameraOptions`

## pseudocode

```c
__int64 __fastcall FSGetCameraManagedModePolicy(_QWORD *a1, _DWORD *a2)
{
  __int64 v5; // [rsp+20h] [rbp-60h] BYREF
  _DWORD v6[2]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v7; // [rsp+30h] [rbp-50h] BYREF
  int v8; // [rsp+38h] [rbp-48h]
  wchar_t v9; // [rsp+3Ch] [rbp-44h]
  __int128 v10; // [rsp+40h] [rbp-40h] BYREF
  _OWORD v11[2]; // [rsp+50h] [rbp-30h]

  v8 = *(_DWORD *)L"ra";
  v7 = *(_QWORD *)L"Camera";
  v11[0] = *(_OWORD *)L"eCameraOptions";
  v9 = aCamera[6];
  v10 = *(_OWORD *)L"ConfigureCameraOptions";
  v6[0] = 1;
  *a1 = 0;
  *a2 = 0;
  *(_OWORD *)((char *)v11 + 14) = *(_OWORD *)L"Options";
  v6[1] = 2;
  v5 = 0;
  if ( (int)PolicyManager_GetPolicy(&v7, &v10, v6, &v5) >= 0 && *(_DWORD *)(v5 + 8) == 1 )
  {
    if ( *(_DWORD *)(v5 + 16) == 1 )
    {
      *a1 |= 4uLL;
LABEL_7:
      *a2 = 1;
      goto LABEL_8;
    }
    if ( *(_DWORD *)(v5 + 16) == 2 )
    {
      *a1 |= 1uLL;
      goto LABEL_7;
    }
  }
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v5);
  return 0;
}

```

## disassembly

```asm
0x180038464  mov     [rsp-8+arg_10], rbx
0x180038469  mov     [rsp-8+arg_18], rdi
0x18003846e  push    rbp
0x18003846f  mov     rbp, rsp
0x180038472  sub     rsp, 80h
0x180038479  mov     rax, cs:__security_cookie
0x180038480  xor     rax, rsp
0x180038483  mov     [rbp+var_10], rax
0x180038487  movsd   xmm0, qword ptr cs:aCamera; "Camera"
0x18003848f  lea     r9, [rbp+var_60]
0x180038493  mov     eax, dword ptr cs:aCamera+8; "ra"
0x180038499  lea     r8, [rbp+var_58]
0x18003849d  movups  xmm1, xmmword ptr cs:aConfigurecamer+10h; "eCameraOptions"
0x1800384a4  mov     rdi, rdx
0x1800384a7  mov     [rbp+var_48], eax
0x1800384aa  movsd   [rbp+var_50], xmm0
0x1800384af  mov     rbx, rcx
0x1800384b2  movups  xmm0, xmmword ptr cs:aConfigurecamer; "ConfigureCameraOptions"
0x1800384b9  movzx   eax, word ptr cs:aCamera+0Ch; ""
0x1800384c0  movups  xmmword ptr [rbp+var_30], xmm1
0x1800384c4  mov     [rbp+var_44], ax
0x1800384c8  movups  [rbp+var_40], xmm0
0x1800384cc  mov     [rbp+var_58], 1
0x1800384d3  movups  xmm0, xmmword ptr cs:aConfigurecamer+1Eh; "Options"
0x1800384da  mov     qword ptr [rcx], 0
0x1800384e1  lea     rcx, [rbp+var_50]
0x1800384e5  mov     dword ptr [rdx], 0
0x1800384eb  lea     rdx, [rbp+var_40]
0x1800384ef  movups  xmmword ptr [rbp+var_30+0Eh], xmm0
0x1800384f3  mov     [rbp+var_54], 2
0x1800384fa  mov     [rbp+var_60], 0
0x180038502  call    cs:__imp_PolicyManager_GetPolicy
0x180038508  test    eax, eax
0x18003850a  js      short loc_180038532
0x18003850c  mov     rax, [rbp+var_60]
0x180038510  cmp     dword ptr [rax+8], 1
0x180038514  jnz     short loc_180038532
0x180038516  cmp     dword ptr [rax+10h], 1
0x18003851a  jnz     short loc_180038522
0x18003851c  or      qword ptr [rbx], 4
0x180038520  jmp     short loc_18003852C
0x180038522  cmp     dword ptr [rax+10h], 2
0x180038526  jnz     short loc_180038532
0x180038528  or      qword ptr [rbx], 1
0x18003852c  mov     dword ptr [rdi], 1
0x180038532  lea     rcx, [rbp+var_60]
0x180038536  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x18003853b  xor     eax, eax
0x18003853d  mov     rcx, [rbp+var_10]
0x180038541  xor     rcx, rsp; StackCookie
0x180038544  call    __security_check_cookie
0x180038549  lea     r11, [rsp+80h+var_s0]
0x180038551  mov     rbx, [r11+20h]
0x180038555  mov     rdi, [r11+28h]
0x180038559  mov     rsp, r11
0x18003855c  pop     rbp
0x18003855d  retn
```
