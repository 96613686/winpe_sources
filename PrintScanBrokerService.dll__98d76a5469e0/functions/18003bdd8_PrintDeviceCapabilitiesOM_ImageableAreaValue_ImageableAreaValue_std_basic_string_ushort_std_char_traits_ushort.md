# PrintDeviceCapabilitiesOM::ImageableAreaValue::ImageableAreaValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003bdd8`
- end: `0x18003bfcd`
- name: `??0ImageableAreaValue@PrintDeviceCapabilitiesOM@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `501`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003afc0`

## callees

- `0x1800028b0`
- `0x180002d40`
- `0x18000f8a8`
- `0x180013d68`
- `0x18001836c`
- `0x18003470c`
- `0x18003bdd8`
- `0x18003e614`
- `0x1800425d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003be9d`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18003be9d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003be83`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003becd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003bed8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003be83`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003becd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003bed8`

## string_xrefs

- `0x18003bf5e`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003bf88`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003bfb2`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
_DWORD *__fastcall PrintDeviceCapabilitiesOM::ImageableAreaValue::ImageableAreaValue(_DWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // r14
  _QWORD *v7; // rcx
  int v8; // eax
  _DWORD *v9; // rdx
  int v11; // [rsp+30h] [rbp-50h] BYREF
  __int128 v12; // [rsp+38h] [rbp-48h] BYREF
  __int64 v13; // [rsp+48h] [rbp-38h]
  _QWORD v14[4]; // [rsp+50h] [rbp-30h] BYREF

  v2 = a2;
  *a1 = -1;
  a1[1] = -1;
  a1[2] = -1;
  a1[3] = -1;
  if ( a2[3] <= 7u )
  {
    v4 = a2;
  }
  else
  {
    v4 = (_QWORD *)*a2;
    a2 = (_QWORD *)*a2;
  }
  if ( _std_count_trivial_2(v4, (char *)a2 + 2 * v2[2], 44) != 3 )
  {
    v11 = 7;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)&v11,
      (_DWORD)v2,
      (unsigned int)L"Invalid ImageableArea value format",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      1346);
  }
  v5 = 0;
  v12 = 0;
  v13 = 0;
  do
  {
    v6 = std::wstring::find(v2, 44, v5);
    std::wstring::substr(v2, v14, v5, v6 - v5);
    if ( !v14[2] )
    {
      v11 = 7;
      PrintDeviceCapabilitiesOM::Exception::Throw::Error(
        (unsigned int)&v11,
        (_DWORD)v2,
        (unsigned int)L"Invalid ImageableArea value format",
        (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        1364);
    }
    *(_DWORD *)_o__errno() = 0;
    v7 = v14;
    if ( v14[3] > 7u )
      v7 = (_QWORD *)v14[0];
    v8 = _o__wtol(v7);
    v11 = v8;
    if ( *((_QWORD *)&v12 + 1) == v13 )
    {
      std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v12, *((_QWORD *)&v12 + 1), &v11);
      v8 = v11;
    }
    else
    {
      **((_DWORD **)&v12 + 1) = v8;
      *((_QWORD *)&v12 + 1) += 4LL;
    }
    if ( !v8 && (*(_DWORD *)_o__errno() == 34 || *(_DWORD *)_o__errno() == 22) )
    {
      v11 = 7;
      PrintDeviceCapabilitiesOM::Exception::Throw::Error(
        (unsigned int)&v11,
        (_DWORD)v2,
        (unsigned int)L"ImageableArea value is not number",
        (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
        1373);
    }
    v5 = v6 + 1;
    std::wstring::_Tidy_deallocate(v14);
    v9 = (_DWORD *)v12;
  }
  while ( (unsigned __int64)((__int64)(*((_QWORD *)&v12 + 1) - v12) >> 2) < 4 );
  *a1 = *(_DWORD *)v12;
  a1[1] = v9[1];
  a1[2] = v9[2];
  a1[3] = v9[3];
  std::vector<unsigned int>::_Tidy(&v12);
  return a1;
}

```

## disassembly

