# GetWbclPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180058668`
- end: `0x180058968`
- name: `?GetWbclPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `768`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cd38`
- `0x180058970`
- `0x180058a40`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000d524`
- `0x18000eb18`
- `0x18000eb54`
- `0x18001a40c`
- `0x18001a42c`
- `0x18001be20`
- `0x18002386c`
- `0x18003f960`
- `0x180043884`
- `0x180058668`
- `0x180058db8`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x18005879c`
- `ntdll!RtlGetPersistedStateLocation` at `0x18005879c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180058884`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180058884`

## string_xrefs

- `0x180058795`: `TpmDriverLogPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall GetWbclPath(__int64 a1)
{
  int StringNoThrow; // eax
  unsigned int v3; // edi
  int PersistedStateLocation; // eax
  rsize_t v6; // rdx
  unsigned int v7; // ebx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rax
  int v13; // [rsp+20h] [rbp-6B8h]
  int v14; // [rsp+20h] [rbp-6B8h]
  rsize_t SourceSize; // [rsp+40h] [rbp-698h] BYREF
  _OWORD v16[2]; // [rsp+48h] [rbp-690h] BYREF
  _BYTE v17[40]; // [rsp+68h] [rbp-670h] BYREF
  unsigned __int16 Destination[264]; // [rsp+90h] [rbp-648h] BYREF
  WCHAR Buffer; // [rsp+2A0h] [rbp-438h] BYREF
  _BYTE v20[526]; // [rsp+2A2h] [rbp-436h] BYREF
  _BYTE Source[528]; // [rsp+4B0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6D8h] [rbp+0h]

  Buffer = 0;
  memset_0(v20, 0, 0x206u);
  v16[0] = 0;
  v16[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v16[0]) = 0;
  memset_0(Destination, 0, 0x208u);
  memset_0(Source, 0, 0x208u);
  LODWORD(SourceSize) = 0;
  StringNoThrow = HWSecurityRegistryManager::GetStringNoThrow(84, v16);
  v3 = StringNoThrow;
  if ( StringNoThrow >= 0 )
  {
    std::wstring::operator=(a1, v16);
    std::wstring::_Tidy_deallocate(v16);
    return 0;
  }
  if ( StringNoThrow != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
      (const char *)(unsigned int)StringNoThrow,
      v13);
    std::wstring::_Tidy_deallocate(v16);
    return v3;
  }
  LODWORD(SourceSize) = 520;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"TpmDriverLogPath",
                             0,
                             Destination,
                             1,
                             Source,
                             520,
                             &SourceSize);
  if ( PersistedStateLocation < 0 )
  {
    if ( PersistedStateLocation != -1073741275 )
    {
      v7 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0xD7,
             (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
             (const char *)(unsigned int)PersistedStateLocation,
             v14);
      std::wstring::_Tidy_deallocate(v16);
      return v7;
    }
  }
  else if ( (unsigned int)SourceSize > 2 )
  {
    if ( memcpy_s_0(Destination, v6, Source, (unsigned int)SourceSize) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
        (const char *)0x8000FFFFLL,
        v14);
      std::wstring::_Tidy_deallocate(v16);
      return 2147549183LL;
    }
    goto LABEL_15;
  }
  if ( !GetWindowsDirectoryW(&Buffer, 0x104u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE0,
                  (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
                  v8);
    std::wstring::_Tidy_deallocate(v16);
    return LastError;
  }
  v10 = StringCchPrintfW(Destination, 0x104u, L"%s\\Logs\\MeasuredBoot", &Buffer);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\base\\ngscb\\tpm\\lib\\wbclhelper\\wbclhelper.cpp",
      (const char *)(unsigned int)v10,
      v14);
    std::wstring::_Tidy_deallocate(v16);
    return v11;
  }
LABEL_15:
  v12 = std::wstring::wstring((__int64)v17, (__int64)Destination);
  std::wstring::operator=(a1, v12);
  std::wstring::_Tidy_deallocate(v17);
  std::wstring::_Tidy_deallocate(v16);
  return 0;
}

