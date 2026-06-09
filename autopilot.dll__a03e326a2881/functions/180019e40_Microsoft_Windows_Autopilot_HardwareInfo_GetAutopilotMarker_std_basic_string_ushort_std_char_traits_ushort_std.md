# Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotMarker(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180019e40`
- end: `0x180019ee7`
- name: `?GetAutopilotMarker@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800174f0`
- `0x180019230`
- `0x180019e40`
- `0x1800203bc`

## string_xrefs

- `0x180019ea1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotMarker(__int64 a1)
{
  unsigned int v2; // ebx
  int v4[4]; // [rsp+20h] [rbp-38h] BYREF
  __m128i si128; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v4 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v4[0]) = 0;
  v2 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker((__int64)v4);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147024895 )
  {
    std::wstring::operator=(a1, v4);
    v2 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v2,
      v4[0]);
  }
  std::wstring::_Tidy_deallocate(v4);
  return v2;
}

```

## disassembly

```asm
0x180019e40  mov     [rsp+arg_8], rbx
0x180019e45  push    rdi
0x180019e46  sub     rsp, 50h
0x180019e4a  mov     rax, cs:__security_cookie
0x180019e51  xor     rax, rsp
0x180019e54  mov     [rsp+58h+var_18], rax
0x180019e59  mov     rdi, rcx
0x180019e5c  xorps   xmm0, xmm0
0x180019e5f  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x180019e64  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180019e6c  movdqu  [rsp+58h+var_28], xmm1
0x180019e72  xor     eax, eax
0x180019e74  mov     word ptr [rsp+58h+var_38], ax; int
0x180019e79  lea     rcx, [rsp+58h+var_38]
0x180019e7e  call    ?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::wstring &)
0x180019e83  mov     ebx, eax
0x180019e85  mov     eax, 80000000h
0x180019e8a  lea     ecx, [rbx+rax]
0x180019e8d  test    eax, ecx
0x180019e8f  jnz     short loc_180019EB4
0x180019e91  cmp     ebx, 80070001h
0x180019e97  jz      short loc_180019EB4
0x180019e99  mov     rcx, [rsp+58h]; this
0x180019e9e  mov     r9d, ebx; char *
0x180019ea1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019ea8  mov     edx, 0E7h; void *
0x180019ead  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019eb2  jmp     short loc_180019EC3
0x180019eb4  lea     rdx, [rsp+58h+var_38]
0x180019eb9  mov     rcx, rdi
0x180019ebc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180019ec1  xor     ebx, ebx
0x180019ec3  lea     rcx, [rsp+58h+var_38]
0x180019ec8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019ecd  mov     eax, ebx
0x180019ecf  mov     rcx, [rsp+58h+var_18]
0x180019ed4  xor     rcx, rsp; StackCookie
0x180019ed7  call    __security_check_cookie
0x180019edc  mov     rbx, [rsp+58h+arg_8]
0x180019ee1  add     rsp, 50h
0x180019ee5  pop     rdi
0x180019ee6  retn
```
