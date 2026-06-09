# GetValueIfExists(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180022ab8`
- end: `0x180022c59`
- name: `?GetValueIfExists@@YA?AV?$optional@K@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@00@Z`
- size: `417`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002297c`

## callees

- `0x18000a584`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cfc0`
- `0x180013dcc`
- `0x180022ab8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022b14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022b6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022b14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022b6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022be7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180022be7`

## string_xrefs

- `0x180022b25`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`
- `0x180022b97`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`
- `0x180022c05`: `shellcommon\shell\sharedpc\accountmanager\lib\util\stateseparationutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetValueIfExists(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  const WCHAR *v10; // rax
  int v11; // eax
  const WCHAR *v12; // rax
  int ValueW; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  int phkResulta; // [rsp+20h] [rbp-30h]
  int phkResultb; // [rsp+20h] [rbp-30h]
  HKEY hkey; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int pvData; // [rsp+70h] [rbp+20h] BYREF
  __int16 v22; // [rsp+75h] [rbp+25h]
  char v23; // [rsp+77h] [rbp+27h]
  DWORD pcbData; // [rsp+78h] [rbp+28h] BYREF

  *(_BYTE *)(a1 + 4) = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hKey);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x3B,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
      (const char *)v9,
      phkResult);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v11 = RegOpenKeyExW(hKey, v10, 0, 1u, &hkey);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  if ( v11 != -2147024894 )
  {
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
        (const char *)(unsigned int)v11,
        phkResulta);
    pvData = 0;
    pcbData = 4;
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    ValueW = RegGetValueW(hkey, 0, v12, 0x10u, 0, &pvData, &pcbData);
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    if ( ValueW != -2147024894 )
    {
      if ( ValueW < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x48,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\stateseparationutils.cpp",
          (const char *)(unsigned int)ValueW,
          phkResultb);
      *(_DWORD *)a1 = pvData;
      *(_BYTE *)(a1 + 4) = 1;
      *(_WORD *)(a1 + 5) = v22;
      *(_BYTE *)(a1 + 7) = v23;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a1;
}

```

## disassembly

```asm
0x180022ab8  mov     [rsp-18h+arg_10], rbx
0x180022abd  mov     [rsp-18h+arg_18], rsi
0x180022ac2  push    rbp
0x180022ac3  push    rdi
0x180022ac4  push    r14
0x180022ac6  mov     rbp, rsp
0x180022ac9  sub     rsp, 50h
0x180022acd  mov     r14, r9
0x180022ad0  mov     rsi, r8
0x180022ad3  mov     rbx, rdx
0x180022ad6  mov     rdi, rcx
0x180022ad9  mov     byte ptr [rcx+4], 0
0x180022add  mov     [rbp+hKey], 0
0x180022ae5  xor     edx, edx
0x180022ae7  lea     rcx, [rbp+hKey]
0x180022aeb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180022af0  mov     rcx, rbx
0x180022af3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022af8  mov     rdx, rax; lpSubKey
0x180022afb  lea     rax, [rbp+hKey]
0x180022aff  mov     [rsp+50h+phkResult], rax; unsigned int
0x180022b04  mov     r9d, 20019h; samDesired
0x180022b0a  xor     r8d, r8d; ulOptions
0x180022b0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022b14  call    cs:__imp_RegOpenKeyExW
0x180022b1a  mov     rcx, [rbp+18h]; this
0x180022b1e  test    eax, eax
0x180022b20  jz      short loc_180022B37
0x180022b22  mov     r9d, eax; char *
0x180022b25  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x180022b2c  mov     edx, 3Bh ; ';'; void *
0x180022b31  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180022b37  mov     [rbp+hkey], 0
0x180022b3f  xor     edx, edx
0x180022b41  lea     rcx, [rbp+hkey]
0x180022b45  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180022b4a  mov     rcx, rsi
0x180022b4d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022b52  mov     rdx, rax; lpSubKey
0x180022b55  lea     rax, [rbp+hkey]
0x180022b59  mov     [rsp+50h+phkResult], rax; int
0x180022b5e  mov     r9d, 1; samDesired
0x180022b64  xor     r8d, r8d; ulOptions
0x180022b67  mov     rcx, [rbp+hKey]; hKey
0x180022b6b  call    cs:__imp_RegOpenKeyExW
0x180022b71  mov     esi, 80070000h
0x180022b76  test    eax, eax
0x180022b78  jle     short loc_180022B7F
0x180022b7a  movzx   eax, ax
0x180022b7d  or      eax, esi
0x180022b7f  mov     ebx, 80070002h
0x180022b84  cmp     eax, ebx
0x180022b86  jz      loc_180022C2E
0x180022b8c  mov     rcx, [rbp+18h]; this
0x180022b90  test    eax, eax
0x180022b92  jns     short loc_180022BA9
0x180022b94  mov     r9d, eax; char *
0x180022b97  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x180022b9e  mov     edx, 41h ; 'A'; void *
0x180022ba3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022ba9  mov     [rbp+arg_0], 0
0x180022bb0  mov     [rbp+arg_8], 4
0x180022bb7  mov     rcx, r14
0x180022bba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022bbf  mov     r8, rax; lpValue
0x180022bc2  lea     rax, [rbp+arg_8]
0x180022bc6  mov     [rsp+50h+pcbData], rax; pcbData
0x180022bcb  lea     rax, [rbp+arg_0]
0x180022bcf  mov     [rsp+50h+pvData], rax; pvData
0x180022bd4  mov     [rsp+50h+phkResult], 0; int
0x180022bdd  xor     edx, edx; lpSubKey
0x180022bdf  lea     r9d, [rdx+10h]; dwFlags
0x180022be3  mov     rcx, [rbp+hkey]; hkey
0x180022be7  call    cs:__imp_RegGetValueW
0x180022bed  test    eax, eax
0x180022bef  jle     short loc_180022BF6
0x180022bf1  movzx   eax, ax
0x180022bf4  or      eax, esi
0x180022bf6  cmp     eax, ebx
0x180022bf8  jz      short loc_180022C2E
0x180022bfa  mov     rcx, [rbp+18h]; this
0x180022bfe  test    eax, eax
0x180022c00  jns     short loc_180022C17
0x180022c02  mov     r9d, eax; char *
0x180022c05  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\sharedpc\\accountma"...
0x180022c0c  mov     edx, 48h ; 'H'; void *
0x180022c11  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022c17  mov     eax, [rbp+arg_0]
0x180022c1a  mov     [rdi], eax
0x180022c1c  mov     byte ptr [rdi+4], 1
0x180022c20  movzx   eax, [rbp+arg_5]
0x180022c24  mov     [rdi+5], ax
0x180022c28  mov     al, [rbp+arg_7]
0x180022c2b  mov     [rdi+7], al
0x180022c2e  lea     rcx, [rbp+hkey]
0x180022c32  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022c37  nop
0x180022c38  lea     rcx, [rbp+hKey]
0x180022c3c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022c41  mov     rax, rdi
0x180022c44  lea     r11, [rsp+50h+var_s0]
0x180022c49  mov     rbx, [r11+30h]
0x180022c4d  mov     rsi, [r11+38h]
0x180022c51  mov     rsp, r11
0x180022c54  pop     r14
0x180022c56  pop     rdi
0x180022c57  pop     rbp
0x180022c58  retn
```
