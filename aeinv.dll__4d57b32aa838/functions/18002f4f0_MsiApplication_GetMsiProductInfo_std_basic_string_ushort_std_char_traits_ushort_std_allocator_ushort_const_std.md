# MsiApplication::GetMsiProductInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,tagMSIINSTALLCONTEXT,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002f4f0`
- end: `0x18002f70c`
- name: `?GetMsiProductInfo@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4tagMSIINSTALLCONTEXT@@0AEAV23@@Z`
- size: `540`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, MSIINSTALLCONTEXT, LPCWSTR szProperty, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18003b364`
- `0x18003bfb0`

## callees

- `0x1800118d0`
- `0x180018a60`
- `0x1800197d4`
- `0x18002f4f0`
- `0x1800404c4`
- `0x180045480`
- `0x180059920`
- `0x18005a8bc`
- `0x18010ef38`

## import_xrefs

- `msi!__imp_MsiGetProductInfoExW` at `0x18002f5aa`
- `msi!__imp_MsiGetProductInfoExW` at `0x18002f64a`
- `msi!__imp_MsiGetProductInfoExW` at `0x18002f5aa`
- `msi!__imp_MsiGetProductInfoExW` at `0x18002f64a`

## string_xrefs

- `0x18002f6b6`: `MsiApplication::GetMsiProductInfo`
- `0x18002f6a9`: `GetMsiProductInfo failed to get %ls from %ls`

## pseudocode

```c
__int64 __fastcall MsiApplication::GetMsiProductInfo(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        MSIINSTALLCONTEXT a4,
        LPCWSTR szProperty,
        __int64 a6)
{
  const WCHAR *v10; // r9
  const WCHAR *v11; // rdx
  const WCHAR *v12; // rcx
  UINT ProductInfo; // r14d
  MSIINSTALLCONTEXT v14; // esi
  const WCHAR *v15; // r9
  const WCHAR *v16; // rdx
  const WCHAR *v17; // rcx
  __int64 v19; // r8
  DWORD pcchValue; // [rsp+30h] [rbp-D0h] BYREF
  MSIINSTALLCONTEXT dwContext; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h]
  LPCWSTR szUserSid[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR szValue[264]; // [rsp+60h] [rbp-A0h] BYREF

  v22 = -2;
  memset_0(szValue, 0, 0x208u);
  pcchValue = 260;
  if ( *((_QWORD *)szProperty + 3) <= 7u )
    v10 = szProperty;
  else
    v10 = *(const WCHAR **)szProperty;
  if ( *((_QWORD *)a3 + 2) )
  {
    if ( *((_QWORD *)a3 + 3) <= 7u )
      v11 = a3;
    else
      v11 = *(const WCHAR **)a3;
  }
  else
  {
    v11 = 0;
  }
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v12 = (const WCHAR *)a2;
  else
    v12 = *(const WCHAR **)a2;
  ProductInfo = MsiGetProductInfoExW(v12, v11, a4, v10, szValue, &pcchValue);
  if ( ProductInfo == 1605 )
  {
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    std::wstring::wstring(szUserSid, a3);
    dwContext = a4;
    MsiApplication::GetMsiInstallContextAndUserSid(a1, a2, szUserSid, &dwContext);
    v14 = dwContext;
    if ( (unsigned int)(dwContext - 1) <= 1 )
    {
      pcchValue = 260;
      if ( *((_QWORD *)szProperty + 3) <= 7u )
        v15 = szProperty;
      else
        v15 = *(const WCHAR **)szProperty;
      v16 = (const WCHAR *)szUserSid;
      if ( szUserSid[3] > (LPCWSTR)7 )
        v16 = szUserSid[0];
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v17 = (const WCHAR *)a2;
      else
        v17 = *(const WCHAR **)a2;
      ProductInfo = MsiGetProductInfoExW(v17, v16, dwContext, v15, szValue, &pcchValue);
      if ( !ProductInfo )
      {
        *(_DWORD *)(a1 + 696) = v14;
        std::wstring::operator=(a1 + 1008, szUserSid);
      }
    }
    std::wstring::~wstring(szUserSid);
  }
  if ( ProductInfo )
    return AslLogCallPrintf(
             3,
             (unsigned int)"MsiApplication::GetMsiProductInfo",
             473,
             (unsigned int)"GetMsiProductInfo failed to get %ls from %ls");
  v19 = -1;
  do
    ++v19;
  while ( szValue[v19] );
  return std::wstring::_Assign<unsigned short>(a6, szValue);
}

