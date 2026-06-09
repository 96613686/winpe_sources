# Windows::WCP::Implementation::Rtl::InitializeWdscore(void)

- ea: `0x180073840`
- end: `0x1800738ed`
- name: `?InitializeWdscore@Rtl@Implementation@WCP@Windows@@YAXXZ`
- size: `173`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011b10`
- `0x180073774`
- `0x18007f330`
- `0x18007f370`
- `0x18007f540`
- `0x18007faa0`
- `0x180080a50`

## callees

- `0x1800293a0`
- `0x180073840`

## import_xrefs

- `ntdll!LdrGetProcedureAddress` at `0x1800738ce`
- `ntdll!LdrGetProcedureAddress` at `0x1800738ce`
- `ntdll!LdrUnloadDll` at `0x1800738a5`
- `ntdll!LdrUnloadDll` at `0x1800738a5`
- `ntdll!LdrGetDllHandleEx` at `0x18007387e`
- `ntdll!LdrGetDllHandleEx` at `0x18007387e`

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
0x180073840  sub     rsp, 58h
0x180073844  mov     rax, cs:__security_cookie
0x18007384b  xor     rax, rsp
0x18007384e  mov     [rsp+58h+var_18], rax
0x180073853  cmp     cs:BaseAddress, 0
0x18007385b  jnz     short loc_1800738DA
0x18007385d  lea     rax, [rsp+58h+BaseAddress]
0x180073862  mov     [rsp+58h+BaseAddress], 0
0x18007386b  lea     r9, g_UNICODE_STRING_wdscore_dot_dll; DllName
0x180073872  mov     [rsp+58h+DllHandle], rax; DllHandle
0x180073877  xor     r8d, r8d; DllCharacteristics
0x18007387a  xor     edx, edx; DllPath
0x18007387c  xor     ecx, ecx; Flags
0x18007387e  call    cs:__imp_LdrGetDllHandleEx
0x180073885  nop     dword ptr [rax+rax+00h]
0x18007388a  test    eax, eax
0x18007388c  js      short loc_1800738DA
0x18007388e  mov     rcx, [rsp+58h+BaseAddress]
0x180073893  xor     eax, eax
0x180073895  lock cmpxchg cs:BaseAddress, rcx
0x18007389e  jz      short loc_1800738B1
0x1800738a0  mov     rcx, [rsp+58h+BaseAddress]; BaseAddress
0x1800738a5  call    cs:__imp_LdrUnloadDll
0x1800738ac  nop     dword ptr [rax+rax+00h]
0x1800738b1  lock or [rsp+58h+var_58], 0
0x1800738b6  mov     rcx, cs:BaseAddress; BaseAddress
0x1800738bd  lea     r9, ProcedureAddress; ProcedureAddress
0x1800738c4  xor     r8d, r8d; Ordinal
0x1800738c7  lea     rdx, g_ANSI_STRING_WdsSetupLogMessageA; Name
0x1800738ce  call    cs:__imp_LdrGetProcedureAddress
0x1800738d5  nop     dword ptr [rax+rax+00h]
0x1800738da  mov     rcx, [rsp+58h+var_18]
0x1800738df  xor     rcx, rsp; StackCookie
0x1800738e2  call    __security_check_cookie
0x1800738e7  add     rsp, 58h
0x1800738eb  retn
```
