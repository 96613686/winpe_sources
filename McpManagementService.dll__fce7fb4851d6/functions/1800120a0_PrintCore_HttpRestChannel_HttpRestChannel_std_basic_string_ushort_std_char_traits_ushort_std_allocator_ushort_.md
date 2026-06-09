# PrintCore::HttpRestChannel::HttpRestChannel(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,ulong,PrintCore::HttpTimeouts)

- ea: `0x1800120a0`
- end: `0x180012276`
- name: `??0HttpRestChannel@PrintCore@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00_NKUHttpTimeouts@1@@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, int, __int64)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800146b8`
- `0x1800157bc`
- `0x180016184`
- `0x18001b128`

## callees

- `0x180003a60`
- `0x180003aa0`
- `0x180007468`
- `0x180009264`
- `0x18000e1ac`
- `0x18000e208`
- `0x18000e790`
- `0x180011d98`
- `0x180011de0`
- `0x1800120a0`
- `0x180012e90`
- `0x18001c0f4`
- `0x18001c5f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180012198`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180012198`

## string_xrefs

- `0x1800121e2`: `Not using SSL/TLS encryption (NoEncryption registry key set)`

## pseudocode

```c
__int64 __fastcall PrintCore::HttpRestChannel::HttpRestChannel(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  _QWORD *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // r8d
  HKEY v13; // rbx
  HKEY phkResult; // [rsp+20h] [rbp-41h] BYREF
  _QWORD v16[2]; // [rsp+28h] [rbp-39h] BYREF
  _BYTE v17[32]; // [rsp+38h] [rbp-29h] BYREF
  _BYTE v18[32]; // [rsp+58h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+47h]

  v16[1] = a1;
  *(_DWORD *)a1 = 0x10000;
  std::wstring::wstring(a1 + 8, a2);
  std::wstring::wstring(a1 + 40, a3);
  std::wstring::wstring(a1 + 72, a4);
  v16[0] = a1 + 104;
  *(_DWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  v10 = operator new(0x50u);
  *v10 = v10;
  v10[1] = v10;
  *(_QWORD *)(a1 + 112) = v10;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 7;
  *(_QWORD *)(a1 + 160) = 8;
  *(_DWORD *)(a1 + 104) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Assign_grow(
    a1 + 128,
    16,
    *(_QWORD *)(a1 + 112));
  *(_BYTE *)(a1 + 168) = 1;
  *(_DWORD *)(a1 + 172) = 0;
  *(_QWORD *)(a1 + 176) = *(_QWORD *)a7;
  *(_DWORD *)(a1 + 184) = *(_DWORD *)(a7 + 8);
  *(_QWORD *)(a1 + 192) = -1;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v11 = RegOpenCurrentUser(0x20019u, &phkResult);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x3C, v12, (const char *)v11, (unsigned int)phkResult);
  v13 = phkResult;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  v16[0] = v13;
  phkResult = v13;
  if ( PrintCore::RegHelpers::GetDwordValue(
         &phkResult,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Print\\Ipp",
         L"NoEncryption",
         0) == 1 )
  {
    HttpRestTelemetry::WriteDbgTraceInfo(
      "PrintCore::HttpRestChannel::HttpRestChannel",
      L"Not using SSL/TLS encryption (NoEncryption registry key set)");
    *(_BYTE *)(a1 + 168) = 0;
  }
  std::wstring::wstring(v18, L"10.0.29599.1000");
  std::wstring::wstring(v17, L"MS-WIN-VER");
  PrintCore::HttpRestChannel::AddRequestHeader(a1, v17, v18);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v16);
  return a1;
}

