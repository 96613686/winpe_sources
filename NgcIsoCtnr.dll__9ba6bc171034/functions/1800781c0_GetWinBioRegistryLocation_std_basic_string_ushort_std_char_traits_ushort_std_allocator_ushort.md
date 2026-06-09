# GetWinBioRegistryLocation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1800781c0`
- end: `0x1800782b0`
- name: `?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `240`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180077060`
- `0x180077b14`
- `0x180077db0`
- `0x180078070`

## callees

- `0x18000d62c`
- `0x180011c1c`
- `0x18001cf64`
- `0x18001ddec`
- `0x180069140`
- `0x1800781c0`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800781f3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180078263`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800781f3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180078263`

## string_xrefs

- `0x18007821f`: `onecore\ds\security\biometrics\service\common\biostatesep.cpp`
- `0x180078275`: `onecore\ds\security\biometrics\service\common\biostatesep.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetWinBioRegistryLocation(__int64 a1)
{
  int PersistedRegistryLocationW; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  _QWORD v6[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v8; // [rsp+68h] [rbp+10h] BYREF

  v8 = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WinBio",
                                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\",
                                 0,
                                 0);
  v3 = PersistedRegistryLocationW;
  if ( PersistedRegistryLocationW == 234 )
  {
    std::vector<unsigned char>::vector<unsigned char>(v6, v8);
    v4 = GetPersistedRegistryLocationW(L"WinBio", L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\", v6[0], v8);
    if ( v4 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1C,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\biostatesep.cpp",
             (const char *)v4,
             (unsigned int)&v8);
    }
    else
    {
      std::wstring::assign(a1, v6[0]);
      v3 = 0;
    }
    std::vector<unsigned char>::_Tidy(v6);
  }
  else
  {
    if ( PersistedRegistryLocationW > 0 )
      v3 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v3 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\biostatesep.cpp",
        (const char *)v3,
        (int)&v8);
  }
  return v3;
}

```

## disassembly

```asm
0x1800781c0  mov     [rsp+arg_0], rbx
0x1800781c5  push    rdi
0x1800781c6  sub     rsp, 50h
0x1800781ca  mov     rdi, rcx
0x1800781cd  mov     [rsp+58h+arg_8], 0
0x1800781d5  lea     rax, [rsp+58h+arg_8]
0x1800781da  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800781df  xor     r9d, r9d
0x1800781e2  xor     r8d, r8d
0x1800781e5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800781ec  lea     rcx, aWinbio; "WinBio"
0x1800781f3  call    cs:__imp_GetPersistedRegistryLocationW
0x1800781f9  mov     ebx, eax
0x1800781fb  cmp     eax, 0EAh
0x180078200  jz      short loc_180078232
0x180078202  test    eax, eax
0x180078204  jle     short loc_18007820F
0x180078206  movzx   ebx, ax
0x180078209  or      ebx, 80070000h
0x18007820f  test    ebx, ebx
0x180078211  jns     loc_1800782A3
0x180078217  mov     rcx, [rsp+58h]; this
0x18007821c  mov     r9d, ebx; char *
0x18007821f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\biometrics\\serv"...
0x180078226  mov     edx, 14h; void *
0x18007822b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078230  jmp     short loc_1800782A3
0x180078232  mov     edx, [rsp+58h+arg_8]
0x180078236  lea     rcx, [rsp+58h+var_28]
0x18007823b  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180078240  nop
0x180078241  lea     rax, [rsp+58h+arg_8]
0x180078246  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x18007824b  mov     r9d, [rsp+58h+arg_8]
0x180078250  mov     r8, [rsp+58h+var_28]
0x180078255  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18007825c  lea     rcx, aWinbio; "WinBio"
0x180078263  call    cs:__imp_GetPersistedRegistryLocationW
0x180078269  test    eax, eax
0x18007826b  jz      short loc_18007828A
0x18007826d  mov     rcx, [rsp+58h]; this
0x180078272  mov     r9d, eax; char *
0x180078275  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\biometrics\\serv"...
0x18007827c  mov     edx, 1Ch; void *
0x180078281  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180078286  mov     ebx, eax
0x180078288  jmp     short loc_180078299
0x18007828a  mov     rdx, [rsp+58h+var_28]
0x18007828f  mov     rcx, rdi
0x180078292  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180078297  xor     ebx, ebx
0x180078299  lea     rcx, [rsp+58h+var_28]
0x18007829e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800782a3  mov     eax, ebx
0x1800782a5  mov     rbx, [rsp+58h+arg_0]
0x1800782aa  add     rsp, 50h
0x1800782ae  pop     rdi
0x1800782af  retn
```
