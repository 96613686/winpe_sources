# Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)

- ea: `0x180020c34`
- end: `0x180020cc1`
- name: `?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z`
- size: `141`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e260`
- `0x18001e514`

## callees

- `0x1800166dc`
- `0x180020c34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020c78`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020c78`

## string_xrefs

- `0x180020c99`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

## pseudocode

```c
int __fastcall Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int ValueW; // eax
  unsigned int v7; // [rsp+20h] [rbp-38h]
  DWORD v8[6]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v10; // [rsp+60h] [rbp+8h] BYREF
  int v11; // [rsp+64h] [rbp+Ch]

  v11 = HIDWORD(a1);
  v10 = 0;
  v8[0] = 4;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, a2, a3, 0x10u, 0, &v10, v8);
  if ( ValueW - 2 <= 1 )
    return -2147023727;
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1A4,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateutils.cpp",
             (const char *)ValueW,
             v7);
  *a4 = v10;
  return 0;
}

```

## disassembly

```asm
0x180020c34  mov     r11, rsp
0x180020c37  mov     [r11+8], rcx
0x180020c3b  push    rbx
0x180020c3c  sub     rsp, 50h
0x180020c40  mov     rbx, r9
0x180020c43  mov     [rsp+58h+arg_0], 0
0x180020c4b  mov     [rsp+58h+var_18], 4
0x180020c53  lea     rax, [r11-18h]
0x180020c57  mov     [r11-28h], rax
0x180020c5b  lea     rax, [r11+8]
0x180020c5f  mov     [r11-30h], rax
0x180020c63  mov     qword ptr [r11-38h], 0
0x180020c6b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180020c72  mov     r9d, 10h; dwFlags
0x180020c78  call    cs:__imp_RegGetValueW
0x180020c7e  lea     ecx, [rax-2]
0x180020c81  cmp     ecx, 1
0x180020c84  ja      short loc_180020C8D
0x180020c86  mov     eax, 80070491h
0x180020c8b  jmp     short loc_180020CBA
0x180020c8d  test    eax, eax
0x180020c8f  jz      short loc_180020CAC
0x180020c91  mov     rcx, [rsp+58h]; this
0x180020c96  mov     r9d, eax; char *
0x180020c99  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020ca0  mov     edx, 1A4h; void *
0x180020ca5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020caa  jmp     short loc_180020CBA
0x180020cac  mov     eax, [rsp+58h+arg_0]
0x180020cb0  mov     [rbx], eax
0x180020cb2  xor     eax, eax
0x180020cb4  jmp     short loc_180020CBA
0x180020cb6  mov     eax, [rsp+58h+arg_0]
0x180020cba  add     rsp, 50h
0x180020cbe  pop     rbx
0x180020cbf  retn
```
