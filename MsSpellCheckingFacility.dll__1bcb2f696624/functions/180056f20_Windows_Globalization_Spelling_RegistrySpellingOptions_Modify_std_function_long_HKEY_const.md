# Windows::Globalization::Spelling::RegistrySpellingOptions::Modify(std::function<long (HKEY__ *)> const &)

- ea: `0x180056f20`
- end: `0x180056fd1`
- name: `?Modify@RegistrySpellingOptions@Spelling@Globalization@Windows@@CAJAEBV?$function@$$A6AJPEAUHKEY__@@@Z@std@@@Z`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180056e00`
- `0x180056ea0`

## callees

- `0x180056f20`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180056f92`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180056f92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056fb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056fb1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056f73`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180056f73`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::RegistrySpellingOptions::Modify(__int64 a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  HKEY v7; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Spelling\\Options", 0, 0, 0, 2u, 0, &hKey, 0);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    v4 = *(_QWORD *)(a1 + 56);
    v7 = hKey;
    if ( !v4 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    v3 = (*(__int64 (__fastcall **)(__int64, HKEY *))(*(_QWORD *)v4 + 16LL))(v4, &v7);
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180056f20  mov     r11, rsp
0x180056f23  mov     [r11+8], rbx
0x180056f27  push    rdi
0x180056f28  sub     rsp, 50h
0x180056f2c  mov     qword ptr [r11-18h], 0
0x180056f34  lea     rax, [r11+10h]
0x180056f38  mov     [r11-20h], rax
0x180056f3c  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Spelling\\Options"
0x180056f43  mov     qword ptr [r11-28h], 0
0x180056f4b  mov     rdi, rcx
0x180056f4e  mov     [rsp+58h+samDesired], 2; samDesired
0x180056f56  xor     r9d, r9d; lpClass
0x180056f59  xor     r8d, r8d; Reserved
0x180056f5c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180056f64  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180056f6b  mov     qword ptr [r11+10h], 0
0x180056f73  call    cs:__imp_RegCreateKeyExW
0x180056f79  mov     ebx, eax
0x180056f7b  test    eax, eax
0x180056f7d  jnz     short loc_180056FB9
0x180056f7f  mov     rcx, [rdi+38h]
0x180056f83  mov     rax, [rsp+58h+hKey]
0x180056f88  mov     [rsp+58h+arg_10], rax
0x180056f8d  test    rcx, rcx
0x180056f90  jnz     short loc_180056F99
0x180056f92  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180056f98  int     3; Trap to Debugger
0x180056f99  mov     rax, [rcx]
0x180056f9c  lea     rdx, [rsp+58h+arg_10]
0x180056fa1  mov     rax, [rax+10h]
0x180056fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056faa  mov     rcx, [rsp+58h+hKey]; hKey
0x180056faf  mov     ebx, eax
0x180056fb1  call    cs:__imp_RegCloseKey
0x180056fb7  jmp     short loc_180056FC4
0x180056fb9  jle     short loc_180056FC4
0x180056fbb  movzx   ebx, ax
0x180056fbe  or      ebx, 80070000h
0x180056fc4  mov     eax, ebx
0x180056fc6  mov     rbx, [rsp+58h+arg_0]
0x180056fcb  add     rsp, 50h
0x180056fcf  pop     rdi
0x180056fd0  retn
```
