# SystemSettings::BatteryUsageHandlers::CreateAutomationLabel2

- ea: `0x180016d1c`
- end: `0x18001706b`
- name: `SystemSettings::BatteryUsageHandlers::CreateAutomationLabel2`
- size: `847`
- prototype: `__int64 __usercall@<rax>(SystemSettings::BatteryUsageHandlers *this@<rcx>, unsigned __int64, unsigned __int64, HSTRING *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ad60`
- `0x18001b610`

## callees

- `0x1800028d0`
- `0x180011da4`
- `0x180011fec`
- `0x180014f8c`
- `0x1800162c0`
- `0x180016d1c`
- `0x180017074`
- `0x180017210`
- `0x180017894`
- `0x180018494`
- `0x180019b4c`
- `0x18001e360`
- `0x18001e4a0`
- `0x18001e5c8`
- `0x18001ef00`
- `0x180026490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180016e52`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180016e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001702f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001702f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016f53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016fd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016f53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016fd5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::BatteryUsageHandlers::CreateAutomationLabel2(
        SystemSettings::BatteryUsageHandlers *this,
        unsigned __int64 a2,
        int a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        HSTRING *a7)
{
  HSTRING *v11; // r9
  PCWSTR StringRawBuffer; // rax
  struct _SYSTEMTIME *v13; // r8
  PCWSTR v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // edi
  int v19; // edi
  UINT v20; // ecx
  __int64 v21; // rax
  PCWSTR v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  PCWSTR v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  PCWSTR v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  UINT32 length; // [rsp+20h] [rbp-E0h] BYREF
  UINT32 v36; // [rsp+24h] [rbp-DCh] BYREF
  UINT32 v37; // [rsp+28h] [rbp-D8h] BYREF
  UINT32 v38; // [rsp+2Ch] [rbp-D4h] BYREF
  UINT32 v39; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v41; // [rsp+40h] [rbp-C0h]
  HSTRING v42; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v43; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v44; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h]
  _BYTE v47[240]; // [rsp+80h] [rbp-80h] BYREF
  SYSTEMTIME Time; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v49[512]; // [rsp+190h] [rbp+90h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v47);
  v45 = 0;
  v46 = 0;
  string = 0;
  if ( (int)SystemSettings::BatteryUsageHandlers::CreateDateString(
              this,
              (unsigned __int64)L"day month",
              (unsigned __int16 *)&string,
              v11) < 0 )
    goto LABEL_17;
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, StringRawBuffer);
  if ( a2 <= 0x64 )
  {
    Time = 0;
    v41 = 0;
    if ( !TimeFormatUtils::TimestampToLocalTime(this, (unsigned __int64)&Time, v13)
      || (int)SystemSettings::BatteryUsageHandlers::CreateTimeString(&Time) < 0 )
    {
      goto LABEL_17;
    }
    v36 = 0;
    v14 = WindowsGetStringRawBuffer(v41, &v36);
    v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, ", ");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, v14);
    _o__ui64tow_s(a2, v49, 256, 10);
    v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, ", ");
    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16, v49);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, "%");
    v18 = a3 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 1 )
          goto LABEL_13;
        v20 = 9257;
      }
      else
      {
        v20 = 9258;
      }
    }
    else
    {
      v20 = 9256;
    }
    if ( (int)SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(v20) < 0 )
    {
LABEL_17:
      WindowsCreateString(0, 0, a7);
      goto LABEL_18;
    }
    v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, ", ");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, v45);
  }
