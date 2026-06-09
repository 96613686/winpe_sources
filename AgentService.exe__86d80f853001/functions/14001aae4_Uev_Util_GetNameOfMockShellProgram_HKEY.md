# Uev::Util::GetNameOfMockShellProgram(HKEY__ *)

- ea: `0x14001aae4`
- end: `0x14001accf`
- name: `?GetNameOfMockShellProgram@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHKEY__@@@Z`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14001b48c`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x14000ac88`
- `0x14000acc4`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000f01c`
- `0x1400191ec`
- `0x14001aae4`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14001ab7c`
- `ADVAPI32!RegGetValueW` at `0x14001abeb`
- `ADVAPI32!RegGetValueW` at `0x14001ab7c`
- `ADVAPI32!RegGetValueW` at `0x14001abeb`

## string_xrefs

- `0x14001ab1d`: `AgentService.Util::GetNameOfMockShellProgram: Entry`
- `0x14001ab8b`: `AgentService.Util::GetNameOfMockShellProgram: No mock shell program has been defined`
- `0x14001ab9e`: `AgentService.Util::GetNameOfMockShellProgram: ::RegGetValueW() [1] returned system error code 0x%lX`
- `0x14001abf7`: `AgentService.Util::GetNameOfMockShellProgram: ::RegGetValueW() [2] returned system error code 0x%lX`
- `0x14001ac77`: `AgentService.Util::GetNameOfMockShellProgram: Mock shell program is '%s'`
- `0x14001ac9b`: `AgentService.Util::GetNameOfMockShellProgram: Exit ['%s']`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int128 *__fastcall Uev::Util::GetNameOfMockShellProgram(__int128 *a1, HKEY a2)
{
  LSTATUS ValueW; // eax
  _WORD *pvData; // rdi
  unsigned __int64 v6; // r8
  __int128 v8; // [rsp+48h] [rbp-1h] BYREF
  __int128 v9; // [rsp+58h] [rbp+Fh]
  __int128 *v10; // [rsp+68h] [rbp+1Fh]
  _WORD *v11; // [rsp+70h] [rbp+27h]
  DWORD pcbData; // [rsp+78h] [rbp+2Fh] BYREF

  v10 = a1;
  DbgTrace<5>(L"AgentService.Util::GetNameOfMockShellProgram: Entry");
  pcbData = 0;
  *a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  std::wstring::_Construct<1,wchar_t *>(a1, &Data, 0);
  ValueW = RegGetValueW(a2, L"Software\\Microsoft\\UE-V\\test", L"MockShell", 2u, 0, 0, &pcbData);
  if ( ValueW )
  {
    if ( ValueW == 2 )
      DbgTrace<5>(L"AgentService.Util::GetNameOfMockShellProgram: No mock shell program has been defined");
    else
      DbgTraceFrmt<5,long>((wchar_t *)L"AgentService.Util::GetNameOfMockShellProgram: ::RegGetValueW() [1] returned system"
                                       " error code 0x%lX");
  }
  else
  {
    pvData = operator new[](pcbData + 2);
    v11 = pvData;
    if ( RegGetValueW(a2, L"Software\\Microsoft\\UE-V\\test", L"MockShell", 2u, 0, pvData, &pcbData) )
    {
      DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.Util::GetNameOfMockShellProgram: ::RegGetValueW() [2] returned syste"
                                        "m error code 0x%lX");
    }
    else
    {
      v8 = 0;
      v9 = 0u;
      v6 = -1;
      do
        ++v6;
      while ( pvData[v6] );
      std::wstring::_Construct<1,wchar_t *>(&v8, pvData, v6);
      if ( a1 != &v8 )
      {
        std::wstring::_Tidy_deallocate(a1);
        *a1 = v8;
        a1[1] = v9;
        *(_QWORD *)&v9 = 0;
        *((_QWORD *)&v9 + 1) = 7;
        LOWORD(v8) = 0;
      }
      std::wstring::_Tidy_deallocate(&v8);
      DbgTraceFrmt<5,wchar_t const *>((wchar_t *)L"AgentService.Util::GetNameOfMockShellProgram: Mock shell program is '%s'");
    }
    operator delete(pvData);
  }
  DbgTraceFrmt<5,wchar_t const *>((wchar_t *)L"AgentService.Util::GetNameOfMockShellProgram: Exit ['%s']");
  return a1;
}

