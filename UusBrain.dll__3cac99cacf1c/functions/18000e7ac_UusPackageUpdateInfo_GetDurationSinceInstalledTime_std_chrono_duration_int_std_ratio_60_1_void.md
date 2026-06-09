# UusPackageUpdateInfo::GetDurationSinceInstalledTime<std::chrono::duration<int,std::ratio<60,1>>>(void)

- ea: `0x18000e7ac`
- end: `0x18000e880`
- name: `??$GetDurationSinceInstalledTime@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@@UusPackageUpdateInfo@@QEBA?AV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@XZ`
- size: `212`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000c510`
- `0x180036ab4`

## callees

- `0x18000a2a8`
- `0x18000a4c8`
- `0x18000e7ac`
- `0x180028728`
- `0x180029644`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000e7d5`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000e7d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall UusPackageUpdateInfo::GetDurationSinceInstalledTime<std::chrono::duration<int,std::ratio<60,1>>>(
        __int64 a1,
        _DWORD *a2)
{
  unsigned __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rbx
  _DWORD *result; // rax
  _BYTE v8[16]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+30h] [rbp-30h]
  _BYTE v10[32]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+80h] [rbp+20h] BYREF

  v11 = 0;
  GetSystemTimePreciseAsFileTime(&v11);
  v4 = (unsigned int)v11 + ((unsigned __int64)HIDWORD(v11) << 32) - 116444736000000000LL;
  v5 = std::wstring::wstring(v10, UusPackageUpdateInfo::_keyInstalledTime);
  UusPackageUpdateInfo::GetStringOrEmpty(a1, (__int64)v8, v5);
  if ( v9 )
  {
    UusPackageUpdateInfo::StringToTimePoint(&v11, (__int64)v8);
    v6 = (__int64)(v4 - v11) / 600000000;
  }
  else
  {
    LODWORD(v6) = 0;
  }
  std::wstring::_Tidy_deallocate(v8);
  result = a2;
  if ( (int)v6 <= 0 )
    *a2 = 1;
  else
    *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x18000e7ac  mov     [rsp-8+arg_0], rbx
0x18000e7b1  mov     [rsp-8+arg_8], rsi
0x18000e7b6  mov     [rsp-8+arg_18], rdi
0x18000e7bb  push    rbp
0x18000e7bc  mov     rbp, rsp
0x18000e7bf  sub     rsp, 60h
0x18000e7c3  mov     rdi, rdx
0x18000e7c6  mov     rbx, rcx
0x18000e7c9  mov     [rbp+arg_10], 0
0x18000e7d1  lea     rcx, [rbp+arg_10]
0x18000e7d5  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18000e7db  mov     esi, dword ptr [rbp+arg_10+4]
0x18000e7de  shl     rsi, 20h
0x18000e7e2  mov     r8d, dword ptr [rbp+arg_10]
0x18000e7e6  mov     rcx, 0FE624E212AC18000h
0x18000e7f0  add     rsi, rcx
0x18000e7f3  add     rsi, r8
0x18000e7f6  lea     rdx, ?_keyInstalledTime@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyInstalledTime
0x18000e7fd  lea     rcx, [rbp+var_20]
0x18000e801  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000e806  mov     r8, rax
0x18000e809  lea     rdx, [rbp+var_40]
0x18000e80d  mov     rcx, rbx
0x18000e810  call    ?GetStringOrEmpty@UusPackageUpdateInfo@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V23@@Z; UusPackageUpdateInfo::GetStringOrEmpty(std::wstring)
0x18000e815  nop
0x18000e816  cmp     [rbp+var_30], 0
0x18000e81b  jnz     short loc_18000E821
0x18000e81d  xor     ebx, ebx
0x18000e81f  jmp     short loc_18000E850
0x18000e821  lea     rdx, [rbp+var_40]
0x18000e825  lea     rcx, [rbp+arg_10]
0x18000e829  call    ?StringToTimePoint@UusPackageUpdateInfo@@CA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; UusPackageUpdateInfo::StringToTimePoint(std::wstring const &)
0x18000e82e  sub     rsi, [rbp+arg_10]
0x18000e832  mov     rax, 1CA213D840BAF7D5h
0x18000e83c  imul    rsi
0x18000e83f  mov     rbx, rdx
0x18000e842  sar     rbx, 1Ah
0x18000e846  mov     rax, rbx
0x18000e849  shr     rax, 3Fh
0x18000e84d  add     rbx, rax
0x18000e850  lea     rcx, [rbp+var_40]
0x18000e854  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000e859  mov     rax, rdi
0x18000e85c  test    ebx, ebx
0x18000e85e  jle     short loc_18000E864
0x18000e860  mov     [rdi], ebx
0x18000e862  jmp     short loc_18000E86A
0x18000e864  mov     dword ptr [rdi], 1
0x18000e86a  lea     r11, [rsp+60h+var_s0]
0x18000e86f  mov     rbx, [r11+10h]
0x18000e873  mov     rsi, [r11+18h]
0x18000e877  mov     rdi, [r11+28h]
0x18000e87b  mov     rsp, r11
0x18000e87e  pop     rbp
0x18000e87f  retn
```
