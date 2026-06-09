# SystemSettings::BatteryUsageHandlers::DataDurationSelector::get_Id(HSTRING__ * *)

- ea: `0x180027030`
- end: `0x1800270bc`
- name: `?get_Id@DataDurationSelector@BatteryUsageHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `140`
- prototype: `int(SystemSettings::BatteryUsageHandlers::DataDurationSelector *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001de40`
- `0x180021138`
- `0x180021534`
- `0x180027030`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002709e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002709e`

## string_xrefs

- `0x18002704e`: `UsageDataDurationComboBox`

## pseudocode

```c
HRESULT __fastcall SystemSettings::BatteryUsageHandlers::DataDurationSelector::get_Id(
        SystemSettings::BatteryUsageHandlers::DataDurationSelector *this,
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
               L"UsageDataDurationComboBox");
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
0x180027030  mov     r11, rsp
0x180027033  mov     [r11+8], rbx
0x180027037  mov     [r11+10h], rsi
0x18002703b  push    rdi
0x18002703c  sub     rsp, 40h
0x180027040  mov     rax, [rcx+60h]
0x180027044  xor     esi, esi
0x180027046  mov     rdi, rdx
0x180027049  test    rax, rax
0x18002704c  jnz     short loc_18002708B
0x18002704e  lea     rdx, aUsagedatadurat; "UsageDataDurationComboBox"
0x180027055  mov     [r11-28h], rsi
0x180027059  lea     rcx, [r11-28h]
0x18002705d  mov     [r11-20h], rsi
0x180027061  mov     [r11-18h], rsi
0x180027065  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002706a  mov     ebx, eax
0x18002706c  test    eax, eax
0x18002706e  js      short loc_18002707F
0x180027070  mov     rcx, [rsp+48h+var_28]; this
0x180027075  mov     rdx, rdi; unsigned __int16 *
0x180027078  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x18002707d  mov     ebx, eax
0x18002707f  lea     rcx, [rsp+48h+var_28]
0x180027084  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180027089  jmp     short loc_1800270AA
0x18002708b  mov     rcx, [rax]; sourceString
0x18002708e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180027092  inc     rdx; length
0x180027095  cmp     [rcx+rdx*2], si
0x180027099  jnz     short loc_180027092
0x18002709b  mov     r8, rdi; string
0x18002709e  call    cs:__imp_WindowsCreateString
0x1800270a4  mov     ebx, eax
0x1800270a6  test    eax, eax
0x1800270a8  js      short loc_1800270AC
0x1800270aa  mov     eax, ebx
0x1800270ac  mov     rbx, [rsp+48h+arg_0]
0x1800270b1  mov     rsi, [rsp+48h+arg_8]
0x1800270b6  add     rsp, 40h
0x1800270ba  pop     rdi
0x1800270bb  retn
```
