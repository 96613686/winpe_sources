# PhoneSettingsConfig::_InitializeValues(void)

- ea: `0x18003e300`
- end: `0x18003f137`
- name: `?_InitializeValues@PhoneSettingsConfig@@MEAAJXZ`
- size: `3639`
- prototype: `__int64 __fastcall(PhoneSettingsConfig *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800056a0`
- `0x1800091a8`
- `0x18002aa58`
- `0x18002aaec`
- `0x18002c580`
- `0x18003e300`
- `0x18004b294`
- `0x18004b4a8`
- `0x18008d9b0`

## string_xrefs

- `0x18003e46e`: `IncomingInternationalAssist`
- `0x18003f020`: `IncomingCallAnnounceEnabled`
- `0x18003e36e`: `onecoreuap\internal\net\inc\phone\PhoneSettingsConfig.h`
- `0x18003ea5d`: `onecoreuap\internal\net\inc\phone\PhoneSettingsConfig.h`
- `0x18003e355`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e3b7`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e3d2`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e426`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e441`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e4a0`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e4ba`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e504`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e55b`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e575`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e5bc`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e607`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e622`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e67c`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e690`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e6d9`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e730`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e773`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e7ca`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e811`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e82d`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e843`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e880`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e8ce`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e925`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e96b`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e987`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e9d2`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003e9ee`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003eaf1`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003eb05`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003eb4e`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ebcb`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ec16`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ec6d`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ecb0`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ed86`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003eda2`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ee1d`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ee39`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ee85`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003eea1`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003eeea`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ef06`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ef52`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003ef6e`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003efe5`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003f001`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003f04d`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003f069`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003f0b5`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003f0d1`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`

## pseudocode

