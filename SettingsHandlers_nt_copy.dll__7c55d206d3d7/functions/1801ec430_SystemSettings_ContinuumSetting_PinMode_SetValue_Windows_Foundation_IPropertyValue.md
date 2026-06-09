# SystemSettings::ContinuumSetting::PinMode::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x1801ec430`
- end: `0x1801ec658`
- name: `?SetValue@PinMode@ContinuumSetting@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(SystemSettings::ContinuumSetting::PinMode *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001bc0`
- `0x18000280c`
- `0x18004e918`
- `0x180099d58`
- `0x1801eb3f4`
- `0x1801ec430`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ec4e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ec4e8`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801ec594`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801ec5b7`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801ec594`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1801ec5b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec47a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec47a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ec636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ec4be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ec4be`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::ContinuumSetting::PinMode::SetValue(
        SystemSettings::ContinuumSetting::PinMode *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  LSTATUS inited; // ebx
  __int64 (__fastcall *v5)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  unsigned int i; // ebp
  const WCHAR *StringRawBuffer; // rax
  LSTATUS v8; // eax
  unsigned int v9; // r9d
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  int v12; // r9d
  HSTRING string[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+18h] BYREF
  int v16; // [rsp+78h] [rbp+20h] BYREF

  inited = SystemSettings::ContinuumSetting::PinMode::InitPossibleValues(this);
  if ( inited >= 0 && *((_BYTE *)this + 312) )
  {
    string[0] = 0;
    v5 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
    WindowsDeleteString(0);
    string[0] = 0;
    inited = v5(a2, string);
    if ( inited >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 3 )
        {
          inited = -2147467259;
          goto LABEL_23;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
        if ( CompareStringOrdinal(*((LPCWCH *)this + 3 * i + 30), -1, StringRawBuffer, -1, 0) == 2 )
          break;
      }
      if ( !i )
      {
        inited = SHRegSetDWORD(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\MiracastReceiver",
                   L"Primary Authorization Method",
                   1u);
        if ( inited < 0 )
          goto LABEL_23;
        v8 = SHRegSetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\MiracastReceiver",
               L"Secondary Authorization Method",
               2u);
        goto LABEL_16;
      }
      if ( i == 1 )
        v9 = 2;
      else
        v9 = 3;
      inited = SHRegSetDWORD(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\MiracastReceiver",
                 L"Primary Authorization Method",
                 v9);
      if ( inited >= 0 )
      {
        v8 = RegDeleteKeyValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\MiracastReceiver",
               L"Secondary Authorization Method");
LABEL_16:
        inited = v8;
        if ( v8 >= 0 )
        {
          inited = RegDeleteKeyValueW(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\MiracastReceiver",
                     L"Tertiary Authorization Method");
          if ( inited >= 0 )
          {
            v10 = SettingsHandlersLogging::Provider();
            if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11, v10) )
            {
              v15 = i;
              v16 = *((_DWORD *)this + 80);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v12,
                (unsigned int)&unk_180353495,
                0,
                v12,
                (__int64)&v16,
                (__int64)&v15);
            }
            *((_DWORD *)this + 80) = i;
          }
        }
      }
    }
LABEL_23:
    WindowsDeleteString(string[0]);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1801ec430  mov     [rsp+arg_0], rbx
0x1801ec435  mov     [rsp+arg_8], rbp
0x1801ec43a  push    rsi
0x1801ec43b  push    rdi
0x1801ec43c  push    r14
0x1801ec43e  sub     rsp, 40h
0x1801ec442  mov     rdi, rdx
0x1801ec445  mov     r14, rcx
0x1801ec448  call    ?InitPossibleValues@PinMode@ContinuumSetting@SystemSettings@@AEAAJXZ; SystemSettings::ContinuumSetting::PinMode::InitPossibleValues(void)
0x1801ec44d  mov     ebx, eax
0x1801ec44f  test    eax, eax
0x1801ec451  js      loc_1801EC642
0x1801ec457  cmp     byte ptr [r14+138h], 0
0x1801ec45f  jz      loc_1801EC642
0x1801ec465  mov     [rsp+58h+string], 0
0x1801ec46e  mov     rax, [rdi]
0x1801ec471  mov     rbx, [rax+98h]
0x1801ec478  xor     ecx, ecx; string
0x1801ec47a  call    cs:__imp_WindowsDeleteString
0x1801ec481  nop     dword ptr [rax+rax+00h]
0x1801ec486  mov     [rsp+58h+string], 0
0x1801ec48f  lea     rdx, [rsp+58h+string]
0x1801ec494  mov     rcx, rdi
0x1801ec497  mov     rax, rbx
0x1801ec49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec49f  mov     ebx, eax
0x1801ec4a1  test    eax, eax
0x1801ec4a3  js      loc_1801EC631
0x1801ec4a9  xor     ebp, ebp
0x1801ec4ab  or      ebx, 0FFFFFFFFh
0x1801ec4ae  cmp     ebp, 3
0x1801ec4b1  jnb     loc_1801EC62C
0x1801ec4b7  xor     edx, edx; length
0x1801ec4b9  mov     rcx, [rsp+58h+string]; string
0x1801ec4be  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ec4c5  nop     dword ptr [rax+rax+00h]
0x1801ec4ca  mov     ecx, ebp
0x1801ec4cc  add     rcx, 0Ah
0x1801ec4d0  lea     rcx, [rcx+rcx*2]
0x1801ec4d4  mov     [rsp+58h+bIgnoreCase], 0; bIgnoreCase
0x1801ec4dc  mov     r9d, ebx; cchCount2
0x1801ec4df  mov     r8, rax; lpString2
0x1801ec4e2  mov     edx, ebx; cchCount1
0x1801ec4e4  mov     rcx, [r14+rcx*8]; lpString1
0x1801ec4e8  call    cs:__imp_CompareStringOrdinal
0x1801ec4ef  nop     dword ptr [rax+rax+00h]
0x1801ec4f4  cmp     eax, 2
0x1801ec4f7  jz      short loc_1801EC4FD
0x1801ec4f9  inc     ebp
0x1801ec4fb  jmp     short loc_1801EC4AE
0x1801ec4fd  test    ebp, ebp
0x1801ec4ff  jnz     short loc_1801EC547
0x1801ec501  lea     r9d, [rbp+1]; unsigned int
0x1801ec505  lea     r8, aPrimaryAuthori; "Primary Authorization Method"
0x1801ec50c  lea     rdi, aSoftwareMicros_37; "Software\\Microsoft\\MiracastReceiver"
0x1801ec513  mov     rdx, rdi; unsigned __int16 *
0x1801ec516  mov     rsi, 0FFFFFFFF80000002h
0x1801ec51d  mov     rcx, rsi; HKEY
0x1801ec520  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801ec525  mov     ebx, eax
0x1801ec527  test    eax, eax
0x1801ec529  js      loc_1801EC631
0x1801ec52f  lea     r9d, [rbp+2]; unsigned int
0x1801ec533  lea     r8, aSecondaryAutho; "Secondary Authorization Method"
0x1801ec53a  mov     rdx, rdi; unsigned __int16 *
0x1801ec53d  mov     rcx, rsi; HKEY
0x1801ec540  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801ec545  jmp     short loc_1801EC5A0
0x1801ec547  cmp     ebp, 1
0x1801ec54a  jnz     short loc_1801EC552
0x1801ec54c  lea     r9d, [rbp+1]
0x1801ec550  jmp     short loc_1801EC55D
0x1801ec552  xor     ebx, ebx
0x1801ec554  cmp     ebp, 2
0x1801ec557  jnz     short loc_1801EC5C9
0x1801ec559  lea     r9d, [rbx+3]; unsigned int
0x1801ec55d  lea     rdi, aSoftwareMicros_37; "Software\\Microsoft\\MiracastReceiver"
0x1801ec564  mov     rsi, 0FFFFFFFF80000002h
0x1801ec56b  lea     r8, aPrimaryAuthori; "Primary Authorization Method"
0x1801ec572  mov     rdx, rdi; unsigned __int16 *
0x1801ec575  mov     rcx, rsi; HKEY
0x1801ec578  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1801ec57d  test    eax, eax
0x1801ec57f  mov     ebx, eax
0x1801ec581  js      loc_1801EC631
0x1801ec587  lea     r8, aSecondaryAutho; "Secondary Authorization Method"
0x1801ec58e  mov     rdx, rdi; lpSubKey
0x1801ec591  mov     rcx, rsi; hKey
0x1801ec594  call    cs:__imp_RegDeleteKeyValueW
0x1801ec59b  nop     dword ptr [rax+rax+00h]
0x1801ec5a0  mov     ebx, eax
0x1801ec5a2  test    eax, eax
0x1801ec5a4  js      loc_1801EC631
0x1801ec5aa  lea     r8, aTertiaryAuthor; "Tertiary Authorization Method"
0x1801ec5b1  mov     rdx, rdi; lpSubKey
0x1801ec5b4  mov     rcx, rsi; hKey
0x1801ec5b7  call    cs:__imp_RegDeleteKeyValueW
0x1801ec5be  nop     dword ptr [rax+rax+00h]
0x1801ec5c3  mov     ebx, eax
0x1801ec5c5  test    eax, eax
0x1801ec5c7  js      short loc_1801EC631
0x1801ec5c9  call    ?Provider@SettingsHandlersLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersLogging::Provider(void)
0x1801ec5ce  mov     r9, rax
0x1801ec5d1  mov     ecx, [rax]
0x1801ec5d3  cmp     ecx, 5
0x1801ec5d6  jbe     short loc_1801EC623
0x1801ec5d8  mov     rdx, 400000000000h
0x1801ec5e2  mov     rcx, rax
0x1801ec5e5  call    _tlgKeywordOn
0x1801ec5ea  test    al, al
0x1801ec5ec  jz      short loc_1801EC623
0x1801ec5ee  mov     [rsp+58h+arg_10], ebp
0x1801ec5f2  mov     ecx, [r14+140h]
0x1801ec5f9  mov     [rsp+58h+arg_18], ecx
0x1801ec5fd  lea     rax, [rsp+58h+arg_10]
0x1801ec602  mov     [rsp+58h+var_30], rax
0x1801ec607  lea     rax, [rsp+58h+arg_18]
0x1801ec60c  mov     qword ptr [rsp+58h+bIgnoreCase], rax
0x1801ec611  xor     r8d, r8d
0x1801ec614  lea     rdx, unk_180353495
0x1801ec61b  mov     rcx, r9
0x1801ec61e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801ec623  mov     [r14+140h], ebp
0x1801ec62a  jmp     short loc_1801EC631
0x1801ec62c  mov     ebx, 80004005h
0x1801ec631  mov     rcx, [rsp+58h+string]; string
0x1801ec636  call    cs:__imp_WindowsDeleteString
0x1801ec63d  nop     dword ptr [rax+rax+00h]
0x1801ec642  mov     eax, ebx
0x1801ec644  mov     rbx, [rsp+58h+arg_0]
0x1801ec649  mov     rbp, [rsp+58h+arg_8]
0x1801ec64e  add     rsp, 40h
0x1801ec652  pop     r14
0x1801ec654  pop     rdi
0x1801ec655  pop     rsi
0x1801ec656  retn
```
