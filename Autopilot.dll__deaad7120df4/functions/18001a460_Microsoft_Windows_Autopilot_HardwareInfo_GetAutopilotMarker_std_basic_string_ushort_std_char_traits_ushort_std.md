# Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotMarker(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001a460`
- end: `0x18001a508`
- name: `?GetAutopilotMarker@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180017a20`
- `0x18001982c`
- `0x18001a460`
- `0x180020d20`

## string_xrefs

- `0x18001a4c1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotMarker(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 v3; // r8
  int v5[4]; // [rsp+20h] [rbp-38h] BYREF
  __m128i si128; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v5 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v5[0]) = 0;
  v2 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(v5);
  if ( (int)(v2 + 0x80000000) < 0 || v2 == -2147024895 )
  {
    std::wstring::operator=(a1, v5, v3);
    v2 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v2,
      v5[0]);
  }
  std::wstring::_Tidy_deallocate((char **)v5);
  return v2;
}

```

## disassembly

```asm
0x18001a460  mov     [rsp+arg_8], rbx
0x18001a465  push    rdi
0x18001a466  sub     rsp, 50h
0x18001a46a  mov     rax, cs:__security_cookie
0x18001a471  xor     rax, rsp
0x18001a474  mov     [rsp+58h+var_18], rax
0x18001a479  mov     rdi, rcx
0x18001a47c  xorps   xmm0, xmm0
0x18001a47f  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18001a484  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001a48c  movdqu  [rsp+58h+var_28], xmm1
0x18001a492  xor     eax, eax
0x18001a494  mov     word ptr [rsp+58h+var_38], ax; int
0x18001a499  lea     rcx, [rsp+58h+var_38]
0x18001a49e  call    ?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::wstring &)
0x18001a4a3  mov     ebx, eax
0x18001a4a5  mov     eax, 80000000h
0x18001a4aa  lea     ecx, [rbx+rax]
0x18001a4ad  test    eax, ecx
0x18001a4af  jnz     short loc_18001A4D4
0x18001a4b1  cmp     ebx, 80070001h
0x18001a4b7  jz      short loc_18001A4D4
0x18001a4b9  mov     rcx, [rsp+58h]; this
0x18001a4be  mov     r9d, ebx; char *
0x18001a4c1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001a4c8  mov     edx, 0E7h; void *
0x18001a4cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a4d2  jmp     short loc_18001A4E3
0x18001a4d4  lea     rdx, [rsp+58h+var_38]
0x18001a4d9  mov     rcx, rdi
0x18001a4dc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001a4e1  xor     ebx, ebx
0x18001a4e3  lea     rcx, [rsp+58h+var_38]
0x18001a4e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a4ed  mov     eax, ebx
0x18001a4ef  mov     rcx, [rsp+58h+var_18]
0x18001a4f4  xor     rcx, rsp; StackCookie
0x18001a4f7  call    __security_check_cookie
0x18001a4fc  mov     rbx, [rsp+58h+arg_8]
0x18001a501  add     rsp, 50h
0x18001a505  pop     rdi
0x18001a506  retn
```
