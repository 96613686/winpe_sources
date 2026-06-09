# Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(ushort const *,ulong *)

- ea: `0x1800189a4`
- end: `0x180018b2f`
- name: `?GetDwordPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAK@Z`
- size: `395`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012960`
- `0x180012ab0`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x1800185f8`
- `0x1800189a4`
- `0x180018b38`
- `0x18001ecc4`
- `0x18002f010`

## string_xrefs

- `0x1800189f9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018ab5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(
        const unsigned __int16 *a1,
        unsigned int *a2)
{
  int JsonFromRegistry; // eax
  unsigned int v5; // r8d
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, PVOID, double *); // rbx
  HSTRING_HEADER *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-40h] BYREF
  double v15; // [rsp+28h] [rbp-38h] BYREF
  const WCHAR *v16; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER v17; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v16 = a1;
  if ( Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled() )
    return 2147943569LL;
  v14 = 0;
  JsonFromRegistry = Microsoft::Windows::Autopilot::GetJsonFromRegistry(&v14);
  v6 = JsonFromRegistry;
  if ( JsonFromRegistry < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)(unsigned int)JsonFromRegistry,
      v14);
    v7 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v6;
  }
  v15 = 0.0;
  v8 = v14;
  v9 = *(__int64 (__fastcall **)(__int64, PVOID, double *))(*(_QWORD *)v14 + 88LL);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v17, &v16, v5);
  v6 = v9(v8, v10[1].Reserved.Reserved1, &v15);
  if ( v6 == -2089484279 )
  {
    v6 = -2147023727;
  }
  else if ( v6 == -2147483634 )
  {
    v6 = -2147023267;
  }
  if ( v6 == -2147023727 )
  {
    v11 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return 2147943569LL;
  }
  else
  {
    if ( (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)v6,
        v14);
      v12 = v14;
      if ( v14 )
      {
        v14 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      return v6;
    }
    *a2 = (int)v15;
    v13 = v14;
    if ( v14 )
    {
      v14 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800189a4  mov     [rsp-18h+arg_10], rbx
0x1800189a9  push    rbp
0x1800189aa  push    rsi
0x1800189ab  push    rdi
0x1800189ac  mov     rbp, rsp
0x1800189af  sub     rsp, 60h
0x1800189b3  mov     rax, cs:__security_cookie
0x1800189ba  xor     rax, rsp
0x1800189bd  mov     [rbp+var_8], rax
0x1800189c1  mov     rsi, rdx
0x1800189c4  mov     [rbp+var_30], rcx
0x1800189c8  call    ?IsDisabled@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled(void)
0x1800189cd  test    al, al
0x1800189cf  jz      short loc_1800189DB
0x1800189d1  mov     eax, 80070491h
0x1800189d6  jmp     loc_180018B12
0x1800189db  mov     [rbp+var_40], 0
0x1800189e3  lea     rcx, [rbp+var_40]
0x1800189e7  call    ?GetJsonFromRegistry@Autopilot@Windows@Microsoft@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@3@@Z; Microsoft::Windows::Autopilot::GetJsonFromRegistry(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800189ec  mov     ebx, eax
0x1800189ee  test    eax, eax
0x1800189f0  jns     short loc_180018A30
0x1800189f2  mov     rcx, [rbp+18h]; this
0x1800189f6  mov     r9d, eax; char *
0x1800189f9  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018a00  mov     edx, 67h ; 'g'; void *
0x180018a05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a0a  nop
0x180018a0b  mov     rcx, [rbp+var_40]
0x180018a0f  test    rcx, rcx
0x180018a12  jz      short loc_180018A29
0x180018a14  mov     [rbp+var_40], 0
0x180018a1c  mov     rax, [rcx]
0x180018a1f  mov     rax, [rax+10h]
0x180018a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a28  nop
0x180018a29  mov     eax, ebx
0x180018a2b  jmp     loc_180018B12
0x180018a30  xorps   xmm0, xmm0
0x180018a33  movsd   [rbp+var_38], xmm0
0x180018a38  mov     rdi, [rbp+var_40]
0x180018a3c  mov     rax, [rdi]
0x180018a3f  mov     rbx, [rax+58h]
0x180018a43  lea     rdx, [rbp+var_30]
0x180018a47  lea     rcx, [rbp+var_28]
0x180018a4b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180018a50  nop
0x180018a51  lea     r8, [rbp+var_38]
0x180018a55  mov     rdx, [rax+18h]
0x180018a59  mov     rcx, rdi
0x180018a5c  mov     rax, rbx
0x180018a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a64  mov     ebx, eax
0x180018a66  mov     edi, 80070491h
0x180018a6b  cmp     eax, 83750009h
0x180018a70  jnz     short loc_180018A76
0x180018a72  mov     ebx, edi
0x180018a74  jmp     short loc_180018A84
0x180018a76  mov     eax, 8007065Dh
0x180018a7b  cmp     ebx, 8000000Eh
0x180018a81  cmovz   ebx, eax
0x180018a84  cmp     ebx, edi
0x180018a86  jnz     short loc_180018AAA
0x180018a88  mov     rcx, [rbp+var_40]
0x180018a8c  test    rcx, rcx
0x180018a8f  jz      short loc_180018AA6
0x180018a91  mov     [rbp+var_40], 0
0x180018a99  mov     rax, [rcx]
0x180018a9c  mov     rax, [rax+10h]
0x180018aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aa5  nop
0x180018aa6  mov     eax, edi
0x180018aa8  jmp     short loc_180018B12
0x180018aaa  test    ebx, ebx
0x180018aac  jns     short loc_180018AEA
0x180018aae  mov     rcx, [rbp+18h]; this
0x180018ab2  mov     r9d, ebx; char *
0x180018ab5  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018abc  mov     edx, 6Ch ; 'l'; void *
0x180018ac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ac6  nop
0x180018ac7  mov     rcx, [rbp+var_40]
0x180018acb  test    rcx, rcx
0x180018ace  jz      short loc_180018AE5
0x180018ad0  mov     [rbp+var_40], 0
0x180018ad8  mov     rdx, [rcx]
0x180018adb  mov     rax, [rdx+10h]
0x180018adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ae4  nop
0x180018ae5  jmp     loc_180018A29
0x180018aea  cvttsd2si rax, [rbp+var_38]
0x180018af0  mov     [rsi], eax
0x180018af2  mov     rcx, [rbp+var_40]
0x180018af6  test    rcx, rcx
0x180018af9  jz      short loc_180018B10
0x180018afb  mov     [rbp+var_40], 0
0x180018b03  mov     rax, [rcx]
0x180018b06  mov     rax, [rax+10h]
0x180018b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b0f  nop
0x180018b10  xor     eax, eax
0x180018b12  mov     rcx, [rbp+var_8]
0x180018b16  xor     rcx, rsp; StackCookie
0x180018b19  call    __security_check_cookie
0x180018b1e  mov     rbx, [rsp+60h+arg_10]
0x180018b26  add     rsp, 60h
0x180018b2a  pop     rdi
0x180018b2b  pop     rsi
0x180018b2c  pop     rbp
0x180018b2d  retn
```
