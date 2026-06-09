# WindowsStorage::Utilities::registry_open_key_nothrow(HKEY__ *,ushort const *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x180011048`
- end: `0x1800110a8`
- name: `?registry_open_key_nothrow@Utilities@WindowsStorage@@YAJPEAUHKEY__@@PEBGKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010f78`
- `0x180010fdc`

## callees

- `0x18000f040`
- `0x180011048`
- `0x180011344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011078`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011078`

## string_xrefs

- `0x180011087`: `onecore\base\windows.storage\src\Registry.h`

## pseudocode

```c
int __fastcall WindowsStorage::Utilities::registry_open_key_nothrow(
        HKEY hKey,
        LPCWSTR lpSubKey,
        REGSAM samDesired,
        HKEY *a4)
{
  unsigned int v8; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    a4,
    0);
  v8 = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, a4);
  if ( v8 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2A,
             (unsigned int)"onecore\\base\\windows.storage\\src\\Registry.h",
             (const char *)v8,
             phkResult);
  else
    return 0;
}

```

## disassembly

```asm
0x180011048  push    rbx
0x18001104a  push    rbp
0x18001104b  push    rsi
0x18001104c  push    rdi
0x18001104d  sub     rsp, 38h
0x180011051  mov     rsi, rdx
0x180011054  mov     rbp, rcx
0x180011057  xor     edx, edx
0x180011059  mov     rcx, r9
0x18001105c  mov     rbx, r9
0x18001105f  mov     edi, r8d
0x180011062  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180011067  mov     r9d, edi; samDesired
0x18001106a  mov     qword ptr [rsp+58h+phkResult], rbx; unsigned int
0x18001106f  xor     r8d, r8d; ulOptions
0x180011072  mov     rdx, rsi; lpSubKey
0x180011075  mov     rcx, rbp; hKey
0x180011078  call    cs:__imp_RegOpenKeyExW
0x18001107e  test    eax, eax
0x180011080  jz      short loc_18001109D
0x180011082  mov     rcx, [rsp+58h]; this
0x180011087  lea     r8, aOnecoreBaseWin_7; "onecore\\base\\windows.storage\\src\\Re"...
0x18001108e  mov     r9d, eax; char *
0x180011091  mov     edx, 2Ah ; '*'; void *
0x180011096  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001109b  jmp     short loc_18001109F
0x18001109d  xor     eax, eax
0x18001109f  add     rsp, 38h
0x1800110a3  pop     rdi
0x1800110a4  pop     rsi
0x1800110a5  pop     rbp
0x1800110a6  pop     rbx
0x1800110a7  retn
```
