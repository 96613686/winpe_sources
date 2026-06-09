# LanguageOverlayServiceModule::_GetServiceParameterOrDefault(ushort const *,ulong)

- ea: `0x180011bec`
- end: `0x180011cc4`
- name: `?_GetServiceParameterOrDefault@LanguageOverlayServiceModule@@AEAAKPEBGK@Z`
- size: `216`
- prototype: `unsigned int __fastcall(LanguageOverlayServiceModule *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800121a8`

## callees

- `0x180003a00`
- `0x180011334`
- `0x180011bec`
- `0x18005f5f8`

## import_xrefs

- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180011c21`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180011c21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c8c`

## string_xrefs

- `0x180011cb1`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LanguageOverlayServiceModule::_GetServiceParameterOrDefault(
        LanguageOverlayServiceModule *this,
        const unsigned __int16 *a2)
{
  unsigned int ServiceRegistryStateKey; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  unsigned int v5; // [rsp+20h] [rbp-48h]
  unsigned int v6; // [rsp+40h] [rbp-28h] BYREF
  DWORD v7; // [rsp+44h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  hKey = 0;
  ServiceRegistryStateKey = GetServiceRegistryStateKey(*((_QWORD *)this + 17), 1, 131097, &hKey);
  try
  {
    if ( ServiceRegistryStateKey )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
        (const char *)ServiceRegistryStateKey,
        v5);
    v6 = 0;
    v7 = 4;
    v3 = 10000;
    if ( TryGetRegValue(hKey, 0, L"IdleShutdownDelay", 0x10u, &v7, &v6, 0) )
      v3 = v6;
    if ( hKey )
      RegCloseKey(hKey);
    result = v3;
  }
  catch ( ... )
  {
    return 10000;
  }
  return result;
}

```

## disassembly

```asm
0x180011bec  push    rbx
0x180011bee  sub     rsp, 60h
0x180011bf2  mov     rax, cs:__security_cookie
0x180011bf9  xor     rax, rsp
0x180011bfc  mov     [rsp+68h+var_18], rax
0x180011c01  mov     [rsp+68h+hKey], 0
0x180011c0a  lea     r9, [rsp+68h+hKey]
0x180011c0f  mov     edx, 1
0x180011c14  mov     r8d, 20019h
0x180011c1a  mov     rcx, [rcx+88h]
0x180011c21  call    cs:__imp_GetServiceRegistryStateKey
0x180011c27  mov     rcx, [rsp+68h]; this
0x180011c2c  test    eax, eax
0x180011c2e  jnz     short loc_180011CAE
0x180011c30  mov     [rsp+68h+var_28], 0
0x180011c38  mov     [rsp+68h+var_24], 4
0x180011c40  mov     [rsp+68h+var_38], 0; LPDWORD
0x180011c49  lea     rax, [rsp+68h+var_28]
0x180011c4e  mov     [rsp+68h+var_40], rax; PVOID
0x180011c53  lea     rax, [rsp+68h+var_24]
0x180011c58  mov     [rsp+68h+var_48], rax; LPDWORD
0x180011c5d  mov     r9d, 10h; unsigned int
0x180011c63  lea     r8, aIdleshutdownde; "IdleShutdownDelay"
0x180011c6a  xor     edx, edx; unsigned __int16 *
0x180011c6c  mov     rcx, [rsp+68h+hKey]; HKEY
0x180011c71  call    ?TryGetRegValue@@YA_NPEAUHKEY__@@PEBG1KPEAKPEAX2@Z; TryGetRegValue(HKEY__ *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x180011c76  mov     ebx, 2710h
0x180011c7b  test    al, al
0x180011c7d  cmovnz  ebx, [rsp+68h+var_28]
0x180011c82  mov     rcx, [rsp+68h+hKey]; hKey
0x180011c87  test    rcx, rcx
0x180011c8a  jz      short loc_180011C92
0x180011c8c  call    cs:__imp_RegCloseKey
0x180011c92  mov     eax, ebx
0x180011c94  jmp     short loc_180011C9B
0x180011c96  mov     eax, 2710h
0x180011c9b  mov     rcx, [rsp+68h+var_18]
0x180011ca0  xor     rcx, rsp; StackCookie
0x180011ca3  call    __security_check_cookie
0x180011ca8  add     rsp, 60h
0x180011cac  pop     rbx
0x180011cad  retn
0x180011cae  mov     r9d, eax; char *
0x180011cb1  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x180011cb8  mov     edx, 1C6h; void *
0x180011cbd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
