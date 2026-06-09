# ArpApplication::GetInstallLocationFromCommandString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000da54`
- end: `0x18000ddb2`
- name: `?GetInstallLocationFromCommandString@ArpApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `862`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003caa8`
- `0x18003d33c`
- `0x180044110`

## callees

- `0x18000c270`
- `0x18000d834`
- `0x18000da54`
- `0x18000e458`
- `0x1800118d0`
- `0x1800150ac`
- `0x1800175b0`
- `0x180018300`
- `0x180018a60`
- `0x1800197d4`
- `0x18001e0d0`
- `0x18003e070`
- `0x1800404c4`
- `0x180046c3c`
- `0x180046d58`
- `0x180051410`
- `0x180052f28`
- `0x180059920`
- `0x180069330`
- `0x18012549c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000dbb0`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000dbb0`

## string_xrefs

- `0x18000dd49`: `Ignoring command line: %ws`
- `0x18000dd56`: `ArpApplication::GetInstallLocationFromCommandString`
- `0x18000dc50`: `uninst.dll`
- `0x18000dc79`: `ctor.dll`

## pseudocode

```c
__int64 __fastcall ArpApplication::GetInstallLocationFromCommandString(__int64 a1)
{
  int v2; // edi
  __int64 v3; // rdx
  _QWORD *v4; // rax
  _QWORD *v5; // rcx
  char *v6; // rsi
  char *v7; // rdx
  __int64 traits_2_0_unsigned_short; // rax
  __int64 v9; // r11
  __int64 v10; // rdx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  unsigned __int64 v13; // rsi
  _QWORD *v14; // rax
  __int64 v15; // rbx
  unsigned __int64 v16; // rsi
  char v17; // r15
  __int64 v18; // rax
  unsigned __int64 v19; // rbx
  _QWORD *v20; // rcx
  __int64 v21; // rax
  _QWORD *v22; // rcx
  bool v23; // bl
  __int64 v25; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+48h] [rbp-C0h]
  __int64 v27; // [rsp+50h] [rbp-B8h]
  __int64 v28; // [rsp+58h] [rbp-B0h]
  __int64 v29; // [rsp+60h] [rbp-A8h]
  _QWORD *v30; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+78h] [rbp-90h]
  unsigned __int64 v32; // [rsp+80h] [rbp-88h]
  _BYTE v33[16]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v34; // [rsp+98h] [rbp-70h]
  _BYTE v35[32]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v36[32]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v37[32]; // [rsp+E8h] [rbp-20h] BYREF

  v28 = -2;
  v29 = a1;
  std::wstring::wstring(a1);
  v2 = 1;
  std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(&v25);
  Utility::ToLower(&v30, v3);
  v4 = &v30;
  v5 = v30;
  if ( v32 > 7 )
    v4 = v30;
  v6 = (char *)v4 + 2 * v31;
  if ( v32 <= 7 )
  {
    v7 = (char *)&v30 + 2 * v31;
    v5 = &v30;
  }
  else
  {
    v7 = (char *)v30 + 2 * v31;
  }
  traits_2_0_unsigned_short = anonymous_namespace_::_Finding::_Find_impl__anonymous_namespace_::_Finding::_Find_traits_2_0_unsigned_short_(
                                v5,
                                v7,
                                34);
  v9 = traits_2_0_unsigned_short;
  if ( traits_2_0_unsigned_short != v10 )
    v9 = _std_remove_2(traits_2_0_unsigned_short);
  v11 = &v30;
  if ( v32 > 7 )
    v11 = v30;
  v12 = (v9 - (__int64)v11) >> 1;
  v13 = (__int64)&v6[-v9] >> 1;
  if ( v31 - v12 < v13 )
    v13 = v31 - v12;
  v14 = &v30;
  if ( v32 > 7 )
    v14 = v30;
  v15 = v31 - v13;
  memmove_0((char *)v14 + 2 * v12, (char *)v14 + 2 * v12 + 2 * v13, 2 * (v31 - v13 - v12) + 2);
  v31 = v15;
  v16 = 0;
  v17 = 0;
  do
  {
    v18 = std::wstring::find(&v30, L":\\", v16);
    v19 = v18;
    if ( v18 == -1 )
      break;
    if ( v18 )
    {
      v20 = &v30;
      if ( v32 > 7 )
        v20 = v30;
      if ( (unsigned int)_o_iswalpha(*((unsigned __int16 *)v20 + v18 - 1)) )
        --v19;
    }
    v21 = std::wstring::find(&v30, L":\\", v19 + 3);
    if ( v21 == -1 )
    {
      v16 = v31 - 1;
      v17 = 1;
    }
    else
    {
      v22 = &v30;
      if ( v32 > 7 )
        v22 = v30;
      v16 = std::_Traits_rfind_ch<std::char_traits<unsigned short>>(v22, v31, v21, 32);
    }
    if ( v16 >= v19 )
    {
      if ( v16 - v19 > 3 )
      {
        std::wstring::substr(&v30, v35, v19, v16 - v19);
        ArpApplication::GetFileLocationFromCommandString(v33, v35);
        v23 = 0;
        if ( v34 )
        {
          std::wstring::wstring(v37, L"uninst.dll");
          v2 |= 2u;
          if ( !(unsigned __int8)Utility::FoundSubstring(v37, v35) )
          {
            std::wstring::wstring(v36, L"ctor.dll");
            v2 |= 4u;
            if ( !(unsigned __int8)Utility::FoundSubstring(v36, v35) )
              v23 = 1;
          }
        }
        if ( (v2 & 4) != 0 )
        {
          v2 &= ~4u;
          std::wstring::~wstring(v36);
        }
        if ( (v2 & 2) != 0 )
        {
          v2 &= ~2u;
          std::wstring::~wstring(v37);
        }
        if ( v23 )
        {
          if ( v26 == v27 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v25, v26, v33);
          }
          else
          {
            std::wstring::wstring(v26, v33);
            v26 += 32;
          }
        }
        std::wstring::~wstring(v33);
        std::wstring::~wstring(v35);
      }
    }
    else
    {
      v16 = v19;
    }
  }
  while ( !v17 );
  if ( v25 == v26 )
    AslLogCallPrintf(
      3,
      (unsigned int)"ArpApplication::GetInstallLocationFromCommandString",
      1203,
      (unsigned int)"Ignoring command line: %ws");
  else
    std::wstring::operator=(a1, v26 - 32);
  std::wstring::~wstring(&v30);
  std::vector<std::wstring>::_Tidy(&v25);
  return a1;
}

