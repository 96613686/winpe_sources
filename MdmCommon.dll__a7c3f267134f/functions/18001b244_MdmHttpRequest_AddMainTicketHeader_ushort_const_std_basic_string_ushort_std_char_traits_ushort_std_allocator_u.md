# MdmHttpRequest::AddMainTicketHeader(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b244`
- end: `0x18001b29e`
- name: `?AddMainTicketHeader@MdmHttpRequest@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001be50`

## callees

- `0x18000630c`
- `0x18001b244`

## string_xrefs

- `0x18001b25b`: `X-User-Token: `

## pseudocode

```c
__int64 __fastcall MdmHttpRequest::AddMainTicketHeader(void *a1, void *Src)
{
  unsigned int v4; // ebx
  int v5; // ecx
  __int64 v7; // [rsp+0h] [rbp-38h] BYREF

  v4 = 0;
  try
  {
    std::wstring::append(Src, L"X-User-Token: ");
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
        15,
        "CHR(((HRESULT)0x8007000EL))");
    return (unsigned int)-2147024882;
  }
  return v4;
}

```

## disassembly

```asm
0x18001b244  mov     [rsp+arg_0], rbx
0x18001b249  mov     [rsp+arg_8], rsi
0x18001b24e  push    rdi
0x18001b24f  sub     rsp, 30h
0x18001b253  mov     rdi, rdx
0x18001b256  mov     rsi, rcx
0x18001b259  xor     ebx, ebx
0x18001b25b  lea     rdx, aXUserToken; "X-User-Token: "
0x18001b262  mov     rcx, rdi; Src
0x18001b265  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b26a  mov     rdx, rsi; void *
0x18001b26d  mov     rcx, rdi; Src
0x18001b270  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b275  lea     rdx, asc_18002B100; "\r\n"
0x18001b27c  mov     rcx, rdi; Src
0x18001b27f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b284  nop
0x18001b285  jmp     short loc_18001B28B
0x18001b287  mov     ebx, [rsp+38h+arg_10]
0x18001b28b  mov     eax, ebx
0x18001b28d  mov     rbx, [rsp+38h+arg_0]
0x18001b292  mov     rsi, [rsp+38h+arg_8]
0x18001b297  add     rsp, 30h
0x18001b29b  pop     rdi
0x18001b29c  retn
```