```asm
0x18003bdd8  mov     [rsp-18h+arg_10], rbx
0x18003bddd  mov     [rsp-18h+arg_18], rsi
0x18003bde2  push    rbp
0x18003bde3  push    rdi
0x18003bde4  push    r14
0x18003bde6  mov     rbp, rsp
0x18003bde9  sub     rsp, 80h
0x18003bdf0  mov     rax, cs:__security_cookie
0x18003bdf7  xor     rax, rsp
0x18003bdfa  mov     [rbp+var_10], rax
0x18003bdfe  mov     rbx, rdx
0x18003be01  mov     rdi, rcx
0x18003be04  or      eax, 0FFFFFFFFh
0x18003be07  mov     [rcx], eax
0x18003be09  mov     [rcx+4], eax
0x18003be0c  mov     [rcx+8], eax
0x18003be0f  mov     [rcx+0Ch], eax
0x18003be12  cmp     qword ptr [rdx+18h], 7
0x18003be17  jbe     short loc_18003BE21
0x18003be19  mov     rcx, [rdx]
0x18003be1c  mov     rdx, rcx
0x18003be1f  jmp     short loc_18003BE24
0x18003be21  mov     rcx, rbx
0x18003be24  mov     r8d, 2Ch ; ','
0x18003be2a  mov     rax, [rbx+10h]
0x18003be2e  lea     rdx, [rdx+rax*2]
0x18003be32  call    __std_count_trivial_2
0x18003be37  cmp     rax, 3
0x18003be3b  jnz     loc_18003BFA3
0x18003be41  xor     esi, esi
0x18003be43  xorps   xmm0, xmm0
0x18003be46  movdqu  [rbp+var_48], xmm0
0x18003be4b  mov     [rbp+var_38], rsi
0x18003be4f  mov     edx, 2Ch ; ','
0x18003be54  mov     r8, rsi
0x18003be57  mov     rcx, rbx
0x18003be5a  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18003be5f  mov     r14, rax
0x18003be62  mov     r9, rax
0x18003be65  sub     r9, rsi
0x18003be68  mov     r8, rsi
0x18003be6b  lea     rdx, [rbp+var_30]
0x18003be6f  mov     rcx, rbx
0x18003be72  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18003be77  nop
0x18003be78  cmp     [rbp+var_20], 0
0x18003be7d  jz      loc_18003BF79
0x18003be83  call    cs:__imp__o__errno
0x18003be89  mov     dword ptr [rax], 0
0x18003be8f  lea     rcx, [rbp+var_30]
0x18003be93  cmp     [rbp+var_18], 7
0x18003be98  cmova   rcx, [rbp+var_30]
0x18003be9d  call    cs:__imp__o__wtol
0x18003bea3  mov     [rbp+var_50], eax
0x18003bea6  mov     rdx, qword ptr [rbp+var_48+8]
0x18003beaa  cmp     rdx, [rbp+var_38]
0x18003beae  jz      short loc_18003BEB9
0x18003beb0  mov     [rdx], eax
0x18003beb2  add     qword ptr [rbp+var_48+8], 4
0x18003beb7  jmp     short loc_18003BEC9
0x18003beb9  lea     r8, [rbp+var_50]
0x18003bebd  lea     rcx, [rbp+var_48]
0x18003bec1  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x18003bec6  mov     eax, [rbp+var_50]
0x18003bec9  test    eax, eax
0x18003becb  jnz     short loc_18003BEE3
0x18003becd  call    cs:__imp__o__errno
0x18003bed3  cmp     dword ptr [rax], 22h ; '"'
0x18003bed6  jz      short loc_18003BF4F
0x18003bed8  call    cs:__imp__o__errno
0x18003bede  cmp     dword ptr [rax], 16h
0x18003bee1  jz      short loc_18003BF4F
0x18003bee3  lea     rsi, [r14+1]
0x18003bee7  lea     rcx, [rbp+var_30]
0x18003beeb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003bef0  mov     rax, qword ptr [rbp+var_48+8]
0x18003bef4  mov     rdx, qword ptr [rbp+var_48]
0x18003bef8  sub     rax, rdx
0x18003befb  sar     rax, 2
0x18003beff  cmp     rax, 4
0x18003bf03  jb      loc_18003BE4F
0x18003bf09  mov     ecx, [rdx]
0x18003bf0b  mov     [rdi], ecx
0x18003bf0d  mov     ecx, [rdx+4]
0x18003bf10  mov     [rdi+4], ecx
0x18003bf13  mov     ecx, [rdx+8]
0x18003bf16  mov     [rdi+8], ecx
0x18003bf19  mov     ecx, [rdx+0Ch]
0x18003bf1c  mov     [rdi+0Ch], ecx
0x18003bf1f  lea     rcx, [rbp+var_48]
0x18003bf23  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18003bf28  mov     rax, rdi
0x18003bf2b  mov     rcx, [rbp+var_10]
0x18003bf2f  xor     rcx, rsp; StackCookie
0x18003bf32  call    __security_check_cookie
0x18003bf37  lea     r11, [rsp+80h+var_s0]
0x18003bf3f  mov     rbx, [r11+30h]
0x18003bf43  mov     rsi, [r11+38h]
0x18003bf47  mov     rsp, r11
0x18003bf4a  pop     r14
0x18003bf4c  pop     rdi
0x18003bf4d  pop     rbp
0x18003bf4e  retn
0x18003bf4f  mov     [rbp+var_50], 7
0x18003bf56  mov     [rsp+80h+var_60], 55Dh
0x18003bf5e  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003bf65  lea     r8, aImageableareaV; "ImageableArea value is not number"
0x18003bf6c  mov     rdx, rbx
0x18003bf6f  lea     rcx, [rbp+var_50]
0x18003bf73  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
0x18003bf79  mov     [rbp+var_50], 7
0x18003bf80  mov     [rsp+80h+var_60], 554h
0x18003bf88  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003bf8f  lea     r8, aInvalidImageab; "Invalid ImageableArea value format"
0x18003bf96  mov     rdx, rbx
0x18003bf99  lea     rcx, [rbp+var_50]
0x18003bf9d  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
0x18003bfa3  mov     [rbp+var_50], 7
0x18003bfaa  mov     [rsp+80h+var_60], 542h
0x18003bfb2  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003bfb9  lea     r8, aInvalidImageab; "Invalid ImageableArea value format"
0x18003bfc0  mov     rdx, rbx
0x18003bfc3  lea     rcx, [rbp+var_50]
0x18003bfc7  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
