# SystemSettings::BatteryUsageHandlers::CreateValueLabelEmission

- ea: `0x180017b30`
- end: `0x180017cf5`
- name: `SystemSettings::BatteryUsageHandlers::CreateValueLabelEmission`
- size: `453`
- prototype: `__int64 __fastcall(TimeFormatUtils *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c230`

## callees

- `0x1800028d0`
- `0x180011da4`
- `0x180011fec`
- `0x180014f8c`
- `0x1800162c0`
- `0x180017210`
- `0x180017894`
- `0x180017b30`
- `0x180019b4c`
- `0x18001e360`
- `0x18001e4a0`
- `0x18001e5c8`
- `0x18001ef00`
- `0x180026490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180017bea`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180017c03`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180017bea`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180017c03`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180017bcc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180017c74`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180017bcc`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180017c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017baf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017baf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::BatteryUsageHandlers::CreateValueLabelEmission(
        TimeFormatUtils *this,
        __int64 a2,
        __int64 a3,
        HSTRING *a4)
{
  struct _SYSTEMTIME *v8; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  int HString; // ebx
  __int128 v20; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h]
  __int128 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  _BYTE v24[240]; // [rsp+60h] [rbp-A0h] BYREF
  SYSTEMTIME Time; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v26[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v27[512]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v28[512]; // [rsp+380h] [rbp+280h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v24);
  Time = 0;
  if ( !TimeFormatUtils::TimestampToLocalTime(this, (unsigned __int64)&Time, v8)
    || (int)SystemSettings::BatteryUsageHandlers::CreateTimeString(&Time) < 0 )
  {
    goto LABEL_6;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(0, 0);
  v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, StringRawBuffer);
  std::basic_ostream<unsigned short>::operator<<(v10, std::endl<unsigned short,std::char_traits<unsigned short>>);
  _o__ui64tow_s(a2, v27, 256, 10);
  _o__ui64tow_s(a3, v28, 256, 10);
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( (int)SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(0x2438u) >= 0 )
  {
    v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, v20);
    v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, v27);
    v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, "%");
    std::basic_ostream<unsigned short>::operator<<(v13, std::endl<unsigned short,std::char_traits<unsigned short>>);
  }
  v14 = std::basic_ostringstream<unsigned short>::str(v24, v26);
  v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14, v15, v16);
  HString = SystemSettings::BatteryUsageHandlers::CreateHString(v17, a4);
  std::wstring::_Tidy_deallocate(v26);
  std::vector<unsigned short>::_Tidy(&v22);
  std::vector<unsigned short>::_Tidy(&v20);
  if ( HString < 0 )
LABEL_6:
    WindowsCreateString(0, 0, a4);
  return std::basic_ostringstream<unsigned short>::`vbase destructor'(v24);
}

