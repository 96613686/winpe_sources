# MdmHttpRequest::AddMainTicketHeader(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ace4`
- end: `0x18001ad3d`
- name: `?AddMainTicketHeader@MdmHttpRequest@@CAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b8b0`

## callees

- `0x1800062a4`
- `0x18001ace4`

## string_xrefs

- `0x18001acfb`: `X-User-Token: `

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
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmhttprequest.cpp",
        15,
        (__int64)"CHR(((HRESULT)0x8007000EL))");
    return (unsigned int)-2147024882;
  }
  std::wstring::append(Src, L"X-User-Token: ");
}

```

## disassembly

```asm
0x18001ace4  mov     [rsp+arg_0], rbx
0x18001ace9  mov     [rsp+arg_8], rsi
0x18001acee  push    rdi
0x18001acef  sub     rsp, 30h
0x18001acf3  mov     rdi, rdx
0x18001acf6  mov     rsi, rcx
0x18001acf9  xor     ebx, ebx
0x18001acfb  lea     rdx, aXUserToken; "X-User-Token: "
0x18001ad02  mov     rcx, rdi; Src
0x18001ad05  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ad0a  mov     rdx, rsi; void *
0x18001ad0d  mov     rcx, rdi; Src
0x18001ad10  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ad15  lea     rdx, asc_18002B100; "\r\n"
0x18001ad1c  mov     rcx, rdi; Src
0x18001ad1f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001ad24  nop
0x18001ad25  jmp     short loc_18001AD2B
0x18001ad27  mov     ebx, [rsp+38h+arg_10]
0x18001ad2b  mov     eax, ebx
0x18001ad2d  mov     rbx, [rsp+38h+arg_0]
0x18001ad32  mov     rsi, [rsp+38h+arg_8]
0x18001ad37  add     rsp, 30h
0x18001ad3b  pop     rdi
0x18001ad3c  retn
```