LABEL_13:
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, ". ");
  v42 = 0;
  v43 = 0;
  v44 = 0;
  if ( SystemSettings::DataModel::BatteryUsageHelper::FormatTimeRemaining(a4, &v42) < 0 )
    goto LABEL_17;
  if ( SystemSettings::DataModel::BatteryUsageHelper::FormatTimeRemaining(a5, &v43) < 0 )
    goto LABEL_17;
  if ( SystemSettings::DataModel::BatteryUsageHelper::FormatTimeRemaining(a6, &v44) < 0 )
    goto LABEL_17;
  v37 = 0;
  v22 = WindowsGetStringRawBuffer(v42, &v37);
  v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, "Screen on: ");
  v24 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23, v22);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, ", ");
  v38 = 0;
  v25 = WindowsGetStringRawBuffer(v43, &v38);
  v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, "Screen off: ");
  v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v26, v25);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, ", ");
  v39 = 0;
  v28 = WindowsGetStringRawBuffer(v44, &v39);
  v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, "Sleep: ");
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, v28);
  v30 = std::basic_ostringstream<unsigned short>::str(v47, &Time);
  v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30, v31, v32);
  LODWORD(v28) = SystemSettings::BatteryUsageHandlers::CreateHString(v33, a7);
  std::wstring::_Tidy_deallocate(&Time);
  if ( (int)v28 < 0 )
    goto LABEL_17;
LABEL_18:
  std::vector<unsigned short>::_Tidy(&v45);
  return std::basic_ostringstream<unsigned short>::`vbase destructor'(v47);
}

```

## disassembly

