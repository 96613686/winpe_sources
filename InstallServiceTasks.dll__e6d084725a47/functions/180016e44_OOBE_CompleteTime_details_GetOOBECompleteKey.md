# OOBE::CompleteTime::details::GetOOBECompleteKey

- ea: `0x180016e44`
- end: `0x180016ee3`
- name: `OOBE::CompleteTime::details::GetOOBECompleteKey`
- size: `159`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800191a4`

## callees

- `0x18000912c`
- `0x1800156c8`
- `0x180016e44`
- `0x180016eec`
- `0x1800198e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016eb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016eb2`

## string_xrefs

- `0x180016e85`: `onecoreuap\internal\shell\inc\OOBECompleteTime.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::CompleteTime::details::GetOOBECompleteKey(PHKEY phkResult)
{
  const unsigned __int16 *v2; // rdx
  const unsigned __int16 *v3; // rcx
  int RedirectionKeyPath; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+8h] BYREF

  *phkResult = 0;
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(v3, v2, (unsigned __int16 **)&lpSubKey);
  v5 = RedirectionKeyPath;
  if ( RedirectionKeyPath >= 0 )
  {
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, phkResult);
    if ( v6 )
    {
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v5 = v6;
    }
    else
    {
      v5 = 0;
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
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpSubKey);
  return v5;
}

```

## disassembly

```asm
0x180016e44  mov     [rsp+arg_8], rbx
0x180016e49  push    rdi
0x180016e4a  sub     rsp, 30h
0x180016e4e  mov     rdi, rcx
0x180016e51  mov     qword ptr [rcx], 0
0x180016e58  mov     [rsp+38h+lpSubKey], 0
0x180016e61  xor     edx, edx
0x180016e63  lea     rcx, [rsp+38h+lpSubKey]
0x180016e68  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180016e6d  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180016e72  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180016e77  mov     ebx, eax
0x180016e79  test    eax, eax
0x180016e7b  jns     short loc_180016E98
0x180016e7d  mov     rcx, [rsp+38h]; this
0x180016e82  mov     r9d, eax; char *
0x180016e85  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\OOBEC"...
0x180016e8c  mov     edx, 16h; void *
0x180016e91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e96  jmp     short loc_180016ECC
0x180016e98  mov     qword ptr [rsp+38h+phkResult], rdi; phkResult
0x180016e9d  mov     r9d, 2001Fh; samDesired
0x180016ea3  xor     r8d, r8d; ulOptions
0x180016ea6  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180016eab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016eb2  call    cs:__imp_RegOpenKeyExW
0x180016eb8  test    eax, eax
0x180016eba  jz      short loc_180016ECA
0x180016ebc  jle     short loc_180016EC6
0x180016ebe  movzx   eax, ax
0x180016ec1  or      eax, 80070000h
0x180016ec6  mov     ebx, eax
0x180016ec8  jmp     short loc_180016ECC
0x180016eca  xor     ebx, ebx
0x180016ecc  lea     rcx, [rsp+38h+lpSubKey]
0x180016ed1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180016ed6  mov     eax, ebx
0x180016ed8  mov     rbx, [rsp+38h+arg_8]
0x180016edd  add     rsp, 30h
0x180016ee1  pop     rdi
0x180016ee2  retn
```