```

## disassembly

```asm
0x14001aae4  mov     [rsp-8+arg_10], rbx
0x14001aae9  mov     [rsp-8+arg_18], rsi
0x14001aaee  push    rbp
0x14001aaef  push    rdi
0x14001aaf0  push    r14
0x14001aaf2  lea     rbp, [rsp-47h]
0x14001aaf7  sub     rsp, 90h
0x14001aafe  mov     rax, cs:__security_cookie
0x14001ab05  xor     rax, rsp
0x14001ab08  mov     [rbp+57h+var_20], rax
0x14001ab0c  mov     rsi, rdx
0x14001ab0f  mov     rbx, rcx
0x14001ab12  mov     [rbp+57h+var_38], rcx
0x14001ab16  xor     r14d, r14d
0x14001ab19  mov     [rbp+57h+var_60], r14d
0x14001ab1d  lea     rcx, aAgentserviceUt_35; "AgentService.Util::GetNameOfMockShellPr"...
0x14001ab24  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001ab29  mov     [rbp+57h+var_28], r14d
0x14001ab2d  xorps   xmm0, xmm0
0x14001ab30  movups  xmmword ptr [rbx], xmm0
0x14001ab33  mov     [rbx+10h], r14
0x14001ab37  mov     [rbx+18h], r14
0x14001ab3b  xor     r8d, r8d
0x14001ab3e  lea     rdx, Data
0x14001ab45  mov     rcx, rbx
0x14001ab48  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14001ab4d  mov     [rbp+57h+var_60], 1
0x14001ab54  lea     rax, [rbp+57h+var_28]
0x14001ab58  mov     [rsp+0A0h+pcbData], rax; pcbData
0x14001ab5d  mov     [rsp+0A0h+pvData], r14; pvData
0x14001ab62  mov     [rsp+0A0h+pdwType], r14; pdwType
0x14001ab67  lea     r9d, [r14+2]; dwFlags
0x14001ab6b  lea     r8, Value; "MockShell"
0x14001ab72  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\UE-V\\test"
0x14001ab79  mov     rcx, rsi; hkey
0x14001ab7c  call    cs:__imp_RegGetValueW
0x14001ab82  test    eax, eax
0x14001ab84  jz      short loc_14001ABAF
0x14001ab86  cmp     eax, 2
0x14001ab89  jnz     short loc_14001AB9C
0x14001ab8b  lea     rcx, aAgentserviceUt_38; "AgentService.Util::GetNameOfMockShellPr"...
0x14001ab92  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14001ab97  jmp     loc_14001AC8C
0x14001ab9c  mov     edx, eax
0x14001ab9e  lea     rcx, aAgentserviceUt_4; "AgentService.Util::GetNameOfMockShellPr"...
0x14001aba5  call    ??$DbgTraceFrmt@$04J@@YAXPEB_WJ@Z; DbgTraceFrmt<5,long>(wchar_t const *,long)
0x14001abaa  jmp     loc_14001AC8C
0x14001abaf  mov     ecx, [rbp+57h+var_28]
0x14001abb2  add     ecx, 2; unsigned __int64
0x14001abb5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14001abba  mov     rdi, rax
0x14001abbd  mov     [rbp+57h+var_30], rax
0x14001abc1  lea     rax, [rbp+57h+var_28]
0x14001abc5  mov     [rsp+0A0h+pcbData], rax; pcbData
0x14001abca  mov     [rsp+0A0h+pvData], rdi; pvData
0x14001abcf  mov     [rsp+0A0h+pdwType], r14; pdwType
0x14001abd4  mov     r9d, 2; dwFlags
0x14001abda  lea     r8, Value; "MockShell"
0x14001abe1  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\UE-V\\test"
0x14001abe8  mov     rcx, rsi; hkey
0x14001abeb  call    cs:__imp_RegGetValueW
0x14001abf1  test    eax, eax
0x14001abf3  jz      short loc_14001AC05
0x14001abf5  mov     edx, eax
0x14001abf7  lea     rcx, aAgentserviceUt_12; "AgentService.Util::GetNameOfMockShellPr"...
0x14001abfe  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001ac03  jmp     short loc_14001AC84
0x14001ac05  xorps   xmm0, xmm0
0x14001ac08  movups  [rbp+57h+var_58], xmm0
0x14001ac0c  mov     qword ptr [rbp+57h+var_48], r14
0x14001ac10  mov     qword ptr [rbp+57h+var_48+8], r14
0x14001ac14  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001ac18  inc     r8
0x14001ac1b  cmp     [rdi+r8*2], r14w
0x14001ac20  jnz     short loc_14001AC18
0x14001ac22  mov     rdx, rdi
0x14001ac25  lea     rcx, [rbp+57h+var_58]
0x14001ac29  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14001ac2e  lea     rax, [rbp+57h+var_58]
0x14001ac32  cmp     rbx, rax
0x14001ac35  jz      short loc_14001AC5F
0x14001ac37  mov     rcx, rbx
0x14001ac3a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001ac3f  movups  xmm0, [rbp+57h+var_58]
0x14001ac43  movups  xmmword ptr [rbx], xmm0
0x14001ac46  movups  xmm1, [rbp+57h+var_48]
0x14001ac4a  movups  xmmword ptr [rbx+10h], xmm1
0x14001ac4e  mov     qword ptr [rbp+57h+var_48], r14
0x14001ac52  mov     qword ptr [rbp+57h+var_48+8], 7
0x14001ac5a  mov     word ptr [rbp+57h+var_58], r14w
0x14001ac5f  lea     rcx, [rbp+57h+var_58]
0x14001ac63  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001ac68  cmp     qword ptr [rbx+18h], 7
0x14001ac6d  jbe     short loc_14001AC74
0x14001ac6f  mov     rdx, [rbx]
0x14001ac72  jmp     short loc_14001AC77
0x14001ac74  mov     rdx, rbx
0x14001ac77  lea     rcx, aAgentserviceUt_19; "AgentService.Util::GetNameOfMockShellPr"...
0x14001ac7e  call    ??$DbgTraceFrmt@$04PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<5,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001ac83  nop
0x14001ac84  mov     rcx, rdi; Block
0x14001ac87  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001ac8c  cmp     qword ptr [rbx+18h], 7
0x14001ac91  jbe     short loc_14001AC98
0x14001ac93  mov     rdx, [rbx]
0x14001ac96  jmp     short loc_14001AC9B
0x14001ac98  mov     rdx, rbx
0x14001ac9b  lea     rcx, aAgentserviceUt_18; "AgentService.Util::GetNameOfMockShellPr"...
0x14001aca2  call    ??$DbgTraceFrmt@$04PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<5,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001aca7  mov     rax, rbx
0x14001acaa  mov     rcx, [rbp+57h+var_20]
0x14001acae  xor     rcx, rsp; StackCookie
0x14001acb1  call    __security_check_cookie
0x14001acb6  lea     r11, [rsp+0A0h+var_10]
0x14001acbe  mov     rbx, [r11+30h]
0x14001acc2  mov     rsi, [r11+38h]
0x14001acc6  mov     rsp, r11
0x14001acc9  pop     r14
0x14001accb  pop     rdi
0x14001accc  pop     rbp
0x14001accd  retn
```
