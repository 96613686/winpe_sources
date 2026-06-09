# OOBE::CompleteTime::details::GetOOBECompleteKey

- ea: `0x180024cbc`
- end: `0x180024d69`
- name: `OOBE::CompleteTime::details::GetOOBECompleteKey`
- size: `173`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002649c`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x1800153f8`
- `0x180024cbc`
- `0x180024d70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024d38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024d38`

## string_xrefs

- `0x180024cf1`: `OOBECompleteTimestamp`
- `0x180024cea`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`
- `0x180024d0b`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::CompleteTime::details::GetOOBECompleteKey(PHKEY phkResult)
{
  int RedirectionKeyPath; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+8h] BYREF

  *phkResult = 0;
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(
                         L"OOBECompleteTimestamp",
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompleteTimestamp",
                         (unsigned __int16 **)&lpSubKey);
  v3 = RedirectionKeyPath;
  if ( RedirectionKeyPath >= 0 )
  {
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, phkResult);
    if ( v4 )
    {
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      v3 = v4;
    }
    else
    {
      v3 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBECompleteTime.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      phkResulta);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  return v3;
}

```

## disassembly

```asm
0x180024cbc  mov     [rsp+arg_8], rbx
0x180024cc1  push    rdi
0x180024cc2  sub     rsp, 30h
0x180024cc6  mov     rdi, rcx
0x180024cc9  mov     qword ptr [rcx], 0
0x180024cd0  mov     [rsp+38h+lpSubKey], 0
0x180024cd9  xor     edx, edx
0x180024cdb  lea     rcx, [rsp+38h+lpSubKey]
0x180024ce0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180024ce5  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180024cea  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180024cf1  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x180024cf8  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180024cfd  mov     ebx, eax
0x180024cff  test    eax, eax
0x180024d01  jns     short loc_180024D1E
0x180024d03  mov     rcx, [rsp+38h]; this
0x180024d08  mov     r9d, eax; char *
0x180024d0b  lea     r8, aOnecoreuapInte_8; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x180024d12  mov     edx, 16h; void *
0x180024d17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024d1c  jmp     short loc_180024D52
0x180024d1e  mov     qword ptr [rsp+38h+phkResult], rdi; phkResult
0x180024d23  mov     r9d, 2001Fh; samDesired
0x180024d29  xor     r8d, r8d; ulOptions
0x180024d2c  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180024d31  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024d38  call    cs:__imp_RegOpenKeyExW
0x180024d3e  test    eax, eax
0x180024d40  jz      short loc_180024D50
0x180024d42  jle     short loc_180024D4C
0x180024d44  movzx   eax, ax
0x180024d47  or      eax, 80070000h
0x180024d4c  mov     ebx, eax
0x180024d4e  jmp     short loc_180024D52
0x180024d50  xor     ebx, ebx
0x180024d52  lea     rcx, [rsp+38h+lpSubKey]
0x180024d57  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024d5c  mov     eax, ebx
0x180024d5e  mov     rbx, [rsp+38h+arg_8]
0x180024d63  add     rsp, 30h
0x180024d67  pop     rdi
0x180024d68  retn
```
