# udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent

- ea: `0x18007dc3c`
- end: `0x18007dcd8`
- name: `udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007dce0`

## callees

- `0x18001fb38`
- `0x18007dc3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dc6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007dc6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007dc8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007dcc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007dc8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007dcc5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool udk::npu_detection::_anonymous_namespace_::IsHybridComputeFrameworkPresent()
{
  LSTATUS v0; // eax
  __int64 v1; // r8
  bool v2; // sf
  signed int v3; // eax
  bool result; // al
  const char *v5; // r9
  bool v6; // bl
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v8; // [rsp+40h] [rbp+8h] BYREF
  char v9; // [rsp+44h] [rbp+Ch]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkloadManager\\HCF\\Status",
         0,
         0x20019u,
         &hKey);
  v2 = v0 < 0;
  if ( v0 > 0 )
  {
    v3 = (unsigned __int16)v0 | 0x80070000;
    v2 = v3 < 0;
  }
  if ( v2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    try
    {
      wil::reg::try_get_value<unsigned int>((__int64)&v8, hKey, v1, L"IsHcfPresent");
      v6 = (v9 != 0 ? v8 : 0) != 0;
      if ( hKey )
        RegCloseKey(hKey);
      result = v6;
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"onecore\\internal\\shell\\inc\\npu_detection.h",
        v5);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007dc3c  push    rbx
0x18007dc3e  sub     rsp, 30h
0x18007dc42  mov     [rsp+38h+hKey], 0
0x18007dc4b  lea     rax, [rsp+38h+hKey]
0x18007dc50  mov     [rsp+38h+phkResult], rax; phkResult
0x18007dc55  mov     r9d, 20019h; samDesired
0x18007dc5b  xor     r8d, r8d; ulOptions
0x18007dc5e  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18007dc65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007dc6c  call    cs:__imp_RegOpenKeyExW
0x18007dc72  test    eax, eax
0x18007dc74  jle     short loc_18007DC80
0x18007dc76  movzx   eax, ax
0x18007dc79  or      eax, 80070000h
0x18007dc7e  test    eax, eax
0x18007dc80  jns     short loc_18007DC96
0x18007dc82  mov     rcx, [rsp+38h+hKey]; hKey
0x18007dc87  test    rcx, rcx
0x18007dc8a  jz      short loc_18007DC92
0x18007dc8c  call    cs:__imp_RegCloseKey
0x18007dc92  xor     al, al
0x18007dc94  jmp     short loc_18007DCD1
0x18007dc96  lea     r9, ValueName; "IsHcfPresent"
0x18007dc9d  mov     rdx, [rsp+38h+hKey]
0x18007dca2  lea     rcx, [rsp+38h+arg_0]
0x18007dca7  call    ??$try_get_value@I@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value<uint>(HKEY__ *,wchar_t const *,wchar_t const *)
0x18007dcac  mov     al, [rsp+38h+arg_4]
0x18007dcb0  neg     al
0x18007dcb2  sbb     ecx, ecx
0x18007dcb4  and     ecx, [rsp+38h+arg_0]
0x18007dcb8  setnz   bl
0x18007dcbb  mov     rcx, [rsp+38h+hKey]; hKey
0x18007dcc0  test    rcx, rcx
0x18007dcc3  jz      short loc_18007DCCB
0x18007dcc5  call    cs:__imp_RegCloseKey
0x18007dccb  mov     al, bl
0x18007dccd  jmp     short loc_18007DCD1
0x18007dccf  xor     al, al
0x18007dcd1  add     rsp, 30h
0x18007dcd5  pop     rbx
0x18007dcd6  retn
```
