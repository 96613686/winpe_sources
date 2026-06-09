# AppCompatUtility::ParseRegistryKeyString(HKEY__ * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800430f8`
- end: `0x1800434b2`
- name: `?ParseRegistryKeyString@AppCompatUtility@@YAJPEAPEAUHKEY__@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@@Z`
- size: `954`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028330`
- `0x18002fdd0`
- `0x18003c014`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e504`
- `0x180010718`
- `0x180011d40`
- `0x1800430f8`
- `0x1800543c0`
- `0x180062af0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043291`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800432b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800432dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043303`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043329`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004334f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043375`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004339b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800433c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800433e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043291`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800432b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800432dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043303`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043329`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004334f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043375`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004339b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800433c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800433e3`

## string_xrefs

- `0x180043410`: `AppCompatUtility::ParseRegistryKeyString`
- `0x1800433ba`: `HKEY_CURRENT_CONFIG`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppCompatUtility::ParseRegistryKeyString(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // r15
  __int64 v7; // rax
  _QWORD *v8; // r11
  __int64 traits_2_0_unsigned_short; // rax
  __int64 v10; // r11
  __int64 v11; // rdx
  unsigned __int64 v12; // r14
  __int64 v13; // r8
  _QWORD *v14; // rdx
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // rax
  _WORD *v19; // rcx
  __int128 *v20; // rdx
  __int128 *v21; // rdx
  __int128 *v22; // rdx
  __int128 *v23; // rdx
  __int128 *v24; // rdx
  __int128 *v25; // rdx
  __int128 *v26; // rdx
  __int128 *v27; // rdx
  __int128 *v28; // rdx
  __int128 *v29; // rdx
  const wchar_t *v30; // rax
  const char *v31; // r9
  __int64 result; // rax
  unsigned int v33; // [rsp+30h] [rbp-88h]
  __int128 v35; // [rsp+48h] [rbp-70h] BYREF
  __m128i si128; // [rsp+58h] [rbp-60h]
  __int128 v37; // [rsp+68h] [rbp-50h] BYREF
  __int128 v38; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v35 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v35) = 0;
  v6 = -1;
  *a1 = -1;
  v7 = a3[2];
  if ( a3[3] <= 7u )
    v8 = a3;
  else
    v8 = (_QWORD *)*a3;
  try
  {
    if ( !v7
      || (traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                        v8,
                                        (char *)v8 + 2 * v7,
                                        92),
          traits_2_0_unsigned_short == v11)
      || (v12 = (traits_2_0_unsigned_short - v10) >> 1, v12 == -1) )
    {
      std::wstring::operator=(&v35, a3);
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v19 = (_WORD *)a2;
      else
        v19 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 0;
      *v19 = 0;
    }
    else
    {
      v37 = 0;
      v38 = 0;
      v13 = (traits_2_0_unsigned_short - v10) >> 1;
      if ( a3[2] < v12 )
        v13 = a3[2];
      if ( a3[3] <= 7u )
        v14 = a3;
      else
        v14 = (_QWORD *)*a3;
      std::wstring::_Construct<1,unsigned short const *>(&v37, v14, v13);
      std::wstring::operator=(&v35, &v37);
      std::wstring::~wstring(&v37);
      v15 = v12 + 1;
      v37 = 0;
      v38 = 0;
      v16 = a3[2];
      if ( v16 < v15 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      v17 = v16 - v15;
      if ( v17 != -1 )
        v6 = v17;
      if ( a3[3] <= 7u )
        v18 = a3;
      else
        v18 = (_QWORD *)*a3;
      std::wstring::_Construct<1,unsigned short const *>(&v37, (char *)v18 + 2 * v15, v6);
      std::wstring::operator=(a2, &v37);
      std::wstring::~wstring(&v37);
    }
    v20 = &v35;
    if ( si128.m128i_i64[1] > 7uLL )
      v20 = (__int128 *)v35;
    if ( !(unsigned int)_o__wcsicmp(L"HKEY_LOCAL_MACHINE", v20) )
      goto LABEL_60;
    v21 = &v35;
    if ( si128.m128i_i64[1] > 7uLL )
      v21 = (__int128 *)v35;
    if ( (unsigned int)_o__wcsicmp(L"HKLM", v21) )
    {
      v22 = &v35;
      if ( si128.m128i_i64[1] > 7uLL )
        v22 = (__int128 *)v35;
      if ( !(unsigned int)_o__wcsicmp(L"HKEY_CLASSES_ROOT", v22) )
        goto LABEL_59;
      v23 = &v35;
      if ( si128.m128i_i64[1] > 7uLL )
        v23 = (__int128 *)v35;
      if ( (unsigned int)_o__wcsicmp(L"HKCR", v23) )
      {
        v24 = &v35;
        if ( si128.m128i_i64[1] > 7uLL )
          v24 = (__int128 *)v35;
        if ( !(unsigned int)_o__wcsicmp(L"HKEY_CURRENT_USER", v24) )
          goto LABEL_58;
        v25 = &v35;
        if ( si128.m128i_i64[1] > 7uLL )
          v25 = (__int128 *)v35;
        if ( (unsigned int)_o__wcsicmp(L"HKCU", v25) )
        {
          v26 = &v35;
          if ( si128.m128i_i64[1] > 7uLL )
            v26 = (__int128 *)v35;
          if ( !(unsigned int)_o__wcsicmp(L"HKEY_USERS", v26) )
            goto LABEL_57;
          v27 = &v35;
          if ( si128.m128i_i64[1] > 7uLL )
            v27 = (__int128 *)v35;
          if ( (unsigned int)_o__wcsicmp(L"HKU", v27) )
          {
            v28 = &v35;
            if ( si128.m128i_i64[1] > 7uLL )
              v28 = (__int128 *)v35;
            if ( (unsigned int)_o__wcsicmp(L"HKEY_CURRENT_CONFIG", v28) )
            {
              v29 = &v35;
              if ( si128.m128i_i64[1] > 7uLL )
                v29 = (__int128 *)v35;
              if ( (unsigned int)_o__wcsicmp(L"HKCC", v29) )
              {
                v30 = (const wchar_t *)&v35;
                if ( si128.m128i_i64[1] > 7uLL )
                  v30 = (const wchar_t *)v35;
                AslLogCallPrintf(
                  1,
                  "AppCompatUtility::ParseRegistryKeyString",
                  2310,
                  "Unsupported or incorrect Root Key: '%ls'.",
                  v30);
                std::wstring::~wstring(&v35);
                std::wstring::~wstring(a3);
                return 2147942487LL;
              }
            }
            *a1 = -2147483643;
          }
          else
          {
LABEL_57:
            *a1 = -2147483645;
          }
        }
        else
        {
LABEL_58:
          *a1 = -2147483647;
        }
      }
      else
      {
LABEL_59:
        *a1 = 0xFFFFFFFF80000000uLL;
      }
    }
    else
    {
LABEL_60:
      *a1 = -2147483646;
    }
    std::wstring::~wstring(&v35);
    std::wstring::~wstring(a3);
    result = 0;
  }
  catch ( ... )
  {
    v33 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x90C,
            (unsigned int)"onecore\\windows\\appcompat\\migrationshims\\lib\\utility.cpp",
            v31);
    std::wstring::~wstring(a3);
    return v33;
  }
  return result;
}

