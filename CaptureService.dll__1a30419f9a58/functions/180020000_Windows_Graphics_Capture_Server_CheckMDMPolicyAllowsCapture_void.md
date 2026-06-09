# Windows::Graphics::Capture::Server::CheckMDMPolicyAllowsCapture(void)

- ea: `0x180020000`
- end: `0x180020065`
- name: `?CheckMDMPolicyAllowsCapture@Server@Capture@Graphics@Windows@@YAJXZ`
- size: `101`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180012f30`
- `0x18001d350`

## callees

- `0x18000907c`
- `0x180020000`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyInt` at `0x180020021`
- `policymanager!PolicyManager_GetPolicyInt` at `0x180020021`

## string_xrefs

- `0x180020037`: `onecoreuap\windows\dwm\capture\svc\dll\policy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CheckMDMPolicyAllowsCapture(
        Windows::Graphics::Capture::Server *this)
{
  int PolicyInt; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"Experience", L"AllowScreenCapture", &v6);
  if ( PolicyInt < 0 )
  {
    v2 = 20;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\policy.cpp",
      (const char *)(unsigned int)PolicyInt,
      v4);
    return (unsigned int)PolicyInt;
  }
  if ( !v6 )
  {
    PolicyInt = -2147024891;
    v2 = 23;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180020000  push    rbx; int
0x180020002  sub     rsp, 20h
0x180020006  lea     r8, [rsp+28h+arg_0]
0x18002000b  mov     [rsp+28h+arg_0], 0
0x180020013  lea     rdx, aAllowscreencap; "AllowScreenCapture"
0x18002001a  lea     rcx, aExperience; "Experience"
0x180020021  call    cs:__imp_PolicyManager_GetPolicyInt
0x180020027  mov     ebx, eax
0x180020029  test    eax, eax
0x18002002b  jns     short loc_18002004A
0x18002002d  mov     edx, 14h; void *
0x180020032  mov     rcx, [rsp+28h]; this
0x180020037  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18002003e  mov     r9d, ebx; char *
0x180020041  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020046  mov     eax, ebx
0x180020048  jmp     short loc_18002005F
0x18002004a  cmp     [rsp+28h+arg_0], 0
0x18002004f  jnz     short loc_18002005D
0x180020051  mov     ebx, 80070005h
0x180020056  mov     edx, 17h
0x18002005b  jmp     short loc_180020032
0x18002005d  xor     eax, eax
0x18002005f  add     rsp, 20h
0x180020063  pop     rbx
0x180020064  retn
```