```c
__int64 __fastcall PhoneSettingsConfig::_InitializeValues(PhoneSettingsConfig *this)
{
  char *v1; // rbx
  int v3; // ebx
  __int64 v4; // r9
  __int64 v6; // r9
  __int64 v7; // r9
  __int16 *v8; // rcx
  void *Block; // [rsp+30h] [rbp-38h] BYREF
  __int16 *v10; // [rsp+38h] [rbp-30h]
  __int16 v11; // [rsp+40h] [rbp-28h] BYREF
  __int64 v12; // [rsp+42h] [rbp-26h]
  int v13; // [rsp+4Ah] [rbp-1Eh]
  __int16 v14; // [rsp+4Eh] [rbp-1Ah]

  v1 = (char *)this + 152;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 152) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 349;
LABEL_3:
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\PhoneSettingsConfig.h", v4);
    return (unsigned int)v3;
  }
  *((_QWORD *)v1 + 4) = this;
  *((_QWORD *)v1 + 5) = PhoneServiceConfig::BooleanValidator;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 632) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v4 = 352;
    goto LABEL_3;
  }
  *((_QWORD *)this + 83) = this;
  *((_QWORD *)this + 84) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 172) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 696) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v4 = 358;
    goto LABEL_3;
  }
  *((_QWORD *)this + 91) = this;
  *((_QWORD *)this + 92) = PhoneSettingsConfig::DefaultRTTCallFeatureBehaviorsValidator;
  *((_DWORD *)this + 188) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 208) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v4 = 361;
    goto LABEL_3;
  }
  *((_QWORD *)this + 30) = this;
  *((_QWORD *)this + 31) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 66) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 272) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 363;
    goto LABEL_3;
  }
  *((_QWORD *)this + 38) = this;
  *((_QWORD *)this + 39) = PhoneServiceConfig::BooleanValidator;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 760) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v4 = 369;
    goto LABEL_3;
  }
  *((_QWORD *)this + 99) = this;
  *((_QWORD *)this + 100) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 204) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 328) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 371;
    goto LABEL_3;
  }
  *((_QWORD *)this + 45) = this;
  *((_QWORD *)this + 46) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 416) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v4 = 377;
    goto LABEL_3;
  }
  *((_QWORD *)this + 56) = this;
  *((_DWORD *)this + 118) = 1;
  *((_QWORD *)this + 57) = PhoneServiceConfig::BooleanValidator;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 824) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v4 = 383;
    goto LABEL_3;
  }
  *((_QWORD *)this + 107) = this;
  *((_QWORD *)this + 108) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 220) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 888) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 385;
    goto LABEL_3;
  }
  *((_QWORD *)this + 115) = this;
  *((_QWORD *)this + 116) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 992) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 387;
    goto LABEL_3;
  }
  *((_QWORD *)this + 128) = this;
  *((_QWORD *)this + 129) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 1096) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 389;
    goto LABEL_3;
  }
  *((_QWORD *)this + 141) = this;
  *((_QWORD *)this + 142) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 480) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v6 = 613;
LABEL_31:
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v6);
    v4 = 391;
    goto LABEL_3;
  }
  *((_QWORD *)this + 64) = this;
  *((_QWORD *)this + 65) = 0;
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear((char *)this + 592);
  *((_DWORD *)this + 156) = 0;
  if ( !(unsigned __int8)utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::assign(
                           (char *)this + 592,
                           (char *)this + 3392) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1378);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 677);
    v6 = 614;
    goto LABEL_31;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 1200) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 393;
    goto LABEL_3;
  }
  *((_QWORD *)this + 154) = this;
  *((_QWORD *)this + 155) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 1288) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 396;
    goto LABEL_3;
  }
  *((_QWORD *)this + 165) = this;
  *((_QWORD *)this + 166) = PhoneServiceConfig::BooleanValidator;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 1344) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v4 = 398;
    goto LABEL_3;
  }
  *((_QWORD *)this + 172) = this;
  *((_QWORD *)this + 173) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 1448) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v4 = 404;
    goto LABEL_3;
  }
  *((_QWORD *)this + 185) = this;
  *((_QWORD *)this + 186) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 376) = 1;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 1512) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v4 = 407;
    goto LABEL_3;
  }
  *((_QWORD *)this + 193) = this;
  Block = &v11;
  *((_QWORD *)this + 194) = PhoneServiceConfig::BooleanValidator;
  v10 = &v11;
  *((_DWORD *)this + 392) = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v11 = 0;
  v3 = ConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         (char *)this + 1576,
         L"PreferredCallUpgradeLineId",
         this,
         &Block);
  if ( v3 < 0 )
  {
    v7 = 411;
    goto LABEL_44;
  }
  v10 = (__int16 *)Block;
  *(_WORD *)Block = 0;
  v3 = ConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         (char *)this + 1696,
         L"PreferredVoipOutgoingLineId",
         this,
         &Block);
  if ( v3 < 0 )
  {
    v7 = 414;
    goto LABEL_44;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 1816) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 416;
    goto LABEL_44;
  }
  *((_QWORD *)this + 231) = this;
  *((_QWORD *)this + 232) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 468) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 1880) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v7 = 418;
    goto LABEL_44;
  }
  *((_QWORD *)this + 239) = this;
  *((_QWORD *)this + 240) = 0;
  v3 = ConfigValueWithDefault<unsigned long>::Initialize(
         (int)this + 1968,
         (unsigned int)L"ConferenceCallMaximumPartyCount",
         (_DWORD)this,
         0,
         0);
  if ( v3 < 0 )
  {
    v7 = 420;
    goto LABEL_44;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 2032) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v7 = 422;
    goto LABEL_44;
  }
  *((_QWORD *)this + 258) = this;
  *((_QWORD *)this + 259) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 2120) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v7 = 424;
    goto LABEL_44;
  }
  *((_QWORD *)this + 269) = this;
  *((_QWORD *)this + 270) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 2448) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v7 = 426;
    goto LABEL_44;
  }
  *((_QWORD *)this + 310) = this;
  *((_QWORD *)this + 311) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 2536) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    v7 = 428;
    goto LABEL_44;
  }
  *((_QWORD *)this + 321) = this;
  *((_QWORD *)this + 322) = 0;
  v3 = ConfigValueWithDefault<unsigned long>::Initialize(
         (int)this + 2624,
         (unsigned int)L"VideoCallingDismissButtonsTimerMilliseconds",
         (_DWORD)this,
         5000,
         0);
  if ( v3 < 0 )
  {
    v7 = 431;
    goto LABEL_44;
  }
  v3 = ConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         (char *)this + 2208,
         L"VideoCapabilityLabel",
         this,
         &Block);
  if ( v3 < 0 )
  {
    v7 = 433;
    goto LABEL_44;
  }
  v3 = ConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         (char *)this + 2328,
         L"VideoCapabilityDescription",
         this,
         &Block);
  if ( v3 < 0 )
  {
    v7 = 435;
    goto LABEL_44;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 2688) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 437;
    goto LABEL_44;
  }
  *((_QWORD *)this + 340) = this;
  *((_QWORD *)this + 341) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 686) = 0;
  v3 = ConfigValueWithDefault<unsigned long>::Initialize(
         (int)this + 2752,
         (unsigned int)L"LowVideoQualityTimeout",
         (_DWORD)this,
         0,
         0);
  if ( v3 < 0 )
  {
    v7 = 439;
    goto LABEL_44;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 2816) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 441;
    goto LABEL_44;
  }
  *((_QWORD *)this + 356) = this;
  *((_QWORD *)this + 357) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 718) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 2880) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 447;
    goto LABEL_44;
  }
  *((_QWORD *)this + 364) = this;
  *((_QWORD *)this + 365) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 734) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 2944) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 449;
    goto LABEL_44;
  }
  *((_QWORD *)this + 372) = this;
  *((_QWORD *)this + 373) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 750) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 3008) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 451;
    goto LABEL_44;
  }
  *((_QWORD *)this + 380) = this;
  *((_QWORD *)this + 381) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 766) = 0;
  v3 = ConfigValueWithDefault<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::Initialize(
         (char *)this + 3072,
         L"PreferredRecordingApplication",
         this,
         &Block);
  if ( v3 < 0 )
  {
    v7 = 453;
    goto LABEL_44;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 3192) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 455;
    goto LABEL_44;
  }
  *((_QWORD *)this + 403) = this;
  *((_QWORD *)this + 404) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 812) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 3256) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 457;
    goto LABEL_44;
  }
  *((_QWORD *)this + 411) = this;
  *((_QWORD *)this + 412) = PhoneServiceConfig::BooleanValidator;
  *((_DWORD *)this + 828) = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign((char *)this + 3320) )
  {
    v3 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 119);
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 605);
    v7 = 460;
LABEL_44:
    Log_HREvent_7((unsigned int)v3, 1, "onecoreuap\\internal\\net\\inc\\phone\\PhoneSettingsConfig.h", v7);
    if ( Block != &v11 )
      operator delete(Block);
    return (unsigned int)v3;
  }
  v8 = (__int16 *)Block;
  *((_QWORD *)this + 420) = PhoneSettingsConfig::DefaultRTTCallFeatureBehaviorsValidator;
  *((_QWORD *)this + 419) = this;
  *((_DWORD *)this + 844) = 0;
  if ( v8 != &v11 )
    operator delete(v8);
  return 0;
}

```

