# OOBE::CompleteTime::details::GetOOBECompleteKey

- ea: `0x18002586c`
- end: `0x180025919`
- name: `OOBE::CompleteTime::details::GetOOBECompleteKey`
- size: `173`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800269d0`

## callees

- `0x180007134`
- `0x18000a5c8`
- `0x18000e580`
- `0x18002586c`
- `0x180025b8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800258e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800258e8`

## string_xrefs

- `0x1800258a1`: `OOBECompleteTimestamp`
- `0x1800258bb`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`
- `0x18002589a`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompleteTimestamp`

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
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
  return v3;
}

```

## disassembly

```asm
0x18002586c  mov     [rsp+arg_8], rbx
0x180025871  push    rdi
0x180025872  sub     rsp, 30h
0x180025876  mov     rdi, rcx
0x180025879  mov     qword ptr [rcx], 0
0x180025880  mov     [rsp+38h+lpSubKey], 0
0x180025889  xor     edx, edx
0x18002588b  lea     rcx, [rsp+38h+lpSubKey]
0x180025890  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025895  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x18002589a  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800258a1  lea     rcx, aOobecompleteti; "OOBECompleteTimestamp"
0x1800258a8  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800258ad  mov     ebx, eax
0x1800258af  test    eax, eax
0x1800258b1  jns     short loc_1800258CE
0x1800258b3  mov     rcx, [rsp+38h]; this
0x1800258b8  mov     r9d, eax; char *
0x1800258bb  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x1800258c2  mov     edx, 16h; void *
0x1800258c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800258cc  jmp     short loc_180025902
0x1800258ce  mov     qword ptr [rsp+38h+phkResult], rdi; phkResult
0x1800258d3  mov     r9d, 2001Fh; samDesired
0x1800258d9  xor     r8d, r8d; ulOptions
0x1800258dc  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x1800258e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800258e8  call    cs:__imp_RegOpenKeyExW
0x1800258ee  test    eax, eax
0x1800258f0  jz      short loc_180025900
0x1800258f2  jle     short loc_1800258FC
0x1800258f4  movzx   eax, ax
0x1800258f7  or      eax, 80070000h
0x1800258fc  mov     ebx, eax
0x1800258fe  jmp     short loc_180025902
0x180025900  xor     ebx, ebx
0x180025902  lea     rcx, [rsp+38h+lpSubKey]
0x180025907  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002590c  mov     eax, ebx
0x18002590e  mov     rbx, [rsp+38h+arg_8]
0x180025913  add     rsp, 30h
0x180025917  pop     rdi
0x180025918  retn
```