```

## disassembly

```asm
0x180017b30  push    rbp
0x180017b32  push    rbx
0x180017b33  push    rsi
0x180017b34  push    rdi
0x180017b35  push    r14
0x180017b37  lea     rbp, [rsp-490h]
0x180017b3f  sub     rsp, 590h
0x180017b46  mov     rax, cs:__security_cookie
0x180017b4d  xor     rax, rsp
0x180017b50  mov     [rbp+4B0h+var_30], rax
0x180017b57  mov     rdi, r9
0x180017b5a  mov     r14, r8
0x180017b5d  mov     rsi, rdx
0x180017b60  mov     rbx, rcx
0x180017b63  lea     rcx, [rsp+5B0h+var_550]
0x180017b68  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180017b6d  nop
0x180017b6e  mov     [rsp+5B0h+string], 0
0x180017b77  xorps   xmm0, xmm0
0x180017b7a  movups  xmmword ptr [rbp+4B0h+Time.wYear], xmm0
0x180017b7e  lea     rdx, [rbp+4B0h+Time]; unsigned __int64
0x180017b82  mov     rcx, rbx; this
0x180017b85  call    ?TimestampToLocalTime@TimeFormatUtils@@YAH_KPEAU_SYSTEMTIME@@@Z; TimeFormatUtils::TimestampToLocalTime(unsigned __int64,_SYSTEMTIME *)
0x180017b8a  test    eax, eax
0x180017b8c  jz      loc_180017CC0
0x180017b92  lea     rdx, [rsp+5B0h+string]
0x180017b97  lea     rcx, [rbp+4B0h+Time]; lpTime
0x180017b9b  call    SystemSettings__BatteryUsageHandlers__CreateTimeString
0x180017ba0  test    eax, eax
0x180017ba2  js      loc_180017CC0
0x180017ba8  xor     edx, edx; length
0x180017baa  mov     rcx, [rsp+5B0h+string]; string
0x180017baf  call    cs:__imp_WindowsGetStringRawBuffer
0x180017bb5  mov     rdx, rax
0x180017bb8  lea     rcx, [rsp+5B0h+var_550]
0x180017bbd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180017bc2  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180017bc9  mov     rcx, rax
0x180017bcc  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180017bd2  mov     ebx, 100h
0x180017bd7  mov     r9d, 0Ah
0x180017bdd  mov     r8d, ebx
0x180017be0  lea     rdx, [rbp+4B0h+var_430]
0x180017be7  mov     rcx, rsi
0x180017bea  call    cs:__imp__o__ui64tow_s
0x180017bf0  mov     r9d, 0Ah
0x180017bf6  mov     r8d, ebx
0x180017bf9  lea     rdx, [rbp+4B0h+var_230]
0x180017c00  mov     rcx, r14
0x180017c03  call    cs:__imp__o__ui64tow_s
0x180017c09  xorps   xmm0, xmm0
0x180017c0c  movdqu  [rsp+5B0h+var_588], xmm0
0x180017c12  mov     [rsp+5B0h+var_578], 0
0x180017c1b  movdqu  [rsp+5B0h+var_570], xmm0
0x180017c21  mov     [rsp+5B0h+var_560], 0
0x180017c2a  lea     rdx, [rsp+5B0h+var_588]
0x180017c2f  mov     ecx, 2438h; uID
0x180017c34  call    ?GetResourceString@BatteryUsageHelper@DataModel@SystemSettings@@SAJIAEAV?$vector@GV?$allocator@G@std@@@std@@@Z; SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(uint,std::vector<ushort> &)
0x180017c39  test    eax, eax
0x180017c3b  js      short loc_180017C7A
0x180017c3d  mov     rdx, qword ptr [rsp+5B0h+var_588]
0x180017c42  lea     rcx, [rsp+5B0h+var_550]
0x180017c47  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180017c4c  mov     rcx, rax
0x180017c4f  lea     rdx, [rbp+4B0h+var_430]
0x180017c56  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180017c5b  mov     rcx, rax
0x180017c5e  lea     rdx, asc_18006544C; "%"
0x180017c65  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180017c6a  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x180017c71  mov     rcx, rax
0x180017c74  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x180017c7a  lea     rdx, [rbp+4B0h+var_450]
0x180017c7e  lea     rcx, [rsp+5B0h+var_550]
0x180017c83  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x180017c88  mov     rcx, rax
0x180017c8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017c90  mov     rdx, rdi
0x180017c93  mov     rcx, rax
0x180017c96  call    SystemSettings__BatteryUsageHandlers__CreateHString
0x180017c9b  mov     ebx, eax
0x180017c9d  lea     rcx, [rbp+4B0h+var_450]
0x180017ca1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017ca6  nop
0x180017ca7  lea     rcx, [rsp+5B0h+var_570]
0x180017cac  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180017cb1  nop
0x180017cb2  lea     rcx, [rsp+5B0h+var_588]
0x180017cb7  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180017cbc  test    ebx, ebx
0x180017cbe  jns     short loc_180017CCE
0x180017cc0  mov     r8, rdi; string
0x180017cc3  xor     edx, edx; length
0x180017cc5  xor     ecx, ecx; sourceString
0x180017cc7  call    cs:__imp_WindowsCreateString
0x180017ccd  nop
0x180017cce  lea     rcx, [rsp+5B0h+var_550]
0x180017cd3  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180017cd8  mov     rcx, [rbp+4B0h+var_30]
0x180017cdf  xor     rcx, rsp; StackCookie
0x180017ce2  call    __security_check_cookie
0x180017ce7  add     rsp, 590h
0x180017cee  pop     r14
0x180017cf0  pop     rdi
0x180017cf1  pop     rsi
0x180017cf2  pop     rbx
0x180017cf3  pop     rbp
0x180017cf4  retn
```
