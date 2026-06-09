# SystemSettings::BatteryUsageHandlers::CreateValueLabel2

- ea: `0x1800179dc`
- end: `0x180017b27`
- name: `SystemSettings::BatteryUsageHandlers::CreateValueLabel2`
- size: `331`
- prototype: `__int64 __fastcall(TimeFormatUtils *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ad60`
- `0x18001c230`

## callees

- `0x1800028d0`
- `0x180011da4`
- `0x180011fec`
- `0x180014f8c`
- `0x1800162c0`
- `0x180017210`
- `0x180017894`
- `0x1800179dc`
- `0x18001e360`
- `0x18001e5c8`
- `0x18001ef00`
- `0x180026490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180017a9a`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180017a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017af4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017af4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017a65`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::CreateValueLabel2(
        TimeFormatUtils *this,
        __int64 a2,
        HSTRING *a3)
{
  struct _SYSTEMTIME *v6; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  int HString; // ebx
  UINT32 length; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h]
  _BYTE v18[240]; // [rsp+30h] [rbp-D0h] BYREF
  SYSTEMTIME Time; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v20[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v21[512]; // [rsp+150h] [rbp+50h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v18);
  string = 0;
  Time = 0;
  if ( TimeFormatUtils::TimestampToLocalTime(this, (unsigned __int64)&Time, v6) != 1 )
    goto LABEL_4;
  if ( (int)SystemSettings::BatteryUsageHandlers::CreateTimeString(&Time) < 0 )
    goto LABEL_4;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, StringRawBuffer);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, "\n");
  _o__ui64tow_s(a2, v21, 256, 10);
  v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, v21);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9, "%");
  v10 = std::basic_ostringstream<unsigned short>::str(v18, v20);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10, v11, v12);
  HString = SystemSettings::BatteryUsageHandlers::CreateHString(v13, a3);
  std::wstring::_Tidy_deallocate(v20);
  if ( HString < 0 )
LABEL_4:
    WindowsCreateString(0, 0, a3);
  return std::basic_ostringstream<unsigned short>::`vbase destructor'(v18);
}

```

## disassembly

```asm
0x1800179dc  mov     [rsp-8+arg_18], rbx
0x1800179e1  push    rbp
0x1800179e2  push    rsi
0x1800179e3  push    rdi
0x1800179e4  lea     rbp, [rsp-260h]
0x1800179ec  sub     rsp, 360h
0x1800179f3  mov     rax, cs:__security_cookie
0x1800179fa  xor     rax, rsp
0x1800179fd  mov     [rbp+270h+var_20], rax
0x180017a04  mov     rdi, r8
0x180017a07  mov     rsi, rdx
0x180017a0a  mov     rbx, rcx
0x180017a0d  lea     rcx, [rsp+370h+var_340]
0x180017a12  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180017a17  nop
0x180017a18  mov     [rsp+370h+string], 0
0x180017a21  xorps   xmm0, xmm0
0x180017a24  movups  xmmword ptr [rbp+270h+Time.wYear], xmm0
0x180017a28  lea     rdx, [rbp+270h+Time]; unsigned __int64
0x180017a2c  mov     rcx, rbx; this
0x180017a2f  call    ?TimestampToLocalTime@TimeFormatUtils@@YAH_KPEAU_SYSTEMTIME@@@Z; TimeFormatUtils::TimestampToLocalTime(unsigned __int64,_SYSTEMTIME *)
0x180017a34  cmp     eax, 1
0x180017a37  jnz     loc_180017AED
0x180017a3d  lea     rdx, [rsp+370h+string]
0x180017a42  lea     rcx, [rbp+270h+Time]; lpTime
0x180017a46  call    SystemSettings__BatteryUsageHandlers__CreateTimeString
0x180017a4b  test    eax, eax
0x180017a4d  js      loc_180017AED
0x180017a53  mov     [rsp+370h+length], 0
0x180017a5b  lea     rdx, [rsp+370h+length]; length
0x180017a60  mov     rcx, [rsp+370h+string]; string
0x180017a65  call    cs:__imp_WindowsGetStringRawBuffer
0x180017a6b  mov     rdx, rax
0x180017a6e  lea     rcx, [rsp+370h+var_340]
0x180017a73  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180017a78  mov     rcx, rax
0x180017a7b  lea     rdx, asc_1800654A0; "\n"
0x180017a82  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180017a87  mov     r9d, 0Ah
0x180017a8d  mov     r8d, 100h
0x180017a93  lea     rdx, [rbp+270h+var_220]
0x180017a97  mov     rcx, rsi
0x180017a9a  call    cs:__imp__o__ui64tow_s
0x180017aa0  lea     rdx, [rbp+270h+var_220]
0x180017aa4  lea     rcx, [rsp+370h+var_340]
0x180017aa9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180017aae  mov     rcx, rax
0x180017ab1  lea     rdx, asc_18006544C; "%"
0x180017ab8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180017abd  lea     rdx, [rbp+270h+var_240]
0x180017ac1  lea     rcx, [rsp+370h+var_340]
0x180017ac6  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x180017acb  mov     rcx, rax
0x180017ace  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017ad3  mov     rdx, rdi
0x180017ad6  mov     rcx, rax
0x180017ad9  call    SystemSettings__BatteryUsageHandlers__CreateHString
0x180017ade  mov     ebx, eax
0x180017ae0  lea     rcx, [rbp+270h+var_240]
0x180017ae4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017ae9  test    ebx, ebx
0x180017aeb  jns     short loc_180017AFB
0x180017aed  mov     r8, rdi; string
0x180017af0  xor     edx, edx; length
0x180017af2  xor     ecx, ecx; sourceString
0x180017af4  call    cs:__imp_WindowsCreateString
0x180017afa  nop
0x180017afb  lea     rcx, [rsp+370h+var_340]
0x180017b00  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180017b05  mov     rcx, [rbp+270h+var_20]
0x180017b0c  xor     rcx, rsp; StackCookie
0x180017b0f  call    __security_check_cookie
0x180017b14  mov     rbx, [rsp+370h+arg_18]
0x180017b1c  add     rsp, 360h
0x180017b23  pop     rdi
0x180017b24  pop     rsi
0x180017b25  pop     rbp
0x180017b26  retn
```
