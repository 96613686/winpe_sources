# MdmHttpRequest::AddSecondaryTicketHeader(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ad64`
- end: `0x18001adbd`
- name: `?AddSecondaryTicketHeader@MdmHttpRequest@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x1800062a4`
- `0x18001ad64`

## string_xrefs

- `0x18001ad7b`: `X-Device-Token: `

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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        36,
        (__int64)"CHR(((HRESULT)0x8007000EL))");
    return (unsigned int)-2147024882;
  }
  std::wstring::append(Src, L"X-Device-Token: ");
}

```

## disassembly

```asm
0x18001ad64  mov     [rsp+arg_0], rbx
0x18001ad69  mov     [rsp+arg_8], rsi
0x18001ad6e  push    rdi
0x18001ad6f  sub     rsp, 30h
0x18001ad73  mov     rdi, rdx
0x18001ad76  mov     rsi, rcx
0x18001ad79  xor     ebx, ebx
0x18001ad7b  lea     rdx, aXDeviceToken; "X-Device-Token: "
0x18001ad82  mov     rcx, rdi; Src
0x18001ad85  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ad8a  mov     rdx, rsi; void *
0x18001ad8d  mov     rcx, rdi; Src
0x18001ad90  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ad95  lea     rdx, asc_18002B100; "\r\n"
0x18001ad9c  mov     rcx, rdi; Src
0x18001ad9f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ada4  nop
0x18001ada5  jmp     short loc_18001ADAB
0x18001ada7  mov     ebx, [rsp+38h+arg_10]
0x18001adab  mov     eax, ebx
0x18001adad  mov     rbx, [rsp+38h+arg_0]
0x18001adb2  mov     rsi, [rsp+38h+arg_8]
0x18001adb7  add     rsp, 30h
0x18001adbb  pop     rdi
0x18001adbc  retn
```
