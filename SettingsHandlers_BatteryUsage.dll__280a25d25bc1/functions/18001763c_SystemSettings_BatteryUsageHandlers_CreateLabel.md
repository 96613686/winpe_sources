# SystemSettings::BatteryUsageHandlers::CreateLabel

- ea: `0x18001763c`
- end: `0x180017776`
- name: `SystemSettings::BatteryUsageHandlers::CreateLabel`
- size: `314`
- prototype: `__int64 __usercall@<rax>(SystemSettings::BatteryUsageHandlers *this@<rcx>, unsigned __int64@<rdx>, HSTRING *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18001b250`
- `0x18001b9a0`

## callees

- `0x1800028d0`
- `0x180011da4`
- `0x180011fec`
- `0x180014f8c`
- `0x1800162c0`
- `0x180017074`
- `0x180017210`
- `0x18001763c`
- `0x18001e360`
- `0x18001e5c8`
- `0x18001ef00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800176ec`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800176ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017746`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800176bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800176bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::CreateLabel(
        SystemSettings::BatteryUsageHandlers *this,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        HSTRING *a5)
{
  HSTRING *v9; // r9
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  int HString; // ebx
  UINT32 length; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v21[240]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v23[512]; // [rsp+140h] [rbp+40h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v21);
  if ( a2 )
  {
    string = 0;
    if ( (int)SystemSettings::BatteryUsageHandlers::CreateDateString(this, a2, (unsigned __int16 *)&string, v9) < 0 )
    {
LABEL_5:
      WindowsCreateString(0, 0, a5);
      return std::basic_ostringstream<unsigned short>::`vbase destructor'(v21);
    }
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, StringRawBuffer);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, a4);
  }
  _o__ui64tow_s(a3, v23, 256, 10);
  v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, v23);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, "%");
  v13 = std::basic_ostringstream<unsigned short>::str(v21, v22);
  v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13, v14, v15);
  HString = SystemSettings::BatteryUsageHandlers::CreateHString(v16, a5);
  std::wstring::_Tidy_deallocate(v22);
  if ( HString < 0 )
    goto LABEL_5;
  return std::basic_ostringstream<unsigned short>::`vbase destructor'(v21);
}

```

## disassembly

```asm
0x18001763c  push    rbp
0x18001763e  push    rbx
0x18001763f  push    rsi
0x180017640  push    rdi
0x180017641  push    r14
0x180017643  push    r15
0x180017645  lea     rbp, [rsp-258h]
0x18001764d  sub     rsp, 358h
0x180017654  mov     rax, cs:__security_cookie
0x18001765b  xor     rax, rsp
0x18001765e  mov     [rbp+280h+var_40], rax
0x180017665  mov     r14, r9
0x180017668  mov     r15, r8
0x18001766b  mov     rbx, rdx
0x18001766e  mov     rsi, rcx
0x180017671  mov     rdi, [rbp+280h+arg_20]
0x180017678  lea     rcx, [rsp+380h+var_350]
0x18001767d  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180017682  nop
0x180017683  test    rbx, rbx
0x180017686  jz      short loc_1800176D9
0x180017688  mov     [rsp+380h+string], 0
0x180017691  lea     r8, [rsp+380h+string]; unsigned __int16 *
0x180017696  mov     rdx, rbx; unsigned __int64
0x180017699  mov     rcx, rsi; this
0x18001769c  call    ?CreateDateString@BatteryUsageHandlers@SystemSettings@@YAJ_KPEAGPEAPEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::CreateDateString(unsigned __int64,ushort *,HSTRING__ * *)
0x1800176a1  test    eax, eax
0x1800176a3  js      loc_18001773F
0x1800176a9  mov     [rsp+380h+length], 0
0x1800176b1  lea     rdx, [rsp+380h+length]; length
0x1800176b6  mov     rcx, [rsp+380h+string]; string
0x1800176bb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800176c1  mov     rdx, rax
0x1800176c4  lea     rcx, [rsp+380h+var_350]
0x1800176c9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800176ce  mov     rcx, rax
0x1800176d1  mov     rdx, r14
0x1800176d4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800176d9  mov     r9d, 0Ah
0x1800176df  mov     r8d, 100h
0x1800176e5  lea     rdx, [rbp+280h+var_240]
0x1800176e9  mov     rcx, r15
0x1800176ec  call    cs:__imp__o__ui64tow_s
0x1800176f2  lea     rdx, [rbp+280h+var_240]
0x1800176f6  lea     rcx, [rsp+380h+var_350]
0x1800176fb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180017700  mov     rcx, rax
0x180017703  lea     rdx, asc_18006544C; "%"
0x18001770a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x18001770f  lea     rdx, [rbp+280h+var_260]
0x180017713  lea     rcx, [rsp+380h+var_350]
0x180017718  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x18001771d  mov     rcx, rax
0x180017720  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017725  mov     rdx, rdi
0x180017728  mov     rcx, rax
0x18001772b  call    SystemSettings__BatteryUsageHandlers__CreateHString
0x180017730  mov     ebx, eax
0x180017732  lea     rcx, [rbp+280h+var_260]
0x180017736  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001773b  test    ebx, ebx
0x18001773d  jns     short loc_18001774D
0x18001773f  mov     r8, rdi; string
0x180017742  xor     edx, edx; length
0x180017744  xor     ecx, ecx; sourceString
0x180017746  call    cs:__imp_WindowsCreateString
0x18001774c  nop
0x18001774d  lea     rcx, [rsp+380h+var_350]
0x180017752  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180017757  mov     rcx, [rbp+280h+var_40]
0x18001775e  xor     rcx, rsp; StackCookie
0x180017761  call    __security_check_cookie
0x180017766  add     rsp, 358h
0x18001776d  pop     r15
0x18001776f  pop     r14
0x180017771  pop     rdi
0x180017772  pop     rsi
0x180017773  pop     rbx
0x180017774  pop     rbp
0x180017775  retn
```
