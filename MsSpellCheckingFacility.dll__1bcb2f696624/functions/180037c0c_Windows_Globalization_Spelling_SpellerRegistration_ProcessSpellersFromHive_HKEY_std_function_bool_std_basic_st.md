# Windows::Globalization::Spelling::SpellerRegistration::ProcessSpellersFromHive(HKEY__ *,std::function<bool (std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)>)

- ea: `0x180037c0c`
- end: `0x180037caf`
- name: `?ProcessSpellersFromHive@SpellerRegistration@Spelling@Globalization@Windows@@CA_NPEAUHKEY__@@V?$function@$$A6A_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z@std@@@Z`
- size: `163`
- prototype: `char __fastcall(HKEY, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037b60`

## callees

- `0x180037c0c`
- `0x180052718`
- `0x18006f958`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037c74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037c42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037c42`

## pseudocode

```c
char __fastcall Windows::Globalization::Spelling::SpellerRegistration::ProcessSpellersFromHive(HKEY a1, __int64 *a2)
{
  char v3; // di
  __int64 *v4; // rcx
  __int64 v5; // rdx
  _BYTE v7[72]; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  v3 = 1;
  hKey = 0;
  if ( !RegOpenKeyExW(a1, L"Software\\Microsoft\\Spelling\\Spellers", 0, 0x20019u, &hKey) )
  {
    std::function<bool (std::wstring const &,std::wstring const &)>::function<bool (std::wstring const &,std::wstring const &)>(
      v7,
      a2);
    v3 = Windows::Globalization::Spelling::SpellerRegistration::ProcessSpellersFromKey(hKey);
    RegCloseKey(hKey);
  }
  v4 = (__int64 *)a2[7];
  if ( v4 )
  {
    v5 = *v4;
    LOBYTE(v5) = v4 != a2;
    (*(void (__fastcall **)(__int64 *, __int64))(*v4 + 32))(v4, v5);
    a2[7] = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180037c0c  mov     r11, rsp
0x180037c0f  mov     [r11+8], rbx
0x180037c13  mov     [r11+10h], rdx
0x180037c17  push    rdi
0x180037c18  sub     rsp, 70h
0x180037c1c  mov     rbx, rdx
0x180037c1f  mov     dil, 1
0x180037c22  mov     qword ptr [r11+18h], 0
0x180037c2a  lea     rax, [r11+18h]
0x180037c2e  mov     [r11-58h], rax
0x180037c32  mov     r9d, 20019h; samDesired
0x180037c38  xor     r8d, r8d; ulOptions
0x180037c3b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Spelling\\Spellers"
0x180037c42  call    cs:__imp_RegOpenKeyExW
0x180037c48  test    eax, eax
0x180037c4a  jnz     short loc_180037C7B
0x180037c4c  mov     rdx, rbx
0x180037c4f  lea     rcx, [rsp+78h+var_48]
0x180037c54  call    ??0?$function@$$A6A_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z@std@@QEAA@AEBV01@@Z; std::function<bool (std::wstring const &,std::wstring const &)>::function<bool (std::wstring const &,std::wstring const &)>(std::function<bool (std::wstring const &,std::wstring const &)> const &)
0x180037c59  mov     rdx, rax
0x180037c5c  mov     rcx, [rsp+78h+hKey]; hkey
0x180037c64  call    ?ProcessSpellersFromKey@SpellerRegistration@Spelling@Globalization@Windows@@CA_NPEAUHKEY__@@V?$function@$$A6A_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z@std@@@Z; Windows::Globalization::Spelling::SpellerRegistration::ProcessSpellersFromKey(HKEY__ *,std::function<bool (std::wstring const &,std::wstring const &)>)
0x180037c69  mov     dil, al
0x180037c6c  mov     rcx, [rsp+78h+hKey]; hKey
0x180037c74  call    cs:__imp_RegCloseKey
0x180037c7a  nop
0x180037c7b  mov     rcx, [rbx+38h]
0x180037c7f  test    rcx, rcx
0x180037c82  jz      short loc_180037C9E
0x180037c84  mov     rdx, [rcx]
0x180037c87  mov     rax, [rdx+20h]
0x180037c8b  cmp     rcx, rbx
0x180037c8e  setnz   dl
0x180037c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c96  mov     qword ptr [rbx+38h], 0
0x180037c9e  mov     al, dil
0x180037ca1  mov     rbx, [rsp+78h+arg_0]
0x180037ca9  add     rsp, 70h
0x180037cad  pop     rdi
0x180037cae  retn
```
