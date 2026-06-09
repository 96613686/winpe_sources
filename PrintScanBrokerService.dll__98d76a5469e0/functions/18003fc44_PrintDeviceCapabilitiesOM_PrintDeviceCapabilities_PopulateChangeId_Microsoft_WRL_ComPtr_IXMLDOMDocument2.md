# PrintDeviceCapabilitiesOM::PrintDeviceCapabilities::PopulateChangeId(Microsoft::WRL::ComPtr<IXMLDOMDocument2> &)

- ea: `0x18003fc44`
- end: `0x18003fd9b`
- name: `?PopulateChangeId@PrintDeviceCapabilities@PrintDeviceCapabilitiesOM@@AEAAXAEAV?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@@Z`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ee54`

## callees

- `0x1800387fc`
- `0x18003ae84`
- `0x18003b7a4`
- `0x18003e0e0`
- `0x18003f2dc`
- `0x18003fc44`
- `0x180040d3c`
- `0x1800421e0`
- `0x180048010`

## string_xrefs

- `0x18003fcb1`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003fd32`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PrintDeviceCapabilitiesOM::PrintDeviceCapabilities::PopulateChangeId(_QWORD *a1, __int64 *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, _QWORD, __int64 *); // rbx
  PrintCore::BStrRAII *v5; // rax
  __int64 v6; // rdi
  unsigned int (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 *v8; // rax
  void **v10; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+28h] [rbp-18h] BYREF
  std::_Ref_count_base *v12[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v13; // [rsp+68h] [rbp+28h] BYREF

  v13 = 0;
  v3 = *a2;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)*a2 + 296LL);
  v5 = PrintCore::BStrRAII::BStrRAII(
         (PrintCore::BStrRAII *)v12,
         L"/psf2:PrintDeviceCapabilities/psf2:CapabilitiesChangeID");
  LODWORD(v4) = v4(v3, *((_QWORD *)v5 + 1), &v13);
  v12[0] = (std::_Ref_count_base *)&PrintCore::BStrRAII::`vftable';
  PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)v12);
  PrintCore::ThrowIfError(
    (PrintCore *)(unsigned int)v4,
    "Internal error",
    "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
    (const char *)0x9F6,
    (unsigned int)v10);
  if ( (_DWORD)v4 == 1 )
  {
    *(_OWORD *)v12 = 0;
    std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(a1, (__int64 *)v12);
    if ( v12[1] )
      std::_Ref_count_base::_Decref(v12[1]);
  }
  else
  {
    v10 = &PrintCore::BStrRAII::`vftable';
    v11 = 0;
    v6 = v13;
    v7 = *(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 208LL);
    PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v10);
    if ( v7(v6, &v11) )
      PrintCore::ThrowIfError(
        (PrintCore *)0x80040004LL,
        "Unspecified.",
        "onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        (const char *)0xA00,
        (unsigned int)v10);
    v8 = (__int64 *)std::make_shared<std::wstring,PrintCore::BStrRAII &>(v12, &v10);
    std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(a1, v8);
    if ( v12[1] )
      std::_Ref_count_base::_Decref(v12[1]);
    v10 = &PrintCore::BStrRAII::`vftable';
    PrintCore::BStrRAII::Clean((PrintCore::BStrRAII *)&v10);
  }
  return Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(&v13);
}

```

## disassembly

