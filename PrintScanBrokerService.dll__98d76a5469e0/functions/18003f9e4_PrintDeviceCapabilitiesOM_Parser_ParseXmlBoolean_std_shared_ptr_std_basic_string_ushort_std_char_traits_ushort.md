# PrintDeviceCapabilitiesOM::Parser::ParseXmlBoolean(std::shared_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &)

- ea: `0x18003f9e4`
- end: `0x18003fa9d`
- name: `?ParseXmlBoolean@Parser@PrintDeviceCapabilitiesOM@@YA_NAEBV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b7f4`
- `0x18003cadc`

## callees

- `0x18001031c`
- `0x1800328a8`
- `0x18003e614`
- `0x18003f9e4`
- `0x180040d3c`

## string_xrefs

- `0x18003f9f9`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003fa7c`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003fa00`: `Missing boolean XML value`
- `0x18003fa8b`: `Incorrect boolean XML value`

## pseudocode

```c
char __fastcall PrintDeviceCapabilitiesOM::Parser::ParseXmlBoolean(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  int v6; // eax
  unsigned int v7; // [rsp+20h] [rbp-18h]
  int v8; // [rsp+40h] [rbp+8h] BYREF

  if ( !*a1 )
    PrintCore::ThrowIfError(
      (PrintCore *)0x80070057LL,
      "Missing boolean XML value",
      "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      (const char *)0x2D0,
      v7);
  if ( !(unsigned int)std::wstring::compare(*a1, L"true") || !(unsigned int)std::wstring::compare(*a1, L"1") )
    return 1;
  if ( (unsigned int)std::wstring::compare(*a1, L"false") )
  {
    if ( (unsigned int)std::wstring::compare(*a1, L"0") )
    {
      v6 = std::shared_ptr<std::wstring>::operator*<std::wstring,0>(a1, v2, v3, v4);
      v8 = 14;
      PrintDeviceCapabilitiesOM::Exception::Throw::Error(
        (unsigned int)&v8,
        v6,
        (unsigned int)L"Incorrect boolean XML value",
        (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        736);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003f9e4  push    rbx
0x18003f9e6  sub     rsp, 30h
0x18003f9ea  cmp     qword ptr [rcx], 0
0x18003f9ee  mov     rbx, rcx
0x18003f9f1  jnz     short loc_18003FA11
0x18003f9f3  mov     r9d, 2D0h; char *
0x18003f9f9  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003fa00  lea     rdx, aMissingBoolean; "Missing boolean XML value"
0x18003fa07  mov     ecx, 80070057h; this
0x18003fa0c  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003fa11  mov     rcx, [rbx]
0x18003fa14  lea     rdx, aTrue; "true"
0x18003fa1b  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003fa20  test    eax, eax
0x18003fa22  jz      short loc_18003FA61
0x18003fa24  mov     rcx, [rbx]
0x18003fa27  lea     rdx, a1; "1"
0x18003fa2e  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003fa33  test    eax, eax
0x18003fa35  jz      short loc_18003FA61
0x18003fa37  mov     rcx, [rbx]
0x18003fa3a  lea     rdx, aFalse; "false"
0x18003fa41  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003fa46  test    eax, eax
0x18003fa48  jz      short loc_18003FA5D
0x18003fa4a  mov     rcx, [rbx]
0x18003fa4d  lea     rdx, a0; "0"
0x18003fa54  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003fa59  test    eax, eax
0x18003fa5b  jnz     short loc_18003FA69
0x18003fa5d  xor     al, al
0x18003fa5f  jmp     short loc_18003FA63
0x18003fa61  mov     al, 1
0x18003fa63  add     rsp, 30h
0x18003fa67  pop     rbx
0x18003fa68  retn
0x18003fa69  mov     rcx, rbx
0x18003fa6c  call    ??$?DV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEBAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::shared_ptr<std::wstring>::operator*<std::wstring,0>(void)
0x18003fa71  mov     rdx, rax
0x18003fa74  mov     [rsp+38h+arg_0], 0Eh
0x18003fa7c  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003fa83  mov     [rsp+38h+var_18], 2E0h
0x18003fa8b  lea     r8, aIncorrectBoole; "Incorrect boolean XML value"
0x18003fa92  lea     rcx, [rsp+38h+arg_0]
0x18003fa97  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
