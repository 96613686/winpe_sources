# Windows::WCP::Implementation::Rtl::InitializeWdscore(void)

- ea: `0x1800735e0`
- end: `0x18007368d`
- name: `?InitializeWdscore@Rtl@Implementation@WCP@Windows@@YAXXZ`
- size: `173`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001bb10`
- `0x180073514`
- `0x18007e3b0`
- `0x18007e3f0`
- `0x18007e5c0`
- `0x18007eb20`
- `0x18007fae0`

## callees

- `0x18002d2b0`
- `0x1800735e0`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x18007366e`
- `ntdll!LdrGetProcedureAddress` at `0x18007366e`
- `ntdll!LdrUnloadDll` at `0x180073645`
- `ntdll!LdrUnloadDll` at `0x180073645`
- `ntdll!LdrGetDllHandleEx` at `0x18007361e`
- `ntdll!LdrGetDllHandleEx` at `0x18007361e`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::InitializeWdscore(Windows::WCP::Implementation::Rtl *this)
{
  signed __int32 v1[8]; // [rsp+0h] [rbp-58h] BYREF
  PVOID BaseAddress; // [rsp+38h] [rbp-20h] BYREF

  if ( !::BaseAddress )
  {
    BaseAddress = 0;
    if ( LdrGetDllHandleEx(0, 0, 0, (PUNICODE_STRING)&g_UNICODE_STRING_wdscore_dot_dll, &BaseAddress) >= 0 )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&::BaseAddress, (signed __int64)BaseAddress, 0) )
        LdrUnloadDll(BaseAddress);
      _InterlockedOr(v1, 0);
      LdrGetProcedureAddress(::BaseAddress, (PANSI_STRING)&g_ANSI_STRING_WdsSetupLogMessageA, 0, &ProcedureAddress);
    }
  }
}

```

## disassembly

```asm
0x1800735e0  sub     rsp, 58h
0x1800735e4  mov     rax, cs:__security_cookie
0x1800735eb  xor     rax, rsp
0x1800735ee  mov     [rsp+58h+var_18], rax
0x1800735f3  cmp     cs:BaseAddress, 0
0x1800735fb  jnz     short loc_18007367A
0x1800735fd  lea     rax, [rsp+58h+BaseAddress]
0x180073602  mov     [rsp+58h+BaseAddress], 0
0x18007360b  lea     r9, g_UNICODE_STRING_wdscore_dot_dll; DllName
0x180073612  mov     [rsp+58h+DllHandle], rax; DllHandle
0x180073617  xor     r8d, r8d; DllCharacteristics
0x18007361a  xor     edx, edx; DllPath
0x18007361c  xor     ecx, ecx; Flags
0x18007361e  call    cs:__imp_LdrGetDllHandleEx
0x180073625  nop     dword ptr [rax+rax+00h]
0x18007362a  test    eax, eax
0x18007362c  js      short loc_18007367A
0x18007362e  mov     rcx, [rsp+58h+BaseAddress]
0x180073633  xor     eax, eax
0x180073635  lock cmpxchg cs:BaseAddress, rcx
0x18007363e  jz      short loc_180073651
0x180073640  mov     rcx, [rsp+58h+BaseAddress]; BaseAddress
0x180073645  call    cs:__imp_LdrUnloadDll
0x18007364c  nop     dword ptr [rax+rax+00h]
0x180073651  lock or [rsp+58h+var_58], 0
0x180073656  mov     rcx, cs:BaseAddress; BaseAddress
0x18007365d  lea     r9, ProcedureAddress; ProcedureAddress
0x180073664  xor     r8d, r8d; Ordinal
0x180073667  lea     rdx, g_ANSI_STRING_WdsSetupLogMessageA; Name
0x18007366e  call    cs:__imp_LdrGetProcedureAddress
0x180073675  nop     dword ptr [rax+rax+00h]
0x18007367a  mov     rcx, [rsp+58h+var_18]
0x18007367f  xor     rcx, rsp; StackCookie
0x180073682  call    __security_check_cookie
0x180073687  add     rsp, 58h
0x18007368b  retn
```
