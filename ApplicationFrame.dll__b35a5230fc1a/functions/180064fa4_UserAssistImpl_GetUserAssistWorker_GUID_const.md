# UserAssistImpl::GetUserAssistWorker(_GUID const &)

- ea: `0x180064fa4`
- end: `0x18006503e`
- name: `?GetUserAssistWorker@UserAssistImpl@@YAPEAUIShellUserAssist@@AEBU_GUID@@@Z`
- size: `154`
- prototype: `struct IShellUserAssist *__fastcall(UserAssistImpl *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800674a8`

## callees

- `0x180064fa4`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180064fdd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180064fdd`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x180064fee`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x180064fee`

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
0x180064fa4  mov     r11, rsp
0x180064fa7  mov     [r11+8], rcx
0x180064fab  sub     rsp, 38h
0x180064faf  mov     rax, cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x180064fb6  test    rax, rax
0x180064fb9  jnz     short loc_18006502F
0x180064fbb  mov     [r11+8], rax
0x180064fbf  lea     r9, _GUID_49b36d57_5fd2_45a7_981b_06028d577a47; riid
0x180064fc6  lea     rax, [r11+8]
0x180064fca  xor     edx, edx; pUnkOuter
0x180064fcc  mov     r8d, 403h; dwClsContext
0x180064fd2  mov     [r11-18h], rax
0x180064fd6  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c; rclsid
0x180064fdd  call    cs:__imp_CoCreateInstance
0x180064fe3  test    eax, eax
0x180064fe5  js      short loc_180064FFB
0x180064fe7  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c
0x180064fee  call    cs:__imp_SHPinDllOfCLSID
0x180064ff4  mov     rcx, [rsp+38h+arg_0]
0x180064ff9  jmp     short loc_180065004
0x180064ffb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180064fff  mov     [rsp+38h+arg_0], rcx
0x180065004  xor     eax, eax
0x180065006  lock cmpxchg cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA, rcx; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x18006500f  jz      short loc_180065028
0x180065011  mov     rcx, [rsp+38h+arg_0]
0x180065016  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006501a  jz      short loc_180065028
0x18006501c  mov     rax, [rcx]
0x18006501f  mov     rax, [rax+10h]
0x180065023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065028  mov     rax, cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x18006502f  xor     ecx, ecx
0x180065031  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180065035  cmovz   rax, rcx
0x180065039  add     rsp, 38h
0x18006503d  retn
```
