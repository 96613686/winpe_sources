# UserAssistImpl::GetUserAssistWorker(_GUID const &)

- ea: `0x180046240`
- end: `0x1800462da`
- name: `?GetUserAssistWorker@UserAssistImpl@@YAPEAUIShellUserAssist@@AEBU_GUID@@@Z`
- size: `154`
- prototype: `struct IShellUserAssist *__fastcall(UserAssistImpl *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800487a8`

## callees

- `0x180046240`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046279`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046279`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x18004628a`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x18004628a`

## pseudocode

```c
struct IShellUserAssist *__fastcall UserAssistImpl::GetUserAssistWorker(UserAssistImpl *this, const struct _GUID *a2)
{
  struct IShellUserAssist *result; // rax
  signed __int64 v3; // rcx
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = (__int64)this;
  result = UserAssistImpl::g_cachedUserAssist;
  if ( !UserAssistImpl::g_cachedUserAssist )
  {
    v4 = 0;
    if ( CoCreateInstance(
           &GUID_dd313e04_feff_11d1_8ecd_0000f87a470c,
           0,
           0x403u,
           &GUID_49b36d57_5fd2_45a7_981b_06028d577a47,
           (LPVOID *)&v4) < 0 )
    {
      v3 = -1;
      v4 = -1;
    }
    else
    {
      SHPinDllOfCLSID(&GUID_dd313e04_feff_11d1_8ecd_0000f87a470c);
      v3 = v4;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&UserAssistImpl::g_cachedUserAssist, v3, 0)
      && v4 != -1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    result = UserAssistImpl::g_cachedUserAssist;
  }
  if ( result == (struct IShellUserAssist *)-1LL )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180046240  mov     r11, rsp
0x180046243  mov     [r11+8], rcx
0x180046247  sub     rsp, 38h
0x18004624b  mov     rax, cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x180046252  test    rax, rax
0x180046255  jnz     short loc_1800462CB
0x180046257  mov     [r11+8], rax
0x18004625b  lea     r9, _GUID_49b36d57_5fd2_45a7_981b_06028d577a47; riid
0x180046262  lea     rax, [r11+8]
0x180046266  xor     edx, edx; pUnkOuter
0x180046268  mov     r8d, 403h; dwClsContext
0x18004626e  mov     [r11-18h], rax
0x180046272  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c; rclsid
0x180046279  call    cs:__imp_CoCreateInstance
0x18004627f  test    eax, eax
0x180046281  js      short loc_180046297
0x180046283  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c
0x18004628a  call    cs:__imp_SHPinDllOfCLSID
0x180046290  mov     rcx, [rsp+38h+arg_0]
0x180046295  jmp     short loc_1800462A0
0x180046297  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004629b  mov     [rsp+38h+arg_0], rcx
0x1800462a0  xor     eax, eax
0x1800462a2  lock cmpxchg cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA, rcx; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x1800462ab  jz      short loc_1800462C4
0x1800462ad  mov     rcx, [rsp+38h+arg_0]
0x1800462b2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800462b6  jz      short loc_1800462C4
0x1800462b8  mov     rax, [rcx]
0x1800462bb  mov     rax, [rax+10h]
0x1800462bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800462c4  mov     rax, cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x1800462cb  xor     ecx, ecx
0x1800462cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800462d1  cmovz   rax, rcx
0x1800462d5  add     rsp, 38h
0x1800462d9  retn
```
