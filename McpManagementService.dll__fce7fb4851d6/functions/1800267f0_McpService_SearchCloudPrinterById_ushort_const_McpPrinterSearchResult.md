# McpService::SearchCloudPrinterById(ushort const *,_McpPrinterSearchResult * *)

- ea: `0x1800267f0`
- end: `0x180026897`
- name: `?SearchCloudPrinterById@McpService@@UEAAJPEBGPEAPEAU_McpPrinterSearchResult@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(McpService *__hidden this, const unsigned __int16 *, struct _McpPrinterSearchResult **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180003a60`
- `0x18000c4cc`
- `0x18000e208`
- `0x18000e2dc`
- `0x180011de0`
- `0x1800267f0`
- `0x1800268a0`

## string_xrefs

- `0x180026868`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall McpService::SearchCloudPrinterById(
        McpService *this,
        const unsigned __int16 *a2,
        struct _McpPrinterSearchResult **a3)
{
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-48h]
  _BYTE v9[32]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( a2 && *a2 )
  {
    std::wstring::wstring((__int64)v9, (__int64)L"uuid=");
    std::wstring::append((__int64)v9, (__int64)a2);
    v6 = McpService::SearchCloudPrinters((__int64)this, (__int64)v9, a3);
    std::wstring::_Tidy_deallocate((__int64)v9);
    return v6;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)0x80070057LL,
      v8);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800267f0  push    rbx
0x1800267f2  push    rsi
0x1800267f3  push    rdi
0x1800267f4  sub     rsp, 50h
0x1800267f8  mov     rax, cs:__security_cookie
0x1800267ff  xor     rax, rsp
0x180026802  mov     [rsp+68h+var_20], rax
0x180026807  mov     rsi, r8
0x18002680a  mov     rbx, rdx
0x18002680d  mov     rdi, rcx
0x180026810  xor     eax, eax
0x180026812  test    rdx, rdx
0x180026815  jz      short loc_18002685B
0x180026817  cmp     [rdx], ax
0x18002681a  jz      short loc_18002685B
0x18002681c  lea     rdx, aUuid; "uuid="
0x180026823  lea     rcx, [rsp+68h+var_40]
0x180026828  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002682d  nop
0x18002682e  mov     rdx, rbx
0x180026831  lea     rcx, [rsp+68h+var_40]
0x180026836  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002683b  mov     r8, rsi
0x18002683e  lea     rdx, [rsp+68h+var_40]
0x180026843  mov     rcx, rdi
0x180026846  call    ?SearchCloudPrinters@McpService@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAU_McpPrinterSearchResult@@@Z; McpService::SearchCloudPrinters(std::wstring const &,_McpPrinterSearchResult * *)
0x18002684b  mov     ebx, eax
0x18002684d  lea     rcx, [rsp+68h+var_40]
0x180026852  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026857  mov     eax, ebx
0x180026859  jmp     short loc_180026881
0x18002685b  mov     rcx, [rsp+68h]; this
0x180026860  mov     ebx, 80070057h
0x180026865  mov     r9d, ebx; char *
0x180026868  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002686f  mov     edx, 153h; void *
0x180026874  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026879  mov     eax, ebx
0x18002687b  jmp     short loc_180026881
0x18002687d  mov     eax, [rsp+68h+var_48]
0x180026881  mov     rcx, [rsp+68h+var_20]
0x180026886  xor     rcx, rsp; StackCookie
0x180026889  call    __security_check_cookie
0x18002688e  add     rsp, 50h
0x180026892  pop     rdi
0x180026893  pop     rsi
0x180026894  pop     rbx
0x180026895  retn
```
