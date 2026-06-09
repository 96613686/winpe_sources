# PrintCore::RegHelpers::OpenKey(HKEY__ * const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x18002a034`
- end: `0x18002a0e0`
- name: `?OpenKey@RegHelpers@PrintCore@@SAPEAUHKEY__@@AEBQEAU3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `172`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002a6f0`

## callees

- `0x180027060`
- `0x18002a034`
- `0x18002f1d4`
- `0x18002faf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a07c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a07c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY __fastcall PrintCore::RegHelpers::OpenKey(HKEY *a1, const WCHAR *a2)
{
  unsigned int v4; // eax
  HKEY v5; // rbx
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v9,
    0);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v4 = RegOpenKeyExW(*a1, a2, 0, 0xF003Fu, &v9);
  if ( v4 == 2 || v4 == 1018 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v9);
    return 0;
  }
  else
  {
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x30,
        (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\RegHelpers.h",
        (const char *)v4,
        phkResult);
    v5 = v9;
    v9 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v9);
    return v5;
  }
}

```

## disassembly

```asm
0x18002a034  mov     [rsp+arg_8], rbx
0x18002a039  push    rdi
0x18002a03a  sub     rsp, 30h
0x18002a03e  mov     rbx, rdx
0x18002a041  mov     rdi, rcx
0x18002a044  mov     [rsp+38h+arg_0], 0
0x18002a04d  xor     edx, edx
0x18002a04f  lea     rcx, [rsp+38h+arg_0]
0x18002a054  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a059  cmp     qword ptr [rbx+18h], 7
0x18002a05e  jbe     short loc_18002A063
0x18002a060  mov     rbx, [rbx]
0x18002a063  lea     rax, [rsp+38h+arg_0]
0x18002a068  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x18002a06d  mov     r9d, 0F003Fh; samDesired
0x18002a073  xor     r8d, r8d; ulOptions
0x18002a076  mov     rdx, rbx; lpSubKey
0x18002a079  mov     rcx, [rdi]; hKey
0x18002a07c  call    cs:__imp_RegOpenKeyExW
0x18002a082  cmp     eax, 2
0x18002a085  jz      short loc_18002A0B4
0x18002a087  cmp     eax, 3FAh
0x18002a08c  jz      short loc_18002A0B4
0x18002a08e  mov     rcx, [rsp+38h]; this
0x18002a093  test    eax, eax
0x18002a095  jnz     short loc_18002A0CB
0x18002a097  mov     rbx, [rsp+38h+arg_0]
0x18002a09c  mov     [rsp+38h+arg_0], 0
0x18002a0a5  lea     rcx, [rsp+38h+arg_0]
0x18002a0aa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a0af  mov     rax, rbx
0x18002a0b2  jmp     short loc_18002A0C0
0x18002a0b4  lea     rcx, [rsp+38h+arg_0]
0x18002a0b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a0be  xor     eax, eax
0x18002a0c0  mov     rbx, [rsp+38h+arg_8]
0x18002a0c5  add     rsp, 30h
0x18002a0c9  pop     rdi
0x18002a0ca  retn
0x18002a0cb  mov     r9d, eax; char *
0x18002a0ce  lea     r8, aOnecoreuapInte_3; "OneCoreUap\\Internal\\Printscan\\inc\\R"...
0x18002a0d5  mov     edx, 30h ; '0'; void *
0x18002a0da  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
