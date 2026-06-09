# SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector::get_Id(HSTRING__ * *)

- ea: `0x180037c40`
- end: `0x180037ccc`
- name: `?get_Id@EmissionMonitorModeSelector@BatteryUsageHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `140`
- prototype: `int(SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001de40`
- `0x180021138`
- `0x180021534`
- `0x180037c40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180037cae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180037cae`

## string_xrefs

- `0x180037c5e`: `ModeSelectorComboBox`

## pseudocode

```c
HRESULT __fastcall SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector::get_Id(
        SystemSettings::BatteryUsageHandlers::EmissionMonitorModeSelector *this,
        HSTRING *a2)
{
  const WCHAR **v2; // rax
  int String; // ebx
  HSTRING *v5; // r8
  const WCHAR *v6; // rcx
  __int64 v7; // rdx
  HRESULT result; // eax
  SystemSettings::DataModel *v9[5]; // [rsp+20h] [rbp-28h] BYREF

  v2 = (const WCHAR **)*((_QWORD *)this + 12);
  if ( !v2 )
  {
    memset(v9, 0, 24);
    String = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
               v9,
               L"ModeSelectorComboBox");
    if ( String >= 0 )
      String = SystemSettings::DataModel::WindowsCreateString(v9[0], (const unsigned __int16 *)a2, v5);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v9);
    return String;
  }
  v6 = *v2;
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  result = WindowsCreateString(v6, v7, a2);
  String = result;
  if ( result >= 0 )
    return String;
  return result;
}

```

## disassembly

```asm
0x180037c40  mov     r11, rsp
0x180037c43  mov     [r11+8], rbx
0x180037c47  mov     [r11+10h], rsi
0x180037c4b  push    rdi
0x180037c4c  sub     rsp, 40h
0x180037c50  mov     rax, [rcx+60h]
0x180037c54  xor     esi, esi
0x180037c56  mov     rdi, rdx
0x180037c59  test    rax, rax
0x180037c5c  jnz     short loc_180037C9B
0x180037c5e  lea     rdx, aModeselectorco; "ModeSelectorComboBox"
0x180037c65  mov     [r11-28h], rsi
0x180037c69  lea     rcx, [r11-28h]
0x180037c6d  mov     [r11-20h], rsi
0x180037c71  mov     [r11-18h], rsi
0x180037c75  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180037c7a  mov     ebx, eax
0x180037c7c  test    eax, eax
0x180037c7e  js      short loc_180037C8F
0x180037c80  mov     rcx, [rsp+48h+var_28]; this
0x180037c85  mov     rdx, rdi; unsigned __int16 *
0x180037c88  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x180037c8d  mov     ebx, eax
0x180037c8f  lea     rcx, [rsp+48h+var_28]
0x180037c94  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180037c99  jmp     short loc_180037CBA
0x180037c9b  mov     rcx, [rax]; sourceString
0x180037c9e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180037ca2  inc     rdx; length
0x180037ca5  cmp     [rcx+rdx*2], si
0x180037ca9  jnz     short loc_180037CA2
0x180037cab  mov     r8, rdi; string
0x180037cae  call    cs:__imp_WindowsCreateString
0x180037cb4  mov     ebx, eax
0x180037cb6  test    eax, eax
0x180037cb8  js      short loc_180037CBC
0x180037cba  mov     eax, ebx
0x180037cbc  mov     rbx, [rsp+48h+arg_0]
0x180037cc1  mov     rsi, [rsp+48h+arg_8]
0x180037cc6  add     rsp, 40h
0x180037cca  pop     rdi
0x180037ccb  retn
```
