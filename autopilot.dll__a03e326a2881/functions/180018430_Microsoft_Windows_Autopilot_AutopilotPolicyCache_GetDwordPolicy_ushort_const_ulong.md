# Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(ushort const *,ulong *)

- ea: `0x180018430`
- end: `0x1800185ba`
- name: `?GetDwordPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAK@Z`
- size: `394`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012720`
- `0x180012870`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800180a8`
- `0x180018430`
- `0x1800185c0`
- `0x18001e470`
- `0x18002e010`

## string_xrefs

- `0x180018485`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018541`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(
        const unsigned __int16 *a1,
        unsigned int *a2)
{
  __int64 v3; // rdx
  int JsonFromRegistry; // eax
  unsigned int v6; // r8d
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, PVOID, double *); // rbx
  HSTRING_HEADER *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+20h] [rbp-40h] BYREF
  double v16; // [rsp+28h] [rbp-38h] BYREF
  const WCHAR *v17; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER v18; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v17 = a1;
  if ( Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled() )
    return 2147943569LL;
  v15 = 0;
  JsonFromRegistry = Microsoft::Windows::Autopilot::GetJsonFromRegistry(&v15, v3);
  v7 = JsonFromRegistry;
  if ( JsonFromRegistry < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)(unsigned int)JsonFromRegistry,
      v15);
    v8 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  v16 = 0.0;
  v9 = v15;
  v10 = *(__int64 (__fastcall **)(__int64, PVOID, double *))(*(_QWORD *)v15 + 88LL);
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v18, &v17, v6);
  v7 = v10(v9, v11[1].Reserved.Reserved1, &v16);
  if ( v7 == -2089484279 )
  {
    v7 = -2147023727;
  }
  else if ( v7 == -2147483634 )
  {
    v7 = -2147023267;
  }
  if ( v7 == -2147023727 )
  {
    v12 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return 2147943569LL;
  }
  else
  {
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)v7,
        v15);
      v13 = v15;
      if ( v15 )
      {
        v15 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return v7;
    }
    *a2 = (int)v16;
    v14 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180018430  mov     [rsp-18h+arg_10], rbx
0x180018435  push    rbp
0x180018436  push    rsi
0x180018437  push    rdi
0x180018438  mov     rbp, rsp
0x18001843b  sub     rsp, 60h
0x18001843f  mov     rax, cs:__security_cookie
0x180018446  xor     rax, rsp
0x180018449  mov     [rbp+var_8], rax
0x18001844d  mov     rsi, rdx
0x180018450  mov     [rbp+var_30], rcx
0x180018454  call    ?IsDisabled@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled(void)
0x180018459  test    al, al
0x18001845b  jz      short loc_180018467
0x18001845d  mov     eax, 80070491h
0x180018462  jmp     loc_18001859E
0x180018467  mov     [rbp+var_40], 0
0x18001846f  lea     rcx, [rbp+var_40]
0x180018473  call    ?GetJsonFromRegistry@Autopilot@Windows@Microsoft@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@3@@Z; Microsoft::Windows::Autopilot::GetJsonFromRegistry(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180018478  mov     ebx, eax
0x18001847a  test    eax, eax
0x18001847c  jns     short loc_1800184BC
0x18001847e  mov     rcx, [rbp+18h]; this
0x180018482  mov     r9d, eax; char *
0x180018485  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001848c  mov     edx, 67h ; 'g'; void *
0x180018491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018496  nop
0x180018497  mov     rcx, [rbp+var_40]
0x18001849b  test    rcx, rcx
0x18001849e  jz      short loc_1800184B5
0x1800184a0  mov     [rbp+var_40], 0
0x1800184a8  mov     rax, [rcx]
0x1800184ab  mov     rax, [rax+10h]
0x1800184af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184b4  nop
0x1800184b5  mov     eax, ebx
0x1800184b7  jmp     loc_18001859E
0x1800184bc  xorps   xmm0, xmm0
0x1800184bf  movsd   [rbp+var_38], xmm0
0x1800184c4  mov     rdi, [rbp+var_40]
0x1800184c8  mov     rax, [rdi]
0x1800184cb  mov     rbx, [rax+58h]
0x1800184cf  lea     rdx, [rbp+var_30]
0x1800184d3  lea     rcx, [rbp+var_28]
0x1800184d7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800184dc  nop
0x1800184dd  lea     r8, [rbp+var_38]
0x1800184e1  mov     rdx, [rax+18h]
0x1800184e5  mov     rcx, rdi
0x1800184e8  mov     rax, rbx
0x1800184eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184f0  mov     ebx, eax
0x1800184f2  mov     edi, 80070491h
0x1800184f7  cmp     eax, 83750009h
0x1800184fc  jnz     short loc_180018502
0x1800184fe  mov     ebx, edi
0x180018500  jmp     short loc_180018510
0x180018502  mov     eax, 8007065Dh
0x180018507  cmp     ebx, 8000000Eh
0x18001850d  cmovz   ebx, eax
0x180018510  cmp     ebx, edi
0x180018512  jnz     short loc_180018536
0x180018514  mov     rcx, [rbp+var_40]
0x180018518  test    rcx, rcx
0x18001851b  jz      short loc_180018532
0x18001851d  mov     [rbp+var_40], 0
0x180018525  mov     rax, [rcx]
0x180018528  mov     rax, [rax+10h]
0x18001852c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018531  nop
0x180018532  mov     eax, edi
0x180018534  jmp     short loc_18001859E
0x180018536  test    ebx, ebx
0x180018538  jns     short loc_180018576
0x18001853a  mov     rcx, [rbp+18h]; this
0x18001853e  mov     r9d, ebx; char *
0x180018541  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018548  mov     edx, 6Ch ; 'l'; void *
0x18001854d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018552  nop
0x180018553  mov     rcx, [rbp+var_40]
0x180018557  test    rcx, rcx
0x18001855a  jz      short loc_180018571
0x18001855c  mov     [rbp+var_40], 0
0x180018564  mov     rdx, [rcx]
0x180018567  mov     rax, [rdx+10h]
0x18001856b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018570  nop
0x180018571  jmp     loc_1800184B5
0x180018576  cvttsd2si rax, [rbp+var_38]
0x18001857c  mov     [rsi], eax
0x18001857e  mov     rcx, [rbp+var_40]
0x180018582  test    rcx, rcx
0x180018585  jz      short loc_18001859C
0x180018587  mov     [rbp+var_40], 0
0x18001858f  mov     rax, [rcx]
0x180018592  mov     rax, [rax+10h]
0x180018596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001859b  nop
0x18001859c  xor     eax, eax
0x18001859e  mov     rcx, [rbp+var_8]
0x1800185a2  xor     rcx, rsp; StackCookie
0x1800185a5  call    __security_check_cookie
0x1800185aa  mov     rbx, [rsp+60h+arg_10]
0x1800185b2  add     rsp, 60h
0x1800185b6  pop     rdi
0x1800185b7  pop     rsi
0x1800185b8  pop     rbp
0x1800185b9  retn
```
