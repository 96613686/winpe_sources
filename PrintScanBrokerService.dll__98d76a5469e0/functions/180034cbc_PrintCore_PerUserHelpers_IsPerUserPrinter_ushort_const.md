# PrintCore::PerUserHelpers::IsPerUserPrinter(ushort const *)

- ea: `0x180034cbc`
- end: `0x180034d5a`
- name: `?IsPerUserPrinter@PerUserHelpers@PrintCore@@SA_NPEBG@Z`
- size: `158`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034ae0`

## callees

- `0x180002d40`
- `0x18000f8a8`
- `0x180034a3c`
- `0x180034cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180034cd9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180034cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034d27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034d27`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180034d18`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180034d18`

## pseudocode

```c
char __fastcall PrintCore::PerUserHelpers::IsPerUserPrinter(const unsigned __int16 *a1)
{
  const WCHAR *v2; // rcx
  PSID Sid; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR StringSid[4]; // [rsp+28h] [rbp-30h] BYREF

  if ( wcschr(a1, 0x3Au) )
  {
    PrintCore::PerUserHelpers::GetSidFromPerUserPrinterName(StringSid, a1);
    if ( StringSid[2] )
    {
      v2 = (const WCHAR *)StringSid;
      Sid = 0;
      if ( StringSid[3] > (LPCWSTR)7 )
        v2 = StringSid[0];
      if ( ConvertStringSidToSidW(v2, &Sid) )
      {
        LocalFree(Sid);
        std::wstring::_Tidy_deallocate(StringSid);
        return 1;
      }
    }
    std::wstring::_Tidy_deallocate(StringSid);
  }
  return 0;
}

```

## disassembly

```asm
0x180034cbc  push    rbx
0x180034cbe  sub     rsp, 50h
0x180034cc2  mov     rax, cs:__security_cookie
0x180034cc9  xor     rax, rsp
0x180034ccc  mov     [rsp+58h+var_10], rax
0x180034cd1  mov     edx, 3Ah ; ':'; Ch
0x180034cd6  mov     rbx, rcx
0x180034cd9  call    cs:__imp_wcschr
0x180034cdf  test    rax, rax
0x180034ce2  jz      short loc_180034D45
0x180034ce4  mov     rdx, rbx
0x180034ce7  lea     rcx, [rsp+58h+StringSid]
0x180034cec  call    ?GetSidFromPerUserPrinterName@PerUserHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; PrintCore::PerUserHelpers::GetSidFromPerUserPrinterName(ushort const *)
0x180034cf1  cmp     [rsp+58h+var_20], 0
0x180034cf7  jz      short loc_180034D3B
0x180034cf9  cmp     [rsp+58h+var_18], 7
0x180034cff  lea     rcx, [rsp+58h+StringSid]
0x180034d04  lea     rdx, [rsp+58h+Sid]; Sid
0x180034d09  mov     [rsp+58h+Sid], 0
0x180034d12  cmova   rcx, [rsp+58h+StringSid]; StringSid
0x180034d18  call    cs:__imp_ConvertStringSidToSidW
0x180034d1e  test    eax, eax
0x180034d20  jz      short loc_180034D3B
0x180034d22  mov     rcx, [rsp+58h+Sid]; hMem
0x180034d27  call    cs:__imp_LocalFree
0x180034d2d  lea     rcx, [rsp+58h+StringSid]
0x180034d32  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034d37  mov     al, 1
0x180034d39  jmp     short loc_180034D47
0x180034d3b  lea     rcx, [rsp+58h+StringSid]
0x180034d40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034d45  xor     al, al
0x180034d47  mov     rcx, [rsp+58h+var_10]
0x180034d4c  xor     rcx, rsp; StackCookie
0x180034d4f  call    __security_check_cookie
0x180034d54  add     rsp, 50h
0x180034d58  pop     rbx
0x180034d59  retn
```
