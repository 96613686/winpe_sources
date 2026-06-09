# Windows::Globalization::Spelling::RegistrySpellingOptions::Enum(std::function<void (ushort const *,ulong,uchar)> const &)

- ea: `0x18008b500`
- end: `0x18008b6b0`
- name: `?Enum@RegistrySpellingOptions@Spelling@Globalization@Windows@@UEAAJAEBV?$function@$$A6AXPEBGKE@Z@std@@@Z`
- size: `432`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180061320`
- `0x18008b500`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18008b694`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18008b694`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b668`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b668`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18008b652`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18008b652`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008b577`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008b577`

## pseudocode

```c
LSTATUS __fastcall Windows::Globalization::Spelling::RegistrySpellingOptions::Enum(__int64 a1, __int64 a2)
{
  LSTATUS result; // eax
  DWORD v4; // edi
  DWORD i; // edx
  __int64 v6; // rcx
  LSTATUS v7; // eax
  BYTE v8[8]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchValueName; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD v14; // [rsp+70h] [rbp-90h] BYREF
  WCHAR *v15; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ValueName[256]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  result = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Spelling\\Options", 0, 0, 0, 1u, 0, &hKey, 0);
  if ( !result )
  {
    *(_DWORD *)Data = 0;
    v4 = 0;
    Type = 0;
    for ( i = 0; ; i = v4 )
    {
      cbData = 4;
      cchValueName = 256;
      v7 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
      if ( v7 == 259 )
        break;
      if ( !v7 && Type == 4 && *(_DWORD *)Data <= 0xFFu )
      {
        v6 = *(_QWORD *)(a2 + 56);
        v8[0] = Data[0];
        v14 = cchValueName;
        v15 = ValueName;
        if ( !v6 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        (*(void (__fastcall **)(__int64, WCHAR **, DWORD *, BYTE *))(*(_QWORD *)v6 + 16LL))(v6, &v15, &v14, v8);
      }
      ++v4;
    }
    RegCloseKey(hKey);
    return 0;
  }
  if ( result == 259 )
    return 0;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18008b500  mov     [rsp-8+arg_0], rsi
0x18008b505  mov     [rsp-8+arg_10], rdi
0x18008b50a  push    rbp
0x18008b50b  lea     rbp, [rsp-190h]
0x18008b513  sub     rsp, 290h
0x18008b51a  mov     rax, cs:__security_cookie
0x18008b521  xor     rax, rsp
0x18008b524  mov     [rbp+190h+var_10], rax
0x18008b52b  mov     [rsp+290h+lpdwDisposition], 0; lpdwDisposition
0x18008b534  lea     rax, [rsp+290h+hKey]
0x18008b539  mov     [rsp+290h+phkResult], rax; phkResult
0x18008b53e  mov     rsi, rdx
0x18008b541  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18008b54a  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Spelling\\Options"
0x18008b551  mov     [rsp+290h+samDesired], 1; samDesired
0x18008b559  xor     r9d, r9d; lpClass
0x18008b55c  xor     r8d, r8d; Reserved
0x18008b55f  mov     [rsp+290h+dwOptions], 0; dwOptions
0x18008b567  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008b56e  mov     [rsp+290h+hKey], 0
0x18008b577  call    cs:__imp_RegCreateKeyExW
0x18008b57d  test    eax, eax
0x18008b57f  jnz     loc_18008B69B
0x18008b585  mov     dword ptr [rsp+290h+Data], eax
0x18008b589  xor     edi, edi
0x18008b58b  mov     [rsp+290h+Type], eax
0x18008b58f  xor     edx, edx
0x18008b591  lea     rax, [rsp+290h+cbData]
0x18008b596  mov     [rsp+290h+phkResult], rax
0x18008b59b  lea     rax, [rsp+290h+Data]
0x18008b5a0  mov     [rsp+290h+lpSecurityAttributes], rax
0x18008b5a5  lea     rax, [rsp+290h+Type]
0x18008b5aa  mov     qword ptr [rsp+290h+samDesired], rax
0x18008b5af  mov     qword ptr [rsp+290h+dwOptions], rdi
0x18008b5b4  jmp     short loc_18008B634
0x18008b5b6  test    eax, eax
0x18008b5b8  jnz     short loc_18008B609
0x18008b5ba  cmp     [rsp+290h+Type], 4
0x18008b5bf  jnz     short loc_18008B609
0x18008b5c1  mov     eax, dword ptr [rsp+290h+Data]
0x18008b5c5  cmp     eax, 0FFh
0x18008b5ca  ja      short loc_18008B609
0x18008b5cc  mov     rcx, [rsi+38h]
0x18008b5d0  mov     [rsp+290h+var_240], al
0x18008b5d4  mov     eax, [rsp+290h+cchValueName]
0x18008b5d8  mov     [rsp+290h+var_220], eax
0x18008b5dc  lea     rax, [rbp+190h+ValueName]
0x18008b5e0  mov     [rsp+290h+var_218], rax
0x18008b5e5  test    rcx, rcx
0x18008b5e8  jz      loc_18008B694
0x18008b5ee  mov     rax, [rcx]
0x18008b5f1  lea     r9, [rsp+290h+var_240]
0x18008b5f6  lea     r8, [rsp+290h+var_220]
0x18008b5fb  lea     rdx, [rsp+290h+var_218]
0x18008b600  mov     rax, [rax+10h]
0x18008b604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b609  lea     rax, [rsp+290h+cbData]
0x18008b60e  inc     edi
0x18008b610  mov     [rsp+290h+phkResult], rax; lpcbData
0x18008b615  mov     edx, edi; dwIndex
0x18008b617  lea     rax, [rsp+290h+Data]
0x18008b61c  mov     [rsp+290h+lpSecurityAttributes], rax; lpData
0x18008b621  lea     rax, [rsp+290h+Type]
0x18008b626  mov     qword ptr [rsp+290h+samDesired], rax; lpType
0x18008b62b  mov     qword ptr [rsp+290h+dwOptions], 0; lpReserved
0x18008b634  mov     rcx, [rsp+290h+hKey]; hKey
0x18008b639  lea     r9, [rsp+290h+cchValueName]; lpcchValueName
0x18008b63e  lea     r8, [rbp+190h+ValueName]; lpValueName
0x18008b642  mov     [rsp+290h+cbData], 4
0x18008b64a  mov     [rsp+290h+cchValueName], 100h
0x18008b652  call    cs:__imp_RegEnumValueW
0x18008b658  cmp     eax, 103h
0x18008b65d  jnz     loc_18008B5B6
0x18008b663  mov     rcx, [rsp+290h+hKey]; hKey
0x18008b668  call    cs:__imp_RegCloseKey
0x18008b66e  xor     eax, eax
0x18008b670  mov     rcx, [rbp+190h+var_10]
0x18008b677  xor     rcx, rsp; StackCookie
0x18008b67a  call    __security_check_cookie
0x18008b67f  lea     r11, [rsp+290h+var_s0]
0x18008b687  mov     rsi, [r11+10h]
0x18008b68b  mov     rdi, [r11+20h]
0x18008b68f  mov     rsp, r11
0x18008b692  pop     rbp
0x18008b693  retn
0x18008b694  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18008b69a  int     3; Trap to Debugger
0x18008b69b  cmp     eax, 103h
0x18008b6a0  jz      short loc_18008B66E
0x18008b6a2  test    eax, eax
0x18008b6a4  jle     short loc_18008B670
0x18008b6a6  movzx   eax, ax
0x18008b6a9  or      eax, 80070000h
0x18008b6ae  jmp     short loc_18008B670
```
