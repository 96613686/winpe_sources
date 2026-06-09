# EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotWhiteGloveUtils::GetDeviceAutopilotMode(EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *)

- ea: `0x18002735c`
- end: `0x180027442`
- name: `?GetDeviceAutopilotMode@AutoPilotWhiteGloveUtils@AutoPilot@Service@EnterpriseDeviceManagement@@SAJPEAW4AutopilotMode@234@@Z`
- size: `230`
- prototype: `__int64 __fastcall(enum EnterpriseDeviceManagement::Service::AutoPilot::AutopilotMode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e260`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013a40`
- `0x1800174f0`
- `0x18002735c`
- `0x18002e010`

## string_xrefs

- `0x1800273e9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicyinternal.cpp`
- `0x180027402`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotwhitegloveutils.cpp`

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
  v2 = (__int64 (__fastcall *)(void ***, _OWORD *, int *))off_180042150[1];
  memset(v6, 0, sizeof(v6));
  std::wstring::_Construct<1,unsigned short const *>(v6, L"AutopilotMode", 13);
  v3 = v2(&off_180042150, v6, &v5);
  std::wstring::_Tidy_deallocate(v6);
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
0x18002735c  mov     [rsp+arg_8], rbx
0x180027361  push    rdi
0x180027362  sub     rsp, 50h
0x180027366  mov     rax, cs:__security_cookie
0x18002736d  xor     rax, rsp
0x180027370  mov     [rsp+58h+var_10], rax
0x180027375  mov     rax, cs:off_180042150
0x18002737c  lea     rdx, aAutopilotmode; "AutopilotMode"
0x180027383  mov     rdi, rcx
0x180027386  mov     [rsp+58h+var_38], 0; int
0x18002738e  xorps   xmm0, xmm0
0x180027391  lea     rcx, [rsp+58h+var_30]
0x180027396  xorps   xmm1, xmm1
0x180027399  mov     r8d, 0Dh
0x18002739f  mov     rbx, [rax+8]
0x1800273a3  movups  [rsp+58h+var_30], xmm0
0x1800273a8  movdqu  [rsp+58h+var_20], xmm1
0x1800273ae  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800273b3  lea     r8, [rsp+58h+var_38]
0x1800273b8  mov     rax, rbx
0x1800273bb  lea     rdx, [rsp+58h+var_30]
0x1800273c0  lea     rcx, off_180042150
0x1800273c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273cc  lea     rcx, [rsp+58h+var_30]
0x1800273d1  mov     ebx, eax
0x1800273d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800273d8  test    ebx, ebx
0x1800273da  jns     short loc_180027422
0x1800273dc  cmp     ebx, 80070491h
0x1800273e2  jz      short loc_18002741A
0x1800273e4  mov     rcx, [rsp+58h]; this
0x1800273e9  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800273f0  mov     r9d, ebx; char *
0x1800273f3  mov     edx, 0AFh; void *
0x1800273f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800273fd  mov     rcx, [rsp+58h]; this
0x180027402  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027409  mov     r9d, ebx; char *
0x18002740c  mov     edx, 22h ; '"'; void *
0x180027411  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027416  mov     eax, ebx
0x180027418  jmp     short loc_18002742A
0x18002741a  mov     dword ptr [rdi], 0
0x180027420  jmp     short loc_180027428
0x180027422  mov     eax, [rsp+58h+var_38]
0x180027426  mov     [rdi], eax
0x180027428  xor     eax, eax
0x18002742a  mov     rcx, [rsp+58h+var_10]
0x18002742f  xor     rcx, rsp; StackCookie
0x180027432  call    __security_check_cookie
0x180027437  mov     rbx, [rsp+58h+arg_8]
0x18002743c  add     rsp, 50h
0x180027440  pop     rdi
0x180027441  retn
```
