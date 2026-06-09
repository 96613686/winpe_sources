# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotWhiteGloveUtils::GetDeviceAutopilotMode(EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *)

- ea: `0x180028380`
- end: `0x180028467`
- name: `?GetDeviceAutopilotMode@AutoPilotWhiteGloveUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEAW4AutopilotMode@234@@Z`
- size: `231`
- prototype: `__int64 __fastcall(enum EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001eaa8`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013de4`
- `0x180017a20`
- `0x180028380`
- `0x18002f010`

## string_xrefs

- `0x18002840d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicyinternal.cpp`
- `0x180028426`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotwhitegloveutils.cpp`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotWhiteGloveUtils::GetDeviceAutopilotMode(
        enum EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *a1)
{
  __int64 (__fastcall *v2)(void ***, _OWORD *, int *); // rbx
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-38h] BYREF
  _OWORD v6[2]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = 0;
  v2 = (__int64 (__fastcall *)(void ***, _OWORD *, int *))off_180043150[1];
  memset(v6, 0, sizeof(v6));
  std::wstring::_Construct<1,unsigned short const *>(v6, L"AutopilotMode", 0xDu);
  v3 = v2(&off_180043150, v6, &v5);
  std::wstring::_Tidy_deallocate((char **)v6);
  if ( (v3 & 0x80000000) == 0 )
  {
    *(_DWORD *)a1 = v5;
  }
  else
  {
    if ( v3 != -2147023727 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicyinternal.cpp",
        (const char *)v3,
        v5);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotwhitegloveutils.cpp",
        (const char *)v3,
        v5);
      return v3;
    }
    *(_DWORD *)a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180028380  mov     [rsp+arg_8], rbx
0x180028385  push    rdi
0x180028386  sub     rsp, 50h
0x18002838a  mov     rax, cs:__security_cookie
0x180028391  xor     rax, rsp
0x180028394  mov     [rsp+58h+var_10], rax
0x180028399  mov     rax, cs:off_180043150
0x1800283a0  lea     rdx, aAutopilotmode; "AutopilotMode"
0x1800283a7  mov     rdi, rcx
0x1800283aa  mov     [rsp+58h+var_38], 0; int
0x1800283b2  xorps   xmm0, xmm0
0x1800283b5  lea     rcx, [rsp+58h+var_30]
0x1800283ba  xorps   xmm1, xmm1
0x1800283bd  mov     r8d, 0Dh
0x1800283c3  mov     rbx, [rax+8]
0x1800283c7  movups  [rsp+58h+var_30], xmm0
0x1800283cc  movdqu  [rsp+58h+var_20], xmm1
0x1800283d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800283d7  lea     r8, [rsp+58h+var_38]
0x1800283dc  mov     rax, rbx
0x1800283df  lea     rdx, [rsp+58h+var_30]
0x1800283e4  lea     rcx, off_180043150
0x1800283eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283f0  lea     rcx, [rsp+58h+var_30]
0x1800283f5  mov     ebx, eax
0x1800283f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800283fc  test    ebx, ebx
0x1800283fe  jns     short loc_180028446
0x180028400  cmp     ebx, 80070491h
0x180028406  jz      short loc_18002843E
0x180028408  mov     rcx, [rsp+58h]; this
0x18002840d  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028414  mov     r9d, ebx; char *
0x180028417  mov     edx, 0AFh; void *
0x18002841c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028421  mov     rcx, [rsp+58h]; this
0x180028426  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002842d  mov     r9d, ebx; char *
0x180028430  mov     edx, 22h ; '"'; void *
0x180028435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002843a  mov     eax, ebx
0x18002843c  jmp     short loc_18002844E
0x18002843e  mov     dword ptr [rdi], 0
0x180028444  jmp     short loc_18002844C
0x180028446  mov     eax, [rsp+58h+var_38]
0x18002844a  mov     [rdi], eax
0x18002844c  xor     eax, eax
0x18002844e  mov     rcx, [rsp+58h+var_10]
0x180028453  xor     rcx, rsp; StackCookie
0x180028456  call    __security_check_cookie
0x18002845b  mov     rbx, [rsp+58h+arg_8]
0x180028460  add     rsp, 50h
0x180028464  pop     rdi
0x180028465  retn
```
