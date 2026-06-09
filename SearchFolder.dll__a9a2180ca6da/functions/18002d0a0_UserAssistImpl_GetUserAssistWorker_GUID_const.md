# UserAssistImpl::GetUserAssistWorker(_GUID const &)

- ea: `0x18002d0a0`
- end: `0x18002d131`
- name: `?GetUserAssistWorker@UserAssistImpl@@YAPEAUIShellUserAssist@@AEBU_GUID@@@Z`
- size: `145`
- prototype: `struct IShellUserAssist *__fastcall(UserAssistImpl *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002ff6c`

## callees

- `0x18002d0a0`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x18002d0e0`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x18002d0e0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d0d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d0d3`

## pseudocode

```c
struct IShellUserAssist *__fastcall UserAssistImpl::GetUserAssistWorker(const IID *this, const struct _GUID *a2)
{
  struct IShellUserAssist *result; // rax
  signed __int64 v4; // rcx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  result = UserAssistImpl::g_cachedUserAssist;
  if ( !UserAssistImpl::g_cachedUserAssist )
  {
    ppv = 0;
    if ( CoCreateInstance(this, 0, 0x403u, &GUID_49b36d57_5fd2_45a7_981b_06028d577a47, &ppv) < 0 )
    {
      v4 = -1;
      ppv = (LPVOID)-1LL;
    }
    else
    {
      SHPinDllOfCLSID(this);
      v4 = (signed __int64)ppv;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&UserAssistImpl::g_cachedUserAssist, v4, 0)
      && ppv != (LPVOID)-1LL )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
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
0x18002d0a0  push    rbx
0x18002d0a2  sub     rsp, 30h
0x18002d0a6  mov     rax, cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x18002d0ad  mov     rbx, rcx
0x18002d0b0  test    rax, rax
0x18002d0b3  jnz     short loc_18002D121
0x18002d0b5  mov     [rsp+38h+arg_8], rax
0x18002d0ba  lea     r9, _GUID_49b36d57_5fd2_45a7_981b_06028d577a47; riid
0x18002d0c1  lea     rax, [rsp+38h+arg_8]
0x18002d0c6  xor     edx, edx; pUnkOuter
0x18002d0c8  mov     r8d, 403h; dwClsContext
0x18002d0ce  mov     [rsp+38h+ppv], rax; ppv
0x18002d0d3  call    cs:__imp_CoCreateInstance
0x18002d0d9  test    eax, eax
0x18002d0db  js      short loc_18002D0ED
0x18002d0dd  mov     rcx, rbx
0x18002d0e0  call    cs:__imp_SHPinDllOfCLSID
0x18002d0e6  mov     rcx, [rsp+38h+arg_8]
0x18002d0eb  jmp     short loc_18002D0F6
0x18002d0ed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002d0f1  mov     [rsp+38h+arg_8], rcx
0x18002d0f6  xor     eax, eax
0x18002d0f8  lock cmpxchg cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA, rcx; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x18002d101  jz      short loc_18002D11A
0x18002d103  mov     rcx, [rsp+38h+arg_8]
0x18002d108  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d10c  jz      short loc_18002D11A
0x18002d10e  mov     rax, [rcx]
0x18002d111  mov     rax, [rax+10h]
0x18002d115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d11a  mov     rax, cs:?g_cachedUserAssist@UserAssistImpl@@3PEAUIShellUserAssist@@EA; IShellUserAssist * UserAssistImpl::g_cachedUserAssist
0x18002d121  xor     ecx, ecx
0x18002d123  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d127  cmovz   rax, rcx
0x18002d12b  add     rsp, 30h
0x18002d12f  pop     rbx
0x18002d130  retn
```
