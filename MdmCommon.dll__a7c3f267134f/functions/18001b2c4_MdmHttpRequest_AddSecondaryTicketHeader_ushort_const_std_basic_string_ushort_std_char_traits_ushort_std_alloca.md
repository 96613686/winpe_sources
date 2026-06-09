# MdmHttpRequest::AddSecondaryTicketHeader(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b2c4`
- end: `0x18001b31e`
- name: `?AddSecondaryTicketHeader@MdmHttpRequest@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001be50`

## callees

- `0x18000630c`
- `0x18001b2c4`

## string_xrefs

- `0x18001b2db`: `X-Device-Token: `

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddSecondaryTicketHeader(void *a1, void *Src)
{
  unsigned int v4; // ebx
  int v5; // ecx
  __int64 v7; // [rsp+0h] [rbp-38h] BYREF

  v4 = 0;
  try
  {
    std::wstring::append(Src, L"X-Device-Token: ");
    std::wstring::append(Src, a1);
    std::wstring::append(Src, L"\r\n");
  }
  catch ( std::bad_alloc )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        (unsigned int)&v7,
        -2147024882,
        "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        36,
        "CHR(((HRESULT)0x8007000EL))");
    return (unsigned int)-2147024882;
  }
  return v4;
}

```

## disassembly

```asm
0x18001b2c4  mov     [rsp+arg_0], rbx
0x18001b2c9  mov     [rsp+arg_8], rsi
0x18001b2ce  push    rdi
0x18001b2cf  sub     rsp, 30h
0x18001b2d3  mov     rdi, rdx
0x18001b2d6  mov     rsi, rcx
0x18001b2d9  xor     ebx, ebx
0x18001b2db  lea     rdx, aXDeviceToken; "X-Device-Token: "
0x18001b2e2  mov     rcx, rdi; Src
0x18001b2e5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b2ea  mov     rdx, rsi; void *
0x18001b2ed  mov     rcx, rdi; Src
0x18001b2f0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b2f5  lea     rdx, asc_18002B100; "\r\n"
0x18001b2fc  mov     rcx, rdi; Src
0x18001b2ff  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b304  nop
0x18001b305  jmp     short loc_18001B30B
0x18001b307  mov     ebx, [rsp+38h+arg_10]
0x18001b30b  mov     eax, ebx
0x18001b30d  mov     rbx, [rsp+38h+arg_0]
0x18001b312  mov     rsi, [rsp+38h+arg_8]
0x18001b317  add     rsp, 30h
0x18001b31b  pop     rdi
0x18001b31c  retn
```
