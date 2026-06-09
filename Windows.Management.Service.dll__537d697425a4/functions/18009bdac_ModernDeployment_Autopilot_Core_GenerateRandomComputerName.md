# ModernDeployment::Autopilot::Core::GenerateRandomComputerName

- ea: `0x18009bdac`
- end: `0x18009c1dd`
- name: `ModernDeployment::Autopilot::Core::GenerateRandomComputerName`
- size: `1073`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009b1b0`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006841c`
- `0x18006bb78`
- `0x180077de0`
- `0x180080bac`
- `0x180081f38`
- `0x18008ed40`
- `0x18008ed78`
- `0x180098d38`
- `0x180099a08`
- `0x18009a1cc`
- `0x18009bdac`
- `0x1800a2048`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18009beb0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18009beb0`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18009c05c`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18009c05c`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18009c034`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18009c034`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c016`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009c024`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009c024`

## string_xrefs

- `0x18009beeb`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009bf9c`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`
- `0x18009c0b1`: `onecoreuap\admin\moderndeployment\autopilot\service\autopilotutilities\autopilotutilities.cpp`

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
          std::_Deallocate<16>(v22, 8 * ((__int64)(v23 - v22) >> 3));
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
          std::_Deallocate<16>(v22, 8 * ((__int64)(v23 - v22) >> 3));
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
        std::_Deallocate<16>(v22, 8 * ((__int64)(v23 - v22) >> 3));
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
      std::_Deallocate<16>(v22, 8 * ((__int64)(v23 - v22) >> 3));
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
0x18009bdac  mov     [rsp+arg_8], rbx
0x18009bdb1  push    rsi
0x18009bdb2  push    rdi
0x18009bdb3  push    r12
0x18009bdb5  push    r14
0x18009bdb7  push    r15
0x18009bdb9  sub     rsp, 130h
0x18009bdc0  mov     rax, cs:__security_cookie
0x18009bdc7  xor     rax, rsp
0x18009bdca  mov     [rsp+158h+var_30], rax
0x18009bdd2  mov     rbx, r8
0x18009bdd5  mov     rsi, rcx
0x18009bdd8  mov     r8d, 100h
0x18009bdde  lea     rdx, aRandD; "(%RAND:)(\\d+)(%)"
0x18009bde5  lea     rcx, [rsp+158h+var_B8]
0x18009bded  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18009bdf2  nop
0x18009bdf3  xor     r12d, r12d
0x18009bdf6  mov     [rsp+158h+var_128], r12
0x18009bdfb  mov     [rsp+158h+var_120], r12b
0x18009be00  xorps   xmm0, xmm0
0x18009be03  movdqa  [rsp+158h+var_118], xmm0
0x18009be09  xorps   xmm1, xmm1
0x18009be0c  movdqa  [rsp+158h+var_108], xmm1
0x18009be12  mov     [rsp+158h+var_F8], r12
0x18009be17  mov     [rsp+158h+var_F0], r12b
0x18009be1c  movdqa  [rsp+158h+var_E8], xmm0
0x18009be22  mov     [rsp+158h+var_D8], r12b
0x18009be2a  mov     [rsp+158h+var_D0], r12
0x18009be32  mov     [rsp+158h+var_C8], r12
0x18009be3a  mov     [rsp+158h+var_C0], r12b
0x18009be42  mov     [rbx], r12b
0x18009be45  lea     r8, [rsp+158h+var_B8]
0x18009be4d  lea     rdx, [rsp+158h+var_128]
0x18009be52  mov     rcx, rsi
0x18009be55  call    ??$regex_search@U?$char_traits@G@std@@V?$allocator@G@2@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<std::char_traits<ushort>,std::allocator<ushort>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x18009be5a  mov     rdi, 0AAAAAAAAAAAAAAABh
0x18009be64  test    al, al
0x18009be66  jz      loc_18009C16A
0x18009be6c  mov     byte ptr [rbx], 1
0x18009be6f  mov     rcx, qword ptr [rsp+158h+var_118]
0x18009be74  mov     rax, qword ptr [rsp+158h+var_118+8]
0x18009be79  sub     rax, rcx
0x18009be7c  sar     rax, 3
0x18009be80  imul    rax, rdi
0x18009be84  cmp     rax, 2
0x18009be88  ja      short loc_18009BE94
0x18009be8a  lea     rcx, [rsp+158h+var_D0]
0x18009be92  jmp     short loc_18009BE98
0x18009be94  add     rcx, 30h ; '0'
0x18009be98  lea     rdx, [rsp+158h+var_50]
0x18009bea0  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18009bea5  mov     rcx, rax
0x18009bea8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009bead  mov     rcx, rax
0x18009beb0  call    cs:__imp__o__wtoi
0x18009beb7  nop     dword ptr [rax+rax+00h]
0x18009bebc  mov     ebx, eax
0x18009bebe  or      r14d, 0FFFFFFFFh
0x18009bec2  test    eax, eax
0x18009bec4  cmovns  r14d, eax
0x18009bec8  sar     ebx, 1Fh
0x18009becb  lea     rcx, [rsp+158h+var_50]
0x18009bed3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bed8  and     ebx, 80070216h
0x18009bede  jns     short loc_18009BF49
0x18009bee0  mov     rcx, [rsp+158h]; this
0x18009bee8  mov     r9d, ebx; char *
0x18009beeb  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009bef2  mov     edx, 39h ; '9'; void *
0x18009bef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009befc  nop
0x18009befd  mov     rax, qword ptr [rsp+158h+var_118]
0x18009bf02  test    rax, rax
0x18009bf05  jz      short loc_18009BF35
0x18009bf07  mov     rcx, qword ptr [rsp+158h+var_108]
0x18009bf0c  sub     rcx, rax
0x18009bf0f  sar     rcx, 3
0x18009bf13  imul    rcx, rdi
0x18009bf17  lea     rdx, [rcx+rcx*2]
0x18009bf1b  shl     rdx, 3
0x18009bf1f  mov     rcx, rax
0x18009bf22  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009bf27  xorps   xmm0, xmm0
0x18009bf2a  movdqa  [rsp+158h+var_118], xmm0
0x18009bf30  mov     qword ptr [rsp+158h+var_108], r12
0x18009bf35  lea     rcx, [rsp+158h+var_B8]
0x18009bf3d  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18009bf42  mov     eax, ebx
0x18009bf44  jmp     loc_18009C1B4
0x18009bf49  lea     rdx, [rsp+158h+var_70]
0x18009bf51  lea     rcx, [rsp+158h+var_108+8]
0x18009bf56  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18009bf5b  nop
0x18009bf5c  lea     rdx, [rsp+158h+var_90]
0x18009bf64  lea     rcx, [rsp+158h+var_E8]
0x18009bf69  call    ?str@?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(void)
0x18009bf6e  nop
0x18009bf6f  mov     eax, r14d
0x18009bf72  add     rax, [rsp+158h+var_80]
0x18009bf7a  add     rax, [rsp+158h+var_60]
0x18009bf82  cmp     rax, 3Fh ; '?'
0x18009bf86  jbe     loc_18009C016
0x18009bf8c  mov     rcx, [rsp+158h]; this
0x18009bf94  mov     ebx, 8007092Fh
0x18009bf99  mov     r9d, ebx; char *
0x18009bf9c  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009bfa3  mov     edx, 3Eh ; '>'; void *
0x18009bfa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009bfad  nop
0x18009bfae  lea     rcx, [rsp+158h+var_90]
0x18009bfb6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bfbb  nop
0x18009bfbc  lea     rcx, [rsp+158h+var_70]
0x18009bfc4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bfc9  nop
0x18009bfca  mov     r8, qword ptr [rsp+158h+var_118]
0x18009bfcf  test    r8, r8
0x18009bfd2  jz      short loc_18009C002
0x18009bfd4  mov     rcx, qword ptr [rsp+158h+var_108]
0x18009bfd9  sub     rcx, r8
0x18009bfdc  sar     rcx, 3
0x18009bfe0  imul    rcx, rdi
0x18009bfe4  lea     rdx, [rcx+rcx*2]
0x18009bfe8  shl     rdx, 3
0x18009bfec  mov     rcx, r8
0x18009bfef  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009bff4  xorps   xmm0, xmm0
0x18009bff7  movdqa  [rsp+158h+var_118], xmm0
0x18009bffd  mov     qword ptr [rsp+158h+var_108], r12
0x18009c002  lea     rcx, [rsp+158h+var_B8]
0x18009c00a  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18009c00f  mov     eax, ebx
0x18009c011  jmp     loc_18009C1B4
0x18009c016  call    cs:__imp_GetCurrentThreadId
0x18009c01d  nop     dword ptr [rax+rax+00h]
0x18009c022  mov     ebx, eax
0x18009c024  call    cs:__imp_GetTickCount
0x18009c02b  nop     dword ptr [rax+rax+00h]
0x18009c030  xor     ebx, eax
0x18009c032  mov     ecx, ebx
0x18009c034  call    cs:__imp__o_srand
0x18009c03b  nop     dword ptr [rax+rax+00h]
0x18009c040  lea     rdx, [rsp+158h+var_70]
0x18009c048  mov     rcx, rsi
0x18009c04b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009c050  mov     ebx, r12d
0x18009c053  cmp     ebx, r14d
0x18009c056  jnb     loc_18009C13D
0x18009c05c  call    cs:__imp_rand
0x18009c063  nop     dword ptr [rax+rax+00h]
0x18009c068  mov     r9d, eax
0x18009c06b  mov     eax, 66666667h
0x18009c070  imul    r9d
0x18009c073  sar     edx, 2
0x18009c076  mov     eax, edx
0x18009c078  shr     eax, 1Fh
0x18009c07b  add     edx, eax
0x18009c07d  lea     eax, [rdx+rdx*4]
0x18009c080  add     eax, eax
0x18009c082  sub     r9d, eax
0x18009c085  lea     r8, aD; "%d"
0x18009c08c  mov     edx, 2; unsigned __int64
0x18009c091  lea     rcx, [rsp+158h+var_138]; unsigned __int16 *
0x18009c096  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009c09b  mov     r15d, eax
0x18009c09e  test    eax, eax
0x18009c0a0  jns     loc_18009C129
0x18009c0a6  mov     rcx, [rsp+158h]; this
0x18009c0ae  mov     r9d, eax; char *
0x18009c0b1  lea     r8, aOnecoreuapAdmi_45; "onecoreuap\\admin\\moderndeployment\\au"...
0x18009c0b8  mov     edx, 45h ; 'E'; void *
0x18009c0bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c0c2  nop
0x18009c0c3  lea     rcx, [rsp+158h+var_90]
0x18009c0cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009c0d0  nop
0x18009c0d1  lea     rcx, [rsp+158h+var_70]
0x18009c0d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009c0de  nop
0x18009c0df  mov     rcx, qword ptr [rsp+158h+var_118]
0x18009c0e4  test    rcx, rcx
0x18009c0e7  jz      short loc_18009C114
0x18009c0e9  mov     rax, qword ptr [rsp+158h+var_108]
0x18009c0ee  sub     rax, rcx
0x18009c0f1  sar     rax, 3
0x18009c0f5  imul    rax, rdi
0x18009c0f9  lea     rdx, [rax+rax*2]
0x18009c0fd  shl     rdx, 3
0x18009c101  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009c106  xorps   xmm0, xmm0
0x18009c109  movdqa  [rsp+158h+var_118], xmm0
0x18009c10f  mov     qword ptr [rsp+158h+var_108], r12
0x18009c114  lea     rcx, [rsp+158h+var_B8]
0x18009c11c  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18009c121  mov     eax, r15d
0x18009c124  jmp     loc_18009C1B4
0x18009c129  lea     rdx, [rsp+158h+var_138]
0x18009c12e  mov     rcx, rsi
0x18009c131  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18009c136  inc     ebx
0x18009c138  jmp     loc_18009C053
0x18009c13d  lea     rdx, [rsp+158h+var_90]
0x18009c145  mov     rcx, rsi
0x18009c148  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18009c14d  nop
0x18009c14e  lea     rcx, [rsp+158h+var_90]
0x18009c156  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009c15b  nop
0x18009c15c  lea     rcx, [rsp+158h+var_70]
0x18009c164  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009c169  nop
0x18009c16a  mov     rcx, qword ptr [rsp+158h+var_118]
0x18009c16f  test    rcx, rcx
0x18009c172  jz      short loc_18009C19F
0x18009c174  mov     rax, qword ptr [rsp+158h+var_108]
0x18009c179  sub     rax, rcx
0x18009c17c  sar     rax, 3
0x18009c180  imul    rax, rdi
0x18009c184  lea     rdx, [rax+rax*2]
0x18009c188  shl     rdx, 3
0x18009c18c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009c191  xorps   xmm0, xmm0
0x18009c194  movdqa  [rsp+158h+var_118], xmm0
0x18009c19a  mov     qword ptr [rsp+158h+var_108], r12
0x18009c19f  lea     rcx, [rsp+158h+var_B8]
0x18009c1a7  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18009c1ac  xor     eax, eax
0x18009c1ae  jmp     short loc_18009C1B4
0x18009c1b0  mov     eax, dword ptr [rsp+158h+var_138]
0x18009c1b4  mov     rcx, [rsp+158h+var_30]
0x18009c1bc  xor     rcx, rsp; StackCookie
0x18009c1bf  call    __security_check_cookie
0x18009c1c4  mov     rbx, [rsp+158h+arg_8]
0x18009c1cc  add     rsp, 130h
0x18009c1d3  pop     r15
0x18009c1d5  pop     r14
0x18009c1d7  pop     r12
0x18009c1d9  pop     rdi
0x18009c1da  pop     rsi
0x18009c1db  retn
```
