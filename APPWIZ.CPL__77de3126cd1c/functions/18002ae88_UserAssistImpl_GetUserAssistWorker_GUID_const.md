# UserAssistImpl::GetUserAssistWorker(_GUID const &)

- ea: `0x18002ae88`
- end: `0x18002af22`
- name: `?GetUserAssistWorker@UserAssistImpl@@YAPEAUIShellUserAssist@@AEBU_GUID@@@Z`
- size: `154`
- prototype: `struct IShellUserAssist *__fastcall(UserAssistImpl *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b484`

## callees

- `0x18002ae88`
- `0x180059010`

## import_xrefs

- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x18002aed2`
- `SHLWAPI!__imp_SHPinDllOfCLSID` at `0x18002aed2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002aec1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002aec1`

## pseudocode

```c
struct IShellUserAssist *__fastcall UserAssistImpl::GetUserAssistWorker(UserAssistImpl *this, const struct _GUID *a2)
{
  struct IShellUserAssist *result; // rax
  signed __int64 v3; // rcx
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  v4 = (__int64)this;
  result = *(struct IShellUserAssist **)g_hSQMSession.Data4;
  if ( !*(_QWORD *)g_hSQMSession.Data4 )
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
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)g_hSQMSession.Data4, v3, 0) && v4 != -1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    result = *(struct IShellUserAssist **)g_hSQMSession.Data4;
  }
  if ( result == (struct IShellUserAssist *)-1LL )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18002ae88  mov     r11, rsp
0x18002ae8b  mov     [r11+8], rcx
0x18002ae8f  sub     rsp, 38h
0x18002ae93  mov     rax, qword ptr cs:?g_hSQMSession@@3PEAU_GUID@@EA.Data4; _GUID * g_hSQMSession ...
0x18002ae9a  test    rax, rax
0x18002ae9d  jnz     short loc_18002AF13
0x18002ae9f  mov     [r11+8], rax
0x18002aea3  lea     r9, _GUID_49b36d57_5fd2_45a7_981b_06028d577a47; riid
0x18002aeaa  lea     rax, [r11+8]
0x18002aeae  xor     edx, edx; pUnkOuter
0x18002aeb0  mov     r8d, 403h; dwClsContext
0x18002aeb6  mov     [r11-18h], rax
0x18002aeba  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c; rclsid
0x18002aec1  call    cs:__imp_CoCreateInstance
0x18002aec7  test    eax, eax
0x18002aec9  js      short loc_18002AEDF
0x18002aecb  lea     rcx, _GUID_dd313e04_feff_11d1_8ecd_0000f87a470c
0x18002aed2  call    cs:__imp_SHPinDllOfCLSID
0x18002aed8  mov     rcx, [rsp+38h+arg_0]
0x18002aedd  jmp     short loc_18002AEE8
0x18002aedf  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002aee3  mov     [rsp+38h+arg_0], rcx
0x18002aee8  xor     eax, eax
0x18002aeea  lock cmpxchg qword ptr cs:?g_hSQMSession@@3PEAU_GUID@@EA.Data4, rcx; _GUID * g_hSQMSession ...
0x18002aef3  jz      short loc_18002AF0C
0x18002aef5  mov     rcx, [rsp+38h+arg_0]
0x18002aefa  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002aefe  jz      short loc_18002AF0C
0x18002af00  mov     rax, [rcx]
0x18002af03  mov     rax, [rax+10h]
0x18002af07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af0c  mov     rax, qword ptr cs:?g_hSQMSession@@3PEAU_GUID@@EA.Data4; _GUID * g_hSQMSession ...
0x18002af13  xor     ecx, ecx
0x18002af15  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002af19  cmovz   rax, rcx
0x18002af1d  add     rsp, 38h
0x18002af21  retn
```
