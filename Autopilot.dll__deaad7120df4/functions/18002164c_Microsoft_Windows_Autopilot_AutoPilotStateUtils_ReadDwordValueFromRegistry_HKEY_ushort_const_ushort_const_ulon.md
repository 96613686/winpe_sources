# Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadDwordValueFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong &)

- ea: `0x18002164c`
- end: `0x1800216df`
- name: `?ReadDwordValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAK@Z`
- size: `147`
- prototype: `int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eaa8`
- `0x18001ed68`

## callees

- `0x180016b80`
- `0x18002164c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021690`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180021690`

## string_xrefs

- `0x1800216b7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateutils.cpp`

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
0x18002164c  mov     r11, rsp
0x18002164f  mov     [r11+8], rcx
0x180021653  push    rbx
0x180021654  sub     rsp, 50h
0x180021658  mov     rbx, r9
0x18002165b  mov     [rsp+58h+arg_0], 0
0x180021663  mov     [rsp+58h+var_18], 4
0x18002166b  lea     rax, [r11-18h]
0x18002166f  mov     [r11-28h], rax
0x180021673  lea     rax, [r11+8]
0x180021677  mov     [r11-30h], rax
0x18002167b  mov     qword ptr [r11-38h], 0
0x180021683  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002168a  mov     r9d, 10h; dwFlags
0x180021690  call    cs:__imp_RegGetValueW
0x180021697  nop     dword ptr [rax+rax+00h]
0x18002169c  lea     ecx, [rax-2]
0x18002169f  cmp     ecx, 1
0x1800216a2  ja      short loc_1800216AB
0x1800216a4  mov     eax, 80070491h
0x1800216a9  jmp     short loc_1800216D8
0x1800216ab  test    eax, eax
0x1800216ad  jz      short loc_1800216CA
0x1800216af  mov     rcx, [rsp+58h]; this
0x1800216b4  mov     r9d, eax; char *
0x1800216b7  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800216be  mov     edx, 1A4h; void *
0x1800216c3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800216c8  jmp     short loc_1800216D8
0x1800216ca  mov     eax, [rsp+58h+arg_0]
0x1800216ce  mov     [rbx], eax
0x1800216d0  xor     eax, eax
0x1800216d2  jmp     short loc_1800216D8
0x1800216d4  mov     eax, [rsp+58h+arg_0]
0x1800216d8  add     rsp, 50h
0x1800216dc  pop     rbx
0x1800216dd  retn
```
