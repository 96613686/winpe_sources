# PrintDeviceCapabilitiesOM::NamespaceUri::GetNamespaceType(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003eae4`
- end: `0x18003ebc2`
- name: `?GetNamespaceType@NamespaceUri@PrintDeviceCapabilitiesOM@@CA?AW4NamespaceType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c1e0`
- `0x18003e10c`

## callees

- `0x1800328a8`
- `0x18003eae4`

## string_xrefs

- `0x18003eb3b`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework`
- `0x18003eb01`: `http://schemas.microsoft.com/windows/2013/05/printing/printschemakeywordsv11`
- `0x18003eb1e`: `http://schemas.microsoft.com/windows/2013/12/printing/printschemakeywordsv12`
- `0x18003eb55`: `http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2`
- `0x18003eaea`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18003eb89`: `http://www.w3.org/2001/XMLSchema`
- `0x18003eba3`: `http://schemas.microsoft.com/windows/2018/04/printing/printschemakeywords/Ipp`
- `0x18003eb6f`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c
__int64 __fastcall PrintDeviceCapabilitiesOM::NamespaceUri::GetNamespaceType(__int64 a1)
{
  __int64 result; // rax

  result = std::wstring::compare(a1, L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords");
  if ( (_DWORD)result )
  {
    if ( (unsigned int)std::wstring::compare(
                         a1,
                         L"http://schemas.microsoft.com/windows/2013/05/printing/printschemakeywordsv11") )
    {
      if ( (unsigned int)std::wstring::compare(
                           a1,
                           L"http://schemas.microsoft.com/windows/2013/12/printing/printschemakeywordsv12") )
      {
        if ( (unsigned int)std::wstring::compare(
                             a1,
                             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemaframework") )
        {
          if ( (unsigned int)std::wstring::compare(
                               a1,
                               L"http://schemas.microsoft.com/windows/2013/12/printing/printschemaframework2") )
          {
            if ( (unsigned int)std::wstring::compare(a1, L"http://www.w3.org/2001/XMLSchema-instance") )
            {
              if ( (unsigned int)std::wstring::compare(a1, L"http://www.w3.org/2001/XMLSchema") )
                return (unsigned int)((unsigned int)std::wstring::compare(
                                                      a1,
                                                      L"http://schemas.microsoft.com/windows/2018/04/printing/printschemakeywords/Ipp") != 0)
                     + 7;
              else
                return 6;
            }
            else
            {
              return 5;
            }
          }
          else
          {
            return 4;
          }
        }
        else
        {
          return 3;
        }
      }
      else
      {
        return 2;
      }
    }
    else
    {
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003eae4  push    rbx
0x18003eae6  sub     rsp, 20h
0x18003eaea  lea     rdx, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/20"...
0x18003eaf1  mov     rbx, rcx
0x18003eaf4  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003eaf9  test    eax, eax
0x18003eafb  jz      loc_18003EBBC
0x18003eb01  lea     rdx, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/20"...
0x18003eb08  mov     rcx, rbx
0x18003eb0b  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003eb10  test    eax, eax
0x18003eb12  jnz     short loc_18003EB1E
0x18003eb14  mov     eax, 1
0x18003eb19  jmp     loc_18003EBBC
0x18003eb1e  lea     rdx, aHttpSchemasMic_4; "http://schemas.microsoft.com/windows/20"...
0x18003eb25  mov     rcx, rbx
0x18003eb28  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003eb2d  test    eax, eax
0x18003eb2f  jnz     short loc_18003EB3B
0x18003eb31  mov     eax, 2
0x18003eb36  jmp     loc_18003EBBC
0x18003eb3b  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18003eb42  mov     rcx, rbx
0x18003eb45  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003eb4a  test    eax, eax
0x18003eb4c  jnz     short loc_18003EB55
0x18003eb4e  mov     eax, 3
0x18003eb53  jmp     short loc_18003EBBC
0x18003eb55  lea     rdx, aHttpSchemasMic_2; "http://schemas.microsoft.com/windows/20"...
0x18003eb5c  mov     rcx, rbx
0x18003eb5f  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003eb64  test    eax, eax
0x18003eb66  jnz     short loc_18003EB6F
0x18003eb68  mov     eax, 4
0x18003eb6d  jmp     short loc_18003EBBC
0x18003eb6f  lea     rdx, aHttpWwwW3Org20_0; "http://www.w3.org/2001/XMLSchema-instan"...
0x18003eb76  mov     rcx, rbx
0x18003eb79  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003eb7e  test    eax, eax
0x18003eb80  jnz     short loc_18003EB89
0x18003eb82  mov     eax, 5
0x18003eb87  jmp     short loc_18003EBBC
0x18003eb89  lea     rdx, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x18003eb90  mov     rcx, rbx
0x18003eb93  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003eb98  test    eax, eax
0x18003eb9a  jnz     short loc_18003EBA3
0x18003eb9c  mov     eax, 6
0x18003eba1  jmp     short loc_18003EBBC
0x18003eba3  lea     rdx, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18003ebaa  mov     rcx, rbx
0x18003ebad  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003ebb2  xor     ecx, ecx
0x18003ebb4  test    eax, eax
0x18003ebb6  setnz   cl
0x18003ebb9  lea     eax, [rcx+7]
0x18003ebbc  add     rsp, 20h
0x18003ebc0  pop     rbx
0x18003ebc1  retn
```
