# OuEnumerateSubKeys(void *,utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &)

- ea: `0x180083fe0`
- end: `0x18008439e`
- name: `?OuEnumerateSubKeys@@YAJPEAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@@Z`
- size: `958`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x180081a38`
- `0x180081ffc`
- `0x180082e0c`
- `0x180083190`

## callees

- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x18007ca6c`
- `0x18007d794`
- `0x18007da70`
- `0x18007de48`
- `0x18007df88`
- `0x18007e020`
- `0x18007e288`
- `0x180083fe0`
- `0x180084d28`
- `0x180085134`

## string_xrefs

- `0x18008401c`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800840bb`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180084138`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800842a9`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800842db`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180084312`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180084352`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800842cb`: `SubKeyVector.emplace_back(utl::move(SubKeyName))`

## pseudocode

```c
__int64 __fastcall OuEnumerateSubKeys(__int64 a1, __int64 *a2)
{
  int v3; // r13d
  __int64 v5; // rdi
  int v6; // eax
  __int64 v7; // r8
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // r14d
  unsigned int v11; // ebx
  int v12; // r15d
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rax
  _QWORD *v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v21; // [rsp+64h] [rbp-9Ch] BYREF
  _QWORD v22[4]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v23[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v24[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v25[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v26[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v27[4]; // [rsp+108h] [rbp+8h] BYREF
  int v28; // [rsp+128h] [rbp+28h] BYREF
  __m128i si128; // [rsp+130h] [rbp+30h] BYREF
  __int64 v30; // [rsp+140h] [rbp+40h]
  const char *v31; // [rsp+148h] [rbp+48h] BYREF
  const char *v32; // [rsp+150h] [rbp+50h]
  _QWORD v33[2]; // [rsp+158h] [rbp+58h] BYREF

  v28 = 0;
  v3 = a1;
  if ( !a1 )
  {
    v33[0] = 100;
    v31 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v32 = "OuEnumerateSubKeys";
    v33[1] = "Not-null check failed: ParentHandle";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v28,
             &v31);
  }
  v5 = -1;
  v21 = 0;
  v20 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v30 = -1;
  v6 = ORQueryInfoKey(a1, 0, 0, (unsigned int)&v21, (__int64)&v20, 0, 0, 0, 0, 0, 0);
  v7 = (unsigned int)v6;
  if ( v6 )
  {
    v22[2] = 118;
    v22[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v22[1] = "OuEnumerateSubKeys";
    v22[3] = "ORQueryInfoKey( ParentHandle, nullptr, nullptr, &LocalSubKeyCount, &SubKeyMaxLengthChars, nullptr, nullptr,"
             " nullptr, nullptr, nullptr, nullptr)";
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v8 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
           &v28,
           v22,
           v7);
    goto LABEL_12;
  }
  v9 = v21;
  v10 = v20 + 1;
  if ( !v21 )
  {
LABEL_14:
    v12 = 0;
    v13 = si128.m128i_i64[1];
    if ( v21 )
    {
      while ( 1 )
      {
        v31 = (const char *)v33;
        v20 = v10;
        v32 = (const char *)v33;
        LOWORD(v33[0]) = 0;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                                 &v31,
                                 v10) )
        {
          v27[2] = 129;
          v27[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
          v18 = v27;
          v27[1] = "OuEnumerateSubKeys";
          v27[3] = "SubKeyName.resize(SubKeyLengthChars)";
          goto LABEL_30;
        }
        v14 = OREnumKey(v3, v12, (_DWORD)v31, (unsigned int)&v20, 0, 0, 0);
        v15 = (unsigned int)v14;
        if ( v14 )
          break;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                                 &v31,
                                 v20) )
        {
          v25[2] = 142;
          v25[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
          v18 = v25;
          v25[1] = "OuEnumerateSubKeys";
          v25[3] = "SubKeyName.resize(SubKeyLengthChars)";
          goto LABEL_30;
        }
        if ( v13 == v5 )
        {
          if ( !(unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(&si128) )
          {
            v24[2] = 146;
            v24[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
            v18 = v24;
            v24[1] = "OuEnumerateSubKeys";
            v24[3] = "SubKeyVector.emplace_back(utl::move(SubKeyName))";
LABEL_30:
            v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                    &v28,
                    v18,
                    3221225495LL);
            goto LABEL_31;
          }
          v5 = v30;
          v13 = si128.m128i_i64[1];
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          v13,
          &v31);
        v13 += 32;
        si128.m128i_i64[1] = v13;
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v31);
        if ( ++v12 >= v21 )
          goto LABEL_22;
      }
      v26[2] = 139;
      v26[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
      v26[1] = "OuEnumerateSubKeys";
      v26[3] = "OREnumKey( ParentHandle, Index, SubKeyName.data(), &SubKeyLengthChars, nullptr, nullptr, nullptr)";
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      v19 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
              &v28,
              v26,
              v15);
LABEL_31:
      v11 = v19;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(&v31);
    }
    else
    {
LABEL_22:
      v16 = *a2;
      *a2 = si128.m128i_i64[0];
      si128.m128i_i64[1] = a2[1];
      v17 = a2[2];
      a2[1] = v13;
      v11 = 0;
      v30 = v17;
      si128.m128i_i64[0] = v16;
      a2[2] = v5;
    }
    goto LABEL_23;
  }
  if ( v21 <= 8uLL )
    v9 = 8;
  if ( (unsigned __int8)utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_SetCapacity(
                          &si128,
                          v9,
                          (unsigned int)v6) )
  {
    v5 = v30;
    goto LABEL_14;
  }
  v23[2] = 122;
  v23[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
  v23[1] = "OuEnumerateSubKeys";
  v23[3] = "SubKeyVector.reserve(LocalSubKeyCount)";
  v8 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
         &v28,
         v23,
         3221225495LL);
LABEL_12:
  v11 = v8;
LABEL_23:
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(&si128);
  return v11;
}

```

## disassembly

```asm
0x180083fe0  mov     [rsp-8+arg_10], rbx
0x180083fe5  mov     [rsp-8+arg_18], rsi
0x180083fea  push    rbp
0x180083feb  push    rdi
0x180083fec  push    r13
0x180083fee  push    r14
0x180083ff0  push    r15
0x180083ff2  lea     rbp, [rsp-70h]
0x180083ff7  sub     rsp, 170h
0x180083ffe  mov     rax, cs:__security_cookie
0x180084005  xor     rax, rsp
0x180084008  mov     [rbp+90h+var_28], rax
0x18008400c  xor     ebx, ebx
0x18008400e  mov     rsi, rdx
0x180084011  mov     [rbp+90h+var_68], ebx
0x180084014  mov     r13, rcx
0x180084017  test    rcx, rcx
0x18008401a  jnz     short loc_180084057
0x18008401c  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180084023  mov     [rbp+90h+var_38], 64h ; 'd'
0x18008402b  mov     [rbp+90h+var_48], rax
0x18008402f  lea     rdx, [rbp+90h+var_48]
0x180084033  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x18008403a  mov     [rbp+90h+var_40], rax
0x18008403e  lea     rcx, [rbp+90h+var_68]
0x180084042  lea     rax, aNotNullCheckFa_8; "Not-null check failed: ParentHandle"
0x180084049  mov     [rbp+90h+var_30], rax
0x18008404d  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180084052  jmp     loc_180084280
0x180084057  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18008405f  lea     rax, [rsp+190h+var_130]
0x180084064  mov     [rsp+190h+var_140], rbx
0x180084069  lea     r9, [rsp+190h+var_12C]
0x18008406e  mov     [rsp+190h+var_148], rbx
0x180084073  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180084077  mov     [rsp+190h+var_150], rbx
0x18008407c  xor     r8d, r8d
0x18008407f  mov     [rsp+190h+var_158], rbx
0x180084084  xor     edx, edx
0x180084086  mov     [rsp+190h+var_160], rbx
0x18008408b  mov     [rsp+190h+var_168], rbx
0x180084090  mov     [rsp+190h+var_170], rax
0x180084095  mov     [rsp+190h+var_12C], ebx
0x180084099  mov     [rsp+190h+var_130], ebx
0x18008409d  movdqu  [rbp+90h+var_60], xmm0
0x1800840a2  mov     [rbp+90h+var_50], rdi
0x1800840a6  call    ORQueryInfoKey
0x1800840ab  mov     r8d, eax
0x1800840ae  test    eax, eax
0x1800840b0  jz      short loc_1800840FE
0x1800840b2  mov     [rsp+190h+var_118], 76h ; 'v'
0x1800840bb  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800840c2  mov     [rsp+190h+var_128], rax
0x1800840c7  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x1800840ce  mov     [rsp+190h+var_120], rax
0x1800840d3  lea     rax, aOrqueryinfokey; "ORQueryInfoKey( ParentHandle, nullptr, "...
0x1800840da  mov     [rbp+90h+var_110], rax
0x1800840de  test    r8d, r8d
0x1800840e1  jle     short loc_1800840EE
0x1800840e3  movzx   r8d, r8w
0x1800840e7  or      r8d, 80070000h
0x1800840ee  lea     rdx, [rsp+190h+var_128]
0x1800840f3  lea     rcx, [rbp+90h+var_68]
0x1800840f7  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800840fc  jmp     short loc_180084174
0x1800840fe  mov     r14d, [rsp+190h+var_130]
0x180084103  mov     edx, [rsp+190h+var_12C]
0x180084107  inc     r14d
0x18008410a  test    rdx, rdx
0x18008410d  jz      short loc_18008417F
0x18008410f  cmp     rdx, 8
0x180084113  jbe     short loc_180084126
0x180084115  mov     rax, 3FFFFFFFFFFFFFFh
0x18008411f  cmp     rdx, rax
0x180084122  ja      short loc_180084138
0x180084124  jmp     short loc_18008412B
0x180084126  mov     edx, 8
0x18008412b  lea     rcx, [rbp+90h+var_60]
0x18008412f  call    ?_SetCapacity@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_SetCapacity(unsigned __int64)
0x180084134  test    al, al
0x180084136  jnz     short loc_18008417B
0x180084138  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x18008413f  mov     [rbp+90h+var_F8], 7Ah ; 'z'
0x180084147  mov     [rbp+90h+var_108], rax
0x18008414b  lea     rdx, [rbp+90h+var_108]
0x18008414f  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x180084156  mov     r8d, 0C0000017h
0x18008415c  mov     [rbp+90h+var_100], rax
0x180084160  lea     rcx, [rbp+90h+var_68]
0x180084164  lea     rax, aSubkeyvectorRe; "SubKeyVector.reserve(LocalSubKeyCount)"
0x18008416b  mov     [rbp+90h+var_F0], rax
0x18008416f  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180084174  mov     ebx, eax
0x180084176  jmp     loc_180084275
0x18008417b  mov     rdi, [rbp+90h+var_50]
0x18008417f  cmp     [rsp+190h+var_12C], ebx
0x180084183  mov     r15d, ebx
0x180084186  mov     rbx, qword ptr [rbp+90h+var_60+8]
0x18008418a  jbe     loc_18008424D
0x180084190  lea     rax, [rbp+90h+var_38]
0x180084194  mov     edx, r14d
0x180084197  mov     [rbp+90h+var_48], rax
0x18008419b  lea     rcx, [rbp+90h+var_48]
0x18008419f  lea     rax, [rbp+90h+var_38]
0x1800841a3  mov     [rsp+190h+var_130], r14d
0x1800841a8  mov     [rbp+90h+var_40], rax
0x1800841ac  xor     eax, eax
0x1800841ae  mov     word ptr [rbp+90h+var_38], ax
0x1800841b2  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800841b7  xor     ecx, ecx
0x1800841b9  test    al, al
0x1800841bb  jz      loc_180084352
0x1800841c1  mov     r8, [rbp+90h+var_48]
0x1800841c5  lea     r9, [rsp+190h+var_130]
0x1800841ca  mov     [rsp+190h+var_160], rcx
0x1800841cf  mov     edx, r15d
0x1800841d2  mov     [rsp+190h+var_168], rcx
0x1800841d7  mov     [rsp+190h+var_170], rcx
0x1800841dc  mov     rcx, r13
0x1800841df  call    OREnumKey
0x1800841e4  mov     r8d, eax
0x1800841e7  test    eax, eax
0x1800841e9  jnz     loc_18008430A
0x1800841ef  mov     edx, [rsp+190h+var_130]
0x1800841f3  lea     rcx, [rbp+90h+var_48]
0x1800841f7  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800841fc  test    al, al
0x1800841fe  jz      loc_1800842DB
0x180084204  cmp     rbx, rdi
0x180084207  jnz     short loc_180084222
0x180084209  lea     rcx, [rbp+90h+var_60]
0x18008420d  call    ?_Grow@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(void)
0x180084212  test    al, al
0x180084214  jz      loc_1800842A9
0x18008421a  mov     rdi, [rbp+90h+var_50]
0x18008421e  mov     rbx, qword ptr [rbp+90h+var_60+8]
0x180084222  lea     rdx, [rbp+90h+var_48]
0x180084226  mov     rcx, rbx
0x180084229  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18008422e  add     rbx, 20h ; ' '
0x180084232  lea     rcx, [rbp+90h+var_48]
0x180084236  mov     qword ptr [rbp+90h+var_60+8], rbx
0x18008423a  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x18008423f  inc     r15d
0x180084242  cmp     r15d, [rsp+190h+var_12C]
0x180084247  jb      loc_180084190
0x18008424d  mov     rax, qword ptr [rbp+90h+var_60]
0x180084251  mov     rcx, [rsi]
0x180084254  mov     [rsi], rax
0x180084257  mov     rax, [rsi+8]
0x18008425b  mov     qword ptr [rbp+90h+var_60+8], rax
0x18008425f  mov     rax, [rsi+10h]
0x180084263  mov     [rsi+8], rbx
0x180084267  xor     ebx, ebx
0x180084269  mov     [rbp+90h+var_50], rax
0x18008426d  mov     qword ptr [rbp+90h+var_60], rcx
0x180084271  mov     [rsi+10h], rdi
0x180084275  lea     rcx, [rbp+90h+var_60]
0x180084279  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x18008427e  mov     eax, ebx
0x180084280  mov     rcx, [rbp+90h+var_28]
0x180084284  xor     rcx, rsp; StackCookie
0x180084287  call    __security_check_cookie
0x18008428c  lea     r11, [rsp+190h+var_20]
0x180084294  mov     rbx, [r11+40h]
0x180084298  mov     rsi, [r11+48h]
0x18008429c  mov     rsp, r11
0x18008429f  pop     r15
0x1800842a1  pop     r14
0x1800842a3  pop     r13
0x1800842a5  pop     rdi
0x1800842a6  pop     rbp
0x1800842a7  retn
0x1800842a9  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800842b0  mov     [rbp+90h+var_D8], 92h
0x1800842b8  mov     [rbp+90h+var_E8], rax
0x1800842bc  lea     rdx, [rbp+90h+var_E8]
0x1800842c0  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x1800842c7  mov     [rbp+90h+var_E0], rax
0x1800842cb  lea     rax, aSubkeyvectorEm; "SubKeyVector.emplace_back(utl::move(Sub"...
0x1800842d2  mov     [rbp+90h+var_D0], rax
0x1800842d6  jmp     loc_18008437F
0x1800842db  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800842e2  mov     [rbp+90h+var_B8], 8Eh
0x1800842ea  mov     [rbp+90h+var_C8], rax
0x1800842ee  lea     rdx, [rbp+90h+var_C8]
0x1800842f2  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x1800842f9  mov     [rbp+90h+var_C0], rax
0x1800842fd  lea     rax, aSubkeynameResi; "SubKeyName.resize(SubKeyLengthChars)"
0x180084304  mov     [rbp+90h+var_B0], rax
0x180084308  jmp     short loc_18008437F
0x18008430a  mov     [rbp+90h+var_98], 8Bh
0x180084312  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180084319  mov     [rbp+90h+var_A8], rax
0x18008431d  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x180084324  mov     [rbp+90h+var_A0], rax
0x180084328  lea     rax, aOrenumkeyParen; "OREnumKey( ParentHandle, Index, SubKeyN"...
0x18008432f  mov     [rbp+90h+var_90], rax
0x180084333  test    r8d, r8d
0x180084336  jle     short loc_180084343
0x180084338  movzx   r8d, r8w
0x18008433c  or      r8d, 80070000h
0x180084343  lea     rdx, [rbp+90h+var_A8]
0x180084347  lea     rcx, [rbp+90h+var_68]
0x18008434b  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180084350  jmp     short loc_18008438E
0x180084352  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180084359  mov     [rbp+90h+var_78], 81h
0x180084361  mov     [rbp+90h+var_88], rax
0x180084365  lea     rdx, [rbp+90h+var_88]
0x180084369  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x180084370  mov     [rbp+90h+var_80], rax
0x180084374  lea     rax, aSubkeynameResi; "SubKeyName.resize(SubKeyLengthChars)"
0x18008437b  mov     [rbp+90h+var_70], rax
0x18008437f  mov     r8d, 0C0000017h
0x180084385  lea     rcx, [rbp+90h+var_68]
0x180084389  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008438e  lea     rcx, [rbp+90h+var_48]
0x180084392  mov     ebx, eax
0x180084394  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180084399  jmp     loc_180084275
```