```

## disassembly

```asm
0x180058668  mov     [rsp+arg_8], rbx
0x18005866d  mov     [rsp+arg_10], rsi
0x180058672  push    rdi
0x180058673  sub     rsp, 6D0h
0x18005867a  mov     rax, cs:__security_cookie
0x180058681  xor     rax, rsp
0x180058684  mov     [rsp+6D8h+var_18], rax
0x18005868c  mov     rbx, rcx
0x18005868f  xor     eax, eax
0x180058691  mov     [rsp+6D8h+Buffer], ax
0x180058699  xor     edx, edx; Val
0x18005869b  mov     r8d, 206h; Size
0x1800586a1  lea     rcx, [rsp+6D8h+var_436]; void *
0x1800586a9  call    memset_0
0x1800586ae  xorps   xmm0, xmm0
0x1800586b1  movups  [rsp+6D8h+var_690], xmm0
0x1800586b6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800586be  movdqu  [rsp+6D8h+var_680], xmm1
0x1800586c4  xor     eax, eax
0x1800586c6  mov     word ptr [rsp+6D8h+var_690], ax
0x1800586cb  mov     esi, 208h
0x1800586d0  mov     r8d, esi; Size
0x1800586d3  xor     edx, edx; Val
0x1800586d5  lea     rcx, [rsp+6D8h+Destination]; void *
0x1800586dd  call    memset_0
0x1800586e2  mov     r8d, esi; Size
0x1800586e5  xor     edx, edx; Val
0x1800586e7  lea     rcx, [rsp+6D8h+Source]; void *
0x1800586ef  call    memset_0
0x1800586f4  mov     dword ptr [rsp+6D8h+SourceSize], 0
0x1800586fc  lea     rdx, [rsp+6D8h+var_690]
0x180058701  mov     ecx, 54h ; 'T'
0x180058706  call    ?GetStringNoThrow@HWSecurityRegistryManager@@SAJW4RegValues@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HWSecurityRegistryManager::GetStringNoThrow(HWSecurityRegistryManager::RegValues,std::wstring &)
0x18005870b  mov     edi, eax
0x18005870d  test    eax, eax
0x18005870f  js      short loc_180058730
0x180058711  lea     rdx, [rsp+6D8h+var_690]
0x180058716  mov     rcx, rbx
0x180058719  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005871e  nop
0x18005871f  lea     rcx, [rsp+6D8h+var_690]
0x180058724  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180058729  xor     eax, eax
0x18005872b  jmp     loc_180058942
0x180058730  cmp     edi, 80070002h
0x180058736  jz      short loc_180058766
0x180058738  mov     rcx, [rsp+6D8h]; this
0x180058740  mov     r9d, edi; char *
0x180058743  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x18005874a  mov     edx, 0B6h; void *
0x18005874f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058754  nop
0x180058755  lea     rcx, [rsp+6D8h+var_690]
0x18005875a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005875f  mov     eax, edi
0x180058761  jmp     loc_180058942
0x180058766  mov     dword ptr [rsp+6D8h+SourceSize], esi
0x18005876a  lea     rax, [rsp+6D8h+SourceSize]
0x18005876f  mov     [rsp+6D8h+var_6A8], rax
0x180058774  mov     [rsp+6D8h+var_6B0], esi
0x180058778  lea     rax, [rsp+6D8h+Source]
0x180058780  mov     qword ptr [rsp+6D8h+var_6B8], rax; int
0x180058785  mov     r9d, 1
0x18005878b  lea     r8, [rsp+6D8h+Destination]
0x180058793  xor     edx, edx
0x180058795  lea     rcx, aTpmdriverlogpa; "TpmDriverLogPath"
0x18005879c  call    cs:__imp_RtlGetPersistedStateLocation
0x1800587a2  test    eax, eax
0x1800587a4  js      loc_18005883F
0x1800587aa  cmp     dword ptr [rsp+6D8h+SourceSize], 2
0x1800587af  jbe     loc_180058875
0x1800587b5  mov     r9d, dword ptr [rsp+6D8h+SourceSize]; SourceSize
0x1800587ba  lea     r8, [rsp+6D8h+Source]; Source
0x1800587c2  lea     rcx, [rsp+6D8h+Destination]; Destination
0x1800587ca  call    memcpy_s_0
0x1800587cf  test    eax, eax
0x1800587d1  jz      short loc_180058806
0x1800587d3  mov     rcx, [rsp+6D8h]; this
0x1800587db  mov     ebx, 8000FFFFh
0x1800587e0  mov     r9d, ebx; char *
0x1800587e3  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x1800587ea  mov     edx, 0CDh; void *
0x1800587ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800587f4  nop
0x1800587f5  lea     rcx, [rsp+6D8h+var_690]
0x1800587fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800587ff  mov     eax, ebx
0x180058801  jmp     loc_180058942
0x180058806  lea     rdx, [rsp+6D8h+Destination]
0x18005880e  lea     rcx, [rsp+6D8h+var_670]
0x180058813  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180058818  mov     rdx, rax
0x18005881b  mov     rcx, rbx
0x18005881e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180058823  lea     rcx, [rsp+6D8h+var_670]
0x180058828  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005882d  nop
0x18005882e  lea     rcx, [rsp+6D8h+var_690]
0x180058833  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180058838  xor     eax, eax
0x18005883a  jmp     loc_180058942
0x18005883f  cmp     eax, 0C0000225h
0x180058844  jz      short loc_180058875
0x180058846  mov     rcx, [rsp+6D8h]; this
0x18005884e  mov     r9d, eax; char *
0x180058851  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x180058858  mov     edx, 0D7h; void *
0x18005885d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180058862  mov     ebx, eax
0x180058864  lea     rcx, [rsp+6D8h+var_690]
0x180058869  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005886e  mov     eax, ebx
0x180058870  jmp     loc_180058942
0x180058875  mov     edi, 104h
0x18005887a  mov     edx, edi; uSize
0x18005887c  lea     rcx, [rsp+6D8h+Buffer]; lpBuffer
0x180058884  call    cs:__imp_GetWindowsDirectoryW
0x18005888a  test    eax, eax
0x18005888c  jnz     short loc_1800588B8
0x18005888e  mov     rcx, [rsp+6D8h]; this
0x180058896  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x18005889d  lea     edx, [rdi-24h]; void *
0x1800588a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800588a5  mov     ebx, eax
0x1800588a7  lea     rcx, [rsp+6D8h+var_690]
0x1800588ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800588b1  mov     eax, ebx
0x1800588b3  jmp     loc_180058942
0x1800588b8  lea     r9, [rsp+6D8h+Buffer]
0x1800588c0  lea     r8, aSLogsMeasuredb; "%s\\Logs\\MeasuredBoot"
0x1800588c7  mov     rdx, rdi; unsigned __int64
0x1800588ca  lea     rcx, [rsp+6D8h+Destination]; unsigned __int16 *
0x1800588d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800588d7  mov     edi, eax
0x1800588d9  test    eax, eax
0x1800588db  jns     short loc_180058908
0x1800588dd  mov     rcx, [rsp+6D8h]; this
0x1800588e5  mov     r9d, eax; char *
0x1800588e8  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\tpm\\lib\\wbclhel"...
0x1800588ef  mov     edx, 0E3h; void *
0x1800588f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800588f9  nop
0x1800588fa  lea     rcx, [rsp+6D8h+var_690]
0x1800588ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180058904  mov     eax, edi
0x180058906  jmp     short loc_180058942
0x180058908  lea     rdx, [rsp+6D8h+Destination]
0x180058910  lea     rcx, [rsp+6D8h+var_670]
0x180058915  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005891a  mov     rdx, rax
0x18005891d  mov     rcx, rbx
0x180058920  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180058925  lea     rcx, [rsp+6D8h+var_670]
0x18005892a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005892f  nop
0x180058930  lea     rcx, [rsp+6D8h+var_690]
0x180058935  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005893a  xor     eax, eax
0x18005893c  jmp     short loc_180058942
0x18005893e  mov     eax, dword ptr [rsp+6D8h+SourceSize]
0x180058942  mov     rcx, [rsp+6D8h+var_18]
0x18005894a  xor     rcx, rsp; StackCookie
0x18005894d  call    __security_check_cookie
0x180058952  lea     r11, [rsp+6D8h+var_8]
0x18005895a  mov     rbx, [r11+18h]
0x18005895e  mov     rsi, [r11+20h]
0x180058962  mov     rsp, r11
0x180058965  pop     rdi
0x180058966  retn
```