```

## disassembly

```asm
0x1800430f8  push    rbx
0x1800430fa  push    rsi
0x1800430fb  push    rdi
0x1800430fc  push    r14
0x1800430fe  push    r15
0x180043100  sub     rsp, 90h
0x180043107  mov     [rsp+0B8h+var_80], 0FFFFFFFFFFFFFFFEh
0x180043110  mov     rax, cs:__security_cookie
0x180043117  xor     rax, rsp
0x18004311a  mov     [rsp+0B8h+var_30], rax
0x180043122  mov     rbx, r8
0x180043125  mov     rsi, rdx
0x180043128  mov     rdi, rcx
0x18004312b  mov     [rsp+0B8h+var_78], rbx
0x180043130  xorps   xmm0, xmm0
0x180043133  movups  [rsp+0B8h+var_70], xmm0
0x180043138  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180043140  movdqu  [rsp+0B8h+var_60], xmm1
0x180043146  xor     eax, eax
0x180043148  mov     word ptr [rsp+0B8h+var_70], ax
0x18004314d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180043151  mov     [rcx], r15
0x180043154  mov     rax, [r8+10h]
0x180043158  cmp     qword ptr [r8+18h], 7
0x18004315d  jbe     short loc_180043164
0x18004315f  mov     r11, [r8]
0x180043162  jmp     short loc_180043167
0x180043164  mov     r11, rbx
0x180043167  test    rax, rax
0x18004316a  jz      loc_180043250
0x180043170  lea     rdx, [r11+rax*2]
0x180043174  mov     r8d, 5Ch ; '\'
0x18004317a  mov     rcx, r11
0x18004317d  call    _anonymous_namespace____Finding___Find_impl__anonymous_namespace____Finding___Find_traits_2_0_unsigned_short_
0x180043182  mov     r14, rax
0x180043185  cmp     rax, rdx
0x180043188  jz      loc_180043250
0x18004318e  sub     r14, r11
0x180043191  sar     r14, 1
0x180043194  cmp     r14, r15
0x180043197  jz      loc_180043250
0x18004319d  xorps   xmm0, xmm0
0x1800431a0  movups  [rsp+0B8h+var_50], xmm0
0x1800431a5  xorps   xmm1, xmm1
0x1800431a8  movdqu  [rsp+0B8h+var_40], xmm1
0x1800431ae  mov     r8, r14
0x1800431b1  cmp     [rbx+10h], r14
0x1800431b5  cmovb   r8, [rbx+10h]
0x1800431ba  cmp     qword ptr [rbx+18h], 7
0x1800431bf  jbe     short loc_1800431C6
0x1800431c1  mov     rdx, [rbx]
0x1800431c4  jmp     short loc_1800431C9
0x1800431c6  mov     rdx, rbx
0x1800431c9  lea     rcx, [rsp+0B8h+var_50]
0x1800431ce  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800431d3  lea     rdx, [rsp+0B8h+var_50]
0x1800431d8  lea     rcx, [rsp+0B8h+var_70]
0x1800431dd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800431e2  lea     rcx, [rsp+0B8h+var_50]; void *
0x1800431e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800431ec  inc     r14
0x1800431ef  xorps   xmm0, xmm0
0x1800431f2  movups  [rsp+0B8h+var_50], xmm0
0x1800431f7  xorps   xmm1, xmm1
0x1800431fa  movdqu  [rsp+0B8h+var_40], xmm1
0x180043200  mov     rax, [rbx+10h]
0x180043204  cmp     rax, r14
0x180043207  jb      loc_1800434AB
0x18004320d  sub     rax, r14
0x180043210  cmp     rax, r15
0x180043213  cmovb   r15, rax
0x180043217  cmp     qword ptr [rbx+18h], 7
0x18004321c  jbe     short loc_180043223
0x18004321e  mov     rax, [rbx]
0x180043221  jmp     short loc_180043226
0x180043223  mov     rax, rbx
0x180043226  lea     rdx, [rax+r14*2]
0x18004322a  mov     r8, r15
0x18004322d  lea     rcx, [rsp+0B8h+var_50]
0x180043232  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180043237  lea     rdx, [rsp+0B8h+var_50]
0x18004323c  mov     rcx, rsi
0x18004323f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180043244  lea     rcx, [rsp+0B8h+var_50]; void *
0x180043249  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004324e  jmp     short loc_180043279
0x180043250  mov     rdx, rbx
0x180043253  lea     rcx, [rsp+0B8h+var_70]
0x180043258  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004325d  cmp     qword ptr [rsi+18h], 7
0x180043262  jbe     short loc_180043269
0x180043264  mov     rcx, [rsi]
0x180043267  jmp     short loc_18004326C
0x180043269  mov     rcx, rsi
0x18004326c  mov     qword ptr [rsi+10h], 0
0x180043274  xor     eax, eax
0x180043276  mov     [rcx], ax
0x180043279  lea     rdx, [rsp+0B8h+var_70]
0x18004327e  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x180043284  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x18004328a  lea     rcx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x180043291  call    cs:__imp__o__wcsicmp
0x180043297  test    eax, eax
0x180043299  jz      loc_180043460
0x18004329f  lea     rdx, [rsp+0B8h+var_70]
0x1800432a4  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x1800432aa  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x1800432b0  lea     rcx, aHklm; "HKLM"
0x1800432b7  call    cs:__imp__o__wcsicmp
0x1800432bd  test    eax, eax
0x1800432bf  jz      loc_180043460
0x1800432c5  lea     rdx, [rsp+0B8h+var_70]
0x1800432ca  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x1800432d0  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x1800432d6  lea     rcx, aHkeyClassesRoo; "HKEY_CLASSES_ROOT"
0x1800432dd  call    cs:__imp__o__wcsicmp
0x1800432e3  test    eax, eax
0x1800432e5  jz      loc_180043457
0x1800432eb  lea     rdx, [rsp+0B8h+var_70]
0x1800432f0  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x1800432f6  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x1800432fc  lea     rcx, aHkcr; "HKCR"
0x180043303  call    cs:__imp__o__wcsicmp
0x180043309  test    eax, eax
0x18004330b  jz      loc_180043457
0x180043311  lea     rdx, [rsp+0B8h+var_70]
0x180043316  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x18004331c  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x180043322  lea     rcx, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180043329  call    cs:__imp__o__wcsicmp
0x18004332f  test    eax, eax
0x180043331  jz      loc_18004344E
0x180043337  lea     rdx, [rsp+0B8h+var_70]
0x18004333c  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x180043342  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x180043348  lea     rcx, aHkcu; "HKCU"
0x18004334f  call    cs:__imp__o__wcsicmp
0x180043355  test    eax, eax
0x180043357  jz      loc_18004344E
0x18004335d  lea     rdx, [rsp+0B8h+var_70]
0x180043362  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x180043368  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x18004336e  lea     rcx, aHkeyUsers; "HKEY_USERS"
0x180043375  call    cs:__imp__o__wcsicmp
0x18004337b  test    eax, eax
0x18004337d  jz      loc_180043445
0x180043383  lea     rdx, [rsp+0B8h+var_70]
0x180043388  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x18004338e  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x180043394  lea     rcx, aHku; "HKU"
0x18004339b  call    cs:__imp__o__wcsicmp
0x1800433a1  test    eax, eax
0x1800433a3  jz      loc_180043445
0x1800433a9  lea     rdx, [rsp+0B8h+var_70]
0x1800433ae  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x1800433b4  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x1800433ba  lea     rcx, aHkeyCurrentCon; "HKEY_CURRENT_CONFIG"
0x1800433c1  call    cs:__imp__o__wcsicmp
0x1800433c7  test    eax, eax
0x1800433c9  jz      short loc_18004343C
0x1800433cb  lea     rdx, [rsp+0B8h+var_70]
0x1800433d0  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x1800433d6  cmova   rdx, qword ptr [rsp+0B8h+var_70]
0x1800433dc  lea     rcx, aHkcc; "HKCC"
0x1800433e3  call    cs:__imp__o__wcsicmp
0x1800433e9  test    eax, eax
0x1800433eb  jz      short loc_18004343C
0x1800433ed  lea     rax, [rsp+0B8h+var_70]
0x1800433f2  cmp     qword ptr [rsp+0B8h+var_60+8], 7
0x1800433f8  cmova   rax, qword ptr [rsp+0B8h+var_70]
0x1800433fe  mov     [rsp+0B8h+var_98], rax
0x180043403  lea     r9, aUnsupportedOrI; "Unsupported or incorrect Root Key: '%ls"...
0x18004340a  mov     r8d, 906h
0x180043410  lea     rdx, aAppcompatutili; "AppCompatUtility::ParseRegistryKeyStrin"...
0x180043417  mov     ecx, 1
0x18004341c  call    AslLogCallPrintf
0x180043421  nop
0x180043422  lea     rcx, [rsp+0B8h+var_70]; void *
0x180043427  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004342c  nop
0x18004342d  mov     rcx, rbx; void *
0x180043430  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043435  mov     eax, 80070057h
0x18004343a  jmp     short loc_18004348C
0x18004343c  mov     qword ptr [rdi], 0FFFFFFFF80000005h
0x180043443  jmp     short loc_180043467
0x180043445  mov     qword ptr [rdi], 0FFFFFFFF80000003h
0x18004344c  jmp     short loc_180043467
0x18004344e  mov     qword ptr [rdi], 0FFFFFFFF80000001h
0x180043455  jmp     short loc_180043467
0x180043457  mov     qword ptr [rdi], 0FFFFFFFF80000000h
0x18004345e  jmp     short loc_180043467
0x180043460  mov     qword ptr [rdi], 0FFFFFFFF80000002h
0x180043467  lea     rcx, [rsp+0B8h+var_70]; void *
0x18004346c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043471  nop
0x180043472  mov     rcx, rbx; void *
0x180043475  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004347a  xor     eax, eax
0x18004347c  jmp     short loc_18004348C
0x18004347e  mov     rcx, [rsp+0B8h+var_78]; void *
0x180043483  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043488  mov     eax, [rsp+0B8h+var_88]
0x18004348c  mov     rcx, [rsp+0B8h+var_30]
0x180043494  xor     rcx, rsp; StackCookie
0x180043497  call    __security_check_cookie
0x18004349c  add     rsp, 90h
0x1800434a3  pop     r15
0x1800434a5  pop     r14
0x1800434a7  pop     rdi
0x1800434a8  pop     rsi
0x1800434a9  pop     rbx
0x1800434aa  retn
0x1800434ab  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
