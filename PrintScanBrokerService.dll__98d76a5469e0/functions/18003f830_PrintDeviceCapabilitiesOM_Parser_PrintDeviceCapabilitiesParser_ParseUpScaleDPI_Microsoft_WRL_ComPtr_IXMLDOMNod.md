# PrintDeviceCapabilitiesOM::Parser::PrintDeviceCapabilitiesParser::ParseUpScaleDPI(Microsoft::WRL::ComPtr<IXMLDOMNode> &)

- ea: `0x18003f830`
- end: `0x18003f8e1`
- name: `?ParseUpScaleDPI@PrintDeviceCapabilitiesParser@Parser@PrintDeviceCapabilitiesOM@@UEAAIAEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001031c`
- `0x18003e614`
- `0x18003ebc8`
- `0x18003f830`
- `0x1800421e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003f86d`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003f86d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003f858`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003f879`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003f884`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003f858`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003f879`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003f884`

## string_xrefs

- `0x18003f8c8`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrintDeviceCapabilitiesOM::Parser::PrintDeviceCapabilitiesParser::ParseUpScaleDPI(
        __int64 a1,
        __int64 *a2)
{
  unsigned int v2; // edi
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  int v8; // eax
  _QWORD *v9; // [rsp+30h] [rbp-18h] BYREF
  std::_Ref_count_base *v10; // [rsp+38h] [rbp-10h]
  int v11; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  PrintDeviceCapabilitiesOM::Parser::GetNodeText(&v9, a2, L"psf2:RenderUpscaleDPI");
  v3 = v9;
  if ( v9 )
  {
    *(_DWORD *)_o__errno() = 0;
    if ( v3[3] > 7u )
      v3 = (_QWORD *)*v3;
    v2 = _o__wtol(v3);
    if ( !v2 && (*(_DWORD *)_o__errno() == 34 || *(_DWORD *)_o__errno() == 22) )
    {
      v11 = 7;
      v8 = std::shared_ptr<std::wstring>::operator*<std::wstring,0>(&v9, v4, v5, v6);
      PrintDeviceCapabilitiesOM::Exception::Throw::Error(
        (unsigned int)&v11,
        v8,
        (unsigned int)L"Not a valid integer",
        (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        2757);
    }
  }
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  return v2;
}

```

## disassembly

```asm
0x18003f830  mov     [rsp+arg_0], rbx
0x18003f835  push    rdi
0x18003f836  sub     rsp, 40h
0x18003f83a  xor     edi, edi
0x18003f83c  lea     r8, aPsf2Renderupsc; "psf2:RenderUpscaleDPI"
0x18003f843  lea     rcx, [rsp+48h+var_18]
0x18003f848  call    ?GetNodeText@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z; PrintDeviceCapabilitiesOM::Parser::GetNodeText(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)
0x18003f84d  nop
0x18003f84e  mov     rbx, [rsp+48h+var_18]
0x18003f853  test    rbx, rbx
0x18003f856  jz      short loc_18003F88F
0x18003f858  call    cs:__imp__o__errno
0x18003f85e  mov     [rax], edi
0x18003f860  cmp     qword ptr [rbx+18h], 7
0x18003f865  jbe     short loc_18003F86A
0x18003f867  mov     rbx, [rbx]
0x18003f86a  mov     rcx, rbx
0x18003f86d  call    cs:__imp__o__wtol
0x18003f873  mov     edi, eax
0x18003f875  test    eax, eax
0x18003f877  jnz     short loc_18003F88F
0x18003f879  call    cs:__imp__o__errno
0x18003f87f  cmp     dword ptr [rax], 22h ; '"'
0x18003f882  jz      short loc_18003F8AB
0x18003f884  call    cs:__imp__o__errno
0x18003f88a  cmp     dword ptr [rax], 16h
0x18003f88d  jz      short loc_18003F8AB
0x18003f88f  mov     rcx, [rsp+48h+var_10]; this
0x18003f894  test    rcx, rcx
0x18003f897  jz      short loc_18003F89E
0x18003f899  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f89e  mov     eax, edi
0x18003f8a0  mov     rbx, [rsp+48h+arg_0]
0x18003f8a5  add     rsp, 40h
0x18003f8a9  pop     rdi
0x18003f8aa  retn
0x18003f8ab  mov     [rsp+48h+arg_10], 7
0x18003f8b3  lea     rcx, [rsp+48h+var_18]
0x18003f8b8  call    ??$?DV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEBAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::shared_ptr<std::wstring>::operator*<std::wstring,0>(void)
0x18003f8bd  mov     rdx, rax
0x18003f8c0  mov     [rsp+48h+var_28], 0AC5h
0x18003f8c8  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003f8cf  lea     r8, aNotAValidInteg; "Not a valid integer"
0x18003f8d6  lea     rcx, [rsp+48h+arg_10]
0x18003f8db  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
