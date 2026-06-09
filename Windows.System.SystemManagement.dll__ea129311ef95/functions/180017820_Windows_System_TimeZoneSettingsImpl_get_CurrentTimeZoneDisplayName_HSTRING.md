# Windows::System::TimeZoneSettingsImpl::get_CurrentTimeZoneDisplayName(HSTRING__ * *)

- ea: `0x180017820`
- end: `0x180017980`
- name: `?get_CurrentTimeZoneDisplayName@TimeZoneSettingsImpl@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `352`
- prototype: `int(Windows::System::TimeZoneSettingsImpl *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002dc0`
- `0x18000399c`
- `0x180015d04`
- `0x180016080`
- `0x180017820`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017979`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001795b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001795b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800178d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800178d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017902`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017902`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x1800178a9`
- `api-ms-win-core-timezone-l1-1-0!GetDynamicTimeZoneInformation` at `0x1800178a9`

## pseudocode

```c
__int64 __fastcall Windows::System::TimeZoneSettingsImpl::get_CurrentTimeZoneDisplayName(
        Windows::System::TimeZoneSettingsImpl *this,
        HSTRING *a2)
{
  int TimeZoneDisplayName; // ebx
  signed int LastError; // eax
  LSTATUS v6; // eax
  Windows::System::TimeZoneSettingsImpl *v7; // rcx
  int v8; // eax
  void **v9; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  _TIME_DYNAMIC_ZONE_INFORMATION pTimeZoneInformation; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  memset_0(&pTimeZoneInformation, 0, sizeof(pTimeZoneInformation));
  phkResult = 0;
  v9 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable';
  if ( a2 )
  {
    Buffer[0] = 0;
    *a2 = 0;
    if ( GetDynamicTimeZoneInformation(&pTimeZoneInformation) == -1 || !GetSystemDirectoryW(Buffer, 0x104u) )
    {
      LastError = GetLastError();
      TimeZoneDisplayName = LastError;
      if ( LastError > 0 )
        TimeZoneDisplayName = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones",
             0,
             1u,
             &phkResult);
      TimeZoneDisplayName = v6;
      if ( v6 > 0 )
        TimeZoneDisplayName = (unsigned __int16)v6 | 0x80070000;
      if ( TimeZoneDisplayName >= 0 )
        TimeZoneDisplayName = Windows::System::TimeZoneSettingsImpl::GetTimeZoneDisplayName(
                                v7,
                                phkResult,
                                Buffer,
                                &pTimeZoneInformation,
                                a2);
    }
    v9 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable';
    if ( phkResult
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::InternalClose(&v9) )
    {
      v8 = GetLastError();
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      RaiseException(v8, 1u, 0, 0);
      JUMPOUT(0x18001797FLL);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)TimeZoneDisplayName;
}

```

## disassembly

```asm
0x180017820  push    rbp
0x180017822  push    rbx
0x180017823  push    rsi
0x180017824  push    r15
0x180017826  lea     rbp, [rsp-318h]
0x18001782e  sub     rsp, 418h
0x180017835  mov     rax, cs:__security_cookie
0x18001783c  xor     rax, rsp
0x18001783f  mov     [rbp+330h+var_30], rax
0x180017846  mov     rsi, rdx
0x180017849  lea     rcx, [rsp+430h+pTimeZoneInformation]; void *
0x18001784e  xor     edx, edx; Val
0x180017850  mov     r8d, 1B0h; Size
0x180017856  call    memset_0
0x18001785b  mov     [rsp+430h+var_3F8], 0
0x180017864  lea     r15, ??_7?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::`vftable'
0x18001786b  mov     [rsp+430h+var_400], r15
0x180017870  test    rsi, rsi
0x180017873  jnz     short loc_180017898
0x180017875  mov     ebx, 80004003h
0x18001787a  mov     eax, ebx
0x18001787c  mov     rcx, [rbp+330h+var_30]
0x180017883  xor     rcx, rsp; StackCookie
0x180017886  call    __security_check_cookie
0x18001788b  add     rsp, 418h
0x180017892  pop     r15
0x180017894  pop     rsi
0x180017895  pop     rbx
0x180017896  pop     rbp
0x180017897  retn
0x180017898  xor     eax, eax
0x18001789a  lea     rcx, [rsp+430h+pTimeZoneInformation]; pTimeZoneInformation
0x18001789f  mov     [rbp+330h+Buffer], ax
0x1800178a6  mov     [rsi], rax
0x1800178a9  call    cs:__imp_GetDynamicTimeZoneInformation
0x1800178af  cmp     eax, 0FFFFFFFFh
0x1800178b2  jnz     short loc_1800178CB
0x1800178b4  call    cs:__imp_GetLastError
0x1800178ba  mov     ebx, eax
0x1800178bc  test    eax, eax
0x1800178be  jle     short loc_180017938
0x1800178c0  movzx   ebx, ax
0x1800178c3  or      ebx, 80070000h
0x1800178c9  jmp     short loc_180017938
0x1800178cb  mov     edx, 104h; uSize
0x1800178d0  lea     rcx, [rbp+330h+Buffer]; lpBuffer
0x1800178d7  call    cs:__imp_GetSystemDirectoryW
0x1800178dd  test    eax, eax
0x1800178df  jz      short loc_1800178B4
0x1800178e1  lea     rax, [rsp+430h+var_3F8]
0x1800178e6  mov     r9d, 1; samDesired
0x1800178ec  xor     r8d, r8d; ulOptions
0x1800178ef  mov     [rsp+430h+phkResult], rax; phkResult
0x1800178f4  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800178fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017902  call    cs:__imp_RegOpenKeyExW
0x180017908  mov     ebx, eax
0x18001790a  test    eax, eax
0x18001790c  jle     short loc_180017917
0x18001790e  movzx   ebx, ax
0x180017911  or      ebx, 80070000h
0x180017917  test    ebx, ebx
0x180017919  js      short loc_180017938
0x18001791b  mov     rdx, [rsp+430h+var_3F8]; HKEY
0x180017920  lea     r9, [rsp+430h+pTimeZoneInformation]; struct _TIME_DYNAMIC_ZONE_INFORMATION *
0x180017925  lea     r8, [rbp+330h+Buffer]; unsigned __int16 *
0x18001792c  mov     [rsp+430h+phkResult], rsi; HSTRING *
0x180017931  call    ?GetTimeZoneDisplayName@TimeZoneSettingsImpl@System@Windows@@AEAAJPEAUHKEY__@@PEBGQEAU_TIME_DYNAMIC_ZONE_INFORMATION@@PEAPEAUHSTRING__@@@Z; Windows::System::TimeZoneSettingsImpl::GetTimeZoneDisplayName(HKEY__ *,ushort const *,_TIME_DYNAMIC_ZONE_INFORMATION * const,HSTRING__ * *)
0x180017936  mov     ebx, eax
0x180017938  cmp     [rsp+430h+var_3F8], 0
0x18001793e  mov     [rsp+430h+var_400], r15
0x180017943  jz      loc_18001787A
0x180017949  lea     rcx, [rsp+430h+var_400]
0x18001794e  call    ?InternalClose@?$HandleT@URegistryKeyTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::RegistryKeyTraits>::InternalClose(void)
0x180017953  test    al, al
0x180017955  jnz     loc_18001787A
0x18001795b  call    cs:__imp_GetLastError
0x180017961  test    eax, eax
0x180017963  jle     short loc_18001796D
0x180017965  movzx   eax, ax
0x180017968  or      eax, 80070000h
0x18001796d  xor     r9d, r9d; lpArguments
0x180017970  xor     r8d, r8d; nNumberOfArguments
0x180017973  mov     ecx, eax; dwExceptionCode
0x180017975  lea     edx, [r9+1]; dwExceptionFlags
0x180017979  call    cs:__imp_RaiseException
```