```

## disassembly

```asm
0x1800120a0  push    rbp
0x1800120a2  push    rbx
0x1800120a3  push    rsi
0x1800120a4  push    rdi
0x1800120a5  lea     rbp, [rsp-27h]
0x1800120aa  sub     rsp, 88h
0x1800120b1  mov     rax, cs:__security_cookie
0x1800120b8  xor     rax, rsp
0x1800120bb  mov     [rbp+3Fh+var_28], rax
0x1800120bf  mov     rdi, r9
0x1800120c2  mov     rbx, r8
0x1800120c5  mov     rsi, rcx
0x1800120c8  mov     [rbp+3Fh+var_70], rcx
0x1800120cc  mov     dword ptr [rcx], 10000h
0x1800120d2  add     rcx, 8
0x1800120d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800120db  nop
0x1800120dc  lea     rcx, [rsi+28h]
0x1800120e0  mov     rdx, rbx
0x1800120e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800120e8  nop
0x1800120e9  lea     rcx, [rsi+48h]
0x1800120ed  mov     rdx, rdi
0x1800120f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800120f5  nop
0x1800120f6  lea     rbx, [rsi+68h]
0x1800120fa  mov     [rbp+3Fh+var_78], rbx
0x1800120fe  xor     edi, edi
0x180012100  mov     [rbx], edi
0x180012102  mov     [rbx+8], rdi
0x180012106  mov     [rbx+10h], rdi
0x18001210a  lea     ecx, [rdi+50h]; Size
0x18001210d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012112  mov     [rax], rax
0x180012115  mov     [rax+8], rax
0x180012119  mov     [rbx+8], rax
0x18001211d  lea     rcx, [rbx+18h]
0x180012121  mov     [rcx], rdi
0x180012124  mov     [rcx+8], rdi
0x180012128  mov     [rcx+10h], rdi
0x18001212c  mov     qword ptr [rbx+30h], 7
0x180012134  mov     qword ptr [rbx+38h], 8
0x18001213c  mov     dword ptr [rbx], 3F800000h
0x180012142  mov     r8, [rbx+8]
0x180012146  lea     edx, [rdi+10h]
0x180012149  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::wstring>>>>)
0x18001214e  nop
0x18001214f  mov     byte ptr [rsi+0A8h], 1
0x180012156  mov     [rsi+0ACh], edi
0x18001215c  mov     rax, [rbp+3Fh+arg_30]
0x180012160  movsd   xmm0, qword ptr [rax]
0x180012164  movsd   qword ptr [rsi+0B0h], xmm0
0x18001216c  mov     eax, [rax+8]
0x18001216f  mov     [rsi+0B8h], eax
0x180012175  mov     qword ptr [rsi+0C0h], 0FFFFFFFFFFFFFFFFh
0x180012180  mov     [rbp+3Fh+phkResult], rdi
0x180012184  xor     edx, edx
0x180012186  lea     rcx, [rbp+3Fh+phkResult]
0x18001218a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001218f  lea     rdx, [rbp+3Fh+phkResult]; phkResult
0x180012193  mov     ecx, 20019h; samDesired
0x180012198  call    cs:__imp_RegOpenCurrentUser
0x18001219e  mov     rcx, [rbp+47h]; this
0x1800121a2  test    eax, eax
0x1800121a4  jnz     loc_180012268
0x1800121aa  mov     rbx, [rbp+3Fh+phkResult]
0x1800121ae  mov     [rbp+3Fh+phkResult], rdi
0x1800121b2  lea     rcx, [rbp+3Fh+phkResult]
0x1800121b6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800121bb  mov     [rbp+3Fh+var_78], rbx
0x1800121bf  mov     [rbp+3Fh+phkResult], rbx
0x1800121c3  xor     r9d, r9d; bool *
0x1800121c6  lea     r8, aNoencryption; "NoEncryption"
0x1800121cd  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800121d4  lea     rcx, [rbp+3Fh+phkResult]; HKEY *
0x1800121d8  call    ?GetDwordValue@RegHelpers@PrintCore@@SAKAEBQEAUHKEY__@@PEBG1PEA_N@Z; PrintCore::RegHelpers::GetDwordValue(HKEY__ * const &,ushort const *,ushort const *,bool *)
0x1800121dd  cmp     eax, 1
0x1800121e0  jnz     short loc_1800121FC
0x1800121e2  lea     rdx, aNotUsingSslTls; "Not using SSL/TLS encryption (NoEncrypt"...
0x1800121e9  lea     rcx, aPrintcoreHttpr_6; "PrintCore::HttpRestChannel::HttpRestCha"...
0x1800121f0  call    ?WriteDbgTraceInfo@HttpRestTelemetry@@SAXPEBDPEBGZZ; HttpRestTelemetry::WriteDbgTraceInfo(char const *,ushort const *,...)
0x1800121f5  mov     [rsi+0A8h], dil
0x1800121fc  lea     rdx, a100295991000; "10.0.29599.1000"
0x180012203  lea     rcx, [rbp+3Fh+var_48]
0x180012207  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001220c  nop
0x18001220d  lea     rdx, aMsWinVer; "MS-WIN-VER"
0x180012214  lea     rcx, [rbp+3Fh+var_68]
0x180012218  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001221d  nop
0x18001221e  lea     r8, [rbp+3Fh+var_48]
0x180012222  lea     rdx, [rbp+3Fh+var_68]
0x180012226  mov     rcx, rsi
0x180012229  call    ?AddRequestHeader@HttpRestChannel@PrintCore@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PrintCore::HttpRestChannel::AddRequestHeader(std::wstring const &,std::wstring const &)
0x18001222e  nop
0x18001222f  lea     rcx, [rbp+3Fh+var_68]
0x180012233  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012238  nop
0x180012239  lea     rcx, [rbp+3Fh+var_48]
0x18001223d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012242  nop
0x180012243  lea     rcx, [rbp+3Fh+var_78]
0x180012247  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001224c  nop
0x18001224d  mov     rax, rsi
0x180012250  mov     rcx, [rbp+3Fh+var_28]
0x180012254  xor     rcx, rsp; StackCookie
0x180012257  call    __security_check_cookie
0x18001225c  add     rsp, 88h
0x180012263  pop     rdi
0x180012264  pop     rsi
0x180012265  pop     rbx
0x180012266  pop     rbp
0x180012267  retn
0x180012268  mov     r9d, eax; char *
0x18001226b  mov     edx, 3Ch ; '<'; void *
0x180012270  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