```

## disassembly

```asm
0x18000da54  mov     rax, rsp
0x18000da57  push    rbp
0x18000da58  push    rsi
0x18000da59  push    rdi
0x18000da5a  push    r14
0x18000da5c  push    r15
0x18000da5e  lea     rbp, [rax-38h]
0x18000da62  sub     rsp, 110h
0x18000da69  mov     [rsp+130h+var_E0], 0FFFFFFFFFFFFFFFEh
0x18000da72  mov     [rax+18h], rbx
0x18000da76  mov     rax, cs:__security_cookie
0x18000da7d  xor     rax, rsp
0x18000da80  mov     [rbp+30h+var_30], rax
0x18000da84  mov     r14, rcx
0x18000da87  mov     [rsp+130h+var_D8], rcx
0x18000da8c  mov     dword ptr [rsp+130h+var_100], 0
0x18000da94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000da99  mov     edi, 1
0x18000da9e  mov     dword ptr [rsp+130h+var_100], edi
0x18000daa2  lea     rcx, [rsp+130h+var_F8]
0x18000daa7  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x18000daac  nop
0x18000daad  lea     rcx, [rsp+60h]
0x18000dab2  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18000dab7  nop
0x18000dab8  lea     rax, [rsp+60h]
0x18000dabd  mov     rcx, [rsp+60h]
0x18000dac2  cmp     [rsp+130h+var_B8], 7
0x18000dac8  cmova   rax, rcx
0x18000dacc  mov     rdx, [rsp+130h+var_C0]
0x18000dad1  lea     rsi, [rax+rdx*2]
0x18000dad5  jbe     short loc_18000DADD
0x18000dad7  lea     rdx, [rcx+rdx*2]
0x18000dadb  jmp     short loc_18000DAEB
0x18000dadd  lea     rax, [rsp+60h]
0x18000dae2  lea     rdx, [rax+rdx*2]
0x18000dae6  lea     rcx, [rsp+60h]
0x18000daeb  mov     r8d, 22h ; '"'
0x18000daf1  call    _anonymous_namespace____Finding___Find_impl__anonymous_namespace____Finding___Find_traits_2_0_unsigned_short_
0x18000daf6  mov     r11, rax
0x18000daf9  cmp     rax, rdx
0x18000dafc  jz      short loc_18000DB09
0x18000dafe  mov     rcx, rax
0x18000db01  call    __std_remove_2
0x18000db06  mov     r11, rax
0x18000db09  lea     rax, [rsp+60h]
0x18000db0e  cmp     [rsp+130h+var_B8], 7
0x18000db14  cmova   rax, [rsp+60h]
0x18000db1a  mov     rdx, r11
0x18000db1d  sub     rdx, rax
0x18000db20  sar     rdx, 1
0x18000db23  sub     rsi, r11
0x18000db26  sar     rsi, 1
0x18000db29  mov     rbx, [rsp+130h+var_C0]
0x18000db2e  mov     rax, rbx
0x18000db31  sub     rax, rdx
0x18000db34  cmp     rax, rsi
0x18000db37  cmovb   rsi, rax
0x18000db3b  lea     rax, [rsp+60h]
0x18000db40  cmp     [rsp+130h+var_B8], 7
0x18000db46  cmova   rax, [rsp+60h]
0x18000db4c  lea     rcx, [rax+rdx*2]; void *
0x18000db50  sub     rbx, rsi
0x18000db53  mov     r8, rbx
0x18000db56  sub     r8, rdx
0x18000db59  lea     r8, ds:2[r8*2]; Size
0x18000db61  lea     rdx, [rcx+rsi*2]; Src
0x18000db65  call    memmove_0
0x18000db6a  mov     [rsp+130h+var_C0], rbx
0x18000db6f  xor     esi, esi
0x18000db71  xor     r15b, r15b
0x18000db74  mov     r8, rsi
0x18000db77  lea     rdx, asc_180155348; ":\\"
0x18000db7e  lea     rcx, [rsp+60h]
0x18000db83  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18000db88  mov     rbx, rax
0x18000db8b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000db8f  jz      loc_18000DD27
0x18000db95  test    rax, rax
0x18000db98  jz      short loc_18000DBBD
0x18000db9a  lea     rcx, [rsp+60h]
0x18000db9f  cmp     [rsp+130h+var_B8], 7
0x18000dba5  cmova   rcx, [rsp+60h]
0x18000dbab  movzx   ecx, word ptr [rcx+rax*2-2]
0x18000dbb0  call    cs:__imp__o_iswalpha
0x18000dbb6  test    eax, eax
0x18000dbb8  jz      short loc_18000DBBD
0x18000dbba  dec     rbx
0x18000dbbd  lea     r8, [rbx+3]
0x18000dbc1  lea     rdx, asc_180155348; ":\\"
0x18000dbc8  lea     rcx, [rsp+60h]
0x18000dbcd  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18000dbd2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000dbd6  jnz     short loc_18000DBE5
0x18000dbd8  mov     rsi, [rsp+130h+var_C0]
0x18000dbdd  dec     rsi
0x18000dbe0  mov     r15b, 1
0x18000dbe3  jmp     short loc_18000DC0C
0x18000dbe5  lea     rcx, [rsp+60h]
0x18000dbea  cmp     [rsp+130h+var_B8], 7
0x18000dbf0  cmova   rcx, [rsp+60h]
0x18000dbf6  mov     r9d, 20h ; ' '
0x18000dbfc  mov     r8, rax
0x18000dbff  mov     rdx, [rsp+130h+var_C0]
0x18000dc04  call    ??$_Traits_rfind_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_rfind_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18000dc09  mov     rsi, rax
0x18000dc0c  cmp     rsi, rbx
0x18000dc0f  jnb     short loc_18000DC19
0x18000dc11  mov     rsi, rbx
0x18000dc14  jmp     loc_18000DD1E
0x18000dc19  mov     r9, rsi
0x18000dc1c  sub     r9, rbx
0x18000dc1f  cmp     r9, 3
0x18000dc23  jbe     loc_18000DD1E
0x18000dc29  mov     r8, rbx
0x18000dc2c  lea     rdx, [rbp+30h+var_90]
0x18000dc30  lea     rcx, [rsp+60h]
0x18000dc35  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000dc3a  nop
0x18000dc3b  lea     rdx, [rbp+30h+var_90]
0x18000dc3f  lea     rcx, [rbp+30h+var_B0]
0x18000dc43  call    ?GetFileLocationFromCommandString@ArpApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ArpApplication::GetFileLocationFromCommandString(std::wstring const &)
0x18000dc48  nop
0x18000dc49  cmp     [rbp+30h+var_A0], 0
0x18000dc4e  jz      short loc_18000DCA6
0x18000dc50  lea     rdx, aUninstDll; "uninst.dll"
0x18000dc57  lea     rcx, [rbp+30h+var_50]
0x18000dc5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000dc60  nop
0x18000dc61  or      edi, 2
0x18000dc64  mov     dword ptr [rsp+130h+var_100], edi
0x18000dc68  lea     rdx, [rbp+30h+var_90]
0x18000dc6c  lea     rcx, [rbp+30h+var_50]
0x18000dc70  call    ?FoundSubstring@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::FoundSubstring(std::wstring const &,std::wstring const &)
0x18000dc75  test    al, al
0x18000dc77  jnz     short loc_18000DCA6
0x18000dc79  lea     rdx, aCtorDll; "ctor.dll"
0x18000dc80  lea     rcx, [rbp+30h+var_70]
0x18000dc84  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000dc89  nop
0x18000dc8a  or      edi, 4
0x18000dc8d  mov     dword ptr [rsp+130h+var_100], edi
0x18000dc91  lea     rdx, [rbp+30h+var_90]
0x18000dc95  lea     rcx, [rbp+30h+var_70]
0x18000dc99  call    ?FoundSubstring@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::FoundSubstring(std::wstring const &,std::wstring const &)
0x18000dc9e  test    al, al
0x18000dca0  jnz     short loc_18000DCA6
0x18000dca2  mov     bl, 1
0x18000dca4  jmp     short loc_18000DCA8
0x18000dca6  xor     bl, bl
0x18000dca8  test    dil, 4
0x18000dcac  jz      short loc_18000DCBF
0x18000dcae  and     edi, 0FFFFFFFBh
0x18000dcb1  mov     dword ptr [rsp+130h+var_100], edi
0x18000dcb5  lea     rcx, [rbp+30h+var_70]
0x18000dcb9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dcbe  nop
0x18000dcbf  test    dil, 2
0x18000dcc3  jz      short loc_18000DCD5
0x18000dcc5  and     edi, 0FFFFFFFDh
0x18000dcc8  mov     dword ptr [rsp+130h+var_100], edi
0x18000dccc  lea     rcx, [rbp+30h+var_50]
0x18000dcd0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dcd5  test    bl, bl
0x18000dcd7  jz      short loc_18000DD0B
0x18000dcd9  mov     rax, [rsp+130h+var_F0]
0x18000dcde  cmp     rax, [rsp+130h+var_E8]
0x18000dce3  jz      short loc_18000DCF9
0x18000dce5  lea     rdx, [rbp+30h+var_B0]
0x18000dce9  mov     rcx, rax
0x18000dcec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000dcf1  add     [rsp+130h+var_F0], 20h ; ' '
0x18000dcf7  jmp     short loc_18000DD0B
0x18000dcf9  lea     r8, [rbp+30h+var_B0]
0x18000dcfd  mov     rdx, rax
0x18000dd00  lea     rcx, [rsp+130h+var_F8]
0x18000dd05  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18000dd0a  nop
0x18000dd0b  lea     rcx, [rbp+30h+var_B0]
0x18000dd0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dd14  nop
0x18000dd15  lea     rcx, [rbp+30h+var_90]
0x18000dd19  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dd1e  test    r15b, r15b
0x18000dd21  jz      loc_18000DB74
0x18000dd27  mov     rdx, [rsp+130h+var_F0]
0x18000dd2c  cmp     [rsp+130h+var_F8], rdx
0x18000dd31  jnz     short loc_18000DD69
0x18000dd33  lea     rax, [rsp+60h]
0x18000dd38  cmp     [rsp+130h+var_B8], 7
0x18000dd3e  cmova   rax, [rsp+60h]
0x18000dd44  mov     [rsp+20h], rax
0x18000dd49  lea     r9, aIgnoringComman; "Ignoring command line: %ws"
0x18000dd50  mov     r8d, 4B3h
0x18000dd56  lea     rdx, aArpapplication; "ArpApplication::GetInstallLocationFromC"...
0x18000dd5d  mov     ecx, 3
0x18000dd62  call    AslLogCallPrintf
0x18000dd67  jmp     short loc_18000DD76
0x18000dd69  add     rdx, 0FFFFFFFFFFFFFFE0h
0x18000dd6d  mov     rcx, r14
0x18000dd70  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000dd75  nop
0x18000dd76  lea     rcx, [rsp+60h]
0x18000dd7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000dd80  nop
0x18000dd81  lea     rcx, [rsp+130h+var_F8]
0x18000dd86  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000dd8b  mov     rax, r14
0x18000dd8e  mov     rcx, [rbp+30h+var_30]
0x18000dd92  xor     rcx, rsp; StackCookie
0x18000dd95  call    __security_check_cookie
0x18000dd9a  mov     rbx, [rsp+130h+arg_10]
0x18000dda2  add     rsp, 110h
0x18000dda9  pop     r15
0x18000ddab  pop     r14
0x18000ddad  pop     rdi
0x18000ddae  pop     rsi
0x18000ddaf  pop     rbp
0x18000ddb0  retn
```
