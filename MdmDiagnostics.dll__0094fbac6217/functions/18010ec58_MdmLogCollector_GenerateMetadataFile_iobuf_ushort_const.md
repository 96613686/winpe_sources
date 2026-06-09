# MdmLogCollector::GenerateMetadataFile(_iobuf *,ushort const *)

- ea: `0x18010ec58`
- end: `0x18010edcf`
- name: `?GenerateMetadataFile@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z`
- size: `375`
- prototype: `int(MdmLogCollector *__hidden this, struct _iobuf *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18010a908`

## callees

- `0x180019000`
- `0x18001a04c`
- `0x1800e66dc`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x18010ec58`
- `0x1801109fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010ecba`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010ecba`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010ed9c`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010ed9c`

## string_xrefs

- `0x18010ec87`: `MdmDiagLogMetadata.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall MdmLogCollector::GenerateMetadataFile(
        MdmLogCollector *this,
        struct _iobuf *a2,
        const unsigned __int16 *a3)
{
  const wchar_t *v5; // rax
  errno_t v6; // r14d
  __int64 v7; // rdx
  unsigned int v8; // edi
  unsigned __int64 v9; // rsi
  __int64 v10; // rax
  const wchar_t *v11; // rdx
  __int64 v12; // rax
  FILE *Stream; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v15[32]; // [rsp+30h] [rbp-58h] BYREF

  std::wstring::wstring(v15, a3);
  std::wstring::append(v15, L"MdmDiagLogMetadata.json");
  Stream = 0;
  v5 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  v6 = _wfopen_s(&Stream, v5, L"a+");
  fwprintf_s(Stream, L"{\n");
  v7 = *((_QWORD *)this + 16);
  if ( (*((_QWORD *)this + 17) - v7) >> 5 )
  {
    v8 = 0;
    v9 = 0;
    do
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7 + 32 * v9);
      fwprintf_s(Stream, L"  %s", v10);
      v11 = L",\n";
      if ( v9 >= ((__int64)(*((_QWORD *)this + 17) - *((_QWORD *)this + 16)) >> 5) - 1 )
        v11 = L"\n";
      fwprintf_s(Stream, v11);
      ++v8;
      v7 = *((_QWORD *)this + 16);
      v9 = v8;
    }
    while ( v8 < (unsigned __int64)((*((_QWORD *)this + 17) - v7) >> 5) );
  }
  fwprintf_s(Stream, L"}\n");
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  MdmLogCollector::WriteToFile(a2, L"metadataFile generated:%s\n", v12);
  if ( !v6 )
    fclose(Stream);
  std::wstring::_Tidy_deallocate(v15);
  return 0;
}

```

## disassembly

```asm
0x18010ec58  push    rbx
0x18010ec5a  push    rsi
0x18010ec5b  push    rdi
0x18010ec5c  push    r14
0x18010ec5e  push    r15
0x18010ec60  sub     rsp, 60h
0x18010ec64  mov     rax, cs:__security_cookie
0x18010ec6b  xor     rax, rsp
0x18010ec6e  mov     [rsp+88h+var_38], rax
0x18010ec73  mov     r15, rdx
0x18010ec76  mov     rbx, rcx
0x18010ec79  mov     rdx, r8
0x18010ec7c  lea     rcx, [rsp+88h+var_58]
0x18010ec81  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010ec86  nop
0x18010ec87  lea     rdx, aMdmdiaglogmeta; "MdmDiagLogMetadata.json"
0x18010ec8e  lea     rcx, [rsp+88h+var_58]
0x18010ec93  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010ec98  mov     [rsp+88h+Stream], 0
0x18010eca1  lea     rcx, [rsp+88h+var_58]
0x18010eca6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ecab  mov     rdx, rax; FileName
0x18010ecae  lea     r8, aA; "a+"
0x18010ecb5  lea     rcx, [rsp+88h+Stream]; Stream
0x18010ecba  call    cs:__imp__wfopen_s
0x18010ecc0  mov     r14d, eax
0x18010ecc3  lea     rdx, asc_1801D1F84; "{\n"
0x18010ecca  mov     rcx, [rsp+88h+Stream]; Stream
0x18010eccf  call    fwprintf_s
0x18010ecd4  mov     rdx, [rbx+80h]
0x18010ecdb  mov     rcx, [rbx+88h]
0x18010ece2  sub     rcx, rdx
0x18010ece5  sar     rcx, 5
0x18010ece9  test    rcx, rcx
0x18010ecec  jz      short loc_18010ED65
0x18010ecee  xor     edi, edi
0x18010ecf0  xor     esi, esi
0x18010ecf2  mov     rcx, rsi
0x18010ecf5  shl     rcx, 5
0x18010ecf9  add     rcx, rdx
0x18010ecfc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ed01  mov     r8, rax
0x18010ed04  lea     rdx, aS_0; "  %s"
0x18010ed0b  mov     rcx, [rsp+88h+Stream]; Stream
0x18010ed10  call    fwprintf_s
0x18010ed15  mov     rax, [rbx+88h]
0x18010ed1c  sub     rax, [rbx+80h]
0x18010ed23  sar     rax, 5
0x18010ed27  dec     rax
0x18010ed2a  mov     rcx, [rsp+88h+Stream]; Stream
0x18010ed2f  cmp     rsi, rax
0x18010ed32  lea     rdx, asc_1801D1F94; ",\n"
0x18010ed39  jb      short loc_18010ED42
0x18010ed3b  lea     rdx, asc_1801B9CF8; "\n"
0x18010ed42  call    fwprintf_s
0x18010ed47  inc     edi
0x18010ed49  mov     rdx, [rbx+80h]
0x18010ed50  mov     esi, edi
0x18010ed52  mov     rax, [rbx+88h]
0x18010ed59  sub     rax, rdx
0x18010ed5c  sar     rax, 5
0x18010ed60  cmp     rsi, rax
0x18010ed63  jb      short loc_18010ECF2
0x18010ed65  lea     rdx, asc_1801D1F8C; "}\n"
0x18010ed6c  mov     rcx, [rsp+88h+Stream]; Stream
0x18010ed71  call    fwprintf_s
0x18010ed76  lea     rcx, [rsp+88h+var_58]
0x18010ed7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ed80  mov     r8, rax
0x18010ed83  lea     rdx, aMetadatafileGe; "metadataFile generated:%s\n"
0x18010ed8a  mov     rcx, r15; struct _iobuf *
0x18010ed8d  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ed92  test    r14d, r14d
0x18010ed95  jnz     short loc_18010EDA3
0x18010ed97  mov     rcx, [rsp+88h+Stream]; Stream
0x18010ed9c  call    cs:__imp_fclose
0x18010eda2  nop
0x18010eda3  lea     rcx, [rsp+88h+var_58]
0x18010eda8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010edad  xor     eax, eax
0x18010edaf  jmp     short loc_18010EDB5
0x18010edb1  mov     eax, [rsp+88h+var_60]
0x18010edb5  mov     rcx, [rsp+88h+var_38]
0x18010edba  xor     rcx, rsp; StackCookie
0x18010edbd  call    __security_check_cookie
0x18010edc2  add     rsp, 60h
0x18010edc6  pop     r15
0x18010edc8  pop     r14
0x18010edca  pop     rdi
0x18010edcb  pop     rsi
0x18010edcc  pop     rbx
0x18010edcd  retn
```