```

## disassembly

```asm
0x18002f4f0  push    rbp
0x18002f4f2  push    rbx
0x18002f4f3  push    rsi
0x18002f4f4  push    rdi
0x18002f4f5  push    r12
0x18002f4f7  push    r13
0x18002f4f9  push    r14
0x18002f4fb  push    r15
0x18002f4fd  lea     rbp, [rsp-188h]
0x18002f505  sub     rsp, 288h
0x18002f50c  mov     [rsp+2C0h+var_288], 0FFFFFFFFFFFFFFFEh
0x18002f515  mov     rax, cs:__security_cookie
0x18002f51c  xor     rax, rsp
0x18002f51f  mov     [rbp+1C0h+var_50], rax
0x18002f526  mov     r12d, r9d
0x18002f529  mov     rsi, r8
0x18002f52c  mov     rdi, rdx
0x18002f52f  mov     r15, rcx
0x18002f532  mov     rbx, [rbp+1C0h+szProperty]
0x18002f539  mov     r13, [rbp+1C0h+arg_28]
0x18002f540  xor     edx, edx; Val
0x18002f542  mov     r8d, 208h; Size
0x18002f548  lea     rcx, [rsp+2C0h+var_260]; void *
0x18002f54d  call    memset_0
0x18002f552  mov     [rsp+2C0h+var_290], 104h
0x18002f55a  cmp     qword ptr [rbx+18h], 7
0x18002f55f  jbe     short loc_18002F566
0x18002f561  mov     r9, [rbx]
0x18002f564  jmp     short loc_18002F569
0x18002f566  mov     r9, rbx; szProperty
0x18002f569  xor     eax, eax
0x18002f56b  cmp     [rsi+10h], rax
0x18002f56f  jnz     short loc_18002F575
0x18002f571  mov     edx, eax
0x18002f573  jmp     short loc_18002F584
0x18002f575  cmp     qword ptr [rsi+18h], 7
0x18002f57a  jbe     short loc_18002F581
0x18002f57c  mov     rdx, [rsi]
0x18002f57f  jmp     short loc_18002F584
0x18002f581  mov     rdx, rsi; szUserSid
0x18002f584  cmp     qword ptr [rdi+18h], 7
0x18002f589  jbe     short loc_18002F590
0x18002f58b  mov     rcx, [rdi]
0x18002f58e  jmp     short loc_18002F593
0x18002f590  mov     rcx, rdi; szProductCode
0x18002f593  lea     rax, [rsp+2C0h+var_290]
0x18002f598  mov     [rsp+2C0h+pcchValue], rax; pcchValue
0x18002f59d  lea     rax, [rsp+2C0h+var_260]
0x18002f5a2  mov     [rsp+2C0h+szValue], rax; szValue
0x18002f5a7  mov     r8d, r12d; dwContext
0x18002f5aa  call    cs:__imp_MsiGetProductInfoExW
0x18002f5b0  mov     r14d, eax
0x18002f5b3  cmp     eax, 645h
0x18002f5b8  jnz     loc_18002F683
0x18002f5be  cmp     qword ptr [rsi+18h], 7
0x18002f5c3  jbe     short loc_18002F5C8
0x18002f5c5  mov     rsi, [rsi]
0x18002f5c8  mov     rdx, rsi
0x18002f5cb  lea     rcx, [rsp+2C0h+szUserSid]
0x18002f5d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002f5d5  nop
0x18002f5d6  mov     [rsp+2C0h+dwContext], r12d
0x18002f5db  lea     r9, [rsp+2C0h+dwContext]
0x18002f5e0  lea     r8, [rsp+2C0h+szUserSid]
0x18002f5e5  mov     rdx, rdi
0x18002f5e8  mov     rcx, r15
0x18002f5eb  call    ?GetMsiInstallContextAndUserSid@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@AEAW4tagMSIINSTALLCONTEXT@@@Z; MsiApplication::GetMsiInstallContextAndUserSid(std::wstring const &,std::wstring &,tagMSIINSTALLCONTEXT &)
0x18002f5f0  mov     esi, [rsp+2C0h+dwContext]
0x18002f5f4  lea     eax, [rsi-1]
0x18002f5f7  cmp     eax, 1
0x18002f5fa  ja      short loc_18002F674
0x18002f5fc  mov     [rsp+2C0h+var_290], 104h
0x18002f604  cmp     qword ptr [rbx+18h], 7
0x18002f609  jbe     short loc_18002F610
0x18002f60b  mov     r9, [rbx]
0x18002f60e  jmp     short loc_18002F613
0x18002f610  mov     r9, rbx; szProperty
0x18002f613  lea     rdx, [rsp+2C0h+szUserSid]
0x18002f618  cmp     [rsp+2C0h+var_268], 7
0x18002f61e  cmova   rdx, [rsp+2C0h+szUserSid]; szUserSid
0x18002f624  cmp     qword ptr [rdi+18h], 7
0x18002f629  jbe     short loc_18002F630
0x18002f62b  mov     rcx, [rdi]
0x18002f62e  jmp     short loc_18002F633
0x18002f630  mov     rcx, rdi; szProductCode
0x18002f633  lea     rax, [rsp+2C0h+var_290]
0x18002f638  mov     [rsp+2C0h+pcchValue], rax; pcchValue
0x18002f63d  lea     rax, [rsp+2C0h+var_260]
0x18002f642  mov     [rsp+2C0h+szValue], rax; szValue
0x18002f647  mov     r8d, esi; dwContext
0x18002f64a  call    cs:__imp_MsiGetProductInfoExW
0x18002f650  mov     r14d, eax
0x18002f653  xor     r12d, r12d
0x18002f656  test    eax, eax
0x18002f658  jnz     short loc_18002F677
0x18002f65a  mov     [r15+2B8h], esi
0x18002f661  lea     rcx, [r15+3F0h]
0x18002f668  lea     rdx, [rsp+2C0h+szUserSid]
0x18002f66d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002f672  jmp     short loc_18002F677
0x18002f674  xor     r12d, r12d
0x18002f677  lea     rcx, [rsp+2C0h+szUserSid]
0x18002f67c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f681  jmp     short loc_18002F686
0x18002f683  xor     r12d, r12d
0x18002f686  test    r14d, r14d
0x18002f689  jz      short loc_18002F6C9
0x18002f68b  cmp     qword ptr [rdi+18h], 7
0x18002f690  jbe     short loc_18002F695
0x18002f692  mov     rdi, [rdi]
0x18002f695  cmp     qword ptr [rbx+18h], 7
0x18002f69a  jbe     short loc_18002F69F
0x18002f69c  mov     rbx, [rbx]
0x18002f69f  mov     [rsp+2C0h+pcchValue], rdi
0x18002f6a4  mov     [rsp+2C0h+szValue], rbx
0x18002f6a9  lea     r9, aGetmsiproducti; "GetMsiProductInfo failed to get %ls fro"...
0x18002f6b0  mov     r8d, 1D9h
0x18002f6b6  lea     rdx, aMsiapplication_0; "MsiApplication::GetMsiProductInfo"
0x18002f6bd  mov     ecx, 3
0x18002f6c2  call    AslLogCallPrintf
0x18002f6c7  jmp     short loc_18002F6E9
0x18002f6c9  lea     rax, [rsp+2C0h+var_260]
0x18002f6ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002f6d2  inc     r8
0x18002f6d5  cmp     [rax+r8*2], r12w
0x18002f6da  jnz     short loc_18002F6D2
0x18002f6dc  lea     rdx, [rsp+2C0h+var_260]
0x18002f6e1  mov     rcx, r13
0x18002f6e4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002f6e9  mov     rcx, [rbp+1C0h+var_50]
0x18002f6f0  xor     rcx, rsp; StackCookie
0x18002f6f3  call    __security_check_cookie
0x18002f6f8  add     rsp, 288h
0x18002f6ff  pop     r15
0x18002f701  pop     r14
0x18002f703  pop     r13
0x18002f705  pop     r12
0x18002f707  pop     rdi
0x18002f708  pop     rsi
0x18002f709  pop     rbx
0x18002f70a  pop     rbp
0x18002f70b  retn
```
