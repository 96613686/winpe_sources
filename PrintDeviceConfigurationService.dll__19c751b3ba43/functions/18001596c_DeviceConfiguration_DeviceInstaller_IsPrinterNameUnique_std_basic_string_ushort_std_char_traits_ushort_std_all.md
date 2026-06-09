# DeviceConfiguration::DeviceInstaller::_IsPrinterNameUnique(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,_PRINTER_INFO_2W *)

- ea: `0x18001596c`
- end: `0x180015ac7`
- name: `?_IsPrinterNameUnique@DeviceInstaller@DeviceConfiguration@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAU_PRINTER_INFO_2W@@@Z`
- size: `347`
- prototype: `char __fastcall(__int64, __int64, DWORD, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800153bc`
- `0x180015e58`

## callees

- `0x1800020c0`
- `0x18000d89c`
- `0x18000e628`
- `0x18000e83c`
- `0x18000f48c`
- `0x180011510`
- `0x1800115a0`
- `0x18001596c`
- `0x180016284`

## string_xrefs

- `0x1800159dd`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`

## pseudocode

```c
char __fastcall DeviceConfiguration::DeviceInstaller::_IsPrinterNameUnique(
        __int64 a1,
        __int64 a2,
        DWORD a3,
        __int64 a4)
{
  int v7; // r14d
  __int64 v8; // rdx
  DWORD v9; // r8d
  __int64 v10; // r9
  unsigned int v11; // eax
  char v12; // di
  DWORD i; // r15d
  char v14; // bl
  _WORD *v15; // rdx
  char v16; // bl
  const char *v18; // [rsp+28h] [rbp-58h]
  DWORD v19; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v7 = 0;
  v19 = 0;
  std::vector<std::shared_ptr<DeviceConfiguration::Device>>::vector<std::shared_ptr<DeviceConfiguration::Device>>(v20);
  if ( !v10 )
  {
    v11 = DeviceConfiguration::EnumeratePrinters((int)a4 + 10, v8, &v19, (__int64)v20);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xF8,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      (const char *)v11,
      (int)"EnumeratePrinters failed!",
      v18);
    a4 = v20[0];
    a3 = v19;
    v9 = 0;
  }
  v12 = 1;
  for ( i = v9; i < a3; ++i )
  {
    std::wstring::wstring(v21, *(_QWORD *)(a4 + 8));
    v14 = PrintCore::StringHelpers::IEquals(a2, v21);
    std::wstring::_Tidy_deallocate(v21);
    if ( v14 )
      goto LABEL_14;
    v15 = *(_WORD **)(a4 + 16);
    if ( !v15
      || !*v15
      || (std::wstring::wstring(v21, v15),
          v7 |= 1u,
          v16 = 1,
          !(unsigned __int8)PrintCore::StringHelpers::IEquals(a2, v21)) )
    {
      v16 = 0;
    }
    if ( (v7 & 1) != 0 )
    {
      v7 &= ~1u;
      std::wstring::_Tidy_deallocate(v21);
    }
    if ( v16 )
    {
LABEL_14:
      v12 = 0;
      break;
    }
    a4 += 136;
  }
  std::vector<unsigned char>::_Tidy(v20);
  return v12;
}

