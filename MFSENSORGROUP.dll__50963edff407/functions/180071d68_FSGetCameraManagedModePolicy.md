# FSGetCameraManagedModePolicy

- ea: `0x180071d68`
- end: `0x180071e62`
- name: `FSGetCameraManagedModePolicy`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180071be4`

## callees

- `0x180044f30`
- `0x18006fce8`
- `0x180071d68`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180071e06`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180071e06`

## string_xrefs

- `0x180071db6`: `ConfigureCameraOptions`

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
0x180071d68  mov     [rsp-8+arg_10], rbx
0x180071d6d  mov     [rsp-8+arg_18], rdi
0x180071d72  push    rbp
0x180071d73  mov     rbp, rsp
0x180071d76  sub     rsp, 80h
0x180071d7d  mov     rax, cs:__security_cookie
0x180071d84  xor     rax, rsp
0x180071d87  mov     [rbp+var_10], rax
0x180071d8b  movsd   xmm0, qword ptr cs:aCamera; "Camera"
0x180071d93  lea     r9, [rbp+var_60]
0x180071d97  mov     eax, dword ptr cs:aCamera+8; "ra"
0x180071d9d  lea     r8, [rbp+var_58]
0x180071da1  movups  xmm1, xmmword ptr cs:aConfigurecamer+10h; "eCameraOptions"
0x180071da8  mov     rdi, rdx
0x180071dab  mov     [rbp+var_48], eax
0x180071dae  movsd   [rbp+var_50], xmm0
0x180071db3  mov     rbx, rcx
0x180071db6  movups  xmm0, xmmword ptr cs:aConfigurecamer; "ConfigureCameraOptions"
0x180071dbd  movzx   eax, word ptr cs:aCamera+0Ch; ""
0x180071dc4  movups  xmmword ptr [rbp+var_30], xmm1
0x180071dc8  mov     [rbp+var_44], ax
0x180071dcc  movups  [rbp+var_40], xmm0
0x180071dd0  mov     [rbp+var_58], 1
0x180071dd7  movups  xmm0, xmmword ptr cs:aConfigurecamer+1Eh; "Options"
0x180071dde  mov     qword ptr [rcx], 0
0x180071de5  lea     rcx, [rbp+var_50]
0x180071de9  mov     dword ptr [rdx], 0
0x180071def  lea     rdx, [rbp+var_40]
0x180071df3  movups  xmmword ptr [rbp+var_30+0Eh], xmm0
0x180071df7  mov     [rbp+var_54], 2
0x180071dfe  mov     [rbp+var_60], 0
0x180071e06  call    cs:__imp_PolicyManager_GetPolicy
0x180071e0c  test    eax, eax
0x180071e0e  js      short loc_180071E36
0x180071e10  mov     rax, [rbp+var_60]
0x180071e14  cmp     dword ptr [rax+8], 1
0x180071e18  jnz     short loc_180071E36
0x180071e1a  cmp     dword ptr [rax+10h], 1
0x180071e1e  jnz     short loc_180071E26
0x180071e20  or      qword ptr [rbx], 4
0x180071e24  jmp     short loc_180071E30
0x180071e26  cmp     dword ptr [rax+10h], 2
0x180071e2a  jnz     short loc_180071E36
0x180071e2c  or      qword ptr [rbx], 1
0x180071e30  mov     dword ptr [rdi], 1
0x180071e36  lea     rcx, [rbp+var_60]
0x180071e3a  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x180071e3f  xor     eax, eax
0x180071e41  mov     rcx, [rbp+var_10]
0x180071e45  xor     rcx, rsp; StackCookie
0x180071e48  call    __security_check_cookie
0x180071e4d  lea     r11, [rsp+80h+var_s0]
0x180071e55  mov     rbx, [r11+20h]
0x180071e59  mov     rdi, [r11+28h]
0x180071e5d  mov     rsp, r11
0x180071e60  pop     rbp
0x180071e61  retn
```
