# OOBEUserAutologon::ClearAutologon(void)

- ea: `0x18001edf0`
- end: `0x18001ee60`
- name: `?ClearAutologon@OOBEUserAutologon@@UEAAJXZ`
- size: `112`
- prototype: `int(OOBEUserAutologon *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007134`
- `0x180018c98`
- `0x18001edf0`
- `0x18001ee68`
- `0x18001f168`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18001ee13`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18001ee13`

## string_xrefs

- `0x18001ee22`: `shell\oobe\user\dll\oobeuserautologon.cpp`

## pseudocode

```c
__int64 __fastcall OOBEUserAutologon::ClearAutologon(OOBEUserAutologon *this)
{
  unsigned int v1; // ebx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY phkResult; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  if ( RegOpenCurrentUser(0xF003Fu, &phkResult) )
  {
    v1 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"shell\\oobe\\user\\dll\\oobeuserautologon.cpp",
      (const char *)0x80070005LL,
      v3);
  }
  else
  {
    ClearCachedAutologonSettings(L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE", phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v1;
}

```

## disassembly

```asm
0x18001edf0  push    rbx; int
0x18001edf2  sub     rsp, 20h
0x18001edf6  xor     ebx, ebx
0x18001edf8  lea     rcx, [rsp+28h+phkResult]
0x18001edfd  xor     edx, edx
0x18001edff  mov     [rsp+28h+phkResult], rbx
0x18001ee04  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001ee09  lea     rdx, [rsp+28h+phkResult]; phkResult
0x18001ee0e  mov     ecx, 0F003Fh; samDesired
0x18001ee13  call    cs:__imp_RegOpenCurrentUser
0x18001ee19  test    eax, eax
0x18001ee1b  jz      short loc_18001EE3D
0x18001ee1d  mov     rcx, [rsp+28h]; this
0x18001ee22  lea     r8, aShellOobeUserD_4; "shell\\oobe\\user\\dll\\oobeuserautolog"...
0x18001ee29  mov     ebx, 80070005h
0x18001ee2e  mov     edx, 2Dh ; '-'; void *
0x18001ee33  mov     r9d, ebx; char *
0x18001ee36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee3b  jmp     short loc_18001EE4E
0x18001ee3d  mov     rdx, [rsp+28h+phkResult]; HKEY
0x18001ee42  lea     rcx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001ee49  call    ?ClearCachedAutologonSettings@@YAXPEBGPEAUHKEY__@@@Z; ClearCachedAutologonSettings(ushort const *,HKEY__ *)
0x18001ee4e  lea     rcx, [rsp+28h+phkResult]
0x18001ee53  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001ee58  mov     eax, ebx
0x18001ee5a  add     rsp, 20h
0x18001ee5e  pop     rbx
0x18001ee5f  retn
```
