# LSUtility::GetOSVersion(void)

- ea: `0x180058570`
- end: `0x1800586e2`
- name: `?GetOSVersion@LSUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007f4f0`
- `0x18011d3c0`

## callees

- `0x180016e8c`
- `0x18002085c`
- `0x1800209d4`
- `0x1800498bc`
- `0x180058570`
- `0x1800a98c0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180058601`
- `OLEAUT32!__imp_SysFreeString` at `0x1800586b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180058601`
- `OLEAUT32!__imp_SysFreeString` at `0x1800586b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800585e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058674`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800585e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058674`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800586ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800586ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005862e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005862e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
OLECHAR *__fastcall LSUtility::GetOSVersion(OLECHAR *a1)
{
  OLECHAR *v2; // rbx
  LSTATUS ValueW; // eax
  bool v4; // sf
  LSTATUS v6; // eax
  signed int v7; // edi
  __int64 v8; // rax
  void *pvData; // rsi
  OLECHAR *v10; // [rsp+48h] [rbp-28h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-10h] BYREF

  bstrString[1] = a1;
  std::wstring::wstring(a1);
  v2 = 0;
  v10 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion",
             L"BuildLabEx",
             2u,
             0,
             0,
             &pcbData);
  v4 = ValueW < 0;
  if ( ValueW > 0 )
    v4 = 1;
  if ( !v4 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    if ( pvData )
    {
      v6 = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion",
             L"BuildLabEx",
             2u,
             0,
             pvData,
             &pcbData);
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      if ( v7 >= 0 )
      {
        *((_WORD *)pvData + ((unsigned __int64)pcbData >> 1) - 1) = 0;
        v8 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, (const unsigned __int16 *)pvData);
        ATL::CComBSTR::operator=(&v10, v8);
        SysFreeString(bstrString[0]);
        v2 = v10;
      }
      CoTaskMemFree(pvData);
      if ( v7 >= 0 )
        std::wstring::append(a1, v2);
    }
  }
  SysFreeString(v2);
  return a1;
}

```

## disassembly

```asm
0x180058570  mov     [rsp-18h+arg_8], rbx
0x180058575  mov     [rsp-18h+arg_10], rsi
0x18005857a  push    rbp
0x18005857b  push    rdi
0x18005857c  push    r14
0x18005857e  mov     rbp, rsp
0x180058581  sub     rsp, 70h
0x180058585  mov     rax, cs:__security_cookie
0x18005858c  xor     rax, rsp
0x18005858f  mov     [rbp+var_8], rax
0x180058593  mov     r14, rcx
0x180058596  mov     [rbp+var_18], rcx
0x18005859a  mov     dword ptr [rbp+var_30], 0
0x1800585a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800585a6  mov     dword ptr [rbp+var_30], 1
0x1800585ad  xor     ebx, ebx
0x1800585af  mov     [rbp+var_28], rbx
0x1800585b3  mov     [rbp+var_10], ebx
0x1800585b6  lea     rax, [rbp+var_10]
0x1800585ba  mov     [rsp+70h+pcbData], rax; pcbData
0x1800585bf  mov     [rsp+70h+pvData], rbx; pvData
0x1800585c4  mov     [rsp+70h+pdwType], rbx; pdwType
0x1800585c9  lea     edi, [rbx+2]
0x1800585cc  mov     r9d, edi; dwFlags
0x1800585cf  lea     r8, Value; "BuildLabEx"
0x1800585d6  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800585dd  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800585e4  call    cs:__imp_RegGetValueW
0x1800585ea  test    eax, eax
0x1800585ec  jle     short loc_1800585F8
0x1800585ee  movzx   eax, ax
0x1800585f1  or      eax, 80070000h
0x1800585f6  test    eax, eax
0x1800585f8  jns     loc_1800586C7
0x1800585fe  mov     rcx, rbx; bstrString
0x180058601  call    cs:__imp_SysFreeString
0x180058607  mov     rax, r14
0x18005860a  mov     rcx, [rbp+var_8]
0x18005860e  xor     rcx, rsp; StackCookie
0x180058611  call    __security_check_cookie
0x180058616  lea     r11, [rsp+70h+var_s0]
0x18005861b  mov     rbx, [r11+28h]
0x18005861f  mov     rsi, [r11+30h]
0x180058623  mov     rsp, r11
0x180058626  pop     r14
0x180058628  pop     rdi
0x180058629  pop     rbp
0x18005862a  retn
0x18005862b  mov     rcx, rsi; pv
0x18005862e  call    cs:__imp_CoTaskMemFree
0x180058634  test    edi, edi
0x180058636  js      short loc_1800585FE
0x180058638  mov     rdx, rbx
0x18005863b  mov     rcx, r14
0x18005863e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180058643  jmp     short loc_1800585FE
0x180058645  lea     rax, [rbp+var_10]
0x180058649  mov     [rsp+70h+pcbData], rax; pcbData
0x18005864e  mov     [rsp+70h+pvData], rsi; pvData
0x180058653  mov     [rsp+70h+pdwType], 0; pdwType
0x18005865c  mov     r9d, edi; dwFlags
0x18005865f  lea     r8, Value; "BuildLabEx"
0x180058666  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005866d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180058674  call    cs:__imp_RegGetValueW
0x18005867a  mov     edi, eax
0x18005867c  test    eax, eax
0x18005867e  jle     short loc_180058689
0x180058680  movzx   edi, ax
0x180058683  or      edi, 80070000h
0x180058689  test    edi, edi
0x18005868b  js      short loc_18005862B
0x18005868d  mov     ecx, [rbp+var_10]
0x180058690  shr     rcx, 1
0x180058693  xor     eax, eax
0x180058695  mov     [rsi+rcx*2-2], ax
0x18005869a  mov     rdx, rsi; unsigned __int16 *
0x18005869d  lea     rcx, [rbp+bstrString]; this
0x1800586a1  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800586a6  nop
0x1800586a7  mov     rdx, rax
0x1800586aa  lea     rcx, [rbp+var_28]
0x1800586ae  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x1800586b3  nop
0x1800586b4  mov     rcx, [rbp+bstrString]; bstrString
0x1800586b8  call    cs:__imp_SysFreeString
0x1800586be  mov     rbx, [rbp+var_28]
0x1800586c2  jmp     loc_18005862B
0x1800586c7  mov     ecx, [rbp+var_10]; cb
0x1800586ca  call    cs:__imp_CoTaskMemAlloc
0x1800586d0  mov     rsi, rax
0x1800586d3  test    rax, rax
0x1800586d6  jz      loc_1800585FE
0x1800586dc  jmp     loc_180058645
```
