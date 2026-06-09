# ModernDeployment::Autopilot::Core::GenerateRandomComputerName

- ea: `0x18009a96c`
- end: `0x18009ad7f`
- name: `ModernDeployment::Autopilot::Core::GenerateRandomComputerName`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180099db0`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x180067ffc`
- `0x18006b690`
- `0x18007755c`
- `0x18008019c`
- `0x1800814a8`
- `0x18008dc5c`
- `0x18008dc94`
- `0x1800979c8`
- `0x180098644`
- `0x180098dfc`
- `0x18009a96c`
- `0x1800a0a78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18009aa70`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18009aa70`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18009ac04`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18009ac04`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18009abe2`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18009abe2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009abd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009abd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009abd8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009abd8`

## string_xrefs

- `0x18009aaa5`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009ab56`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009ac53`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::GenerateRandomComputerName(__int64 a1, __int64 a2, _BYTE *a3)
{
  _QWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // eax
  int v9; // ebx
  unsigned int v10; // r14d
  unsigned int v11; // ebx
  DWORD CurrentThreadId; // ebx
  DWORD TickCount; // eax
  unsigned int i; // ebx
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r15d
  unsigned __int16 v19[2]; // [rsp+20h] [rbp-138h] BYREF
  __int64 v20; // [rsp+30h] [rbp-128h] BYREF
  char v21; // [rsp+38h] [rbp-120h]
  __int128 v22; // [rsp+40h] [rbp-118h]
  __int128 v23; // [rsp+50h] [rbp-108h] BYREF
  __int64 v24; // [rsp+60h] [rbp-F8h]
  char v25; // [rsp+68h] [rbp-F0h]
  __int128 v26; // [rsp+70h] [rbp-E8h] BYREF
  char v27; // [rsp+80h] [rbp-D8h]
  _QWORD v28[2]; // [rsp+88h] [rbp-D0h] BYREF
  char v29; // [rsp+98h] [rbp-C0h]
  _BYTE v30[40]; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v31[16]; // [rsp+C8h] [rbp-90h] BYREF
  __int64 v32; // [rsp+D8h] [rbp-80h]
  _BYTE v33[16]; // [rsp+E8h] [rbp-70h] BYREF
  __int64 v34; // [rsp+F8h] [rbp-60h]
  _BYTE v35[32]; // [rsp+108h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
    v30,
    L"(%RAND:)(\\d+)(%)",
    256);
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  *a3 = 0;
  if ( (unsigned __int8)std::regex_search<std::char_traits<unsigned short>,std::allocator<unsigned short>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>>(
                          a1,
                          &v20,
                          v30) )
  {
    *a3 = 1;
    if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3) > 2 )
      v5 = (_QWORD *)(v22 + 48);
    else
      v5 = v28;
    v6 = std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(v5, v35);
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
    v8 = _o__wtoi(v7);
    v9 = v8;
    v10 = -1;
    if ( v8 >= 0 )
      v10 = v8;
    std::wstring::_Tidy_deallocate(v35);
    v11 = (v9 >> 31) & 0x80070216;
    if ( (v11 & 0x80000000) == 0 )
    {
      std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
        (char *)&v23 + 8,
        v33);
      std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(&v26, v31);
      if ( v34 + v32 + (unsigned __int64)v10 <= 0x3F )
      {
        CurrentThreadId = GetCurrentThreadId();
        TickCount = GetTickCount();
        _o_srand(TickCount ^ CurrentThreadId);
        std::wstring::operator=(a1, v33);
        for ( i = 0; ; ++i )
        {
          if ( i >= v10 )
          {
            std::wstring::append(a1, v31);
            std::wstring::_Tidy_deallocate(v31);
            std::wstring::_Tidy_deallocate(v33);
            goto LABEL_23;
          }
          v16 = rand();
          v17 = StringCchPrintfW(v19, 2u, L"%d", (unsigned int)(v16 % 10));
          v18 = v17;
          if ( v17 < 0 )
            break;
          std::wstring::append(a1, v19);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
          (const char *)(unsigned int)v17,
          *(int *)v19);
        std::wstring::_Tidy_deallocate(v31);
        std::wstring::_Tidy_deallocate(v33);
        if ( (_QWORD)v22 )
        {
          std::_Deallocate<16>((void *)v22, (struct std::nothrow_t *)(8 * ((__int64)(v23 - v22) >> 3)));
          v22 = 0;
          *(_QWORD *)&v23 = 0;
        }
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v30);
        return v18;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
          (const char *)0x8007092FLL,
          *(int *)v19);
        std::wstring::_Tidy_deallocate(v31);
        std::wstring::_Tidy_deallocate(v33);
        if ( (_QWORD)v22 )
        {
          std::_Deallocate<16>((void *)v22, (struct std::nothrow_t *)(8 * ((__int64)(v23 - v22) >> 3)));
          v22 = 0;
          *(_QWORD *)&v23 = 0;
        }
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v30);
        return 2147944751LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\autopilotutilities\\autopilotutilities.cpp",
        (const char *)v11,
        *(int *)v19);
      if ( (_QWORD)v22 )
      {
        std::_Deallocate<16>((void *)v22, (struct std::nothrow_t *)(8 * ((__int64)(v23 - v22) >> 3)));
        v22 = 0;
        *(_QWORD *)&v23 = 0;
      }
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v30);
      return v11;
    }
  }
  else
  {
LABEL_23:
    if ( (_QWORD)v22 )
    {
      std::_Deallocate<16>((void *)v22, (struct std::nothrow_t *)(8 * ((__int64)(v23 - v22) >> 3)));
      v22 = 0;
      *(_QWORD *)&v23 = 0;
    }
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v30);
    return 0;
  }
}

```

