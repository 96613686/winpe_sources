# OuEnumerateSubKeys(void *,utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &)

- ea: `0x180084f48`
- end: `0x180085306`
- name: `?OuEnumerateSubKeys@@YAJPEAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@@Z`
- size: `958`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x1800829a0`
- `0x180082f64`
- `0x180083d74`
- `0x1800840f8`

## callees

- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x18007da08`
- `0x18007e720`
- `0x18007e9fc`
- `0x18007edd4`
- `0x18007ef14`
- `0x18007efac`
- `0x18007f214`
- `0x180084f48`
- `0x180085c94`
- `0x1800860a0`

## string_xrefs

- `0x180084f84`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085023`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800850a0`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085211`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085243`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x18008527a`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800852ba`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085233`: `SubKeyVector.emplace_back(utl::move(SubKeyName))`

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
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit((void **)&v31);
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
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit((void **)&v31);
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
0x180084f48  mov     [rsp-8+arg_10], rbx
0x180084f4d  mov     [rsp-8+arg_18], rsi
0x180084f52  push    rbp
0x180084f53  push    rdi
0x180084f54  push    r13
0x180084f56  push    r14
0x180084f58  push    r15
0x180084f5a  lea     rbp, [rsp-70h]
0x180084f5f  sub     rsp, 170h
0x180084f66  mov     rax, cs:__security_cookie
0x180084f6d  xor     rax, rsp
0x180084f70  mov     [rbp+90h+var_28], rax
0x180084f74  xor     ebx, ebx
0x180084f76  mov     rsi, rdx
0x180084f79  mov     [rbp+90h+var_68], ebx
0x180084f7c  mov     r13, rcx
0x180084f7f  test    rcx, rcx
0x180084f82  jnz     short loc_180084FBF
0x180084f84  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180084f8b  mov     [rbp+90h+var_38], 64h ; 'd'
0x180084f93  mov     [rbp+90h+var_48], rax
0x180084f97  lea     rdx, [rbp+90h+var_48]
0x180084f9b  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x180084fa2  mov     [rbp+90h+var_40], rax
0x180084fa6  lea     rcx, [rbp+90h+var_68]
0x180084faa  lea     rax, aNotNullCheckFa_8; "Not-null check failed: ParentHandle"
0x180084fb1  mov     [rbp+90h+var_30], rax
0x180084fb5  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180084fba  jmp     loc_1800851E8
0x180084fbf  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180084fc7  lea     rax, [rsp+190h+var_130]
0x180084fcc  mov     [rsp+190h+var_140], rbx
0x180084fd1  lea     r9, [rsp+190h+var_12C]
0x180084fd6  mov     [rsp+190h+var_148], rbx
0x180084fdb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180084fdf  mov     [rsp+190h+var_150], rbx
0x180084fe4  xor     r8d, r8d
0x180084fe7  mov     [rsp+190h+var_158], rbx
0x180084fec  xor     edx, edx
0x180084fee  mov     [rsp+190h+var_160], rbx
0x180084ff3  mov     [rsp+190h+var_168], rbx
0x180084ff8  mov     [rsp+190h+var_170], rax
0x180084ffd  mov     [rsp+190h+var_12C], ebx
0x180085001  mov     [rsp+190h+var_130], ebx
0x180085005  movdqu  [rbp+90h+var_60], xmm0
0x18008500a  mov     [rbp+90h+var_50], rdi
0x18008500e  call    ORQueryInfoKey
0x180085013  mov     r8d, eax
0x180085016  test    eax, eax
0x180085018  jz      short loc_180085066
0x18008501a  mov     [rsp+190h+var_118], 76h ; 'v'
0x180085023  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x18008502a  mov     [rsp+190h+var_128], rax
0x18008502f  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x180085036  mov     [rsp+190h+var_120], rax
0x18008503b  lea     rax, aOrqueryinfokey; "ORQueryInfoKey( ParentHandle, nullptr, "...
0x180085042  mov     [rbp+90h+var_110], rax
0x180085046  test    r8d, r8d
0x180085049  jle     short loc_180085056
0x18008504b  movzx   r8d, r8w
0x18008504f  or      r8d, 80070000h
0x180085056  lea     rdx, [rsp+190h+var_128]
0x18008505b  lea     rcx, [rbp+90h+var_68]
0x18008505f  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180085064  jmp     short loc_1800850DC
0x180085066  mov     r14d, [rsp+190h+var_130]
0x18008506b  mov     edx, [rsp+190h+var_12C]
0x18008506f  inc     r14d
0x180085072  test    rdx, rdx
0x180085075  jz      short loc_1800850E7
0x180085077  cmp     rdx, 8
0x18008507b  jbe     short loc_18008508E
0x18008507d  mov     rax, 3FFFFFFFFFFFFFFh
0x180085087  cmp     rdx, rax
0x18008508a  ja      short loc_1800850A0
0x18008508c  jmp     short loc_180085093
0x18008508e  mov     edx, 8
0x180085093  lea     rcx, [rbp+90h+var_60]
0x180085097  call    ?_SetCapacity@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_SetCapacity(unsigned __int64)
0x18008509c  test    al, al
0x18008509e  jnz     short loc_1800850E3
0x1800850a0  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800850a7  mov     [rbp+90h+var_F8], 7Ah ; 'z'
0x1800850af  mov     [rbp+90h+var_108], rax
0x1800850b3  lea     rdx, [rbp+90h+var_108]
0x1800850b7  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x1800850be  mov     r8d, 0C0000017h
0x1800850c4  mov     [rbp+90h+var_100], rax
0x1800850c8  lea     rcx, [rbp+90h+var_68]
0x1800850cc  lea     rax, aSubkeyvectorRe; "SubKeyVector.reserve(LocalSubKeyCount)"
0x1800850d3  mov     [rbp+90h+var_F0], rax
0x1800850d7  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800850dc  mov     ebx, eax
0x1800850de  jmp     loc_1800851DD
0x1800850e3  mov     rdi, [rbp+90h+var_50]
0x1800850e7  cmp     [rsp+190h+var_12C], ebx
0x1800850eb  mov     r15d, ebx
0x1800850ee  mov     rbx, qword ptr [rbp+90h+var_60+8]
0x1800850f2  jbe     loc_1800851B5
0x1800850f8  lea     rax, [rbp+90h+var_38]
0x1800850fc  mov     edx, r14d
0x1800850ff  mov     [rbp+90h+var_48], rax
0x180085103  lea     rcx, [rbp+90h+var_48]
0x180085107  lea     rax, [rbp+90h+var_38]
0x18008510b  mov     [rsp+190h+var_130], r14d
0x180085110  mov     [rbp+90h+var_40], rax
0x180085114  xor     eax, eax
0x180085116  mov     word ptr [rbp+90h+var_38], ax
0x18008511a  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18008511f  xor     ecx, ecx
0x180085121  test    al, al
0x180085123  jz      loc_1800852BA
0x180085129  mov     r8, [rbp+90h+var_48]
0x18008512d  lea     r9, [rsp+190h+var_130]
0x180085132  mov     [rsp+190h+var_160], rcx
0x180085137  mov     edx, r15d
0x18008513a  mov     [rsp+190h+var_168], rcx
0x18008513f  mov     [rsp+190h+var_170], rcx
0x180085144  mov     rcx, r13
0x180085147  call    OREnumKey
0x18008514c  mov     r8d, eax
0x18008514f  test    eax, eax
0x180085151  jnz     loc_180085272
0x180085157  mov     edx, [rsp+190h+var_130]
0x18008515b  lea     rcx, [rbp+90h+var_48]
0x18008515f  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x180085164  test    al, al
0x180085166  jz      loc_180085243
0x18008516c  cmp     rbx, rdi
0x18008516f  jnz     short loc_18008518A
0x180085171  lea     rcx, [rbp+90h+var_60]
0x180085175  call    ?_Grow@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Grow(void)
0x18008517a  test    al, al
0x18008517c  jz      loc_180085211
0x180085182  mov     rdi, [rbp+90h+var_50]
0x180085186  mov     rbx, qword ptr [rbp+90h+var_60+8]
0x18008518a  lea     rdx, [rbp+90h+var_48]
0x18008518e  mov     rcx, rbx
0x180085191  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180085196  add     rbx, 20h ; ' '
0x18008519a  lea     rcx, [rbp+90h+var_48]
0x18008519e  mov     qword ptr [rbp+90h+var_60+8], rbx
0x1800851a2  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x1800851a7  inc     r15d
0x1800851aa  cmp     r15d, [rsp+190h+var_12C]
0x1800851af  jb      loc_1800850F8
0x1800851b5  mov     rax, qword ptr [rbp+90h+var_60]
0x1800851b9  mov     rcx, [rsi]
0x1800851bc  mov     [rsi], rax
0x1800851bf  mov     rax, [rsi+8]
0x1800851c3  mov     qword ptr [rbp+90h+var_60+8], rax
0x1800851c7  mov     rax, [rsi+10h]
0x1800851cb  mov     [rsi+8], rbx
0x1800851cf  xor     ebx, ebx
0x1800851d1  mov     [rbp+90h+var_50], rax
0x1800851d5  mov     qword ptr [rbp+90h+var_60], rcx
0x1800851d9  mov     [rsi+10h], rdi
0x1800851dd  lea     rcx, [rbp+90h+var_60]
0x1800851e1  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x1800851e6  mov     eax, ebx
0x1800851e8  mov     rcx, [rbp+90h+var_28]
0x1800851ec  xor     rcx, rsp; StackCookie
0x1800851ef  call    __security_check_cookie
0x1800851f4  lea     r11, [rsp+190h+var_20]
0x1800851fc  mov     rbx, [r11+40h]
0x180085200  mov     rsi, [r11+48h]
0x180085204  mov     rsp, r11
0x180085207  pop     r15
0x180085209  pop     r14
0x18008520b  pop     r13
0x18008520d  pop     rdi
0x18008520e  pop     rbp
0x18008520f  retn
0x180085211  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180085218  mov     [rbp+90h+var_D8], 92h
0x180085220  mov     [rbp+90h+var_E8], rax
0x180085224  lea     rdx, [rbp+90h+var_E8]
0x180085228  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x18008522f  mov     [rbp+90h+var_E0], rax
0x180085233  lea     rax, aSubkeyvectorEm; "SubKeyVector.emplace_back(utl::move(Sub"...
0x18008523a  mov     [rbp+90h+var_D0], rax
0x18008523e  jmp     loc_1800852E7
0x180085243  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x18008524a  mov     [rbp+90h+var_B8], 8Eh
0x180085252  mov     [rbp+90h+var_C8], rax
0x180085256  lea     rdx, [rbp+90h+var_C8]
0x18008525a  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x180085261  mov     [rbp+90h+var_C0], rax
0x180085265  lea     rax, aSubkeynameResi; "SubKeyName.resize(SubKeyLengthChars)"
0x18008526c  mov     [rbp+90h+var_B0], rax
0x180085270  jmp     short loc_1800852E7
0x180085272  mov     [rbp+90h+var_98], 8Bh
0x18008527a  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180085281  mov     [rbp+90h+var_A8], rax
0x180085285  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x18008528c  mov     [rbp+90h+var_A0], rax
0x180085290  lea     rax, aOrenumkeyParen; "OREnumKey( ParentHandle, Index, SubKeyN"...
0x180085297  mov     [rbp+90h+var_90], rax
0x18008529b  test    r8d, r8d
0x18008529e  jle     short loc_1800852AB
0x1800852a0  movzx   r8d, r8w
0x1800852a4  or      r8d, 80070000h
0x1800852ab  lea     rdx, [rbp+90h+var_A8]
0x1800852af  lea     rcx, [rbp+90h+var_68]
0x1800852b3  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800852b8  jmp     short loc_1800852F6
0x1800852ba  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800852c1  mov     [rbp+90h+var_78], 81h
0x1800852c9  mov     [rbp+90h+var_88], rax
0x1800852cd  lea     rdx, [rbp+90h+var_88]
0x1800852d1  lea     rax, aOuenumeratesub; "OuEnumerateSubKeys"
0x1800852d8  mov     [rbp+90h+var_80], rax
0x1800852dc  lea     rax, aSubkeynameResi; "SubKeyName.resize(SubKeyLengthChars)"
0x1800852e3  mov     [rbp+90h+var_70], rax
0x1800852e7  mov     r8d, 0C0000017h
0x1800852ed  lea     rcx, [rbp+90h+var_68]
0x1800852f1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800852f6  lea     rcx, [rbp+90h+var_48]
0x1800852fa  mov     ebx, eax
0x1800852fc  call    ?_Uninit@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAAXXZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(void)
0x180085301  jmp     loc_1800851DD
```
