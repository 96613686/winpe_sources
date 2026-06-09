# Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::QueryTransportSupport(_GUID const &,Microsoft::Bluetooth::Audio::ChosenTransport)

- ea: `0x1800432a0`
- end: `0x180043497`
- name: `?QueryTransportSupport@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@AEAA?AV?$optional@_N@std@@AEBU_GUID@@W4ChosenTransport@234@@Z`
- size: `503`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003fe50`
- `0x1800405bc`

## callees

- `0x180001dd0`
- `0x1800151f4`
- `0x180015238`
- `0x180015b1c`
- `0x180019c68`
- `0x180019d20`
- `0x180019f80`
- `0x18003a434`
- `0x18003aa54`
- `0x18003d654`
- `0x18003d694`
- `0x18003d6cc`
- `0x1800432a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180043320`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180043320`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800433dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800433dd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043424`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043424`

## string_xrefs

- `0x1800432cd`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool *__fastcall Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::QueryTransportSupport(
        __int64 a1,
        bool *a2,
        const GUID *a3,
        int a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  const WCHAR *v15; // rax
  const WCHAR *v16; // rax
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v22[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v23[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v24[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v25[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v26[40]; // [rsp+F8h] [rbp-8h] BYREF
  OLECHAR sz[40]; // [rsp+120h] [rbp+20h] BYREF

  v8 = std::wstring::wstring(
         (__int64)v24,
         (__int64)L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats");
  v9 = std::operator+<unsigned short>(v23, v8);
  std::operator+<unsigned short>(v22, v9, a1 + 248);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v24);
  if ( !StringFromGUID2(a3, sz, 39) )
    goto LABEL_11;
  v10 = std::wstring::wstring((__int64)v26, (__int64)sz);
  v12 = std::operator+<unsigned short>(v25, v11, v10);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
  std::wstring::_Append<unsigned short>(v22, v13);
  std::wstring::_Tidy_deallocate(v25);
  std::wstring::_Tidy_deallocate(v26);
  std::wstring::wstring(v21);
  if ( a4 )
  {
    if ( a4 != 1 )
    {
      a2[1] = 0;
      goto LABEL_9;
    }
    v14 = 128;
  }
  else
  {
    v14 = 96;
  }
  std::wstring::operator=(v21, v14 + a1);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0x20019u, &hkey)
    || (pvData = 0,
        pcbData = 4,
        v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21),
        RegGetValueW(hkey, 0, v16, 0x10u, 0, &pvData, &pcbData)) )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    std::wstring::_Tidy_deallocate(v21);
LABEL_11:
    a2[1] = 0;
    goto LABEL_12;
  }
  *a2 = pvData != 0;
  a2[1] = 1;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
LABEL_9:
  std::wstring::_Tidy_deallocate(v21);
LABEL_12:
  std::wstring::_Tidy_deallocate(v22);
  return a2;
}