## disassembly

```asm
0x18009a96c  mov     [rsp+arg_8], rbx
0x18009a971  push    rsi
0x18009a972  push    rdi
0x18009a973  push    r12
0x18009a975  push    r14
0x18009a977  push    r15
0x18009a979  sub     rsp, 130h
0x18009a980  mov     rax, cs:__security_cookie
0x18009a987  xor     rax, rsp
0x18009a98a  mov     [rsp+158h+var_30], rax
0x18009a992  mov     rbx, r8
0x18009a995  mov     rsi, rcx
0x18009a998  mov     r8d, 100h
0x18009a99e  lea     rdx, aRandD; "(%RAND:)(\\d+)(%)"
0x18009a9a5  lea     rcx, [rsp+158h+var_B8]
0x18009a9ad  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18009a9b2  nop
0x18009a9b3  xor     r12d, r12d
0x18009a9b6  mov     [rsp+158h+var_128], r12
0x18009a9bb  mov     [rsp+158h+var_120], r12b
0x18009a9c0  xorps   xmm0, xmm0
0x18009a9c3  movdqa  [rsp+158h+var_118], xmm0
0x18009a9c9  xorps   xmm1, xmm1
0x18009a9cc  movdqa  [rsp+158h+var_108], xmm1
0x18009a9d2  mov     [rsp+158h+var_F8], r12
0x18009a9d7  mov     [rsp+158h+var_F0], r12b
0x18009a9dc  movdqa  [rsp+158h+var_E8], xmm0
0x18009a9e2  mov     [rsp+158h+var_D8], r12b
0x18009a9ea  mov     [rsp+158h+var_D0], r12
0x18009a9f2  mov     [rsp+158h+var_C8], r12
0x18009a9fa  mov     [rsp+158h+var_C0], r12b
0x18009aa02  mov     [rbx], r12b
0x18009aa05  lea     r8, [rsp+158h+var_B8]
0x18009aa0d  lea     rdx, [rsp+158h+var_128]
0x18009aa12  mov     rcx, rsi
0x18009aa15  call    ??$regex_search@U?$char_traits@G@std@@V?$allocator@G@2@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<std::char_traits<ushort>,std::allocator<ushort>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x18009aa1a  mov     rdi, 0AAAAAAAAAAAAAAABh
0x18009aa24  test    al, al
0x18009aa26  jz      loc_18009AD0C
0x18009aa2c  mov     byte ptr [rbx], 1
0x18009aa2f  mov     rcx, qword ptr [rsp+158h+var_118]
0x18009aa34  mov     rax, qword ptr [rsp+158h+var_118+8]
0x18009aa39  sub     rax, rcx
0x18009aa3c  sar     rax, 3
0x18009aa40  imul    rax, rdi
0x18009aa44  cmp     rax, 2
0x18009aa48  ja      short loc_18009AA54
0x18009aa4a  lea     rcx, [rsp+158h+var_D0]
0x18009aa52  jmp     short loc_18009AA58
0x18009aa54  add     rcx, 30h ; '0'
0x18009aa58  lea     rdx, [rsp+158h+var_50]
0x18009aa60  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18009aa65  mov     rcx, rax
0x18009aa68  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009aa6d  mov     rcx, rax
0x18009aa70  call    cs:__imp__o__wtoi
0x18009aa76  mov     ebx, eax
0x18009aa78  or      r14d, 0FFFFFFFFh
0x18009aa7c  test    eax, eax
0x18009aa7e  cmovns  r14d, eax
0x18009aa82  sar     ebx, 1Fh
0x18009aa85  lea     rcx, [rsp+158h+var_50]
0x18009aa8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009aa92  and     ebx, 80070216h
0x18009aa98  jns     short loc_18009AB03
0x18009aa9a  mov     rcx, [rsp+158h]; this
0x18009aaa2  mov     r9d, ebx; char *
0x18009aaa5  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009aaac  mov     edx, 39h ; '9'; void *
0x18009aab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009aab6  nop
0x18009aab7  mov     rax, qword ptr [rsp+158h+var_118]
0x18009aabc  test    rax, rax
0x18009aabf  jz      short loc_18009AAEF
0x18009aac1  mov     rcx, qword ptr [rsp+158h+var_108]
0x18009aac6  sub     rcx, rax
0x18009aac9  sar     rcx, 3
0x18009aacd  imul    rcx, rdi
0x18009aad1  lea     rdx, [rcx+rcx*2]
0x18009aad5  shl     rdx, 3
0x18009aad9  mov     rcx, rax
0x18009aadc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009aae1  xorps   xmm0, xmm0
0x18009aae4  movdqa  [rsp+158h+var_118], xmm0
0x18009aaea  mov     qword ptr [rsp+158h+var_108], r12
0x18009aaef  lea     rcx, [rsp+158h+var_B8]
0x18009aaf7  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18009aafc  mov     eax, ebx
0x18009aafe  jmp     loc_18009AD56
0x18009ab03  lea     rdx, [rsp+158h+var_70]
0x18009ab0b  lea     rcx, [rsp+158h+var_108+8]
0x18009ab10  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18009ab15  nop
0x18009ab16  lea     rdx, [rsp+158h+var_90]
0x18009ab1e  lea     rcx, [rsp+158h+var_E8]
0x18009ab23  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18009ab28  nop
0x18009ab29  mov     eax, r14d
0x18009ab2c  add     rax, [rsp+158h+var_80]
0x18009ab34  add     rax, [rsp+158h+var_60]
0x18009ab3c  cmp     rax, 3Fh ; '?'
0x18009ab40  jbe     loc_18009ABD0
0x18009ab46  mov     rcx, [rsp+158h]; this
0x18009ab4e  mov     ebx, 8007092Fh
0x18009ab53  mov     r9d, ebx; char *
0x18009ab56  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009ab5d  mov     edx, 3Eh ; '>'; void *
0x18009ab62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ab67  nop
0x18009ab68  lea     rcx, [rsp+158h+var_90]
0x18009ab70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ab75  nop
0x18009ab76  lea     rcx, [rsp+158h+var_70]
0x18009ab7e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ab83  nop
0x18009ab84  mov     r8, qword ptr [rsp+158h+var_118]
0x18009ab89  test    r8, r8
0x18009ab8c  jz      short loc_18009ABBC
0x18009ab8e  mov     rcx, qword ptr [rsp+158h+var_108]
0x18009ab93  sub     rcx, r8
0x18009ab96  sar     rcx, 3
0x18009ab9a  imul    rcx, rdi
0x18009ab9e  lea     rdx, [rcx+rcx*2]
0x18009aba2  shl     rdx, 3
0x18009aba6  mov     rcx, r8
0x18009aba9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009abae  xorps   xmm0, xmm0
0x18009abb1  movdqa  [rsp+158h+var_118], xmm0
0x18009abb7  mov     qword ptr [rsp+158h+var_108], r12
0x18009abbc  lea     rcx, [rsp+158h+var_B8]
0x18009abc4  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18009abc9  mov     eax, ebx
0x18009abcb  jmp     loc_18009AD56
0x18009abd0  call    cs:__imp_GetCurrentThreadId
0x18009abd6  mov     ebx, eax
0x18009abd8  call    cs:__imp_GetTickCount
0x18009abde  xor     ebx, eax
0x18009abe0  mov     ecx, ebx
0x18009abe2  call    cs:__imp__o_srand
0x18009abe8  lea     rdx, [rsp+158h+var_70]
0x18009abf0  mov     rcx, rsi
0x18009abf3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009abf8  mov     ebx, r12d
0x18009abfb  cmp     ebx, r14d
0x18009abfe  jnb     loc_18009ACDF
0x18009ac04  call    cs:__imp_rand
0x18009ac0a  mov     r9d, eax
0x18009ac0d  mov     eax, 66666667h
0x18009ac12  imul    r9d
0x18009ac15  sar     edx, 2
0x18009ac18  mov     eax, edx
0x18009ac1a  shr     eax, 1Fh
0x18009ac1d  add     edx, eax
0x18009ac1f  lea     eax, [rdx+rdx*4]
0x18009ac22  add     eax, eax
0x18009ac24  sub     r9d, eax
0x18009ac27  lea     r8, aD; "%d"
0x18009ac2e  mov     edx, 2; unsigned __int64
0x18009ac33  lea     rcx, [rsp+158h+var_138]; unsigned __int16 *
0x18009ac38  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009ac3d  mov     r15d, eax
0x18009ac40  test    eax, eax
0x18009ac42  jns     loc_18009ACCB
0x18009ac48  mov     rcx, [rsp+158h]; this
0x18009ac50  mov     r9d, eax; char *
0x18009ac53  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009ac5a  mov     edx, 45h ; 'E'; void *
0x18009ac5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ac64  nop
0x18009ac65  lea     rcx, [rsp+158h+var_90]
0x18009ac6d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ac72  nop
0x18009ac73  lea     rcx, [rsp+158h+var_70]
0x18009ac7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ac80  nop
0x18009ac81  mov     rcx, qword ptr [rsp+158h+var_118]
0x18009ac86  test    rcx, rcx
0x18009ac89  jz      short loc_18009ACB6
0x18009ac8b  mov     rax, qword ptr [rsp+158h+var_108]
0x18009ac90  sub     rax, rcx
0x18009ac93  sar     rax, 3
0x18009ac97  imul    rax, rdi
0x18009ac9b  lea     rdx, [rax+rax*2]
0x18009ac9f  shl     rdx, 3
0x18009aca3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009aca8  xorps   xmm0, xmm0
0x18009acab  movdqa  [rsp+158h+var_118], xmm0
0x18009acb1  mov     qword ptr [rsp+158h+var_108], r12
0x18009acb6  lea     rcx, [rsp+158h+var_B8]
0x18009acbe  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18009acc3  mov     eax, r15d
0x18009acc6  jmp     loc_18009AD56
0x18009accb  lea     rdx, [rsp+158h+var_138]
0x18009acd0  mov     rcx, rsi
0x18009acd3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18009acd8  inc     ebx
0x18009acda  jmp     loc_18009ABFB
0x18009acdf  lea     rdx, [rsp+158h+var_90]
0x18009ace7  mov     rcx, rsi
0x18009acea  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18009acef  nop
0x18009acf0  lea     rcx, [rsp+158h+var_90]
0x18009acf8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009acfd  nop
0x18009acfe  lea     rcx, [rsp+158h+var_70]
0x18009ad06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ad0b  nop
0x18009ad0c  mov     rcx, qword ptr [rsp+158h+var_118]
0x18009ad11  test    rcx, rcx
0x18009ad14  jz      short loc_18009AD41
0x18009ad16  mov     rax, qword ptr [rsp+158h+var_108]
0x18009ad1b  sub     rax, rcx
0x18009ad1e  sar     rax, 3
0x18009ad22  imul    rax, rdi
0x18009ad26  lea     rdx, [rax+rax*2]
0x18009ad2a  shl     rdx, 3
0x18009ad2e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009ad33  xorps   xmm0, xmm0
0x18009ad36  movdqa  [rsp+158h+var_118], xmm0
0x18009ad3c  mov     qword ptr [rsp+158h+var_108], r12
0x18009ad41  lea     rcx, [rsp+158h+var_B8]
0x18009ad49  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18009ad4e  xor     eax, eax
0x18009ad50  jmp     short loc_18009AD56
0x18009ad52  mov     eax, dword ptr [rsp+158h+var_138]
0x18009ad56  mov     rcx, [rsp+158h+var_30]
0x18009ad5e  xor     rcx, rsp; StackCookie
0x18009ad61  call    __security_check_cookie
0x18009ad66  mov     rbx, [rsp+158h+arg_8]
0x18009ad6e  add     rsp, 130h
0x18009ad75  pop     r15
0x18009ad77  pop     r14
0x18009ad79  pop     r12
0x18009ad7b  pop     rdi
0x18009ad7c  pop     rsi
0x18009ad7d  retn
```
