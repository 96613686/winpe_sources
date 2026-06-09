# StorageHealth::OneSettings::ForceResetQueryState(void)

- ea: `0x18005052c`
- end: `0x1800505d6`
- name: `?ForceResetQueryState@OneSettings@StorageHealth@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(StorageHealth::OneSettings *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004fdf8`

## callees

- `0x180019210`
- `0x180019db4`
- `0x18001c130`
- `0x18005052c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180050582`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005059f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180050582`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005059f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050565`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050565`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageHealth::OneSettings::ForceResetQueryState(StorageHealth::OneSettings *this)
{
  unsigned int v1; // ebx
  const WCHAR *v2; // rax
  __int64 v3; // r10
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  hKey = 0;
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 136);
  v4 = RegOpenKeyExW(*(HKEY *)(v3 + 248), v2, 0, 0xF003Fu, &hKey);
  if ( v4 )
  {
    v5 = 298;
LABEL_7:
    v1 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagehealth\\onesettings.cpp",
           (const char *)v4,
           phkResult);
    goto LABEL_8;
  }
  v4 = RegDeleteValueW(hKey, L"ETag");
  if ( v4 )
  {
    v5 = 299;
    goto LABEL_7;
  }
  v4 = RegDeleteValueW(hKey, L"refreshAfter");
  if ( v4 )
  {
    v5 = 300;
    goto LABEL_7;
  }
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v1;
}

```

## disassembly

```asm
0x18005052c  push    rbx
0x18005052e  sub     rsp, 30h
0x180050532  mov     r10, rcx
0x180050535  xor     ebx, ebx
0x180050537  mov     [rsp+38h+hKey], rbx
0x18005053c  add     rcx, 88h
0x180050543  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050548  lea     rcx, [rsp+38h+hKey]
0x18005054d  mov     qword ptr [rsp+38h+phkResult], rcx; unsigned int
0x180050552  mov     r9d, 0F003Fh; samDesired
0x180050558  xor     r8d, r8d; ulOptions
0x18005055b  mov     rdx, rax; lpSubKey
0x18005055e  mov     rcx, [r10+0F8h]; hKey
0x180050565  call    cs:__imp_RegOpenKeyExW
0x18005056b  test    eax, eax
0x18005056d  jz      short loc_180050576
0x18005056f  mov     edx, 12Ah
0x180050574  jmp     short loc_1800505AE
0x180050576  lea     rdx, aEtag; "ETag"
0x18005057d  mov     rcx, [rsp+38h+hKey]; hKey
0x180050582  call    cs:__imp_RegDeleteValueW
0x180050588  test    eax, eax
0x18005058a  jz      short loc_180050593
0x18005058c  mov     edx, 12Bh
0x180050591  jmp     short loc_1800505AE
0x180050593  lea     rdx, aRefreshafter; "refreshAfter"
0x18005059a  mov     rcx, [rsp+38h+hKey]; hKey
0x18005059f  call    cs:__imp_RegDeleteValueW
0x1800505a5  test    eax, eax
0x1800505a7  jz      short loc_1800505C4
0x1800505a9  mov     edx, 12Ch; void *
0x1800505ae  mov     r9d, eax; char *
0x1800505b1  lea     r8, aOnecoreDrivers_29; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800505b8  mov     rcx, [rsp+38h]; this
0x1800505bd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800505c2  mov     ebx, eax
0x1800505c4  lea     rcx, [rsp+38h+hKey]
0x1800505c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800505ce  mov     eax, ebx
0x1800505d0  add     rsp, 30h
0x1800505d4  pop     rbx
0x1800505d5  retn
```