```

## disassembly

```asm
0x18001596c  mov     [rsp-38h+arg_0], rbx
0x180015971  push    rbp
0x180015972  push    rsi
0x180015973  push    rdi
0x180015974  push    r12
0x180015976  push    r13
0x180015978  push    r14
0x18001597a  push    r15
0x18001597c  mov     rbp, rsp
0x18001597f  sub     rsp, 80h
0x180015986  mov     rax, cs:__security_cookie
0x18001598d  xor     rax, rsp
0x180015990  mov     [rbp+var_10], rax
0x180015994  mov     rsi, r9
0x180015997  mov     r12d, r8d
0x18001599a  mov     r13, rdx
0x18001599d  xor     r8d, r8d
0x1800159a0  mov     r14d, r8d
0x1800159a3  mov     [rbp+var_50], r8d
0x1800159a7  mov     [rbp+var_50], r8d
0x1800159ab  lea     rcx, [rbp+var_48]
0x1800159af  call    ??0?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DeviceConfiguration::Device>>::vector<std::shared_ptr<DeviceConfiguration::Device>>(void)
0x1800159b4  nop
0x1800159b5  test    r9, r9
0x1800159b8  jnz     short loc_1800159F9
0x1800159ba  lea     r9, [rbp+var_48]
0x1800159be  lea     r8, [rbp+var_50]
0x1800159c2  lea     ecx, [rsi+0Ah]; Flags
0x1800159c5  call    ?EnumeratePrinters@DeviceConfiguration@@YAJKKPEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; DeviceConfiguration::EnumeratePrinters(ulong,ulong,ulong *,std::vector<uchar> &)
0x1800159ca  mov     rcx, [rbp+38h]; this
0x1800159ce  lea     rdx, aEnumerateprint; "EnumeratePrinters failed!"
0x1800159d5  mov     qword ptr [rsp+80h+var_60], rdx; int
0x1800159da  mov     r9d, eax; char *
0x1800159dd  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x1800159e4  mov     edx, 0F8h; void *
0x1800159e9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800159ee  mov     rsi, [rbp+var_48]
0x1800159f2  mov     r12d, [rbp+var_50]
0x1800159f6  xor     r8d, r8d
0x1800159f9  mov     edi, 1
0x1800159fe  mov     r15d, r8d
0x180015a01  cmp     r15d, r12d
0x180015a04  jnb     loc_180015A94
0x180015a0a  mov     rdx, [rsi+8]
0x180015a0e  lea     rcx, [rbp+var_30]
0x180015a12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015a17  lea     rdx, [rbp+var_30]
0x180015a1b  mov     rcx, r13
0x180015a1e  call    ?IEquals@StringHelpers@PrintCore@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::StringHelpers::IEquals(std::wstring const &,std::wstring const &)
0x180015a23  mov     bl, al
0x180015a25  lea     rcx, [rbp+var_30]
0x180015a29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015a2e  xor     r8d, r8d
0x180015a31  test    bl, bl
0x180015a33  jnz     short loc_180015A91
0x180015a35  mov     rdx, [rsi+10h]
0x180015a39  test    rdx, rdx
0x180015a3c  jz      short loc_180015A66
0x180015a3e  cmp     [rdx], r8w
0x180015a42  jz      short loc_180015A66
0x180015a44  lea     rcx, [rbp+var_30]
0x180015a48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015a4d  or      r14d, edi
0x180015a50  lea     rdx, [rbp+var_30]
0x180015a54  mov     rcx, r13
0x180015a57  call    ?IEquals@StringHelpers@PrintCore@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::StringHelpers::IEquals(std::wstring const &,std::wstring const &)
0x180015a5c  xor     r8d, r8d
0x180015a5f  test    al, al
0x180015a61  mov     bl, dil
0x180015a64  jnz     short loc_180015A69
0x180015a66  mov     bl, r8b
0x180015a69  test    dil, r14b
0x180015a6c  jz      short loc_180015A7E
0x180015a6e  and     r14d, 0FFFFFFFEh
0x180015a72  lea     rcx, [rbp+var_30]
0x180015a76  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015a7b  xor     r8d, r8d
0x180015a7e  test    bl, bl
0x180015a80  jnz     short loc_180015A91
0x180015a82  add     r15d, edi
0x180015a85  add     rsi, 88h
0x180015a8c  jmp     loc_180015A01
0x180015a91  mov     dil, r8b
0x180015a94  lea     rcx, [rbp+var_48]
0x180015a98  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180015a9d  mov     al, dil
0x180015aa0  mov     rcx, [rbp+var_10]
0x180015aa4  xor     rcx, rsp; StackCookie
0x180015aa7  call    __security_check_cookie
0x180015aac  mov     rbx, [rsp+80h+arg_0]
0x180015ab4  add     rsp, 80h
0x180015abb  pop     r15
0x180015abd  pop     r14
0x180015abf  pop     r13
0x180015ac1  pop     r12
0x180015ac3  pop     rdi
0x180015ac4  pop     rsi
0x180015ac5  pop     rbp
0x180015ac6  retn
```