## disassembly

```asm
0x18003e300  push    rbp
0x18003e302  push    rbx
0x18003e303  push    rsi
0x18003e304  push    rdi
0x18003e305  push    r12
0x18003e307  push    r13
0x18003e309  push    r14
0x18003e30b  push    r15
0x18003e30d  mov     rbp, rsp
0x18003e310  sub     rsp, 68h
0x18003e314  mov     rax, cs:__security_cookie
0x18003e31b  xor     rax, rsp
0x18003e31e  mov     [rbp+var_18], rax
0x18003e322  lea     rbx, [rcx+98h]
0x18003e329  mov     rdi, rcx
0x18003e32c  mov     esi, 13h
0x18003e331  lea     rdx, aAssisteddialse; "AssistedDialSetting"
0x18003e338  mov     r8d, esi
0x18003e33b  mov     rcx, rbx
0x18003e33e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e343  xor     r15d, r15d
0x18003e346  test    al, al
0x18003e348  jnz     short loc_18003E383
0x18003e34a  mov     ebx, 8007000Eh
0x18003e34f  lea     r9d, [rsi+64h]
0x18003e353  mov     ecx, ebx
0x18003e355  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e35c  xor     edx, edx
0x18003e35e  call    Log_HREvent_7
0x18003e363  mov     r9d, 15Dh
0x18003e369  mov     edx, 1
0x18003e36e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e375  mov     ecx, ebx
0x18003e377  call    Log_HREvent_7
0x18003e37c  mov     eax, ebx
0x18003e37e  jmp     loc_18003F11A
0x18003e383  mov     [rbx+20h], rdi
0x18003e387  lea     r12, ?BooleanValidator@PhoneServiceConfig@@SAHAEBH@Z; PhoneServiceConfig::BooleanValidator(int const &)
0x18003e38e  mov     [rbx+28h], r12
0x18003e392  lea     rdx, aAutomaticcalla; "AutomaticCallAudioRoutingBasedOnProximi"...
0x18003e399  lea     rbx, [rdi+278h]
0x18003e3a0  mov     r8d, 2Fh ; '/'
0x18003e3a6  mov     rcx, rbx
0x18003e3a9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e3ae  test    al, al
0x18003e3b0  jnz     short loc_18003E3F5
0x18003e3b2  mov     ebx, 8007000Eh
0x18003e3b7  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e3be  mov     ecx, ebx
0x18003e3c0  mov     r9d, 77h ; 'w'
0x18003e3c6  xor     edx, edx
0x18003e3c8  call    Log_HREvent_7
0x18003e3cd  mov     esi, 1
0x18003e3d2  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e3d9  mov     edx, esi
0x18003e3db  mov     r9d, 25Dh
0x18003e3e1  mov     ecx, ebx
0x18003e3e3  call    Log_HREvent_7
0x18003e3e8  mov     r9d, 160h
0x18003e3ee  mov     edx, esi
0x18003e3f0  jmp     loc_18003E36E
0x18003e3f5  mov     [rbx+20h], rdi
0x18003e3f9  lea     rdx, aDefaultcallaud; "DefaultCallAudioRoutingBehavior"
0x18003e400  mov     [rbx+28h], r12
0x18003e404  mov     r8d, 1Fh
0x18003e40a  mov     [rbx+38h], r15d
0x18003e40e  lea     rbx, [rdi+2B8h]
0x18003e415  mov     rcx, rbx
0x18003e418  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e41d  test    al, al
0x18003e41f  jnz     short loc_18003E45F
0x18003e421  mov     ebx, 8007000Eh
0x18003e426  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e42d  mov     ecx, ebx
0x18003e42f  mov     r9d, 77h ; 'w'
0x18003e435  xor     edx, edx
0x18003e437  call    Log_HREvent_7
0x18003e43c  mov     esi, 1
0x18003e441  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e448  mov     edx, esi
0x18003e44a  mov     r9d, 25Dh
0x18003e450  mov     ecx, ebx
0x18003e452  call    Log_HREvent_7
0x18003e457  mov     r9d, 166h
0x18003e45d  jmp     short loc_18003E3EE
0x18003e45f  lea     rax, ?DefaultRTTCallFeatureBehaviorsValidator@PhoneSettingsConfig@@SAHAEBK@Z; PhoneSettingsConfig::DefaultRTTCallFeatureBehaviorsValidator(ulong const &)
0x18003e466  mov     [rbx+20h], rdi
0x18003e46a  mov     [rbx+28h], rax
0x18003e46e  lea     rdx, aIncomingintern; "IncomingInternationalAssist"
0x18003e475  mov     [rbx+38h], r15d
0x18003e479  mov     r13d, 1Bh
0x18003e47f  lea     rbx, [rdi+0D0h]
0x18003e486  mov     r8d, r13d
0x18003e489  mov     rcx, rbx
0x18003e48c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e491  test    al, al
0x18003e493  jnz     short loc_18003E4D3
0x18003e495  mov     ebx, 8007000Eh
0x18003e49a  lea     r9d, [r13+5Ch]
0x18003e49e  mov     ecx, ebx
0x18003e4a0  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e4a7  xor     edx, edx
0x18003e4a9  call    Log_HREvent_7
0x18003e4ae  lea     esi, [r13-1Ah]
0x18003e4b2  mov     r9d, 25Dh
0x18003e4b8  mov     edx, esi
0x18003e4ba  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e4c1  mov     ecx, ebx
0x18003e4c3  call    Log_HREvent_7
0x18003e4c8  mov     r9d, 169h
0x18003e4ce  jmp     loc_18003E3EE
0x18003e4d3  mov     [rbx+20h], rdi
0x18003e4d7  lea     rdx, aContinuousdtmf; "ContinuousDTMFEnabled"
0x18003e4de  mov     [rbx+28h], r12
0x18003e4e2  mov     r8d, 15h
0x18003e4e8  mov     [rbx+38h], r15d
0x18003e4ec  lea     rbx, [rdi+110h]
0x18003e4f3  mov     rcx, rbx
0x18003e4f6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e4fb  test    al, al
0x18003e4fd  jnz     short loc_18003E525
0x18003e4ff  mov     ebx, 8007000Eh
0x18003e504  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e50b  mov     ecx, ebx
0x18003e50d  mov     r9d, 77h ; 'w'
0x18003e513  xor     edx, edx
0x18003e515  call    Log_HREvent_7
0x18003e51a  mov     r9d, 16Bh
0x18003e520  jmp     loc_18003E369
0x18003e525  mov     [rbx+20h], rdi
0x18003e529  lea     rdx, aHidecallforwar; "HideCallForwarding"
0x18003e530  mov     [rbx+28h], r12
0x18003e534  mov     r14d, 12h
0x18003e53a  lea     rbx, [rdi+2F8h]
0x18003e541  mov     r8d, r14d
0x18003e544  mov     rcx, rbx
0x18003e547  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e54c  test    al, al
0x18003e54e  jnz     short loc_18003E58E
0x18003e550  mov     ebx, 8007000Eh
0x18003e555  lea     r9d, [r14+65h]
0x18003e559  mov     ecx, ebx
0x18003e55b  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e562  xor     edx, edx
0x18003e564  call    Log_HREvent_7
0x18003e569  lea     esi, [r14-11h]
0x18003e56d  mov     r9d, 25Dh
0x18003e573  mov     edx, esi
0x18003e575  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e57c  mov     ecx, ebx
0x18003e57e  call    Log_HREvent_7
0x18003e583  mov     r9d, 171h
0x18003e589  jmp     loc_18003E3EE
0x18003e58e  mov     [rbx+20h], rdi
0x18003e592  lea     rdx, aPhonelinefacto_2; "PhoneLineFactories"
0x18003e599  mov     [rbx+28h], r12
0x18003e59d  mov     r8, r14
0x18003e5a0  mov     [rbx+38h], r15d
0x18003e5a4  lea     rbx, [rdi+148h]
0x18003e5ab  mov     rcx, rbx
0x18003e5ae  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e5b3  test    al, al
0x18003e5b5  jnz     short loc_18003E5DD
0x18003e5b7  mov     ebx, 8007000Eh
0x18003e5bc  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e5c3  mov     ecx, ebx
0x18003e5c5  mov     r9d, 77h ; 'w'
0x18003e5cb  xor     edx, edx
0x18003e5cd  call    Log_HREvent_7
0x18003e5d2  mov     r9d, 173h
0x18003e5d8  jmp     loc_18003E369
0x18003e5dd  mov     [rbx+20h], rdi
0x18003e5e1  lea     rdx, aShowassisteddi; "ShowAssistedDialing"
0x18003e5e8  mov     [rbx+28h], r15
0x18003e5ec  mov     r8, rsi
0x18003e5ef  lea     rbx, [rdi+1A0h]
0x18003e5f6  mov     rcx, rbx
0x18003e5f9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e5fe  test    al, al
0x18003e600  jnz     short loc_18003E643
0x18003e602  mov     ebx, 8007000Eh
0x18003e607  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e60e  mov     ecx, ebx
0x18003e610  mov     r9d, 77h ; 'w'
0x18003e616  xor     edx, edx
0x18003e618  call    Log_HREvent_7
0x18003e61d  mov     esi, 1
0x18003e622  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e629  mov     edx, esi
0x18003e62b  mov     r9d, 25Dh
0x18003e631  mov     ecx, ebx
0x18003e633  call    Log_HREvent_7
0x18003e638  mov     r9d, 179h
0x18003e63e  jmp     loc_18003E3EE
0x18003e643  mov     esi, 1
0x18003e648  mov     [rbx+20h], rdi
0x18003e64c  mov     [rbx+38h], esi
0x18003e64f  lea     rdx, aShowlongtones; "ShowLongTones"
0x18003e656  mov     [rbx+28h], r12
0x18003e65a  lea     rbx, [rdi+338h]
0x18003e661  mov     rcx, rbx
0x18003e664  lea     r8d, [rsi+0Ch]
0x18003e668  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e66d  test    al, al
0x18003e66f  jnz     short loc_18003E6AB
0x18003e671  mov     ebx, 8007000Eh
0x18003e676  lea     r9d, [rsi+76h]
0x18003e67a  mov     ecx, ebx
0x18003e67c  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e683  xor     edx, edx
0x18003e685  call    Log_HREvent_7
0x18003e68a  mov     r9d, 25Dh
0x18003e690  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e697  mov     edx, esi
0x18003e699  mov     ecx, ebx
0x18003e69b  call    Log_HREvent_7
0x18003e6a0  mov     r9d, 17Fh
0x18003e6a6  jmp     loc_18003E3EE
0x18003e6ab  mov     [rbx+20h], rdi
0x18003e6af  lea     rdx, aPartnerimmedia; "PartnerImmediateDialStrings"
0x18003e6b6  mov     [rbx+28h], r12
0x18003e6ba  mov     r8, r13
0x18003e6bd  mov     [rbx+38h], r15d
0x18003e6c1  lea     rbx, [rdi+378h]
0x18003e6c8  mov     rcx, rbx
0x18003e6cb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e6d0  test    al, al
0x18003e6d2  jnz     short loc_18003E6FA
0x18003e6d4  mov     ebx, 8007000Eh
0x18003e6d9  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e6e0  mov     ecx, ebx
0x18003e6e2  mov     r9d, 77h ; 'w'
0x18003e6e8  xor     edx, edx
0x18003e6ea  call    Log_HREvent_7
0x18003e6ef  mov     r9d, 181h
0x18003e6f5  jmp     loc_18003E3EE
0x18003e6fa  mov     [rbx+20h], rdi
0x18003e6fe  lea     rdx, aPartnernonimme; "PartnerNonImmediateDialStrings"
0x18003e705  mov     [rbx+28h], r15
0x18003e709  mov     r14d, 1Eh
0x18003e70f  lea     rbx, [rdi+3E0h]
0x18003e716  mov     r8d, r14d
0x18003e719  mov     rcx, rbx
0x18003e71c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e721  test    al, al
0x18003e723  jnz     short loc_18003E749
0x18003e725  mov     ebx, 8007000Eh
0x18003e72a  lea     r9d, [r14+59h]
0x18003e72e  mov     ecx, ebx
0x18003e730  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e737  xor     edx, edx
0x18003e739  call    Log_HREvent_7
0x18003e73e  mov     r9d, 183h
0x18003e744  jmp     loc_18003E3EE
0x18003e749  mov     [rbx+20h], rdi
0x18003e74d  lea     rdx, aHomenetworkspe; "HomeNetworkSpecificDialStrings"
0x18003e754  mov     [rbx+28h], r15
0x18003e758  mov     r8, r14
0x18003e75b  lea     rbx, [rdi+448h]
0x18003e762  mov     rcx, rbx
0x18003e765  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e76a  test    al, al
0x18003e76c  jnz     short loc_18003E794
0x18003e76e  mov     ebx, 8007000Eh
0x18003e773  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e77a  mov     ecx, ebx
0x18003e77c  mov     r9d, 77h ; 'w'
0x18003e782  xor     edx, edx
0x18003e784  call    Log_HREvent_7
0x18003e789  mov     r9d, 185h
0x18003e78f  jmp     loc_18003E3EE
0x18003e794  lea     r14, [rdi+1E0h]
0x18003e79b  mov     [rbx+20h], rdi
0x18003e79f  mov     r13d, 0Fh
0x18003e7a5  mov     [rbx+28h], r15
0x18003e7a9  mov     r8d, r13d
0x18003e7ac  lea     rdx, aNolognumberlis; "NoLogNumberList"
0x18003e7b3  mov     rcx, r14
0x18003e7b6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18003e7bb  test    al, al
0x18003e7bd  jnz     short loc_18003E7E0
0x18003e7bf  mov     ebx, 8007000Eh
0x18003e7c4  lea     r9d, [r13+68h]
0x18003e7c8  mov     ecx, ebx
0x18003e7ca  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18003e7d1  xor     edx, edx
0x18003e7d3  call    Log_HREvent_7
0x18003e7d8  mov     r9d, 265h
0x18003e7de  jmp     short loc_18003E843
0x18003e7e0  lea     rcx, [r14+70h]
0x18003e7e4  mov     [r14+20h], rdi
0x18003e7e8  mov     [r14+28h], r15
0x18003e7ec  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x18003e7f1  lea     rdx, [rdi+0D40h]
0x18003e7f8  mov     [r14+90h], r15d
0x18003e7ff  lea     rcx, [r14+70h]
0x18003e803  call    ?assign@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV12@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::assign(utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> const &)
0x18003e808  test    al, al
0x18003e80a  jnz     short loc_18003E85E
0x18003e80c  mov     ebx, 8007000Eh
  ... truncated ...
```
