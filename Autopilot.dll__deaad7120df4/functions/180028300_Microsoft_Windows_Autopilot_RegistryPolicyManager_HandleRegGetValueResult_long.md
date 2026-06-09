# Microsoft::Windows::Autopilot::RegistryPolicyManager::HandleRegGetValueResult(long)

- ea: `0x180028300`
- end: `0x180028362`
- name: `?HandleRegGetValueResult@RegistryPolicyManager@Autopilot@Windows@Microsoft@@CAJJ@Z`
- size: `98`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028010`
- `0x1800280d0`

## callees

- `0x180010764`
- `0x180028300`

## string_xrefs

- `0x180028327`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\registrypolicymanager.cpp`

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
0x180028300  push    rbx; int
0x180028302  sub     rsp, 20h
0x180028306  lea     eax, [rcx-2]
0x180028309  mov     ebx, ecx
0x18002830b  cmp     eax, 1
0x18002830e  jbe     short loc_180028356
0x180028310  cmp     ecx, 65Eh
0x180028316  jnz     short loc_18002833A
0x180028318  mov     ebx, 8007065Dh
0x18002831d  mov     edx, 39h ; '9'; void *
0x180028322  mov     rcx, [rsp+28h]; this
0x180028327  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002832e  mov     r9d, ebx; char *
0x180028331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028336  mov     eax, ebx
0x180028338  jmp     short loc_18002835B
0x18002833a  test    ecx, ecx
0x18002833c  jle     short loc_180028347
0x18002833e  movzx   ebx, cx
0x180028341  or      ebx, 80070000h
0x180028347  test    ebx, ebx
0x180028349  jns     short loc_180028352
0x18002834b  mov     edx, 3Ch ; '<'
0x180028350  jmp     short loc_180028322
0x180028352  xor     eax, eax
0x180028354  jmp     short loc_18002835B
0x180028356  mov     eax, 80070491h
0x18002835b  add     rsp, 20h
0x18002835f  pop     rbx
0x180028360  retn
```
