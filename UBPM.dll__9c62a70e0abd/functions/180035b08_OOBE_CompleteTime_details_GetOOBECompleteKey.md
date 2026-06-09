# OOBE::CompleteTime::details::GetOOBECompleteKey

- ea: `0x180035b08`
- end: `0x180035ba2`
- name: `OOBE::CompleteTime::details::GetOOBECompleteKey`
- size: `154`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003639c`

## callees

- `0x1800355e8`
- `0x180035b08`
- `0x180035ba8`
- `0x1800361e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035b6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035b6a`

## string_xrefs

- `0x180035b3a`: `onecoreuap\internal\shell\inc\OobeCompleteTime.h`

## pseudocode

```c
__int64 __fastcall OOBE::CompleteTime::details::GetOOBECompleteKey(
        unsigned __int16 *phkResult,
        const unsigned __int16 *a2)
{
  int RedirectionKeyPath; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)phkResult = 0;
  lpSubKey = 0;
  RedirectionKeyPath = GetRedirectionKeyPath(phkResult, a2, (unsigned __int16 **)&lpSubKey);
  v4 = RedirectionKeyPath;
  if ( RedirectionKeyPath >= 0 )
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, (PHKEY)phkResult);
    if ( v5 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      v4 = v5;
    }
    else
    {
      v4 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeCompleteTime.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      phkResulta);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  return v4;
}

```

## disassembly

```asm
0x180035b08  mov     [rsp+arg_8], rbx
0x180035b0d  push    rdi
0x180035b0e  sub     rsp, 30h
0x180035b12  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180035b17  mov     qword ptr [rcx], 0
0x180035b1e  mov     rdi, rcx
0x180035b21  mov     [rsp+38h+lpSubKey], 0
0x180035b2a  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180035b2f  mov     ebx, eax
0x180035b31  test    eax, eax
0x180035b33  jns     short loc_180035B50
0x180035b35  mov     rcx, [rsp+38h]; this
0x180035b3a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OobeC"...
0x180035b41  mov     r9d, eax; char *
0x180035b44  mov     edx, 16h; void *
0x180035b49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b4e  jmp     short loc_180035B8A
0x180035b50  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180035b55  mov     r9d, 2001Fh; samDesired
0x180035b5b  xor     r8d, r8d; ulOptions
0x180035b5e  mov     qword ptr [rsp+38h+phkResult], rdi; phkResult
0x180035b63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035b6a  call    cs:__imp_RegOpenKeyExW
0x180035b71  nop     dword ptr [rax+rax+00h]
0x180035b76  test    eax, eax
0x180035b78  jz      short loc_180035B88
0x180035b7a  jle     short loc_180035B84
0x180035b7c  movzx   eax, ax
0x180035b7f  or      eax, 80070000h
0x180035b84  mov     ebx, eax
0x180035b86  jmp     short loc_180035B8A
0x180035b88  xor     ebx, ebx
0x180035b8a  lea     rcx, [rsp+38h+lpSubKey]
0x180035b8f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180035b94  mov     eax, ebx
0x180035b96  mov     rbx, [rsp+38h+arg_8]
0x180035b9b  add     rsp, 30h
0x180035b9f  pop     rdi
0x180035ba0  retn
```
