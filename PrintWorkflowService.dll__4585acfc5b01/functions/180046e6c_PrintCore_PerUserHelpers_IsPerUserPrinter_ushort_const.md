# PrintCore::PerUserHelpers::IsPerUserPrinter(ushort const *)

- ea: `0x180046e6c`
- end: `0x180046f06`
- name: `?IsPerUserPrinter@PerUserHelpers@PrintCore@@SA_NPEBG@Z`
- size: `154`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046b2c`

## callees

- `0x180003ca0`
- `0x180012784`
- `0x180012820`
- `0x180046dcc`
- `0x180046e6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180046e89`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180046e89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046ed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046ed3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180046ec4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180046ec4`

## pseudocode

```c
char __fastcall PrintCore::PerUserHelpers::IsPerUserPrinter(const unsigned __int16 *a1)
{
  const WCHAR *v2; // rax
  PSID Sid; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v5[16]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v6; // [rsp+38h] [rbp-20h]

  if ( wcschr(a1, 0x3Au) )
  {
    PrintCore::PerUserHelpers::GetSidFromPerUserPrinterName(v5, a1);
    if ( v6 )
    {
      Sid = 0;
      v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
      if ( ConvertStringSidToSidW(v2, &Sid) )
      {
        LocalFree(Sid);
        std::wstring::_Tidy_deallocate(v5);
        return 1;
      }
    }
    std::wstring::_Tidy_deallocate(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180046e6c  push    rbx
0x180046e6e  sub     rsp, 50h
0x180046e72  mov     rax, cs:__security_cookie
0x180046e79  xor     rax, rsp
0x180046e7c  mov     [rsp+58h+var_10], rax
0x180046e81  mov     edx, 3Ah ; ':'; Ch
0x180046e86  mov     rbx, rcx
0x180046e89  call    cs:__imp_wcschr
0x180046e8f  test    rax, rax
0x180046e92  jz      short loc_180046EF1
0x180046e94  mov     rdx, rbx
0x180046e97  lea     rcx, [rsp+58h+var_30]
0x180046e9c  call    ?GetSidFromPerUserPrinterName@PerUserHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; PrintCore::PerUserHelpers::GetSidFromPerUserPrinterName(ushort const *)
0x180046ea1  cmp     [rsp+58h+var_20], 0
0x180046ea7  jz      short loc_180046EE7
0x180046ea9  lea     rcx, [rsp+58h+var_30]
0x180046eae  mov     [rsp+58h+Sid], 0
0x180046eb7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180046ebc  mov     rcx, rax; StringSid
0x180046ebf  lea     rdx, [rsp+58h+Sid]; Sid
0x180046ec4  call    cs:__imp_ConvertStringSidToSidW
0x180046eca  test    eax, eax
0x180046ecc  jz      short loc_180046EE7
0x180046ece  mov     rcx, [rsp+58h+Sid]; hMem
0x180046ed3  call    cs:__imp_LocalFree
0x180046ed9  lea     rcx, [rsp+58h+var_30]
0x180046ede  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046ee3  mov     al, 1
0x180046ee5  jmp     short loc_180046EF3
0x180046ee7  lea     rcx, [rsp+58h+var_30]
0x180046eec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180046ef1  xor     al, al
0x180046ef3  mov     rcx, [rsp+58h+var_10]
0x180046ef8  xor     rcx, rsp; StackCookie
0x180046efb  call    __security_check_cookie
0x180046f00  add     rsp, 50h
0x180046f04  pop     rbx
0x180046f05  retn
```
