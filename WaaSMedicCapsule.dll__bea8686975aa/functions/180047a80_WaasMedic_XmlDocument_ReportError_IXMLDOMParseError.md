# WaasMedic::XmlDocument::ReportError(IXMLDOMParseError *)

- ea: `0x180047a80`
- end: `0x180047bb3`
- name: `?ReportError@XmlDocument@WaasMedic@@AEAAJPEAUIXMLDOMParseError@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(WaasMedic::XmlDocument *__hidden this, struct IXMLDOMParseError *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180047bbc`

## callees

- `0x18002543c`
- `0x180047a80`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180047b2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180047ba3`
- `OLEAUT32!__imp_SysFreeString` at `0x180047b2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180047ba3`

## string_xrefs

- `0x180047ab2`: `Failed to read error code from IXMLDOMParseError. Err=0x%08x`
- `0x180047b14`: `Failed to read line position from IXMLDOMParseError. Err=0x%08x`
- `0x180047aeb`: `Failed to read line number from IXMLDOMParseError. Err=0x%08x`
- `0x180047b8d`: `Invalid XML (line %u, position %u): %s. Err:0x%08x`
- `0x180047b54`: `Failed to read error reason from IXMLDOMParseError. Err=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::XmlDocument::ReportError(WaasMedic::XmlDocument *this, struct IXMLDOMParseError *a2)
{
  int v3; // ebx
  HRESULT (__stdcall *get_reason)(IXMLDOMParseError *, BSTR *); // rbx
  int v5; // eax
  BSTR v6; // rdx
  int v8; // [rsp+28h] [rbp-8h]
  int v9; // [rsp+50h] [rbp+20h] BYREF
  int v10; // [rsp+54h] [rbp+24h]
  unsigned int v11; // [rsp+58h] [rbp+28h] BYREF
  unsigned int v12; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF

  v10 = HIDWORD(this);
  v9 = 0;
  v3 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, int *))a2->lpVtbl->get_errorCode)(a2, &v9);
  if ( v3 >= 0 )
  {
    v12 = 0;
    v3 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, unsigned int *))a2->lpVtbl->get_line)(a2, &v12);
    if ( v3 >= 0 )
    {
      v11 = 0;
      v3 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, unsigned int *))a2->lpVtbl->get_linepos)(a2, &v11);
      if ( v3 >= 0 )
      {
        bstrString = 0;
        get_reason = a2->lpVtbl->get_reason;
        SysFreeString(0);
        bstrString = 0;
        v5 = ((__int64 (__fastcall *)(struct IXMLDOMParseError *, BSTR *))get_reason)(a2, &bstrString);
        v3 = v5;
        if ( v5 >= 0 )
        {
          v6 = (BSTR)&word_18006939C;
          if ( bstrString )
            v6 = bstrString;
          v8 = v9;
          LogLevelW(2u, L"Invalid XML (line %u, position %u): %s. Err:0x%08x", v12, v11, v6, v8);
        }
        else
        {
          LogLevelW(2u, L"Failed to read error reason from IXMLDOMParseError. Err=0x%08x", (unsigned int)v5);
        }
        SysFreeString(bstrString);
      }
      else
      {
        LogLevelW(2u, L"Failed to read line position from IXMLDOMParseError. Err=0x%08x", (unsigned int)v3);
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to read line number from IXMLDOMParseError. Err=0x%08x", (unsigned int)v3);
    }
  }
  else
  {
    LogLevelW(2u, L"Failed to read error code from IXMLDOMParseError. Err=0x%08x", (unsigned int)v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180047a80  mov     [rsp-18h+arg_0], rcx
0x180047a85  push    rbp
0x180047a86  push    rbx
0x180047a87  push    rdi
0x180047a88  mov     rbp, rsp
0x180047a8b  sub     rsp, 30h
0x180047a8f  mov     rdi, rdx
0x180047a92  mov     dword ptr [rbp+arg_0], 0
0x180047a99  mov     rax, [rdx]
0x180047a9c  lea     rdx, [rbp+arg_0]
0x180047aa0  mov     rcx, rdi
0x180047aa3  mov     rax, [rax+38h]
0x180047aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047aac  mov     ebx, eax
0x180047aae  test    eax, eax
0x180047ab0  jns     short loc_180047ACB
0x180047ab2  lea     rdx, aFailedToReadEr; "Failed to read error code from IXMLDOMP"...
0x180047ab9  mov     r8d, ebx
0x180047abc  mov     ecx, 2; unsigned __int8
0x180047ac1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180047ac6  jmp     loc_180047BA9
0x180047acb  mov     [rbp+arg_10], 0
0x180047ad2  mov     rax, [rdi]
0x180047ad5  lea     rdx, [rbp+arg_10]
0x180047ad9  mov     rcx, rdi
0x180047adc  mov     rax, [rax+58h]
0x180047ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ae5  mov     ebx, eax
0x180047ae7  test    eax, eax
0x180047ae9  jns     short loc_180047AF4
0x180047aeb  lea     rdx, aFailedToReadLi_0; "Failed to read line number from IXMLDOM"...
0x180047af2  jmp     short loc_180047AB9
0x180047af4  mov     [rbp+arg_8], 0
0x180047afb  mov     rax, [rdi]
0x180047afe  lea     rdx, [rbp+arg_8]
0x180047b02  mov     rcx, rdi
0x180047b05  mov     rax, [rax+60h]
0x180047b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b0e  mov     ebx, eax
0x180047b10  test    eax, eax
0x180047b12  jns     short loc_180047B1D
0x180047b14  lea     rdx, aFailedToReadLi; "Failed to read line position from IXMLD"...
0x180047b1b  jmp     short loc_180047AB9
0x180047b1d  mov     [rbp+bstrString], 0
0x180047b25  mov     rax, [rdi]
0x180047b28  mov     rbx, [rax+48h]
0x180047b2c  xor     ecx, ecx; bstrString
0x180047b2e  call    cs:__imp_SysFreeString
0x180047b34  mov     [rbp+bstrString], 0
0x180047b3c  lea     rdx, [rbp+bstrString]
0x180047b40  mov     rcx, rdi
0x180047b43  mov     rax, rbx
0x180047b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b4b  mov     ebx, eax
0x180047b4d  test    eax, eax
0x180047b4f  jns     short loc_180047B67
0x180047b51  mov     r8d, eax
0x180047b54  lea     rdx, aFailedToReadEr_0; "Failed to read error reason from IXMLDO"...
0x180047b5b  mov     ecx, 2; unsigned __int8
0x180047b60  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180047b65  jmp     short loc_180047B9F
0x180047b67  mov     ecx, dword ptr [rbp+arg_0]
0x180047b6a  lea     rdx, word_18006939C
0x180047b71  mov     rax, [rbp+bstrString]
0x180047b75  test    rax, rax
0x180047b78  cmovnz  rdx, rax
0x180047b7c  mov     [rsp+30h+var_8], ecx
0x180047b80  mov     [rsp+30h+var_10], rdx
0x180047b85  mov     r9d, [rbp+arg_8]
0x180047b89  mov     r8d, [rbp+arg_10]
0x180047b8d  lea     rdx, aInvalidXmlLine; "Invalid XML (line %u, position %u): %s."...
0x180047b94  mov     ecx, 2; unsigned __int8
0x180047b99  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180047b9e  nop
0x180047b9f  mov     rcx, [rbp+bstrString]; bstrString
0x180047ba3  call    cs:__imp_SysFreeString
0x180047ba9  mov     eax, ebx
0x180047bab  add     rsp, 30h
0x180047baf  pop     rdi
0x180047bb0  pop     rbx
0x180047bb1  pop     rbp
0x180047bb2  retn
```
