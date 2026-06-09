# Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(long)

- ea: `0x1800272e0`
- end: `0x180027341`
- name: `?HandleRegGetValueResult@RegistryPolicyManager@Autopilot@Windows@Microsoft@@CAJJ@Z`
- size: `97`
- prototype: `static int(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027030`
- `0x1800270e0`

## callees

- `0x1800105f4`
- `0x1800272e0`

## string_xrefs

- `0x180027307`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(int a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = a1;
  if ( (unsigned int)(a1 - 2) <= 1 )
    return 2147943569LL;
  if ( a1 == 1630 )
  {
    v1 = -2147023267;
    v2 = 57;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\registrypolicymanager.cpp",
      (const char *)v1,
      v4);
    return v1;
  }
  if ( a1 > 0 )
    v1 = (unsigned __int16)a1 | 0x80070000;
  if ( (v1 & 0x80000000) != 0 )
  {
    v2 = 60;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800272e0  push    rbx; int
0x1800272e2  sub     rsp, 20h
0x1800272e6  lea     eax, [rcx-2]
0x1800272e9  mov     ebx, ecx
0x1800272eb  cmp     eax, 1
0x1800272ee  jbe     short loc_180027336
0x1800272f0  cmp     ecx, 65Eh
0x1800272f6  jnz     short loc_18002731A
0x1800272f8  mov     ebx, 8007065Dh
0x1800272fd  mov     edx, 39h ; '9'; void *
0x180027302  mov     rcx, [rsp+28h]; this
0x180027307  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002730e  mov     r9d, ebx; char *
0x180027311  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027316  mov     eax, ebx
0x180027318  jmp     short loc_18002733B
0x18002731a  test    ecx, ecx
0x18002731c  jle     short loc_180027327
0x18002731e  movzx   ebx, cx
0x180027321  or      ebx, 80070000h
0x180027327  test    ebx, ebx
0x180027329  jns     short loc_180027332
0x18002732b  mov     edx, 3Ch ; '<'
0x180027330  jmp     short loc_180027302
0x180027332  xor     eax, eax
0x180027334  jmp     short loc_18002733B
0x180027336  mov     eax, 80070491h
0x18002733b  add     rsp, 20h
0x18002733f  pop     rbx
0x180027340  retn
```