```asm
0x18003fc44  mov     [rsp-18h+arg_0], rbx
0x18003fc49  mov     [rsp-18h+arg_10], rsi
0x18003fc4e  push    rbp
0x18003fc4f  push    rdi
0x18003fc50  push    r14
0x18003fc52  mov     rbp, rsp
0x18003fc55  sub     rsp, 40h
0x18003fc59  mov     rsi, rcx
0x18003fc5c  mov     [rbp+arg_8], 0
0x18003fc64  mov     rdi, [rdx]
0x18003fc67  mov     rax, [rdi]
0x18003fc6a  mov     rbx, [rax+128h]
0x18003fc71  lea     rdx, aPsf2Printdevic_0; "/psf2:PrintDeviceCapabilities/psf2:Capa"...
0x18003fc78  lea     rcx, [rbp+var_10]; this
0x18003fc7c  call    ??0BStrRAII@PrintCore@@QEAA@PEBG@Z; PrintCore::BStrRAII::BStrRAII(ushort const *)
0x18003fc81  nop
0x18003fc82  lea     r8, [rbp+arg_8]
0x18003fc86  mov     rdx, [rax+8]
0x18003fc8a  mov     rcx, rdi
0x18003fc8d  mov     rax, rbx
0x18003fc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc95  mov     ebx, eax
0x18003fc97  lea     r14, ??_7BStrRAII@PrintCore@@6B@; const PrintCore::BStrRAII::`vftable'
0x18003fc9e  mov     [rbp+var_10], r14
0x18003fca2  lea     rcx, [rbp+var_10]; this
0x18003fca6  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003fcab  mov     r9d, 9F6h; char *
0x18003fcb1  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003fcb8  lea     rdx, aInternalError; "Internal error"
0x18003fcbf  mov     ecx, ebx; this
0x18003fcc1  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003fcc6  cmp     ebx, 1
0x18003fcc9  jnz     short loc_18003FCF6
0x18003fccb  xorps   xmm0, xmm0
0x18003fcce  movdqu  xmmword ptr [rbp+var_10], xmm0
0x18003fcd3  lea     rdx, [rbp+var_10]
0x18003fcd7  mov     rcx, rsi
0x18003fcda  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003fcdf  mov     rcx, [rbp+var_10+8]; this
0x18003fce3  test    rcx, rcx
0x18003fce6  jz      loc_18003FD7F
0x18003fcec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003fcf1  jmp     loc_18003FD7F
0x18003fcf6  mov     [rbp+var_20], r14
0x18003fcfa  mov     [rbp+var_18], 0
0x18003fd02  mov     rdi, [rbp+arg_8]
0x18003fd06  mov     rax, [rdi]
0x18003fd09  mov     rbx, [rax+0D0h]
0x18003fd10  lea     rcx, [rbp+var_20]; this
0x18003fd14  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003fd19  lea     rdx, [rbp+var_18]
0x18003fd1d  mov     rcx, rdi
0x18003fd20  mov     rax, rbx
0x18003fd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd28  test    eax, eax
0x18003fd2a  jz      short loc_18003FD4A
0x18003fd2c  mov     r9d, 0A00h; char *
0x18003fd32  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003fd39  lea     rdx, aUnspecified; "Unspecified."
0x18003fd40  mov     ecx, 80040004h; this
0x18003fd45  call    ?ThrowIfError@PrintCore@@YAXJPEBD0I@Z; PrintCore::ThrowIfError(long,char const *,char const *,uint)
0x18003fd4a  lea     rdx, [rbp+var_20]
0x18003fd4e  lea     rcx, [rbp+var_10]
0x18003fd52  call    ??$make_shared@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVBStrRAII@PrintCore@@@std@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@AEAVBStrRAII@PrintCore@@@Z; std::make_shared<std::wstring,PrintCore::BStrRAII &>(PrintCore::BStrRAII &)
0x18003fd57  mov     rdx, rax
0x18003fd5a  mov     rcx, rsi
0x18003fd5d  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003fd62  mov     rcx, [rbp+var_10+8]; this
0x18003fd66  test    rcx, rcx
0x18003fd69  jz      short loc_18003FD71
0x18003fd6b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003fd70  nop
0x18003fd71  mov     [rbp+var_20], r14
0x18003fd75  lea     rcx, [rbp+var_20]; this
0x18003fd79  call    ?Clean@BStrRAII@PrintCore@@AEAAXXZ; PrintCore::BStrRAII::Clean(void)
0x18003fd7e  nop
0x18003fd7f  lea     rcx, [rbp+arg_8]
0x18003fd83  call    ?InternalRelease@?$ComPtr@UIXMLDOMDocument2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMDocument2>::InternalRelease(void)
0x18003fd88  mov     rbx, [rsp+40h+arg_0]
0x18003fd8d  mov     rsi, [rsp+40h+arg_10]
0x18003fd92  add     rsp, 40h
0x18003fd96  pop     r14
0x18003fd98  pop     rdi
0x18003fd99  pop     rbp
0x18003fd9a  retn
```