```

## disassembly

```asm
0x1800432a0  push    rbp
0x1800432a2  push    rbx
0x1800432a3  push    rsi
0x1800432a4  push    rdi
0x1800432a5  push    r14
0x1800432a7  lea     rbp, [rsp-80h]
0x1800432ac  sub     rsp, 180h
0x1800432b3  mov     rax, cs:__security_cookie
0x1800432ba  xor     rax, rsp
0x1800432bd  mov     [rbp+0A0h+var_30], rax
0x1800432c1  mov     esi, r9d
0x1800432c4  mov     rbx, r8
0x1800432c7  mov     rdi, rdx
0x1800432ca  mov     r14, rcx
0x1800432cd  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x1800432d4  lea     rcx, [rbp+0A0h+var_E8]
0x1800432d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800432dd  nop
0x1800432de  mov     rdx, rax
0x1800432e1  lea     rcx, [rbp+0A0h+var_108]
0x1800432e5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800432ea  nop
0x1800432eb  lea     r8, [r14+0F8h]
0x1800432f2  mov     rdx, rax
0x1800432f5  lea     rcx, [rsp+1A0h+var_128]
0x1800432fa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800432ff  nop
0x180043300  lea     rcx, [rbp+0A0h+var_108]
0x180043304  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043309  nop
0x18004330a  lea     rcx, [rbp+0A0h+var_E8]
0x18004330e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043313  mov     r8d, 27h ; '''; cchMax
0x180043319  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18004331d  mov     rcx, rbx; rguid
0x180043320  call    cs:__imp_StringFromGUID2
0x180043326  xor     ebx, ebx
0x180043328  test    eax, eax
0x18004332a  jz      loc_180043467
0x180043330  lea     rdx, [rbp+0A0h+sz]
0x180043334  lea     rcx, [rbp+0A0h+var_A8]
0x180043338  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004333d  nop
0x18004333e  mov     r8, rax
0x180043341  lea     rcx, [rbp+0A0h+var_C8]
0x180043345  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18004334a  mov     r8, [rax+10h]
0x18004334e  mov     rcx, rax
0x180043351  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043356  mov     rdx, rax
0x180043359  lea     rcx, [rsp+1A0h+var_128]
0x18004335e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180043363  nop
0x180043364  lea     rcx, [rbp+0A0h+var_C8]
0x180043368  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004336d  nop
0x18004336e  lea     rcx, [rbp+0A0h+var_A8]
0x180043372  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043377  lea     rcx, [rsp+1A0h+var_148]
0x18004337c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180043381  nop
0x180043382  test    esi, esi
0x180043384  jnz     short loc_18004338B
0x180043386  lea     eax, [rbx+60h]
0x180043389  jmp     short loc_180043397
0x18004338b  cmp     esi, 1
0x18004338e  jnz     loc_180043491
0x180043394  lea     eax, [rsi+7Fh]
0x180043397  lea     rdx, [rax+r14]
0x18004339b  lea     rcx, [rsp+1A0h+var_148]
0x1800433a0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800433a5  mov     [rsp+1A0h+hkey], rbx
0x1800433aa  xor     edx, edx
0x1800433ac  lea     rcx, [rsp+1A0h+hkey]
0x1800433b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800433b6  lea     rcx, [rsp+1A0h+var_128]
0x1800433bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800433c0  mov     rdx, rax; lpSubKey
0x1800433c3  lea     rax, [rsp+1A0h+hkey]
0x1800433c8  mov     [rsp+1A0h+phkResult], rax; phkResult
0x1800433cd  mov     r9d, 20019h; samDesired
0x1800433d3  xor     r8d, r8d; ulOptions
0x1800433d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800433dd  call    cs:__imp_RegOpenKeyExW
0x1800433e3  test    eax, eax
0x1800433e5  jnz     short loc_180043452
0x1800433e7  mov     [rsp+1A0h+var_160], ebx
0x1800433eb  mov     [rsp+1A0h+var_150], 4
0x1800433f3  lea     rcx, [rsp+1A0h+var_148]
0x1800433f8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800433fd  mov     r8, rax; lpValue
0x180043400  lea     rax, [rsp+1A0h+var_150]
0x180043405  mov     [rsp+1A0h+pcbData], rax; pcbData
0x18004340a  lea     rax, [rsp+1A0h+var_160]
0x18004340f  mov     [rsp+1A0h+pvData], rax; pvData
0x180043414  mov     [rsp+1A0h+phkResult], rbx; pdwType
0x180043419  xor     edx, edx; lpSubKey
0x18004341b  lea     r9d, [rdx+10h]; dwFlags
0x18004341f  mov     rcx, [rsp+1A0h+hkey]; hkey
0x180043424  call    cs:__imp_RegGetValueW
0x18004342a  test    eax, eax
0x18004342c  jnz     short loc_180043452
0x18004342e  cmp     [rsp+1A0h+var_160], ebx
0x180043432  setnz   cl
0x180043435  mov     [rdi], cl
0x180043437  mov     byte ptr [rdi+1], 1
0x18004343b  lea     rcx, [rsp+1A0h+hkey]
0x180043440  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043445  nop
0x180043446  lea     rcx, [rsp+1A0h+var_148]
0x18004344b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043450  jmp     short loc_18004346A
0x180043452  lea     rcx, [rsp+1A0h+hkey]
0x180043457  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004345c  nop
0x18004345d  lea     rcx, [rsp+1A0h+var_148]
0x180043462  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043467  mov     [rdi+1], bl
0x18004346a  lea     rcx, [rsp+1A0h+var_128]
0x18004346f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043474  mov     rax, rdi
0x180043477  mov     rcx, [rbp+0A0h+var_30]
0x18004347b  xor     rcx, rsp; StackCookie
0x18004347e  call    __security_check_cookie
0x180043483  add     rsp, 180h
0x18004348a  pop     r14
0x18004348c  pop     rdi
0x18004348d  pop     rsi
0x18004348e  pop     rbx
0x18004348f  pop     rbp
0x180043490  retn
0x180043491  mov     [rdi+1], bl
0x180043494  jmp     short loc_180043446
```
