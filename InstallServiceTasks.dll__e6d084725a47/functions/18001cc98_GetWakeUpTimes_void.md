# GetWakeUpTimes(void)

- ea: `0x18001cc98`
- end: `0x18001cf10`
- name: `?GetWakeUpTimes@@YA?AV?$vector@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@V?$allocator@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@3@@std@@XZ`
- size: `632`
- prototype: `_QWORD *__fastcall(_QWORD *, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d4e0`

## callees

- `0x18000556c`
- `0x180010170`
- `0x180014300`
- `0x180019d84`
- `0x18001a3a8`
- `0x18001cc98`
- `0x180020f8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18001cd37`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18001cd49`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18001cd66`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18001cd78`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18001cd37`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18001cd49`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18001cd66`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18001cd78`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001cdf9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001cdf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ccd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ce0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ccd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001ce0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cd09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cd09`

## string_xrefs

- `0x18001ceca`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001cefe`: `onecoreuap\enduser\winstore\installservice\lib\downloadandinstallpendingupdatesworker.cpp`
- `0x18001ce2f`: `TaskWakeUpIntervalInMins`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall GetWakeUpTimes(_QWORD *a1, int a2, int a3, int a4)
{
  __int64 v5; // rcx
  const char *StringRawBuffer; // r14
  wchar_t *v7; // rdi
  wchar_t v8; // cx
  unsigned int v9; // r8d
  unsigned int v10; // edx
  HSTRING v11; // rax
  _QWORD *v12; // rdx
  __int64 v14; // rdi
  __int64 ActiveHours; // rax
  __int64 v16; // rcx
  __int64 v17; // r14
  __int64 *v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HSTRING string; // [rsp+78h] [rbp+38h] BYREF
  HSTRING v23; // [rsp+80h] [rbp+40h] BYREF

  string = 0;
  Registry::GetValue<Microsoft::WRL::Wrappers::HString>((unsigned int)&v23, a2, a3, a4, (__int64)&string);
  WindowsDeleteString(string);
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  if ( v23 )
  {
    StringRawBuffer = (const char *)WindowsGetStringRawBuffer(v23, 0);
    v7 = (wchar_t *)StringRawBuffer;
    if ( StringRawBuffer )
    {
      do
      {
        v8 = *v7;
        if ( *v7 == 32 )
          v8 = *++v7;
        if ( !(unsigned int)_o_isdigit(v8)
          || !(unsigned int)_o_isdigit(v7[1])
          || v7[2] != 58
          || !(unsigned int)_o_isdigit(v7[3])
          || !(unsigned int)_o_isdigit(v7[4]) )
        {
          v19 = wil::verify_hresult<long>(2147942413LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x26,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
            (const char *)v19,
            (int)"Cannot parse wake up trigger times : %ws",
            StringRawBuffer,
            1);
        }
        v9 = v7[1] + 10 * *v7;
        if ( v9 >= 0x228 || (v10 = v7[4] + 10 * v7[3], v10 >= 0x24C) )
        {
          v20 = wil::verify_hresult<long>(2147942413LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x2D,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\downloadandinstallpendingupdatesworker.cpp",
            (const char *)v20,
            (int)"Invalid Hours:Min in the setting : %ws",
            StringRawBuffer,
            1);
        }
        v11 = (HSTRING)(600000000 * (v10 + 60 * v9 - 32208LL));
        string = v11;
        v12 = (_QWORD *)a1[1];
        if ( v12 == (_QWORD *)a1[2] )
        {
          std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(
            a1,
            v12,
            &string);
        }
        else
        {
          *v12 = v11;
          a1[1] += 8LL;
        }
        v7 = wcschr(v7, 0x20u);
      }
      while ( v7 );
    }
  }
  else
  {
    LODWORD(string) = 120;
    v14 = (int)Registry::GetValue<unsigned long>(
                 v5,
                 "S\x00O\x00F\x00T\x00W\x00A\x00R\x00E\x00\\\x00M\x00i\x00c\x00r\x00o\x00s\x00o\x00f\x00t\x00\\\x00W\x00i\x00n\x00d\x00o\x00w\x00s\x00\\\x00C\x00u\x00r\x00r\x00e\x00n\x00t\x00V\x00e\x00r\x00s\x00i\x00o\x00n\x00\\\x00I\x00n\x00s\x00t\x00a\x00l\x00l\x00S\x00e\x00r\x00v\x00i\x00c\x00e\x00\\\x00C\x00o\x00n\x00f\x00i\x00g\x00u\x00r\x00a\x00t\x00i\x00o\x00n",
                 L"TaskWakeUpIntervalInMins",
                 &string);
    ActiveHours = GetActiveHours();
    v16 = 36000000000LL * SHIDWORD(ActiveHours);
    v17 = 36000000000LL * ((int)ActiveHours + 24);
    while ( 1 )
    {
      string = (HSTRING)v16;
      if ( v16 >= v17 )
        break;
      v18 = (__int64 *)a1[1];
      if ( v18 == (__int64 *)a1[2] )
      {
        std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(
          a1,
          v18,
          &string);
        v16 = (__int64)string;
      }
      else
      {
        *v18 = v16;
        a1[1] += 8LL;
      }
      v16 += 600000000 * v14;
    }
  }
  WindowsDeleteString(v23);
  return a1;
}

```