```asm
0x180016d1c  push    rbp
0x180016d1e  push    rbx
0x180016d1f  push    rsi
0x180016d20  push    rdi
0x180016d21  push    r13
0x180016d23  push    r14
0x180016d25  push    r15
0x180016d27  lea     rbp, [rsp-2A0h]
0x180016d2f  sub     rsp, 3A0h
0x180016d36  mov     rax, cs:__security_cookie
0x180016d3d  xor     rax, rsp
0x180016d40  mov     [rbp+2D0h+var_40], rax
0x180016d47  mov     r15, r9
0x180016d4a  mov     edi, r8d
0x180016d4d  mov     r14, rdx
0x180016d50  mov     rbx, rcx
0x180016d53  mov     rsi, [rbp+2D0h+arg_30]
0x180016d5a  lea     rcx, [rbp+2D0h+var_350]
0x180016d5e  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180016d63  nop
0x180016d64  xorps   xmm0, xmm0
0x180016d67  movdqu  [rsp+3D0h+var_370], xmm0
0x180016d6d  mov     [rsp+3D0h+var_360], 0
0x180016d76  mov     [rsp+3D0h+string], 0
0x180016d7f  lea     r8, [rsp+3D0h+string]; unsigned __int16 *
0x180016d84  lea     rdx, aDayMonth; "day month"
0x180016d8b  mov     rcx, rbx; this
0x180016d8e  call    ?CreateDateString@BatteryUsageHandlers@SystemSettings@@YAJ_KPEAGPEAPEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::CreateDateString(unsigned __int64,ushort *,HSTRING__ * *)
0x180016d93  test    eax, eax
0x180016d95  js      loc_180017028
0x180016d9b  mov     [rsp+3D0h+length], 0
0x180016da3  lea     rdx, [rsp+3D0h+length]; length
0x180016da8  mov     rcx, [rsp+3D0h+string]; string
0x180016dad  call    cs:__imp_WindowsGetStringRawBuffer
0x180016db3  mov     rdx, rax
0x180016db6  lea     rcx, [rbp+2D0h+var_350]
0x180016dba  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180016dbf  lea     r13, asc_18006546C; ", "
0x180016dc6  cmp     r14, 64h ; 'd'
0x180016dca  ja      loc_180016ECF
0x180016dd0  xorps   xmm0, xmm0
0x180016dd3  movups  xmmword ptr [rbp+2D0h+Time.wYear], xmm0
0x180016dd7  mov     [rsp+3D0h+var_390], 0
0x180016de0  lea     rdx, [rbp+2D0h+Time]; unsigned __int64
0x180016de4  mov     rcx, rbx; this
0x180016de7  call    ?TimestampToLocalTime@TimeFormatUtils@@YAH_KPEAU_SYSTEMTIME@@@Z; TimeFormatUtils::TimestampToLocalTime(unsigned __int64,_SYSTEMTIME *)
0x180016dec  test    eax, eax
0x180016dee  jz      loc_180017028
0x180016df4  lea     rdx, [rsp+3D0h+var_390]
0x180016df9  lea     rcx, [rbp+2D0h+Time]; lpTime
0x180016dfd  call    SystemSettings__BatteryUsageHandlers__CreateTimeString
0x180016e02  test    eax, eax
0x180016e04  js      loc_180017028
0x180016e0a  mov     [rsp+3D0h+var_3AC], 0
0x180016e12  lea     rdx, [rsp+3D0h+var_3AC]; length
0x180016e17  mov     rcx, [rsp+3D0h+var_390]; string
0x180016e1c  call    cs:__imp_WindowsGetStringRawBuffer
0x180016e22  mov     rbx, rax
0x180016e25  mov     rdx, r13
0x180016e28  lea     rcx, [rbp+2D0h+var_350]
0x180016e2c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016e31  mov     rcx, rax
0x180016e34  mov     rdx, rbx
0x180016e37  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180016e3c  mov     r9d, 0Ah
0x180016e42  mov     r8d, 100h
0x180016e48  lea     rdx, [rbp+2D0h+var_240]
0x180016e4f  mov     rcx, r14
0x180016e52  call    cs:__imp__o__ui64tow_s
0x180016e58  mov     rdx, r13
0x180016e5b  lea     rcx, [rbp+2D0h+var_350]
0x180016e5f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016e64  mov     rcx, rax
0x180016e67  lea     rdx, [rbp+2D0h+var_240]
0x180016e6e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180016e73  mov     rcx, rax
0x180016e76  lea     rdx, asc_18006544C; "%"
0x180016e7d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016e82  sub     edi, 1
0x180016e85  jz      short loc_180016E9F
0x180016e87  sub     edi, 1
0x180016e8a  jz      short loc_180016E98
0x180016e8c  cmp     edi, 1
0x180016e8f  jnz     short loc_180016ECF
0x180016e91  mov     ecx, 2429h
0x180016e96  jmp     short loc_180016EA4
0x180016e98  mov     ecx, 242Ah
0x180016e9d  jmp     short loc_180016EA4
0x180016e9f  mov     ecx, 2428h; uID
0x180016ea4  lea     rdx, [rsp+3D0h+var_370]
0x180016ea9  call    ?GetResourceString@BatteryUsageHelper@DataModel@SystemSettings@@SAJIAEAV?$vector@GV?$allocator@G@std@@@std@@@Z; SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(uint,std::vector<ushort> &)
0x180016eae  test    eax, eax
0x180016eb0  js      loc_180017028
0x180016eb6  mov     rdx, r13
0x180016eb9  lea     rcx, [rbp+2D0h+var_350]
0x180016ebd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016ec2  mov     rdx, qword ptr [rsp+3D0h+var_370]
0x180016ec7  mov     rcx, rax
0x180016eca  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180016ecf  lea     rdx, asc_180065470; ". "
0x180016ed6  lea     rcx, [rbp+2D0h+var_350]
0x180016eda  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016edf  mov     [rsp+3D0h+var_388], 0
0x180016ee8  mov     [rsp+3D0h+var_380], 0
0x180016ef1  mov     [rsp+3D0h+var_378], 0
0x180016efa  lea     rdx, [rsp+3D0h+var_388]; HSTRING *
0x180016eff  mov     rcx, r15; unsigned __int64
0x180016f02  call    ?FormatTimeRemaining@BatteryUsageHelper@DataModel@SystemSettings@@SAJ_KPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::BatteryUsageHelper::FormatTimeRemaining(unsigned __int64,HSTRING__ * *)
0x180016f07  test    eax, eax
0x180016f09  js      loc_180017028
0x180016f0f  lea     rdx, [rsp+3D0h+var_380]; HSTRING *
0x180016f14  mov     rcx, [rbp+2D0h+arg_20]; unsigned __int64
0x180016f1b  call    ?FormatTimeRemaining@BatteryUsageHelper@DataModel@SystemSettings@@SAJ_KPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::BatteryUsageHelper::FormatTimeRemaining(unsigned __int64,HSTRING__ * *)
0x180016f20  test    eax, eax
0x180016f22  js      loc_180017028
0x180016f28  lea     rdx, [rsp+3D0h+var_378]; HSTRING *
0x180016f2d  mov     rcx, [rbp+2D0h+arg_28]; unsigned __int64
0x180016f34  call    ?FormatTimeRemaining@BatteryUsageHelper@DataModel@SystemSettings@@SAJ_KPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::BatteryUsageHelper::FormatTimeRemaining(unsigned __int64,HSTRING__ * *)
0x180016f39  test    eax, eax
0x180016f3b  js      loc_180017028
0x180016f41  mov     [rsp+3D0h+var_3A8], 0
0x180016f49  lea     rdx, [rsp+3D0h+var_3A8]; length
0x180016f4e  mov     rcx, [rsp+3D0h+var_388]; string
0x180016f53  call    cs:__imp_WindowsGetStringRawBuffer
0x180016f59  mov     rbx, rax
0x180016f5c  lea     rdx, aScreenOn; "Screen on: "
0x180016f63  lea     rcx, [rbp+2D0h+var_350]
0x180016f67  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016f6c  mov     rcx, rax
0x180016f6f  mov     rdx, rbx
0x180016f72  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180016f77  mov     rcx, rax
0x180016f7a  mov     rdx, r13
0x180016f7d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016f82  mov     [rsp+3D0h+var_3A4], 0
0x180016f8a  lea     rdx, [rsp+3D0h+var_3A4]; length
0x180016f8f  mov     rcx, [rsp+3D0h+var_380]; string
0x180016f94  call    cs:__imp_WindowsGetStringRawBuffer
0x180016f9a  mov     rbx, rax
0x180016f9d  lea     rdx, aScreenOff; "Screen off: "
0x180016fa4  lea     rcx, [rbp+2D0h+var_350]
0x180016fa8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016fad  mov     rcx, rax
0x180016fb0  mov     rdx, rbx
0x180016fb3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180016fb8  mov     rcx, rax
0x180016fbb  mov     rdx, r13
0x180016fbe  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016fc3  mov     [rsp+3D0h+var_3A0], 0
0x180016fcb  lea     rdx, [rsp+3D0h+var_3A0]; length
0x180016fd0  mov     rcx, [rsp+3D0h+var_378]; string
0x180016fd5  call    cs:__imp_WindowsGetStringRawBuffer
0x180016fdb  mov     rbx, rax
0x180016fde  lea     rdx, aSleep; "Sleep: "
0x180016fe5  lea     rcx, [rbp+2D0h+var_350]
0x180016fe9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180016fee  mov     rcx, rax
0x180016ff1  mov     rdx, rbx
0x180016ff4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180016ff9  lea     rdx, [rbp+2D0h+Time]
0x180016ffd  lea     rcx, [rbp+2D0h+var_350]
0x180017001  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x180017006  mov     rcx, rax
0x180017009  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001700e  mov     rdx, rsi
0x180017011  mov     rcx, rax
0x180017014  call    SystemSettings__BatteryUsageHandlers__CreateHString
0x180017019  mov     ebx, eax
0x18001701b  lea     rcx, [rbp+2D0h+Time]
0x18001701f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017024  test    ebx, ebx
0x180017026  jns     short loc_180017036
0x180017028  mov     r8, rsi; string
0x18001702b  xor     edx, edx; length
0x18001702d  xor     ecx, ecx; sourceString
0x18001702f  call    cs:__imp_WindowsCreateString
0x180017035  nop
0x180017036  lea     rcx, [rsp+3D0h+var_370]
0x18001703b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180017040  nop
0x180017041  lea     rcx, [rbp+2D0h+var_350]
0x180017045  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18001704a  mov     rcx, [rbp+2D0h+var_40]
0x180017051  xor     rcx, rsp; StackCookie
0x180017054  call    __security_check_cookie
0x180017059  add     rsp, 3A0h
0x180017060  pop     r15
0x180017062  pop     r14
0x180017064  pop     r13
0x180017066  pop     rdi
0x180017067  pop     rsi
0x180017068  pop     rbx
0x180017069  pop     rbp
0x18001706a  retn
```
