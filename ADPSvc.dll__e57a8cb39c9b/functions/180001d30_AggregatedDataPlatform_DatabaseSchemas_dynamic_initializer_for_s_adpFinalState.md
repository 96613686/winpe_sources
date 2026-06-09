# AggregatedDataPlatform::DatabaseSchemas::_dynamic_initializer_for__s_adpFinalState__

- ea: `0x180001d30`
- end: `0x180001e46`
- name: `AggregatedDataPlatform::DatabaseSchemas::_dynamic_initializer_for__s_adpFinalState__`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002250`
- `0x1800026d0`
- `0x180030354`

## string_xrefs

- `0x180001db1`: `LastUpdatedTimestamp`

## pseudocode

```c
int AggregatedDataPlatform::DatabaseSchemas::_dynamic_initializer_for__s_adpFinalState__()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-89h] BYREF
  _QWORD v2[24]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v3; // [rsp+F0h] [rbp+47h] BYREF

  v2[17] = 10;
  v2[1] = 4;
  v2[2] = "TEXT";
  v2[6] = "TEXT";
  v2[0] = "Kind";
  v2[3] = 4;
  v2[4] = "Data";
  v2[8] = "HourOfDay";
  v2[12] = "DayOfWeek";
  v2[16] = "UsageCount";
  v2[20] = "LastUpdatedTimestamp";
  v2[22] = "DATETIME";
  v2[5] = 4;
  v2[7] = 4;
  v1[0] = v2;
  v2[9] = 9;
  v2[11] = 7;
  v2[13] = 9;
  v2[15] = 7;
  v2[19] = 7;
  v1[1] = &v3;
  v2[10] = "INTEGER";
  v2[14] = "INTEGER";
  v2[18] = "INTEGER";
  v2[21] = 20;
  v2[23] = 8;
  std::vector<std::pair<std::string_view,std::string_view>>::vector<std::pair<std::string_view,std::string_view>>(
    qword_18010E6F8,
    v1);
  return atexit(AggregatedDataPlatform::DatabaseSchemas::_dynamic_atexit_destructor_for__s_adpFinalState__);
}

```

## disassembly

```asm
0x180001d30  push    rbp
0x180001d32  lea     rbp, [rsp-57h]
0x180001d37  sub     rsp, 100h
0x180001d3e  mov     rax, cs:__security_cookie
0x180001d45  xor     rax, rsp
0x180001d48  mov     [rbp+57h+var_10], rax
0x180001d4c  mov     edx, 4
0x180001d51  mov     [rbp+57h+var_48], 0Ah
0x180001d59  lea     rcx, aText; "TEXT"
0x180001d60  mov     [rbp+57h+var_C8], rdx
0x180001d64  lea     r8, aInteger_0; "INTEGER"
0x180001d6b  mov     [rbp+57h+var_C0], rcx
0x180001d6f  mov     [rbp+57h+var_A0], rcx
0x180001d73  lea     rax, aKind; "Kind"
0x180001d7a  mov     [rbp+57h+var_D0], rax
0x180001d7e  lea     ecx, [rdx+5]
0x180001d81  mov     [rbp+57h+var_B8], rdx
0x180001d85  lea     rax, aData; "Data"
0x180001d8c  mov     [rbp+57h+var_B0], rax
0x180001d90  lea     rax, aHourofday; "HourOfDay"
0x180001d97  mov     [rbp+57h+var_90], rax
0x180001d9b  lea     rax, aDayofweek; "DayOfWeek"
0x180001da2  mov     [rbp+57h+var_70], rax
0x180001da6  lea     rax, aUsagecount; "UsageCount"
0x180001dad  mov     [rbp+57h+var_50], rax
0x180001db1  lea     rax, aLastupdatedtim; "LastUpdatedTimestamp"
0x180001db8  mov     [rbp+57h+var_30], rax
0x180001dbc  lea     rax, aDatetime; "DATETIME"
0x180001dc3  mov     [rbp+57h+var_20], rax
0x180001dc7  lea     rax, [rbp+57h+var_D0]
0x180001dcb  mov     [rbp+57h+var_A8], rdx
0x180001dcf  mov     [rbp+57h+var_98], rdx
0x180001dd3  lea     edx, [rcx-2]
0x180001dd6  mov     [rsp+100h+var_E0], rax
0x180001ddb  lea     rax, [rbp+57h+var_10]
0x180001ddf  mov     [rbp+57h+var_88], rcx
0x180001de3  mov     [rbp+57h+var_78], rdx
0x180001de7  mov     [rbp+57h+var_68], rcx
0x180001deb  lea     rcx, qword_18010E6F8
0x180001df2  mov     [rbp+57h+var_58], rdx
0x180001df6  mov     [rbp+57h+var_38], rdx
0x180001dfa  lea     rdx, [rsp+100h+var_E0]
0x180001dff  mov     [rsp+100h+var_D8], rax
0x180001e04  mov     [rbp+57h+var_80], r8
0x180001e08  mov     [rbp+57h+var_60], r8
0x180001e0c  mov     [rbp+57h+var_40], r8
0x180001e10  mov     [rbp+57h+var_28], 14h
0x180001e18  mov     [rbp+57h+var_18], 8
0x180001e20  call    ??0?$vector@U?$pair@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V12@@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V12@@std@@@1@AEBV?$allocator@U?$pair@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V12@@std@@@1@@Z; std::vector<std::pair<std::string_view,std::string_view>>::vector<std::pair<std::string_view,std::string_view>>(std::initializer_list<std::pair<std::string_view,std::string_view>>,std::allocator<std::pair<std::string_view,std::string_view>> const &)
0x180001e25  lea     rcx, AggregatedDataPlatform__DatabaseSchemas___dynamic_atexit_destructor_for__s_adpFinalState__; void (__cdecl *)()
0x180001e2c  call    atexit
0x180001e31  mov     rcx, [rbp+57h+var_10]
0x180001e35  xor     rcx, rsp; StackCookie
0x180001e38  call    __security_check_cookie
0x180001e3d  add     rsp, 100h
0x180001e44  pop     rbp
0x180001e45  retn
```