## disassembly

```asm
0x18001cc98  mov     [rsp-28h+arg_0], rcx
0x18001cc9d  push    rbp
0x18001cc9e  push    rsi
0x18001cc9f  push    rdi
0x18001cca0  push    r12
0x18001cca2  push    r14
0x18001cca4  mov     rbp, rsp
0x18001cca7  sub     rsp, 40h
0x18001ccab  mov     rsi, rcx
0x18001ccae  mov     [rbp+var_10], 0
0x18001ccb5  mov     [rbp+string], 0
0x18001ccbd  lea     rax, [rbp+string]
0x18001ccc1  mov     qword ptr [rsp+40h+var_20], rax
0x18001ccc6  lea     rcx, [rbp+arg_10]
0x18001ccca  call    ??$GetValue@VHString@Wrappers@WRL@Microsoft@@@Registry@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUHKEY__@@PEBG1$$QEAV1234@@Z; Registry::GetValue<Microsoft::WRL::Wrappers::HString>(HKEY__ *,ushort const *,ushort const *,Microsoft::WRL::Wrappers::HString &&)
0x18001cccf  nop
0x18001ccd0  mov     rcx, [rbp+string]; string
0x18001ccd4  call    cs:__imp_WindowsDeleteString
0x18001ccda  mov     qword ptr [rsi], 0
0x18001cce1  mov     qword ptr [rsi+8], 0
0x18001cce9  mov     qword ptr [rsi+10h], 0
0x18001ccf1  mov     [rbp+var_10], 1
0x18001ccf8  cmp     [rbp+arg_10], 0
0x18001ccfd  jz      loc_18001CE24
0x18001cd03  xor     edx, edx; length
0x18001cd05  mov     rcx, [rbp+arg_10]; string
0x18001cd09  call    cs:__imp_WindowsGetStringRawBuffer
0x18001cd0f  mov     r14, rax
0x18001cd12  mov     rdi, rax
0x18001cd15  test    rax, rax
0x18001cd18  jz      loc_18001CE0B
0x18001cd1e  mov     r12d, 20h ; ' '
0x18001cd24  movzx   ecx, word ptr [rdi]
0x18001cd27  cmp     cx, r12w
0x18001cd2b  jnz     short loc_18001CD34
0x18001cd2d  add     rdi, 2
0x18001cd31  movzx   ecx, word ptr [rdi]
0x18001cd34  movzx   ecx, cx
0x18001cd37  call    cs:__imp__o_isdigit
0x18001cd3d  test    eax, eax
0x18001cd3f  jz      loc_18001CEA8
0x18001cd45  movzx   ecx, word ptr [rdi+2]
0x18001cd49  call    cs:__imp__o_isdigit
0x18001cd4f  test    eax, eax
0x18001cd51  jz      loc_18001CEA8
0x18001cd57  cmp     word ptr [rdi+4], 3Ah ; ':'
0x18001cd5c  jnz     loc_18001CEA8
0x18001cd62  movzx   ecx, word ptr [rdi+6]
0x18001cd66  call    cs:__imp__o_isdigit
0x18001cd6c  test    eax, eax
0x18001cd6e  jz      loc_18001CEA8
0x18001cd74  movzx   ecx, word ptr [rdi+8]
0x18001cd78  call    cs:__imp__o_isdigit
0x18001cd7e  test    eax, eax
0x18001cd80  jz      loc_18001CEA8
0x18001cd86  movzx   eax, word ptr [rdi]
0x18001cd89  lea     ecx, [rax+rax*4]
0x18001cd8c  movzx   eax, word ptr [rdi+2]
0x18001cd90  lea     r8d, [rax+rcx*2]
0x18001cd94  cmp     r8d, 228h
0x18001cd9b  jnb     loc_18001CEDC
0x18001cda1  movzx   eax, word ptr [rdi+6]
0x18001cda5  lea     ecx, [rax+rax*4]
0x18001cda8  movzx   eax, word ptr [rdi+8]
0x18001cdac  lea     edx, [rax+rcx*2]
0x18001cdaf  cmp     edx, 24Ch
0x18001cdb5  jnb     loc_18001CEDC
0x18001cdbb  imul    ecx, r8d, 3Ch ; '<'
0x18001cdbf  add     ecx, edx
0x18001cdc1  sub     rcx, 7DD0h
0x18001cdc8  imul    rax, rcx, 23C34600h
0x18001cdcf  mov     [rbp+string], rax
0x18001cdd3  mov     rdx, [rsi+8]
0x18001cdd7  cmp     rdx, [rsi+10h]
0x18001cddb  jz      short loc_18001CDE7
0x18001cddd  mov     [rdx], rax
0x18001cde0  add     qword ptr [rsi+8], 8
0x18001cde5  jmp     short loc_18001CDF3
0x18001cde7  lea     r8, [rbp+string]
0x18001cdeb  mov     rcx, rsi
0x18001cdee  call    ??$_Emplace_reallocate@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@?$vector@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@V?$allocator@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@3@@std@@AEAAPEAV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@1@QEAV231@$$QEAV231@@Z; std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(std::chrono::duration<__int64,std::ratio<1,10000000>> * const,std::chrono::duration<__int64,std::ratio<1,10000000>> &&)
0x18001cdf3  mov     edx, r12d; Ch
0x18001cdf6  mov     rcx, rdi; Str
0x18001cdf9  call    cs:__imp_wcschr
0x18001cdff  mov     rdi, rax
0x18001ce02  test    rax, rax
0x18001ce05  jnz     loc_18001CD24
0x18001ce0b  mov     rcx, [rbp+arg_10]; string
0x18001ce0f  call    cs:__imp_WindowsDeleteString
0x18001ce15  mov     rax, rsi
0x18001ce18  add     rsp, 40h
0x18001ce1c  pop     r14
0x18001ce1e  pop     r12
0x18001ce20  pop     rdi
0x18001ce21  pop     rsi
0x18001ce22  pop     rbp
0x18001ce23  retn
0x18001ce24  mov     dword ptr [rbp+string], 78h ; 'x'
0x18001ce2b  lea     r9, [rbp+string]
0x18001ce2f  lea     r8, aTaskwakeupinte; "TaskWakeUpIntervalInMins"
0x18001ce36  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; "S\x00O\x00F\x00T\x00W\x00A\x00R\x00E"...
0x18001ce3d  call    ??$GetValue@K@Registry@@YAKPEAUHKEY__@@PEBG1$$QEAK@Z; Registry::GetValue<ulong>(HKEY__ *,ushort const *,ushort const *,ulong &&)
0x18001ce42  movsxd  rdi, eax
0x18001ce45  call    ?GetActiveHours@@YA?AUActiveHours@@XZ; GetActiveHours(void)
0x18001ce4a  mov     rcx, rax
0x18001ce4d  shr     rcx, 20h
0x18001ce51  movsxd  rcx, ecx
0x18001ce54  mov     r8, 861C46800h
0x18001ce5e  imul    rcx, r8
0x18001ce62  add     eax, 18h
0x18001ce65  movsxd  r14, eax
0x18001ce68  imul    r14, r8
0x18001ce6c  mov     rdx, rcx
0x18001ce6f  mov     [rbp+string], rcx
0x18001ce73  cmp     rcx, r14
0x18001ce76  jge     short loc_18001CE0B
0x18001ce78  mov     rdx, [rsi+8]
0x18001ce7c  cmp     rdx, [rsi+10h]
0x18001ce80  jz      short loc_18001CE8C
0x18001ce82  mov     [rdx], rcx
0x18001ce85  add     qword ptr [rsi+8], 8
0x18001ce8a  jmp     short loc_18001CE9C
0x18001ce8c  lea     r8, [rbp+string]
0x18001ce90  mov     rcx, rsi
0x18001ce93  call    ??$_Emplace_reallocate@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@?$vector@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@V?$allocator@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@3@@std@@AEAAPEAV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@1@QEAV231@$$QEAV231@@Z; std::vector<std::chrono::duration<__int64,std::ratio<1,10000000>>>::_Emplace_reallocate<std::chrono::duration<__int64,std::ratio<1,10000000>>>(std::chrono::duration<__int64,std::ratio<1,10000000>> * const,std::chrono::duration<__int64,std::ratio<1,10000000>> &&)
0x18001ce98  mov     rcx, [rbp+string]
0x18001ce9c  imul    rdx, rdi, 23C34600h
0x18001cea3  add     rcx, rdx
0x18001cea6  jmp     short loc_18001CE6C
0x18001cea8  mov     ecx, 8007000Dh
0x18001cead  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001ceb2  mov     r9d, eax; char *
0x18001ceb5  mov     rcx, [rbp+28h]; this
0x18001ceb9  mov     [rsp+40h+var_18], r14; char *
0x18001cebe  lea     rax, aCannotParseWak; "Cannot parse wake up trigger times : %w"...
0x18001cec5  mov     qword ptr [rsp+40h+var_20], rax; int
0x18001ceca  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001ced1  mov     edx, 26h ; '&'; void *
0x18001ced6  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001cedc  mov     ecx, 8007000Dh
0x18001cee1  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001cee6  mov     r9d, eax; char *
0x18001cee9  mov     rcx, [rbp+28h]; this
0x18001ceed  mov     [rsp+40h+var_18], r14; char *
0x18001cef2  lea     rax, aInvalidHoursMi; "Invalid Hours:Min in the setting : %ws"
0x18001cef9  mov     qword ptr [rsp+40h+var_20], rax; int
0x18001cefe  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\installs"...
0x18001cf05  mov     edx, 2Dh ; '-'; void *
0x18001cf0a  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
